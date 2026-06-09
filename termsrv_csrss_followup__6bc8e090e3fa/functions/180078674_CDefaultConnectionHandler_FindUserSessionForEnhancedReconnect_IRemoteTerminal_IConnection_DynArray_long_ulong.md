# CDefaultConnectionHandler::FindUserSessionForEnhancedReconnect(IRemoteTerminal *,IConnection *,DynArray<long,ulong> &)

- ea: `0x180078674`
- end: `0x18007914b`
- name: `?FindUserSessionForEnhancedReconnect@CDefaultConnectionHandler@@AEAAJPEAVIRemoteTerminal@@PEAVIConnection@@AEAV?$DynArray@JK@@@Z`
- size: `2775`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007690c`

## callees

- `0x180001294`
- `0x1800016a8`
- `0x18000332c`
- `0x180013948`
- `0x1800139c0`
- `0x180015310`
- `0x18002558c`
- `0x18002cd9c`
- `0x180033f60`
- `0x180034494`
- `0x18003e5ec`
- `0x180051128`
- `0x180051484`
- `0x180076534`
- `0x180078674`
- `0x180079920`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180078903`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180078903`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078735`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800787c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800788dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078f68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078735`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800787c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800788dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078f68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800787b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800790b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800790c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800790d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800787b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800790b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800790c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800790d9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180078d2d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180078d2d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180078965`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180078965`

## string_xrefs

- `0x180078754`: `LocalAlloc failed for pPropertyValueFastReconnectUserSID`
- `0x1800787e6`: `LocalAlloc failed for pPropertyValueFastReconnectUserSID after getting required size from stack`
- `0x18007883e`: `Failed to query fast reconnect user SID property after getting required size from stack`
- `0x1800788a6`: `Failed to query fast reconnect user SID property for the required size`
- `0x180078928`: `Setting pEnhancedFastReconnectUserSID from stack`
- `0x180079087`: `Fast reconnect user SID property from stack wasn't a strVal`
- `0x180078984`: `ConvertStringSidToSid failed`
- `0x180078e31`: `ptrCurrentSessionUserName->GetUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CDefaultConnectionHandler::FindUserSessionForEnhancedReconnect(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  WCHAR *v7; // rsi
  __int64 *v8; // rax
  unsigned int *v9; // rax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  unsigned int *v13; // rdi
  char *v14; // rax
  __int16 *v15; // rdx
  int InstanceOfSessionManager; // ebx
  void *v17; // r12
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  unsigned int *v22; // rax
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // r8
  int v25; // r9d
  const char **v26; // rax
  char *v27; // rdx
  const char **v28; // rax
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // r8d
  int v33; // r9d
  const char **v34; // rax
  __int64 *v35; // rdx
  int v36; // eax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  const char **v40; // rax
  __int16 *v41; // rdx
  const char *v42; // rax
  unsigned int v43; // ebx
  const char *v44; // rax
  __int16 *v45; // rdx
  HLOCAL v46; // rax
  __int64 v47; // r9
  __int64 *v48; // rdx
  __int64 *v49; // rcx
  unsigned __int64 appended; // rax
  __int64 *v51; // rdx
  PSID *p_pSid2; // [rsp+28h] [rbp-D8h]
  PSID *v54; // [rsp+38h] [rbp-C8h]
  const char **v55; // [rsp+38h] [rbp-C8h]
  int v56; // [rsp+40h] [rbp-C0h] BYREF
  const char *v57; // [rsp+48h] [rbp-B8h] BYREF
  const char *v58; // [rsp+50h] [rbp-B0h] BYREF
  PSID pSid2; // [rsp+58h] [rbp-A8h] BYREF
  int v60; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 v61[4]; // [rsp+64h] [rbp-9Ch] BYREF
  const char *v62; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v63[2]; // [rsp+70h] [rbp-90h] BYREF
  SIZE_T uBytes; // [rsp+80h] [rbp-80h] BYREF
  __int64 v65; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v66; // [rsp+90h] [rbp-70h] BYREF
  __int64 v67; // [rsp+98h] [rbp-68h] BYREF
  int v68; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v70; // [rsp+B0h] [rbp-50h] BYREF
  struct ISessionManager *v71; // [rsp+B8h] [rbp-48h] BYREF
  PSID Sid; // [rsp+C0h] [rbp-40h] BYREF
  int v73; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v74; // [rsp+D8h] [rbp-28h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+100h] [rbp+0h]
  __int64 v79; // [rsp+108h] [rbp+8h]
  __int128 v80; // [rsp+110h] [rbp+10h] BYREF
  __int128 v81; // [rsp+120h] [rbp+20h] BYREF

  v81 = 0;
  v7 = 0;
  v71 = 0;
  v70 = 0;
  v67 = 0;
  v65 = 0;
  v68 = 0;
  v66 = 0;
  v80 = 0;
  v69 = 0;
  v60 = 0;
  v75 = 0;
  v8 = (__int64 *)operator new(0x18u);
  *v8 = (__int64)v8;
  v8[1] = (__int64)v8;
  v74 = v8;
  v76 = 0;
  v77 = 0;
  v78 = 7;
  v79 = 8;
  v73 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<long>>,std::_Iterator_base0>>>::_Assign_grow(
    &v76,
    16,
    v8);
  *(_DWORD *)v61 = 0;
  Sid = 0;
  LODWORD(uBytes) = 24;
  v9 = (unsigned int *)LocalAlloc(0x40u, 0x18u);
  v13 = v9;
  if ( !v9 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
    {
LABEL_5:
      InstanceOfSessionManager = -2147024882;
      goto LABEL_90;
    }
    v14 = "LocalAlloc failed for pPropertyValueFastReconnectUserSID";
    v15 = (__int16 *)byte_180111F3D;
LABEL_4:
    pSid2 = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v10,
      (_DWORD)v15,
      v11,
      v12,
      (__int64)&pSid2);
    goto LABEL_5;
  }
  v17 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64 *, SIZE_T *, unsigned int *))(*(_QWORD *)a3 + 528LL))(
          a3,
          PROPERTY_TYPE_GET_FAST_RECONNECT_USER_SID,
          &uBytes,
          v9);
  InstanceOfSessionManager = v18;
  if ( v18 != -2147024774 )
  {
    if ( v18 < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v57 = "Failed to query fast reconnect user SID property for the required size";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v19,
          (unsigned int)word_180111EBA,
          v20,
          v21,
          (__int64)&v57);
      }
      goto LABEL_86;
    }
LABEL_18:
    v7 = (WCHAR *)LocalAlloc(0x40u, 2 * v13[2] + 2);
    if ( *(_WORD *)v13 != 2 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v63[0] = "Fast reconnect user SID property from stack wasn't a strVal";
        v34 = (const char **)v63;
        v35 = qword_180111E58;
        goto LABEL_84;
      }
LABEL_85:
      InstanceOfSessionManager = -2147024883;
      goto LABEL_86;
    }
    _o_wcscpy_s(v7, v13[2], *((_QWORD *)v13 + 2));
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      v57 = (const char *)v7;
      pSid2 = (PSID)*((_QWORD *)v13 + 2);
      v58 = "Setting pEnhancedFastReconnectUserSID from stack";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        dword_18012E170,
        (unsigned int)byte_180111E7B,
        v32,
        v33,
        (__int64)&v58,
        (__int64)&pSid2,
        (__int64)&v57);
    }
    if ( !ConvertStringSidToSidW(v7, &Sid) )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v57 = "ConvertStringSidToSid failed";
        v34 = &v57;
        v35 = (__int64 *)byte_180111E35;
LABEL_84:
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v29,
          (_DWORD)v35,
          v30,
          v31,
          (__int64)v34);
        goto LABEL_85;
      }
      goto LABEL_85;
    }
    InstanceOfSessionManager = CUtils::GetInstanceOfSessionManager(&v71);
    if ( InstanceOfSessionManager < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_86;
      v57 = "FindUserSessionForEnhancedReconnect";
      pSid2 = "CUtils::GetInstanceOfSessionManager";
      v58 = "Warning HResult failed";
      v54 = (PSID *)&v57;
      p_pSid2 = &pSid2;
      v28 = &v58;
      v27 = (char *)qword_180111DF8;
      goto LABEL_14;
    }
    InstanceOfSessionManager = (*(__int64 (__fastcall **)(struct ISessionManager *, __int64 *))(*(_QWORD *)v71 + 24LL))(
                                 v71,
                                 &v70);
    if ( InstanceOfSessionManager < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_86;
      v57 = "FindUserSessionForEnhancedReconnect";
      pSid2 = "GetSessionList";
      v58 = "Warning HResult failed";
      v54 = (PSID *)&v57;
      p_pSid2 = &pSid2;
      v28 = &v58;
      v27 = byte_180111DBB;
      goto LABEL_14;
    }
    InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v70 + 32LL))(v70, &v67);
    if ( InstanceOfSessionManager < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_86;
      v57 = "FindUserSessionForEnhancedReconnect";
      pSid2 = "GetInstanceOfEnum";
      v58 = "Warning HResult failed";
      v54 = (PSID *)&v57;
      p_pSid2 = &pSid2;
      v28 = &v58;
      v27 = (char *)&word_180111D7E;
      goto LABEL_14;
    }
    InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, __int128 *, int *, unsigned int *, __int128 *))(*(_QWORD *)a2 + 136LL))(
                                 a2,
                                 &v81,
                                 &v68,
                                 &v66,
                                 &v80);
    if ( InstanceOfSessionManager < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_86;
      v57 = "FindUserSessionForEnhancedReconnect";
      pSid2 = "pRemoteTerminal->GetTerminalTypeExtended";
      v58 = "Warning HResult failed";
      v54 = (PSID *)&v57;
      p_pSid2 = &pSid2;
      v28 = &v58;
      v27 = byte_180111D41;
      goto LABEL_14;
    }
    InstanceOfSessionManager = CDefaultSessionArbitrationFilter::GetInstanceOfDefaultSessionArbitrationFilter(
                                 0,
                                 v66,
                                 &v80,
                                 &v69);
    if ( InstanceOfSessionManager < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_86;
      v57 = "FindUserSessionForEnhancedReconnect";
      pSid2 = "GetInstanceOfDefaultSessionArbitrationFilter";
      v58 = "Warning HResult failed";
      v54 = (PSID *)&v57;
      p_pSid2 = &pSid2;
      v28 = &v58;
      v27 = (char *)&dword_180111D04;
      goto LABEL_14;
    }
    InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 32LL))(v67, v69);
    if ( InstanceOfSessionManager < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_86;
      v57 = "FindUserSessionForEnhancedReconnect";
      pSid2 = "AddFilter Initialprogram";
      v58 = "Warning HResult failed";
      v54 = (PSID *)&v57;
      p_pSid2 = &pSid2;
      v28 = &v58;
      v27 = &byte_180111CC7;
      goto LABEL_14;
    }
    while ( 1 )
    {
      SmartPtr<ITerminal>::operator=(&v65, 0);
      v36 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 80LL))(v67, &v65);
      if ( v36 < 0 )
        break;
      v58 = 0;
      pSid2 = 0;
      InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v65 + 80LL))(v65, &v60);
      if ( InstanceOfSessionManager < 0 )
      {
        if ( (unsigned int)dword_18012E170 <= 3 )
          goto LABEL_60;
        v63[0] = "FindUserSessionForEnhancedReconnect";
        v42 = "ptrSession->getId";
        v41 = word_180111C8A;
LABEL_58:
        v62 = v42;
        v57 = "Warning HResult failed";
        v55 = (const char **)v63;
        v40 = &v57;
LABEL_59:
        v56 = InstanceOfSessionManager;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v37,
          (_DWORD)v41,
          v38,
          v39,
          (__int64)v40,
          (__int64)&v62,
          (__int64)&v56,
          (__int64)v55);
LABEL_60:
        SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v58);
        goto LABEL_86;
      }
      if ( (*(int (__fastcall **)(__int64, const char **))(*(_QWORD *)v65 + 96LL))(v65, &v58) >= 0 )
      {
        InstanceOfSessionManager = (*(__int64 (__fastcall **)(const char *, PSID *))(*(_QWORD *)v58 + 72LL))(
                                     v58,
                                     &pSid2);
        if ( InstanceOfSessionManager < 0 )
        {
          if ( (unsigned int)dword_18012E170 <= 3 )
            goto LABEL_60;
          v63[0] = "FindUserSessionForEnhancedReconnect";
          v42 = "ptrCurrentSessionUserName->GetUserSid";
          v41 = (__int16 *)byte_180111C4D;
          goto LABEL_58;
        }
        if ( EqualSid(Sid, pSid2) )
        {
          InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v65 + 80LL))(v65, &v60);
          if ( InstanceOfSessionManager < 0 )
          {
            if ( (unsigned int)dword_18012E170 > 3 )
            {
              v57 = "FindUserSessionForEnhancedReconnect";
              v62 = "ptrSession->getId";
              v63[0] = "Warning HResult failed";
              v55 = &v57;
              v40 = (const char **)v63;
              v41 = (__int16 *)qword_180111C10;
              goto LABEL_59;
            }
            goto LABEL_60;
          }
          if ( (unsigned int)dword_18012E170 > 4 )
          {
            v56 = v60;
            v57 = "Enhanced fast reconnect - adding session";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v37,
              (unsigned int)word_180111BE2,
              v38,
              v39,
              (__int64)&v57,
              (__int64)&v56);
          }
          std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::emplace<long const &>(
            &v73,
            v63,
            &v60);
        }
      }
      SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v58);
    }
    InstanceOfSessionManager = 0;
    if ( v36 != -2147024637 )
      InstanceOfSessionManager = v36;
    if ( InstanceOfSessionManager < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_86;
      v63[0] = "FindUserSessionForEnhancedReconnect";
      v62 = "Failure while looping through sessions";
      v57 = "Warning HResult failed";
      v54 = (PSID *)v63;
      v26 = &v62;
      v27 = byte_180111BA5;
      goto LABEL_13;
    }
    v43 = v75;
    if ( (_DWORD)v75 )
    {
      v46 = LocalAlloc(0x40u, 4LL * (unsigned int)v75);
      v17 = v46;
      v47 = 0;
      v48 = v74;
      v49 = (__int64 *)*v74;
      while ( v49 != v48 )
      {
        *((_DWORD *)v46 + v47) = *((_DWORD *)v49 + 4);
        v47 = (unsigned int)(v47 + 1);
        v49 = (__int64 *)*v49;
        v48 = v74;
      }
      InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, HLOCAL, _QWORD, unsigned __int8 *))(*(_QWORD *)a3 + 480LL))(
                                   a3,
                                   v46,
                                   v43,
                                   v61);
      if ( InstanceOfSessionManager < 0 )
      {
        if ( (unsigned int)dword_18012E170 <= 3 )
          goto LABEL_86;
        v63[0] = "FindUserSessionForEnhancedReconnect";
        v62 = "GetSessionForEnhancedFastReconnect failed";
        v57 = "Warning HResult failed";
        v54 = (PSID *)v63;
        v26 = &v62;
        v27 = byte_180111B45;
        goto LABEL_13;
      }
      appended = std::_Fnv1a_append_bytes(v23, v61, v24);
      v51 = *(__int64 **)(std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::_Find_last<unsigned long>(
                            &v73,
                            v63,
                            v61,
                            appended)
                        + 8);
      if ( v51 && v51 != v74 )
      {
        (*(void (__fastcall **)(__int64, unsigned __int8 *))(*(_QWORD *)a4 + 8LL))(a4, v61);
        goto LABEL_86;
      }
      if ( (unsigned int)dword_18012E170 > 4 )
      {
        v44 = "Session returned by stack is not in the list of sessions passed to it";
        v45 = word_180111B22;
        goto LABEL_69;
      }
    }
    else if ( (unsigned int)dword_18012E170 > 4 )
    {
      v44 = "Fast reconnect can't find a session to reconnect to";
      v45 = word_180111B82;
LABEL_69:
      v63[0] = v44;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v23,
        (_DWORD)v45,
        v24,
        v25,
        (__int64)v63);
    }
    InstanceOfSessionManager = -2147024894;
    goto LABEL_86;
  }
  LocalFree(v13);
  v22 = (unsigned int *)LocalAlloc(0x40u, (unsigned int)uBytes);
  v13 = v22;
  if ( !v22 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_5;
    v14 = "LocalAlloc failed for pPropertyValueFastReconnectUserSID after getting required size from stack";
    v15 = word_180111F1A;
    goto LABEL_4;
  }
  InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, __int64 *, SIZE_T *, unsigned int *))(*(_QWORD *)a3 + 528LL))(
                               a3,
                               PROPERTY_TYPE_GET_FAST_RECONNECT_USER_SID,
                               &uBytes,
                               v22);
  if ( InstanceOfSessionManager >= 0 )
    goto LABEL_18;
  if ( (unsigned int)dword_18012E170 > 3 )
  {
    pSid2 = "FindUserSessionForEnhancedReconnect";
    v58 = "Failed to query fast reconnect user SID property after getting required size from stack";
    v57 = "Warning HResult failed";
    v54 = &pSid2;
    v26 = &v58;
    v27 = byte_180111EDD;
LABEL_13:
    p_pSid2 = (PSID *)v26;
    v28 = &v57;
LABEL_14:
    v56 = InstanceOfSessionManager;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v23,
      (_DWORD)v27,
      v24,
      v25,
      (__int64)v28,
      (__int64)p_pSid2,
      (__int64)&v56,
      (__int64)v54);
  }
LABEL_86:
  LocalFree(v13);
  if ( v17 )
    LocalFree(v17);
  if ( v7 )
    LocalFree(v7);
LABEL_90:
  std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::~_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>(&v73);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v69);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v65);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v67);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v70);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v71);
  return (unsigned int)InstanceOfSessionManager;
}

```

## disassembly

```asm
0x180078674  mov     [rsp-8+arg_0], rbx
0x180078679  push    rbp
0x18007867a  push    rsi
0x18007867b  push    rdi
0x18007867c  push    r12
0x18007867e  push    r13
0x180078680  push    r14
0x180078682  push    r15
0x180078684  lea     rbp, [rsp-40h]
0x180078689  sub     rsp, 140h
0x180078690  mov     rax, cs:__security_cookie
0x180078697  xor     rax, rsp
0x18007869a  mov     [rbp+70h+var_40], rax
0x18007869e  mov     r13, r9
0x1800786a1  mov     r14, r8
0x1800786a4  mov     r15, rdx
0x1800786a7  xorps   xmm0, xmm0
0x1800786aa  movups  [rbp+70h+var_50], xmm0
0x1800786ae  xor     esi, esi
0x1800786b0  mov     [rbp+70h+var_B8], rsi
0x1800786b4  mov     [rbp+70h+var_C0], rsi
0x1800786b8  mov     [rbp+70h+var_D8], rsi
0x1800786bc  mov     [rbp+70h+var_E8], rsi
0x1800786c0  mov     [rbp+70h+var_D0], esi
0x1800786c3  mov     [rbp+70h+var_E0], esi
0x1800786c6  movups  [rbp+70h+var_60], xmm0
0x1800786ca  mov     [rbp+70h+var_C8], rsi
0x1800786ce  mov     [rsp+170h+var_110], esi
0x1800786d2  mov     [rbp+70h+var_A0], esi
0x1800786d5  mov     [rbp+70h+var_98], rsi
0x1800786d9  mov     [rbp+70h+var_90], rsi
0x1800786dd  lea     ebx, [rsi+18h]
0x1800786e0  mov     ecx, ebx; Size
0x1800786e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800786e7  mov     [rax], rax
0x1800786ea  mov     [rax+8], rax
0x1800786ee  mov     [rbp+70h+var_98], rax
0x1800786f2  mov     [rbp+70h+var_88], rsi
0x1800786f6  xorps   xmm0, xmm0
0x1800786f9  movdqa  [rbp+70h+var_80], xmm0
0x1800786fe  mov     [rbp+70h+var_70], 7
0x180078706  mov     [rbp+70h+var_68], 8
0x18007870e  mov     [rbp+70h+var_A0], 3F800000h
0x180078715  mov     r8, rax
0x180078718  lea     edx, [rsi+10h]
0x18007871b  lea     rcx, [rbp+70h+var_88]
0x18007871f  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@J@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@J@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<long>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<long>>,std::_Iterator_base0>)
0x180078724  nop
0x180078725  mov     dword ptr [rsp+170h+var_10C], esi
0x180078729  mov     [rbp+70h+Sid], rsi
0x18007872d  mov     dword ptr [rbp+70h+uBytes], ebx
0x180078730  mov     edx, ebx; uBytes
0x180078732  lea     ecx, [rsi+40h]; uFlags
0x180078735  call    cs:__imp_LocalAlloc
0x18007873c  nop     dword ptr [rax+rax+00h]
0x180078741  mov     rdi, rax
0x180078744  test    rax, rax
0x180078747  jnz     short loc_180078780
0x180078749  mov     eax, cs:dword_18012E170
0x18007874f  cmp     eax, 3
0x180078752  jbe     short loc_180078776
0x180078754  lea     rax, aLocalallocFail_0; "LocalAlloc failed for pPropertyValueFas"...
0x18007875b  lea     rdx, byte_180111F3D
0x180078762  mov     [rsp+170h+pSid2], rax
0x180078767  lea     rax, [rsp+170h+pSid2]
0x18007876c  mov     [rsp+170h+var_150], rax
0x180078771  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180078776  mov     ebx, 8007000Eh
0x18007877b  jmp     loc_1800790E6
0x180078780  mov     r12, rsi
0x180078783  mov     rax, [r14]
0x180078786  mov     r9, rdi
0x180078789  lea     r8, [rbp+70h+uBytes]
0x18007878d  lea     rdx, PROPERTY_TYPE_GET_FAST_RECONNECT_USER_SID
0x180078794  mov     rcx, r14
0x180078797  mov     rax, [rax+210h]
0x18007879e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800787a3  mov     ebx, eax
0x1800787a5  cmp     eax, 8007007Ah
0x1800787aa  jnz     loc_180078893
0x1800787b0  mov     rcx, rdi; hMem
0x1800787b3  call    cs:__imp_LocalFree
0x1800787ba  nop     dword ptr [rax+rax+00h]
0x1800787bf  mov     edx, dword ptr [rbp+70h+uBytes]; uBytes
0x1800787c2  mov     ecx, 40h ; '@'; uFlags
0x1800787c7  call    cs:__imp_LocalAlloc
0x1800787ce  nop     dword ptr [rax+rax+00h]
0x1800787d3  mov     rdi, rax
0x1800787d6  test    rax, rax
0x1800787d9  jnz     short loc_1800787F9
0x1800787db  mov     eax, cs:dword_18012E170
0x1800787e1  cmp     eax, 3
0x1800787e4  jbe     short loc_180078776
0x1800787e6  lea     rax, aLocalallocFail; "LocalAlloc failed for pPropertyValueFas"...
0x1800787ed  lea     rdx, word_180111F1A
0x1800787f4  jmp     loc_180078762
0x1800787f9  mov     rax, [r14]
0x1800787fc  mov     r9, rdi
0x1800787ff  lea     r8, [rbp+70h+uBytes]
0x180078803  lea     rdx, PROPERTY_TYPE_GET_FAST_RECONNECT_USER_SID
0x18007880a  mov     rcx, r14
0x18007880d  mov     rax, [rax+210h]
0x180078814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078819  mov     ebx, eax
0x18007881b  test    eax, eax
0x18007881d  jns     loc_1800788CD
0x180078823  mov     eax, cs:dword_18012E170
0x180078829  cmp     eax, 3
0x18007882c  jbe     loc_1800790AE
0x180078832  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
0x180078839  mov     [rsp+170h+pSid2], rax
0x18007883e  lea     rax, aFailedToQueryF_0; "Failed to query fast reconnect user SID"...
0x180078845  mov     [rsp+170h+var_120], rax
0x18007884a  lea     rax, aWarningHresult; "Warning HResult failed"
0x180078851  mov     [rsp+170h+var_128], rax
0x180078856  lea     rax, [rsp+170h+pSid2]
0x18007885b  mov     [rsp+170h+var_138], rax
0x180078860  lea     rax, [rsp+170h+var_130]
0x180078865  mov     [rsp+170h+var_140], rax
0x18007886a  lea     rax, [rsp+170h+var_120]
0x18007886f  lea     rdx, byte_180111EDD
0x180078876  mov     [rsp+170h+var_148], rax
0x18007887b  lea     rax, [rsp+170h+var_128]
0x180078880  mov     [rsp+170h+var_130], ebx
0x180078884  mov     [rsp+170h+var_150], rax
0x180078889  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18007888e  jmp     loc_1800790AE
0x180078893  test    eax, eax
0x180078895  jns     short loc_1800788CD
0x180078897  mov     eax, cs:dword_18012E170
0x18007889d  cmp     eax, 3
0x1800788a0  jbe     loc_1800790AE
0x1800788a6  lea     rax, aFailedToQueryF_1; "Failed to query fast reconnect user SID"...
0x1800788ad  mov     [rsp+170h+var_128], rax
0x1800788b2  lea     rax, [rsp+170h+var_128]
0x1800788b7  mov     [rsp+170h+var_150], rax
0x1800788bc  lea     rdx, word_180111EBA
0x1800788c3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800788c8  jmp     loc_1800790AE
0x1800788cd  mov     eax, [rdi+8]
0x1800788d0  lea     edx, ds:2[rax*2]; uBytes
0x1800788d7  mov     ecx, 40h ; '@'; uFlags
0x1800788dc  call    cs:__imp_LocalAlloc
0x1800788e3  nop     dword ptr [rax+rax+00h]
0x1800788e8  mov     rsi, rax
0x1800788eb  mov     eax, 2
0x1800788f0  cmp     ax, [rdi]
0x1800788f3  jnz     loc_18007907C
0x1800788f9  mov     edx, [rdi+8]
0x1800788fc  mov     r8, [rdi+10h]
0x180078900  mov     rcx, rsi
0x180078903  call    cs:__imp__o_wcscpy_s
0x18007890a  nop     dword ptr [rax+rax+00h]
0x18007890f  mov     ecx, cs:dword_18012E170
0x180078915  cmp     ecx, 5
0x180078918  jbe     short loc_18007895E
0x18007891a  mov     [rsp+170h+var_128], rsi
0x18007891f  mov     rax, [rdi+10h]
0x180078923  mov     [rsp+170h+pSid2], rax
0x180078928  lea     rax, aSettingPenhanc; "Setting pEnhancedFastReconnectUserSID f"...
0x18007892f  mov     [rsp+170h+var_120], rax
0x180078934  lea     rax, [rsp+170h+var_128]
0x180078939  mov     [rsp+170h+var_140], rax
0x18007893e  lea     rax, [rsp+170h+pSid2]
0x180078943  mov     [rsp+170h+var_148], rax
0x180078948  lea     rax, [rsp+170h+var_120]
0x18007894d  mov     [rsp+170h+var_150], rax
0x180078952  lea     rdx, byte_180111E7B
0x180078959  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18007895e  lea     rdx, [rbp+70h+Sid]; Sid
0x180078962  mov     rcx, rsi; StringSid
0x180078965  call    cs:__imp_ConvertStringSidToSidW
0x18007896c  nop     dword ptr [rax+rax+00h]
0x180078971  test    eax, eax
0x180078973  jnz     short loc_1800789A1
0x180078975  mov     eax, cs:dword_18012E170
0x18007897b  cmp     eax, 3
0x18007897e  jbe     loc_1800790A9
0x180078984  lea     rax, aConvertstrings_1; "ConvertStringSidToSid failed"
0x18007898b  mov     [rsp+170h+var_128], rax
0x180078990  lea     rax, [rsp+170h+var_128]
0x180078995  lea     rdx, byte_180111E35
0x18007899c  jmp     loc_18007909F
0x1800789a1  lea     rcx, [rbp+70h+var_B8]; struct ISessionManager **
0x1800789a5  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x1800789aa  mov     ebx, eax
0x1800789ac  test    eax, eax
0x1800789ae  jns     short loc_180078A12
0x1800789b0  mov     eax, cs:dword_18012E170
0x1800789b6  cmp     eax, 3
0x1800789b9  jbe     loc_1800790AE
0x1800789bf  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
0x1800789c6  mov     [rsp+170h+var_128], rax
0x1800789cb  lea     rax, aCutilsGetinsta_1; "CUtils::GetInstanceOfSessionManager"
0x1800789d2  mov     [rsp+170h+pSid2], rax
0x1800789d7  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800789de  mov     [rsp+170h+var_120], rax
0x1800789e3  lea     rax, [rsp+170h+var_128]
0x1800789e8  mov     [rsp+170h+var_138], rax
0x1800789ed  lea     rax, [rsp+170h+var_130]
0x1800789f2  mov     [rsp+170h+var_140], rax
0x1800789f7  lea     rax, [rsp+170h+pSid2]
0x1800789fc  mov     [rsp+170h+var_148], rax
0x180078a01  lea     rax, [rsp+170h+var_120]
0x180078a06  lea     rdx, qword_180111DF8
0x180078a0d  jmp     loc_180078880
0x180078a12  mov     rcx, [rbp+70h+var_B8]
0x180078a16  mov     rax, [rcx]
0x180078a19  lea     rdx, [rbp+70h+var_C0]
0x180078a1d  mov     rax, [rax+18h]
0x180078a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a26  mov     ebx, eax
0x180078a28  test    eax, eax
0x180078a2a  jns     short loc_180078A8E
0x180078a2c  mov     eax, cs:dword_18012E170
0x180078a32  cmp     eax, 3
0x180078a35  jbe     loc_1800790AE
0x180078a3b  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
0x180078a42  mov     [rsp+170h+var_128], rax
0x180078a47  lea     rax, aGetsessionlist_1; "GetSessionList"
0x180078a4e  mov     [rsp+170h+pSid2], rax
0x180078a53  lea     rax, aWarningHresult; "Warning HResult failed"
0x180078a5a  mov     [rsp+170h+var_120], rax
0x180078a5f  lea     rax, [rsp+170h+var_128]
0x180078a64  mov     [rsp+170h+var_138], rax
0x180078a69  lea     rax, [rsp+170h+var_130]
0x180078a6e  mov     [rsp+170h+var_140], rax
0x180078a73  lea     rax, [rsp+170h+pSid2]
0x180078a78  mov     [rsp+170h+var_148], rax
0x180078a7d  lea     rax, [rsp+170h+var_120]
0x180078a82  lea     rdx, byte_180111DBB
0x180078a89  jmp     loc_180078880
0x180078a8e  mov     rcx, [rbp+70h+var_C0]
0x180078a92  mov     rax, [rcx]
0x180078a95  lea     rdx, [rbp+70h+var_D8]
0x180078a99  mov     rax, [rax+20h]
0x180078a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078aa2  mov     ebx, eax
0x180078aa4  test    eax, eax
0x180078aa6  jns     short loc_180078B0A
0x180078aa8  mov     eax, cs:dword_18012E170
0x180078aae  cmp     eax, 3
0x180078ab1  jbe     loc_1800790AE
0x180078ab7  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
0x180078abe  mov     [rsp+170h+var_128], rax
0x180078ac3  lea     rax, aGetinstanceofe_1; "GetInstanceOfEnum"
0x180078aca  mov     [rsp+170h+pSid2], rax
0x180078acf  lea     rax, aWarningHresult; "Warning HResult failed"
0x180078ad6  mov     [rsp+170h+var_120], rax
0x180078adb  lea     rax, [rsp+170h+var_128]
0x180078ae0  mov     [rsp+170h+var_138], rax
0x180078ae5  lea     rax, [rsp+170h+var_130]
0x180078aea  mov     [rsp+170h+var_140], rax
0x180078aef  lea     rax, [rsp+170h+pSid2]
0x180078af4  mov     [rsp+170h+var_148], rax
0x180078af9  lea     rax, [rsp+170h+var_120]
0x180078afe  lea     rdx, word_180111D7E
0x180078b05  jmp     loc_180078880
0x180078b0a  mov     rax, [r15]
0x180078b0d  lea     rcx, [rbp+70h+var_60]
0x180078b11  mov     [rsp+170h+var_150], rcx
0x180078b16  lea     r9, [rbp+70h+var_E0]
0x180078b1a  lea     r8, [rbp+70h+var_D0]
0x180078b1e  lea     rdx, [rbp+70h+var_50]
0x180078b22  mov     rcx, r15
0x180078b25  mov     rax, [rax+88h]
0x180078b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078b31  mov     ebx, eax
0x180078b33  test    eax, eax
0x180078b35  jns     short loc_180078B99
0x180078b37  mov     eax, cs:dword_18012E170
0x180078b3d  cmp     eax, 3
0x180078b40  jbe     loc_1800790AE
0x180078b46  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
0x180078b4d  mov     [rsp+170h+var_128], rax
0x180078b52  lea     rax, aPremotetermina_1; "pRemoteTerminal->GetTerminalTypeExtende"...
0x180078b59  mov     [rsp+170h+pSid2], rax
0x180078b5e  lea     rax, aWarningHresult; "Warning HResult failed"
0x180078b65  mov     [rsp+170h+var_120], rax
0x180078b6a  lea     rax, [rsp+170h+var_128]
0x180078b6f  mov     [rsp+170h+var_138], rax
0x180078b74  lea     rax, [rsp+170h+var_130]
0x180078b79  mov     [rsp+170h+var_140], rax
0x180078b7e  lea     rax, [rsp+170h+pSid2]
0x180078b83  mov     [rsp+170h+var_148], rax
0x180078b88  lea     rax, [rsp+170h+var_120]
0x180078b8d  lea     rdx, byte_180111D41
0x180078b94  jmp     loc_180078880
0x180078b99  lea     r9, [rbp+70h+var_C8]
0x180078b9d  lea     r8, [rbp+70h+var_60]
0x180078ba1  mov     edx, [rbp+70h+var_E0]
0x180078ba4  xor     ecx, ecx
0x180078ba6  call    ?GetInstanceOfDefaultSessionArbitrationFilter@CDefaultSessionArbitrationFilter@@SAJQEAGW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0004@@AEBU_GUID@@PEAPEAUISessionEnumFilter@@@Z; CDefaultSessionArbitrationFilter::GetInstanceOfDefaultSessionArbitrationFilter(ushort * const,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0004,_GUID const &,ISessionEnumFilter * *)
0x180078bab  mov     ebx, eax
0x180078bad  test    eax, eax
0x180078baf  jns     short loc_180078C13
0x180078bb1  mov     eax, cs:dword_18012E170
0x180078bb7  cmp     eax, 3
0x180078bba  jbe     loc_1800790AE
0x180078bc0  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
  ... truncated ...
```
