# wil::details::out_param_t<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>::~out_param_t<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>(void)

- ea: `0x18000efc0`
- end: `0x18000efee`
- name: `??1?$out_param_t@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016bfe`

## callees

- `0x18000efc0`
- `0x180015a00`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall wil::details::out_param_t<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>::~out_param_t<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>(
        __int64 **a1)
{
  __int64 *v1; // rdx
  __int64 *result; // rax
  __int64 v3; // rcx

  if ( *((_BYTE *)a1 + 16) )
  {
    v1 = a1[1];
    result = *a1;
    v3 = **a1;
    *result = (__int64)v1;
    if ( v3 )
      return (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x18000efc0  sub     rsp, 28h
0x18000efc4  cmp     byte ptr [rcx+10h], 0
0x18000efc8  jz      short loc_18000EFE9
0x18000efca  mov     rdx, [rcx+8]
0x18000efce  mov     rax, [rcx]
0x18000efd1  mov     rcx, [rax]
0x18000efd4  mov     [rax], rdx
0x18000efd7  test    rcx, rcx
0x18000efda  jz      short loc_18000EFE9
0x18000efdc  mov     rax, [rcx]
0x18000efdf  mov     rax, [rax+10h]
0x18000efe3  call    _guard_dispatch_icall
0x18000efe8  nop
0x18000efe9  add     rsp, 28h
0x18000efed  retn
```
