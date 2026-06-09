# DllRegisterServer

- ea: `0x180015780`
- end: `0x1800157b0`
- name: `DllRegisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180015780`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x1800157a9`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  PCInterfaceStubVtblList v0; // rax
  const CLSID *piid; // r8

  v0 = *aProxyFileList->pStubVtblList;
  if ( v0 )
    piid = v0->header.piid;
  else
    piid = 0;
  return NdrDllRegisterProxy((HMODULE)hProxyDll, (const ProxyFileInfo **)&aProxyFileList, piid);
}

```

## disassembly

```asm
0x180015780  mov     rax, cs:aProxyFileList
0x180015787  mov     rcx, [rax+8]
0x18001578b  mov     rax, [rcx]
0x18001578e  test    rax, rax
0x180015791  jz      short loc_180015798
0x180015793  mov     r8, [rax]
0x180015796  jmp     short loc_18001579B
0x180015798  xor     r8d, r8d
0x18001579b  mov     rcx, cs:hProxyDll
0x1800157a2  lea     rdx, aProxyFileList
0x1800157a9  jmp     cs:__imp_NdrDllRegisterProxy
```
