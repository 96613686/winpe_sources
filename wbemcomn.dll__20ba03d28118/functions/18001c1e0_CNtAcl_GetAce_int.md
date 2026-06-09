# CNtAcl::GetAce(int)

- ea: `0x18001c1e0`
- end: `0x18001c282`
- name: `?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z`
- size: `162`
- prototype: `struct CNtAce *__fastcall(CNtAcl *__hidden this, int)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a650`
- `0x18001b490`
- `0x18001b8a0`
- `0x18001c030`
- `0x18003b210`
- `0x18003cad0`

## callees

- `0x18000a290`
- `0x18001c1e0`
- `0x18001c5c0`
- `0x18001d19c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c256`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c256`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c26e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c26e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct CNtAce *__fastcall CNtAcl::GetAce(CNtAcl *this, unsigned int a2)
{
  __int64 v3; // rbx
  FARPROC ProcAddress; // rax
  struct CNtAce *result; // rax
  DWORD SecurityDll; // eax
  struct _ACCESS_ALLOWED_ACE *v7; // [rsp+30h] [rbp+8h] BYREF
  struct CNtAce *v8; // [rsp+40h] [rbp+18h]

  v3 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    return 0;
  v7 = 0;
  ProcAddress = (FARPROC)qword_1800702D8;
  if ( !qword_1800702D8 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return 0;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetAce");
    qword_1800702D8 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return 0;
  }
  if ( !((unsigned int (__fastcall *)(__int64, _QWORD, struct _ACCESS_ALLOWED_ACE **))ProcAddress)(v3, a2, &v7) )
    return 0;
  result = (struct CNtAce *)CWin32DefaultArena::WbemMemAlloc(0x18u);
  v8 = result;
  if ( result )
    return CNtAce::CNtAce(result, v7);
  return result;
}

```

## disassembly

```asm
0x18001c1e0  mov     [rsp+arg_8], rbx
0x18001c1e5  push    rdi
0x18001c1e6  sub     rsp, 20h
0x18001c1ea  mov     edi, edx
0x18001c1ec  mov     rbx, [rcx]
0x18001c1ef  test    rbx, rbx
0x18001c1f2  jz      short loc_18001C25C
0x18001c1f4  mov     [rsp+28h+arg_0], 0
0x18001c1fd  mov     rax, cs:qword_1800702D8
0x18001c204  test    rax, rax
0x18001c207  jz      short loc_18001C24B
0x18001c209  lea     r8, [rsp+28h+arg_0]
0x18001c20e  mov     edx, edi
0x18001c210  mov     rcx, rbx
0x18001c213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c218  test    eax, eax
0x18001c21a  jz      short loc_18001C25C
0x18001c21c  mov     ecx, 18h; unsigned __int64
0x18001c221  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001c226  mov     [rsp+28h+arg_10], rax
0x18001c22b  test    rax, rax
0x18001c22e  jz      short loc_18001C23E
0x18001c230  mov     rdx, [rsp+28h+arg_0]; struct _ACCESS_ALLOWED_ACE *
0x18001c235  mov     rcx, rax; this
0x18001c238  call    ??0CNtAce@@QEAA@PEAU_ACCESS_ALLOWED_ACE@@@Z; CNtAce::CNtAce(_ACCESS_ALLOWED_ACE *)
0x18001c23d  nop
0x18001c23e  mov     rbx, [rsp+28h+arg_8]
0x18001c243  add     rsp, 20h
0x18001c247  pop     rdi
0x18001c248  retn
0x18001c249  jmp     short loc_18001C23E
0x18001c24b  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001c250  test    eax, eax
0x18001c252  jz      short loc_18001C260
0x18001c254  mov     ecx, eax; dwErrCode
0x18001c256  call    cs:__imp_SetLastError
0x18001c25c  xor     eax, eax
0x18001c25e  jmp     short loc_18001C23E
0x18001c260  lea     rdx, aGetace; "GetAce"
0x18001c267  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001c26e  call    cs:__imp_GetProcAddress
0x18001c274  mov     cs:qword_1800702D8, rax
0x18001c27b  test    rax, rax
0x18001c27e  jz      short loc_18001C25C
0x18001c280  jmp     short loc_18001C209
```
