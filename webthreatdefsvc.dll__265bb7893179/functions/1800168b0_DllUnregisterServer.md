# DllUnregisterServer

- ea: `0x1800168b0`
- end: `0x1800168cc`
- name: `DllUnregisterServer`
- size: `28`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x1800168c5`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  return NdrDllUnregisterProxy((HMODULE)qword_180026900, (const ProxyFileInfo **)&pProxyFileList, &pclsid);
}

```

## disassembly

```asm
0x1800168b0  mov     rcx, cs:qword_180026900
0x1800168b7  lea     r8, pclsid
0x1800168be  lea     rdx, pProxyFileList
0x1800168c5  jmp     cs:NdrDllUnregisterProxy
```
