# std::_Uninit_copy<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18001019c`
- end: `0x1800101f5`
- name: `??$_Uninit_copy@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010998`

## callees

- `0x18001019c`
- `0x1800104f4`

## pseudocode

```c
__int64 __fastcall std::_Uninit_copy<std::wstring *,std::wstring *,std::allocator<std::wstring>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdi
  __int64 result; // rax
  __int64 i; // rbx
  __int64 v8; // [rsp+40h] [rbp+18h]

  v8 = a3;
  v3 = a3;
  v5 = a1;
  try
  {
    while ( v5 != a2 )
    {
      std::wstring::wstring(v3, v5);
      v3 += 40;
      v8 = v3;
      v5 += 40;
    }
    result = v3;
  }
  catch ( ... )
  {
    for ( i = a3; i != v8; i += 40 )
      std::_Dest_val<std::allocator<std::wstring>,std::wstring>(a1, i);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18001019c  mov     rax, rsp
0x18001019f  mov     [rax+8], rbx
0x1800101a3  mov     [rax+10h], rsi
0x1800101a7  mov     [rax+20h], r9
0x1800101ab  mov     [rax+18h], r8
0x1800101af  push    rdi
0x1800101b0  sub     rsp, 20h
0x1800101b4  mov     rbx, r8
0x1800101b7  mov     rsi, rdx
0x1800101ba  mov     rdi, rcx
0x1800101bd  mov     [rsp+28h+arg_18], rbx
0x1800101c2  cmp     rdi, rsi
0x1800101c5  jz      short loc_1800101E1
0x1800101c7  mov     rdx, rdi
0x1800101ca  mov     rcx, rbx
0x1800101cd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800101d2  add     rbx, 28h ; '('
0x1800101d6  mov     [rsp+28h+arg_10], rbx
0x1800101db  add     rdi, 28h ; '('
0x1800101df  jmp     short loc_1800101C2
0x1800101e1  mov     rax, rbx
0x1800101e4  mov     rbx, [rsp+28h+arg_0]
0x1800101e9  mov     rsi, [rsp+28h+arg_8]
0x1800101ee  add     rsp, 20h
0x1800101f2  pop     rdi
0x1800101f3  retn
```
