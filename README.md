userid=$_POST['Id'];
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
while($row =
