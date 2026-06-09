# CNtSecurityDescriptor::SetFromAbsoluteCopy(SNtAbsoluteSD *)

- ea: `0x180023b40`
- end: `0x180023d35`
- name: `?SetFromAbsoluteCopy@CNtSecurityDescriptor@@QEAAHPEAUSNtAbsoluteSD@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(CNtSecurityDescriptor *__hidden this, struct SNtAbsoluteSD *)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a730`
- `0x180023800`
- `0x180023a60`
- `0x18003c7b0`
- `0x18003f9b0`

## callees

- `0x18000a290`
- `0x18000ab30`
- `0x18001d19c`
- `0x180023b40`
- `0x180023d3c`
- `0x1800442d3`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bf4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023caf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023cee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023caf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023cee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023c8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023cc8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023d04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023c8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023cc8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023d04`

## string_xrefs

- `0x180023c86`: `GetSecurityDescriptorControl`

## pseudocode

```c
__int64 __fastcall CNtSecurityDescriptor::SetFromAbsoluteCopy(void **this, void **a2)
{
  void *v4; // rsi
  FARPROC ProcAddress; // rax
  FARPROC v6; // rax
  void *v7; // rsi
  void *v8; // rax
  FARPROC v9; // rax
  void *v10; // rsi
  void *v11; // rdi
  DWORD SecurityDll; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  void *v16; // rcx
  __int16 v17; // [rsp+48h] [rbp+10h] BYREF
  size_t Size; // [rsp+50h] [rbp+18h] BYREF
  int v19; // [rsp+58h] [rbp+20h] BYREF

  if ( !a2 || !(unsigned int)DLIsValidSecurityDescriptor(*a2) )
    return 0;
  v4 = *a2;
  v17 = 0;
  v19 = 0;
  ProcAddress = (FARPROC)qword_180070340;
  if ( !qword_180070340 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return 0;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetSecurityDescriptorControl");
    qword_180070340 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return 0;
  }
  if ( !((unsigned int (__fastcall *)(void *, __int16 *, int *))ProcAddress)(v4, &v17, &v19) || v17 < 0 )
    return 0;
  if ( *this )
  {
    CMUILocale::_Free(*this);
    *this = 0;
  }
  v6 = (FARPROC)qword_1800702E0;
  *((_DWORD *)this + 2) = 1;
  v7 = *a2;
  LODWORD(Size) = 0;
  if ( v6 )
    goto LABEL_9;
  v14 = DLpLoadSecurityDll();
  if ( v14 )
  {
    SetLastError(v14);
  }
  else
  {
    v6 = GetProcAddress(g_hInstSecurityDLL, "MakeSelfRelativeSD");
    qword_1800702E0 = (__int64)v6;
    if ( v6 )
LABEL_9:
      ((void (__fastcall *)(void *, _QWORD, size_t *))v6)(v7, 0, &Size);
  }
  if ( GetLastError() == 122 )
  {
    v8 = CWin32DefaultArena::WbemMemAlloc((unsigned int)Size);
    *this = v8;
    if ( v8 )
    {
      memset_0(v8, 0, (unsigned int)Size);
      v9 = (FARPROC)qword_1800702E0;
      v10 = *this;
      v11 = *a2;
      if ( qword_1800702E0 )
        goto LABEL_13;
      v15 = DLpLoadSecurityDll();
      if ( v15 )
      {
        SetLastError(v15);
      }
      else
      {
        v9 = GetProcAddress(g_hInstSecurityDLL, "MakeSelfRelativeSD");
        qword_1800702E0 = (__int64)v9;
        if ( v9 )
        {
LABEL_13:
          if ( ((unsigned int (__fastcall *)(void *, void *, size_t *))v9)(v11, v10, &Size) )
          {
            *((_DWORD *)this + 2) = 0;
            return 1;
          }
        }
      }
      v16 = *this;
      *((_DWORD *)this + 2) = 3;
      CMUILocale::_Free(v16);
      *this = 0;
      return 0;
    }
  }
  *((_DWORD *)this + 2) = 3;
  return 0;
}

```

## disassembly

```asm
0x180023b40  push    rbx
0x180023b42  push    rsi
0x180023b43  push    rdi
0x180023b44  sub     rsp, 20h
0x180023b48  mov     rdi, rdx
0x180023b4b  mov     rbx, rcx
0x180023b4e  test    rdx, rdx
0x180023b51  jz      loc_180023C68
0x180023b57  mov     rcx, [rdx]; void *
0x180023b5a  call    ?DLIsValidSecurityDescriptor@@YAHPEAX@Z; DLIsValidSecurityDescriptor(void *)
0x180023b5f  test    eax, eax
0x180023b61  jz      loc_180023C68
0x180023b67  mov     rsi, [rdi]
0x180023b6a  xor     eax, eax
0x180023b6c  mov     [rsp+38h+arg_8], ax
0x180023b71  mov     [rsp+38h+arg_18], eax
0x180023b75  mov     rax, cs:qword_180070340
0x180023b7c  test    rax, rax
0x180023b7f  jz      loc_180023C6C
0x180023b85  lea     r8, [rsp+38h+arg_18]
0x180023b8a  mov     rcx, rsi
0x180023b8d  lea     rdx, [rsp+38h+arg_8]
0x180023b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b97  test    eax, eax
0x180023b99  jz      loc_180023C68
0x180023b9f  mov     eax, 8000h
0x180023ba4  test    [rsp+38h+arg_8], ax
0x180023ba9  jnz     loc_180023C68
0x180023baf  mov     rcx, [rbx]; void *
0x180023bb2  test    rcx, rcx
0x180023bb5  jz      short loc_180023BC3
0x180023bb7  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180023bbc  mov     qword ptr [rbx], 0
0x180023bc3  mov     rax, cs:qword_1800702E0
0x180023bca  mov     dword ptr [rbx+8], 1
0x180023bd1  mov     rsi, [rdi]
0x180023bd4  mov     dword ptr [rsp+38h+Size], 0
0x180023bdc  test    rax, rax
0x180023bdf  jz      loc_180023CA4
0x180023be5  lea     r8, [rsp+38h+Size]
0x180023bea  xor     edx, edx
0x180023bec  mov     rcx, rsi
0x180023bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bf4  call    cs:__imp_GetLastError
0x180023bfa  cmp     eax, 7Ah ; 'z'
0x180023bfd  jnz     short loc_180023C61
0x180023bff  mov     ecx, dword ptr [rsp+38h+Size]; unsigned __int64
0x180023c03  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180023c08  mov     [rbx], rax
0x180023c0b  test    rax, rax
0x180023c0e  jz      short loc_180023C61
0x180023c10  mov     r8d, dword ptr [rsp+38h+Size]; Size
0x180023c15  xor     edx, edx; Val
0x180023c17  mov     rcx, rax; void *
0x180023c1a  call    memset_0
0x180023c1f  mov     rax, cs:qword_1800702E0
0x180023c26  mov     rsi, [rbx]
0x180023c29  mov     rdi, [rdi]
0x180023c2c  test    rax, rax
0x180023c2f  jz      loc_180023CE3
0x180023c35  lea     r8, [rsp+38h+Size]
0x180023c3a  mov     rdx, rsi
0x180023c3d  mov     rcx, rdi
0x180023c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c45  test    eax, eax
0x180023c47  jz      loc_180023D1A
0x180023c4d  mov     dword ptr [rbx+8], 0
0x180023c54  mov     eax, 1
0x180023c59  add     rsp, 20h
0x180023c5d  pop     rdi
0x180023c5e  pop     rsi
0x180023c5f  pop     rbx
0x180023c60  retn
0x180023c61  mov     dword ptr [rbx+8], 3
0x180023c68  xor     eax, eax
0x180023c6a  jmp     short loc_180023C59
0x180023c6c  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180023c71  test    eax, eax
0x180023c73  jz      short loc_180023C7F
0x180023c75  mov     ecx, eax; dwErrCode
0x180023c77  call    cs:__imp_SetLastError
0x180023c7d  jmp     short loc_180023C68
0x180023c7f  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180023c86  lea     rdx, aGetsecuritydes_2; "GetSecurityDescriptorControl"
0x180023c8d  call    cs:__imp_GetProcAddress
0x180023c93  mov     cs:qword_180070340, rax
0x180023c9a  test    rax, rax
0x180023c9d  jz      short loc_180023C68
0x180023c9f  jmp     loc_180023B85
0x180023ca4  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180023ca9  test    eax, eax
0x180023cab  jz      short loc_180023CBA
0x180023cad  mov     ecx, eax; dwErrCode
0x180023caf  call    cs:__imp_SetLastError
0x180023cb5  jmp     loc_180023BF4
0x180023cba  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180023cc1  lea     rdx, aMakeselfrelati; "MakeSelfRelativeSD"
0x180023cc8  call    cs:__imp_GetProcAddress
0x180023cce  mov     cs:qword_1800702E0, rax
0x180023cd5  test    rax, rax
0x180023cd8  jz      loc_180023BF4
0x180023cde  jmp     loc_180023BE5
0x180023ce3  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180023ce8  test    eax, eax
0x180023cea  jz      short loc_180023CF6
0x180023cec  mov     ecx, eax; dwErrCode
0x180023cee  call    cs:__imp_SetLastError
0x180023cf4  jmp     short loc_180023D1A
0x180023cf6  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180023cfd  lea     rdx, aMakeselfrelati; "MakeSelfRelativeSD"
0x180023d04  call    cs:__imp_GetProcAddress
0x180023d0a  mov     cs:qword_1800702E0, rax
0x180023d11  test    rax, rax
0x180023d14  jnz     loc_180023C35
0x180023d1a  mov     rcx, [rbx]; void *
0x180023d1d  mov     dword ptr [rbx+8], 3
0x180023d24  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180023d29  mov     qword ptr [rbx], 0
0x180023d30  jmp     loc_180023C68
```
