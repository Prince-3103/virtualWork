# Task 4: Penetration Testing Simulation

## 1. Objective

The objective of this task is to understand the basic penetration testing process, inspect network services, perform port scanning, and learn how security testing can help identify potential weaknesses in a system.

## 2. Environment

- **Operating System:** Kali Linux
- **Testing machine:** Local Kali Linux system
- **Tools used:** Nmap, Metasploit Framework, Linux networking commands
- **Target:** My own Kali Linux machine
- **Testing scope:** Local network configuration and TCP port inspection

## 3. Tools Used

### Nmap
Nmap is a network scanning tool used to identify hosts, discover open ports, and detect services running on a system.

### Metasploit Framework
Metasploit is a penetration testing framework used by security professionals to investigate and validate vulnerabilities in authorized environments.

### Linux Networking Commands
Commands such as `ip addr` and `ss -tuln` help inspect network interfaces and listening sockets.

## 4. Methodology

### Step 1: Verify Installed Tools

I checked whether Nmap and Metasploit were available on my Kali Linux system.

```bash
nmap --version
msfconsole --version
```

**Observation:** Nmap 7.99 and Metasploit Framework 6.5.2-dev were available.

### Step 2: Identify Network Configuration

```bash
ip addr
```

**Observation:** The active network interface `eth0` had the IPv4 address `192.168.31.79/24`. The loopback interface used `127.0.0.1`.

### Step 3: Inspect Listening Sockets

```bash
ss -tuln
```

**Observation:** The displayed output showed a UDP socket on port 546 associated with an IPv6 link-local address. No TCP listening sockets appeared in the displayed results.

### Step 4: Scan the Localhost

```bash
sudo nmap -sT -sV 127.0.0.1
```

**Observation:** The host was reachable. All 1,000 scanned TCP ports were reported closed with connection refused.

### Step 5: Scan the Kali Network Interface

```bash
sudo nmap -sT -sV -p 1-1024 192.168.31.79
```

**Observation:** The host was reachable. All 1,024 scanned TCP ports were reported closed with connection refused. No open TCP services were identified in the scanned range.

### Step 6: Inspect Metasploit Lab Configuration

I inspected the available Metasploit lab configuration files:

```bash
ls /usr/share/metasploit-framework/data/lab
cat /usr/share/metasploit-framework/data/lab/test_lab.yml
cat /usr/share/metasploit-framework/data/lab/test_targets.yml
```

**Observation:** The directory contained `test_lab.yml` and `test_targets.yml`. These files referenced virtual machine configurations for Metasploitable and older Windows targets. Their presence did not confirm that those virtual machines were installed or running on my system.

## 5. Results

The practical demonstrated how to:

- Verify the availability of security testing tools.
- Identify local network interfaces and IP addresses.
- Inspect listening sockets.
- Perform TCP port scans against my own machine.
- Interpret Nmap results.
- Inspect Metasploit lab configuration files.

The scans did not identify open TCP ports within the ranges tested.

## 6. Limitations

This exercise was limited to local network and service inspection. A separate intentionally vulnerable target machine was not configured.

No vulnerability exploitation was performed, and no successful exploitation was demonstrated. Therefore, this report documents preliminary penetration testing activities rather than a complete exploitation simulation.

## 7. Conclusion

This practical improved my understanding of network reconnaissance, TCP port scanning, local service inspection, and the use of security testing tools in Kali Linux.

I also learned that identifying closed ports does not prove a system is completely secure. Further vulnerability assessment requires an appropriate testing scope and an authorized target environment.

## 8. Evidence

Screenshots of the terminal outputs are included with this report to demonstrate the commands executed and the observations recorded.
