# CStringMap::insert_or_assign(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)

- ea: `0x140019e3c`
- end: `0x14001a020`
- name: `?insert_or_assign@CStringMap@@QEAA?AU?$pair@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@utl@@_N@utl@@$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@V?$basic_string_view@_WU?$char_traits@_W@utl@@@3@@Z`
- size: `484`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400192b0`

## callees

- `0x140003224`
- `0x14000db44`
- `0x140018c4c`
- `0x140018d70`
- `0x140019e3c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140019eb1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140019f1e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140019eb1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140019f1e`

## pseudocode

```c
__int64 __fastcall CStringMap::insert_or_assign(__int64 a1, __int64 a2, __int64 *a3, _QWORD *a4)
{
  void ***v4; // rsi
  void ***v9; // rdi
  void **v10; // rbp
  __int64 v11; // r13
  unsigned __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // r8
  void **v20; // rdi
  _QWORD *v21; // rdi
  _QWORD *v22; // rcx
  __int64 v23; // rax
  _QWORD *v24; // rcx
  _QWORD *v25; // rcx
  __int64 v27; // [rsp+30h] [rbp-58h] BYREF
  void *v28; // [rsp+90h] [rbp+8h] BYREF

  v4 = (void ***)(a1 + 24);
  v9 = (void ***)(a1 + 24);
  if ( *(_QWORD *)(a1 + 40) != a1 + 24 )
  {
    v10 = *v4;
    v11 = 2;
    do
    {
      v12 = (unsigned __int64)v10[4];
      v13 = (a3[1] - *a3) >> 1;
      if ( (v12 | v13) > 0x7FFFFFFF )
        __int2c();
      v14 = 2;
      v15 = 2;
      if ( *a3 )
        v14 = *a3;
      if ( v10[3] )
        v15 = (__int64)v10[3];
      if ( CompareStringOrdinal((LPCWCH)v15, v12, (LPCWCH)v14, v13, 1) == 1 )
      {
        v16 = 2;
      }
      else
      {
        v9 = (void ***)v10;
        v16 = 1;
      }
      v10 = (void **)v10[v16];
    }
    while ( v10 != &utl::_TreeSentinel );
    if ( v9 != v4 )
    {
      v17 = (unsigned __int64)v9[4];
      v18 = (a3[1] - *a3) >> 1;
      if ( (v18 | v17) > 0x7FFFFFFF )
        __int2c();
      v19 = 2;
      if ( v9[3] )
        v19 = (__int64)v9[3];
      if ( *a3 )
        v11 = *a3;
      if ( CompareStringOrdinal((LPCWCH)v11, v18, (LPCWCH)v19, v17, 1) != 1 )
      {
        v20 = v9[5];
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                v20 + 6,
                                *a4,
                                a4[1]) )
        {
          *(_QWORD *)a2 = v20;
LABEL_32:
          *(_BYTE *)(a2 + 8) = 0;
          return a2;
        }
LABEL_31:
        *(_QWORD *)a2 = 0;
        goto LABEL_32;
      }
    }
  }
  if ( !(unsigned __int8)utl::list<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>::emplace_back<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,0>(
                           a1,
                           a3,
                           a4) )
    goto LABEL_31;
  v28 = *(void **)(a1 + 8);
  utl::_Tree<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>,0>::emplace_hint<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> const &,0>(
    (_DWORD)v4,
    (unsigned int)&v27,
    (_DWORD)v9,
    (_DWORD)v28 + 16,
    (__int64)&v28);
  if ( !v27 )
  {
    v21 = v28;
    v22 = (_QWORD *)*((_QWORD *)v28 + 1);
    v23 = *(_QWORD *)v28;
    *v22 = *(_QWORD *)v28;
    *(_QWORD *)(v23 + 8) = v22;
    v24 = (_QWORD *)v21[6];
    if ( v24 != v21 + 8 )
      operator delete(v24, (const struct std::nothrow_t *)&std::nothrow);
    v25 = (_QWORD *)v21[2];
    if ( v25 != v21 + 4 )
      operator delete(v25, (const struct std::nothrow_t *)&std::nothrow);
    operator delete(v21, (const struct std::nothrow_t *)&std::nothrow);
    --*(_QWORD *)(a1 + 16);
    goto LABEL_31;
  }
  *(_QWORD *)a2 = v28;
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x140019e3c  push    rbx
0x140019e3e  push    rbp
0x140019e3f  push    rsi
0x140019e40  push    rdi
0x140019e41  push    r12
0x140019e43  push    r13
0x140019e45  push    r14
0x140019e47  push    r15
0x140019e49  sub     rsp, 48h
0x140019e4d  lea     rsi, [rcx+18h]
0x140019e51  mov     r12, r9
0x140019e54  mov     r15, r8
0x140019e57  mov     rbx, rdx
0x140019e5a  mov     r14, rcx
0x140019e5d  mov     rdi, rsi
0x140019e60  cmp     [rsi+10h], rsi
0x140019e64  jz      loc_140019F4F
0x140019e6a  mov     rbp, [rsi]
0x140019e6d  mov     r13d, 2
0x140019e73  mov     r9, [r15+8]
0x140019e77  sub     r9, [r15]
0x140019e7a  mov     rdx, [rbp+20h]; cchCount1
0x140019e7e  sar     r9, 1; cchCount2
0x140019e81  mov     rax, r9
0x140019e84  or      rax, rdx
0x140019e87  cmp     rax, 7FFFFFFFh
0x140019e8d  jbe     short loc_140019E91
0x140019e8f  int     2Ch; Windows NT - assertion failure
0x140019e91  cmp     qword ptr [r15], 0
0x140019e95  mov     r8, r13
0x140019e98  mov     rcx, r13
0x140019e9b  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x140019ea3  cmovnz  r8, [r15]; lpString2
0x140019ea7  cmp     qword ptr [rbp+18h], 0
0x140019eac  cmovnz  rcx, [rbp+18h]; lpString1
0x140019eb1  call    cs:__imp_CompareStringOrdinal
0x140019eb7  cmp     eax, 1
0x140019eba  jnz     short loc_140019EC3
0x140019ebc  mov     eax, 10h
0x140019ec1  jmp     short loc_140019ECB
0x140019ec3  mov     rdi, rbp
0x140019ec6  mov     eax, 8
0x140019ecb  mov     rbp, [rax+rbp]
0x140019ecf  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140019ed6  cmp     rbp, rax
0x140019ed9  jnz     short loc_140019E73
0x140019edb  cmp     rdi, rsi
0x140019ede  jz      short loc_140019F4F
0x140019ee0  mov     rdx, [r15+8]
0x140019ee4  sub     rdx, [r15]
0x140019ee7  mov     r9, [rdi+20h]; cchCount2
0x140019eeb  sar     rdx, 1; cchCount1
0x140019eee  mov     rax, r9
0x140019ef1  or      rax, rdx
0x140019ef4  cmp     rax, 7FFFFFFFh
0x140019efa  jbe     short loc_140019EFE
0x140019efc  int     2Ch; Windows NT - assertion failure
0x140019efe  cmp     qword ptr [rdi+18h], 0
0x140019f03  mov     r8, r13
0x140019f06  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x140019f0e  cmovnz  r8, [rdi+18h]; lpString2
0x140019f13  cmp     qword ptr [r15], 0
0x140019f17  cmovnz  r13, [r15]
0x140019f1b  mov     rcx, r13; lpString1
0x140019f1e  call    cs:__imp_CompareStringOrdinal
0x140019f24  cmp     eax, 1
0x140019f27  jz      short loc_140019F4F
0x140019f29  mov     rdi, [rdi+28h]
0x140019f2d  mov     r8, [r12+8]
0x140019f32  mov     rdx, [r12]
0x140019f36  lea     rcx, [rdi+30h]
0x140019f3a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140019f3f  test    al, al
0x140019f41  jz      loc_14001A001
0x140019f47  mov     [rbx], rdi
0x140019f4a  jmp     loc_14001A008
0x140019f4f  mov     r8, r12
0x140019f52  mov     rdx, r15
0x140019f55  mov     rcx, r14
0x140019f58  call    ??$emplace_back@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@2@$0A@@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@2@@utl@@QEAA_N$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@1@@Z; utl::list<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>::emplace_back<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,0>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &)
0x140019f5d  test    al, al
0x140019f5f  jz      loc_14001A001
0x140019f65  mov     r9, [r14+8]
0x140019f69  lea     rax, [rsp+88h+arg_0]
0x140019f71  mov     [rsp+88h+arg_0], r9
0x140019f79  lea     rdx, [rsp+88h+var_58]
0x140019f7e  add     r9, 10h
0x140019f82  mov     qword ptr [rsp+88h+bIgnoreCase], rax
0x140019f87  mov     r8, rdi
0x140019f8a  mov     rcx, rsi
0x140019f8d  call    ??$emplace_hint@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBV?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@2@$0A@@?$_Tree@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@2@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@2@@utl@@@2@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@2@@utl@@@1@V?$_TreeConstIt@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@2@@utl@@@1@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@AEBV?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@1@@Z
0x140019f92  cmp     [rsp+88h+var_58], 0
0x140019f98  jz      short loc_140019FAB
0x140019f9a  mov     rax, [rsp+88h+arg_0]
0x140019fa2  mov     [rbx], rax
0x140019fa5  mov     byte ptr [rbx+8], 1
0x140019fa9  jmp     short loc_14001A00C
0x140019fab  mov     rdi, [rsp+88h+arg_0]
0x140019fb3  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140019fba  mov     rcx, [rdi+8]
0x140019fbe  mov     rax, [rdi]
0x140019fc1  mov     [rcx], rax
0x140019fc4  mov     [rax+8], rcx
0x140019fc8  lea     rax, [rdi+40h]
0x140019fcc  mov     rcx, [rdi+30h]; void *
0x140019fd0  cmp     rcx, rax
0x140019fd3  jz      short loc_140019FDD
0x140019fd5  mov     rdx, rsi; struct std::nothrow_t *
0x140019fd8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140019fdd  mov     rcx, [rdi+10h]; void *
0x140019fe1  lea     rax, [rdi+20h]
0x140019fe5  cmp     rcx, rax
0x140019fe8  jz      short loc_140019FF2
0x140019fea  mov     rdx, rsi; struct std::nothrow_t *
0x140019fed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140019ff2  mov     rdx, rsi; struct std::nothrow_t *
0x140019ff5  mov     rcx, rdi; void *
0x140019ff8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140019ffd  dec     qword ptr [r14+10h]
0x14001a001  mov     qword ptr [rbx], 0
0x14001a008  mov     byte ptr [rbx+8], 0
0x14001a00c  mov     rax, rbx
0x14001a00f  add     rsp, 48h
0x14001a013  pop     r15
0x14001a015  pop     r14
0x14001a017  pop     r13
0x14001a019  pop     r12
0x14001a01b  pop     rdi
0x14001a01c  pop     rsi
0x14001a01d  pop     rbp
0x14001a01e  pop     rbx
0x14001a01f  retn
```
