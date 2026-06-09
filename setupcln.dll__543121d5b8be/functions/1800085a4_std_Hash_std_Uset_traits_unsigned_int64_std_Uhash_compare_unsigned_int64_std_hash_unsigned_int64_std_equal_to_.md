# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Init(unsigned __int64)

- ea: `0x1800085a4`
- end: `0x180008639`
- name: `?_Init@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `149`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006868`
- `0x180008308`

## callees

- `0x180001e68`
- `0x1800085a4`
- `0x180008698`
- `0x180008894`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Init(
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
      std::_Xlength_error("vector<T> too long");
    std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>>>>::_Reallocate(
      a1 + 2,
      v4);
  }
  v6 = *v2;
  v8 = *a1;
  v2[1] = v6;
  std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>>>>::_Insert_n(
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
0x1800085a4  mov     [rsp+arg_10], rbx
0x1800085a9  push    rsi
0x1800085aa  push    rdi
0x1800085ab  push    r14
0x1800085ad  sub     rsp, 30h
0x1800085b1  lea     rbx, [rcx+10h]
0x1800085b5  mov     r14, rdx
0x1800085b8  mov     rax, [rbx+10h]
0x1800085bc  lea     rdi, [rdx+rdx]
0x1800085c0  sub     rax, [rbx]
0x1800085c3  mov     rsi, rcx
0x1800085c6  sar     rax, 3
0x1800085ca  cmp     rax, rdi
0x1800085cd  jnb     short loc_1800085F6
0x1800085cf  mov     rax, 1FFFFFFFFFFFFFFFh
0x1800085d9  cmp     rdi, rax
0x1800085dc  jbe     short loc_1800085EB
0x1800085de  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x1800085e5  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800085eb  mov     rdx, rdi
0x1800085ee  mov     rcx, rbx
0x1800085f1  call    ?_Reallocate@?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>>>>::_Reallocate(unsigned __int64)
0x1800085f6  mov     rax, [rsi]
0x1800085f9  lea     rdx, [rsp+48h+arg_8]
0x1800085fe  mov     r8, [rbx]
0x180008601  mov     r9, rdi
0x180008604  mov     [rsp+48h+arg_0], rax
0x180008609  mov     rcx, rbx
0x18000860c  lea     rax, [rsp+48h+arg_0]
0x180008611  mov     [rbx+8], r8
0x180008615  mov     [rsp+48h+var_28], rax
0x18000861a  call    ?_Insert_n@?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@@2@_KAEBV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@2@@Z; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>>>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>>>>,unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0> const &)
0x18000861f  mov     rbx, [rsp+48h+arg_10]
0x180008624  lea     rax, [r14-1]
0x180008628  mov     [rsi+28h], rax
0x18000862c  mov     [rsi+30h], r14
0x180008630  add     rsp, 30h
0x180008634  pop     r14
0x180008636  pop     rdi
0x180008637  pop     rsi
0x180008638  retn
```
