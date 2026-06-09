# CValidationManager::ValidateServiceDescriptions(ushort const *,SmartComPtr<IXMLDOMNode>,ushort * *)

- ea: `0x180025bb4`
- end: `0x180025d14`
- name: `?ValidateServiceDescriptions@CValidationManager@@AEAAJPEBGV?$SmartComPtr@UIXMLDOMNode@@@@PEAPEAG@Z`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003f30`

## callees

- `0x180003e08`
- `0x1800056d8`
- `0x1800056f0`
- `0x180007920`
- `0x180025bb4`
- `0x180025fa4`
- `0x180049258`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025c71`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025c80`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025c71`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025c80`

## string_xrefs

- `0x180025be2`: `//ddd:device/ddd:serviceList/ddd:service/ddd:SCPDURL`

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
  _BYTE v15[8]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v16; // [rsp+48h] [rbp-8h] BYREF

  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v16);
  NodeText = HrSelectNodes(L"//ddd:device/ddd:serviceList/ddd:service/ddd:SCPDURL", a3, &v16);
  while ( !NodeText )
  {
    SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v15);
    v9 = 0;
    v14 = 0;
    NodeText = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v16 + 72LL))(v16, v15);
    if ( !NodeText )
    {
      NodeText = HrGetNodeText(v15, &v14);
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
    ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v15);
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
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v16);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(a3);
  return v10;
}

```

## disassembly

```asm
0x180025bb4  push    rbp
0x180025bb6  push    rbx
0x180025bb7  push    rsi
0x180025bb8  push    rdi
0x180025bb9  push    r12
0x180025bbb  push    r14
0x180025bbd  push    r15
0x180025bbf  mov     rbp, rsp
0x180025bc2  sub     rsp, 50h
0x180025bc6  mov     r15, rcx
0x180025bc9  mov     r14, r9
0x180025bcc  lea     rcx, [rbp+var_8]; void *
0x180025bd0  mov     rsi, r8
0x180025bd3  mov     r12, rdx
0x180025bd6  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180025bdb  lea     r8, [rbp+var_8]
0x180025bdf  mov     rdx, rsi
0x180025be2  lea     rcx, aDddDeviceDddSe; "//ddd:device/ddd:serviceList/ddd:servic"...
0x180025be9  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x180025bee  mov     edi, eax
0x180025bf0  test    eax, eax
0x180025bf2  jnz     loc_180025C9D
0x180025bf8  lea     rcx, [rbp+var_10]; void *
0x180025bfc  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180025c01  mov     rcx, [rbp+var_8]
0x180025c05  lea     rdx, [rbp+var_10]
0x180025c09  xor     ebx, ebx
0x180025c0b  mov     [rbp+var_18], rbx
0x180025c0f  mov     rax, [rcx]
0x180025c12  mov     rax, [rax+48h]
0x180025c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c1b  mov     edi, eax
0x180025c1d  test    eax, eax
0x180025c1f  jnz     short loc_180025C7D
0x180025c21  lea     rdx, [rbp+var_18]
0x180025c25  lea     rcx, [rbp+var_10]
0x180025c29  call    ?HrGetNodeText@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrGetNodeText(SmartComPtr<IXMLDOMNode> &,CUString &)
0x180025c2e  mov     edi, eax
0x180025c30  test    eax, eax
0x180025c32  js      loc_180025CCB
0x180025c38  mov     [rbp+Block], rbx
0x180025c3c  lea     r8, [rbp+Block]; struct CUString *
0x180025c40  mov     rbx, [rbp+var_18]
0x180025c44  mov     rcx, r12; pszSrc
0x180025c47  mov     rdx, rbx; STRSAFE_PCNZWCH
0x180025c4a  call    ?HrMakeFullPath@@YAJPEBG0AEAVCUString@@@Z; HrMakeFullPath(ushort const *,ushort const *,CUString &)
0x180025c4f  mov     edi, eax
0x180025c51  test    eax, eax
0x180025c53  js      short loc_180025C6D
0x180025c55  mov     rax, [r15]
0x180025c58  mov     r8, r14
0x180025c5b  mov     rdx, [rbp+Block]
0x180025c5f  mov     rcx, r15
0x180025c62  mov     rax, [rax+20h]
0x180025c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c6b  mov     edi, eax
0x180025c6d  mov     rcx, [rbp+Block]; Block
0x180025c71  call    cs:__imp_free
0x180025c78  nop     dword ptr [rax+rax+00h]
0x180025c7d  mov     rcx, rbx; Block
0x180025c80  call    cs:__imp_free
0x180025c87  nop     dword ptr [rax+rax+00h]
0x180025c8c  lea     rcx, [rbp+var_10]
0x180025c90  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180025c95  test    edi, edi
0x180025c97  jz      loc_180025BF8
0x180025c9d  xor     ebx, ebx
0x180025c9f  test    edi, edi
0x180025ca1  cmovs   ebx, edi
0x180025ca4  test    ebx, ebx
0x180025ca6  jnz     short loc_180025CD1
0x180025ca8  lea     rcx, [rbp+var_8]
0x180025cac  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180025cb1  mov     rcx, rsi
0x180025cb4  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180025cb9  mov     eax, ebx
0x180025cbb  add     rsp, 50h
0x180025cbf  pop     r15
0x180025cc1  pop     r14
0x180025cc3  pop     r12
0x180025cc5  pop     rdi
0x180025cc6  pop     rsi
0x180025cc7  pop     rbx
0x180025cc8  pop     rbp
0x180025cc9  retn
0x180025ccb  mov     rbx, [rbp+var_18]
0x180025ccf  jmp     short loc_180025C7D
0x180025cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cd8  lea     rax, WPP_GLOBAL_Control
0x180025cdf  cmp     rcx, rax
0x180025ce2  jz      short loc_180025CA8
0x180025ce4  test    byte ptr [rcx+1Ch], 1
0x180025ce8  jz      short loc_180025CA8
0x180025cea  cmp     qword ptr [r14], 0
0x180025cee  lea     r9, aUnspecified; "Unspecified"
0x180025cf5  mov     rcx, [rcx+10h]
0x180025cf9  lea     r8, WPP_e65b018b8a8f3bfaebbe1893d9f2a383_Traceguids
0x180025d00  cmovnz  r9, [r14]
0x180025d04  mov     edx, 1Bh
0x180025d09  mov     [rsp+50h+var_30], ebx
0x180025d0d  call    WPP_SF_Sd
0x180025d12  jmp     short loc_180025CA8
```
