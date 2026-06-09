# DLAllocateAndInitializeSid(_SID_IDENTIFIER_AUTHORITY *,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,void * *)

- ea: `0x18001b3c4`
- end: `0x18001b47f`
- name: `?DLAllocateAndInitializeSid@@YAHPEAU_SID_IDENTIFIER_AUTHORITY@@EKKKKKKKKPEAPEAX@Z`
- size: `187`
- prototype: `__int64 __fastcall(struct _SID_IDENTIFIER_AUTHORITY *, __int64, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003e670`
- `0x18003e720`
- `0x18003f730`

## callees

- `0x18001b3c4`
- `0x18001d19c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b477`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b477`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b45d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b45d`

## string_xrefs

- `0x18001b456`: `AllocateAndInitializeSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DLAllocateAndInitializeSid(
        struct _SID_IDENTIFIER_AUTHORITY *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        void **a11)
{
  FARPROC ProcAddress; // rax
  char v14; // bp
  unsigned int v16; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_180070348;
  v14 = a2;
  if ( !qword_180070348 )
  {
    v16 = 0;
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return v16;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "AllocateAndInitializeSid");
    qword_180070348 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v16;
  }
  LOBYTE(a2) = v14;
  return ((unsigned int (__fastcall *)(struct _SID_IDENTIFIER_AUTHORITY *, __int64, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, void **))ProcAddress)(
           a1,
           a2,
           a3,
           a4,
           0,
           0,
           0,
           0,
           0,
           0,
           a11);
}

```

## disassembly

```asm
0x18001b3c4  push    rbx
0x18001b3c6  push    rbp
0x18001b3c7  push    rsi
0x18001b3c8  push    rdi
0x18001b3c9  push    r14
0x18001b3cb  sub     rsp, 60h
0x18001b3cf  mov     rax, cs:qword_180070348
0x18001b3d6  mov     edi, r9d
0x18001b3d9  mov     esi, r8d
0x18001b3dc  mov     bpl, dl
0x18001b3df  mov     r14, rcx
0x18001b3e2  test    rax, rax
0x18001b3e5  jz      short loc_18001B444
0x18001b3e7  mov     rcx, [rsp+88h+arg_50]
0x18001b3ef  mov     r9d, edi
0x18001b3f2  mov     [rsp+88h+var_38], rcx
0x18001b3f7  mov     r8d, esi
0x18001b3fa  mov     [rsp+88h+var_40], 0
0x18001b402  mov     dl, bpl
0x18001b405  mov     [rsp+88h+var_48], 0
0x18001b40d  mov     rcx, r14
0x18001b410  mov     [rsp+88h+var_50], 0
0x18001b418  mov     [rsp+88h+var_58], 0
0x18001b420  mov     [rsp+88h+var_60], 0
0x18001b428  mov     [rsp+88h+var_68], 0
0x18001b430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b435  mov     ebx, eax
0x18001b437  mov     eax, ebx
0x18001b439  add     rsp, 60h
0x18001b43d  pop     r14
0x18001b43f  pop     rdi
0x18001b440  pop     rsi
0x18001b441  pop     rbp
0x18001b442  pop     rbx
0x18001b443  retn
0x18001b444  xor     ebx, ebx
0x18001b446  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001b44b  test    eax, eax
0x18001b44d  jnz     short loc_18001B475
0x18001b44f  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001b456  lea     rdx, aAllocateandini; "AllocateAndInitializeSid"
0x18001b45d  call    cs:__imp_GetProcAddress
0x18001b463  mov     cs:qword_180070348, rax
0x18001b46a  test    rax, rax
0x18001b46d  jnz     loc_18001B3E7
0x18001b473  jmp     short loc_18001B437
0x18001b475  mov     ecx, eax; dwErrCode
0x18001b477  call    cs:__imp_SetLastError
0x18001b47d  jmp     short loc_18001B437
```
