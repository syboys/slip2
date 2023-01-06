# slip2
this is slip 2

Q1) Write a Java Program to implement Singleton pattern for multithreading

Q2) Write a python program to find all null values in a given dataset and remove them.

Q3) Create an HTML form that contain the Employee Registration details and writea
JavaScript to validate DOB, Joining Date, and Salary.

1)Write a Java Program to implement Singleton pattern for multithreading

:
public class Main {
 public static void main(String ar[]) {
 Test1 t = new Test1();
 Test1 t2 = new Test1();
 Test1 t3 = new Test1();
 Thread tt = new Thread(t);
 Thread tt2 = new Thread(t2);
Thread tt3 = new Thread(t3);
 Thread tt4 = new Thread(t);
 Thread tt5 = new Thread(t);
 tt.start();
 tt2.start();
 tt3.start();
 tt4.start();
 tt5.start();
 }
}
final class Test1 implements Runnable {
 @Override
 public void run() {
 for (int i = 0; i < 5; i++) {
 System.out.println(Thread.currentThread().getName() + " : " +
Single.getInstance().hashCode());
 }
 }
}

class Single {
 private final static Single sing = new Single();
 private Single() {
 }
 public static Single getInstance() {
 return sing;
 }
 } 


2)Write a python program to find all null values in a given dataset and remove them.

:
df = df.dropna(how='any',axis=0) 


#Recreate random DataFrame with Nan values
df = pd.DataFrame(index = pd.date_range('2017-01-01', '2017-01-10', freq='1d'))
# Average speed in miles per hour
df['A'] = np.random.randint(low=198, high=205, size=len(df.index))
df['B'] = np.random.random(size=len(df.index))*2

#Create dummy NaN value on 2 cells
df.iloc[2,1]=None
df.iloc[5,0]=None

print(df)
                A         B
2017-01-01  203.0  1.175224
2017-01-02  199.0  1.338474
2017-01-03  198.0       NaN
2017-01-04  198.0  0.652318
2017-01-05  199.0  1.577577
2017-01-06    NaN  0.234882
2017-01-07  203.0  1.732908
2017-01-08  204.0  1.473146
2017-01-09  198.0  1.109261
2017-01-10  202.0  1.745309

#Delete row with dummy value
df = df.dropna(how='any',axis=0)

print(df)

                A         B
2017-01-01  203.0  1.175224
2017-01-02  199.0  1.338474
2017-01-04  198.0  0.652318
2017-01-05  199.0  1.577577
2017-01-07  203.0  1.732908
2017-01-08  204.0  1.473146
2017-01-09  198.0  1.109261
2017-01-10  202.0  1.745309


3)Create an HTML form that contain the Employee Registration details and writea
JavaScript to validate DOB, Joining Date, and Salary.

:
<html lang="en">
<head>
 <title>EMPLOYEE REGISTRATION</title>
 <script>
 function register()
 {
 var bd = document.getElementById("d1").value;
 var bdlen = bd.length;
 if(bdlen==0)
 {
 alert("Please Enter BirthDate");
 return false;
 }
 else
 {
 alert("BirthDate Entered\n"+bd);
 }
 var jd = document.getElementById("d2").value;
 var jdlen = jd.length;
 if(jdlen==0)
 {
 alert("Please Enter Joining Date");
 return false;
}
 else
 {
 alert("Joining Date Entered\n"+jd);
 }
 var sal = document.getElementById("d3").value;
 if(sal==0)
 {
 alert("Salary Must be entered");
 return false;
 }
 else
 {
 alert("Salary Entered\n"+sal);
 }

 }
 </script>
</head>
<body>
 <form action="">
 Enter Birthdate <input type="date" id="d1">
 Enter Joining date <input type="date" id="d2">
 Enter Employee salary <input type="number" id="d3">
 <button onclick="register()">RGISTER</button>
 </form>
</body>
</html>
