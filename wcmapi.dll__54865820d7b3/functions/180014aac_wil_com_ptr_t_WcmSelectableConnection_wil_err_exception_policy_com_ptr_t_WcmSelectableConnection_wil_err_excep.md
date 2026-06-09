# wil::com_ptr_t<WcmSelectableConnection,wil::err_exception_policy>::~com_ptr_t<WcmSelectableConnection,wil::err_exception_policy>(void)

- ea: `0x180014aac`
- end: `0x180014acb`
- name: `??1?$com_ptr_t@VWcmSelectableConnection@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014cc0`
- `0x18001d349`

## callees

- `0x180014aac`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<WcmSelectableConnection,wil::err_exception_policy>::~com_ptr_t<WcmSelectableConnection,wil::err_exception_policy>(
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
0x180014aac  sub     rsp, 28h
0x180014ab0  mov     rcx, [rcx]
0x180014ab3  test    rcx, rcx
0x180014ab6  jz      short loc_180014AC5
0x180014ab8  mov     rax, [rcx]
0x180014abb  mov     rax, [rax+10h]
0x180014abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ac4  nop
0x180014ac5  add     rsp, 28h
0x180014ac9  retn
```
