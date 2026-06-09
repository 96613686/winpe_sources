# wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(void)

- ea: `0x1800065e4`
- end: `0x180006602`
- name: `??1?$com_ptr_t@UIStoreRequestHelperStatics@Store@Services@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `18`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005b0c`
- `0x1800060a8`
- `0x180006c3c`
- `0x180010084`
- `0x180012b74`
- `0x180027de6`
- `0x180027df8`
- `0x180027e0a`
- `0x180027e1c`
- `0x180027e40`
- `0x180027e88`
- `0x180027e9a`
- `0x180027eac`
- `0x180027f3b`
- `0x180028349`
- `0x18002836d`
- `0x18002863c`
- `0x18002867a`

## callees

- `0x1800065e4`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Services::Store::IStoreRequestHelperStatics,wil::err_exception_policy>(
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
0x1800065e4  sub     rsp, 28h
0x1800065e8  mov     rcx, [rcx]
0x1800065eb  test    rcx, rcx
0x1800065ee  jz      short loc_1800065FD
0x1800065f0  mov     rax, [rcx]
0x1800065f3  mov     rax, [rax+10h]
0x1800065f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065fc  nop
0x1800065fd  add     rsp, 28h
0x180006601  retn
```
