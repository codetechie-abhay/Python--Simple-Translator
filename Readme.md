
# Python Project (Translator)

A low dependency and really simple to start project template for Python Projects.


# project_description

## Install it from PyPI

```bash
pip install googletrans==3.1.0a0
```

## Usage

```py
from tkinter import *
from tkinter import ttk
import tkinter

from googletrans import Translator,LANGUAGES

#Adding the Translator
def change(text="type",src="English",dest="Hindi"):
    text1=text
    src1=src
    dest1=dest
    trans=Translator()
    trans1=trans.translate(text=text1,src=src1,dest=dest1)
    return trans1.text

def data():
    s=comb_sor.get()
    d=comb_dest.get()
    msg=sor_txt.get(1.0,END)
    textget=change(text=msg,src=s,dest=d)
    dest_txt.delete(1.0,END)
    dest_txt.insert(END,textget)



root=Tk()
root.title("Translator")
root.geometry("500x800")
#Background-Change
bluish="#597EBD"
root.config(bg=bluish)

#label
lab_txt=Label(root,text='Translator',font=("Times New Roman",45,"bold"),borderwidth=2, relief="groove")
# Releif is the effect what goes with the border.
#" flat", "raised", "sunken", "ridge", "solid" are relief commands too.
#Label's Height&Width
lab_txt.place(x=100,y=40,height=50,width=300)

frame = Frame(root).pack(side=BOTTOM)

#label
lab_txt=Label(root,text='Source Text',font=("Times New Roman",18,"bold"),fg="black",bg=bluish)
#Label's Height&Width
lab_txt.place(x=100,y=100,height=20,width=300)


#source's text box
sor_txt=Text(frame,font=("Times New Roman",20,"bold"),wrap=WORD)
sor_txt.place(x=10,y=130,height=150,width=480)



list_text=list(LANGUAGES.values())
#Combo Box
comb_sor = ttk.Combobox(frame)
comb_sor.place(x=10,y=300,height=40,width=150)
comb_sor.set("English")

#button
Button_change=Button(frame,text="Translate",relief=RAISED,command=data)
Button_change.place(x=170,y=300,height=40,width=150)


#Combo Box-dest
comb_dest = ttk.Combobox(frame,value=list_text)
comb_dest.place(x=330,y=300,height=40,width=150)
comb_dest.set("Convert")

#label
lab_txt=Label(root,text='Destination Text',font=("Times New Roman",20,"bold"),relief="flat",fg="black",bg=bluish)
#Label's Height&Width
lab_txt.place(x=100,y=360,height=20,width=300)

#dest's text box
dest_txt=Text(frame,font=("Times New Roman",20,"bold"),wrap=WORD)
dest_txt.place(x=10,y=400,height=150,width=480)

lab_txt=Label(root,text='Made by Abhay Nautiyal',font=("Times New Roman",10,"bold"),borderwidth=2,bg="#CCFFCC", relief="groove")
lab_txt.place(x=350,y=680,height=20,width=150)
root.mainloop()
```

```bash
$ python3 -m main.py
#or
$ main.py
```


