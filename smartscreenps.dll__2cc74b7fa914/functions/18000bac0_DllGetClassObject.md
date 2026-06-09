# DllGetClassObject

- ea: `0x18000bac0`
- end: `0x18000baee`
- name: `DllGetClassObject`
- size: `46`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000bae3`
- `RPCRT4!NdrDllGetClassObject` at `0x18000bae3`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  return NdrDllGetClassObject(
           rclsid,
           riid,
           ppv,
           (const ProxyFileInfo **)&aProxyFileList,
           &CLSID_PSFactoryBuffer,
           &gPFactory);
}

```

## disassembly

```asm
0x18000bac0  sub     rsp, 38h
0x18000bac4  lea     rax, gPFactory
0x18000bacb  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000bad0  lea     r9, aProxyFileList; pProxyFileList
0x18000bad7  lea     rax, CLSID_PSFactoryBuffer
0x18000bade  mov     [rsp+38h+pclsid], rax; pclsid
0x18000bae3  call    cs:__imp_NdrDllGetClassObject
0x18000bae9  add     rsp, 38h
0x18000baed  retn
```
