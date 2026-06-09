# ATL::CAcl::GetPACL(void)

- ea: `0x1800237dc`
- end: `0x180023959`
- name: `?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ`
- size: `381`
- prototype: `const struct _ACL *__fastcall(ATL::CAcl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021ba0`

## callees

- `0x1800237dc`
- `0x1800529a0`
- `0x180055004`
- `0x180088010`

## import_xrefs

- `msvcrt!malloc` at `0x18002384a`
- `msvcrt!malloc` at `0x18002384a`
- `msvcrt!free` at `0x18002388e`
- `msvcrt!free` at `0x18002392d`
- `msvcrt!free` at `0x18002388e`
- `msvcrt!free` at `0x18002392d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180023873`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180023873`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18002390e`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18002390e`

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
0x1800237dc  push    rbx
0x1800237de  push    rbp
0x1800237df  push    rsi
0x1800237e0  push    rdi
0x1800237e1  push    r14
0x1800237e3  sub     rsp, 30h
0x1800237e7  cmp     qword ptr [rcx+8], 0
0x1800237ec  mov     rdi, rcx
0x1800237ef  jnz     loc_180023949
0x1800237f5  cmp     byte ptr [rcx+10h], 0
0x1800237f9  jnz     loc_180023949
0x1800237ff  mov     rax, [rcx]
0x180023802  mov     esi, 8
0x180023807  mov     rax, [rax+8]
0x18002380b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023810  xor     ebx, ebx
0x180023812  mov     ebp, eax
0x180023814  test    eax, eax
0x180023816  jz      short loc_180023848
0x180023818  mov     rcx, [rdi]
0x18002381b  mov     edx, ebx
0x18002381d  mov     rax, [rcx+20h]
0x180023821  mov     rcx, rdi
0x180023824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023829  mov     rdx, rax
0x18002382c  test    rax, rax
0x18002382f  jz      short loc_180023842
0x180023831  mov     rcx, [rax]
0x180023834  mov     rax, [rcx+10h]
0x180023838  mov     rcx, rdx
0x18002383b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023840  add     esi, eax
0x180023842  inc     ebx
0x180023844  cmp     ebx, ebp
0x180023846  jb      short loc_180023818
0x180023848  mov     ecx, esi; Size
0x18002384a  call    cs:__imp_malloc
0x180023851  nop     dword ptr [rax+rax+00h]
0x180023856  mov     [rdi+8], rax
0x18002385a  test    rax, rax
0x18002385d  jnz     short loc_18002386A
0x18002385f  mov     ecx, 8007000Eh; unsigned int
0x180023864  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002386a  mov     r8d, [rdi+14h]; dwAclRevision
0x18002386e  mov     edx, esi; nAclLength
0x180023870  mov     rcx, rax; pAcl
0x180023873  call    cs:__imp_InitializeAcl
0x18002387a  nop     dword ptr [rax+rax+00h]
0x18002387f  test    eax, eax
0x180023881  jnz     short loc_1800238AA
0x180023883  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180023888  mov     rcx, [rdi+8]; Block
0x18002388c  mov     ebx, eax
0x18002388e  call    cs:__imp_free
0x180023895  nop     dword ptr [rax+rax+00h]
0x18002389a  mov     ecx, ebx; unsigned int
0x18002389c  mov     qword ptr [rdi+8], 0
0x1800238a4  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800238aa  mov     rax, [rdi]
0x1800238ad  mov     rcx, rdi
0x1800238b0  mov     rax, [rax+28h]
0x1800238b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238b9  xor     esi, esi
0x1800238bb  cmp     esi, ebp
0x1800238bd  jnb     loc_180023949
0x1800238c3  mov     rax, [rdi]
0x1800238c6  mov     edx, esi
0x1800238c8  mov     rcx, rdi
0x1800238cb  mov     rax, [rax+20h]
0x1800238cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238d4  mov     r14, rax
0x1800238d7  test    rax, rax
0x1800238da  jz      short loc_180023922
0x1800238dc  mov     rcx, [rax]
0x1800238df  mov     rax, [rcx+10h]
0x1800238e3  mov     rcx, r14
0x1800238e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238eb  mov     rcx, [r14]
0x1800238ee  mov     ebx, eax
0x1800238f0  mov     rax, [rcx+8]
0x1800238f4  mov     rcx, r14
0x1800238f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238fc  mov     edx, [rdi+14h]; dwAceRevision
0x1800238ff  mov     r9, rax; pAceList
0x180023902  mov     rcx, [rdi+8]; pAcl
0x180023906  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18002390a  mov     [rsp+58h+nAceListLength], ebx; nAceListLength
0x18002390e  call    cs:__imp_AddAce
0x180023915  nop     dword ptr [rax+rax+00h]
0x18002391a  test    eax, eax
0x18002391c  jz      short loc_180023922
0x18002391e  inc     esi
0x180023920  jmp     short loc_1800238BB
0x180023922  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180023927  mov     rcx, [rdi+8]; Block
0x18002392b  mov     ebx, eax
0x18002392d  call    cs:__imp_free
0x180023934  nop     dword ptr [rax+rax+00h]
0x180023939  mov     ecx, ebx; unsigned int
0x18002393b  mov     qword ptr [rdi+8], 0
0x180023943  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180023949  mov     rax, [rdi+8]
0x18002394d  add     rsp, 30h
0x180023951  pop     r14
0x180023953  pop     rdi
0x180023954  pop     rsi
0x180023955  pop     rbp
0x180023956  pop     rbx
0x180023957  retn
```
