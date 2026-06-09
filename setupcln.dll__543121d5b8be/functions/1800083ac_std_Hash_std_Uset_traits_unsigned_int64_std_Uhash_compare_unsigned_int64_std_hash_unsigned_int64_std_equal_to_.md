# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_End(unsigned __int64)

- ea: `0x1800083ac`
- end: `0x1800083d0`
- name: `?_End@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAA?AV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@2@_K@Z`
- size: `36`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003754`
- `0x180003894`
- `0x1800071a8`

## callees

- `0x1800083ac`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_End(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v3; // r9
  __int64 v4; // r8

  v3 = a1[2];
  v4 = 2 * a3;
  if ( *(_QWORD *)(v3 + 8 * v4) == *a1 )
    *a2 = *a1;
  else
    *a2 = **(_QWORD **)(v3 + 8 * v4 + 8);
  return a2;
}

```

## disassembly

```asm
0x1800083ac  mov     r9, [rcx+10h]
0x1800083b0  add     r8, r8
0x1800083b3  mov     rax, [rcx]
0x1800083b6  cmp     [r9+r8*8], rax
0x1800083ba  jnz     short loc_1800083C1
0x1800083bc  mov     [rdx], rax
0x1800083bf  jmp     short loc_1800083CC
0x1800083c1  mov     rax, [r9+r8*8+8]
0x1800083c6  mov     rcx, [rax]
0x1800083c9  mov     [rdx], rcx
0x1800083cc  mov     rax, rdx
0x1800083cf  retn
```
