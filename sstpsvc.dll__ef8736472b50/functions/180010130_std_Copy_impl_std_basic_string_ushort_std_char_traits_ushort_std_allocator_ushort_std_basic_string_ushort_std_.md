# std::_Copy_impl<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180010130`
- end: `0x180010180`
- name: `??$_Copy_impl@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010998`

## callees

- `0x180010130`
- `0x180013610`

## pseudocode

```c
__int64 __fastcall std::_Copy_impl<std::wstring *,std::wstring *>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 i; // rdi

  for ( i = a1; i != a2; i += 40 )
  {
    std::wstring::assign(a3, i, 0, -1);
    a3 += 40;
  }
  return a3;
}

```

## disassembly

```asm
0x180010130  mov     [rsp+arg_0], rbx
0x180010135  mov     [rsp+arg_8], rsi
0x18001013a  push    rdi
0x18001013b  sub     rsp, 20h
0x18001013f  mov     rbx, r8
0x180010142  mov     rsi, rdx
0x180010145  mov     rdi, rcx
0x180010148  cmp     rcx, rdx
0x18001014b  jz      short loc_18001016C
0x18001014d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180010151  xor     r8d, r8d
0x180010154  mov     rdx, rdi
0x180010157  mov     rcx, rbx
0x18001015a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001015f  add     rbx, 28h ; '('
0x180010163  add     rdi, 28h ; '('
0x180010167  cmp     rdi, rsi
0x18001016a  jnz     short loc_18001014D
0x18001016c  mov     rsi, [rsp+28h+arg_8]
0x180010171  mov     rax, rbx
0x180010174  mov     rbx, [rsp+28h+arg_0]
0x180010179  add     rsp, 20h
0x18001017d  pop     rdi
0x18001017e  retn
```
