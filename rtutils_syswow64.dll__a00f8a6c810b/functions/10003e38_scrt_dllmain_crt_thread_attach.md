# ___scrt_dllmain_crt_thread_attach

- ea: `0x10003e38`
- end: `0x10003e57`
- name: `___scrt_dllmain_crt_thread_attach`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10003880`

## callees

- `0x10003e38`
- `0x1000470d`

## pseudocode

```c
char __scrt_dllmain_crt_thread_attach()
{
  if ( !(unsigned __int8)__scrt_stub_for_acrt_initialize() )
    return 0;
  if ( !(unsigned __int8)__scrt_stub_for_acrt_initialize() )
  {
    __scrt_stub_for_acrt_initialize();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x10003e38  call    ___scrt_stub_for_acrt_initialize
0x10003e3d  test    al, al
0x10003e3f  jnz     short loc_10003E44
0x10003e41  xor     al, al
0x10003e43  retn
0x10003e44  call    ___scrt_stub_for_acrt_initialize
0x10003e49  test    al, al
0x10003e4b  jnz     short loc_10003E54
0x10003e4d  call    ___scrt_stub_for_acrt_initialize
0x10003e52  jmp     short loc_10003E41
0x10003e54  mov     al, 1
0x10003e56  retn
```
