# __GSHandlerCheck

- ea: `0x1400018c4`
- end: `0x1400018e1`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400018e8`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheck(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _GSHandlerCheckCommon(a2, a4, *(_QWORD *)(a4 + 56));
  return 1;
}

```

## disassembly

```asm
0x1400018c4  sub     rsp, 28h
0x1400018c8  mov     r8, [r9+38h]
0x1400018cc  mov     rcx, rdx
0x1400018cf  mov     rdx, r9
0x1400018d2  call    __GSHandlerCheckCommon
0x1400018d7  mov     eax, 1
0x1400018dc  add     rsp, 28h
0x1400018e0  retn
```
