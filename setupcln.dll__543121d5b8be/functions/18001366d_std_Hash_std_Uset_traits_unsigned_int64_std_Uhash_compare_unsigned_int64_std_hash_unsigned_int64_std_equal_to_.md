# _std::_Hash_std::_Uset_traits_unsigned___int64_std::_Uhash_compare_unsigned___int64_std::hash_unsigned___int64__std::equal_to_unsigned___int64____std::allocator_unsigned___int64__0___::_Insert_unsigned___int64_const_&_std::_Nil__::_1_::catch$0

- ea: `0x18001366d`
- end: `0x180013695`
- name: `_std::_Hash_std::_Uset_traits_unsigned___int64_std::_Uhash_compare_unsigned___int64_std::hash_unsigned___int64__std::equal_to_unsigned___int64____std::allocator_unsigned___int64__0___::_Insert_unsigned___int64_const_&_std::_Nil__::_1_::catch$0`
- size: `40`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002b4c`
- `0x1800089c8`

## pseudocode

```c
void __fastcall __noreturn std::_Hash_std::_Uset_traits_unsigned___int64_std::_Uhash_compare_unsigned___int64_std::hash_unsigned___int64__std::equal_to_unsigned___int64____std::allocator_unsigned___int64__0___::_Insert_unsigned___int64_const___std::_Nil__::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::erase(
    *(_QWORD **)(a2 + 80),
    (_QWORD *)(a2 + 32),
    *(_QWORD *)(a2 + 32));
  throw;
}

```

## disassembly

```asm
0x18001366d  mov     [rsp+arg_8], rdx
0x180013672  push    rbp
0x180013673  sub     rsp, 20h
0x180013677  mov     rbp, rdx
0x18001367a  mov     r8, [rbp+20h]
0x18001367e  lea     rdx, [rbp+20h]
0x180013682  mov     rcx, [rbp+50h]
0x180013686  call    ?erase@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@2@V32@@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>>)
0x18001368b  xor     edx, edx; pThrowInfo
0x18001368d  xor     ecx, ecx; pExceptionObject
0x18001368f  call    _CxxThrowException_0
```
