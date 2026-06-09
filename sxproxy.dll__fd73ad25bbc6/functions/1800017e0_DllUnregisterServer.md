# DllUnregisterServer

- ea: `0x1800017e0`
- end: `0x180001810`
- name: `DllUnregisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800017e0`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x180001809`

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
0x1800017e0  mov     rax, cs:aProxyFileList
0x1800017e7  mov     rcx, [rax+8]
0x1800017eb  mov     rax, [rcx]
0x1800017ee  test    rax, rax
0x1800017f1  jz      short loc_1800017F8
0x1800017f3  mov     r8, [rax]
0x1800017f6  jmp     short loc_1800017FB
0x1800017f8  xor     r8d, r8d
0x1800017fb  mov     rcx, cs:hProxyDll
0x180001802  lea     rdx, aProxyFileList
0x180001809  jmp     cs:__imp_NdrDllUnregisterProxy
```
