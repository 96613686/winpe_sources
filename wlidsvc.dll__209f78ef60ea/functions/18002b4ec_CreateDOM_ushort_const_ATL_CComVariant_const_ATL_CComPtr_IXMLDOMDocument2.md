# CreateDOM(ushort const *,ATL::CComVariant const &,ATL::CComPtr<IXMLDOMDocument2> &)

- ea: `0x18002b4ec`
- end: `0x18002b77f`
- name: `?CreateDOM@@YAJPEBGAEBVCComVariant@ATL@@AEAV?$CComPtr@UIXMLDOMDocument2@@@2@@Z`
- size: `659`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002b068`
- `0x1800f479c`

## callees

- `0x18000c050`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18002b4ec`
- `0x180039ee8`
- `0x1800406a8`
- `0x180044598`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b58a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b58a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b5fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b65d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b713`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b5fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b65d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b713`

## string_xrefs

- `0x18002b526`: `CreateDOM`
- `0x18002b72f`: `wszXml != nullptr && *wszXml != L'\0'`
- `0x18002b597`: `hr = pDOMXml.CoCreateInstance(CLSID_DOMDocument60)`
- `0x18002b607`: `hr = pDOMXml->setProperty(CComBSTR(XML_PROP_SELECTION_NAMESPACES), cvNamespaces)`
- `0x18002b667`: `hr = pDOMXml->loadXML(CComBSTR(wszXml), &bParsedOK)`
- `0x18002b6e1`: `XML load for text failed at %d: %ls.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CreateDOM(unsigned __int16 *a1, __int128 *a2, LPVOID *a3)
{
  HRESULT Instance; // eax
  int v7; // r9d
  unsigned int v8; // r8d
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, _QWORD, __int128 *); // rbx
  __int128 v11; // xmm6
  __int64 v12; // xmm7_8
  ATL::CComBSTR *v13; // rax
  int v14; // ebx
  const char *v15; // rax
  unsigned int v16; // r8d
  LPVOID v17; // rdi
  __int64 (__fastcall *v18)(LPVOID, _QWORD, __int16 *); // rbx
  ATL::CComBSTR *v19; // rax
  unsigned int v20; // ebx
  LPVOID *ppv; // [rsp+28h] [rbp-69h]
  LPVOID *ppva; // [rsp+28h] [rbp-69h]
  const char *ppvb; // [rsp+28h] [rbp-69h]
  int v25; // [rsp+38h] [rbp-59h] BYREF
  __int64 v26; // [rsp+40h] [rbp-51h] BYREF
  BSTR bstrString[2]; // [rsp+48h] [rbp-49h] BYREF
  __int128 v28; // [rsp+58h] [rbp-39h] BYREF
  __int64 v29; // [rsp+68h] [rbp-29h]
  _QWORD v30[8]; // [rsp+78h] [rbp-19h] BYREF
  __int16 v31; // [rsp+F8h] [rbp+67h] BYREF
  int v32; // [rsp+110h] [rbp+7Fh] BYREF

  v32 = 0;
  v31 = 0;
  v30[0] = "CreateDOM";
  v30[1] = &v32;
  v30[2] = 0;
  v30[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\util.cpp",
    "CreateDOM",
    (const char *)0x1E1,
    0,
    (const unsigned __int16 *)ppv);
  if ( !a1 || !*a1 )
  {
    v7 = -2147188642;
    v32 = -2147188642;
    ppvb = "wszXml != nullptr && *wszXml != L'\\0'";
    v8 = 483;
    goto LABEL_15;
  }
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, a3);
  v32 = Instance;
  if ( Instance < 0 )
  {
    ppvb = "hr = pDOMXml.CoCreateInstance(CLSID_DOMDocument60)";
    v7 = Instance;
    v8 = 485;
LABEL_15:
    Telemetry::IfFailExit("onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\util.cpp", "CreateDOM", v8, v7, ppvb);
    goto LABEL_16;
  }
  v9 = *a3;
  v10 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int128 *))(*(_QWORD *)*a3 + 640LL);
  v11 = *a2;
  v12 = *((_QWORD *)a2 + 2);
  v13 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"SelectionNamespaces");
  v28 = v11;
  v29 = v12;
  v14 = v10(v9, *(_QWORD *)v13, &v28);
  v32 = v14;
  SysFreeString(bstrString[0]);
  if ( v14 < 0 )
  {
    v15 = "hr = pDOMXml->setProperty(CComBSTR(XML_PROP_SELECTION_NAMESPACES), cvNamespaces)";
    v16 = 487;
LABEL_7:
    Telemetry::IfFailExit("onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\util.cpp", "CreateDOM", v16, v14, v15);
    goto LABEL_16;
  }
  v17 = *a3;
  v18 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int16 *))(*(_QWORD *)*a3 + 520LL);
  v19 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, a1);
  v14 = v18(v17, *(_QWORD *)v19, &v31);
  v32 = v14;
  SysFreeString(bstrString[0]);
  if ( v14 < 0 )
  {
    v15 = "hr = pDOMXml->loadXML(CComBSTR(wszXml), &bParsedOK)";
    v16 = 489;
    goto LABEL_7;
  }
  if ( v31 != -1 )
  {
    v26 = 0;
    bstrString[0] = 0;
    v25 = -1;
    (*(void (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)*a3 + 480LL))(*a3, &v26);
    if ( v26 )
    {
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v26 + 72LL))(v26, bstrString);
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 88LL))(v26, &v25);
      LODWORD(ppva) = v25;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\util.cpp",
        0x1F6u,
        L"XML load for text failed at %d: %ls.",
        ppva,
        bstrString[0]);
    }
    v32 = -2147188477;
    ATL::CComPtrBase<IXMLDOMNodeList>::Release(a3);
    SysFreeString(bstrString[0]);
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v26);
  }
LABEL_16:
  v20 = v32;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v30);
  return v20;
}

```

## disassembly

```asm
0x18002b4ec  mov     rax, rsp
0x18002b4ef  mov     [rax+10h], rbx
0x18002b4f3  push    rbp
0x18002b4f4  push    rsi
0x18002b4f5  push    rdi
0x18002b4f6  push    r12
0x18002b4f8  push    r13
0x18002b4fa  push    r14
0x18002b4fc  push    r15
0x18002b4fe  lea     rbp, [rax-5Fh]
0x18002b502  sub     rsp, 0B0h
0x18002b509  movaps  xmmword ptr [rax-48h], xmm6
0x18002b50d  movaps  xmmword ptr [rax-58h], xmm7
0x18002b511  mov     rsi, r8
0x18002b514  mov     r15, rdx
0x18002b517  mov     r14, rcx
0x18002b51a  xor     r12d, r12d
0x18002b51d  mov     [rbp+57h+arg_18], r12d
0x18002b521  mov     [rbp+57h+arg_0], r12w
0x18002b526  lea     r13, aCreatedom; "CreateDOM"
0x18002b52d  mov     [rbp+57h+var_70], r13
0x18002b531  lea     rax, [rbp+57h+arg_18]
0x18002b535  mov     [rbp+57h+var_68], rax
0x18002b539  mov     [rbp+57h+var_60], r12
0x18002b53d  mov     [rbp+57h+var_58], r12
0x18002b541  xor     r9d, r9d; unsigned int
0x18002b544  mov     r8d, 1E1h; char *
0x18002b54a  mov     rdx, r13; char *
0x18002b54d  lea     rbx, aOnecoreuapDsEx_47; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002b554  mov     rcx, rbx; this
0x18002b557  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18002b55c  nop
0x18002b55d  test    r14, r14
0x18002b560  jz      loc_18002B725
0x18002b566  cmp     [r14], r12w
0x18002b56a  jz      loc_18002B725
0x18002b570  mov     [rsp+0E0h+ppv], rsi; ppv
0x18002b575  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18002b57c  xor     edx, edx; pUnkOuter
0x18002b57e  lea     r8d, [r12+17h]; dwClsContext
0x18002b583  lea     rcx, CLSID_DOMDocument60; rclsid
0x18002b58a  call    cs:__imp_CoCreateInstance
0x18002b590  mov     [rbp+57h+arg_18], eax
0x18002b593  test    eax, eax
0x18002b595  jns     short loc_18002B5B1
0x18002b597  lea     r8, aHrPdomxmlCocre; "hr = pDOMXml.CoCreateInstance(CLSID_DOM"...
0x18002b59e  mov     [rsp+0E0h+ppv], r8
0x18002b5a3  mov     r9d, eax
0x18002b5a6  mov     r8d, 1E5h
0x18002b5ac  jmp     loc_18002B741
0x18002b5b1  mov     rdi, [rsi]
0x18002b5b4  mov     rax, [rdi]
0x18002b5b7  mov     rbx, [rax+280h]
0x18002b5be  movups  xmm6, xmmword ptr [r15]
0x18002b5c2  movsd   xmm7, qword ptr [r15+10h]
0x18002b5c8  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18002b5cf  lea     rcx, [rbp+57h+bstrString]; this
0x18002b5d3  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002b5d8  nop
0x18002b5d9  movaps  [rbp+57h+var_90], xmm6
0x18002b5dd  movsd   [rbp+57h+var_80], xmm7
0x18002b5e2  lea     r8, [rbp+57h+var_90]
0x18002b5e6  mov     rdx, [rax]
0x18002b5e9  mov     rcx, rdi
0x18002b5ec  mov     rax, rbx
0x18002b5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5f4  mov     ebx, eax
0x18002b5f6  mov     [rbp+57h+arg_18], eax
0x18002b5f9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002b5fd  call    cs:__imp_SysFreeString
0x18002b603  test    ebx, ebx
0x18002b605  jns     short loc_18002B628
0x18002b607  lea     rax, aHrPdomxmlSetpr; "hr = pDOMXml->setProperty(CComBSTR(XML_"...
0x18002b60e  mov     r8d, 1E7h
0x18002b614  mov     r9d, ebx
0x18002b617  mov     [rsp+0E0h+ppv], rax
0x18002b61c  lea     rcx, aOnecoreuapDsEx_47; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002b623  jmp     loc_18002B744
0x18002b628  mov     rdi, [rsi]
0x18002b62b  mov     rax, [rdi]
0x18002b62e  mov     rbx, [rax+208h]
0x18002b635  mov     rdx, r14; unsigned __int16 *
0x18002b638  lea     rcx, [rbp+57h+bstrString]; this
0x18002b63c  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002b641  nop
0x18002b642  lea     r8, [rbp+57h+arg_0]
0x18002b646  mov     rdx, [rax]
0x18002b649  mov     rcx, rdi
0x18002b64c  mov     rax, rbx
0x18002b64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b654  mov     ebx, eax
0x18002b656  mov     [rbp+57h+arg_18], eax
0x18002b659  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002b65d  call    cs:__imp_SysFreeString
0x18002b663  test    ebx, ebx
0x18002b665  jns     short loc_18002B676
0x18002b667  lea     rax, aHrPdomxmlLoadx; "hr = pDOMXml->loadXML(CComBSTR(wszXml),"...
0x18002b66e  mov     r8d, 1E9h
0x18002b674  jmp     short loc_18002B614
0x18002b676  or      eax, 0FFFFFFFFh
0x18002b679  cmp     [rbp+57h+arg_0], ax
0x18002b67d  jz      loc_18002B74C
0x18002b683  mov     [rbp+57h+var_A8], r12
0x18002b687  mov     [rbp+57h+bstrString], r12
0x18002b68b  mov     [rbp+57h+var_B0], eax
0x18002b68e  mov     rcx, [rsi]
0x18002b691  mov     rax, [rcx]
0x18002b694  lea     rdx, [rbp+57h+var_A8]
0x18002b698  mov     rax, [rax+1E0h]
0x18002b69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6a4  mov     rcx, [rbp+57h+var_A8]
0x18002b6a8  test    rcx, rcx
0x18002b6ab  jz      short loc_18002B6FF
0x18002b6ad  mov     rax, [rcx]
0x18002b6b0  lea     rdx, [rbp+57h+bstrString]
0x18002b6b4  mov     rax, [rax+48h]
0x18002b6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6bd  mov     rcx, [rbp+57h+var_A8]
0x18002b6c1  mov     rax, [rcx]
0x18002b6c4  lea     rdx, [rbp+57h+var_B0]
0x18002b6c8  mov     rax, [rax+58h]
0x18002b6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6d1  mov     rax, [rbp+57h+bstrString]
0x18002b6d5  mov     [rsp+0E0h+var_B8], rax
0x18002b6da  mov     eax, [rbp+57h+var_B0]
0x18002b6dd  mov     dword ptr [rsp+0E0h+ppv], eax
0x18002b6e1  lea     r9, aXmlLoadForText; "XML load for text failed at %d: %ls."
0x18002b6e8  mov     r8d, 1F6h; unsigned int
0x18002b6ee  lea     rdx, aOnecoreuapDsEx_47; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002b6f5  mov     ecx, 2; unsigned __int8
0x18002b6fa  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002b6ff  mov     [rbp+57h+arg_18], 80048103h
0x18002b706  mov     rcx, rsi
0x18002b709  call    ?Release@?$CComPtrBase@UIXMLDOMNodeList@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMNodeList>::Release(void)
0x18002b70e  nop
0x18002b70f  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002b713  call    cs:__imp_SysFreeString
0x18002b719  nop
0x18002b71a  lea     rcx, [rbp+57h+var_A8]
0x18002b71e  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18002b723  jmp     short loc_18002B74C
0x18002b725  mov     r9d, 8004805Eh; int
0x18002b72b  mov     [rbp+57h+arg_18], r9d
0x18002b72f  lea     rax, aWszxmlNullptrW; "wszXml != nullptr && *wszXml != L'\\0'"
0x18002b736  mov     [rsp+0E0h+ppv], rax; char *
0x18002b73b  mov     r8d, 1E3h; unsigned int
0x18002b741  mov     rcx, rbx; char *
0x18002b744  mov     rdx, r13; char *
0x18002b747  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18002b74c  mov     ebx, [rbp+57h+arg_18]
0x18002b74f  lea     rcx, [rbp+57h+var_70]
0x18002b753  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002b758  mov     eax, ebx
0x18002b75a  lea     r11, [rsp+0E0h+var_30]
0x18002b762  mov     rbx, [r11+48h]
0x18002b766  movaps  xmm6, xmmword ptr [r11-10h]
0x18002b76b  movaps  xmm7, xmmword ptr [r11-20h]
0x18002b770  mov     rsp, r11
0x18002b773  pop     r15
0x18002b775  pop     r14
0x18002b777  pop     r13
0x18002b779  pop     r12
0x18002b77b  pop     rdi
0x18002b77c  pop     rsi
0x18002b77d  pop     rbp
0x18002b77e  retn
```
