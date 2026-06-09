# GetKeyFromClsid

- ea: `0x180043b90`
- end: `0x180043cf6`
- name: `GetKeyFromClsid`
- size: `358`
- prototype: `__int64 __fastcall(IID *rclsid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800643ac`

## callees

- `0x180043b90`
- `0x1800767a0`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180043c56`
- `KERNEL32!WideCharToMultiByte` at `0x180043c56`
- `OLE32!CoTaskMemFree` at `0x180043ca9`
- `OLE32!CoTaskMemFree` at `0x180043ca9`
- `OLE32!StringFromCLSID` at `0x180043c1b`
- `OLE32!StringFromCLSID` at `0x180043c1b`
- `ADVAPI32!RegOpenKeyExA` at `0x180043bf7`
- `ADVAPI32!RegOpenKeyExA` at `0x180043c76`
- `ADVAPI32!RegOpenKeyExA` at `0x180043bf7`
- `ADVAPI32!RegOpenKeyExA` at `0x180043c76`
- `ADVAPI32!RegCloseKey` at `0x180043cb8`
- `ADVAPI32!RegCloseKey` at `0x180043ccf`
- `ADVAPI32!RegCloseKey` at `0x180043cb8`
- `ADVAPI32!RegCloseKey` at `0x180043ccf`

## string_xrefs

- `0x180043bd3`: `CLSID`

## pseudocode

```c
__int64 __fastcall GetKeyFromClsid(IID *rclsid, HKEY *a2)
{
  LSTATUS v4; // eax
  int v5; // ebx
  LSTATUS v6; // eax
  HKEY phkResult; // [rsp+40h] [rbp-9h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+7h] BYREF
  CHAR MultiByteStr[48]; // [rsp+58h] [rbp+Fh] BYREF

  *a2 = 0;
  lpsz = 0;
  hKey = 0;
  phkResult = 0;
  v4 = RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    v5 = StringFromCLSID(rclsid, &lpsz);
    if ( v5 >= 0 )
    {
      WideCharToMultiByte(0, 0, lpsz, -1, MultiByteStr, 48, 0, 0);
      v6 = RegOpenKeyExA(hKey, MultiByteStr, 0, 0x20019u, &phkResult);
      v5 = v6;
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v5 >= 0 )
      {
        v5 = 0;
        *a2 = phkResult;
        phkResult = 0;
      }
    }
  }
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180043b90  mov     [rsp-8+arg_10], rbx
0x180043b95  push    rbp
0x180043b96  push    rsi
0x180043b97  push    rdi
0x180043b98  lea     rbp, [rsp-47h]
0x180043b9d  sub     rsp, 90h
0x180043ba4  mov     rax, cs:__security_cookie
0x180043bab  xor     rax, rsp
0x180043bae  mov     [rbp+57h+var_18], rax
0x180043bb2  mov     rdi, rdx
0x180043bb5  mov     qword ptr [rdx], 0
0x180043bbc  mov     rsi, rcx
0x180043bbf  mov     [rbp+57h+lpsz], 0
0x180043bc7  lea     rax, [rbp+57h+hKey]
0x180043bcb  mov     [rbp+57h+hKey], 0
0x180043bd3  lea     rdx, aClsid; "CLSID"
0x180043bda  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180043bdf  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180043be6  mov     [rbp+57h+var_60], 0
0x180043bee  mov     r9d, 20019h; samDesired
0x180043bf4  xor     r8d, r8d; ulOptions
0x180043bf7  call    cs:__imp_RegOpenKeyExA
0x180043bfd  mov     ebx, eax
0x180043bff  test    eax, eax
0x180043c01  jle     short loc_180043C0C
0x180043c03  movzx   ebx, ax
0x180043c06  or      ebx, 80070000h
0x180043c0c  test    ebx, ebx
0x180043c0e  js      loc_180043CA0
0x180043c14  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x180043c18  mov     rcx, rsi; rclsid
0x180043c1b  call    cs:__imp_StringFromCLSID
0x180043c21  mov     ebx, eax
0x180043c23  test    eax, eax
0x180043c25  js      short loc_180043CA0
0x180043c27  mov     r8, [rbp+57h+lpsz]; lpWideCharStr
0x180043c2b  lea     rax, [rbp+57h+MultiByteStr]
0x180043c2f  mov     [rsp+0A0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180043c38  or      r9d, 0FFFFFFFFh; cchWideChar
0x180043c3c  mov     [rsp+0A0h+lpDefaultChar], 0; lpDefaultChar
0x180043c45  xor     edx, edx; dwFlags
0x180043c47  mov     [rsp+0A0h+cbMultiByte], 30h ; '0'; cbMultiByte
0x180043c4f  xor     ecx, ecx; CodePage
0x180043c51  mov     [rsp+0A0h+phkResult], rax; lpMultiByteStr
0x180043c56  call    cs:__imp_WideCharToMultiByte
0x180043c5c  mov     rcx, [rbp+57h+hKey]; hKey
0x180043c60  lea     rax, [rbp+57h+var_60]
0x180043c64  mov     r9d, 20019h; samDesired
0x180043c6a  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180043c6f  xor     r8d, r8d; ulOptions
0x180043c72  lea     rdx, [rbp+57h+MultiByteStr]; lpSubKey
0x180043c76  call    cs:__imp_RegOpenKeyExA
0x180043c7c  mov     ebx, eax
0x180043c7e  test    eax, eax
0x180043c80  jle     short loc_180043C8B
0x180043c82  movzx   ebx, ax
0x180043c85  or      ebx, 80070000h
0x180043c8b  test    ebx, ebx
0x180043c8d  js      short loc_180043CA0
0x180043c8f  mov     rax, [rbp+57h+var_60]
0x180043c93  xor     ebx, ebx
0x180043c95  mov     [rdi], rax
0x180043c98  mov     [rbp+57h+var_60], 0
0x180043ca0  mov     rcx, [rbp+57h+lpsz]; pv
0x180043ca4  test    rcx, rcx
0x180043ca7  jz      short loc_180043CAF
0x180043ca9  call    cs:__imp_CoTaskMemFree
0x180043caf  mov     rcx, [rbp+57h+var_60]; hKey
0x180043cb3  test    rcx, rcx
0x180043cb6  jz      short loc_180043CC6
0x180043cb8  call    cs:__imp_RegCloseKey
0x180043cbe  mov     [rbp+57h+var_60], 0
0x180043cc6  mov     rcx, [rbp+57h+hKey]; hKey
0x180043cca  test    rcx, rcx
0x180043ccd  jz      short loc_180043CD5
0x180043ccf  call    cs:__imp_RegCloseKey
0x180043cd5  mov     eax, ebx
0x180043cd7  mov     rcx, [rbp+57h+var_18]
0x180043cdb  xor     rcx, rsp; StackCookie
0x180043cde  call    __security_check_cookie
0x180043ce3  mov     rbx, [rsp+0A0h+arg_10]
0x180043ceb  add     rsp, 90h
0x180043cf2  pop     rdi
0x180043cf3  pop     rsi
0x180043cf4  pop     rbp
0x180043cf5  retn
```
