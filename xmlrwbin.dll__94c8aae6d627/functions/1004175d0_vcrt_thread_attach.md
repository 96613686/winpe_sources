# __vcrt_thread_attach

- ea: `0x1004175d0`
- end: `0x1004175e4`
- name: `__vcrt_thread_attach`
- size: `20`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100416dbc`

## callees

- `0x100417a9c`

## pseudocode

```c
__vcrt_bool __cdecl _vcrt_thread_attach()
{
  return _vcrt_getptd_noexit() != 0;
}

```

## disassembly

```asm
0x1004175d0  sub     rsp, 28h
0x1004175d4  call    __vcrt_getptd_noexit
0x1004175d9  test    rax, rax
0x1004175dc  setnz   al
0x1004175df  add     rsp, 28h
0x1004175e3  retn
```
