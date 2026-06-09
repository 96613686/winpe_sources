# std::_Uninit_move<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x180010288`
- end: `0x1800102e1`
- name: `??$_Uninit_move@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014168`

## callees

- `0x180010288`
- `0x1800104c4`

## pseudocode

```c
__int64 __fastcall std::_Uninit_move<std::wstring *,std::wstring *,std::allocator<std::wstring>,std::wstring>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  while ( a1 != a2 )
  {
    std::wstring::wstring(a3, a1);
    a3 += 40;
    a1 += 40;
  }
  return a3;
}

```

## disassembly

```asm
0x180010288  mov     rax, rsp
0x18001028b  mov     [rax+8], rbx
0x18001028f  mov     [rax+10h], rsi
0x180010293  mov     [rax+20h], r9
0x180010297  mov     [rax+18h], r8
0x18001029b  push    rdi
0x18001029c  sub     rsp, 20h
0x1800102a0  mov     rbx, r8
0x1800102a3  mov     rsi, rdx
0x1800102a6  mov     rdi, rcx
0x1800102a9  mov     [rsp+28h+arg_18], rbx
0x1800102ae  cmp     rdi, rsi
0x1800102b1  jz      short loc_1800102CD
0x1800102b3  mov     rdx, rdi
0x1800102b6  mov     rcx, rbx
0x1800102b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800102be  add     rbx, 28h ; '('
0x1800102c2  mov     [rsp+28h+arg_10], rbx
0x1800102c7  add     rdi, 28h ; '('
0x1800102cb  jmp     short loc_1800102AE
0x1800102cd  mov     rax, rbx
0x1800102d0  mov     rbx, [rsp+28h+arg_0]
0x1800102d5  mov     rsi, [rsp+28h+arg_8]
0x1800102da  add     rsp, 20h
0x1800102de  pop     rdi
0x1800102df  retn
```
