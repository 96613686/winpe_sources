# CreateDOM(ushort const *,ATL::CComVariant const &,ATL::CComPtr<IXMLDOMDocument2> &)

- ea: `0x1800547c4`
- end: `0x180054a66`
- name: `?CreateDOM@@YAJPEBGAEBVCComVariant@ATL@@AEAV?$CComPtr@UIXMLDOMDocument2@@@2@@Z`
- size: `674`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int128 *, LPVOID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ee6c`
- `0x18003d850`

## callees

- `0x18000cc9c`
- `0x18000e870`
- `0x180013384`
- `0x180013638`
- `0x1800530e4`
- `0x180053890`
- `0x1800547c4`
- `0x180063010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800548d5`
- `OLEAUT32!__imp_SysFreeString` at `0x180054935`
- `OLEAUT32!__imp_SysFreeString` at `0x1800549fa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800548d5`
- `OLEAUT32!__imp_SysFreeString` at `0x180054935`
- `OLEAUT32!__imp_SysFreeString` at `0x1800549fa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054862`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054862`

## string_xrefs

- `0x1800547fe`: `CreateDOM`
- `0x180054a16`: `wszXml != nullptr && *wszXml != L'\0'`
- `0x18005486f`: `hr = pDOMXml.CoCreateInstance(CLSID_DOMDocument60)`
- `0x1800548df`: `hr = pDOMXml->setProperty(CComBSTR(XML_PROP_SELECTION_NAMESPACES), cvNamespaces)`
- `0x18005493f`: `hr = pDOMXml->loadXML(CComBSTR(wszXml), &bParsedOK)`
- `0x1800549b9`: `XML load for text failed at %d: %ls.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateDOM(unsigned __int16 *a1, __int128 *a2, LPVOID *a3)
{
  HRESULT Instance; // eax
  int v7; // r9d
  unsigned int v8; // r8d
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, _QWORD, __int128 *); // rbx
  __int128 v11; // xmm6
  __int64 v12; // xmm7_8
  _QWORD *v13; // rax
  int v14; // ebx
  const char *v15; // rax
  unsigned int v16; // r8d
  LPVOID v17; // rdi
  __int64 (__fastcall *v18)(LPVOID, _QWORD, __int16 *); // rbx
  _QWORD *v19; // rax
  LPVOID v20; // rcx
  unsigned int v21; // ebx
  LPVOID *ppv; // [rsp+28h] [rbp-69h]
  LPVOID *ppva; // [rsp+28h] [rbp-69h]
  const char *ppvb; // [rsp+28h] [rbp-69h]
  int v26; // [rsp+38h] [rbp-59h] BYREF
  __int64 v27; // [rsp+40h] [rbp-51h] BYREF
  BSTR bstrString[2]; // [rsp+48h] [rbp-49h] BYREF
  __int128 v29; // [rsp+58h] [rbp-39h] BYREF
  __int64 v30; // [rsp+68h] [rbp-29h]
  _QWORD v31[8]; // [rsp+78h] [rbp-19h] BYREF
  __int16 v32; // [rsp+F8h] [rbp+67h] BYREF
  int v33; // [rsp+110h] [rbp+7Fh] BYREF

  v33 = 0;
  v32 = 0;
  v31[0] = "CreateDOM";
  v31[1] = &v33;
  v31[2] = 0;
  v31[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\util.cpp",
    "CreateDOM",
    (const char *)0x1E1,
    0,
    (const unsigned __int16 *)ppv);
  if ( !a1 || !*a1 )
  {
    v7 = -2147188642;
    v33 = -2147188642;
    ppvb = "wszXml != nullptr && *wszXml != L'\\0'";
    v8 = 483;
    goto LABEL_17;
  }
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x17u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, a3);
  v33 = Instance;
  if ( Instance < 0 )
  {
    ppvb = "hr = pDOMXml.CoCreateInstance(CLSID_DOMDocument60)";
    v7 = Instance;
    v8 = 485;
LABEL_17:
    Telemetry::IfFailExit("onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\util.cpp", "CreateDOM", v8, v7, ppvb);
    goto LABEL_18;
  }
  v9 = *a3;
  v10 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int128 *))(*(_QWORD *)*a3 + 640LL);
  v11 = *a2;
  v12 = *((_QWORD *)a2 + 2);
  v13 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"SelectionNamespaces");
  v29 = v11;
  v30 = v12;
  v14 = v10(v9, *v13, &v29);
  v33 = v14;
  SysFreeString(bstrString[0]);
  if ( v14 < 0 )
  {
    v15 = "hr = pDOMXml->setProperty(CComBSTR(XML_PROP_SELECTION_NAMESPACES), cvNamespaces)";
    v16 = 487;
LABEL_7:
    Telemetry::IfFailExit("onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\util.cpp", "CreateDOM", v16, v14, v15);
    goto LABEL_18;
  }
  v17 = *a3;
  v18 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int16 *))(*(_QWORD *)*a3 + 520LL);
  v19 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, a1);
  v14 = v18(v17, *v19, &v32);
  v33 = v14;
  SysFreeString(bstrString[0]);
  if ( v14 < 0 )
  {
    v15 = "hr = pDOMXml->loadXML(CComBSTR(wszXml), &bParsedOK)";
    v16 = 489;
    goto LABEL_7;
  }
  if ( v32 != -1 )
  {
    v27 = 0;
    bstrString[0] = 0;
    v26 = -1;
    (*(void (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)*a3 + 480LL))(*a3, &v27);
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v27 + 72LL))(v27, bstrString);
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 88LL))(v27, &v26);
      LODWORD(ppva) = v26;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\util.cpp",
        0x1F6u,
        L"XML load for text failed at %d: %ls.",
        ppva,
        bstrString[0]);
    }
    v33 = -2147188477;
    v20 = *a3;
    if ( *a3 )
    {
      *a3 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    }
    SysFreeString(bstrString[0]);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  }
LABEL_18:
  v21 = v33;
  CTraceFuncW<long>::~CTraceFuncW<long>(v31);
  return v21;
}

```

## disassembly

```asm
0x1800547c4  mov     rax, rsp
0x1800547c7  mov     [rax+10h], rbx
0x1800547cb  push    rbp
0x1800547cc  push    rsi
0x1800547cd  push    rdi
0x1800547ce  push    r12
0x1800547d0  push    r13
0x1800547d2  push    r14
0x1800547d4  push    r15
0x1800547d6  lea     rbp, [rax-5Fh]
0x1800547da  sub     rsp, 0B0h
0x1800547e1  movaps  xmmword ptr [rax-48h], xmm6
0x1800547e5  movaps  xmmword ptr [rax-58h], xmm7
0x1800547e9  mov     rsi, r8
0x1800547ec  mov     r15, rdx
0x1800547ef  mov     r14, rcx
0x1800547f2  xor     r12d, r12d
0x1800547f5  mov     [rbp+57h+arg_18], r12d
0x1800547f9  mov     [rbp+57h+arg_0], r12w
0x1800547fe  lea     r13, aCreatedom; "CreateDOM"
0x180054805  mov     [rbp+57h+var_70], r13
0x180054809  lea     rax, [rbp+57h+arg_18]
0x18005480d  mov     [rbp+57h+var_68], rax
0x180054811  mov     [rbp+57h+var_60], r12
0x180054815  mov     [rbp+57h+var_58], r12
0x180054819  xor     r9d, r9d; unsigned int
0x18005481c  mov     r8d, 1E1h; char *
0x180054822  mov     rdx, r13; char *
0x180054825  lea     rbx, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18005482c  mov     rcx, rbx; this
0x18005482f  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180054834  nop
0x180054835  test    r14, r14
0x180054838  jz      loc_180054A0C
0x18005483e  cmp     [r14], r12w
0x180054842  jz      loc_180054A0C
0x180054848  mov     [rsp+0E0h+ppv], rsi; ppv
0x18005484d  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180054854  xor     edx, edx; pUnkOuter
0x180054856  lea     r8d, [r12+17h]; dwClsContext
0x18005485b  lea     rcx, CLSID_DOMDocument60; rclsid
0x180054862  call    cs:__imp_CoCreateInstance
0x180054868  mov     [rbp+57h+arg_18], eax
0x18005486b  test    eax, eax
0x18005486d  jns     short loc_180054889
0x18005486f  lea     r8, aHrPdomxmlCocre; "hr = pDOMXml.CoCreateInstance(CLSID_DOM"...
0x180054876  mov     [rsp+0E0h+ppv], r8
0x18005487b  mov     r9d, eax
0x18005487e  mov     r8d, 1E5h
0x180054884  jmp     loc_180054A28
0x180054889  mov     rdi, [rsi]
0x18005488c  mov     rax, [rdi]
0x18005488f  mov     rbx, [rax+280h]
0x180054896  movups  xmm6, xmmword ptr [r15]
0x18005489a  movsd   xmm7, qword ptr [r15+10h]
0x1800548a0  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x1800548a7  lea     rcx, [rbp+57h+bstrString]; this
0x1800548ab  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800548b0  nop
0x1800548b1  movaps  [rbp+57h+var_90], xmm6
0x1800548b5  movsd   [rbp+57h+var_80], xmm7
0x1800548ba  lea     r8, [rbp+57h+var_90]
0x1800548be  mov     rdx, [rax]
0x1800548c1  mov     rcx, rdi
0x1800548c4  mov     rax, rbx
0x1800548c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548cc  mov     ebx, eax
0x1800548ce  mov     [rbp+57h+arg_18], eax
0x1800548d1  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800548d5  call    cs:__imp_SysFreeString
0x1800548db  test    ebx, ebx
0x1800548dd  jns     short loc_180054900
0x1800548df  lea     rax, aHrPdomxmlSetpr; "hr = pDOMXml->setProperty(CComBSTR(XML_"...
0x1800548e6  mov     r8d, 1E7h
0x1800548ec  mov     r9d, ebx
0x1800548ef  mov     [rsp+0E0h+ppv], rax
0x1800548f4  lea     rcx, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800548fb  jmp     loc_180054A2B
0x180054900  mov     rdi, [rsi]
0x180054903  mov     rax, [rdi]
0x180054906  mov     rbx, [rax+208h]
0x18005490d  mov     rdx, r14; unsigned __int16 *
0x180054910  lea     rcx, [rbp+57h+bstrString]; this
0x180054914  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180054919  nop
0x18005491a  lea     r8, [rbp+57h+arg_0]
0x18005491e  mov     rdx, [rax]
0x180054921  mov     rcx, rdi
0x180054924  mov     rax, rbx
0x180054927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005492c  mov     ebx, eax
0x18005492e  mov     [rbp+57h+arg_18], eax
0x180054931  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180054935  call    cs:__imp_SysFreeString
0x18005493b  test    ebx, ebx
0x18005493d  jns     short loc_18005494E
0x18005493f  lea     rax, aHrPdomxmlLoadx; "hr = pDOMXml->loadXML(CComBSTR(wszXml),"...
0x180054946  mov     r8d, 1E9h
0x18005494c  jmp     short loc_1800548EC
0x18005494e  or      eax, 0FFFFFFFFh
0x180054951  cmp     [rbp+57h+arg_0], ax
0x180054955  jz      loc_180054A33
0x18005495b  mov     [rbp+57h+var_A8], r12
0x18005495f  mov     [rbp+57h+bstrString], r12
0x180054963  mov     [rbp+57h+var_B0], eax
0x180054966  mov     rcx, [rsi]
0x180054969  mov     rax, [rcx]
0x18005496c  lea     rdx, [rbp+57h+var_A8]
0x180054970  mov     rax, [rax+1E0h]
0x180054977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005497c  mov     rcx, [rbp+57h+var_A8]
0x180054980  test    rcx, rcx
0x180054983  jz      short loc_1800549D7
0x180054985  mov     rax, [rcx]
0x180054988  lea     rdx, [rbp+57h+bstrString]
0x18005498c  mov     rax, [rax+48h]
0x180054990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054995  mov     rcx, [rbp+57h+var_A8]
0x180054999  mov     rax, [rcx]
0x18005499c  lea     rdx, [rbp+57h+var_B0]
0x1800549a0  mov     rax, [rax+58h]
0x1800549a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549a9  mov     rax, [rbp+57h+bstrString]
0x1800549ad  mov     [rsp+0E0h+var_B8], rax
0x1800549b2  mov     eax, [rbp+57h+var_B0]
0x1800549b5  mov     dword ptr [rsp+0E0h+ppv], eax
0x1800549b9  lea     r9, aXmlLoadForText; "XML load for text failed at %d: %ls."
0x1800549c0  mov     r8d, 1F6h; unsigned int
0x1800549c6  lea     rdx, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800549cd  mov     ecx, 2; unsigned __int8
0x1800549d2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800549d7  mov     [rbp+57h+arg_18], 80048103h
0x1800549de  mov     rcx, [rsi]
0x1800549e1  test    rcx, rcx
0x1800549e4  jz      short loc_1800549F6
0x1800549e6  mov     [rsi], r12
0x1800549e9  mov     rax, [rcx]
0x1800549ec  mov     rax, [rax+10h]
0x1800549f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549f5  nop
0x1800549f6  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800549fa  call    cs:__imp_SysFreeString
0x180054a00  nop
0x180054a01  lea     rcx, [rbp+57h+var_A8]
0x180054a05  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180054a0a  jmp     short loc_180054A33
0x180054a0c  mov     r9d, 8004805Eh; int
0x180054a12  mov     [rbp+57h+arg_18], r9d
0x180054a16  lea     rax, aWszxmlNullptrW; "wszXml != nullptr && *wszXml != L'\\0'"
0x180054a1d  mov     [rsp+0E0h+ppv], rax; char *
0x180054a22  mov     r8d, 1E3h; unsigned int
0x180054a28  mov     rcx, rbx; char *
0x180054a2b  mov     rdx, r13; char *
0x180054a2e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180054a33  mov     ebx, [rbp+57h+arg_18]
0x180054a36  lea     rcx, [rbp+57h+var_70]
0x180054a3a  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180054a3f  mov     eax, ebx
0x180054a41  lea     r11, [rsp+0E0h+var_30]
0x180054a49  mov     rbx, [r11+48h]
0x180054a4d  movaps  xmm6, xmmword ptr [r11-10h]
0x180054a52  movaps  xmm7, xmmword ptr [r11-20h]
0x180054a57  mov     rsp, r11
0x180054a5a  pop     r15
0x180054a5c  pop     r14
0x180054a5e  pop     r13
0x180054a60  pop     r12
0x180054a62  pop     rdi
0x180054a63  pop     rsi
0x180054a64  pop     rbp
0x180054a65  retn
```
