# DLCheckTokenMembership(void *,void *,int *)

- ea: `0x18001c658`
- end: `0x18001c6c8`
- name: `?DLCheckTokenMembership@@YAHPEAX0PEAH@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *, void *, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001be80`
- `0x18003e670`
- `0x18003e720`

## callees

- `0x18001c658`
- `0x18001d19c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c69e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c69e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c6b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c6b4`

## string_xrefs

- `0x18001c6ad`: `CheckTokenMembership`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DLCheckTokenMembership(void *a1, void *a2, int *a3)
{
  FARPROC ProcAddress; // rax
  unsigned int v7; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_180070320;
  if ( !qword_180070320 )
  {
    v7 = 0;
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return v7;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "CheckTokenMembership");
    qword_180070320 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v7;
  }
  return ((unsigned int (__fastcall *)(void *, void *, int *))ProcAddress)(a1, a2, a3);
}

```

## disassembly

```asm
0x18001c658  push    rbx
0x18001c65a  push    rbp
0x18001c65b  push    rsi
0x18001c65c  push    rdi
0x18001c65d  sub     rsp, 28h
0x18001c661  mov     rax, cs:qword_180070320
0x18001c668  mov     rdi, r8
0x18001c66b  mov     rsi, rdx
0x18001c66e  mov     rbp, rcx
0x18001c671  test    rax, rax
0x18001c674  jz      short loc_18001C691
0x18001c676  mov     r8, rdi
0x18001c679  mov     rdx, rsi
0x18001c67c  mov     rcx, rbp
0x18001c67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c684  mov     ebx, eax
0x18001c686  mov     eax, ebx
0x18001c688  add     rsp, 28h
0x18001c68c  pop     rdi
0x18001c68d  pop     rsi
0x18001c68e  pop     rbp
0x18001c68f  pop     rbx
0x18001c690  retn
0x18001c691  xor     ebx, ebx
0x18001c693  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001c698  test    eax, eax
0x18001c69a  jz      short loc_18001C6A6
0x18001c69c  mov     ecx, eax; dwErrCode
0x18001c69e  call    cs:__imp_SetLastError
0x18001c6a4  jmp     short loc_18001C686
0x18001c6a6  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001c6ad  lea     rdx, aChecktokenmemb; "CheckTokenMembership"
0x18001c6b4  call    cs:__imp_GetProcAddress
0x18001c6ba  mov     cs:qword_180070320, rax
0x18001c6c1  test    rax, rax
0x18001c6c4  jz      short loc_18001C686
0x18001c6c6  jmp     short loc_18001C676
```
