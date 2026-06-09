# DllRegisterServer

- ea: `0x180016880`
- end: `0x18001689c`
- name: `DllRegisterServer`
- size: `28`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x180016895`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  return NdrDllRegisterProxy((HMODULE)qword_180026900, (const ProxyFileInfo **)&pProxyFileList, &pclsid);
}

```

## disassembly

```asm
0x180016880  mov     rcx, cs:qword_180026900
0x180016887  lea     r8, pclsid
0x18001688e  lea     rdx, pProxyFileList
0x180016895  jmp     cs:NdrDllRegisterProxy
```
