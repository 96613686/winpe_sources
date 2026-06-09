# __scrt_dllmain_after_initialize_c

- ea: `0x180001690`
- end: `0x1800016c4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800012e8`

## callees

- `0x180001690`
- `0x180001bb8`
- `0x180001e44`
- `0x180001e50`
- `0x180001eca`
- `0x180001eee`

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
0x180001690  sub     rsp, 28h
0x180001694  call    __scrt_is_ucrt_dll_in_use
0x180001699  test    eax, eax
0x18000169b  jz      short loc_1800016A4
0x18000169d  call    __isa_available_init
0x1800016a2  jmp     short loc_1800016BD
0x1800016a4  call    _get_startup_argv_mode
0x1800016a9  mov     ecx, eax; mode
0x1800016ab  call    _o__configure_narrow_argv_0
0x1800016b0  test    eax, eax
0x1800016b2  jz      short loc_1800016B8
0x1800016b4  xor     al, al
0x1800016b6  jmp     short loc_1800016BF
0x1800016b8  call    _initialize_narrow_environment
0x1800016bd  mov     al, 1
0x1800016bf  add     rsp, 28h
0x1800016c3  retn
```
