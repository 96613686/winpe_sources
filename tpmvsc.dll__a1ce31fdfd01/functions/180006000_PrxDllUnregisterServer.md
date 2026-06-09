# PrxDllUnregisterServer

- ea: `0x180006000`
- end: `0x180006030`
- name: `PrxDllUnregisterServer`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001c580`
- `0x18001c690`

## callees

- `0x180006000`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x180006029`

## pseudocode

```c
HRESULT PrxDllUnregisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  return NdrDllUnregisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
}

```

## disassembly

```asm
0x180006000  mov     rax, cs:aProxyFileList
0x180006007  mov     rcx, [rax+8]
0x18000600b  mov     rax, [rcx]
0x18000600e  test    rax, rax
0x180006011  jz      short loc_180006018
0x180006013  mov     r8, [rax]
0x180006016  jmp     short loc_18000601B
0x180006018  xor     r8d, r8d
0x18000601b  mov     rcx, cs:hProxyDll
0x180006022  lea     rdx, aProxyFileList
0x180006029  jmp     cs:__imp_NdrDllUnregisterProxy
```
