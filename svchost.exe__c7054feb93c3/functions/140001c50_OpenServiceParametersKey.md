# OpenServiceParametersKey

- ea: `0x140001c50`
- end: `0x140001d3b`
- name: `OpenServiceParametersKey`
- size: `235`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, PHKEY phkResult)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x140003180`
- `0x1400039f0`
- `0x140005ea0`

## callees

- `0x140001c50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001cad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001cbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001cad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001cbd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001c8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001ced`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001d13`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001c8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001ced`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001d13`

## string_xrefs

- `0x140001c6e`: `System\CurrentControlSet\Services`

## pseudocode

```c
__int64 __fastcall OpenServiceParametersKey(LPCWSTR lpSubKey, PHKEY phkResult)
{
  unsigned int v4; // ebx
  HKEY v5; // rcx
  HKEY v7; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  v7 = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services", 0, 0x20019u, &hKey);
  if ( v4
    || (v4 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &v7)) != 0
    || (v4 = RegOpenKeyExW(v7, L"Parameters", 0, 0x20019u, phkResult), v4 != 2) )
  {
    v5 = v7;
  }
  else
  {
    v5 = 0;
    *phkResult = v7;
    v4 = 0;
    v7 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v5 = v7;
  }
  if ( v5 )
    RegCloseKey(v5);
  return v4;
}

```

## disassembly

```asm
0x140001c50  mov     [rsp+arg_0], rbx
0x140001c55  push    rbp
0x140001c56  push    rsi
0x140001c57  push    rdi
0x140001c58  sub     rsp, 30h
0x140001c5c  mov     rdi, rdx
0x140001c5f  lea     rax, [rsp+48h+hKey]
0x140001c64  mov     rsi, rcx
0x140001c67  mov     [rsp+48h+phkResult], rax; phkResult
0x140001c6c  xor     ebp, ebp
0x140001c6e  lea     rdx, SubKey; "System\\CurrentControlSet\\Services"
0x140001c75  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140001c7c  mov     [rsp+48h+hKey], rbp
0x140001c81  mov     r9d, 20019h; samDesired
0x140001c87  mov     [rsp+48h+arg_10], rbp
0x140001c8c  xor     r8d, r8d; ulOptions
0x140001c8f  call    cs:__imp_RegOpenKeyExW
0x140001c95  mov     ebx, eax
0x140001c97  test    eax, eax
0x140001c99  jz      short loc_140001CD2
0x140001c9b  mov     rcx, [rsp+48h+arg_10]
0x140001ca0  mov     rax, [rsp+48h+hKey]
0x140001ca5  test    rax, rax
0x140001ca8  jz      short loc_140001CB8
0x140001caa  mov     rcx, rax; hKey
0x140001cad  call    cs:__imp_RegCloseKey
0x140001cb3  mov     rcx, [rsp+48h+arg_10]; hKey
0x140001cb8  test    rcx, rcx
0x140001cbb  jz      short loc_140001CC3
0x140001cbd  call    cs:__imp_RegCloseKey
0x140001cc3  mov     eax, ebx
0x140001cc5  mov     rbx, [rsp+48h+arg_0]
0x140001cca  add     rsp, 30h
0x140001cce  pop     rdi
0x140001ccf  pop     rsi
0x140001cd0  pop     rbp
0x140001cd1  retn
0x140001cd2  mov     rcx, [rsp+48h+hKey]; hKey
0x140001cd7  lea     rax, [rsp+48h+arg_10]
0x140001cdc  mov     r9d, 20019h; samDesired
0x140001ce2  mov     [rsp+48h+phkResult], rax; phkResult
0x140001ce7  xor     r8d, r8d; ulOptions
0x140001cea  mov     rdx, rsi; lpSubKey
0x140001ced  call    cs:__imp_RegOpenKeyExW
0x140001cf3  mov     ebx, eax
0x140001cf5  test    eax, eax
0x140001cf7  jnz     short loc_140001C9B
0x140001cf9  mov     rcx, [rsp+48h+arg_10]; hKey
0x140001cfe  lea     rdx, aParameters; "Parameters"
0x140001d05  mov     r9d, 20019h; samDesired
0x140001d0b  mov     [rsp+48h+phkResult], rdi; phkResult
0x140001d10  xor     r8d, r8d; ulOptions
0x140001d13  call    cs:__imp_RegOpenKeyExW
0x140001d19  mov     ebx, eax
0x140001d1b  cmp     eax, 2
0x140001d1e  jnz     loc_140001C9B
0x140001d24  mov     rax, [rsp+48h+arg_10]
0x140001d29  mov     rcx, rbp
0x140001d2c  mov     [rdi], rax
0x140001d2f  mov     ebx, ebp
0x140001d31  mov     [rsp+48h+arg_10], rcx
0x140001d36  jmp     loc_140001CA0
```
