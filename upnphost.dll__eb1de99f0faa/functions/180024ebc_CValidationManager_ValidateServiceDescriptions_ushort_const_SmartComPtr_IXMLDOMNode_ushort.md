# CValidationManager::ValidateServiceDescriptions(ushort const *,SmartComPtr<IXMLDOMNode>,ushort * *)

- ea: `0x180024ebc`
- end: `0x18002500f`
- name: `?ValidateServiceDescriptions@CValidationManager@@AEAAJPEBGV?$SmartComPtr@UIXMLDOMNode@@@@PEAPEAG@Z`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800249e0`

## callees

- `0x1800117bc`
- `0x1800117d0`
- `0x180013870`
- `0x180024ebc`
- `0x180025018`
- `0x180025330`
- `0x180046540`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024f79`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024f82`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024f79`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024f82`

## string_xrefs

- `0x180024eea`: `//ddd:device/ddd:serviceList/ddd:service/ddd:SCPDURL`

## pseudocode

```c
__int64 __fastcall CValidationManager::ValidateServiceDescriptions(
        __int64 a1,
        const wchar_t *a2,
        __int64 a3,
        const wchar_t **a4)
{
  int NodeText; // edi
  wchar_t *v9; // rbx
  unsigned int v10; // ebx
  const wchar_t *v12; // r9
  void *Block; // [rsp+30h] [rbp-20h] BYREF
  STRSAFE_PCNZWCH v14; // [rsp+38h] [rbp-18h] BYREF
  __int64 v15; // [rsp+40h] [rbp-10h] BYREF
  __int64 v16; // [rsp+48h] [rbp-8h] BYREF

  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v16);
  NodeText = HrSelectNodes(L"//ddd:device/ddd:serviceList/ddd:service/ddd:SCPDURL", a3, &v16);
  while ( !NodeText )
  {
    SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v15);
    v9 = 0;
    v14 = 0;
    NodeText = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 72LL))(v16, &v15);
    if ( !NodeText )
    {
      NodeText = HrGetNodeText(&v15, &v14);
      if ( NodeText < 0 )
      {
        v9 = (wchar_t *)v14;
      }
      else
      {
        Block = 0;
        v9 = (wchar_t *)v14;
        NodeText = HrMakeFullPath(a2, v14, (struct CUString *)&Block);
        if ( NodeText >= 0 )
          NodeText = (*(__int64 (__fastcall **)(__int64, void *, const wchar_t **))(*(_QWORD *)a1 + 32LL))(
                       a1,
                       Block,
                       a4);
        free(Block);
      }
    }
    free(v9);
    ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v15);
  }
  v10 = 0;
  if ( NodeText < 0 )
    v10 = NodeText;
  if ( v10 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v12 = L"Unspecified";
    if ( *a4 )
      v12 = *a4;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      (unsigned int)WPP_e65b018b8a8f3bfaebbe1893d9f2a383_Traceguids,
      (_DWORD)v12,
      v10);
  }
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v16);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(a3);
  return v10;
}

```

## disassembly

```asm
0x180024ebc  push    rbp
0x180024ebe  push    rbx
0x180024ebf  push    rsi
0x180024ec0  push    rdi
0x180024ec1  push    r12
0x180024ec3  push    r14
0x180024ec5  push    r15
0x180024ec7  mov     rbp, rsp
0x180024eca  sub     rsp, 50h
0x180024ece  mov     r15, rcx
0x180024ed1  mov     r14, r9
0x180024ed4  lea     rcx, [rbp+var_8]; void *
0x180024ed8  mov     rsi, r8
0x180024edb  mov     r12, rdx
0x180024ede  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180024ee3  lea     r8, [rbp+var_8]
0x180024ee7  mov     rdx, rsi
0x180024eea  lea     rcx, aDddDeviceDddSe; "//ddd:device/ddd:serviceList/ddd:servic"...
0x180024ef1  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x180024ef6  mov     edi, eax
0x180024ef8  test    eax, eax
0x180024efa  jnz     loc_180024F99
0x180024f00  lea     rcx, [rbp+var_10]; void *
0x180024f04  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180024f09  mov     rcx, [rbp+var_8]
0x180024f0d  lea     rdx, [rbp+var_10]
0x180024f11  xor     ebx, ebx
0x180024f13  mov     [rbp+var_18], rbx
0x180024f17  mov     rax, [rcx]
0x180024f1a  mov     rax, [rax+48h]
0x180024f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f23  mov     edi, eax
0x180024f25  test    eax, eax
0x180024f27  jnz     short loc_180024F7F
0x180024f29  lea     rdx, [rbp+var_18]
0x180024f2d  lea     rcx, [rbp+var_10]
0x180024f31  call    ?HrGetNodeText@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrGetNodeText(SmartComPtr<IXMLDOMNode> &,CUString &)
0x180024f36  mov     edi, eax
0x180024f38  test    eax, eax
0x180024f3a  js      loc_180024FC6
0x180024f40  mov     [rbp+Block], rbx
0x180024f44  lea     r8, [rbp+Block]; struct CUString *
0x180024f48  mov     rbx, [rbp+var_18]
0x180024f4c  mov     rcx, r12; pszSrc
0x180024f4f  mov     rdx, rbx; STRSAFE_PCNZWCH
0x180024f52  call    ?HrMakeFullPath@@YAJPEBG0AEAVCUString@@@Z; HrMakeFullPath(ushort const *,ushort const *,CUString &)
0x180024f57  mov     edi, eax
0x180024f59  test    eax, eax
0x180024f5b  js      short loc_180024F75
0x180024f5d  mov     rax, [r15]
0x180024f60  mov     r8, r14
0x180024f63  mov     rdx, [rbp+Block]
0x180024f67  mov     rcx, r15
0x180024f6a  mov     rax, [rax+20h]
0x180024f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f73  mov     edi, eax
0x180024f75  mov     rcx, [rbp+Block]; Block
0x180024f79  call    cs:__imp_free
0x180024f7f  mov     rcx, rbx; Block
0x180024f82  call    cs:__imp_free
0x180024f88  lea     rcx, [rbp+var_10]
0x180024f8c  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180024f91  test    edi, edi
0x180024f93  jz      loc_180024F00
0x180024f99  xor     ebx, ebx
0x180024f9b  test    edi, edi
0x180024f9d  cmovs   ebx, edi
0x180024fa0  test    ebx, ebx
0x180024fa2  jnz     short loc_180024FCC
0x180024fa4  lea     rcx, [rbp+var_8]
0x180024fa8  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180024fad  mov     rcx, rsi
0x180024fb0  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180024fb5  mov     eax, ebx
0x180024fb7  add     rsp, 50h
0x180024fbb  pop     r15
0x180024fbd  pop     r14
0x180024fbf  pop     r12
0x180024fc1  pop     rdi
0x180024fc2  pop     rsi
0x180024fc3  pop     rbx
0x180024fc4  pop     rbp
0x180024fc5  retn
0x180024fc6  mov     rbx, [rbp+var_18]
0x180024fca  jmp     short loc_180024F7F
0x180024fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180024fd3  lea     rax, WPP_GLOBAL_Control
0x180024fda  cmp     rcx, rax
0x180024fdd  jz      short loc_180024FA4
0x180024fdf  test    byte ptr [rcx+1Ch], 1
0x180024fe3  jz      short loc_180024FA4
0x180024fe5  cmp     qword ptr [r14], 0
0x180024fe9  lea     r9, aUnspecified; "Unspecified"
0x180024ff0  mov     rcx, [rcx+10h]
0x180024ff4  lea     r8, WPP_e65b018b8a8f3bfaebbe1893d9f2a383_Traceguids
0x180024ffb  cmovnz  r9, [r14]
0x180024fff  mov     edx, 1Bh
0x180025004  mov     [rsp+50h+var_30], ebx
0x180025008  call    WPP_SF_Sd
0x18002500d  jmp     short loc_180024FA4
```
