# utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_LowerBoundNonEmpty<wchar_t const *>(wchar_t const * const &)

- ea: `0x180035fec`
- end: `0x180036086`
- name: `??$_LowerBoundNonEmpty@PEB_W@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@1@AEBQEB_W@Z`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180035f48`

## callees

- `0x180035fec`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036050`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036050`

## pseudocode

```c
void **__fastcall utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_LowerBoundNonEmpty<wchar_t const *>(
        void ***a1,
        __int64 *a2)
{
  void **v2; // rbx
  void **v4; // rdi
  _BYTE *v5; // r10
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rax

  v2 = *a1;
  v4 = (void **)a1;
  do
  {
    v5 = v2[3];
    v6 = *a2;
    v7 = ((_BYTE *)v2[4] - v5) >> 1;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v6 + 2 * v8) );
    if ( (v8 | (unsigned __int64)v7) > 0x7FFFFFFF )
      __int2c();
    v9 = 2;
    if ( v6 )
      v9 = *a2;
    v10 = 2;
    if ( v5 )
      v10 = (__int64)v2[3];
    if ( CompareStringOrdinal((LPCWCH)v10, v7, (LPCWCH)v9, v8, 1) == 1 )
    {
      v11 = 2;
    }
    else
    {
      v4 = v2;
      v11 = 1;
    }
    v2 = (void **)v2[v11];
  }
  while ( v2 != &utl::_TreeSentinel );
  return v4;
}

```

## disassembly

```asm
0x180035fec  push    rbx
0x180035fee  push    rbp
0x180035fef  push    rsi
0x180035ff0  push    rdi
0x180035ff1  sub     rsp, 38h
0x180035ff5  mov     rbx, [rcx]
0x180035ff8  mov     rsi, rdx
0x180035ffb  mov     rdi, rcx
0x180035ffe  xor     ebp, ebp
0x180036000  mov     r10, [rbx+18h]
0x180036004  mov     rdx, [rbx+20h]
0x180036008  mov     rcx, [rsi]
0x18003600b  sub     rdx, r10
0x18003600e  sar     rdx, 1; cchCount1
0x180036011  or      r9, 0FFFFFFFFFFFFFFFFh
0x180036015  inc     r9; cchCount2
0x180036018  cmp     [rcx+r9*2], bp
0x18003601d  jnz     short loc_180036015
0x18003601f  mov     rax, rdx
0x180036022  or      rax, r9
0x180036025  cmp     rax, 7FFFFFFFh
0x18003602b  jbe     short loc_18003602F
0x18003602d  int     2Ch; Windows NT - assertion failure
0x18003602f  test    rcx, rcx
0x180036032  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18003603a  mov     r8d, 2
0x180036040  cmovnz  r8, rcx; lpString2
0x180036044  test    r10, r10
0x180036047  mov     ecx, 2
0x18003604c  cmovnz  rcx, r10; lpString1
0x180036050  call    cs:__imp_CompareStringOrdinal
0x180036056  cmp     eax, 1
0x180036059  jnz     short loc_180036062
0x18003605b  mov     eax, 10h
0x180036060  jmp     short loc_18003606A
0x180036062  mov     rdi, rbx
0x180036065  mov     eax, 8
0x18003606a  mov     rbx, [rax+rbx]
0x18003606e  lea     rax, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x180036075  cmp     rbx, rax
0x180036078  jnz     short loc_180036000
0x18003607a  mov     rax, rdi
0x18003607d  add     rsp, 38h
0x180036081  pop     rdi
0x180036082  pop     rsi
0x180036083  pop     rbp
0x180036084  pop     rbx
0x180036085  retn
```
