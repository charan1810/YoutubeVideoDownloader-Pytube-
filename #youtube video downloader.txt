#youtube video downloader


from pytube import YouTube
from yt_dlp import YoutubeDL


link=input("Enter youtube video: ")
yt=YouTube(link)

print("Title : ", yt.title)
print("Views : ",yt.views)
print("Duration :",yt.length)
print("Description :",yt.description)
print("rating :",yt.rating)

down=input("Do you want to download this video:(y/n)").lower()
if down=="y":
    url= link
    ydl_opts= {'format' : 'best'} # doubt
    with YoutubeDL(ydl_opts) as ydl:
        print("Downloading........")
        ydl.download([url])
        print("Download complete.....")
else:
    print("Download aborted")

