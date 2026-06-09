# lafe_getprogname

- ea: `0x1400071e0`
- end: `0x1400071e8`
- name: `lafe_getprogname`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140001ee4`
- `0x140003768`

## pseudocode

```c
__int64 lafe_getprogname()
{
  return qword_14000F118;
}

```

## disassembly

```asm
0x1400071e0  mov     rax, cs:qword_14000F118
0x1400071e7  retn
```
