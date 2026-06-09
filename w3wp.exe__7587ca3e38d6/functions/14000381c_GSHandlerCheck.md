# __GSHandlerCheck

- ea: `0x14000381c`
- end: `0x140003839`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003840`

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
0x14000381c  sub     rsp, 28h
0x140003820  mov     r8, [r9+38h]
0x140003824  mov     rcx, rdx
0x140003827  mov     rdx, r9
0x14000382a  call    __GSHandlerCheckCommon
0x14000382f  mov     eax, 1
0x140003834  add     rsp, 28h
0x140003838  retn
```
