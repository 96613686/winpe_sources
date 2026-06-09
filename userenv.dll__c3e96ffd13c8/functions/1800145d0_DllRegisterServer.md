# DllRegisterServer

- ea: `0x1800145d0`
- end: `0x180014600`
- name: `DllRegisterServer`
- size: `48`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800145d0`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x1800145f9`

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
0x1800145d0  mov     rax, cs:aProxyFileList
0x1800145d7  mov     rcx, [rax+8]
0x1800145db  mov     rax, [rcx]
0x1800145de  test    rax, rax
0x1800145e1  jz      short loc_1800145E8
0x1800145e3  mov     r8, [rax]
0x1800145e6  jmp     short loc_1800145EB
0x1800145e8  xor     r8d, r8d
0x1800145eb  mov     rcx, cs:hProxyDll
0x1800145f2  lea     rdx, aProxyFileList
0x1800145f9  jmp     cs:__imp_NdrDllRegisterProxy
```
