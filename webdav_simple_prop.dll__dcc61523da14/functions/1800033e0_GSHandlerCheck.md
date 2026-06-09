# __GSHandlerCheck

- ea: `0x1800033e0`
- end: `0x1800033fd`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003404`

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
0x1800033e0  sub     rsp, 28h
0x1800033e4  mov     r8, [r9+38h]
0x1800033e8  mov     rcx, rdx
0x1800033eb  mov     rdx, r9
0x1800033ee  call    __GSHandlerCheckCommon
0x1800033f3  mov     eax, 1
0x1800033f8  add     rsp, 28h
0x1800033fc  retn
```
