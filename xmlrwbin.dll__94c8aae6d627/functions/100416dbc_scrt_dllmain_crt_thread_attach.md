# __scrt_dllmain_crt_thread_attach

- ea: `0x100416dbc`
- end: `0x100416de4`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1004165c0`

## callees

- `0x100416dbc`
- `0x1004175d0`
- `0x1004175ec`
- `0x10041b060`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !_vcrt_thread_attach() )
    return 0;
  if ( !_acrt_thread_attach() )
  {
    _vcrt_thread_detach();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x100416dbc  sub     rsp, 28h
0x100416dc0  call    __vcrt_thread_attach
0x100416dc5  test    al, al
0x100416dc7  jnz     short loc_100416DCD
0x100416dc9  xor     al, al
0x100416dcb  jmp     short loc_100416DDF
0x100416dcd  call    __acrt_thread_attach
0x100416dd2  test    al, al
0x100416dd4  jnz     short loc_100416DDD
0x100416dd6  call    __vcrt_thread_detach
0x100416ddb  jmp     short loc_100416DC9
0x100416ddd  mov     al, 1
0x100416ddf  add     rsp, 28h
0x100416de3  retn
```
