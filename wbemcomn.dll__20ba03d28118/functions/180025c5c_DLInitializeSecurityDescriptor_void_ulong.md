# DLInitializeSecurityDescriptor(void *,ulong)

- ea: `0x180025c5c`
- end: `0x180025cc8`
- name: `?DLInitializeSecurityDescriptor@@YAHPEAXK@Z`
- size: `108`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025aa0`

## callees

- `0x18001d19c`
- `0x180025c5c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025c9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025c9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025cb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025cb4`

## string_xrefs

- `0x180025cad`: `InitializeSecurityDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DLInitializeSecurityDescriptor(void *a1)
{
  FARPROC ProcAddress; // rax
  unsigned int v3; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_1800702D0;
  if ( !qword_1800702D0 )
  {
    v3 = 0;
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return v3;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "InitializeSecurityDescriptor");
    qword_1800702D0 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v3;
  }
  return ((unsigned int (__fastcall *)(void *, __int64))ProcAddress)(a1, 1);
}

```

## disassembly

```asm
0x180025c5c  mov     [rsp+arg_0], rbx
0x180025c61  push    rdi
0x180025c62  sub     rsp, 20h
0x180025c66  mov     rax, cs:qword_1800702D0
0x180025c6d  mov     rdi, rcx
0x180025c70  test    rax, rax
0x180025c73  jz      short loc_180025C91
0x180025c75  mov     edx, 1
0x180025c7a  mov     rcx, rdi
0x180025c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c82  mov     ebx, eax
0x180025c84  mov     eax, ebx
0x180025c86  mov     rbx, [rsp+28h+arg_0]
0x180025c8b  add     rsp, 20h
0x180025c8f  pop     rdi
0x180025c90  retn
0x180025c91  xor     ebx, ebx
0x180025c93  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180025c98  test    eax, eax
0x180025c9a  jz      short loc_180025CA6
0x180025c9c  mov     ecx, eax; dwErrCode
0x180025c9e  call    cs:__imp_SetLastError
0x180025ca4  jmp     short loc_180025C84
0x180025ca6  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180025cad  lea     rdx, aInitializesecu; "InitializeSecurityDescriptor"
0x180025cb4  call    cs:__imp_GetProcAddress
0x180025cba  mov     cs:qword_1800702D0, rax
0x180025cc1  test    rax, rax
0x180025cc4  jz      short loc_180025C84
0x180025cc6  jmp     short loc_180025C75
```
