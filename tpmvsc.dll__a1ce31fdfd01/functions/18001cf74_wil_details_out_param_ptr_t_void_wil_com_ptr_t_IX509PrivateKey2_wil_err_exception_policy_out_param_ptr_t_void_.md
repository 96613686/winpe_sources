# wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IX509PrivateKey2,wil::err_exception_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IX509PrivateKey2,wil::err_exception_policy>>(void)

- ea: `0x18001cf74`
- end: `0x18001cfa2`
- name: `??1?$out_param_ptr_t@PEAPEAXV?$com_ptr_t@UIX509PrivateKey2@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ`
- size: `46`
- prototype: `__int64 *__fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800207b4`

## callees

- `0x18001cf74`
- `0x180037010`

## pseudocode

```c
__int64 *__fastcall wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<IX509PrivateKey2,wil::err_exception_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<IX509PrivateKey2,wil::err_exception_policy>>(
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
0x18001cf74  sub     rsp, 28h
0x18001cf78  cmp     byte ptr [rcx+10h], 0
0x18001cf7c  jz      short loc_18001CF9D
0x18001cf7e  mov     rdx, [rcx+8]
0x18001cf82  mov     rax, [rcx]
0x18001cf85  mov     rcx, [rax]
0x18001cf88  mov     [rax], rdx
0x18001cf8b  test    rcx, rcx
0x18001cf8e  jz      short loc_18001CF9D
0x18001cf90  mov     rax, [rcx]
0x18001cf93  mov     rax, [rax+10h]
0x18001cf97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf9c  nop
0x18001cf9d  add     rsp, 28h
0x18001cfa1  retn
```
