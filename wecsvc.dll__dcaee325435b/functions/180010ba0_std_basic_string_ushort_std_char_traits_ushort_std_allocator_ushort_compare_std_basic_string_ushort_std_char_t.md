# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::compare(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180010ba0`
- end: `0x180010bc9`
- name: `?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006e6c`
- `0x180007320`
- `0x1800075c8`
- `0x18000840c`
- `0x180010f80`
- `0x18001102c`
- `0x180011098`
- `0x18001718c`

## callees

- `0x180010ba0`
- `0x180010bd0`

## pseudocode

```c
__int64 __fastcall std::wstring::compare(_QWORD *a1, __int64 a2)
{
  unsigned __int64 v2; // rax

  v2 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) >= 8u )
    a2 = *(_QWORD *)a2;
  return std::wstring::compare(a1, a2, a1[2], (_WORD *)a2, v2);
}

```

## disassembly

```asm
0x180010ba0  sub     rsp, 38h
0x180010ba4  mov     rax, [rdx+10h]
0x180010ba8  cmp     qword ptr [rdx+18h], 8
0x180010bad  jb      short loc_180010BB2
0x180010baf  mov     rdx, [rdx]
0x180010bb2  mov     [rsp+38h+var_18], rax
0x180010bb7  mov     r9, rdx
0x180010bba  mov     r8, [rcx+10h]
0x180010bbe  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0PEBG0@Z; std::wstring::compare(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x180010bc3  nop
0x180010bc4  add     rsp, 38h
0x180010bc8  retn
```
