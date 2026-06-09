# __scrt_dllmain_after_initialize_c

- ea: `0x18000fcf4`
- end: `0x18000fd28`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180010188`

## callees

- `0x18000fbaa`
- `0x18000fbe6`
- `0x18000fcf4`
- `0x180010654`
- `0x1800108f0`
- `0x1800108fc`

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
0x18000fcf4  sub     rsp, 28h
0x18000fcf8  call    __scrt_is_ucrt_dll_in_use
0x18000fcfd  test    eax, eax
0x18000fcff  jz      short loc_18000FD08
0x18000fd01  call    __isa_available_init
0x18000fd06  jmp     short loc_18000FD21
0x18000fd08  call    _get_startup_argv_mode
0x18000fd0d  mov     ecx, eax; mode
0x18000fd0f  call    _o__configure_narrow_argv_0
0x18000fd14  test    eax, eax
0x18000fd16  jz      short loc_18000FD1C
0x18000fd18  xor     al, al
0x18000fd1a  jmp     short loc_18000FD23
0x18000fd1c  call    _initialize_narrow_environment
0x18000fd21  mov     al, 1
0x18000fd23  add     rsp, 28h
0x18000fd27  retn
```
