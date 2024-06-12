#### Black Marlin | Swordfish attacks | Enumeration tool | NTA tool | [BME](https://github.com/pxcs/BlackMarlinExec/) |

<a href="https://github.com/pxcs/BlackMarlinExec/"><p align="center">
<img width="300" height="300" src="/images/swordfish.png">
</p></a>

## About BlackMarlinExec
BlackMarlinExec uses graph and analysis theory to reveal the hidden and unintended relationships within an Active Directory or active environment. Attackers can use BlackMarlinExec to easily identify highly complex attack paths that would otherwise be impossible to `quickly` identify. It also has it's own attack path management that continuously maps and quantifies Active Directory attack paths. Attackers can see millions, even `billions` of attack paths within your existing architecture.

## BlackMarlinExec [Kerberos](https://www.youtube.com/watch?v=-3MxoxdzFNI&t=353s&ab_channel=Conda) Attacks Performance
BlackMarlinExec incorporates a specialized [Kerberos](https://github.com/pxcs/KerberossianCracker) attack module, empowering attackers to effectively test and exploit weaknesses within the Kerberos authentication protocol. This module is designed to enhance the enumeration and `analysis` capabilities by focusing on potential vulnerabilities in Kerberos implementations.

#### Ticket Harvesting by:

- AS-REP Roasting by automates the extraction of AS-REP responses for accounts that do not require pre-authentication.
- And kerberoasting to identifies and extracts service tickets (TGS) for services that leverage Kerberos.

By integrating advanced Kerberos attack techniques with [BME](https://github.com/pxcs/BlackMarlinExec/) powerful enumeration and network traffic analysis capabilities, Attackers would gain a holistic view of the network's security posture.<br>

<a href="https://github.com/pxcs/KerberossianCracker"><p align="center">
<img width="320" height="300" src="/images/qerberus.png">
</p></a><hr>

## Small Demonstration for [TCP](https://github.com/pxcs/BlackMarlinExec/tree/main/bma/ABAMB/tunnel_barracuda) Killer
During an enumeration attack, hackers verify records stored in a web server using brute-force methods. These attacks occur on web pages that interact with web server databases after a user submits a form. The two most commonly targeted web app pages in enumeration attacks are login pages and `password` reset [pages.](https://www.techtarget.com/searchsecurity/tip/What-enumeration-attacks-are-and-how-to-prevent-them)

## Intro About [Barracuda](https://github.com/pxcs/BlackMarlinExec/tree/main/bma/ABAMB) Attacks

<a href="https://github.com/pxcs/KerberossianCracker"><p align="center">
<img width="150" height="150" src="/images/barracuda.png">
<img width="150" height="150" src="/images/WEB-300_Fill.svg">
</p></a>

### Main Features:
 - Shows a list of processes, and tcp ports they are listening to
 - The list can by filtered by port number
 - You can select a process, and terminate it
 
#### There are many tools that implement this functionality. This tool will additionally:
 - Resolve the application name of java processes (if `jps` is available)
 - For IANA registered ports you can hover over the port number, and it will show additional information
 - On windows, will show the names of services running as children of `ABAMB.exe`
<br>

Shuts down a TCP connection on Linux, macOS, and Windows. Local and remote endpoint arguments can be copied from the output of `netstat_lanW.`

The functionality offered by *tcp_killer* is intended to mimic [TCPView](https://technet.microsoft.com/en-us/sysinternals/tcpview.aspx)'s "Close Connection" functionality and [tcpdrop](http://man.openbsd.org/tcpdrop.8)'s functionality on Linux and macOS.

## Basic Usage

`BME_barracuda.py [-verbose] <local endpoint> <remote endpoint>`

#### Arguments:

    -verbose           Show verbose output
    <local endpoint>   Connection's local IP address and port
    <remote endpoint>  Connection's remote IP address and port

#### Examples:

    BME_barracuda.py 10.31.33.7:50246 93.184.216.34:443
    BME_barracuda.py 2001:db8:85a3::8a2e:370:7334.93 2606:2800:220:1:248:1893:25c8:1946.80
    BME_barracuda.py -verbose [2001:4860:4860::8888]:46820 [2607:f8b0:4005:807::200e]:80

### Full Example
```
geffner@ubuntu:~$ # Create a server to listen on TCP port 12345
geffner@ubuntu:~$ nc -d -l -p 12345 &
[1] 135578

geffner@ubuntu:~$ # Connect to the local server on TCP port 12345
geffner@ubuntu:~$ nc -v -d localhost 12345 &
[2] 135579
Connection to localhost 12345 port [tcp/*] succeeded!

geffner@ubuntu:~$ # Find the connection endpoints
geffner@ubuntu:~$ netstat -lanW | grep 12345.*ESTABLISHED
tcp        0      0 127.0.0.1:33994         127.0.0.1:12345         ESTABLISHED
tcp        0      0 127.0.0.1:12345         127.0.0.1:33994         ESTABLISHED

geffner@ubuntu:~$ # Kill the connection by copying and pasting the output of netstat
geffner@ubuntu:~$ python BME_barracuda.py 127.0.0.1:33994         127.0.0.1:12345
TCP connection was successfully shutdown.
[1]-  Done                    nc -d -l -p 12345
[2]+  Done                    nc -v -d localhost 12345
```

## [LDAP](https://www.youtube.com/watch?v=Xjpi8xYqPcY&pp=ygUUa2VyYmVyb3MgdnMga2VyYmVyb3M%3D) & Kerberos Protocol Potential Attacks
Using [BlackMarlinExec](https://github.com/pxcs/BlackMarlinExec/) to get benefits of integration. Firstly find a significant risk. An attacker would steal user credentials through malware or AD Attacks using [BME](https://github.com/pxcs/BlackMarlinExec/), enabling them to `obtain` a Ticket Granting Ticket (TGT) and access network services. Man-in-the-Middle (MITM) attacks pose another threat, where an attacker intercepts communication using [BME](https://github.com/pxcs/BlackMarlinExec/) to get access between the user and the Key Distribution Center (KDC) or between services and the LDAP directory, potentially `stealing` or `modifying` data.

> [!IMPORTANT]
> [<img src="https://darkcitygame.com/images/thumb/c/c3/Kerberos.png/500px-Kerberos.png" width="30">]()
Attacker might steal user credentials through phishing, allowing them to get a Ticket Granting Ticket (TGT) and access network services. Another risk is ticket forgery, where an attacker creates fake tickets to impersonate users.<br><br>

> [!WARNING]
> [<img src="https://darkcitygame.com/images/thumb/c/c3/Kerberos.png/500px-Kerberos.png" width="30">]()
Attackers intercept communications between users and the Key Distribution Center (KDC) or between services and the LDAP directory to steal or alter data. LDAP injection is another potential attack, where attackers manipulate directory queries to access or change data `illegally.`<br>

## What Is the flaws in Kerberos?
Biggest lose was the assumption of secure time system, and resolution of synchronization required.

<a href="https://github.com/pxcs/BlackMarlinExec/"><p align="center">
<img width="250" height="250" src="/images/keb5.png">
</p></a>

Users authenticate once with Kerberos and can `access` multiple services without re-entering credentials, thanks to the TGT. ~Haha~ this is the time when the attackers could use this privileges.
<br>

## [LDAP](https://www.youtube.com/watch?v=S2mQBXcW3P0&pp=ygUMTERBUCBhdHRhY2tz) Automatic Injections
<a href="https://github.com/pxcs/BlackMarlinExec/"><p align="center">
<img width="150" height="150" src="/images/PEN-210_Fill.svg">
<img width="150" height="150" src="/images/PEN-200_Fill.svg">
</p></a>

Using ***BME*** to automate the process of detecting and exploiting LDAP injection vulnerabilities in AD scenario. With [BME](https://github.com/pxcs/BlackMarlinExec/), Attackers can quickly identify and exploit LDAP injection flaws, allowing attackers to assess the security posture of the applications more effectively.

## "Animal" Features

- Automated detection of LDAP injection vulnerabilities.
- Exploitation of LDAP injection vulnerabilities to extract sensitive information.
- Customizable payloads for fine-tuning injection attacks.

```
Replace `<target_url>` with the URL of the web application you want to scan.
```
For any questions or inquiries, feel free to contact the `developers` [@pxcs](https://github.com/pxcs/)

<hr>

- **Information Gathering:**
  ```powershell
  Find-DomainTarget (-p-) (-sV-) (-Pn-) (-Al-) (-more-)
  ```

- **Get Domain Controllers:**
  ```powershell
  Get-DomainController
  Get-DomainController -Domain <DomainName>
  ```
- **Enumerate Domain Users:**

  ```powershell
  Get-DomainUser | Out-File -FilePath .\DomainUsers.txt

- **Enumerate Shares:**

  ```powershell
  Find-DomainShare

  Find-DomainShare -CheckShareAccess

  Find-InterestingDomainShareFile -Include *passwords*
  ```

- **Enum Group Policies:**

  ```powershell
  Get-DomainGPO -Properties DisplayName | Sort-Object -Property DisplayName

  #Enumerate specific computer
  Get-DomainGPO -ComputerIdentity <ComputerName> -Properties DisplayName | Sort-Object -Property DisplayName

  #Get users that are local Admin group
  Get-DomainGPOComputerLocalGroupMapping -ComputerName <ComputerName>
  ```
  
- **Results Filtering:**
  ```powershell
  #grep #invert #etc
  0.0.0.0 | grep ''

  #grep with attackers .txt
  0.0.0.0 | grep 5 (-c-)(-Pn-) 'List.txt'
  ```
<hr>

## Main Usage

```
usage: BME [-h] [--command COMMAND] [--output OUTPUT] [--interface INTERFACE] [--port PORT]

options:
  -h, --help            show this help message and exit
  --command COMMAND, -c COMMAND
                        command to run on the target (default: calc)
  --output OUTPUT, -o OUTPUT
                        output maldoc file (default: BME)
  --interface INTERFACE, -i INTERFACE
                        network interface or IP address to host the HTTP server (default: eth0)
  --port PORT, -p PORT  port to serve the HTTP server (default: 8000)
```

## Examples

Pop results `BME.exe` :

```
$ BME.exe   
[+] copied staging doc ./
[+] finalizing payload doc ./
[x] created maldoc ./
[x] serving payload on :8000 (Example)
```
- [x] Output
- [x] Compromising Kerberos
- [x] Kerberos `Compromised!`

#### [Vulnerability Report](https://github.com/pxcs/CVE-29343-Sysmon-list/)

<a href="https://github.com/pxcs/BlackMarlin/">
    <img align="center"style="padding-right:10px;" src="https://github.com/pxcs/BlackMarlin/assets/151133481/ef88a928-41a1-4a24-810a-b70031d5efe3" /></a>
<br><br>

<a href="https://github.com/pxcs/BlackMarlinExec/"><img src="https://github.com/pxcs/BlackMarlinExec/assets/151133481/ba7ffa1c-fd3a-4dfa-8e79-0a9c1a644b19" align="right" width="70" alt="smilodon-logo"></a>
> [<img src="https://github.com/pxcs/BlackMarlinExec/assets/151133481/ba7ffa1c-fd3a-4dfa-8e79-0a9c1a644b19" width="20">]() BlackMarlinExec | Submarine project-75: <br>
***BlackMarlinExex*** is a cutting edge Cyber Attacks tool. Designed for comprehensive network traffic analysis and sophisticated enumeration, akin to the functionalities provided by harpoonhound. Developed for cyber attacks and penetration testers, BlackMarlinExec offers a robust suite of features tailored to identify, assess, and scan security vulnerabilities within complex network environments.<br><br>

## Network traffic analysis

#### Network Traffic Classification
This is a research project for classifying network traffic. We collected more than ***300000*** flows from some network. After that, we used nDPI to analyze the flows. We got more than 100 types of applications. Then we group that application into 10 classes. After that, we tried different ML algorithms to classify them.

#### Our current results

- Decision Tree `95.8%` accuracy
- Random Forest `96.69%` accuracy
- Regression `92.1%` accuracy
- Boosting `95.8%` accuracy
- Neural Net `97.5%` accuracy
- KNN `97.24%` accuracy
- PAA `99.29%` accuracy
- SVM `94.7%` accuracy

To get the dataset check out the instructions in the dataset folder.

#### How did we collect Data

***Attackers*** can use used [Wireshark](https://www.wireshark.org/) or [BlackMarlinExec](https://github.com/pxcs/BlackMarlinExec/) to collect the packets. Since for the project we wanted to use lab environment data, we first redirected the lab network to one personal computer(pc) and in that pc we used Wireshark. After collecting the packets, we used ndpi to analyze the packets and get extract flow info and then we export that data as an note file. The `data.csv` contains information on all parameters. However, for this project, we only used most important parameters as features.

## Network traffic lesson.

### Data Set
The dataset used in this demo is: [Malware_Capture](https://mcfp.felk.cvut.cz/publicDatasets/IoT-23-Dataset/IndividualScenarios/CTU-IoT-Malware-Capture-34-1/bro/).<br/>
- It is part of [Aposemat_Dataset](https://www.stratosphereips.org/datasets-iot23).
- A labeled dataset with malicious IoT network traffic.
- This dataset was created as part of the Avast AIC laboratory with the funding of Avast Software. 

#### Data Classification Details
The project is implemented in several distinct steps simulating the essential data processing and analysis phases. <br/>
- Each step is represented in a corresponding notebook inside [notebooks](notebooks).
- Intermediary data files are stored inside the [data](data) path.
- Trained models are stored inside [models](models).

#### PHASE 1 - Initial Data Analysis
> Pre note:  [Data_reading](https://github.com/pxcs/BlackMarlinExec/tree/main/bma)

Implemented data exploration and cleaning tasks:
1. Loading the raw dataset file into pandas DataFrame.
2. Exploring dataset summary and statistics.
3. Fixing combined columns.
4. Dropping irrelevant columns.
5. Fixing unset values and validating data types.
6. Checking the cleaned version of the dataset.
7. Storing the cleaned dataset to a csv file.

#### PHASE 2 - Data Processing
> Corresponding note:  [Data_preprocessing](https://github.com/pxcs/BlackMarlinExec/tree/main/bma)

Implemented data processing and transformation tasks:
1. Loading dataset file into pandas DataFrame.
2. Exploring dataset summary and statistics.
3. Analyzing the target attribute.
4. Encoding the target attribute using [LabelEncoder](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html).
5. Handling outliers using [IQR (Inter_quartile_Range)](https://en.wikipedia.org/wiki/Interquartile_range).
6. Handling missing values:
    1. Impute missing categorical features using [KNeighborsClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html).
    2. Impute missing numerical features using [KNNImputer](https://scikit-learn.org/stable/modules/generated/sklearn.impute.KNNImputer.html).
7. Scaling numerical attributes using [MinMaxScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.MinMaxScaler.html).
8. Encoding categorical features: handling rare values and applying [One_Hot_Encoding](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html).
9. Checking the processed dataset and storing it to a csv file.

#### PHASE 3 - Report Analysis
> BME:  [Data_Attack_and _exploit](https://github.com/pxcs/BlackMarlinExec/tree/main/bma)

Trained and analyzed classification models:
1. Naive Bayes: [ComplementNB](https://scikit-learn.org/stable/modules/generated/sklearn.naive_bayes.ComplementNB.html)
2. Decision Tree: [DecisionTreeClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html)
3. Logistic Regression: [LogisticRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html)    
4. Random Forest: [RandomForestClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)
5. Support Vector Classifier: [SVC](https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html#sklearn.svm.SVC)
6. K-Nearest Neighbors: [KNeighborsClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html)
7. XGBoost: [XGBClassifier](https://xgboost.readthedocs.io/en/stable/index.html#)

Evaluation method: 
- Cross-Validation Technique: [Cross_Validator](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.StratifiedKFold.html)
- Folds number: Anon
- Shuffled: Enabled

Results were analyzed and compared for each model.<br/>

#### PHASE 4 - Tuning and Enumeration
> Trust Kerberos Attack: [Kerberos](https://github.com/pxcs/BlackMarlinExec/tree/main/kerberos/common)

Model tuning details:
- Tuned model: Support Vector Classifier - [SVC](https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html#sklearn.svm.SVC)
- Tuning method: [GridSearch](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html)
- Results were analyzed before/after tuning.<br>

Publicly share you guys about my red teaming ***experiments*** tested on several environments/infrastructures that involve playing with various tools and techniques used by penetration testers and redteamers.

- [x] Project in progress
- [x] Contributions needed

**Ability**
- [x] Pivoting
- [x] Domain Enumeration
- [x] Auto `grep` results
- [x] Credential Harvesting
- [x] Network Identification

<hr>

## Disclaimer
***BlackMarlinExec*** is designed primarily for research, identification, and authorized testing scenarios. This tool is to provide professionals and researchers with a tool to understand and identify vulnerabilities of the security systems. It is fundamentally imperative that users ensure they have obtained explicit, mutual consent from all involved parties before applying this tool on any system, or network.

#### Educational purposes only.<br>

## Sutton_Program Organization
Check out the ORG repo for more tools like this [@](https://github.com/SuttonProgram)

## Thanks to

- Allah and [pxcs](https://github.com/pxcs/) p3xsouger
- Some credit to ugs people
- And several open [Github](https://github.com/) repo.
