# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Make_iter(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>)

- ea: `0x1800206ac`
- end: `0x1800206b3`
- name: `?_Make_iter@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@2@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180032dab`
- `0x180032e0f`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Make_iter(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  *a2 = a3;
  return a2;
}

```

## disassembly

```asm
0x1800206ac  mov     [rdx], r8
0x1800206af  mov     rax, rdx
0x1800206b2  retn
```
