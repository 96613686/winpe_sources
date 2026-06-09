# __scrt_dllmain_after_initialize_c

- ea: `0x1800025f4`
- end: `0x180002628`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002268`

## callees

- `0x1800025f4`
- `0x180002c10`
- `0x180002e9c`
- `0x180002ea8`
- `0x180002fb2`
- `0x180002fe2`

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
0x1800025f4  sub     rsp, 28h
0x1800025f8  call    __scrt_is_ucrt_dll_in_use
0x1800025fd  test    eax, eax
0x1800025ff  jz      short loc_180002608
0x180002601  call    __isa_available_init
0x180002606  jmp     short loc_180002621
0x180002608  call    _get_startup_argv_mode
0x18000260d  mov     ecx, eax; mode
0x18000260f  call    _o__configure_narrow_argv_0
0x180002614  test    eax, eax
0x180002616  jz      short loc_18000261C
0x180002618  xor     al, al
0x18000261a  jmp     short loc_180002623
0x18000261c  call    _initialize_narrow_environment
0x180002621  mov     al, 1
0x180002623  add     rsp, 28h
0x180002627  retn
```
