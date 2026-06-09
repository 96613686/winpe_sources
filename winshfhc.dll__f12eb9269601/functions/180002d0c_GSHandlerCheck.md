# __GSHandlerCheck

- ea: `0x180002d0c`
- end: `0x180002d29`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002d30`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheck(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _GSHandlerCheckCommon(a2, a4);
  return 1;
}

```

## disassembly

```asm
0x180002d0c  sub     rsp, 28h
0x180002d10  mov     r8, [r9+38h]
0x180002d14  mov     rcx, rdx
0x180002d17  mov     rdx, r9
0x180002d1a  call    __GSHandlerCheckCommon
0x180002d1f  mov     eax, 1
0x180002d24  add     rsp, 28h
0x180002d28  retn
```
