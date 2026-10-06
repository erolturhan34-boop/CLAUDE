DDEI YARA Test Samples - BENIGN (zararsiz)
===========================================
Bu dosyalarin hicbiri zararli degildir. Her biri yalnizca kendini tanitan
bir metin gosterir/yazar; payload, komut calistirma veya indirme yoktur.
Amac: DDEI YARA kurallarinin ilgili DOSYA TIPINI yakalayip yakalamadigini test etmek.

Dosya            Tip         Not
---------------  ----------  ------------------------------------------------
sample.ps1       PowerShell  Write-Host ile metin
sample.bat       Batch       echo
sample.cmd       Batch       echo
sample.js        JScript     WScript.Echo (zararsiz - davranis kurali tetiklenmez)
sample.hta       HTA         Mesaj gosteren HTML uygulamasi
sample.elf       ELF         Linux hello (gcc)
sample.exe       PE EXE      Windows x64 hello (mingw)
sample.lnk       LNK         notepad.exe'ye isaret eden zararsiz kisayol
sample.chm       CHM         ITSF basligi + tek HTML sayfa
sample.jar       JAR         Java hello
sample.class     Java CLASS  Java hello (derlenmis)

Mevcut kurallarinla eslesme (test edildi, YARA 3.10.0):
  sample.elf   -> Detect_ELF_Executable
  sample.exe   -> IsEXE
  sample.jar   -> IsJAR
  Digerleri icin kural YOK (asagiya bak).
