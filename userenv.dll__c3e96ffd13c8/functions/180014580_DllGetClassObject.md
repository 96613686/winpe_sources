# DllGetClassObject

- ea: `0x180014580`
- end: `0x1800145bd`
- name: `DllGetClassObject`
- size: `61`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180014580`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800145b2`
- `RPCRT4!NdrDllGetClassObject` at `0x1800145b2`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
}

```

## disassembly

```asm
0x180014580  sub     rsp, 38h
0x180014584  mov     rax, cs:aProxyFileList
0x18001458b  mov     r9, [rax+8]
0x18001458f  mov     rax, [r9]
0x180014592  test    rax, rax
0x180014595  jz      short loc_18001459A
0x180014597  mov     rax, [rax]
0x18001459a  lea     r9, gPFactory
0x1800145a1  mov     [rsp+38h+pPSFactoryBuffer], r9; pPSFactoryBuffer
0x1800145a6  lea     r9, aProxyFileList; pProxyFileList
0x1800145ad  mov     [rsp+38h+pclsid], rax; pclsid
0x1800145b2  call    cs:__imp_NdrDllGetClassObject
0x1800145b8  add     rsp, 38h
0x1800145bc  retn
```
