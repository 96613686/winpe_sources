# RegHelper::CreateSub(char const *)

- ea: `0x18000a7c4`
- end: `0x18000a842`
- name: `?CreateSub@RegHelper@@QEAA_NPEBD@Z`
- size: `126`
- prototype: `bool __fastcall(RegHelper *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000aacc`

## callees

- `0x18000a7c4`

## import_xrefs

- `ADVAPI32!RegCreateKeyExA` at `0x18000a82c`
- `ADVAPI32!RegCreateKeyExA` at `0x18000a82c`
- `ADVAPI32!RegCloseKey` at `0x18000a7e2`
- `ADVAPI32!RegCloseKey` at `0x18000a7e2`

## pseudocode

```c
bool __fastcall RegHelper::CreateSub(RegHelper *this, const char *a2)
{
  HKEY *phkResult; // rdi
  HKEY v4; // rcx
  HKEY v5; // rcx
  const char *dwDisposition; // [rsp+68h] [rbp+10h] BYREF

  dwDisposition = a2;
  phkResult = (HKEY *)((char *)this + 8);
  v4 = (HKEY)*((_QWORD *)this + 1);
  if ( v4 )
    RegCloseKey(v4);
  v5 = *(HKEY *)this;
  LODWORD(dwDisposition) = 0;
  return RegCreateKeyExA(v5, "InProcServer32", 0, (LPSTR)Class, 0, 0x2001Fu, 0, phkResult, (LPDWORD)&dwDisposition) == 0;
}

```

## disassembly

```asm
0x18000a7c4  mov     [rsp+arg_0], rbx
0x18000a7c9  mov     [rsp+dwDisposition], rdx
0x18000a7ce  push    rdi
0x18000a7cf  sub     rsp, 50h
0x18000a7d3  lea     rdi, [rcx+8]
0x18000a7d7  mov     rbx, rcx
0x18000a7da  mov     rcx, [rdi]; hKey
0x18000a7dd  test    rcx, rcx
0x18000a7e0  jz      short loc_18000A7E8
0x18000a7e2  call    cs:__imp_RegCloseKey
0x18000a7e8  mov     rcx, [rbx]; hKey
0x18000a7eb  lea     rax, [rsp+58h+dwDisposition]
0x18000a7f0  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18000a7f5  lea     r9, Class; lpClass
0x18000a7fc  mov     [rsp+58h+phkResult], rdi; phkResult
0x18000a801  lea     rdx, aInprocserver32; "InProcServer32"
0x18000a808  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000a811  xor     r8d, r8d; Reserved
0x18000a814  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18000a81c  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000a824  mov     dword ptr [rsp+58h+dwDisposition], 0
0x18000a82c  call    cs:__imp_RegCreateKeyExA
0x18000a832  mov     rbx, [rsp+58h+arg_0]
0x18000a837  test    eax, eax
0x18000a839  setz    al
0x18000a83c  add     rsp, 50h
0x18000a840  pop     rdi
0x18000a841  retn
```
