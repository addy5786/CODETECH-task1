# CODETECH-task1
# this part is all about GUI

from tkinter import  * 
from employee import employee_form
from supplier import supplier_form
from categroy import categroy_form
from product import product_form
from employee import connect_database
import time


# Functionality Part
# #00827f
# ff8c00
def update():
    cursor,connection=connect_database()
    if not cursor or not connection:
            return
    cursor.execute("use inventory_system")
    cursor.execute("SELECT * from employee_data")
    emp_records=cursor.fetchall()
    total_emp_icon_label.config(text=len(emp_records))

    cursor.execute("SELECT * from supplier_data")
    sup_records=cursor.fetchall()
    total_sup_icon_label.config(text=len(sup_records))

    cursor.execute("SELECT * from categroy_data")
    cat_records=cursor.fetchall()
    total_cat_icon_label.config(text=len(cat_records))

    cursor.execute("SELECT * from product_data")
    pro_records=cursor.fetchall()
    total_pro_icon_label.config(text=len(pro_records))

    date_time=time.strftime("%I:%M:%S %p on %A, %B %d, %Y")
    subtitlelabel.config(text=f"Welcome Admin\t\t\t\t{date_time}")
    subtitlelabel.after(1000,update)

current_frame=None
def show_form(form_function):
    global current_frame
    if current_frame:
        current_frame.place_forget()
    current_frame=form_function(window)

# GUI Part
window=Tk()
window.title("Dashboard")
window.geometry("1530x768+0+0")
window.resizable(0,0)
window.config(bg="white")

image = PhotoImage(file="image/inventory.png")

titleLabel=Label(window,text="Inventory Management System",image=image,compound=LEFT,font=("times new roman",40,"bold"),bg="#0f1111",fg="white",anchor="w",padx="20px")
titleLabel.place(x=0,y=0,relwidth=1)

logoutbutton=Button(window,text="LogOut",font=("times new roman",20,"bold"),bg="blue",fg="white")
logoutbutton.place(x=1400,y=10)

subtitlelabel=Label(window,text="Welcome Admin\t\t Date:15-12-24\t\t Time: 16:13:29 pm\t\t",font=("times new roman",20,"bold"),bg="#4d636d",fg="white")
subtitlelabel.place(x=0,y=70,relwidth=1)

leftFrame=Frame(window)
leftFrame.place(x=0,y=110,width=200,height=555)

my_image=PhotoImage(file="image/checklist.png")
imagelabel=Label(leftFrame,image=my_image)
imagelabel.grid(row=0,column=0)
imagelabel.pack()

menulabel=Label(leftFrame,text="Menu",font=("times new roman",20,"bold"),bg="black",fg="white")
menulabel.pack(fill=X)

        # Employee Button

logo=PhotoImage(file="image/teamwork.png")
employee_button=Button(leftFrame,text="  Employee",image=logo,compound=LEFT,font=("times new roman",15,"bold"),bg="green",fg="white",anchor="w",padx=10,command=lambda:show_form(employee_form))
employee_button.pack(fill=X)

        # Supplier Button

logo_supp=PhotoImage(file="image/agreement.png")
Supplier_button=Button(leftFrame,text="  Supplier",image=logo_supp,compound=LEFT,font=("times new roman",15,"bold"),bg="red",fg="white",anchor="w",padx=10,command=lambda:show_form(supplier_form))
Supplier_button.pack(fill=X)

        # Category Button

logo_cat=PhotoImage(file="image/category.png")
Category_button=Button(leftFrame,text="  Category",image=logo_cat,compound=LEFT,font=("times new roman",15,"bold"),bg="blue",fg="white",anchor="w",padx=10,command=lambda:show_form(categroy_form))
Category_button.pack(fill=X)

# Product Button

logo_pro=PhotoImage(file="image/buying.png")
Product_button=Button(leftFrame,text="  Product",image=logo_pro,compound=LEFT,font=("times new roman",15,"bold"),bg="brown",fg="white",anchor="w",padx=10,command=lambda:show_form(product_form))
Product_button.pack(fill=X)

# Sales Button

logo_sale=PhotoImage(file="image/profit.png")
Sales_button=Button(leftFrame,text="  Sales",image=logo_sale,compound=LEFT,font=("times new roman",15,"bold"),bg="orange",fg="white",anchor="w",padx=10)
Sales_button.pack(fill=X)

# Exit Button

logo_ex=PhotoImage(file="image/sign-out.png")
Exit_button=Button(leftFrame,text="  Exit",image=logo_ex,compound=LEFT,font=("times new roman",15,"bold"),bg="grey",fg="white",anchor="w",padx=10)
Exit_button.pack(fill=X)

        # for Employee

emp_frame=Frame(window,bg="#7281e8",bd=3,relief=RIDGE)
emp_frame.place(x=400,y=180,height=180,width=300)
total_emp_icon=PhotoImage(file="image/employee.png")
total_emp_icon_label=Label(emp_frame,image=total_emp_icon,bg="#7281e8")
total_emp_icon_label.pack()

total_emp_icon_label=Label(emp_frame,text="Total Employes",font=("times new roman",20,"bold"),bg="#7281e8",fg="white")
total_emp_icon_label.pack()

total_emp_icon_label=Label(emp_frame,text="0",font=("times new roman",30,"bold"),bg="#7281e8",fg="white")
total_emp_icon_label.pack()


            # For Supplier

supp_frame=Frame(window,bg="#d728d2",bd=3,relief=RIDGE)
supp_frame.place(x=800,y=180,height=180,width=300)

total_sup_icon=PhotoImage(file="image/supplier.png")
total_sup_icon_label=Label(supp_frame,image=total_sup_icon,bg="#d728d2")
total_sup_icon_label.pack()

total_sup_icon_label=Label(supp_frame,text="Total Suppliers",font=("times new roman",20,"bold"),bg="#d728d2",fg="white")
total_sup_icon_label.pack()

total_sup_icon_label=Label(supp_frame,text="0",font=("times new roman",30,"bold"),bg="#d728d2",fg="white")
total_sup_icon_label.pack()

            # for Categroy

cat_frame=Frame(window,bg="#fa8072",bd=3,relief=RIDGE)
cat_frame.place(x=1200,y=180,height=180,width=300)
total_cat_icon=PhotoImage(file="image/market-segment.png")
total_cat_icon_label=Label(cat_frame,image=total_cat_icon,bg="#fa8072")
total_cat_icon_label.pack()

total_cat_icon_label=Label(cat_frame,text="Total Categories",font=("times new roman",20,"bold"),bg="#fa8072",fg="white")
total_cat_icon_label.pack()

total_cat_icon_label=Label(cat_frame,text="0",font=("times new roman",30,"bold"),bg="#fa8072",fg="white")
total_cat_icon_label.pack()

            # for Product

pro_frame=Frame(window,bg="#b62b39",bd=3,relief=RIDGE)
pro_frame.place(x=400,y=400,height=180,width=300)
total_pro_icon=PhotoImage(file="image/products.png")
total_pro_icon_label=Label(pro_frame,image=total_pro_icon,bg="#b62b39")
total_pro_icon_label.pack()

total_pro_icon_label=Label(pro_frame,text="Total Products",font=("times new roman",20,"bold"),bg="#b62b39",fg="white")
total_pro_icon_label.pack()

total_pro_icon_label=Label(pro_frame,text="0",font=("times new roman",30,"bold"),bg="#b62b39",fg="white")
total_pro_icon_label.pack()

        # for Sales

sale_frame=Frame(window,bg="#63814e",bd=3,relief=RIDGE)
sale_frame.place(x=800,y=400,height=180,width=300)

total_sale_icon=PhotoImage(file="image/revenue.png")
total_sale_icon_label=Label(sale_frame,image=total_sale_icon,bg="#63814e")
total_sale_icon_label.pack()

total_sale_icon_label=Label(sale_frame,text="Total Sales",font=("times new roman",20,"bold"),bg="#63814e",fg="white")
total_sale_icon_label.pack()

total_sale_icon_label=Label(sale_frame,text="0",font=("times new roman",30,"bold"),bg="#63814e",fg="white")
total_sale_icon_label.pack()

update()
window.mainloop()

# 2.
# This part is of back-end that How add,delete,update,etc buttons work
# Employee Frame Part How employee page work

from tkinter import  * 
from tkinter import ttk
from tkcalendar import DateEntry
import pymysql
from tkinter import messagebox

# DataBase Code
def connect_database():
    try:
        connection = pymysql.connect(host="localhost",user="root",passwd="w@5786djkq#")
        cursor = connection.cursor()
    except:
         messagebox.showerror("Error","DataBase Conntivity issue, Open mysql Command Line")
         return None,None
   
    return cursor,connection

def create_database_table():
    cursor,connection = connect_database()
    if not cursor or not connection:
            return
    cursor.execute("CREATE DATABASE IF NOT EXISTS inventory_system")
    cursor.execute("USE inventory_system")
    cursor.execute("CREATE TABLE IF NOT EXISTS employee_data(Emp_id INT PRIMARY KEY,Name VARCHAR(100),Email VARCHAR(100),gender VARCHAR(50),DOB VARCHAR(30),Contact VARCHAR(10), Employee VARCHAR(50),Education VARCHAR(100),work VARCHAR(50),"
                   "address VARCHAR(100),DOJ VARCHAR(30),Salary VARCHAR(50),usertype VARCHAR(50),password VARCHAR(50))")

# Functoinality

def treeview_data():
        cursor,connection = connect_database()
        if not cursor or not connection:
            return
        cursor.execute("use inventory_system")
        try:
            cursor.execute("SELECT * from employee_data")
            employee_records=cursor.fetchall()
            emp_treeview.delete(*emp_treeview.get_children())
            for record in employee_records:
                emp_treeview.insert("",END,values=record)

        except Exception as e:
            messagebox.showerror("Error",f"Error due to {e}")
        finally:
            cursor.close()
            connection.close()

        
def clear_fields(Empid_entry,Name_entry,Email_entry,gender_combobox,Dob_date_entry,Contact_entry,Employee_combobox,Education_combobox,work_combobox,address_text,DoJ_date_entry,Salary_entry,usertype_combobox,password_entry,check):
     
     Empid_entry.delete(0,END)
     Name_entry.delete(0,END)
     Email_entry.delete(0,END)
     gender_combobox.set("Select Gender")
     from datetime import date
     Dob_date_entry.set_date(date.today())
     Contact_entry.delete(0,END)
     Employee_combobox.set("Select Type")
     Education_combobox.set("Select Education")
     work_combobox.set("Select Work_Shift")
     address_text.delete(1.0,END)
     DoJ_date_entry.set_date(date.today())
     Salary_entry.delete(0,END)
     usertype_combobox.set("Select Usertype")
     password_entry.delete(0,END)
     if check:
      emp_treeview.selection_remove(emp_treeview.selection())
 
def select_data(event,Empid_entry,Name_entry,Email_entry,gender_combobox,Dob_date_entry,Contact_entry,Employee_combobox,Education_combobox,work_combobox,address_text,DoJ_date_entry,Salary_entry,usertype_combobox,password_entry):
     index=emp_treeview.selection()
     content=emp_treeview.item(index)
     row=content["values"]

     clear_fields(Empid_entry,Name_entry,Email_entry,gender_combobox,Dob_date_entry,Contact_entry,Employee_combobox,Education_combobox,work_combobox,address_text,DoJ_date_entry,Salary_entry,usertype_combobox,password_entry,False)

     Empid_entry.insert(0,row[0])
     Name_entry.insert(0,row[1])
     Email_entry.insert(0,row[2])
     gender_combobox.set(row[3])
     Dob_date_entry.set_date(row[4])
     Contact_entry.insert(0,row[5])
     Employee_combobox.set(row[6])
     Education_combobox.set(row[7])
     work_combobox.set(row[8])
     address_text.insert(1.0,row[9])
     DoJ_date_entry.set_date(row[10])
     Salary_entry.insert(0,row[11])
     usertype_combobox.set(row[12])
     password_entry.insert(0,row[13])
             
     

def add_employee(Emp_id,name,email,gender,dob,contact,employee,education,work,address,doj,salary,usertype,password):
    if( Emp_id=="" or name=="" or email=="" or gender=="Select Gender" or dob=="" or contact==""or employee=="Select Type" or education=="Select Education"or work=="Select Work"or address=="\n"or doj=="" or salary==""or usertype=="Select Type"or password==""):
        messagebox.showerror("Error","All fields are required")
    else:
            cursor,connection = connect_database()
            if not cursor or not connection:
               return
            
            cursor.execute("use inventory_system")
            try:
                cursor.execute("SELECT Emp_id from employee_data WHERE Emp_id=%s",(Emp_id ))
                if cursor.fetchone():
                     messagebox.showerror("Error","Id already exists")
                     return
                address=address.strip()
                cursor.execute("INSERT INTO employee_data VALUES(%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s)",(Emp_id,name,email,gender,dob,contact,employee,education,work,address,doj,salary,usertype,password))
                connection.commit()
                treeview_data()
                messagebox.showinfo("Success","Data is inserted successfully")

            except Exception as e:
                    messagebox.showerror("Error",f"Error due to {e}")
            finally:
                cursor.close()
                connection.close()

def update_employee(Emp_id,name,email,gender,dob,contact,employee,education,work,address,doj,salary,usertype,password):
    selected=emp_treeview.selection()
    if not selected:
         messagebox.showerror("Error","No row is selected")
    else:
            cursor,connection = connect_database()
            if not cursor or not connection:
               return
            cursor.execute("use inventory_system")
            try:
                cursor.execute("SELECT * from employee_data WHERE Emp_id=%s",(Emp_id,))
                current_data=cursor.fetchone()
                
                address=address.strip()
                new_data=(Emp_id,name,email,gender,dob,contact,employee,education,work,address,doj,salary,usertype,password)

               
                if current_data==new_data:
                    messagebox.showinfo("Information","No changes detected")
                    return

                cursor.execute("UPDATE employee_data SET name=%s,email=%s,gender=%s,dob=%s,contact=%s,employee=%s,"
                            "education=%s,work=%s,address=%s,doj=%s,salary=%s,usertype=%s,password=%s WHERE Emp_id=%s",
                (name,email,gender,dob,contact,employee,education,work,address,doj,salary,usertype,password,Emp_id))
                connection.commit()
                treeview_data()
                messagebox.showinfo("Sucess","Data is successfully updated")

            except Exception as e:
                    messagebox.showerror("Error",f"Error due to {e}")
            finally:
                cursor.close()
                connection.close()



def delete_employee(Emp_id):
     
    selected=emp_treeview.selection()
    if not selected:
         messagebox.showerror("Error","No row is selected")
    else:
            result=messagebox.askyesno("Confirm","Do you really want to delete record")
            if result:
                cursor,connection = connect_database()
                if not cursor or not connection:
                    return  
                try:      
                    cursor.execute("use inventory_system")
                    cursor.execute("DELETE FROM employee_data Where Emp_id=%s",(Emp_id,))
                    connection.commit()
                    treeview_data()
                    messagebox.showinfo("Sucess","Record is deleted")

                except Exception as e:
                    messagebox.showerror("Error",f"Error due to {e}")
                finally:
                    cursor.close()
                    connection.close()

def search_employee(search_option,values):
    if search_option=="Search By":
          messagebox.showerror("Error","No option is selected")
    elif values=="":
                messagebox.showerror("Error","Enter the value to search")
    else:
                search_option=search_option.replace(" ","_")
                cursor,connection = connect_database()
                if not cursor or not connection:
                    return  
                try:
                    cursor.execute("use inventory_system")
                    cursor.execute(f"SELECT * from employee_data WHERE {search_option} LIKE %s",f"%{values}%")
                    records=cursor.fetchall()
                    emp_treeview.delete(*emp_treeview.get_children())
                    for record in records:
                        emp_treeview.insert("",END,values=record)
                except Exception as e:
                    messagebox.showerror("Error",f"Error due to {e}")
                finally:
                    cursor.close()
                    connection.close()

def show_all(search_entry,search_combobox):
     treeview_data()
     search_entry.delete(0,END)
     search_combobox.set("Search By")


def employee_form(window): 
                                                                                                        
        global back_image,emp_treeview
        employee_Frame=Frame(window,width=1320,height=655,bg="white")
        employee_Frame.place(x=200,y=107,width=1330,height=655)

        head_Label=Label(employee_Frame,text="Manage Employee Details",font=("times new roman",25,"bold"),bg="#00827f",fg="white")
        head_Label.place(x=0,y=0,relwidth=1)

        back_image=PhotoImage(file="image/arrow.png")
        back_Button=Button(employee_Frame,image=back_image,cursor="hand2",bd=0,bg="white",command=lambda:employee_Frame.place_forget())
        back_Button.place(x=5,y=45)
        
        top_Frame=Frame(employee_Frame,bg="white")
        top_Frame.place(x=0,y=75,relwidth=1,height=230)

        search_frame=Frame(top_Frame,bg="white")
        search_frame.pack()

        search_combobox=ttk.Combobox(search_frame,values=("Emp_id","Name","Email","Gender","DOB","Contact","Employee_Type","Education_Type","Work_Shift","Address","DOJ","Salary","Usertype","Password"),font=("times new roman",10,"bold"),state="readonly")
        search_combobox.set("Search By")
        search_combobox.grid(row=0,column=0,padx=20)

        search_entry=Entry(search_frame,bd=0.5,font=("times new roman",10,"bold"),bg="lightgrey")
        search_entry.grid(row=0,column=1,padx=20)

        search_button=Button(search_frame,text="SEARCH",font=("times new roman",10),bg="red",fg="white",command=lambda:search_employee(search_combobox.get(),search_entry.get()))
        search_button.grid(row=0,column=2,padx=10)

        show_button=Button(search_frame,text="Show All",font=("times new roman",10),width=10,cursor="hand2",bg="red",fg="white",command=lambda:show_all(search_combobox,search_entry))
        show_button.grid(row=0,column=3)

        horizontal_scrollbar=Scrollbar(top_Frame,orient=HORIZONTAL)
        vertical_scrollbar=Scrollbar(top_Frame,orient=VERTICAL)


        emp_treeview=ttk.Treeview(top_Frame,columns=("Emp_id","Name","Email","gender","dob","contact","employement_type","education","work_shift","address","date-of-joining","salary","usertype"),show="headings",yscrollcommand=vertical_scrollbar.set,xscrollcommand=horizontal_scrollbar.set)
        horizontal_scrollbar.pack(side=BOTTOM,fill=X)
        vertical_scrollbar.pack(side=RIGHT,fill=Y,pady=(10,0))
        horizontal_scrollbar.config(command=emp_treeview.xview)
        vertical_scrollbar.config(command=emp_treeview.yview)
        emp_treeview.pack(pady=(10,0))

        emp_treeview.heading("Emp_id",text="Emp_id")
        emp_treeview.heading("Name",text="Name")
        emp_treeview.heading("Email",text="Email")
        emp_treeview.heading("gender",text="Gender")
        emp_treeview.heading("dob",text="DOB")
        emp_treeview.heading("contact",text="Contact")
        emp_treeview.heading("employement_type",text="Employement_type")
        emp_treeview.heading("education",text="Education")
        emp_treeview.heading("work_shift",text="Work_shift")
        emp_treeview.heading("address",text="Address")
        emp_treeview.heading("date-of-joining",text="Date-Of-Joining")
        emp_treeview.heading("salary",text="Salary")
        emp_treeview.heading("usertype",text="User_Type")

        emp_treeview.column("Emp_id",width=60)
        emp_treeview.column("Name",width=140)
        emp_treeview.column("Email",width=180)
        emp_treeview.column("gender",width=80)
        emp_treeview.column("dob",width=100)
        emp_treeview.column("contact",width=120)
        emp_treeview.column("employement_type",width=120)
        emp_treeview.column("education",width=120)
        emp_treeview.column("work_shift",width=100)
        emp_treeview.column("address",width=200)
        emp_treeview.column("date-of-joining",width=100)
        emp_treeview.column("salary",width=140)
        emp_treeview.column("usertype",width=120)

        treeview_data()
        

        detail_frame=Frame(employee_Frame,bg="white")
        detail_frame.place(x=20,y=300)

        Emp_id_label=Label(detail_frame,text="Emp_id",font=("times new roman",10),bg="white")
        Emp_id_label.grid(row=0,column=0)
        Empid_entry=Entry(detail_frame,font=("times new roman",15,"bold"),bg ="lightgrey")
        Empid_entry.grid(row=0,column=1,padx=20,pady=10)


        Name_label=Label(detail_frame,text="Name",font=("times new roman",10),bg="white")
        Name_label.grid(row=0,column=2,padx=20,pady=10)
        Name_entry=Entry(detail_frame,font=("times new roman",15,"bold"),bg ="lightgrey")
        Name_entry.grid(row=0,column=3,padx=20,pady=10)

        Email_label=Label(detail_frame,text="Email",font=("times new roman",10),bg="white")
        Email_label.grid(row=0,column=4)
        Email_entry=Entry(detail_frame,font=("times new roman",15,"bold"),bg ="lightgrey")
        Email_entry.grid(row=0,column=5,padx=20,pady=10)

        gender_label=Label(detail_frame,text="Gender",font=("times new roman",10),bg="white")
        gender_label.grid(row=1,column=0,padx=20,pady=10)
        gender_combobox=ttk.Combobox(detail_frame,values=("Male","Female"),font=("times new roman",12,),width=18,state="readonly")
        gender_combobox.set("Select Gender")
        gender_combobox.grid(row=1,column=1)


        DOB_label=Label(detail_frame,text="Date Of Birth",font=("times new roman",10),bg="white")
        DOB_label.grid(row=1,column=2,padx=20,pady=10)
        Dob_date_entry=DateEntry(detail_frame,font=("times new roman",10),width=15,state="readonly",date_pattern="dd/mm/yyyy")
        Dob_date_entry.grid(row=1,column=3)

        Contact_label=Label(detail_frame,text="Contact",font=("times new roman",10),bg="white")
        Contact_label.grid(row=1,column=4)
        Contact_entry=Entry(detail_frame,font=("times new roman",15,"bold"),bg ="lightgrey")
        Contact_entry.grid(row=1,column=5,padx=20,pady=10)

        Employee_label=Label(detail_frame,text="Employement Type",font=("times new roman",10),bg="white")
        Employee_label.grid(row=2,column=0,padx=20,pady=10)
        Employee_combobox=ttk.Combobox(detail_frame,values=("Part Time","Full Time","Contract","Casual","Intern"),font=("times new roman",12,),width=18,state="readonly")
        Employee_combobox.set("Select Type")
        Employee_combobox.grid(row=2,column=1)

        Education_label=Label(detail_frame,text="Education",font=("times new roman",12),bg="white")
        Education_label.grid(row=2,column=2,padx=20,pady=10,sticky="w")

        education_option=["B Tech","BSC","B.Arch","BCom","BBA","LLB","LLM","M Tech","M Com","M.Arch","Msc","MBA"]

        Education_combobox=ttk.Combobox(detail_frame,values=education_option,font=("times new roman",12,),width=18,state="readonly")
        Education_combobox.set("Select")
        Education_combobox.grid(row=2,column=3)

        work_label=Label(detail_frame,text="Work Shift",font=("times new roman",10),bg="white")
        work_label.grid(row=2,column=4,padx=20,pady=10)
        work_combobox=ttk.Combobox(detail_frame,values=("Morning","Evening","Night"),font=("times new roman",12,),width=18,state="readonly")
        work_combobox.set("Select")
        work_combobox.grid(row=2,column=5)

        address_label=Label(detail_frame,text="Address",font=("times new roman",10),bg="white")
        address_label.grid(row=3,column=0,padx=20,pady=10)
        address_text=Text(detail_frame,width=20,height=3,bg="lightgrey")
        address_text.grid(row=3,column=1)

        DOJ_label=Label(detail_frame,text="Date Of Joining",font=("times new roman",10),bg="white")
        DOJ_label.grid(row=3,column=2,padx=20,pady=10)
        DoJ_date_entry=DateEntry(detail_frame,font=("times new roman",10),width=15,state="readonly",date_pattern="dd/mm/yyyy")
        DoJ_date_entry.grid(row=3,column=3)
       
       
        Salary_label=Label(detail_frame,text="Salary",font=("times new roman",10),bg="white")
        Salary_label.grid(row=3,column=4)
        Salary_entry=Entry(detail_frame,font=("times new roman",15,"bold"),bg ="lightgrey")
        Salary_entry.grid(row=3,column=5,padx=20,pady=10)

        
        usertype_label=Label(detail_frame,text="User Type",font=("times new roman",10),bg="white")
        usertype_label.grid(row=4,column=2,padx=20,pady=10)
        usertype_combobox=ttk.Combobox(detail_frame,values=("Admin","Employee"),font=("times new roman",12,),width=18,state="readonly")
        usertype_combobox.set("Select")
        usertype_combobox.grid(row=4,column=3)

        password_label=Label(detail_frame,text="Password",font=("times new roman",10),bg="white")
        password_label.grid(row=4,column=4)
        password_entry=Entry(detail_frame,font=("times new roman",15,"bold"),bg ="lightgrey")
        password_entry.grid(row=4,column=5,padx=20,pady=10)

        Button_frame=Frame(employee_Frame,bg="white")
        Button_frame.place(x=200,y=530)

        add_button=Button(Button_frame,text="Add",font=("times new roman",15,"bold"),width=10,cursor="hand2",fg="white",bg="red",command=lambda:add_employee(Empid_entry.get(),Name_entry.get(),Email_entry.get(),gender_combobox.get(),Dob_date_entry.get(),Contact_entry.get(),Employee_combobox.get(),
                                                                                                                                                             Education_combobox.get(),work_combobox.get(),address_text.get(1.0,END),DoJ_date_entry.get(),Salary_entry.get(),usertype_combobox.get(),password_entry.get()))
        add_button.grid(row=0,column=0,padx=20)

        
        update_button=Button(Button_frame,text="Update",font=("times new roman",15,"bold"),width=10,cursor="hand2",fg="white",bg="red",command=lambda:update_employee(Empid_entry.get(),Name_entry.get(),Email_entry.get(),gender_combobox.get(),Dob_date_entry.get(),Contact_entry.get(),Employee_combobox.get(),
                                                                                                                                                                      Education_combobox.get(),work_combobox.get(),address_text.get(1.0,END),DoJ_date_entry.get(),Salary_entry.get(),usertype_combobox.get(),password_entry.get()))
        update_button.grid(row=0,column=1,padx=20,pady=10)

        
        delete_button=Button(Button_frame,text="Delete",font=("times new roman",15,"bold"),width=10,cursor="hand2",fg="white",bg="red",command=lambda:delete_employee(Empid_entry.get(),))
        delete_button.grid(row=0,column=3,padx=20,pady=10)
        
        clear_button=Button(Button_frame,text="Clear",font=("times new roman",15,"bold"),width=10,cursor="hand2",fg="white",bg="red",command=lambda:clear_fields(Empid_entry,Name_entry,Email_entry,gender_combobox,Dob_date_entry,Contact_entry,Employee_combobox,Education_combobox,work_combobox,address_text,DoJ_date_entry,Salary_entry,usertype_combobox,password_entry,True))
        clear_button.grid(row=0,column=4,padx=20,pady=10)

        emp_treeview.bind("<Button-1>",lambda event:select_data(event,Empid_entry,Name_entry,Email_entry,gender_combobox,Dob_date_entry,Contact_entry,Employee_combobox,Education_combobox,work_combobox,address_text,DoJ_date_entry,Salary_entry,usertype_combobox,password_entry))

        create_database_table()
        return employee_Frame

# 3.
# This part is of back-end that How add,delete,update,etc buttons work.
# Supplier Frame Part How Supplier page work.

from tkinter import  * 
from tkinter import ttk
from tkinter import messagebox
from employee import connect_database

def treeview_data(treeview):
    cursor,connection=connect_database()
    if not cursor or not connection:
            return
    cursor.execute("use inventory_system")
    try:
        cursor.execute("SELECT * from supplier_data")
        records=cursor.fetchall()
        treeview.delete(*treeview.get_children())
        for record in records:
            treeview.insert("",END,values=record)
    except Exception as e:
                    messagebox.showerror("Error",f"Error due to {e}")
    finally:
            cursor.close()
            connection.close() 
        
def clear_field(invoice_entry,name_entry,contact_entry,description_text,check):
      invoice_entry.delete(0,END)
      name_entry.delete(0,END)
      contact_entry.delete(0,END)
      description_text.delete(1.0,END)
      if check:
        treeview.selection_remove(treeview.selection())

def select_data(event,invoice_entry,name_entry,contact_entry,description_text,treeview):
    index=treeview.selection()
    content=treeview.item(index)
    row=content["values"]
    
    clear_field(invoice_entry,name_entry,contact_entry,description_text)

    invoice_entry.insert(0,row[0])
    name_entry.insert(0,row[1])
    contact_entry.insert(0,row[2])
    description_text.insert(1.0,row[3])




def add_supplier(invoice,name,contact,description,treeview):
    if invoice=="" or name=="" or contact=="" or description=="":
       messagebox.showerror("Error","All fields are required") 
    else:
        cursor,connection=connect_database()
        if not cursor or not connection:
            return
        cursor.execute("use inventory_system")
        try:
            cursor.execute("SELECT * from supplier_data WHERE invoice=%s",invoice)
            if cursor.fetchone():
                messagebox.showerror("Error","Id already exists")
                return
            cursor.execute("CREATE TABLE IF NOT EXISTS supplier_data (invoice INT PRIMARY KEY,name VARCHAR(100),contact VARCHAR(15),description TEXT)")
            cursor.execute("INSERT INTO supplier_data VALUES(%s,%s,%s,%s)",(invoice,name,contact,description))
            connection.commit()
            messagebox.showinfo("Info","Data is inserted")
            treeview_data(treeview)
        except Exception as e:
                messagebox.showerror("Error",f"Error due to {e}")
        finally:
            cursor.close()
            connection.close()

def update_supplier(invoice,name,contact,description,treeview):
      
    selected=treeview.selection()
    if not selected:
         messagebox.showerror("Error","No row is selected")
         return
    else:
            cursor,connection = connect_database()
            if not cursor or not connection:
               return
            cursor.execute("use inventory_system")
            try:
                cursor.execute("SELECT * from supplier_data WHERE invoice=%s",(invoice,))
                current_data=cursor.fetchone()
                current_data=current_data[1:]
                new_data=(name,contact,description)
                if current_data==new_data:
                    messagebox.showinfo("Information","No changes detected")
                    return

                cursor.execute("UPDATE supplier_data SET name=%s,contact=%s,description=%s WHERE invoice=%s",(name,contact,description,invoice))
                connection.commit()
                messagebox.showinfo("Sucess","Data is successfully updated")
                treeview_data(treeview)
            except Exception as e:
                messagebox.showerror("Error",f"Error due to {e}")
            finally:
                cursor.close()
                connection.close()

def delete_supplier(invoice,treeview):
    selected=treeview.selection()
    if not selected:
         messagebox.showerror("Error","No row is selected")
    else:
            result=messagebox.askyesno("Confirm","Do you really want to delete record")
            if result:
                cursor,connection = connect_database()
                if not cursor or not connection:
                    return  
                try:      
                    cursor.execute("use inventory_system")
                    cursor.execute("DELETE FROM supplier_data Where invoice=%s",(invoice,))
                    connection.commit()
                    treeview_data(treeview)
                    messagebox.showinfo("Sucess","Record is deleted")

                except Exception as e:
                    messagebox.showerror("Error",f"Error due to {e}")
                finally:
                    cursor.close()
                    connection.close()

def clear_field(invoice_entry,name_entry,contact_entry,description_text):
      invoice_entry.delete(0,END)
      name_entry.delete(0,END)
      contact_entry.delete(0,END)
      description_text.delete(1.0,END)      

def search_supplier(invoice,treeview):
    if invoice=="":
          messagebox.showerror("Error","Please enter invoice no.")
    else:
        cursor,connection = connect_database()
        if not cursor or not connection:
                    return  
        try:
            cursor.execute("use inventory_system")
            cursor.execute("SELECT * from supplier_data where invoice=%s",invoice)
            record=cursor.fetchone()
            treeview.delete(*treeview.get_children())
            treeview.insert("",END,values=record)

        except Exception as e:
            messagebox.showerror("Error",f"Error due to {e}")
        finally:
            cursor.close()
            connection.close()

    
def show_all(search_entry,treeview):
     treeview_data(treeview)
     search_entry.delete(0,END)
     

def supplier_form(window):
    global back_image,treeview
    supplier_Frame=Frame(window,width=1320,height=655,bg="white")
    supplier_Frame.place(x=200,y=107,width=1330,height=655)

    head_Label=Label(supplier_Frame,text="Manage Supplier Details",font=("times new roman",25,"bold"),bg="#00827f",fg="white")
    head_Label.place(x=0,y=0,relwidth=1)

    back_image=PhotoImage(file="image/arrow1.png")
    back_Button=Button(supplier_Frame,image=back_image,cursor="hand2",bd=0,bg="white",command=lambda:supplier_Frame.place_forget())
    back_Button.place(x=5,y=45)

        #Left Frame 
    left_frame=Frame(supplier_Frame,bg="white")
    left_frame.place(x=10,y=100)

            # Invoice Label

    invoice_label=Label(left_frame,text="Invoice No",font=("times new roman",17,"bold"),bg="white")
    invoice_label.grid(row=0,column=0,padx=(20,40),sticky="w")
    invoice_entry=Entry(left_frame,bd=1,font=("times new roman",17,"bold"),bg="lightgrey")
    invoice_entry.grid(row=0,column=1)

            #Supplier_Name Label

    name_label=Label(left_frame,text="Supplier Name",font=("times new roman",17,"bold"),bg="white")
    name_label.grid(row=1,column=0,padx=(20,40),pady=25,sticky="w")
    name_entry=Entry(left_frame,bd=1,font=("times new roman",17,"bold"),bg="lightgrey")
    name_entry.grid(row=1,column=1)

        # Contact Label

    contact_label=Label(left_frame,text="Contact",font=("times new roman",17,"bold"),bg="white")
    contact_label.grid(row=2,column=0,padx=(20,40),sticky="w")
    contact_entry=Entry(left_frame,bd=1,font=("times new roman",17,"bold"),bg="lightgrey")
    contact_entry.grid(row=2,column=1)

    # Description Label

    description_label=Label(left_frame,text="Description",font=("times new roman",17,"bold"),bg="white")
    description_label.grid(row=3,column=0,padx=(20,40),pady=25,sticky="nw")
    description_text=Text(left_frame,width=25,height=7,bd=1,font=("times new roman",17,"bold"),bg="lightgrey")
    description_text.grid(row=3,column=1,pady=25)

    # Button

    Button_frame=Frame(left_frame,bg="white")
    Button_frame.grid(row=4,columnspan=2)

    add_button=Button(Button_frame,text="Add",font=("times new roman",17,"bold"),width=8,cursor="hand2",fg="white",bg="red",command=lambda:add_supplier(invoice_entry.get(),name_entry.get(),contact_entry.get(),description_text.get(1.0,END).strip(),treeview))
    add_button.grid(row=0,column=0,padx=20)

    
    update_button=Button(Button_frame,text="Update",font=("times new roman",17,"bold"),width=8,cursor="hand2",fg="white",bg="red",command=lambda:update_supplier(invoice_entry.get(),name_entry.get(),contact_entry.get(),description_text.get(1.0,END).strip(),treeview))
    update_button.grid(row=0,column=1,padx=20,pady=10)


    delete_button=Button(Button_frame,text="Delete",font=("times new roman",17,"bold"),width=8,cursor="hand2",fg="white",bg="red",command=lambda:delete_supplier(invoice_entry.get(),treeview))
    delete_button.grid(row=0,column=2,padx=20,pady=10)

    
    clear_button=Button(Button_frame,text="Clear",font=("times new roman",15,"bold"),width=8,cursor="hand2",fg="white",bg="red",command=lambda:clear_field(invoice_entry,name_entry,contact_entry,description_text))
    clear_button.grid(row=0,column=3,padx=20,pady=10)

    # Right Frame

    right_frame=Frame(supplier_Frame,bg="white")
    right_frame.place(x=750,y=95,width=560,height=350)

    search_frame=Frame(right_frame,bg="white")
    search_frame.pack(pady=(0,20))

    num_label=Label(search_frame,text="Invoice No",font=("times new roman",17,"bold"),bg="white")
    num_label.grid(row=0,column=0,padx=15,sticky="w")
    search_entry=Entry(search_frame,bd=1,font=("times new roman",17,"bold"),bg="lightgrey",width=10)
    search_entry.grid(row=0,column=1)

    search_button=Button(search_frame,text="Search",font=("times new roman",13,"bold"),width=8,bg="red",fg="white",command=lambda:search_supplier(search_entry.get(),treeview))
    search_button.grid(row=0,column=2,padx=15)

    
    show_button=Button(search_frame,text="Show All",font=("times new roman",13,"bold"),width=8,cursor="hand2",bg="red",fg="white",command=lambda:show_all(search_entry,treeview))
    show_button.grid(row=0,column=3,padx=(0,15))

    horizontal_scrollbar=Scrollbar(right_frame,orient=HORIZONTAL)
    vertical_scrollbar=Scrollbar(right_frame,orient=VERTICAL)



    treeview=ttk.Treeview(right_frame,column=("invoice","name","contact","description"),show="headings",yscrollcommand=vertical_scrollbar.set,xscrollcommand=horizontal_scrollbar.set)
    horizontal_scrollbar.pack(side=BOTTOM,fill=X)
    vertical_scrollbar.pack(side=RIGHT,fill=Y,pady=(10,0))
    horizontal_scrollbar.config(command=treeview.xview)
    vertical_scrollbar.config(command=treeview.yview)
    treeview.pack(fill=BOTH,expand=1,pady=(10,0))
    treeview.heading("invoice",text="Invoice Id")
    treeview.heading("name",text="Supplier Name")
    treeview.heading("contact",text="Supplier Contact")   
    treeview.heading("description",text="Description")

    treeview.column("invoice",width=90)
    treeview.column("name",width=160)
    treeview.column("contact",width=130)
    treeview.column("description",width=200)

    treeview.bind("<ButtonRelease-1>",lambda event:select_data(event,invoice_entry,name_entry,contact_entry,description_text,treeview))
    treeview_data(treeview)
    return supplier_Frame

 # 3.
# This part is of back-end that How add,delete,update,etc buttons work.
# Categroy Frame Part How Categroy page work.

from tkinter import  * 
from tkinter import ttk
from tkinter import messagebox
from employee import connect_database


def treeview_data(treeview):
    cursor,connection=connect_database()
    if not cursor or not connection:
            return
        
    try:
            cursor.execute("use inventory_system")
            cursor.execute("SELECT * from categroy_data")
            records=cursor.fetchall()
            treeview.delete(*treeview.get_children())
            for record in records:
                treeview.insert("",END,values=record)
    except Exception as e:
                    messagebox.showerror("Error",f"Error due to {e}")
    finally:
            cursor.close()
            connection.close() 


def add_categroy(Id,Name,description,treeview):
    if Id=="" or Name=="" or description=="":
        messagebox.showerror("Error","All fields are required")
    else:
        cursor,connection=connect_database()
        if not cursor or not connection:
            return
        cursor.execute("use inventory_system")
        try:
            cursor.execute("CREATE TABLE IF NOT EXISTS categroy_data (Id INT PRIMARY KEY,Name VARCHAR(100),description TEXT)")
            cursor.execute("SELECT * from categroy_data WHERE Id=%s",Id)
            if cursor.fetchone():
                messagebox.showerror("Error","Id already exists")
                return
            cursor.execute("INSERT INTO categroy_data VALUES(%s,%s,%s)",(Id,Name,description))
            connection.commit()
            messagebox.showinfo("Info","Data is inserted")
            treeview_data(treeview)
        except Exception as e:
                messagebox.showerror("Error",f"Error due to {e}")
        finally:
            cursor.close()
            connection.close()

def delete_categroy(treeview):
    selected=treeview.selection()
    content=treeview.item(selected)
    row=content["values"]
    Id=row[0]
    if not selected:
         messagebox.showerror("Error","No row is selected")
    else:
            result=messagebox.askyesno("Confirm","Do you really want to delete record")
            if result:
                cursor,connection = connect_database()
                if not cursor or not connection:
                    return  
                try:      
                    cursor.execute("use inventory_system")
                    cursor.execute("DELETE FROM categroy_data Where Id=%s",(Id,))
                    connection.commit()
                    treeview_data(treeview)
                    messagebox.showinfo("Sucess","Record is deleted")

                except Exception as e:
                    messagebox.showerror("Error",f"Error due to {e}")
                finally:
                    cursor.close()
                    connection.close()

      
def clear_field(categroy_Id_entry,categroy_name_entry,description_text):
      categroy_Id_entry.delete(0,END)
      categroy_name_entry.delete(0,END)
      description_text.delete(1.0,END)      




def categroy_form(window):
    global back_image,logo
    categroy_Frame=Frame(window,width=1320,height=655,bg="white")
    categroy_Frame.place(x=200,y=107,width=1330,height=655)

    head_Label=Label(categroy_Frame,text="Manage Product Categroy ",font=("times new roman",25,"bold"),bg="#00827f",fg="white")
    head_Label.place(x=0,y=0,relwidth=1)

    back_image=PhotoImage(file="image/arrow1.png")
    back_Button=Button(categroy_Frame,image=back_image,cursor="hand2",bd=0,bg="white",command=lambda:categroy_Frame.place_forget())
    back_Button.place(x=5,y=45)

    logo = PhotoImage(file="image/inventory-management.png")
    label=Label(categroy_Frame,image=logo,bg="white")
    label.place(x=30,y=100)

    details_frame=Frame(categroy_Frame,bg="white")
    details_frame.place(x=650,y=60)

    categroy_id_label=Label(details_frame,text="Categroy Id",font=("times new roman",15,"bold"),bg="white")
    categroy_id_label.grid(row=0,column=0,padx=20,sticky="w")
    categroy_Id_entry=Entry(details_frame,font=("times new roman",18,"bold"),bg ="lightgrey")
    categroy_Id_entry.grid(row=0,column=1,padx=20,pady=10)

    categroy_name_label=Label(details_frame,text="Categroy Name",font=("times new roman",15,"bold"),bg="white")
    categroy_name_label.grid(row=1,column=0,padx=20,sticky="w")
    categroy_name_entry=Entry(details_frame,font=("times new roman",18,"bold"),bg ="lightgrey")
    categroy_name_entry.grid(row=1,column=1,padx=20,pady=10)

    description_label=Label(details_frame,text="Description",font=("times new roman",17,"bold"),bg="white")
    description_label.grid(row=3,column=0,padx=(20,40),pady=25,sticky="nw")
    description_text=Text(details_frame,width=25,height=5,bd=1,font=("times new roman",17,"bold"),bg="lightgrey")
    description_text.grid(row=3,column=1,pady=25)

    Button_frame=Frame(categroy_Frame,bg="white")
    Button_frame.place(x=780,y=340)

    add_button=Button(Button_frame,text="Add",font=("times new roman",17,"bold"),width=8,cursor="hand2",fg="white",bg="red",command=lambda:add_categroy(categroy_Id_entry.get(),categroy_name_entry.get(),description_text.get(1.0,END).strip(),treeview))
    add_button.grid(row=0,column=0,padx=10)

    delete_button=Button(Button_frame,text="Delete",font=("times new roman",17,"bold"),width=8,cursor="hand2",fg="white",bg="red",command=lambda:delete_categroy(treeview))
    delete_button.grid(row=0,column=2,padx=20,pady=10)
    delete_button.grid(row=0,column=1,padx=20,pady=0)

    clear_button=Button(Button_frame,text="Clear",font=("times new roman",15,"bold"),width=8,cursor="hand2",fg="white",bg="red",command=lambda:clear_field(categroy_Id_entry,categroy_name_entry,description_text))
    clear_button.grid(row=0,column=3,padx=20,pady=10)

    treeview_frame=Frame(categroy_Frame,bg="white")
    treeview_frame.place(x=740,y=400,height=200,width=500)

    horizontal_scrollbar=Scrollbar(treeview_frame,orient=HORIZONTAL)
    vertical_scrollbar=Scrollbar(treeview_frame,orient=VERTICAL)

    treeview=ttk.Treeview(treeview_frame,column=("Id","Name","description"),show="headings",yscrollcommand=vertical_scrollbar.set,xscrollcommand=horizontal_scrollbar.set)
    horizontal_scrollbar.pack(side=BOTTOM,fill=X)
    vertical_scrollbar.pack(side=RIGHT,fill=Y,pady=(10,0))
    horizontal_scrollbar.config(command=treeview.xview)
    vertical_scrollbar.config(command=treeview.yview)
    treeview.pack(fill=BOTH,expand=1,pady=(10,0))
    treeview.heading("Id",text="Categroy Id")
    treeview.heading("Name",text="Categroy Name") 
    treeview.heading("description",text="Description")
   
    treeview.column("Id",width=100)
    treeview.column("Name",width=200)
    treeview.column("description",width=250)

    treeview_data(treeview)
    return categroy_Frame

# 4.
# This part is of back-end that How add,delete,update,etc buttons work.
# Product Frame Part How Product page work.

from tkinter import  *
from tkinter import ttk 
from tkinter import messagebox
from employee import connect_database

def show_all(treeview,search_combobox,search_entry):
     treeview_data(treeview)
     search_combobox.set("Search By")
     search_entry.delete(0,END)

def search_product(search_combobox,search_entry,treeview):
     if search_combobox.get()=="Search By":
          messagebox.showwarning("Warning","Please select an option")
     elif search_entry.get()=="":
          messagebox.showwarning("Warning","Please enter the value to search")
     else:
               cursor,connection=connect_database()
     if not cursor or not connection:
            return
     cursor.execute("use inventory_system")
     cursor.execute(f"SELECT * from product_data WHERE {search_combobox.get()}=%s",search_entry.get())
     records=cursor.fetchall()
     if len(records)==0:
          messagebox.showerror("Error","No records found")
          return
     treeview.delete(*treeview.get_children())
     for record in records:
          treeview.insert("",END,values=record)
        
def select_data(event,treeview,categroy_combobox,supplier_combobox,name_entry,price_entry,quantity_entry,status_combobox):
     index=treeview.selection()
     content=treeview.item(index)
     row=content["values"]

     name_entry.delete(0,END)
     price_entry.delete(0,END)
     quantity_entry.delete(0,END)
     categroy_combobox.set(row[1])
     supplier_combobox.set(row[2])
     name_entry.insert(0,row[3])
     price_entry.insert(0,row[4])
     quantity_entry.insert(0,row[5])
     status_combobox.set(row[6])

def clear_field(categroy_combobox,supplier_combobox,name_entry,price_entry,quantity_entry,status_combobox,treeview):
     treeview.selection_remove(treeview.selection())
     categroy_combobox.set("Select")
     supplier_combobox.set("Select")
     name_entry.delete(0,END)
     price_entry.delete(0,END)
     quantity_entry.delete(0,END)
     status_combobox.set("Select Status")
      


def treeview_data(treeview):
     cursor,connection=connect_database()
     if not cursor or not connection:
            return
        
     try:
            cursor.execute("use inventory_system")
            cursor.execute("SELECT * from product_data")
            records=cursor.fetchall()
            treeview.delete(*treeview.get_children())
            for record in records:
                treeview.insert("",END,values=record)
     except Exception as e:
                messagebox.showerror("Error",f"Error due to {e}")
     finally:
            cursor.close()
            connection.close()


def fetch_supplier_categroy(categroy_combobox,supplier_combobox):
    categroy_option=[]
    supplier_option=[]
    cursor,connection=connect_database()
    if not cursor or not connection:
            return
    cursor.execute("USE inventory_system")
    cursor.execute("SELECT name from categroy_data")
    names=cursor.fetchall()
    if len(names)>0:
         categroy_combobox.set("Select")
    for name in names:
         categroy_option.append(name[0])
         categroy_combobox.config(values=categroy_option)

         cursor.execute("SELECT name from supplier_data")
    names=cursor.fetchall()
    if len(names)>0:
         supplier_combobox.set("Select")
    for name in names:
         supplier_option.append(name[0])
         supplier_combobox.config(values=supplier_option)


def add_product(categroy,supplier,name,price,quantity,status,treeview):
     if categroy=="Empty":
            messagebox.showerror("Errror","Please add categories")
     elif supplier=="Empty":
           messagebox.showerror("Errror","Please add supplier")
     elif categroy=="Select" or supplier=="Select"or name=="" or price=="" or quantity=="" or status=="Select Status":
           messagebox.showerror("Error","All fields are Required")
     else:
          cursor,connection=connect_database()
          if not cursor or not connection:
             return
          cursor.execute("use inventory_system")
          cursor.execute("CREATE TABLE IF NOT EXISTS product_data (Id INT AUTO_INCREMENT PRIMARY KEY,Categroy VARCHAR(100),Supplier VARCHAR(100),Name VARCHAR(100),Price DECIMAL(10,2),Quantity INT,Status VARCHAR(20))")
          cursor.execute("SELECT * from product_data WHERE categroy=%s AND supplier=%s AND name=%s",(categroy,supplier,name))
          existing_product=cursor.fetchone()
          if existing_product:
                messagebox.showerror("Error","Product already exists")
                return
          cursor.execute("INSERT INTO product_data(categroy,supplier,name,price,quantity,status) VALUES(%s,%s,%s,%s,%s,%s)",(categroy,supplier,name,price,quantity,status))
          connection.commit()
          messagebox.showinfo("Success","Data is added sucessfully")
          treeview_data(treeview)

def update_product(categroy,supplier,name,price,quantity,status,treeview):
     selected=treeview.selection()
     dict=treeview.item(selected)
     content=dict["values"]
     id=content[0]
     if not selected:
         messagebox.showerror("Error","No row is selected")
         return
     cursor,connection = connect_database()
     if not cursor or not connection:
          return
     cursor.execute("use inventory_system")
     cursor.execute("SELECT * from product_data WHERE id=%s",(id))
     current_data=cursor.fetchone()
     current_data=current_data[1:]
     current_data=list(current_data)
     current_data[3]=str(current_data[3])
     current_data=tuple(current_data)

     quantity=int(quantity)
     new_data=(categroy,supplier,name,price,quantity,status)

     if current_data==new_data:
         messagebox.showinfo("Information","No changes detected")
         return
     
     cursor.execute("UPDATE product_data SET categroy=%s,supplier=%s,name=%s,price=%s,quantity=%s,status=%s WHERE id=%s",(categroy,supplier,name,price,quantity,status,id))
     connection.commit()
     messagebox.showinfo("Sucess","Data is successfully updated")
     treeview_data(treeview)

def delete_product(treeview,categroy_combobox,supplier_combobox,name_entry,price_entry,quantity_entry,status_combobox):
     selected=treeview.selection()
     dict=treeview.item(selected)
     content=dict["values"]
     id=content[0]
     if not selected:
         messagebox.showerror("Error","No row is selected")
     else:
            result=messagebox.askyesno("Confirm","Do you really want to delete record")
            if result:
                cursor,connection = connect_database()
                if not cursor or not connection:
                    return  
                try:      
                    cursor.execute("use inventory_system")
                    cursor.execute("DELETE FROM product_data Where id=%s",(id))
                    connection.commit()
                    treeview_data(treeview)
                    messagebox.showinfo("Sucess","Record is deleted")
                    clear_field(categroy_combobox,supplier_combobox,name_entry,price_entry,quantity_entry,status_combobox,treeview)
                except Exception as e:
                    messagebox.showerror("Error",f"Error due to {e}")
                finally:
                    cursor.close()
                    connection.close()
      


def product_form(window):
    global back_image
    product_Frame=Frame(window,width=1320,height=655,bg="white")
    product_Frame.place(x=200,y=107,width=1330,height=655)

    
    back_image=PhotoImage(file="image/arrow1.png")
    back_Button=Button(product_Frame,image=back_image,cursor="hand2",bd=0,bg="white",command=lambda:product_Frame.place_forget())
    back_Button.place(x=5,y=5)

    left_frame=Frame(product_Frame,bg="white",bd=2,relief=RIDGE)
    left_frame.place(x=20,y=40)

    heading_Label=Label(left_frame,text="Manage Product Details ",font=("times new roman",25,"bold"),bg="#0f4d7d",fg="white")
    heading_Label.grid(row=0,columnspan=2,sticky="we")

    categroy_label=Label(left_frame,text="Categroy",font=("times new roman",17,"bold"),bg="white")
    categroy_label.grid(row=1,column=0,padx=20,sticky="w")
    categroy_combobox=ttk.Combobox(left_frame,font=("times new roman",17,"bold"),width=15,state="readonly")
    categroy_combobox.grid(row=1,column=1,pady=20)
    categroy_combobox.set("Empty")

    supplier_label=Label(left_frame,text="Supplier",font=("times new roman",17,"bold"),bg="white")
    supplier_label.grid(row=2,column=0,padx=20,sticky="w")
    supplier_combobox=ttk.Combobox(left_frame,font=("times new roman",17,"bold"),width=15,state="readonly")
    supplier_combobox.grid(row=2,column=1,pady=20,)
    supplier_combobox.set("Empty")

    
    name_label=Label(left_frame,text="Product Name",font=("times new roman",15,"bold"),bg="white")
    name_label.grid(row=3,column=0,padx=20,sticky="w")
    name_entry=Entry(left_frame,font=("times new roman",15,"bold"),bg ="lightgrey")
    name_entry.grid(row=3,column=1,pady=20)

    price_label=Label(left_frame,text="Price",font=("times new roman",15,"bold"),bg="white")
    price_label.grid(row=4,column=0,padx=20,sticky="w")
    price_entry=Entry(left_frame,font=("times new roman",15,"bold"),bg ="lightgrey")
    price_entry.grid(row=4,column=1,pady=20)

    quantity_label=Label(left_frame,text="Quantity",font=("times new roman",15,"bold"),bg="white")
    quantity_label.grid(row=5,column=0,padx=20,sticky="w")
    quantity_entry=Entry(left_frame,font=("times new roman",15,"bold"),bg ="lightgrey")
    quantity_entry.grid(row=5,column=1,pady=20)

    status_label=Label(left_frame,text="Status",font=("times new roman",17,"bold"),bg="white")
    status_label.grid(row=6,column=0,padx=20,sticky="w")
    status_combobox=ttk.Combobox(left_frame,values=("Active" , "Inactive"),font=("times new roman",17,"bold"),width=15,state="readonly")
    status_combobox.grid(row=6,column=1,pady=20,)
    status_combobox.set("Select Status")

    Button_frame=Frame(left_frame,bg="white")
    Button_frame.grid(row=7,columnspan=2,pady=20)

    add_button=Button(Button_frame,text="Add",font=("times new roman",15,"bold"),width=8,cursor="hand2",fg="white",bg="red",command=lambda:add_product(categroy_combobox.get(),supplier_combobox.get(),name_entry.get(),price_entry.get(),quantity_entry.get(),status_combobox.get(),treeview))
    add_button.grid(row=0,column=0,padx=20)

    update_button=Button(Button_frame,text="Update",font=("times new roman",15,"bold"),width=8,cursor="hand2",fg="white",bg="red",command=lambda:update_product(categroy_combobox.get(),supplier_combobox.get(),name_entry.get(),price_entry.get(),quantity_entry.get(),status_combobox.get(),treeview))
    update_button.grid(row=0,column=1,padx=20)

    delete_button=Button(Button_frame,text="Delete",font=("times new roman",15,"bold"),width=8,cursor="hand2",fg="white",bg="red",command=lambda:delete_product(treeview,categroy_combobox,supplier_combobox,name_entry,price_entry,quantity_entry,status_combobox))
    delete_button.grid(row=0,column=2,padx=20)

    clear_button=Button(Button_frame,text="Clear",font=("times new roman",15,"bold"),width=8,cursor="hand2",fg="white",bg="red",command=lambda:clear_field(categroy_combobox,supplier_combobox,name_entry,price_entry,quantity_entry,status_combobox,treeview))
    clear_button.grid(row=0,column=3,padx=20)

    search_frame=Label(product_Frame,text="Search Product",font=("times new roman",15,"bold"),bg="white")
    search_frame.place(x=680,y=40)

    search_combobox=ttk.Combobox(search_frame,values=("Categroy","Supplier","Name","Price","Quantity","Status"),state="readonly",width=16,font=("times new roman",15,"bold"))
    search_combobox.grid(row=0,column=0,padx=10)
    search_combobox.set("Search By")

    search_entry=Entry(search_frame,text="Search",font=("times new roman",15,"bold"),bg="lightgrey")
    search_entry.grid(row=0,column=1)

    search_button=Button(search_frame,text="Search",font=("times new roman",12,"bold"),width=7,cursor="hand2",fg="white",bg="red",command=lambda:search_product(search_combobox,search_entry,treeview))
    search_button.grid(row=0,column=2,padx=(10,0),pady=10)

    show_button=Button(search_frame,text="Show All",font=("times new roman",12,"bold"),width=7,cursor="hand2",fg="white",bg="red",command=lambda:show_all(treeview,search_combobox,search_entry))
    show_button.grid(row=0,column=3,padx=10)

    treeview_frame=Frame(product_Frame,bg="white")
    treeview_frame.place(x=660,y=100,width=655,height=470)
    
    horizontal_scrollbar=Scrollbar(treeview_frame,orient=HORIZONTAL)
    vertical_scrollbar=Scrollbar(treeview_frame,orient=VERTICAL)

    treeview=ttk.Treeview(treeview_frame,column=("Id","Categroy","Supplier","Name","Price","Quantity","Status"),show="headings",yscrollcommand=vertical_scrollbar.set,xscrollcommand=horizontal_scrollbar.set)
    horizontal_scrollbar.pack(side=BOTTOM,fill=X)
    vertical_scrollbar.pack(side=RIGHT,fill=Y,pady=(10,0))
    horizontal_scrollbar.config(command=treeview.xview)
    vertical_scrollbar.config(command=treeview.yview)
    treeview.pack(fill=BOTH,expand=1,pady=(10,0))
 
    treeview.heading("Id",text="Id")
    treeview.heading("Categroy",text="Categroy")
    treeview.heading("Supplier",text="Supplier")  
    treeview.heading("Name",text="Product Name") 
    treeview.heading("Price",text="Price")
    treeview.heading("Quantity",text="Quantity") 
    treeview.heading("Status",text="Status") 
   
    treeview.column("Id",width=50)
    treeview.column("Categroy",width=100)
    treeview.column("Supplier",width=120)
    treeview.column("Name",width=100)
    treeview.column("Price",width=80)
    treeview.column("Quantity",width=100)
    treeview.column("Status",width=100)

    fetch_supplier_categroy(categroy_combobox,supplier_combobox)
    treeview.bind("<ButtonRelease-1>",lambda event:select_data(event,treeview,categroy_combobox,supplier_combobox,name_entry,price_entry,quantity_entry,status_combobox))
    treeview_data(treeview)
    return product_Frame

