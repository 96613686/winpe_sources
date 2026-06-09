# __scrt_dllmain_after_initialize_c

- ea: `0x180002680`
- end: `0x1800026b4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800022f8`

## callees

- `0x180002680`
- `0x180002bbc`
- `0x180002e48`
- `0x180002e54`
- `0x180002ec6`
- `0x180002eea`

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
0x180002680  sub     rsp, 28h
0x180002684  call    __scrt_is_ucrt_dll_in_use
0x180002689  test    eax, eax
0x18000268b  jz      short loc_180002694
0x18000268d  call    __isa_available_init
0x180002692  jmp     short loc_1800026AD
0x180002694  call    _get_startup_argv_mode
0x180002699  mov     ecx, eax; mode
0x18000269b  call    _o__configure_narrow_argv_0
0x1800026a0  test    eax, eax
0x1800026a2  jz      short loc_1800026A8
0x1800026a4  xor     al, al
0x1800026a6  jmp     short loc_1800026AF
0x1800026a8  call    _initialize_narrow_environment
0x1800026ad  mov     al, 1
0x1800026af  add     rsp, 28h
0x1800026b3  retn
```
