# DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO_Encode

- ea: `0x180006f20`
- end: `0x180006f51`
- name: `DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO_Encode`
- size: `49`
- prototype: `void __fastcall(void *, const void *pObject)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `RPCRT4!NdrMesTypeEncode3` at `0x180006f46`
- `RPCRT4!NdrMesTypeEncode3` at `0x180006f46`

## pseudocode

```c
void __fastcall DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO_Encode(void *a1, const void *pObject)
{
  NdrMesTypeEncode3(
    a1,
    &pPicklingInfo,
    &drvwuhelper_pickle_private_ProxyInfo,
    (const unsigned int **)&ArrTypeOffset,
    1u,
    pObject);
}

```

## disassembly

```asm
0x180006f20  sub     rsp, 38h
0x180006f24  mov     [rsp+38h+pObject], rdx; pObject
0x180006f29  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180006f30  lea     rdx, pPicklingInfo; pPicklingInfo
0x180006f37  mov     [rsp+38h+nTypeIndex], 1; nTypeIndex
0x180006f3f  lea     r8, ?drvwuhelper_pickle_private_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180006f46  call    cs:__imp_NdrMesTypeEncode3
0x180006f4c  add     rsp, 38h
0x180006f50  retn
```
