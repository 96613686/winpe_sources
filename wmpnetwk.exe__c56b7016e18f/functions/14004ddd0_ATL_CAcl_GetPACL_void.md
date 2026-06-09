# ATL::CAcl::GetPACL(void)

- ea: `0x14004ddd0`
- end: `0x14004df2a`
- name: `?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ`
- size: `346`
- prototype: `const struct _ACL *__fastcall(ATL::CAcl *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400538b0`
- `0x1400923dc`
- `0x140093330`

## callees

- `0x1400396dc`
- `0x14004bb5c`
- `0x14004ddd0`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x14004de61`
- `ADVAPI32!InitializeAcl` at `0x14004de61`
- `ADVAPI32!AddAce` at `0x14004deec`
- `ADVAPI32!AddAce` at `0x14004deec`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004de76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004df05`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004de76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14004df05`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14004de3e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14004de3e`

## pseudocode

```c
const struct _ACL *__fastcall ATL::CAcl::GetPACL(ATL::CAcl *this)
{
  DWORD v2; // esi
  unsigned int v3; // ebx
  unsigned int v4; // ebp
  __int64 v5; // rax
  struct _ACL *v6; // rax
  int Error; // ebx
  unsigned int i; // esi
  __int64 v9; // rax
  __int64 v10; // r14
  DWORD nAceListLength; // ebx
  void *v12; // rax
  int v13; // ebx

  if ( !*((_QWORD *)this + 1) && !*((_BYTE *)this + 16) )
  {
    v2 = 8;
    v3 = 0;
    v4 = (*(__int64 (__fastcall **)(ATL::CAcl *))(*(_QWORD *)this + 8LL))(this);
    if ( v4 )
    {
      do
      {
        v5 = (*(__int64 (__fastcall **)(ATL::CAcl *, _QWORD))(*(_QWORD *)this + 32LL))(this, v3);
        if ( v5 )
          v2 += (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        ++v3;
      }
      while ( v3 < v4 );
    }
    v6 = (struct _ACL *)malloc(v2);
    *((_QWORD *)this + 1) = v6;
    if ( !v6 )
      ATL::AtlThrowImpl(-2147024882);
    if ( !InitializeAcl(v6, v2, *((_DWORD *)this + 5)) )
    {
      Error = ATL::AtlHresultFromLastError();
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
      ATL::AtlThrowImpl(Error);
    }
    (*(void (__fastcall **)(ATL::CAcl *))(*(_QWORD *)this + 40LL))(this);
    for ( i = 0; i < v4; ++i )
    {
      v9 = (*(__int64 (__fastcall **)(ATL::CAcl *, _QWORD))(*(_QWORD *)this + 32LL))(this, i);
      v10 = v9;
      if ( v9 )
      {
        nAceListLength = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        v12 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
        if ( AddAce(*((PACL *)this + 1), *((_DWORD *)this + 5), 0xFFFFFFFF, v12, nAceListLength) )
          continue;
      }
      v13 = ATL::AtlHresultFromLastError();
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
      ATL::AtlThrowImpl(v13);
    }
  }
  return (const struct _ACL *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x14004ddd0  push    rbx
0x14004ddd2  push    rbp
0x14004ddd3  push    rsi
0x14004ddd4  push    rdi
0x14004ddd5  push    r14
0x14004ddd7  sub     rsp, 30h
0x14004dddb  cmp     qword ptr [rcx+8], 0
0x14004dde0  mov     rdi, rcx
0x14004dde3  jnz     loc_14004DF1B
0x14004dde9  cmp     byte ptr [rcx+10h], 0
0x14004dded  jnz     loc_14004DF1B
0x14004ddf3  mov     rax, [rcx]
0x14004ddf6  mov     esi, 8
0x14004ddfb  mov     rax, [rax+8]
0x14004ddff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004de04  xor     ebx, ebx
0x14004de06  mov     ebp, eax
0x14004de08  test    eax, eax
0x14004de0a  jz      short loc_14004DE3C
0x14004de0c  mov     rcx, [rdi]
0x14004de0f  mov     edx, ebx
0x14004de11  mov     rax, [rcx+20h]
0x14004de15  mov     rcx, rdi
0x14004de18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004de1d  mov     rdx, rax
0x14004de20  test    rax, rax
0x14004de23  jz      short loc_14004DE36
0x14004de25  mov     rcx, [rax]
0x14004de28  mov     rax, [rcx+10h]
0x14004de2c  mov     rcx, rdx
0x14004de2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004de34  add     esi, eax
0x14004de36  inc     ebx
0x14004de38  cmp     ebx, ebp
0x14004de3a  jb      short loc_14004DE0C
0x14004de3c  mov     ecx, esi; Size
0x14004de3e  call    cs:__imp_malloc
0x14004de44  mov     [rdi+8], rax
0x14004de48  test    rax, rax
0x14004de4b  jnz     short loc_14004DE58
0x14004de4d  mov     ecx, 8007000Eh; int
0x14004de52  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14004de58  mov     r8d, [rdi+14h]; dwAclRevision
0x14004de5c  mov     edx, esi; nAclLength
0x14004de5e  mov     rcx, rax; pAcl
0x14004de61  call    cs:__imp_InitializeAcl
0x14004de67  test    eax, eax
0x14004de69  jnz     short loc_14004DE8C
0x14004de6b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14004de70  mov     rcx, [rdi+8]; Block
0x14004de74  mov     ebx, eax
0x14004de76  call    cs:__imp_free
0x14004de7c  mov     ecx, ebx; int
0x14004de7e  mov     qword ptr [rdi+8], 0
0x14004de86  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14004de8c  mov     rax, [rdi]
0x14004de8f  mov     rcx, rdi
0x14004de92  mov     rax, [rax+28h]
0x14004de96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004de9b  xor     esi, esi
0x14004de9d  cmp     esi, ebp
0x14004de9f  jnb     short loc_14004DF1B
0x14004dea1  mov     rax, [rdi]
0x14004dea4  mov     edx, esi
0x14004dea6  mov     rcx, rdi
0x14004dea9  mov     rax, [rax+20h]
0x14004dead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004deb2  mov     r14, rax
0x14004deb5  test    rax, rax
0x14004deb8  jz      short loc_14004DEFA
0x14004deba  mov     rcx, [rax]
0x14004debd  mov     rax, [rcx+10h]
0x14004dec1  mov     rcx, r14
0x14004dec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dec9  mov     rcx, [r14]
0x14004decc  mov     ebx, eax
0x14004dece  mov     rax, [rcx+8]
0x14004ded2  mov     rcx, r14
0x14004ded5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004deda  mov     edx, [rdi+14h]; dwAceRevision
0x14004dedd  mov     r9, rax; pAceList
0x14004dee0  mov     rcx, [rdi+8]; pAcl
0x14004dee4  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x14004dee8  mov     [rsp+58h+nAceListLength], ebx; nAceListLength
0x14004deec  call    cs:__imp_AddAce
0x14004def2  test    eax, eax
0x14004def4  jz      short loc_14004DEFA
0x14004def6  inc     esi
0x14004def8  jmp     short loc_14004DE9D
0x14004defa  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14004deff  mov     rcx, [rdi+8]; Block
0x14004df03  mov     ebx, eax
0x14004df05  call    cs:__imp_free
0x14004df0b  mov     ecx, ebx; int
0x14004df0d  mov     qword ptr [rdi+8], 0
0x14004df15  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14004df1b  mov     rax, [rdi+8]
0x14004df1f  add     rsp, 30h
0x14004df23  pop     r14
0x14004df25  pop     rdi
0x14004df26  pop     rsi
0x14004df27  pop     rbp
0x14004df28  pop     rbx
0x14004df29  retn
```
