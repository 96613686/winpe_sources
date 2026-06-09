# DLGetKernelObjectSecurity(void *,ulong,void *,ulong,ulong *)

- ea: `0x180043e24`
- end: `0x180043ea4`
- name: `?DLGetKernelObjectSecurity@@YAHPEAXK0KPEAK@Z`
- size: `128`
- prototype: `__int64 __fastcall(void *, __int64, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003f730`

## callees

- `0x18001d19c`
- `0x180043e24`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043e4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043e4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043e65`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043e65`

## string_xrefs

- `0x180043e5e`: `GetKernelObjectSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DLGetKernelObjectSecurity(void *a1, __int64 a2, void *a3, unsigned int a4, unsigned int *a5)
{
  FARPROC ProcAddress; // rax
  unsigned int v9; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_1800702E8;
  if ( qword_1800702E8 )
    return ((unsigned int (__fastcall *)(void *, __int64, void *, _QWORD, unsigned int *))ProcAddress)(
             a1,
             4,
             a3,
             a4,
             a5);
  v9 = 0;
  SecurityDll = DLpLoadSecurityDll();
  if ( !SecurityDll )
  {
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetKernelObjectSecurity");
    qword_1800702E8 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v9;
    return ((unsigned int (__fastcall *)(void *, __int64, void *, _QWORD, unsigned int *))ProcAddress)(
             a1,
             4,
             a3,
             a4,
             a5);
  }
  SetLastError(SecurityDll);
  return v9;
}

```

## disassembly

```asm
0x180043e24  push    rbx
0x180043e26  push    rbp
0x180043e27  push    rsi
0x180043e28  push    rdi
0x180043e29  sub     rsp, 38h
0x180043e2d  mov     rax, cs:qword_1800702E8
0x180043e34  mov     edi, r9d
0x180043e37  mov     rsi, r8
0x180043e3a  mov     rbp, rcx
0x180043e3d  test    rax, rax
0x180043e40  jnz     short loc_180043E77
0x180043e42  xor     ebx, ebx
0x180043e44  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180043e49  test    eax, eax
0x180043e4b  jz      short loc_180043E57
0x180043e4d  mov     ecx, eax; dwErrCode
0x180043e4f  call    cs:__imp_SetLastError
0x180043e55  jmp     short loc_180043E99
0x180043e57  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180043e5e  lea     rdx, aGetkernelobjec; "GetKernelObjectSecurity"
0x180043e65  call    cs:__imp_GetProcAddress
0x180043e6b  mov     cs:qword_1800702E8, rax
0x180043e72  test    rax, rax
0x180043e75  jz      short loc_180043E99
0x180043e77  mov     rcx, [rsp+58h+arg_20]
0x180043e7f  mov     r9d, edi
0x180043e82  mov     [rsp+58h+var_38], rcx
0x180043e87  mov     r8, rsi
0x180043e8a  mov     rcx, rbp
0x180043e8d  mov     edx, 4
0x180043e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e97  mov     ebx, eax
0x180043e99  mov     eax, ebx
0x180043e9b  add     rsp, 38h
0x180043e9f  pop     rdi
0x180043ea0  pop     rsi
0x180043ea1  pop     rbp
0x180043ea2  pop     rbx
0x180043ea3  retn
```
