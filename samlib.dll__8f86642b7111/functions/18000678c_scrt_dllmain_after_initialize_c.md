# __scrt_dllmain_after_initialize_c

- ea: `0x18000678c`
- end: `0x1800067c0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180006308`

## callees

- `0x18000678c`
- `0x180006b60`
- `0x180006dec`
- `0x180006df8`
- `0x180006e7a`
- `0x180006e92`

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
0x18000678c  sub     rsp, 28h
0x180006790  call    __scrt_is_ucrt_dll_in_use
0x180006795  test    eax, eax
0x180006797  jz      short loc_1800067A0
0x180006799  call    __isa_available_init
0x18000679e  jmp     short loc_1800067B9
0x1800067a0  call    _get_startup_argv_mode
0x1800067a5  mov     ecx, eax; mode
0x1800067a7  call    _o__configure_narrow_argv_0
0x1800067ac  test    eax, eax
0x1800067ae  jz      short loc_1800067B4
0x1800067b0  xor     al, al
0x1800067b2  jmp     short loc_1800067BB
0x1800067b4  call    _initialize_narrow_environment
0x1800067b9  mov     al, 1
0x1800067bb  add     rsp, 28h
0x1800067bf  retn
```
