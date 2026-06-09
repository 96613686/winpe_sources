# __GSHandlerCheck

- ea: `0x18000288c`
- end: `0x1800028a9`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800028b0`

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
0x18000288c  sub     rsp, 28h
0x180002890  mov     r8, [r9+38h]
0x180002894  mov     rcx, rdx
0x180002897  mov     rdx, r9
0x18000289a  call    __GSHandlerCheckCommon
0x18000289f  mov     eax, 1
0x1800028a4  add     rsp, 28h
0x1800028a8  retn
```
