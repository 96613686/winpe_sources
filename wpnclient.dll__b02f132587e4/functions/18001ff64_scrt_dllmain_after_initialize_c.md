# __scrt_dllmain_after_initialize_c

- ea: `0x18001ff64`
- end: `0x18001ff98`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001fbe8`

## callees

- `0x18001ff64`
- `0x180020850`
- `0x180020adc`
- `0x180020ae8`
- `0x180020c8a`
- `0x180020cae`

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
0x18001ff64  sub     rsp, 28h
0x18001ff68  call    __scrt_is_ucrt_dll_in_use
0x18001ff6d  test    eax, eax
0x18001ff6f  jz      short loc_18001FF78
0x18001ff71  call    __isa_available_init
0x18001ff76  jmp     short loc_18001FF91
0x18001ff78  call    _get_startup_argv_mode
0x18001ff7d  mov     ecx, eax; mode
0x18001ff7f  call    _o__configure_narrow_argv_0
0x18001ff84  test    eax, eax
0x18001ff86  jz      short loc_18001FF8C
0x18001ff88  xor     al, al
0x18001ff8a  jmp     short loc_18001FF93
0x18001ff8c  call    _initialize_narrow_environment
0x18001ff91  mov     al, 1
0x18001ff93  add     rsp, 28h
0x18001ff97  retn
```
