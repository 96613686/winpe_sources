# wil::com_ptr_t<ITpmVCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVCardManager,wil::err_exception_policy>(void)

- ea: `0x18001b1c0`
- end: `0x18001b1de`
- name: `??1?$com_ptr_t@UITpmVCardManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b7b0`
- `0x18001bae8`
- `0x18001bc9c`
- `0x1800207b4`
- `0x18002f818`
- `0x18002feac`
- `0x1800361a4`
- `0x180036b5a`
- `0x180036b6c`

## callees

- `0x18001b1c0`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<ITpmVCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVCardManager,wil::err_exception_policy>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18001b1c0  sub     rsp, 28h
0x18001b1c4  mov     rcx, [rcx]
0x18001b1c7  test    rcx, rcx
0x18001b1ca  jz      short loc_18001B1D9
0x18001b1cc  mov     rax, [rcx]
0x18001b1cf  mov     rax, [rax+10h]
0x18001b1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1d8  nop
0x18001b1d9  add     rsp, 28h
0x18001b1dd  retn
```
