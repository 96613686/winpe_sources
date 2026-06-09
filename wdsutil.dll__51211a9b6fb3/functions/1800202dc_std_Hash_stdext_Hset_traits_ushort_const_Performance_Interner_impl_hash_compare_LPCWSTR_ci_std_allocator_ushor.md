# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Destroy_if_not_nil(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>)

- ea: `0x1800202dc`
- end: `0x180020319`
- name: `?_Destroy_if_not_nil@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180032de8`

## callees

- `0x1800202dc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180020302`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020302`

## pseudocode

```c
void __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Destroy_if_not_nil(
        _QWORD *a1,
        _QWORD **a2)
{
  if ( a2 != (_QWORD **)*a1 )
  {
    *a2[1] = *a2;
    (*a2)[1] = a2[1];
    operator delete(a2);
    --a1[1];
  }
}

```

## disassembly

```asm
0x1800202dc  push    rbx
0x1800202de  sub     rsp, 20h
0x1800202e2  mov     rbx, rcx
0x1800202e5  cmp     rdx, [rcx]
0x1800202e8  jz      short loc_180020312
0x1800202ea  mov     r8, [rdx+8]
0x1800202ee  mov     rcx, rdx
0x1800202f1  mov     rax, [rdx]
0x1800202f4  mov     [r8], rax
0x1800202f7  mov     r8, [rdx]
0x1800202fa  mov     rax, [rdx+8]
0x1800202fe  mov     [r8+8], rax
0x180020302  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020309  nop     dword ptr [rax+rax+00h]
0x18002030e  dec     qword ptr [rbx+8]
0x180020312  add     rsp, 20h
0x180020316  pop     rbx
0x180020317  retn
```
