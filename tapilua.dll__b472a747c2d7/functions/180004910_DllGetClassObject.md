# DllGetClassObject

- ea: `0x180004910`
- end: `0x18000498b`
- name: `DllGetClassObject`
- size: `123`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002780`
- `0x180004910`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180004975`
- `RPCRT4!NdrDllGetClassObject` at `0x180004975`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  const PCInterfaceStubVtblList *pStubVtblList; // r9
  const CLSID *pclsid; // rcx

  result = ATL::AtlModuleGetClassObject((struct ATL::_ATL_MODULE *)rclsid, rclsid, riid, ppv);
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
0x180004910  mov     [rsp+arg_0], rbx
0x180004915  mov     [rsp+arg_8], rsi
0x18000491a  push    rdi
0x18000491b  sub     rsp, 30h
0x18000491f  mov     rbx, r8
0x180004922  mov     r9, r8; void **
0x180004925  mov     r8, rdx; struct _GUID *
0x180004928  mov     rdi, rdx
0x18000492b  mov     rdx, rcx; struct _GUID *
0x18000492e  mov     rsi, rcx
0x180004931  call    ?AtlModuleGetClassObject@ATL@@YAJPEAU_ATL_MODULE@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlModuleGetClassObject(ATL::_ATL_MODULE *,_GUID const &,_GUID const &,void * *)
0x180004936  test    eax, eax
0x180004938  jns     short loc_18000497B
0x18000493a  mov     rax, cs:aProxyFileList
0x180004941  mov     r9, [rax+8]
0x180004945  mov     rax, [r9]
0x180004948  test    rax, rax
0x18000494b  jz      short loc_180004952
0x18000494d  mov     rcx, [rax]
0x180004950  jmp     short loc_180004954
0x180004952  xor     ecx, ecx
0x180004954  lea     rax, gPFactory
0x18000495b  mov     r8, rbx; ppv
0x18000495e  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180004963  lea     r9, aProxyFileList; pProxyFileList
0x18000496a  mov     [rsp+38h+pclsid], rcx; pclsid
0x18000496f  mov     rdx, rdi; riid
0x180004972  mov     rcx, rsi; rclsid
0x180004975  call    cs:__imp_NdrDllGetClassObject
0x18000497b  mov     rbx, [rsp+38h+arg_0]
0x180004980  mov     rsi, [rsp+38h+arg_8]
0x180004985  add     rsp, 30h
0x180004989  pop     rdi
0x18000498a  retn
```
