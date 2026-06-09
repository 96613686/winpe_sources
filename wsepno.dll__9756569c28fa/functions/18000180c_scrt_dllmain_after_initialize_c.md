# __scrt_dllmain_after_initialize_c

- ea: `0x18000180c`
- end: `0x180001840`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001448`

## callees

- `0x18000180c`
- `0x180001dd0`
- `0x18000205c`
- `0x180002068`
- `0x18000214e`
- `0x180002172`

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
0x18000180c  sub     rsp, 28h
0x180001810  call    __scrt_is_ucrt_dll_in_use
0x180001815  test    eax, eax
0x180001817  jz      short loc_180001820
0x180001819  call    __isa_available_init
0x18000181e  jmp     short loc_180001839
0x180001820  call    _get_startup_argv_mode
0x180001825  mov     ecx, eax; mode
0x180001827  call    _o__configure_narrow_argv_0
0x18000182c  test    eax, eax
0x18000182e  jz      short loc_180001834
0x180001830  xor     al, al
0x180001832  jmp     short loc_18000183B
0x180001834  call    _initialize_narrow_environment
0x180001839  mov     al, 1
0x18000183b  add     rsp, 28h
0x18000183f  retn
```
