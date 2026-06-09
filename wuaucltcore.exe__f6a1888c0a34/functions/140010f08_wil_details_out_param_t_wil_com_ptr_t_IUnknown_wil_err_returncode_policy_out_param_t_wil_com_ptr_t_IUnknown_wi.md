# wil::details::out_param_t<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>::~out_param_t<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>(void)

- ea: `0x140010f08`
- end: `0x140010f36`
- name: `??1?$out_param_t@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002180d`

## callees

- `0x140010f08`
- `0x1400206e0`

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
0x140010f08  sub     rsp, 28h
0x140010f0c  cmp     byte ptr [rcx+10h], 0
0x140010f10  jz      short loc_140010F31
0x140010f12  mov     rdx, [rcx+8]
0x140010f16  mov     rax, [rcx]
0x140010f19  mov     rcx, [rax]
0x140010f1c  mov     [rax], rdx
0x140010f1f  test    rcx, rcx
0x140010f22  jz      short loc_140010F31
0x140010f24  mov     rax, [rcx]
0x140010f27  mov     rax, [rax+10h]
0x140010f2b  call    _guard_dispatch_icall
0x140010f30  nop
0x140010f31  add     rsp, 28h
0x140010f35  retn
```
