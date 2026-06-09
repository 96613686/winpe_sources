# wil::details::out_param_t<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>::~out_param_t<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>(void)

- ea: `0x18000ef70`
- end: `0x18000ef9e`
- name: `??1?$out_param_t@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ`
- size: `46`
- prototype: `__int64 *__fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016bae`

## callees

- `0x18000ef70`
- `0x1800159b0`

## pseudocode

```c
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
0x18000ef70  sub     rsp, 28h
0x18000ef74  cmp     byte ptr [rcx+10h], 0
0x18000ef78  jz      short loc_18000EF99
0x18000ef7a  mov     rdx, [rcx+8]
0x18000ef7e  mov     rax, [rcx]
0x18000ef81  mov     rcx, [rax]
0x18000ef84  mov     [rax], rdx
0x18000ef87  test    rcx, rcx
0x18000ef8a  jz      short loc_18000EF99
0x18000ef8c  mov     rax, [rcx]
0x18000ef8f  mov     rax, [rax+10h]
0x18000ef93  call    _guard_dispatch_icall
0x18000ef98  nop
0x18000ef99  add     rsp, 28h
0x18000ef9d  retn
```
