# CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::GetTypeInfoCount(uint *)

- ea: `0x180009490`
- end: `0x1800094a1`
- name: `?GetTypeInfoCount@?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@UEAAJPEAI@Z`
- size: `17`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180009490`

## pseudocode

```c
__int64 __fastcall CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>::GetTypeInfoCount(
        __int64 a1,
        _DWORD *a2)
{
  if ( a2 )
    *a2 = 0;
  return 2147500033LL;
}

```

## disassembly

```asm
0x180009490  test    rdx, rdx
0x180009493  jz      short loc_18000949B
0x180009495  mov     dword ptr [rdx], 0
0x18000949b  mov     eax, 80004001h
0x1800094a0  retn
```
