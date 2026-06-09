# WsRestoreGlobalMappingsFromRegistry

- ea: `0x18000e57c`
- end: `0x18000e730`
- name: `WsRestoreGlobalMappingsFromRegistry`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002fe70`

## callees

- `0x18000e57c`
- `0x18001fbd0`
- `0x18002be90`
- `0x180030d6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000e67c`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000e67c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e5df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e65c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e5df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e65c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e6ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e6e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e6ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e6e7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000e620`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000e620`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e6f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e6f8`

## pseudocode

```c
LSTATUS WsRestoreGlobalMappingsFromRegistry()
{
  DWORD v0; // ebx
  LSTATUS result; // eax
  char v2; // cl
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h]
  WCHAR v7; // [rsp+60h] [rbp-A0h] BYREF
  int v8; // [rsp+62h] [rbp-9Eh]
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  phkResult = 0;
  hMem = 0;
  cchName = 0;
  v0 = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\NetworkProvider\\GlobalMappings",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    while ( 1 )
    {
      cchName = 261;
      result = RegEnumKeyExW(hKey, v0, Name, &cchName, 0, 0, 0, 0);
      if ( result )
        break;
      if ( cchName && !RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
      {
        if ( Name[1] || !(unsigned int)_o_iswalpha(Name[0]) )
        {
          v2 = 0;
        }
        else
        {
          v2 = 1;
          v7 = Name[0];
          v8 = 58;
        }
        if ( (unsigned int)ReadConnectionInfoFromRegistry(
                             phkResult,
                             (STRSAFE_LPCWSTR)((unsigned __int64)&v7 & -(__int64)(v2 != 0))) )
        {
          RegCloseKey(phkResult);
        }
        else
        {
          WsRestoreGlobalMapping(hMem);
          RegCloseKey(phkResult);
          LocalFree(hMem);
        }
      }
      ++v0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e57c  mov     [rsp-8+arg_0], rbx
0x18000e581  mov     [rsp-8+arg_8], rdi
0x18000e586  push    rbp
0x18000e587  lea     rbp, [rsp-190h]
0x18000e58f  sub     rsp, 290h
0x18000e596  mov     rax, cs:__security_cookie
0x18000e59d  xor     rax, rsp
0x18000e5a0  mov     [rbp+190h+var_10], rax
0x18000e5a7  xor     edi, edi
0x18000e5a9  lea     rax, [rsp+290h+hKey]
0x18000e5ae  mov     r9d, 20019h; samDesired
0x18000e5b4  mov     [rsp+290h+hKey], rdi
0x18000e5b9  xor     r8d, r8d; ulOptions
0x18000e5bc  mov     [rsp+290h+var_248], rdi
0x18000e5c1  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Net"...
0x18000e5c8  mov     [rsp+290h+hMem], rdi
0x18000e5cd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e5d4  mov     [rsp+290h+cchName], edi
0x18000e5d8  mov     ebx, edi
0x18000e5da  mov     [rsp+290h+phkResult], rax; phkResult
0x18000e5df  call    cs:__imp_RegOpenKeyExW
0x18000e5e6  nop     dword ptr [rax+rax+00h]
0x18000e5eb  test    eax, eax
0x18000e5ed  jnz     loc_18000E70B
0x18000e5f3  mov     rcx, [rsp+290h+hKey]; hKey
0x18000e5f8  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000e5fd  mov     [rsp+290h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18000e602  lea     r8, [rsp+290h+Name]; lpName
0x18000e607  mov     [rsp+290h+lpcchClass], rdi; lpcchClass
0x18000e60c  mov     edx, ebx; dwIndex
0x18000e60e  mov     [rsp+290h+lpClass], rdi; lpClass
0x18000e613  mov     [rsp+290h+phkResult], rdi; lpReserved
0x18000e618  mov     [rsp+290h+cchName], 105h
0x18000e620  call    cs:__imp_RegEnumKeyExW
0x18000e627  nop     dword ptr [rax+rax+00h]
0x18000e62c  test    eax, eax
0x18000e62e  jnz     loc_18000E70B
0x18000e634  cmp     [rsp+290h+cchName], 1
0x18000e639  jb      loc_18000E704
0x18000e63f  mov     rcx, [rsp+290h+hKey]; hKey
0x18000e644  lea     rax, [rsp+290h+var_248]
0x18000e649  mov     r9d, 20019h; samDesired
0x18000e64f  mov     [rsp+290h+phkResult], rax; phkResult
0x18000e654  xor     r8d, r8d; ulOptions
0x18000e657  lea     rdx, [rsp+290h+Name]; lpSubKey
0x18000e65c  call    cs:__imp_RegOpenKeyExW
0x18000e663  nop     dword ptr [rax+rax+00h]
0x18000e668  test    eax, eax
0x18000e66a  jnz     loc_18000E704
0x18000e670  cmp     [rsp+290h+var_21E], di
0x18000e675  jnz     short loc_18000E6A2
0x18000e677  movzx   ecx, [rsp+290h+Name]
0x18000e67c  call    cs:__imp__o_iswalpha
0x18000e683  nop     dword ptr [rax+rax+00h]
0x18000e688  test    eax, eax
0x18000e68a  jz      short loc_18000E6A2
0x18000e68c  movzx   eax, [rsp+290h+Name]
0x18000e691  mov     cl, 1
0x18000e693  mov     [rsp+290h+var_230], ax
0x18000e698  mov     [rsp+290h+var_22E], 3Ah ; ':'
0x18000e6a0  jmp     short loc_18000E6A5
0x18000e6a2  mov     cl, dil
0x18000e6a5  neg     cl
0x18000e6a7  lea     rax, [rsp+290h+var_230]
0x18000e6ac  mov     rcx, [rsp+290h+var_248]; hKey
0x18000e6b1  lea     r8, [rsp+290h+hMem]
0x18000e6b6  sbb     rdx, rdx
0x18000e6b9  and     rdx, rax; pszSrc
0x18000e6bc  call    ReadConnectionInfoFromRegistry
0x18000e6c1  test    eax, eax
0x18000e6c3  jz      short loc_18000E6D8
0x18000e6c5  mov     rcx, [rsp+290h+var_248]; hKey
0x18000e6ca  call    cs:__imp_RegCloseKey
0x18000e6d1  nop     dword ptr [rax+rax+00h]
0x18000e6d6  jmp     short loc_18000E704
0x18000e6d8  mov     rcx, [rsp+290h+hMem]
0x18000e6dd  call    WsRestoreGlobalMapping
0x18000e6e2  mov     rcx, [rsp+290h+var_248]; hKey
0x18000e6e7  call    cs:__imp_RegCloseKey
0x18000e6ee  nop     dword ptr [rax+rax+00h]
0x18000e6f3  mov     rcx, [rsp+290h+hMem]; hMem
0x18000e6f8  call    cs:__imp_LocalFree
0x18000e6ff  nop     dword ptr [rax+rax+00h]
0x18000e704  inc     ebx
0x18000e706  jmp     loc_18000E5F3
0x18000e70b  mov     rcx, [rbp+190h+var_10]
0x18000e712  xor     rcx, rsp; StackCookie
0x18000e715  call    __security_check_cookie
0x18000e71a  lea     r11, [rsp+290h+var_s0]
0x18000e722  mov     rbx, [r11+10h]
0x18000e726  mov     rdi, [r11+18h]
0x18000e72a  mov     rsp, r11
0x18000e72d  pop     rbp
0x18000e72e  retn
```
