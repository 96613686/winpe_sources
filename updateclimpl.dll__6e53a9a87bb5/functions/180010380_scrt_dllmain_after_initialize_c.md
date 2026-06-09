# __scrt_dllmain_after_initialize_c

- ea: `0x180010380`
- end: `0x1800103b4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180010798`

## callees

- `0x180010174`
- `0x1800101bc`
- `0x180010380`
- `0x180010c70`
- `0x180010f0c`
- `0x180010f18`

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
0x180010380  sub     rsp, 28h
0x180010384  call    __scrt_is_ucrt_dll_in_use
0x180010389  test    eax, eax
0x18001038b  jz      short loc_180010394
0x18001038d  call    __isa_available_init
0x180010392  jmp     short loc_1800103AD
0x180010394  call    _get_startup_argv_mode
0x180010399  mov     ecx, eax; mode
0x18001039b  call    _o__configure_narrow_argv_0
0x1800103a0  test    eax, eax
0x1800103a2  jz      short loc_1800103A8
0x1800103a4  xor     al, al
0x1800103a6  jmp     short loc_1800103AF
0x1800103a8  call    _initialize_narrow_environment
0x1800103ad  mov     al, 1
0x1800103af  add     rsp, 28h
0x1800103b3  retn
```
