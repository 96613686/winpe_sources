# __scrt_dllmain_after_initialize_c

- ea: `0x180002aec`
- end: `0x180002b20`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002668`

## callees

- `0x180002aec`
- `0x180002ec0`
- `0x18000314c`
- `0x180003158`
- `0x1800031b2`
- `0x1800031ca`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode startup_argv_mode; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    startup_argv_mode = get_startup_argv_mode();
    if ( o__configure_narrow_argv_0(startup_argv_mode) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180002aec  sub     rsp, 28h
0x180002af0  call    __scrt_is_ucrt_dll_in_use
0x180002af5  test    eax, eax
0x180002af7  jz      short loc_180002B00
0x180002af9  call    __isa_available_init
0x180002afe  jmp     short loc_180002B19
0x180002b00  call    _get_startup_argv_mode
0x180002b05  mov     ecx, eax; mode
0x180002b07  call    _o__configure_narrow_argv_0
0x180002b0c  test    eax, eax
0x180002b0e  jz      short loc_180002B14
0x180002b10  xor     al, al
0x180002b12  jmp     short loc_180002B1B
0x180002b14  call    _initialize_narrow_environment
0x180002b19  mov     al, 1
0x180002b1b  add     rsp, 28h
0x180002b1f  retn
```
