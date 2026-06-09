# CDefaultConnectionHandler::FindUserSessionForEnhancedReconnect(IRemoteTerminal *,IConnection *,DynArray<long,ulong> &)

- ea: `0x1800750e8`
- end: `0x180075b7c`
- name: `?FindUserSessionForEnhancedReconnect@CDefaultConnectionHandler@@AEAAJPEAVIRemoteTerminal@@PEAVIConnection@@AEAV?$DynArray@JK@@@Z`
- size: `2708`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007339c`

## callees

- `0x180001284`
- `0x180001688`
- `0x1800032f8`
- `0x1800130d8`
- `0x180013150`
- `0x1800148f0`
- `0x1800241f0`
- `0x18002b5f4`
- `0x1800321f0`
- `0x180032724`
- `0x18003c464`
- `0x18004ea90`
- `0x18004edec`
- `0x180072f74`
- `0x1800750e8`
- `0x180076350`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007535f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18007535f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800751a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007522f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007533e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800759b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800751a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007522f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007533e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800759b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075221`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075af5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075b03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075b11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075221`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075af5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075b03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075b11`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18007577d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18007577d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800753bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800753bb`

## string_xrefs

- `0x1800751c2`: `LocalAlloc failed for pPropertyValueFastReconnectUserSID`
- `0x180075248`: `LocalAlloc failed for pPropertyValueFastReconnectUserSID after getting required size from stack`
- `0x1800752a0`: `Failed to query fast reconnect user SID property after getting required size from stack`
- `0x180075308`: `Failed to query fast reconnect user SID property for the required size`
- `0x18007537e`: `Setting pEnhancedFastReconnectUserSID from stack`
- `0x180075acb`: `Fast reconnect user SID property from stack wasn't a strVal`
- `0x1800753d4`: `ConvertStringSidToSid failed`
- `0x18007587b`: `ptrCurrentSessionUserName->GetUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    if ( (unsigned int)dword_180128170 <= 3 )
    {
LABEL_5:
      InstanceOfSessionManager = -2147024882;
      goto LABEL_90;
    }
    v14 = "LocalAlloc failed for pPropertyValueFastReconnectUserSID";
    v15 = (__int16 *)byte_18010BEBD;
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v57 = "Failed to query fast reconnect user SID property for the required size";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v19,
          (unsigned int)word_18010BE3A,
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v63[0] = "Fast reconnect user SID property from stack wasn't a strVal";
        v34 = (const char **)v63;
        v35 = qword_18010BDD8;
        goto LABEL_84;
      }
LABEL_85:
      InstanceOfSessionManager = -2147024883;
      goto LABEL_86;
    }
    _o_wcscpy_s(v7, v13[2], *((_QWORD *)v13 + 2));
    if ( (unsigned int)dword_180128170 > 5 )
    {
      v57 = (const char *)v7;
      pSid2 = (PSID)*((_QWORD *)v13 + 2);
      v58 = "Setting pEnhancedFastReconnectUserSID from stack";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        dword_180128170,
        (unsigned int)byte_18010BDFB,
        v32,
        v33,
        (__int64)&v58,
        (__int64)&pSid2,
        (__int64)&v57);
    }
    if ( !ConvertStringSidToSidW(v7, &Sid) )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v57 = "ConvertStringSidToSid failed";
        v34 = &v57;
        v35 = (__int64 *)byte_18010BDB5;
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
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_86;
      v57 = "FindUserSessionForEnhancedReconnect";
      pSid2 = "CUtils::GetInstanceOfSessionManager";
      v58 = "Warning HResult failed";
      v54 = (PSID *)&v57;
      p_pSid2 = &pSid2;
      v28 = &v58;
      v27 = (char *)qword_18010BD78;
      goto LABEL_14;
    }
    InstanceOfSessionManager = (*(__int64 (__fastcall **)(struct ISessionManager *, __int64 *))(*(_QWORD *)v71 + 24LL))(
                                 v71,
                                 &v70);
    if ( InstanceOfSessionManager < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_86;
      v57 = "FindUserSessionForEnhancedReconnect";
      pSid2 = "GetSessionList";
      v58 = "Warning HResult failed";
      v54 = (PSID *)&v57;
      p_pSid2 = &pSid2;
      v28 = &v58;
      v27 = byte_18010BD3B;
      goto LABEL_14;
    }
    InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v70 + 32LL))(v70, &v67);
    if ( InstanceOfSessionManager < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_86;
      v57 = "FindUserSessionForEnhancedReconnect";
      pSid2 = "GetInstanceOfEnum";
      v58 = "Warning HResult failed";
      v54 = (PSID *)&v57;
      p_pSid2 = &pSid2;
      v28 = &v58;
      v27 = (char *)&word_18010BCFE;
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
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_86;
      v57 = "FindUserSessionForEnhancedReconnect";
      pSid2 = "pRemoteTerminal->GetTerminalTypeExtended";
      v58 = "Warning HResult failed";
      v54 = (PSID *)&v57;
      p_pSid2 = &pSid2;
      v28 = &v58;
      v27 = byte_18010BCC1;
      goto LABEL_14;
    }
    InstanceOfSessionManager = CDefaultSessionArbitrationFilter::GetInstanceOfDefaultSessionArbitrationFilter(
                                 0,
                                 v66,
                                 &v80,
                                 &v69);
    if ( InstanceOfSessionManager < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_86;
      v57 = "FindUserSessionForEnhancedReconnect";
      pSid2 = "GetInstanceOfDefaultSessionArbitrationFilter";
      v58 = "Warning HResult failed";
      v54 = (PSID *)&v57;
      p_pSid2 = &pSid2;
      v28 = &v58;
      v27 = (char *)&dword_18010BC84;
      goto LABEL_14;
    }
    InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 32LL))(v67, v69);
    if ( InstanceOfSessionManager < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_86;
      v57 = "FindUserSessionForEnhancedReconnect";
      pSid2 = "AddFilter Initialprogram";
      v58 = "Warning HResult failed";
      v54 = (PSID *)&v57;
      p_pSid2 = &pSid2;
      v28 = &v58;
      v27 = &byte_18010BC47;
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
        if ( (unsigned int)dword_180128170 <= 3 )
          goto LABEL_60;
        v63[0] = "FindUserSessionForEnhancedReconnect";
        v42 = "ptrSession->getId";
        v41 = word_18010BC0A;
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
          if ( (unsigned int)dword_180128170 <= 3 )
            goto LABEL_60;
          v63[0] = "FindUserSessionForEnhancedReconnect";
          v42 = "ptrCurrentSessionUserName->GetUserSid";
          v41 = (__int16 *)byte_18010BBCD;
          goto LABEL_58;
        }
        if ( EqualSid(Sid, pSid2) )
        {
          InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v65 + 80LL))(v65, &v60);
          if ( InstanceOfSessionManager < 0 )
          {
            if ( (unsigned int)dword_180128170 > 3 )
            {
              v57 = "FindUserSessionForEnhancedReconnect";
              v62 = "ptrSession->getId";
              v63[0] = "Warning HResult failed";
              v55 = &v57;
              v40 = (const char **)v63;
              v41 = (__int16 *)qword_18010BB90;
              goto LABEL_59;
            }
            goto LABEL_60;
          }
          if ( (unsigned int)dword_180128170 > 4 )
          {
            v56 = v60;
            v57 = "Enhanced fast reconnect - adding session";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v37,
              (unsigned int)word_18010BB62,
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
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_86;
      v63[0] = "FindUserSessionForEnhancedReconnect";
      v62 = "Failure while looping through sessions";
      v57 = "Warning HResult failed";
      v54 = (PSID *)v63;
      v26 = &v62;
      v27 = byte_18010BB25;
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
        if ( (unsigned int)dword_180128170 <= 3 )
          goto LABEL_86;
        v63[0] = "FindUserSessionForEnhancedReconnect";
        v62 = "GetSessionForEnhancedFastReconnect failed";
        v57 = "Warning HResult failed";
        v54 = (PSID *)v63;
        v26 = &v62;
        v27 = byte_18010BAC5;
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
      if ( (unsigned int)dword_180128170 > 4 )
      {
        v44 = "Session returned by stack is not in the list of sessions passed to it";
        v45 = word_18010BAA2;
        goto LABEL_69;
      }
    }
    else if ( (unsigned int)dword_180128170 > 4 )
    {
      v44 = "Fast reconnect can't find a session to reconnect to";
      v45 = word_18010BB02;
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
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_5;
    v14 = "LocalAlloc failed for pPropertyValueFastReconnectUserSID after getting required size from stack";
    v15 = word_18010BE9A;
    goto LABEL_4;
  }
  InstanceOfSessionManager = (*(__int64 (__fastcall **)(__int64, __int64 *, SIZE_T *, unsigned int *))(*(_QWORD *)a3 + 528LL))(
                               a3,
                               PROPERTY_TYPE_GET_FAST_RECONNECT_USER_SID,
                               &uBytes,
                               v22);
  if ( InstanceOfSessionManager >= 0 )
    goto LABEL_18;
  if ( (unsigned int)dword_180128170 > 3 )
  {
    pSid2 = "FindUserSessionForEnhancedReconnect";
    v58 = "Failed to query fast reconnect user SID property after getting required size from stack";
    v57 = "Warning HResult failed";
    v54 = &pSid2;
    v26 = &v58;
    v27 = byte_18010BE5D;
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
0x1800750e8  mov     [rsp-8+arg_0], rbx
0x1800750ed  push    rbp
0x1800750ee  push    rsi
0x1800750ef  push    rdi
0x1800750f0  push    r12
0x1800750f2  push    r13
0x1800750f4  push    r14
0x1800750f6  push    r15
0x1800750f8  lea     rbp, [rsp-40h]
0x1800750fd  sub     rsp, 140h
0x180075104  mov     rax, cs:__security_cookie
0x18007510b  xor     rax, rsp
0x18007510e  mov     [rbp+70h+var_40], rax
0x180075112  mov     r13, r9
0x180075115  mov     r14, r8
0x180075118  mov     r15, rdx
0x18007511b  xorps   xmm0, xmm0
0x18007511e  movups  [rbp+70h+var_50], xmm0
0x180075122  xor     esi, esi
0x180075124  mov     [rbp+70h+var_B8], rsi
0x180075128  mov     [rbp+70h+var_C0], rsi
0x18007512c  mov     [rbp+70h+var_D8], rsi
0x180075130  mov     [rbp+70h+var_E8], rsi
0x180075134  mov     [rbp+70h+var_D0], esi
0x180075137  mov     [rbp+70h+var_E0], esi
0x18007513a  movups  [rbp+70h+var_60], xmm0
0x18007513e  mov     [rbp+70h+var_C8], rsi
0x180075142  mov     [rsp+170h+var_110], esi
0x180075146  mov     [rbp+70h+var_A0], esi
0x180075149  mov     [rbp+70h+var_98], rsi
0x18007514d  mov     [rbp+70h+var_90], rsi
0x180075151  lea     ebx, [rsi+18h]
0x180075154  mov     ecx, ebx; Size
0x180075156  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007515b  mov     [rax], rax
0x18007515e  mov     [rax+8], rax
0x180075162  mov     [rbp+70h+var_98], rax
0x180075166  mov     [rbp+70h+var_88], rsi
0x18007516a  xorps   xmm0, xmm0
0x18007516d  movdqa  [rbp+70h+var_80], xmm0
0x180075172  mov     [rbp+70h+var_70], 7
0x18007517a  mov     [rbp+70h+var_68], 8
0x180075182  mov     [rbp+70h+var_A0], 3F800000h
0x180075189  mov     r8, rax
0x18007518c  lea     edx, [rsi+10h]
0x18007518f  lea     rcx, [rbp+70h+var_88]
0x180075193  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@J@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@J@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<long>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<long>>,std::_Iterator_base0>)
0x180075198  nop
0x180075199  mov     dword ptr [rsp+170h+var_10C], esi
0x18007519d  mov     [rbp+70h+Sid], rsi
0x1800751a1  mov     dword ptr [rbp+70h+uBytes], ebx
0x1800751a4  mov     edx, ebx; uBytes
0x1800751a6  lea     ecx, [rsi+40h]; uFlags
0x1800751a9  call    cs:__imp_LocalAlloc
0x1800751af  mov     rdi, rax
0x1800751b2  test    rax, rax
0x1800751b5  jnz     short loc_1800751EE
0x1800751b7  mov     eax, cs:dword_180128170
0x1800751bd  cmp     eax, 3
0x1800751c0  jbe     short loc_1800751E4
0x1800751c2  lea     rax, aLocalallocFail_0; "LocalAlloc failed for pPropertyValueFas"...
0x1800751c9  lea     rdx, byte_18010BEBD
0x1800751d0  mov     [rsp+170h+pSid2], rax
0x1800751d5  lea     rax, [rsp+170h+pSid2]
0x1800751da  mov     [rsp+170h+var_150], rax
0x1800751df  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800751e4  mov     ebx, 8007000Eh
0x1800751e9  jmp     loc_180075B18
0x1800751ee  mov     r12, rsi
0x1800751f1  mov     rax, [r14]
0x1800751f4  mov     r9, rdi
0x1800751f7  lea     r8, [rbp+70h+uBytes]
0x1800751fb  lea     rdx, PROPERTY_TYPE_GET_FAST_RECONNECT_USER_SID
0x180075202  mov     rcx, r14
0x180075205  mov     rax, [rax+210h]
0x18007520c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075211  mov     ebx, eax
0x180075213  cmp     eax, 8007007Ah
0x180075218  jnz     loc_1800752F5
0x18007521e  mov     rcx, rdi; hMem
0x180075221  call    cs:__imp_LocalFree
0x180075227  mov     edx, dword ptr [rbp+70h+uBytes]; uBytes
0x18007522a  mov     ecx, 40h ; '@'; uFlags
0x18007522f  call    cs:__imp_LocalAlloc
0x180075235  mov     rdi, rax
0x180075238  test    rax, rax
0x18007523b  jnz     short loc_18007525B
0x18007523d  mov     eax, cs:dword_180128170
0x180075243  cmp     eax, 3
0x180075246  jbe     short loc_1800751E4
0x180075248  lea     rax, aLocalallocFail; "LocalAlloc failed for pPropertyValueFas"...
0x18007524f  lea     rdx, word_18010BE9A
0x180075256  jmp     loc_1800751D0
0x18007525b  mov     rax, [r14]
0x18007525e  mov     r9, rdi
0x180075261  lea     r8, [rbp+70h+uBytes]
0x180075265  lea     rdx, PROPERTY_TYPE_GET_FAST_RECONNECT_USER_SID
0x18007526c  mov     rcx, r14
0x18007526f  mov     rax, [rax+210h]
0x180075276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007527b  mov     ebx, eax
0x18007527d  test    eax, eax
0x18007527f  jns     loc_18007532F
0x180075285  mov     eax, cs:dword_180128170
0x18007528b  cmp     eax, 3
0x18007528e  jbe     loc_180075AF2
0x180075294  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
0x18007529b  mov     [rsp+170h+pSid2], rax
0x1800752a0  lea     rax, aFailedToQueryF_0; "Failed to query fast reconnect user SID"...
0x1800752a7  mov     [rsp+170h+var_120], rax
0x1800752ac  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800752b3  mov     [rsp+170h+var_128], rax
0x1800752b8  lea     rax, [rsp+170h+pSid2]
0x1800752bd  mov     [rsp+170h+var_138], rax
0x1800752c2  lea     rax, [rsp+170h+var_130]
0x1800752c7  mov     [rsp+170h+var_140], rax
0x1800752cc  lea     rax, [rsp+170h+var_120]
0x1800752d1  lea     rdx, byte_18010BE5D
0x1800752d8  mov     [rsp+170h+var_148], rax
0x1800752dd  lea     rax, [rsp+170h+var_128]
0x1800752e2  mov     [rsp+170h+var_130], ebx
0x1800752e6  mov     [rsp+170h+var_150], rax
0x1800752eb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800752f0  jmp     loc_180075AF2
0x1800752f5  test    eax, eax
0x1800752f7  jns     short loc_18007532F
0x1800752f9  mov     eax, cs:dword_180128170
0x1800752ff  cmp     eax, 3
0x180075302  jbe     loc_180075AF2
0x180075308  lea     rax, aFailedToQueryF_1; "Failed to query fast reconnect user SID"...
0x18007530f  mov     [rsp+170h+var_128], rax
0x180075314  lea     rax, [rsp+170h+var_128]
0x180075319  mov     [rsp+170h+var_150], rax
0x18007531e  lea     rdx, word_18010BE3A
0x180075325  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007532a  jmp     loc_180075AF2
0x18007532f  mov     eax, [rdi+8]
0x180075332  lea     edx, ds:2[rax*2]; uBytes
0x180075339  mov     ecx, 40h ; '@'; uFlags
0x18007533e  call    cs:__imp_LocalAlloc
0x180075344  mov     rsi, rax
0x180075347  mov     eax, 2
0x18007534c  cmp     ax, [rdi]
0x18007534f  jnz     loc_180075AC0
0x180075355  mov     edx, [rdi+8]
0x180075358  mov     r8, [rdi+10h]
0x18007535c  mov     rcx, rsi
0x18007535f  call    cs:__imp__o_wcscpy_s
0x180075365  mov     ecx, cs:dword_180128170
0x18007536b  cmp     ecx, 5
0x18007536e  jbe     short loc_1800753B4
0x180075370  mov     [rsp+170h+var_128], rsi
0x180075375  mov     rax, [rdi+10h]
0x180075379  mov     [rsp+170h+pSid2], rax
0x18007537e  lea     rax, aSettingPenhanc; "Setting pEnhancedFastReconnectUserSID f"...
0x180075385  mov     [rsp+170h+var_120], rax
0x18007538a  lea     rax, [rsp+170h+var_128]
0x18007538f  mov     [rsp+170h+var_140], rax
0x180075394  lea     rax, [rsp+170h+pSid2]
0x180075399  mov     [rsp+170h+var_148], rax
0x18007539e  lea     rax, [rsp+170h+var_120]
0x1800753a3  mov     [rsp+170h+var_150], rax
0x1800753a8  lea     rdx, byte_18010BDFB
0x1800753af  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800753b4  lea     rdx, [rbp+70h+Sid]; Sid
0x1800753b8  mov     rcx, rsi; StringSid
0x1800753bb  call    cs:__imp_ConvertStringSidToSidW
0x1800753c1  test    eax, eax
0x1800753c3  jnz     short loc_1800753F1
0x1800753c5  mov     eax, cs:dword_180128170
0x1800753cb  cmp     eax, 3
0x1800753ce  jbe     loc_180075AED
0x1800753d4  lea     rax, aConvertstrings_1; "ConvertStringSidToSid failed"
0x1800753db  mov     [rsp+170h+var_128], rax
0x1800753e0  lea     rax, [rsp+170h+var_128]
0x1800753e5  lea     rdx, byte_18010BDB5
0x1800753ec  jmp     loc_180075AE3
0x1800753f1  lea     rcx, [rbp+70h+var_B8]; struct ISessionManager **
0x1800753f5  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x1800753fa  mov     ebx, eax
0x1800753fc  test    eax, eax
0x1800753fe  jns     short loc_180075462
0x180075400  mov     eax, cs:dword_180128170
0x180075406  cmp     eax, 3
0x180075409  jbe     loc_180075AF2
0x18007540f  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
0x180075416  mov     [rsp+170h+var_128], rax
0x18007541b  lea     rax, aCutilsGetinsta_1; "CUtils::GetInstanceOfSessionManager"
0x180075422  mov     [rsp+170h+pSid2], rax
0x180075427  lea     rax, aWarningHresult; "Warning HResult failed"
0x18007542e  mov     [rsp+170h+var_120], rax
0x180075433  lea     rax, [rsp+170h+var_128]
0x180075438  mov     [rsp+170h+var_138], rax
0x18007543d  lea     rax, [rsp+170h+var_130]
0x180075442  mov     [rsp+170h+var_140], rax
0x180075447  lea     rax, [rsp+170h+pSid2]
0x18007544c  mov     [rsp+170h+var_148], rax
0x180075451  lea     rax, [rsp+170h+var_120]
0x180075456  lea     rdx, qword_18010BD78
0x18007545d  jmp     loc_1800752E2
0x180075462  mov     rcx, [rbp+70h+var_B8]
0x180075466  mov     rax, [rcx]
0x180075469  lea     rdx, [rbp+70h+var_C0]
0x18007546d  mov     rax, [rax+18h]
0x180075471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075476  mov     ebx, eax
0x180075478  test    eax, eax
0x18007547a  jns     short loc_1800754DE
0x18007547c  mov     eax, cs:dword_180128170
0x180075482  cmp     eax, 3
0x180075485  jbe     loc_180075AF2
0x18007548b  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
0x180075492  mov     [rsp+170h+var_128], rax
0x180075497  lea     rax, aGetsessionlist_1; "GetSessionList"
0x18007549e  mov     [rsp+170h+pSid2], rax
0x1800754a3  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800754aa  mov     [rsp+170h+var_120], rax
0x1800754af  lea     rax, [rsp+170h+var_128]
0x1800754b4  mov     [rsp+170h+var_138], rax
0x1800754b9  lea     rax, [rsp+170h+var_130]
0x1800754be  mov     [rsp+170h+var_140], rax
0x1800754c3  lea     rax, [rsp+170h+pSid2]
0x1800754c8  mov     [rsp+170h+var_148], rax
0x1800754cd  lea     rax, [rsp+170h+var_120]
0x1800754d2  lea     rdx, byte_18010BD3B
0x1800754d9  jmp     loc_1800752E2
0x1800754de  mov     rcx, [rbp+70h+var_C0]
0x1800754e2  mov     rax, [rcx]
0x1800754e5  lea     rdx, [rbp+70h+var_D8]
0x1800754e9  mov     rax, [rax+20h]
0x1800754ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800754f2  mov     ebx, eax
0x1800754f4  test    eax, eax
0x1800754f6  jns     short loc_18007555A
0x1800754f8  mov     eax, cs:dword_180128170
0x1800754fe  cmp     eax, 3
0x180075501  jbe     loc_180075AF2
0x180075507  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
0x18007550e  mov     [rsp+170h+var_128], rax
0x180075513  lea     rax, aGetinstanceofe_1; "GetInstanceOfEnum"
0x18007551a  mov     [rsp+170h+pSid2], rax
0x18007551f  lea     rax, aWarningHresult; "Warning HResult failed"
0x180075526  mov     [rsp+170h+var_120], rax
0x18007552b  lea     rax, [rsp+170h+var_128]
0x180075530  mov     [rsp+170h+var_138], rax
0x180075535  lea     rax, [rsp+170h+var_130]
0x18007553a  mov     [rsp+170h+var_140], rax
0x18007553f  lea     rax, [rsp+170h+pSid2]
0x180075544  mov     [rsp+170h+var_148], rax
0x180075549  lea     rax, [rsp+170h+var_120]
0x18007554e  lea     rdx, word_18010BCFE
0x180075555  jmp     loc_1800752E2
0x18007555a  mov     rax, [r15]
0x18007555d  lea     rcx, [rbp+70h+var_60]
0x180075561  mov     [rsp+170h+var_150], rcx
0x180075566  lea     r9, [rbp+70h+var_E0]
0x18007556a  lea     r8, [rbp+70h+var_D0]
0x18007556e  lea     rdx, [rbp+70h+var_50]
0x180075572  mov     rcx, r15
0x180075575  mov     rax, [rax+88h]
0x18007557c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075581  mov     ebx, eax
0x180075583  test    eax, eax
0x180075585  jns     short loc_1800755E9
0x180075587  mov     eax, cs:dword_180128170
0x18007558d  cmp     eax, 3
0x180075590  jbe     loc_180075AF2
0x180075596  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
0x18007559d  mov     [rsp+170h+var_128], rax
0x1800755a2  lea     rax, aPremotetermina_1; "pRemoteTerminal->GetTerminalTypeExtende"...
0x1800755a9  mov     [rsp+170h+pSid2], rax
0x1800755ae  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800755b5  mov     [rsp+170h+var_120], rax
0x1800755ba  lea     rax, [rsp+170h+var_128]
0x1800755bf  mov     [rsp+170h+var_138], rax
0x1800755c4  lea     rax, [rsp+170h+var_130]
0x1800755c9  mov     [rsp+170h+var_140], rax
0x1800755ce  lea     rax, [rsp+170h+pSid2]
0x1800755d3  mov     [rsp+170h+var_148], rax
0x1800755d8  lea     rax, [rsp+170h+var_120]
0x1800755dd  lea     rdx, byte_18010BCC1
0x1800755e4  jmp     loc_1800752E2
0x1800755e9  lea     r9, [rbp+70h+var_C8]
0x1800755ed  lea     r8, [rbp+70h+var_60]
0x1800755f1  mov     edx, [rbp+70h+var_E0]
0x1800755f4  xor     ecx, ecx
0x1800755f6  call    ?GetInstanceOfDefaultSessionArbitrationFilter@CDefaultSessionArbitrationFilter@@SAJQEAGW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0004@@AEBU_GUID@@PEAPEAUISessionEnumFilter@@@Z; CDefaultSessionArbitrationFilter::GetInstanceOfDefaultSessionArbitrationFilter(ushort * const,__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0004,_GUID const &,ISessionEnumFilter * *)
0x1800755fb  mov     ebx, eax
0x1800755fd  test    eax, eax
0x1800755ff  jns     short loc_180075663
0x180075601  mov     eax, cs:dword_180128170
0x180075607  cmp     eax, 3
0x18007560a  jbe     loc_180075AF2
0x180075610  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
0x180075617  mov     [rsp+170h+var_128], rax
0x18007561c  lea     rax, aGetinstanceofd_0; "GetInstanceOfDefaultSessionArbitrationF"...
0x180075623  mov     [rsp+170h+pSid2], rax
0x180075628  lea     rax, aWarningHresult; "Warning HResult failed"
0x18007562f  mov     [rsp+170h+var_120], rax
0x180075634  lea     rax, [rsp+170h+var_128]
  ... truncated ...
```
