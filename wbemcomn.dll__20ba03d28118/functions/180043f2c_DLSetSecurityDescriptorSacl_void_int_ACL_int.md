# DLSetSecurityDescriptorSacl(void *,int,_ACL *,int)

- ea: `0x180043f2c`
- end: `0x180043f9b`
- name: `?DLSetSecurityDescriptorSacl@@YAHPEAXHPEAU_ACL@@H@Z`
- size: `111`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _ACL *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003c7b0`
- `0x18003f9b0`

## callees

- `0x18001d19c`
- `0x180043f2c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043f56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043f56`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043f6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043f6c`

## string_xrefs

- `0x180043f65`: `SetSecurityDescriptorSacl`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DLSetSecurityDescriptorSacl(void *a1, unsigned int a2, struct _ACL *a3)
{
  FARPROC ProcAddress; // rax
  unsigned int v7; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_180070350;
  if ( qword_180070350 )
    return ((unsigned int (__fastcall *)(void *, _QWORD, struct _ACL *, _QWORD))ProcAddress)(a1, a2, a3, 0);
  v7 = 0;
  SecurityDll = DLpLoadSecurityDll();
  if ( !SecurityDll )
  {
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "SetSecurityDescriptorSacl");
    qword_180070350 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v7;
    return ((unsigned int (__fastcall *)(void *, _QWORD, struct _ACL *, _QWORD))ProcAddress)(a1, a2, a3, 0);
  }
  SetLastError(SecurityDll);
  return v7;
}

```

## disassembly

```asm
0x180043f2c  push    rbx
0x180043f2e  push    rbp
0x180043f2f  push    rsi
0x180043f30  push    rdi
0x180043f31  sub     rsp, 38h
0x180043f35  mov     rax, cs:qword_180070350
0x180043f3c  mov     rdi, r8
0x180043f3f  mov     esi, edx
0x180043f41  mov     rbp, rcx
0x180043f44  test    rax, rax
0x180043f47  jnz     short loc_180043F7E
0x180043f49  xor     ebx, ebx
0x180043f4b  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180043f50  test    eax, eax
0x180043f52  jz      short loc_180043F5E
0x180043f54  mov     ecx, eax; dwErrCode
0x180043f56  call    cs:__imp_SetLastError
0x180043f5c  jmp     short loc_180043F90
0x180043f5e  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180043f65  lea     rdx, aSetsecuritydes; "SetSecurityDescriptorSacl"
0x180043f6c  call    cs:__imp_GetProcAddress
0x180043f72  mov     cs:qword_180070350, rax
0x180043f79  test    rax, rax
0x180043f7c  jz      short loc_180043F90
0x180043f7e  xor     r9d, r9d
0x180043f81  mov     r8, rdi
0x180043f84  mov     edx, esi
0x180043f86  mov     rcx, rbp
0x180043f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f8e  mov     ebx, eax
0x180043f90  mov     eax, ebx
0x180043f92  add     rsp, 38h
0x180043f96  pop     rdi
0x180043f97  pop     rsi
0x180043f98  pop     rbp
0x180043f99  pop     rbx
0x180043f9a  retn
```
