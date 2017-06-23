<?php


//$api_url = 'http://api.openweathermap.org/data/2.5/weather?q=Sochi,ru&appid=2dfdb8a50127d69900c3c0e7eecc926f';

$file_name ='json_answer1.txt';

//$data = file_get_contents($api_url);

//$str = $data;

//$file = file_put_contents($file_name,$str);

$data2 = fopen($file_name,'rb');

$contents = fread($data2, filesize($file_name));

$contents = file_get_contents($api_url);

$array = json_decode($contents, true);



$city = $array['name'];

$sky = $array['weather'][0]['main'];


$temp = round(($array['main']['temp'])-273.15); //Переводим Кельвины в Цельсия и округляем


echo '<h1>Город '.$city.'</h1>';
echo '<p>Небо '.$sky.'</p>';
echo '<p>Температура '.$temp.' градусов Цельсия</p>';
?>



