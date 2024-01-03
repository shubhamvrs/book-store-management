import random as r
import mysql.connector as myc
con=myc.connect(host="localhost",user="root",passwd="a3n123456",database="BOOK_STORE")
cus=con.cursor()
print("A3N WELCOMES ALL THE BOOK LOVERS")
def main_menu():
    show='''[1]CUSTOMER
[2]OWNER
[3]EXIT'''
    print("-----------------------------------------------------------------")
    print(show)
    inpt=int(input('enter your choice:->'))
    return inpt
def menu1():
    show='''[1]NEW CUSTOMER
[2]EXISTING CUSTOMER
[3]back'''
    print("-----------------------------------------------------------------")
    print(show)
    inpt1=int(input('enter your choice:->'))
    return inpt1
def menu3():
    show3='''[1]VIEW TABLES
[2]ADD BOOKS
[3]BACK'''
    print("-----------------------------------------------------------------")
    print(show3)
    inpt3=int(input("enter your choice:->"))
    return inpt3
def menu4():
    show4='''
[1]VIEW ALL BOOKS
[2]BACK'''
    print("-----------------------------------------------------------------")
    print(show4)
    intp4=int(input("enter your choice:->"))
    return intp4
def menu5():
    show5='''[1]ORDER
[2]BACK'''
    print(show5)
    print("-----------------------------------------------------------------")
    inpt5=int(input("enter your choice"))
    return inpt5
              
def display():
    cus.execute("select BOOK_CODE,BOOK_NAME,RATE FROM BOOKS")
    r=cus.fetchall()
    for i in r:
        print("BOOK_CODE=",i[0])
        print("BOOK_NAME=",i[1])
        print("BOOK_RATE=",i[2])
        print("______________________________________________________________________")
def customer():
    cus.execute("select* from CUSTOMER")
    c=cus.fetchall()
    for i in c:
        print("CUS_NAME:",i[0])
        print("CUS_USERID:",i[1])
        print("CUS_CUSERNAME:",i[2])
        print("cus_PHONENO:",i[3])
        print('CUS_ADRESS:',i[4])
        print("CUS_PASSWORD:",i[5])
        print("CUS_GMAIL:",i[6])
        print("________________________________________________")
    menu2()
def menu2():
    show6='''[1]CUSTOMER
[2]BOOKS
[3]ORDER
[4]BACK'''
    print(show6)
    print("------------------------------------------------------------------")
    inpt6=int(input("enter your choice:->"))
    return inpt6
def book():
    cus.execute("select* from BOOKS")
    c=cus.fetchall()
    for i in c:
        print("BOOK_CODE:",i[0])
        print("BOOK_NAME:",i[1])
        print("AUTHOR:",i[2])
        print("CATEGORY:",i[3])
        print("RATE;",i[4])
        print("___________________________________________________")
    menu2()
def order():
    cus.execute("select* from ORDER_TABLE")
    c=cus.fetchall()
    for i in c:
        
        print("USER_ID:",i[1])
        print("DATE:",i[2])
        print("QUANTITY:",i[3])
        print("cost:",i[4])
        print("___________________________________________________")
    menu2()

    
        
while True:
    choice=main_menu()
    if choice==1:
        choice1=menu1() 
        if choice1==2:
            e=1
            while e==1:
                user=input("enter your username:->")
                paswd=input('enter your password:->')
                cus.execute('select Username,Password from CUSTOMER')
                check=cus.fetchall()
                for i in check:
                    if user==i[0] and paswd==i[1]:
                        print("logged in succesfully")
                        e=2
                        choice2=menu4()
                        if choice2==1:
                            display()
                            choice3=menu5()
                            if choice3==1:
                                while True:
                                    usid=input('enter userid:->')
                                    while True:
                                        n=input("enter bookname:->")
                                        break
                                    while True:
                                        c=int(input("enter code:->"))
                                        break
                                    while True:
                                        q=int(input("enter quantity:->"))
                                        break
                                    while True:
                                        rate=int(input("enter cost:->"))
                                        cost=q*rate
                                        break
                                    while True:
                                        cr=input("enter date in this format-YYYY-MM-DD:->")
                                        break
                                    while True:
                                        usi=r.randint(0,99)
                                        cus.execute('select SLNO from ORDER_TABLE')
                                        check=cus.fetchall()
                                        if usi in check:
                                            pass
                                        else:
                                            break  
                                        
                                    break
                                print("------------------BILL-------------------")
                                print("date:",cr)
                                print("userid        :",usid)
                                print("bookname      :",n)
                                print("bookcode      :",c)
                                print("quatity       :",q)
                                print("cost          :",cost)
                                print("__________________________________________")
                                y=input("do you want to confirm your order  Y/N  ")
                                if y=="N":
                                    menu5()
                                    break
                                elif y=="Y":
                                    add="insert into ORDER_TABLE values(%s,%s,%s,%s,%s)"
                                    i=(usi,usid,cr,q,cost)
                                    cus.execute(add,i)
                                    con.commit()
                                    print("-------------------------------------------------------------")
                                    print("your odr is placed succesfully......... your order will reach you with in a week")
                                    print("-------------------------------------------------------------------------------------")
                                    print('                   THANK YOU FOR VISITING...                   ')
                                    print("      THERE IS ONLY ONE THING THAT COULD REPLACE A BOOK ; A NEW BOOK....           ")
                                    print("                       DO VISIT AGAIN :)                                           ")
                                    print("-------------------------------------------------------------------------------------")
                            elif choice3==2:
                                menu4()
                                break
                        elif choice2==2:
                            main_menu()
                            
                                    
                                            
                                
                        
                    else:
                        pass
            else:
                break
                    
           
          
                
                    
        elif choice1==1:
            while True:
                name=input("enter your namne:->")
                while True:
                    phno=input('enter your phoneno.:->')
                    cus.execute('select Phone_no from CUSTOMER')
                    check=cus.fetchall()
                    if not phno.isdigit() or len(phno)!=10:
                        print('please enter a valid no.')
                    else:
                        for i in check:
                            if phno in i:
                                print('no alredy exixts')
                                break
                            else:
                                pass
                        else:
                            break
                while True:
                    adrs=input("enter your address:->")
                    break
                while True:
                    usrn=input('enter your username:->')
                    cus.execute('select Username from CUSTOMER')
                    check=cus.fetchall()
                    for i in check:
                        if usrn in i:
                            print("username alredy exixts")
                        else:
                            break
                    else:
                        break
                    break
                
                paswd=input("enter password:->")
                while True:
                    Gmail=input("enter ur gmail account:->")
                    cus.execute("select gmail from CUSTOMER")
                    check=cus.fetchall()
                    if not Gmail.endswith("@gmail.com"):
                        print("please enter a valid gmail")
                    else:
                        for i in check:
                            if Gmail in i:
                                print("it alredy exists plz enter another 1")
                                break
                            else:
                                pass
                        else:
                            break
                        
                while True:
                     usi=r.randint(4444,9999)
                     cus.execute('select User_id from CUSTOMER')
                     check=cus.fetchall()
                     if usi in check:
                         pass
                     else:
                         print("user id generated")
                         print("ur user id is",usi)
                         break
                add="insert into CUSTOMER values(%s,%s,%s,%s,%s,%s,%s)"
                i=(name,usi,usrn,phno,adrs,paswd,Gmail)
                cus.execute(add,i)
                con.commit()
                print('signup succesfully')
                print("now log in  in existing cutsomer")
                
                break
        elif choice1==3:
            break
          
           
        else:
            print("wrong input")
    elif choice==2:
        user=input('enter your username:->')
        pas=input('enter password:->')
        if user!="BOOK_STORE_A3N" and pas!="a3n123456":
            print("enter valid username or password")
        else:
            choice4=menu3()
            while True:
                if choice4==1:
                    choice5=menu2()
                
                    while True:
                         if choice5==1:
                            customer()
                            break
                    
                         elif choice5==2:
                               book()
                    
                               break
                         elif choice5==3:
                               order()
                        
                               break
                elif choice4==2:
                    while True:
                        bc=int(input('enter book code:->'))
                        while True:
                            bn=input("enter book name:->")
                            break
                        while True:
                            a=input('enter author name:->')
                            break
                        while True:
                            cat=input("enter category:->")
                            break
                        while True:
                            rat=input("enter cost:->")
                            add="insert into BOOKS values(%s,%s,%s,%s,%s)"
                    i=(bc,bn,a,cat,rat)
                    cus.execute(add,i)
                    con.commit()
                elif choice4==3:
                    main_menu()
                else:
                    print("wrong input")
                    break
                
    elif choice==3:
         print("-------------------------------------------------------------------------------------")
         print('                   THANK YOU FOR VISITING...                   ')
         print("      THERE IS ONLY ONE THING THAT COULD REPLACE A BOOK ; A NEW BOOK....           ")
         print("                       DO VISIT AGAIN :)                                           ")
         print("-------------------------------------------------------------------------------------")
         break
    else:
        print("wrong input")
        break

            
