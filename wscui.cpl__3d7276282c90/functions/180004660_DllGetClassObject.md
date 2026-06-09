# DllGetClassObject

- ea: `0x180004660`
- end: `0x18000470b`
- name: `DllGetClassObject`
- size: `171`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004258`
- `0x1800043e4`
- `0x180004660`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180004697`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046a2`
- `OLEAUT32!__imp_SysFreeString` at `0x180004697`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046a2`
- `RPCRT4!NdrDllGetClassObject` at `0x1800046f5`
- `RPCRT4!NdrDllGetClassObject` at `0x1800046f5`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  struct ATL::_ATL_COM_MODULE70 *v6; // rcx
  HRESULT result; // eax
  const PCInterfaceStubVtblList *pStubVtblList; // rcx
  const CLSID *pclsid; // rcx
  BSTR v10[3]; // [rsp+30h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+20h] BYREF

  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v10, rclsid);
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, riid);
  SysFreeString(bstrString);
  SysFreeString(v10[0]);
  result = ATL::AtlComModuleGetClassObject(v6, rclsid, riid, ppv);
  if ( result < 0 )
  {
    pStubVtblList = aProxyFileList->pStubVtblList;
    if ( *pStubVtblList )
      pclsid = **(const CLSID ***)pStubVtblList;
    else
      pclsid = 0;
    return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  }
  return result;
}

```

## disassembly

```asm
0x180004660  mov     [rsp+arg_0], rbx
0x180004665  mov     [rsp+arg_8], rsi
0x18000466a  push    rdi
0x18000466b  sub     rsp, 40h
0x18000466f  mov     rbx, rdx
0x180004672  mov     rdi, rcx
0x180004675  mov     rdx, rcx; struct _GUID *
0x180004678  mov     rsi, r8
0x18000467b  lea     rcx, [rsp+48h+var_18]; this
0x180004680  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x180004685  mov     rdx, rbx; struct _GUID *
0x180004688  lea     rcx, [rsp+48h+bstrString]; this
0x18000468d  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x180004692  mov     rcx, [rsp+48h+bstrString]; bstrString
0x180004697  call    cs:__imp_SysFreeString
0x18000469d  mov     rcx, [rsp+48h+var_18]; bstrString
0x1800046a2  call    cs:__imp_SysFreeString
0x1800046a8  mov     r9, rsi; void **
0x1800046ab  mov     r8, rbx; struct _GUID *
0x1800046ae  mov     rdx, rdi; struct _GUID *
0x1800046b1  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800046b6  test    eax, eax
0x1800046b8  jns     short loc_1800046FB
0x1800046ba  mov     rax, cs:aProxyFileList
0x1800046c1  mov     rcx, [rax+8]
0x1800046c5  mov     rax, [rcx]
0x1800046c8  test    rax, rax
0x1800046cb  jz      short loc_1800046D2
0x1800046cd  mov     rcx, [rax]
0x1800046d0  jmp     short loc_1800046D4
0x1800046d2  xor     ecx, ecx
0x1800046d4  lea     rax, gPFactory
0x1800046db  mov     r8, rsi; ppv
0x1800046de  mov     [rsp+48h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x1800046e3  lea     r9, aProxyFileList; pProxyFileList
0x1800046ea  mov     [rsp+48h+pclsid], rcx; pclsid
0x1800046ef  mov     rdx, rbx; riid
0x1800046f2  mov     rcx, rdi; rclsid
0x1800046f5  call    cs:__imp_NdrDllGetClassObject
0x1800046fb  mov     rbx, [rsp+48h+arg_0]
0x180004700  mov     rsi, [rsp+48h+arg_8]
0x180004705  add     rsp, 40h
0x180004709  pop     rdi
0x18000470a  retn
```
