# wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::~com_ptr_t<IUnknown,wil::err_returncode_policy>(void)

- ea: `0x18000efa4`
- end: `0x18000efc2`
- name: `??1?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016b9c`

## callees

- `0x18000efa4`
- `0x1800159b0`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::~com_ptr_t<IUnknown,wil::err_returncode_policy>(
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
0x18000efa4  sub     rsp, 28h
0x18000efa8  mov     rcx, [rcx]
0x18000efab  test    rcx, rcx
0x18000efae  jz      short loc_18000EFBD
0x18000efb0  mov     rax, [rcx]
0x18000efb3  mov     rax, [rax+10h]
0x18000efb7  call    _guard_dispatch_icall
0x18000efbc  nop
0x18000efbd  add     rsp, 28h
0x18000efc1  retn
```
