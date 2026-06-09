# CNtSecurityDescriptor::GetSacl(CNtAcl * *)

- ea: `0x18002a8e0`
- end: `0x18002a9e8`
- name: `?GetSacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z`
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
- `0x18002a8e0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a973`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a930`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a930`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a946`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a946`

## string_xrefs

- `0x18002a938`: `GetSecurityDescriptorSacl`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall CNtSecurityDescriptor::GetSacl(CNtSecurityDescriptor *this, struct CNtAcl **a2)
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
  ProcAddress = (FARPROC)qword_1800702C8;
  if ( qword_1800702C8 )
    goto LABEL_22;
  SecurityDll = DLpLoadSecurityDll();
  if ( SecurityDll )
  {
    SetLastError(SecurityDll);
    goto LABEL_8;
  }
  ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetSecurityDescriptorSacl");
  qword_1800702C8 = (__int64)ProcAddress;
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
0x18002a8e0  mov     [rsp+arg_8], rbx
0x18002a8e5  push    rdi
0x18002a8e6  sub     rsp, 40h
0x18002a8ea  mov     rbx, rdx
0x18002a8ed  mov     [rsp+48h+arg_0], 0
0x18002a8f5  mov     [rsp+48h+arg_10], 0
0x18002a8fd  cmp     dword ptr [rcx+8], 0
0x18002a901  jz      short loc_18002A90D
0x18002a903  mov     eax, 80041001h
0x18002a908  jmp     loc_18002A9DD
0x18002a90d  mov     [rsp+48h+arg_18], 0
0x18002a916  mov     rdi, [rcx]
0x18002a919  mov     rax, cs:qword_1800702C8
0x18002a920  test    rax, rax
0x18002a923  jnz     short loc_18002A958
0x18002a925  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18002a92a  test    eax, eax
0x18002a92c  jz      short loc_18002A938
0x18002a92e  mov     ecx, eax; dwErrCode
0x18002a930  call    cs:__imp_SetLastError
0x18002a936  jmp     short loc_18002A973
0x18002a938  lea     rdx, aGetsecuritydes_1; "GetSecurityDescriptorSacl"
0x18002a93f  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18002a946  call    cs:__imp_GetProcAddress
0x18002a94c  mov     cs:qword_1800702C8, rax
0x18002a953  test    rax, rax
0x18002a956  jz      short loc_18002A973
0x18002a958  lea     r9, [rsp+48h+arg_10]
0x18002a95d  lea     r8, [rsp+48h+arg_18]
0x18002a962  lea     rdx, [rsp+48h+arg_0]
0x18002a967  mov     rcx, rdi
0x18002a96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a96f  test    eax, eax
0x18002a971  jnz     short loc_18002A987
0x18002a973  call    cs:__imp_GetLastError
0x18002a979  test    eax, eax
0x18002a97b  jle     short loc_18002A9DD
0x18002a97d  movzx   eax, ax
0x18002a980  or      eax, 80070000h
0x18002a985  jmp     short loc_18002A9DD
0x18002a987  cmp     [rsp+48h+arg_0], 0
0x18002a98c  jnz     short loc_18002A999
0x18002a98e  mov     qword ptr [rbx], 0
0x18002a995  xor     eax, eax
0x18002a997  jmp     short loc_18002A9DD
0x18002a999  mov     ecx, 10h; unsigned __int64
0x18002a99e  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002a9a3  mov     [rsp+48h+var_18], rax
0x18002a9a8  test    rax, rax
0x18002a9ab  jz      short loc_18002A9BB
0x18002a9ad  mov     rdx, [rsp+48h+arg_18]; struct _ACL *
0x18002a9b2  mov     rcx, rax; this
0x18002a9b5  call    ??0CNtAcl@@QEAA@PEAU_ACL@@@Z; CNtAcl::CNtAcl(_ACL *)
0x18002a9ba  nop
0x18002a9bb  test    rax, rax
0x18002a9be  jz      short loc_18002A9D8
0x18002a9c0  cmp     dword ptr [rax+8], 0
0x18002a9c4  jz      short loc_18002A9D3
0x18002a9c6  mov     rcx, rax; this
0x18002a9c9  call    ??_GCNtAcl@@QEAAPEAXI@Z; CNtAcl::`scalar deleting destructor'(uint)
0x18002a9ce  jmp     loc_18002A903
0x18002a9d3  mov     [rbx], rax
0x18002a9d6  jmp     short loc_18002A995
0x18002a9d8  mov     eax, 80041006h
0x18002a9dd  mov     rbx, [rsp+48h+arg_8]
0x18002a9e2  add     rsp, 40h
0x18002a9e6  pop     rdi
0x18002a9e7  retn
```
