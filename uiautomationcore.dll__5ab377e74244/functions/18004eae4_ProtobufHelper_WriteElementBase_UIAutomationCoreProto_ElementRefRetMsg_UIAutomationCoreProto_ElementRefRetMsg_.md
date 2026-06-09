# ProtobufHelper::WriteElementBase<UIAutomationCoreProto::ElementRefRetMsg>(UIAutomationCoreProto::ElementRefRetMsg &,ElementRefRet &)

- ea: `0x18004eae4`
- end: `0x18004eff3`
- name: `??$WriteElementBase@VElementRefRetMsg@UIAutomationCoreProto@@@ProtobufHelper@@SAXAEAVElementRefRetMsg@UIAutomationCoreProto@@AEAUElementRefRet@@@Z`
- size: `1295`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180067070`
- `0x180069694`

## callees

- `0x1800206e8`
- `0x18002f580`
- `0x180032724`
- `0x18003c820`
- `0x18004e194`
- `0x18004e318`
- `0x18004e410`
- `0x18004e5f8`
- `0x18004e668`
- `0x18004e6c8`
- `0x18004eae4`
- `0x180068f08`
- `0x1800690c4`
- `0x180181488`
- `0x180189804`
- `0x1801a9630`
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

- `OLEAUT32!__imp_SysFreeString` at `0x18004ec81`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ec81`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004ee5c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004ee5c`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18004ecf7`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18004ecf7`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18004ed64`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18004ed64`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18004ed47`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18004ed47`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004ed88`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004ed88`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004edff`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004eef6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004edff`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004eef6`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18004ed14`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18004ed14`

## string_xrefs

- `0x18004eed9`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18004ef0d`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18004ee13`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ProtobufHelper::WriteElementBase<UIAutomationCoreProto::ElementRefRetMsg>(__int64 a1, __int64 a2)
{
  ProviderEntryPoint *v4; // rcx
  const unsigned __int16 *v5; // rcx
  UIAutomationCoreProto::ElementExtraInfoMsg *v6; // rsi
  _QWORD *v7; // rcx
  struct UIAutomationCoreProto::ProviderEntryPointMsg *v8; // rax
  _QWORD *v9; // rcx
  unsigned int v10; // edx
  _BYTE *v11; // rcx
  _QWORD *v12; // rcx
  SAFEARRAY *v13; // rsi
  __int64 v14; // r13
  struct google::protobuf::Arena *v15; // rcx
  _DWORD *v16; // rbx
  signed int i; // r14d
  HRESULT Vartype; // eax
  int v19; // edi
  unsigned __int64 v20; // rax
  _DWORD *v21; // r9
  __int64 v22; // r8
  signed int j; // edi
  UIAutomationCoreProto::UiaPropertyConditionMsg *v24; // rdi
  struct UIAutomationCoreProto::GuidMsg *v25; // rax
  const unsigned __int16 *v26; // rbx
  struct UIAutomationCoreProto::WstringMsg *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // r9
  struct UIAutomationCoreProto::CrossMachinePlaceHolderMsg *v31; // rax
  int pvt; // [rsp+20h] [rbp-89h] BYREF
  LONG plLbound; // [rsp+28h] [rbp-81h] BYREF
  LONG plUbound; // [rsp+30h] [rbp-79h] BYREF
  SAFEARRAY *v35; // [rsp+38h] [rbp-71h]
  unsigned int v36; // [rsp+40h] [rbp-69h]
  void *ppvData; // [rsp+48h] [rbp-61h] BYREF
  SAFEARRAY *psa; // [rsp+50h] [rbp-59h] BYREF
  _DWORD *v39; // [rsp+58h] [rbp-51h]
  ProviderEntryPoint *v40; // [rsp+60h] [rbp-49h] BYREF
  char v41; // [rsp+68h] [rbp-41h]
  GUID Buf1; // [rsp+6Ch] [rbp-3Dh] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v44[40]; // [rsp+88h] [rbp-21h] BYREF
  char v45; // [rsp+B0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  *(_DWORD *)(a1 + 40) = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 )
  {
    v4 = *(ProviderEntryPoint **)(a2 + 8);
    v40 = v4;
    if ( v4 )
      (*(void (__fastcall **)(ProviderEntryPoint *))(*(_QWORD *)v4 + 8LL))(v4);
    v41 = *(_BYTE *)(a2 + 16);
    Buf1 = *(GUID *)(a2 + 20);
    bstrString = 0;
    v45 = 0;
    if ( *(_BYTE *)(a2 + 88) )
      std::_Optional_construct_base<CrossMachinePlaceholderInfo>::_Construct<CrossMachinePlaceholderInfo const &>(
        v44,
        a2 + 48);
    v5 = *(const unsigned __int16 **)(a2 + 40);
    if ( v5 && (int)HrSysAllocString(v5, &bstrString) < 0 )
      Buf1 = GUID_NULL;
    v6 = *(UIAutomationCoreProto::ElementExtraInfoMsg **)(a1 + 16);
    if ( !v6 )
    {
      v7 = (_QWORD *)(*(_QWORD *)(a1 + 8) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
        v7 = (_QWORD *)*v7;
      v6 = (UIAutomationCoreProto::ElementExtraInfoMsg *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoMsg,>(v7);
      *(_QWORD *)(a1 + 16) = v6;
    }
    if ( v40 )
    {
      v8 = (struct UIAutomationCoreProto::ProviderEntryPointMsg *)*((_QWORD *)v6 + 2);
      if ( !v8 )
      {
        v9 = (_QWORD *)(*((_QWORD *)v6 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
        if ( (*((_BYTE *)v6 + 8) & 1) != 0 )
          v9 = (_QWORD *)*v9;
        v8 = (struct UIAutomationCoreProto::ProviderEntryPointMsg *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ProviderEntryPointMsg,>(v9);
        *((_QWORD *)v6 + 2) = v8;
      }
      ProviderEntryPoint::WriteToMessage(v40, v8);
    }
    if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      v24 = UIAutomationCoreProto::ElementExtraInfoMsg::_internal_mutable_component_site(v6);
      v25 = UIAutomationCoreProto::UiaPropertyConditionMsg::_internal_mutable_property_id(v24);
      ProtobufHelper::WriteGuid(v25, &Buf1);
      v26 = bstrString;
      v27 = UIAutomationCoreProto::StructuredMarkupRangeGetMarkupWithMarkedRangeRequestMsg::_internal_mutable_language(v24);
      ProtobufHelper::WriteString(v27, v26, 1);
    }
    if ( v45 )
    {
      v31 = UIAutomationCoreProto::ElementExtraInfoMsg::_internal_mutable_cross_machine_placeholder(v6);
      CrossMachinePlaceholderInfo::WriteToMessage((CrossMachinePlaceholderInfo *)v44, v31);
    }
    v11 = (_BYTE *)*((_QWORD *)v6 + 6);
    if ( !v11 )
    {
      v12 = (_QWORD *)(*((_QWORD *)v6 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*((_BYTE *)v6 + 8) & 1) != 0 )
        v12 = (_QWORD *)*v12;
      v11 = (_BYTE *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoFlagsMsg,>(v12);
      *((_QWORD *)v6 + 6) = v11;
    }
    v11[16] = v41 & 1;
    v11[17] = (v41 & 2) != 0;
    v11[18] = (v41 & 4) != 0;
    v11[19] = (v41 & 8) != 0;
    v11[20] = (v41 & 0x10) != 0;
    v11[21] = (v41 & 0x20) != 0;
    if ( v45 )
      CrossMachinePlaceholderInfo::`scalar deleting destructor'((CrossMachinePlaceholderInfo *)v44, v10);
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
  }
  ElementRefRet::TryGetRuntimeIdCopy(a2, &psa);
  v13 = psa;
  if ( psa )
  {
    v14 = *(_QWORD *)(a1 + 32);
    if ( !v14 )
    {
      v15 = (struct google::protobuf::Arena *)(*(_QWORD *)(a1 + 8) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
        v15 = *(struct google::protobuf::Arena **)v15;
      v14 = google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::IntArrayMsg,>(v15);
      *(_QWORD *)(a1 + 32) = v14;
    }
    if ( !v13 )
    {
      google::protobuf::RepeatedField<bool>::Clear(v14 + 16);
      goto LABEL_55;
    }
    v16 = 0;
    v39 = 0;
    v36 = 0;
    ppvData = 0;
    i = 0;
    v35 = v13;
    if ( SafeArrayGetDim(v13) == 1 )
    {
      LOWORD(pvt) = 0;
      Vartype = SafeArrayGetVartype(v35, (VARTYPE *)&pvt);
      v19 = Vartype;
      if ( Vartype < 0 )
      {
        v29 = 95;
      }
      else
      {
        if ( (_WORD)pvt != 3 && (_WORD)pvt != 22 )
        {
          v30 = 2147942487LL;
          v19 = -2147024809;
          v29 = 106;
          goto LABEL_63;
        }
        plLbound = 0;
        plUbound = 0;
        Vartype = SafeArrayGetLBound(v35, 1u, &plLbound);
        v19 = Vartype;
        if ( Vartype < 0 )
        {
          v29 = 111;
        }
        else
        {
          Vartype = SafeArrayGetUBound(v35, 1u, &plUbound);
          v19 = Vartype;
          if ( Vartype < 0 )
          {
            v29 = 112;
          }
          else
          {
            v36 = plUbound - plLbound + 1;
            Vartype = SafeArrayAccessData(v35, &ppvData);
            v19 = Vartype;
            if ( Vartype >= 0 )
            {
              v20 = 4LL * v36;
              if ( !is_mul_ok(v36, 4u) )
                v20 = -1;
              v21 = operator new[](v20, (const struct std::nothrow_t *)std::nothrow);
              if ( v21 )
              {
                v22 = 0;
                for ( i = v36; (unsigned int)v22 < v36; i = v36 )
                {
                  v21[(unsigned int)v22] = *((_DWORD *)ppvData + (unsigned int)v22);
                  v22 = (unsigned int)(v22 + 1);
                }
                v16 = v21;
                v39 = v21;
                if ( v35 )
                  SafeArrayUnaccessData(v35);
                v19 = 0;
                goto LABEL_50;
              }
              v19 = -2147024882;
              v28 = 162;
LABEL_59:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v28,
                (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                (const char *)(unsigned int)v19,
                pvt);
              if ( v35 )
                SafeArrayUnaccessData(v35);
LABEL_50:
              if ( v19 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x290,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
                  (const char *)(unsigned int)v19,
                  pvt);
              for ( j = 0; j < i; ++j )
              {
                plLbound = v16[j];
                google::protobuf::RepeatedField<unsigned int>::Add(v14 + 16, &plLbound, v22);
              }
              operator delete(v16);
              goto LABEL_55;
            }
            v29 = 115;
          }
        }
      }
      v30 = (unsigned int)Vartype;
    }
    else
    {
      v30 = 2147942487LL;
      v19 = -2147024809;
      v29 = 92;
    }
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v30,
      pvt);
    v28 = 159;
    goto LABEL_59;
  }
LABEL_55:
  if ( v13 )
    SafeArrayDestroy(v13);
}

```

## disassembly

```asm
0x18004eae4  mov     [rsp-8+arg_10], rbx
0x18004eae9  push    rbp
0x18004eaea  push    rsi
0x18004eaeb  push    rdi
0x18004eaec  push    r12
0x18004eaee  push    r13
0x18004eaf0  push    r14
0x18004eaf2  push    r15
0x18004eaf4  lea     rbp, [rsp-27h]
0x18004eaf9  sub     rsp, 0D0h
0x18004eb00  mov     rax, cs:__security_cookie
0x18004eb07  xor     rax, rsp
0x18004eb0a  mov     [rbp+57h+var_40], rax
0x18004eb0e  mov     r14, rdx
0x18004eb11  mov     r15, rcx
0x18004eb14  mov     eax, [rdx]
0x18004eb16  mov     [rcx+28h], eax
0x18004eb19  mov     edi, 1
0x18004eb1e  xor     r12d, r12d
0x18004eb21  cmp     [rdx], r12d
0x18004eb24  jz      loc_18004EC94
0x18004eb2a  mov     rcx, [rdx+8]
0x18004eb2e  mov     [rbp+57h+var_A0], rcx
0x18004eb32  test    rcx, rcx
0x18004eb35  jz      short loc_18004EB44
0x18004eb37  mov     rax, [rcx]
0x18004eb3a  mov     rax, [rax+8]
0x18004eb3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb43  nop
0x18004eb44  mov     al, [r14+10h]
0x18004eb48  mov     [rbp+57h+var_98], al
0x18004eb4b  mov     rax, [r14+14h]
0x18004eb4f  mov     [rbp+57h+Buf1], rax
0x18004eb53  mov     rax, [r14+1Ch]
0x18004eb57  mov     [rbp+57h+var_8C], rax
0x18004eb5b  mov     [rbp+57h+bstrString], r12
0x18004eb5f  lea     rdx, [r14+30h]
0x18004eb63  mov     [rbp+57h+var_50], r12b
0x18004eb67  cmp     [rdx+28h], r12b
0x18004eb6b  jnz     loc_18004EF92
0x18004eb71  mov     rcx, [r14+28h]; unsigned __int16 *
0x18004eb75  test    rcx, rcx
0x18004eb78  jnz     loc_18004EFA0
0x18004eb7e  mov     rsi, [r15+10h]
0x18004eb82  test    rsi, rsi
0x18004eb85  jnz     short loc_18004EBA5
0x18004eb87  mov     rcx, [r15+8]
0x18004eb8b  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18004eb8f  test    [r15+8], dil
0x18004eb93  jnz     loc_18004EF46
0x18004eb99  call    ??$CreateMaybeMessage@VElementExtraInfoMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVElementExtraInfoMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoMsg,>(google::protobuf::Arena *)
0x18004eb9e  mov     rsi, rax
0x18004eba1  mov     [r15+10h], rax
0x18004eba5  cmp     [rbp+57h+var_A0], r12
0x18004eba9  jz      short loc_18004EBDB
0x18004ebab  mov     rax, [rsi+10h]
0x18004ebaf  test    rax, rax
0x18004ebb2  jnz     short loc_18004EBCF
0x18004ebb4  mov     rcx, [rsi+8]
0x18004ebb8  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18004ebbc  test    [rsi+8], dil
0x18004ebc0  jnz     loc_18004EF56
0x18004ebc6  call    ??$CreateMaybeMessage@VProviderEntryPointMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVProviderEntryPointMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ProviderEntryPointMsg,>(google::protobuf::Arena *)
0x18004ebcb  mov     [rsi+10h], rax
0x18004ebcf  mov     rdx, rax; struct UIAutomationCoreProto::ProviderEntryPointMsg *
0x18004ebd2  mov     rcx, [rbp+57h+var_A0]; this
0x18004ebd6  call    ?WriteToMessage@ProviderEntryPoint@@QEBAJPEAVProviderEntryPointMsg@UIAutomationCoreProto@@@Z; ProviderEntryPoint::WriteToMessage(UIAutomationCoreProto::ProviderEntryPointMsg *)
0x18004ebdb  mov     r8d, 10h; Size
0x18004ebe1  lea     rdx, GUID_NULL; Buf2
0x18004ebe8  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18004ebec  call    memcmp_0
0x18004ebf1  test    eax, eax
0x18004ebf3  jnz     loc_18004EE89
0x18004ebf9  cmp     [rbp+57h+var_50], r12b
0x18004ebfd  jnz     loc_18004EFCC
0x18004ec03  mov     rcx, [rsi+30h]
0x18004ec07  test    rcx, rcx
0x18004ec0a  jnz     short loc_18004EC2A
0x18004ec0c  mov     rcx, [rsi+8]
0x18004ec10  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18004ec14  test    [rsi+8], dil
0x18004ec18  jnz     loc_18004EF4E
0x18004ec1e  call    ??$CreateMaybeMessage@VElementExtraInfoFlagsMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVElementExtraInfoFlagsMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::ElementExtraInfoFlagsMsg,>(google::protobuf::Arena *)
0x18004ec23  mov     rcx, rax
0x18004ec26  mov     [rsi+30h], rax
0x18004ec2a  mov     al, [rbp+57h+var_98]
0x18004ec2d  and     al, dil
0x18004ec30  mov     [rcx+10h], al
0x18004ec33  mov     al, [rbp+57h+var_98]
0x18004ec36  shr     al, 1
0x18004ec38  and     al, dil
0x18004ec3b  mov     [rcx+11h], al
0x18004ec3e  mov     al, [rbp+57h+var_98]
0x18004ec41  shr     al, 2
0x18004ec44  and     al, dil
0x18004ec47  mov     [rcx+12h], al
0x18004ec4a  mov     al, [rbp+57h+var_98]
0x18004ec4d  shr     al, 3
0x18004ec50  and     al, dil
0x18004ec53  mov     [rcx+13h], al
0x18004ec56  mov     al, [rbp+57h+var_98]
0x18004ec59  shr     al, 4
0x18004ec5c  and     al, dil
0x18004ec5f  mov     [rcx+14h], al
0x18004ec62  mov     al, [rbp+57h+var_98]
0x18004ec65  shr     al, 5
0x18004ec68  and     al, dil
0x18004ec6b  mov     [rcx+15h], al
0x18004ec6e  cmp     [rbp+57h+var_50], r12b
0x18004ec72  jnz     loc_18004EFE5
0x18004ec78  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18004ec7c  test    rcx, rcx
0x18004ec7f  jz      short loc_18004EC8B
0x18004ec81  call    cs:__imp_SysFreeString
0x18004ec87  mov     [rbp+57h+bstrString], r12
0x18004ec8b  lea     rcx, [rbp+57h+var_A0]
0x18004ec8f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ec94  lea     rdx, [rbp+57h+psa]
0x18004ec98  mov     rcx, r14
0x18004ec9b  call    ?TryGetRuntimeIdCopy@ElementRefRet@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; ElementRefRet::TryGetRuntimeIdCopy(void)
0x18004eca0  nop
0x18004eca1  mov     rsi, [rbp+57h+psa]
0x18004eca5  test    rsi, rsi
0x18004eca8  jz      loc_18004EE54
0x18004ecae  mov     r13, [r15+20h]
0x18004ecb2  test    r13, r13
0x18004ecb5  jnz     short loc_18004ECD5
0x18004ecb7  mov     rcx, [r15+8]
0x18004ecbb  and     rcx, 0FFFFFFFFFFFFFFFCh; struct google::protobuf::Arena *
0x18004ecbf  test    [r15+8], dil
0x18004ecc3  jnz     loc_18004EF3E
0x18004ecc9  call    ??$CreateMaybeMessage@VIntArrayMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVIntArrayMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::IntArrayMsg,>(google::protobuf::Arena *)
0x18004ecce  mov     r13, rax
0x18004ecd1  mov     [r15+20h], rax
0x18004ecd5  test    rsi, rsi
0x18004ecd8  jz      loc_18004EF5E
0x18004ecde  mov     rbx, r12
0x18004ece1  mov     [rbp+57h+var_A8], rbx
0x18004ece5  mov     [rbp+57h+var_C0], r12d
0x18004ece9  mov     [rbp+57h+ppvData], r12
0x18004eced  mov     r14d, r12d
0x18004ecf0  mov     [rbp+57h+var_C8], rsi
0x18004ecf4  mov     rcx, rsi; psa
0x18004ecf7  call    cs:__imp_SafeArrayGetDim
0x18004ecfd  cmp     eax, edi
0x18004ecff  jnz     loc_18004EF27
0x18004ed05  mov     word ptr [rsp+100h+pvt], r12w; int
0x18004ed0b  lea     rdx, [rsp+100h+pvt]; pvt
0x18004ed10  mov     rcx, [rbp+57h+var_C8]; psa
0x18004ed14  call    cs:__imp_SafeArrayGetVartype
0x18004ed1a  mov     edi, eax
0x18004ed1c  test    eax, eax
0x18004ed1e  js      loc_18004EF37
0x18004ed24  cmp     word ptr [rsp+100h+pvt], 3
0x18004ed2a  jnz     loc_18004EF73
0x18004ed30  mov     [rsp+100h+plLbound], r12d
0x18004ed35  mov     [rbp+57h+plUbound], r12d
0x18004ed39  lea     r8, [rsp+100h+plLbound]; plLbound
0x18004ed3e  mov     edx, 1; nDim
0x18004ed43  mov     rcx, [rbp+57h+var_C8]; psa
0x18004ed47  call    cs:__imp_SafeArrayGetLBound
0x18004ed4d  mov     edi, eax
0x18004ed4f  test    eax, eax
0x18004ed51  js      loc_18004EF01
0x18004ed57  lea     r8, [rbp+57h+plUbound]; plUbound
0x18004ed5b  mov     edx, 1; nDim
0x18004ed60  mov     rcx, [rbp+57h+var_C8]; psa
0x18004ed64  call    cs:__imp_SafeArrayGetUBound
0x18004ed6a  mov     edi, eax
0x18004ed6c  test    eax, eax
0x18004ed6e  js      loc_18004EF20
0x18004ed74  mov     eax, [rbp+57h+plUbound]
0x18004ed77  sub     eax, [rsp+100h+plLbound]
0x18004ed7b  inc     eax
0x18004ed7d  mov     [rbp+57h+var_C0], eax
0x18004ed80  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18004ed84  mov     rcx, [rbp+57h+var_C8]; psa
0x18004ed88  call    cs:__imp_SafeArrayAccessData
0x18004ed8e  mov     edi, eax
0x18004ed90  test    eax, eax
0x18004ed92  js      loc_18004EF6C
0x18004ed98  mov     ecx, [rbp+57h+var_C0]
0x18004ed9b  mov     eax, 4
0x18004eda0  mul     rcx
0x18004eda3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004edaa  cmovb   rax, rcx
0x18004edae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004edb5  mov     rcx, rax; unsigned __int64
0x18004edb8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004edbd  mov     r9, rax
0x18004edc0  test    rax, rax
0x18004edc3  jz      loc_18004EECC
0x18004edc9  mov     r8d, r12d
0x18004edcc  mov     r14d, [rbp+57h+var_C0]
0x18004edd0  test    r14d, r14d
0x18004edd3  jz      short loc_18004EDEF
0x18004edd5  mov     edx, r8d
0x18004edd8  mov     rcx, [rbp+57h+ppvData]
0x18004eddc  mov     eax, [rcx+rdx*4]
0x18004eddf  mov     [r9+rdx*4], eax
0x18004ede3  inc     r8d
0x18004ede6  mov     r14d, [rbp+57h+var_C0]
0x18004edea  cmp     r8d, r14d
0x18004eded  jb      short loc_18004EDD5
0x18004edef  mov     rbx, r9
0x18004edf2  mov     [rbp+57h+var_A8], rbx
0x18004edf6  mov     rcx, [rbp+57h+var_C8]; psa
0x18004edfa  test    rcx, rcx
0x18004edfd  jz      short loc_18004EE05
0x18004edff  call    cs:__imp_SafeArrayUnaccessData
0x18004ee05  mov     edi, r12d
0x18004ee08  mov     rcx, [rbp+5Fh]; this
0x18004ee0c  test    edi, edi
0x18004ee0e  jns     short loc_18004EE25
0x18004ee10  mov     r9d, edi; char *
0x18004ee13  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x18004ee1a  mov     edx, 290h; void *
0x18004ee1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ee25  mov     edi, r12d
0x18004ee28  test    r14d, r14d
0x18004ee2b  jle     short loc_18004EE4B
0x18004ee2d  mov     eax, edi
0x18004ee2f  mov     ecx, [rbx+rax*4]
0x18004ee32  mov     [rsp+100h+plLbound], ecx
0x18004ee36  lea     rdx, [rsp+100h+plLbound]
0x18004ee3b  lea     rcx, [r13+10h]
0x18004ee3f  call    ?Add@?$RepeatedField@I@protobuf@google@@QEAAXAEBI@Z; google::protobuf::RepeatedField<uint>::Add(uint const &)
0x18004ee44  inc     edi
0x18004ee46  cmp     edi, r14d
0x18004ee49  jl      short loc_18004EE2D
0x18004ee4b  mov     rcx, rbx; Block
0x18004ee4e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004ee53  nop
0x18004ee54  test    rsi, rsi
0x18004ee57  jz      short loc_18004EE62
0x18004ee59  mov     rcx, rsi; psa
0x18004ee5c  call    cs:__imp_SafeArrayDestroy
0x18004ee62  mov     rcx, [rbp+57h+var_40]
0x18004ee66  xor     rcx, rsp; StackCookie
0x18004ee69  call    __security_check_cookie
0x18004ee6e  mov     rbx, [rsp+100h+arg_10]
0x18004ee76  add     rsp, 0D0h
0x18004ee7d  pop     r15
0x18004ee7f  pop     r14
0x18004ee81  pop     r13
0x18004ee83  pop     r12
0x18004ee85  pop     rdi
0x18004ee86  pop     rsi
0x18004ee87  pop     rbp
0x18004ee88  retn
0x18004ee89  mov     rcx, rsi; this
0x18004ee8c  call    ?_internal_mutable_component_site@ElementExtraInfoMsg@UIAutomationCoreProto@@AEAAPEAVComponentSiteMsg@2@XZ; UIAutomationCoreProto::ElementExtraInfoMsg::_internal_mutable_component_site(void)
0x18004ee91  mov     rdi, rax
0x18004ee94  mov     rcx, rax; this
0x18004ee97  call    ?_internal_mutable_property_id@UiaPropertyConditionMsg@UIAutomationCoreProto@@AEAAPEAVGuidMsg@2@XZ; UIAutomationCoreProto::UiaPropertyConditionMsg::_internal_mutable_property_id(void)
0x18004ee9c  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x18004eea0  mov     rcx, rax; struct UIAutomationCoreProto::GuidMsg *
0x18004eea3  call    ?WriteGuid@ProtobufHelper@@SAXAEAVGuidMsg@UIAutomationCoreProto@@AEBU_GUID@@@Z; ProtobufHelper::WriteGuid(UIAutomationCoreProto::GuidMsg &,_GUID const &)
0x18004eea8  mov     rbx, [rbp+57h+bstrString]
0x18004eeac  mov     rcx, rdi; this
0x18004eeaf  call    ?_internal_mutable_language@StructuredMarkupRangeGetMarkupWithMarkedRangeRequestMsg@UIAutomationCoreProto@@AEAAPEAVWstringMsg@2@XZ; UIAutomationCoreProto::StructuredMarkupRangeGetMarkupWithMarkedRangeRequestMsg::_internal_mutable_language(void)
0x18004eeb4  mov     edi, 1
0x18004eeb9  mov     r8b, dil; bool
0x18004eebc  mov     rdx, rbx; unsigned __int16 *
0x18004eebf  mov     rcx, rax; struct UIAutomationCoreProto::WstringMsg *
0x18004eec2  call    ?WriteString@ProtobufHelper@@SAXAEAVWstringMsg@UIAutomationCoreProto@@PEBG_N@Z; ProtobufHelper::WriteString(UIAutomationCoreProto::WstringMsg &,ushort const *,bool)
0x18004eec7  jmp     loc_18004EBF9
0x18004eecc  mov     edi, 8007000Eh
0x18004eed1  mov     edx, 0A2h; void *
0x18004eed6  mov     r9d, edi; char *
0x18004eed9  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18004eee0  mov     rcx, [rbp+5Fh]; this
0x18004eee4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eee9  mov     rcx, [rbp+57h+var_C8]; psa
0x18004eeed  test    rcx, rcx
0x18004eef0  jz      loc_18004EE08
0x18004eef6  call    cs:__imp_SafeArrayUnaccessData
0x18004eefc  jmp     loc_18004EE08
0x18004ef01  mov     edx, 6Fh ; 'o'; void *
0x18004ef06  mov     r9d, eax; char *
0x18004ef09  mov     rcx, [rbp+5Fh]; this
0x18004ef0d  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x18004ef14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ef19  mov     edx, 9Fh
0x18004ef1e  jmp     short loc_18004EED6
0x18004ef20  mov     edx, 70h ; 'p'
0x18004ef25  jmp     short loc_18004EF06
0x18004ef27  mov     r9d, 80070057h
0x18004ef2d  mov     edi, r9d
0x18004ef30  mov     edx, 5Ch ; '\'
0x18004ef35  jmp     short loc_18004EF09
0x18004ef37  mov     edx, 5Fh ; '_'
0x18004ef3c  jmp     short loc_18004EF06
0x18004ef3e  mov     rcx, [rcx]
0x18004ef41  jmp     loc_18004ECC9
0x18004ef46  mov     rcx, [rcx]
0x18004ef49  jmp     loc_18004EB99
0x18004ef4e  mov     rcx, [rcx]
0x18004ef51  jmp     loc_18004EC1E
0x18004ef56  mov     rcx, [rcx]
  ... truncated ...
```
