# CSdSafeguard::_CustomizeSellSettingsForFolder(ushort const *)

- ea: `0x1800373c8`
- end: `0x1800376ec`
- name: `?_CustomizeSellSettingsForFolder@CSdSafeguard@@AEAAJPEBG@Z`
- size: `804`
- prototype: `int(CSdSafeguard *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800361a0`

## callees

- `0x1800081d8`
- `0x180008200`
- `0x1800373c8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18009a24c`
- `0x18009a378`
- `0x18009ae34`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x180037481`
- `KERNEL32!SetFileAttributesW` at `0x1800375b2`
- `KERNEL32!SetFileAttributesW` at `0x180037481`
- `KERNEL32!SetFileAttributesW` at `0x1800375b2`
- `KERNEL32!CreateFileW` at `0x1800374ec`
- `KERNEL32!CreateFileW` at `0x1800374ec`
- `KERNEL32!GetLastError` at `0x180037603`
- `KERNEL32!GetLastError` at `0x18003763e`
- `KERNEL32!GetLastError` at `0x180037603`
- `KERNEL32!GetLastError` at `0x18003763e`
- `KERNEL32!CloseHandle` at `0x1800376b1`
- `KERNEL32!CloseHandle` at `0x1800376b1`
- `KERNEL32!WriteFile` at `0x180037515`
- `KERNEL32!WriteFile` at `0x180037572`
- `KERNEL32!WriteFile` at `0x180037515`
- `KERNEL32!WriteFile` at `0x180037572`

## string_xrefs

- `0x180037459`: `[.ShellClassInfo]\nDirectoryClass=WindowsBackupFolderOptions\nIconResource=%SystemRoot%\system32\sdclt.exe,-5501`

## pseudocode

```c
__int64 __fastcall CSdSafeguard::_CustomizeSellSettingsForFolder(
        struct _SECURITY_ATTRIBUTES *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rbx
  __int16 v5; // ax
  __int64 v6; // rcx
  HANDLE FileW; // rax
  __int64 v8; // rcx
  int v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  signed int LastError; // eax
  signed int v15; // edi
  unsigned int v16; // edi
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-59h]
  const unsigned __int16 *v19; // [rsp+38h] [rbp-51h]
  const unsigned __int16 *v20; // [rsp+40h] [rbp-49h]
  const unsigned __int16 *v21; // [rsp+48h] [rbp-41h]
  const unsigned __int16 *v22; // [rsp+50h] [rbp-39h]
  LPCVOID lpBuffer; // [rsp+60h] [rbp-29h] BYREF
  __int64 v24; // [rsp+68h] [rbp-21h]
  LPCWSTR lpFileName[2]; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v26[2]; // [rsp+80h] [rbp-9h] BYREF
  int LastFailureAsHRESULT; // [rsp+90h] [rbp+7h] BYREF
  __int16 v28; // [rsp+94h] [rbp+Bh]
  __int16 v29; // [rsp+96h] [rbp+Dh]
  __int16 Buffer; // [rsp+F8h] [rbp+6Fh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+100h] [rbp+77h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSdSafeguard::_CustomizeSellSettingsForFolder",
    785,
    1);
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  lpBuffer = qword_1800E8530;
  v24 = 0;
  v4 = -1;
  NumberOfBytesWritten = 0;
  v26[0] = qword_1800E8530;
  v26[1] = 0;
  Buffer = -257;
  v5 = 797;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_3:
    v29 = v5;
    goto LABEL_32;
  }
  LastFailureAsHRESULT = 0;
  v28 = 797;
  LastFailureAsHRESULT = CBsString::Set(
                           (CBsString *)&lpBuffer,
                           L"[.ShellClassInfo]\r\n"
                            "DirectoryClass=WindowsBackupFolderOptions\r\n"
                            "IconResource=%SystemRoot%\\system32\\sdclt.exe,-5501");
  v5 = 799;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v28 = 799;
  if ( !SetFileAttributesW(a2, 1u) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6);
    v5 = 801;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v28 = 801;
  CBsString::SetPath((CBsString *)lpFileName, a2, L"Desktop.ini", 0, 0, 0, hTemplateFile, v19, v20, v21, v22);
  FileW = CreateFileW(lpFileName[0], 0xC0000000, 0, this + 3, 1u, 1u, 0);
  v4 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( GetLastError() == 80 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v13 = 22;
        goto LABEL_24;
      }
    }
    else
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids,
          (unsigned int)v15);
      LastFailureAsHRESULT = v15;
      v5 = 835;
      if ( v15 < 0 )
        goto LABEL_3;
      v28 = 835;
    }
  }
  else
  {
    if ( !WriteFile(FileW, &Buffer, 2u, &NumberOfBytesWritten, 0) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
      v5 = 818;
      goto LABEL_3;
    }
    v28 = 818;
    v5 = 819;
    if ( NumberOfBytesWritten != 2 )
      goto LABEL_11;
    LastFailureAsHRESULT = 0;
    v28 = 819;
    v9 = 2 * v24;
    if ( !WriteFile((HANDLE)v4, lpBuffer, 2 * v24, &NumberOfBytesWritten, 0) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
      v5 = 820;
      goto LABEL_3;
    }
    v28 = 820;
    v5 = 821;
    if ( NumberOfBytesWritten != v9 )
    {
LABEL_11:
      LastFailureAsHRESULT = -2130706378;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v28 = 821;
    if ( !SetFileAttributesW(lpFileName[0], 6u) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
      v5 = 823;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v28 = 823;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v13 = 21;
LABEL_24:
      WPP_SF_(v12[2], v13, WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids);
    }
  }
LABEL_32:
  v16 = LastFailureAsHRESULT;
  CBsString::_Release((CBsString *)v26);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v4);
  CBsString::_Release((CBsString *)&lpBuffer);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v16;
}

```

## disassembly

```asm
0x1800373c8  mov     [rsp-8+arg_0], rbx
0x1800373cd  mov     [rsp-8+arg_18], rsi
0x1800373d2  push    rbp
0x1800373d3  push    rdi
0x1800373d4  push    r14
0x1800373d6  lea     rbp, [rsp-47h]
0x1800373db  sub     rsp, 0D0h
0x1800373e2  mov     rdi, rdx
0x1800373e5  mov     rsi, rcx
0x1800373e8  mov     r9d, 1; unsigned __int16
0x1800373ee  mov     r8d, 311h; unsigned __int16
0x1800373f4  lea     rdx, aCsdsafeguardCu; "CSdSafeguard::_CustomizeSellSettingsFor"...
0x1800373fb  lea     rcx, [rbp+57h+var_50]; this
0x1800373ff  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180037404  lea     rax, qword_1800E8530
0x18003740b  mov     [rbp+57h+lpFileName], rax
0x18003740f  xor     r14d, r14d
0x180037412  mov     [rbp+57h+var_68], r14
0x180037416  mov     [rbp+57h+lpBuffer], rax
0x18003741a  mov     [rbp+57h+var_78], r14
0x18003741e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180037422  mov     [rbp+57h+NumberOfBytesWritten], r14d
0x180037426  mov     [rbp+57h+var_60], rax
0x18003742a  mov     [rbp+57h+var_58], r14
0x18003742e  mov     eax, 0FEFFh
0x180037433  mov     [rbp+57h+Buffer], ax
0x180037437  mov     eax, 31Dh
0x18003743c  test    rdi, rdi
0x18003743f  jnz     short loc_180037451
0x180037441  mov     [rbp+57h+var_50], 80070057h
0x180037448  mov     [rbp+57h+var_4A], ax
0x18003744c  jmp     loc_180037698
0x180037451  mov     [rbp+57h+var_50], r14d
0x180037455  mov     [rbp+57h+var_4C], ax
0x180037459  lea     rdx, aShellclassinfo; "[.ShellClassInfo]\r\nDirectoryClass=Win"...
0x180037460  lea     rcx, [rbp+57h+lpBuffer]; this
0x180037464  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180037469  mov     [rbp+57h+var_50], eax
0x18003746c  test    eax, eax
0x18003746e  mov     eax, 31Fh
0x180037473  js      short loc_180037448
0x180037475  mov     [rbp+57h+var_4C], ax
0x180037479  mov     edx, 1; dwFileAttributes
0x18003747e  mov     rcx, rdi; lpFileName
0x180037481  call    cs:__imp_SetFileAttributesW
0x180037487  test    eax, eax
0x180037489  jnz     short loc_18003749A
0x18003748b  call    GetLastFailureAsHRESULT
0x180037490  mov     [rbp+57h+var_50], eax
0x180037493  mov     eax, 321h
0x180037498  jmp     short loc_180037448
0x18003749a  mov     [rbp+57h+var_50], r14d
0x18003749e  mov     eax, 321h
0x1800374a3  mov     [rbp+57h+var_4C], ax
0x1800374a7  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], r14; unsigned __int16 *
0x1800374ac  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r14; unsigned __int16 *
0x1800374b1  xor     r9d, r9d; unsigned __int16 *
0x1800374b4  lea     r8, aDesktopIni; "Desktop.ini"
0x1800374bb  mov     rdx, rdi; unsigned __int16 *
0x1800374be  lea     rcx, [rbp+57h+lpFileName]; this
0x1800374c2  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800374c7  lea     r9, [rsi+48h]; lpSecurityAttributes
0x1800374cb  mov     [rsp+0E0h+hTemplateFile], r14; hTemplateFile
0x1800374d0  mov     [rsp+0E0h+dwFlagsAndAttributes], 1; dwFlagsAndAttributes
0x1800374d8  mov     [rsp+0E0h+dwCreationDisposition], 1; dwCreationDisposition
0x1800374e0  xor     r8d, r8d; dwShareMode
0x1800374e3  mov     edx, 0C0000000h; dwDesiredAccess
0x1800374e8  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800374ec  call    cs:__imp_CreateFileW
0x1800374f2  mov     rbx, rax
0x1800374f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800374f9  jz      loc_180037603
0x1800374ff  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r14; lpOverlapped
0x180037504  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180037508  mov     r8d, 2; nNumberOfBytesToWrite
0x18003750e  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180037512  mov     rcx, rax; hFile
0x180037515  call    cs:__imp_WriteFile
0x18003751b  test    eax, eax
0x18003751d  jnz     short loc_180037531
0x18003751f  call    GetLastFailureAsHRESULT
0x180037524  mov     [rbp+57h+var_50], eax
0x180037527  mov     eax, 332h
0x18003752c  jmp     loc_180037448
0x180037531  mov     eax, 332h
0x180037536  mov     [rbp+57h+var_4C], ax
0x18003753a  mov     eax, 333h
0x18003753f  cmp     [rbp+57h+NumberOfBytesWritten], 2
0x180037543  jz      short loc_180037551
0x180037545  mov     [rbp+57h+var_50], 81000036h
0x18003754c  jmp     loc_180037448
0x180037551  mov     [rbp+57h+var_50], r14d
0x180037555  mov     [rbp+57h+var_4C], ax
0x180037559  mov     eax, dword ptr [rbp+57h+var_78]
0x18003755c  lea     edi, [rax+rax]
0x18003755f  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r14; lpOverlapped
0x180037564  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180037568  mov     r8d, edi; nNumberOfBytesToWrite
0x18003756b  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x18003756f  mov     rcx, rbx; hFile
0x180037572  call    cs:__imp_WriteFile
0x180037578  test    eax, eax
0x18003757a  jnz     short loc_18003758E
0x18003757c  call    GetLastFailureAsHRESULT
0x180037581  mov     [rbp+57h+var_50], eax
0x180037584  mov     eax, 334h
0x180037589  jmp     loc_180037448
0x18003758e  mov     eax, 334h
0x180037593  mov     [rbp+57h+var_4C], ax
0x180037597  mov     eax, 335h
0x18003759c  cmp     [rbp+57h+NumberOfBytesWritten], edi
0x18003759f  jnz     short loc_180037545
0x1800375a1  mov     [rbp+57h+var_50], r14d
0x1800375a5  mov     [rbp+57h+var_4C], ax
0x1800375a9  mov     edx, 6; dwFileAttributes
0x1800375ae  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800375b2  call    cs:__imp_SetFileAttributesW
0x1800375b8  test    eax, eax
0x1800375ba  jnz     short loc_1800375CE
0x1800375bc  call    GetLastFailureAsHRESULT
0x1800375c1  mov     [rbp+57h+var_50], eax
0x1800375c4  mov     eax, 337h
0x1800375c9  jmp     loc_180037448
0x1800375ce  mov     [rbp+57h+var_50], r14d
0x1800375d2  mov     eax, 337h
0x1800375d7  mov     [rbp+57h+var_4C], ax
0x1800375db  lea     rax, WPP_GLOBAL_Control
0x1800375e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800375e9  cmp     rcx, rax
0x1800375ec  jz      loc_180037698
0x1800375f2  test    byte ptr [rcx+1Ch], 20h
0x1800375f6  jz      loc_180037698
0x1800375fc  mov     edx, 15h
0x180037601  jmp     short loc_18003762C
0x180037603  call    cs:__imp_GetLastError
0x180037609  cmp     eax, 50h ; 'P'
0x18003760c  jnz     short loc_18003763E
0x18003760e  lea     rax, WPP_GLOBAL_Control
0x180037615  mov     rcx, cs:WPP_GLOBAL_Control
0x18003761c  cmp     rcx, rax
0x18003761f  jz      short loc_180037698
0x180037621  test    byte ptr [rcx+1Ch], 2
0x180037625  jz      short loc_180037698
0x180037627  mov     edx, 16h
0x18003762c  lea     r8, WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids
0x180037633  mov     rcx, [rcx+10h]
0x180037637  call    WPP_SF_
0x18003763c  jmp     short loc_180037698
0x18003763e  call    cs:__imp_GetLastError
0x180037644  mov     edi, eax
0x180037646  test    eax, eax
0x180037648  jle     short loc_180037653
0x18003764a  movzx   edi, ax
0x18003764d  or      edi, 80070000h
0x180037653  lea     rax, WPP_GLOBAL_Control
0x18003765a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037661  cmp     rcx, rax
0x180037664  jz      short loc_180037684
0x180037666  test    byte ptr [rcx+1Ch], 20h
0x18003766a  jz      short loc_180037684
0x18003766c  mov     edx, 17h
0x180037671  mov     r9d, edi
0x180037674  lea     r8, WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids
0x18003767b  mov     rcx, [rcx+10h]
0x18003767f  call    WPP_SF_d
0x180037684  mov     [rbp+57h+var_50], edi
0x180037687  mov     eax, 343h
0x18003768c  test    edi, edi
0x18003768e  js      loc_180037448
0x180037694  mov     [rbp+57h+var_4C], ax
0x180037698  mov     edi, [rbp+57h+var_50]
0x18003769b  lea     rcx, [rbp+57h+var_60]; this
0x18003769f  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800376a4  lea     rcx, [rbx-1]
0x1800376a8  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800376ac  ja      short loc_1800376B7
0x1800376ae  mov     rcx, rbx; hObject
0x1800376b1  call    cs:__imp_CloseHandle
0x1800376b7  lea     rcx, [rbp+57h+lpBuffer]; this
0x1800376bb  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800376c0  lea     rcx, [rbp+57h+lpFileName]; this
0x1800376c4  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800376c9  lea     rcx, [rbp+57h+var_50]; this
0x1800376cd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800376d2  mov     eax, edi
0x1800376d4  lea     r11, [rsp+0E0h+var_10]
0x1800376dc  mov     rbx, [r11+20h]
0x1800376e0  mov     rsi, [r11+38h]
0x1800376e4  mov     rsp, r11
0x1800376e7  pop     r14
0x1800376e9  pop     rdi
0x1800376ea  pop     rbp
0x1800376eb  retn
```
