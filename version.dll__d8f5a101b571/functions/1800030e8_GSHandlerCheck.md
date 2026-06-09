# __GSHandlerCheck

- ea: `0x1800030e8`
- end: `0x180003105`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000310c`

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
0x1800030e8  sub     rsp, 28h
0x1800030ec  mov     r8, [r9+38h]
0x1800030f0  mov     rcx, rdx
0x1800030f3  mov     rdx, r9
0x1800030f6  call    __GSHandlerCheckCommon
0x1800030fb  mov     eax, 1
0x180003100  add     rsp, 28h
0x180003104  retn
```
