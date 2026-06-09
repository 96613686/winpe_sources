# utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>>,0>::_LowerBoundNonEmpty<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)

- ea: `0x18003608c`
- end: `0x180036125`
- name: `??$_LowerBoundNonEmpty@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U_PublisherRecord@LocalePublisherTable@@@utl@@@1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@1@@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180037500`

## callees

- `0x18003608c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800360e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800360e8`

## pseudocode

```c
void **__fastcall utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,LocalePublisherTable::_PublisherRecord>>,0>::_LowerBoundNonEmpty<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(
        void ***a1,
        __int64 *a2)
{
  void **v2; // rbx
  void **v4; // rdi
  _BYTE *v5; // r10
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rax

  v2 = *a1;
  v4 = (void **)a1;
  do
  {
    v5 = v2[3];
    v6 = a2[1];
    v7 = ((_BYTE *)v2[4] - v5) >> 1;
    if ( (v7 | (unsigned __int64)v6) > 0x7FFFFFFF )
      __int2c();
    v8 = 2;
    v9 = 2;
    if ( *a2 )
      v8 = *a2;
    if ( v5 )
      v9 = (__int64)v2[3];
    if ( CompareStringOrdinal((LPCWCH)v9, v7, (LPCWCH)v8, v6, 1) == 1 )
    {
      v10 = 2;
    }
    else
    {
      v4 = v2;
      v10 = 1;
    }
    v2 = (void **)v2[v10];
  }
  while ( v2 != &utl::_TreeSentinel );
  return v4;
}

```

## disassembly

```asm
0x18003608c  mov     [rsp+arg_0], rbx
0x180036091  mov     [rsp+arg_8], rsi
0x180036096  push    rdi
0x180036097  sub     rsp, 30h
0x18003609b  mov     rbx, [rcx]
0x18003609e  mov     rsi, rdx
0x1800360a1  mov     rdi, rcx
0x1800360a4  mov     r10, [rbx+18h]
0x1800360a8  mov     rdx, [rbx+20h]
0x1800360ac  mov     r9, [rsi+8]; cchCount2
0x1800360b0  sub     rdx, r10
0x1800360b3  sar     rdx, 1; cchCount1
0x1800360b6  mov     rax, r9
0x1800360b9  or      rax, rdx
0x1800360bc  cmp     rax, 7FFFFFFFh
0x1800360c2  jbe     short loc_1800360C6
0x1800360c4  int     2Ch; Windows NT - assertion failure
0x1800360c6  cmp     qword ptr [rsi], 0
0x1800360ca  mov     r8d, 2
0x1800360d0  mov     ecx, 2
0x1800360d5  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800360dd  cmovnz  r8, [rsi]; lpString2
0x1800360e1  test    r10, r10
0x1800360e4  cmovnz  rcx, r10; lpString1
0x1800360e8  call    cs:__imp_CompareStringOrdinal
0x1800360ee  cmp     eax, 1
0x1800360f1  jnz     short loc_1800360FA
0x1800360f3  mov     eax, 10h
0x1800360f8  jmp     short loc_180036102
0x1800360fa  mov     rdi, rbx
0x1800360fd  mov     eax, 8
0x180036102  mov     rbx, [rax+rbx]
0x180036106  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18003610d  cmp     rbx, rax
0x180036110  jnz     short loc_1800360A4
0x180036112  mov     rbx, [rsp+38h+arg_0]
0x180036117  mov     rax, rdi
0x18003611a  mov     rsi, [rsp+38h+arg_8]
0x18003611f  add     rsp, 30h
0x180036123  pop     rdi
0x180036124  retn
```
