# RegHelper::CreateSub(char const *)

- ea: `0x18000e52c`
- end: `0x18000e5ae`
- name: `?CreateSub@RegHelper@@QEAA_NPEBD@Z`
- size: `130`
- prototype: `bool(RegHelper *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000e8b8`
- `0x18000ebac`

## callees

- `0x18000e52c`

## import_xrefs

- `ADVAPI32!RegCreateKeyExA` at `0x18000e593`
- `ADVAPI32!RegCreateKeyExA` at `0x18000e593`
- `ADVAPI32!RegCloseKey` at `0x18000e54d`
- `ADVAPI32!RegCloseKey` at `0x18000e54d`

## pseudocode

```c
bool __fastcall RegHelper::CreateSub(RegHelper *this, const char *a2)
{
  HKEY *phkResult; // rdi
  HKEY v4; // rcx
  HKEY v6; // rcx
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF

  phkResult = (HKEY *)((char *)this + 8);
  v4 = (HKEY)*((_QWORD *)this + 1);
  if ( v4 )
    RegCloseKey(v4);
  v6 = *(HKEY *)this;
  dwDisposition = 0;
  return RegCreateKeyExA(v6, a2, 0, (LPSTR)Class, 0, 0x2001Fu, 0, phkResult, &dwDisposition) == 0;
}

```

## disassembly

```asm
0x18000e52c  mov     [rsp+arg_8], rbx
0x18000e531  mov     [rsp+arg_10], rsi
0x18000e536  push    rdi
0x18000e537  sub     rsp, 50h
0x18000e53b  lea     rdi, [rcx+8]
0x18000e53f  mov     rbx, rcx
0x18000e542  mov     rcx, [rdi]; hKey
0x18000e545  mov     rsi, rdx
0x18000e548  test    rcx, rcx
0x18000e54b  jz      short loc_18000E553
0x18000e54d  call    cs:__imp_RegCloseKey
0x18000e553  mov     rcx, [rbx]; hKey
0x18000e556  lea     rax, [rsp+58h+dwDisposition]
0x18000e55b  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18000e560  lea     r9, Class; lpClass
0x18000e567  mov     [rsp+58h+phkResult], rdi; phkResult
0x18000e56c  xor     r8d, r8d; Reserved
0x18000e56f  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000e578  mov     rdx, rsi; lpSubKey
0x18000e57b  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18000e583  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000e58b  mov     [rsp+58h+dwDisposition], 0
0x18000e593  call    cs:__imp_RegCreateKeyExA
0x18000e599  mov     rbx, [rsp+58h+arg_8]
0x18000e59e  test    eax, eax
0x18000e5a0  mov     rsi, [rsp+58h+arg_10]
0x18000e5a5  setz    al
0x18000e5a8  add     rsp, 50h
0x18000e5ac  pop     rdi
0x18000e5ad  retn
```
