# wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>(ICloudAPHelper *)

- ea: `0x18000bd5c`
- end: `0x18000bd85`
- name: `??0?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVICloudAPHelper@@@Z`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bba0`

## callees

- `0x18000bd5c`
- `0x180016010`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>(
        _QWORD *a1,
        __int64 a2)
{
  *a1 = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  return a1;
}

```

## disassembly

```asm
0x18000bd5c  push    rbx
0x18000bd5e  sub     rsp, 20h
0x18000bd62  mov     [rcx], rdx
0x18000bd65  mov     rbx, rcx
0x18000bd68  test    rdx, rdx
0x18000bd6b  jz      short loc_18000BD7C
0x18000bd6d  mov     rax, [rdx]
0x18000bd70  mov     rcx, rdx
0x18000bd73  mov     rax, [rax+8]
0x18000bd77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd7c  mov     rax, rbx
0x18000bd7f  add     rsp, 20h
0x18000bd83  pop     rbx
0x18000bd84  retn
```
