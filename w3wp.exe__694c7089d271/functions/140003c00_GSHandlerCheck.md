# __GSHandlerCheck

- ea: `0x140003c00`
- end: `0x140003c1d`
- name: `__GSHandlerCheck`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003c24`

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
0x140003c00  sub     rsp, 28h
0x140003c04  mov     r8, [r9+38h]
0x140003c08  mov     rcx, rdx
0x140003c0b  mov     rdx, r9
0x140003c0e  call    __GSHandlerCheckCommon
0x140003c13  mov     eax, 1
0x140003c18  add     rsp, 28h
0x140003c1c  retn
```
