# std::_Copy_impl<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18000f388`
- end: `0x18000f3d7`
- name: `??$_Copy_impl@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00@Z`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fbb0`

## callees

- `0x18000f388`
- `0x180012644`

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
0x18000f388  mov     [rsp+arg_0], rbx
0x18000f38d  mov     [rsp+arg_8], rsi
0x18000f392  push    rdi
0x18000f393  sub     rsp, 20h
0x18000f397  mov     rbx, r8
0x18000f39a  mov     rsi, rdx
0x18000f39d  mov     rdi, rcx
0x18000f3a0  cmp     rcx, rdx
0x18000f3a3  jz      short loc_18000F3C4
0x18000f3a5  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000f3a9  xor     r8d, r8d
0x18000f3ac  mov     rdx, rdi
0x18000f3af  mov     rcx, rbx
0x18000f3b2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000f3b7  add     rbx, 28h ; '('
0x18000f3bb  add     rdi, 28h ; '('
0x18000f3bf  cmp     rdi, rsi
0x18000f3c2  jnz     short loc_18000F3A5
0x18000f3c4  mov     rsi, [rsp+28h+arg_8]
0x18000f3c9  mov     rax, rbx
0x18000f3cc  mov     rbx, [rsp+28h+arg_0]
0x18000f3d1  add     rsp, 20h
0x18000f3d5  pop     rdi
0x18000f3d6  retn
```
