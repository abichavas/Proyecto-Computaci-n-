# Proyecto-Computaci-n-
Código para Arduino
#include  <Servo.h>

Servo  miservo ;
const  int  pin_servo  =  2 ;
const  int  trig_pin  =  3 ;
const  int  echo_pin  =  4 ;
const  int  inter_time  =  200 ;
 tiempo  int =  0 ;

 configuración vacía () 
{
  de serie comenzar ( 9600 );
  miservo _ adjuntar ( servo_pin ,  500 ,  2400 );
  miservo _ escribir ( 90 );
  pinMode  ( trig_pin ,  SALIDA );
  pinMode  ( echo_pin ,  ENTRADA );
  retraso ( 3000 );
} 

 bucle vacío () 
{
   duración flotante ,  distancia ;
  escritura digital ( trig_pin , ALTO ); 
  retrasoMicrosegundos ( 1000 );
  escritura digital ( trig_pin , BAJO ); 
  duración  =  pulseIn  ( echo_pin ,  HIGH );
  distancia  =  ( duración / 2 ) / 29 ;
  de serie imprimir ( distancia );
  de serie println ( "cm" );
  tiempo  =  tiempo  +  inter_tiempo ;
  retraso ( entre_tiempo );
  si  ( distancia  <  10 )
  {
    para ( int  i  =  1500 ;  i  >=  1100 ;  i -= 25 ){
      miservo _ escribir Microsegundos ( i );
      de serie imprimir ( "2" );
      retraso ( 100 );
    }
    retraso ( 1000 );
    para ( int  i  =  1100 ;  i  <=  1500 ;  i += 25 ){
      miservo _ escribir Microsegundos ( i );
      de serie imprimir ( "1" );
      retraso ( 100 );
    }
  }
}
