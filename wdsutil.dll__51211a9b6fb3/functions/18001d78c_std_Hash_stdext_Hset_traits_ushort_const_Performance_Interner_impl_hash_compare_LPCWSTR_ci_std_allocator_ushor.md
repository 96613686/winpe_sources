# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Insert<ushort const * const &,std::_Nil>(ushort const * const &,std::_Nil)

- ea: `0x18001d78c`
- end: `0x18001d928`
- name: `??$_Insert@AEBQEBGU_Nil@std@@@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@1@AEBQEBGU_Nil@1@@Z`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001f830`

## callees

- `0x180001540`
- `0x18001d758`
- `0x18001d78c`
- `0x180020200`
- `0x180020320`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001d7eb`
- `msvcrt!_wcsicmp` at `0x18001d802`
- `msvcrt!_wcsicmp` at `0x18001d7eb`
- `msvcrt!_wcsicmp` at `0x18001d802`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Insert<unsigned short const * const &,std::_Nil>(
        __int64 **a1,
        __int64 a2,
        const wchar_t **a3)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 *v8; // rbx
  __int64 v9; // rdi
  __int64 *v10; // rax
  __int64 v11; // r13
  __int64 result; // rax
  __int64 v13; // r13
  __int64 v14; // rdx
  __int64 *v15; // rax
  __int64 **v16; // r14
  __int64 *v17; // rdx
  __int64 *v18; // rcx
  __int64 *v19; // rdx
  __int64 *v20; // rax
  __int64 *v21; // rax
  __int64 ***v22; // rax
  __int64 **v23; // rcx
  __int64 *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  _QWORD *iter; // rax
  _QWORD v29[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v30; // [rsp+30h] [rbp-48h] BYREF

  v29[1] = -2;
  v6 = std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Hashval(
         a1,
         a3);
  v8 = *a1;
  v9 = 2 * v6;
  v10 = a1[2];
  if ( (__int64 *)v10[v9] != *a1 )
    v8 = *(__int64 **)v10[v9 + 1];
  while ( v8 != (__int64 *)a1[2][v9] )
  {
    v11 = v8[1];
    v8 = (__int64 *)v11;
    if ( _wcsicmp(*a3, *(const wchar_t **)(v11 + 16)) >= 0 )
    {
      if ( _wcsicmp(*(const wchar_t **)(v11 + 16), *a3) >= 0 )
      {
        *(_QWORD *)a2 = v11;
        *(_BYTE *)(a2 + 8) = 0;
        return a2;
      }
      v8 = *(__int64 **)v11;
      break;
    }
  }
  v13 = **a1;
  v14 = std::_List_buy<unsigned short const *>::_Buynode<unsigned short const * const &>(
          v7,
          v13,
          *(_QWORD *)(v13 + 8),
          a3);
  v15 = a1[1];
  if ( v15 == (__int64 *)0xAAAAAAAAAAAAAA9LL )
    std::_Xlength_error("list<T> too long");
  a1[1] = (__int64 *)((char *)v15 + 1);
  *(_QWORD *)(v13 + 8) = v14;
  **(_QWORD **)(v14 + 8) = v14;
  v16 = (__int64 **)**a1;
  v29[0] = v16;
  v17 = *v16;
  if ( v8 != *v16 )
  {
    *v16[1] = (__int64)v17;
    *(_QWORD *)v17[1] = v8;
    *(_QWORD *)v8[1] = v16;
    v18 = (__int64 *)v8[1];
    v8[1] = v17[1];
    v17[1] = (__int64)v16[1];
    v16[1] = v18;
  }
  v19 = a1[2];
  v20 = (__int64 *)v19[v9];
  if ( v20 == *a1 )
  {
    v19[v9] = (__int64)v16;
    v21 = a1[2];
    v21[v9 + 1] = (__int64)v16;
  }
  else if ( v20 == v8 )
  {
    v19[v9] = (__int64)v16;
  }
  else
  {
    v22 = (__int64 ***)v19[v9 + 1];
    v23 = *v22;
    v19[v9 + 1] = (__int64)*v22;
    if ( v23 != v16 )
    {
      v24 = a1[2];
      v25 = v24[v9 + 1];
      v26 = *(_QWORD *)(v25 + 8);
      v24[v9 + 1] = v26;
    }
  }
  try
  {
    std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Check_size(a1);
    *(_QWORD *)a2 = v16;
    *(_BYTE *)(a2 + 8) = 1;
    result = a2;
  }
  catch ( ... )
  {
    iter = (_QWORD *)std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Make_iter(
                       v27,
                       v29,
                       v29[0]);
    std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::erase(
      a1,
      &v30,
      *iter);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18001d78c  mov     [rsp+arg_0], rcx
0x18001d791  push    rbx
0x18001d792  push    rsi
0x18001d793  push    rdi
0x18001d794  push    r13
0x18001d796  push    r14
0x18001d798  push    r15
0x18001d79a  sub     rsp, 48h
0x18001d79e  mov     [rsp+78h+var_50], 0FFFFFFFFFFFFFFFEh
0x18001d7a7  mov     r14, r8
0x18001d7aa  mov     r15, rdx
0x18001d7ad  mov     rsi, rcx
0x18001d7b0  mov     rdx, r8
0x18001d7b3  call    ?_Hashval@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA_KAEBQEBG@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Hashval(ushort const * const &)
0x18001d7b8  mov     rdi, rax
0x18001d7bb  mov     rbx, [rsi]
0x18001d7be  add     rdi, rdi
0x18001d7c1  mov     rax, [rsi+10h]
0x18001d7c5  cmp     [rax+rdi*8], rbx
0x18001d7c9  jz      short loc_18001D7D3
0x18001d7cb  mov     rbx, [rax+rdi*8+8]
0x18001d7d0  mov     rbx, [rbx]
0x18001d7d3  mov     rax, [rsi+10h]
0x18001d7d7  cmp     rbx, [rax+rdi*8]
0x18001d7db  jz      short loc_18001D828
0x18001d7dd  mov     r13, [rbx+8]
0x18001d7e1  mov     rbx, r13
0x18001d7e4  mov     rdx, [r13+10h]; String2
0x18001d7e8  mov     rcx, [r14]; String1
0x18001d7eb  call    cs:__imp__wcsicmp
0x18001d7f2  nop     dword ptr [rax+rax+00h]
0x18001d7f7  test    eax, eax
0x18001d7f9  js      short loc_18001D7D3
0x18001d7fb  mov     rdx, [r14]; String2
0x18001d7fe  mov     rcx, [r13+10h]; String1
0x18001d802  call    cs:__imp__wcsicmp
0x18001d809  nop     dword ptr [rax+rax+00h]
0x18001d80e  test    eax, eax
0x18001d810  jns     short loc_18001D818
0x18001d812  mov     rbx, [r13+0]
0x18001d816  jmp     short loc_18001D828
0x18001d818  mov     [r15], rbx
0x18001d81b  mov     byte ptr [r15+8], 0
0x18001d820  mov     rax, r15
0x18001d823  jmp     loc_18001D90C
0x18001d828  mov     rax, [rsi]
0x18001d82b  mov     r13, [rax]
0x18001d82e  mov     r9, r14
0x18001d831  mov     r8, [r13+8]
0x18001d835  mov     rdx, r13
0x18001d838  call    ??$_Buynode@AEBQEBG@?$_List_buy@PEBGV?$allocator@PEBG@std@@@std@@QEAAPEAU?$_List_node@PEBGPEAX@1@PEAU21@0AEBQEBG@Z; std::_List_buy<ushort const *>::_Buynode<ushort const * const &>(std::_List_node<ushort const *,void *> *,std::_List_node<ushort const *,void *> *,ushort const * const &)
0x18001d83d  mov     rdx, rax
0x18001d840  mov     rax, [rsi+8]
0x18001d844  mov     rcx, 0AAAAAAAAAAAAAA9h
0x18001d84e  sub     rcx, rax
0x18001d851  cmp     rcx, 1
0x18001d855  jb      loc_18001D91B
0x18001d85b  inc     rax
0x18001d85e  mov     [rsi+8], rax
0x18001d862  mov     [r13+8], rdx
0x18001d866  mov     rax, [rdx+8]
0x18001d86a  mov     [rax], rdx
0x18001d86d  mov     rax, [rsi]
0x18001d870  mov     r14, [rax]
0x18001d873  mov     [rsp+78h+var_58], r14
0x18001d878  mov     rdx, [r14]
0x18001d87b  cmp     rbx, rdx
0x18001d87e  jz      short loc_18001D8AD
0x18001d880  mov     rax, [r14+8]
0x18001d884  mov     [rax], rdx
0x18001d887  mov     rax, [rdx+8]
0x18001d88b  mov     [rax], rbx
0x18001d88e  mov     rax, [rbx+8]
0x18001d892  mov     [rax], r14
0x18001d895  mov     rcx, [rbx+8]
0x18001d899  mov     rax, [rdx+8]
0x18001d89d  mov     [rbx+8], rax
0x18001d8a1  mov     rax, [r14+8]
0x18001d8a5  mov     [rdx+8], rax
0x18001d8a9  mov     [r14+8], rcx
0x18001d8ad  mov     rdx, [rsi+10h]
0x18001d8b1  mov     rax, [rdx+rdi*8]
0x18001d8b5  cmp     rax, [rsi]
0x18001d8b8  jnz     short loc_18001D8C9
0x18001d8ba  mov     [rdx+rdi*8], r14
0x18001d8be  mov     rax, [rsi+10h]
0x18001d8c2  mov     [rax+rdi*8+8], r14
0x18001d8c7  jmp     short loc_18001D8F8
0x18001d8c9  cmp     rax, rbx
0x18001d8cc  jnz     short loc_18001D8D4
0x18001d8ce  mov     [rdx+rdi*8], r14
0x18001d8d2  jmp     short loc_18001D8F8
0x18001d8d4  mov     rax, [rdx+rdi*8+8]
0x18001d8d9  mov     rcx, [rax]
0x18001d8dc  mov     [rdx+rdi*8+8], rcx
0x18001d8e1  cmp     rcx, r14
0x18001d8e4  jz      short loc_18001D8F8
0x18001d8e6  mov     rdx, [rsi+10h]
0x18001d8ea  mov     rax, [rdx+rdi*8+8]
0x18001d8ef  mov     rcx, [rax+8]
0x18001d8f3  mov     [rdx+rdi*8+8], rcx
0x18001d8f8  mov     rcx, rsi
0x18001d8fb  call    ?_Check_size@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAXXZ; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Check_size(void)
0x18001d900  nop
0x18001d901  mov     [r15], r14
0x18001d904  mov     byte ptr [r15+8], 1
0x18001d909  mov     rax, r15
0x18001d90c  add     rsp, 48h
0x18001d910  pop     r15
0x18001d912  pop     r14
0x18001d914  pop     r13
0x18001d916  pop     rdi
0x18001d917  pop     rsi
0x18001d918  pop     rbx
0x18001d919  retn
0x18001d91b  lea     rcx, aListTTooLong; "list<T> too long"
0x18001d922  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
