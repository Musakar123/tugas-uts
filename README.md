
#IMPORT LIBRARY
from tkinter import *

#fungsi menampilkan angka (number)
def addNumber(number,entry):
    entry.insert(END,number)

#fungsi menampilkan teks (string)
def addString(string,entry):
    temp_input = str(entry.get())+string
    entry.delete(0,END)
    entry.insert(0,temp_input)

#fungsi penjumlahan
def addition(entry):
    global operator
    operator = 'addition'
    global first_number
    first_number = float(entry.get())
    entry.delete(0,END)
    
#fungsi pengurangan
def subtraction(entry):
    if (entry.get() == ''):
        entry.insert(0,'-')
    else:
        global operator
        operator = 'subtraction'
        global first_number
        first_number = float(entry.get())
        entry.delete(0,END)

#fungsi perkalian
def multiplication(entry):
    global operator
    operator = 'multiplication'
    global first_number
    first_number = float(entry.get())
    entry.delete(0,END)
#fungsi pembagian
def division(entry):
    global operator
    operator = 'division'
    global first_number
    first_number = float(entry.get())
    entry.delete(0,END)

#fungsi 'DELETE'
def delete(entry):
    new = entry.get()[:-1]
    entry.delete(0, END)
    entry.insert(0, new)
#fungsi 'CLEAR'
def clear(entry1,entry2):
    entry1.delete(0,END)
    entry2.delete(0,END)

#fungsi 'Ans'
def answer(entry):
    entry.insert(0,result)
    
#fungsi 'sama dengan'
def equal(entry1, entry2):
    entry2.delete(0,END)
    second_number = float(entry1.get())
    entry1.delete(0,END)
    global result
    if (operator == 'addition'):
        result = format(first_number + second_number, '.5f')
    elif (operator == 'subtraction'):
        result = format(first_number - second_number, '.5f')
    elif (operator == 'multiplication'):
        result = format(first_number * second_number, '.5f')
    elif (operator == 'division'):
        result = format(first_number / second_number, '.5f')
    entry2.insert(0,result)
