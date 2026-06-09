# _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)

- ea: `0x180019818`
- end: `0x180019836`
- name: `?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800173f8`
- `0x180018850`

## callees

- `0x180019818`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(
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
0x180019818  sub     rsp, 28h
0x18001981c  mov     rcx, [rcx]
0x18001981f  test    rcx, rcx
0x180019822  jz      short loc_180019831
0x180019824  mov     rax, [rcx]
0x180019827  mov     rax, [rax+10h]
0x18001982b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019830  nop
0x180019831  add     rsp, 28h
0x180019835  retn
```
