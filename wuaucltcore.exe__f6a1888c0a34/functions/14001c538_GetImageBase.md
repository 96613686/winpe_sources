# _GetImageBase

- ea: `0x14001c538`
- end: `0x14001c54a`
- name: `_GetImageBase`
- size: `18`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x14001cfb0`
- `0x14001d1a8`
- `0x14001d534`
- `0x14001d618`
- `0x14001d6fc`
- `0x14001e13c`
- `0x14001e3a4`
- `0x14001e6b0`
- `0x14001e7d8`
- `0x14001e920`
- `0x14001f740`
- `0x14001f8d0`
- `0x14001fc8c`
- `0x14001fd7c`

## callees

- `0x14001cbf8`

## pseudocode

```c
__int64 GetImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 96);
}

```

## disassembly

```asm
0x14001c538  sub     rsp, 28h
0x14001c53c  call    __vcrt_getptd
0x14001c541  mov     rax, [rax+60h]
0x14001c545  add     rsp, 28h
0x14001c549  retn
```
