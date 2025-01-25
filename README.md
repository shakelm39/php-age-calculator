
<?php 

    if(isset($_POST['calculate'])){

        //getting data form form and convert this string
        $birth_day = new DateTime(date("d-m-Y",strtotime($_POST['birthday'])));
        
        $cur_date = new DateTime(date('d.m.y'));
        //set difference two date object oriented
        $difference = $cur_date->diff($birth_day);
        
        
    }

?>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Birthday Calculator</title>
</head>
<body>
    <h2>Please Select Your Birthday</h2>
    <form action="" method="POST">
        <input type="date" name="birthday">
        <button type="submit" name="calculate">Calculate Age</button>
    </form>
    <p>
        <?php 

            if(isset($_POST['calculate'])){
                //checking null value
                if($_POST['birthday']==!null){
                    printf('Your age is: %d Years, %d months, %d days', $difference -> y, $difference -> m, $difference -> d);
                }else{
                    echo "Please Select Your birth date";
                }
            }
        
        ?>
    </p>
</body>
</html>
