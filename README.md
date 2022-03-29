# Mortgage-Calculater
\\Moderately Good code for calculating mortgage in java

package mortgagecalculater;

import java.text.NumberFormat;
import java.util.Scanner;


public class MortgageCalculater {

   
    public static void main(String[] args) {
         Scanner scanner = new Scanner (System.in);
       
       int principal = 0;
       float annualinterest = 0;
       int period = 0;
       
       while(true){
           System.out.print("Principal(1k-1M) - ");
           principal = scanner.nextInt();
           if(principal>=1000 && principal<=1000000)
               break;
           System.out.println("Please enter a valid number");
           }
       
       while(true){
           System.out.print("Annual Interest Rate(1%-30%) - ");
            annualinterest = scanner.nextFloat();
           if(annualinterest>=1 && annualinterest<=30)
               break;
           System.out.println("Please enter a valid number");
       }
       
       while(true){
           System.out.print("Period( Years ) - ");
            period = scanner.nextInt();
           if(period>=1 && period<=30)
               break;
           System.out.println("Please enter a valid number(1-30)");
       }
           
           float monthlyinterest = annualinterest/12/100;
           int numberofpayments = period*12;
           
           double mortgage = principal * (monthlyinterest * Math.pow(1+monthlyinterest, numberofpayments))/(Math.pow(1+monthlyinterest, numberofpayments)-1);
           
           NumberFormat mortgageformatted = NumberFormat.getCurrencyInstance();
           String result = mortgageformatted.format(mortgage);
           
           System.out.println(result);
    }
    
}
