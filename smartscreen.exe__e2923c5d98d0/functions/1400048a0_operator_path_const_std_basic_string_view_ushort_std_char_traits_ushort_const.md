# operator/(path const &,std::basic_string_view<ushort,std::char_traits<ushort>> const &)

- ea: `0x1400048a0`
- end: `0x140004aea`
- name: `??K@YA?AVpath@@AEBV0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003cd8`

## callees

- `0x1400048a0`
- `0x140004af0`
- `0x140005260`
- `0x140013780`
- `0x14001609c`
- `0x1400160f0`
- `0x140017f68`
- `0x140018b58`
- `0x14001bbf0`
- `0x140025aa0`
- `0x140025f04`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x140004963`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x140004963`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004ac5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004ac5`
- `ext-ms-win-shell32-shellfolders-l1-1-0!PathCleanupSpec` at `0x140004933`
- `ext-ms-win-shell32-shellfolders-l1-1-0!PathCleanupSpec` at `0x140004933`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall operator/(__int64 a1, const WCHAR *a2, unsigned __int64 *a3)
{
  unsigned __int64 v5; // rcx
  __int64 v6; // rdx
  HRESULT v7; // eax
  __int64 v8; // r8
  PWSTR v9; // rcx
  const struct std::nothrow_t *v10; // rdx
  __int128 *v12; // rdx
  int v13; // [rsp+20h] [rbp-29h] BYREF
  void *v14; // [rsp+28h] [rbp-21h] BYREF
  unsigned __int64 v15; // [rsp+30h] [rbp-19h] BYREF
  __int128 v16; // [rsp+38h] [rbp-11h] BYREF
  __int64 v17; // [rsp+48h] [rbp-1h]
  unsigned __int64 v18; // [rsp+50h] [rbp+7h]
  __int64 v19; // [rsp+60h] [rbp+17h]
  PWSTR ppszPathOut; // [rsp+68h] [rbp+1Fh] BYREF
  PWSTR pszSpec[2]; // [rsp+70h] [rbp+27h] BYREF
  WCHAR *v22; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v19 = a1;
  v5 = *a3;
  v6 = 2 * a3[1];
  *(_OWORD *)pszSpec = 0;
  v22 = 0;
  v15 = v5;
  v14 = (void *)(v6 + v5);
  std::vector<unsigned short>::_Construct_n<unsigned short const *,unsigned short const *>(pszSpec, v6 >> 1, &v15, &v14);
  LOWORD(v13) = 0;
  if ( pszSpec[1] == v22 )
    std::vector<unsigned short>::_Emplace_reallocate<unsigned short>(pszSpec, pszSpec[1], &v13);
  else
    *pszSpec[1]++ = 0;
  if ( PathCleanupSpec(0, pszSpec[0]) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17F,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
      (const char *)0x80070057LL,
      v13);
  ppszPathOut = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  v7 = PathAllocCombine(a2, pszSpec[0], 1u, &ppszPathOut);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
      (const char *)(unsigned int)v7,
      v13);
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v8 = -1;
  do
    ++v8;
  while ( ppszPathOut[v8] );
  std::wstring::_Construct<1,unsigned short const *>(&v16, ppszPathOut, v8);
  v14 = &v16;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct_empty(a1);
  if ( (__int128 *)a1 != &v16 )
  {
    v12 = &v16;
    if ( v18 > 7 )
      v12 = (__int128 *)v16;
    std::wstring::assign(a1, v12, v17);
  }
  if ( v18 > 7 )
    std::_Deallocate<16>(v16, 2 * v18 + 2);
  v17 = 0;
  v18 = 7;
  LOWORD(v16) = 0;
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  v9 = pszSpec[0];
  if ( pszSpec[0] )
  {
    v10 = (const struct std::nothrow_t *)(2 * (v22 - pszSpec[0]));
    v15 = (unsigned __int64)v10;
    v14 = pszSpec[0];
    if ( (unsigned __int64)v10 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v14, &v15);
      v10 = (const struct std::nothrow_t *)v15;
      v9 = (PWSTR)v14;
    }
    operator delete(v9, v10);
  }
  return a1;
}

```

## disassembly

```asm
0x1400048a0  mov     [rsp-8+arg_10], rbx
0x1400048a5  mov     [rsp-8+arg_18], rsi
0x1400048aa  push    rbp
0x1400048ab  push    rdi
0x1400048ac  push    r14
0x1400048ae  lea     rbp, [rsp-47h]
0x1400048b3  sub     rsp, 90h
0x1400048ba  mov     rax, cs:__security_cookie
0x1400048c1  xor     rax, rsp
0x1400048c4  mov     [rbp+57h+var_18], rax
0x1400048c8  mov     rbx, rdx
0x1400048cb  mov     rdi, rcx
0x1400048ce  mov     [rbp+57h+var_40], rcx
0x1400048d2  xor     r14d, r14d
0x1400048d5  mov     rcx, [r8]
0x1400048d8  mov     rax, [r8+8]
0x1400048dc  lea     rdx, [rax+rax]
0x1400048e0  xorps   xmm0, xmm0
0x1400048e3  movdqu  xmmword ptr [rbp+57h+pszSpec], xmm0
0x1400048e8  mov     [rbp+57h+var_20], r14
0x1400048ec  mov     [rbp+57h+var_70], rcx
0x1400048f0  lea     rax, [rdx+rcx]
0x1400048f4  mov     [rbp+57h+var_78], rax
0x1400048f8  sar     rdx, 1
0x1400048fb  lea     r9, [rbp+57h+var_78]
0x1400048ff  lea     r8, [rbp+57h+var_70]
0x140004903  lea     rcx, [rbp+57h+pszSpec]
0x140004907  call    ??$_Construct_n@PEBGPEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K$$QEAPEBG1@Z; std::vector<ushort>::_Construct_n<ushort const *,ushort const *>(unsigned __int64,ushort const * &&,ushort const * &&)
0x14000490c  nop
0x14000490d  mov     word ptr [rbp+57h+var_80], r14w
0x140004912  mov     rdx, [rbp+57h+pszSpec+8]
0x140004916  cmp     rdx, [rbp+57h+var_20]
0x14000491a  jz      loc_140004A63
0x140004920  mov     [rdx], r14w
0x140004924  add     [rbp+57h+pszSpec+8], 2
0x140004929  mov     rsi, [rbp+5Fh]
0x14000492d  mov     rdx, [rbp+57h+pszSpec]; pszSpec
0x140004931  xor     ecx, ecx; pszDir
0x140004933  call    cs:__imp_PathCleanupSpec
0x140004939  shr     eax, 1Fh
0x14000493c  test    al, al
0x14000493e  jnz     loc_140004A75
0x140004944  mov     [rbp+57h+ppszPathOut], r14
0x140004948  cmp     qword ptr [rbx+18h], 7
0x14000494d  jbe     short loc_140004952
0x14000494f  mov     rbx, [rbx]
0x140004952  lea     r9, [rbp+57h+ppszPathOut]; ppszPathOut
0x140004956  mov     r8d, 1; dwFlags
0x14000495c  mov     rdx, [rbp+57h+pszSpec]; pszMore
0x140004960  mov     rcx, rbx; pszPathIn
0x140004963  call    cs:__imp_PathAllocCombine
0x140004969  mov     rcx, [rbp+5Fh]; this
0x14000496d  test    eax, eax
0x14000496f  jns     short loc_140004986
0x140004971  mov     r9d, eax; char *
0x140004974  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x14000497b  mov     edx, 182h; void *
0x140004980  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140004986  mov     rdx, [rbp+57h+ppszPathOut]
0x14000498a  xorps   xmm0, xmm0
0x14000498d  movups  [rbp+57h+var_68], xmm0
0x140004991  mov     [rbp+57h+var_58], r14
0x140004995  mov     [rbp+57h+var_50], r14
0x140004999  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1400049a0  inc     r8
0x1400049a3  cmp     word ptr [rdx+r8*2], 0
0x1400049a9  jnz     short loc_1400049A0
0x1400049ab  lea     rcx, [rbp+57h+var_68]
0x1400049af  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400049b4  lea     rax, [rbp+57h+var_68]
0x1400049b8  mov     [rbp+57h+var_78], rax
0x1400049bc  xorps   xmm0, xmm0
0x1400049bf  movups  xmmword ptr [rdi], xmm0
0x1400049c2  mov     [rdi+10h], r14
0x1400049c6  mov     [rdi+18h], r14
0x1400049ca  mov     rcx, rdi
0x1400049cd  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1400049d2  nop
0x1400049d3  lea     rax, [rbp+57h+var_68]
0x1400049d7  cmp     rdi, rax
0x1400049da  jnz     loc_140004A90
0x1400049e0  mov     rdx, [rbp+57h+var_50]
0x1400049e4  cmp     rdx, 7
0x1400049e8  ja      loc_140004AAF
0x1400049ee  mov     [rbp+57h+var_58], r14
0x1400049f2  mov     [rbp+57h+var_50], 7
0x1400049fa  mov     word ptr [rbp+57h+var_68], r14w
0x1400049ff  mov     rcx, [rbp+57h+ppszPathOut]; hMem
0x140004a03  test    rcx, rcx
0x140004a06  jnz     loc_140004AC5
0x140004a0c  mov     rcx, [rbp+57h+pszSpec]; void *
0x140004a10  test    rcx, rcx
0x140004a13  jz      short loc_140004A3C
0x140004a15  mov     rdx, [rbp+57h+var_20]
0x140004a19  sub     rdx, rcx
0x140004a1c  sar     rdx, 1
0x140004a1f  add     rdx, rdx; struct std::nothrow_t *
0x140004a22  mov     [rbp+57h+var_70], rdx
0x140004a26  mov     [rbp+57h+var_78], rcx
0x140004a2a  cmp     rdx, 1000h
0x140004a31  jnb     loc_140004AD0
0x140004a37  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140004a3c  mov     rax, rdi
0x140004a3f  mov     rcx, [rbp+57h+var_18]
0x140004a43  xor     rcx, rsp; StackCookie
0x140004a46  call    __security_check_cookie
0x140004a4b  lea     r11, [rsp+0A0h+var_10]
0x140004a53  mov     rbx, [r11+30h]
0x140004a57  mov     rsi, [r11+38h]
0x140004a5b  mov     rsp, r11
0x140004a5e  pop     r14
0x140004a60  pop     rdi
0x140004a61  pop     rbp
0x140004a62  retn
0x140004a63  lea     r8, [rbp+57h+var_80]
0x140004a67  lea     rcx, [rbp+57h+pszSpec]
0x140004a6b  call    ??$_Emplace_reallocate@G@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAG$$QEAG@Z; std::vector<ushort>::_Emplace_reallocate<ushort>(ushort * const,ushort &&)
0x140004a70  jmp     loc_140004929
0x140004a75  mov     r9d, 80070057h; char *
0x140004a7b  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140004a82  mov     edx, 17Fh; void *
0x140004a87  mov     rcx, rsi; this
0x140004a8a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140004a90  lea     rdx, [rbp+57h+var_68]
0x140004a94  cmp     [rbp+57h+var_50], 7
0x140004a99  cmova   rdx, qword ptr [rbp+57h+var_68]
0x140004a9e  mov     r8, [rbp+57h+var_58]
0x140004aa2  mov     rcx, rdi
0x140004aa5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x140004aaa  jmp     loc_1400049E0
0x140004aaf  lea     rdx, ds:2[rdx*2]
0x140004ab7  mov     rcx, qword ptr [rbp+57h+var_68]
0x140004abb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140004ac0  jmp     loc_1400049EE
0x140004ac5  call    cs:__imp_LocalFree
0x140004acb  jmp     loc_140004A0C
0x140004ad0  lea     rdx, [rbp+57h+var_70]; unsigned __int64 *
0x140004ad4  lea     rcx, [rbp+57h+var_78]; void **
0x140004ad8  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x140004add  mov     rdx, [rbp+57h+var_70]
0x140004ae1  mov     rcx, [rbp+57h+var_78]
0x140004ae5  jmp     loc_140004A37
```
