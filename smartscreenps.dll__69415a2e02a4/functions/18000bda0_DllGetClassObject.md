# DllGetClassObject

- ea: `0x18000bda0`
- end: `0x18000bdd5`
- name: `DllGetClassObject`
- size: `53`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000bdc3`
- `RPCRT4!NdrDllGetClassObject` at `0x18000bdc3`

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
0x18000bda0  sub     rsp, 38h
0x18000bda4  lea     rax, gPFactory
0x18000bdab  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000bdb0  lea     r9, aProxyFileList; pProxyFileList
0x18000bdb7  lea     rax, CLSID_PSFactoryBuffer
0x18000bdbe  mov     [rsp+38h+pclsid], rax; pclsid
0x18000bdc3  call    cs:__imp_NdrDllGetClassObject
0x18000bdca  nop     dword ptr [rax+rax+00h]
0x18000bdcf  add     rsp, 38h
0x18000bdd3  retn
```
