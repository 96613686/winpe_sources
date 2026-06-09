# CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180009470`
- end: `0x180009482`
- name: `?GetTypeInfo@?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `18`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180009470`

## pseudocode

```c
__int64 __fastcall CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::GetTypeInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  if ( a4 )
    *a4 = 0;
  return 2147500033LL;
}

```

## disassembly

```asm
0x180009470  test    r9, r9
0x180009473  jz      short loc_18000947C
0x180009475  mov     qword ptr [r9], 0
0x18000947c  mov     eax, 80004001h
0x180009481  retn
```
