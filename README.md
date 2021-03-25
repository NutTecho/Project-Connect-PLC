# Python Connect PLC
I use library pymcprotocal from link https://pypi.org/project/pymcprotocol/
and test on plc Mitsubishi Q-Series model Q03UDVCPU and Ethernet module QJ71E71-100.
It's work very well!! I want to thank you a lot for developer. It's very helpfull.
Just starting config in plc to connect in ethernet mode and set port and ip.
you can follow from the example

Create your project in GX work2 and use plc model Q03UDVCPU
![Screenshot (22)](https://user-images.githubusercontent.com/77104969/112495172-3b192500-8db6-11eb-98f5-5357c147041c.png)


 Go to Network Parameter and set config on your network
![Screenshot (23)](https://user-images.githubusercontent.com/77104969/112495451-7c113980-8db6-11eb-968a-71fed66cd08f.png)


Click Operation setting  and config like this
- Communication Data Code is Binary
- Tick enable online change
- Tick Alway wait for Open in Initial Timing
- Tick Use the Ping
![Screenshot (42)](https://user-images.githubusercontent.com/77104969/112495789-ca263d00-8db6-11eb-8926-554736acd2bc.png)



After thet click Open setting and set communication like this
you can adjust your own ip and port 
![Screenshot (43)](https://user-images.githubusercontent.com/77104969/112496130-11143280-8db7-11eb-9708-a4d9d9dc6092.png)

 And then create some ladder program and upload to your PLC.
 #### **After upload complete should restart your PLC again for make sure old data is clear

### On python code.you can use for sample test connection

- import pymcprotocol
- pymc3e = pymcprotocol.Type3E()
- pymc3e.setaccessopt(commtype="binary")
- pymc3e.connect("192.168.10.15", 5002)
- cpu_type, cpu_code = pymc3e.read_cputype()
- print(cpu_type)

### if connection sucsessfull. Code will get PLC model Q03UDVCPU
