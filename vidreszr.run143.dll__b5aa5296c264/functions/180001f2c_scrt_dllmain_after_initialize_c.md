# __scrt_dllmain_after_initialize_c

- ea: `0x180001f2c`
- end: `0x180001f60`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001aa8`

## callees

- `0x180001f2c`
- `0x180002300`
- `0x18000258c`
- `0x180002598`
- `0x1800025fe`
- `0x180002616`

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
0x180001f2c  sub     rsp, 28h
0x180001f30  call    __scrt_is_ucrt_dll_in_use
0x180001f35  test    eax, eax
0x180001f37  jz      short loc_180001F40
0x180001f39  call    __isa_available_init
0x180001f3e  jmp     short loc_180001F59
0x180001f40  call    _get_startup_argv_mode
0x180001f45  mov     ecx, eax; mode
0x180001f47  call    _o__configure_narrow_argv_0
0x180001f4c  test    eax, eax
0x180001f4e  jz      short loc_180001F54
0x180001f50  xor     al, al
0x180001f52  jmp     short loc_180001F5B
0x180001f54  call    _initialize_narrow_environment
0x180001f59  mov     al, 1
0x180001f5b  add     rsp, 28h
0x180001f5f  retn
```
