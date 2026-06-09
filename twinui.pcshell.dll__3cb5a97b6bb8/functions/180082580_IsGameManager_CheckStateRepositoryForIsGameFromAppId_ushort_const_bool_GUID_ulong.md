# IsGameManager::CheckStateRepositoryForIsGameFromAppId(ushort const *,bool *,_GUID *,ulong *)

- ea: `0x180082580`
- end: `0x18008338f`
- name: `?CheckStateRepositoryForIsGameFromAppId@IsGameManager@@AEAAJPEBGPEA_NPEAU_GUID@@PEAK@Z`
- size: `3599`
- prototype: `int(IsGameManager *__hidden this, const unsigned __int16 *, bool *, struct _GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800821f0`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180031c70`
- `0x180082580`
- `0x180083398`
- `0x1800833b0`
- `0x18008a6f0`
- `0x1801f3738`
- `0x180356360`
- `0x18039b6c0`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800832ca`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800832e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180083300`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008331b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800832ca`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800832e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180083300`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008331b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180082901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180082901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180082634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180082790`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008297d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800829e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180082634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180082790`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008297d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800829e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082918`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082b13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082c03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082cb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082d5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082df4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082eaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082ed9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082feb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008309b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800830ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008318d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800831dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083215`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082918`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082b13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082c03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082cb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082d5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082df4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082eaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082ed9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082feb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008309b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800830ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008318d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800831dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180083215`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082ad9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800826dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082860`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082c12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082cc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082d6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082ee8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082ffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800830d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800826dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082860`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082c12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082cc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082d6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082ee8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082ffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800830d9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180082afa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180082afa`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008265f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800829a8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008265f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800829a8`

## string_xrefs

- `0x180082b59`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180082be9`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180082c97`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180082d45`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180082e8e`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180082f79`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180082fb4`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180082fd1`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x18008307f`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180083173`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x1800831f9`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180083254`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x18008329d`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall IsGameManager::CheckStateRepositoryForIsGameFromAppId(
        IsGameManager *this,
        unsigned __int16 *a2,
        bool *a3,
        struct _GUID *a4,
        unsigned int *a5)
{
  IsGameManager *v6; // rdi
  unsigned int v7; // r15d
  void *v8; // r14
  HSTRING v9; // rbx
  struct _GUID *v10; // r9
  unsigned int *v11; // r10
  bool v12; // r12
  HSTRING v13; // rdi
  int ActivationFactory; // eax
  unsigned __int16 **v15; // r8
  unsigned int v16; // edi
  int PackageFullNameFromAppId; // edi
  unsigned __int64 v18; // rdx
  HRESULT v19; // edi
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64, HSTRING, _QWORD); // rsi
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rdx
  bool v30; // zf
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rsi
  __int64 (__fastcall *v36)(__int64, _QWORD, HSTRING, __int64 *); // rdi
  int v37; // eax
  unsigned int v38; // edi
  HSTRING v39; // rdi
  int v40; // eax
  unsigned int v41; // edi
  __int64 v42; // rdi
  __int64 (__fastcall *v43)(__int64, __int64, HSTRING, __int64 *); // rsi
  int v44; // eax
  unsigned int v45; // edi
  int v46; // eax
  unsigned int v47; // edi
  __int64 v48; // rsi
  __int64 (__fastcall *v49)(__int64, _QWORD, HSTRING *); // rdi
  int v50; // eax
  int v51; // eax
  unsigned int v52; // edi
  int v53; // eax
  const WCHAR *StringRawBuffer; // rax
  HSTRING v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  __int64 v75; // rdx
  HSTRING v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  int updated; // eax
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  HSTRING v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  __int64 v90; // rcx
  int v91; // eax
  __int64 v92; // rcx
  int v93; // eax
  int v94; // edi
  __int64 v95; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int *bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v99; // [rsp+30h] [rbp-D0h] BYREF
  bool v100[7]; // [rsp+31h] [rbp-CFh] BYREF
  __int64 v101; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v102; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v103; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v104; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v105; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v106; // [rsp+60h] [rbp-A0h] BYREF
  int v107[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v108; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  __int64 v110; // [rsp+80h] [rbp-80h]
  __int64 v111; // [rsp+88h] [rbp-78h]
  struct _GUID *v112[2]; // [rsp+90h] [rbp-70h] BYREF
  HSTRING v113; // [rsp+A0h] [rbp-60h]
  bool *v114; // [rsp+A8h] [rbp-58h]
  IsGameManager *v115; // [rsp+B0h] [rbp-50h]
  unsigned int *v116[2]; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING string; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v112[0] = a4;
  v114 = a3;
  v6 = this;
  v115 = this;
  v116[0] = a5;
  v7 = 0;
  v103 = 0;
  v104 = 0;
  v102 = 0;
  v101 = 0;
  v8 = 0;
  pv = 0;
  v110 = 0;
  v111 = 0;
  v9 = 0;
  v113 = 0;
  v108 = 0;
  v100[0] = 0;
  v99 = 0;
  *a3 = 0;
  if ( IsCheckStateRepositoryMocked(v100, &v99) )
  {
    v12 = v100[0];
    LOBYTE(v29) = v99;
LABEL_32:
    if ( v12 )
    {
      v30 = (_BYTE)v29 == 0;
    }
    else
    {
      v30 = (_BYTE)v29 == 0;
      if ( !(_BYTE)v29 )
      {
        *(_OWORD *)v116 = xmmword_180769B30;
        if ( (*(int (__fastcall **)(_QWORD, unsigned __int16 *, unsigned int **, struct _GUID *))(**((_QWORD **)v6 + 2)
                                                                                                + 40LL))(
               *((_QWORD *)v6 + 2),
               a2,
               v116,
               v10) >= 0 )
        {
          LODWORD(v106) = 0;
          LODWORD(v105) = 4;
          v95 = *((_QWORD *)v6 + 2);
          *(_OWORD *)v112 = *(_OWORD *)v116;
          if ( (*(int (__fastcall **)(__int64, struct _GUID **, __int64, HSTRING *))(*(_QWORD *)v95 + 64LL))(
                 v95,
                 v112,
                 11,
                 &v106) >= 0 )
          {
            if ( (_DWORD)v106 )
            {
              v92 = *((_QWORD *)v6 + 2);
              *(_OWORD *)v112 = *(_OWORD *)v116;
              v93 = (*(__int64 (__fastcall **)(__int64, struct _GUID **))(*(_QWORD *)v92 + 8LL))(v92, v112);
              v94 = v93;
              if ( v93 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x559,
                  (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
                  (const char *)(unsigned int)v93,
                  (int)&v105);
                GameDVRTraceProvider::IsGameManager_UpdateGameConfigStoreFromKGL_RemoveError(v94);
              }
            }
          }
        }
LABEL_35:
        if ( v9 )
          WindowsDeleteString(v9);
        if ( v8 )
          CoTaskMemFree(v8);
        v31 = v101;
        if ( v101 )
        {
          v101 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        }
        v32 = v102;
        if ( v102 )
        {
          v102 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        }
        v33 = v104;
        if ( v104 )
        {
          v104 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        }
        v34 = v103;
        if ( v103 )
        {
          v103 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        }
        return 0;
      }
    }
    updated = IsGameManager::UpdateGameConfigStoreForStoreApp(v6, a2, !v30, v10, v11);
    if ( updated < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x547,
        (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
        (const char *)(unsigned int)updated,
        bIgnoreCaseb);
    goto LABEL_35;
  }
  v12 = 0;
  v99 = 0;
  if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v13 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v104);
  ActivationFactory = RoGetActivationFactory(v13, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v104);
  v16 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x508,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)ActivationFactory,
      bIgnoreCase);
    v56 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    }
    v57 = v102;
    if ( v102 )
    {
      v102 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    v58 = v104;
    if ( v104 )
    {
      v104 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    }
    v59 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    return v16;
  }
  v110 = -1;
  v111 = -1;
  PackageFullNameFromAppId = CallerIdentity::GetPackageFullNameFromAppId(
                               (CallerIdentity *)a2,
                               (const unsigned __int16 *)&pv,
                               v15);
  if ( PackageFullNameFromAppId < 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    v20 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = v102;
    if ( v102 )
    {
      v102 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v104;
    if ( v104 )
    {
      v104 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    return (unsigned int)PackageFullNameFromAppId;
  }
  v8 = pv;
  if ( !pv )
  {
    v19 = -2147467261;
    goto LABEL_184;
  }
  v105 = 0;
  v18 = -1;
  do
    ++v18;
  while ( *((_WORD *)pv + v18) );
  if ( v18 <= 0xFFFFFFFF )
  {
    v19 = WindowsCreateString((PCNZWCH)pv, v18, &v105);
    if ( v19 >= 0 )
    {
      v9 = v105;
      v113 = v105;
      WindowsDeleteString(0);
    }
  }
  else
  {
    v19 = -2147024362;
  }
  if ( v19 < 0 )
  {
LABEL_184:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50C,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)v19,
      bIgnoreCase);
    if ( !v9 )
      goto LABEL_186;
    goto LABEL_185;
  }
  v35 = v104;
  v36 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v104 + 368LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v103);
  v37 = v36(v35, 0, v9, &v103);
  v38 = v37;
  if ( v37 == -2147023728 )
  {
    if ( v9 )
      WindowsDeleteString(v9);
    if ( v8 )
      CoTaskMemFree(v8);
    v72 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    }
    v73 = v102;
    if ( v102 )
    {
      v102 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    }
    v74 = v104;
    if ( v104 )
    {
      v104 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    }
    v75 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    }
    return 2147943568LL;
  }
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50F,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)v37,
      bIgnoreCase);
    if ( v9 )
      WindowsDeleteString(v9);
    if ( v8 )
      CoTaskMemFree(v8);
    v64 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    }
    v65 = v102;
    if ( v102 )
    {
      v102 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    }
    v66 = v104;
    if ( v104 )
    {
      v104 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    }
    v67 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    }
    return v38;
  }
  if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackagePolicy", 0x2Eu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v39 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
  v40 = RoGetActivationFactory(v39, &GUID_93b105c2_0759_4c56_b8da_6e8f72ac464e, &v102);
  v41 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x512,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)v40,
      bIgnoreCase);
    if ( v9 )
      WindowsDeleteString(v9);
    if ( v8 )
      CoTaskMemFree(v8);
    v68 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    }
    v69 = v102;
    if ( v102 )
    {
      v102 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    }
    v70 = v104;
    if ( v104 )
    {
      v104 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    }
    v71 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    }
    return v41;
  }
  v42 = v102;
  v43 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64 *))(*(_QWORD *)v102 + 360LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
  if ( WindowsCreateStringReference(L"AppCategory", 0xBu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v44 = v43(v42, v103, string, &v101);
  v45 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x514,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)v44,
      bIgnoreCase);
    if ( v9 )
      WindowsDeleteString(v9);
    if ( v8 )
      CoTaskMemFree(v8);
    v60 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    }
    v61 = v102;
    if ( v102 )
    {
      v102 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    }
    v62 = v104;
    if ( v104 )
    {
      v104 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    }
    v63 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    }
    return v45;
  }
  v46 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v101 + 56LL))(v101, &v108);
  v47 = v46;
  if ( v46 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x515,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)v46,
      bIgnoreCase);
    if ( v9 )
      WindowsDeleteString(v9);
    if ( v8 )
      CoTaskMemFree(v8);
    v82 = v101;
    if ( v101 )
    {
      v101 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
    }
    v83 = v102;
    if ( v102 )
    {
      v102 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    }
    v84 = v104;
    if ( v104 )
    {
      v104 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
    }
    v85 = v103;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    }
    return v47;
  }
  while ( 1 )
  {
    if ( v7 >= v108 )
      goto LABEL_22;
    v105 = 0;
    v106 = 0;
    v100[0] = 1;
    v48 = v101;
    v49 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v101 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v105);
    v50 = v49(v48, v7, &v105);
    v19 = v50;
    if ( v50 < 0 )
      break;
    v51 = (*(__int64 (__fastcall **)(HSTRING, bool *))(*(_QWORD *)v105 + 176LL))(v105, v100);
    v52 = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x520,
        (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
        (const char *)(unsigned int)v51,
        bIgnoreCase);
      if ( v106 )
        WindowsDeleteString(v106);
      v86 = v105;
      if ( v105 )
      {
        v105 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v86 + 16LL))(v86);
      }
      if ( v9 )
        WindowsDeleteString(v9);
      if ( v8 )
        CoTaskMemFree(v8);
      v87 = v101;
      if ( v101 )
      {
        v101 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
      }
      v88 = v102;
      if ( v102 )
      {
        v102 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      }
      v89 = v104;
      if ( v104 )
      {
        v104 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      }
      v90 = v103;
      if ( v103 )
      {
        v103 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
      }
      return v52;
    }
    if ( !v100[0] )
    {
      v53 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v105 + 192LL))(v105, &v106);
      v19 = v53;
      if ( v53 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x524,
          (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
          (const char *)(unsigned int)v53,
          bIgnoreCase);
        if ( v106 )
          WindowsDeleteString(v106);
        v76 = v105;
        if ( v105 )
        {
          v105 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v76 + 16LL))(v76);
        }
        if ( v9 )
          WindowsDeleteString(v9);
        if ( v8 )
          CoTaskMemFree(v8);
        v77 = v101;
        if ( v101 )
        {
          v101 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
        }
        v78 = v102;
        if ( v102 )
        {
          v102 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        }
        v79 = v104;
        if ( v104 )
        {
          v104 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
        }
        v80 = v103;
        if ( v103 )
        {
          v103 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
        }
        return (unsigned int)v19;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(v106, 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, L"game", -1, 1) == 2 )
      {
        v12 = 1;
        if ( v106 )
          WindowsDeleteString(v106);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v105);
LABEL_22:
        *(_QWORD *)v107 = 0;
        v25 = v102;
        v26 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, _QWORD))(*(_QWORD *)v102 + 488LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v107);
        if ( WindowsCreateStringReference(L"DVROptOut", 9u, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        bIgnoreCasea = v107;
        v27 = v26(v25, v103, string, 0);
        if ( v27 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x531,
            (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
            (const char *)(unsigned int)v27,
            (int)v107);
        v28 = *(_QWORD *)v107;
        if ( *(_QWORD *)v107 )
        {
          v91 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *))(**(_QWORD **)v107 + 264LL))(
                  *(_QWORD *)v107,
                  &v99);
          if ( v91 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x535,
              (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
              (const char *)(unsigned int)v91,
              (int)bIgnoreCasea);
          v28 = *(_QWORD *)v107;
        }
        v29 = v99;
        if ( v12 )
          *v114 = v99 == 0;
        if ( v28 )
        {
          *(_QWORD *)v107 = 0;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 16LL))(v28, v29);
          LOBYTE(v29) = v99;
        }
        v6 = v115;
        v10 = v112[0];
        v11 = v116[0];
        goto LABEL_32;
      }
    }
    if ( v106 )
      WindowsDeleteString(v106);
    v55 = v105;
    if ( v105 )
    {
      v105 = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v55 + 16LL))(v55);
    }
    ++v7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x51E,
    (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
    (const char *)(unsigned int)v50,
    bIgnoreCase);
  if ( v106 )
    WindowsDeleteString(v106);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v105);
  if ( !v9 )
    goto LABEL_186;
LABEL_185:
  WindowsDeleteString(v9);
LABEL_186:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v104);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v103);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180082580  push    rbp
0x180082582  push    rbx
0x180082583  push    rsi
0x180082584  push    rdi
0x180082585  push    r12
0x180082587  push    r13
0x180082589  push    r14
0x18008258b  push    r15
0x18008258d  lea     rbp, [rsp-8]
0x180082592  sub     rsp, 108h
0x180082599  mov     rax, cs:__security_cookie
0x1800825a0  xor     rax, rsp
0x1800825a3  mov     [rbp+40h+var_50], rax
0x1800825a7  mov     [rbp+40h+var_B0], r9
0x1800825ab  mov     [rbp+40h+var_98], r8
0x1800825af  mov     r13, rdx
0x1800825b2  mov     rdi, rcx
0x1800825b5  mov     [rbp+40h+var_90], rcx
0x1800825b9  mov     r10, [rbp+40h+arg_20]
0x1800825bd  mov     [rbp+40h+var_80], r10
0x1800825c1  xor     r15d, r15d
0x1800825c4  mov     [rsp+140h+var_F8], r15
0x1800825c9  mov     [rsp+140h+var_F0], r15
0x1800825ce  mov     [rsp+140h+var_100], r15
0x1800825d3  mov     [rsp+140h+var_108], r15
0x1800825d8  mov     r14d, r15d
0x1800825db  mov     [rsp+140h+pv], r15
0x1800825e0  mov     [rbp+40h+var_C0], r15
0x1800825e4  mov     [rbp+40h+var_B8], r15
0x1800825e8  mov     ebx, r15d
0x1800825eb  mov     [rbp+40h+var_A0], rbx
0x1800825ef  mov     [rsp+140h+var_D0], r15d
0x1800825f4  mov     [rsp+140h+var_10F], r15b
0x1800825f9  mov     [rsp+140h+var_110], r15b
0x1800825fe  mov     [r8], r15b
0x180082601  lea     rdx, [rsp+140h+var_110]; unsigned __int8 *
0x180082606  lea     rcx, [rsp+140h+var_10F]; bool *
0x18008260b  call    ?IsCheckStateRepositoryMocked@@YA_NPEA_NPEAE@Z; IsCheckStateRepositoryMocked(bool *,uchar *)
0x180082610  test    al, al
0x180082612  jnz     loc_180082B42
0x180082618  xor     r12b, r12b
0x18008261b  mov     [rsp+140h+var_110], r12b
0x180082620  lea     r9, [rbp+40h+string]; string
0x180082624  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x180082628  mov     edx, 28h ; '('; length
0x18008262d  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180082634  call    cs:__imp_WindowsCreateStringReference
0x18008263a  test    eax, eax
0x18008263c  js      loc_1800832BA
0x180082642  mov     rdi, [rbp+40h+string]
0x180082646  lea     rcx, [rsp+140h+var_F0]
0x18008264b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180082650  lea     r8, [rsp+140h+var_F0]
0x180082655  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18008265c  mov     rcx, rdi
0x18008265f  call    cs:__imp_RoGetActivationFactory
0x180082665  mov     edi, eax
0x180082667  test    eax, eax
0x180082669  js      loc_180082B52
0x18008266f  mov     [rbp+40h+var_C0], 0FFFFFFFFFFFFFFFFh
0x180082677  mov     [rbp+40h+var_B8], 0FFFFFFFFFFFFFFFFh
0x18008267f  lea     rdx, [rsp+140h+pv]; unsigned __int16 *
0x180082684  mov     rcx, r13; this
0x180082687  call    ?GetPackageFullNameFromAppId@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetPackageFullNameFromAppId(ushort const *,ushort * *)
0x18008268c  mov     edi, eax
0x18008268e  test    eax, eax
0x180082690  js      short loc_1800826D3
0x180082692  mov     r14, [rsp+140h+pv]
0x180082697  test    r14, r14
0x18008269a  jz      loc_180083167
0x1800826a0  mov     [rsp+140h+var_E8], r15
0x1800826a5  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800826ac  nop     dword ptr [rax+00h]
0x1800826b0  inc     rdx; length
0x1800826b3  cmp     word ptr [r14+rdx*2], 0
0x1800826b9  jnz     short loc_1800826B0
0x1800826bb  mov     eax, 0FFFFFFFFh
0x1800826c0  cmp     rdx, rax
0x1800826c3  jbe     loc_1800828F9
0x1800826c9  mov     edi, 80070216h
0x1800826ce  jmp     loc_18008291E
0x1800826d3  mov     rcx, [rsp+140h+pv]; pv
0x1800826d8  test    rcx, rcx
0x1800826db  jz      short loc_1800826E4
0x1800826dd  call    cs:__imp_CoTaskMemFree
0x1800826e3  nop
0x1800826e4  mov     rcx, [rsp+140h+var_108]
0x1800826e9  test    rcx, rcx
0x1800826ec  jz      short loc_180082700
0x1800826ee  mov     [rsp+140h+var_108], r15
0x1800826f3  mov     rax, [rcx]
0x1800826f6  mov     rax, [rax+10h]
0x1800826fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800826ff  nop
0x180082700  mov     rcx, [rsp+140h+var_100]
0x180082705  test    rcx, rcx
0x180082708  jz      short loc_18008271C
0x18008270a  mov     [rsp+140h+var_100], r15
0x18008270f  mov     rax, [rcx]
0x180082712  mov     rax, [rax+10h]
0x180082716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008271b  nop
0x18008271c  mov     rcx, [rsp+140h+var_F0]
0x180082721  test    rcx, rcx
0x180082724  jz      short loc_180082738
0x180082726  mov     [rsp+140h+var_F0], r15
0x18008272b  mov     rax, [rcx]
0x18008272e  mov     rax, [rax+10h]
0x180082732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082737  nop
0x180082738  mov     rcx, [rsp+140h+var_F8]
0x18008273d  test    rcx, rcx
0x180082740  jz      short loc_180082754
0x180082742  mov     [rsp+140h+var_F8], r15
0x180082747  mov     rax, [rcx]
0x18008274a  mov     rax, [rax+10h]
0x18008274e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082753  nop
0x180082754  mov     eax, edi
0x180082756  jmp     loc_1800828D9
0x18008275b  xor     r15d, r15d
0x18008275e  mov     qword ptr [rsp+140h+var_D8], r15
0x180082763  mov     rdi, [rsp+140h+var_100]
0x180082768  mov     rax, [rdi]
0x18008276b  mov     rsi, [rax+1E8h]
0x180082772  lea     rcx, [rsp+140h+var_D8]
0x180082777  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008277c  lea     r9, [rbp+40h+string]; string
0x180082780  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x180082784  mov     edx, 9; length
0x180082789  lea     rcx, aDvroptout; "DVROptOut"
0x180082790  call    cs:__imp_WindowsCreateStringReference
0x180082796  test    eax, eax
0x180082798  js      loc_18008330B
0x18008279e  lea     rax, [rsp+140h+var_D8]
0x1800827a3  mov     qword ptr [rsp+140h+bIgnoreCase], rax; int
0x1800827a8  xor     r9d, r9d
0x1800827ab  mov     r8, [rbp+40h+string]
0x1800827af  mov     rdx, [rsp+140h+var_F8]
0x1800827b4  mov     rcx, rdi
0x1800827b7  mov     rax, rsi
0x1800827ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800827bf  mov     rcx, [rbp+48h]; this
0x1800827c3  test    eax, eax
0x1800827c5  js      loc_180082F76
0x1800827cb  mov     rcx, qword ptr [rsp+140h+var_D8]
0x1800827d0  test    rcx, rcx
0x1800827d3  jnz     loc_180083235
0x1800827d9  movzx   edx, [rsp+140h+var_110]
0x1800827de  test    r12b, r12b
0x1800827e1  jnz     loc_180083326
0x1800827e7  test    rcx, rcx
0x1800827ea  jz      short loc_180082802
0x1800827ec  mov     qword ptr [rsp+140h+var_D8], r15
0x1800827f1  mov     rax, [rcx]
0x1800827f4  mov     rax, [rax+10h]
0x1800827f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800827fd  movzx   edx, [rsp+140h+var_110]
0x180082802  mov     rdi, [rbp+40h+var_90]
0x180082806  mov     r9, [rbp+40h+var_B0]; struct _GUID *
0x18008280a  mov     r10, [rbp+40h+var_80]
0x18008280e  test    r12b, r12b
0x180082811  jnz     loc_180082F8F
0x180082817  test    dl, dl
0x180082819  jnz     loc_180082F91
0x18008281f  movups  xmm0, cs:xmmword_180769B30
0x180082826  movaps  xmmword ptr [rbp+40h+var_80], xmm0
0x18008282a  mov     rcx, [rdi+10h]
0x18008282e  mov     rax, [rcx]
0x180082831  lea     r8, [rbp+40h+var_80]
0x180082835  mov     rdx, r13
0x180082838  mov     rax, [rax+28h]
0x18008283c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082841  test    eax, eax
0x180082843  jns     loc_180083337
0x180082849  test    rbx, rbx
0x18008284c  jz      short loc_180082858
0x18008284e  mov     rcx, rbx; string
0x180082851  call    cs:__imp_WindowsDeleteString
0x180082857  nop
0x180082858  test    r14, r14
0x18008285b  jz      short loc_180082867
0x18008285d  mov     rcx, r14; pv
0x180082860  call    cs:__imp_CoTaskMemFree
0x180082866  nop
0x180082867  mov     rcx, [rsp+140h+var_108]
0x18008286c  test    rcx, rcx
0x18008286f  jz      short loc_180082883
0x180082871  mov     [rsp+140h+var_108], r15
0x180082876  mov     rax, [rcx]
0x180082879  mov     rax, [rax+10h]
0x18008287d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082882  nop
0x180082883  mov     rcx, [rsp+140h+var_100]
0x180082888  test    rcx, rcx
0x18008288b  jz      short loc_18008289F
0x18008288d  mov     [rsp+140h+var_100], r15
0x180082892  mov     rax, [rcx]
0x180082895  mov     rax, [rax+10h]
0x180082899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008289e  nop
0x18008289f  mov     rcx, [rsp+140h+var_F0]
0x1800828a4  test    rcx, rcx
0x1800828a7  jz      short loc_1800828BB
0x1800828a9  mov     [rsp+140h+var_F0], r15
0x1800828ae  mov     rax, [rcx]
0x1800828b1  mov     rax, [rax+10h]
0x1800828b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800828ba  nop
0x1800828bb  mov     rcx, [rsp+140h+var_F8]
0x1800828c0  test    rcx, rcx
0x1800828c3  jz      short loc_1800828D7
0x1800828c5  mov     [rsp+140h+var_F8], r15
0x1800828ca  mov     rax, [rcx]
0x1800828cd  mov     rax, [rax+10h]
0x1800828d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800828d6  nop
0x1800828d7  xor     eax, eax
0x1800828d9  mov     rcx, [rbp+40h+var_50]
0x1800828dd  xor     rcx, rsp; StackCookie
0x1800828e0  call    __security_check_cookie
0x1800828e5  add     rsp, 108h
0x1800828ec  pop     r15
0x1800828ee  pop     r14
0x1800828f0  pop     r13
0x1800828f2  pop     r12
0x1800828f4  pop     rdi
0x1800828f5  pop     rsi
0x1800828f6  pop     rbx
0x1800828f7  pop     rbp
0x1800828f8  retn
0x1800828f9  lea     r8, [rsp+140h+var_E8]; string
0x1800828fe  mov     rcx, r14; sourceString
0x180082901  call    cs:__imp_WindowsCreateString
0x180082907  mov     edi, eax
0x180082909  test    eax, eax
0x18008290b  js      short loc_18008291E
0x18008290d  mov     rbx, [rsp+140h+var_E8]
0x180082912  mov     [rbp+40h+var_A0], rbx
0x180082916  xor     ecx, ecx; string
0x180082918  call    cs:__imp_WindowsDeleteString
0x18008291e  test    edi, edi
0x180082920  js      loc_18008316C
0x180082926  mov     rsi, [rsp+140h+var_F0]
0x18008292b  mov     rax, [rsi]
0x18008292e  mov     rdi, [rax+170h]
0x180082935  lea     rcx, [rsp+140h+var_F8]
0x18008293a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008293f  lea     r9, [rsp+140h+var_F8]
0x180082944  mov     r8, rbx
0x180082947  xor     edx, edx
0x180082949  mov     rcx, rsi
0x18008294c  mov     rax, rdi
0x18008294f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082954  mov     edi, eax
0x180082956  cmp     eax, 80070490h
0x18008295b  jz      loc_180082DEC
0x180082961  test    eax, eax
0x180082963  js      loc_180082C90
0x180082969  lea     r9, [rbp+40h+string]; string
0x18008296d  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x180082971  mov     edx, 2Eh ; '.'; length
0x180082976  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackagePolicy@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18008297d  call    cs:__imp_WindowsCreateStringReference
0x180082983  test    eax, eax
0x180082985  js      loc_1800832D5
0x18008298b  mov     rdi, [rbp+40h+string]
0x18008298f  lea     rcx, [rsp+140h+var_100]
0x180082994  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180082999  lea     r8, [rsp+140h+var_100]
0x18008299e  lea     rdx, _GUID_93b105c2_0759_4c56_b8da_6e8f72ac464e
0x1800829a5  mov     rcx, rdi
0x1800829a8  call    cs:__imp_RoGetActivationFactory
0x1800829ae  mov     edi, eax
0x1800829b0  test    eax, eax
0x1800829b2  js      loc_180082D3E
0x1800829b8  mov     rdi, [rsp+140h+var_100]
0x1800829bd  mov     rax, [rdi]
0x1800829c0  mov     rsi, [rax+168h]
0x1800829c7  lea     rcx, [rsp+140h+var_108]
0x1800829cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800829d1  lea     r9, [rbp+40h+string]; string
0x1800829d5  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x1800829d9  mov     edx, 0Bh; length
0x1800829de  lea     rcx, aAppcategory; "AppCategory"
0x1800829e5  call    cs:__imp_WindowsCreateStringReference
0x1800829eb  test    eax, eax
0x1800829ed  js      loc_1800832F0
0x1800829f3  lea     r9, [rsp+140h+var_108]
0x1800829f8  mov     r8, [rbp+40h+string]
0x1800829fc  mov     rdx, [rsp+140h+var_F8]
0x180082a01  mov     rcx, rdi
0x180082a04  mov     rax, rsi
0x180082a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082a0c  mov     edi, eax
0x180082a0e  test    eax, eax
0x180082a10  js      loc_180082BE2
0x180082a16  mov     rcx, [rsp+140h+var_108]
0x180082a1b  mov     rax, [rcx]
0x180082a1e  lea     rdx, [rsp+140h+var_D0]
  ... truncated ...
```
