# DllGetClassObject

- ea: `0x180001730`
- end: `0x18000176d`
- name: `DllGetClassObject`
- size: `61`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001730`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180001762`
- `RPCRT4!NdrDllGetClassObject` at `0x180001762`

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
0x180001730  sub     rsp, 38h
0x180001734  mov     rax, cs:aProxyFileList
0x18000173b  mov     r9, [rax+8]
0x18000173f  mov     rax, [r9]
0x180001742  test    rax, rax
0x180001745  jz      short loc_18000174A
0x180001747  mov     rax, [rax]
0x18000174a  lea     r9, gPFactory
0x180001751  mov     [rsp+38h+pPSFactoryBuffer], r9; pPSFactoryBuffer
0x180001756  lea     r9, aProxyFileList; pProxyFileList
0x18000175d  mov     [rsp+38h+pclsid], rax; pclsid
0x180001762  call    cs:__imp_NdrDllGetClassObject
0x180001768  add     rsp, 38h
0x18000176c  retn
```
