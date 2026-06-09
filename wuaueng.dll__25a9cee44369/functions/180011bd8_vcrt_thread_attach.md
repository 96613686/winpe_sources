# __vcrt_thread_attach

- ea: `0x180011bd8`
- end: `0x180011bec`
- name: `__vcrt_thread_attach`
- size: `20`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fd4c`

## callees

- `0x180011fb8`

## pseudocode

```c
__vcrt_bool __cdecl _vcrt_thread_attach()
{
  return _vcrt_getptd_noexit() != 0;
}

```

## disassembly

```asm
0x180011bd8  sub     rsp, 28h
0x180011bdc  call    __vcrt_getptd_noexit
0x180011be1  test    rax, rax
0x180011be4  setnz   al
0x180011be7  add     rsp, 28h
0x180011beb  retn
```
