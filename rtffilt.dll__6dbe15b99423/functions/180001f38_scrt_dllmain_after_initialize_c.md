# __scrt_dllmain_after_initialize_c

- ea: `0x180001f38`
- end: `0x180001f6c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001b18`

## callees

- `0x180001f38`
- `0x1800024e0`
- `0x18000276c`
- `0x18000280a`
- `0x18000282e`
- `0x180014470`

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
0x180001f38  sub     rsp, 28h
0x180001f3c  call    __scrt_is_ucrt_dll_in_use
0x180001f41  test    eax, eax
0x180001f43  jz      short loc_180001F4C
0x180001f45  call    __isa_available_init
0x180001f4a  jmp     short loc_180001F65
0x180001f4c  call    _get_startup_argv_mode
0x180001f51  mov     ecx, eax; mode
0x180001f53  call    _o__configure_narrow_argv_0
0x180001f58  test    eax, eax
0x180001f5a  jz      short loc_180001F60
0x180001f5c  xor     al, al
0x180001f5e  jmp     short loc_180001F67
0x180001f60  call    _initialize_narrow_environment
0x180001f65  mov     al, 1
0x180001f67  add     rsp, 28h
0x180001f6b  retn
```
