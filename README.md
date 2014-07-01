EJERCICIOS-PHP
==============

MOREIRA BRAVO DIEGO ARMANDO-CARVAJAL TUMBACO ANELL DORALISA
<?php

/***********************************
echo ejercicio_1(8,9);

    function ejercicio_1($x,$y){
        $a = array(7,6,8,4,9,2,10,0,11,-2);
        if($x<=0 || $x>255 || $y<=0 || $y>255 ){
         return -1;   
        }else{
            
            return $a[$x-1]+$a[$y-1];
        }    
    }
    */
/*********************************
echo ejercicio_2(3,4); 
    
    function ejercicio_2($x, $y){
        
        $semilla=$x;
        if($x<=0 || $x>255 || $y<=0 || $y>255 ){
             return -1; 
        }else{
        
        for($i=2; $i<=$y; $i++){
           $semilla*=$i;
           }
       }
       return $semilla;
            
    }    
*/
/****************************
echo ejercicio_3(60,8); 
    
    function ejercicio_3($x, $y){
        
        $semilla=$x;
        if($x<=0 || $x>255 || $y<=0 || $y>255 ){
             return -1; 
        }else{
        
        for($i=2; $i<=$y; $i++){
           $semilla=$x/$i;
           }
       }
       return $semilla;
            
    }   */
    
/**************************  echo "la cadena 1 se diferencia de la segunda por \"".ejercicio_4("La vida es bella","El santo")."\""; 
    
    function ejercicio_4($x, $y){
        
        for($i=0; $i<strlen($y); $i++){
            $c=substr($y,$i,1);
            $total="";
            for($j=0; $j<strlen($x); $j++){
                 $f=substr($x,$j,1);
                if(strtoupper($c)!=strtoupper($f)){
                   $total.=$f;
                }
            }
            
         $x=$total;
         
        }
    return $total;
    }    
 */
/***********************************
$x=array(-3,-2,0,0,5,7,9,11,11,25);
print_r(ejercicio_5($x)); 
    
    function ejercicio_5($i){
        return array_values(array_unique($i));;
    }    
 
*/
/**********************************
ejercicio_6("hola soy carlos, y todo bien");

function ejercicio_6($str){
    $a=explode(" ",$str);
    for($i=count($a)-1;$i>=0;$i--){
        echo " ".$a[$i];
    }
}
*/

/*******************************************
 echo ejercicio_7("Cadena , !/+FFFca 122434");
 
 function ejercicio_7($str){
    $a=array("A","B","C","D","E","F","G","H","I","J","K","L","M","N","Ñ","O","P","Q","R","S","T","U","V","W","X","Y","Z");
    $total="";
    $f=true;
    for($i=0;$i<strlen($str);$i++){
        $c=substr($str,$i,1);
        for($j=0;$j<count($a);$j++){
            if($c==$a[$j]){
                $total.=chr(ord($c)+32);
                $f=false;
                break;
            }else{
                $f=true;
            }
        }
        if($f){
            $total.=$c;
        }
    }
    return $total;
 }*/

 /**********************************
 echo ejercicio_8(". Ah, este es un texto de muestra, que da una lid de análisis" );
 
 function ejercicio_8($str){
    $total=0;
    $siHayA=false;
    for($i=0;$i<strlen($str);$i++){
        $c=substr($str,$i,1);
        if($c=="a" || $c=="A"){
            $siHayA=true;
        }
        if($c==" " || $i==strlen($str)-1){
            if($siHayA){
               $total+=1; 
            }
            $siHayA=false;
        }
    }
    return $total;
 }
*/

/**************************
if(ejercicio_9(16)){
    echo "es correcto";
}else{
    echo "es falso";
}

function ejercicio_9($num){
    for($i=1;($i*$i)<$num;$i++){  
    }
    if(($i*$i)==$num){
            return true;            
    }else{
        return false;
    } 
}*/

/*******************************
echo ejercicio_10(1,7);
 function ejercicio_10($x,$y){
    for($i=$x;$i<=$y;$i++){
        if(EsNumeroPerfecto($i)){
            return $i;
        }
    }
    return -1;
}
function EsNumeroPerfecto($num){
    $total=0;
    for($j=1;$j<$num;$j++){
      if($num%$j==0){
        $total+=$j;
      } 
    }
    if($total==$num){
        return true;
    }else{
        return false;
    }
}
*/

/*********************

$mat=array(1,5,3,-2,4,2,4,-2,5,5,2,1,3);
echo ejercicio_11($mat);

function ejercicio_11($array){
    $cont=0;
    $repetidos = 0;
    $valor=0;
    $ya_duplicados = array();
    foreach($array as $item){
        
        for($u=0;$u<sizeof($array); $u++){
            if($item == $array[$u] && !in_array($item, $ya_duplicados)){
                ++$cont;
                if($repetidos<=$cont){
                    $repetidos=$cont;
                    $valor=$item;
                }
            }
        }
        
        if($cont >= 2){
            array_push($ya_duplicados, $item);
        }
        $cont=0;
        
    }
    return $valor;
    
}
****************************/

/***********************
 $a=array(-7, 1, 5, 2, -4, 3, 0);
 echo ejercicio_12($a);
 
function ejercicio_12($arr){
    $v1=0;
    $v2=0;
    for($i=0;$i<count($arr);$i++){
        for($j=0;$j<count($arr);$j++){
            if($j<$i){
                $v1+=$arr[$j];
            }
            if($j>$i){
                $v2+=$arr[$j];
            }
        }
        if($v1==$v2){
            return $i;
        }
        $v1=$v2=0;
    }
    return -1;
 }

************************/

/*******************************
$a=array(4,-3,-100,7,0,1,-6);
foreach(ejercicio_13($a) as $lista){
    echo $lista.", ";
}

function ejercicio_13($ar){
    $nueva=array();
    foreach($ar as $item){
        if($item<0){
           array_push($nueva,$item);
        }
    }
    foreach($ar as $item){
       if($item>=0){
           array_push($nueva,$item);
        } 
    }
    return $nueva;
}

******************************/


/********************************
echo ejercicio_14(5,3,3);

    function ejercicio_14($x,$y,$z){
        $a=array();
        if($x<=0 || $x>255 || $y<=0 || $y>255 || $z<=0 || $z>255){
         return -1;   
        }else{
            for($i=0;$i<$z;$i++){
                array_push($a,($x+$i).($y+$i));
                array_push($a,($y+$i).($x+$i));
            }
            return $a[$z-1];
        }
        return -1;  
    }
***********************************/


?>

<?php
/***********************************

echo ejercicio_17("doscientos cincuenta y cinco");

function ejercicio_17($pal){
    $pal=strtolower($pal);
    $a1=array("cero","uno","dos","tres","cuatro","cinco","seis","siete","ocho","nueve");
    $a2=array("diez","once","doce","trece","catorce","quince", "dieciseis", "diecisiete", "dieciocho", "diecinueve","veinte");
    $a3=array("veinte","treinta","cuarenta","cincuenta","sesenta", "setenta","ochenta","noventa","-","-");
    $a4=array("ciento","doscientos");
    $sum=0;
    $sum2=0;
    $sum3=-1;
    for($i=0;$i<=200;$i++){
        //del 0 al 9
        if($i<10){
            if($a1[$i]==$pal){
                return $i;
            }
        }
        //del 10 al 20
        if($i>=10 && $i<21){
            if($a2[$sum]==$pal){
                return $i;
            }
            $sum++;
        }
        //del 21 al 99
        
        if($i>=21 && $i<100){ 
            if($i%10==0){
               $sum2++; 
            }
            if($a3[$sum2]==$pal){
                return $i;
            }else{
                for($j=1;$j<10;$j++){
                    if(("veinti".$a1[$j])==$pal || ($a3[$sum2]." y ".$a1[$j])==$pal){
                        if($i<30){
                            return $i+$j-1;
                        }else{
                        return $i+$j;
                        }
                    }
                }
            }
        }
        //del 100 al 255
        if($i>=100){
            if($i%100==0){
                $sum3++;
            }
            if($a4[$sum3]==$pal || substr($a4[$sum3],0,4)==$pal){
                return $i;
            }else{
               for($j=0;$j<10;$j++){
                    if(($a4[$sum3]." ".$a1[$j])==$pal){
                        return $i+$j;
                    }
                    if(($a4[$sum3]." ".$a2[$j])==$pal){
                         return $i+10+$j;
                    }
                    if(($a4[$sum3]." ".$a3[$j])==$pal){
                        return $i+(($j+2)*10);
                    }
                    for($x=1;$x<10;$x++){
                        if(($a4[$sum3]." veinti".$a1[$x])==$pal || ($a4[$sum3]." ".$a3[$j]." y ".$a1[$x])==$pal){
                            $superior=$i+(($j+2)*10)+$x;
                            if($superior<=255){
                                return $superior;
                            }else{
                                return -1;
                            }
                            }
                    }
               } 
            }          
        }
    }
    return -1;
}


***************************************************/
/*******************************
$matriz=array("test","concurso","programación","más");
foreach(ejercicio_18($matriz) as $item){
        echo $item."<br/>";
    }
function ejercicio_18($a){
    for($j=0;$j<count($a);$j++){
        for($i=0;$i<count($a)-$j-1;$i++){
            $y= substr($a[$i],0,1);
            $x= substr($a[$i+1],0,1);
            if($y>=$x){
                $auxiliar=$a[$i];
                $a[$i]=$a[$i+1];
                $a[$i+1]=$auxiliar;
            }
        }
        
    }
    return $a;
       
}

*************************/

/*******************
echo ejercicio_19(25);
function ejercicio_19($eb){
    $total=0;
    //2^32=4294967296 numero de 32 bits
    if($eb<(4294967296)){
        $eb=decbin($eb);
        for($i=0;$i<strlen($eb);$i++){
            $total+=substr($eb,$i,1);
        }
        return $total;
    }else{
        return -1;
    }
}
*******************/
/****************
echo ejercicio_20(4);
function ejercicio_20($n){
    //ta jodido
    $cabeza=exp(M_PI*sqrt((2*$n)/3));
    return $cabeza/(4*$n*sqrt(3));
    //no vale
    
}
********************/

/************************
$array = array(array("a","b","c"),
                array("d","e","f"),
                array("g","h","i"));
                
echo ejercicio_21($array);
function ejercicio_21($a){
    $j=$k=-1;
    $cont=0;
    $val=0;
    $total="";
    $casillas = count($a)*count($a[0]);
    $columnas=count($a);
    $filas=count($a[0]);
    do{
        ++$j;
        ++$k;
        for($j;$j<$columnas-$val;++$j){
           ++$cont;
           $total.=$a[$k][$j];
        }
            --$j;
            ++$k;
        for($k;$k<$filas-$val;++$k){
           ++$cont;
           $total.=$a[$k][$j];
        }
           --$k;
           --$j;
        for($j;$j>0+$val;--$j){
           ++$cont;
           $total.=$a[$k][$j];
        }
        
        for($k;$k>0+$val;--$k){
           ++$cont;
           $total.=$a[$k][$j];
        }
        $val += 1;
    }while($cont!=$casillas);
    return $total;
}
******************/

/**************************+
$array = array(array(5,4,7),
                array(1,2,3),
                array(3,2,1));
                
echo ejercicio_22($array);
function ejercicio_22($a){
    $j=$k=-1;
    $cont=0;
    $val=0;
    $total="";
    $v1=0;
    $casillas = count($a)*count($a[0]);
    $columnas=count($a);
    $filas=count($a[0]);
    do{
        ++$j;
        ++$k;
        for($j;$j<$columnas-$val;++$j){
           ++$cont;
           $total.=$a[$k][$j];
        }
            --$j;
            ++$k;
        for($k;$k<$filas-$val;++$k){
           ++$cont;
           $total.=$a[$k][$j];
        }
           --$k;
           --$j;
        for($j;$j>0+$val;--$j){
           ++$cont;
           $total.=$a[$k][$j];
        }
        
        for($k;$k>0+$val;--$k){
           ++$cont;
           $total.=$a[$k][$j];
        }
        $val += 1;
    }while($cont!=$casillas);
    $operacion=0;
    for($i=0;$i<strlen($total);$i++){
        if($operacion<=1){
            $v1+=substr($total,$i,1);
            $operacion++;
        }else
        if($operacion==2){
            $v1-=substr($total,$i,1);
            $operacion++;
        }else
        if($operacion==3){
            $v1*=substr($total,$i,1);
            $operacion=1;
        }
    }
    return $v1;
}

***********************/

?>
