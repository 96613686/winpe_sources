# DllGetClassObject

- ea: `0x18000d2f0`
- end: `0x18000d361`
- name: `DllGetClassObject`
- size: `113`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004948`
- `0x18000d2f0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000d339`
- `RPCRT4!NdrDllGetClassObject` at `0x18000d339`

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
  if ( result < 0 )
    return ATL::AtlComModuleGetClassObject(v8, rclsid, riid, ppv);
  return result;
}

```

## disassembly

```asm
0x18000d2f0  mov     [rsp+arg_0], rbx
0x18000d2f5  mov     [rsp+arg_8], rsi
0x18000d2fa  push    rdi
0x18000d2fb  sub     rsp, 30h
0x18000d2ff  mov     rax, cs:aProxyFileList
0x18000d306  mov     rbx, r8
0x18000d309  mov     rdi, rdx
0x18000d30c  mov     rsi, rcx
0x18000d30f  mov     r9, [rax+8]
0x18000d313  mov     rax, [r9]
0x18000d316  test    rax, rax
0x18000d319  jz      short loc_18000D31E
0x18000d31b  mov     rax, [rax]
0x18000d31e  lea     rcx, gPFactory
0x18000d325  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x18000d32a  lea     r9, aProxyFileList; pProxyFileList
0x18000d331  mov     rcx, rsi; rclsid
0x18000d334  mov     [rsp+38h+pclsid], rax; pclsid
0x18000d339  call    cs:__imp_NdrDllGetClassObject
0x18000d33f  test    eax, eax
0x18000d341  jns     short loc_18000D351
0x18000d343  mov     r9, rbx; void **
0x18000d346  mov     r8, rdi; struct _GUID *
0x18000d349  mov     rdx, rsi; struct _GUID *
0x18000d34c  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18000d351  mov     rbx, [rsp+38h+arg_0]
0x18000d356  mov     rsi, [rsp+38h+arg_8]
0x18000d35b  add     rsp, 30h
0x18000d35f  pop     rdi
0x18000d360  retn
```
