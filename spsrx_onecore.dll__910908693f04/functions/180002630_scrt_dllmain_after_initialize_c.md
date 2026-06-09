# __scrt_dllmain_after_initialize_c

- ea: `0x180002630`
- end: `0x180002664`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002258`

## callees

- `0x180001ec0`
- `0x180002630`
- `0x180002b48`
- `0x180002dd4`
- `0x180002e3a`
- `0x180002e5e`

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
0x180002630  sub     rsp, 28h
0x180002634  call    __scrt_is_ucrt_dll_in_use
0x180002639  test    eax, eax
0x18000263b  jz      short loc_180002644
0x18000263d  call    __isa_available_init
0x180002642  jmp     short loc_18000265D
0x180002644  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x180002649  mov     ecx, eax; mode
0x18000264b  call    _o__configure_narrow_argv_0
0x180002650  test    eax, eax
0x180002652  jz      short loc_180002658
0x180002654  xor     al, al
0x180002656  jmp     short loc_18000265F
0x180002658  call    _initialize_narrow_environment
0x18000265d  mov     al, 1
0x18000265f  add     rsp, 28h
0x180002663  retn
```
