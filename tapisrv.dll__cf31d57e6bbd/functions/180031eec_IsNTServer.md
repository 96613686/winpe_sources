# IsNTServer

- ea: `0x180031eec`
- end: `0x180031fcd`
- name: `IsNTServer`
- size: `225`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002d6d0`
- `0x1800326c0`
- `0x180032ad0`

## callees

- `0x180001600`
- `0x180031eec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031fa8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031fa8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031f36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031f36`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031f6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031f6b`
- `KERNEL32!lstrcmpiW` at `0x180031f80`
- `KERNEL32!lstrcmpiW` at `0x180031f95`
- `KERNEL32!lstrcmpiW` at `0x180031f80`
- `KERNEL32!lstrcmpiW` at `0x180031f95`

## pseudocode

```c
__int64 IsNTServer()
{
  unsigned int v0; // ebx
  DWORD cbData; // [rsp+30h] [rbp-49h] BYREF
  DWORD Type; // [rsp+34h] [rbp-45h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-41h] BYREF
  WCHAR Data[64]; // [rsp+40h] [rbp-39h] BYREF

  v0 = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\ProductOptions", 0, 1u, &hKey) )
  {
    cbData = 128;
    if ( !RegQueryValueExW(hKey, L"ProductType", 0, &Type, (LPBYTE)Data, &cbData)
      && (!lstrcmpiW(Data, L"ServerNT") || !lstrcmpiW(Data, L"LANMANNT")) )
    {
      v0 = 1;
    }
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x180031eec  mov     [rsp-8+arg_0], rbx
0x180031ef1  push    rbp
0x180031ef2  lea     rbp, [rsp-57h]
0x180031ef7  sub     rsp, 0D0h
0x180031efe  mov     rax, cs:__security_cookie
0x180031f05  xor     rax, rsp
0x180031f08  mov     [rbp+57h+var_10], rax
0x180031f0c  xor     ebx, ebx
0x180031f0e  lea     rax, [rbp+57h+hKey]
0x180031f12  xor     r8d, r8d; ulOptions
0x180031f15  mov     [rbp+57h+hKey], rbx
0x180031f19  lea     rdx, gszRegKeyNTServer; "System\\CurrentControlSet\\Control\\Pro"...
0x180031f20  mov     [rbp+57h+cbData], ebx
0x180031f23  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031f2a  mov     [rbp+57h+Type], ebx
0x180031f2d  lea     r9d, [rbx+1]; samDesired
0x180031f31  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180031f36  call    cs:__imp_RegOpenKeyExW
0x180031f3c  test    eax, eax
0x180031f3e  jnz     short loc_180031FAE
0x180031f40  mov     rcx, [rbp+57h+hKey]; hKey
0x180031f44  lea     rax, [rbp+57h+cbData]
0x180031f48  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180031f4d  lea     r9, [rbp+57h+Type]; lpType
0x180031f51  lea     rax, [rbp+57h+Data]
0x180031f55  mov     [rbp+57h+cbData], 80h
0x180031f5c  xor     r8d, r8d; lpReserved
0x180031f5f  mov     [rsp+0D0h+phkResult], rax; lpData
0x180031f64  lea     rdx, gszProductType; "ProductType"
0x180031f6b  call    cs:__imp_RegQueryValueExW
0x180031f71  test    eax, eax
0x180031f73  jnz     short loc_180031FA4
0x180031f75  lea     rdx, gszProductTypeServer; "ServerNT"
0x180031f7c  lea     rcx, [rbp+57h+Data]; lpString1
0x180031f80  call    cs:__imp_lstrcmpiW
0x180031f86  test    eax, eax
0x180031f88  jz      short loc_180031F9F
0x180031f8a  lea     rdx, gszProductTypeLanmanNt; "LANMANNT"
0x180031f91  lea     rcx, [rbp+57h+Data]; lpString1
0x180031f95  call    cs:__imp_lstrcmpiW
0x180031f9b  test    eax, eax
0x180031f9d  jnz     short loc_180031FA4
0x180031f9f  mov     ebx, 1
0x180031fa4  mov     rcx, [rbp+57h+hKey]; hKey
0x180031fa8  call    cs:__imp_RegCloseKey
0x180031fae  mov     eax, ebx
0x180031fb0  mov     rcx, [rbp+57h+var_10]
0x180031fb4  xor     rcx, rsp; StackCookie
0x180031fb7  call    __security_check_cookie
0x180031fbc  mov     rbx, [rsp+0D0h+arg_0]
0x180031fc4  add     rsp, 0D0h
0x180031fcb  pop     rbp
0x180031fcc  retn
```
