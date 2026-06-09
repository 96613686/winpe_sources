# CreateShellSessionSubKey(ushort const *,ulong,bool *,HKEY__ * *)

- ea: `0x140054ef8`
- end: `0x140054fe3`
- name: `?CreateShellSessionSubKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, unsigned int, bool *, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140056db0`

## callees

- `0x140054e24`
- `0x140054ef8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140054fc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140054fd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140054fc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140054fd3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140054f92`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140054f92`

## pseudocode

```c
__int64 __fastcall CreateShellSessionSubKey(LPCWSTR lpSubKey, DWORD a2, bool *a3, HKEY *a4)
{
  int v6; // ebx
  LSTATUS v7; // eax
  DWORD dwDisposition; // [rsp+78h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  phkResult = (HKEY)a3;
  dwDisposition = a2;
  if ( a4 )
    *a4 = 0;
  hKey = 0;
  v6 = CreateShellSessionKey((__int64)lpSubKey, &hKey);
  if ( v6 >= 0 )
  {
    phkResult = 0;
    dwDisposition = 0;
    v7 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 1u, 0x20006u, 0, &phkResult, &dwDisposition);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v6 >= 0 )
    {
      if ( a4 )
        *a4 = phkResult;
      else
        RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140054ef8  mov     [rsp+arg_10], r8
0x140054efd  mov     [rsp+dwDisposition], edx
0x140054f01  push    rbx
0x140054f02  push    rsi
0x140054f03  push    rdi
0x140054f04  sub     rsp, 50h
0x140054f08  mov     rdi, r9
0x140054f0b  mov     rsi, rcx
0x140054f0e  test    r9, r9
0x140054f11  jz      short loc_140054F1A
0x140054f13  mov     qword ptr [r9], 0
0x140054f1a  lea     rdx, [rsp+68h+hKey]; HKEY *
0x140054f22  mov     [rsp+68h+hKey], 0
0x140054f2e  call    ?CreateShellSessionKey@@YAJKPEAPEAUHKEY__@@@Z; CreateShellSessionKey(ulong,HKEY__ * *)
0x140054f33  mov     ebx, eax
0x140054f35  test    eax, eax
0x140054f37  js      loc_140054FD9
0x140054f3d  mov     rcx, [rsp+68h+hKey]; hKey
0x140054f45  lea     rax, [rsp+68h+dwDisposition]
0x140054f4a  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x140054f4f  xor     r9d, r9d; lpClass
0x140054f52  lea     rax, [rsp+68h+arg_10]
0x140054f5a  mov     [rsp+68h+arg_10], 0
0x140054f66  mov     [rsp+68h+phkResult], rax; phkResult
0x140054f6b  xor     r8d, r8d; Reserved
0x140054f6e  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140054f77  mov     rdx, rsi; lpSubKey
0x140054f7a  mov     [rsp+68h+samDesired], 20006h; samDesired
0x140054f82  mov     [rsp+68h+dwOptions], 1; dwOptions
0x140054f8a  mov     [rsp+68h+dwDisposition], 0
0x140054f92  call    cs:__imp_RegCreateKeyExW
0x140054f98  mov     ebx, eax
0x140054f9a  test    eax, eax
0x140054f9c  jle     short loc_140054FA7
0x140054f9e  movzx   ebx, ax
0x140054fa1  or      ebx, 80070000h
0x140054fa7  test    ebx, ebx
0x140054fa9  js      short loc_140054FCB
0x140054fab  test    rdi, rdi
0x140054fae  jz      short loc_140054FBD
0x140054fb0  mov     rax, [rsp+68h+arg_10]
0x140054fb8  mov     [rdi], rax
0x140054fbb  jmp     short loc_140054FCB
0x140054fbd  mov     rcx, [rsp+68h+arg_10]; hKey
0x140054fc5  call    cs:__imp_RegCloseKey
0x140054fcb  mov     rcx, [rsp+68h+hKey]; hKey
0x140054fd3  call    cs:__imp_RegCloseKey
0x140054fd9  mov     eax, ebx
0x140054fdb  add     rsp, 50h
0x140054fdf  pop     rdi
0x140054fe0  pop     rsi
0x140054fe1  pop     rbx
0x140054fe2  retn
```
