# DllGetClassObject

- ea: `0x180015730`
- end: `0x180015774`
- name: `DllGetClassObject`
- size: `68`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180015730`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180015762`
- `RPCRT4!NdrDllGetClassObject` at `0x180015762`

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
0x180015730  sub     rsp, 38h
0x180015734  mov     rax, cs:aProxyFileList
0x18001573b  mov     r9, [rax+8]
0x18001573f  mov     rax, [r9]
0x180015742  test    rax, rax
0x180015745  jz      short loc_18001574A
0x180015747  mov     rax, [rax]
0x18001574a  lea     r9, gPFactory
0x180015751  mov     [rsp+38h+pPSFactoryBuffer], r9; pPSFactoryBuffer
0x180015756  lea     r9, aProxyFileList; pProxyFileList
0x18001575d  mov     [rsp+38h+pclsid], rax; pclsid
0x180015762  call    cs:__imp_NdrDllGetClassObject
0x180015769  nop     dword ptr [rax+rax+00h]
0x18001576e  add     rsp, 38h
0x180015772  retn
```
