# __vcrt_thread_attach

- ea: `0x180011c28`
- end: `0x180011c3c`
- name: `__vcrt_thread_attach`
- size: `20`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fd9c`

## callees

- `0x180012008`

## pseudocode

```c
__vcrt_bool __cdecl _vcrt_thread_attach()
{
  return _vcrt_getptd_noexit() != 0;
}

```

## disassembly

```asm
0x180011c28  sub     rsp, 28h
0x180011c2c  call    __vcrt_getptd_noexit
0x180011c31  test    rax, rax
0x180011c34  setnz   al
0x180011c37  add     rsp, 28h
0x180011c3b  retn
```
