# wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>::~com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>(void)

- ea: `0x18000bed8`
- end: `0x18000bef5`
- name: `??1?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800063c8`
- `0x18000c010`
- `0x18000c0c0`
- `0x18000c270`
- `0x18000c450`

## callees

- `0x18000bed8`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>::~com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>(
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
0x18000bed8  sub     rsp, 28h
0x18000bedc  mov     rcx, [rcx]
0x18000bedf  test    rcx, rcx
0x18000bee2  jz      short loc_18000BEF0
0x18000bee4  mov     rax, [rcx]
0x18000bee7  mov     rax, [rax+10h]
0x18000beeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bef0  add     rsp, 28h
0x18000bef4  retn
```
