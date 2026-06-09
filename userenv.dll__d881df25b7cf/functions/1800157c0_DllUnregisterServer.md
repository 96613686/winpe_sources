# DllUnregisterServer

- ea: `0x1800157c0`
- end: `0x1800157f0`
- name: `DllUnregisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800157c0`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x1800157e9`

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
0x1800157c0  mov     rax, cs:aProxyFileList
0x1800157c7  mov     rcx, [rax+8]
0x1800157cb  mov     rax, [rcx]
0x1800157ce  test    rax, rax
0x1800157d1  jz      short loc_1800157D8
0x1800157d3  mov     r8, [rax]
0x1800157d6  jmp     short loc_1800157DB
0x1800157d8  xor     r8d, r8d
0x1800157db  mov     rcx, cs:hProxyDll
0x1800157e2  lea     rdx, aProxyFileList
0x1800157e9  jmp     cs:__imp_NdrDllUnregisterProxy
```
