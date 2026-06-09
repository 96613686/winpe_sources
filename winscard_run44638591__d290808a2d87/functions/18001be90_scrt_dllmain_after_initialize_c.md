# __scrt_dllmain_after_initialize_c

- ea: `0x18001be90`
- end: `0x18001bec4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001baf8`

## callees

- `0x18001be90`
- `0x18001c3d8`
- `0x18001c664`
- `0x18001c670`
- `0x18001c70a`
- `0x18001c72e`

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
0x18001be90  sub     rsp, 28h
0x18001be94  call    __scrt_is_ucrt_dll_in_use
0x18001be99  test    eax, eax
0x18001be9b  jz      short loc_18001BEA4
0x18001be9d  call    __isa_available_init
0x18001bea2  jmp     short loc_18001BEBD
0x18001bea4  call    _get_startup_argv_mode
0x18001bea9  mov     ecx, eax; mode
0x18001beab  call    _o__configure_narrow_argv_0
0x18001beb0  test    eax, eax
0x18001beb2  jz      short loc_18001BEB8
0x18001beb4  xor     al, al
0x18001beb6  jmp     short loc_18001BEBF
0x18001beb8  call    _initialize_narrow_environment
0x18001bebd  mov     al, 1
0x18001bebf  add     rsp, 28h
0x18001bec3  retn
```
