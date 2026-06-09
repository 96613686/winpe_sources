# RegCreateKeyHelperPrivate

- ea: `0x1400107fc`
- end: `0x140010954`
- name: `RegCreateKeyHelperPrivate`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001095c`

## callees

- `0x1400105d8`
- `0x1400107fc`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140010896`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400108ed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140010896`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400108ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001091c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001092b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001091c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001092b`

## string_xrefs

- `0x140010867`: `Software\Classes\CLSID`

## pseudocode

```c
__int64 __fastcall RegCreateKeyHelperPrivate(__int64 a1, __int64 a2, const WCHAR *a3, HKEY *a4)
{
  signed int v6; // ebx
  REGSAM v7; // r14d
  LSTATUS v8; // eax
  REGSAM samDesired; // [rsp+50h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF

  hKey = 0;
  phkResult = 0;
  samDesired = 131078;
  *a4 = 0;
  v6 = SetRegistryType(a1, &samDesired);
  if ( v6 >= 0 )
  {
    v7 = samDesired;
    v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\CLSID", 0, 0, 0, samDesired, 0, &hKey, 0);
    if ( v8 )
    {
LABEL_3:
      v6 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 <= 0 )
        v6 = v8;
      goto LABEL_10;
    }
    if ( a3 )
    {
      v8 = RegCreateKeyExW(hKey, a3, 0, 0, 1u, v7, 0, &phkResult, 0);
      if ( !v8 )
      {
        *a4 = phkResult;
        phkResult = 0;
        goto LABEL_12;
      }
      goto LABEL_3;
    }
    *a4 = hKey;
    hKey = 0;
  }
LABEL_10:
  if ( phkResult )
    RegCloseKey(phkResult);
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400107fc  mov     [rsp-18h+arg_0], rbx
0x140010801  mov     [rsp-18h+arg_8], rsi
0x140010806  push    rbp
0x140010807  push    rdi
0x140010808  push    r14
0x14001080a  mov     rbp, rsp
0x14001080d  sub     rsp, 70h
0x140010811  mov     rax, cs:__security_cookie
0x140010818  xor     rax, rsp
0x14001081b  mov     [rbp+var_8], rax
0x14001081f  lea     rdx, [rbp+var_20]
0x140010823  mov     [rbp+hKey], 0
0x14001082b  mov     rdi, r9
0x14001082e  mov     [rbp+var_18], 0
0x140010836  mov     rsi, r8
0x140010839  mov     [rbp+var_20], 20006h
0x140010840  mov     qword ptr [r9], 0
0x140010847  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x14001084c  mov     ebx, eax
0x14001084e  test    eax, eax
0x140010850  js      loc_140010913
0x140010856  mov     r14d, [rbp+var_20]
0x14001085a  lea     rax, [rbp+hKey]
0x14001085e  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x140010867  lea     rdx, SubKey; "Software\\Classes\\CLSID"
0x14001086e  mov     [rsp+70h+phkResult], rax; phkResult
0x140010873  xor     r9d, r9d; lpClass
0x140010876  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14001087f  xor     r8d, r8d; Reserved
0x140010882  mov     [rsp+70h+samDesired], r14d; samDesired
0x140010887  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001088e  mov     [rsp+70h+dwOptions], 0; dwOptions
0x140010896  call    cs:__imp_RegCreateKeyExW
0x14001089c  test    eax, eax
0x14001089e  jz      short loc_1400108B0
0x1400108a0  movzx   ebx, ax
0x1400108a3  or      ebx, 80070000h
0x1400108a9  test    eax, eax
0x1400108ab  cmovle  ebx, eax
0x1400108ae  jmp     short loc_140010913
0x1400108b0  mov     rax, [rbp+hKey]
0x1400108b4  test    rsi, rsi
0x1400108b7  jz      short loc_140010908
0x1400108b9  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x1400108c2  lea     rcx, [rbp+var_18]
0x1400108c6  mov     [rsp+70h+phkResult], rcx; phkResult
0x1400108cb  xor     r9d, r9d; lpClass
0x1400108ce  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400108d7  xor     r8d, r8d; Reserved
0x1400108da  mov     [rsp+70h+samDesired], r14d; samDesired
0x1400108df  mov     rdx, rsi; lpSubKey
0x1400108e2  mov     rcx, rax; hKey
0x1400108e5  mov     [rsp+70h+dwOptions], 1; dwOptions
0x1400108ed  call    cs:__imp_RegCreateKeyExW
0x1400108f3  test    eax, eax
0x1400108f5  jnz     short loc_1400108A0
0x1400108f7  mov     rax, [rbp+var_18]
0x1400108fb  mov     [rdi], rax
0x1400108fe  mov     [rbp+var_18], 0
0x140010906  jmp     short loc_140010922
0x140010908  mov     [rdi], rax
0x14001090b  mov     [rbp+hKey], 0
0x140010913  mov     rcx, [rbp+var_18]; hKey
0x140010917  test    rcx, rcx
0x14001091a  jz      short loc_140010922
0x14001091c  call    cs:__imp_RegCloseKey
0x140010922  mov     rcx, [rbp+hKey]; hKey
0x140010926  test    rcx, rcx
0x140010929  jz      short loc_140010931
0x14001092b  call    cs:__imp_RegCloseKey
0x140010931  mov     eax, ebx
0x140010933  mov     rcx, [rbp+var_8]
0x140010937  xor     rcx, rsp; StackCookie
0x14001093a  call    __security_check_cookie
0x14001093f  lea     r11, [rsp+70h+var_s0]
0x140010944  mov     rbx, [r11+20h]
0x140010948  mov     rsi, [r11+28h]
0x14001094c  mov     rsp, r11
0x14001094f  pop     r14
0x140010951  pop     rdi
0x140010952  pop     rbp
0x140010953  retn
```
