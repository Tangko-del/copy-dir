# copy-dir

<?php

$src_dir = 'E:\XAMPP\htdocs\Copyfolder';
$new_dir = 'E:\XAMPP\htdocs\NewCreatedFolder';
// 0777 for file permissions to change the directory
mkdir($new_dir,'0777');
$new_file_dir = 'E:\XAMPP\htdocs\NewCreatedFolder\newfile.html';
$old_file_dir = 'E:\XAMPP\htdocs\Copyfolder\clone.html';

//create new file in the directory
fopen($new_file_dir,"w");
fopen($old_file_dir,"w");

//copies file from old to new folder(not recomende)
copy($new_file_dir,$old_file_dir);

$curr_dir = getCwd();
$arr = scandir($src_dir);
print_r($arr);

//recomended for ccopying all files
foreach(scandir($src_dir) as $file){
    copy($src_dir.'/'.$file,$new_dir.'/'.$file);
}
echo $curr_dir;
fclose($old_file_dir);
fclose($new_file_dir);

?>
