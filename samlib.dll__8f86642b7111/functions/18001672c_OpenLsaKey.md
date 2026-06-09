# OpenLsaKey

- ea: `0x18001672c`
- end: `0x180016841`
- name: `OpenLsaKey`
- size: `277`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016848`
- `0x180016900`
- `0x180016e30`
- `0x180016eb4`

## callees

- `0x180006620`
- `0x18001672c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001679f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001679f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800167c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800167c9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016811`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016811`

## pseudocode

```c
HKEY OpenLsaKey()
{
  const WCHAR *v0; // rbx
  DWORD pcbData; // [rsp+50h] [rbp-238h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-230h] BYREF
  _BYTE pvData[528]; // [rsp+60h] [rbp-228h] BYREF

  pcbData = 260;
  phkResult = 0;
  v0 = (const WCHAR *)pvData;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Lsa",
         L"RedirectionKey",
         2u,
         0,
         pvData,
         &pcbData) )
  {
    v0 = L"System\\CurrentControlSet\\Control\\Lsa";
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v0, 0, 0x2001Fu, &phkResult) == 2
    && v0 != L"System\\CurrentControlSet\\Control\\Lsa" )
  {
    RegCreateKeyExW(HKEY_LOCAL_MACHINE, v0, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
  }
  return phkResult;
}

```

## disassembly

```asm
0x18001672c  mov     [rsp+arg_0], rbx
0x180016731  mov     [rsp+arg_8], rbp
0x180016736  push    rsi
0x180016737  sub     rsp, 280h
0x18001673e  mov     rax, cs:__security_cookie
0x180016745  xor     rax, rsp
0x180016748  mov     [rsp+288h+var_18], rax
0x180016750  lea     rax, [rsp+288h+var_238]
0x180016755  mov     [rsp+288h+var_238], 104h
0x18001675d  mov     [rsp+288h+pcbData], rax; pcbData
0x180016762  lea     rsi, SubKey; "System\\CurrentControlSet\\Control\\Lsa"
0x180016769  lea     rax, [rsp+288h+var_228]
0x18001676e  mov     [rsp+288h+phkResult], 0
0x180016777  mov     [rsp+288h+pvData], rax; pvData
0x18001677c  lea     r8, aRedirectionkey; "RedirectionKey"
0x180016783  mov     rbp, 0FFFFFFFF80000002h
0x18001678a  mov     [rsp+288h+pdwType], 0; pdwType
0x180016793  mov     r9d, 2; dwFlags
0x180016799  mov     rdx, rsi; lpSubKey
0x18001679c  mov     rcx, rbp; hkey
0x18001679f  call    cs:__imp_RegGetValueW
0x1800167a5  lea     rbx, [rsp+288h+var_228]
0x1800167aa  mov     r9d, 2001Fh; samDesired
0x1800167b0  test    eax, eax
0x1800167b2  mov     rcx, rbp; hKey
0x1800167b5  lea     rax, [rsp+288h+phkResult]
0x1800167ba  cmovnz  rbx, rsi
0x1800167be  mov     [rsp+288h+pdwType], rax; phkResult
0x1800167c3  mov     rdx, rbx; lpSubKey
0x1800167c6  xor     r8d, r8d; ulOptions
0x1800167c9  call    cs:__imp_RegOpenKeyExW
0x1800167cf  cmp     eax, 2
0x1800167d2  jnz     short loc_180016817
0x1800167d4  cmp     rbx, rsi
0x1800167d7  jz      short loc_180016817
0x1800167d9  mov     [rsp+288h+lpdwDisposition], 0; lpdwDisposition
0x1800167e2  lea     rax, [rsp+288h+phkResult]
0x1800167e7  mov     [rsp+288h+var_250], rax; phkResult
0x1800167ec  xor     r9d, r9d; lpClass
0x1800167ef  mov     [rsp+288h+pcbData], 0; lpSecurityAttributes
0x1800167f8  xor     r8d, r8d; Reserved
0x1800167fb  mov     dword ptr [rsp+288h+pvData], 2001Fh; samDesired
0x180016803  mov     rdx, rbx; lpSubKey
0x180016806  mov     rcx, rbp; hKey
0x180016809  mov     dword ptr [rsp+288h+pdwType], 0; dwOptions
0x180016811  call    cs:__imp_RegCreateKeyExW
0x180016817  mov     rax, [rsp+288h+phkResult]
0x18001681c  mov     rcx, [rsp+288h+var_18]
0x180016824  xor     rcx, rsp; StackCookie
0x180016827  call    __security_check_cookie
0x18001682c  lea     r11, [rsp+288h+var_8]
0x180016834  mov     rbx, [r11+10h]
0x180016838  mov     rbp, [r11+18h]
0x18001683c  mov     rsp, r11
0x18001683f  pop     rsi
0x180016840  retn
```
