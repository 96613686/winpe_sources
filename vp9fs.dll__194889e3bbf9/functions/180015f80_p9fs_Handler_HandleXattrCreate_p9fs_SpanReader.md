# p9fs::Handler::HandleXattrCreate(p9fs::SpanReader &)

- ea: `0x180015f80`
- end: `0x180016309`
- name: `?HandleXattrCreate@Handler@p9fs@@AEAAJAEAVSpanReader@2@@Z`
- size: `905`
- prototype: `__int64 __fastcall(p9fs::Handler *__hidden this, struct p9fs::SpanReader *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18000f528`

## callees

- `0x1800030b0`
- `0x1800030d0`
- `0x180004120`
- `0x1800074e0`
- `0x18000be58`
- `0x18000c208`
- `0x180015f80`
- `0x180016840`
- `0x1800192a8`
- `0x18001c75c`
- `0x18001c93c`
- `0x180034010`

## string_xrefs

- `0x1800162f7`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall p9fs::Handler::HandleXattrCreate(
        p9fs::Handler *this,
        struct p9fs::SpanReader *a2,
        __int64 a3,
        const char *a4)
{
  p9fs::Handler *v5; // r14
  unsigned __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // esi
  const char *v9; // r9
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rax
  const char *v12; // r9
  unsigned __int64 v13; // rdx
  __int64 v14; // rdi
  int v15; // ebx
  __int64 v16; // r15
  unsigned int v17; // esi
  volatile signed __int32 *v18; // rbx
  const char *v20; // r9
  __int64 *v21; // r8
  __int64 *v22; // rdx
  __int64 *v23; // rcx
  __int64 *v24; // rax
  _QWORD *v25; // rdx
  char v26; // al
  volatile signed __int32 *v27; // rcx
  volatile signed __int32 *v28; // rsi
  volatile signed __int32 *v29; // rbx
  volatile signed __int32 *v30; // rbx
  __int128 v31; // [rsp+30h] [rbp-49h] BYREF
  __int128 v32; // [rsp+40h] [rbp-39h] BYREF
  int v33; // [rsp+5Ch] [rbp-1Dh]
  char v34[8]; // [rsp+68h] [rbp-11h] BYREF
  __int64 v35; // [rsp+70h] [rbp-9h]
  volatile signed __int32 *v36; // [rsp+78h] [rbp-1h]
  _OWORD v37[2]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v5 = this;
  v6 = *((_QWORD *)a2 + 2);
  if ( *(_QWORD *)a2 - v6 < 4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
      a4);
  if ( *(_QWORD *)a2 < v6 )
    goto LABEL_46;
  v7 = *((_QWORD *)a2 + 1);
  *((_QWORD *)a2 + 2) = v6 + 4;
  v8 = *(_DWORD *)(v7 + v6);
  v31 = 0;
  p9fs::SpanReader::String(a2, &v31);
  v10 = *((_QWORD *)a2 + 2);
  this = *(p9fs::Handler **)a2;
  v11 = *(_QWORD *)a2 - v10;
  if ( v11 < 8 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
      v9);
  if ( (unsigned __int64)this < v10 )
    goto LABEL_46;
  v12 = (const char *)*((_QWORD *)a2 + 1);
  v13 = v10 + 8;
  *((_QWORD *)a2 + 2) = v10 + 8;
  if ( v11 - 8 < 4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
      v12);
  if ( (unsigned __int64)this < v13 || (this = (p9fs::Handler *)((char *)this - v13), (unsigned __int64)this < 4) )
LABEL_46:
    gsl::details::terminate(this);
  v14 = *(_QWORD *)&v12[v10];
  *((_QWORD *)a2 + 2) = v10 + 12;
  v15 = *(_DWORD *)&v12[v13];
  v32 = 0;
  p9fs::Handler::LookupFid(v5, &v32, v8);
  memset(v37, 0, sizeof(v37));
  std::string::_Construct<1,char const *>(v37, v31, *((_QWORD *)&v31 + 1));
  v16 = v32;
  (*(void (__fastcall **)(_QWORD, char *, _OWORD *, __int64))(*(_QWORD *)v32 + 184LL))(v32, v34, v37, v14);
  if ( !v34[0] )
  {
    v17 = v35;
    std::string::~string(v37);
    v18 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
    if ( *((_QWORD *)&v32 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
    return v17;
  }
  *(_QWORD *)&v31 = (char *)v5 + 32;
  Smtx_lock_exclusive((_Smtx_t *)v5 + 4);
  v21 = (__int64 *)*((_QWORD *)v5 + 5);
  v22 = (__int64 *)v21[1];
  v33 = 0;
  v23 = v21;
  if ( !*((_BYTE *)v22 + 25) )
  {
    do
    {
      if ( *((_DWORD *)v22 + 8) >= v8 )
        v23 = v22;
      v24 = v22 + 2;
      if ( *((_DWORD *)v22 + 8) >= v8 )
        v24 = v22;
      v22 = (__int64 *)*v24;
    }
    while ( !*(_BYTE *)(*v24 + 25) );
  }
  if ( *((_BYTE *)v23 + 25) || v8 < *((_DWORD *)v23 + 8) )
  {
    v23 = v21;
LABEL_26:
    v26 = 1;
    v25 = v23 + 5;
    goto LABEL_27;
  }
  if ( v23 == v21 )
    goto LABEL_26;
  v25 = v23 + 5;
  if ( v23[5] != v16 )
    goto LABEL_26;
  v26 = 0;
LABEL_27:
  if ( v26 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x348,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
      (const char *)0x8000FFFFLL,
      v15);
  if ( !v34[0] )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\vm\\inc\\expected.h",
      v20);
  v27 = v36;
  if ( v36 )
  {
    _InterlockedIncrement(v36 + 2);
    v27 = v36;
  }
  *v25 = v35;
  v28 = (volatile signed __int32 *)v25[1];
  v25[1] = v27;
  if ( v28 )
  {
    if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
      if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
    }
  }
  Smtx_unlock_exclusive((_Smtx_t *)v5 + 4);
  if ( v34[0] )
  {
    v29 = v36;
    if ( v36 )
    {
      if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
        if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      }
    }
  }
  std::string::~string(v37);
  v30 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
  if ( *((_QWORD *)&v32 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
      if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180015f80  mov     [rsp-8+arg_10], rbx
0x180015f85  push    rbp
0x180015f86  push    rsi
0x180015f87  push    rdi
0x180015f88  push    r14
0x180015f8a  push    r15
0x180015f8c  lea     rbp, [rsp-37h]
0x180015f91  sub     rsp, 0B0h
0x180015f98  mov     rax, cs:__security_cookie
0x180015f9f  xor     rax, rsp
0x180015fa2  mov     [rbp+57h+var_30], rax
0x180015fa6  mov     rbx, rdx
0x180015fa9  mov     r14, rcx
0x180015fac  mov     rdx, [rdx+10h]
0x180015fb0  mov     rax, [rbx]
0x180015fb3  sub     rax, rdx
0x180015fb6  cmp     rax, 4
0x180015fba  jb      loc_1800162AF
0x180015fc0  cmp     [rbx], rdx
0x180015fc3  jb      loc_1800162A9
0x180015fc9  mov     rcx, [rbx+8]
0x180015fcd  lea     rax, [rdx+4]
0x180015fd1  mov     [rbx+10h], rax
0x180015fd5  mov     esi, [rcx+rdx]
0x180015fd8  xorps   xmm0, xmm0
0x180015fdb  movups  [rbp+57h+var_A0], xmm0
0x180015fdf  lea     rdx, [rbp+57h+var_A0]
0x180015fe3  mov     rcx, rbx
0x180015fe6  call    ?String@SpanReader@p9fs@@QEAA?AV?$basic_string_view@DU?$char_traits@D@std@@@std@@XZ; p9fs::SpanReader::String(void)
0x180015feb  mov     r8, [rbx+10h]
0x180015fef  mov     rcx, [rbx]
0x180015ff2  mov     rax, rcx
0x180015ff5  sub     rax, r8
0x180015ff8  cmp     rax, 8
0x180015ffc  jb      loc_1800162C5
0x180016002  cmp     rcx, r8
0x180016005  jb      loc_1800162A9
0x18001600b  mov     r9, [rbx+8]; char *
0x18001600f  lea     rdx, [r8+8]
0x180016013  mov     [rbx+10h], rdx
0x180016017  add     rax, 0FFFFFFFFFFFFFFF8h
0x18001601b  cmp     rax, 4
0x18001601f  jb      loc_1800162DB
0x180016025  cmp     rcx, rdx
0x180016028  jb      loc_1800162A9
0x18001602e  sub     rcx, rdx
0x180016031  cmp     rcx, 4
0x180016035  jb      loc_1800162A9
0x18001603b  mov     rdi, [r9+r8]
0x18001603f  lea     rax, [r8+0Ch]
0x180016043  mov     [rbx+10h], rax
0x180016047  mov     ebx, [rdx+r9]
0x18001604b  xorps   xmm0, xmm0
0x18001604e  movups  [rbp+57h+var_90], xmm0
0x180016052  mov     r8d, esi
0x180016055  lea     rdx, [rbp+57h+var_90]
0x180016059  mov     rcx, r14
0x18001605c  call    ?LookupFid@Handler@p9fs@@AEAA?AV?$shared_ptr@VFid@p9fs@@@std@@I@Z; p9fs::Handler::LookupFid(uint)
0x180016061  nop
0x180016062  xorps   xmm0, xmm0
0x180016065  movups  [rbp+57h+var_50], xmm0
0x180016069  xorps   xmm1, xmm1
0x18001606c  movdqu  [rbp+57h+var_40], xmm1
0x180016071  mov     r8, qword ptr [rbp+57h+var_A0+8]
0x180016075  mov     rdx, qword ptr [rbp+57h+var_A0]
0x180016079  lea     rcx, [rbp+57h+var_50]
0x18001607d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180016082  nop
0x180016083  mov     r15, qword ptr [rbp+57h+var_90]
0x180016087  mov     rax, [r15]
0x18001608a  mov     [rsp+0D0h+var_B0], ebx; int
0x18001608e  mov     r9, rdi
0x180016091  lea     r8, [rbp+57h+var_50]
0x180016095  lea     rdx, [rbp+57h+var_68]
0x180016099  mov     rcx, r15
0x18001609c  mov     rax, [rax+0B8h]
0x1800160a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160a8  nop
0x1800160a9  cmp     [rbp+57h+var_68], 0
0x1800160ad  jnz     short loc_180016120
0x1800160af  mov     esi, dword ptr [rbp+57h+var_60]
0x1800160b2  lea     rcx, [rbp+57h+var_50]
0x1800160b6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800160bb  nop
0x1800160bc  mov     rbx, qword ptr [rbp+57h+var_90+8]
0x1800160c0  test    rbx, rbx
0x1800160c3  jz      short loc_1800160FB
0x1800160c5  or      edi, 0FFFFFFFFh
0x1800160c8  mov     eax, edi
0x1800160ca  lock xadd [rbx+8], eax
0x1800160cf  add     eax, edi
0x1800160d1  jnz     short loc_1800160FB
0x1800160d3  mov     rax, [rbx]
0x1800160d6  mov     rcx, rbx
0x1800160d9  mov     rax, [rax]
0x1800160dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160e1  mov     edx, edi
0x1800160e3  lock xadd [rbx+0Ch], edx
0x1800160e8  add     edx, edi
0x1800160ea  jnz     short loc_1800160FB
0x1800160ec  mov     rdx, [rbx]
0x1800160ef  mov     rcx, rbx
0x1800160f2  mov     rax, [rdx+8]
0x1800160f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160fb  mov     eax, esi
0x1800160fd  mov     rcx, [rbp+57h+var_30]
0x180016101  xor     rcx, rsp; StackCookie
0x180016104  call    __security_check_cookie
0x180016109  mov     rbx, [rsp+0D0h+arg_10]
0x180016111  add     rsp, 0B0h
0x180016118  pop     r15
0x18001611a  pop     r14
0x18001611c  pop     rdi
0x18001611d  pop     rsi
0x18001611e  pop     rbp
0x18001611f  retn
0x180016120  lea     rbx, [r14+20h]
0x180016124  mov     qword ptr [rbp+57h+var_A0], rbx
0x180016128  mov     rcx, rbx; _Smtx_t *
0x18001612b  call    _Smtx_lock_exclusive
0x180016130  nop
0x180016131  mov     r8, [r14+28h]
0x180016135  mov     rdx, [r8+8]
0x180016139  xor     eax, eax
0x18001613b  mov     [rbp+57h+var_74], eax
0x18001613e  mov     rcx, r8
0x180016141  cmp     [rdx+19h], al
0x180016144  jnz     short loc_18001615E
0x180016146  cmp     [rdx+20h], esi
0x180016149  cmovnb  rcx, rdx
0x18001614d  lea     rax, [rdx+10h]
0x180016151  cmovnb  rax, rdx
0x180016155  mov     rdx, [rax]
0x180016158  cmp     byte ptr [rdx+19h], 0
0x18001615c  jz      short loc_180016146
0x18001615e  cmp     byte ptr [rcx+19h], 0
0x180016162  jnz     short loc_18001617B
0x180016164  cmp     esi, [rcx+20h]
0x180016167  jb      short loc_18001617B
0x180016169  cmp     rcx, r8
0x18001616c  jz      short loc_18001617E
0x18001616e  lea     rdx, [rcx+28h]
0x180016172  cmp     [rdx], r15
0x180016175  jnz     short loc_18001617E
0x180016177  xor     al, al
0x180016179  jmp     short loc_180016184
0x18001617b  mov     rcx, r8
0x18001617e  mov     al, 1
0x180016180  lea     rdx, [rcx+28h]
0x180016184  mov     rcx, [rbp+5Fh]; this
0x180016188  test    al, al
0x18001618a  jnz     loc_1800162F1
0x180016190  cmp     [rbp+57h+var_68], al
0x180016193  setz    al
0x180016196  mov     rcx, [rbp+5Fh]; this
0x18001619a  test    al, al
0x18001619c  jnz     loc_180016297
0x1800161a2  mov     rcx, [rbp+57h+var_58]
0x1800161a6  test    rcx, rcx
0x1800161a9  jz      short loc_1800161B3
0x1800161ab  lock inc dword ptr [rcx+8]
0x1800161af  mov     rcx, [rbp+57h+var_58]
0x1800161b3  mov     rax, [rbp+57h+var_60]
0x1800161b7  mov     [rdx], rax
0x1800161ba  mov     rsi, [rdx+8]
0x1800161be  mov     [rdx+8], rcx
0x1800161c2  or      edi, 0FFFFFFFFh
0x1800161c5  test    rsi, rsi
0x1800161c8  jz      short loc_1800161FE
0x1800161ca  mov     eax, edi
0x1800161cc  lock xadd [rsi+8], eax
0x1800161d1  add     eax, edi
0x1800161d3  jnz     short loc_1800161FE
0x1800161d5  mov     rax, [rsi]
0x1800161d8  mov     rcx, rsi
0x1800161db  mov     rax, [rax]
0x1800161de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161e3  mov     eax, edi
0x1800161e5  lock xadd [rsi+0Ch], eax
0x1800161ea  add     eax, edi
0x1800161ec  jnz     short loc_1800161FE
0x1800161ee  mov     rax, [rsi]
0x1800161f1  mov     rcx, rsi
0x1800161f4  mov     rax, [rax+8]
0x1800161f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161fd  nop
0x1800161fe  mov     rcx, rbx; _Smtx_t *
0x180016201  call    _Smtx_unlock_exclusive
0x180016206  nop
0x180016207  cmp     [rbp+57h+var_68], 0
0x18001620b  jz      short loc_18001624A
0x18001620d  mov     rbx, [rbp+57h+var_58]
0x180016211  test    rbx, rbx
0x180016214  jz      short loc_18001624A
0x180016216  mov     eax, edi
0x180016218  lock xadd [rbx+8], eax
0x18001621d  add     eax, edi
0x18001621f  jnz     short loc_18001624A
0x180016221  mov     rax, [rbx]
0x180016224  mov     rcx, rbx
0x180016227  mov     rax, [rax]
0x18001622a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001622f  mov     eax, edi
0x180016231  lock xadd [rbx+0Ch], eax
0x180016236  add     eax, edi
0x180016238  jnz     short loc_18001624A
0x18001623a  mov     rax, [rbx]
0x18001623d  mov     rcx, rbx
0x180016240  mov     rax, [rax+8]
0x180016244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016249  nop
0x18001624a  lea     rcx, [rbp+57h+var_50]
0x18001624e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016253  nop
0x180016254  mov     rbx, qword ptr [rbp+57h+var_90+8]
0x180016258  test    rbx, rbx
0x18001625b  jz      short loc_180016290
0x18001625d  mov     eax, edi
0x18001625f  lock xadd [rbx+8], eax
0x180016264  add     eax, edi
0x180016266  jnz     short loc_180016290
0x180016268  mov     rax, [rbx]
0x18001626b  mov     rcx, rbx
0x18001626e  mov     rax, [rax]
0x180016271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016276  mov     eax, edi
0x180016278  lock xadd [rbx+0Ch], eax
0x18001627d  add     eax, edi
0x18001627f  jnz     short loc_180016290
0x180016281  mov     rax, [rbx]
0x180016284  mov     rcx, rbx
0x180016287  mov     rax, [rax+8]
0x18001628b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016290  xor     eax, eax
0x180016292  jmp     loc_1800160FD
0x180016297  lea     r8, aOnecoreVmIncEx; "onecore\\vm\\inc\\expected.h"
0x18001629e  mov     edx, 139h; void *
0x1800162a3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800162a9  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x1800162af  mov     rcx, [rbp+5Fh]; this
0x1800162b3  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x1800162ba  mov     edx, 29h ; ')'; void *
0x1800162bf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800162c5  mov     rcx, [rbp+5Fh]; this
0x1800162c9  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x1800162d0  mov     edx, 29h ; ')'; void *
0x1800162d5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800162db  mov     rcx, [rbp+5Fh]; this
0x1800162df  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x1800162e6  mov     edx, 29h ; ')'; void *
0x1800162eb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800162f1  mov     r9d, 8000FFFFh; char *
0x1800162f7  lea     r8, aOnecoreVmDvSto_6; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x1800162fe  mov     edx, 348h; void *
0x180016303  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
