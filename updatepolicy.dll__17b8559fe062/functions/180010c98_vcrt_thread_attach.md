# __vcrt_thread_attach

- ea: `0x180010c98`
- end: `0x180010cac`
- name: `__vcrt_thread_attach`
- size: `20`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ee78`

## callees

- `0x180011078`

## pseudocode

```c
__vcrt_bool __cdecl _vcrt_thread_attach()
{
  return _vcrt_getptd_noexit() != 0;
}

```

## disassembly

```asm
0x180010c98  sub     rsp, 28h
0x180010c9c  call    __vcrt_getptd_noexit
0x180010ca1  test    rax, rax
0x180010ca4  setnz   al
0x180010ca7  add     rsp, 28h
0x180010cab  retn
```
