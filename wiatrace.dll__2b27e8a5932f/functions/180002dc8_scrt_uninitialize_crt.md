# __scrt_uninitialize_crt

- ea: `0x180002dc8`
- end: `0x180002df1`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002768`

## callees

- `0x180002dc8`
- `0x18000325c`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_1800070F1 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    _scrt_stub_for_acrt_uninitialize_critical();
  }
  return 1;
}

```

## disassembly

```asm
0x180002dc8  push    rbx
0x180002dca  sub     rsp, 20h
0x180002dce  cmp     cs:byte_1800070F1, 0
0x180002dd5  mov     bl, cl
0x180002dd7  jz      short loc_180002DDD
0x180002dd9  test    dl, dl
0x180002ddb  jnz     short loc_180002DE9
0x180002ddd  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002de2  mov     cl, bl
0x180002de4  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002de9  mov     al, 1
0x180002deb  add     rsp, 20h
0x180002def  pop     rbx
0x180002df0  retn
```
