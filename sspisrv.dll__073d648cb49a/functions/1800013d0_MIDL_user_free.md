# MIDL_user_free

- ea: `0x1800013d0`
- end: `0x1800013f6`
- name: `MIDL_user_free`
- size: `38`
- prototype: `void __stdcall(void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800012b0`
- `0x180002e10`
- `0x180003060`

## callees

- `0x1800013d0`
- `0x180004010`

## pseudocode

```c
void __stdcall MIDL_user_free(void *a1)
{
  void (__fastcall *v1)(void *); // rax

  if ( gLsapSspiExtension )
  {
    v1 = *(void (__fastcall **)(void *))(gLsapSspiExtension + 8);
    if ( v1 )
      v1(a1);
  }
}

```

## disassembly

```asm
0x1800013d0  sub     rsp, 28h
0x1800013d4  mov     rax, cs:gLsapSspiExtension
0x1800013db  test    rax, rax
0x1800013de  jz      short loc_1800013E9
0x1800013e0  mov     rax, [rax+8]
0x1800013e4  test    rax, rax
0x1800013e7  jnz     short loc_1800013EF
0x1800013e9  add     rsp, 28h
0x1800013ed  retn
0x1800013ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013f4  jmp     short loc_1800013E9
```
