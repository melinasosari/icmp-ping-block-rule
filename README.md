# Windows Firewall Rule - Block Outgoing Ping From Ome windows machine
This Project sets up a custom rule in Wdinows Firewall that Blocks all outgoing ICMP (Ping) traffic from one windows machine ( server or client) to another windows machine

Steps to Create This Rule:        
    1)Open Firewall Settings: oepen the run menu and type *wf.msc*                
    2)Create a New OutBound Rule:                            
            i.Select *outbound rule* click *new rule*                
            ii.Choose *custom* then click next     
            iii.Choose *All Programs* then click next    
            iv.for *Protocol Type* choose *Icmpv4* then select *Csutomize*    
            v.Select *Specific ICMP Types* then Choose *Echo Request*    
            vi.under *remote ip address* select *these ip address*: -add the ip address of the computer that we want to block pinging to (e.g. win11)    
            vii.Choose the firewall profiles(public or private or domain) depending on your network    
            viii.Choose *Block the Connection*    
            ix.Type a name for example *Block Pinging Win11*    
            x.Finish the rule    

Result: After creating this rule, The Source Machine (e.g. DC) will not be able to ping the Target Machine(e.g. Win11)
