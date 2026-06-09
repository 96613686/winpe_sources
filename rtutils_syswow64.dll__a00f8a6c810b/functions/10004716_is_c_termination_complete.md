# __is_c_termination_complete

- ea: `0x10004716`
- end: `0x10004719`
- name: `__is_c_termination_complete`
- size: `3`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x10003eac`

## pseudocode

```c
int __cdecl _is_c_termination_complete()
{
  return 0;
}

```

## disassembly

```asm
0x10004716  xor     eax, eax
0x10004718  retn
```
