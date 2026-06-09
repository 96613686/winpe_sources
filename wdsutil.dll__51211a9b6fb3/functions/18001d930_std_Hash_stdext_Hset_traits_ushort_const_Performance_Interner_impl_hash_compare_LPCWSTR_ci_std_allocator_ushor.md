# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Insert<ushort const * const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>(ushort const * const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>)

- ea: `0x18001d930`
- end: `0x18001daba`
- name: `??$_Insert@AEBQEBGV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@1@AEBQEBGV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@1@@Z`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020200`

## callees

- `0x18001d930`
- `0x180020200`
- `0x180020320`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001d9a0`
- `msvcrt!_wcsicmp` at `0x18001d9b8`
- `msvcrt!_wcsicmp` at `0x18001d9a0`
- `msvcrt!_wcsicmp` at `0x18001d9b8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d9eb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d9eb`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Insert<unsigned short const * const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0>>(
        __int64 **a1,
        __int64 a2,
        const wchar_t **a3,
        __int64 *a4)
{
  __int64 v8; // rax
  __int64 *v9; // rdi
  __int64 v10; // r14
  __int64 *v11; // rax
  __int64 *v12; // r13
  __int64 result; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  __int64 *v16; // rdx
  __int64 *v17; // rax
  __int64 *v18; // rax
  __int64 **v19; // rax
  __int64 *v20; // rcx
  __int64 *v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rcx
  _QWORD *iter; // rax
  __int64 v25; // [rsp+28h] [rbp-40h] BYREF
  __int64 v26; // [rsp+30h] [rbp-38h] BYREF

  v8 = std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Hashval(
         a1,
         a3);
  v9 = *a1;
  v10 = 2 * v8;
  v11 = a1[2];
  if ( (__int64 *)v11[v10] != *a1 )
    v9 = *(__int64 **)v11[v10 + 1];
  do
  {
    if ( v9 == (__int64 *)a1[2][v10] )
      goto LABEL_10;
    v12 = (__int64 *)v9[1];
    v9 = v12;
  }
  while ( _wcsicmp(*a3, (const wchar_t *)v12[2]) < 0 );
  if ( _wcsicmp((const wchar_t *)v12[2], *a3) < 0 )
  {
    v9 = (__int64 *)*v12;
LABEL_10:
    v14 = *a4;
    if ( v9 != (__int64 *)*a4 )
    {
      *(_QWORD *)a4[1] = v14;
      **(_QWORD **)(v14 + 8) = v9;
      *(_QWORD *)v9[1] = a4;
      v15 = (_QWORD *)v9[1];
      v9[1] = *(_QWORD *)(v14 + 8);
      *(_QWORD *)(v14 + 8) = a4[1];
      a4[1] = (__int64)v15;
    }
    v16 = a1[2];
    v17 = (__int64 *)v16[v10];
    if ( v17 == *a1 )
    {
      v16[v10] = (__int64)a4;
      v18 = a1[2];
      v18[v10 + 1] = (__int64)a4;
    }
    else if ( v17 == v9 )
    {
      v16[v10] = (__int64)a4;
    }
    else
    {
      v19 = (__int64 **)v16[v10 + 1];
      v20 = *v19;
      v16[v10 + 1] = (__int64)*v19;
      if ( v20 != a4 )
      {
        v21 = a1[2];
        v22 = v21[v10 + 1];
        v21[v10 + 1] = *(_QWORD *)(v22 + 8);
      }
    }
    try
    {
      std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Check_size(a1);
      *(_QWORD *)a2 = a4;
      *(_BYTE *)(a2 + 8) = 1;
      result = a2;
    }
    catch ( ... )
    {
      iter = (_QWORD *)std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Make_iter(
                         v23,
                         &v25,
                         a4);
      std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::erase(
        a1,
        &v26,
        *iter);
      throw;
    }
    return result;
  }
  if ( a4 != *a1 )
  {
    *(_QWORD *)a4[1] = *a4;
    *(_QWORD *)(*a4 + 8) = a4[1];
    operator delete(a4);
    a1[1] = (__int64 *)((char *)a1[1] - 1);
  }
  *(_QWORD *)a2 = v12;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x18001d930  mov     rax, rsp
0x18001d933  mov     [rax+20h], r9
0x18001d937  mov     [rax+8], rcx
0x18001d93b  push    rdi
0x18001d93c  push    r12
0x18001d93e  push    r13
0x18001d940  push    r14
0x18001d942  push    r15
0x18001d944  sub     rsp, 40h
0x18001d948  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18001d950  mov     [rax+10h], rbx
0x18001d954  mov     [rax+18h], rsi
0x18001d958  mov     rbx, r9
0x18001d95b  mov     r12, r8
0x18001d95e  mov     r15, rdx
0x18001d961  mov     rsi, rcx
0x18001d964  mov     rdx, r8
0x18001d967  call    ?_Hashval@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA_KAEBQEBG@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Hashval(ushort const * const &)
0x18001d96c  mov     r14, rax
0x18001d96f  mov     rdi, [rsi]
0x18001d972  add     r14, r14
0x18001d975  mov     rax, [rsi+10h]
0x18001d979  cmp     [rax+r14*8], rdi
0x18001d97d  jz      short loc_18001D987
0x18001d97f  mov     rdi, [rax+r14*8+8]
0x18001d984  mov     rdi, [rdi]
0x18001d987  mov     rax, [rsi+10h]
0x18001d98b  cmp     rdi, [rax+r14*8]
0x18001d98f  jz      short loc_18001DA0B
0x18001d991  mov     r13, [rdi+8]
0x18001d995  mov     rdi, r13
0x18001d998  mov     rdx, [r13+10h]; String2
0x18001d99c  mov     rcx, [r12]; String1
0x18001d9a0  call    cs:__imp__wcsicmp
0x18001d9a7  nop     dword ptr [rax+rax+00h]
0x18001d9ac  test    eax, eax
0x18001d9ae  js      short loc_18001D987
0x18001d9b0  mov     rdx, [r12]; String2
0x18001d9b4  mov     rcx, [r13+10h]; String1
0x18001d9b8  call    cs:__imp__wcsicmp
0x18001d9bf  nop     dword ptr [rax+rax+00h]
0x18001d9c4  test    eax, eax
0x18001d9c6  jns     short loc_18001D9CE
0x18001d9c8  mov     rdi, [r13+0]
0x18001d9cc  jmp     short loc_18001DA0B
0x18001d9ce  cmp     rbx, [rsi]
0x18001d9d1  jz      short loc_18001D9FB
0x18001d9d3  mov     rcx, [rbx+8]
0x18001d9d7  mov     rax, [rbx]
0x18001d9da  mov     [rcx], rax
0x18001d9dd  mov     rcx, [rbx]
0x18001d9e0  mov     rax, [rbx+8]
0x18001d9e4  mov     [rcx+8], rax
0x18001d9e8  mov     rcx, rbx
0x18001d9eb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d9f2  nop     dword ptr [rax+rax+00h]
0x18001d9f7  dec     qword ptr [rsi+8]
0x18001d9fb  mov     [r15], r13
0x18001d9fe  mov     byte ptr [r15+8], 0
0x18001da03  mov     rax, r15
0x18001da06  jmp     loc_18001DA9F
0x18001da0b  mov     rdx, [rbx]
0x18001da0e  cmp     rdi, rdx
0x18001da11  jz      short loc_18001DA40
0x18001da13  mov     rax, [rbx+8]
0x18001da17  mov     [rax], rdx
0x18001da1a  mov     rax, [rdx+8]
0x18001da1e  mov     [rax], rdi
0x18001da21  mov     rax, [rdi+8]
0x18001da25  mov     [rax], rbx
0x18001da28  mov     rcx, [rdi+8]
0x18001da2c  mov     rax, [rdx+8]
0x18001da30  mov     [rdi+8], rax
0x18001da34  mov     rax, [rbx+8]
0x18001da38  mov     [rdx+8], rax
0x18001da3c  mov     [rbx+8], rcx
0x18001da40  mov     rdx, [rsi+10h]
0x18001da44  mov     rax, [rdx+r14*8]
0x18001da48  cmp     rax, [rsi]
0x18001da4b  jnz     short loc_18001DA5C
0x18001da4d  mov     [rdx+r14*8], rbx
0x18001da51  mov     rax, [rsi+10h]
0x18001da55  mov     [rax+r14*8+8], rbx
0x18001da5a  jmp     short loc_18001DA8B
0x18001da5c  cmp     rax, rdi
0x18001da5f  jnz     short loc_18001DA67
0x18001da61  mov     [rdx+r14*8], rbx
0x18001da65  jmp     short loc_18001DA8B
0x18001da67  mov     rax, [rdx+r14*8+8]
0x18001da6c  mov     rcx, [rax]
0x18001da6f  mov     [rdx+r14*8+8], rcx
0x18001da74  cmp     rcx, rbx
0x18001da77  jz      short loc_18001DA8B
0x18001da79  mov     rdx, [rsi+10h]
0x18001da7d  mov     rax, [rdx+r14*8+8]
0x18001da82  mov     rcx, [rax+8]
0x18001da86  mov     [rdx+r14*8+8], rcx
0x18001da8b  mov     rcx, rsi
0x18001da8e  call    ?_Check_size@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAXXZ; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Check_size(void)
0x18001da93  nop
0x18001da94  mov     [r15], rbx
0x18001da97  mov     byte ptr [r15+8], 1
0x18001da9c  mov     rax, r15
0x18001da9f  lea     r11, [rsp+68h+var_28]
0x18001daa4  mov     rbx, [r11+38h]
0x18001daa8  mov     rsi, [r11+40h]
0x18001daac  mov     rsp, r11
0x18001daaf  pop     r15
0x18001dab1  pop     r14
0x18001dab3  pop     r13
0x18001dab5  pop     r12
0x18001dab7  pop     rdi
0x18001dab8  retn
```
