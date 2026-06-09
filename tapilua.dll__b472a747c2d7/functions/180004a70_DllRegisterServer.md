# DllRegisterServer

- ea: `0x180004a70`
- end: `0x180004aa5`
- name: `DllRegisterServer`
- size: `53`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004a70`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x180004a98`
- `RPCRT4!NdrDllRegisterProxy` at `0x180004a98`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  const CLSID *v0; // r8

  v0 = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( v0 )
    v0 = *(const CLSID **)&v0->Data1;
  NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, v0);
  return 0;
}

```

## disassembly

```asm
0x180004a70  sub     rsp, 28h
0x180004a74  mov     rax, cs:aProxyFileList
0x180004a7b  mov     rcx, [rax+8]
0x180004a7f  mov     r8, [rcx]
0x180004a82  test    r8, r8
0x180004a85  jz      short loc_180004A8A
0x180004a87  mov     r8, [r8]; pclsid
0x180004a8a  mov     rcx, cs:hProxyDll; hDll
0x180004a91  lea     rdx, aProxyFileList; pProxyFileList
0x180004a98  call    cs:__imp_NdrDllRegisterProxy
0x180004a9e  xor     eax, eax
0x180004aa0  add     rsp, 28h
0x180004aa4  retn
```
