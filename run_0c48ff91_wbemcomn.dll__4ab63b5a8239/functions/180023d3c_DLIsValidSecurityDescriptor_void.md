# DLIsValidSecurityDescriptor(void *)

- ea: `0x180023d3c`
- end: `0x180023da3`
- name: `?DLIsValidSecurityDescriptor@@YAHPEAX@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800238d0`
- `0x180023900`
- `0x180023b40`

## callees

- `0x18001d19c`
- `0x180023d3c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023d79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023d79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023d8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023d8f`

## string_xrefs

- `0x180023d88`: `IsValidSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall DLIsValidSecurityDescriptor(void *a1)
{
  FARPROC ProcAddress; // rax
  unsigned int v3; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_1800702F0;
  if ( !qword_1800702F0 )
  {
    v3 = 0;
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return v3;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "IsValidSecurityDescriptor");
    qword_1800702F0 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v3;
  }
  return ((unsigned int (__fastcall *)(void *))ProcAddress)(a1);
}

```

## disassembly

```asm
0x180023d3c  mov     [rsp+arg_0], rbx
0x180023d41  push    rdi
0x180023d42  sub     rsp, 20h
0x180023d46  mov     rax, cs:qword_1800702F0
0x180023d4d  mov     rdi, rcx
0x180023d50  test    rax, rax
0x180023d53  jz      short loc_180023D6C
0x180023d55  mov     rcx, rdi
0x180023d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d5d  mov     ebx, eax
0x180023d5f  mov     eax, ebx
0x180023d61  mov     rbx, [rsp+28h+arg_0]
0x180023d66  add     rsp, 20h
0x180023d6a  pop     rdi
0x180023d6b  retn
0x180023d6c  xor     ebx, ebx
0x180023d6e  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180023d73  test    eax, eax
0x180023d75  jz      short loc_180023D81
0x180023d77  mov     ecx, eax; dwErrCode
0x180023d79  call    cs:__imp_SetLastError
0x180023d7f  jmp     short loc_180023D5F
0x180023d81  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180023d88  lea     rdx, aIsvalidsecurit; "IsValidSecurityDescriptor"
0x180023d8f  call    cs:__imp_GetProcAddress
0x180023d95  mov     cs:qword_1800702F0, rax
0x180023d9c  test    rax, rax
0x180023d9f  jz      short loc_180023D5F
0x180023da1  jmp     short loc_180023D55
```
