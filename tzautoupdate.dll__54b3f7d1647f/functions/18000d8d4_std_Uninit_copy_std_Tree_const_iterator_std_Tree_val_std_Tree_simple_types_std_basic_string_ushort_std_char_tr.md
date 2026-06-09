# std::_Uninit_copy<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Wrap_alloc<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18000d8d4`
- end: `0x18000d95e`
- name: `??$_Uninit_copy@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@0@0PEAV10@AEAU?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d33c`

## callees

- `0x18000d8d4`
- `0x18000da40`
- `0x18000e854`

## pseudocode

```c
__int64 __fastcall std::_Uninit_copy<std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>,std::wstring *,std::allocator<std::wstring>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rsi
  __int64 i; // rax
  __int64 j; // rbx
  __int64 v9; // [rsp+40h] [rbp+18h]

  v3 = a3;
  while ( a1 != a2 )
  {
    try
    {
      std::wstring::wstring();
      v3 += 32;
      v9 = v3;
      if ( !*(_BYTE *)(a1 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)(a1 + 16) + 25LL) )
        {
          for ( i = *(_QWORD *)(a1 + 8); !*(_BYTE *)(i + 25) && a1 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
            a1 = i;
        }
        else
        {
          i = std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Min();
        }
        a1 = i;
      }
    }
    catch ( ... )
    {
      for ( j = a3; j != v9; j += 32 )
        std::wstring::`scalar deleting destructor'(j);
      throw;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000d8d4  mov     rax, rsp
0x18000d8d7  mov     [rax+8], rbx
0x18000d8db  mov     [rax+10h], rsi
0x18000d8df  mov     [rax+20h], r9
0x18000d8e3  mov     [rax+18h], r8
0x18000d8e7  push    rdi
0x18000d8e8  sub     rsp, 20h
0x18000d8ec  mov     rsi, r8
0x18000d8ef  mov     rdi, rdx
0x18000d8f2  mov     rbx, rcx
0x18000d8f5  mov     [rsp+28h+arg_18], r8
0x18000d8fa  cmp     rbx, rdi
0x18000d8fd  jnz     short loc_18000D912
0x18000d8ff  mov     rax, rsi
0x18000d902  mov     rbx, [rsp+28h+arg_0]
0x18000d907  mov     rsi, [rsp+28h+arg_8]
0x18000d90c  add     rsp, 20h
0x18000d910  pop     rdi
0x18000d911  retn
0x18000d912  lea     rdx, [rbx+20h]
0x18000d916  mov     rcx, rsi
0x18000d919  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000d91e  add     rsi, 20h ; ' '
0x18000d922  mov     [rsp+28h+arg_10], rsi
0x18000d927  cmp     byte ptr [rbx+19h], 0
0x18000d92b  jnz     short loc_18000D8FA
0x18000d92d  mov     rcx, [rbx+10h]
0x18000d931  cmp     byte ptr [rcx+19h], 0
0x18000d935  jnz     short loc_18000D93E
0x18000d937  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@SAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Min(std::_Tree_node<std::wstring,void *> *)
0x18000d93c  jmp     short loc_18000D957
0x18000d93e  mov     rax, [rbx+8]
0x18000d942  jmp     short loc_18000D951
0x18000d944  cmp     rbx, [rax+10h]
0x18000d948  jnz     short loc_18000D957
0x18000d94a  mov     rbx, rax
0x18000d94d  mov     rax, [rax+8]
0x18000d951  cmp     byte ptr [rax+19h], 0
0x18000d955  jz      short loc_18000D944
0x18000d957  mov     rbx, rax
0x18000d95a  jmp     short loc_18000D8FA
```
