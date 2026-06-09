# _GetThrowImageBase

- ea: `0x140002a98`
- end: `0x140002aaa`
- name: `_GetThrowImageBase`
- size: `18`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000327c`
- `0x140003478`
- `0x140003624`
- `0x140003e70`
- `0x140003f98`
- `0x1400040e0`
- `0x140004e34`

## callees

- `0x140003008`

## pseudocode

```c
__int64 GetThrowImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 104);
}

```

## disassembly

```asm
0x140002a98  sub     rsp, 28h
0x140002a9c  call    __vcrt_getptd
0x140002aa1  mov     rax, [rax+68h]
0x140002aa5  add     rsp, 28h
0x140002aa9  retn
```
