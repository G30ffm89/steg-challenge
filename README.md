# uwe-steg-challenge

## Dj Khaled
Used the strings command to expose the flag at the bottom of the output

## PCAP 1 
- Opened the PCAP in wireshark 
- Used the filter `http.content_type contains "image/png"` to see image packets
- Next exported the image `File -> Export Objects -> HTTP -> Text Filter "PNG" -> export`
- Open the file to reveal the flag 
![Screenshot From 2024-12-08 16-33-15](https://github.com/user-attachments/assets/683c6a92-1d70-4e94-a4b8-c07ccdb833e5)



## SHREK.GIF
- Opend the gif in ezgif.com
- split the gif into frames
- one of the frames contained the flag
![Screenshot From 2024-12-08 16-28-32](https://github.com/user-attachments/assets/1a40d73a-e141-4582-887f-8276d73c8677)



## Steghide 1
 - Ran command `steghide -sf uwe.jpg`
 - Exported a file called 
 - There was a base64 encoded string 
 - The docoded string revealed the flag
![Screenshot From 2024-12-08 16-38-49](https://github.com/user-attachments/assets/57fc7d2e-471f-4dd1-96f4-2f7a6875b035)


## Steghide 2 
 - Ran command `strings uwe2.jpg`
 - below the file signature there was the line with a string to decode it looked like base64 due to the two equals signs
 - flipped the string and decoded it using base64 within the terminal
![Screenshot From 2024-12-08 16-44-19](https://github.com/user-attachments/assets/e7ae282f-48ca-428b-92f3-79d6698926ee)
 - the command returned a password
 - ran command `steghide extract -sf uwe2.jpg` and used the password to return flie
 - the flag file contained a string 
 - using CyberChef the string was decoded first from base64 then using Bzip2 Decompress returning the flag
![Screenshot From 2024-12-08 16-46-31](https://github.com/user-attachments/assets/70046723-5b7e-4abd-82f9-492a6375f156)


## Hard 
 - Ran command `binwalk -e test.docm` to extract data from the the docm file
 - there were two images contained in the doc  `image1.jpeg` and `image2.png`
 - ran command `binwalk -e image2.png` 
 - Ran the command `olevba test.docm` as there was a vba macro present
 - the output showed a base64 encoded url which downloads a dll file and runs it
![Screenshot From 2024-12-08 16-48-59](https://github.com/user-attachments/assets/f7c6cb22-5adf-46c4-9dd5-561485db530b)




