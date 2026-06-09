# LocalUiaNodeProxy::RealCrossProcess_GetPropertiesAndPatterns(uint,int const *,int,tagVARIANT *,uint,int const *,tagSAFEARRAY * *)

- ea: `0x18001d4bc`
- end: `0x18001df7a`
- name: `?RealCrossProcess_GetPropertiesAndPatterns@LocalUiaNodeProxy@@AEAAJIPEBHHPEAUtagVARIANT@@I0PEAPEAUtagSAFEARRAY@@@Z`
- size: `2750`
- prototype: `int(LocalUiaNodeProxy *__hidden this, unsigned int, const int *, int, struct tagVARIANT *, unsigned int, const int *, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cd90`

## callees

- `0x180014d0c`
- `0x18001c498`
- `0x18001ce34`
- `0x18001d03c`
- `0x18001d324`
- `0x18001d350`
- `0x18001d3ac`
- `0x18001d4bc`
- `0x18001f29c`
- `0x18001f2e4`
- `0x180020cf0`
- `0x180021100`
- `0x180022248`
- `0x180026efc`
- `0x1800275b4`
- `0x180032724`
- `0x180033e04`
- `0x180048a3c`
- `0x180050944`
- `0x1800546ac`
- `0x1800be9c8`
- `0x1800beb48`
- `0x1800d5fac`
- `0x1800d6c88`
- `0x1800d6ee0`
- `0x1800f05c4`
- `0x18012e294`
- `0x1801390ec`
- `0x180195464`
- `0x1801b78fc`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e9240`
- `0x1801ec660`
- `0x1801ec680`
- `0x1802dd010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001df4e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001df4e`
- `OLEAUT32!__imp_VariantInit` at `0x18001d552`
- `OLEAUT32!__imp_VariantInit` at `0x18001d999`
- `OLEAUT32!__imp_VariantInit` at `0x18001da9e`
- `OLEAUT32!__imp_VariantInit` at `0x18001db43`
- `OLEAUT32!__imp_VariantInit` at `0x18001dc73`
- `OLEAUT32!__imp_VariantInit` at `0x18001d552`
- `OLEAUT32!__imp_VariantInit` at `0x18001d999`
- `OLEAUT32!__imp_VariantInit` at `0x18001da9e`
- `OLEAUT32!__imp_VariantInit` at `0x18001db43`
- `OLEAUT32!__imp_VariantInit` at `0x18001dc73`
- `OLEAUT32!__imp_VariantClear` at `0x18001daf1`
- `OLEAUT32!__imp_VariantClear` at `0x18001daf1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001db95`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001db95`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x18001d5cd`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x18001d5cd`

## string_xrefs

- `0x18001d698`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x18001d713`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x18001d8ec`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x18001d8b3`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x18001dc1e`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x18001dcdf`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x18001ddd4`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x18001de2c`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x18001de47`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x18001de92`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall LocalUiaNodeProxy::RealCrossProcess_GetPropertiesAndPatterns(
        LocalUiaNodeProxy *this,
        int a2,
        const int *a3,
        int a4,
        struct tagVARIANT *a5,
        unsigned int a6,
        const int *a7,
        struct tagSAFEARRAY **a8)
{
  const int *v9; // r12
  unsigned int v10; // r14d
  SAFEARRAY *v12; // rdx
  unsigned int v13; // r13d
  unsigned int i; // ebx
  char v15; // al
  struct UIAutomationCoreProto::ElementMethodRequestMsg *v16; // rax
  struct UIAutomationCoreProto::GetPropertiesAndPatternsRequestMsg *properties_and_patterns_request; // rsi
  _DWORD *v18; // rcx
  __int64 v19; // rdx
  void *v20; // rax
  _QWORD *v21; // rdi
  int v22; // edx
  GUID **v23; // rax
  char v24; // cl
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned int v27; // ebx
  unsigned __int64 v28; // rax
  const char *v29; // r9
  void **v30; // r12
  __int64 v31; // rsi
  _QWORD *v32; // rcx
  unsigned __int64 v33; // rax
  unsigned int v34; // edx
  const char *v35; // r9
  _QWORD *v36; // rdi
  size_t v37; // rbx
  __int64 v38; // rdx
  void *v39; // rcx
  void *v40; // rcx
  __int64 v41; // rbx
  const int *v42; // r12
  LocalUiaNodeProxy *v43; // r15
  __int64 v44; // rdi
  int v45; // eax
  unsigned int v46; // eax
  struct UIAutomationCoreProto::GuidMsg *v47; // rax
  char v48; // al
  _QWORD *v49; // rax
  _QWORD *v50; // rbx
  unsigned int v51; // r12d
  unsigned __int64 v52; // rsi
  int v53; // eax
  VARIANTARG *v54; // rbx
  signed __int64 v55; // r15
  unsigned __int64 v56; // r13
  unsigned __int64 v57; // r8
  __int64 size_of; // rax
  __int64 v59; // r14
  __int64 v60; // r15
  VARIANTARG *v61; // rcx
  unsigned int v62; // esi
  SAFEARRAY *v63; // r15
  VARIANTARG *v64; // rcx
  __int128 v65; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  SAFEARRAY **v67; // rax
  SAFEARRAY *v68; // rcx
  const char *v69; // r9
  __int64 result; // rax
  unsigned int v71; // esi
  const int *v72; // r12
  __int64 v73; // rcx
  int v74; // eax
  char *v75; // rbx
  const struct PatternInfo *PatternInfo; // rdx
  int (__fastcall **v77)(char *, char *, struct UIAutomationCoreProto::GetPropertiesAndPatternsRequestMsg **); // rax
  char v78; // cl
  const int **v79; // rax
  const int *v80; // rcx
  struct UserDefinedPropertyInfo *j; // rax
  __int64 v82; // r15
  void *v83; // r14
  int v84; // [rsp+20h] [rbp-168h]
  void *v85; // [rsp+28h] [rbp-160h] BYREF
  unsigned __int64 v86; // [rsp+30h] [rbp-158h] BYREF
  struct UIAutomationCoreProto::GetPropertiesAndPatternsRequestMsg *v87; // [rsp+38h] [rbp-150h] BYREF
  const int *v88; // [rsp+40h] [rbp-148h] BYREF
  const int *v89; // [rsp+48h] [rbp-140h] BYREF
  SAFEARRAY *psa; // [rsp+50h] [rbp-138h] BYREF
  VARIANTARG *pvarg[2]; // [rsp+58h] [rbp-130h] BYREF
  VARIANTARG *v92; // [rsp+68h] [rbp-120h]
  LocalUiaNodeProxy *v93; // [rsp+70h] [rbp-118h]
  __int128 v94; // [rsp+78h] [rbp-110h] BYREF
  __int64 v95; // [rsp+88h] [rbp-100h]
  struct tagSAFEARRAY **v96; // [rsp+90h] [rbp-F8h]
  __int64 v97; // [rsp+98h] [rbp-F0h]
  void *Block[2]; // [rsp+A0h] [rbp-E8h] BYREF
  __int128 v99; // [rsp+B0h] [rbp-D8h]
  _QWORD v100[2]; // [rsp+C0h] [rbp-C8h] BYREF
  int v101; // [rsp+D0h] [rbp-B8h]
  _DWORD *v102; // [rsp+D8h] [rbp-B0h]
  __int64 v103; // [rsp+E0h] [rbp-A8h]
  void *Src[2]; // [rsp+E8h] [rbp-A0h] BYREF
  __int64 v105; // [rsp+F8h] [rbp-90h]
  unsigned __int64 v106; // [rsp+100h] [rbp-88h]
  _QWORD v107[5]; // [rsp+108h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v9 = a3;
  v88 = a3;
  v10 = a2;
  v84 = a2;
  v93 = this;
  v12 = (SAFEARRAY *)a5;
  psa = (SAFEARRAY *)a5;
  v89 = a7;
  v96 = a8;
  v13 = 0;
  if ( a8 )
    *a8 = 0;
  for ( i = 0; i < v10; v12 = psa )
    VariantInit((VARIANTARG *)v12 + i++);
  v15 = (***((__int64 (__fastcall ****)(_QWORD, __int64))this + 5))(*((_QWORD *)this + 5), 4);
  try
  {
    if ( !v15 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x67F,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
        (const char *)0x80004001LL,
        v84);
    v107[1] = 0;
    v107[4] = 0;
    v107[2] = 0;
    v107[0] = &UIAutomationCoreProto::UiaCoreRequestMsg::`vftable';
    v16 = UIAutomationCoreProto::UiaCoreRequestMsg::_internal_mutable_element_method_request((UIAutomationCoreProto::UiaCoreRequestMsg *)v107);
    *((_DWORD *)v16 + 4) = *((_DWORD *)this + 8);
    properties_and_patterns_request = UIAutomationCoreProto::ElementMethodRequestMsg::_internal_mutable_get_properties_and_patterns_request(v16);
    v87 = properties_and_patterns_request;
    *((_QWORD *)properties_and_patterns_request + 8) = GetThreadDpiAwarenessContext();
    *((_BYTE *)properties_and_patterns_request + 72) = a4 != 0;
    while ( 1 )
    {
      if ( v13 >= v10 )
      {
        v41 = 0;
        v42 = v89;
        while ( (unsigned int)v41 < a6 )
        {
          v47 = (struct UIAutomationCoreProto::GuidMsg *)google::protobuf::internal::RepeatedPtrFieldBase::Add<google::protobuf::RepeatedPtrField<UIAutomationCoreProto::GuidMsg>::TypeHandler>((struct UIAutomationCoreProto::GetPropertiesAndPatternsRequestMsg *)((char *)properties_and_patterns_request + 40));
          ProtobufHelper::WriteAutomationId(v47, v42[v41], AutomationIdentifierType_Pattern);
          v41 = (unsigned int)(v41 + 1);
        }
        v100[1] = 0;
        v103 = 0;
        v101 = 0;
        v100[0] = &UIAutomationCoreProto::UiaCoreResponseMsg::`vftable';
        v43 = v93;
        v44 = *((_QWORD *)v93 + 5);
        v97 = v44;
        if ( v44 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
        v45 = DoCallWithReturn(
                *((struct IClientConnection **)v43 + 5),
                (struct UIAutomationCoreProto::UiaCoreRequestMsg *)v107,
                (struct UIAutomationCoreProto::UiaCoreResponseMsg *)v100,
                0);
        if ( v45 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x69E,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
            (const char *)(unsigned int)v45,
            v84);
        if ( HIDWORD(v103) != 12 || (v48 = 0, v102[7] != 36) )
          v48 = 1;
        if ( v48 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6A1,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
            (const char *)0x80040801LL,
            v84);
        v49 = &UIAutomationCoreProto::_ElementMethodResponseMsg_default_instance_;
        if ( HIDWORD(v103) == 12 )
          v49 = v102;
        if ( *((_DWORD *)v49 + 7) == 36 )
          v50 = (_QWORD *)v49[2];
        else
          v50 = &UIAutomationCoreProto::_GetPropertiesAndPatternsResponseMsg_default_instance_;
        v86 = (unsigned __int64)v50;
        *(_OWORD *)pvarg = 0;
        v92 = 0;
        v51 = 0;
        v52 = 0xAAAAAAAAAAAAAAALL;
        while ( v51 < v10 )
        {
          VariantInit((VARIANTARG *)Block);
          ProtobufHelper::GetObj(
            *(const struct UIAutomationCoreProto::VariantObjectMsg **)(v50[4] + 8LL * (int)v51 + 8),
            (struct tagVARIANT *)Block,
            *((struct IClientConnection **)v43 + 5));
          v53 = UiaUtils::AdaptPropertyValueCoordinatesIfNeeded(
                  (VARIANTARG *)Block,
                  v88[v51],
                  *((struct IClientConnection **)v43 + 5));
          if ( v53 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x6AB,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
              (const char *)(unsigned int)v53,
              v84);
          v54 = pvarg[1];
          if ( pvarg[1] == v92 )
          {
            v55 = pvarg[1] - pvarg[0];
            if ( v55 == 0xAAAAAAAAAAAAAAALL )
              std::_Xlength_error("vector too long");
            v56 = v55 + 1;
            v57 = 0xAAAAAAAAAAAAAAABuLL * (((char *)v92 - (char *)pvarg[0]) >> 3);
            if ( v57 <= 0xAAAAAAAAAAAAAAALL - (v57 >> 1) )
            {
              v52 = (v57 >> 1) - 0x5555555555555555LL * (((char *)v92 - (char *)pvarg[0]) >> 3);
              if ( v52 < v56 )
                v52 = v55 + 1;
            }
            size_of = std::_Get_size_of_n<24>(v52);
            v59 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
            v60 = 3 * v55;
            *(_OWORD *)(v59 + 8 * v60) = *(_OWORD *)Block;
            *(_QWORD *)(v59 + 8 * v60 + 16) = v99;
            VariantInit((VARIANTARG *)Block);
            v61 = pvarg[0];
            if ( v54 != pvarg[1] )
            {
              std::_Uninitialized_move<wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)> *,std::allocator<wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>(pvarg[0]);
              v61 = v54;
            }
            std::_Uninitialized_move<wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)> *,std::allocator<wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>(v61);
            std::vector<wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>::_Change_array(
              pvarg,
              v59,
              v56,
              v52);
            v10 = v84;
            v43 = v93;
            v52 = 0xAAAAAAAAAAAAAAALL;
          }
          else
          {
            *(_OWORD *)pvarg[1] = *(_OWORD *)Block;
            v54->pRecInfo = (IRecordInfo *)v99;
            VariantInit((VARIANTARG *)Block);
            ++pvarg[1];
          }
          VariantClear((VARIANTARG *)Block);
          ++v51;
          v50 = (_QWORD *)v86;
        }
        v94 = 0;
        v95 = 0;
        if ( *((int *)v50 + 12) > 0 )
        {
          if ( *((_DWORD *)v50 + 12) != a6 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x6B4,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
              (const char *)0x8000FFFFLL,
              v84);
          v71 = 0;
          v72 = v89;
          while ( v71 < a6 )
          {
            v73 = *(_QWORD *)(v50[7] + 8LL * (int)v71 + 8);
            v85 = 0;
            v74 = LocalPatternProxy::Wrap(*(unsigned int *)(v73 + 16), *((_QWORD *)v43 + 5), &v85);
            if ( v74 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6BB,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
                (const char *)(unsigned int)v74,
                v84);
            v88 = 0;
            v75 = (char *)v85;
            if ( v85 )
            {
              PatternInfo = Schema::GetPatternInfo(v72[v71]);
              if ( *((_QWORD *)PatternInfo + 8) )
              {
                v79 = (const int **)wil::com_ptr_t<LocalPatternProxy,wil::err_exception_policy>::query<IUnknown>(
                                      &v85,
                                      &v89);
                v80 = *v79;
                *v79 = 0;
                v88 = v80;
                if ( v89 )
                  (*(void (__fastcall **)(const int *))(*(_QWORD *)v89 + 16LL))(v89);
              }
              else
              {
                v87 = 0;
                v77 = (int (__fastcall **)(char *, char *, struct UIAutomationCoreProto::GetPropertiesAndPatternsRequestMsg **))*((_QWORD *)v75 + 2);
                v87 = 0;
                if ( (*v77)(v75 + 16, (char *)PatternInfo + 24, &v87) < 0 || (v78 = 0, !v87) )
                  v78 = 1;
                if ( v78 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x6CB,
                    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
                    (const char *)0x80004002LL,
                    v84);
                v88 = (const int *)v87;
              }
            }
            std::vector<wil::com_ptr_t<IUnknown,wil::err_exception_policy>>::_Emplace_one_at_back<wil::com_ptr_t<IUnknown,wil::err_exception_policy> &>(
              &v94,
              &v88);
            if ( v88 )
              (*(void (__fastcall **)(const int *))(*(_QWORD *)v88 + 16LL))(v88);
            if ( v75 )
              (*(void (__fastcall **)(_QWORD *))(*((_QWORD *)v75 + 2) + 16LL))((_QWORD *)v75 + 2);
            ++v71;
            v50 = (_QWORD *)v86;
          }
          v10 = v84;
        }
        v62 = 0;
        if ( v10 )
        {
          v63 = psa;
          do
          {
            v64 = &pvarg[0][v62];
            v65 = *(_OWORD *)&v64->vt;
            pRecInfo = v64->pRecInfo;
            VariantInit(v64);
            *(_OWORD *)(&v63->cDims + 12 * v62) = v65;
            *((_QWORD *)&v63->pvData + 3 * v62++) = pRecInfo;
          }
          while ( v62 < v10 );
        }
        v67 = ArrayToSafeArray_13_wil::com_ptr_t_IUnknown_wil::err_exception_policy___lambda_ec403018b2b048e9b8cca220b05cfc06___(
                &psa,
                v94,
                (__int64)(*((_QWORD *)&v94 + 1) - v94) >> 3);
        v68 = *v67;
        *v67 = 0;
        *v96 = v68;
        if ( psa )
          SafeArrayDestroy(psa);
        std::vector<wil::com_ptr_t<IUIAutomationProxyFactoryEntry,wil::err_exception_policy>>::_Tidy(&v94);
        std::vector<wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>::_Tidy(pvarg);
        if ( v44 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        UIAutomationCoreProto::UiaCoreResponseMsg::~UiaCoreResponseMsg((UIAutomationCoreProto::UiaCoreResponseMsg *)v100);
        UIAutomationCoreProto::UiaCoreRequestMsg::~UiaCoreRequestMsg((UIAutomationCoreProto::UiaCoreRequestMsg *)v107);
        return 0;
      }
      v18 = (_DWORD *)*((_QWORD *)properties_and_patterns_request + 4);
      if ( v18 && (v19 = *((int *)properties_and_patterns_request + 6), (int)v19 < *v18) )
      {
        v21 = *(_QWORD **)&v18[2 * v19 + 2];
        *((_DWORD *)properties_and_patterns_request + 6) = v19 + 1;
      }
      else
      {
        v20 = (void *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::GuidMsg,>(*((_QWORD *)properties_and_patterns_request + 2));
        v21 = google::protobuf::internal::RepeatedPtrFieldBase::AddOutOfLineHelper(
                (struct UIAutomationCoreProto::GetPropertiesAndPatternsRequestMsg *)((char *)properties_and_patterns_request
                                                                                   + 16),
                v20);
      }
      v22 = v9[v13];
      if ( (unsigned int)(v22 - 30000) > 0xAF )
        break;
      v23 = &(&off_1802DE930)[8 * (unsigned __int64)(unsigned int)(v22 - 30000)];
LABEL_14:
      if ( !v23 )
        goto LABEL_114;
      v24 = 1;
LABEL_16:
      if ( !v24 || !*v23 )
      {
        v46 = Error::InternalErrorWorker(L"unknown automation id");
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x33C,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
          (const char *)v46,
          v84);
      }
      ProtobufHelper::GuidToString(Src);
      v27 = v105;
      v28 = 2LL * (unsigned int)v105;
      v29 = v28 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0LL;
      if ( v28 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
          v29,
          v84);
      v30 = Src;
      if ( v106 > 7 )
        v30 = (void **)Src[0];
      v31 = v21[2];
      if ( !v31 )
      {
        v32 = (_QWORD *)(v21[1] & 0xFFFFFFFFFFFFFFFCuLL);
        if ( (v21[1] & 1) != 0 )
          v32 = (_QWORD *)*v32;
        v31 = google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::WstringMsg,>(v32, v25, v26, v29);
        v21[2] = v31;
      }
      v33 = 2LL * v27;
      v34 = 2 * v27;
      if ( v33 > 0xFFFFFFFF )
        v34 = -1;
      v35 = v33 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0LL;
      if ( v33 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2E,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
          v35,
          v84);
      v36 = (_QWORD *)(*(_QWORD *)(v31 + 8) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*(_BYTE *)(v31 + 8) & 1) != 0 )
        v36 = (_QWORD *)*v36;
      *(_OWORD *)Block = 0;
      v99 = 0;
      v37 = v34;
      if ( v34 > 0xF )
      {
        v82 = std::string::_Calculate_growth(v34, 15, 0x7FFFFFFFFFFFFFFFLL, v35);
        v83 = (void *)std::allocator<char>::allocate(Block, v82 + 1);
        Block[0] = v83;
        *(_QWORD *)&v99 = v37;
        *((_QWORD *)&v99 + 1) = v82;
        memcpy_0(v83, v30, v37);
        *((_BYTE *)v83 + v37) = 0;
        v10 = v84;
      }
      else
      {
        v99 = v34;
        memcpy_0(Block, v30, v34);
        *((_BYTE *)Block + v37) = 0;
      }
      LOBYTE(v38) = 0;
      google::protobuf::internal::ArenaStringPtr::Set(v31 + 16, v38, Block, v36);
      if ( *((_QWORD *)&v99 + 1) > 0xFu )
      {
        v86 = *((_QWORD *)&v99 + 1) + 1LL;
        v39 = Block[0];
        v85 = Block[0];
        if ( (unsigned __int64)(*((_QWORD *)&v99 + 1) + 1LL) >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v85, &v86);
          v39 = v85;
        }
        operator delete(v39);
      }
      if ( v106 > 7 )
      {
        v86 = 2 * v106 + 2;
        v40 = Src[0];
        v85 = Src[0];
        if ( v86 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v85, &v86);
          v40 = v85;
        }
        operator delete(v40);
      }
      ++v13;
      properties_and_patterns_request = v87;
      v9 = v88;
    }
    for ( j = g_pUserDefinedProperties; j; j = *(struct UserDefinedPropertyInfo **)j )
    {
      if ( *((_DWORD *)j + 6) == v22 )
      {
        v23 = (GUID **)((char *)j + 16);
        goto LABEL_14;
      }
    }
LABEL_114:
    v24 = 0;
    v23 = (GUID **)v94;
    goto LABEL_16;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6E3,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
                           v69);
  }
  return result;
}

```

## disassembly

```asm
0x18001d4bc  mov     rax, rsp
0x18001d4bf  mov     [rax+10h], rbx
0x18001d4c3  mov     [rax+20h], rsi
0x18001d4c7  push    rdi
0x18001d4c8  push    r12
0x18001d4ca  push    r13
0x18001d4cc  push    r14
0x18001d4ce  push    r15
0x18001d4d0  sub     rsp, 160h
0x18001d4d7  movaps  xmmword ptr [rax-38h], xmm6
0x18001d4db  movaps  xmmword ptr [rax-48h], xmm7
0x18001d4df  mov     rax, cs:__security_cookie
0x18001d4e6  xor     rax, rsp
0x18001d4e9  mov     [rsp+188h+var_58], rax
0x18001d4f1  mov     edi, r9d
0x18001d4f4  mov     r12, r8
0x18001d4f7  mov     [rsp+188h+var_148], r8
0x18001d4fc  mov     r14d, edx
0x18001d4ff  mov     [rsp+188h+var_168], edx; int
0x18001d503  mov     r15, rcx
0x18001d506  mov     [rsp+188h+var_118], rcx
0x18001d50b  mov     rdx, [rsp+188h+arg_20]
0x18001d513  mov     [rsp+188h+psa], rdx
0x18001d518  mov     rax, [rsp+188h+arg_30]
0x18001d520  mov     [rsp+188h+var_140], rax
0x18001d525  mov     rax, [rsp+188h+arg_38]
0x18001d52d  mov     [rsp+188h+var_F8], rax
0x18001d535  xor     r13d, r13d
0x18001d538  test    rax, rax
0x18001d53b  jz      short loc_18001D540
0x18001d53d  mov     [rax], r13
0x18001d540  mov     ebx, r13d
0x18001d543  test    r14d, r14d
0x18001d546  jz      short loc_18001D564
0x18001d548  mov     eax, ebx
0x18001d54a  lea     rcx, [rax+rax*2]
0x18001d54e  lea     rcx, [rdx+rcx*8]; pvarg
0x18001d552  call    cs:__imp_VariantInit
0x18001d558  inc     ebx
0x18001d55a  cmp     ebx, r14d
0x18001d55d  mov     rdx, [rsp+188h+psa]
0x18001d562  jb      short loc_18001D548
0x18001d564  mov     rcx, [r15+28h]
0x18001d568  mov     rax, [rcx]
0x18001d56b  mov     edx, 4
0x18001d570  mov     rax, [rax]
0x18001d573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d578  test    al, al
0x18001d57a  jz      loc_18001DE84
0x18001d580  mov     [rsp+188h+var_78], r13
0x18001d588  mov     [rsp+188h+var_60], r13
0x18001d590  xor     eax, eax
0x18001d592  mov     [rsp+188h+var_70], rax
0x18001d59a  lea     rax, ??_7UiaCoreRequestMsg@UIAutomationCoreProto@@6B@; const UIAutomationCoreProto::UiaCoreRequestMsg::`vftable'
0x18001d5a1  mov     [rsp+188h+var_80], rax
0x18001d5a9  lea     rcx, [rsp+188h+var_80]; this
0x18001d5b1  call    ?_internal_mutable_element_method_request@UiaCoreRequestMsg@UIAutomationCoreProto@@AEAAPEAVElementMethodRequestMsg@2@XZ; UIAutomationCoreProto::UiaCoreRequestMsg::_internal_mutable_element_method_request(void)
0x18001d5b6  mov     ecx, [r15+20h]
0x18001d5ba  mov     [rax+10h], ecx
0x18001d5bd  mov     rcx, rax; this
0x18001d5c0  call    ?_internal_mutable_get_properties_and_patterns_request@ElementMethodRequestMsg@UIAutomationCoreProto@@AEAAPEAVGetPropertiesAndPatternsRequestMsg@2@XZ; UIAutomationCoreProto::ElementMethodRequestMsg::_internal_mutable_get_properties_and_patterns_request(void)
0x18001d5c5  mov     rsi, rax
0x18001d5c8  mov     [rsp+188h+var_150], rax
0x18001d5cd  call    cs:__imp_GetThreadDpiAwarenessContext
0x18001d5d3  mov     [rsi+40h], rax
0x18001d5d7  test    edi, edi
0x18001d5d9  setnz   cl
0x18001d5dc  mov     [rsi+48h], cl
0x18001d5df  mov     r15d, 0FFFFFFFFh
0x18001d5e5  cmp     r13d, r14d
0x18001d5e8  jnb     loc_18001D820
0x18001d5ee  mov     rcx, [rsi+20h]
0x18001d5f2  test    rcx, rcx
0x18001d5f5  jz      short loc_18001D603
0x18001d5f7  movsxd  rdx, dword ptr [rsi+18h]
0x18001d5fb  cmp     edx, [rcx]
0x18001d5fd  jl      loc_18001D8C5
0x18001d603  mov     rcx, [rsi+10h]
0x18001d607  call    ??$CreateMaybeMessage@VGuidMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVGuidMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::GuidMsg,>(google::protobuf::Arena *)
0x18001d60c  mov     rdx, rax; void *
0x18001d60f  lea     rcx, [rsi+10h]; this
0x18001d613  call    ?AddOutOfLineHelper@RepeatedPtrFieldBase@internal@protobuf@google@@AEAAPEAXPEAX@Z; google::protobuf::internal::RepeatedPtrFieldBase::AddOutOfLineHelper(void *)
0x18001d618  mov     rdi, rax
0x18001d61b  mov     ecx, r13d
0x18001d61e  mov     edx, [r12+rcx*4]
0x18001d622  lea     ecx, [rdx-7530h]
0x18001d628  cmp     ecx, 0AFh
0x18001d62e  ja      loc_18001DE59
0x18001d634  mov     eax, ecx
0x18001d636  shl     rax, 6
0x18001d63a  lea     rcx, off_1802DE930
0x18001d641  add     rax, rcx
0x18001d644  test    rax, rax
0x18001d647  jz      loc_18001DE78
0x18001d64d  mov     cl, 1
0x18001d64f  test    cl, cl
0x18001d651  jz      loc_18001D8D5
0x18001d657  mov     rdx, [rax]
0x18001d65a  test    rdx, rdx
0x18001d65d  jz      loc_18001D8D5
0x18001d663  lea     rcx, [rsp+188h+Src]
0x18001d66b  call    ?GuidToString@ProtobufHelper@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; ProtobufHelper::GuidToString(_GUID const &)
0x18001d670  nop
0x18001d671  mov     rbx, [rsp+188h+var_90]
0x18001d679  mov     eax, ebx
0x18001d67b  add     rax, rax
0x18001d67e  cmp     r15, rax
0x18001d681  sbb     r9d, r9d
0x18001d684  and     r9d, 80070216h; char *
0x18001d68b  mov     rcx, [rsp+188h]; this
0x18001d693  cmp     rax, r15
0x18001d696  jbe     short loc_18001D6A9
0x18001d698  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x18001d69f  mov     edx, 4Eh ; 'N'; void *
0x18001d6a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001d6a9  lea     r12, [rsp+188h+Src]
0x18001d6b1  cmp     [rsp+188h+var_88], 7
0x18001d6ba  cmova   r12, [rsp+188h+Src]
0x18001d6c3  mov     rsi, [rdi+10h]
0x18001d6c7  test    rsi, rsi
0x18001d6ca  jnz     short loc_18001D6EA
0x18001d6cc  mov     rcx, [rdi+8]
0x18001d6d0  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18001d6d4  test    byte ptr [rdi+8], 1
0x18001d6d8  jnz     loc_18001DDBE
0x18001d6de  call    ??$CreateMaybeMessage@VWstringMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVWstringMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::WstringMsg,>(google::protobuf::Arena *)
0x18001d6e3  mov     rsi, rax
0x18001d6e6  mov     [rdi+10h], rax
0x18001d6ea  mov     eax, ebx
0x18001d6ec  add     rax, rax
0x18001d6ef  cmp     rax, r15
0x18001d6f2  mov     edx, eax
0x18001d6f4  jbe     short loc_18001D6F9
0x18001d6f6  mov     edx, r15d
0x18001d6f9  cmp     r15, rax
0x18001d6fc  sbb     r9d, r9d
0x18001d6ff  and     r9d, 80070216h; char *
0x18001d706  mov     rcx, [rsp+188h]; this
0x18001d70e  cmp     rax, r15
0x18001d711  jbe     short loc_18001D724
0x18001d713  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x18001d71a  mov     edx, 2Eh ; '.'; void *
0x18001d71f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001d724  mov     rdi, [rsi+8]
0x18001d728  and     rdi, 0FFFFFFFFFFFFFFFCh
0x18001d72c  test    byte ptr [rsi+8], 1
0x18001d730  jnz     loc_18001DDC6
0x18001d736  xorps   xmm0, xmm0
0x18001d739  movups  xmmword ptr [rsp+188h+Block], xmm0
0x18001d741  xorps   xmm1, xmm1
0x18001d744  movdqu  [rsp+188h+var_D8], xmm1
0x18001d74d  mov     ebx, edx
0x18001d74f  mov     eax, 0Fh
0x18001d754  cmp     edx, eax
0x18001d756  ja      loc_18001DEA4
0x18001d75c  mov     qword ptr [rsp+188h+var_D8], rbx
0x18001d764  mov     qword ptr [rsp+188h+var_D8+8], rax
0x18001d76c  mov     r8d, ebx; Size
0x18001d76f  mov     rdx, r12; Src
0x18001d772  lea     rcx, [rsp+188h+Block]; void *
0x18001d77a  call    memcpy_0
0x18001d77f  mov     byte ptr [rsp+rbx+188h+Block], 0
0x18001d787  xor     dl, dl
0x18001d789  lea     rcx, [rsi+10h]
0x18001d78d  mov     r9, rdi
0x18001d790  lea     r8, [rsp+188h+Block]
0x18001d798  call    ?Set@ArenaStringPtr@internal@protobuf@google@@QEAAXUEmptyDefault@1234@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAVArena@34@@Z; google::protobuf::internal::ArenaStringPtr::Set(google::protobuf::internal::ArenaStringPtr::EmptyDefault,std::string const &,google::protobuf::Arena *)
0x18001d79d  nop
0x18001d79e  mov     rdx, qword ptr [rsp+188h+var_D8+8]
0x18001d7a6  cmp     rdx, 0Fh
0x18001d7aa  jbe     short loc_18001D7D4
0x18001d7ac  inc     rdx
0x18001d7af  mov     [rsp+188h+var_158], rdx
0x18001d7b4  mov     rcx, [rsp+188h+Block]; Block
0x18001d7bc  mov     [rsp+188h+var_160], rcx
0x18001d7c1  cmp     rdx, 1000h
0x18001d7c8  jnb     loc_18001DF0B
0x18001d7ce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d7d3  nop
0x18001d7d4  mov     rdx, [rsp+188h+var_88]
0x18001d7dc  cmp     rdx, 7
0x18001d7e0  jbe     short loc_18001D80E
0x18001d7e2  lea     rdx, ds:2[rdx*2]
0x18001d7ea  mov     [rsp+188h+var_158], rdx
0x18001d7ef  mov     rcx, [rsp+188h+Src]; Block
0x18001d7f7  mov     [rsp+188h+var_160], rcx
0x18001d7fc  cmp     rdx, 1000h
0x18001d803  jnb     loc_18001DF29
0x18001d809  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d80e  inc     r13d
0x18001d811  mov     rsi, [rsp+188h+var_150]
0x18001d816  mov     r12, [rsp+188h+var_148]
0x18001d81b  jmp     loc_18001D5E5
0x18001d820  xor     ebx, ebx
0x18001d822  mov     r13d, [rsp+188h+arg_28]
0x18001d82a  mov     r12, [rsp+188h+var_140]
0x18001d82f  cmp     ebx, r13d
0x18001d832  jb      loc_18001D8FD
0x18001d838  xor     r13d, r13d
0x18001d83b  mov     [rsp+188h+var_C0], r13
0x18001d843  mov     [rsp+188h+var_A8], r13
0x18001d84b  mov     [rsp+188h+var_B8], r13d
0x18001d853  lea     rax, ??_7UiaCoreResponseMsg@UIAutomationCoreProto@@6B@; const UIAutomationCoreProto::UiaCoreResponseMsg::`vftable'
0x18001d85a  mov     [rsp+188h+var_C8], rax
0x18001d862  mov     r15, [rsp+188h+var_118]
0x18001d867  mov     rdi, [r15+28h]
0x18001d86b  mov     [rsp+188h+var_F0], rdi
0x18001d873  test    rdi, rdi
0x18001d876  jz      short loc_18001D888
0x18001d878  mov     rax, [rdi]
0x18001d87b  mov     rcx, rdi
0x18001d87e  mov     rax, [rax+8]
0x18001d882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d887  nop
0x18001d888  xor     r9d, r9d; bool
0x18001d88b  lea     r8, [rsp+188h+var_C8]; struct UIAutomationCoreProto::UiaCoreResponseMsg *
0x18001d893  lea     rdx, [rsp+188h+var_80]; struct UIAutomationCoreProto::UiaCoreRequestMsg *
0x18001d89b  mov     rcx, [r15+28h]; struct IClientConnection *
0x18001d89f  call    ?DoCallWithReturn@@YAJPEAVIClientConnection@@AEAVUiaCoreRequestMsg@UIAutomationCoreProto@@AEAVUiaCoreResponseMsg@3@_N@Z; DoCallWithReturn(IClientConnection *,UIAutomationCoreProto::UiaCoreRequestMsg &,UIAutomationCoreProto::UiaCoreResponseMsg &,bool)
0x18001d8a4  mov     rcx, [rsp+188h]; this
0x18001d8ac  test    eax, eax
0x18001d8ae  jns     short loc_18001D91F
0x18001d8b0  mov     r9d, eax; char *
0x18001d8b3  lea     r8, aOnecoreWindows_78; "onecore\\windows\\accessibletech\\uiaut"...
0x18001d8ba  mov     edx, 69Eh; void *
0x18001d8bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001d8c5  mov     rdi, [rcx+rdx*8+8]
0x18001d8ca  lea     eax, [rdx+1]
0x18001d8cd  mov     [rsi+18h], eax
0x18001d8d0  jmp     loc_18001D61B
0x18001d8d5  lea     rcx, aUnknownAutomat; "unknown automation id"
0x18001d8dc  call    ?InternalErrorWorker@Error@@SAJPEBG@Z; Error::InternalErrorWorker(ushort const *)
0x18001d8e1  mov     rcx, [rsp+188h]; this
0x18001d8e9  mov     r9d, eax; char *
0x18001d8ec  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x18001d8f3  mov     edx, 33Ch; void *
0x18001d8f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001d8fd  lea     rcx, [rsi+28h]; this
0x18001d901  call    ??$Add@VTypeHandler@?$RepeatedPtrField@VGuidMsg@UIAutomationCoreProto@@@protobuf@google@@@RepeatedPtrFieldBase@internal@protobuf@google@@IEAAPEAVGuidMsg@UIAutomationCoreProto@@PEAV45@@Z; google::protobuf::internal::RepeatedPtrFieldBase::Add<google::protobuf::RepeatedPtrField<UIAutomationCoreProto::GuidMsg>::TypeHandler>(UIAutomationCoreProto::GuidMsg *)
0x18001d906  mov     r8d, 1; enum AutomationIdentifierType
0x18001d90c  mov     edx, [r12+rbx*4]; int
0x18001d910  mov     rcx, rax; struct UIAutomationCoreProto::GuidMsg *
0x18001d913  call    ?WriteAutomationId@ProtobufHelper@@CAXAEAVGuidMsg@UIAutomationCoreProto@@HW4AutomationIdentifierType@@@Z; ProtobufHelper::WriteAutomationId(UIAutomationCoreProto::GuidMsg &,int,AutomationIdentifierType)
0x18001d918  inc     ebx
0x18001d91a  jmp     loc_18001D82F
0x18001d91f  mov     rcx, [rsp+188h+var_B0]
0x18001d927  cmp     dword ptr [rsp+188h+var_A8+4], 0Ch
0x18001d92f  jz      loc_18001DC40
0x18001d935  mov     al, 1
0x18001d937  mov     r10, [rsp+188h]
0x18001d93f  test    al, al
0x18001d941  jnz     loc_18001DDCE
0x18001d947  lea     rax, ?_ElementMethodResponseMsg_default_instance_@UIAutomationCoreProto@@3UElementMethodResponseMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::ElementMethodResponseMsgDefaultTypeInternal UIAutomationCoreProto::_ElementMethodResponseMsg_default_instance_
0x18001d94e  cmp     dword ptr [rsp+188h+var_A8+4], 0Ch
0x18001d956  cmovz   rax, rcx
0x18001d95a  cmp     dword ptr [rax+1Ch], 24h ; '$'
0x18001d95e  jnz     loc_18001DC34
0x18001d964  mov     rbx, [rax+10h]
0x18001d968  mov     [rsp+188h+var_158], rbx
0x18001d96d  xorps   xmm0, xmm0
0x18001d970  movdqu  xmmword ptr [rsp+188h+pvarg], xmm0
0x18001d976  mov     [rsp+188h+var_120], r13
0x18001d97b  mov     r12d, r13d
0x18001d97e  mov     rsi, 0AAAAAAAAAAAAAAAh
0x18001d988  cmp     r12d, r14d
0x18001d98b  jnb     loc_18001DB04
0x18001d991  lea     rcx, [rsp+188h+Block]; pvarg
0x18001d999  call    cs:__imp_VariantInit
0x18001d99f  nop
0x18001d9a0  movsxd  rax, r12d
0x18001d9a3  mov     rcx, [rbx+20h]
0x18001d9a7  mov     r8, [r15+28h]; struct IClientConnection *
0x18001d9ab  lea     rdx, [rsp+188h+Block]; struct tagVARIANT *
0x18001d9b3  mov     rcx, [rcx+rax*8+8]; struct UIAutomationCoreProto::VariantObjectMsg *
0x18001d9b8  call    ?GetObj@ProtobufHelper@@SAXAEBVVariantObjectMsg@UIAutomationCoreProto@@PEAUtagVARIANT@@PEAVIClientConnection@@@Z; ProtobufHelper::GetObj(UIAutomationCoreProto::VariantObjectMsg const &,tagVARIANT *,IClientConnection *)
0x18001d9bd  mov     edx, r12d
0x18001d9c0  mov     r8, [r15+28h]; struct IClientConnection *
0x18001d9c4  mov     rax, [rsp+188h+var_148]
0x18001d9c9  mov     edx, [rax+rdx*4]; int
0x18001d9cc  lea     rcx, [rsp+188h+Block]; pvarg
0x18001d9d4  call    ?AdaptPropertyValueCoordinatesIfNeeded@UiaUtils@@SAJPEAUtagVARIANT@@HPEAVIClientConnection@@@Z; UiaUtils::AdaptPropertyValueCoordinatesIfNeeded(tagVARIANT *,int,IClientConnection *)
0x18001d9d9  mov     rcx, [rsp+188h]; this
0x18001d9e1  test    eax, eax
0x18001d9e3  js      loc_18001DC1B
0x18001d9e9  mov     r8, [rsp+188h+var_120]
0x18001d9ee  mov     rbx, [rsp+188h+pvarg+8]
0x18001d9f3  cmp     rbx, r8
0x18001d9f6  jnz     loc_18001DC52
0x18001d9fc  mov     rcx, rbx
0x18001d9ff  sub     rcx, [rsp+188h+pvarg]
0x18001da04  mov     rax, 2AAAAAAAAAAAAAABh
0x18001da0e  imul    rcx
0x18001da11  mov     r15, rdx
0x18001da14  sar     r15, 2
0x18001da18  mov     rax, r15
0x18001da1b  shr     rax, 3Fh
0x18001da1f  add     r15, rax
0x18001da22  cmp     r15, rsi
0x18001da25  jz      loc_18001DF47
0x18001da2b  lea     r13, [r15+1]
  ... truncated ...
```
