# __scrt_dllmain_after_initialize_c

- ea: `0x18000528c`
- end: `0x1800052c0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180004dd8`

## callees

- `0x18000528c`
- `0x180005888`
- `0x180005b14`
- `0x180005b20`
- `0x180005bba`
- `0x180005bde`

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
0x18000528c  sub     rsp, 28h
0x180005290  call    __scrt_is_ucrt_dll_in_use
0x180005295  test    eax, eax
0x180005297  jz      short loc_1800052A0
0x180005299  call    __isa_available_init
0x18000529e  jmp     short loc_1800052B9
0x1800052a0  call    _get_startup_argv_mode
0x1800052a5  mov     ecx, eax; mode
0x1800052a7  call    _o__configure_narrow_argv_0
0x1800052ac  test    eax, eax
0x1800052ae  jz      short loc_1800052B4
0x1800052b0  xor     al, al
0x1800052b2  jmp     short loc_1800052BB
0x1800052b4  call    _initialize_narrow_environment
0x1800052b9  mov     al, 1
0x1800052bb  add     rsp, 28h
0x1800052bf  retn
```
