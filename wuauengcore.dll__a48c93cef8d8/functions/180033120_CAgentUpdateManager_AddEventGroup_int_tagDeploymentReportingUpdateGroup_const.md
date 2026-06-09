# CAgentUpdateManager::AddEventGroup(int,tagDeploymentReportingUpdateGroup const *)

- ea: `0x180033120`
- end: `0x180033a55`
- name: `?AddEventGroup@CAgentUpdateManager@@QEAAJHPEBUtagDeploymentReportingUpdateGroup@@@Z`
- size: `2357`
- prototype: `void __fastcall __noreturn(CAgentUpdateManager *__hidden this, int, const struct tagDeploymentReportingUpdateGroup *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d1aa0`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x180033120`
- `0x180038edc`
- `0x18003baf4`
- `0x1800549f4`
- `0x180110914`
- `0x18011098c`
- `0x180113ae8`
- `0x18012b618`
- `0x18012bf80`
- `0x18013ef7c`
- `0x1801457f4`
- `0x18014dcf0`
- `0x180150e90`
- `0x180150f8c`
- `0x180238960`
- `0x180238984`
- `0x180239110`
- `0x18023b03c`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180033212`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180033212`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800333ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800336d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800333ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800336d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336c3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003341a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800336f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003341a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800336f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800333f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033589`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800336d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033869`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800333f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033589`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800336d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033869`

## string_xrefs

- `0x1800335a7`: `C:\__w\1\s\src\Client\Engine\Agent\updatemanager.cpp`
- `0x1800335eb`: `C:\__w\1\s\src\Client\Engine\Agent\updatemanager.cpp`
- `0x1800338da`: `C:\__w\1\s\src\Client\Engine\Agent\updatemanager.cpp`
- `0x18003391e`: `C:\__w\1\s\src\Client\Engine\Agent\updatemanager.cpp`
- `0x180033960`: `C:\__w\1\s\src\Client\Engine\Agent\updatemanager.cpp`
- `0x18003399b`: `C:\__w\1\s\src\Client\Engine\Agent\updatemanager.cpp`
- `0x1800339cd`: `C:\__w\1\s\src\Client\Engine\Agent\updatemanager.cpp`
- `0x180033491`: `AddEventGroup: Adding %ws event for update id %ws`
- `0x18003376a`: `AddEventGroup: Adding %ws event for update id %ws`
- `0x180033552`: `AddEventGroup: Failed to set UpdateState`
- `0x180033832`: `AddEventGroup: Failed to set UpdateState for bundle`
- `0x180033228`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`
- `0x18003324a`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`
- `0x18003326a`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`
- `0x1800332bb`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
void __fastcall __noreturn CAgentUpdateManager::AddEventGroup(
        CAgentUpdateManager *this,
        int a2,
        const struct tagDeploymentReportingUpdateGroup *a3)
{
  CReportingUpdateGroup *v5; // rbx
  PSID v6; // rdi
  signed int v7; // esi
  __int64 v8; // rdx
  char *v9; // rax
  CReportingUpdateGroup *v10; // r14
  DWORD ModuleFileNameW; // eax
  const char *v12; // r9
  int LastError; // eax
  wchar_t *v14; // rax
  WCHAR *v15; // rcx
  int v16; // eax
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, __int64 *); // r12
  unsigned int v19; // r12d
  unsigned __int64 v20; // r9
  unsigned int v21; // esi
  __int64 v22; // r12
  __int64 v23; // rcx
  CUpdateManagerReportingData *v24; // rax
  CUpdateManagerReportingData *v25; // r13
  int updated; // esi
  DWORD v27; // esi
  const char *v28; // r9
  void *v29; // rcx
  int v30; // eax
  __int64 v31; // rax
  const wchar_t *v32; // rcx
  int v33; // eax
  __int64 v34; // r8
  __int64 v35; // rdx
  int v36; // eax
  int v37; // r13d
  unsigned __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // r12
  __int64 v41; // rcx
  CUpdateManagerReportingData *v42; // rax
  CUpdateManagerReportingData *v43; // r13
  int v44; // esi
  DWORD v45; // esi
  const char *v46; // r9
  void *v47; // rcx
  int v48; // eax
  __int64 v49; // rax
  const wchar_t *v50; // rcx
  int v51; // eax
  __int64 v52; // r8
  __int64 v53; // rdx
  int v54; // eax
  CAgentUpdateManager *v55; // rsi
  int v56; // eax
  wil::details::in1diag3 *v57; // rcx
  __int64 v58; // rdx
  int v59; // eax
  int v60; // eax
  unsigned int v61; // [rsp+20h] [rbp-E0h]
  int v62; // [rsp+40h] [rbp-C0h]
  unsigned int v63; // [rsp+44h] [rbp-BCh]
  unsigned int v64; // [rsp+44h] [rbp-BCh]
  int v66; // [rsp+4Ch] [rbp-B4h]
  int v67; // [rsp+4Ch] [rbp-B4h]
  HLOCAL v68; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  CReportingUpdateGroup *v70; // [rsp+60h] [rbp-A0h]
  CAgentUpdateManager *v71; // [rsp+68h] [rbp-98h]
  __int128 v72; // [rsp+70h] [rbp-90h] BYREF
  int v73; // [rsp+80h] [rbp-80h]
  PSID v74; // [rsp+88h] [rbp-78h]
  CUpdateManagerReportingData *v75; // [rsp+90h] [rbp-70h]
  __int128 v76; // [rsp+98h] [rbp-68h]
  _BYTE v77[112]; // [rsp+B0h] [rbp-50h] BYREF
  PSID Sid; // [rsp+120h] [rbp+20h] BYREF
  __int64 v79; // [rsp+128h] [rbp+28h] BYREF
  int v80; // [rsp+130h] [rbp+30h] BYREF
  __int128 v81; // [rsp+134h] [rbp+34h]
  int v82; // [rsp+144h] [rbp+44h]
  wchar_t Filename[264]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v71 = this;
  v5 = 0;
  v70 = 0;
  v62 = 0;
  v6 = 0;
  v74 = 0;
  v79 = 0;
  if ( !a3 )
  {
    v7 = -2147467261;
    v8 = 11778;
LABEL_25:
    v20 = (unsigned int)v7;
LABEL_100:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
      (const char *)v20,
      v61);
    goto LABEL_101;
  }
  v9 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = (CReportingUpdateGroup *)v9;
  if ( v9 )
  {
    *(_QWORD *)v9 = &CSusArrayList<_tagReportingUpdateEvent *,CSusArrayListItemOpDelete<_tagReportingUpdateEvent *>>::`vftable';
    *((_QWORD *)v9 + 1) = 0;
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 3) = &CSusArrayList<_tagReportingUpdateEvent *,CSusArrayListItemOpDelete<_tagReportingUpdateEvent *>>::`vftable';
    *((_QWORD *)v9 + 4) = 0;
    *((_QWORD *)v9 + 5) = 0;
    *((_DWORD *)v9 + 12) = 0;
    *(_QWORD *)(v9 + 52) = 0;
  }
  else
  {
    v10 = 0;
  }
  v5 = v10;
  v70 = v10;
  v7 = v10 == 0 ? 0x8007000E : 0;
  if ( !v10 )
  {
    v8 = 11780;
    goto LABEL_25;
  }
  Sid = 0;
  ModuleFileNameW = GetModuleFileNameW(g_hInstance, Filename, 0x105u);
  if ( ModuleFileNameW )
  {
    if ( ModuleFileNameW < 0x105 )
    {
      Filename[ModuleFileNameW] = 0;
      goto LABEL_15;
    }
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x63,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\commonutil.cpp",
                  (const char *)0x7A,
                  v61);
  }
  else
  {
    Filename[0] = 0;
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x5F,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\commonutil.cpp",
                  v12);
  }
  v7 = LastError;
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\commonutil.cpp",
      (const char *)(unsigned int)LastError,
      v61);
LABEL_20:
    v8 = 11782;
    goto LABEL_25;
  }
LABEL_15:
  v14 = wcsrchr(Filename, 0x5Cu);
  v15 = Filename;
  if ( v14 )
    v15 = v14 + 1;
  v16 = DuplicateString<wchar_t const *,wchar_t *>(v15, &Sid);
  v7 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\commonutil.cpp",
      (const char *)(unsigned int)v16,
      v61);
    if ( Sid )
      SusFree(Sid);
    goto LABEL_20;
  }
  v6 = Sid;
  v74 = Sid;
  v17 = *((_QWORD *)this + 281);
  v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 24LL);
  if ( v79 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
    v79 = 0;
  }
  v7 = v18(v17, &v79);
  v19 = 0;
  if ( v7 < 0 )
  {
    v8 = 11785;
    goto LABEL_25;
  }
  v21 = 0;
  v63 = 0;
  if ( *(_DWORD *)a3 )
  {
    while ( 1 )
    {
      v22 = 32LL * v21;
      v23 = *(_QWORD *)(v22 + *((_QWORD *)a3 + 1));
      v76 = *(_OWORD *)(v23 + 236);
      v72 = v76;
      v66 = *(_DWORD *)(v23 + 252);
      v73 = v66;
      Sid = 0;
      v24 = (CUpdateManagerReportingData *)operator new(0x800u, (const struct std::nothrow_t *)&std::nothrow);
      v75 = v24;
      v25 = v24 ? CUpdateManagerReportingData::CUpdateManagerReportingData(v24) : 0LL;
      v68 = v25;
      if ( !v25 )
        break;
      updated = CUpdateManagerReportingData::PopulateFromUpdateDeploymentReportingData(
                  v25,
                  *(const struct tagUpdateDeploymentReportingData **)(v22 + *((_QWORD *)a3 + 1)));
      if ( updated < 0 )
      {
        v39 = 11796;
        goto LABEL_55;
      }
      if ( *(_QWORD *)(v22 + *((_QWORD *)a3 + 1) + 24) )
      {
        hMem = Sid;
        if ( Sid )
        {
          v27 = GetLastError();
          LocalFree(hMem);
          SetLastError(v27);
        }
        Sid = 0;
        if ( !ConvertStringSidToSidW(*(LPCWSTR *)(v22 + *((_QWORD *)a3 + 1) + 24), &Sid) )
        {
          wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x2E18,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
            v28);
          goto LABEL_57;
        }
      }
      if ( *((_BYTE *)v25 + 1428) == 1 )
      {
        v29 = (void *)*((_QWORD *)v25 + 179);
        if ( v29 )
        {
          SusFree(v29);
          *((_QWORD *)v25 + 179) = 0;
        }
        v30 = DuplicateString<wchar_t *,wchar_t *>(v6, (char *)v25 + 1432);
        if ( v30 < 0 )
        {
          v38 = (unsigned int)v30;
          v39 = 11806;
          goto LABEL_56;
        }
      }
      v31 = Trace::UpdateIdToString::UpdateIdToString(
              (Trace::UpdateIdToString *)v77,
              (const struct tagDSGlobalUpdateId *)&v72);
      v32 = L"non-pending";
      if ( a2 )
        v32 = L"pending";
      WUTrace(0, 0, 1, 4, 0, L"AddEventGroup: Adding %ws event for update id %ws", v32, v31);
      v61 = (unsigned int)Sid;
      v33 = CReportingUpdateGroup::AddEvent(
              v10,
              &v68,
              *(unsigned int *)(v22 + *((_QWORD *)a3 + 1) + 8),
              *(_QWORD *)(v22 + *((_QWORD *)a3 + 1) + 16));
      v19 = 0;
      if ( v33 < 0 )
      {
        v38 = (unsigned int)v33;
        v39 = 11819;
        goto LABEL_56;
      }
      v80 = 0;
      v81 = v76;
      v82 = v66;
      v34 = *(_QWORD *)(32LL * v63 + *((_QWORD *)a3 + 1));
      v35 = *(unsigned int *)(v34 + 536);
      if ( (_DWORD)v35 )
      {
        v61 = v34 + 544;
        v36 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v79 + 232LL))(v79, v35, 1, &v80);
        if ( v36 < 0 )
          WUTrace(0, 0, 1, 3, v36, L"AddEventGroup: Failed to set UpdateState");
      }
      v37 = ++v62;
      if ( Sid )
        LocalFree(Sid);
      v21 = v63 + 1;
      v63 = v21;
      if ( v21 >= *(_DWORD *)a3 )
        goto LABEL_60;
    }
    updated = -2147024882;
    v39 = 11793;
LABEL_55:
    v38 = (unsigned int)updated;
    goto LABEL_56;
  }
  v37 = 0;
LABEL_60:
  v64 = 0;
  if ( *((_DWORD *)a3 + 4) )
  {
    while ( 1 )
    {
      v40 = 32LL * v19;
      v41 = *(_QWORD *)(*((_QWORD *)a3 + 3) + v40);
      v76 = *(_OWORD *)(v41 + 236);
      v72 = v76;
      v67 = *(_DWORD *)(v41 + 252);
      v73 = v67;
      Sid = 0;
      v42 = (CUpdateManagerReportingData *)operator new(0x800u, (const struct std::nothrow_t *)&std::nothrow);
      v75 = v42;
      v43 = v42 ? CUpdateManagerReportingData::CUpdateManagerReportingData(v42) : 0LL;
      hMem = v43;
      if ( !v43 )
        break;
      v44 = CUpdateManagerReportingData::PopulateFromUpdateDeploymentReportingData(
              v43,
              *(const struct tagUpdateDeploymentReportingData **)(*((_QWORD *)a3 + 3) + v40));
      if ( v44 < 0 )
      {
        v39 = 11850;
        goto LABEL_92;
      }
      if ( *(_QWORD *)(*((_QWORD *)a3 + 3) + v40 + 24) )
      {
        v68 = Sid;
        if ( Sid )
        {
          v45 = GetLastError();
          LocalFree(v68);
          SetLastError(v45);
        }
        Sid = 0;
        if ( !ConvertStringSidToSidW(*(LPCWSTR *)(*((_QWORD *)a3 + 3) + v40 + 24), &Sid) )
        {
          wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x2E4E,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
            v46);
          goto LABEL_57;
        }
      }
      if ( *((_BYTE *)v43 + 1428) == 1 )
      {
        v47 = (void *)*((_QWORD *)v43 + 179);
        if ( v47 )
        {
          SusFree(v47);
          *((_QWORD *)v43 + 179) = 0;
        }
        v48 = DuplicateString<wchar_t *,wchar_t *>(v6, (char *)v43 + 1432);
        if ( v48 < 0 )
        {
          v38 = (unsigned int)v48;
          v39 = 11860;
          goto LABEL_56;
        }
      }
      v49 = Trace::UpdateIdToString::UpdateIdToString(
              (Trace::UpdateIdToString *)v77,
              (const struct tagDSGlobalUpdateId *)&v72);
      v50 = L"non-pending";
      if ( a2 )
        v50 = L"pending";
      WUTrace(0, 0, 1, 4, 0, L"AddEventGroup: Adding %ws event for update id %ws", v50, v49);
      v61 = (unsigned int)Sid;
      v51 = CReportingUpdateGroup::AddEvent(
              v10,
              &hMem,
              *(unsigned int *)(32LL * v64 + *((_QWORD *)a3 + 3) + 8),
              *(_QWORD *)(32LL * v64 + *((_QWORD *)a3 + 3) + 16));
      if ( v51 < 0 )
      {
        v38 = (unsigned int)v51;
        v39 = 11873;
        goto LABEL_56;
      }
      v80 = 0;
      v81 = v76;
      v82 = v67;
      v52 = *(_QWORD *)(32LL * v64 + *((_QWORD *)a3 + 3));
      v53 = *(unsigned int *)(v52 + 536);
      if ( (_DWORD)v53 )
      {
        v61 = v52 + 544;
        v54 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v79 + 232LL))(v79, v53, 1, &v80);
        if ( v54 < 0 )
          WUTrace(0, 0, 1, 3, v54, L"AddEventGroup: Failed to set UpdateState for bundle");
      }
      v37 = ++v62;
      if ( Sid )
        LocalFree(Sid);
      v19 = v64 + 1;
      v64 = v19;
      if ( v19 >= *((_DWORD *)a3 + 4) )
        goto LABEL_83;
    }
    v44 = -2147024882;
    v39 = 11847;
LABEL_92:
    v38 = (unsigned int)v44;
LABEL_56:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
      (const char *)v38,
      v61);
LABEL_57:
    if ( Sid )
      LocalFree(Sid);
    goto LABEL_101;
  }
LABEL_83:
  if ( !v37 )
    goto LABEL_101;
  v55 = v71;
  if ( a2 )
  {
    v5 = 0;
    v70 = 0;
    v68 = v10;
    v56 = CPendingReportingEventHandler::AddPendingEventGroup(
            (CAgentUpdateManager *)((char *)v71 + 2848),
            (struct CReportingUpdateGroup **)&v68);
    v57 = retaddr;
    if ( v56 >= 0 )
      goto LABEL_96;
    v58 = 11905;
  }
  else
  {
    v56 = (*(__int64 (__fastcall **)(__int64, CReportingUpdateGroup *, _QWORD))(*(_QWORD *)(*((_QWORD *)v71 + 280)
                                                                                          + 2416LL)
                                                                              + 8LL))(
            *((_QWORD *)v71 + 280) + 2416LL,
            v10,
            0);
    v57 = retaddr;
    if ( v56 >= 0 )
      goto LABEL_96;
    v58 = 11899;
  }
  wil::details::in1diag3::_Log_Hr(
    v57,
    (void *)v58,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
    (const char *)(unsigned int)v56,
    v61);
LABEL_96:
  v59 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(*((_QWORD *)v55 + 280) + 2416LL) + 24LL))(
          *((_QWORD *)v55 + 280) + 2416LL,
          1);
  if ( v59 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2E85,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
      (const char *)(unsigned int)v59,
      v61);
  v60 = CReporter::Flush((CReporter *)(*((_QWORD *)v55 + 280) + 2408LL));
  if ( v60 < 0 )
  {
    v20 = (unsigned int)v60;
    v8 = 11911;
    goto LABEL_100;
  }
LABEL_101:
  if ( v79 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
    v79 = 0;
  }
  if ( v6 )
    SusFree(v6);
  if ( v5 )
  {
    CReportingUpdateGroup::~CReportingUpdateGroup(v5);
    operator delete(v5, (const struct std::nothrow_t *)0x40);
  }
}

```

## disassembly

```asm
0x180033120  mov     [rsp-8+arg_18], rbx
0x180033125  push    rbp
0x180033126  push    rsi
0x180033127  push    rdi
0x180033128  push    r12
0x18003312a  push    r13
0x18003312c  push    r14
0x18003312e  push    r15
0x180033130  lea     rbp, [rsp-270h]
0x180033138  sub     rsp, 370h
0x18003313f  mov     rax, cs:__security_cookie
0x180033146  xor     rax, rsp
0x180033149  mov     [rbp+2A0h+var_40], rax
0x180033150  mov     r15, r8
0x180033153  mov     [rsp+3A0h+var_358], edx
0x180033157  mov     r13, rcx
0x18003315a  mov     [rsp+3A0h+var_338], rcx
0x18003315f  xor     r12d, r12d
0x180033162  mov     ebx, r12d
0x180033165  mov     [rsp+3A0h+var_340], rbx
0x18003316a  mov     [rsp+3A0h+var_360], r12d
0x18003316f  mov     edi, r12d
0x180033172  mov     [rbp+2A0h+var_318], r12
0x180033176  mov     [rbp+2A0h+var_278], r12
0x18003317a  test    r8, r8
0x18003317d  jnz     short loc_18003318E
0x18003317f  mov     esi, 80004003h
0x180033184  mov     edx, 2E02h
0x180033189  jmp     loc_180033331
0x18003318e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180033195  mov     ecx, 40h ; '@'; unsigned __int64
0x18003319a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z
0x18003319f  mov     r14, rax
0x1800331a2  test    rax, rax
0x1800331a5  jz      short loc_1800331D1
0x1800331a7  lea     rax, ??_7?$CSusArrayList@PEAU_tagReportingUpdateEvent@@V?$CSusArrayListItemOpDelete@PEAU_tagReportingUpdateEvent@@@@@@6B@
0x1800331ae  mov     [r14], rax
0x1800331b1  mov     [r14+8], r12
0x1800331b5  mov     [r14+10h], r12
0x1800331b9  mov     [r14+18h], rax
0x1800331bd  mov     [r14+20h], r12
0x1800331c1  mov     [r14+28h], r12
0x1800331c5  mov     [r14+30h], r12d
0x1800331c9  xor     eax, eax
0x1800331cb  mov     [r14+34h], rax
0x1800331cf  jmp     short loc_1800331D4
0x1800331d1  mov     r14, r12
0x1800331d4  mov     rbx, r14
0x1800331d7  mov     [rsp+3A0h+var_340], rbx
0x1800331dc  mov     rax, r14
0x1800331df  neg     rax
0x1800331e2  sbb     esi, esi
0x1800331e4  not     esi
0x1800331e6  and     esi, 8007000Eh
0x1800331ec  test    r14, r14
0x1800331ef  jnz     short loc_1800331FB
0x1800331f1  mov     edx, 2E04h
0x1800331f6  jmp     loc_180033331
0x1800331fb  mov     [rbp+2A0h+Sid], r12
0x1800331ff  mov     esi, 105h
0x180033204  mov     r8d, esi; nSize
0x180033207  lea     rdx, [rbp+2A0h+Filename]; lpFilename
0x18003320b  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180033212  call    cs:__imp_GetModuleFileNameW
0x180033218  test    eax, eax
0x18003321a  jnz     short loc_180033239
0x18003321c  mov     [rbp+2A0h+Filename], r12w
0x180033221  mov     rcx, [rbp+2A8h]; this
0x180033228  lea     r8, aCW1SSrcClientL_12
0x18003322f  lea     edx, [rax+5Fh]; void *
0x180033232  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z
0x180033237  jmp     short loc_18003325A
0x180033239  cmp     eax, esi
0x18003323b  jb      short loc_18003327D
0x18003323d  mov     rcx, [rbp+2A8h]; this
0x180033244  mov     r9d, 7Ah ; 'z'; char *
0x18003324a  lea     r8, aCW1SSrcClientL_12
0x180033251  lea     edx, [r9-17h]; void *
0x180033255  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z
0x18003325a  mov     esi, eax
0x18003325c  test    eax, eax
0x18003325e  jns     short loc_180033285
0x180033260  mov     rcx, [rbp+2A8h]; this
0x180033267  mov     r9d, eax; char *
0x18003326a  lea     r8, aCW1SSrcClientL_12
0x180033271  mov     edx, 73h ; 's'; void *
0x180033276  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18003327b  jmp     short loc_1800332DA
0x18003327d  mov     eax, eax
0x18003327f  mov     [rbp+rax*2+2A0h+Filename], r12w
0x180033285  mov     edx, 5Ch ; '\'; Ch
0x18003328a  lea     rcx, [rbp+2A0h+Filename]; Str
0x18003328e  call    wcsrchr
0x180033293  lea     rdx, [rax+2]
0x180033297  lea     rcx, [rbp+2A0h+Filename]
0x18003329b  test    rax, rax
0x18003329e  cmovnz  rcx, rdx
0x1800332a2  lea     rdx, [rbp+2A0h+Sid]
0x1800332a6  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z
0x1800332ab  mov     esi, eax
0x1800332ad  test    eax, eax
0x1800332af  jns     short loc_1800332E1
0x1800332b1  mov     rcx, [rbp+2A8h]; this
0x1800332b8  mov     r9d, eax; char *
0x1800332bb  lea     r8, aCW1SSrcClientL_12
0x1800332c2  mov     edx, 78h ; 'x'; void *
0x1800332c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800332cc  mov     rcx, [rbp+2A0h+Sid]; lpMem
0x1800332d0  test    rcx, rcx
0x1800332d3  jz      short loc_1800332DA
0x1800332d5  call    ?SusFree@@YAXPEAX@Z
0x1800332da  mov     edx, 2E06h
0x1800332df  jmp     short loc_180033331
0x1800332e1  mov     rdi, [rbp+2A0h+Sid]
0x1800332e5  mov     [rbp+2A0h+var_318], rdi
0x1800332e9  mov     rsi, [r13+8C8h]
0x1800332f0  mov     rax, [rsi]
0x1800332f3  mov     r12, [rax+18h]
0x1800332f7  mov     rcx, [rbp+2A0h+var_278]
0x1800332fb  test    rcx, rcx
0x1800332fe  jz      short loc_180033314
0x180033300  mov     rdx, [rcx]
0x180033303  mov     rax, [rdx+10h]
0x180033307  call    _guard_dispatch_icall
0x18003330c  mov     [rbp+2A0h+var_278], 0
0x180033314  lea     rdx, [rbp+2A0h+var_278]
0x180033318  mov     rcx, rsi
0x18003331b  mov     rax, r12
0x18003331e  call    _guard_dispatch_icall
0x180033323  mov     esi, eax
0x180033325  xor     r12d, r12d
0x180033328  test    eax, eax
0x18003332a  jns     short loc_180033339
0x18003332c  mov     edx, 2E09h
0x180033331  mov     r9d, esi
0x180033334  jmp     loc_1800339CD
0x180033339  mov     esi, r12d
0x18003333c  mov     [rsp+3A0h+var_35C], r12d
0x180033341  cmp     [r15], r12d
0x180033344  jbe     loc_180033610
0x18003334a  mov     r12d, esi
0x18003334d  shl     r12, 5
0x180033351  mov     rax, [r15+8]
0x180033355  mov     rcx, [r12+rax]
0x180033359  movups  xmm0, xmmword ptr [rcx+0ECh]
0x180033360  movups  [rbp+2A0h+var_308], xmm0
0x180033364  movups  [rsp+3A0h+var_330], xmm0
0x180033369  mov     eax, [rcx+0FCh]
0x18003336f  mov     [rsp+3A0h+var_354], eax
0x180033373  mov     [rbp+2A0h+var_320], eax
0x180033376  mov     [rbp+2A0h+Sid], 0
0x18003337e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180033385  mov     ecx, 800h; unsigned __int64
0x18003338a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z
0x18003338f  mov     [rbp+2A0h+var_310], rax
0x180033393  test    rax, rax
0x180033396  jz      short loc_1800333A5
0x180033398  mov     rcx, rax; this
0x18003339b  call    ??0CUpdateManagerReportingData@@QEAA@XZ
0x1800333a0  mov     r13, rax
0x1800333a3  jmp     short loc_1800333A8
0x1800333a5  xor     r13d, r13d
0x1800333a8  mov     [rsp+3A0h+var_350], r13
0x1800333ad  test    r13, r13
0x1800333b0  jz      loc_1800335D7
0x1800333b6  mov     rdx, [r15+8]
0x1800333ba  mov     rdx, [r12+rdx]; struct tagUpdateDeploymentReportingData *
0x1800333be  mov     rcx, r13; this
0x1800333c1  call    ?PopulateFromUpdateDeploymentReportingData@CUpdateManagerReportingData@@QEAAJAEBUtagUpdateDeploymentReportingData@@@Z
0x1800333c6  mov     esi, eax
0x1800333c8  test    eax, eax
0x1800333ca  js      loc_1800335D0
0x1800333d0  mov     rax, [r15+8]
0x1800333d4  cmp     qword ptr [r12+rax+18h], 0
0x1800333da  jz      short loc_180033428
0x1800333dc  mov     rax, [rbp+2A0h+Sid]
0x1800333e0  mov     [rsp+3A0h+hMem], rax
0x1800333e5  test    rax, rax
0x1800333e8  jz      short loc_180033405
0x1800333ea  call    cs:__imp_GetLastError
0x1800333f0  mov     esi, eax
0x1800333f2  mov     rcx, [rsp+3A0h+hMem]; hMem
0x1800333f7  call    cs:__imp_LocalFree
0x1800333fd  mov     ecx, esi; dwErrCode
0x1800333ff  call    cs:__imp_SetLastError
0x180033405  mov     [rbp+2A0h+Sid], 0
0x18003340d  mov     rcx, [r15+8]
0x180033411  lea     rdx, [rbp+2A0h+Sid]; Sid
0x180033415  mov     rcx, [r12+rcx+18h]; StringSid
0x18003341a  call    cs:__imp_ConvertStringSidToSidW
0x180033420  test    eax, eax
0x180033422  jz      loc_1800335A0
0x180033428  cmp     byte ptr [r13+594h], 1
0x180033430  jnz     short loc_180033462
0x180033432  lea     rsi, [r13+598h]
0x180033439  mov     rcx, [rsi]; lpMem
0x18003343c  test    rcx, rcx
0x18003343f  jz      short loc_18003344D
0x180033441  call    ?SusFree@@YAXPEAX@Z
0x180033446  mov     qword ptr [rsi], 0
0x18003344d  mov     rdx, rsi
0x180033450  mov     rcx, rdi
0x180033453  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z
0x180033458  mov     esi, eax
0x18003345a  test    eax, eax
0x18003345c  js      loc_1800335BC
0x180033462  lea     rdx, [rsp+3A0h+var_330]; struct tagDSGlobalUpdateId *
0x180033467  lea     rcx, [rbp+2A0h+var_2F0]; this
0x18003346b  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z
0x180033470  lea     rcx, aNonPending
0x180033477  cmp     [rsp+3A0h+var_358], 0
0x18003347c  lea     rdx, aPending
0x180033483  cmovnz  rcx, rdx
0x180033487  mov     [rsp+3A0h+var_368], rax
0x18003348c  mov     [rsp+3A0h+var_370], rcx
0x180033491  lea     rax, aAddeventgroupA
0x180033498  mov     [rsp+3A0h+var_378], rax
0x18003349d  mov     qword ptr [rsp+3A0h+var_380], 0
0x1800334a6  xor     edx, edx
0x1800334a8  xor     ecx, ecx
0x1800334aa  lea     r9d, [rdx+4]
0x1800334ae  lea     r8d, [rdx+1]
0x1800334b2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ
0x1800334b7  mov     rcx, [rbp+2A0h+Sid]
0x1800334bb  mov     r8, [r15+8]
0x1800334bf  mov     eax, [r13+0D0h]
0x1800334c6  mov     dword ptr [rsp+3A0h+var_378], eax
0x1800334ca  mov     qword ptr [rsp+3A0h+var_380], rcx
0x1800334cf  mov     r9, [r12+r8+10h]
0x1800334d4  mov     r8d, [r12+r8+8]
0x1800334d9  lea     rdx, [rsp+3A0h+var_350]
0x1800334de  mov     rcx, r14
0x1800334e1  call    ?AddEvent@CReportingUpdateGroup@@QEAAJPEAPEAVCUpdateManagerReportingData@@W4tagUHUpdateHandler@@PEB_WQEAXW4_tagReportingUpdateEventType@@@Z
0x1800334e6  mov     esi, eax
0x1800334e8  xor     r12d, r12d
0x1800334eb  test    eax, eax
0x1800334ed  js      loc_1800335C6
0x1800334f3  mov     [rbp+2A0h+var_270], r12d
0x1800334f7  movups  xmm0, [rbp+2A0h+var_308]
0x1800334fb  movups  [rbp+2A0h+var_26C], xmm0
0x1800334ff  mov     eax, [rsp+3A0h+var_354]
0x180033503  mov     [rbp+2A0h+var_25C], eax
0x180033506  mov     esi, [rsp+3A0h+var_35C]
0x18003350a  mov     ecx, esi
0x18003350c  shl     rcx, 5
0x180033510  mov     rax, [r15+8]
0x180033514  mov     r8, [rcx+rax]
0x180033518  mov     edx, [r8+218h]
0x18003351f  test    edx, edx
0x180033521  jz      short loc_180033573
0x180033523  add     r8, 220h
0x18003352a  mov     rcx, [rbp+2A0h+var_278]
0x18003352e  mov     rax, [rcx]
0x180033531  mov     qword ptr [rsp+3A0h+var_380], r8
0x180033536  lea     r9, [rbp+2A0h+var_270]
0x18003353a  lea     r13d, [r12+1]
0x18003353f  mov     r8d, r13d
0x180033542  mov     rax, [rax+0E8h]
0x180033549  call    _guard_dispatch_icall
0x18003354e  test    eax, eax
0x180033550  jns     short loc_180033573
0x180033552  lea     rcx, aAddeventgroupF_0
0x180033559  mov     [rsp+3A0h+var_378], rcx
0x18003355e  mov     [rsp+3A0h+var_380], eax
0x180033562  lea     r9d, [r12+3]
0x180033567  mov     r8d, r13d
0x18003356a  xor     edx, edx
0x18003356c  xor     ecx, ecx
0x18003356e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ
0x180033573  mov     r13d, [rsp+3A0h+var_360]
0x180033578  inc     r13d
0x18003357b  mov     [rsp+3A0h+var_360], r13d
0x180033580  mov     rcx, [rbp+2A0h+Sid]; hMem
0x180033584  test    rcx, rcx
0x180033587  jz      short loc_18003358F
0x180033589  call    cs:__imp_LocalFree
0x18003358f  inc     esi
0x180033591  mov     [rsp+3A0h+var_35C], esi
0x180033595  cmp     esi, [r15]
0x180033598  jb      loc_18003334A
0x18003359e  jmp     short loc_180033613
0x1800335a0  mov     rcx, [rbp+2A8h]; this
0x1800335a7  lea     r8, aCW1SSrcClientE_96
0x1800335ae  mov     edx, 2E18h; void *
0x1800335b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z
0x1800335b8  mov     esi, eax
0x1800335ba  jmp     short loc_1800335F8
0x1800335bc  mov     r9d, eax
0x1800335bf  mov     edx, 2E1Eh
0x1800335c4  jmp     short loc_1800335E4
0x1800335c6  mov     r9d, eax
0x1800335c9  mov     edx, 2E2Bh
0x1800335ce  jmp     short loc_1800335E4
0x1800335d0  mov     edx, 2E14h
0x1800335d5  jmp     short loc_1800335E1
0x1800335d7  mov     esi, 8007000Eh
0x1800335dc  mov     edx, 2E11h; void *
0x1800335e1  mov     r9d, esi; char *
0x1800335e4  mov     rcx, [rbp+2A8h]; this
0x1800335eb  lea     r8, aCW1SSrcClientE_96
  ... truncated ...
```
