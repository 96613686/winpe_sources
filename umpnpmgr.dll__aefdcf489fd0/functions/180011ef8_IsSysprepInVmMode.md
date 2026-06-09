# IsSysprepInVmMode

- ea: `0x180011ef8`
- end: `0x180011ffe`
- name: `IsSysprepInVmMode`
- size: `262`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000a6b0`
- `0x18000cf30`

## callees

- `0x180011ef8`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011fa2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011fa2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011f95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011f95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011f5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011f5b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180011fd3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180011fd3`

## pseudocode

```c
__int64 IsSysprepInVmMode()
{
  unsigned int v0; // edi
  LSTATUS v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Data[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  v0 = 0;
  Type = 0;
  cbData = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\Setup\\Sysprep", 0, 1u, &hKey) )
  {
    cbData = 520;
    v1 = RegQueryValueExW(hKey, L"Mode", 0, &Type, (LPBYTE)Data, &cbData);
    RegCloseKey(hKey);
    if ( !v1 && Type == 1 )
      return CompareStringW(0x7Fu, 1u, Data, -1, L"vm", -1) == 2;
  }
  return v0;
}

```

## disassembly

```asm
0x180011ef8  push    rbp
0x180011efa  push    rbx
0x180011efb  push    rdi
0x180011efc  push    r14
0x180011efe  lea     rbp, [rsp-168h]
0x180011f06  sub     rsp, 268h
0x180011f0d  mov     rax, cs:__security_cookie
0x180011f14  xor     rax, rsp
0x180011f17  mov     [rbp+180h+var_30], rax
0x180011f1e  lea     rax, [rsp+280h+hKey]
0x180011f23  mov     [rsp+280h+hKey], 0
0x180011f2c  xor     edi, edi
0x180011f2e  mov     [rsp+280h+Type], 0
0x180011f36  xor     r8d, r8d; ulOptions
0x180011f39  mov     [rsp+280h+cbData], 0
0x180011f41  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180011f48  mov     [rsp+280h+phkResult], rax; phkResult
0x180011f4d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011f54  lea     r14d, [rdi+1]
0x180011f58  mov     r9d, r14d; samDesired
0x180011f5b  call    cs:__imp_RegOpenKeyExW
0x180011f61  test    eax, eax
0x180011f63  jnz     short loc_180011FE0
0x180011f65  mov     rcx, [rsp+280h+hKey]; hKey
0x180011f6a  lea     rax, [rsp+280h+cbData]
0x180011f6f  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180011f74  lea     r9, [rsp+280h+Type]; lpType
0x180011f79  lea     rax, [rsp+280h+Data]
0x180011f7e  mov     [rsp+280h+cbData], 208h
0x180011f86  xor     r8d, r8d; lpReserved
0x180011f89  mov     [rsp+280h+phkResult], rax; lpData
0x180011f8e  lea     rdx, aMode; "Mode"
0x180011f95  call    cs:__imp_RegQueryValueExW
0x180011f9b  mov     rcx, [rsp+280h+hKey]; hKey
0x180011fa0  mov     ebx, eax
0x180011fa2  call    cs:__imp_RegCloseKey
0x180011fa8  test    ebx, ebx
0x180011faa  jnz     short loc_180011FE0
0x180011fac  cmp     [rsp+280h+Type], r14d
0x180011fb1  jnz     short loc_180011FE0
0x180011fb3  or      r9d, 0FFFFFFFFh; cchCount1
0x180011fb7  lea     rax, aVm; "vm"
0x180011fbe  mov     dword ptr [rsp+280h+lpcbData], r9d; cchCount2
0x180011fc3  lea     r8, [rsp+280h+Data]; lpString1
0x180011fc8  mov     edx, r14d; dwCmpFlags
0x180011fcb  mov     [rsp+280h+phkResult], rax; lpString2
0x180011fd0  lea     ecx, [rdi+7Fh]; Locale
0x180011fd3  call    cs:__imp_CompareStringW
0x180011fd9  cmp     eax, 2
0x180011fdc  cmovz   edi, r14d
0x180011fe0  mov     eax, edi
0x180011fe2  mov     rcx, [rbp+180h+var_30]
0x180011fe9  xor     rcx, rsp; StackCookie
0x180011fec  call    __security_check_cookie
0x180011ff1  add     rsp, 268h
0x180011ff8  pop     r14
0x180011ffa  pop     rdi
0x180011ffb  pop     rbx
0x180011ffc  pop     rbp
0x180011ffd  retn
```
