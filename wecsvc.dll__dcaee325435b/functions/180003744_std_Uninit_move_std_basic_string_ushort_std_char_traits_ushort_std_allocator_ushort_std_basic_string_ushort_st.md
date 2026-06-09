# std::_Uninit_move<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Wrap_alloc<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x180003744`
- end: `0x18000379f`
- name: `??$_Uninit_move@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800061b0`

## callees

- `0x180003744`
- `0x1800037a8`

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
    std::wstring::wstring(a3, i);
    a3 += 32;
  }
  return a3;
}

```

## disassembly

```asm
0x180003744  mov     rax, rsp
0x180003747  mov     [rax+8], rbx
0x18000374b  mov     [rax+10h], rsi
0x18000374f  mov     [rax+20h], r9
0x180003753  mov     [rax+18h], r8
0x180003757  push    rdi
0x180003758  sub     rsp, 20h
0x18000375c  mov     rbx, r8
0x18000375f  mov     rsi, rdx
0x180003762  mov     rdi, rcx
0x180003765  mov     [rsp+28h+arg_18], rbx
0x18000376a  cmp     rcx, rdx
0x18000376d  jz      short loc_18000378C
0x18000376f  mov     rdx, rdi
0x180003772  mov     rcx, rbx
0x180003775  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000377a  add     rbx, 20h ; ' '
0x18000377e  mov     [rsp+28h+arg_10], rbx
0x180003783  add     rdi, 20h ; ' '
0x180003787  cmp     rdi, rsi
0x18000378a  jnz     short loc_18000376F
0x18000378c  mov     rax, rbx
0x18000378f  mov     rbx, [rsp+28h+arg_0]
0x180003794  mov     rsi, [rsp+28h+arg_8]
0x180003799  add     rsp, 20h
0x18000379d  pop     rdi
0x18000379e  retn
```
