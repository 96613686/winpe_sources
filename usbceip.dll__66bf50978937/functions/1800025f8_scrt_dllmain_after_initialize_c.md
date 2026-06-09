# __scrt_dllmain_after_initialize_c

- ea: `0x1800025f8`
- end: `0x18000262c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800020e8`

## callees

- `0x1800025f8`
- `0x180002a98`
- `0x180002d24`
- `0x180002d30`
- `0x180002dde`
- `0x180002e02`

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
0x1800025f8  sub     rsp, 28h
0x1800025fc  call    __scrt_is_ucrt_dll_in_use
0x180002601  test    eax, eax
0x180002603  jz      short loc_18000260C
0x180002605  call    __isa_available_init
0x18000260a  jmp     short loc_180002625
0x18000260c  call    _get_startup_argv_mode
0x180002611  mov     ecx, eax; mode
0x180002613  call    _o__configure_narrow_argv_0
0x180002618  test    eax, eax
0x18000261a  jz      short loc_180002620
0x18000261c  xor     al, al
0x18000261e  jmp     short loc_180002627
0x180002620  call    _initialize_narrow_environment
0x180002625  mov     al, 1
0x180002627  add     rsp, 28h
0x18000262b  retn
```
