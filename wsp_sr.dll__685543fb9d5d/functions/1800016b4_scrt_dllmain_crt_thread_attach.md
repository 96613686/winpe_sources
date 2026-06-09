# __scrt_dllmain_crt_thread_attach

- ea: `0x1800016b4`
- end: `0x1800016dc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001170`

## callees

- `0x1800016b4`
- `0x1800029a8`

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
0x1800016b4  sub     rsp, 28h
0x1800016b8  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016bd  test    al, al
0x1800016bf  jnz     short loc_1800016C5
0x1800016c1  xor     al, al
0x1800016c3  jmp     short loc_1800016D7
0x1800016c5  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016ca  test    al, al
0x1800016cc  jnz     short loc_1800016D5
0x1800016ce  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016d3  jmp     short loc_1800016C1
0x1800016d5  mov     al, 1
0x1800016d7  add     rsp, 28h
0x1800016db  retn
```
