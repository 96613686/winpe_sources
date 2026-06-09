# __scrt_dllmain_after_initialize_c

- ea: `0x100416d64`
- end: `0x100416d98`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x100416618`

## callees

- `0x1004163dc`
- `0x100416d64`
- `0x100417300`
- `0x10041730c`
- `0x10041a674`
- `0x10041aa68`

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
    if ( configure_narrow_argv(startup_argv_mode) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x100416d64  sub     rsp, 28h
0x100416d68  call    __scrt_is_ucrt_dll_in_use
0x100416d6d  test    eax, eax
0x100416d6f  jz      short loc_100416D78
0x100416d71  call    __isa_available_init
0x100416d76  jmp     short loc_100416D91
0x100416d78  call    _get_startup_argv_mode
0x100416d7d  mov     ecx, eax; mode
0x100416d7f  call    _configure_narrow_argv
0x100416d84  test    eax, eax
0x100416d86  jz      short loc_100416D8C
0x100416d88  xor     al, al
0x100416d8a  jmp     short loc_100416D93
0x100416d8c  call    _initialize_narrow_environment
0x100416d91  mov     al, 1
0x100416d93  add     rsp, 28h
0x100416d97  retn
```
