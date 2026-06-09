# DllGetClassObject

- ea: `0x18001b0a0`
- end: `0x18001b11b`
- name: `DllGetClassObject`
- size: `123`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001931c`
- `0x18001b0a0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18001b105`
- `RPCRT4!NdrDllGetClassObject` at `0x18001b105`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  const PCInterfaceStubVtblList *pStubVtblList; // r9
  const CLSID *pclsid; // rcx

  result = ATL::CComModule::GetClassObject((ATL::CComModule *)rclsid, rclsid, riid, ppv);
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
0x18001b0a0  mov     [rsp+arg_0], rbx
0x18001b0a5  mov     [rsp+arg_8], rsi
0x18001b0aa  push    rdi
0x18001b0ab  sub     rsp, 30h
0x18001b0af  mov     rbx, r8
0x18001b0b2  mov     r9, r8; void **
0x18001b0b5  mov     r8, rdx; struct _GUID *
0x18001b0b8  mov     rdi, rdx
0x18001b0bb  mov     rdx, rcx; struct _GUID *
0x18001b0be  mov     rsi, rcx
0x18001b0c1  call    ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
0x18001b0c6  test    eax, eax
0x18001b0c8  jns     short loc_18001B10B
0x18001b0ca  mov     rax, cs:aProxyFileList
0x18001b0d1  mov     r9, [rax+8]
0x18001b0d5  mov     rax, [r9]
0x18001b0d8  test    rax, rax
0x18001b0db  jz      short loc_18001B0E2
0x18001b0dd  mov     rcx, [rax]
0x18001b0e0  jmp     short loc_18001B0E4
0x18001b0e2  xor     ecx, ecx
0x18001b0e4  lea     rax, gPFactory
0x18001b0eb  mov     r8, rbx; ppv
0x18001b0ee  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18001b0f3  lea     r9, aProxyFileList; pProxyFileList
0x18001b0fa  mov     [rsp+38h+pclsid], rcx; pclsid
0x18001b0ff  mov     rdx, rdi; riid
0x18001b102  mov     rcx, rsi; rclsid
0x18001b105  call    cs:__imp_NdrDllGetClassObject
0x18001b10b  mov     rbx, [rsp+38h+arg_0]
0x18001b110  mov     rsi, [rsp+38h+arg_8]
0x18001b115  add     rsp, 30h
0x18001b119  pop     rdi
0x18001b11a  retn
```
