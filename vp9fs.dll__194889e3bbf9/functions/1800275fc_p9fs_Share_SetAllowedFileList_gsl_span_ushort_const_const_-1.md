# p9fs::Share::SetAllowedFileList(gsl::span<ushort const * const,-1>)

- ea: `0x1800275fc`
- end: `0x1800277e0`
- name: `?SetAllowedFileList@Share@p9fs@@QEAAXV?$span@QEBG$0?0@gsl@@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800277f0`

## callees

- `0x180004120`
- `0x180004144`
- `0x18000c880`
- `0x18001c75c`
- `0x18001c794`
- `0x18001c93c`
- `0x18001ce4c`
- `0x1800275fc`
- `0x180028768`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002778a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002778a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027741`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027741`

## string_xrefs

- `0x1800277c8`: `onecore\vm\dv\storage\plan9\dll\windows\p9file.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall p9fs::Share::SetAllowedFileList(__int64 a1, _QWORD *a2)
{
  __int64 *v3; // rsi
  __int64 v4; // r15
  __int64 *v5; // r12
  unsigned __int64 v6; // rbx
  size_t v7; // rbx
  _QWORD *v8; // rdi
  void *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 *v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rdx
  char *v15; // rdx
  int v17; // [rsp+20h] [rbp-48h]
  __int128 v18; // [rsp+40h] [rbp-28h] BYREF
  char *v19; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  if ( *(char *)(a1 + 8) >= 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9file.h",
      (const char *)0x80070057LL,
      v17);
  v3 = (__int64 *)a2[1];
  v4 = 8LL * *a2;
  v5 = &v3[(unsigned __int64)v4 / 8];
  v18 = 0;
  v19 = 0;
  if ( v3 > &v3[(unsigned __int64)v4 / 8] )
    gsl::details::terminate(retaddr);
  v6 = v4 >> 3;
  if ( v4 >> 3 )
  {
    if ( v6 > 0x7FFFFFFFFFFFFFFLL )
      std::vector<std::basic_string_view<unsigned short>>::_Xlength(retaddr);
    v7 = 32 * v6;
    if ( v7 )
    {
      if ( v7 < 0x1000 )
      {
        v8 = operator new(v7);
      }
      else
      {
        if ( v7 + 39 < v7 )
          __scrt_throw_std_bad_array_new_length();
        v9 = operator new(v7 + 39);
        if ( !v9 )
          __fastfail(5u);
        v8 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v8 - 1) = v9;
      }
    }
    else
    {
      v8 = 0;
    }
    *(_QWORD *)&v18 = v8;
    *((_QWORD *)&v18 + 1) = v8;
    v19 = (char *)&v8[v7 / 8];
    if ( v4 )
    {
      do
      {
        v10 = *v3;
        *(_OWORD *)v8 = 0;
        v8[2] = 0;
        v8[3] = 0;
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)(v10 + 2 * v11) );
        std::wstring::_Construct<1,unsigned short const *>(v8, v10, v11);
        v8 += 4;
        ++v3;
      }
      while ( v3 != v5 );
    }
    *((_QWORD *)&v18 + 1) = v8;
  }
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
  v12 = (__int64 *)(a1 + 24);
  if ( (__int128 *)(a1 + 24) != &v18 )
  {
    v13 = *v12;
    *v12 = v18;
    *(_QWORD *)&v18 = v13;
    v14 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = *((_QWORD *)&v18 + 1);
    *((_QWORD *)&v18 + 1) = v14;
    v15 = *(char **)(a1 + 40);
    *(_QWORD *)(a1 + 40) = v19;
    v19 = v15;
  }
  if ( a1 != -16 )
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 16));
  return std::vector<std::wstring>::_Tidy(&v18);
}

```

## disassembly

```asm
0x1800275fc  push    rbp
0x1800275fe  push    rbx
0x1800275ff  push    rsi
0x180027600  push    rdi
0x180027601  push    r12
0x180027603  push    r13
0x180027605  push    r14
0x180027607  push    r15
0x180027609  mov     rbp, rsp
0x18002760c  sub     rsp, 68h
0x180027610  mov     rax, cs:__security_cookie
0x180027617  xor     rax, rsp
0x18002761a  mov     [rbp+var_10], rax
0x18002761e  mov     r14, rcx
0x180027621  mov     rcx, [rbp+40h]; this
0x180027625  test    byte ptr [r14+8], 80h
0x18002762a  jz      loc_1800277C2
0x180027630  mov     rsi, [rdx+8]
0x180027634  mov     rax, [rdx]
0x180027637  lea     r15, ds:0[rax*8]
0x18002763f  lea     r12, [r15+rsi]
0x180027643  xorps   xmm0, xmm0
0x180027646  movdqu  [rbp+var_28], xmm0
0x18002764b  xor     r13d, r13d
0x18002764e  mov     [rbp+var_18], r13
0x180027652  cmp     rsi, r12
0x180027655  ja      loc_1800277BC
0x18002765b  mov     rbx, r15
0x18002765e  sar     rbx, 3
0x180027662  test    rbx, rbx
0x180027665  jz      loc_18002773A
0x18002766b  mov     rax, 7FFFFFFFFFFFFFFh
0x180027675  cmp     rbx, rax
0x180027678  ja      loc_1800277DA
0x18002767e  shl     rbx, 5
0x180027682  test    rbx, rbx
0x180027685  jnz     short loc_18002768C
0x180027687  mov     edi, r13d
0x18002768a  jmp     short loc_1800276CA
0x18002768c  cmp     rbx, 1000h
0x180027693  jb      short loc_1800276BF
0x180027695  lea     rcx, [rbx+27h]; Size
0x180027699  cmp     rcx, rbx
0x18002769c  jbe     loc_1800277B6
0x1800276a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800276a7  test    rax, rax
0x1800276aa  jnz     short loc_1800276B1
0x1800276ac  lea     ecx, [rax+5]
0x1800276af  int     29h; Win8: RtlFailFast(ecx)
0x1800276b1  lea     rdi, [rax+27h]
0x1800276b5  and     rdi, 0FFFFFFFFFFFFFFE0h
0x1800276b9  mov     [rdi-8], rax
0x1800276bd  jmp     short loc_1800276CA
0x1800276bf  mov     rcx, rbx; Size
0x1800276c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800276c7  mov     rdi, rax
0x1800276ca  mov     qword ptr [rbp+var_28], rdi
0x1800276ce  mov     qword ptr [rbp+var_28+8], rdi
0x1800276d2  lea     rcx, [rbx+rdi]
0x1800276d6  mov     [rbp+var_18], rcx
0x1800276da  lea     rax, [rbp+var_28]
0x1800276de  mov     [rbp+var_30], rax
0x1800276e2  xorps   xmm0, xmm0
0x1800276e5  movups  [rbp+var_48], xmm0
0x1800276e9  mov     qword ptr [rbp+var_48], rdi
0x1800276ed  mov     qword ptr [rbp+var_48+8], rdi
0x1800276f1  lea     rax, [rbp+var_28]
0x1800276f5  mov     [rbp+var_38], rax
0x1800276f9  test    r15, r15
0x1800276fc  jz      short loc_180027736
0x1800276fe  mov     rdx, [rsi]
0x180027701  xorps   xmm0, xmm0
0x180027704  movups  xmmword ptr [rdi], xmm0
0x180027707  mov     [rdi+10h], r13
0x18002770b  mov     [rdi+18h], r13
0x18002770f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027713  inc     r8
0x180027716  cmp     [rdx+r8*2], r13w
0x18002771b  jnz     short loc_180027713
0x18002771d  mov     rcx, rdi
0x180027720  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027725  add     rdi, 20h ; ' '
0x180027729  mov     qword ptr [rbp+var_48+8], rdi
0x18002772d  add     rsi, 8
0x180027731  cmp     rsi, r12
0x180027734  jnz     short loc_1800276FE
0x180027736  mov     qword ptr [rbp+var_28+8], rdi
0x18002773a  lea     rbx, [r14+10h]
0x18002773e  mov     rcx, rbx; SRWLock
0x180027741  call    cs:__imp_AcquireSRWLockExclusive
0x180027747  lea     r8, [r14+18h]
0x18002774b  lea     rax, [rbp+var_28]
0x18002774f  cmp     r8, rax
0x180027752  jz      short loc_180027782
0x180027754  mov     rcx, [r8]
0x180027757  mov     rax, qword ptr [rbp+var_28]
0x18002775b  mov     [r8], rax
0x18002775e  mov     qword ptr [rbp+var_28], rcx
0x180027762  mov     rdx, [r8+8]
0x180027766  mov     rax, qword ptr [rbp+var_28+8]
0x18002776a  mov     [r8+8], rax
0x18002776e  mov     qword ptr [rbp+var_28+8], rdx
0x180027772  mov     rdx, [r8+10h]
0x180027776  mov     rax, [rbp+var_18]
0x18002777a  mov     [r8+10h], rax
0x18002777e  mov     [rbp+var_18], rdx
0x180027782  test    rbx, rbx
0x180027785  jz      short loc_180027790
0x180027787  mov     rcx, rbx; SRWLock
0x18002778a  call    cs:__imp_ReleaseSRWLockExclusive
0x180027790  lea     rcx, [rbp+var_28]
0x180027794  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180027799  mov     rcx, [rbp+var_10]
0x18002779d  xor     rcx, rsp; StackCookie
0x1800277a0  call    __security_check_cookie
0x1800277a5  add     rsp, 68h
0x1800277a9  pop     r15
0x1800277ab  pop     r14
0x1800277ad  pop     r13
0x1800277af  pop     r12
0x1800277b1  pop     rdi
0x1800277b2  pop     rsi
0x1800277b3  pop     rbx
0x1800277b4  pop     rbp
0x1800277b5  retn
0x1800277b6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x1800277bc  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x1800277c2  mov     r9d, 80070057h; char *
0x1800277c8  lea     r8, aOnecoreVmDvSto_12; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x1800277cf  mov     edx, 20h ; ' '; void *
0x1800277d4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800277da  call    ?_Xlength@?$vector@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@2@@std@@CAXXZ; std::vector<std::basic_string_view<ushort>>::_Xlength(void)
```
