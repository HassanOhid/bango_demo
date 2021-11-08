 
package problemsolve;

 

import java.util.*;

class Student{
   private int id;
   private String  name;
   private double cgpa;
   public Student(int id, String name, double cgpa) {
      super();
      this.id = id;
      this.name = name;
      this.cgpa = cgpa;
   }
   public int getId() {
      return id;
   }
   public String name() {
      return name;
   }
   public double getCgpa() {
      return cgpa;
   }
}

public class Problemsolve {

     
     public static void main(String[] args){
      Scanner in = new Scanner(System.in);
      int testCases = Integer.parseInt(in.nextLine());
      
      List<Student> studentList = new ArrayList<Student>();
      while(testCases>0){
         int id = in.nextInt();
         String name = in.next();
         double cgpa = in.nextDouble();
         
         Student st = new Student(id, name, cgpa);
         studentList.add(st);
         
         testCases--;
      }
       Collections.sort(studentList, new Comparator<Student>() {
              @Override
               public int compare(Student s1, Student s2) {
                    if(s2.getCgpa()>s1.getCgpa()){
                        return 1;
                    }else if(s2.getCgpa()<s1.getCgpa()){
                        return -1;
                    }
                    return s1.name().compareTo(s2.name());
                }
        });
      
         for(Student st: studentList){
         System.out.println(st.name());
      }
   }
}
