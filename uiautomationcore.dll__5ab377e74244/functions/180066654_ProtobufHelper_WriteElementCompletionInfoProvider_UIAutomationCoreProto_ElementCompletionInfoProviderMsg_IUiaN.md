# ProtobufHelper::WriteElementCompletionInfoProvider(UIAutomationCoreProto::ElementCompletionInfoProviderMsg &,IUiaNode *,IServerConnection *)

- ea: `0x180066654`
- end: `0x180066d0f`
- name: `?WriteElementCompletionInfoProvider@ProtobufHelper@@SAXAEAVElementCompletionInfoProviderMsg@UIAutomationCoreProto@@PEAVIUiaNode@@PEAVIServerConnection@@@Z`
- size: `1723`
- prototype: `void __fastcall(struct UIAutomationCoreProto::ElementCompletionInfoProviderMsg *, struct IUiaNode *, struct IServerConnection *)`
- caller_count: `2`
- callee_count: `34`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800665c0`
- `0x18013b170`

## callees

- `0x1800206e8`
- `0x18002f580`
- `0x180030cd4`
- `0x180030ee4`
- `0x180032724`
- `0x18003c820`
- `0x18004c8c0`
- `0x18004dd30`
- `0x18004e194`
- `0x18004e244`
- `0x18004e318`
- `0x18004e410`
- `0x18004e5f8`
- `0x18004e668`
- `0x18004e6c8`
- `0x180066654`
- `0x180068f08`
- `0x1800690c4`
- `0x1800be9c8`
- `0x180181488`
- `0x180189804`
- `0x1801a9630`
- `0x1801ad0e0`
- `0x1801b7238`
- `0x1801b799c`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e88a0`
- `0x1801e9234`
- `0x1801eae30`
- `0x1801eafa0`
- `0x1801fc5d8`
- `0x1801fc640`
- `0x1802dd010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800668fa`
- `OLEAUT32!__imp_SysFreeString` at `0x180066b16`
- `OLEAUT32!__imp_SysFreeString` at `0x1800668fa`
- `OLEAUT32!__imp_SysFreeString` at `0x180066b16`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180066763`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180066aed`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180066afd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180066763`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180066aed`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180066afd`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180066977`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180066977`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800669e6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800669e6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800669c9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800669c9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180066a0f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180066a0f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180066a8c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180066bbc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180066a8c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180066bbc`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180066996`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x180066996`

## string_xrefs

- `0x180066b9b`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x180066bd6`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x180066c86`: `onecore\windows\accessibletech\uiautomationcore\ElementPatternRef.h`
- `0x180066aa3`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall ProtobufHelper::WriteElementCompletionInfoProvider(
        struct UIAutomationCoreProto::ElementCompletionInfoProviderMsg *a1,
        struct IUiaNode *a2,
        struct IServerConnection *a3)
{
  UiaNode *v6; // rsi
  __int64 v7; // r14
  _QWORD *v8; // rcx
  UIAutomationCoreProto::ElementExtraInfoMsg *v9; // rsi
  _QWORD *v10; // rcx
  struct UIAutomationCoreProto::ProviderEntryPointMsg *v11; // rax
  _QWORD *v12; // rcx
  unsigned int v13; // edx
  _BYTE *v14; // rcx
  _QWORD *v15; // rcx
  unsigned int v16; // edx
  SAFEARRAY *v17; // rsi
  __int64 v18; // r15
  struct google::protobuf::Arena *v19; // rcx
  _DWORD *v20; // rbx
  signed int i; // r14d
  HRESULT Vartype; // eax
  int v23; // edi
  unsigned __int64 v24; // rax
  _DWORD *v25; // r9
  __int64 v26; // r8
  signed int j; // edi
  UIAutomationCoreProto::UiaPropertyConditionMsg *v28; // rdi
  struct UIAutomationCoreProto::GuidMsg *v29; // rax
  const unsigned __int16 *v30; // rbx
  struct UIAutomationCoreProto::WstringMsg *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // r9
  unsigned int v35; // eax
  struct UIAutomationCoreProto::CrossMachinePlaceHolderMsg *v36; // rax
  int v37; // [rsp+20h] [rbp-E0h]
  VARTYPE pvt; // [rsp+30h] [rbp-D0h] BYREF
  SAFEARRAY *psa; // [rsp+38h] [rbp-C8h] BYREF
  LONG plUbound; // [rsp+40h] [rbp-C0h] BYREF
  SAFEARRAY *v41; // [rsp+48h] [rbp-B8h]
  unsigned int v42; // [rsp+50h] [rbp-B0h]
  void *ppvData; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD *v44; // [rsp+60h] [rbp-A0h] BYREF
  void *Block; // [rsp+68h] [rbp-98h]
  SAFEARRAY *v46; // [rsp+70h] [rbp-90h] BYREF
  ProviderEntryPoint *v47; // [rsp+80h] [rbp-80h] BYREF
  char v48; // [rsp+88h] [rbp-78h]
  GUID Buf1; // [rsp+8Ch] [rbp-74h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v51[40]; // [rsp+A8h] [rbp-58h] BYREF
  char v52; // [rsp+D0h] [rbp-30h]
  int v53; // [rsp+E0h] [rbp-20h] BYREF
  ProviderEntryPoint *v54; // [rsp+E8h] [rbp-18h] BYREF
  char v55; // [rsp+F0h] [rbp-10h]
  GUID v56; // [rsp+F4h] [rbp-Ch]
  BSTR v57; // [rsp+108h] [rbp+8h]
  _BYTE v58[40]; // [rsp+110h] [rbp+10h] BYREF
  char v59; // [rsp+138h] [rbp+38h]
  SAFEARRAY *v60; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v54 = 0;
  v55 &= 0xC0u;
  v56 = GUID_NULL;
  v57 = 0;
  v59 = 0;
  v60 = 0;
  if ( a2 )
  {
    v6 = (UiaNode *)(*(__int64 (__fastcall **)(struct IUiaNode *))(*(_QWORD *)a2 + 32LL))(a2);
    if ( v6 )
    {
      GetRuntimeIdSafeArray(&psa, a2);
      LODWORD(v44) = 0;
      Block = 0;
      SafeArrayToRuntimeId(psa, &v44);
      v37 = 0;
      v53 = (*(__int64 (__fastcall **)(struct IServerConnection *, struct IUiaNode *, int *, _DWORD **))(*(_QWORD *)a3 + 40LL))(
              a3,
              a2,
              &NodeMarker,
              &v44);
      UiaNode::GetElementExtraInfo(v6, (struct ElementExtraInfo *)&v54);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>>::operator=(
        &v60,
        &psa);
      if ( Block )
        operator delete(Block);
      LODWORD(v44) = 0;
      Block = 0;
      if ( psa )
        SafeArrayDestroy(psa);
    }
    else
    {
      v53 = 0;
      v35 = Error::InternalErrorWorker(L"Expecting object to be local");
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\ElementPatternRef.h",
        (const char *)v35,
        v37);
    }
  }
  else
  {
    v53 = 0;
  }
  v7 = *((_QWORD *)a1 + 2);
  if ( !v7 )
  {
    v8 = (_QWORD *)(*((_QWORD *)a1 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
    if ( (*((_BYTE *)a1 + 8) & 1) != 0 )
      v8 = (_QWORD *)*v8;
    v7 = google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementBaseMsg,>(v8);
    *((_QWORD *)a1 + 2) = v7;
  }
  *(_DWORD *)(v7 + 32) = v53;
  if ( v53 )
  {
    v47 = v54;
    if ( v54 )
      (*(void (__fastcall **)(ProviderEntryPoint *))(*(_QWORD *)v54 + 8LL))(v54);
    v48 = v55;
    Buf1 = v56;
    bstrString = 0;
    v52 = 0;
    if ( v59 )
      std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
        v51,
        v58);
    if ( v57 && (int)HrSysAllocString(v57, &bstrString) < 0 )
      Buf1 = GUID_NULL;
    v9 = *(UIAutomationCoreProto::ElementExtraInfoMsg **)(v7 + 16);
    if ( !v9 )
    {
      v10 = (_QWORD *)(*(_QWORD *)(v7 + 8) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*(_BYTE *)(v7 + 8) & 1) != 0 )
        v10 = (_QWORD *)*v10;
      v9 = (UIAutomationCoreProto::ElementExtraInfoMsg *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoMsg,>(v10);
      *(_QWORD *)(v7 + 16) = v9;
    }
    if ( v47 )
    {
      v11 = (struct UIAutomationCoreProto::ProviderEntryPointMsg *)*((_QWORD *)v9 + 2);
      if ( !v11 )
      {
        v12 = (_QWORD *)(*((_QWORD *)v9 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
        if ( (*((_BYTE *)v9 + 8) & 1) != 0 )
          v12 = (_QWORD *)*v12;
        v11 = (struct UIAutomationCoreProto::ProviderEntryPointMsg *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ProviderEntryPointMsg,>(v12);
        *((_QWORD *)v9 + 2) = v11;
      }
      ProviderEntryPoint::WriteToMessage(v47, v11);
    }
    if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      v28 = UIAutomationCoreProto::ElementExtraInfoMsg::_internal_mutable_component_site(v9);
      v29 = UIAutomationCoreProto::UiaPropertyConditionMsg::_internal_mutable_property_id(v28);
      ProtobufHelper::WriteGuid(v29, &Buf1);
      v30 = bstrString;
      v31 = UIAutomationCoreProto::StructuredMarkupRangeGetMarkupWithMarkedRangeRequestMsg::_internal_mutable_language(v28);
      ProtobufHelper::WriteString(v31, v30, 1);
    }
    if ( v52 )
    {
      v36 = UIAutomationCoreProto::ElementExtraInfoMsg::_internal_mutable_cross_machine_placeholder(v9);
      CrossMachinePlaceholderInfo::WriteToMessage((CrossMachinePlaceholderInfo *)v51, v36);
    }
    v14 = (_BYTE *)*((_QWORD *)v9 + 6);
    if ( !v14 )
    {
      v15 = (_QWORD *)(*((_QWORD *)v9 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*((_BYTE *)v9 + 8) & 1) != 0 )
        v15 = (_QWORD *)*v15;
      v14 = (_BYTE *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoFlagsMsg,>(v15);
      *((_QWORD *)v9 + 6) = v14;
    }
    v14[16] = v48 & 1;
    v14[17] = (v48 & 2) != 0;
    v14[18] = (v48 & 4) != 0;
    v14[19] = (v48 & 8) != 0;
    v14[20] = (v48 & 0x10) != 0;
    v14[21] = (v48 & 0x20) != 0;
    if ( v52 )
      CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v51, v13);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
  }
  ElementRefRet::TryGetRuntimeIdCopy(&v53, &v46);
  v17 = v46;
  if ( v46 )
  {
    v18 = *(_QWORD *)(v7 + 24);
    if ( !v18 )
    {
      v19 = (struct google::protobuf::Arena *)(*(_QWORD *)(v7 + 8) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*(_BYTE *)(v7 + 8) & 1) != 0 )
        v19 = *(struct google::protobuf::Arena **)v19;
      v18 = google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::IntArrayMsg,>(v19);
      *(_QWORD *)(v7 + 24) = v18;
    }
    if ( !v17 )
    {
      google::protobuf::RepeatedField<bool>::Clear(v18 + 16);
      goto LABEL_65;
    }
    v20 = 0;
    v44 = 0;
    v42 = 0;
    ppvData = 0;
    i = 0;
    v41 = v17;
    if ( SafeArrayGetDim(v17) == 1 )
    {
      pvt = 0;
      Vartype = SafeArrayGetVartype(v41, &pvt);
      v23 = Vartype;
      if ( Vartype < 0 )
      {
        v33 = 95;
      }
      else
      {
        if ( pvt != 3 && pvt != 22 )
        {
          v34 = 2147942487LL;
          v23 = -2147024809;
          v33 = 106;
          goto LABEL_79;
        }
        LODWORD(psa) = 0;
        plUbound = 0;
        Vartype = SafeArrayGetLBound(v41, 1u, (LONG *)&psa);
        v23 = Vartype;
        if ( Vartype < 0 )
        {
          v33 = 111;
        }
        else
        {
          Vartype = SafeArrayGetUBound(v41, 1u, &plUbound);
          v23 = Vartype;
          if ( Vartype < 0 )
          {
            v33 = 112;
          }
          else
          {
            v42 = plUbound - (_DWORD)psa + 1;
            Vartype = SafeArrayAccessData(v41, &ppvData);
            v23 = Vartype;
            if ( Vartype >= 0 )
            {
              v24 = 4LL * v42;
              if ( !is_mul_ok(v42, 4u) )
                v24 = -1;
              v25 = operator new[](v24, (const struct std::nothrow_t *)std::nothrow);
              if ( v25 )
              {
                v26 = 0;
                for ( i = v42; (unsigned int)v26 < v42; i = v42 )
                {
                  v25[(unsigned int)v26] = *((_DWORD *)ppvData + (unsigned int)v26);
                  v26 = (unsigned int)(v26 + 1);
                }
                v20 = v25;
                v44 = v25;
                if ( v41 )
                  SafeArrayUnaccessData(v41);
                v23 = 0;
                goto LABEL_60;
              }
              v23 = -2147024882;
              v32 = 162;
LABEL_75:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v32,
                (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                (const char *)(unsigned int)v23,
                v37);
              if ( v41 )
                SafeArrayUnaccessData(v41);
LABEL_60:
              if ( v23 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x290,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
                  (const char *)(unsigned int)v23,
                  v37);
              for ( j = 0; j < i; ++j )
              {
                LODWORD(psa) = v20[j];
                google::protobuf::RepeatedField<unsigned int>::Add(v18 + 16, &psa, v26);
              }
              operator delete(v20);
              goto LABEL_65;
            }
            v33 = 115;
          }
        }
      }
      v34 = (unsigned int)Vartype;
    }
    else
    {
      v34 = 2147942487LL;
      v23 = -2147024809;
      v33 = 92;
    }
LABEL_79:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v34,
      v37);
    v32 = 159;
    goto LABEL_75;
  }
LABEL_65:
  if ( v17 )
    SafeArrayDestroy(v17);
  if ( v60 )
    SafeArrayDestroy(v60);
  if ( v59 )
    CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v58, v16);
  if ( v57 )
  {
    SysFreeString(v57);
    v57 = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
}

```

## disassembly

```asm
0x180066654  mov     [rsp-8+arg_18], rbx
0x180066659  push    rbp
0x18006665a  push    rsi
0x18006665b  push    rdi
0x18006665c  push    r12
0x18006665e  push    r13
0x180066660  push    r14
0x180066662  push    r15
0x180066664  lea     rbp, [rsp-60h]
0x180066669  sub     rsp, 160h
0x180066670  mov     rax, cs:__security_cookie
0x180066677  xor     rax, rsp
0x18006667a  mov     [rbp+90h+var_40], rax
0x18006667e  mov     r14, r8
0x180066681  mov     rdi, rdx
0x180066684  mov     rbx, rcx
0x180066687  xor     r12d, r12d
0x18006668a  mov     [rbp+90h+var_A8], r12
0x18006668e  and     [rbp+90h+var_A0], 0C0h
0x180066692  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180066699  mov     [rbp+90h+var_9C], rax
0x18006669d  mov     rax, qword ptr cs:GUID_NULL.Data4
0x1800666a4  mov     [rbp+90h+var_94], rax
0x1800666a8  mov     [rbp+90h+var_88], r12
0x1800666ac  mov     [rbp+90h+var_58], r12b
0x1800666b0  mov     [rbp+90h+var_50], r12
0x1800666b4  test    rdx, rdx
0x1800666b7  jz      loc_180066C63
0x1800666bd  mov     rax, [rdx]
0x1800666c0  mov     rcx, rdx
0x1800666c3  mov     rax, [rax+20h]
0x1800666c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666cc  mov     rsi, rax
0x1800666cf  test    rax, rax
0x1800666d2  jz      loc_180066C6C
0x1800666d8  mov     rdx, rdi
0x1800666db  lea     rcx, [rsp+190h+psa]
0x1800666e0  call    ?GetRuntimeIdSafeArray@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAVIUiaNode@@@Z; GetRuntimeIdSafeArray(IUiaNode *)
0x1800666e5  nop
0x1800666e6  mov     dword ptr [rsp+190h+var_130], r12d
0x1800666eb  mov     [rsp+190h+Block], r12
0x1800666f0  lea     rdx, [rsp+190h+var_130]
0x1800666f5  mov     rcx, [rsp+190h+psa]
0x1800666fa  call    ?SafeArrayToRuntimeId@@YAXPEAUtagSAFEARRAY@@PEAU?$BasicArrayPair@H@@@Z; SafeArrayToRuntimeId(tagSAFEARRAY *,BasicArrayPair<int> *)
0x1800666ff  mov     rax, [r14]
0x180066702  mov     qword ptr [rsp+190h+var_170], r12; int
0x180066707  lea     r9, [rsp+190h+var_130]
0x18006670c  lea     r8, ?NodeMarker@@3HA; int NodeMarker
0x180066713  mov     rdx, rdi
0x180066716  mov     rcx, r14
0x180066719  mov     rax, [rax+28h]
0x18006671d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066722  mov     [rbp+90h+var_B0], eax
0x180066725  lea     rdx, [rbp+90h+var_A8]; struct ElementExtraInfo *
0x180066729  mov     rcx, rsi; this
0x18006672c  call    ?GetElementExtraInfo@UiaNode@@QEAAXPEAUElementExtraInfo@@@Z; UiaNode::GetElementExtraInfo(ElementExtraInfo *)
0x180066731  lea     rdx, [rsp+190h+psa]
0x180066736  lea     rcx, [rbp+90h+var_50]
0x18006673a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>> &&)
0x18006673f  nop
0x180066740  mov     rcx, [rsp+190h+Block]; Block
0x180066745  test    rcx, rcx
0x180066748  jz      short loc_18006674F
0x18006674a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006674f  mov     dword ptr [rsp+190h+var_130], r12d
0x180066754  mov     [rsp+190h+Block], r12
0x180066759  mov     rcx, [rsp+190h+psa]; psa
0x18006675e  test    rcx, rcx
0x180066761  jz      short loc_18006676A
0x180066763  call    cs:__imp_SafeArrayDestroy
0x180066769  nop
0x18006676a  mov     r14, [rbx+10h]
0x18006676e  mov     r13d, 1
0x180066774  test    r14, r14
0x180066777  jnz     short loc_180066797
0x180066779  mov     rcx, [rbx+8]
0x18006677d  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180066781  test    [rbx+8], r13b
0x180066785  jnz     loc_180066C00
0x18006678b  call    ??$CreateMaybeMessage@VElementBaseMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVElementBaseMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementBaseMsg,>(google::protobuf::Arena *)
0x180066790  mov     r14, rax
0x180066793  mov     [rbx+10h], rax
0x180066797  mov     eax, [rbp+90h+var_B0]
0x18006679a  mov     [r14+20h], eax
0x18006679e  cmp     [rbp+90h+var_B0], r12d
0x1800667a2  jz      loc_18006690D
0x1800667a8  mov     rcx, [rbp+90h+var_A8]
0x1800667ac  mov     [rbp+90h+var_110], rcx
0x1800667b0  test    rcx, rcx
0x1800667b3  jz      short loc_1800667C2
0x1800667b5  mov     rax, [rcx]
0x1800667b8  mov     rax, [rax+8]
0x1800667bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667c1  nop
0x1800667c2  mov     al, [rbp+90h+var_A0]
0x1800667c5  mov     [rbp+90h+var_108], al
0x1800667c8  mov     rax, [rbp+90h+var_9C]
0x1800667cc  mov     [rbp+90h+Buf1], rax
0x1800667d0  mov     rax, [rbp+90h+var_94]
0x1800667d4  mov     [rbp+90h+var_FC], rax
0x1800667d8  mov     [rbp+90h+bstrString], r12
0x1800667dc  mov     [rbp+90h+var_C0], r12b
0x1800667e0  cmp     [rbp+90h+var_58], r12b
0x1800667e4  jnz     loc_180066C9C
0x1800667ea  mov     rcx, [rbp+90h+var_88]; unsigned __int16 *
0x1800667ee  test    rcx, rcx
0x1800667f1  jnz     loc_180066CAE
0x1800667f7  mov     rsi, [r14+10h]
0x1800667fb  test    rsi, rsi
0x1800667fe  jnz     short loc_18006681E
0x180066800  mov     rcx, [r14+8]
0x180066804  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180066808  test    [r14+8], r13b
0x18006680c  jnz     loc_180066C0F
0x180066812  call    ??$CreateMaybeMessage@VElementExtraInfoMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVElementExtraInfoMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoMsg,>(google::protobuf::Arena *)
0x180066817  mov     rsi, rax
0x18006681a  mov     [r14+10h], rax
0x18006681e  cmp     [rbp+90h+var_110], r12
0x180066822  jz      short loc_180066854
0x180066824  mov     rax, [rsi+10h]
0x180066828  test    rax, rax
0x18006682b  jnz     short loc_180066848
0x18006682d  mov     rcx, [rsi+8]
0x180066831  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180066835  test    [rsi+8], r13b
0x180066839  jnz     loc_180066C27
0x18006683f  call    ??$CreateMaybeMessage@VProviderEntryPointMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVProviderEntryPointMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ProviderEntryPointMsg,>(google::protobuf::Arena *)
0x180066844  mov     [rsi+10h], rax
0x180066848  mov     rdx, rax; struct UIAutomationCoreProto::ProviderEntryPointMsg *
0x18006684b  mov     rcx, [rbp+90h+var_110]; this
0x18006684f  call    ?WriteToMessage@ProviderEntryPoint@@QEBAJPEAVProviderEntryPointMsg@UIAutomationCoreProto@@@Z; ProviderEntryPoint::WriteToMessage(UIAutomationCoreProto::ProviderEntryPointMsg *)
0x180066854  mov     r8d, 10h; Size
0x18006685a  lea     rdx, GUID_NULL; Buf2
0x180066861  lea     rcx, [rbp+90h+Buf1]; Buf1
0x180066865  call    memcmp_0
0x18006686a  test    eax, eax
0x18006686c  jnz     loc_180066B50
0x180066872  cmp     [rbp+90h+var_C0], r12b
0x180066876  jnz     loc_180066CDA
0x18006687c  mov     rcx, [rsi+30h]
0x180066880  test    rcx, rcx
0x180066883  jnz     short loc_1800668A3
0x180066885  mov     rcx, [rsi+8]
0x180066889  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18006688d  test    [rsi+8], r13b
0x180066891  jnz     loc_180066C1F
0x180066897  call    ??$CreateMaybeMessage@VElementExtraInfoFlagsMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVElementExtraInfoFlagsMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoFlagsMsg,>(google::protobuf::Arena *)
0x18006689c  mov     rcx, rax
0x18006689f  mov     [rsi+30h], rax
0x1800668a3  mov     al, [rbp+90h+var_108]
0x1800668a6  and     al, r13b
0x1800668a9  mov     [rcx+10h], al
0x1800668ac  mov     al, [rbp+90h+var_108]
0x1800668af  shr     al, 1
0x1800668b1  and     al, r13b
0x1800668b4  mov     [rcx+11h], al
0x1800668b7  mov     al, [rbp+90h+var_108]
0x1800668ba  shr     al, 2
0x1800668bd  and     al, r13b
0x1800668c0  mov     [rcx+12h], al
0x1800668c3  mov     al, [rbp+90h+var_108]
0x1800668c6  shr     al, 3
0x1800668c9  and     al, r13b
0x1800668cc  mov     [rcx+13h], al
0x1800668cf  mov     al, [rbp+90h+var_108]
0x1800668d2  shr     al, 4
0x1800668d5  and     al, r13b
0x1800668d8  mov     [rcx+14h], al
0x1800668db  mov     al, [rbp+90h+var_108]
0x1800668de  shr     al, 5
0x1800668e1  and     al, r13b
0x1800668e4  mov     [rcx+15h], al
0x1800668e7  cmp     [rbp+90h+var_C0], r12b
0x1800668eb  jnz     loc_180066CF3
0x1800668f1  mov     rcx, [rbp+90h+bstrString]; bstrString
0x1800668f5  test    rcx, rcx
0x1800668f8  jz      short loc_180066904
0x1800668fa  call    cs:__imp_SysFreeString
0x180066900  mov     [rbp+90h+bstrString], r12
0x180066904  lea     rcx, [rbp+90h+var_110]
0x180066908  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006690d  lea     rdx, [rsp+190h+var_120]
0x180066912  lea     rcx, [rbp+90h+var_B0]
0x180066916  call    ?TryGetRuntimeIdCopy@ElementRefRet@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; ElementRefRet::TryGetRuntimeIdCopy(void)
0x18006691b  nop
0x18006691c  mov     rsi, [rsp+190h+var_120]
0x180066921  test    rsi, rsi
0x180066924  jz      loc_180066AE5
0x18006692a  mov     r15, [r14+18h]
0x18006692e  test    r15, r15
0x180066931  jnz     short loc_180066951
0x180066933  mov     rcx, [r14+8]
0x180066937  and     rcx, 0FFFFFFFFFFFFFFFCh; struct google::protobuf::Arena *
0x18006693b  test    [r14+8], r13b
0x18006693f  jnz     loc_180066C17
0x180066945  call    ??$CreateMaybeMessage@VIntArrayMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVIntArrayMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::IntArrayMsg,>(google::protobuf::Arena *)
0x18006694a  mov     r15, rax
0x18006694d  mov     [r14+18h], rax
0x180066951  test    rsi, rsi
0x180066954  jz      loc_180066C2F
0x18006695a  mov     rbx, r12
0x18006695d  mov     [rsp+190h+var_130], rbx
0x180066962  mov     [rsp+190h+var_140], r12d
0x180066967  mov     [rsp+190h+ppvData], r12
0x18006696c  mov     r14d, r12d
0x18006696f  mov     [rsp+190h+var_148], rsi
0x180066974  mov     rcx, rsi; psa
0x180066977  call    cs:__imp_SafeArrayGetDim
0x18006697d  cmp     eax, r13d
0x180066980  jnz     loc_180066BF0
0x180066986  mov     [rsp+190h+pvt], r12w
0x18006698c  lea     rdx, [rsp+190h+pvt]; pvt
0x180066991  mov     rcx, [rsp+190h+var_148]; psa
0x180066996  call    cs:__imp_SafeArrayGetVartype
0x18006699c  mov     edi, eax
0x18006699e  test    eax, eax
0x1800669a0  js      loc_180066C08
0x1800669a6  cmp     [rsp+190h+pvt], 3
0x1800669ac  jnz     loc_180066C44
0x1800669b2  mov     dword ptr [rsp+190h+psa], r12d
0x1800669b7  mov     [rsp+190h+plUbound], r12d
0x1800669bc  lea     r8, [rsp+190h+psa]; plLbound
0x1800669c1  mov     edx, r13d; nDim
0x1800669c4  mov     rcx, [rsp+190h+var_148]; psa
0x1800669c9  call    cs:__imp_SafeArrayGetLBound
0x1800669cf  mov     edi, eax
0x1800669d1  test    eax, eax
0x1800669d3  js      loc_180066BC7
0x1800669d9  lea     r8, [rsp+190h+plUbound]; plUbound
0x1800669de  mov     edx, r13d; nDim
0x1800669e1  mov     rcx, [rsp+190h+var_148]; psa
0x1800669e6  call    cs:__imp_SafeArrayGetUBound
0x1800669ec  mov     edi, eax
0x1800669ee  test    eax, eax
0x1800669f0  js      loc_180066BE9
0x1800669f6  mov     eax, [rsp+190h+plUbound]
0x1800669fa  sub     eax, dword ptr [rsp+190h+psa]
0x1800669fe  add     eax, r13d
0x180066a01  mov     [rsp+190h+var_140], eax
0x180066a05  lea     rdx, [rsp+190h+ppvData]; ppvData
0x180066a0a  mov     rcx, [rsp+190h+var_148]; psa
0x180066a0f  call    cs:__imp_SafeArrayAccessData
0x180066a15  mov     edi, eax
0x180066a17  test    eax, eax
0x180066a19  js      loc_180066C3D
0x180066a1f  mov     ecx, [rsp+190h+var_140]
0x180066a23  mov     eax, 4
0x180066a28  mul     rcx
0x180066a2b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180066a32  cmovb   rax, rcx
0x180066a36  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180066a3d  mov     rcx, rax; unsigned __int64
0x180066a40  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180066a45  mov     r9, rax
0x180066a48  test    rax, rax
0x180066a4b  jz      loc_180066B8E
0x180066a51  mov     r8d, r12d
0x180066a54  mov     r14d, [rsp+190h+var_140]
0x180066a59  test    r14d, r14d
0x180066a5c  jz      short loc_180066A7A
0x180066a5e  mov     edx, r8d
0x180066a61  mov     rcx, [rsp+190h+ppvData]
0x180066a66  mov     eax, [rcx+rdx*4]
0x180066a69  mov     [r9+rdx*4], eax
0x180066a6d  add     r8d, r13d
0x180066a70  mov     r14d, [rsp+190h+var_140]
0x180066a75  cmp     r8d, r14d
0x180066a78  jb      short loc_180066A5E
0x180066a7a  mov     rbx, r9
0x180066a7d  mov     [rsp+190h+var_130], rbx
0x180066a82  mov     rcx, [rsp+190h+var_148]; psa
0x180066a87  test    rcx, rcx
0x180066a8a  jz      short loc_180066A92
0x180066a8c  call    cs:__imp_SafeArrayUnaccessData
0x180066a92  mov     edi, r12d
0x180066a95  mov     rcx, [rbp+98h]; this
0x180066a9c  test    edi, edi
0x180066a9e  jns     short loc_180066AB5
0x180066aa0  mov     r9d, edi; char *
0x180066aa3  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x180066aaa  mov     edx, 290h; void *
0x180066aaf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066ab5  mov     edi, r12d
0x180066ab8  test    r14d, r14d
0x180066abb  jle     short loc_180066ADC
0x180066abd  mov     eax, edi
0x180066abf  mov     ecx, [rbx+rax*4]
0x180066ac2  mov     dword ptr [rsp+190h+psa], ecx
0x180066ac6  lea     rdx, [rsp+190h+psa]
0x180066acb  lea     rcx, [r15+10h]
0x180066acf  call    ?Add@?$RepeatedField@I@protobuf@google@@QEAAXAEBI@Z; google::protobuf::RepeatedField<uint>::Add(uint const &)
0x180066ad4  add     edi, r13d
0x180066ad7  cmp     edi, r14d
0x180066ada  jl      short loc_180066ABD
0x180066adc  mov     rcx, rbx; Block
0x180066adf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180066ae4  nop
0x180066ae5  test    rsi, rsi
0x180066ae8  jz      short loc_180066AF4
0x180066aea  mov     rcx, rsi; psa
  ... truncated ...
```
