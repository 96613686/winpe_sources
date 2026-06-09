# __scrt_dllmain_after_initialize_c

- ea: `0x180024aec`
- end: `0x180024b20`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180024738`

## callees

- `0x180024aec`
- `0x180025160`
- `0x1800253ec`
- `0x1800253f8`
- `0x180025476`
- `0x18002549a`

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
0x180024aec  sub     rsp, 28h
0x180024af0  call    __scrt_is_ucrt_dll_in_use
0x180024af5  test    eax, eax
0x180024af7  jz      short loc_180024B00
0x180024af9  call    __isa_available_init
0x180024afe  jmp     short loc_180024B19
0x180024b00  call    _get_startup_argv_mode
0x180024b05  mov     ecx, eax; mode
0x180024b07  call    _o__configure_narrow_argv_0
0x180024b0c  test    eax, eax
0x180024b0e  jz      short loc_180024B14
0x180024b10  xor     al, al
0x180024b12  jmp     short loc_180024B1B
0x180024b14  call    _initialize_narrow_environment
0x180024b19  mov     al, 1
0x180024b1b  add     rsp, 28h
0x180024b1f  retn
```
