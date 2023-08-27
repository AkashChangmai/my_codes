# Internet_SpeedTest
from tkinter import*
import speedtest


root=Tk()
root.title("Internet Speed Test")
root.geometry("400x600")
root.resizable(False,False)
root.configure(bg="#1a212d")
  
        

def Check():

    test=speedtest.Speedtest()

    Uploading = round(test.upload()/(1024*1024),2)
    upload.config(text=Uploading)

    downloading = round(test.download()/(1024*1024),2)
    download.config(text=downloading)
    Download.config(text=downloading)

    servernames= []
    test.get_servers(servernames)
    ping.config(text=test.results.ping)


#icon
image_icon = PhotoImage(file="logo.png.png")
root.iconphoto(False,image_icon)


#image
Top=PhotoImage(file="top.png.png")
Label(root,image=Top,bg="#1a212d").pack()

Main=PhotoImage(file="main.png.png")
Label(root,image=Main,bg="#1a212d").pack(pady=(40,0))

button=PhotoImage(file="button.png.png")
Button=Button(root,image=button, bg="#1a212d",bd=0,activebackground="#1a212d",cursor="hand2",command=Check)
Button.pack(pady=10)


#Label
Label(root,text="PING",font="arial 10 bold",bg="#384056", fg="white").place(x=70,y=0)
Label(root,text="DOWNLOAD",font="arial 10 bold",bg="#384056", fg="white").place(x=160,y=0)
Label(root,text="UPLOAD",font="arial 10 bold",bg="#384056", fg="white").place(x=280,y=0)


Label(root,text="MS",font="arial 7 bold",bg="#384056",fg="white").place(x=82,y=90)
Label(root,text="Mbps",font="arial 7 bold",bg="#384056",fg="white").place(x=186,y=90)
Label(root,text="Mbps",font="arial 7 bold",bg="#384056",fg="white").place(x=296,y=90)


Label(root,text="DOWNLOAD",font="arial 15 bold",bg="#384056",fg="white").place(x=144,y=280)
Label(root,text="Mbps",font="arial 15 bold",bg="#384056",fg="white").place(x=179,y=392)


Label(root, text="SERVER", font="arial 10 bold", bg="#384056", fg="white").place(x=100, y=450)




ping=Label(root,text="00",font="arial 13 bold",bg="#384056",fg="white")
ping.place(x=90,y=65,anchor="center")



download=Label(root,text="00",font="arial 13 bold",bg="#384056",fg="white")
download.place(x=200,y=65,anchor="center")



upload=Label(root,text="00",font="arial 13 bold",bg="#384056",fg="white")
upload.place(x=311,y=65,anchor="center")


Download=Label(root,text="00",font="arial 40 bold",bg="#384056")
Download.place(x=207,y=350,anchor="center")




root.mainloop()










