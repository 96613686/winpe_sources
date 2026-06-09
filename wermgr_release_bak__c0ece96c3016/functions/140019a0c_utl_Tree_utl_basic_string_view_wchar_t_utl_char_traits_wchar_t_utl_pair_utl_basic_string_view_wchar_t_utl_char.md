# utl::_Tree<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>,0>::_FindInsertionPointUniqueUpper(utl::_TreeNode<utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>> * &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)

- ea: `0x140019a0c`
- end: `0x140019b01`
- name: `?_FindInsertionPointUniqueUpper@?$_Tree@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@2@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@2@@utl@@@2@$0A@@utl@@AEAA?AU?$pair@PEAU?$_TreeNode@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@2@@utl@@@utl@@_N@2@AEAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@2@@utl@@@2@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140018d70`
- `0x140019828`

## callees

- `0x140019a0c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140019a72`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140019ae1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140019a72`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140019ae1`

## pseudocode

```c
__int64 __fastcall utl::_Tree<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>,0>::_FindInsertionPointUniqueUpper(
        __int64 *a1,
        __int64 a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 v4; // rbx
  __int64 v8; // rbp
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rcx
  unsigned __int8 v13; // al
  __int64 v14; // rax
  unsigned __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // r8

  v4 = *a1;
  *(_QWORD *)a2 = 0;
  *(_BYTE *)(a2 + 8) = 0;
  *a3 = 0;
  v8 = 2;
  do
  {
    v9 = *(_QWORD *)(v4 + 32);
    v10 = a4[1];
    if ( (v10 | v9) > 0x7FFFFFFF )
      __int2c();
    v11 = 2;
    v12 = 2;
    if ( *(_QWORD *)(v4 + 24) )
      v11 = *(_QWORD *)(v4 + 24);
    if ( *a4 )
      v12 = *a4;
    if ( CompareStringOrdinal((LPCWCH)v12, v10, (LPCWCH)v11, v9, 1) == 1 )
    {
      v13 = 0;
    }
    else
    {
      v13 = 1;
      *a3 = v4;
    }
    *(_BYTE *)(a2 + 8) = v13;
    *(_QWORD *)a2 = v4;
    v4 = *(_QWORD *)(v4 + 8LL * v13 + 8);
  }
  while ( (void **)v4 != &utl::_TreeSentinel );
  v14 = *a3;
  if ( *a3 )
  {
    v15 = *(_QWORD *)(v14 + 32);
    v16 = a4[1];
    if ( (v16 | v15) > 0x7FFFFFFF )
      __int2c();
    v17 = 2;
    if ( *a4 )
      v17 = *a4;
    if ( *(_QWORD *)(v14 + 24) )
      v8 = *(_QWORD *)(v14 + 24);
    if ( CompareStringOrdinal((LPCWCH)v8, v15, (LPCWCH)v17, v16, 1) == 1 )
      *a3 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x140019a0c  push    rbx
0x140019a0e  push    rbp
0x140019a0f  push    rsi
0x140019a10  push    rdi
0x140019a11  push    r14
0x140019a13  sub     rsp, 30h
0x140019a17  mov     rbx, [rcx]
0x140019a1a  mov     r14, r9
0x140019a1d  mov     rsi, r8
0x140019a20  mov     qword ptr [rdx], 0
0x140019a27  mov     rdi, rdx
0x140019a2a  mov     byte ptr [rdx+8], 0
0x140019a2e  mov     qword ptr [r8], 0
0x140019a35  mov     ebp, 2
0x140019a3a  mov     r9, [rbx+20h]; cchCount2
0x140019a3e  mov     rdx, [r14+8]; cchCount1
0x140019a42  mov     rax, r9
0x140019a45  or      rax, rdx
0x140019a48  cmp     rax, 7FFFFFFFh
0x140019a4e  jbe     short loc_140019A52
0x140019a50  int     2Ch; Windows NT - assertion failure
0x140019a52  cmp     qword ptr [rbx+18h], 0
0x140019a57  mov     r8, rbp
0x140019a5a  mov     rcx, rbp
0x140019a5d  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x140019a65  cmovnz  r8, [rbx+18h]; lpString2
0x140019a6a  cmp     qword ptr [r14], 0
0x140019a6e  cmovnz  rcx, [r14]; lpString1
0x140019a72  call    cs:__imp_CompareStringOrdinal
0x140019a78  cmp     eax, 1
0x140019a7b  jnz     short loc_140019A81
0x140019a7d  xor     al, al
0x140019a7f  jmp     short loc_140019A86
0x140019a81  mov     al, 1
0x140019a83  mov     [rsi], rbx
0x140019a86  mov     [rdi+8], al
0x140019a89  movzx   eax, al
0x140019a8c  mov     [rdi], rbx
0x140019a8f  mov     rbx, [rbx+rax*8+8]
0x140019a94  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140019a9b  cmp     rbx, rax
0x140019a9e  jnz     short loc_140019A3A
0x140019aa0  mov     rax, [rsi]
0x140019aa3  test    rax, rax
0x140019aa6  jz      short loc_140019AF3
0x140019aa8  mov     rdx, [rax+20h]; cchCount1
0x140019aac  mov     rcx, [rax+18h]
0x140019ab0  mov     rax, rdx
0x140019ab3  mov     r9, [r14+8]; cchCount2
0x140019ab7  or      rax, r9
0x140019aba  cmp     rax, 7FFFFFFFh
0x140019ac0  jbe     short loc_140019AC4
0x140019ac2  int     2Ch; Windows NT - assertion failure
0x140019ac4  cmp     qword ptr [r14], 0
0x140019ac8  mov     r8, rbp
0x140019acb  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x140019ad3  cmovnz  r8, [r14]; lpString2
0x140019ad7  test    rcx, rcx
0x140019ada  cmovnz  rbp, rcx
0x140019ade  mov     rcx, rbp; lpString1
0x140019ae1  call    cs:__imp_CompareStringOrdinal
0x140019ae7  cmp     eax, 1
0x140019aea  jnz     short loc_140019AF3
0x140019aec  mov     qword ptr [rsi], 0
0x140019af3  mov     rax, rdi
0x140019af6  add     rsp, 30h
0x140019afa  pop     r14
0x140019afc  pop     rdi
0x140019afd  pop     rsi
0x140019afe  pop     rbp
0x140019aff  pop     rbx
0x140019b00  retn
```
