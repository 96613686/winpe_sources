# LocalUiaNodeProxy::RealCrossProcess_GetPropertyValues(int,uint,int const *,int,tagVARIANT *)

- ea: `0x1800d6314`
- end: `0x1800d6c80`
- name: `?RealCrossProcess_GetPropertyValues@LocalUiaNodeProxy@@AEAAJHIPEBHHPEAUtagVARIANT@@@Z`
- size: `2412`
- prototype: `__int64 __fastcall(LocalUiaNodeProxy *__hidden this, int, unsigned int, const int *, int, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops`

## callers

- `0x1800d5f50`

## callees

- `0x18001c498`
- `0x18001d324`
- `0x18001d350`
- `0x18001d3ac`
- `0x18001f2e4`
- `0x180021100`
- `0x180022248`
- `0x180026efc`
- `0x1800275b4`
- `0x180032724`
- `0x180033e04`
- `0x180050944`
- `0x18005633c`
- `0x1800be9c8`
- `0x1800d6314`
- `0x1800d6c88`
- `0x1800d6ee0`
- `0x1800d7144`
- `0x1800d7808`
- `0x18012e294`
- `0x1801390ec`
- `0x1801b78fc`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e9240`
- `0x1801ec660`
- `0x1801ec680`
- `0x1802a4530`
- `0x1802a51bc`
- `0x1802dd010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800d6c1a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800d6c1a`
- `OLEAUT32!__imp_VariantInit` at `0x1800d637f`
- `OLEAUT32!__imp_VariantInit` at `0x1800d6612`
- `OLEAUT32!__imp_VariantInit` at `0x1800d6778`
- `OLEAUT32!__imp_VariantInit` at `0x1800d6875`
- `OLEAUT32!__imp_VariantInit` at `0x1800d6ae5`
- `OLEAUT32!__imp_VariantInit` at `0x1800d637f`
- `OLEAUT32!__imp_VariantInit` at `0x1800d6612`
- `OLEAUT32!__imp_VariantInit` at `0x1800d6778`
- `OLEAUT32!__imp_VariantInit` at `0x1800d6875`
- `OLEAUT32!__imp_VariantInit` at `0x1800d6ae5`
- `OLEAUT32!__imp_VariantClear` at `0x1800d6643`
- `OLEAUT32!__imp_VariantClear` at `0x1800d68c4`
- `OLEAUT32!__imp_VariantClear` at `0x1800d6643`
- `OLEAUT32!__imp_VariantClear` at `0x1800d68c4`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x1800d6409`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x1800d6409`

## string_xrefs

- `0x1800d64e5`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x1800d6945`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x1800d6a9d`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`
- `0x1800d6570`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x1800d6a60`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`
- `0x1800d6ab5`: `onecore\windows\accessibletech\uiautomationcore\localuianodeproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall LocalUiaNodeProxy::RealCrossProcess_GetPropertyValues(
        LocalUiaNodeProxy *this,
        __int64 a2,
        unsigned int a3,
        const int *a4,
        int a5,
        struct tagVARIANT *a6)
{
  const int *v6; // r14
  unsigned int v7; // r13d
  struct tagVARIANT *v9; // rdx
  unsigned int v10; // r12d
  unsigned int i; // ebx
  struct UIAutomationCoreProto::ElementMethodRequestMsg *v12; // rax
  struct UIAutomationCoreProto::ElementMethodRequestMsg *v13; // rbx
  _QWORD *v14; // rcx
  struct IClientConnection *v15; // rbx
  unsigned int j; // r15d
  _DWORD *v17; // rcx
  __int64 v18; // rdx
  void *v19; // rax
  _QWORD *v20; // rdi
  int v21; // edx
  GUID **v22; // rax
  char v23; // cl
  __int64 v24; // r8
  unsigned int v25; // ebx
  unsigned __int64 v26; // rax
  const char *v27; // r9
  LocalUiaNodeProxy *v28; // rdi
  struct IClientConnection *v29; // rbx
  int v30; // eax
  char v31; // al
  _QWORD *v32; // rax
  _QWORD *v33; // rdi
  __int64 v34; // r14
  _QWORD *v35; // r15
  VARIANTARG *v36; // rcx
  __int128 v37; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  VARIANTARG *v39; // rdi
  VARIANTARG *v40; // r14
  char v41; // dl
  __int64 v42; // rcx
  unsigned __int64 v43; // r8
  const char *v44; // r9
  __int64 result; // rax
  int v46; // eax
  VARIANTARG *v47; // rdi
  signed __int64 v48; // r13
  unsigned __int64 v49; // r8
  unsigned __int64 v50; // r14
  __int64 size_of; // rax
  __int64 v52; // r15
  __int64 v53; // r13
  VARIANTARG *v54; // rcx
  void **v55; // r12
  __int64 v56; // r14
  _QWORD *v57; // rcx
  unsigned __int64 v58; // rax
  unsigned int v59; // ecx
  const char *v60; // r9
  _QWORD *v61; // rdi
  size_t v62; // rbx
  __int64 v63; // rdx
  void *v64; // rcx
  void *v65; // rcx
  unsigned int v66; // eax
  struct UserDefinedPropertyInfo *k; // rax
  google::protobuf::Arena *v68; // rcx
  __int64 v69; // r13
  void *v70; // r15
  void *v71; // [rsp+20h] [rbp-138h] BYREF
  unsigned int v72; // [rsp+28h] [rbp-130h]
  void *v73; // [rsp+30h] [rbp-128h] BYREF
  VARIANTARG *pvarg[2]; // [rsp+38h] [rbp-120h] BYREF
  VARIANTARG *v75; // [rsp+48h] [rbp-110h]
  unsigned __int64 v76; // [rsp+50h] [rbp-108h] BYREF
  void *v77; // [rsp+58h] [rbp-100h] BYREF
  LocalUiaNodeProxy *v78; // [rsp+60h] [rbp-F8h]
  struct IClientConnection *v79; // [rsp+68h] [rbp-F0h]
  _BYTE v80[32]; // [rsp+70h] [rbp-E8h] BYREF
  void **v81; // [rsp+90h] [rbp-C8h] BYREF
  __int64 v82; // [rsp+98h] [rbp-C0h] BYREF
  int v83; // [rsp+A0h] [rbp-B8h]
  _DWORD *v84; // [rsp+A8h] [rbp-B0h]
  __int64 v85; // [rsp+B0h] [rbp-A8h]
  void *Src[2]; // [rsp+B8h] [rbp-A0h] BYREF
  __int64 v87; // [rsp+C8h] [rbp-90h]
  unsigned __int64 v88; // [rsp+D0h] [rbp-88h]
  _QWORD v89[5]; // [rsp+D8h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v6 = a4;
  v76 = (unsigned __int64)a4;
  v7 = a3;
  v72 = a3;
  v78 = this;
  v9 = a6;
  v77 = a6;
  v10 = 0;
  for ( i = 0; i < v7; v9 = (struct tagVARIANT *)v77 )
    VariantInit(&v9[i++]);
  v89[1] = 0;
  v89[4] = 0;
  v89[2] = 0;
  v89[0] = &UIAutomationCoreProto::UiaCoreRequestMsg::`vftable';
  try
  {
    v12 = UIAutomationCoreProto::UiaCoreRequestMsg::_internal_mutable_element_method_request((UIAutomationCoreProto::UiaCoreRequestMsg *)v89);
    v13 = v12;
    *((_DWORD *)v12 + 4) = *((_DWORD *)this + 8);
    if ( *((_DWORD *)v12 + 9) != 11 )
    {
      UIAutomationCoreProto::ElementMethodRequestMsg::clear_element_method_payload(v12);
      *((_DWORD *)v13 + 9) = 11;
      v14 = (_QWORD *)(*((_QWORD *)v13 + 1) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*((_BYTE *)v13 + 8) & 1) != 0 )
        v14 = (_QWORD *)*v14;
      *((_QWORD *)v13 + 3) = google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::GetPropertyValuesRequestMsg,>(v14);
    }
    v15 = (struct IClientConnection *)*((_QWORD *)v13 + 3);
    v79 = v15;
    *((_QWORD *)v15 + 5) = GetThreadDpiAwarenessContext();
    *((_BYTE *)v15 + 48) = a5 != 0;
    for ( j = 0; ; ++j )
    {
      LODWORD(v71) = j;
      if ( j >= v7 )
      {
        v82 = 0;
        v85 = 0;
        v83 = 0;
        v81 = &UIAutomationCoreProto::UiaCoreResponseMsg::`vftable';
        v28 = v78;
        v29 = (struct IClientConnection *)*((_QWORD *)v78 + 5);
        v79 = v29;
        if ( v29 )
          (*(void (__fastcall **)(struct IClientConnection *))(*(_QWORD *)v29 + 8LL))(v29);
        v30 = DoCallWithReturn(
                *((struct IClientConnection **)v28 + 5),
                (struct UIAutomationCoreProto::UiaCoreRequestMsg *)v89,
                (struct UIAutomationCoreProto::UiaCoreResponseMsg *)&v81,
                0);
        if ( v30 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD8,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
            (const char *)(unsigned int)v30,
            (int)v71);
        if ( HIDWORD(v85) != 12 || (v31 = 0, v84[7] != 11) )
          v31 = 1;
        if ( v31 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDB,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
            (const char *)0x80040801LL,
            (int)v71);
        v32 = &UIAutomationCoreProto::_ElementMethodResponseMsg_default_instance_;
        if ( HIDWORD(v85) == 12 )
          v32 = v84;
        if ( *((_DWORD *)v32 + 7) == 11 )
          v33 = (_QWORD *)v32[2];
        else
          v33 = &UIAutomationCoreProto::_GetPropertyValuesResponseMsg_default_instance_;
        v73 = v33;
        *(_OWORD *)pvarg = 0;
        v75 = 0;
        while ( v10 < v7 )
        {
          VariantInit((VARIANTARG *)v80);
          ProtobufHelper::GetObj(
            *(const struct UIAutomationCoreProto::VariantObjectMsg **)(v33[4] + 8LL * (int)v10 + 8),
            (struct tagVARIANT *)v80,
            v29);
          v46 = UiaUtils::AdaptPropertyValueCoordinatesIfNeeded((VARIANTARG *)v80, v6[v10], v29);
          if ( v46 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xE5,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
              (const char *)(unsigned int)v46,
              (int)v71);
          v47 = pvarg[1];
          if ( pvarg[1] == v75 )
          {
            v48 = pvarg[1] - pvarg[0];
            if ( v48 == 0xAAAAAAAAAAAAAAALL )
              std::_Xlength_error("vector too long");
            v78 = (LocalUiaNodeProxy *)(v48 + 1);
            v49 = 0xAAAAAAAAAAAAAAABuLL * (((char *)v75 - (char *)pvarg[0]) >> 3);
            if ( v49 > 0xAAAAAAAAAAAAAAALL - (v49 >> 1) )
            {
              v50 = 0xAAAAAAAAAAAAAAALL;
            }
            else
            {
              v50 = (v49 >> 1) - 0x5555555555555555LL * (((char *)v75 - (char *)pvarg[0]) >> 3);
              if ( v50 < v48 + 1 )
                v50 = v48 + 1;
            }
            size_of = std::_Get_size_of_n<24>(v50);
            v52 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
            v53 = 3 * v48;
            *(_OWORD *)(v52 + 8 * v53) = *(_OWORD *)v80;
            *(_QWORD *)(v52 + 8 * v53 + 16) = *(_QWORD *)&v80[16];
            VariantInit((VARIANTARG *)v80);
            v54 = pvarg[0];
            if ( v47 != pvarg[1] )
            {
              std::_Uninitialized_move<wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)> *,std::allocator<wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>(pvarg[0]);
              v54 = v47;
            }
            std::_Uninitialized_move<wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)> *,std::allocator<wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>(v54);
            std::vector<wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>::_Change_array(
              pvarg,
              v52,
              v78,
              v50);
            v7 = v72;
            v6 = (const int *)v76;
          }
          else
          {
            *(_OWORD *)pvarg[1] = *(_OWORD *)v80;
            v47->pRecInfo = *(IRecordInfo **)&v80[16];
            VariantInit((VARIANTARG *)v80);
            ++pvarg[1];
          }
          VariantClear((VARIANTARG *)v80);
          ++v10;
          v33 = v73;
        }
        v34 = 0;
        if ( v7 )
        {
          v35 = v77;
          do
          {
            v36 = &pvarg[0][v34];
            v37 = *(_OWORD *)&v36->vt;
            pRecInfo = v36->pRecInfo;
            VariantInit(v36);
            *(_OWORD *)&v35[3 * v34] = v37;
            v35[3 * v34 + 2] = pRecInfo;
            v34 = (unsigned int)(v34 + 1);
          }
          while ( (unsigned int)v34 < v7 );
        }
        v39 = pvarg[0];
        if ( pvarg[0] )
        {
          v40 = pvarg[1];
          if ( pvarg[0] != pvarg[1] )
          {
            do
              VariantClear(v39++);
            while ( v39 != v40 );
            v39 = pvarg[0];
          }
          v76 = 8 * (((char *)v75 - (char *)v39) >> 3);
          v77 = v39;
          if ( v76 >= 0x1000 )
          {
            std::_Adjust_manually_vector_aligned(&v77, &v76);
            v39 = (VARIANTARG *)v77;
          }
          operator delete(v39);
          *(_OWORD *)pvarg = 0;
          v75 = 0;
        }
        if ( v29 )
          (*(void (__fastcall **)(struct IClientConnection *))(*(_QWORD *)v29 + 16LL))(v29);
        v81 = &UIAutomationCoreProto::UiaCoreResponseMsg::`vftable';
        v41 = v82;
        v42 = v82;
        if ( (v82 & 1) != 0 )
          v43 = *(_QWORD *)(v82 & 0xFFFFFFFFFFFFFFFCuLL);
        else
          v43 = v82 & 0xFFFFFFFFFFFFFFFCuLL;
        if ( !v43 )
        {
          if ( HIDWORD(v85) )
          {
            UIAutomationCoreProto::UiaCoreResponseMsg::clear_payload((UIAutomationCoreProto::UiaCoreResponseMsg *)&v81);
            v42 = v82;
            v41 = v82;
          }
          if ( (v41 & 1) != 0 )
          {
            google::protobuf::internal::InternalMetadata::DeleteOutOfLineHelper<std::string>(&v82);
            v42 = v82;
            v41 = v82;
          }
        }
        if ( (v42 & 2) != 0 )
        {
          v68 = (google::protobuf::Arena *)(v42 & 0xFFFFFFFFFFFFFFFCuLL);
          if ( (v41 & 1) != 0 )
            v68 = *(google::protobuf::Arena **)v68;
          if ( v68 )
            google::protobuf::Arena::`scalar deleting destructor'(v68, 1u);
        }
        UIAutomationCoreProto::UiaCoreRequestMsg::~UiaCoreRequestMsg((UIAutomationCoreProto::UiaCoreRequestMsg *)v89);
        return 0;
      }
      v17 = (_DWORD *)*((_QWORD *)v15 + 4);
      if ( v17 && (v18 = *((int *)v15 + 6), (int)v18 < *v17) )
      {
        v20 = *(_QWORD **)&v17[2 * v18 + 2];
        *((_DWORD *)v15 + 6) = v18 + 1;
      }
      else
      {
        v19 = (void *)google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::GuidMsg,>(*((_QWORD *)v15 + 2));
        v20 = google::protobuf::internal::RepeatedPtrFieldBase::AddOutOfLineHelper(
                (struct IClientConnection *)((char *)v15 + 16),
                v19);
      }
      v21 = v6[j];
      if ( (unsigned int)(v21 - 30000) > 0xAF )
        break;
      v22 = &(&off_1802DE930)[8 * (unsigned __int64)(unsigned int)(v21 - 30000)];
LABEL_15:
      if ( !v22 )
        goto LABEL_103;
      v23 = 1;
LABEL_17:
      if ( !v23 || !*v22 )
      {
        v66 = Error::InternalErrorWorker(L"unknown automation id");
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x33C,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
          (const char *)v66,
          (int)v71);
      }
      ProtobufHelper::GuidToString(Src);
      v25 = v87;
      v26 = 2LL * (unsigned int)v87;
      v27 = v26 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0LL;
      if ( v26 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
          v27,
          (int)v71);
      v55 = Src;
      if ( v88 > 7 )
        v55 = (void **)Src[0];
      v56 = v20[2];
      if ( !v56 )
      {
        v57 = (_QWORD *)(v20[1] & 0xFFFFFFFFFFFFFFFCuLL);
        if ( (v20[1] & 1) != 0 )
          v57 = (_QWORD *)*v57;
        v56 = google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::WstringMsg,>(
                v57,
                0xFFFFFFFFLL,
                v24,
                v27);
        v20[2] = v56;
      }
      v58 = 2LL * v25;
      v59 = 2 * v25;
      if ( v58 > 0xFFFFFFFF )
        v59 = -1;
      v60 = v58 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0LL;
      if ( v58 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2E,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
          v60,
          (int)v71);
      v61 = (_QWORD *)(*(_QWORD *)(v56 + 8) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( (*(_BYTE *)(v56 + 8) & 1) != 0 )
        v61 = (_QWORD *)*v61;
      memset(v80, 0, sizeof(v80));
      v62 = v59;
      if ( v59 > 0xF )
      {
        v69 = std::string::_Calculate_growth(v59, 15, 0x7FFFFFFFFFFFFFFFLL, v60);
        v70 = (void *)std::allocator<char>::allocate(v80, v69 + 1);
        *(_QWORD *)v80 = v70;
        *(_QWORD *)&v80[16] = v62;
        *(_QWORD *)&v80[24] = v69;
        memcpy_0(v70, v55, v62);
        v10 = 0;
        *((_BYTE *)v70 + v62) = 0;
        j = (unsigned int)v71;
        v7 = v72;
      }
      else
      {
        *(_OWORD *)&v80[16] = v59;
        memcpy_0(v80, v55, v59);
        v10 = 0;
        v80[v62] = 0;
      }
      LOBYTE(v63) = 0;
      google::protobuf::internal::ArenaStringPtr::Set(v56 + 16, v63, v80, v61);
      if ( *(_QWORD *)&v80[24] > 0xFu )
      {
        v71 = (void *)(*(_QWORD *)&v80[24] + 1LL);
        v64 = *(void **)v80;
        v73 = *(void **)v80;
        if ( (unsigned __int64)(*(_QWORD *)&v80[24] + 1LL) >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v73, (unsigned __int64 *)&v71);
          v64 = v73;
        }
        operator delete(v64);
      }
      if ( v88 > 7 )
      {
        v73 = (void *)(2 * v88 + 2);
        v65 = Src[0];
        v71 = Src[0];
        if ( (unsigned __int64)v73 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v71, (unsigned __int64 *)&v73);
          v65 = v71;
        }
        operator delete(v65);
      }
      v15 = v79;
      v6 = (const int *)v76;
    }
    for ( k = g_pUserDefinedProperties; k; k = *(struct UserDefinedPropertyInfo **)k )
    {
      if ( *((_DWORD *)k + 6) == v21 )
      {
        v22 = (GUID **)((char *)k + 16);
        goto LABEL_15;
      }
    }
LABEL_103:
    v23 = 0;
    v22 = *(GUID ***)v80;
    goto LABEL_17;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xF0,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\localuianodeproxy.cpp",
                           v44);
  }
  return result;
}

```

## disassembly

```asm
0x1800d6314  mov     rax, rsp
0x1800d6317  mov     [rax+10h], rbx
0x1800d631b  push    rdi
0x1800d631c  push    r12
0x1800d631e  push    r13
0x1800d6320  push    r14
0x1800d6322  push    r15
0x1800d6324  sub     rsp, 130h
0x1800d632b  movaps  xmmword ptr [rax-38h], xmm6
0x1800d632f  movaps  xmmword ptr [rax-48h], xmm7
0x1800d6333  mov     rax, cs:__security_cookie
0x1800d633a  xor     rax, rsp
0x1800d633d  mov     [rsp+158h+var_58], rax
0x1800d6345  mov     r14, r9
0x1800d6348  mov     [rsp+158h+var_108], r9
0x1800d634d  mov     r13d, r8d
0x1800d6350  mov     [rsp+158h+var_130], r8d
0x1800d6355  mov     rdi, rcx
0x1800d6358  mov     [rsp+158h+var_F8], rcx
0x1800d635d  mov     rdx, [rsp+158h+arg_28]
0x1800d6365  mov     [rsp+158h+var_100], rdx
0x1800d636a  xor     r12d, r12d
0x1800d636d  mov     ebx, r12d
0x1800d6370  test    r8d, r8d
0x1800d6373  jz      short loc_1800D6391
0x1800d6375  mov     eax, ebx
0x1800d6377  lea     rcx, [rax+rax*2]
0x1800d637b  lea     rcx, [rdx+rcx*8]; pvarg
0x1800d637f  call    cs:__imp_VariantInit
0x1800d6385  inc     ebx
0x1800d6387  cmp     ebx, r13d
0x1800d638a  mov     rdx, [rsp+158h+var_100]
0x1800d638f  jb      short loc_1800D6375
0x1800d6391  mov     [rsp+158h+var_78], r12
0x1800d6399  mov     [rsp+158h+var_60], r12
0x1800d63a1  xor     eax, eax
0x1800d63a3  mov     [rsp+158h+var_70], rax
0x1800d63ab  lea     rax, ??_7UiaCoreRequestMsg@UIAutomationCoreProto@@6B@; const UIAutomationCoreProto::UiaCoreRequestMsg::`vftable'
0x1800d63b2  mov     [rsp+158h+var_80], rax
0x1800d63ba  lea     rcx, [rsp+158h+var_80]; this
0x1800d63c2  call    ?_internal_mutable_element_method_request@UiaCoreRequestMsg@UIAutomationCoreProto@@AEAAPEAVElementMethodRequestMsg@2@XZ; UIAutomationCoreProto::UiaCoreRequestMsg::_internal_mutable_element_method_request(void)
0x1800d63c7  mov     rbx, rax
0x1800d63ca  mov     ecx, [rdi+20h]
0x1800d63cd  mov     [rax+10h], ecx
0x1800d63d0  cmp     dword ptr [rax+24h], 0Bh
0x1800d63d4  jz      short loc_1800D6400
0x1800d63d6  mov     rcx, rax; this
0x1800d63d9  call    ?clear_element_method_payload@ElementMethodRequestMsg@UIAutomationCoreProto@@QEAAXXZ; UIAutomationCoreProto::ElementMethodRequestMsg::clear_element_method_payload(void)
0x1800d63de  mov     dword ptr [rbx+24h], 0Bh
0x1800d63e5  mov     rcx, [rbx+8]
0x1800d63e9  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800d63ed  test    byte ptr [rbx+8], 1
0x1800d63f1  jnz     loc_1800D6B05
0x1800d63f7  call    ??$CreateMaybeMessage@VGetPropertyValuesRequestMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVGetPropertyValuesRequestMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::GetPropertyValuesRequestMsg,>(google::protobuf::Arena *)
0x1800d63fc  mov     [rbx+18h], rax
0x1800d6400  mov     rbx, [rbx+18h]
0x1800d6404  mov     [rsp+158h+var_F0], rbx
0x1800d6409  call    cs:__imp_GetThreadDpiAwarenessContext
0x1800d640f  mov     [rbx+28h], rax
0x1800d6413  cmp     [rsp+158h+arg_20], r12d
0x1800d641b  setnz   al
0x1800d641e  mov     [rbx+30h], al
0x1800d6421  mov     r15d, r12d
0x1800d6424  mov     dword ptr [rsp+158h+var_138], r15d; int
0x1800d6429  cmp     r15d, r13d
0x1800d642c  jnb     loc_1800D64F7
0x1800d6432  mov     rcx, [rbx+20h]
0x1800d6436  test    rcx, rcx
0x1800d6439  jz      short loc_1800D6447
0x1800d643b  movsxd  rdx, dword ptr [rbx+18h]
0x1800d643f  cmp     edx, [rcx]
0x1800d6441  jl      loc_1800D6A76
0x1800d6447  mov     rcx, [rbx+10h]
0x1800d644b  call    ??$CreateMaybeMessage@VGuidMsg@UIAutomationCoreProto@@$$V@Arena@protobuf@google@@CAPEAVGuidMsg@UIAutomationCoreProto@@PEAV012@@Z; google::protobuf::Arena::CreateMaybeMessage<UIAutomationCoreProto::GuidMsg,>(google::protobuf::Arena *)
0x1800d6450  mov     rdx, rax; void *
0x1800d6453  lea     rcx, [rbx+10h]; this
0x1800d6457  call    ?AddOutOfLineHelper@RepeatedPtrFieldBase@internal@protobuf@google@@AEAAPEAXPEAX@Z; google::protobuf::internal::RepeatedPtrFieldBase::AddOutOfLineHelper(void *)
0x1800d645c  mov     rdi, rax
0x1800d645f  mov     ecx, r15d
0x1800d6462  mov     edx, [r14+rcx*4]
0x1800d6466  lea     ecx, [rdx-7530h]
0x1800d646c  cmp     ecx, 0AFh
0x1800d6472  ja      loc_1800D6B1D
0x1800d6478  mov     eax, ecx
0x1800d647a  shl     rax, 6
0x1800d647e  lea     rcx, off_1802DE930
0x1800d6485  add     rax, rcx
0x1800d6488  test    rax, rax
0x1800d648b  jz      loc_1800D6B44
0x1800d6491  mov     cl, 1
0x1800d6493  test    cl, cl
0x1800d6495  jz      loc_1800D6A86
0x1800d649b  mov     rdx, [rax]
0x1800d649e  test    rdx, rdx
0x1800d64a1  jz      loc_1800D6A86
0x1800d64a7  lea     rcx, [rsp+158h+Src]
0x1800d64af  call    ?GuidToString@ProtobufHelper@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; ProtobufHelper::GuidToString(_GUID const &)
0x1800d64b4  nop
0x1800d64b5  mov     rbx, [rsp+158h+var_90]
0x1800d64bd  mov     eax, ebx
0x1800d64bf  add     rax, rax
0x1800d64c2  mov     edx, 0FFFFFFFFh
0x1800d64c7  cmp     rdx, rax
0x1800d64ca  sbb     r9d, r9d
0x1800d64cd  and     r9d, 80070216h; char *
0x1800d64d4  mov     rcx, [rsp+158h]; this
0x1800d64dc  cmp     rax, rdx
0x1800d64df  jbe     loc_1800D68D7
0x1800d64e5  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x1800d64ec  mov     edx, 4Eh ; 'N'; void *
0x1800d64f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d64f7  mov     [rsp+158h+var_C0], r12
0x1800d64ff  mov     [rsp+158h+var_A8], 0
0x1800d650b  mov     [rsp+158h+var_B8], r12d
0x1800d6513  lea     rax, ??_7UiaCoreResponseMsg@UIAutomationCoreProto@@6B@; const UIAutomationCoreProto::UiaCoreResponseMsg::`vftable'
0x1800d651a  mov     [rsp+158h+var_C8], rax
0x1800d6522  mov     rdi, [rsp+158h+var_F8]
0x1800d6527  mov     rbx, [rdi+28h]
0x1800d652b  mov     [rsp+158h+var_F0], rbx
0x1800d6530  test    rbx, rbx
0x1800d6533  jz      short loc_1800D6545
0x1800d6535  mov     rax, [rbx]
0x1800d6538  mov     rcx, rbx
0x1800d653b  mov     rax, [rax+8]
0x1800d653f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6544  nop
0x1800d6545  xor     r9d, r9d; bool
0x1800d6548  lea     r8, [rsp+158h+var_C8]; struct UIAutomationCoreProto::UiaCoreResponseMsg *
0x1800d6550  lea     rdx, [rsp+158h+var_80]; struct UIAutomationCoreProto::UiaCoreRequestMsg *
0x1800d6558  mov     rcx, [rdi+28h]; struct IClientConnection *
0x1800d655c  call    ?DoCallWithReturn@@YAJPEAVIClientConnection@@AEAVUiaCoreRequestMsg@UIAutomationCoreProto@@AEAVUiaCoreResponseMsg@3@_N@Z; DoCallWithReturn(IClientConnection *,UIAutomationCoreProto::UiaCoreRequestMsg &,UIAutomationCoreProto::UiaCoreResponseMsg &,bool)
0x1800d6561  mov     rcx, [rsp+158h]; this
0x1800d6569  test    eax, eax
0x1800d656b  jns     short loc_1800D6581
0x1800d656d  mov     r9d, eax; char *
0x1800d6570  lea     r8, aOnecoreWindows_78; "onecore\\windows\\accessibletech\\uiaut"...
0x1800d6577  mov     edx, 0D8h; void *
0x1800d657c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d6581  mov     rcx, [rsp+158h+var_B0]
0x1800d6589  cmp     dword ptr [rsp+158h+var_A8+4], 0Ch
0x1800d6591  jz      loc_1800D6A4B
0x1800d6597  mov     al, 1
0x1800d6599  mov     r10, [rsp+158h]
0x1800d65a1  test    al, al
0x1800d65a3  jnz     loc_1800D6AAF
0x1800d65a9  lea     rax, ?_ElementMethodResponseMsg_default_instance_@UIAutomationCoreProto@@3UElementMethodResponseMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::ElementMethodResponseMsgDefaultTypeInternal UIAutomationCoreProto::_ElementMethodResponseMsg_default_instance_
0x1800d65b0  cmp     dword ptr [rsp+158h+var_A8+4], 0Ch
0x1800d65b8  cmovz   rax, rcx
0x1800d65bc  cmp     dword ptr [rax+1Ch], 0Bh
0x1800d65c0  jnz     loc_1800D6767
0x1800d65c6  mov     rdi, [rax+10h]
0x1800d65ca  mov     [rsp+158h+var_128], rdi
0x1800d65cf  xorps   xmm0, xmm0
0x1800d65d2  movdqu  xmmword ptr [rsp+158h+pvarg], xmm0
0x1800d65d8  mov     [rsp+158h+var_110], r12
0x1800d65dd  mov     r15, 0AAAAAAAAAAAAAAAh
0x1800d65e7  cmp     r12d, r13d
0x1800d65ea  jb      loc_1800D6773
0x1800d65f0  xor     r14d, r14d
0x1800d65f3  test    r13d, r13d
0x1800d65f6  jz      short loc_1800D662C
0x1800d65f8  mov     r15, [rsp+158h+var_100]
0x1800d65fd  lea     rdi, [r14+r14*2]
0x1800d6601  mov     rax, [rsp+158h+pvarg]
0x1800d6606  lea     rcx, [rax+rdi*8]; pvarg
0x1800d660a  movups  xmm6, xmmword ptr [rcx]
0x1800d660d  movsd   xmm7, qword ptr [rcx+10h]
0x1800d6612  call    cs:__imp_VariantInit
0x1800d6618  movups  xmmword ptr [r15+rdi*8], xmm6
0x1800d661d  movsd   qword ptr [r15+rdi*8+10h], xmm7
0x1800d6624  inc     r14d
0x1800d6627  cmp     r14d, r13d
0x1800d662a  jb      short loc_1800D65FD
0x1800d662c  mov     rdi, [rsp+158h+pvarg]
0x1800d6631  test    rdi, rdi
0x1800d6634  jz      short loc_1800D66AA
0x1800d6636  mov     r14, [rsp+158h+pvarg+8]
0x1800d663b  cmp     rdi, r14
0x1800d663e  jz      short loc_1800D6657
0x1800d6640  mov     rcx, rdi; pvarg
0x1800d6643  call    cs:__imp_VariantClear
0x1800d6649  add     rdi, 18h
0x1800d664d  cmp     rdi, r14
0x1800d6650  jnz     short loc_1800D6640
0x1800d6652  mov     rdi, [rsp+158h+pvarg]
0x1800d6657  mov     rax, [rsp+158h+var_110]
0x1800d665c  sub     rax, rdi
0x1800d665f  sar     rax, 3
0x1800d6663  mov     rcx, 0AAAAAAAAAAAAAAABh
0x1800d666d  imul    rax, rcx
0x1800d6671  lea     rdx, [rax+rax*2]
0x1800d6675  shl     rdx, 3
0x1800d6679  mov     [rsp+158h+var_108], rdx
0x1800d667e  mov     [rsp+158h+var_100], rdi
0x1800d6683  cmp     rdx, 1000h
0x1800d668a  jnb     loc_1800D6C3D
0x1800d6690  mov     rcx, rdi; Block
0x1800d6693  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d6698  xorps   xmm0, xmm0
0x1800d669b  movdqu  xmmword ptr [rsp+158h+pvarg], xmm0
0x1800d66a1  mov     [rsp+158h+var_110], 0
0x1800d66aa  test    rbx, rbx
0x1800d66ad  jz      short loc_1800D66BF
0x1800d66af  mov     rax, [rbx]
0x1800d66b2  mov     rcx, rbx
0x1800d66b5  mov     rax, [rax+10h]
0x1800d66b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d66be  nop
0x1800d66bf  lea     rax, ??_7UiaCoreResponseMsg@UIAutomationCoreProto@@6B@; const UIAutomationCoreProto::UiaCoreResponseMsg::`vftable'
0x1800d66c6  mov     [rsp+158h+var_C8], rax
0x1800d66ce  mov     dl, byte ptr [rsp+158h+var_C0]
0x1800d66d5  mov     rcx, [rsp+158h+var_C0]
0x1800d66dd  test    dl, 1
0x1800d66e0  jnz     loc_1800D6AF6
0x1800d66e6  mov     r8, rcx
0x1800d66e9  and     r8, 0FFFFFFFFFFFFFFFCh
0x1800d66ed  test    r8, r8
0x1800d66f0  jnz     short loc_1800D671C
0x1800d66f2  cmp     dword ptr [rsp+158h+var_A8+4], r8d
0x1800d66fa  jz      short loc_1800D6713
0x1800d66fc  lea     rcx, [rsp+158h+var_C8]; this
0x1800d6704  call    ?clear_payload@UiaCoreResponseMsg@UIAutomationCoreProto@@QEAAXXZ; UIAutomationCoreProto::UiaCoreResponseMsg::clear_payload(void)
0x1800d6709  mov     rcx, [rsp+158h+var_C0]
0x1800d6711  mov     dl, cl
0x1800d6713  test    dl, 1
0x1800d6716  jnz     loc_1800D6C5B
0x1800d671c  test    cl, 2
0x1800d671f  jnz     loc_1800D6B51
0x1800d6725  lea     rcx, [rsp+158h+var_80]; this
0x1800d672d  call    ??1UiaCoreRequestMsg@UIAutomationCoreProto@@UEAA@XZ; UIAutomationCoreProto::UiaCoreRequestMsg::~UiaCoreRequestMsg(void)
0x1800d6732  xor     eax, eax
0x1800d6734  mov     rcx, [rsp+158h+var_58]
0x1800d673c  xor     rcx, rsp; StackCookie
0x1800d673f  call    __security_check_cookie
0x1800d6744  lea     r11, [rsp+158h+var_28]
0x1800d674c  mov     rbx, [r11+38h]
0x1800d6750  movaps  xmm6, xmmword ptr [r11-10h]
0x1800d6755  movaps  xmm7, xmmword ptr [r11-20h]
0x1800d675a  mov     rsp, r11
0x1800d675d  pop     r15
0x1800d675f  pop     r14
0x1800d6761  pop     r13
0x1800d6763  pop     r12
0x1800d6765  pop     rdi
0x1800d6766  retn
0x1800d6767  lea     rdi, ?_GetPropertyValuesResponseMsg_default_instance_@UIAutomationCoreProto@@3UGetPropertyValuesResponseMsgDefaultTypeInternal@1@A; UIAutomationCoreProto::GetPropertyValuesResponseMsgDefaultTypeInternal UIAutomationCoreProto::_GetPropertyValuesResponseMsg_default_instance_
0x1800d676e  jmp     loc_1800D65CA
0x1800d6773  lea     rcx, [rsp+158h+var_E8]; pvarg
0x1800d6778  call    cs:__imp_VariantInit
0x1800d677e  nop
0x1800d677f  movsxd  rax, r12d
0x1800d6782  mov     rcx, [rdi+20h]
0x1800d6786  mov     r8, rbx; struct IClientConnection *
0x1800d6789  lea     rdx, [rsp+158h+var_E8]; struct tagVARIANT *
0x1800d678e  mov     rcx, [rcx+rax*8+8]; struct UIAutomationCoreProto::VariantObjectMsg *
0x1800d6793  call    ?GetObj@ProtobufHelper@@SAXAEBVVariantObjectMsg@UIAutomationCoreProto@@PEAUtagVARIANT@@PEAVIClientConnection@@@Z; ProtobufHelper::GetObj(UIAutomationCoreProto::VariantObjectMsg const &,tagVARIANT *,IClientConnection *)
0x1800d6798  mov     edx, r12d
0x1800d679b  mov     r8, rbx; struct IClientConnection *
0x1800d679e  mov     edx, [r14+rdx*4]; int
0x1800d67a2  lea     rcx, [rsp+158h+var_E8]; pvarg
0x1800d67a7  call    ?AdaptPropertyValueCoordinatesIfNeeded@UiaUtils@@SAJPEAUtagVARIANT@@HPEAVIClientConnection@@@Z; UiaUtils::AdaptPropertyValueCoordinatesIfNeeded(tagVARIANT *,int,IClientConnection *)
0x1800d67ac  mov     rcx, [rsp+158h]; this
0x1800d67b4  test    eax, eax
0x1800d67b6  js      loc_1800D6A5D
0x1800d67bc  mov     r8, [rsp+158h+var_110]
0x1800d67c1  mov     rdi, [rsp+158h+pvarg+8]
0x1800d67c6  cmp     rdi, r8
0x1800d67c9  jnz     loc_1800D6ACA
0x1800d67cf  mov     rcx, rdi
0x1800d67d2  sub     rcx, [rsp+158h+pvarg]
0x1800d67d7  mov     rax, 2AAAAAAAAAAAAAABh
0x1800d67e1  imul    rcx
0x1800d67e4  mov     r13, rdx
0x1800d67e7  sar     r13, 2
0x1800d67eb  mov     rax, r13
0x1800d67ee  shr     rax, 3Fh
0x1800d67f2  add     r13, rax
0x1800d67f5  cmp     r13, r15
0x1800d67f8  jz      loc_1800D6C13
0x1800d67fe  lea     rdx, [r13+1]
0x1800d6802  mov     [rsp+158h+var_F8], rdx
0x1800d6807  sub     r8, [rsp+158h+pvarg]
0x1800d680c  sar     r8, 3
0x1800d6810  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800d681a  imul    r8, rax
0x1800d681e  mov     rcx, r8
0x1800d6821  shr     rcx, 1
0x1800d6824  mov     rax, r15
0x1800d6827  sub     rax, rcx
0x1800d682a  cmp     r8, rax
0x1800d682d  ja      loc_1800D6B37
0x1800d6833  lea     r14, [rcx+r8]
0x1800d6837  cmp     r14, rdx
0x1800d683a  cmovb   r14, rdx
0x1800d683e  mov     rcx, r14
0x1800d6841  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x1800d6846  mov     rcx, rax
0x1800d6849  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800d684e  mov     r15, rax
0x1800d6851  lea     r13, [r13+r13*2+0]
  ... truncated ...
```
