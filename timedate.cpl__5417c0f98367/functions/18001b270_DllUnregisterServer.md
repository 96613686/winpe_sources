# DllUnregisterServer

- ea: `0x18001b270`
- end: `0x18001b2a0`
- name: `DllUnregisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001b270`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x18001b299`

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
0x18001b270  mov     rax, cs:aProxyFileList
0x18001b277  mov     rcx, [rax+8]
0x18001b27b  mov     rax, [rcx]
0x18001b27e  test    rax, rax
0x18001b281  jz      short loc_18001B288
0x18001b283  mov     r8, [rax]
0x18001b286  jmp     short loc_18001B28B
0x18001b288  xor     r8d, r8d
0x18001b28b  mov     rcx, cs:hProxyDll
0x18001b292  lea     rdx, aProxyFileList
0x18001b299  jmp     cs:__imp_NdrDllUnregisterProxy
```
