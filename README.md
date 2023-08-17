<html>
<head>
<title>online shopping</title>
<link rel="stylesheet" type="text/css" href="onlineshop.css">
<script type="text/javascript">
<!--
var image1=new Image()
image1.src="slide1.jpg"
var image2=new Image()
image2.src="slide2.jpg"
var image3=new Image()
image3.src="slide3.jpg"
var image4=new Image()
image4.src="slide4.jpg"
//-->
</script>
<script src="reg_valid.js"></script>
</head>
<body>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
<small>FOR ANY QUERIES/SUGGESTION CALL ON:18001800</small>
<br><br><br>
<div id="header" style="background-image:url("title.jpg")">
<marquee behavior="alternate">WOMENSERA-ONE STOP SHOP FOR ALL TYPES OF WOMEN PRODUCTS</marquee>
<br><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp;
<table>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp;
<tr>
<td><a href="onlineshop.html">HOME</a></td>
<td><a href="apparels.html">APPARELS</a></td>
<td><a href="accessories.html">ACCESSORIES</a></td>
<td><a href="watches.html">WATCHES</a></td>
<td><a href="bags.html">BAGS</a></td>
<tr>
</table>
<br><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp;
<img src="slide1.jpg" name="slide" width="500" height="350">
<script>
<!--
//variable that will increment through the images
var step=1
function slideit(){
//if browser does not support the image object, exit.
if (!document.images)
return
document.images.slide.src=eval("image"+step+".sac")
if (step<4)
step++
else
step=1
//call function "slideit()" every 2.5 seconds
setTimeout("slideit()",1200)
}
Slideit ()
//-->
</script>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp;
&nbsp; &nbsp; &nbsp;
<div id="aside" style="background-color:#D8D8D8;height:320px;width:350px;float:right">
<h3 align="center"><b><u>REGISTER HERE!!!!</u></b></h3>
<form name="myForm" onsubmit="return validateForm()" action="register.php" method="post">
&nbsp; &nbsp; &nbsp;User Id:<input type="text" name="UserId"><br><br>
&nbsp; &nbsp; &nbsp;Username:<input type="text" name="UserName"><br><br>
&nbsp; &nbsp; &nbsp;Email id :&nbsp;<input type="text" name="Email"><br><br>
&nbsp; &nbsp; &nbsp;Password: <input type="password" name="Password"><br><br>
&nbsp; &nbsp; &nbsp;Address:&nbsp;&nbsp; <input type="text" name="Address"><br><br>
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <input type="submit"
value="submit">
</form>
</div>
</body>
</html>
<?php
include("page.php");
$localhost1='localhost';
$username='root';
$password='';
$con= mysqli_connect($localhost1,$username,$password) or exit('could not connect to server');
mysqli_select_db($con, 'online_shop') or exit('could not find the database');
$userid=$_POST['UserId'];
$name=$_POST['UserName'];
$email=$_POST['Email'];
$password=$_POST['Password'];
$address=$_POST['Address'];
$res="insert into
register(UserId,UserName,Email,Password,Address)values('$userid','$name','$email','$password','$address')";
$db=mysqli_query($con,$res);
echo'<center><div id="aside" style="background-color:#D8D8D8;height:200px;width:350px;float:">';
echo"<br>"." You have been successfully registered<br> Plzz remember your userid and password";
echo"</div></center>";
?>
<?php
include("page.php");
$localhost1='localhost';
$username='root';
$password='';
$con= mysqli_connect($localhost1,$username,$password) or exit('could not connect to server');
mysqli_select_db($con, 'online_shop') or exit('could not find the database');
$userid=$_POST['Id'];
$sql="select * from cart where UserId1='".$_POST['Id']."'";
$retval=mysqli_query( $con, $sql );
if(! $retval )
{
die('Could not get data: ' . mysql_error());
}
$sum=0;
#echo'<table><th><td></td>';
$sql="select distinct UserName1,Address1 from cart where UserId1='".$_POST['Id']."'";
$retval1=mysqli_query( $con, $sql );
if(! $retval1 )
{
die('Could not get data: ' . mysql_error());
}
while($row = mysqli_fetch_array($retval1))
{
echo'<center><div id="aside" style="background-color:#D8D8D8;height:50px;width:350px;float:">';
echo "<h4>User Name :{$row['UserName1']}<br>"."Address : {$row['Address1']}<br></h4>";
echo"</div></center>";
}
while($row = mysqli_fetch_array($retval))
{
echo'<center><div id="aside" style="background-color:#D8D8D8;height:120px;width:350px;border:2px solid darkred">';
# echo "User Name :{$row['UserName1']} <br> "."Address : {$row['Address1']} <br>";
echo "Product id :{$row['ProductId1']}<br><br> "."Product Name : {$row['ProductName1']}<br> ";
echo "Product Cost:{$row['ProductCost1']}<br>";
$productid1=$row['ProductId1'];
echo'<form action="del.php" method="post"><input type="hidden" name="Uid" id="Uid" value="'.$userid.'"><input
type="checkbox" name="Pid" id="Pid" value="'.$productid1.'">';
echo '<input type="submit" value="delete"></form> ';
echo"</div></center>";
$sum=$sum+$row['ProductCost1'];
}
echo'<center><div id="aside" style="background-color:#D8D8D8;height:50px;width:350px;float:">';
echo "<h4>Total cost:".$sum;echo"</h4></div></center>";
?>
