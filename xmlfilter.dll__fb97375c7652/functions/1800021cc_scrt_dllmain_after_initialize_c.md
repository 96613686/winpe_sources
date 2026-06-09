# __scrt_dllmain_after_initialize_c

- ea: `0x1800021cc`
- end: `0x180002200`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001db8`

## callees

- `0x1800021cc`
- `0x180002770`
- `0x1800029fc`
- `0x180002aa6`
- `0x180002aca`
- `0x18000e980`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  CSaxContentHandler *v0; // rcx
  _crt_argv_mode v1; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    v1 = CSaxContentHandler::Release(v0);
    if ( o__configure_narrow_argv_0(v1) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x1800021cc  sub     rsp, 28h
0x1800021d0  call    __scrt_is_ucrt_dll_in_use
0x1800021d5  test    eax, eax
0x1800021d7  jz      short loc_1800021E0
0x1800021d9  call    __isa_available_init
0x1800021de  jmp     short loc_1800021F9
0x1800021e0  call    ?Release@CSaxContentHandler@@UEAAKXZ; CSaxContentHandler::Release(void)
0x1800021e5  mov     ecx, eax; mode
0x1800021e7  call    _o__configure_narrow_argv_0
0x1800021ec  test    eax, eax
0x1800021ee  jz      short loc_1800021F4
0x1800021f0  xor     al, al
0x1800021f2  jmp     short loc_1800021FB
0x1800021f4  call    _initialize_narrow_environment
0x1800021f9  mov     al, 1
0x1800021fb  add     rsp, 28h
0x1800021ff  retn
```
