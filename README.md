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


