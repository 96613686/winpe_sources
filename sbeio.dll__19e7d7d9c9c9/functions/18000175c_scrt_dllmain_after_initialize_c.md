# __scrt_dllmain_after_initialize_c

- ea: `0x18000175c`
- end: `0x180001790`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800012d8`

## callees

- `0x18000175c`
- `0x180001b90`
- `0x180001e1c`
- `0x180001e8a`
- `0x180001eae`
- `0x1800043e0`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  CASFMarkerObject *v0; // rcx
  _crt_argv_mode IsBackwardsCompatible; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    IsBackwardsCompatible = (unsigned int)CASFMarkerObject::IsBackwardsCompatible(v0);
    if ( o__configure_narrow_argv_0(IsBackwardsCompatible) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x18000175c  sub     rsp, 28h
0x180001760  call    __scrt_is_ucrt_dll_in_use
0x180001765  test    eax, eax
0x180001767  jz      short loc_180001770
0x180001769  call    __isa_available_init
0x18000176e  jmp     short loc_180001789
0x180001770  call    ?IsBackwardsCompatible@CASFMarkerObject@@UEAAHXZ; CASFMarkerObject::IsBackwardsCompatible(void)
0x180001775  mov     ecx, eax; mode
0x180001777  call    _o__configure_narrow_argv_0
0x18000177c  test    eax, eax
0x18000177e  jz      short loc_180001784
0x180001780  xor     al, al
0x180001782  jmp     short loc_18000178B
0x180001784  call    _initialize_narrow_environment
0x180001789  mov     al, 1
0x18000178b  add     rsp, 28h
0x18000178f  retn
```
