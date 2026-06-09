# DllUnregisterServer

- ea: `0x180004ab0`
- end: `0x180004ae0`
- name: `DllUnregisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004ab0`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x180004ad9`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
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
0x180004ab0  mov     rax, cs:aProxyFileList
0x180004ab7  mov     rcx, [rax+8]
0x180004abb  mov     rax, [rcx]
0x180004abe  test    rax, rax
0x180004ac1  jz      short loc_180004AC8
0x180004ac3  mov     r8, [rax]
0x180004ac6  jmp     short loc_180004ACB
0x180004ac8  xor     r8d, r8d
0x180004acb  mov     rcx, cs:hProxyDll
0x180004ad2  lea     rdx, aProxyFileList
0x180004ad9  jmp     cs:__imp_NdrDllUnregisterProxy
```
