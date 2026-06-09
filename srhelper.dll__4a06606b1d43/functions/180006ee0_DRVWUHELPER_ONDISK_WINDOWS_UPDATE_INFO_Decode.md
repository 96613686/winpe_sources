# DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO_Decode

- ea: `0x180006ee0`
- end: `0x180006f11`
- name: `DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO_Decode`
- size: `49`
- prototype: `void __fastcall(void *, void *pObject)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x180006f06`
- `RPCRT4!NdrMesTypeDecode3` at `0x180006f06`

## pseudocode

```c
void __fastcall DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO_Decode(void *a1, void *pObject)
{
  NdrMesTypeDecode3(
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
0x180006ee0  sub     rsp, 38h
0x180006ee4  mov     [rsp+38h+pObject], rdx; pObject
0x180006ee9  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180006ef0  lea     rdx, pPicklingInfo; pPicklingInfo
0x180006ef7  mov     [rsp+38h+nTypeIndex], 1; nTypeIndex
0x180006eff  lea     r8, ?drvwuhelper_pickle_private_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180006f06  call    cs:__imp_NdrMesTypeDecode3
0x180006f0c  add     rsp, 38h
0x180006f10  retn
```
