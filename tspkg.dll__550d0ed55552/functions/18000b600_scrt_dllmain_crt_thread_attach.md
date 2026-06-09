# __scrt_dllmain_crt_thread_attach

- ea: `0x18000b600`
- end: `0x18000b628`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b1e0`

## callees

- `0x18000b600`
- `0x18000c8d8`

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
0x18000b600  sub     rsp, 28h
0x18000b604  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000b609  test    al, al
0x18000b60b  jnz     short loc_18000B611
0x18000b60d  xor     al, al
0x18000b60f  jmp     short loc_18000B623
0x18000b611  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000b616  test    al, al
0x18000b618  jnz     short loc_18000B621
0x18000b61a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000b61f  jmp     short loc_18000B60D
0x18000b621  mov     al, 1
0x18000b623  add     rsp, 28h
0x18000b627  retn
```
