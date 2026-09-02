# Exercise 2: Create a Linux Virtual Machine and Connect to It from the Jump Box Using SSH

In this exercise, you will create and deploy a new Linux virtual machine in an isolated virtual network environment. You will then use SSH to access the virtual machine from the Jump Box and verify the connection.

Follow these steps.

\[**Steps**▶️\]

1. Sign in to the [Azure portal](https://portal.azure.com/) and select the \[**+**\] Create a resource icon at the top of the portal. If the icon is not displayed, select the hamburger menu in the upper-left corner, and then select \[**Create a resource**\].

    ![Create a resource](img/EN-create_AzureResource.png)

2. On the \[**Create a resource**\] page, enter `Virtual machine` in the search box, and then select the \[**Virtual machine**\] tile in the search results.

    ![Search for a virtual machine](img/EN-VM_tail.png)

3. On the \[**Virtual machines**\] page, select \[**Create**\].

4. On the \[**Basics**\] tab of the \[**Create a virtual machine**\] page, configure each setting as follows.

    **Project details**

    |Setting|Value|
    |:---|:---|
    |Subscription \*|The subscription to use|
    |Resource group|\[*Any resource group*\]|

    **Instance details**

    |Setting|Value|
    |:---|:---|
    |Virtual machine name \*|`poc-linux-vm`|
    |Region \*|\[**(Asia Pacific) Japan West**\]|
    |Availability options|\[**No infrastructure redundancy required**\] (Note 1)|
    |Security type|\[**Standard**\]|
    |Image \*|**Ubuntu Server 20.04 LTS**|
    |VM architecture|\[**x64**\]|
    |Size|*Select any size*|

    **Administrator account**

    |Setting|Value|
    |:---|:---|
    |Authentication type \*|\[**Password**\]|
    |Username \*|`poc-admin`|
    |Password \*|`P@ssw0rd1234`|
    |Confirm password \*|`P@ssw0rd1234`|

    **Inbound port rules**

    |Setting|Value|
    |:---|:---|
    |Public inbound ports \*|\[**None**\]|

    <img src="img/EN-vm_dev_jpwest.png" width="700px">

   After configuring the settings, select \[**Next: Disks >**\].

5. On the \[**Disks**\] tab, keep the default settings and select \[**Next: Networking >**\].

    You may select any disk for \[**OS disk type**\].

6. On the \[**Networking**\] tab, verify that each setting is configured as follows by default. For **Virtual network** and **Subnet**, select the resources created in this exercise.

    **Network interface**

    |Setting|Value|
    |:---|:---|
    |Virtual network \*|\[**PoC-jpwest-vnet**\]|
    |Subnet \*|\[**poc-linuxvm-subnet**\]|
    |Public IP|\[**None**\]|
    |NIC network security group|Select \[**None**\]|
    |Delete public IP and NIC when VM is deleted|(Optional)|
    |Enable accelerated networking|Selected|

    **Load balancing**

    |Setting|Value|
    |:---|:---|
    |Load balancing options|Select \[**None**\]|

     <img src="img/EN-vm-mon-jpwest-createNetwork.png" width="700px">

    After configuring the settings, select \[**Review + create**\]. When the \[**Create**\] button becomes available, select it to begin the deployment.

7. When the virtual machine deployment is complete, the \[**Go to resource**\] button appears. Do not select it yet; instead, sign in to the desktop of the Jump Box.

8. Open a terminal, run the `ipconfig` command, and make a note of the Jump Box IP address.

9. In a web browser on the Jump Box, access the Azure portal and open the resource page for the virtual machine you created.

10. From the menu on the left, select \[**Connect**\]. On the page that appears, select \[**Other ways to connect**\] to expand it.

    On the \[**Native SSH**\] tile, select \[**Connect via SSH**\].

    ![Virtual machine connection page](img/EN-connect-VM.png)
    
11. The \[**Native SSH**\] pane appears on the right. Configure the settings as follows.
 
    |Setting|Value|
    |:---|:---|
    |Source machine operating system|`Windows`|
    |Source IP address|\[**Custom IP**\] / *Jump Box IP address*|
    
12. Select \[**Check access**\].

    After just-in-time (JIT) access is enabled, select \[**Save changes**\] to save the settings. Then select the copy button in the \[Connect to VM via SSH\] box to obtain the connection command.

    ![Configure the SSH connection](img/EN-vm-connetct-SSH.png)

13. In the Jump Box terminal, use the SSH connection command you obtained to connect to the Linux virtual machine.


You have now created a Linux virtual machine in an isolated virtual network environment and signed in to it using SSH.

To manage a virtual machine deployed in an isolated virtual network environment, you must access the Azure portal using a web browser on the Jump Box.

<br>

👈 [**Exercise 1: Create a Subnet for the Virtual Machine**](en-ex01.md)

---

🏚️　[Back to README](README.md)