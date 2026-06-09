# __vcrt_thread_attach

- ea: `0x180011c88`
- end: `0x180011c9c`
- name: `__vcrt_thread_attach`
- size: `20`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800103d8`

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
0x180011c88  sub     rsp, 28h
0x180011c8c  call    __vcrt_getptd_noexit
0x180011c91  test    rax, rax
0x180011c94  setnz   al
0x180011c97  add     rsp, 28h
0x180011c9b  retn
```
