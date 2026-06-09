# __scrt_initialize_crt

- ea: `0x180002c28`
- end: `0x180002c62`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002668`

## callees

- `0x180002c28`
- `0x180002ec0`
- `0x18000325c`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  if ( !a1 )
    byte_1800070F1 = 1;
  _isa_available_init();
  if ( !_scrt_stub_for_acrt_uninitialize_critical() )
    return 0;
  if ( !_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180002c28  sub     rsp, 28h
0x180002c2c  test    ecx, ecx
0x180002c2e  jnz     short loc_180002C37
0x180002c30  mov     cs:byte_1800070F1, 1
0x180002c37  call    __isa_available_init
0x180002c3c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002c41  test    al, al
0x180002c43  jnz     short loc_180002C49
0x180002c45  xor     al, al
0x180002c47  jmp     short loc_180002C5D
0x180002c49  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002c4e  test    al, al
0x180002c50  jnz     short loc_180002C5B
0x180002c52  xor     ecx, ecx
0x180002c54  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002c59  jmp     short loc_180002C45
0x180002c5b  mov     al, 1
0x180002c5d  add     rsp, 28h
0x180002c61  retn
```
