# __scrt_dllmain_after_initialize_c

- ea: `0x1800015a0`
- end: `0x1800015d4`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800011e8`

## callees

- `0x1800015a0`
- `0x180001b28`
- `0x180001db4`
- `0x18000208e`
- `0x1800020b2`
- `0x1800026a0`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  ATL::CRegObject *v0; // rcx
  _crt_argv_mode v1; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    v1 = ATL::CRegObject::AddRef(v0);
    if ( o__configure_narrow_argv_0(v1) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x1800015a0  sub     rsp, 28h
0x1800015a4  call    __scrt_is_ucrt_dll_in_use
0x1800015a9  test    eax, eax
0x1800015ab  jz      short loc_1800015B4
0x1800015ad  call    __isa_available_init
0x1800015b2  jmp     short loc_1800015CD
0x1800015b4  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x1800015b9  mov     ecx, eax; mode
0x1800015bb  call    _o__configure_narrow_argv_0
0x1800015c0  test    eax, eax
0x1800015c2  jz      short loc_1800015C8
0x1800015c4  xor     al, al
0x1800015c6  jmp     short loc_1800015CF
0x1800015c8  call    _initialize_narrow_environment
0x1800015cd  mov     al, 1
0x1800015cf  add     rsp, 28h
0x1800015d3  retn
```
