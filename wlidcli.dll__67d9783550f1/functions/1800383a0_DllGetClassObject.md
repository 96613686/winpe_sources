# DllGetClassObject

- ea: `0x1800383a0`
- end: `0x180038411`
- name: `DllGetClassObject`
- size: `113`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180038248`
- `0x1800383a0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800383e9`
- `RPCRT4!NdrDllGetClassObject` at `0x1800383e9`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  HRESULT result; // eax
  struct ATL::_ATL_COM_MODULE70 *v8; // rcx

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( result )
    return ATL::AtlComModuleGetClassObject(v8, rclsid, riid, ppv);
  return result;
}

```

## disassembly

```asm
0x1800383a0  mov     [rsp+arg_0], rbx
0x1800383a5  mov     [rsp+arg_8], rsi
0x1800383aa  push    rdi
0x1800383ab  sub     rsp, 30h
0x1800383af  mov     rax, cs:aProxyFileList
0x1800383b6  mov     rbx, r8
0x1800383b9  mov     rdi, rdx
0x1800383bc  mov     rsi, rcx
0x1800383bf  mov     r9, [rax+8]
0x1800383c3  mov     rax, [r9]
0x1800383c6  test    rax, rax
0x1800383c9  jz      short loc_1800383CE
0x1800383cb  mov     rax, [rax]
0x1800383ce  lea     rcx, gPFactory
0x1800383d5  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x1800383da  lea     r9, aProxyFileList; pProxyFileList
0x1800383e1  mov     rcx, rsi; rclsid
0x1800383e4  mov     [rsp+38h+pclsid], rax; pclsid
0x1800383e9  call    cs:__imp_NdrDllGetClassObject
0x1800383ef  test    eax, eax
0x1800383f1  jz      short loc_180038401
0x1800383f3  mov     r9, rbx; void **
0x1800383f6  mov     r8, rdi; struct _GUID *
0x1800383f9  mov     rdx, rsi; struct _GUID *
0x1800383fc  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180038401  mov     rbx, [rsp+38h+arg_0]
0x180038406  mov     rsi, [rsp+38h+arg_8]
0x18003840b  add     rsp, 30h
0x18003840f  pop     rdi
0x180038410  retn
```
