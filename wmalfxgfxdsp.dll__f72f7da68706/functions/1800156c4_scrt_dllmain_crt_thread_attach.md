# __scrt_dllmain_crt_thread_attach

- ea: `0x1800156c4`
- end: `0x1800156ec`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800151c0`

## callees

- `0x1800156c4`
- `0x180075af4`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800156c4  sub     rsp, 28h
0x1800156c8  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800156cd  test    al, al
0x1800156cf  jnz     short loc_1800156D5
0x1800156d1  xor     al, al
0x1800156d3  jmp     short loc_1800156E7
0x1800156d5  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800156da  test    al, al
0x1800156dc  jnz     short loc_1800156E5
0x1800156de  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800156e3  jmp     short loc_1800156D1
0x1800156e5  mov     al, 1
0x1800156e7  add     rsp, 28h
0x1800156eb  retn
```
