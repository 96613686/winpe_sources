# wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(void)

- ea: `0x1800068a4`
- end: `0x1800068c2`
- name: `??1?$com_ptr_t@UIApplicationDataStatics@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800069ac`
- `0x180008bd8`
- `0x18000c0e3`
- `0x18000c0f5`
- `0x18000c107`
- `0x18000c119`
- `0x18000c19c`

## callees

- `0x1800068a4`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IApplicationDataStatics,wil::err_returncode_policy>(
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
0x1800068a4  sub     rsp, 28h
0x1800068a8  mov     rcx, [rcx]
0x1800068ab  test    rcx, rcx
0x1800068ae  jz      short loc_1800068BD
0x1800068b0  mov     rax, [rcx]
0x1800068b3  mov     rax, [rax+10h]
0x1800068b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068bc  nop
0x1800068bd  add     rsp, 28h
0x1800068c1  retn
```
