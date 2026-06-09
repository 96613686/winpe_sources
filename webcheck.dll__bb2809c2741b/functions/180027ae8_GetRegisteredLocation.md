# GetRegisteredLocation

- ea: `0x180027ae8`
- end: `0x180027bfc`
- name: `GetRegisteredLocation`
- size: `276`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027c04`

## callees

- `0x18000f9e0`
- `0x180027ae8`
- `0x180029280`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsA` at `0x180027b9f`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180027b9f`
- `ADVAPI32!RegCloseKey` at `0x180027bcf`
- `ADVAPI32!RegCloseKey` at `0x180027bcf`
- `ADVAPI32!RegQueryValueExA` at `0x180027b7d`
- `ADVAPI32!RegQueryValueExA` at `0x180027b7d`
- `ADVAPI32!RegOpenKeyExA` at `0x180027b3a`
- `ADVAPI32!RegOpenKeyExA` at `0x180027b3a`

## string_xrefs

- `0x180027b33`: `CLSID\{ADB880A6-D8FF-11CF-9377-00AA003B7A11}\InprocServer32`

## pseudocode

```c
_BOOL8 __fastcall GetRegisteredLocation(char *a1)
{
  BOOL v2; // ebx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[272]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  if ( RegOpenKeyExA(
         HKEY_CLASSES_ROOT,
         "CLSID\\{ADB880A6-D8FF-11CF-9377-00AA003B7A11}\\InprocServer32",
         0,
         0x20019u,
         &hKey) )
  {
    return 0;
  }
  cbData = 260;
  Type = 1;
  v2 = 0;
  if ( !RegQueryValueExA(hKey, 0, 0, &Type, Data, &cbData) )
  {
    Data[259] = 0;
    if ( Type == 2 )
      LOBYTE(v2) = ExpandEnvironmentStringsA((LPCSTR)Data, a1, 0x104u) - 1 <= 0x103;
    else
      v2 = (int)StringCchCopyA(a1, 0x104u, (const char *)Data) >= 0;
  }
  RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180027ae8  mov     [rsp-8+arg_8], rbx
0x180027aed  mov     [rsp-8+arg_10], rdi
0x180027af2  push    rbp
0x180027af3  lea     rbp, [rsp-60h]
0x180027af8  sub     rsp, 160h
0x180027aff  mov     rax, cs:__security_cookie
0x180027b06  xor     rax, rsp
0x180027b09  mov     [rbp+60h+var_10], rax
0x180027b0d  mov     rdi, rcx
0x180027b10  mov     [rsp+160h+hKey], 0
0x180027b19  lea     rax, [rsp+160h+hKey]
0x180027b1e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180027b25  mov     r9d, 20019h; samDesired
0x180027b2b  mov     [rsp+160h+phkResult], rax; phkResult
0x180027b30  xor     r8d, r8d; ulOptions
0x180027b33  lea     rdx, aClsidAdb880a6D; "CLSID\\{ADB880A6-D8FF-11CF-9377-00AA003"...
0x180027b3a  call    cs:__imp_RegOpenKeyExA
0x180027b40  test    eax, eax
0x180027b42  jnz     loc_180027BD9
0x180027b48  mov     rcx, [rsp+160h+hKey]; hKey
0x180027b4d  lea     rax, [rsp+160h+cbData]
0x180027b52  mov     [rsp+160h+lpcbData], rax; lpcbData
0x180027b57  lea     r9, [rsp+160h+Type]; lpType
0x180027b5c  lea     rax, [rsp+160h+Data]
0x180027b61  mov     [rsp+160h+cbData], 104h
0x180027b69  xor     r8d, r8d; lpReserved
0x180027b6c  mov     [rsp+160h+phkResult], rax; lpData
0x180027b71  xor     edx, edx; lpValueName
0x180027b73  mov     [rsp+160h+Type], 1
0x180027b7b  xor     ebx, ebx
0x180027b7d  call    cs:__imp_RegQueryValueExA
0x180027b83  test    eax, eax
0x180027b85  jnz     short loc_180027BCA
0x180027b87  cmp     [rsp+160h+Type], 2
0x180027b8c  mov     [rbp+60h+var_1D], bl
0x180027b8f  jnz     short loc_180027BB1
0x180027b91  mov     r8d, 104h; nSize
0x180027b97  lea     rcx, [rsp+160h+Data]; lpSrc
0x180027b9c  mov     rdx, rdi; lpDst
0x180027b9f  call    cs:__imp_ExpandEnvironmentStringsA
0x180027ba5  dec     eax
0x180027ba7  cmp     eax, 103h
0x180027bac  setbe   bl
0x180027baf  jmp     short loc_180027BCA
0x180027bb1  lea     r8, [rsp+160h+Data]; char *
0x180027bb6  mov     edx, 104h; unsigned __int64
0x180027bbb  mov     rcx, rdi; char *
0x180027bbe  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180027bc3  mov     ebx, eax
0x180027bc5  not     ebx
0x180027bc7  shr     ebx, 1Fh
0x180027bca  mov     rcx, [rsp+160h+hKey]; hKey
0x180027bcf  call    cs:__imp_RegCloseKey
0x180027bd5  mov     eax, ebx
0x180027bd7  jmp     short loc_180027BDB
0x180027bd9  xor     eax, eax
0x180027bdb  mov     rcx, [rbp+60h+var_10]
0x180027bdf  xor     rcx, rsp; StackCookie
0x180027be2  call    __security_check_cookie
0x180027be7  lea     r11, [rsp+160h+var_s0]
0x180027bef  mov     rbx, [r11+18h]
0x180027bf3  mov     rdi, [r11+20h]
0x180027bf7  mov     rsp, r11
0x180027bfa  pop     rbp
0x180027bfb  retn
```
