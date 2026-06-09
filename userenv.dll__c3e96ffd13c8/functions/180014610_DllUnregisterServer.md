# DllUnregisterServer

- ea: `0x180014610`
- end: `0x180014640`
- name: `DllUnregisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180014610`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x180014639`

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
  return NdrDllUnregisterProxy((HMODULE)hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
}

```

## disassembly

```asm
0x180014610  mov     rax, cs:aProxyFileList
0x180014617  mov     rcx, [rax+8]
0x18001461b  mov     rax, [rcx]
0x18001461e  test    rax, rax
0x180014621  jz      short loc_180014628
0x180014623  mov     r8, [rax]
0x180014626  jmp     short loc_18001462B
0x180014628  xor     r8d, r8d
0x18001462b  mov     rcx, cs:hProxyDll
0x180014632  lea     rdx, aProxyFileList
0x180014639  jmp     cs:__imp_NdrDllUnregisterProxy
```
