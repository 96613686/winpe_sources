# CNtSecurityDescriptor::CNtSecurityDescriptor(void)

- ea: `0x180025aa0`
- end: `0x180025c54`
- name: `??0CNtSecurityDescriptor@@QEAA@XZ`
- size: `436`
- prototype: `CNtSecurityDescriptor *__fastcall(CNtSecurityDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003d310`

## callees

- `0x18000a290`
- `0x18000ab30`
- `0x18001d19c`
- `0x180025aa0`
- `0x180025c5c`
- `0x1800442d3`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025bbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025bfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025bbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025bfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025bd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025c12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025bd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025c12`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CNtSecurityDescriptor *__fastcall CNtSecurityDescriptor::CNtSecurityDescriptor(CNtSecurityDescriptor *this)
{
  unsigned int v2; // edx
  _OWORD *v3; // rdi
  FARPROC ProcAddress; // rax
  void *v5; // rax
  FARPROC v6; // rax
  __int64 v7; // rsi
  void *v9; // rcx
  DWORD SecurityDll; // eax
  DWORD v11; // eax
  void *v12; // rcx
  size_t Size; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  v3 = CWin32DefaultArena::WbemMemAlloc(0x28u);
  if ( !v3 )
  {
    v9 = 0;
    goto LABEL_12;
  }
  *v3 = 0;
  v3[1] = 0;
  *((_QWORD *)v3 + 4) = 0;
  if ( !(unsigned int)DLInitializeSecurityDescriptor(v3, v2) )
  {
    v9 = v3;
LABEL_12:
    CMUILocale::_Free(v9);
    *((_DWORD *)this + 2) = 3;
    return this;
  }
  ProcAddress = (FARPROC)qword_1800702E0;
  LODWORD(Size) = 0;
  if ( !qword_1800702E0 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      goto LABEL_5;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "MakeSelfRelativeSD");
    qword_1800702E0 = (__int64)ProcAddress;
    if ( !ProcAddress )
      goto LABEL_5;
  }
  ((void (__fastcall *)(_OWORD *, _QWORD, size_t *))ProcAddress)(v3, 0, &Size);
LABEL_5:
  if ( GetLastError() != 122 || (v5 = CWin32DefaultArena::WbemMemAlloc((unsigned int)Size), (*(_QWORD *)this = v5) == 0) )
  {
    *((_DWORD *)this + 2) = 3;
    goto LABEL_23;
  }
  memset_0(v5, 0, (unsigned int)Size);
  v6 = (FARPROC)qword_1800702E0;
  v7 = *(_QWORD *)this;
  if ( !qword_1800702E0 )
  {
    v11 = DLpLoadSecurityDll();
    if ( v11 )
    {
      SetLastError(v11);
      goto LABEL_21;
    }
    v6 = GetProcAddress(g_hInstSecurityDLL, "MakeSelfRelativeSD");
    qword_1800702E0 = (__int64)v6;
    if ( !v6 )
      goto LABEL_21;
  }
  if ( !((unsigned int (__fastcall *)(_OWORD *, __int64, size_t *))v6)(v3, v7, &Size) )
  {
LABEL_21:
    v12 = *(void **)this;
    *((_DWORD *)this + 2) = 3;
    CMUILocale::_Free(v12);
    *(_QWORD *)this = 0;
LABEL_23:
    CMUILocale::_Free(v3);
    return this;
  }
  CMUILocale::_Free(v3);
  *((_DWORD *)this + 2) = 0;
  return this;
}

```

## disassembly

```asm
0x180025aa0  mov     [rsp+arg_8], rbx
0x180025aa5  mov     [rsp+arg_10], rsi
0x180025aaa  push    rdi
0x180025aab  sub     rsp, 20h
0x180025aaf  mov     rbx, rcx
0x180025ab2  mov     qword ptr [rcx], 0
0x180025ab9  mov     dword ptr [rcx+8], 0
0x180025ac0  mov     ecx, 28h ; '('; unsigned __int64
0x180025ac5  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180025aca  mov     rdi, rax
0x180025acd  test    rax, rax
0x180025ad0  jz      loc_180025BAE
0x180025ad6  xorps   xmm0, xmm0
0x180025ad9  xor     eax, eax
0x180025adb  movups  xmmword ptr [rdi], xmm0
0x180025ade  mov     rcx, rdi; void *
0x180025ae1  movups  xmmword ptr [rdi+10h], xmm0
0x180025ae5  mov     [rdi+20h], rax
0x180025ae9  call    ?DLInitializeSecurityDescriptor@@YAHPEAXK@Z; DLInitializeSecurityDescriptor(void *,ulong)
0x180025aee  test    eax, eax
0x180025af0  jz      loc_180025B9D
0x180025af6  mov     rax, cs:qword_1800702E0
0x180025afd  mov     dword ptr [rsp+28h+Size], 0
0x180025b05  test    rax, rax
0x180025b08  jz      loc_180025BB2
0x180025b0e  lea     r8, [rsp+28h+Size]
0x180025b13  xor     edx, edx
0x180025b15  mov     rcx, rdi
0x180025b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b1d  call    cs:__imp_GetLastError
0x180025b23  cmp     eax, 7Ah ; 'z'
0x180025b26  jnz     loc_180025C40
0x180025b2c  mov     ecx, dword ptr [rsp+28h+Size]; unsigned __int64
0x180025b30  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180025b35  mov     [rbx], rax
0x180025b38  test    rax, rax
0x180025b3b  jz      loc_180025C40
0x180025b41  mov     r8d, dword ptr [rsp+28h+Size]; Size
0x180025b46  xor     edx, edx; Val
0x180025b48  mov     rcx, rax; void *
0x180025b4b  call    memset_0
0x180025b50  mov     rax, cs:qword_1800702E0
0x180025b57  mov     rsi, [rbx]
0x180025b5a  test    rax, rax
0x180025b5d  jz      loc_180025BF1
0x180025b63  lea     r8, [rsp+28h+Size]
0x180025b68  mov     rdx, rsi
0x180025b6b  mov     rcx, rdi
0x180025b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b73  test    eax, eax
0x180025b75  jz      loc_180025C28
0x180025b7b  mov     rcx, rdi; void *
0x180025b7e  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180025b83  mov     dword ptr [rbx+8], 0
0x180025b8a  mov     rsi, [rsp+28h+arg_10]
0x180025b8f  mov     rax, rbx
0x180025b92  mov     rbx, [rsp+28h+arg_8]
0x180025b97  add     rsp, 20h
0x180025b9b  pop     rdi
0x180025b9c  retn
0x180025b9d  mov     rcx, rdi; void *
0x180025ba0  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180025ba5  mov     dword ptr [rbx+8], 3
0x180025bac  jmp     short loc_180025B8A
0x180025bae  xor     ecx, ecx
0x180025bb0  jmp     short loc_180025BA0
0x180025bb2  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180025bb7  test    eax, eax
0x180025bb9  jz      short loc_180025BC8
0x180025bbb  mov     ecx, eax; dwErrCode
0x180025bbd  call    cs:__imp_SetLastError
0x180025bc3  jmp     loc_180025B1D
0x180025bc8  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180025bcf  lea     rdx, aMakeselfrelati; "MakeSelfRelativeSD"
0x180025bd6  call    cs:__imp_GetProcAddress
0x180025bdc  mov     cs:qword_1800702E0, rax
0x180025be3  test    rax, rax
0x180025be6  jz      loc_180025B1D
0x180025bec  jmp     loc_180025B0E
0x180025bf1  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180025bf6  test    eax, eax
0x180025bf8  jz      short loc_180025C04
0x180025bfa  mov     ecx, eax; dwErrCode
0x180025bfc  call    cs:__imp_SetLastError
0x180025c02  jmp     short loc_180025C28
0x180025c04  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180025c0b  lea     rdx, aMakeselfrelati; "MakeSelfRelativeSD"
0x180025c12  call    cs:__imp_GetProcAddress
0x180025c18  mov     cs:qword_1800702E0, rax
0x180025c1f  test    rax, rax
0x180025c22  jnz     loc_180025B63
0x180025c28  mov     rcx, [rbx]; void *
0x180025c2b  mov     dword ptr [rbx+8], 3
0x180025c32  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180025c37  mov     qword ptr [rbx], 0
0x180025c3e  jmp     short loc_180025C47
0x180025c40  mov     dword ptr [rbx+8], 3
0x180025c47  mov     rcx, rdi; void *
0x180025c4a  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180025c4f  jmp     loc_180025B8A
```
