# __vcrt_thread_attach

- ea: `0x1800031dc`
- end: `0x1800031f0`
- name: `__vcrt_thread_attach`
- size: `20`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001640`

## callees

- `0x1800033f8`

## pseudocode

```c
__vcrt_bool __cdecl _vcrt_thread_attach()
{
  return _vcrt_getptd_noexit() != 0;
}

```

## disassembly

```asm
0x1800031dc  sub     rsp, 28h
0x1800031e0  call    __vcrt_getptd_noexit
0x1800031e5  test    rax, rax
0x1800031e8  setnz   al
0x1800031eb  add     rsp, 28h
0x1800031ef  retn
```
