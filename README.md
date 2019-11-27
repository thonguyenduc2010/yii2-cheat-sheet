# yii2-cheat-sheet

## Import CSV
    $handle = fopen($model->file, "r");
                     while (($fileop = fgetcsv($handle, 1000, ",")) !== false) 
                     {
                        $name = $fileop[0];
                        $age = $fileop[1];
                        $location = $fileop[2];
                        // print_r($fileop);exit();
                        $sql = "INSERT INTO details(name, age, location) VALUES ('$name', '$age', '$location')";
                        $query = Yii::$app->db->createCommand($sql)->execute();
                     }
