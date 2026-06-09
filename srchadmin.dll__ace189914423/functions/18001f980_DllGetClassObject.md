# DllGetClassObject

- ea: `0x18001f980`
- end: `0x18001f9f1`
- name: `DllGetClassObject`
- size: `113`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001c898`
- `0x18001f980`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18001f9c9`
- `RPCRT4!NdrDllGetClassObject` at `0x18001f9c9`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  HRESULT result; // eax
  ATL::CComModule *v8; // rcx

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( result )
    return ATL::CComModule::GetClassObject(v8, rclsid, riid, ppv);
  return result;
}

```

## disassembly

```asm
0x18001f980  mov     [rsp+arg_0], rbx
0x18001f985  mov     [rsp+arg_8], rsi
0x18001f98a  push    rdi
0x18001f98b  sub     rsp, 30h
0x18001f98f  mov     rax, cs:aProxyFileList
0x18001f996  mov     rbx, r8
0x18001f999  mov     rdi, rdx
0x18001f99c  mov     rsi, rcx
0x18001f99f  mov     r9, [rax+8]
0x18001f9a3  mov     rax, [r9]
0x18001f9a6  test    rax, rax
0x18001f9a9  jz      short loc_18001F9AE
0x18001f9ab  mov     rax, [rax]
0x18001f9ae  lea     rcx, gPFactory
0x18001f9b5  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x18001f9ba  lea     r9, aProxyFileList; pProxyFileList
0x18001f9c1  mov     rcx, rsi; rclsid
0x18001f9c4  mov     [rsp+38h+pclsid], rax; pclsid
0x18001f9c9  call    cs:__imp_NdrDllGetClassObject
0x18001f9cf  test    eax, eax
0x18001f9d1  jz      short loc_18001F9E1
0x18001f9d3  mov     r9, rbx; void **
0x18001f9d6  mov     r8, rdi; struct _GUID *
0x18001f9d9  mov     rdx, rsi; struct _GUID *
0x18001f9dc  call    ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
0x18001f9e1  mov     rbx, [rsp+38h+arg_0]
0x18001f9e6  mov     rsi, [rsp+38h+arg_8]
0x18001f9eb  add     rsp, 30h
0x18001f9ef  pop     rdi
0x18001f9f0  retn
```
