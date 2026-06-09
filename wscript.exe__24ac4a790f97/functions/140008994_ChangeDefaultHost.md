# ChangeDefaultHost

- ea: `0x140008994`
- end: `0x140008b67`
- name: `ChangeDefaultHost`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000919c`

## callees

- `0x140001338`
- `0x140008994`
- `0x140008b70`
- `0x1400175a0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x140008a3a`
- `ADVAPI32!RegOpenKeyExA` at `0x140008a3a`
- `ADVAPI32!RegQueryValueExA` at `0x140008a75`
- `ADVAPI32!RegQueryValueExA` at `0x140008a75`
- `ADVAPI32!RegEnumKeyExA` at `0x140008af6`
- `ADVAPI32!RegEnumKeyExA` at `0x140008af6`
- `ADVAPI32!RegCloseKey` at `0x140008a82`
- `ADVAPI32!RegCloseKey` at `0x140008a82`

## string_xrefs

- `0x1400089e1`: `Open2`

## pseudocode

```c
signed int __fastcall ChangeDefaultHost(int a1)
{
  signed int result; // eax
  const char *v2; // rdi
  DWORD v3; // esi
  DWORD i; // edx
  bool v5; // cc
  LSTATUS v6; // ebx
  __int64 v7; // rax
  int v8; // eax
  int v9; // ecx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  CHAR SubKey[272]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[272]; // [rsp+160h] [rbp+60h] BYREF

  hKey = 0;
  if ( a1 == 67 )
  {
    v2 = "Open2";
  }
  else
  {
    if ( a1 != 87 )
      return -2147024809;
    v2 = "Open";
  }
  v3 = 0;
  for ( i = 0; ; i = v3 )
  {
    cbData = 260;
    result = RegEnumKeyExA(HKEY_CLASSES_ROOT, i, SubKey, &cbData, 0, 0, 0, 0);
    if ( result == 259 )
    {
      result = ChangeDefaultHostCore("WSFFile", (const BYTE *)v2, 0);
      if ( result >= 0 )
      {
        v8 = ChangeDefaultHostCore("WSHFile", (const BYTE *)v2, 0);
        v9 = 0;
        if ( v8 < 0 )
          return v8;
        return v9;
      }
      return result;
    }
    v5 = result <= 0;
    if ( result )
      break;
    if ( SubKey[0] == 46 )
    {
      result = RegOpenKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey);
      v5 = result <= 0;
      if ( result )
        break;
      cbData = 260;
      v6 = RegQueryValueExA(hKey, ValueName, 0, 0, Data, &cbData);
      RegCloseKey(hKey);
      if ( !v6 && cbData )
      {
        v7 = cbData - 1;
        if ( (unsigned int)v7 >= 0x104 )
          _report_rangecheckfailure();
        SubKey[v7] = 0;
        result = ChangeDefaultHostCore((LPCSTR)Data, (const BYTE *)v2, 1);
        if ( result < 0 )
          return result;
      }
    }
    ++v3;
  }
  if ( !v5 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140008994  push    rbp
0x140008996  push    rbx
0x140008997  push    rsi
0x140008998  push    rdi
0x140008999  push    r12
0x14000899b  lea     rbp, [rsp-180h]
0x1400089a3  sub     rsp, 280h
0x1400089aa  mov     rax, cs:__security_cookie
0x1400089b1  xor     rax, rsp
0x1400089b4  mov     [rbp+1A0h+var_30], rax
0x1400089bb  mov     [rsp+2A0h+hKey], 0
0x1400089c4  cmp     ecx, 43h ; 'C'
0x1400089c7  jz      short loc_1400089E1
0x1400089c9  cmp     ecx, 57h ; 'W'
0x1400089cc  jz      short loc_1400089D8
0x1400089ce  mov     eax, 80070057h
0x1400089d3  jmp     loc_140008B38
0x1400089d8  lea     rdi, aOpen; "Open"
0x1400089df  jmp     short loc_1400089E8
0x1400089e1  lea     rdi, aOpen2; "Open2"
0x1400089e8  xor     esi, esi
0x1400089ea  mov     r12, 0FFFFFFFF80000000h
0x1400089f1  mov     [rsp+2A0h+lpftLastWriteTime], rsi
0x1400089f6  xor     edx, edx
0x1400089f8  mov     [rsp+2A0h+lpcchClass], rsi
0x1400089fd  mov     [rsp+2A0h+lpcbData], rsi
0x140008a02  mov     [rsp+2A0h+phkResult], rsi
0x140008a07  jmp     loc_140008AE1
0x140008a0c  test    eax, eax
0x140008a0e  jnz     loc_140008B55
0x140008a14  cmp     [rsp+2A0h+SubKey], 2Eh ; '.'
0x140008a19  jnz     loc_140008AB9
0x140008a1f  lea     rax, [rsp+2A0h+hKey]
0x140008a24  mov     r9d, 20019h; samDesired
0x140008a2a  xor     r8d, r8d; ulOptions
0x140008a2d  mov     [rsp+2A0h+phkResult], rax; phkResult
0x140008a32  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x140008a37  mov     rcx, r12; hKey
0x140008a3a  call    cs:__imp_RegOpenKeyExA
0x140008a40  test    eax, eax
0x140008a42  jnz     loc_140008B55
0x140008a48  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140008a4d  lea     rax, [rsp+2A0h+cbData]
0x140008a52  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x140008a57  lea     rdx, ValueName; lpValueName
0x140008a5e  lea     rax, [rbp+1A0h+Data]
0x140008a62  mov     [rsp+2A0h+cbData], 104h
0x140008a6a  xor     r9d, r9d; lpType
0x140008a6d  mov     [rsp+2A0h+phkResult], rax; lpData
0x140008a72  xor     r8d, r8d; lpReserved
0x140008a75  call    cs:__imp_RegQueryValueExA
0x140008a7b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140008a80  mov     ebx, eax
0x140008a82  call    cs:__imp_RegCloseKey
0x140008a88  test    ebx, ebx
0x140008a8a  jnz     short loc_140008AB9
0x140008a8c  mov     eax, [rsp+2A0h+cbData]
0x140008a90  test    eax, eax
0x140008a92  jz      short loc_140008AB9
0x140008a94  dec     eax
0x140008a96  cmp     eax, 104h
0x140008a9b  jnb     loc_140008B61
0x140008aa1  lea     r8d, [rbx+1]
0x140008aa5  mov     [rsp+rax+2A0h+SubKey], bl
0x140008aa9  mov     rdx, rdi
0x140008aac  lea     rcx, [rbp+1A0h+Data]; lpSubKey
0x140008ab0  call    ChangeDefaultHostCore
0x140008ab5  test    eax, eax
0x140008ab7  js      short loc_140008B38
0x140008ab9  mov     [rsp+2A0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140008ac2  inc     esi
0x140008ac4  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x140008acd  mov     edx, esi; dwIndex
0x140008acf  mov     [rsp+2A0h+lpcbData], 0; lpClass
0x140008ad8  mov     [rsp+2A0h+phkResult], 0; lpReserved
0x140008ae1  lea     r9, [rsp+2A0h+cbData]; lpcchName
0x140008ae6  mov     [rsp+2A0h+cbData], 104h
0x140008aee  lea     r8, [rsp+2A0h+SubKey]; lpName
0x140008af3  mov     rcx, r12; hKey
0x140008af6  call    cs:__imp_RegEnumKeyExA
0x140008afc  cmp     eax, 103h
0x140008b01  jnz     loc_140008A0C
0x140008b07  xor     r8d, r8d
0x140008b0a  lea     rcx, aWsffile; "WSFFile"
0x140008b11  mov     rdx, rdi
0x140008b14  call    ChangeDefaultHostCore
0x140008b19  test    eax, eax
0x140008b1b  js      short loc_140008B38
0x140008b1d  xor     r8d, r8d
0x140008b20  lea     rcx, aWshfile; "WSHFile"
0x140008b27  mov     rdx, rdi
0x140008b2a  call    ChangeDefaultHostCore
0x140008b2f  xor     ecx, ecx
0x140008b31  test    eax, eax
0x140008b33  cmovs   ecx, eax
0x140008b36  mov     eax, ecx
0x140008b38  mov     rcx, [rbp+1A0h+var_30]
0x140008b3f  xor     rcx, rsp; StackCookie
0x140008b42  call    __security_check_cookie
0x140008b47  add     rsp, 280h
0x140008b4e  pop     r12
0x140008b50  pop     rdi
0x140008b51  pop     rsi
0x140008b52  pop     rbx
0x140008b53  pop     rbp
0x140008b54  retn
0x140008b55  jle     short loc_140008B38
0x140008b57  movzx   eax, ax
0x140008b5a  or      eax, 80070000h
0x140008b5f  jmp     short loc_140008B38
0x140008b61  call    __report_rangecheckfailure
```
