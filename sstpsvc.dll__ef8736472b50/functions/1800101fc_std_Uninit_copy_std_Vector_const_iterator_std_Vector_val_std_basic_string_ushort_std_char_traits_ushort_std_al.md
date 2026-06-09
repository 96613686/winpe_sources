# std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(std::_Vector_const_iterator<std::_Vector_val<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::_Vector_const_iterator<std::_Vector_val<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x1800101fc`
- end: `0x180010257`
- name: `??$_Uninit_copy@V?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@V?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@0@0PEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800106b4`

## callees

- `0x1800101fc`
- `0x1800104f4`

## pseudocode

```c
__int64 __fastcall std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::wstring>>,std::wstring *,std::allocator<std::wstring>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rsi
  __int64 v7; // rcx
  __int64 i; // rbx
  __int64 v9; // [rsp+40h] [rbp+18h]

  v3 = a3;
  while ( a1 != a2 )
  {
    try
    {
      std::wstring::wstring(v3, a1);
      v3 += 40;
      v9 = v3;
      a1 += 40;
    }
    catch ( ... )
    {
      for ( i = a3; i != v9; i += 40 )
        std::_Dest_val<std::allocator<std::wstring>,std::wstring>(v7, i);
      throw;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800101fc  mov     rax, rsp
0x1800101ff  mov     [rax+8], rbx
0x180010203  mov     [rax+10h], rsi
0x180010207  mov     [rax+20h], r9
0x18001020b  mov     [rax+18h], r8
0x18001020f  push    rdi
0x180010210  sub     rsp, 20h
0x180010214  mov     rsi, r8
0x180010217  mov     rdi, rdx
0x18001021a  mov     rbx, rcx
0x18001021d  mov     [rsp+28h+arg_18], r8
0x180010222  cmp     rbx, rdi
0x180010225  jnz     short loc_18001023B
0x180010227  mov     rax, rsi
0x18001022a  mov     rbx, [rsp+28h+arg_0]
0x18001022f  mov     rsi, [rsp+28h+arg_8]
0x180010234  add     rsp, 20h
0x180010238  pop     rdi
0x180010239  retn
0x18001023b  mov     rdx, rbx
0x18001023e  mov     rcx, rsi
0x180010241  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010246  add     rsi, 28h ; '('
0x18001024a  mov     [rsp+28h+arg_10], rsi
0x18001024f  add     rbx, 28h ; '('
0x180010253  jmp     short loc_180010222
```
