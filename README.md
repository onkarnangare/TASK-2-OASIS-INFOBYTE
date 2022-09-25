# TASK-2-OASIS-INFOBYTE
package online.exam;
import java.util.*;

public class OnlineExam {
    


Scanner sc = new Scanner(System.in);
HashMap<String,Integer> data = new HashMap<String,Integer>();

	public void login() {
		data.put("Onkar",5868);
		data.put("Onkar",8593);
		System.out.println("\n\n$$$$$$$$$$ WELCOME TO ONLINE EXAM SYSTEM $$$$$$$$$$");
		String UserId;
		int password;
		System.out.println("CONTINUE TO LOGIN");
		System.out.print("Enter UserName : ");
		UserId = sc.next();
		System.out.print("Enter password : ");
		password = sc.nextInt();
		if(data.containsKey(UserId) && data.get(UserId)==password) {
			System.out.println("\nLOGIN  SUCCESSFULL ");
				option_menu();
		}
		else {
			System.out.println(" Something Went Wrong");
			System.out.println("Please Try Again");
				login();
		}
	}
	public void option_menu() {
		int select;
		System.out.println("\nEnter your choice");
		System.out.println("1.Update Profile and Password");
		System.out.println("2.Start  Exam");
		System.out.println("3.Logout");
		select = sc.nextInt();
		switch(select) {
		case 1:
			data=update();
			option_menu();
			break;
		case 2:
			exam_que();
			option_menu();
			break;
		case 3:
			System.exit(0);
			break;
		default:
			System.out.println("Wrong Entry");
		}
	}
	public HashMap<String,Integer> update(){
		String uUser;
		int upassword;
		System.out.println("Welcome to Update Profile");
		System.out.println("Enter Username");
		uUser = sc.next();
		if(data.containsKey(uUser)) {
		System.out.println("Enter new Password you to want to Update to your Profile");
		upassword = sc.nextInt();
		data.replace(uUser, upassword);
		}
		else {
			System.out.println("User Doesn't Exist");
		}
		return data;
	}
public void exam_que() {
	long examtime=System.currentTimeMillis();
	long endtime=examtime+30;
	int ans_count=0;
	int ans,score;
	System.out.println("Start Your Exam");

	
//Question starts
	while(System.currentTimeMillis()<endtime) {
		System.out.println("You have 30 seconds to answer 5 questions");
		System.out.println("Each Question carries 10 marks"+" "+"-5 for wrong answer");
		System.out.println("\n\nQ.1) Which of the following languages is not well suited for computation?");
		System.out.println("\n(1) COBOL"+"\t"+"(2) FORTRAN"+"\t"+"(3) PASCAL"+"\t"+"(4) None of these");
		System.out.println("Enter Correct Option");
		ans=sc.nextInt();
		System.out.println("Answer Locked...");
		if(ans==1) {
			ans_count++;
		}
		System.out.println("\n\nQ.2)Pascal is a");
		System.out.println("1)Assembly language"+"\t"+"2)High level language"+"\t"+"3) Machine language"+"\t"+"4)Natural language");
		System.out.println("Enter correct option");
		ans=sc.nextInt();
		System.out.println("Answer Locked...");
		if(ans==2) {
			ans_count++;
		}
		System.out.println("\n\nQ.3)Which of the following is the address operator?");
		System.out.println("1) @"+"\t"+"(2) #"+"\t"+"3)&"+"\t"+"4)%");
		System.out.println("Enter correct option");
		ans=sc.nextInt();
		System.out.println("Answer Locked...");
		if(ans==3) {
			ans_count++;
		}
		System.out.println("\n\nQ.4)Which of the following is the original creator of the C++ language?");
		System.out.println("1) Dennis Ritchie"+"\t"+"2) Ken Thompson"+"\t"+"3) Bjarne Stroustrup"+"\t"+"4)Brian Kernighan");
		System.out.println("Enter correct option");
		ans=sc.nextInt();
		System.out.println("Answer Locked...");
		if(ans==3) {
			ans_count++;
		}
		System.out.println("\n\nQ.5)The C++ language is ______ object-oriented language.");
		System.out.println("1)  Pure Object oriented"+"\t"+"2) Not Object oriented"+"\t"+"3) Semi Object-oriented or Partial Object-oriented"+"\t"+"4) None of the above");
		System.out.println("Enter correct option");
		ans=sc.nextInt();
		System.out.println("Answer Locked...");
		if(ans==3) {
			ans_count++;
		}
		break;
	}
	System.out.println("You have done with your exam");
	score=ans_count*10-((5-ans_count)*5); 
	System.out.println("Your score is..."+" "+score+"/50");	
}
public static void main(String[] args) {
        OnlineExam log =new OnlineExam();
		log.login(); 
        
    }
    
}
