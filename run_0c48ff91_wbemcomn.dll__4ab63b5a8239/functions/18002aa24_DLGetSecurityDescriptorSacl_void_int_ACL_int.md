# DLGetSecurityDescriptorSacl(void *,int *,_ACL * *,int *)

- ea: `0x18002aa24`
- end: `0x18002aa9e`
- name: `?DLGetSecurityDescriptorSacl@@YAHPEAXPEAHPEAPEAU_ACL@@1@Z`
- size: `122`
- prototype: `__int64 __fastcall(void *, int *, struct _ACL **, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003d280`

## callees

- `0x18001d19c`
- `0x18002aa24`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aa96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aa96`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002aa75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002aa75`

## string_xrefs

- `0x18002aa6e`: `GetSecurityDescriptorSacl`

## pseudocode

```c
__int64 __fastcall DLGetSecurityDescriptorSacl(void *a1, int *a2, struct _ACL **a3, int *a4)
{
  FARPROC ProcAddress; // rax
  unsigned int v9; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_1800702C8;
  if ( qword_1800702C8 )
    return ((unsigned int (__fastcall *)(void *, int *, struct _ACL **, int *))ProcAddress)(a1, a2, a3, a4);
  v9 = 0;
  SecurityDll = DLpLoadSecurityDll();
  if ( SecurityDll )
  {
    SetLastError(SecurityDll);
    return v9;
  }
  ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetSecurityDescriptorSacl");
  qword_1800702C8 = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(void *, int *, struct _ACL **, int *))ProcAddress)(a1, a2, a3, a4);
  return v9;
}

```

## disassembly

```asm
0x18002aa24  push    rbx
0x18002aa26  push    rbp
0x18002aa27  push    rsi
0x18002aa28  push    rdi
0x18002aa29  push    r14
0x18002aa2b  sub     rsp, 30h
0x18002aa2f  mov     rax, cs:qword_1800702C8
0x18002aa36  mov     rdi, r9
0x18002aa39  mov     rsi, r8
0x18002aa3c  mov     rbp, rdx
0x18002aa3f  mov     r14, rcx
0x18002aa42  test    rax, rax
0x18002aa45  jz      short loc_18002AA89
0x18002aa47  mov     r9, rdi
0x18002aa4a  mov     r8, rsi
0x18002aa4d  mov     rdx, rbp
0x18002aa50  mov     rcx, r14
0x18002aa53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa58  mov     ebx, eax
0x18002aa5a  mov     eax, ebx
0x18002aa5c  add     rsp, 30h
0x18002aa60  pop     r14
0x18002aa62  pop     rdi
0x18002aa63  pop     rsi
0x18002aa64  pop     rbp
0x18002aa65  pop     rbx
0x18002aa66  retn
0x18002aa67  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18002aa6e  lea     rdx, aGetsecuritydes_1; "GetSecurityDescriptorSacl"
0x18002aa75  call    cs:__imp_GetProcAddress
0x18002aa7b  mov     cs:qword_1800702C8, rax
0x18002aa82  test    rax, rax
0x18002aa85  jz      short loc_18002AA5A
0x18002aa87  jmp     short loc_18002AA47
0x18002aa89  xor     ebx, ebx
0x18002aa8b  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18002aa90  test    eax, eax
0x18002aa92  jz      short loc_18002AA67
0x18002aa94  mov     ecx, eax; dwErrCode
0x18002aa96  call    cs:__imp_SetLastError
0x18002aa9c  jmp     short loc_18002AA5A
```
