# __scrt_dllmain_crt_thread_attach

- ea: `0x1800022e0`
- end: `0x180002308`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001ec0`

## callees

- `0x1800022e0`
- `0x18000318c`

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
0x1800022e0  sub     rsp, 28h
0x1800022e4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800022e9  test    al, al
0x1800022eb  jnz     short loc_1800022F1
0x1800022ed  xor     al, al
0x1800022ef  jmp     short loc_180002303
0x1800022f1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800022f6  test    al, al
0x1800022f8  jnz     short loc_180002301
0x1800022fa  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800022ff  jmp     short loc_1800022ED
0x180002301  mov     al, 1
0x180002303  add     rsp, 28h
0x180002307  retn
```
