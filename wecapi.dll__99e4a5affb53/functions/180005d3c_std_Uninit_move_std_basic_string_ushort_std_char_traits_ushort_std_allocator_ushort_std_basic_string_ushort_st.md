# std::_Uninit_move<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Wrap_alloc<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x180005d3c`
- end: `0x180005d97`
- name: `??$_Uninit_move@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009de0`

## callees

- `0x180005d3c`
- `0x180005da0`

## pseudocode

```c
__int64 __fastcall std::_Uninit_move<std::wstring *,std::wstring *,std::allocator<std::wstring>,std::wstring>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 i; // rdi

  for ( i = a1; i != a2; i += 32 )
  {
    std::_Wrap_alloc<std::allocator<std::wstring>>::construct<std::wstring,std::wstring>(a1, a3, i);
    a3 += 32;
  }
  return a3;
}

```

## disassembly

```asm
0x180005d3c  mov     rax, rsp
0x180005d3f  mov     [rax+8], rbx
0x180005d43  mov     [rax+10h], rsi
0x180005d47  mov     [rax+20h], r9
0x180005d4b  mov     [rax+18h], r8
0x180005d4f  push    rdi
0x180005d50  sub     rsp, 20h
0x180005d54  mov     rbx, r8
0x180005d57  mov     rsi, rdx
0x180005d5a  mov     rdi, rcx
0x180005d5d  mov     [rsp+28h+arg_18], rbx
0x180005d62  cmp     rcx, rdx
0x180005d65  jz      short loc_180005D84
0x180005d67  mov     r8, rdi
0x180005d6a  mov     rdx, rbx
0x180005d6d  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::_Wrap_alloc<std::allocator<std::wstring>>::construct<std::wstring,std::wstring>(std::wstring *,std::wstring &&)
0x180005d72  add     rbx, 20h ; ' '
0x180005d76  mov     [rsp+28h+arg_10], rbx
0x180005d7b  add     rdi, 20h ; ' '
0x180005d7f  cmp     rdi, rsi
0x180005d82  jnz     short loc_180005D67
0x180005d84  mov     rax, rbx
0x180005d87  mov     rbx, [rsp+28h+arg_0]
0x180005d8c  mov     rsi, [rsp+28h+arg_8]
0x180005d91  add     rsp, 20h
0x180005d95  pop     rdi
0x180005d96  retn
```
