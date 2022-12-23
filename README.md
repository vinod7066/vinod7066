- 👋 Hi, I’m @vinod7066
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
vinod7066/vinod7066 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
package Std;

import java.sql.*;
import java.util.Scanner;
class InsertionIntoTable{
    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
         try {
      System.out.println("Enter user Id:");
      String userid =sc.next();
      System.out.println("Enter FULL NAME");
      String name =sc.next();
      System.out.println("Enter Date of Birth:");
      String dob = sc.next();
      System.out.println("Enter Emailid:");
      String email = sc.next();
      Class.forName("mysql.jdbc.Driver");
   Connection connect = DriverManager.getConnection("jdbc:mysql://localhost:3306/vinod/crudopn", "username", "passwd");
   PreparedStatement pst = connect.prepareStatement("insert into Employee(USER_ID,FULLNAME,DOB,EMAIL) values(?,?,?,?)");
 
  pst.setString(1,userid);
  pst.setString(2, name);
  pst.setString(3, dob);
  pst.setString(4, email);
        
  int i = pst.executeUpdate();
  if(i!=0){
        System.out.println("added");
      }
      else{
        System.out.println("failed");
      }
    }
    catch (Exception e){
     System.out.println(e);
    }
  }
}
