# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Init(unsigned __int64)

- ea: `0x1800203c8`
- end: `0x180020457`
- name: `?_Init@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAX_K@Z`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001dc54`
- `0x180020200`

## callees

- `0x18001d320`
- `0x1800203c8`
- `0x180020460`
- `0x1800206bc`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Init(
        __int64 *a1,
        __int64 a2)
{
  __int64 *v2; // rbx
  unsigned __int64 v4; // rdi
  __int64 v6; // r8
  __int64 result; // rax
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF
  char v9; // [rsp+58h] [rbp+10h] BYREF

  v2 = a1 + 2;
  v4 = 2 * a2;
  if ( (a1[4] - a1[2]) >> 3 < (unsigned __int64)(2 * a2) )
  {
    if ( v4 > 0x1FFFFFFFFFFFFFFFLL )
      std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Xlen();
    std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0>>>>::_Reallocate(
      a1 + 2,
      v4);
  }
  v6 = *v2;
  v8 = *a1;
  v2[1] = v6;
  std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0>>>>::_Insert_n(
    (_DWORD)v2,
    (unsigned int)&v9,
    v6,
    v4,
    (__int64)&v8);
  result = a2 - 1;
  a1[5] = a2 - 1;
  a1[6] = a2;
  return result;
}

```

## disassembly

```asm
0x1800203c8  mov     [rsp+arg_10], rbx
0x1800203cd  push    rsi
0x1800203ce  push    rdi
0x1800203cf  push    r14
0x1800203d1  sub     rsp, 30h
0x1800203d5  lea     rbx, [rcx+10h]
0x1800203d9  mov     r14, rdx
0x1800203dc  mov     rax, [rbx+10h]
0x1800203e0  lea     rdi, [rdx+rdx]
0x1800203e4  sub     rax, [rbx]
0x1800203e7  mov     rsi, rcx
0x1800203ea  sar     rax, 3
0x1800203ee  cmp     rax, rdi
0x1800203f1  jnb     short loc_18002040D
0x1800203f3  mov     rax, 1FFFFFFFFFFFFFFFh
0x1800203fd  cmp     rdi, rax
0x180020400  ja      short loc_180020451
0x180020402  mov     rdx, rdi
0x180020405  mov     rcx, rbx
0x180020408  call    ?_Reallocate@?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>>::_Reallocate(unsigned __int64)
0x18002040d  mov     rax, [rsi]
0x180020410  lea     rdx, [rsp+48h+arg_8]
0x180020415  mov     r8, [rbx]
0x180020418  mov     r9, rdi
0x18002041b  mov     [rsp+48h+arg_0], rax
0x180020420  mov     rcx, rbx
0x180020423  lea     rax, [rsp+48h+arg_0]
0x180020428  mov     [rbx+8], r8
0x18002042c  mov     [rsp+48h+var_28], rax
0x180020431  call    ?_Insert_n@?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@@2@_KAEBV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@2@@Z; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>>,unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0> const &)
0x180020436  mov     rbx, [rsp+48h+arg_10]
0x18002043b  lea     rax, [r14-1]
0x18002043f  mov     [rsi+28h], rax
0x180020443  mov     [rsi+30h], r14
0x180020447  add     rsp, 30h
0x18002044b  pop     r14
0x18002044d  pop     rdi
0x18002044e  pop     rsi
0x18002044f  retn
0x180020451  call    ?_Xlen@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEBAXXZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Xlen(void)
```
