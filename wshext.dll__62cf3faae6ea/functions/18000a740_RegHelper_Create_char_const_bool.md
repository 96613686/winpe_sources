# RegHelper::Create(char const *,bool)

- ea: `0x18000a740`
- end: `0x18000a7bd`
- name: `?Create@RegHelper@@QEAA_NPEBD_N@Z`
- size: `125`
- prototype: `bool __fastcall(PHKEY phkResult, LPCSTR lpSubKey, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000aacc`

## callees

- `0x18000a740`

## import_xrefs

- `ADVAPI32!RegCreateKeyExA` at `0x18000a7a7`
- `ADVAPI32!RegCreateKeyExA` at `0x18000a7a7`
- `ADVAPI32!RegCloseKey` at `0x18000a75d`
- `ADVAPI32!RegCloseKey` at `0x18000a75d`

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
0x18000a740  mov     [rsp+arg_0], rbx
0x18000a745  mov     byte ptr [rsp+dwDisposition], r8b
0x18000a74a  push    rdi
0x18000a74b  sub     rsp, 50h
0x18000a74f  mov     rbx, rcx
0x18000a752  mov     rdi, rdx
0x18000a755  mov     rcx, [rcx]; hKey
0x18000a758  test    rcx, rcx
0x18000a75b  jz      short loc_18000A763
0x18000a75d  call    cs:__imp_RegCloseKey
0x18000a763  lea     rax, [rsp+58h+dwDisposition]
0x18000a768  mov     [rsp+58h+dwDisposition], 0
0x18000a770  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18000a775  lea     r9, Class; lpClass
0x18000a77c  mov     [rsp+58h+phkResult], rbx; phkResult
0x18000a781  xor     r8d, r8d; Reserved
0x18000a784  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000a78d  mov     rdx, rdi; lpSubKey
0x18000a790  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18000a798  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000a79f  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000a7a7  call    cs:__imp_RegCreateKeyExA
0x18000a7ad  mov     rbx, [rsp+58h+arg_0]
0x18000a7b2  test    eax, eax
0x18000a7b4  setz    al
0x18000a7b7  add     rsp, 50h
0x18000a7bb  pop     rdi
0x18000a7bc  retn
```
