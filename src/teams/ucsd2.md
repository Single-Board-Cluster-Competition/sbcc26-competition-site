# San Diego Super Computing Center / University of California, San Diego - Team Curtesy

## Diagram

![image](./images/ucsd2.png)



## Hardware

- Bitscope blades provide power to pis via GPIO pins.
- Pis communicate via ethernet through switches.
- One pi acting as the designated head node.
- Access the head node pi through the router from the internet, and access the other pis
via ssh from the head pi

## Budget Breakdown

| Part                     | Units | Cost per unit | Shipping | Total Price | Supplier     | Link                                                                                                                                                                                                 |
|--------------------------|-------|---------------|----------|-------------|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Raspberry Pi 4B          | 18    | $75           | $13.48   | $1,363      | Pi Shop US    | [Link](https://www.pishop.us/product/raspberry-pi-4-model-b-8gb/?src=raspberrypi)                                                                                                                   |
| PNY 64Gb MicroSD         | 18    | $5.33         | $0       | $95.94      | Amazon        | [Link](https://www.amazon.com/PNY-Elite-X-microSDXC-Memory-3-Pack/dp/B08T6QSBPJ?ref_=ast_sto_dp&th=1)                                                                                               |
| Unifi Switch 48          | 2     | $589          | $11      | $1,189.00   | Unifi         | [Link](https://techspecs.ui.com/unifi/switching/usw-48?s=us)                                                                                                                                        |
| Bitscope Rack            | 1     | $945.25       | $52.82   | $998.07     | Bitscope      | [Link](http://my.bitscope.com/store/?p=view&i=item+0)                                                                                                                                               |
| Power supply             | 1     | $89.99        | $0       | $89.99      | Amazon        | [Link](https://www.amazon.com/SS-30V-Regulated-Universal-Quick-Charge-Connectors/dp/B0DK2W8QYW/ref=sr_1_4?crid=D7C8HLOL8HGF&dib=eyJ2IjoiMSJ9.K9AQLR1yQenjYAQ6SpufP9BvFHM48BobH3NZmF0QuExYlJ-ZWo6chX91exw7zT5QaXHt7K2NYux5h8UY44tQiEDoAwmNniz2X-bmMdJUdwACqAwIZZShU9K4WezdJDoALNb-3Z3O631cOgGGqOLLPxjYVoIbBc-MVFd4tnxGBllXveMbv4jC4idIyvEAgBwubdoM-jMDCoN0wRldfIBgb_54OBlK-ex7HfNMekQkuvc.vgdi-jbKSu23eW5B6ZadMQmr7bISxzndgSOG3dueVK8&dib_tag=se&keywords=9-48v+power+supply+up+to+30A+power+surge&qid=1740953112&sprefix=9-48v+power+supply+up+to+30a+power+surge%2Caps%2C135&sr=8-4) |
| Fan                      | 1     | $58.99        | $0.00    | $58.99      | Amazon        | [Link](https://www.amazon.com/WDERAIR-Variable-Controller-Refrigerator-Greenhouse/dp/B0BG2JLVQ5/ref=sr_1_8?crid=3BZUBUNNQPIGC&dib=eyJ2IjoiMSJ9.YIcpyW6gYfMLHmXcoQEdkcu85ynK2zlcNusaF6kRwG19d04GGw1vY7_QQbxghZwese47C-R36-aX2O6pS727sY1njaPYrijK41G6GW8UgknSUvNhDWiXEccAd8QA0LkkUwxobPwiJM_wBQPkhUO846Ch9nHSUtKn_NAymlFBVDS2C2NUOKC9Aw_33IKaxEBDdhjtAElhNA1kMd3mQYAAJ7yZxK0wnX3AKOlmcQAJiwU.L-jzuw6x42k-yKfv2oj2A-lUn8Cv7FkrJdaw-9zesQQ&dib_tag=se&keywords=rack%2Bfans&qid=1740953483&sprefix=rack%2Bfans%2Caps%2C176&sr=8-8&th=1) |
| 1ft Cat6 ethernet cables | 18    | $1.59         | $14.76   | $43.38      | Cables for less | [Link](https://www.cablesforless.com/cat6-cables-blue-1-ft/)                                                                                                                                        |
| Wifi Router              | 1     | $86.90        | 0        | $86.90      | Gl-inet       | [Link](https://www.gl-inet.com/products/gl-mt3000/?utm_source=website&utm_medium=menubar)                                                                                                           |
| Long Ethernet cables     | 3     | $9.79         | 0        | $29.37      | Amazon        | [Link](https://www.amazon.com/Cable-Matters-Snagless-Ethernet-Black/dp/B00G9BN9KW/ref=sr_1_3?crid=39WI2LQ3X6GP8&dib=eyJ2IjoiMSJ9.nFGmvG8c15Hl7S30b9WLQMdJjYxHHjvSmai7KEK9zthRuKJV0L0wlysjnkcKzqZZZyxDDOG1hbBv8nq7YUcxBmFgXiywzQtEzzd3eRNR3n6TISRkp-sRiwnoKuBYBrimkWybWa-n6oB12f2FYm1WYU4TVxgFgalzVvlGNwWDoxT-dJ_c192U62JtUdOhok1C6N2BPISnnarhXAMVlbI2Gd9x-vuYpMTWSRM9HNwzqek.Qn3d5cU-X6v1dN3AdoD9MTjqbjyX4USGgSbVKRbvFN0&dib_tag=se&keywords=cat6%2Bethernet%2Bcable%2B18%2Bft&qid=1740951082&sprefix=cat6%2Bethernet%2Bcable%2B18%2Bf%2Caps%2C204&sr=8-3&th=1) |
| USB-C Power cable        | 1     | $15.99        | 0        | $15.99      | Amazon        | [Link](https://www.amazon.com/Anker-Charger-Foldable-Supports-Charging/dp/B0D72ZPXPY/ref=sr_1_19?crid=2IRSHPQAG03DG&dib=eyJ2IjoiMSJ9.8A3wzd7Zx1TEzlK1GQzw64zT8ARJ8YgLcRTVLgkvevMaP6Y8w510jJmo9c2vIj_WRiU_92SVRTPHSWzh-7pYn2vd0MEJAzlFPOn2SMXby7J8wT447LAEQUNRchuM7rssNUa0OLdySu4N-odH6psjMfRJlt8xpCIgRjSrsPMBosOSTaBv1tTKsE3PFWNp0x47GuC030kWcxbDn1eTBBlejsBsj_vQOWBupWIETtZ0YvI.jvMxAT-lKZC9a1h0ggT9BJZ7pmWtxKT5VYho3YWp4oo&dib_tag=se&keywords=usb+c+brick+and+cable&qid=1740951635&sprefix=usb+c+brick+and+cable+%2Caps%2C168&sr=8-19) |
| Power Strip              | 1     | $12.99        | 0        | $12.99      | Amazon        | [Link](https://www.amazon.com/Yintar-Protector-Outlets-Extension-Essentials/dp/B08MTBCXWX/ref=sr_1_11?crid=313NGXCR3HE8Y&dib=eyJ2IjoiMSJ9.0nQ7jmUuVebhPrkYwBwGW1TWmx61tMqJM8toL0xiMBgEBLvsFbBmSENBRSxi9P52XXZhHyMue8IvdNaoVU-1tU2wvy0ZO5fNSdvQheHuAvOwDINEZ146iYXeveJDHB3NqE-ECychFTFDOUjxLJZY4Cg324dHbGVPLN39fiEtCLrvRoPshFJkNPKwpAGNPGdVriZDTZ5B_-b9u5F9dWFYTYz_jdzLtJ72Seb2HQ4aUEI.kUo4WHuauCxYpcx4VBSrYUxPn75_w5GgGAL8cOsMJYM&dib_tag=se&keywords=power+strip&qid=1740951176&sprefix=power+strip%2Caps%2C202&sr=8-11) |
| Power Cables             | 3     | $6.09         | 0        | $18.27      | Amazon        | [Link](https://www.amazon.com/Standard-Electronics-Computer-Printer-Monitor/dp/B09VRLJD7J/ref=sr_1_3?crid=GKWK3VVULDZI&dib=eyJ2IjoiMSJ9.QbKAIploMqI--xHsNbsTyF2MvKEzPkAxa9nHN216KHRedYugJ3BijVhlp6mImdIuON5jpsNGpoETBTrFcxnluZ20DfJfEgSIY2uicCSqB-KKqFo6zfWjvYXFzYYHcddwr4663KBZRbPEgW_LfLDPb7xmfEwxuuw8fJbrJhEkwwmgSQ4W4y0NBJ_R2YcxvVA97Z9r3AsKvpDSZXeAfg2a38U-S6B8fWvD27sem9u-_ws.W6SIsZ7vZlhYn4ZLq1B1GG0tajOtMT9pGOtFT9khJxo&dib_tag=se&keywords=power+cables&qid=1740951242&sprefix=power+cables%2Caps%2C196&sr=8-3) |
| **TOTAL COST**           |       |               |          | **$3,795.47** |              |                                                                                                                                                                                                      |

## Software
We first installed Ansible and wrote Ansible scripts to set up users and distribute ssh keys throughout
the pi network to enable passwordless communication. We installed Slurm as our job scheduler, GCC
for compiling, Openmpi for multinode interfacing when running tasks, spack for package
management, and nfs-utils for sharing files across nodes.


## Team Details
**Cecilia Li**-First-year Electrical Engineering student. Working on sysadmin, STREAM, and Hashcat.
I will also be running the mystery app during the competition. I’m interested in circuits and systems,
signals and imaging, and ML.

**Chanyoung Park**-Second year Data Science student. Working on DLLAMA and Hashcat. Interested
in Data Analysis, Image Processing, and ML.

**George Mathews**-First year Computer Engineering student working on HPL, helping with hashcat
and power + monitoring.

**Ian Webster**-Second year NanoEngineering student. Working on STREAM and Sysadmin.

**Jackson Yang**-Third year Computer Engineering student working on DLLAMA and networking,
power + monitoring. I am interested in Security, Networking, and architecture.

**Srujam Dave**-Second year Computer Engineering student. Working on HPL and Hashcat. Interested
in networking and computer architecture, and excited to learn more through SBCC.

**Yixuan Li**-First year Computer Science major student working on networking, sysadmin, and dllama.

**Zyanya Rios**-Second year Computer Engineering student, working on Hashat and STREAM.
Interested in cybersecurity and hardware for clusters.
