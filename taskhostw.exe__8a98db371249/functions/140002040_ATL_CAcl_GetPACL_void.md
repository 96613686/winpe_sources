# ATL::CAcl::GetPACL(void)

- ea: `0x140002040`
- end: `0x1400021a0`
- name: `?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ`
- size: `352`
- prototype: `const struct _ACL *__fastcall(ATL::CAcl *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001fb0`
- `0x1400022d0`

## callees

- `0x140002040`
- `0x1400072bc`
- `0x140007468`
- `0x14000c010`

## import_xrefs

- `msvcrt!free` at `0x14000215e`
- `msvcrt!free` at `0x14000218a`
- `msvcrt!free` at `0x14000215e`
- `msvcrt!free` at `0x14000218a`
- `msvcrt!malloc` at `0x1400020ae`
- `msvcrt!malloc` at `0x1400020ae`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400020ca`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400020ca`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140002145`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140002145`

## pseudocode

```c
const struct _ACL *__fastcall ATL::CAcl::GetPACL(ATL::CAcl *this)
{
  DWORD v2; // esi
  unsigned int v3; // ebx
  unsigned int v4; // ebp
  __int64 v5; // rax
  struct _ACL *v6; // rax
  unsigned int i; // esi
  __int64 v9; // rax
  __int64 v10; // r14
  DWORD nAceListLength; // ebx
  void *v12; // rax
  signed int Error; // ebx
  signed int v14; // ebx

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
      ATL::PrivateAtlThrow(-2147024882);
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
      v14 = ATL::AtlHresultFromLastError();
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
      ATL::PrivateAtlThrow(v14);
    }
  }
  return (const struct _ACL *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x140002040  push    rbx
0x140002042  push    rbp
0x140002043  push    rsi
0x140002044  push    rdi
0x140002045  push    r14
0x140002047  sub     rsp, 30h
0x14000204b  cmp     qword ptr [rcx+8], 0
0x140002050  mov     rdi, rcx
0x140002053  jnz     loc_1400020E9
0x140002059  cmp     byte ptr [rcx+10h], 0
0x14000205d  jnz     loc_1400020E9
0x140002063  mov     rax, [rcx]
0x140002066  mov     esi, 8
0x14000206b  mov     rax, [rax+8]
0x14000206f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002074  xor     ebx, ebx
0x140002076  mov     ebp, eax
0x140002078  test    eax, eax
0x14000207a  jz      short loc_1400020AC
0x14000207c  mov     rcx, [rdi]
0x14000207f  mov     edx, ebx
0x140002081  mov     rax, [rcx+20h]
0x140002085  mov     rcx, rdi
0x140002088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000208d  mov     rdx, rax
0x140002090  test    rax, rax
0x140002093  jz      short loc_1400020A6
0x140002095  mov     rcx, [rax]
0x140002098  mov     rax, [rcx+10h]
0x14000209c  mov     rcx, rdx
0x14000209f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020a4  add     esi, eax
0x1400020a6  inc     ebx
0x1400020a8  cmp     ebx, ebp
0x1400020aa  jb      short loc_14000207C
0x1400020ac  mov     ecx, esi; Size
0x1400020ae  call    cs:__imp_malloc
0x1400020b4  mov     [rdi+8], rax
0x1400020b8  test    rax, rax
0x1400020bb  jz      loc_140002174
0x1400020c1  mov     r8d, [rdi+14h]; dwAclRevision
0x1400020c5  mov     edx, esi; nAclLength
0x1400020c7  mov     rcx, rax; pAcl
0x1400020ca  call    cs:__imp_InitializeAcl
0x1400020d0  test    eax, eax
0x1400020d2  jz      short loc_140002153
0x1400020d4  mov     rax, [rdi]
0x1400020d7  mov     rcx, rdi
0x1400020da  mov     rax, [rax+28h]
0x1400020de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020e3  xor     esi, esi
0x1400020e5  cmp     esi, ebp
0x1400020e7  jb      short loc_1400020F8
0x1400020e9  mov     rax, [rdi+8]
0x1400020ed  add     rsp, 30h
0x1400020f1  pop     r14
0x1400020f3  pop     rdi
0x1400020f4  pop     rsi
0x1400020f5  pop     rbp
0x1400020f6  pop     rbx
0x1400020f7  retn
0x1400020f8  mov     rax, [rdi]
0x1400020fb  mov     edx, esi
0x1400020fd  mov     rcx, rdi
0x140002100  mov     rax, [rax+20h]
0x140002104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002109  mov     r14, rax
0x14000210c  test    rax, rax
0x14000210f  jz      short loc_14000217F
0x140002111  mov     rcx, [rax]
0x140002114  mov     rax, [rcx+10h]
0x140002118  mov     rcx, r14
0x14000211b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002120  mov     rcx, [r14]
0x140002123  mov     ebx, eax
0x140002125  mov     rax, [rcx+8]
0x140002129  mov     rcx, r14
0x14000212c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002131  mov     edx, [rdi+14h]; dwAceRevision
0x140002134  mov     r9, rax; pAceList
0x140002137  mov     rcx, [rdi+8]; pAcl
0x14000213b  mov     r8d, 0FFFFFFFFh; dwStartingAceIndex
0x140002141  mov     [rsp+58h+nAceListLength], ebx; nAceListLength
0x140002145  call    cs:__imp_AddAce
0x14000214b  test    eax, eax
0x14000214d  jz      short loc_14000217F
0x14000214f  inc     esi
0x140002151  jmp     short loc_1400020E5
0x140002153  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140002158  mov     rcx, [rdi+8]; Block
0x14000215c  mov     ebx, eax
0x14000215e  call    cs:__imp_free
0x140002164  mov     ecx, ebx; int
0x140002166  mov     qword ptr [rdi+8], 0
0x14000216e  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x140002174  mov     ecx, 8007000Eh; int
0x140002179  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x14000217f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140002184  mov     rcx, [rdi+8]; Block
0x140002188  mov     ebx, eax
0x14000218a  call    cs:__imp_free
0x140002190  mov     ecx, ebx; int
0x140002192  mov     qword ptr [rdi+8], 0
0x14000219a  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
