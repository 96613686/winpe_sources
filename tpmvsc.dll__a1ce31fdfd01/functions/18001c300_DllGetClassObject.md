# DllGetClassObject

- ea: `0x18001c300`
- end: `0x18001c3fa`
- name: `DllGetClassObject`
- size: `250`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001ec0`
- `0x18001b200`
- `0x18001b2c4`
- `0x18001b490`
- `0x18001c300`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18001c3b3`
- `RPCRT4!NdrDllGetClassObject` at `0x18001c3b3`

## string_xrefs

- `0x18001c329`: `DllGetClassObject`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  struct ATL::_ATL_COM_MODULE70 *v7; // rcx
  HRESULT v8; // ebx
  HRESULT ClassObject; // [rsp+30h] [rbp-50h] BYREF
  int v11; // [rsp+34h] [rbp-4Ch] BYREF
  _QWORD *v12; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v13[3]; // [rsp+40h] [rbp-40h] BYREF
  char v14[24]; // [rsp+58h] [rbp-28h] BYREF

  ClassObject = 0;
  v13[0] = v14;
  v11 = 0;
  v13[1] = &v11;
  v13[2] = &ClassObject;
  strcpy(v14, "DllGetClassObject");
  lambda_20467aa9563538f1c1cb77e79f60d3a1_::operator()(v13);
  v11 = 1;
  v12 = v13;
  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  ClassObject = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  v8 = ClassObject;
  if ( ClassObject < 0 )
  {
    v8 = ATL::AtlComModuleGetClassObject(v7, rclsid, riid, ppv);
    ClassObject = v8;
  }
  WppTraceUnwinder__lambda_20467aa9563538f1c1cb77e79f60d3a1____::_WppTraceUnwinder__lambda_20467aa9563538f1c1cb77e79f60d3a1____(&v12);
  return v8;
}

```

## disassembly

```asm
0x18001c300  push    rbp
0x18001c302  push    rbx
0x18001c303  push    rsi
0x18001c304  push    rdi
0x18001c305  push    r14
0x18001c307  mov     rbp, rsp
0x18001c30a  sub     rsp, 80h
0x18001c311  mov     rax, cs:__security_cookie
0x18001c318  xor     rax, rsp
0x18001c31b  mov     [rbp+var_10], rax
0x18001c31f  movzx   eax, word ptr cs:aDllgetclassobj_0+10h; "t"
0x18001c326  mov     rdi, rcx
0x18001c329  movups  xmm0, xmmword ptr cs:aDllgetclassobj_0; "DllGetClassObject"
0x18001c330  mov     word ptr [rbp+var_28+10h], ax
0x18001c334  lea     rcx, [rbp+var_40]
0x18001c338  lea     rax, [rbp+var_28]
0x18001c33c  mov     [rbp+var_50], 0
0x18001c343  mov     [rbp+var_40], rax
0x18001c347  mov     r14, r8
0x18001c34a  lea     rax, [rbp+var_4C]
0x18001c34e  mov     [rbp+var_4C], 0
0x18001c355  mov     [rbp+var_38], rax
0x18001c359  mov     rsi, rdx
0x18001c35c  lea     rax, [rbp+var_50]
0x18001c360  mov     [rbp+var_30], rax
0x18001c364  movups  xmmword ptr [rbp+var_28], xmm0
0x18001c368  call    _lambda_20467aa9563538f1c1cb77e79f60d3a1___operator__
0x18001c36d  lea     rax, [rbp+var_40]
0x18001c371  mov     [rbp+var_4C], 1
0x18001c378  mov     [rbp+var_48], rax
0x18001c37c  mov     rax, cs:aProxyFileList
0x18001c383  mov     rcx, [rax+8]
0x18001c387  mov     rax, [rcx]
0x18001c38a  test    rax, rax
0x18001c38d  jz      short loc_18001C392
0x18001c38f  mov     rax, [rax]
0x18001c392  lea     rcx, gPFactory
0x18001c399  mov     r8, r14; ppv
0x18001c39c  mov     [rsp+80h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x18001c3a1  lea     r9, aProxyFileList; pProxyFileList
0x18001c3a8  mov     rcx, rdi; rclsid
0x18001c3ab  mov     [rsp+80h+pclsid], rax; pclsid
0x18001c3b0  mov     rdx, rsi; riid
0x18001c3b3  call    cs:__imp_NdrDllGetClassObject
0x18001c3b9  mov     [rbp+var_50], eax
0x18001c3bc  mov     ebx, eax
0x18001c3be  test    eax, eax
0x18001c3c0  jns     short loc_18001C3D5
0x18001c3c2  mov     r9, r14; void **
0x18001c3c5  mov     r8, rsi; struct _GUID *
0x18001c3c8  mov     rdx, rdi; struct _GUID *
0x18001c3cb  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18001c3d0  mov     ebx, eax
0x18001c3d2  mov     [rbp+var_50], eax
0x18001c3d5  lea     rcx, [rbp+var_48]
0x18001c3d9  call    WppTraceUnwinder__lambda_20467aa9563538f1c1cb77e79f60d3a1_______WppTraceUnwinder__lambda_20467aa9563538f1c1cb77e79f60d3a1____
0x18001c3de  mov     eax, ebx
0x18001c3e0  mov     rcx, [rbp+var_10]
0x18001c3e4  xor     rcx, rsp; StackCookie
0x18001c3e7  call    __security_check_cookie
0x18001c3ec  add     rsp, 80h
0x18001c3f3  pop     r14
0x18001c3f5  pop     rdi
0x18001c3f6  pop     rsi
0x18001c3f7  pop     rbx
0x18001c3f8  pop     rbp
0x18001c3f9  retn
```
