# __acrt_thread_attach

- ea: `0x10041b060`
- end: `0x10041b074`
- name: `__acrt_thread_attach`
- size: `20`
- prototype: `__crt_bool __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100416dbc`

## callees

- `0x10041b940`

## pseudocode

```c
__crt_bool __cdecl _acrt_thread_attach()
{
  return _acrt_getptd_noexit() != 0;
}

```

## disassembly

```asm
0x10041b060  sub     rsp, 28h
0x10041b064  call    __acrt_getptd_noexit
0x10041b069  test    rax, rax
0x10041b06c  setnz   al
0x10041b06f  add     rsp, 28h
0x10041b073  retn
```
