# __scrt_dllmain_crt_thread_attach

- ea: `0x18000c404`
- end: `0x18000c42c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000bed0`

## callees

- `0x18000c404`
- `0x18000d7f4`

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
0x18000c404  sub     rsp, 28h
0x18000c408  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000c40d  test    al, al
0x18000c40f  jnz     short loc_18000C415
0x18000c411  xor     al, al
0x18000c413  jmp     short loc_18000C427
0x18000c415  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000c41a  test    al, al
0x18000c41c  jnz     short loc_18000C425
0x18000c41e  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000c423  jmp     short loc_18000C411
0x18000c425  mov     al, 1
0x18000c427  add     rsp, 28h
0x18000c42b  retn
```
