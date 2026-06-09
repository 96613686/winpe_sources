# __scrt_dllmain_crt_thread_attach

- ea: `0x18000cb2c`
- end: `0x18000cb54`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c620`

## callees

- `0x18000cb2c`
- `0x18000dd84`

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
0x18000cb2c  sub     rsp, 28h
0x18000cb30  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000cb35  test    al, al
0x18000cb37  jnz     short loc_18000CB3D
0x18000cb39  xor     al, al
0x18000cb3b  jmp     short loc_18000CB4F
0x18000cb3d  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000cb42  test    al, al
0x18000cb44  jnz     short loc_18000CB4D
0x18000cb46  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000cb4b  jmp     short loc_18000CB39
0x18000cb4d  mov     al, 1
0x18000cb4f  add     rsp, 28h
0x18000cb53  retn
```
