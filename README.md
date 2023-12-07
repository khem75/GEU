#include<stdio.h>
#include<math.h>

 int balance = 0;

 
void
openAccount ()
{
  
int initial_deposit;
  
printf ("Enter initial deposit (minimum Rs 5000): ");
  
scanf ("%d", &initial_deposit);
  
if (initial_deposit < 5000)
    {
      
printf ("Initial deposit is less than minimum required amount.\n");
      
return;
    
}
  
balance = initial_deposit;
  
printf ("Account opened successfully. Your current balance is Rs %d.\n",
	   balance);

}


 
void
deposit ()
{
  
int amount;
  
printf ("Enter amount to deposit: ");
  
scanf ("%d", &amount);
  
balance += amount;
  
printf ("Deposit successful. Your new balance is Rs %d.\n", balance);

} 
 
void

withdraw ()
{
  
int amount;
  
printf ("Enter amount to withdraw: ");
  
scanf ("%d", &amount);
  
if (balance - amount >= -50000)
    {
      
balance -= amount;
      
printf ("Withdrawal successful. Your new balance is Rs %d.\n",
	       balance);
    
}
  else
    {
      
printf ("Withdrawal amount exceeds overdraft limit.\n");
    
}

}


 
void
applyInterest ()
{
  
if (balance > 0)
    {
      
balance *= pow ((1 + 0.04 / 12), 12);
      
printf ("Interest applied. Your new balance is Rs %d.\n", balance);
    
}
  else
    {
      
balance *= pow ((1 + 0.06 / 12), 12);
      
printf ("Surcharge applied. Your new balance is Rs %d.\n", balance);
    
}

}


 
void
checkBalance ()
{
  
printf ("Your current balance is Rs %d.\n", balance);

} 
 
int

main ()
{
  
int choice;
  
 
while (1)
    {
      
printf
	("\n1. Open Account\n2. Deposit\n3. Withdraw\n4. Apply Interest/Surcharge\n5. Check Balance\n6. Exit\n");
      
printf ("Enter your choice: ");
      
scanf ("%d", &choice);
      
 
switch (choice)
	{
	
case 1:
	  
openAccount ();
	  
break;
	
case 2:
	  
deposit ();
	  
break;
	
case 3:
	  
withdraw ();
	  
break;
	
case 4:
	  
applyInterest ();
	  
break;
	
case 5:
	  
checkBalance ();
	  
break;
	
case 6:
	  
return 0;
	
default:
	  
printf ("Invalid choice.\n");
	
}
    
}
  
 
return 0;

}
