# DLInitializeAcl(_ACL *,ulong,ulong)

- ea: `0x18001d2d0`
- end: `0x18001d34b`
- name: `?DLInitializeAcl@@YAHPEAU_ACL@@KK@Z`
- size: `123`
- prototype: `__int64 __fastcall(struct _ACL *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001d250`

## callees

- `0x18001d19c`
- `0x18001d2d0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d343`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d343`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d322`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d322`

## string_xrefs

- `0x18001d31b`: `InitializeAcl`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DLInitializeAcl(struct _ACL *a1, unsigned int a2)
{
  FARPROC ProcAddress; // rax
  unsigned int v5; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_180070390;
  if ( qword_180070390 )
    return ((unsigned int (__fastcall *)(struct _ACL *, _QWORD, __int64))ProcAddress)(a1, a2, 2);
  v5 = 0;
  SecurityDll = DLpLoadSecurityDll();
  if ( SecurityDll )
  {
    SetLastError(SecurityDll);
    return v5;
  }
  ProcAddress = GetProcAddress(g_hInstSecurityDLL, "InitializeAcl");
  qword_180070390 = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(struct _ACL *, _QWORD, __int64))ProcAddress)(a1, a2, 2);
  return v5;
}

```

## disassembly

```asm
0x18001d2d0  mov     [rsp+arg_0], rbx
0x18001d2d5  mov     [rsp+arg_8], rsi
0x18001d2da  push    rdi
0x18001d2db  sub     rsp, 20h
0x18001d2df  mov     rax, cs:qword_180070390
0x18001d2e6  mov     edi, edx
0x18001d2e8  mov     rsi, rcx
0x18001d2eb  test    rax, rax
0x18001d2ee  jz      short loc_18001D336
0x18001d2f0  mov     r8d, 2
0x18001d2f6  mov     edx, edi
0x18001d2f8  mov     rcx, rsi
0x18001d2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d300  mov     ebx, eax
0x18001d302  mov     rsi, [rsp+28h+arg_8]
0x18001d307  mov     eax, ebx
0x18001d309  mov     rbx, [rsp+28h+arg_0]
0x18001d30e  add     rsp, 20h
0x18001d312  pop     rdi
0x18001d313  retn
0x18001d314  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001d31b  lea     rdx, aInitializeacl; "InitializeAcl"
0x18001d322  call    cs:__imp_GetProcAddress
0x18001d328  mov     cs:qword_180070390, rax
0x18001d32f  test    rax, rax
0x18001d332  jz      short loc_18001D302
0x18001d334  jmp     short loc_18001D2F0
0x18001d336  xor     ebx, ebx
0x18001d338  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001d33d  test    eax, eax
0x18001d33f  jz      short loc_18001D314
0x18001d341  mov     ecx, eax; dwErrCode
0x18001d343  call    cs:__imp_SetLastError
0x18001d349  jmp     short loc_18001D302
```
