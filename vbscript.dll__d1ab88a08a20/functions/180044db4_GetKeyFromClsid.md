# GetKeyFromClsid

- ea: `0x180044db4`
- end: `0x180044f49`
- name: `GetKeyFromClsid`
- size: `405`
- prototype: `__int64 __fastcall(IID *rclsid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006617c`

## callees

- `0x180044db4`
- `0x180079490`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180044e8a`
- `KERNEL32!WideCharToMultiByte` at `0x180044e8a`
- `OLE32!CoTaskMemFree` at `0x180044ee9`
- `OLE32!CoTaskMemFree` at `0x180044ee9`
- `OLE32!StringFromCLSID` at `0x180044e45`
- `OLE32!StringFromCLSID` at `0x180044e45`
- `ADVAPI32!RegOpenKeyExA` at `0x180044e1b`
- `ADVAPI32!RegOpenKeyExA` at `0x180044eb0`
- `ADVAPI32!RegOpenKeyExA` at `0x180044e1b`
- `ADVAPI32!RegOpenKeyExA` at `0x180044eb0`
- `ADVAPI32!RegCloseKey` at `0x180044efe`
- `ADVAPI32!RegCloseKey` at `0x180044f1b`
- `ADVAPI32!RegCloseKey` at `0x180044efe`
- `ADVAPI32!RegCloseKey` at `0x180044f1b`

## string_xrefs

- `0x180044df7`: `CLSID`

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
0x180044db4  mov     [rsp-8+arg_10], rbx
0x180044db9  push    rbp
0x180044dba  push    rsi
0x180044dbb  push    rdi
0x180044dbc  lea     rbp, [rsp-47h]
0x180044dc1  sub     rsp, 90h
0x180044dc8  mov     rax, cs:__security_cookie
0x180044dcf  xor     rax, rsp
0x180044dd2  mov     [rbp+57h+var_18], rax
0x180044dd6  mov     rdi, rdx
0x180044dd9  mov     qword ptr [rdx], 0
0x180044de0  mov     rsi, rcx
0x180044de3  mov     [rbp+57h+lpsz], 0
0x180044deb  lea     rax, [rbp+57h+hKey]
0x180044def  mov     [rbp+57h+hKey], 0
0x180044df7  lea     rdx, aClsid; "CLSID"
0x180044dfe  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180044e03  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180044e0a  mov     [rbp+57h+var_60], 0
0x180044e12  mov     r9d, 20019h; samDesired
0x180044e18  xor     r8d, r8d; ulOptions
0x180044e1b  call    cs:__imp_RegOpenKeyExA
0x180044e22  nop     dword ptr [rax+rax+00h]
0x180044e27  mov     ebx, eax
0x180044e29  test    eax, eax
0x180044e2b  jle     short loc_180044E36
0x180044e2d  movzx   ebx, ax
0x180044e30  or      ebx, 80070000h
0x180044e36  test    ebx, ebx
0x180044e38  js      loc_180044EE0
0x180044e3e  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x180044e42  mov     rcx, rsi; rclsid
0x180044e45  call    cs:__imp_StringFromCLSID
0x180044e4c  nop     dword ptr [rax+rax+00h]
0x180044e51  mov     ebx, eax
0x180044e53  test    eax, eax
0x180044e55  js      loc_180044EE0
0x180044e5b  mov     r8, [rbp+57h+lpsz]; lpWideCharStr
0x180044e5f  lea     rax, [rbp+57h+MultiByteStr]
0x180044e63  mov     [rsp+0A0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180044e6c  or      r9d, 0FFFFFFFFh; cchWideChar
0x180044e70  mov     [rsp+0A0h+lpDefaultChar], 0; lpDefaultChar
0x180044e79  xor     edx, edx; dwFlags
0x180044e7b  mov     [rsp+0A0h+cbMultiByte], 30h ; '0'; cbMultiByte
0x180044e83  xor     ecx, ecx; CodePage
0x180044e85  mov     [rsp+0A0h+phkResult], rax; lpMultiByteStr
0x180044e8a  call    cs:__imp_WideCharToMultiByte
0x180044e91  nop     dword ptr [rax+rax+00h]
0x180044e96  mov     rcx, [rbp+57h+hKey]; hKey
0x180044e9a  lea     rax, [rbp+57h+var_60]
0x180044e9e  mov     r9d, 20019h; samDesired
0x180044ea4  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180044ea9  xor     r8d, r8d; ulOptions
0x180044eac  lea     rdx, [rbp+57h+MultiByteStr]; lpSubKey
0x180044eb0  call    cs:__imp_RegOpenKeyExA
0x180044eb7  nop     dword ptr [rax+rax+00h]
0x180044ebc  mov     ebx, eax
0x180044ebe  test    eax, eax
0x180044ec0  jle     short loc_180044ECB
0x180044ec2  movzx   ebx, ax
0x180044ec5  or      ebx, 80070000h
0x180044ecb  test    ebx, ebx
0x180044ecd  js      short loc_180044EE0
0x180044ecf  mov     rax, [rbp+57h+var_60]
0x180044ed3  xor     ebx, ebx
0x180044ed5  mov     [rdi], rax
0x180044ed8  mov     [rbp+57h+var_60], 0
0x180044ee0  mov     rcx, [rbp+57h+lpsz]; pv
0x180044ee4  test    rcx, rcx
0x180044ee7  jz      short loc_180044EF5
0x180044ee9  call    cs:__imp_CoTaskMemFree
0x180044ef0  nop     dword ptr [rax+rax+00h]
0x180044ef5  mov     rcx, [rbp+57h+var_60]; hKey
0x180044ef9  test    rcx, rcx
0x180044efc  jz      short loc_180044F12
0x180044efe  call    cs:__imp_RegCloseKey
0x180044f05  nop     dword ptr [rax+rax+00h]
0x180044f0a  mov     [rbp+57h+var_60], 0
0x180044f12  mov     rcx, [rbp+57h+hKey]; hKey
0x180044f16  test    rcx, rcx
0x180044f19  jz      short loc_180044F27
0x180044f1b  call    cs:__imp_RegCloseKey
0x180044f22  nop     dword ptr [rax+rax+00h]
0x180044f27  mov     eax, ebx
0x180044f29  mov     rcx, [rbp+57h+var_18]
0x180044f2d  xor     rcx, rsp; StackCookie
0x180044f30  call    __security_check_cookie
0x180044f35  mov     rbx, [rsp+0A0h+arg_10]
0x180044f3d  add     rsp, 90h
0x180044f44  pop     rdi
0x180044f45  pop     rsi
0x180044f46  pop     rbp
0x180044f47  retn
```
