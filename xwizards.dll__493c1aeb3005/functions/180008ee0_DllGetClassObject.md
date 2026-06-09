# DllGetClassObject

- ea: `0x180008ee0`
- end: `0x180008f98`
- name: `DllGetClassObject`
- size: `184`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005fec`
- `0x180006200`
- `0x180006410`
- `0x180006620`
- `0x180008ee0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180008f29`
- `RPCRT4!NdrDllGetClassObject` at `0x180008f29`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  HRESULT result; // eax

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( result < 0 )
  {
    result = CFactory<CWPage,3>::GetClassObject((GUID *)rclsid);
    if ( result < 0 )
    {
      result = CFactory<CWTask,2>::GetClassObject((GUID *)rclsid, riid, (HKEY)ppv);
      if ( result < 0 )
      {
        result = CFactory<CWHost,1>::GetClassObject((GUID *)rclsid);
        if ( result < 0 )
        {
          if ( qword_18004CEC8 )
            return ATL::CComModule::GetClassObject((ATL::CComModule *)&_Module, rclsid, riid, ppv);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008ee0  mov     [rsp+arg_0], rbx
0x180008ee5  mov     [rsp+arg_8], rsi
0x180008eea  push    rdi
0x180008eeb  sub     rsp, 30h
0x180008eef  mov     rax, cs:aProxyFileList
0x180008ef6  mov     rbx, r8
0x180008ef9  mov     rdi, rdx
0x180008efc  mov     rsi, rcx
0x180008eff  mov     r9, [rax+8]
0x180008f03  mov     rax, [r9]
0x180008f06  test    rax, rax
0x180008f09  jz      short loc_180008F0E
0x180008f0b  mov     rax, [rax]
0x180008f0e  lea     rcx, gPFactory
0x180008f15  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x180008f1a  lea     r9, aProxyFileList; pProxyFileList
0x180008f21  mov     rcx, rsi; rclsid
0x180008f24  mov     [rsp+38h+pclsid], rax; pclsid
0x180008f29  call    cs:__imp_NdrDllGetClassObject
0x180008f2f  test    eax, eax
0x180008f31  jns     short loc_180008F88
0x180008f33  mov     r8, rbx
0x180008f36  mov     rdx, rdi
0x180008f39  mov     rcx, rsi; rguid
0x180008f3c  call    ?GetClassObject@?$CFactory@VCWPage@@$02@@SAJAEBU_GUID@@0PEAPEAX@Z; CFactory<CWPage,3>::GetClassObject(_GUID const &,_GUID const &,void * *)
0x180008f41  test    eax, eax
0x180008f43  jns     short loc_180008F88
0x180008f45  mov     r8, rbx
0x180008f48  mov     rdx, rdi
0x180008f4b  mov     rcx, rsi; rguid
0x180008f4e  call    ?GetClassObject@?$CFactory@VCWTask@@$01@@SAJAEBU_GUID@@0PEAPEAX@Z; CFactory<CWTask,2>::GetClassObject(_GUID const &,_GUID const &,void * *)
0x180008f53  test    eax, eax
0x180008f55  jns     short loc_180008F88
0x180008f57  mov     r8, rbx
0x180008f5a  mov     rdx, rdi
0x180008f5d  mov     rcx, rsi; rguid
0x180008f60  call    ?GetClassObject@?$CFactory@VCWHost@@$00@@SAJAEBU_GUID@@0PEAPEAX@Z; CFactory<CWHost,1>::GetClassObject(_GUID const &,_GUID const &,void * *)
0x180008f65  test    eax, eax
0x180008f67  jns     short loc_180008F88
0x180008f69  cmp     cs:qword_18004CEC8, 0
0x180008f71  jz      short loc_180008F88
0x180008f73  mov     r9, rbx; void **
0x180008f76  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x180008f7d  mov     r8, rdi; struct _GUID *
0x180008f80  mov     rdx, rsi; struct _GUID *
0x180008f83  call    ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
0x180008f88  mov     rbx, [rsp+38h+arg_0]
0x180008f8d  mov     rsi, [rsp+38h+arg_8]
0x180008f92  add     rsp, 30h
0x180008f96  pop     rdi
0x180008f97  retn
```
