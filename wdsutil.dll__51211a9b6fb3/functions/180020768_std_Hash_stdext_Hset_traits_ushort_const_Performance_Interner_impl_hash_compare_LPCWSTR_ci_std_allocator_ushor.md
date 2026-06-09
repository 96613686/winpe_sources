# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>>)

- ea: `0x180020768`
- end: `0x180020801`
- name: `?erase@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@2@V32@@Z`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180032dab`
- `0x180032e0f`

## callees

- `0x180020320`
- `0x180020768`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800207e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800207e0`

## pseudocode

```c
wint_t **__fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::erase(
        wint_t **a1,
        wint_t **a2,
        wint_t **a3)
{
  unsigned __int64 v6; // rax
  wint_t *v7; // rcx
  __int64 v8; // r8
  wint_t *v9; // rax
  wint_t *v10; // rsi

  v6 = std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Hashval(
         (__int64)a1,
         a3 + 2);
  v7 = a1[2];
  v8 = 2 * v6;
  if ( *(wint_t ***)&v7[8 * v6 + 4] == a3 )
  {
    if ( *(wint_t ***)&v7[8 * v6] == a3 )
    {
      *(_QWORD *)&v7[8 * v6] = *a1;
      v7 = a1[2];
      v9 = *a1;
    }
    else
    {
      v9 = a3[1];
    }
    *(_QWORD *)&v7[4 * v8 + 4] = v9;
  }
  else if ( *(wint_t ***)&v7[8 * v6] == a3 )
  {
    *(_QWORD *)&v7[8 * v6] = *a3;
  }
  v10 = *a3;
  if ( a3 != (wint_t **)*a1 )
  {
    *(_QWORD *)a3[1] = v10;
    *((_QWORD *)*a3 + 1) = a3[1];
    operator delete(a3);
    a1[1] = (wint_t *)((char *)a1[1] - 1);
  }
  *a2 = v10;
  return a2;
}

```

## disassembly

```asm
0x180020768  push    rbx
0x18002076a  push    rsi
0x18002076b  push    rdi
0x18002076c  push    r14
0x18002076e  sub     rsp, 28h
0x180020772  mov     r14, rdx
0x180020775  mov     rbx, r8
0x180020778  lea     rdx, [r8+10h]
0x18002077c  mov     rdi, rcx
0x18002077f  call    ?_Hashval@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA_KAEBQEBG@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Hashval(ushort const * const &)
0x180020784  mov     rcx, [rdi+10h]
0x180020788  mov     r8, rax
0x18002078b  add     r8, r8
0x18002078e  cmp     [rcx+r8*8+8], rbx
0x180020793  jnz     short loc_1800207B6
0x180020795  cmp     [rcx+r8*8], rbx
0x180020799  jnz     short loc_1800207AB
0x18002079b  mov     rax, [rdi]
0x18002079e  mov     [rcx+r8*8], rax
0x1800207a2  mov     rcx, [rdi+10h]
0x1800207a6  mov     rax, [rdi]
0x1800207a9  jmp     short loc_1800207AF
0x1800207ab  mov     rax, [rbx+8]
0x1800207af  mov     [rcx+r8*8+8], rax
0x1800207b4  jmp     short loc_1800207C3
0x1800207b6  cmp     [rcx+r8*8], rbx
0x1800207ba  jnz     short loc_1800207C3
0x1800207bc  mov     rax, [rbx]
0x1800207bf  mov     [rcx+r8*8], rax
0x1800207c3  mov     rsi, [rbx]
0x1800207c6  cmp     rbx, [rdi]
0x1800207c9  jz      short loc_1800207F0
0x1800207cb  mov     rax, [rbx+8]
0x1800207cf  mov     [rax], rsi
0x1800207d2  mov     rcx, [rbx]
0x1800207d5  mov     rax, [rbx+8]
0x1800207d9  mov     [rcx+8], rax
0x1800207dd  mov     rcx, rbx
0x1800207e0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800207e7  nop     dword ptr [rax+rax+00h]
0x1800207ec  dec     qword ptr [rdi+8]
0x1800207f0  mov     [r14], rsi
0x1800207f3  mov     rax, r14
0x1800207f6  add     rsp, 28h
0x1800207fa  pop     r14
0x1800207fc  pop     rdi
0x1800207fd  pop     rsi
0x1800207fe  pop     rbx
0x1800207ff  retn
```
