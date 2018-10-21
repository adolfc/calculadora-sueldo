# calculadora-sueldo

/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package calcularsueldo;

import javax.swing.JOptionPane;

/**
 *
 * @author Adolf
 */
public class CalcularSueldo {

    /**
     * @param args the command line arguments
     */
   
    public static void main(String[] args){
        JOptionPane.showMessageDialog(null,"Programa que Calcule Sueldo del Empleado");
        String empleado;
        int codigo,tipoe,diast,retardos,horasextra,importe=0,bono=0,descuento=0,sueldo=0;
        
        codigo = Integer.parseInt(JOptionPane.showInputDialog("Codigo:"));
        empleado = JOptionPane.showInputDialog("Nombre del Empleado:");
        tipoe = Integer.parseInt(JOptionPane.showInputDialog("Tipo de Cargo que Ocupa:"));
        diast = Integer.parseInt(JOptionPane.showInputDialog("Dias Trabajados en el Mes:"));
        retardos = Integer.parseInt(JOptionPane.showInputDialog("Retardos:"));
        horasextra = Integer.parseInt(JOptionPane.showInputDialog("Horas extras:"));
        if(tipoe==1){
            importe=350*diast;
        }
        if(tipoe==2){
            importe=250*diast;
        }
        if(tipoe==3){
            importe=125*diast;
        }
        if(horasextra>=1 && horasextra<=5){
            bono=horasextra*100;
        }
        if(horasextra>=6 && horasextra<=10){
            bono=500+((horasextra-5)*150);
        }
        if(horasextra>=11 && horasextra<=15){
            bono=1250+((horasextra-10)*275);
        }
        if(retardos>=1 && retardos<=5){
            descuento=retardos*50;
        }
        if(retardos>=6 && retardos<=10){
            descuento=250+((retardos-5)*75);
        }
        if(retardos>=11 && retardos<=15){
            descuento=625+((retardos-10)*100);
        }
        sueldo=(importe+bono)-descuento;
        
        String imprimir="";
        imprimir=imprimir+("Codigo:"+codigo+"\n");
        imprimir=imprimir+("Nombre del Empleado:"+empleado+"\n");
        imprimir=imprimir+("Tipo de Cargo que Ocupa:"+tipoe+"\n");
        imprimir=imprimir+("Dias Trabajados en el mes:"+diast+"\n");
        imprimir=imprimir+("Retardos:"+retardos+"\n");
        imprimir=imprimir+("Horas Extras:"+horasextra+"\n");
        imprimir=imprimir+("Importe:"+importe+"\n");
        imprimir=imprimir+("Bono:"+bono+"\n");
        imprimir=imprimir+("Descuento:"+descuento+"\n");
        imprimir=imprimir+("Sueldo:"+sueldo+"\n");
        
        JOptionPane.showMessageDialog(null, imprimir," Nomina: ",1);
    }
}

    
