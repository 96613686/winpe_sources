# DLConvertStringSecurityDescriptorToSecurityDescriptorW(ushort const *,ulong,void * *,ulong *)

- ea: `0x1800440ec`
- end: `0x18004415f`
- name: `?DLConvertStringSecurityDescriptorToSecurityDescriptorW@@YAHPEBGKPEAPEAXPEAK@Z`
- size: `115`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f8a0`
- `0x18002cec0`

## callees

- `0x1800440ec`
- `0x180044168`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044117`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044117`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004412d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004412d`

## string_xrefs

- `0x180044126`: `ConvertStringSecurityDescriptorToSecurityDescriptorW`

## pseudocode

```c
__int64 __fastcall DLConvertStringSecurityDescriptorToSecurityDescriptorW(
        const unsigned __int16 *a1,
        __int64 a2,
        void **a3,
        unsigned int *a4)
{
  FARPROC ProcAddress; // rax
  unsigned int v8; // ebx
  DWORD SddlDll; // eax

  ProcAddress = (FARPROC)qword_180070400;
  if ( qword_180070400 )
    return ((unsigned int (__fastcall *)(const unsigned __int16 *, __int64, void **, unsigned int *))ProcAddress)(
             a1,
             1,
             a3,
             a4);
  v8 = 0;
  SddlDll = DLpLoadSddlDll();
  if ( !SddlDll )
  {
    ProcAddress = GetProcAddress(g_hInstSddlDLL, "ConvertStringSecurityDescriptorToSecurityDescriptorW");
    qword_180070400 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v8;
    return ((unsigned int (__fastcall *)(const unsigned __int16 *, __int64, void **, unsigned int *))ProcAddress)(
             a1,
             1,
             a3,
             a4);
  }
  SetLastError(SddlDll);
  return v8;
}

```

## disassembly

```asm
0x1800440ec  push    rbx
0x1800440ee  push    rbp
0x1800440ef  push    rsi
0x1800440f0  push    rdi
0x1800440f1  sub     rsp, 38h
0x1800440f5  mov     rax, cs:qword_180070400
0x1800440fc  mov     rdi, r9
0x1800440ff  mov     rsi, r8
0x180044102  mov     rbp, rcx
0x180044105  test    rax, rax
0x180044108  jnz     short loc_18004413F
0x18004410a  xor     ebx, ebx
0x18004410c  call    ?DLpLoadSddlDll@@YAKXZ; DLpLoadSddlDll(void)
0x180044111  test    eax, eax
0x180044113  jz      short loc_18004411F
0x180044115  mov     ecx, eax; dwErrCode
0x180044117  call    cs:__imp_SetLastError
0x18004411d  jmp     short loc_180044154
0x18004411f  mov     rcx, cs:?g_hInstSddlDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180044126  lea     rdx, aConvertstrings_0; "ConvertStringSecurityDescriptorToSecuri"...
0x18004412d  call    cs:__imp_GetProcAddress
0x180044133  mov     cs:qword_180070400, rax
0x18004413a  test    rax, rax
0x18004413d  jz      short loc_180044154
0x18004413f  mov     r9, rdi
0x180044142  mov     r8, rsi
0x180044145  mov     edx, 1
0x18004414a  mov     rcx, rbp
0x18004414d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044152  mov     ebx, eax
0x180044154  mov     eax, ebx
0x180044156  add     rsp, 38h
0x18004415a  pop     rdi
0x18004415b  pop     rsi
0x18004415c  pop     rbp
0x18004415d  pop     rbx
0x18004415e  retn
```
