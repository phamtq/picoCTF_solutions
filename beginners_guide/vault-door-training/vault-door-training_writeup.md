# [The Beginner's Guide to the picoGym] : vault-door-training

## Challenge
![22nd challenge: Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: VaultDoorTraining.java ](images/vault-door-training_challenge.png)

## Status
![Status Image](images/slayed.gif)

## Approach
This one is much easier than I was expecting. After downloading the [file](files/VaultDoorTraining.java), opening it up in your favorite text editor shows most of the flag on line 24:

```java
import java.util.*;

class VaultDoorTraining {
    public static void main(String args[]) {
        VaultDoorTraining vaultDoor = new VaultDoorTraining();
        Scanner scanner = new Scanner(System.in); 
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
	String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
	if (vaultDoor.checkPassword(input)) {
	    System.out.println("Access granted.");
	} else {
	    System.out.println("Access denied!");
	}
   }

    // The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_000HPpgh7Ph");
    }
}
``` 

Using the format of `picoCTF{xxxxx}` we can enter in the characters `w4rm1ng_Up_w1tH_jAv4_000HPpgh7Ph` for the complete flag. And it works!

## Solution
1.  Open up the file
2.  Copy the part of the flag on line 24
3.  Submit the complete flag to the website

## Lessons
None