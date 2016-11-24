### Virtualization-Layer(虛擬化實現層次)

![Virtualization-Layer](http://i.imgur.com/ApPNYwN.png)

##1.Instruction Set Architecture Level 指令層級
透過純軟體的方式模擬各種不同CPU(x‐86、PowerPC、MIPS、ARM…)硬體的指令來達到虛擬化。
優點：可以完全的模擬出所需要虛擬設備的所有特性
缺點：性能太差，實現複雜。
舉例：QEMU，具高速度及跨平台的特性。

##2.Hardware Abstraction Level 硬體層級
虛擬機的CPU硬體指令集，一般與原本主機實際CPU硬體指令集非常相似。
硬體虛擬化可以把虛擬機的大多數操作指令，通過映射方式(hypercall)在主機上直接執行，從而大幅提供虛擬化的效率。

［備註：客作業系統向#Hypervisor#，發送的請求稱為#Hypercall#］

優點：是簡單、高效
缺點：是所能虛擬的硬體平台範圍有限，且可能需要硬體
舉例：
-Xen，guest OS必須進行明顯地修改才可以在Xen上運行，因此Xen無需特殊硬體支持。
-KVM是一種Linux kernel模組，可以修正QEMU program 使之用於硬體虛擬化。

##3.OS Level 作業系統層級
又稱共享式作業系統的虛擬化。
實體機器的作業系統（核心）層，這將可創建一些#獨立的容器#(類似程序)，在一台實體機器以及它的實例作業系統上，並以最高的效率方式去使用硬體、軟體、
數據中心和管理等資源。

在下圖顯示了作業系統虛擬化和管理程序或硬體虛擬化技術之間相比較。
![Virtualization-Layer](http://www.ideasmultiples.com/imvps/imagenes/dia_09.gif)

##4.Application Level 應用層級
應用層的虛擬技術是最常見的，如Java虛擬機器、微軟.net CLI和Parrot。

##5.Library Level 函式庫層級
Wine庫（在linux下模擬windows的運行環境）
-補充：Wine不是Windows模擬器，而是運用API轉換技術實做出Linux對應到Windows相對應的函式來呼叫DLL以運行Windows程式。
cygwin庫（在windows下模擬linux運行環境）
-補充：Cygwin的基礎是一套軟體模擬層，也就是cygwin1.dll，由此DLL（Dynamic Link Library，動態連結程式庫）提供POSIX的功能，在Windows上模擬出Linux。




