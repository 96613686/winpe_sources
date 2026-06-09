# __scrt_dllmain_crt_thread_attach

- ea: `0x180004e38`
- end: `0x180004e60`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004910`

## callees

- `0x180004e38`
- `0x1800055e8`

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
0x180004e38  sub     rsp, 28h
0x180004e3c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004e41  test    al, al
0x180004e43  jnz     short loc_180004E49
0x180004e45  xor     al, al
0x180004e47  jmp     short loc_180004E5B
0x180004e49  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004e4e  test    al, al
0x180004e50  jnz     short loc_180004E59
0x180004e52  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004e57  jmp     short loc_180004E45
0x180004e59  mov     al, 1
0x180004e5b  add     rsp, 28h
0x180004e5f  retn
```
