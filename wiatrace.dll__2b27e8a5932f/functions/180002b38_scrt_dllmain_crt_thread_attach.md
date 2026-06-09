# __scrt_dllmain_crt_thread_attach

- ea: `0x180002b38`
- end: `0x180002b60`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002610`

## callees

- `0x180002b38`
- `0x18000325c`

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
0x180002b38  sub     rsp, 28h
0x180002b3c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002b41  test    al, al
0x180002b43  jnz     short loc_180002B49
0x180002b45  xor     al, al
0x180002b47  jmp     short loc_180002B5B
0x180002b49  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002b4e  test    al, al
0x180002b50  jnz     short loc_180002B59
0x180002b52  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002b57  jmp     short loc_180002B45
0x180002b59  mov     al, 1
0x180002b5b  add     rsp, 28h
0x180002b5f  retn
```
