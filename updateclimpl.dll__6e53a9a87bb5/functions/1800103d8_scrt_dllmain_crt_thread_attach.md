# __scrt_dllmain_crt_thread_attach

- ea: `0x1800103d8`
- end: `0x180010400`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180010740`

## callees

- `0x1800103d8`
- `0x180011c88`
- `0x180011ca4`
- `0x1800147cc`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !_vcrt_thread_attach() )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _vcrt_thread_detach();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800103d8  sub     rsp, 28h
0x1800103dc  call    __vcrt_thread_attach
0x1800103e1  test    al, al
0x1800103e3  jnz     short loc_1800103E9
0x1800103e5  xor     al, al
0x1800103e7  jmp     short loc_1800103FB
0x1800103e9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800103ee  test    al, al
0x1800103f0  jnz     short loc_1800103F9
0x1800103f2  call    __vcrt_thread_detach
0x1800103f7  jmp     short loc_1800103E5
0x1800103f9  mov     al, 1
0x1800103fb  add     rsp, 28h
0x1800103ff  retn
```
