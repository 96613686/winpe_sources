# CSyncEngineRunner::SyncThreadRunner(void)

- ea: `0x180046670`
- end: `0x1800472ca`
- name: `?SyncThreadRunner@CSyncEngineRunner@@AEAAXXZ`
- size: `3162`
- prototype: `void __fastcall(CSyncEngineRunner *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046590`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180008b60`
- `0x180010f40`
- `0x180011314`
- `0x18001133c`
- `0x1800151d8`
- `0x18001520c`
- `0x1800155e0`
- `0x18001588c`
- `0x1800158d4`
- `0x1800234c8`
- `0x180023588`
- `0x180023b8c`
- `0x18002dad0`
- `0x180043958`
- `0x180043f34`
- `0x180044668`
- `0x1800451e0`
- `0x1800454cc`
- `0x180045a50`
- `0x180046670`
- `0x18004bb30`
- `0x18004bc78`
- `0x18004cc84`
- `0x18004cd58`
- `0x180061544`
- `0x1800616a8`
- `0x18006ef40`
- `0x180124460`
- `0x18013e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046a7f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046a7f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800469f4`
- `OLEAUT32!__imp_SysFreeString` at `0x180046d23`
- `OLEAUT32!__imp_SysFreeString` at `0x1800469f4`
- `OLEAUT32!__imp_SysFreeString` at `0x180046d23`
- `KERNEL32!SetThreadpoolTimer` at `0x1800471be`
- `KERNEL32!SetThreadpoolTimer` at `0x1800471be`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180046860`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180046860`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180047089`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180047089`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800468aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800470c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800468aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800470c3`

## string_xrefs

- `0x180046711`: `CSyncEngineRunner::SyncThreadRunner`

## pseudocode

```c
void __fastcall CSyncEngineRunner::SyncThreadRunner(CSyncEngineRunner *this)
{
  CSyncEngineRunner *v1; // rsi
  _BYTE *v2; // rax
  char v3; // al
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int128 *v6; // r8
  struct _FILETIME *v7; // rbx
  struct _FILETIME v8; // r12
  unsigned int *v9; // rcx
  const ATL::CAtlException *v10; // rbx
  _QWORD *v11; // r9
  const unsigned __int16 *v12; // rdx
  _QWORD *v13; // r8
  _QWORD *v14; // rcx
  int v15; // ebx
  bool IsConnectionError; // al
  bool v17; // r12
  _QWORD *v18; // r8
  const wchar_t *p_String2; // rdx
  const wchar_t *v20; // rcx
  __int64 v21; // r12
  __int64 (__fastcall *v22)(__int64, _QWORD, _QWORD); // r13
  const unsigned __int16 *v23; // rdx
  _QWORD *v24; // rax
  int v25; // r12d
  PVOID *v26; // rcx
  _QWORD *v27; // r9
  bool ShouldRetryOnError; // al
  char v29; // cl
  int v30; // eax
  _QWORD *v31; // rcx
  _QWORD *v32; // r8
  struct IUpstreamCallback *v33; // r13
  char *v34; // rbx
  _QWORD *v35; // rcx
  __int64 v36; // rdx
  struct IUpstreamCallback *v37; // rbx
  _QWORD *v38; // rbx
  int NextTimerBackoffSeconds; // ebx
  char v40; // [rsp+30h] [rbp-5F8h]
  int v42; // [rsp+40h] [rbp-5E8h] BYREF
  int v43; // [rsp+44h] [rbp-5E4h]
  char v44; // [rsp+48h] [rbp-5E0h]
  const char *v45; // [rsp+50h] [rbp-5D8h]
  __int64 v46; // [rsp+58h] [rbp-5D0h]
  int v47; // [rsp+60h] [rbp-5C8h]
  char v48; // [rsp+64h] [rbp-5C4h]
  _BYTE v49[3]; // [rsp+65h] [rbp-5C3h] BYREF
  unsigned int v50; // [rsp+68h] [rbp-5C0h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp-5B8h] BYREF
  bool v52; // [rsp+78h] [rbp-5B0h]
  BSTR bstrString; // [rsp+80h] [rbp-5A8h] BYREF
  struct IUpstreamCallback *v54; // [rsp+88h] [rbp-5A0h]
  int pExceptionObject; // [rsp+90h] [rbp-598h] BYREF
  int v56; // [rsp+94h] [rbp-594h] BYREF
  int LastFailureAsHRESULT; // [rsp+98h] [rbp-590h] BYREF
  __int64 v58; // [rsp+A0h] [rbp-588h]
  int v59; // [rsp+A8h] [rbp-580h] BYREF
  int v60; // [rsp+ACh] [rbp-57Ch] BYREF
  int v61; // [rsp+B0h] [rbp-578h] BYREF
  int v62; // [rsp+B4h] [rbp-574h] BYREF
  int v63; // [rsp+B8h] [rbp-570h] BYREF
  struct _FILETIME *v64; // [rsp+C0h] [rbp-568h] BYREF
  char *v65; // [rsp+C8h] [rbp-560h]
  BSTR v66; // [rsp+D0h] [rbp-558h] BYREF
  char *v67; // [rsp+D8h] [rbp-550h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+E0h] [rbp-548h] BYREF
  char v69; // [rsp+E8h] [rbp-540h]
  LPCRITICAL_SECTION v70; // [rsp+F0h] [rbp-538h] BYREF
  char v71; // [rsp+F8h] [rbp-530h]
  _BYTE v72[16]; // [rsp+100h] [rbp-528h] BYREF
  _BYTE v73[16]; // [rsp+110h] [rbp-518h] BYREF
  int v74; // [rsp+120h] [rbp-508h] BYREF
  const ATL::CAtlException *v75; // [rsp+128h] [rbp-500h] BYREF
  const ATL::CAtlException *v76[3]; // [rsp+130h] [rbp-4F8h] BYREF
  const ATL::CAtlException *v77; // [rsp+148h] [rbp-4E0h] BYREF
  const ATL::CAtlException *v78; // [rsp+150h] [rbp-4D8h] BYREF
  const ATL::CAtlException *v79; // [rsp+158h] [rbp-4D0h] BYREF
  const ATL::CAtlException *v80; // [rsp+160h] [rbp-4C8h] BYREF
  char v81[16]; // [rsp+168h] [rbp-4C0h] BYREF
  __int128 v82; // [rsp+178h] [rbp-4B0h] BYREF
  __int64 v83; // [rsp+188h] [rbp-4A0h]
  unsigned __int64 v84; // [rsp+190h] [rbp-498h]
  _QWORD v85[4]; // [rsp+1A0h] [rbp-488h] BYREF
  _QWORD v86[4]; // [rsp+1C0h] [rbp-468h] BYREF
  unsigned int v87; // [rsp+1E0h] [rbp-448h]
  unsigned int v88; // [rsp+1E4h] [rbp-444h]
  _BYTE v89[136]; // [rsp+1F0h] [rbp-438h] BYREF
  wchar_t *String1[39]; // [rsp+278h] [rbp-3B0h] BYREF
  wchar_t *String2; // [rsp+3B0h] [rbp-278h] BYREF
  size_t MaxCount; // [rsp+3C0h] [rbp-268h]
  unsigned __int64 v93; // [rsp+3C8h] [rbp-260h]
  _BYTE v94[200]; // [rsp+3F0h] [rbp-238h] BYREF
  _QWORD v95[39]; // [rsp+4B8h] [rbp-170h] BYREF

  v1 = this;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v3 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 59, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
  }
  if ( (v2[68] & 8) == 0 || v2[65] < 6u )
    goto LABEL_8;
  v3 = 1;
LABEL_9:
  v42 = 0;
  v43 = 991;
  v44 = v3;
  v45 = "CSyncEngineRunner::SyncThreadRunner";
  v46 = 0;
  v65 = (char *)v1 + 160;
  EcsImpersonate::EcsImpersonate((EcsImpersonate *)v49, *((void **)v1 + 20));
  if ( !CSyncEngineRunner::HandleSetFreshOnlySync(v1) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      v5 = 60;
      goto LABEL_137;
    }
    goto LABEL_138;
  }
  v40 = 0;
  CUniqueSyncEngineHolder::CUniqueSyncEngineHolder(v73, (char *)v1 + 88);
  std::set<std::wstring>::set<std::wstring>(v72);
  v82 = 0;
  v83 = 0;
  v84 = 7;
  LOWORD(v82) = 0;
  while ( 1 )
  {
    v50 = 0;
    v67 = (char *)v1 + 120;
    CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(&lpCriticalSection, (char *)v1 + 120);
    v6 = &v82;
    if ( v84 > 7 )
      v6 = (__int128 *)v82;
    CSyncEngineRunner::FindNextPartnershipToSync(v1, &v64, v6, v72);
    pftDueTime = (struct _FILETIME)*((_QWORD *)v1 + 13);
    if ( v64 == *(struct _FILETIME **)&pftDueTime )
    {
      pftDueTime = 0;
    }
    else
    {
      v7 = v64 + 4;
      v8 = v64[8];
      if ( !ResetEvent(*(HANDLE *)(*(_QWORD *)&v8 + 8LL)) )
      {
        HIWORD(v43) = 1037;
        pExceptionObject = EcsGetLastFailureAsHRESULT();
        throw (long *)&pExceptionObject;
      }
      pftDueTime = v8;
      v42 = 0;
      LOWORD(v43) = 1037;
      std::wstring::operator=((char *)v1 + 192, v7);
      v9 = (unsigned int *)v7[4];
      v50 = *v9;
      *v9 = 0;
    }
    if ( v69 )
    {
      LeaveCriticalSection(lpCriticalSection);
      v69 = 0;
    }
    if ( !*(_QWORD *)&pftDueTime )
      break;
    v54 = *(struct IUpstreamCallback **)(*(_QWORD *)&pftDueTime + 32LL);
    v58 = *(_QWORD *)(*(_QWORD *)&pftDueTime + 40LL);
    v10 = *(const ATL::CAtlException **)(*(_QWORD *)&pftDueTime + 48LL);
    v76[2] = v10;
    AuthenticationInfo::AuthenticationInfo((AuthenticationInfo *)v85);
    if ( __eh34_try(0, 1) )
    {
      __eh34_scope_strut(1);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        v11 = (_QWORD *)((char *)v1 + 192);
        if ( *((_QWORD *)v1 + 27) > 7u )
          v11 = (_QWORD *)*v11;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          61,
          (unsigned int)WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids,
          (_DWORD)v11,
          v50);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      if ( *((_QWORD *)v1 + 23) )
      {
        v12 = (const unsigned __int16 *)((char *)v1 + 192);
        if ( *((_QWORD *)v1 + 27) > 7u )
          v12 = *(const unsigned __int16 **)v12;
        ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v12);
        if ( (*(int (__fastcall **)(_QWORD, BSTR))(**((_QWORD **)v1 + 23) + 32LL))(*((_QWORD *)v1 + 23), bstrString) < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 62, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids);
        }
        SysFreeString(bstrString);
      }
      v13 = (_QWORD *)((char *)v1 + 192);
      if ( *((_QWORD *)v1 + 27) > 7u )
        v13 = (_QWORD *)*v13;
      (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD *))(**((_QWORD **)v1 + 2) + 16LL))(*((_QWORD *)v1 + 2), v94, v13);
      (*(void (__fastcall **)(const ATL::CAtlException *, _BYTE *, char *))(*(_QWORD *)v10 + 8LL))(v10, v94, v65);
      v14 = v95;
      if ( v95[3] > 7u )
        v14 = (_QWORD *)v95[0];
      if ( !(unsigned int)_o__wcsicmp(v14, L"Microsoft.SyncShare.UnProvisionedPartnership") )
      {
        v42 = -2134376389;
        HIWORD(v43) = 1085;
        v56 = -2134376389;
        throw (long *)&v56;
      }
      ((void (__stdcall *)(CSyncEngineRunner *, struct CUniqueSyncEngineHolder *, struct ClientPartnershipDescriptor *, struct IUpstreamCallback *, unsigned int, struct AuthenticationInfo *))CSyncEngineRunner::SyncOnePartnership)(
        v1,
        (struct CUniqueSyncEngineHolder *)v73,
        (struct ClientPartnershipDescriptor *)v94,
        v54,
        v50,
        (struct AuthenticationInfo *)v85);
      ClientPartnershipDescriptor::~ClientPartnershipDescriptor((ClientPartnershipDescriptor *)v94);
    }
    if ( __eh34_catch(1) )
    {
      if ( __eh34_catch_type(1, &long `RTTI Type Descriptor', (long *)&v74) )
      {
        v42 = v74;
        v1 = this;
        __eh34_try_continuation(1, &long `RTTI Type Descriptor', &loc_180046AD3);
        goto LABEL_46;
      }
      if ( __eh34_catch_type(1, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        HIWORD(v43) = 1094;
        v42 = -2147024882;
        v1 = this;
        __eh34_try_continuation(1, &std::bad_alloc `RTTI Type Descriptor', &loc_180046B56);
        goto LABEL_46;
      }
      if ( __eh34_catch_type(1, &std::exception `RTTI Type Descriptor', 0) )
      {
        HIWORD(v43) = 1094;
        v42 = -2147418113;
        v1 = this;
        __eh34_try_continuation(1, &std::exception `RTTI Type Descriptor', &loc_180046B5B);
        goto LABEL_46;
      }
      if ( __eh34_catch_type(1, &ATL::CAtlException `RTTI Type Descriptor', &v77) )
      {
        HIWORD(v43) = 1094;
        v42 = *(_DWORD *)v77;
        v1 = this;
        __eh34_try_continuation(1, &ATL::CAtlException `RTTI Type Descriptor', &loc_180046AD3);
      }
    }
LABEL_46:
    v15 = v42;
    v47 = v42;
    v42 = 0;
    IsConnectionError = CEcsWinHttpClient::IsConnectionError(v47);
    v17 = IsConnectionError;
    v52 = IsConnectionError;
    if ( v47 == -2134376389 || IsConnectionError )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 63, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids);
      }
      if ( __eh34_try(0, 3) )
      {
        __eh34_scope_strut(3);
        v48 = 1;
        v18 = (_QWORD *)((char *)v1 + 192);
        if ( *((_QWORD *)v1 + 27) > 7u )
          v18 = (_QWORD *)*v18;
        (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD *))(**((_QWORD **)v1 + 2) + 16LL))(
          *((_QWORD *)v1 + 2),
          v89,
          v18);
        if ( !v17 )
          goto LABEL_61;
        p_String2 = (const wchar_t *)&String2;
        if ( v93 > 7 )
          p_String2 = String2;
        v20 = (const wchar_t *)String1;
        if ( String1[3] > (wchar_t *)7 )
          v20 = String1[0];
        if ( !wcsncmp_0(v20, p_String2, (unsigned int)MaxCount) )
        {
          v42 = v15;
          v48 = 0;
        }
        else
        {
LABEL_61:
          CSyncEngineRunner::RediscoverAndSyncOnePartnership(
            v1,
            (struct CUniqueSyncEngineHolder *)v73,
            (struct ClientPartnershipDescriptor *)v89,
            v54,
            v50,
            (struct AuthenticationInfo *)v85);
        }
        ClientPartnershipDescriptor::~ClientPartnershipDescriptor((ClientPartnershipDescriptor *)v89);
      }
      if ( __eh34_catch(3) )
      {
        if ( __eh34_catch_type(3, &long `RTTI Type Descriptor', (long *)&v59) )
        {
          v42 = v59;
          v1 = this;
          __eh34_try_continuation(3, &long `RTTI Type Descriptor', &loc_180046C3D);
          goto LABEL_63;
        }
        if ( __eh34_catch_type(3, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 1131;
          v42 = -2147024882;
          v1 = this;
          __eh34_try_continuation(3, &std::bad_alloc `RTTI Type Descriptor', &loc_180046C76);
          goto LABEL_63;
        }
        if ( __eh34_catch_type(3, &std::exception `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 1131;
          v42 = -2147418113;
          v1 = this;
          __eh34_try_continuation(3, &std::exception `RTTI Type Descriptor', &loc_180046C78);
          goto LABEL_63;
        }
        if ( __eh34_catch_type(3, &ATL::CAtlException `RTTI Type Descriptor', &v78) )
        {
          HIWORD(v43) = 1131;
          v42 = *(_DWORD *)v78;
          v1 = this;
          __eh34_try_continuation(3, &ATL::CAtlException `RTTI Type Descriptor', &loc_180046C3D);
        }
      }
LABEL_63:
      v15 = v42;
      v47 = v42;
      v42 = 0;
    }
    if ( __eh34_try(0, 5) )
    {
      __eh34_scope_strut(5);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v58 + 8LL))(v58, (unsigned int)v15);
    }
    if ( __eh34_catch(5) )
    {
      if ( __eh34_catch_type(5, &long `RTTI Type Descriptor', (long *)&v60) )
      {
        v42 = v60;
        v1 = this;
        v15 = v47;
        __eh34_try_continuation(5, &long `RTTI Type Descriptor', &loc_180046C7A);
        goto LABEL_64;
      }
      if ( __eh34_catch_type(5, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        HIWORD(v43) = 1142;
        v42 = -2147024882;
        v1 = this;
        v15 = v47;
        __eh34_try_continuation(5, &std::bad_alloc `RTTI Type Descriptor', &loc_180046E15);
        goto LABEL_64;
      }
      if ( __eh34_catch_type(5, &std::exception `RTTI Type Descriptor', 0) )
      {
        HIWORD(v43) = 1142;
        v42 = -2147418113;
        v1 = this;
        v15 = v47;
        __eh34_try_continuation(5, &std::exception `RTTI Type Descriptor', &loc_180046E1A);
        goto LABEL_64;
      }
      if ( __eh34_catch_type(5, &ATL::CAtlException `RTTI Type Descriptor', &v79) )
      {
        HIWORD(v43) = 1142;
        v42 = *(_DWORD *)v79;
        v1 = this;
        v15 = v47;
        __eh34_try_continuation(5, &ATL::CAtlException `RTTI Type Descriptor', &loc_180046C7A);
      }
    }
LABEL_64:
    if ( v42 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 64, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids);
    }
    v42 = 0;
    v21 = *((_QWORD *)v1 + 23);
    if ( v21 )
    {
      v22 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v21 + 40LL);
      v23 = (const unsigned __int16 *)((char *)v1 + 192);
      if ( *((_QWORD *)v1 + 27) > 7u )
        v23 = *(const unsigned __int16 **)v23;
      v24 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v66, v23);
      v25 = v22(v21, *v24, (unsigned int)v15);
      SysFreeString(v66);
      if ( v25 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 65, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids);
      }
    }
    CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(&v70, v67);
    *(_DWORD *)(*(_QWORD *)&pftDueTime + 24LL) = v15;
    if ( v15 >= 0 )
    {
      if ( __eh34_try(0, 11) )
      {
        __eh34_scope_strut(11);
        v37 = v54;
        (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)v54 + 1) + 48LL))((char *)v54 + 8, v87);
        (*(void (__fastcall **)(char *))(*((_QWORD *)v37 + 1) + 16LL))((char *)v37 + 8);
      }
      if ( __eh34_catch(11) )
      {
        if ( __eh34_catch_type(11, &long `RTTI Type Descriptor', (long *)&v63) )
        {
          v42 = v63;
          v1 = this;
          __eh34_try_continuation(11, &long `RTTI Type Descriptor', &loc_180046FFB);
          goto LABEL_112;
        }
        if ( __eh34_catch_type(11, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 1242;
          v42 = -2147024882;
          v1 = this;
          __eh34_try_continuation(11, &std::bad_alloc `RTTI Type Descriptor', &loc_180047099);
          goto LABEL_112;
        }
        if ( __eh34_catch_type(11, &std::exception `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 1242;
          v42 = -2147418113;
          v1 = this;
          __eh34_try_continuation(11, &std::exception `RTTI Type Descriptor', &loc_18004709E);
          goto LABEL_112;
        }
        if ( __eh34_catch_type(11, &ATL::CAtlException `RTTI Type Descriptor', v76) )
        {
          HIWORD(v43) = 1242;
          v42 = *(_DWORD *)v76[0];
          v1 = this;
          __eh34_try_continuation(11, &ATL::CAtlException `RTTI Type Descriptor', &loc_180046FFB);
        }
      }
LABEL_112:
      if ( v42 < 0 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          v36 = 70;
LABEL_117:
          WPP_SF_d(v35[7], v36, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids);
        }
      }
LABEL_118:
      v42 = 0;
      goto LABEL_119;
    }
    v26 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 66, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids);
      v26 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v15 == -2146762484 )
    {
      if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 68) & 8) != 0 && *((_BYTE *)v26 + 65) >= 2u )
      {
        v27 = (_QWORD *)((char *)v1 + 192);
        if ( *((_QWORD *)v1 + 27) > 7u )
          v27 = (_QWORD *)*v27;
        WPP_SF_Sd(
          (unsigned int)v26[7],
          67,
          (unsigned int)WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids,
          (_DWORD)v27,
          12);
      }
      if ( __eh34_try(0, 7) )
      {
        __eh34_scope_strut(7);
        CSyncEngineRunner::RevokePartnership(v1);
      }
      if ( __eh34_catch(7) )
      {
        if ( __eh34_catch_type(7, &long `RTTI Type Descriptor', (long *)&v61) )
        {
          v42 = v61;
          v1 = this;
          v15 = v47;
          __eh34_try_continuation(7, &long `RTTI Type Descriptor', &loc_180046E1F);
          goto LABEL_89;
        }
        if ( __eh34_catch_type(7, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 1178;
          v42 = -2147024882;
          v1 = this;
          v15 = v47;
          __eh34_try_continuation(7, &std::bad_alloc `RTTI Type Descriptor', &loc_180046E9F);
          goto LABEL_89;
        }
        if ( __eh34_catch_type(7, &std::exception `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 1178;
          v42 = -2147418113;
          v1 = this;
          v15 = v47;
          __eh34_try_continuation(7, &std::exception `RTTI Type Descriptor', &loc_180046EA4);
          goto LABEL_89;
        }
        if ( __eh34_catch_type(7, &ATL::CAtlException `RTTI Type Descriptor', &v80) )
        {
          HIWORD(v43) = 1178;
          v42 = *(_DWORD *)v80;
          v1 = this;
          v15 = v47;
          __eh34_try_continuation(7, &ATL::CAtlException `RTTI Type Descriptor', &loc_180046E1F);
        }
      }
LABEL_89:
      if ( v42 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 68, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids);
      }
      v42 = 0;
    }
    ShouldRetryOnError = CSyncEngineRunner::ShouldRetryOnError(v15);
    v29 = v40;
    if ( ShouldRetryOnError )
      v29 = 1;
    v40 = v29;
    v30 = *(_DWORD *)pftDueTime.dwLowDateTime;
    if ( v15 == -2134375680 )
      *(_DWORD *)pftDueTime.dwLowDateTime = v50 | v30;
    else
      *(_DWORD *)pftDueTime.dwLowDateTime = v30 | v50 & 0xFFFFFFF7;
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      v72,
      v81,
      (char *)v1 + 192);
    if ( v15 == -2134375680 )
    {
      if ( __eh34_try(0, 9) )
      {
        __eh34_scope_strut(9);
        v31 = v86;
        if ( v86[3] > 7u )
          v31 = (_QWORD *)v86[0];
        v32 = v85;
        if ( v85[3] > 7u )
          v32 = (_QWORD *)v85[0];
        v33 = v54;
        v34 = (char *)v54 + 8;
        (*(void (__fastcall **)(char *, _QWORD, _QWORD *, _QWORD, _QWORD *))(*((_QWORD *)v54 + 1) + 8LL))(
          (char *)v54 + 8,
          v87,
          v32,
          v88,
          v31);
        (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)v33 + 1) + 48LL))(v34, v87);
      }
      if ( __eh34_catch(9) )
      {
        if ( __eh34_catch_type(9, &long `RTTI Type Descriptor', (long *)&v62) )
        {
          v42 = v62;
          v1 = this;
          __eh34_try_continuation(9, &long `RTTI Type Descriptor', &loc_180046F76);
          goto LABEL_107;
        }
        if ( __eh34_catch_type(9, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 1225;
          v42 = -2147024882;
          v1 = this;
          __eh34_try_continuation(9, &std::bad_alloc `RTTI Type Descriptor', &loc_180046FC3);
          goto LABEL_107;
        }
        if ( __eh34_catch_type(9, &std::exception `RTTI Type Descriptor', 0) )
        {
          HIWORD(v43) = 1225;
          v42 = -2147418113;
          v1 = this;
          __eh34_try_continuation(9, &std::exception `RTTI Type Descriptor', &loc_180046FC5);
          goto LABEL_107;
        }
        if ( __eh34_catch_type(9, &ATL::CAtlException `RTTI Type Descriptor', &v75) )
        {
          HIWORD(v43) = 1225;
          v42 = *(_DWORD *)v75;
          v1 = this;
          __eh34_try_continuation(9, &ATL::CAtlException `RTTI Type Descriptor', &loc_180046F76);
        }
      }
LABEL_107:
      if ( v42 < 0 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          v36 = 69;
          goto LABEL_117;
        }
      }
      goto LABEL_118;
    }
LABEL_119:
    v38 = (_QWORD *)((char *)v1 + 192);
    std::wstring::operator=(&v82, (char *)v1 + 192);
    *((_QWORD *)v1 + 26) = 0;
    if ( *((_QWORD *)v1 + 27) > 7u )
      v38 = (_QWORD *)*v38;
    *(_WORD *)v38 = 0;
    if ( !SetEvent(*(HANDLE *)(*(_QWORD *)&pftDueTime + 8LL)) )
    {
      HIWORD(v43) = 1255;
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      throw (long *)&LastFailureAsHRESULT;
    }
    v42 = 0;
    LOWORD(v43) = 1255;
    if ( v71 )
    {
      LeaveCriticalSection(v70);
      v71 = 0;
    }
    DiscoverSyncShareResponseType::~DiscoverSyncShareResponseType((DiscoverSyncShareResponseType *)v85);
  }
  std::wstring::_Tidy_deallocate(&v82);
  std::set<std::wstring>::~set<std::wstring>(v72);
  CUniqueSyncEngineHolder::~CUniqueSyncEngineHolder((CUniqueSyncEngineHolder *)v73);
  if ( v42 < 0 || v40 )
  {
    NextTimerBackoffSeconds = CBackoffTimerValueProvider::GetNextTimerBackoffSeconds((CSyncEngineRunner *)((char *)v1 + 240));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 71, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids);
    }
    bstrString = 0;
    pftDueTime = (struct _FILETIME)(10000000LL * -NextTimerBackoffSeconds);
    SetThreadpoolTimer(*((PTP_TIMER *)v1 + 22), &pftDueTime, 0, 0);
  }
  else
  {
    CBackoffTimerValueProvider::Reset((CSyncEngineRunner *)((char *)v1 + 240));
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    v5 = 72;
LABEL_137:
    WPP_SF_(v4[7], v5, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids);
  }
LABEL_138:
  EcsImpersonate::~EcsImpersonate((EcsImpersonate *)v49);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v42);
}

```

## disassembly

```asm
0x180046670  mov     [rsp+arg_8], rbx
0x180046675  mov     [rsp+arg_10], rsi
0x18004667a  push    rdi
0x18004667b  push    r12
0x18004667d  push    r13
0x18004667f  push    r14
0x180046681  push    r15
0x180046683  sub     rsp, 600h
0x18004668a  mov     rax, cs:__security_cookie
0x180046691  xor     rax, rsp
0x180046694  mov     [rsp+628h+var_38], rax
0x18004669c  mov     rsi, rcx
0x18004669f  mov     [rsp+628h+var_5F0], rcx
0x1800466a4  lea     r14, WPP_GLOBAL_Control
0x1800466ab  mov     rax, cs:WPP_GLOBAL_Control
0x1800466b2  cmp     rax, r14
0x1800466b5  jz      short loc_1800466DF
0x1800466b7  test    byte ptr [rax+44h], 8
0x1800466bb  jz      short loc_1800466F8
0x1800466bd  cmp     byte ptr [rax+41h], 6
0x1800466c1  jb      short loc_1800466DF
0x1800466c3  mov     edx, 3Bh ; ';'
0x1800466c8  lea     r8, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids
0x1800466cf  mov     rcx, [rax+38h]
0x1800466d3  call    WPP_SF_
0x1800466d8  mov     rax, cs:WPP_GLOBAL_Control
0x1800466df  test    byte ptr [rax+44h], 8
0x1800466e3  jz      short loc_1800466F8
0x1800466e5  cmp     byte ptr [rax+41h], 6
0x1800466e9  jb      short loc_1800466F8
0x1800466eb  mov     r15d, 1
0x1800466f1  mov     al, r15b
0x1800466f4  xor     edi, edi
0x1800466f6  jmp     short loc_180046701
0x1800466f8  xor     edi, edi
0x1800466fa  mov     al, dil
0x1800466fd  lea     r15d, [rdi+1]
0x180046701  mov     [rsp+628h+var_5E8], edi
0x180046705  mov     [rsp+628h+var_5E4], 3DFh
0x18004670d  mov     [rsp+628h+var_5E0], al
0x180046711  lea     rax, aCsyncenginerun_7; "CSyncEngineRunner::SyncThreadRunner"
0x180046718  mov     [rsp+628h+var_5D8], rax
0x18004671d  mov     [rsp+628h+var_5D0], rdi
0x180046722  lea     rdx, [rsi+0A0h]
0x180046729  mov     [rsp+628h+var_560], rdx
0x180046731  mov     rdx, [rdx]; void *
0x180046734  lea     rcx, [rsp+628h+var_5C3]; this
0x180046739  call    ??0EcsImpersonate@@QEAA@PEAX@Z; EcsImpersonate::EcsImpersonate(void *)
0x18004673e  nop
0x18004673f  mov     rcx, rsi; this
0x180046742  call    ?HandleSetFreshOnlySync@CSyncEngineRunner@@AEAA_NXZ; CSyncEngineRunner::HandleSetFreshOnlySync(void)
0x180046747  test    al, al
0x180046749  jnz     short loc_180046779
0x18004674b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046752  cmp     rcx, r14
0x180046755  jz      loc_1800471F2
0x18004675b  test    byte ptr [rcx+44h], 8
0x18004675f  jz      loc_1800471F2
0x180046765  cmp     byte ptr [rcx+41h], 4
0x180046769  jb      loc_1800471F2
0x18004676f  mov     edx, 3Ch ; '<'
0x180046774  jmp     loc_1800471E1
0x180046779  mov     [rsp+628h+var_5F8], dil
0x18004677e  lea     rdx, [rsi+58h]
0x180046782  lea     rcx, [rsp+628h+var_518]
0x18004678a  call    ??0CUniqueSyncEngineHolder@@QEAA@AEAV?$shared_ptr@VIUniqueSyncEngine@@@std@@@Z; CUniqueSyncEngineHolder::CUniqueSyncEngineHolder(std::shared_ptr<IUniqueSyncEngine> &)
0x18004678f  nop
0x180046790  lea     rcx, [rsp+628h+var_528]
0x180046798  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x18004679d  nop
0x18004679e  xorps   xmm0, xmm0
0x1800467a1  movups  [rsp+628h+var_4B0], xmm0
0x1800467a9  mov     [rsp+628h+var_4A0], rdi
0x1800467b1  mov     [rsp+628h+var_498], rdi
0x1800467b9  mov     [rsp+628h+var_4A0], rdi
0x1800467c1  mov     [rsp+628h+var_498], 7
0x1800467cd  mov     word ptr [rsp+628h+var_4B0], di
0x1800467d5  mov     r13d, 40Dh
0x1800467db  mov     [rsp+628h+var_5C0], edi
0x1800467df  lea     rdx, [rsi+78h]
0x1800467e3  mov     [rsp+628h+var_550], rdx
0x1800467eb  lea     rcx, [rsp+628h+lpCriticalSection]
0x1800467f3  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x1800467f8  nop
0x1800467f9  lea     r8, [rsp+628h+var_4B0]
0x180046801  cmp     [rsp+628h+var_498], 7
0x18004680a  cmova   r8, qword ptr [rsp+628h+var_4B0]
0x180046813  lea     r9, [rsp+628h+var_528]
0x18004681b  lea     rdx, [rsp+628h+var_568]
0x180046823  mov     rcx, rsi
0x180046826  call    ?FindNextPartnershipToSync@CSyncEngineRunner@@AEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPartnershipSyncState@@U?$default_delete@UPartnershipSyncState@@@std@@@2@@std@@@std@@@std@@@std@@PEBGAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@@Z; CSyncEngineRunner::FindNextPartnershipToSync(ushort const *,std::set<std::wstring> &)
0x18004682b  mov     rcx, [rsi+68h]
0x18004682f  mov     qword ptr [rsp+628h+pftDueTime.dwLowDateTime], rcx
0x180046834  mov     rax, [rsp+628h+var_568]
0x18004683c  cmp     rax, rcx
0x18004683f  jnz     short loc_180046848
0x180046841  mov     qword ptr [rsp+628h+pftDueTime.dwLowDateTime], rdi
0x180046846  jmp     short loc_180046898
0x180046848  lea     rbx, [rax+20h]
0x18004684c  mov     r12, [rbx+20h]
0x180046850  mov     eax, [rsp+628h+var_5E8]
0x180046854  mov     [rsp+628h+var_5E8], eax
0x180046858  mov     rcx, [rbx+20h]
0x18004685c  mov     rcx, [rcx+8]; hEvent
0x180046860  call    cs:__imp_ResetEvent
0x180046866  test    eax, eax
0x180046868  jz      loc_180047234
0x18004686e  mov     qword ptr [rsp+628h+pftDueTime.dwLowDateTime], r12
0x180046873  mov     [rsp+628h+var_5E8], edi
0x180046877  mov     word ptr [rsp+628h+var_5E4], r13w
0x18004687d  lea     rcx, [rsi+0C0h]
0x180046884  mov     rdx, rbx
0x180046887  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004688c  mov     rcx, [rbx+20h]
0x180046890  mov     eax, [rcx]
0x180046892  mov     [rsp+628h+var_5C0], eax
0x180046896  mov     [rcx], edi
0x180046898  cmp     [rsp+628h+var_540], dil
0x1800468a0  jz      short loc_1800468B8
0x1800468a2  mov     rcx, [rsp+628h+lpCriticalSection]; lpCriticalSection
0x1800468aa  call    cs:__imp_LeaveCriticalSection
0x1800468b0  mov     [rsp+628h+var_540], dil
0x1800468b8  mov     rcx, qword ptr [rsp+628h+pftDueTime.dwLowDateTime]
0x1800468bd  test    rcx, rcx
0x1800468c0  jz      loc_1800470E3
0x1800468c6  mov     rax, [rcx+20h]
0x1800468ca  mov     [rsp+628h+var_5A0], rax
0x1800468d2  mov     rax, [rcx+28h]
0x1800468d6  mov     [rsp+628h+var_588], rax
0x1800468de  mov     rbx, [rcx+30h]
0x1800468e2  mov     [rsp+628h+var_4E8], rbx
0x1800468ea  lea     rcx, [rsp+628h+var_488]; this
0x1800468f2  call    ??0AuthenticationInfo@@QEAA@XZ; AuthenticationInfo::AuthenticationInfo(void)
0x1800468f7  nop
0x1800468f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800468ff  cmp     rcx, r14
0x180046902  jz      short loc_18004694D
0x180046904  test    byte ptr [rcx+44h], 8
0x180046908  jz      short loc_18004694D
0x18004690a  cmp     byte ptr [rcx+41h], 4
0x18004690e  jb      short loc_18004694D
0x180046910  cmp     qword ptr [rsi+0D8h], 7
0x180046918  jbe     short loc_18004691F
0x18004691a  mov     al, r15b
0x18004691d  jmp     short loc_180046922
0x18004691f  mov     al, dil
0x180046922  lea     r9, [rsi+0C0h]
0x180046929  test    al, al
0x18004692b  jz      short loc_180046930
0x18004692d  mov     r9, [r9]
0x180046930  mov     edx, 3Dh ; '='
0x180046935  mov     eax, [rsp+628h+var_5C0]
0x180046939  mov     [rsp+628h+var_608], eax
0x18004693d  lea     r8, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids
0x180046944  mov     rcx, [rcx+38h]
0x180046948  call    WPP_SF_Sd
0x18004694d  mov     rcx, [rsp+628h+var_588]
0x180046955  mov     rax, [rcx]
0x180046958  mov     rax, [rax+10h]
0x18004695c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046961  cmp     [rsi+0B8h], rdi
0x180046968  jz      loc_1800469FA
0x18004696e  cmp     qword ptr [rsi+0D8h], 7
0x180046976  jbe     short loc_18004697D
0x180046978  mov     al, r15b
0x18004697b  jmp     short loc_180046980
0x18004697d  mov     al, dil
0x180046980  lea     rdx, [rsi+0C0h]
0x180046987  test    al, al
0x180046989  jz      short loc_18004698E
0x18004698b  mov     rdx, [rdx]; unsigned __int16 *
0x18004698e  lea     rcx, [rsp+628h+bstrString]; this
0x180046996  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18004699b  nop
0x18004699c  mov     rcx, [rsi+0B8h]
0x1800469a3  mov     rax, [rcx]
0x1800469a6  mov     rdx, [rsp+628h+bstrString]
0x1800469ae  mov     rax, [rax+20h]
0x1800469b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469b7  test    eax, eax
0x1800469b9  jns     short loc_1800469EC
0x1800469bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800469c2  cmp     rcx, r14
0x1800469c5  jz      short loc_1800469EC
0x1800469c7  test    byte ptr [rcx+44h], 8
0x1800469cb  jz      short loc_1800469EC
0x1800469cd  cmp     byte ptr [rcx+41h], 3
0x1800469d1  jb      short loc_1800469EC
0x1800469d3  mov     edx, 3Eh ; '>'
0x1800469d8  mov     r9d, eax
0x1800469db  lea     r8, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids
0x1800469e2  mov     rcx, [rcx+38h]
0x1800469e6  call    WPP_SF_d
0x1800469eb  nop
0x1800469ec  mov     rcx, [rsp+628h+bstrString]; bstrString
0x1800469f4  call    cs:__imp_SysFreeString
0x1800469fa  cmp     qword ptr [rsi+0D8h], 7
0x180046a02  jbe     short loc_180046A09
0x180046a04  mov     al, r15b
0x180046a07  jmp     short loc_180046A0C
0x180046a09  mov     al, dil
0x180046a0c  lea     r8, [rsi+0C0h]
0x180046a13  test    al, al
0x180046a15  jz      short loc_180046A1A
0x180046a17  mov     r8, [r8]
0x180046a1a  mov     rcx, [rsi+10h]
0x180046a1e  mov     rax, [rcx]
0x180046a21  lea     rdx, [rsp+628h+var_238]
0x180046a29  mov     rax, [rax+10h]
0x180046a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a32  nop
0x180046a33  mov     rax, [rbx]
0x180046a36  mov     r8, [rsp+628h+var_560]
0x180046a3e  lea     rdx, [rsp+628h+var_238]
0x180046a46  mov     rcx, rbx
0x180046a49  mov     rax, [rax+8]
0x180046a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a52  cmp     [rsp+628h+var_158], 7
0x180046a5b  jbe     short loc_180046A62
0x180046a5d  mov     al, r15b
0x180046a60  jmp     short loc_180046A65
0x180046a62  mov     al, dil
0x180046a65  lea     rcx, [rsp+628h+var_170]
0x180046a6d  test    al, al
0x180046a6f  cmovnz  rcx, [rsp+628h+var_170]
0x180046a78  lea     rdx, aMicrosoftSyncs; "Microsoft.SyncShare.UnProvisionedPartne"...
0x180046a7f  call    cs:__imp__o__wcsicmp
0x180046a85  test    eax, eax
0x180046a87  jz      loc_180047260
0x180046a8d  lea     rax, [rsp+628h+var_488]
0x180046a95  mov     [rsp+628h+var_600], rax; struct AuthenticationInfo *
0x180046a9a  mov     eax, [rsp+628h+var_5C0]
0x180046a9e  mov     [rsp+628h+var_608], eax; unsigned int
0x180046aa2  mov     r9, [rsp+628h+var_5A0]; struct IUpstreamCallback *
0x180046aaa  lea     r8, [rsp+628h+var_238]; struct ClientPartnershipDescriptor *
0x180046ab2  lea     rdx, [rsp+628h+var_518]; struct CUniqueSyncEngineHolder *
0x180046aba  mov     rcx, rsi; this
0x180046abd  call    ?SyncOnePartnership@CSyncEngineRunner@@AEAAXAEAVCUniqueSyncEngineHolder@@AEAVClientPartnershipDescriptor@@PEAVIUpstreamCallback@@KAEAUAuthenticationInfo@@@Z; CSyncEngineRunner::SyncOnePartnership(CUniqueSyncEngineHolder &,ClientPartnershipDescriptor &,IUpstreamCallback *,ulong,AuthenticationInfo &)
0x180046ac2  nop
0x180046ac3  lea     rcx, [rsp+628h+var_238]; this
0x180046acb  call    ??1ClientPartnershipDescriptor@@QEAA@XZ; ClientPartnershipDescriptor::~ClientPartnershipDescriptor(void)
0x180046ad0  nop
0x180046ad1  jmp     short loc_180046AE7
0x180046ad3  mov     rsi, [rsp+628h+var_5F0]
0x180046ad8  mov     r15d, 1
0x180046ade  xor     edi, edi
0x180046ae0  lea     r14, WPP_GLOBAL_Control
0x180046ae7  mov     ebx, [rsp+628h+var_5E8]
0x180046aeb  mov     [rsp+628h+var_5C8], ebx
0x180046aef  mov     [rsp+628h+var_5E8], edi
0x180046af3  mov     ecx, ebx; int
0x180046af5  call    ?IsConnectionError@CEcsWinHttpClient@@SA_NJ@Z; CEcsWinHttpClient::IsConnectionError(long)
0x180046afa  mov     r12b, al
0x180046afd  mov     [rsp+628h+var_5B0], al
0x180046b01  cmp     ebx, 80C8003Bh
0x180046b07  jz      short loc_180046B11
0x180046b09  test    al, al
0x180046b0b  jz      loc_180046C5D
0x180046b11  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b18  cmp     rcx, r14
0x180046b1b  jz      short loc_180046B42
0x180046b1d  test    byte ptr [rcx+44h], 8
0x180046b21  jz      short loc_180046B42
0x180046b23  cmp     byte ptr [rcx+41h], 4
0x180046b27  jb      short loc_180046B42
0x180046b29  mov     edx, 3Fh ; '?'
0x180046b2e  mov     r9d, ebx
0x180046b31  lea     r8, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids
0x180046b38  mov     rcx, [rcx+38h]
0x180046b3c  call    WPP_SF_d
0x180046b41  nop
0x180046b42  mov     [rsp+628h+var_5C4], r15b
0x180046b47  cmp     qword ptr [rsi+0D8h], 7
0x180046b4f  jbe     short loc_180046B60
0x180046b51  mov     al, r15b
0x180046b54  jmp     short loc_180046B63
0x180046b56  jmp     loc_180046AD3
0x180046b5b  jmp     loc_180046AD3
0x180046b60  mov     al, dil
0x180046b63  lea     r8, [rsi+0C0h]
0x180046b6a  test    al, al
0x180046b6c  jz      short loc_180046B71
0x180046b6e  mov     r8, [r8]
0x180046b71  mov     rcx, [rsi+10h]
0x180046b75  mov     rax, [rcx]
0x180046b78  lea     rdx, [rsp+628h+var_438]
0x180046b80  mov     rax, [rax+10h]
0x180046b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b89  nop
0x180046b8a  test    r12b, r12b
0x180046b8d  jz      short loc_180046BF7
0x180046b8f  cmp     [rsp+628h+var_260], 7
0x180046b98  jbe     short loc_180046B9F
0x180046b9a  mov     al, r15b
0x180046b9d  jmp     short loc_180046BA2
0x180046b9f  mov     al, dil
0x180046ba2  lea     rdx, [rsp+628h+String2]
0x180046baa  test    al, al
0x180046bac  cmovnz  rdx, [rsp+628h+String2]; String2
0x180046bb5  cmp     [rsp+628h+var_398], 7
  ... truncated ...
```
