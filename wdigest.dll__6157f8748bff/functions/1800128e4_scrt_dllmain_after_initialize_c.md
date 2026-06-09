# __scrt_dllmain_after_initialize_c

- ea: `0x1800128e4`
- end: `0x180012918`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180012568`

## callees

- `0x1800128e4`
- `0x180012e88`
- `0x180013114`
- `0x180013120`
- `0x18001325a`
- `0x18001327e`

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
0x1800128e4  sub     rsp, 28h
0x1800128e8  call    __scrt_is_ucrt_dll_in_use
0x1800128ed  test    eax, eax
0x1800128ef  jz      short loc_1800128F8
0x1800128f1  call    __isa_available_init
0x1800128f6  jmp     short loc_180012911
0x1800128f8  call    _get_startup_argv_mode
0x1800128fd  mov     ecx, eax; mode
0x1800128ff  call    _o__configure_narrow_argv_0
0x180012904  test    eax, eax
0x180012906  jz      short loc_18001290C
0x180012908  xor     al, al
0x18001290a  jmp     short loc_180012913
0x18001290c  call    _initialize_narrow_environment
0x180012911  mov     al, 1
0x180012913  add     rsp, 28h
0x180012917  retn
```
