# tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)

- ea: `0x180005c20`
- end: `0x180005c51`
- name: `??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ`
- size: `49`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180006440`
- `0x18000765c`
- `0x1800080d8`
- `0x180008528`
- `0x180008668`
- `0x18000899c`
- `0x18000fb24`
- `0x18000fc94`
- `0x18001275c`
- `0x18001326c`
- `0x180013ce8`
- `0x1800148a8`

## callees

- `0x180005b40`

## pseudocode

```c
__int64 tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
        __int64 a1,
        __int64 a2,
        ...)
{
  _WORD *v2; // rdx
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  v2 = *(_WORD **)a1;
  *(_QWORD *)(a1 + 8) = *(_QWORD *)a1;
  *v2 = 0;
  return tlx::_AppendVsprintImpl<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,unsigned short>(
           a1,
           a2,
           (__int64 *)va);
}

```

## disassembly

```asm
0x180005c20  mov     r11, rsp
0x180005c23  mov     [r11+10h], rdx
0x180005c27  mov     [r11+18h], r8
0x180005c2b  mov     [r11+20h], r9
0x180005c2f  sub     rsp, 38h
0x180005c33  mov     rdx, [rcx]
0x180005c36  lea     r8, [r11+18h]
0x180005c3a  mov     [rcx+8], rdx
0x180005c3e  xor     eax, eax
0x180005c40  mov     [rdx], ax
0x180005c43  mov     rdx, [r11+10h]
0x180005c47  call    ??$_AppendVsprintImpl@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@G@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGPEAD@Z; tlx::_AppendVsprintImpl<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,ushort>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,char *)
0x180005c4c  add     rsp, 38h
0x180005c50  retn
```
