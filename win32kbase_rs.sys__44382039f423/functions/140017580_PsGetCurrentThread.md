# PsGetCurrentThread

- ea: `0x140017580`
- end: `0x14001758a`
- name: `PsGetCurrentThread`
- size: `10`
- prototype: `PETHREAD(void)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14001778c`

## pseudocode

```c
PETHREAD PsGetCurrentThread(void)
{
  return KeGetCurrentThread();
}

```

## disassembly

```asm
0x140017580  mov     rax, gs:188h
0x140017589  retn
```
