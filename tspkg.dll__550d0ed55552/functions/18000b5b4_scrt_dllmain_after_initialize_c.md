# __scrt_dllmain_after_initialize_c

- ea: `0x18000b5b4`
- end: `0x18000b5e8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b238`

## callees

- `0x18000b5b4`
- `0x18000bb38`
- `0x18000bdc4`
- `0x18000bdd0`
- `0x18000c0d4`
- `0x18000c0f8`

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
0x18000b5b4  sub     rsp, 28h
0x18000b5b8  call    __scrt_is_ucrt_dll_in_use
0x18000b5bd  test    eax, eax
0x18000b5bf  jz      short loc_18000B5C8
0x18000b5c1  call    __isa_available_init
0x18000b5c6  jmp     short loc_18000B5E1
0x18000b5c8  call    _get_startup_argv_mode
0x18000b5cd  mov     ecx, eax; mode
0x18000b5cf  call    _o__configure_narrow_argv_0
0x18000b5d4  test    eax, eax
0x18000b5d6  jz      short loc_18000B5DC
0x18000b5d8  xor     al, al
0x18000b5da  jmp     short loc_18000B5E3
0x18000b5dc  call    _initialize_narrow_environment
0x18000b5e1  mov     al, 1
0x18000b5e3  add     rsp, 28h
0x18000b5e7  retn
```
