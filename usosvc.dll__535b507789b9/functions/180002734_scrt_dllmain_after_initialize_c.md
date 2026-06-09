# __scrt_dllmain_after_initialize_c

- ea: `0x180002734`
- end: `0x180002768`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800023b8`

## callees

- `0x180002734`
- `0x180002d80`
- `0x18000300c`
- `0x180003018`
- `0x1800030fe`
- `0x180003122`

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
0x180002734  sub     rsp, 28h
0x180002738  call    __scrt_is_ucrt_dll_in_use
0x18000273d  test    eax, eax
0x18000273f  jz      short loc_180002748
0x180002741  call    __isa_available_init
0x180002746  jmp     short loc_180002761
0x180002748  call    _get_startup_argv_mode
0x18000274d  mov     ecx, eax; mode
0x18000274f  call    _o__configure_narrow_argv_0
0x180002754  test    eax, eax
0x180002756  jz      short loc_18000275C
0x180002758  xor     al, al
0x18000275a  jmp     short loc_180002763
0x18000275c  call    _initialize_narrow_environment
0x180002761  mov     al, 1
0x180002763  add     rsp, 28h
0x180002767  retn
```
