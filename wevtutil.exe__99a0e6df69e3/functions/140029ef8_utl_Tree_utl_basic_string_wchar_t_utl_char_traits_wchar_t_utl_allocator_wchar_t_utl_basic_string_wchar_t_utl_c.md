# utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_LowerBoundNonEmpty<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> const &)

- ea: `0x140029ef8`
- end: `0x140029f91`
- name: `??$_LowerBoundNonEmpty@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@Uistring_less_ordinal@tlx@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@AEBV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001e02c`

## callees

- `0x140029ef8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140029f54`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140029f54`

## pseudocode

```c
void **__fastcall utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_LowerBoundNonEmpty<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(
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
0x140029ef8  mov     [rsp+arg_0], rbx
0x140029efd  mov     [rsp+arg_8], rsi
0x140029f02  push    rdi
0x140029f03  sub     rsp, 30h
0x140029f07  mov     rbx, [rcx]
0x140029f0a  mov     rsi, rdx
0x140029f0d  mov     rdi, rcx
0x140029f10  mov     r10, [rbx+18h]
0x140029f14  mov     rdx, [rbx+20h]
0x140029f18  mov     r9, [rsi+8]; cchCount2
0x140029f1c  sub     rdx, r10
0x140029f1f  sar     rdx, 1; cchCount1
0x140029f22  mov     rax, r9
0x140029f25  or      rax, rdx
0x140029f28  cmp     rax, 7FFFFFFFh
0x140029f2e  jbe     short loc_140029F32
0x140029f30  int     2Ch; Windows NT - assertion failure
0x140029f32  cmp     qword ptr [rsi], 0
0x140029f36  mov     r8d, 2
0x140029f3c  mov     ecx, 2
0x140029f41  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x140029f49  cmovnz  r8, [rsi]; lpString2
0x140029f4d  test    r10, r10
0x140029f50  cmovnz  rcx, r10; lpString1
0x140029f54  call    cs:__imp_CompareStringOrdinal
0x140029f5a  cmp     eax, 1
0x140029f5d  jnz     short loc_140029F66
0x140029f5f  mov     eax, 10h
0x140029f64  jmp     short loc_140029F6E
0x140029f66  mov     rdi, rbx
0x140029f69  mov     eax, 8
0x140029f6e  mov     rbx, [rax+rbx]
0x140029f72  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140029f79  cmp     rbx, rax
0x140029f7c  jnz     short loc_140029F10
0x140029f7e  mov     rbx, [rsp+38h+arg_0]
0x140029f83  mov     rax, rdi
0x140029f86  mov     rsi, [rsp+38h+arg_8]
0x140029f8b  add     rsp, 30h
0x140029f8f  pop     rdi
0x140029f90  retn
```
