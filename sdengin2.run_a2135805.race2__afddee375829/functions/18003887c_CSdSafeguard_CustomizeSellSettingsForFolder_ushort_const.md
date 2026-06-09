# CSdSafeguard::_CustomizeSellSettingsForFolder(ushort const *)

- ea: `0x18003887c`
- end: `0x180038bd1`
- name: `?_CustomizeSellSettingsForFolder@CSdSafeguard@@AEAAJPEBG@Z`
- size: `853`
- prototype: `int(CSdSafeguard *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180037600`

## callees

- `0x180008370`
- `0x1800083a0`
- `0x18003887c`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009e904`
- `0x18009ea34`
- `0x18009f560`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x180038935`
- `KERNEL32!SetFileAttributesW` at `0x180038a7e`
- `KERNEL32!SetFileAttributesW` at `0x180038935`
- `KERNEL32!SetFileAttributesW` at `0x180038a7e`
- `KERNEL32!CreateFileW` at `0x1800389a6`
- `KERNEL32!CreateFileW` at `0x1800389a6`
- `KERNEL32!GetLastError` at `0x180038ad5`
- `KERNEL32!GetLastError` at `0x180038b16`
- `KERNEL32!GetLastError` at `0x180038ad5`
- `KERNEL32!GetLastError` at `0x180038b16`
- `KERNEL32!CloseHandle` at `0x180038b8f`
- `KERNEL32!CloseHandle` at `0x180038b8f`
- `KERNEL32!WriteFile` at `0x1800389d5`
- `KERNEL32!WriteFile` at `0x180038a38`
- `KERNEL32!WriteFile` at `0x1800389d5`
- `KERNEL32!WriteFile` at `0x180038a38`

## string_xrefs

- `0x18003890d`: `[.ShellClassInfo]\nDirectoryClass=WindowsBackupFolderOptions\nIconResource=%SystemRoot%\system32\sdclt.exe,-5501`

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
    0x311u,
    1u);
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpFileName[1] = 0;
  lpBuffer = qword_1800EE510;
  v24 = 0;
  v4 = -1;
  NumberOfBytesWritten = 0;
  v26[0] = qword_1800EE510;
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
0x18003887c  mov     [rsp-8+arg_0], rbx
0x180038881  mov     [rsp-8+arg_18], rsi
0x180038886  push    rbp
0x180038887  push    rdi
0x180038888  push    r14
0x18003888a  lea     rbp, [rsp-47h]
0x18003888f  sub     rsp, 0D0h
0x180038896  mov     rdi, rdx
0x180038899  mov     rsi, rcx
0x18003889c  mov     r9d, 1; unsigned __int16
0x1800388a2  mov     r8d, 311h; unsigned __int16
0x1800388a8  lea     rdx, aCsdsafeguardCu; "CSdSafeguard::_CustomizeSellSettingsFor"...
0x1800388af  lea     rcx, [rbp+57h+var_50]; this
0x1800388b3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800388b8  lea     rax, qword_1800EE510
0x1800388bf  mov     [rbp+57h+lpFileName], rax
0x1800388c3  xor     r14d, r14d
0x1800388c6  mov     [rbp+57h+var_68], r14
0x1800388ca  mov     [rbp+57h+lpBuffer], rax
0x1800388ce  mov     [rbp+57h+var_78], r14
0x1800388d2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800388d6  mov     [rbp+57h+NumberOfBytesWritten], r14d
0x1800388da  mov     [rbp+57h+var_60], rax
0x1800388de  mov     [rbp+57h+var_58], r14
0x1800388e2  mov     eax, 0FEFFh
0x1800388e7  mov     [rbp+57h+Buffer], ax
0x1800388eb  mov     eax, 31Dh
0x1800388f0  test    rdi, rdi
0x1800388f3  jnz     short loc_180038905
0x1800388f5  mov     [rbp+57h+var_50], 80070057h
0x1800388fc  mov     [rbp+57h+var_4A], ax
0x180038900  jmp     loc_180038B76
0x180038905  mov     [rbp+57h+var_50], r14d
0x180038909  mov     [rbp+57h+var_4C], ax
0x18003890d  lea     rdx, aShellclassinfo; "[.ShellClassInfo]\r\nDirectoryClass=Win"...
0x180038914  lea     rcx, [rbp+57h+lpBuffer]; this
0x180038918  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003891d  mov     [rbp+57h+var_50], eax
0x180038920  test    eax, eax
0x180038922  mov     eax, 31Fh
0x180038927  js      short loc_1800388FC
0x180038929  mov     [rbp+57h+var_4C], ax
0x18003892d  mov     edx, 1; dwFileAttributes
0x180038932  mov     rcx, rdi; lpFileName
0x180038935  call    cs:__imp_SetFileAttributesW
0x18003893c  nop     dword ptr [rax+rax+00h]
0x180038941  test    eax, eax
0x180038943  jnz     short loc_180038954
0x180038945  call    GetLastFailureAsHRESULT
0x18003894a  mov     [rbp+57h+var_50], eax
0x18003894d  mov     eax, 321h
0x180038952  jmp     short loc_1800388FC
0x180038954  mov     [rbp+57h+var_50], r14d
0x180038958  mov     eax, 321h
0x18003895d  mov     [rbp+57h+var_4C], ax
0x180038961  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], r14; unsigned __int16 *
0x180038966  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r14; unsigned __int16 *
0x18003896b  xor     r9d, r9d; unsigned __int16 *
0x18003896e  lea     r8, aDesktopIni; "Desktop.ini"
0x180038975  mov     rdx, rdi; unsigned __int16 *
0x180038978  lea     rcx, [rbp+57h+lpFileName]; this
0x18003897c  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180038981  lea     r9, [rsi+48h]; lpSecurityAttributes
0x180038985  mov     [rsp+0E0h+hTemplateFile], r14; hTemplateFile
0x18003898a  mov     [rsp+0E0h+dwFlagsAndAttributes], 1; dwFlagsAndAttributes
0x180038992  mov     [rsp+0E0h+dwCreationDisposition], 1; dwCreationDisposition
0x18003899a  xor     r8d, r8d; dwShareMode
0x18003899d  mov     edx, 0C0000000h; dwDesiredAccess
0x1800389a2  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800389a6  call    cs:__imp_CreateFileW
0x1800389ad  nop     dword ptr [rax+rax+00h]
0x1800389b2  mov     rbx, rax
0x1800389b5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800389b9  jz      loc_180038AD5
0x1800389bf  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r14; lpOverlapped
0x1800389c4  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800389c8  mov     r8d, 2; nNumberOfBytesToWrite
0x1800389ce  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x1800389d2  mov     rcx, rax; hFile
0x1800389d5  call    cs:__imp_WriteFile
0x1800389dc  nop     dword ptr [rax+rax+00h]
0x1800389e1  test    eax, eax
0x1800389e3  jnz     short loc_1800389F7
0x1800389e5  call    GetLastFailureAsHRESULT
0x1800389ea  mov     [rbp+57h+var_50], eax
0x1800389ed  mov     eax, 332h
0x1800389f2  jmp     loc_1800388FC
0x1800389f7  mov     eax, 332h
0x1800389fc  mov     [rbp+57h+var_4C], ax
0x180038a00  mov     eax, 333h
0x180038a05  cmp     [rbp+57h+NumberOfBytesWritten], 2
0x180038a09  jz      short loc_180038A17
0x180038a0b  mov     [rbp+57h+var_50], 81000036h
0x180038a12  jmp     loc_1800388FC
0x180038a17  mov     [rbp+57h+var_50], r14d
0x180038a1b  mov     [rbp+57h+var_4C], ax
0x180038a1f  mov     eax, dword ptr [rbp+57h+var_78]
0x180038a22  lea     edi, [rax+rax]
0x180038a25  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r14; lpOverlapped
0x180038a2a  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180038a2e  mov     r8d, edi; nNumberOfBytesToWrite
0x180038a31  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x180038a35  mov     rcx, rbx; hFile
0x180038a38  call    cs:__imp_WriteFile
0x180038a3f  nop     dword ptr [rax+rax+00h]
0x180038a44  test    eax, eax
0x180038a46  jnz     short loc_180038A5A
0x180038a48  call    GetLastFailureAsHRESULT
0x180038a4d  mov     [rbp+57h+var_50], eax
0x180038a50  mov     eax, 334h
0x180038a55  jmp     loc_1800388FC
0x180038a5a  mov     eax, 334h
0x180038a5f  mov     [rbp+57h+var_4C], ax
0x180038a63  mov     eax, 335h
0x180038a68  cmp     [rbp+57h+NumberOfBytesWritten], edi
0x180038a6b  jnz     short loc_180038A0B
0x180038a6d  mov     [rbp+57h+var_50], r14d
0x180038a71  mov     [rbp+57h+var_4C], ax
0x180038a75  mov     edx, 6; dwFileAttributes
0x180038a7a  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180038a7e  call    cs:__imp_SetFileAttributesW
0x180038a85  nop     dword ptr [rax+rax+00h]
0x180038a8a  test    eax, eax
0x180038a8c  jnz     short loc_180038AA0
0x180038a8e  call    GetLastFailureAsHRESULT
0x180038a93  mov     [rbp+57h+var_50], eax
0x180038a96  mov     eax, 337h
0x180038a9b  jmp     loc_1800388FC
0x180038aa0  mov     [rbp+57h+var_50], r14d
0x180038aa4  mov     eax, 337h
0x180038aa9  mov     [rbp+57h+var_4C], ax
0x180038aad  lea     rax, WPP_GLOBAL_Control
0x180038ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x180038abb  cmp     rcx, rax
0x180038abe  jz      loc_180038B76
0x180038ac4  test    byte ptr [rcx+1Ch], 20h
0x180038ac8  jz      loc_180038B76
0x180038ace  mov     edx, 15h
0x180038ad3  jmp     short loc_180038B04
0x180038ad5  call    cs:__imp_GetLastError
0x180038adc  nop     dword ptr [rax+rax+00h]
0x180038ae1  cmp     eax, 50h ; 'P'
0x180038ae4  jnz     short loc_180038B16
0x180038ae6  lea     rax, WPP_GLOBAL_Control
0x180038aed  mov     rcx, cs:WPP_GLOBAL_Control
0x180038af4  cmp     rcx, rax
0x180038af7  jz      short loc_180038B76
0x180038af9  test    byte ptr [rcx+1Ch], 2
0x180038afd  jz      short loc_180038B76
0x180038aff  mov     edx, 16h
0x180038b04  lea     r8, WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids
0x180038b0b  mov     rcx, [rcx+10h]
0x180038b0f  call    WPP_SF_
0x180038b14  jmp     short loc_180038B76
0x180038b16  call    cs:__imp_GetLastError
0x180038b1d  nop     dword ptr [rax+rax+00h]
0x180038b22  mov     edi, eax
0x180038b24  test    eax, eax
0x180038b26  jle     short loc_180038B31
0x180038b28  movzx   edi, ax
0x180038b2b  or      edi, 80070000h
0x180038b31  lea     rax, WPP_GLOBAL_Control
0x180038b38  mov     rcx, cs:WPP_GLOBAL_Control
0x180038b3f  cmp     rcx, rax
0x180038b42  jz      short loc_180038B62
0x180038b44  test    byte ptr [rcx+1Ch], 20h
0x180038b48  jz      short loc_180038B62
0x180038b4a  mov     edx, 17h
0x180038b4f  mov     r9d, edi
0x180038b52  lea     r8, WPP_2818ddfe77cb3e37cabd910f13877d81_Traceguids
0x180038b59  mov     rcx, [rcx+10h]
0x180038b5d  call    WPP_SF_d
0x180038b62  mov     [rbp+57h+var_50], edi
0x180038b65  mov     eax, 343h
0x180038b6a  test    edi, edi
0x180038b6c  js      loc_1800388FC
0x180038b72  mov     [rbp+57h+var_4C], ax
0x180038b76  mov     edi, [rbp+57h+var_50]
0x180038b79  lea     rcx, [rbp+57h+var_60]; this
0x180038b7d  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180038b82  lea     rcx, [rbx-1]
0x180038b86  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180038b8a  ja      short loc_180038B9B
0x180038b8c  mov     rcx, rbx; hObject
0x180038b8f  call    cs:__imp_CloseHandle
0x180038b96  nop     dword ptr [rax+rax+00h]
0x180038b9b  lea     rcx, [rbp+57h+lpBuffer]; this
0x180038b9f  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180038ba4  lea     rcx, [rbp+57h+lpFileName]; this
0x180038ba8  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180038bad  lea     rcx, [rbp+57h+var_50]; this
0x180038bb1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180038bb6  mov     eax, edi
0x180038bb8  lea     r11, [rsp+0E0h+var_10]
0x180038bc0  mov     rbx, [r11+20h]
0x180038bc4  mov     rsi, [r11+38h]
0x180038bc8  mov     rsp, r11
0x180038bcb  pop     r14
0x180038bcd  pop     rdi
0x180038bce  pop     rbp
0x180038bcf  retn
```
