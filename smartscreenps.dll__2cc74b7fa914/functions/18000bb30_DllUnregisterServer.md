# DllUnregisterServer

- ea: `0x18000bb30`
- end: `0x18000bb4c`
- name: `DllUnregisterServer`
- size: `28`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x18000bb45`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  return NdrDllUnregisterProxy((HMODULE)hProxyDll, (const ProxyFileInfo **)&aProxyFileList, &CLSID_PSFactoryBuffer);
}

```

## disassembly

```asm
0x18000bb30  mov     rcx, cs:hProxyDll
0x18000bb37  lea     r8, CLSID_PSFactoryBuffer
0x18000bb3e  lea     rdx, aProxyFileList
0x18000bb45  jmp     cs:__imp_NdrDllUnregisterProxy
```
