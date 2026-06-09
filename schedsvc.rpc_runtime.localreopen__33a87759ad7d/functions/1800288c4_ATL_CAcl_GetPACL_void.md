# ATL::CAcl::GetPACL(void)

- ea: `0x1800288c4`
- end: `0x180028a1e`
- name: `?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ`
- size: `346`
- prototype: `const struct _ACL *__fastcall(ATL::CAcl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800269f0`

## callees

- `0x1800288c4`
- `0x1800504b4`
- `0x1800528ac`
- `0x180084010`

## import_xrefs

- `msvcrt!malloc` at `0x180028932`
- `msvcrt!malloc` at `0x180028932`
- `msvcrt!free` at `0x18002896a`
- `msvcrt!free` at `0x1800289f9`
- `msvcrt!free` at `0x18002896a`
- `msvcrt!free` at `0x1800289f9`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180028955`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180028955`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800289e0`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800289e0`

## pseudocode

```c
const struct _ACL *__fastcall ATL::CAcl::GetPACL(ATL::CAcl *this)
{
  DWORD v2; // esi
  unsigned int v3; // ebx
  unsigned int v4; // ebp
  __int64 v5; // rax
  struct _ACL *v6; // rax
  unsigned int Error; // ebx
  unsigned int i; // esi
  __int64 v9; // rax
  __int64 v10; // r14
  DWORD nAceListLength; // ebx
  void *v12; // rax
  unsigned int v13; // ebx

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
      ATL::PrivateAtlThrow(0x8007000E);
    if ( !InitializeAcl(v6, v2, *((_DWORD *)this + 5)) )
    {
      Error = ATL::AtlHresultFromLastError();
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
      ATL::PrivateAtlThrow(Error);
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
      ATL::PrivateAtlThrow(v13);
    }
  }
  return (const struct _ACL *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x1800288c4  push    rbx
0x1800288c6  push    rbp
0x1800288c7  push    rsi
0x1800288c8  push    rdi
0x1800288c9  push    r14
0x1800288cb  sub     rsp, 30h
0x1800288cf  cmp     qword ptr [rcx+8], 0
0x1800288d4  mov     rdi, rcx
0x1800288d7  jnz     loc_180028A0F
0x1800288dd  cmp     byte ptr [rcx+10h], 0
0x1800288e1  jnz     loc_180028A0F
0x1800288e7  mov     rax, [rcx]
0x1800288ea  mov     esi, 8
0x1800288ef  mov     rax, [rax+8]
0x1800288f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288f8  xor     ebx, ebx
0x1800288fa  mov     ebp, eax
0x1800288fc  test    eax, eax
0x1800288fe  jz      short loc_180028930
0x180028900  mov     rcx, [rdi]
0x180028903  mov     edx, ebx
0x180028905  mov     rax, [rcx+20h]
0x180028909  mov     rcx, rdi
0x18002890c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028911  mov     rdx, rax
0x180028914  test    rax, rax
0x180028917  jz      short loc_18002892A
0x180028919  mov     rcx, [rax]
0x18002891c  mov     rax, [rcx+10h]
0x180028920  mov     rcx, rdx
0x180028923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028928  add     esi, eax
0x18002892a  inc     ebx
0x18002892c  cmp     ebx, ebp
0x18002892e  jb      short loc_180028900
0x180028930  mov     ecx, esi; Size
0x180028932  call    cs:__imp_malloc
0x180028938  mov     [rdi+8], rax
0x18002893c  test    rax, rax
0x18002893f  jnz     short loc_18002894C
0x180028941  mov     ecx, 8007000Eh; unsigned int
0x180028946  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002894c  mov     r8d, [rdi+14h]; dwAclRevision
0x180028950  mov     edx, esi; nAclLength
0x180028952  mov     rcx, rax; pAcl
0x180028955  call    cs:__imp_InitializeAcl
0x18002895b  test    eax, eax
0x18002895d  jnz     short loc_180028980
0x18002895f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180028964  mov     rcx, [rdi+8]; Block
0x180028968  mov     ebx, eax
0x18002896a  call    cs:__imp_free
0x180028970  mov     ecx, ebx; unsigned int
0x180028972  mov     qword ptr [rdi+8], 0
0x18002897a  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180028980  mov     rax, [rdi]
0x180028983  mov     rcx, rdi
0x180028986  mov     rax, [rax+28h]
0x18002898a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002898f  xor     esi, esi
0x180028991  cmp     esi, ebp
0x180028993  jnb     short loc_180028A0F
0x180028995  mov     rax, [rdi]
0x180028998  mov     edx, esi
0x18002899a  mov     rcx, rdi
0x18002899d  mov     rax, [rax+20h]
0x1800289a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289a6  mov     r14, rax
0x1800289a9  test    rax, rax
0x1800289ac  jz      short loc_1800289EE
0x1800289ae  mov     rcx, [rax]
0x1800289b1  mov     rax, [rcx+10h]
0x1800289b5  mov     rcx, r14
0x1800289b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289bd  mov     rcx, [r14]
0x1800289c0  mov     ebx, eax
0x1800289c2  mov     rax, [rcx+8]
0x1800289c6  mov     rcx, r14
0x1800289c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289ce  mov     edx, [rdi+14h]; dwAceRevision
0x1800289d1  mov     r9, rax; pAceList
0x1800289d4  mov     rcx, [rdi+8]; pAcl
0x1800289d8  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1800289dc  mov     [rsp+58h+nAceListLength], ebx; nAceListLength
0x1800289e0  call    cs:__imp_AddAce
0x1800289e6  test    eax, eax
0x1800289e8  jz      short loc_1800289EE
0x1800289ea  inc     esi
0x1800289ec  jmp     short loc_180028991
0x1800289ee  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800289f3  mov     rcx, [rdi+8]; Block
0x1800289f7  mov     ebx, eax
0x1800289f9  call    cs:__imp_free
0x1800289ff  mov     ecx, ebx; unsigned int
0x180028a01  mov     qword ptr [rdi+8], 0
0x180028a09  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180028a0f  mov     rax, [rdi+8]
0x180028a13  add     rsp, 30h
0x180028a17  pop     r14
0x180028a19  pop     rdi
0x180028a1a  pop     rsi
0x180028a1b  pop     rbp
0x180028a1c  pop     rbx
0x180028a1d  retn
```
