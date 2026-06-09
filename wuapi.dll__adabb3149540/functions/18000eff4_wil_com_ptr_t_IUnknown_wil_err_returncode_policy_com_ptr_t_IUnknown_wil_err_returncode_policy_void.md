# wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::~com_ptr_t<IUnknown,wil::err_returncode_policy>(void)

- ea: `0x18000eff4`
- end: `0x18000f012`
- name: `??1?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016bec`

## callees

- `0x18000eff4`
- `0x180015a00`

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
0x18000eff4  sub     rsp, 28h
0x18000eff8  mov     rcx, [rcx]
0x18000effb  test    rcx, rcx
0x18000effe  jz      short loc_18000F00D
0x18000f000  mov     rax, [rcx]
0x18000f003  mov     rax, [rax+10h]
0x18000f007  call    _guard_dispatch_icall
0x18000f00c  nop
0x18000f00d  add     rsp, 28h
0x18000f011  retn
```
