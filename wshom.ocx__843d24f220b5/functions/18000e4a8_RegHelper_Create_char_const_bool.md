# RegHelper::Create(char const *,bool)

- ea: `0x18000e4a8`
- end: `0x18000e525`
- name: `?Create@RegHelper@@QEAA_NPEBD_N@Z`
- size: `125`
- prototype: `bool __fastcall(PHKEY phkResult, LPCSTR lpSubKey, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000e8b8`
- `0x18000ebac`

## callees

- `0x18000e4a8`

## import_xrefs

- `ADVAPI32!RegCreateKeyExA` at `0x18000e50f`
- `ADVAPI32!RegCreateKeyExA` at `0x18000e50f`
- `ADVAPI32!RegCloseKey` at `0x18000e4c5`
- `ADVAPI32!RegCloseKey` at `0x18000e4c5`

## pseudocode

```c
bool __fastcall RegHelper::Create(PHKEY phkResult, LPCSTR lpSubKey, char a3)
{
  HKEY v5; // rcx
  DWORD dwDisposition; // [rsp+70h] [rbp+18h] BYREF

  LOBYTE(dwDisposition) = a3;
  v5 = *phkResult;
  if ( v5 )
    RegCloseKey(v5);
  dwDisposition = 0;
  return RegCreateKeyExA(HKEY_CLASSES_ROOT, lpSubKey, 0, (LPSTR)Class, 0, 0x2001Fu, 0, phkResult, &dwDisposition) == 0;
}

```

## disassembly

```asm
0x18000e4a8  mov     [rsp+arg_0], rbx
0x18000e4ad  mov     byte ptr [rsp+dwDisposition], r8b
0x18000e4b2  push    rdi
0x18000e4b3  sub     rsp, 50h
0x18000e4b7  mov     rbx, rcx
0x18000e4ba  mov     rdi, rdx
0x18000e4bd  mov     rcx, [rcx]; hKey
0x18000e4c0  test    rcx, rcx
0x18000e4c3  jz      short loc_18000E4CB
0x18000e4c5  call    cs:__imp_RegCloseKey
0x18000e4cb  lea     rax, [rsp+58h+dwDisposition]
0x18000e4d0  mov     [rsp+58h+dwDisposition], 0
0x18000e4d8  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18000e4dd  lea     r9, Class; lpClass
0x18000e4e4  mov     [rsp+58h+phkResult], rbx; phkResult
0x18000e4e9  xor     r8d, r8d; Reserved
0x18000e4ec  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000e4f5  mov     rdx, rdi; lpSubKey
0x18000e4f8  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18000e500  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000e507  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000e50f  call    cs:__imp_RegCreateKeyExA
0x18000e515  mov     rbx, [rsp+58h+arg_0]
0x18000e51a  test    eax, eax
0x18000e51c  setz    al
0x18000e51f  add     rsp, 50h
0x18000e523  pop     rdi
0x18000e524  retn
```
