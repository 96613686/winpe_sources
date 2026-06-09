# __scrt_dllmain_crt_thread_attach

- ea: `0x1800017a8`
- end: `0x1800017d0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x1800017a8`
- `0x180001f88`

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
0x1800017a8  sub     rsp, 28h
0x1800017ac  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017b1  test    al, al
0x1800017b3  jnz     short loc_1800017B9
0x1800017b5  xor     al, al
0x1800017b7  jmp     short loc_1800017CB
0x1800017b9  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017be  test    al, al
0x1800017c0  jnz     short loc_1800017C9
0x1800017c2  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800017c7  jmp     short loc_1800017B5
0x1800017c9  mov     al, 1
0x1800017cb  add     rsp, 28h
0x1800017cf  retn
```
