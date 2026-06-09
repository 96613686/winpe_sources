# _GetImageBase

- ea: `0x140002a80`
- end: `0x140002a92`
- name: `_GetImageBase`
- size: `18`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x14000327c`
- `0x140003540`
- `0x140003b64`
- `0x140003e70`
- `0x140003f98`
- `0x140004b20`
- `0x140004e34`
- `0x140004f24`

## callees

- `0x140003008`

## pseudocode

```c
__int64 GetImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 96);
}

```

## disassembly

```asm
0x140002a80  sub     rsp, 28h
0x140002a84  call    __vcrt_getptd
0x140002a89  mov     rax, [rax+60h]
0x140002a8d  add     rsp, 28h
0x140002a91  retn
```
