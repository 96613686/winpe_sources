# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Check_size(void)

- ea: `0x180020200`
- end: `0x1800202d5`
- name: `?_Check_size@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAXXZ`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d78c`
- `0x18001d930`

## callees

- `0x18001d930`
- `0x180020200`
- `0x1800203c8`

## pseudocode

```c
void __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Check_size(
        __int64 *a1)
{
  __int64 v1; // r8
  unsigned __int64 v3; // rdx
  float v4; // xmm0_4
  __int64 v5; // rax
  float v6; // xmm1_4
  _QWORD *v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rbx
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  v1 = a1[1];
  v3 = a1[6];
  if ( v1 < 0 )
  {
    v5 = a1[1] & 1 | ((unsigned __int64)a1[1] >> 1);
    v4 = (float)(int)v5 + (float)(int)v5;
  }
  else
  {
    v4 = (float)(int)v1;
  }
  if ( (v3 & 0x8000000000000000uLL) != 0LL )
    v6 = (float)(int)(a1[6] & 1 | (v3 >> 1)) + (float)(int)(a1[6] & 1 | (v3 >> 1));
  else
    v6 = (float)(int)v3;
  if ( (float)(v4 / v6) > *((float *)a1 + 14) )
  {
    if ( v3 >= 0x200 )
    {
      if ( v3 < 0xFFFFFFFFFFFFFFFLL )
        v3 *= 2LL;
    }
    else
    {
      v3 *= 8LL;
    }
    std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Init(
      a1,
      v3);
    v7 = (_QWORD *)*a1;
    if ( (_QWORD *)*v7 != v7 )
    {
      v8 = v7[1];
      do
      {
        v9 = *(_QWORD *)*a1;
        std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Insert<unsigned short const * const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0>>(
          (__int64 **)a1,
          (__int64)v10,
          (const wchar_t **)(v9 + 16),
          (__int64 *)v9);
      }
      while ( v9 != v8 );
    }
  }
}

```

## disassembly

```asm
0x180020200  mov     [rsp+arg_0], rbx
0x180020205  mov     [rsp+arg_8], rsi
0x18002020a  push    rdi
0x18002020b  sub     rsp, 30h
0x18002020f  mov     r8, [rcx+8]
0x180020213  mov     rdi, rcx
0x180020216  mov     rdx, [rcx+30h]
0x18002021a  xorps   xmm0, xmm0
0x18002021d  test    r8, r8
0x180020220  js      short loc_180020229
0x180020222  cvtsi2ss xmm0, r8
0x180020227  jmp     short loc_18002023F
0x180020229  mov     rax, r8
0x18002022c  and     r8d, 1
0x180020230  shr     rax, 1
0x180020233  or      rax, r8
0x180020236  cvtsi2ss xmm0, rax
0x18002023b  addss   xmm0, xmm0
0x18002023f  xorps   xmm1, xmm1
0x180020242  test    rdx, rdx
0x180020245  js      short loc_18002024E
0x180020247  cvtsi2ss xmm1, rdx
0x18002024c  jmp     short loc_180020266
0x18002024e  mov     rax, rdx
0x180020251  mov     rcx, rdx
0x180020254  shr     rcx, 1
0x180020257  and     eax, 1
0x18002025a  or      rcx, rax
0x18002025d  cvtsi2ss xmm1, rcx
0x180020262  addss   xmm1, xmm1
0x180020266  divss   xmm0, xmm1
0x18002026a  comiss  xmm0, dword ptr [rdi+38h]
0x18002026e  jbe     short loc_1800202C4
0x180020270  cmp     rdx, 200h
0x180020277  jnb     short loc_18002027F
0x180020279  shl     rdx, 3
0x18002027d  jmp     short loc_180020291
0x18002027f  mov     rax, 0FFFFFFFFFFFFFFFh
0x180020289  cmp     rdx, rax
0x18002028c  jnb     short loc_180020291
0x18002028e  add     rdx, rdx
0x180020291  mov     rcx, rdi
0x180020294  call    ?_Init@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAX_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Init(unsigned __int64)
0x180020299  mov     rax, [rdi]
0x18002029c  cmp     [rax], rax
0x18002029f  jz      short loc_1800202C4
0x1800202a1  mov     rsi, [rax+8]
0x1800202a5  mov     rbx, [rdi]
0x1800202a8  lea     rdx, [rsp+38h+var_18]
0x1800202ad  mov     rcx, rdi
0x1800202b0  mov     rbx, [rbx]
0x1800202b3  mov     r9, rbx
0x1800202b6  lea     r8, [rbx+10h]
0x1800202ba  call    ??$_Insert@AEBQEBGV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@1@AEBQEBGV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@1@@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Insert<ushort const * const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>(ushort const * const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>)
0x1800202bf  cmp     rbx, rsi
0x1800202c2  jnz     short loc_1800202A5
0x1800202c4  mov     rbx, [rsp+38h+arg_0]
0x1800202c9  mov     rsi, [rsp+38h+arg_8]
0x1800202ce  add     rsp, 30h
0x1800202d2  pop     rdi
0x1800202d3  retn
```
