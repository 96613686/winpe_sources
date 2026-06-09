# CNtSecurityDescriptor::GetDacl(CNtAcl * *)

- ea: `0x18002b370`
- end: `0x18002b478`
- name: `?GetDacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(CNtSecurityDescriptor *__hidden this, struct CNtAcl **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a290`
- `0x18001c900`
- `0x18001d19c`
- `0x18001d204`
- `0x18002b370`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b403`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b3c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b3c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b3d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b3d6`

## string_xrefs

- `0x18002b3c8`: `GetSecurityDescriptorDacl`

## pseudocode

```c
signed int __fastcall CNtSecurityDescriptor::GetDacl(CNtSecurityDescriptor *this, struct CNtAcl **a2)
{
  signed int result; // eax
  __int64 v4; // rdi
  FARPROC ProcAddress; // rax
  DWORD SecurityDll; // eax
  CNtAcl *v7; // rax
  int v8; // [rsp+50h] [rbp+8h] BYREF
  int v9; // [rsp+60h] [rbp+18h] BYREF
  struct _ACL *v10; // [rsp+68h] [rbp+20h] BYREF

  v8 = 0;
  v9 = 0;
  if ( *((_DWORD *)this + 2) )
    return -2147217407;
  v10 = 0;
  v4 = *(_QWORD *)this;
  ProcAddress = (FARPROC)qword_1800702C0;
  if ( qword_1800702C0 )
    goto LABEL_22;
  SecurityDll = DLpLoadSecurityDll();
  if ( SecurityDll )
  {
    SetLastError(SecurityDll);
    goto LABEL_8;
  }
  ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetSecurityDescriptorDacl");
  qword_1800702C0 = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_22:
    if ( ((unsigned int (__fastcall *)(__int64, int *, struct _ACL **, int *))ProcAddress)(v4, &v8, &v10, &v9) )
    {
      if ( v8 )
      {
        v7 = (CNtAcl *)CWin32DefaultArena::WbemMemAlloc(0x10u);
        if ( v7 )
          v7 = CNtAcl::CNtAcl(v7, v10);
        if ( !v7 )
          return -2147217402;
        if ( *((_DWORD *)v7 + 2) )
        {
          CNtAcl::`scalar deleting destructor'((void **)v7);
          return -2147217407;
        }
        *a2 = v7;
      }
      else
      {
        *a2 = 0;
      }
      return 0;
    }
  }
LABEL_8:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002b370  mov     [rsp+arg_8], rbx
0x18002b375  push    rdi
0x18002b376  sub     rsp, 40h
0x18002b37a  mov     rbx, rdx
0x18002b37d  mov     [rsp+48h+arg_0], 0
0x18002b385  mov     [rsp+48h+arg_10], 0
0x18002b38d  cmp     dword ptr [rcx+8], 0
0x18002b391  jz      short loc_18002B39D
0x18002b393  mov     eax, 80041001h
0x18002b398  jmp     loc_18002B46D
0x18002b39d  mov     [rsp+48h+arg_18], 0
0x18002b3a6  mov     rdi, [rcx]
0x18002b3a9  mov     rax, cs:qword_1800702C0
0x18002b3b0  test    rax, rax
0x18002b3b3  jnz     short loc_18002B3E8
0x18002b3b5  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18002b3ba  test    eax, eax
0x18002b3bc  jz      short loc_18002B3C8
0x18002b3be  mov     ecx, eax; dwErrCode
0x18002b3c0  call    cs:__imp_SetLastError
0x18002b3c6  jmp     short loc_18002B403
0x18002b3c8  lea     rdx, aGetsecuritydes_0; "GetSecurityDescriptorDacl"
0x18002b3cf  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18002b3d6  call    cs:__imp_GetProcAddress
0x18002b3dc  mov     cs:qword_1800702C0, rax
0x18002b3e3  test    rax, rax
0x18002b3e6  jz      short loc_18002B403
0x18002b3e8  lea     r9, [rsp+48h+arg_10]
0x18002b3ed  lea     r8, [rsp+48h+arg_18]
0x18002b3f2  lea     rdx, [rsp+48h+arg_0]
0x18002b3f7  mov     rcx, rdi
0x18002b3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3ff  test    eax, eax
0x18002b401  jnz     short loc_18002B417
0x18002b403  call    cs:__imp_GetLastError
0x18002b409  test    eax, eax
0x18002b40b  jle     short loc_18002B46D
0x18002b40d  movzx   eax, ax
0x18002b410  or      eax, 80070000h
0x18002b415  jmp     short loc_18002B46D
0x18002b417  cmp     [rsp+48h+arg_0], 0
0x18002b41c  jnz     short loc_18002B429
0x18002b41e  mov     qword ptr [rbx], 0
0x18002b425  xor     eax, eax
0x18002b427  jmp     short loc_18002B46D
0x18002b429  mov     ecx, 10h; unsigned __int64
0x18002b42e  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002b433  mov     [rsp+48h+var_18], rax
0x18002b438  test    rax, rax
0x18002b43b  jz      short loc_18002B44B
0x18002b43d  mov     rdx, [rsp+48h+arg_18]; struct _ACL *
0x18002b442  mov     rcx, rax; this
0x18002b445  call    ??0CNtAcl@@QEAA@PEAU_ACL@@@Z; CNtAcl::CNtAcl(_ACL *)
0x18002b44a  nop
0x18002b44b  test    rax, rax
0x18002b44e  jz      short loc_18002B468
0x18002b450  cmp     dword ptr [rax+8], 0
0x18002b454  jz      short loc_18002B463
0x18002b456  mov     rcx, rax; this
0x18002b459  call    ??_GCNtAcl@@QEAAPEAXI@Z; CNtAcl::`scalar deleting destructor'(uint)
0x18002b45e  jmp     loc_18002B393
0x18002b463  mov     [rbx], rax
0x18002b466  jmp     short loc_18002B425
0x18002b468  mov     eax, 80041006h
0x18002b46d  mov     rbx, [rsp+48h+arg_8]
0x18002b472  add     rsp, 40h
0x18002b476  pop     rdi
0x18002b477  retn
```
