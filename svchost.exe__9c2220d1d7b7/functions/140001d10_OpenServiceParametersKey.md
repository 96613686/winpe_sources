# OpenServiceParametersKey

- ea: `0x140001d10`
- end: `0x140001e1a`
- name: `OpenServiceParametersKey`
- size: `266`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, PHKEY phkResult)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x140003470`
- `0x140003cd0`
- `0x140006320`

## callees

- `0x140001d10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001d73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001d89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001d73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001d89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001d4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001dc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001dec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001d4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001dc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001dec`

## string_xrefs

- `0x140001d2e`: `System\CurrentControlSet\Services`

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
0x140001d10  mov     [rsp+arg_0], rbx
0x140001d15  push    rbp
0x140001d16  push    rsi
0x140001d17  push    rdi
0x140001d18  sub     rsp, 30h
0x140001d1c  mov     rdi, rdx
0x140001d1f  lea     rax, [rsp+48h+hKey]
0x140001d24  mov     rsi, rcx
0x140001d27  mov     [rsp+48h+phkResult], rax; phkResult
0x140001d2c  xor     ebp, ebp
0x140001d2e  lea     rdx, SubKey; "System\\CurrentControlSet\\Services"
0x140001d35  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140001d3c  mov     [rsp+48h+hKey], rbp
0x140001d41  mov     r9d, 20019h; samDesired
0x140001d47  mov     [rsp+48h+arg_10], rbp
0x140001d4c  xor     r8d, r8d; ulOptions
0x140001d4f  call    cs:__imp_RegOpenKeyExW
0x140001d56  nop     dword ptr [rax+rax+00h]
0x140001d5b  mov     ebx, eax
0x140001d5d  test    eax, eax
0x140001d5f  jz      short loc_140001DA5
0x140001d61  mov     rcx, [rsp+48h+arg_10]
0x140001d66  mov     rax, [rsp+48h+hKey]
0x140001d6b  test    rax, rax
0x140001d6e  jz      short loc_140001D84
0x140001d70  mov     rcx, rax; hKey
0x140001d73  call    cs:__imp_RegCloseKey
0x140001d7a  nop     dword ptr [rax+rax+00h]
0x140001d7f  mov     rcx, [rsp+48h+arg_10]; hKey
0x140001d84  test    rcx, rcx
0x140001d87  jz      short loc_140001D95
0x140001d89  call    cs:__imp_RegCloseKey
0x140001d90  nop     dword ptr [rax+rax+00h]
0x140001d95  mov     eax, ebx
0x140001d97  mov     rbx, [rsp+48h+arg_0]
0x140001d9c  add     rsp, 30h
0x140001da0  pop     rdi
0x140001da1  pop     rsi
0x140001da2  pop     rbp
0x140001da3  retn
0x140001da5  mov     rcx, [rsp+48h+hKey]; hKey
0x140001daa  lea     rax, [rsp+48h+arg_10]
0x140001daf  mov     r9d, 20019h; samDesired
0x140001db5  mov     [rsp+48h+phkResult], rax; phkResult
0x140001dba  xor     r8d, r8d; ulOptions
0x140001dbd  mov     rdx, rsi; lpSubKey
0x140001dc0  call    cs:__imp_RegOpenKeyExW
0x140001dc7  nop     dword ptr [rax+rax+00h]
0x140001dcc  mov     ebx, eax
0x140001dce  test    eax, eax
0x140001dd0  jnz     short loc_140001D61
0x140001dd2  mov     rcx, [rsp+48h+arg_10]; hKey
0x140001dd7  lea     rdx, aParameters; "Parameters"
0x140001dde  mov     r9d, 20019h; samDesired
0x140001de4  mov     [rsp+48h+phkResult], rdi; phkResult
0x140001de9  xor     r8d, r8d; ulOptions
0x140001dec  call    cs:__imp_RegOpenKeyExW
0x140001df3  nop     dword ptr [rax+rax+00h]
0x140001df8  mov     ebx, eax
0x140001dfa  cmp     eax, 2
0x140001dfd  jnz     loc_140001D61
0x140001e03  mov     rax, [rsp+48h+arg_10]
0x140001e08  mov     rcx, rbp
0x140001e0b  mov     [rdi], rax
0x140001e0e  mov     ebx, ebp
0x140001e10  mov     [rsp+48h+arg_10], rcx
0x140001e15  jmp     loc_140001D66
```
