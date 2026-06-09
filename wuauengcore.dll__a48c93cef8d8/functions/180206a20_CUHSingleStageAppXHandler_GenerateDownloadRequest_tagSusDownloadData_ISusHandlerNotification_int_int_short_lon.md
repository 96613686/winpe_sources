# CUHSingleStageAppXHandler::GenerateDownloadRequest(tagSusDownloadData *,ISusHandlerNotification *,int *,int *,short *,long *,int *)

- ea: `0x180206a20`
- end: `0x1802076fa`
- name: `?GenerateDownloadRequest@CUHSingleStageAppXHandler@@UEAAJPEAUtagSusDownloadData@@PEAUISusHandlerNotification@@PEAH2PEAFPEAJ2@Z`
- size: `3290`
- prototype: `int(CUHSingleStageAppXHandler *__hidden this, struct tagSusDownloadData *, struct ISusHandlerNotification *, int *, int *, __int16 *, int *, int *)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001da00`
- `0x180037ae0`
- `0x1801133c8`
- `0x180113ae8`
- `0x18012b618`
- `0x18012bed4`
- `0x1802023ac`
- `0x180203a94`
- `0x180205fb4`
- `0x180206528`
- `0x180206a20`
- `0x180207700`
- `0x180209ddc`
- `0x18020a260`
- `0x180212af4`
- `0x180217e80`
- `0x18021994c`
- `0x180219a18`
- `0x18021d3a8`
- `0x18021f25c`
- `0x180238960`
- `0x180238984`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802071a5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802073e7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802071a5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802073e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180206e8b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180206e8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180207655`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180207655`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180207693`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180207693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180206ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802072bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180206ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802072bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180206e97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802076a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180206e97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802076a1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180206d16`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180206d16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180206d83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180206d9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180206d83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180206d9c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18020722b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18020722b`
- `OLEAUT32!__imp_SysStringLen` at `0x180206b04`
- `OLEAUT32!__imp_SysStringLen` at `0x180206b04`

## string_xrefs

- `0x180206ba3`: `Flat bundle update %ws requesting block validation.`
- `0x180206fd0`: `AppX GDR: GenerateUri requested not to call stage package.`
- `0x1802071f5`: `AppX GDR: Waiting %lu ms for download execute or completion event.`
- `0x180206bf0`: `Flat bundle update %ws is co-serviced set.`
- `0x180206dbf`: `AppX GDR: Unable to find payload file data for update %ws`
- `0x180206e1b`: `AppX GDR: Flat bundle update %ws is legacy XAP`
- `0x180207468`: `AppX GDR: Successfully generated a download request. Update Id: %ws, cFiles=%lu`
- `0x180207524`: `AppX GDR for update %ws`
- `0x180207341`: `AppX GDR: EventCompletion seen. Run is complete.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUHSingleStageAppXHandler::GenerateDownloadRequest(
        CUHSingleStageAppXHandler *this,
        struct tagSusDownloadData *a2,
        struct ISusHandlerNotification *a3,
        int *a4,
        int *a5,
        __int16 *a6,
        int *a7,
        int *a8)
{
  void *v10; // rsi
  struct CUHAppXHandler::AppXReportingData *v11; // r14
  struct CAppxDeploymentOperation *v12; // rbx
  struct AppxDownloadUtils::DownloadRequest *v13; // rdi
  __int64 v14; // r15
  signed int updated; // r12d
  int *v16; // rax
  int *v17; // rcx
  __int64 v18; // rcx
  int RunningDataSourceForUpdate; // eax
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rcx
  const WCHAR *lpString2; // r9
  unsigned int v24; // r12d
  __int64 v25; // rdx
  struct CUHAppXHandler::AppXReportingData *v26; // rax
  const WCHAR *v27; // r8
  __int64 v28; // rcx
  bool v29; // al
  const struct _GUID *v30; // rdx
  CUHSingleStageAppXHandler *v31; // rbx
  HANDLE EventW; // r12
  signed int LastError; // eax
  int v34; // eax
  int v35; // r12d
  int v36; // eax
  int v37; // ecx
  int v38; // eax
  unsigned int v39; // ebx
  CUHSingleStageAppXHandler *v40; // r12
  struct CUHAppXHandler::AppXReportingData *v41; // rcx
  __int64 v42; // rax
  CUHSingleStageAppXHandler *v43; // r12
  bool v44; // cf
  DWORD v45; // r12d
  DWORD v46; // r12d
  signed int v47; // eax
  const wchar_t *v48; // r8
  __int64 v49; // r9
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rdi
  bool v53; // bl
  const wchar_t *v54; // rax
  const struct tagDSGlobalUpdateId *v55; // rdx
  CUHSingleStageAppXHandler *v56; // rdi
  __int64 v57; // rbx
  unsigned int IndexOf; // eax
  int cchCount2; // [rsp+28h] [rbp-D8h]
  bool cchCount2a; // [rsp+28h] [rbp-D8h]
  wchar_t *v62; // [rsp+30h] [rbp-D0h]
  wchar_t *v63; // [rsp+30h] [rbp-D0h]
  wchar_t *v64; // [rsp+30h] [rbp-D0h]
  wchar_t *v65; // [rsp+30h] [rbp-D0h]
  wchar_t *v66; // [rsp+30h] [rbp-D0h]
  wchar_t *v67; // [rsp+30h] [rbp-D0h]
  struct ISusHandlerNotification *v68; // [rsp+38h] [rbp-C8h]
  char v69; // [rsp+50h] [rbp-B0h]
  char v70; // [rsp+51h] [rbp-AFh]
  bool v71; // [rsp+52h] [rbp-AEh] BYREF
  char v72; // [rsp+53h] [rbp-ADh]
  char v73; // [rsp+54h] [rbp-ACh] BYREF
  bool v74; // [rsp+55h] [rbp-ABh] BYREF
  struct AppxDownloadUtils::DownloadRequest *v75; // [rsp+58h] [rbp-A8h] BYREF
  CUHSingleStageAppXHandler *v76; // [rsp+60h] [rbp-A0h]
  struct CAppxDeploymentOperation *v77; // [rsp+68h] [rbp-98h] BYREF
  struct CUHAppXHandler::AppXReportingData *v78; // [rsp+70h] [rbp-90h]
  struct CUHAppXHandler::AppXReportingData *v79; // [rsp+78h] [rbp-88h] BYREF
  PCNZWCH v80; // [rsp+80h] [rbp-80h]
  struct ISusHandlerNotification *v81; // [rsp+88h] [rbp-78h]
  int *v82; // [rsp+90h] [rbp-70h]
  int *v83; // [rsp+98h] [rbp-68h]
  __int16 *v84; // [rsp+A0h] [rbp-60h]
  int *v85; // [rsp+A8h] [rbp-58h]
  _BYTE v86[80]; // [rsp+B0h] [rbp-50h] BYREF
  char v87; // [rsp+100h] [rbp+0h]
  void *lpMem; // [rsp+108h] [rbp+8h] BYREF
  int v89; // [rsp+110h] [rbp+10h] BYREF
  bool v90[8]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v91; // [rsp+120h] [rbp+20h] BYREF
  PCNZWCH v92; // [rsp+128h] [rbp+28h]
  HANDLE Handles[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v94; // [rsp+140h] [rbp+40h]

  v81 = a3;
  v76 = this;
  v82 = a5;
  v84 = a6;
  v83 = a7;
  v85 = a8;
  v10 = 0;
  lpMem = 0;
  v69 = 0;
  v72 = 0;
  v70 = 0;
  v78 = 0;
  v11 = 0;
  v79 = 0;
  v12 = 0;
  v77 = 0;
  v13 = 0;
  v75 = 0;
  v14 = -1;
  *(_OWORD *)Handles = 0;
  v94 = 0;
  WUTrace(0, 0, 4096, 5, 0, L"AppX GDR: Entering GDR");
  if ( !a2 || !*((_QWORD *)a2 + 3) || !*((_QWORD *)a2 + 4) )
    goto LABEL_2;
  if ( !SysStringLen(*((BSTR *)a2 + 2)) )
  {
    updated = -2147024809;
    goto LABEL_134;
  }
  if ( !v81 || !a4 || (v16 = v82) == 0 || !v84 || (v17 = v83) == 0 )
  {
LABEL_2:
    updated = -2147467261;
    goto LABEL_134;
  }
  *v84 = 105;
  *a4 = 0;
  *v16 = 0;
  *v17 = 0;
  *v85 = 0;
  v18 = *((_QWORD *)a2 + 4);
  if ( (*(_DWORD *)(v18 + 28) & 0x224) != 0x224 || !*(_QWORD *)(v18 + 472) || !*(_DWORD *)(v18 + 464) )
  {
    updated = -2145116154;
    WUTrace(0, 0, 4096, 1, 0, L"Invalid files or handler specific data section for Appx download request handler");
LABEL_134:
    v69 = 1;
    v51 = Trace::GuidToString::GuidToString(
            (Trace::GuidToString *)v86,
            (const struct _GUID *)(*((_QWORD *)a2 + 4) + 4LL));
    WUTrace(0, 0, 4096, 1, updated, L"AppX GDR for update %ws", v51);
    if ( v84 )
      *v84 = 105;
LABEL_136:
    if ( updated < 0 )
      goto LABEL_140;
    goto LABEL_137;
  }
  if ( !*((_DWORD *)a2 + 33) )
  {
    v62 = (wchar_t *)Trace::GuidToString::GuidToString((Trace::GuidToString *)v86, (const struct _GUID *)(v18 + 4));
    WUTrace(0, 0, 4096, 1, 0, L"Flat bundle update %ws requesting block validation.", v62);
LABEL_17:
    updated = -2145116154;
    goto LABEL_134;
  }
  if ( (*(_DWORD *)(v18 + 184) & 0x2000) != 0 )
  {
    v63 = (wchar_t *)Trace::GuidToString::GuidToString((Trace::GuidToString *)v86, (const struct _GUID *)(v18 + 4));
    WUTrace(0, 0, 4096, 1, 0, L"Flat bundle update %ws is co-serviced set.", v63);
    goto LABEL_17;
  }
  updated = AppxDownloadUtils::DownloadRequest::Create(
              (const struct tagDSUpdateMetadata *)v18,
              *((struct CAppxStreamingDataSourceFactory **)v76 + 19),
              &v75);
  v13 = v75;
  if ( updated < 0 )
    goto LABEL_131;
  RunningDataSourceForUpdate = CAppxStreamingDataSourceFactory::GetRunningDataSourceForUpdate(
                                 *((CAppxStreamingDataSourceFactory **)v76 + 19),
                                 (const struct _GUID *)(*((_QWORD *)a2 + 4) + 4LL),
                                 &v79);
  v11 = v79;
  if ( RunningDataSourceForUpdate < 0 )
  {
    v91 = 0;
    v92 = 0;
    if ( (int)UHAppXHandlerData::Init(
                (UHAppXHandlerData *)&v91,
                (const struct tagDSDataBlob *)(*((_QWORD *)a2 + 4) + 544LL)) >= 0 )
    {
      lpString2 = v92;
      v80 = v92;
      v24 = 0;
      v25 = *((_QWORD *)a2 + 4);
      if ( *(_DWORD *)(v25 + 464) )
      {
        while ( 1 )
        {
          v26 = (struct CUHAppXHandler::AppXReportingData *)(248LL * v24 + *(_QWORD *)(v25 + 472));
          v79 = v26;
          v27 = (const WCHAR *)*((_QWORD *)v26 + 9);
          if ( v27 == lpString2 )
            break;
          if ( v27 && lpString2 )
          {
            if ( CompareStringW(0x7Fu, 1u, v27, -1, lpString2, -1) == 2 )
            {
              v26 = v79;
              break;
            }
            lpString2 = v80;
          }
          ++v24;
          v25 = *((_QWORD *)a2 + 4);
          if ( v24 >= *(_DWORD *)(v25 + 464) )
            goto LABEL_40;
        }
        v78 = v26;
      }
LABEL_40:
      updated = FlatBundleFileIdList::Initialize(
                  (FlatBundleFileIdList *)(*((_QWORD *)v76 + 19) + 176LL),
                  (const struct _GUID *)(*((_QWORD *)a2 + 4) + 4LL),
                  *(const struct tagDSFile **)(*((_QWORD *)a2 + 4) + 472LL),
                  *(_DWORD *)(*((_QWORD *)a2 + 4) + 464LL));
      if ( updated < 0 )
      {
        if ( v92 )
          CoTaskMemFree((LPVOID)v92);
        goto LABEL_131;
      }
      v70 = 1;
    }
    if ( v92 )
      CoTaskMemFree((LPVOID)v92);
  }
  else
  {
    v20 = *((_QWORD *)v13 + 1);
    v78 = 0;
    v21 = 0;
    if ( *(_DWORD *)(v20 + 8) )
    {
      while ( 1 )
      {
        v22 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v20 + 16) + 8 * v21) + 8LL);
        if ( *(_QWORD *)v22 == *(_QWORD *)((char *)v79 + 9)
          && *(_QWORD *)(v22 + 8) == *(_QWORD *)((char *)v79 + 17)
          && *(_DWORD *)(v22 + 16) == *(_DWORD *)((char *)v79 + 25) )
        {
          break;
        }
        v21 = (unsigned int)(v21 + 1);
        if ( (unsigned int)v21 >= *(_DWORD *)(v20 + 8) )
          goto LABEL_46;
      }
      v78 = *(struct CUHAppXHandler::AppXReportingData **)(*(_QWORD *)(v20 + 16) + 8 * v21);
    }
  }
LABEL_46:
  v28 = *((_QWORD *)a2 + 4);
  if ( !v78 )
  {
    v64 = (wchar_t *)Trace::GuidToString::GuidToString((Trace::GuidToString *)v86, (const struct _GUID *)(v28 + 4));
    WUTrace(0, 0, 4096, 1, 0, L"AppX GDR: Unable to find payload file data for update %ws", v64);
    goto LABEL_17;
  }
  updated = AppxPackage::CreateFromUpdateRuleMetadata(
              *(_DWORD *)(v28 + 608),
              *(const struct tagDSDataBlob **)(v28 + 616),
              (struct AppxPackage **)&lpMem);
  v10 = lpMem;
  if ( updated < 0 )
  {
LABEL_131:
    if ( updated == -2145124343 )
      goto LABEL_136;
    goto LABEL_134;
  }
  v29 = *(_DWORD *)lpMem == 3 && !*((_QWORD *)lpMem + 1);
  v30 = (const struct _GUID *)(*((_QWORD *)a2 + 4) + 4LL);
  if ( v29 )
  {
    v65 = (wchar_t *)Trace::GuidToString::GuidToString((Trace::GuidToString *)v86, v30);
    WUTrace(0, 0, 4096, 1, 0, L"AppX GDR: Flat bundle update %ws is legacy XAP", v65);
    goto LABEL_17;
  }
  v31 = v76;
  (*(void (__fastcall **)(CUHSingleStageAppXHandler *, const struct _GUID *, _QWORD))(*(_QWORD *)v76 + 144LL))(
    v76,
    v30,
    0);
  if ( CUHAppXHandler::GetDeploymentOperation(
         (CUHSingleStageAppXHandler *)((char *)v31 - 56),
         (const struct _GUID *)(*((_QWORD *)a2 + 4) + 4LL),
         &v77) )
  {
    v12 = v77;
  }
  else
  {
    if ( v77 )
      (*(void (__fastcall **)(struct CAppxDeploymentOperation *))(*(_QWORD *)v77 + 16LL))(v77);
    v12 = 0;
    v77 = 0;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  CloseHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v14 = (__int64)EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    updated = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      updated = LastError;
    if ( updated >= 0 )
      updated = -2147418113;
    goto LABEL_131;
  }
  if ( v70 )
  {
    v34 = CWuaClassFactoryBase::RegisterClassFactory(*((CWuaClassFactoryBase **)v76 + 19));
  }
  else
  {
    LOBYTE(cchCount2) = *((_DWORD *)a2 + 31) != 0;
    v34 = (*(__int64 (__fastcall **)(struct AppxDownloadUtils::DownloadRequest *, struct ISusHandlerNotification *, struct CUHAppXHandler::AppXReportingData *, _QWORD, _QWORD, int, bool))(*(_QWORD *)v13 + 16LL))(
            v13,
            v81,
            v78,
            *((_QWORD *)a2 + 18),
            *((_QWORD *)a2 + 2),
            cchCount2,
            *((_DWORD *)a2 + 33) != 0);
  }
  updated = v34;
  if ( v34 < 0 )
    goto LABEL_131;
  if ( v12 )
  {
    v42 = Trace::GuidToString::GuidToString(
            (Trace::GuidToString *)v86,
            (const struct _GUID *)(*((_QWORD *)a2 + 4) + 4LL));
    WUTrace(0, 0, 4096, 4, 0, L"AppX GDR: Existing deployment operation for %ws", v42);
    LODWORD(v75) = 0;
  }
  else
  {
    WUTrace(0, 0, 4096, 4, 0, L"AppX GDR: New Deployment Operation");
    lpMem = 0;
    *(_QWORD *)v90 = 0;
    v87 = 0;
    updated = (*(__int64 (__fastcall **)(struct AppxDownloadUtils::DownloadRequest *, struct CUHAppXHandler::AppXReportingData *, _QWORD, __int64, void **))(*(_QWORD *)v13 + 32LL))(
                v13,
                v78,
                *((_QWORD *)a2 + 2),
                *((_QWORD *)a2 + 19) + 4LL,
                &lpMem);
    if ( updated < 0 )
    {
LABEL_72:
      if ( lpMem )
        SusFree(lpMem);
      goto LABEL_131;
    }
    if ( !v87 )
    {
      WUTrace(0, 0, 4096, 4, 0, L"AppX GDR: GenerateUri requested not to call stage package.");
      if ( lpMem )
        SusFree(lpMem);
      goto LABEL_137;
    }
    v35 = 0;
    if ( *((_BYTE *)v10 + 40) && CUHAppXHandler::ForceInstallAllResources() )
      v35 = 2;
    v36 = v35 | 0x10;
    if ( !*((_DWORD *)a2 + 12) )
      v36 = v35;
    v37 = v36 | 0x20;
    if ( !*((_DWORD *)a2 + 30) )
      v37 = v36;
    v38 = v37 | 0x40;
    if ( !*((_DWORD *)a2 + 31) )
      v38 = v37;
    LODWORD(v75) = v38;
    v73 = 0;
    v74 = 0;
    v71 = 0;
    updated = AppxDownloadUtils::IsDowngradeAllowed(
                *((AppxDownloadUtils **)v10 + 2),
                (const wchar_t *)a2,
                (struct tagSusDownloadData *)&v73,
                &v74,
                &v71,
                v90);
    if ( updated < 0 )
      goto LABEL_72;
    v39 = (unsigned int)v75;
    if ( v73 )
      v39 = (unsigned int)v75 | 0x80;
    v79 = 0;
    v40 = v76;
    if ( (int)CUHAppXHandler::GetAppXReportingData(
                (CUHSingleStageAppXHandler *)((char *)v76 - 56),
                (const struct _GUID *)(*((_QWORD *)a2 + 4) + 4LL),
                &v79) >= 0 )
    {
      v41 = v79;
      *(_BYTE *)v79 = v74;
      *((_BYTE *)v41 + 1) = v71;
    }
    updated = CUHAppXHandler::CreateNewDeploymentOperation(
                (CUHSingleStageAppXHandler *)((char *)v40 - 56),
                (void *)v14,
                a2,
                v39,
                (const wchar_t *)lpMem,
                cchCount2a,
                *((const wchar_t **)v10 + 6),
                v81,
                &v77);
    if ( updated < 0 )
    {
      if ( lpMem )
        SusFree(lpMem);
      v12 = v77;
      goto LABEL_131;
    }
    if ( lpMem )
      SusFree(lpMem);
    LODWORD(v75) = 1;
    v12 = v77;
  }
  if ( !v12 )
  {
    v69 = 0;
    v72 = 0;
    if ( updated < 0 )
      goto LABEL_131;
    goto LABEL_137;
  }
  v43 = v76;
  ResetEvent(*((HANDLE *)v76 + 16));
  if ( !v70 )
    (*(void (__fastcall **)(struct AppxDownloadUtils::DownloadRequest *, _QWORD))(*(_QWORD *)v13 + 40LL))(
      v13,
      *((_QWORD *)v43 + 16));
  Handles[0] = *((HANDLE *)v12 + 4);
  Handles[1] = *((HANDLE *)v43 + 16);
  v94 = *((_QWORD *)v12 + 5);
  v44 = (_DWORD)v75 != 0;
  LODWORD(v75) = -(int)v75;
  v45 = v44 ? 0x64 : 0;
  LODWORD(v66) = v45;
  WUTrace(0, 0, 4096, 4, 0, L"AppX GDR: Waiting %lu ms for download execute or completion event.", v66);
  v46 = WaitForMultipleObjects(3u, Handles, 0, v45);
  if ( !v70 )
    (*(void (__fastcall **)(struct AppxDownloadUtils::DownloadRequest *, _QWORD))(*(_QWORD *)v13 + 40LL))(v13, 0);
  switch ( v46 )
  {
    case 0u:
      WUTrace(0, 0, 4096, 4, 0, L"AppX GDR: EventCancel seen. Cancelled.");
      updated = -2145116152;
      goto LABEL_134;
    case 1u:
      WUTrace(0, 0, 4096, 4, 0, L"AppX GDR: EventExecute seen. Execute, Resetting");
      ResetEvent(*((HANDLE *)v76 + 16));
      LOBYTE(v49) = !*((_DWORD *)a2 + 10) || *((_DWORD *)a2 + 11) && !*((_DWORD *)a2 + 32);
      v89 = 0;
      updated = (*(__int64 (__fastcall **)(struct AppxDownloadUtils::DownloadRequest *, struct CUHAppXHandler::AppXReportingData *, _QWORD, __int64, int *))(*(_QWORD *)v13 + 48LL))(
                  v13,
                  v78,
                  *((_QWORD *)a2 + 3),
                  v49,
                  &v89);
      if ( updated < 0 )
        goto LABEL_131;
      LODWORD(v75) = v89;
      if ( !v89 )
        goto LABEL_116;
      v50 = Trace::GuidToString::GuidToString(
              (Trace::GuidToString *)v86,
              (const struct _GUID *)(*((_QWORD *)a2 + 4) + 4LL));
      LODWORD(v68) = (_DWORD)v75;
      WUTrace(
        0,
        0,
        4096,
        4,
        0,
        L"AppX GDR: Successfully generated a download request. Update Id: %ws, cFiles=%lu",
        v50,
        v68);
      break;
    case 2u:
      WUTrace(0, 0, 4096, 4, 0, L"AppX GDR: EventCompletion seen. Run is complete.");
      v69 = 1;
      updated = *((_DWORD *)v12 + 34);
      *v83 = *((_DWORD *)v12 + 35);
      if ( updated < 0 )
        goto LABEL_131;
      v72 = 1;
      if ( *((_DWORD *)a2 + 29) )
        AppXDeliveryProperties::SetInstalledChannelId(
          *((AppXDeliveryProperties **)v10 + 2),
          *(const wchar_t **)(*((_QWORD *)a2 + 4) + 96LL),
          v48);
      (*(void (__fastcall **)(struct AppxDownloadUtils::DownloadRequest *))(*(_QWORD *)v13 + 64LL))(v13);
      break;
    case 0x102u:
      WUTrace(0, 0, 4096, 4, 0, L"AppX GDR: WAIT_TIMEOUT seen. Wait timed out.");
      *v82 = 0;
LABEL_116:
      updated = -2145124343;
      goto LABEL_140;
    case 0xFFFFFFFF:
      v69 = 1;
      v47 = GetLastError();
      updated = (unsigned __int16)v47 | 0x80070000;
      if ( v47 <= 0 )
        updated = v47;
      if ( updated >= 0 )
        updated = -2147418113;
      WUTrace(0, 0, 4096, 3, updated, L"AppX GDR: Wait failed");
      goto LABEL_131;
    default:
      LODWORD(v67) = v46;
      WUTrace(0, 0, 4096, 3, 0, L"AppX GDR: Event Fired: Error %lu", v67);
      updated = -2145112065;
      goto LABEL_134;
  }
LABEL_137:
  if ( !v12 )
    goto LABEL_142;
  if ( *((_BYTE *)v12 + 544) )
    *v85 = 1;
LABEL_140:
  if ( v12 )
    (*(void (__fastcall **)(struct CAppxDeploymentOperation *))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_142:
  if ( v13 )
    (**(void (__fastcall ***)(struct AppxDownloadUtils::DownloadRequest *, __int64))v13)(v13, 1);
  if ( v69 )
  {
    v52 = *((_QWORD *)a2 + 4);
    v53 = v72 && (!*((_DWORD *)a2 + 11) || *((_DWORD *)a2 + 32)) && (*(_DWORD *)(v52 + 184) & 0x100) == 0;
    v54 = L"No";
    if ( v53 )
      v54 = L"Yes";
    WUTrace(0, 0, 4096, 4, 0, L"AppX GDR: Cleaning up download objects. fCleanupSandbox=%ws", v54);
    v55 = (const struct tagDSGlobalUpdateId *)(v52 + 4);
    *(_QWORD *)v90 = v52 + 4;
    v56 = v76;
    CUHAppXHandler::ShutdownDataSourcesAndDeployment(
      (CUHSingleStageAppXHandler *)((char *)v76 - 56),
      v55,
      1,
      v53,
      *((const wchar_t **)a2 + 2));
    v57 = *((_QWORD *)v56 + 19);
    if ( v57 != -176 )
      EnterCriticalSection((LPCRITICAL_SECTION)(v57 + 184));
    IndexOf = CSusMap<_GUID,DownloadHeartbeatBundle *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<DownloadHeartbeatBundle *>>::GetIndexOf(
                v57 + 224,
                *(_QWORD *)v90);
    if ( IndexOf < *(_DWORD *)(v57 + 244) )
      CSusArrayList<CSusMap<_GUID,CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *>>::_tagMapEntry,CSusMap<_GUID,CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *>>::CMapEntryOps>::RemoveArraySection(
        v57 + 224,
        IndexOf,
        IndexOf,
        1);
    if ( v57 != -176 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v57 + 184));
  }
  if ( v14 )
    CloseHandle((HANDLE)v14);
  if ( v11 )
    (*(void (__fastcall **)(struct CUHAppXHandler::AppXReportingData *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v10 )
  {
    AppxPackage::~AppxPackage((AppxPackage *)v10);
    operator delete(v10, (const struct std::nothrow_t *)0x38);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180206a20  push    rbp
0x180206a22  push    rbx
0x180206a23  push    rsi
0x180206a24  push    rdi
0x180206a25  push    r12
0x180206a27  push    r13
0x180206a29  push    r14
0x180206a2b  push    r15
0x180206a2d  lea     rbp, [rsp-58h]
0x180206a32  sub     rsp, 158h
0x180206a39  mov     rax, cs:__security_cookie
0x180206a40  xor     rax, rsp
0x180206a43  mov     [rbp+90h+var_48], rax
0x180206a47  mov     r12, r9
0x180206a4a  mov     [rbp+90h+var_108], r8
0x180206a4e  mov     r13, rdx
0x180206a51  mov     [rsp+190h+var_130], rcx
0x180206a56  mov     rax, [rbp+90h+arg_20]
0x180206a5d  mov     [rbp+90h+var_100], rax
0x180206a61  mov     rax, [rbp+90h+arg_28]
0x180206a68  mov     [rbp+90h+var_F0], rax
0x180206a6c  mov     rax, [rbp+90h+arg_30]
0x180206a73  mov     [rbp+90h+var_F8], rax
0x180206a77  mov     rax, [rbp+90h+arg_38]
0x180206a7e  mov     [rbp+90h+var_E8], rax
0x180206a82  xor     ecx, ecx
0x180206a84  mov     esi, ecx
0x180206a86  mov     [rbp+90h+lpMem], rcx
0x180206a8a  mov     [rsp+190h+var_140], cl
0x180206a8e  mov     [rsp+190h+var_13D], cl
0x180206a92  mov     [rsp+190h+var_13F], cl
0x180206a96  mov     [rsp+190h+var_120], rcx
0x180206a9b  mov     r14d, ecx
0x180206a9e  mov     [rsp+190h+var_118], rcx
0x180206aa3  mov     ebx, ecx
0x180206aa5  mov     [rsp+190h+var_128], rcx
0x180206aaa  mov     edi, ecx
0x180206aac  mov     [rsp+190h+var_138], rcx
0x180206ab1  or      r15, 0FFFFFFFFFFFFFFFFh
0x180206ab5  xorps   xmm0, xmm0
0x180206ab8  xor     eax, eax
0x180206aba  movups  xmmword ptr [rbp+90h+Handles], xmm0
0x180206abe  mov     [rbp+90h+var_50], rax
0x180206ac2  lea     rax, aAppxGdrEnterin; "AppX GDR: Entering GDR"
0x180206ac9  mov     qword ptr [rsp+190h+cchCount2], rax
0x180206ace  mov     [rsp+190h+lpString2], rcx
0x180206ad3  xor     edx, edx
0x180206ad5  lea     r9d, [rcx+5]
0x180206ad9  mov     r8d, 1000h
0x180206adf  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180206ae4  test    r13, r13
0x180206ae7  jnz     short loc_180206AF4
0x180206ae9  mov     r12d, 80004003h
0x180206aef  jmp     loc_180207509
0x180206af4  cmp     [r13+18h], rbx
0x180206af8  jz      short loc_180206AE9
0x180206afa  cmp     [r13+20h], rbx
0x180206afe  jz      short loc_180206AE9
0x180206b00  mov     rcx, [r13+10h]; pbstr
0x180206b04  call    cs:__imp_SysStringLen
0x180206b0a  xor     r8d, r8d
0x180206b0d  test    eax, eax
0x180206b0f  jnz     short loc_180206B1C
0x180206b11  mov     r12d, 80070057h
0x180206b17  jmp     loc_180207509
0x180206b1c  cmp     [rbp+90h+var_108], r8
0x180206b20  jz      short loc_180206AE9
0x180206b22  test    r12, r12
0x180206b25  jz      short loc_180206AE9
0x180206b27  mov     rax, [rbp+90h+var_100]
0x180206b2b  test    rax, rax
0x180206b2e  jz      short loc_180206AE9
0x180206b30  mov     rdx, [rbp+90h+var_F0]
0x180206b34  test    rdx, rdx
0x180206b37  jz      short loc_180206AE9
0x180206b39  mov     rcx, [rbp+90h+var_F8]
0x180206b3d  test    rcx, rcx
0x180206b40  jz      short loc_180206AE9
0x180206b42  mov     word ptr [rdx], 69h ; 'i'
0x180206b47  mov     [r12], r8d
0x180206b4b  mov     [rax], r8d
0x180206b4e  mov     [rcx], r8d
0x180206b51  mov     rax, [rbp+90h+var_E8]
0x180206b55  mov     [rax], r8d
0x180206b58  mov     rcx, [r13+20h]; struct tagDSUpdateMetadata *
0x180206b5c  mov     eax, [rcx+1Ch]
0x180206b5f  mov     edx, 224h
0x180206b64  and     eax, edx
0x180206b66  cmp     eax, edx
0x180206b68  jnz     loc_1802074DF
0x180206b6e  cmp     [rcx+1D8h], r8
0x180206b75  jz      loc_1802074DF
0x180206b7b  cmp     [rcx+1D0h], r8d
0x180206b82  jz      loc_1802074DF
0x180206b88  cmp     [r13+84h], r8d
0x180206b8f  jnz     short loc_180206BD2
0x180206b91  lea     rdx, [rcx+4]; struct _GUID *
0x180206b95  lea     rcx, [rbp+90h+var_E0]; this
0x180206b99  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180206b9e  mov     [rsp+190h+var_160], rax
0x180206ba3  lea     rax, aFlatBundleUpda; "Flat bundle update %ws requesting block"...
0x180206baa  mov     qword ptr [rsp+190h+cchCount2], rax
0x180206baf  mov     [rsp+190h+lpString2], rbx
0x180206bb4  xor     edx, edx
0x180206bb6  xor     ecx, ecx
0x180206bb8  lea     r9d, [rdx+1]
0x180206bbc  mov     r8d, 1000h
0x180206bc2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180206bc7  mov     r12d, 80242006h
0x180206bcd  jmp     loc_180207509
0x180206bd2  test    dword ptr [rcx+0B8h], 2000h
0x180206bdc  jz      short loc_180206BF9
0x180206bde  lea     rdx, [rcx+4]; struct _GUID *
0x180206be2  lea     rcx, [rbp+90h+var_E0]; this
0x180206be6  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180206beb  mov     [rsp+190h+var_160], rax
0x180206bf0  lea     rax, aFlatBundleUpda_0; "Flat bundle update %ws is co-serviced s"...
0x180206bf7  jmp     short loc_180206BAA
0x180206bf9  lea     r8, [rsp+190h+var_138]; struct AppxDownloadUtils::DownloadRequest **
0x180206bfe  mov     rdx, [rsp+190h+var_130]
0x180206c03  mov     rdx, [rdx+98h]; struct CAppxStreamingDataSourceFactory *
0x180206c0a  call    ?Create@DownloadRequest@AppxDownloadUtils@@SAJPEBUtagDSUpdateMetadata@@PEAVCAppxStreamingDataSourceFactory@@PEAPEAV12@@Z; AppxDownloadUtils::DownloadRequest::Create(tagDSUpdateMetadata const *,CAppxStreamingDataSourceFactory *,AppxDownloadUtils::DownloadRequest * *)
0x180206c0f  mov     r12d, eax
0x180206c12  mov     rdi, [rsp+190h+var_138]
0x180206c17  test    eax, eax
0x180206c19  js      loc_1802074D4
0x180206c1f  mov     rdx, [r13+20h]
0x180206c23  add     rdx, 4; struct _GUID *
0x180206c27  lea     r8, [rsp+190h+var_118]; struct CAppxStreamingDataSource **
0x180206c2c  mov     rax, [rsp+190h+var_130]
0x180206c31  mov     rcx, [rax+98h]; this
0x180206c38  call    ?GetRunningDataSourceForUpdate@CAppxStreamingDataSourceFactory@@QEBAJAEBU_GUID@@PEAPEAVCAppxStreamingDataSource@@@Z; CAppxStreamingDataSourceFactory::GetRunningDataSourceForUpdate(_GUID const &,CAppxStreamingDataSource * *)
0x180206c3d  mov     r14, [rsp+190h+var_118]
0x180206c42  test    eax, eax
0x180206c44  js      short loc_180206C9A
0x180206c46  mov     r9, [rdi+8]
0x180206c4a  mov     [rsp+190h+var_120], rbx
0x180206c4f  xor     edx, edx
0x180206c51  cmp     [r9+8], edx
0x180206c55  jbe     loc_180206DA2
0x180206c5b  mov     rax, [r9+10h]
0x180206c5f  mov     r8, [rax+rdx*8]
0x180206c63  mov     rcx, [r8+8]
0x180206c67  mov     rax, [rcx]
0x180206c6a  cmp     rax, [r14+9]
0x180206c6e  jnz     short loc_180206C83
0x180206c70  mov     rax, [rcx+8]
0x180206c74  cmp     rax, [r14+11h]
0x180206c78  jnz     short loc_180206C83
0x180206c7a  mov     eax, [rcx+10h]
0x180206c7d  cmp     eax, [r14+19h]
0x180206c81  jz      short loc_180206C90
0x180206c83  inc     edx
0x180206c85  cmp     edx, [r9+8]
0x180206c89  jb      short loc_180206C5B
0x180206c8b  jmp     loc_180206DA2
0x180206c90  mov     [rsp+190h+var_120], r8
0x180206c95  jmp     loc_180206DA2
0x180206c9a  mov     [rbp+90h+var_70], rbx
0x180206c9e  mov     [rbp+90h+var_68], rbx
0x180206ca2  mov     rdx, [r13+20h]
0x180206ca6  add     rdx, 220h; struct tagDSDataBlob *
0x180206cad  lea     rcx, [rbp+90h+var_70]; this
0x180206cb1  call    ?Init@UHAppXHandlerData@@QEAAJAEBUtagDSDataBlob@@@Z; UHAppXHandlerData::Init(tagDSDataBlob const &)
0x180206cb6  test    eax, eax
0x180206cb8  js      loc_180206D93
0x180206cbe  mov     r9, [rbp+90h+var_68]
0x180206cc2  mov     [rbp+90h+var_110], r9
0x180206cc6  xor     r12d, r12d
0x180206cc9  mov     rdx, [r13+20h]
0x180206ccd  cmp     [rdx+1D0h], ebx
0x180206cd3  jbe     short loc_180206D41
0x180206cd5  mov     eax, r12d
0x180206cd8  imul    rcx, rax, 0F8h
0x180206cdf  mov     rax, [rdx+1D8h]
0x180206ce6  add     rax, rcx
0x180206ce9  mov     [rsp+190h+var_118], rax
0x180206cee  mov     r8, [rax+48h]; lpString1
0x180206cf2  cmp     r8, r9
0x180206cf5  jz      short loc_180206D3C
0x180206cf7  test    r8, r8
0x180206cfa  jz      short loc_180206D25
0x180206cfc  test    r9, r9
0x180206cff  jz      short loc_180206D25
0x180206d01  mov     [rsp+190h+cchCount2], r15d; cchCount2
0x180206d06  mov     [rsp+190h+lpString2], r9; lpString2
0x180206d0b  mov     r9d, r15d; cchCount1
0x180206d0e  mov     edx, 1; dwCmpFlags
0x180206d13  lea     ecx, [rdx+7Eh]; Locale
0x180206d16  call    cs:__imp_CompareStringW
0x180206d1c  cmp     eax, 2
0x180206d1f  jz      short loc_180206D37
0x180206d21  mov     r9, [rbp+90h+var_110]
0x180206d25  inc     r12d
0x180206d28  mov     rdx, [r13+20h]
0x180206d2c  cmp     r12d, [rdx+1D0h]
0x180206d33  jb      short loc_180206CD5
0x180206d35  jmp     short loc_180206D41
0x180206d37  mov     rax, [rsp+190h+var_118]
0x180206d3c  mov     [rsp+190h+var_120], rax
0x180206d41  mov     r8, [r13+20h]
0x180206d45  lea     rdx, [r8+4]; struct _GUID *
0x180206d49  mov     rax, [rsp+190h+var_130]
0x180206d4e  mov     rcx, [rax+98h]
0x180206d55  add     rcx, 0B0h; this
0x180206d5c  mov     r9d, [r8+1D0h]; unsigned int
0x180206d63  mov     r8, [r8+1D8h]; struct tagDSFile *
0x180206d6a  call    ?Initialize@FlatBundleFileIdList@@QEAAJAEBU_GUID@@PEBUtagDSFile@@I@Z; FlatBundleFileIdList::Initialize(_GUID const &,tagDSFile const *,uint)
0x180206d6f  mov     r12d, eax
0x180206d72  test    eax, eax
0x180206d74  jns     short loc_180206D8E
0x180206d76  mov     rcx, [rbp+90h+var_68]; pv
0x180206d7a  test    rcx, rcx
0x180206d7d  jz      loc_1802074D4
0x180206d83  call    cs:__imp_CoTaskMemFree
0x180206d89  jmp     loc_1802074D4
0x180206d8e  mov     [rsp+190h+var_13F], 1
0x180206d93  mov     rcx, [rbp+90h+var_68]; pv
0x180206d97  test    rcx, rcx
0x180206d9a  jz      short loc_180206DA2
0x180206d9c  call    cs:__imp_CoTaskMemFree
0x180206da2  mov     rcx, [r13+20h]
0x180206da6  cmp     [rsp+190h+var_120], rbx
0x180206dab  jnz     short loc_180206DCB
0x180206dad  lea     rdx, [rcx+4]; struct _GUID *
0x180206db1  lea     rcx, [rbp+90h+var_E0]; this
0x180206db5  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180206dba  mov     [rsp+190h+var_160], rax
0x180206dbf  lea     rax, aAppxGdrUnableT; "AppX GDR: Unable to find payload file d"...
0x180206dc6  jmp     loc_180206BAA
0x180206dcb  lea     r8, [rbp+90h+lpMem]; struct AppxPackage **
0x180206dcf  mov     rdx, [rcx+268h]; struct tagDSDataBlob *
0x180206dd6  mov     ecx, [rcx+260h]; unsigned int
0x180206ddc  call    ?CreateFromUpdateRuleMetadata@AppxPackage@@SAJKPEBUtagDSDataBlob@@PEAPEAV1@@Z; AppxPackage::CreateFromUpdateRuleMetadata(ulong,tagDSDataBlob const *,AppxPackage * *)
0x180206de1  mov     r12d, eax
0x180206de4  mov     rsi, [rbp+90h+lpMem]
0x180206de8  test    eax, eax
0x180206dea  js      loc_1802074D4
0x180206df0  cmp     dword ptr [rsi], 3
0x180206df3  jnz     short loc_180206DFF
0x180206df5  cmp     [rsi+8], rbx
0x180206df9  jnz     short loc_180206DFF
0x180206dfb  mov     al, 1
0x180206dfd  jmp     short loc_180206E01
0x180206dff  xor     al, al
0x180206e01  mov     rdx, [r13+20h]
0x180206e05  add     rdx, 4; struct _GUID *
0x180206e09  test    al, al
0x180206e0b  jz      short loc_180206E27
0x180206e0d  lea     rcx, [rbp+90h+var_E0]; this
0x180206e11  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180206e16  mov     [rsp+190h+var_160], rax
0x180206e1b  lea     rax, aAppxGdrFlatBun; "AppX GDR: Flat bundle update %ws is leg"...
0x180206e22  jmp     loc_180206BAA
0x180206e27  mov     rbx, [rsp+190h+var_130]
0x180206e2c  mov     rax, [rbx]
0x180206e2f  xor     r8d, r8d
0x180206e32  mov     rcx, rbx
0x180206e35  mov     rax, [rax+90h]
0x180206e3c  call    _guard_dispatch_icall
0x180206e41  mov     rdx, [r13+20h]
0x180206e45  add     rdx, 4; struct _GUID *
0x180206e49  lea     rcx, [rbx-38h]; this
0x180206e4d  lea     r8, [rsp+190h+var_128]; struct CAppxDeploymentOperation **
0x180206e52  call    ?GetDeploymentOperation@CUHAppXHandler@@IEAA_NAEBU_GUID@@PEAPEAVCAppxDeploymentOperation@@@Z; CUHAppXHandler::GetDeploymentOperation(_GUID const &,CAppxDeploymentOperation * *)
0x180206e57  test    al, al
0x180206e59  jnz     short loc_180206E7A
0x180206e5b  mov     rcx, [rsp+190h+var_128]
0x180206e60  test    rcx, rcx
0x180206e63  jz      short loc_180206E71
0x180206e65  mov     rax, [rcx]
0x180206e68  mov     rax, [rax+10h]
0x180206e6c  call    _guard_dispatch_icall
0x180206e71  xor     ebx, ebx
0x180206e73  mov     [rsp+190h+var_128], rbx
0x180206e78  jmp     short loc_180206E7F
0x180206e7a  mov     rbx, [rsp+190h+var_128]
0x180206e7f  xor     r9d, r9d; lpName
0x180206e82  xor     r8d, r8d; bInitialState
0x180206e85  lea     edx, [r9+1]; bManualReset
0x180206e89  xor     ecx, ecx; lpEventAttributes
0x180206e8b  call    cs:__imp_CreateEventW
0x180206e91  mov     r12, rax
0x180206e94  mov     rcx, r15; hObject
0x180206e97  call    cs:__imp_CloseHandle
0x180206e9d  mov     r15, r12
0x180206ea0  xor     eax, eax
0x180206ea2  test    r12, r12
0x180206ea5  jnz     short loc_180206ECF
0x180206ea7  call    cs:__imp_GetLastError
0x180206ead  movzx   r12d, ax
0x180206eb1  or      r12d, 80070000h
0x180206eb8  test    eax, eax
0x180206eba  cmovle  r12d, eax
0x180206ebe  mov     eax, 8000FFFFh
0x180206ec3  test    r12d, r12d
0x180206ec6  cmovns  r12d, eax
0x180206eca  jmp     loc_1802074D4
0x180206ecf  cmp     [rsp+190h+var_13F], al
0x180206ed3  jnz     short loc_180206F18
  ... truncated ...
```
