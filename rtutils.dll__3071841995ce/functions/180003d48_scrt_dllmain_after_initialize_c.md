# __scrt_dllmain_after_initialize_c

- ea: `0x180003d48`
- end: `0x180003d7c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180003898`

## callees

- `0x180003d48`
- `0x1800040f8`
- `0x180004384`
- `0x180004390`
- `0x18000441a`
- `0x180004432`

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
0x180003d48  sub     rsp, 28h
0x180003d4c  call    __scrt_is_ucrt_dll_in_use
0x180003d51  test    eax, eax
0x180003d53  jz      short loc_180003D5C
0x180003d55  call    __isa_available_init
0x180003d5a  jmp     short loc_180003D75
0x180003d5c  call    _get_startup_argv_mode
0x180003d61  mov     ecx, eax; mode
0x180003d63  call    _o__configure_narrow_argv_0
0x180003d68  test    eax, eax
0x180003d6a  jz      short loc_180003D70
0x180003d6c  xor     al, al
0x180003d6e  jmp     short loc_180003D77
0x180003d70  call    _initialize_narrow_environment
0x180003d75  mov     al, 1
0x180003d77  add     rsp, 28h
0x180003d7b  retn
```
