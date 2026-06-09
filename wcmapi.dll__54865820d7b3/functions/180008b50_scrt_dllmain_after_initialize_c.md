# __scrt_dllmain_after_initialize_c

- ea: `0x180008b50`
- end: `0x180008b84`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180008768`

## callees

- `0x180008b50`
- `0x1800090c4`
- `0x180009350`
- `0x18000935c`
- `0x18000947a`
- `0x18000949e`

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
0x180008b50  sub     rsp, 28h
0x180008b54  call    __scrt_is_ucrt_dll_in_use
0x180008b59  test    eax, eax
0x180008b5b  jz      short loc_180008B64
0x180008b5d  call    __isa_available_init
0x180008b62  jmp     short loc_180008B7D
0x180008b64  call    _get_startup_argv_mode
0x180008b69  mov     ecx, eax; mode
0x180008b6b  call    _o__configure_narrow_argv_0
0x180008b70  test    eax, eax
0x180008b72  jz      short loc_180008B78
0x180008b74  xor     al, al
0x180008b76  jmp     short loc_180008B7F
0x180008b78  call    _initialize_narrow_environment
0x180008b7d  mov     al, 1
0x180008b7f  add     rsp, 28h
0x180008b83  retn
```
