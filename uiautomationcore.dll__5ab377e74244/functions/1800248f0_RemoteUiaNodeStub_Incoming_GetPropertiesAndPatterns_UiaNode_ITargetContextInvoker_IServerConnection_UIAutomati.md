# RemoteUiaNodeStub::Incoming_GetPropertiesAndPatterns(UiaNode *,ITargetContextInvoker *,IServerConnection *,UIAutomationCoreProto::ElementMethodRequestMsg const &,UIAutomationCoreProto::ElementMethodResponseMsg &)

- ea: `0x1800248f0`
- end: `0x18002528a`
- name: `?Incoming_GetPropertiesAndPatterns@RemoteUiaNodeStub@@CAJPEAVUiaNode@@PEAUITargetContextInvoker@@PEAVIServerConnection@@AEBVElementMethodRequestMsg@UIAutomationCoreProto@@AEAVElementMethodResponseMsg@6@@Z`
- size: `2458`
- prototype: `__int64 __fastcall(struct UiaNode *, struct ITargetContextInvoker *, struct IServerConnection *, const struct UIAutomationCoreProto::ElementMethodRequestMsg *, struct UIAutomationCoreProto::ElementMethodResponseMsg *)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180022548`
- `0x1800239fc`
- `0x1800247e4`
- `0x1800248f0`
- `0x1800264f8`
- `0x180026970`
- `0x18002f580`
- `0x1800313a0`
- `0x180032724`
- `0x180033e04`
- `0x180033e30`
- `0x180033e60`
- `0x180046528`
- `0x180047b90`
- `0x180048a3c`
- `0x180048ab0`
- `0x1800b710c`
- `0x1800be9c8`
- `0x1800c6f64`
- `0x1800c84d0`
- `0x18010e86c`
- `0x18012f650`
- `0x1801b78fc`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e88a0`
- `0x1801e924c`
- `0x1801ec680`
- `0x1802dd010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180025202`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002522d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180025202`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002522d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024d82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024d82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024db0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024db0`
- `OLEAUT32!__imp_VariantInit` at `0x180024bb2`
- `OLEAUT32!__imp_VariantInit` at `0x180024bb2`
- `OLEAUT32!__imp_VariantClear` at `0x1800251ea`
- `OLEAUT32!__imp_VariantClear` at `0x1800251ea`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180024fca`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180024fca`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180024ebc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180024ebc`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180024a66`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180024a66`

## string_xrefs

- `0x180024be6`: `onecore\windows\accessibletech\uiautomationcore\remoteuianodestub.cpp`
- `0x180024cfb`: `onecore\windows\accessibletech\uiautomationcore\remoteuianodestub.cpp`
- `0x180024e5c`: `onecore\windows\accessibletech\uiautomationcore\remoteuianodestub.cpp`
- `0x1800250c9`: `onecore\windows\accessibletech\uiautomationcore\remoteuianodestub.cpp`
- `0x1800250e1`: `onecore\windows\accessibletech\uiautomationcore\remoteuianodestub.cpp`
- `0x180024a7b`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x180025099`: `onecore\windows\accessibletech\uiautomationcore\SmartPointers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall RemoteUiaNodeStub::Incoming_GetPropertiesAndPatterns(
        struct UiaNode *a1,
        struct ITargetContextInvoker *a2,
        struct IServerConnection *a3,
        const struct UIAutomationCoreProto::ElementMethodRequestMsg *a4,
        struct UIAutomationCoreProto::ElementMethodResponseMsg *a5)
{
  __int64 v5; // rsi
  __int64 v6; // r12
  unsigned __int64 v7; // r13
  __int64 size_of; // rax
  void *v9; // rdi
  int i; // ebx
  __int64 v11; // rcx
  void *v12; // rdx
  const OLECHAR *v13; // rcx
  HRESULT v14; // eax
  GUID v15; // xmm6
  OLECHAR *v16; // rcx
  int j; // ecx
  GUID **v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  unsigned __int64 v21; // rax
  struct tagVARIANT *v22; // r15
  __int64 m; // rdi
  int v24; // ebx
  unsigned __int64 v25; // r12
  __int64 v26; // rax
  void *v27; // rdi
  int n; // ebx
  int PropertiesAndPatterns; // eax
  struct UIAutomationCoreProto::GetPropertiesAndPatternsResponseMsg *properties_and_patterns_response; // r13
  unsigned int ii; // edi
  _DWORD *v32; // rcx
  __int64 v33; // rdx
  void *v34; // rax
  UIAutomationCoreProto::VariantObjectMsg *v35; // r14
  int v36; // esi
  __int128 v37; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  GUID **jj; // rbx
  bool v40; // cf
  int RuntimeId; // eax
  SAFEARRAY *v42; // rcx
  unsigned int kk; // ebx
  void *v44; // rcx
  const char *v45; // r9
  void *v46; // rcx
  __int64 result; // rax
  const struct PatternInfo *PatternInfo; // rsi
  __int64 v49; // r14
  struct IRecordInfoVtbl *lpVtbl; // rdx
  int v51; // eax
  int AutomationId; // eax
  struct UserDefinedPropertyInfo *k; // rcx
  _QWORD *v54; // r8
  __int64 v55; // rax
  unsigned int v56; // edi
  unsigned int v57; // ebx
  unsigned int mm; // esi
  int v59; // [rsp+20h] [rbp-168h]
  int v60; // [rsp+20h] [rbp-168h]
  void *v61; // [rsp+50h] [rbp-138h] BYREF
  unsigned int v62; // [rsp+58h] [rbp-130h]
  unsigned __int64 v63; // [rsp+60h] [rbp-128h] BYREF
  void *v64; // [rsp+68h] [rbp-120h] BYREF
  unsigned __int64 v65; // [rsp+70h] [rbp-118h] BYREF
  SAFEARRAY *psa; // [rsp+78h] [rbp-110h] BYREF
  void *v67[2]; // [rsp+80h] [rbp-108h] BYREF
  void *v68; // [rsp+90h] [rbp-F8h]
  int v69[2]; // [rsp+98h] [rbp-F0h]
  int v70; // [rsp+A0h] [rbp-E8h] BYREF
  void *Block; // [rsp+A8h] [rbp-E0h]
  void *Src[2]; // [rsp+B0h] [rbp-D8h] BYREF
  void *v73; // [rsp+C0h] [rbp-C8h]
  GUID v74; // [rsp+D0h] [rbp-B8h]
  GUID iid; // [rsp+E0h] [rbp-A8h] BYREF
  UIAutomationCoreProto::ElementMethodResponseMsg *v76; // [rsp+F0h] [rbp-98h]
  struct ITargetContextInvoker *v77; // [rsp+F8h] [rbp-90h]
  LPCOLESTR lpsz[2]; // [rsp+100h] [rbp-88h] BYREF
  IRecordInfo *v79; // [rsp+110h] [rbp-78h]
  unsigned __int64 v80; // [rsp+118h] [rbp-70h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  try
  {
    v63 = (unsigned __int64)a3;
    v77 = a2;
    v61 = a1;
    v76 = a5;
    if ( *((_DWORD *)a4 + 9) != 36 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2F7,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\remoteuianodestub.cpp",
        (const char *)0x80040803LL,
        v59);
    v5 = *((_QWORD *)a4 + 3);
    v6 = *(_QWORD *)(v5 + 64);
    v69[0] = *(_BYTE *)(v5 + 72) != 0;
    v7 = *(unsigned int *)(v5 + 24);
    v62 = v7;
    *(_OWORD *)Src = 0;
    v73 = 0;
    if ( (_DWORD)v7 )
    {
      if ( (unsigned __int64)(int)v7 > 0x3FFFFFFFFFFFFFFFLL )
        std::_Xlength_error("vector too long");
      size_of = std::_Get_size_of_n<4>((int)v7);
      v9 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
      memmove_0(v9, Src[0], (char *)Src[1] - (char *)Src[0]);
      std::vector<int>::_Change_array(Src, v9, 0, (int)v7);
    }
    for ( i = 0; i < (int)v7; ++i )
    {
      v11 = *(_QWORD *)(*(_QWORD *)(v5 + 32) + 8LL * i + 8);
      v12 = &UIAutomationCoreProto::_WstringMsg_default_instance_;
      if ( *(_QWORD *)(v11 + 16) )
        v12 = *(void **)(v11 + 16);
      ProtobufHelper::GetWstring(lpsz, v12);
      iid = 0;
      v13 = (const OLECHAR *)lpsz;
      if ( v80 > 7 )
        v13 = lpsz[0];
      v14 = IIDFromString(v13, &iid);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x46,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
          (const char *)(unsigned int)v14,
          v59);
      v15 = iid;
      if ( v80 > 7 )
      {
        v65 = 2 * v80 + 2;
        v16 = (OLECHAR *)lpsz[0];
        v64 = (void *)lpsz[0];
        if ( v65 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v64, &v65);
          v16 = (OLECHAR *)v64;
        }
        operator delete(v16);
      }
      v74 = v15;
      for ( j = 0; ; ++j )
      {
        if ( j >= 176 )
        {
          for ( k = g_pUserDefinedProperties; k; k = *(struct UserDefinedPropertyInfo **)k )
          {
            v18 = (GUID **)((char *)k + 16);
            v54 = (_QWORD *)*((_QWORD *)k + 2);
            v55 = *v54 - *(_QWORD *)&v74.Data1;
            if ( *v54 == *(_QWORD *)&v74.Data1 )
              v55 = v54[1] - *(_QWORD *)v74.Data4;
            if ( !v55 )
              goto LABEL_24;
          }
          goto LABEL_89;
        }
        v18 = &(&off_1802DE930)[8 * (__int64)j];
        v19 = *(_QWORD *)&(*v18)->Data1 - *(_QWORD *)&v74.Data1;
        if ( !v19 )
          v19 = *(_QWORD *)(*v18)->Data4 - *(_QWORD *)v74.Data4;
        if ( !v19 )
          break;
      }
LABEL_24:
      if ( v18 )
      {
        v20 = *((_DWORD *)v18 + 2);
        goto LABEL_26;
      }
LABEL_89:
      v20 = 0;
LABEL_26:
      LODWORD(v64) = v20;
      if ( Src[1] == v73 )
      {
        std::vector<uiacore::instructions::OperandId>::_Emplace_reallocate<uiacore::instructions::OperandId &>(
          Src,
          Src[1],
          &v64);
      }
      else
      {
        *(_DWORD *)Src[1] = v20;
        Src[1] = (char *)Src[1] + 4;
      }
    }
    LODWORD(v64) = 0;
    iid.Data1 = 0;
    v21 = 24 * v7;
    if ( !is_mul_ok(v7, 0x18u) )
      v21 = -1;
    v22 = (struct tagVARIANT *)operator new[](v21, (const struct std::nothrow_t *)std::nothrow);
    *(_QWORD *)iid.Data4 = v22;
    if ( v22 )
    {
      for ( m = 0; (unsigned int)m < (unsigned int)v7; m = (unsigned int)(m + 1) )
      {
        VariantInit(&v22[m]);
        v22[m].llVal = 0;
      }
      LODWORD(v64) = v7;
      iid.Data1 = v7;
      v24 = 0;
    }
    else
    {
      v24 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x234,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\SmartPointers.h",
        (const char *)0x8007000ELL,
        v59);
    }
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x307,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\remoteuianodestub.cpp",
        (const char *)(unsigned int)v24,
        v59);
    *(_QWORD *)&v74.Data1 = (char *)v61 + 88;
    *((_QWORD *)v61 + 11) = v6;
    v25 = *(int *)(v5 + 48);
    *(_OWORD *)v67 = 0;
    v68 = 0;
    if ( (_DWORD)v25 )
    {
      if ( v25 > 0x3FFFFFFFFFFFFFFFLL )
        std::_Xlength_error("vector too long");
      v26 = std::_Get_size_of_n<4>(v25);
      v27 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(v26);
      memmove_0(v27, v67[0], (char *)v67[1] - (char *)v67[0]);
      std::vector<int>::_Change_array(v67, v27, 0, v25);
    }
    for ( n = 0; n < (int)v25; ++n )
    {
      AutomationId = ProtobufHelper::GetAutomationId(
                       *(const struct UIAutomationCoreProto::GuidMsg **)(*(_QWORD *)(v5 + 56) + 8LL * n + 8),
                       AutomationIdentifierType_Pattern);
      LODWORD(v65) = AutomationId;
      if ( v67[1] == v68 )
      {
        std::vector<uiacore::instructions::OperandId>::_Emplace_reallocate<uiacore::instructions::OperandId &>(
          v67,
          v67[1],
          &v65);
      }
      else
      {
        *(_DWORD *)v67[1] = AutomationId;
        v67[1] = (char *)v67[1] + 4;
      }
    }
    v65 = (unsigned __int64)v61 + 48;
    psa = 0;
    PropertiesAndPatterns = UiaNode::CrossProcess_GetPropertiesAndPatterns(
                              (UiaNode *)((char *)v61 + 48),
                              0,
                              v7,
                              (const int *)Src[0],
                              v69[0],
                              v22,
                              v25,
                              (const int *)v67[0],
                              &psa);
    if ( PropertiesAndPatterns < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x31D,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\remoteuianodestub.cpp",
        (const char *)(unsigned int)PropertiesAndPatterns,
        v60);
    properties_and_patterns_response = UIAutomationCoreProto::ElementMethodResponseMsg::_internal_mutable_get_properties_and_patterns_response(v76);
    for ( ii = 0; ii < v62; ++ii )
    {
      v32 = (_DWORD *)*((_QWORD *)properties_and_patterns_response + 4);
      if ( v32 && (v33 = *((int *)properties_and_patterns_response + 6), (int)v33 < *v32) )
      {
        v35 = *(UIAutomationCoreProto::VariantObjectMsg **)&v32[2 * v33 + 2];
        *((_DWORD *)properties_and_patterns_response + 6) = v33 + 1;
      }
      else
      {
        v34 = (void *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::VariantObjectMsg,>(*((_QWORD *)properties_and_patterns_response + 2));
        v35 = (UIAutomationCoreProto::VariantObjectMsg *)google::protobuf::internal::RepeatedPtrFieldBase::AddOutOfLineHelper(
                                                           (struct UIAutomationCoreProto::GetPropertiesAndPatternsResponseMsg *)((char *)properties_and_patterns_response + 16),
                                                           v34);
      }
      v36 = *((_DWORD *)Src[0] + ii);
      v37 = *(_OWORD *)&v22[ii].vt;
      pRecInfo = v22[ii].pRecInfo;
      LOBYTE(v69[1]) = 0;
      EnterCriticalSection(&_schemaLock);
      if ( (unsigned int)(v36 - 30000) > 0xAF )
      {
        for ( jj = (GUID **)g_pUserDefinedProperties; jj; jj = (GUID **)*jj )
        {
          if ( *((_DWORD *)jj + 6) == v36 )
          {
            jj += 2;
            break;
          }
        }
      }
      else
      {
        jj = &(&off_1802DE930)[8 * (unsigned __int64)(unsigned int)(v36 - 30000)];
      }
      LeaveCriticalSection(&_schemaLock);
      if ( jj )
        *(_QWORD *)v69 = *(GUID **)((char *)jj + 52);
      *(_OWORD *)lpsz = v37;
      v79 = pRecInfo;
      ProtobufHelper::WriteObjInternal(v35, 0, 0, v63, v63, 1);
    }
    v70 = 0;
    Block = 0;
    v40 = v61 != 0;
    v61 = (void *)-(__int64)v61;
    RuntimeId = GetRuntimeId(v65 & -(__int64)v40, (__int64)&v70);
    if ( RuntimeId < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x327,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\remoteuianodestub.cpp",
        (const char *)(unsigned int)RuntimeId,
        v60);
    v42 = psa;
    if ( psa )
    {
      SafeArrayAccessor<IUnknown *>::SafeArrayAccessor<IUnknown *>(lpsz, psa);
      if ( LODWORD(lpsz[1]) != (_DWORD)v25 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x32C,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\remoteuianodestub.cpp",
          (const char *)0x8000FFFFLL,
          v60);
      for ( kk = 0; ; ++kk )
      {
        if ( kk >= (unsigned int)v25 )
        {
          if ( lpsz[0] )
            SafeArrayUnaccessData((SAFEARRAY *)lpsz[0]);
          v42 = psa;
          goto LABEL_64;
        }
        PatternInfo = Schema::GetPatternInfo(*((_DWORD *)v67[0] + kk));
        if ( !PatternInfo )
          break;
        v49 = google::protobuf::internal::RepeatedPtrFieldBase::Add<google::protobuf::RepeatedPtrField<UIAutomationCoreProto::PatternRefMsg>::TypeHandler>((struct UIAutomationCoreProto::GetPropertiesAndPatternsResponseMsg *)((char *)properties_and_patterns_response + 40));
        lpVtbl = v79[kk].lpVtbl;
        if ( lpVtbl )
          v51 = (*(__int64 (__fastcall **)(unsigned __int64, struct IRecordInfoVtbl *, const struct PatternInfo *, int *, struct ITargetContextInvoker *))(*(_QWORD *)v63 + 40LL))(
                  v63,
                  lpVtbl,
                  PatternInfo,
                  &v70,
                  v77);
        else
          v51 = 0;
        *(_DWORD *)(v49 + 16) = v51;
      }
      v56 = Error::InternalErrorWorker(L"got pattern ID, but lookup of id failed");
      SafeArrayAccessor<IDispatch *>::~SafeArrayAccessor<IDispatch *>(lpsz);
      if ( Block )
        operator delete(Block);
      v70 = 0;
      Block = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>>(&psa);
      std::vector<winrt::Windows::UI::UIAutomation::Core::AutomationRemoteOperationOperandId>::_Tidy(v67);
      if ( v22 )
      {
        v57 = 0;
        for ( mm = (unsigned int)v64; v57 < mm; ++v57 )
          VariantClear(&v22[v57]);
        operator delete(v22);
      }
      std::vector<winrt::Windows::UI::UIAutomation::Core::AutomationRemoteOperationOperandId>::_Tidy(Src);
      result = v56;
    }
    else
    {
LABEL_64:
      **(_QWORD **)&v74.Data1 = 0;
      if ( Block )
      {
        operator delete(Block);
        v42 = psa;
      }
      v70 = 0;
      Block = 0;
      if ( v42 )
        SafeArrayDestroy(v42);
      v44 = v67[0];
      if ( v67[0] )
      {
        v63 = ((unsigned __int64)v68 - (unsigned __int64)v67[0]) & 0xFFFFFFFFFFFFFFFCuLL;
        v61 = v67[0];
        if ( v63 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v61, &v63);
          v44 = v61;
        }
        operator delete(v44);
        *(_OWORD *)v67 = 0;
        v68 = 0;
      }
      StructArrayPair<tagVARIANT>::SafeRelease(&iid);
      v46 = Src[0];
      if ( Src[0] )
      {
        v63 = ((unsigned __int64)v73 - (unsigned __int64)Src[0]) & 0xFFFFFFFFFFFFFFFCuLL;
        v61 = Src[0];
        if ( v63 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v61, &v63);
          v46 = v61;
        }
        operator delete(v46);
      }
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x33E,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\remoteuianodestub.cpp",
                           v45);
  }
  return result;
}

```

## disassembly

```asm
0x1800248f0  mov     rax, rsp
0x1800248f3  push    rbx
0x1800248f4  push    rsi
0x1800248f5  push    rdi
0x1800248f6  push    r12
0x1800248f8  push    r13
0x1800248fa  push    r14
0x1800248fc  push    r15
0x1800248fe  sub     rsp, 150h
0x180024905  movaps  xmmword ptr [rax-48h], xmm6
0x180024909  movaps  xmmword ptr [rax-58h], xmm7
0x18002490d  mov     rax, cs:__security_cookie
0x180024914  xor     rax, rsp
0x180024917  mov     [rsp+188h+var_68], rax
0x18002491f  mov     [rsp+188h+var_128], r8
0x180024924  mov     [rsp+188h+var_90], rdx
0x18002492c  mov     [rsp+188h+var_138], rcx
0x180024931  mov     rax, [rsp+188h+arg_20]
0x180024939  mov     [rsp+188h+var_98], rax
0x180024941  xor     r15d, r15d
0x180024944  cmp     dword ptr [r9+24h], 24h ; '$'
0x180024949  setnz   al
0x18002494c  mov     rcx, [rsp+188h]; this
0x180024954  test    al, al
0x180024956  jnz     loc_1800250C3
0x18002495c  cmp     dword ptr [r9+24h], 24h ; '$'
0x180024961  jnz     loc_180024BF8
0x180024967  mov     rsi, [r9+18h]
0x18002496b  mov     r12, [rsi+40h]
0x18002496f  mov     eax, r15d
0x180024972  cmp     [rsi+48h], r15b
0x180024976  setnz   al
0x180024979  mov     [rsp+188h+var_F0], eax
0x180024980  mov     r13d, [rsi+18h]
0x180024984  mov     [rsp+188h+var_130], r13d
0x180024989  xorps   xmm0, xmm0
0x18002498c  movdqu  xmmword ptr [rsp+188h+Src], xmm0
0x180024995  mov     [rsp+188h+var_C8], r15
0x18002499d  movsxd  rbx, r13d
0x1800249a0  mov     r14, 3FFFFFFFFFFFFFFFh
0x1800249aa  test    r13d, r13d
0x1800249ad  jz      short loc_1800249FC
0x1800249af  cmp     rbx, r14
0x1800249b2  ja      loc_1800251FB
0x1800249b8  mov     rcx, rbx
0x1800249bb  call    ??$_Get_size_of_n@$03@std@@YA_K_K@Z; std::_Get_size_of_n<4>(unsigned __int64)
0x1800249c0  mov     rcx, rax
0x1800249c3  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800249c8  mov     rdi, rax
0x1800249cb  mov     rdx, [rsp+188h+Src]; Src
0x1800249d3  mov     r8, [rsp+188h+Src+8]
0x1800249db  sub     r8, rdx; Size
0x1800249de  mov     rcx, rax; void *
0x1800249e1  call    memmove_0
0x1800249e6  mov     r9, rbx
0x1800249e9  xor     r8d, r8d
0x1800249ec  mov     rdx, rdi
0x1800249ef  lea     rcx, [rsp+188h+Src]
0x1800249f7  call    ?_Change_array@?$vector@HV?$allocator@H@std@@@std@@AEAAXQEAH_K1@Z; std::vector<int>::_Change_array(int * const,unsigned __int64,unsigned __int64)
0x1800249fc  mov     ebx, r15d
0x1800249ff  lea     rdi, off_1802DE930
0x180024a06  cmp     ebx, r13d
0x180024a09  jge     loc_180024B5D
0x180024a0f  movsxd  rcx, ebx
0x180024a12  mov     rax, [rsi+20h]
0x180024a16  mov     rcx, [rax+rcx*8+8]
0x180024a1b  lea     rdx, ?_WstringMsg_default_instance_@UIAutomationCoreProto@@3UWstringMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::WstringMsgDefaultTypeInternal UIAutomationCoreProto::_WstringMsg_default_instance_
0x180024a22  cmp     [rcx+10h], r15
0x180024a26  cmovnz  rdx, [rcx+10h]
0x180024a2b  lea     rcx, [rsp+188h+lpsz]
0x180024a33  call    ?GetWstring@ProtobufHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVWstringMsg@UIAutomationCoreProto@@@Z; ProtobufHelper::GetWstring(UIAutomationCoreProto::WstringMsg const &)
0x180024a38  nop
0x180024a39  xorps   xmm0, xmm0
0x180024a3c  movups  xmmword ptr [rsp+188h+iid.Data1], xmm0
0x180024a44  lea     rcx, [rsp+188h+lpsz]
0x180024a4c  cmp     [rsp+188h+var_70], 7
0x180024a55  cmova   rcx, [rsp+188h+lpsz]; lpsz
0x180024a5e  lea     rdx, [rsp+188h+iid]; lpiid
0x180024a66  call    cs:__imp_IIDFromString
0x180024a6c  mov     rcx, [rsp+188h]; this
0x180024a74  test    eax, eax
0x180024a76  jns     short loc_180024A8C
0x180024a78  mov     r9d, eax; char *
0x180024a7b  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x180024a82  mov     edx, 46h ; 'F'; void *
0x180024a87  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024a8c  movaps  xmm6, xmmword ptr [rsp+188h+iid.Data1]
0x180024a94  mov     rdx, [rsp+188h+var_70]
0x180024a9c  cmp     rdx, 7
0x180024aa0  jbe     short loc_180024ACE
0x180024aa2  lea     rdx, ds:2[rdx*2]
0x180024aaa  mov     [rsp+188h+var_118], rdx
0x180024aaf  mov     rcx, [rsp+188h+lpsz]; Block
0x180024ab7  mov     [rsp+188h+var_120], rcx
0x180024abc  cmp     rdx, 1000h
0x180024ac3  jnb     loc_180025208
0x180024ac9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024ace  movdqa  [rsp+188h+var_B8], xmm6
0x180024ad7  mov     ecx, r15d
0x180024ada  cmp     ecx, 0B0h
0x180024ae0  jge     loc_1800250FB
0x180024ae6  movsxd  rdx, ecx
0x180024ae9  shl     rdx, 6
0x180024aed  add     rdx, rdi
0x180024af0  mov     r8, [rdx]
0x180024af3  mov     rax, [r8]
0x180024af6  sub     rax, qword ptr [rsp+188h+var_B8]
0x180024afe  jnz     short loc_180024B0C
0x180024b00  mov     rax, [r8+8]
0x180024b04  sub     rax, qword ptr [rsp+188h+var_B8+8]
0x180024b0c  test    rax, rax
0x180024b0f  jz      short loc_180024B15
0x180024b11  inc     ecx
0x180024b13  jmp     short loc_180024ADA
0x180024b15  test    rdx, rdx
0x180024b18  jz      loc_1800250F3
0x180024b1e  mov     eax, [rdx+8]
0x180024b21  mov     dword ptr [rsp+188h+var_120], eax
0x180024b25  mov     rdx, [rsp+188h+Src+8]
0x180024b2d  cmp     rdx, [rsp+188h+var_C8]
0x180024b35  jz      short loc_180024B49
0x180024b37  mov     [rdx], eax
0x180024b39  add     [rsp+188h+Src+8], 4
0x180024b42  inc     ebx
0x180024b44  jmp     loc_180024A06
0x180024b49  lea     r8, [rsp+188h+var_120]
0x180024b4e  lea     rcx, [rsp+188h+Src]
0x180024b56  call    ??$_Emplace_reallocate@AEAUOperandId@instructions@uiacore@@@?$vector@UOperandId@instructions@uiacore@@V?$allocator@UOperandId@instructions@uiacore@@@std@@@std@@AEAAPEAUOperandId@instructions@uiacore@@QEAU234@AEAU234@@Z; std::vector<uiacore::instructions::OperandId>::_Emplace_reallocate<uiacore::instructions::OperandId &>(uiacore::instructions::OperandId * const,uiacore::instructions::OperandId &)
0x180024b5b  jmp     short loc_180024B42
0x180024b5d  mov     dword ptr [rsp+188h+var_120], r15d
0x180024b62  mov     [rsp+188h+iid.Data1], r15d
0x180024b6a  mov     eax, 18h
0x180024b6f  mul     r13
0x180024b72  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180024b79  cmovb   rax, rcx
0x180024b7d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024b84  mov     rcx, rax; unsigned __int64
0x180024b87  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180024b8c  mov     r15, rax
0x180024b8f  mov     qword ptr [rsp+188h+iid.Data4], rax
0x180024b97  test    rax, rax
0x180024b9a  jz      loc_180025089
0x180024ba0  xor     edi, edi
0x180024ba2  test    r13d, r13d
0x180024ba5  jz      short loc_180024BC7
0x180024ba7  lea     rcx, [rdi+rdi*2]
0x180024bab  lea     rbx, [r15+rcx*8]
0x180024baf  mov     rcx, rbx; pvarg
0x180024bb2  call    cs:__imp_VariantInit
0x180024bb8  mov     qword ptr [rbx+8], 0
0x180024bc0  inc     edi
0x180024bc2  cmp     edi, r13d
0x180024bc5  jb      short loc_180024BA7
0x180024bc7  mov     eax, r13d
0x180024bca  mov     dword ptr [rsp+188h+var_120], eax
0x180024bce  mov     [rsp+188h+iid.Data1], eax
0x180024bd5  xor     ebx, ebx
0x180024bd7  mov     rcx, [rsp+188h]; this
0x180024bdf  test    ebx, ebx
0x180024be1  jns     short loc_180024C04
0x180024be3  mov     r9d, ebx; char *
0x180024be6  lea     r8, aOnecoreWindows_95; "onecore\\windows\\accessibletech\\uiaut"...
0x180024bed  mov     edx, 307h; void *
0x180024bf2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024bf8  lea     rsi, ?_GetPropertiesAndPatternsRequestMsg_default_instance_@UIAutomationCoreProto@@3UGetPropertiesAndPatternsRequestMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::GetPropertiesAndPatternsRequestMsgDefaultTypeInternal UIAutomationCoreProto::_GetPropertiesAndPatternsRequestMsg_default_instance_
0x180024bff  jmp     loc_18002496B
0x180024c04  mov     rax, [rsp+188h+var_138]
0x180024c09  add     rax, 58h ; 'X'
0x180024c0d  mov     qword ptr [rsp+188h+var_B8], rax
0x180024c15  mov     [rax], r12
0x180024c18  movsxd  r12, dword ptr [rsi+30h]
0x180024c1c  xorps   xmm0, xmm0
0x180024c1f  movdqu  xmmword ptr [rsp+188h+var_108], xmm0
0x180024c28  mov     [rsp+188h+var_F8], 0
0x180024c34  mov     rbx, r12
0x180024c37  test    r12d, r12d
0x180024c3a  jz      short loc_180024C89
0x180024c3c  cmp     rbx, r14
0x180024c3f  ja      loc_180025226
0x180024c45  mov     rcx, rbx
0x180024c48  call    ??$_Get_size_of_n@$03@std@@YA_K_K@Z; std::_Get_size_of_n<4>(unsigned __int64)
0x180024c4d  mov     rcx, rax
0x180024c50  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180024c55  mov     rdi, rax
0x180024c58  mov     rdx, [rsp+188h+var_108]; Src
0x180024c60  mov     r8, [rsp+188h+var_108+8]
0x180024c68  sub     r8, rdx; Size
0x180024c6b  mov     rcx, rax; void *
0x180024c6e  call    memmove_0
0x180024c73  mov     r9, rbx
0x180024c76  xor     r8d, r8d
0x180024c79  mov     rdx, rdi
0x180024c7c  lea     rcx, [rsp+188h+var_108]
0x180024c84  call    ?_Change_array@?$vector@HV?$allocator@H@std@@@std@@AEAAXQEAH_K1@Z; std::vector<int>::_Change_array(int * const,unsigned __int64,unsigned __int64)
0x180024c89  xor     r14d, r14d
0x180024c8c  mov     ebx, r14d
0x180024c8f  cmp     ebx, r12d
0x180024c92  jl      loc_180025047
0x180024c98  mov     rbx, [rsp+188h+var_138]
0x180024c9d  add     rbx, 30h ; '0'
0x180024ca1  mov     [rsp+188h+var_118], rbx
0x180024ca6  mov     [rsp+188h+psa], r14
0x180024cab  mov     rax, [rsp+188h+var_108]
0x180024cb3  lea     rcx, [rsp+188h+psa]
0x180024cb8  mov     [rsp+188h+var_148], rcx; struct tagSAFEARRAY **
0x180024cbd  mov     [rsp+188h+var_150], rax; int *
0x180024cc2  mov     [rsp+188h+var_158], r12d; unsigned int
0x180024cc7  mov     [rsp+188h+var_160], r15; struct tagVARIANT *
0x180024ccc  mov     eax, [rsp+188h+var_F0]
0x180024cd3  mov     dword ptr [rsp+188h+var_168], eax; int
0x180024cd7  mov     r9, [rsp+188h+Src]; int *
0x180024cdf  mov     r8d, r13d; unsigned int
0x180024ce2  xor     edx, edx; bool
0x180024ce4  mov     rcx, rbx; this
0x180024ce7  call    ?CrossProcess_GetPropertiesAndPatterns@UiaNode@@UEAAJ_NIPEBHHPEAUtagVARIANT@@I1PEAPEAUtagSAFEARRAY@@@Z; UiaNode::CrossProcess_GetPropertiesAndPatterns(bool,uint,int const *,int,tagVARIANT *,uint,int const *,tagSAFEARRAY * *)
0x180024cec  mov     rcx, [rsp+188h]; this
0x180024cf4  test    eax, eax
0x180024cf6  jns     short loc_180024D0C
0x180024cf8  mov     r9d, eax; char *
0x180024cfb  lea     r8, aOnecoreWindows_95; "onecore\\windows\\accessibletech\\uiaut"...
0x180024d02  mov     edx, 31Dh; void *
0x180024d07  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024d0c  mov     rcx, [rsp+188h+var_98]; this
0x180024d14  call    ?_internal_mutable_get_properties_and_patterns_response@ElementMethodResponseMsg@UIAutomationCoreProto@@AEAAPEAVGetPropertiesAndPatternsResponseMsg@2@XZ; UIAutomationCoreProto::ElementMethodResponseMsg::_internal_mutable_get_properties_and_patterns_response(void)
0x180024d19  mov     r13, rax
0x180024d1c  mov     edi, r14d
0x180024d1f  cmp     edi, [rsp+188h+var_130]
0x180024d23  jnb     loc_180024E23
0x180024d29  mov     rcx, [r13+20h]
0x180024d2d  test    rcx, rcx
0x180024d30  jz      short loc_180024D3E
0x180024d32  movsxd  rdx, dword ptr [r13+18h]
0x180024d36  cmp     edx, [rcx]
0x180024d38  jl      loc_180025234
0x180024d3e  mov     rcx, [r13+10h]
0x180024d42  call    ??$CreateMaybeMessage@VVariantObjectMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVVariantObjectMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::VariantObjectMsg,>(google::protobuf::Arena *)
0x180024d47  mov     rdx, rax; void *
0x180024d4a  lea     rcx, [r13+10h]; this
0x180024d4e  call    ?AddOutOfLineHelper@RepeatedPtrFieldBase@internal@protobuf@google@@AEAAPEAXPEAX@Z; google::protobuf::internal::RepeatedPtrFieldBase::AddOutOfLineHelper(void *)
0x180024d53  mov     r14, rax
0x180024d56  mov     ecx, edi
0x180024d58  mov     rax, [rsp+188h+Src]
0x180024d60  mov     esi, [rax+rcx*4]
0x180024d63  lea     rax, [rcx+rcx*2]
0x180024d67  movups  xmm6, xmmword ptr [r15+rax*8]
0x180024d6c  movsd   xmm7, qword ptr [r15+rax*8+10h]
0x180024d73  mov     byte ptr [rsp+188h+var_F0+4], 0
0x180024d7b  lea     rcx, ?_schemaLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180024d82  call    cs:__imp_EnterCriticalSection
0x180024d88  lea     eax, [rsi-7530h]
0x180024d8e  cmp     eax, 0AFh
0x180024d93  ja      loc_180025135
0x180024d99  mov     ebx, eax
0x180024d9b  shl     rbx, 6
0x180024d9f  lea     rax, off_1802DE930
0x180024da6  add     rbx, rax
0x180024da9  lea     rcx, ?_schemaLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180024db0  call    cs:__imp_LeaveCriticalSection
0x180024db6  test    rbx, rbx
0x180024db9  jz      short loc_180024DC7
0x180024dbb  mov     rax, [rbx+34h]
0x180024dbf  mov     qword ptr [rsp+188h+var_F0], rax
0x180024dc7  movaps  xmmword ptr [rsp+188h+lpsz], xmm6
0x180024dcf  movsd   [rsp+188h+var_78], xmm7
0x180024dd8  mov     byte ptr [rsp+188h+var_148], 1; char
0x180024ddd  mov     rax, [rsp+188h+var_128]
0x180024de2  mov     [rsp+188h+var_150], rax; __int64
0x180024de7  mov     qword ptr [rsp+188h+var_158], rax; __int64
0x180024dec  mov     [rsp+188h+var_160], 0; __int64
0x180024df5  mov     [rsp+188h+var_168], 0; __int64
0x180024dfe  lea     r9, [rsp+188h+var_F0]
0x180024e06  xor     r8d, r8d
0x180024e09  lea     rdx, [rsp+188h+lpsz]
0x180024e11  mov     rcx, r14; this
0x180024e14  call    ?WriteObjInternal@ProtobufHelper@@CAXAEAVVariantObjectMsg@UIAutomationCoreProto@@UtagVARIANT@@HAEBV?$optional@W4AutomationIdentifierType@@@std@@PEAU?$BasicArrayPair@H@@PEAUITargetContextInvoker@@PEAVIServerConnection@@PEAVIConnectionBase@@_N@Z; ProtobufHelper::WriteObjInternal(UIAutomationCoreProto::VariantObjectMsg &,tagVARIANT,int,std::optional<AutomationIdentifierType> const &,BasicArrayPair<int> *,ITargetContextInvoker *,IServerConnection *,IConnectionBase *,bool)
0x180024e19  inc     edi
0x180024e1b  xor     r14d, r14d
0x180024e1e  jmp     loc_180024D1F
0x180024e23  mov     [rsp+188h+var_E8], r14d
0x180024e2b  mov     [rsp+188h+Block], r14
0x180024e33  neg     [rsp+188h+var_138]
0x180024e38  sbb     rcx, rcx
0x180024e3b  and     rcx, [rsp+188h+var_118]
0x180024e40  lea     rdx, [rsp+188h+var_E8]
0x180024e48  call    ?GetRuntimeId@@YAJPEAVIUiaNode@@PEAU?$BasicArrayPair@H@@@Z; GetRuntimeId(IUiaNode *,BasicArrayPair<int> *)
0x180024e4d  mov     rcx, [rsp+188h]; this
0x180024e55  test    eax, eax
0x180024e57  jns     short loc_180024E6D
0x180024e59  mov     r9d, eax; char *
0x180024e5c  lea     r8, aOnecoreWindows_95; "onecore\\windows\\accessibletech\\uiaut"...
0x180024e63  mov     edx, 327h; void *
0x180024e68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024e6d  mov     rcx, [rsp+188h+psa]
0x180024e72  test    rcx, rcx
0x180024e75  jz      short loc_180024EC7
0x180024e77  mov     rdx, rcx
0x180024e7a  lea     rcx, [rsp+188h+lpsz]
0x180024e82  call    ??0?$SafeArrayAccessor@PEAUIUnknown@@@@QEAA@PEAUtagSAFEARRAY@@G@Z; SafeArrayAccessor<IUnknown *>::SafeArrayAccessor<IUnknown *>(tagSAFEARRAY *,ushort)
0x180024e87  nop
0x180024e88  cmp     dword ptr [rsp+188h+lpsz+8], r12d
  ... truncated ...
```
