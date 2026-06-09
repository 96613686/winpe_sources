# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>>)

- ea: `0x1800089c8`
- end: `0x180008a4c`
- name: `?erase@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@2@V32@@Z`
- size: `132`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001366d`
- `0x1800136b8`

## callees

- `0x18000854c`
- `0x1800089c8`
- `0x180008a54`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::erase(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  unsigned __int64 v5; // rax
  _QWORD *v6; // r11
  __int64 v7; // r9
  __int64 v8; // rcx
  _QWORD *result; // rax
  char v10; // [rsp+30h] [rbp+8h] BYREF

  v5 = std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Hashval(
         (__int64)a1,
         a3 + 16);
  v7 = a1[2];
  if ( *(_QWORD **)(v7 + 16 * v5 + 8) == v6 )
  {
    if ( *(_QWORD **)(v7 + 16 * v5) == v6 )
    {
      *(_QWORD *)(v7 + 16 * v5) = *a1;
      *(_QWORD *)(a1[2] + 16 * v5 + 8) = *a1;
    }
    else
    {
      *(_QWORD *)(v7 + 16 * v5 + 8) = v6[1];
    }
  }
  else if ( *(_QWORD **)(v7 + 16 * v5) == v6 )
  {
    *(_QWORD *)(v7 + 16 * v5) = *v6;
  }
  v8 = *(_QWORD *)std::list<unsigned __int64>::erase(a1, &v10, v6);
  result = a2;
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x1800089c8  mov     [rsp+arg_8], rbx
0x1800089cd  push    rdi
0x1800089ce  sub     rsp, 20h
0x1800089d2  mov     rdi, rdx
0x1800089d5  mov     r11, r8
0x1800089d8  lea     rdx, [r8+10h]
0x1800089dc  mov     rbx, rcx
0x1800089df  call    ?_Hashval@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEBA_KAEB_K@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Hashval(unsigned __int64 const &)
0x1800089e4  mov     r9, [rbx+10h]
0x1800089e8  mov     r8, rax
0x1800089eb  add     r8, r8
0x1800089ee  cmp     [r9+r8*8+8], r11
0x1800089f3  jnz     short loc_180008A1B
0x1800089f5  cmp     [r9+r8*8], r11
0x1800089f9  jnz     short loc_180008A10
0x1800089fb  mov     rcx, [rbx]
0x1800089fe  mov     [r9+r8*8], rcx
0x180008a02  mov     rcx, [rbx+10h]
0x180008a06  mov     rax, [rbx]
0x180008a09  mov     [rcx+r8*8+8], rax
0x180008a0e  jmp     short loc_180008A28
0x180008a10  mov     rax, [r11+8]
0x180008a14  mov     [r9+r8*8+8], rax
0x180008a19  jmp     short loc_180008A28
0x180008a1b  cmp     [r9+r8*8], r11
0x180008a1f  jnz     short loc_180008A28
0x180008a21  mov     rax, [r11]
0x180008a24  mov     [r9+r8*8], rax
0x180008a28  mov     r8, r11
0x180008a2b  lea     rdx, [rsp+28h+arg_0]
0x180008a30  mov     rcx, rbx
0x180008a33  call    ?erase@?$list@_KV?$allocator@_K@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@2@@Z; std::list<unsigned __int64>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>>)
0x180008a38  mov     rbx, [rsp+28h+arg_8]
0x180008a3d  mov     rcx, [rax]
0x180008a40  mov     rax, rdi
0x180008a43  mov     [rdi], rcx
0x180008a46  add     rsp, 20h
0x180008a4a  pop     rdi
0x180008a4b  retn
```
