# CAgentDownloadManager::HandleDownloadJobCompletion(_GUID const *,long,tagDownloadJobError const *,DownloadManagerUpdateID *,int)

- ea: `0x1800a1254`
- end: `0x1800a2bad`
- name: `?HandleDownloadJobCompletion@CAgentDownloadManager@@QEAAXPEBU_GUID@@JPEBUtagDownloadJobError@@PEAUDownloadManagerUpdateID@@H@Z`
- size: `6489`
- prototype: `void __fastcall(CAgentDownloadManager *this, struct _GUID *, int, const struct tagDownloadJobError *, struct DownloadManagerUpdateID *, int)`
- caller_count: `7`
- callee_count: `67`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009c7a0`
- `0x18009cac0`
- `0x1800a08e8`
- `0x1800a36f8`
- `0x1800a3c90`
- `0x1800f47c0`
- `0x180102620`

## callees

- `0x18003b908`
- `0x18003b9c4`
- `0x18007f4e0`
- `0x18008027c`
- `0x18008036c`
- `0x1800805b4`
- `0x180080a80`
- `0x180080c80`
- `0x180080f5c`
- `0x180082544`
- `0x180086a28`
- `0x180089750`
- `0x180089adc`
- `0x18008a914`
- `0x18008bb88`
- `0x18008d968`
- `0x18008de68`
- `0x180093614`
- `0x1800941cc`
- `0x18009573c`
- `0x18009595c`
- `0x18009a144`
- `0x18009f044`
- `0x1800a0ff8`
- `0x1800a1254`
- `0x1800a77fc`
- `0x1800a87e0`
- `0x1800a8d28`
- `0x1800a9464`
- `0x1800a96b4`
- `0x1800abea0`
- `0x1800ac604`
- `0x1800ac854`
- `0x1800ad8c0`
- `0x1800b0e00`
- `0x1800b0ea4`
- `0x1800e1ec0`
- `0x1800e21bc`
- `0x1800e2634`
- `0x1800e3d30`
- `0x1800e4630`
- `0x1800e5848`
- `0x1800e5dfc`
- `0x1800e6358`
- `0x1800e6b34`
- `0x1800e8430`
- `0x1800e84fc`
- `0x1800ea0b4`
- `0x1800ec0b0`
- `0x1800f1d34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1349`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1e80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a223f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a22e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a27ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1349`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1e80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a223f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a22e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a27ac`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800a2395`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800a2395`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1d09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a22cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a249b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a27c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a27eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2ad4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a1d09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a22cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a249b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a27c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a27eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a2ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a239f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a239f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a1f6e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a1f6e`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800a131a`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800a2b69`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800a131a`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800a2b69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a1ff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a20b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a21c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a21d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a1ff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a20b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a21c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a21d5`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800a1eb5`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800a1eb5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a133c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a133c`

## string_xrefs

- `0x1800a266f`: `SetUpdateExpiration.`
- `0x1800a1d27`: `Calling HandleDownloadJobCompletion for update %ws`
- `0x1800a2059`: `All available CDNs for the update %ws are tried but the download job %ws still failed.`
- `0x1800a25f9`: `All available CDNs for the update %ws are tried but the download job %ws still failed.`
- `0x1800a148b`: `%ws job {%ws} failed, updateId = %ws, hr = 0x%08lX. File URL = %ws, local path = %ws, The response headers = %ws`
- `0x1800a1586`: `%ws job {%ws} had an out of band error, updateId = %ws`
- `0x1800a15ec`: `%ws job {%ws} completed successfully, updateId = %ws`
- `0x1800a1653`: `%ws job %ws sent partial download completion callback. Requesting the remaining payload to be downloaded.`
- `0x1800a1932`: `Handler is expecting a GDR to handle the download job failure for update %ws...`
- `0x1800a1b8b`: `Setting %ws job %ws as the last job for update %ws`
- `0x1800a1be6`: `Complete.`
- `0x1800a1c1b`: `Cancel after Complete`
- `0x1800a1e57`: `HandleDownloadJobCompletion for update %ws`
- `0x1800a2175`: `Update is already marked complete; skipping moving working sandbox.`
- `0x1800a274a`: `HandleDownloadJobCompletion: will retry with different CDN for update %ws error 0x%x`
- `0x1800a247f`: `CUpdateDownloadJob::MoveCompletedFiles`

## pseudocode

```c
void __fastcall CAgentDownloadManager::HandleDownloadJobCompletion(
        CAgentDownloadManager *this,
        struct _GUID *a2,
        int a3,
        const struct tagDownloadJobError *a4,
        struct DownloadManagerUpdateID *a5,
        int a6)
{
  char v7; // r12
  struct tagDSFileState *v8; // r14
  struct CUpdateDownloadJob *v9; // rbx
  char v10; // r15
  struct tagDSUpdateMetadata *v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // r8
  bool v14; // al
  struct _GUID *v15; // rdi
  int updated; // r12d
  int v17; // r12d
  int v18; // esi
  __int64 v19; // rdi
  const wchar_t *JobTypeAsString; // rax
  int Progress; // eax
  UINT64 BytesTransferred; // rdi
  unsigned int v23; // eax
  bool v24; // zf
  const struct DownloadManagerUpdateID *v25; // rdi
  int v26; // esi
  __int64 v27; // rdi
  const wchar_t *v28; // rax
  int v29; // r15d
  __int64 v30; // rdi
  const wchar_t *v31; // rax
  __int64 v32; // rdi
  const wchar_t *v33; // rax
  struct tagDSFile *v34; // rax
  const struct _GUID *v35; // rax
  bool v36; // cl
  __int64 v37; // rdi
  BOOL v38; // edx
  int v39; // eax
  __int64 v40; // rax
  bool v41; // di
  CAgentDownloadManager *v42; // rcx
  __int64 v43; // r9
  char v44; // al
  int v45; // r15d
  int v46; // r15d
  const struct _GUID *v47; // rax
  __int64 v48; // rdi
  const wchar_t *v49; // rax
  int v50; // eax
  ULONG v51; // r15d
  wchar_t **v52; // rdi
  wchar_t **v53; // rdi
  void *v54; // rdi
  struct tagDSFileState *v55; // r12
  __int64 v56; // rax
  __int64 v57; // rax
  _QWORD *v58; // r12
  __int64 v59; // rax
  UINT v60; // eax
  size_t v61; // r8
  wchar_t **v62; // r10
  unsigned int v63; // eax
  __int64 v64; // r9
  __int64 v65; // rcx
  _WORD *v66; // rax
  const struct _GUID *v67; // rax
  __int64 v68; // r15
  __int64 v69; // rax
  wchar_t **v70; // r15
  struct tagDSFileState *v71; // rdi
  LPVOID *v72; // rdi
  LPVOID *v73; // r15
  wchar_t **v74; // rax
  LPCRITICAL_SECTION *v75; // r15
  char *v76; // r12
  unsigned int v77; // edx
  unsigned int v78; // r8d
  __int64 v79; // rdi
  wchar_t **v80; // rax
  struct _RTL_CRITICAL_SECTION *v81; // rcx
  struct _RTL_CRITICAL_SECTION *v82; // rax
  signed int LastError; // eax
  struct _RTL_CRITICAL_SECTION *v84; // rax
  int v85; // eax
  int v86; // r15d
  _WORD *v87; // rax
  const struct _GUID *v88; // rax
  __int64 v89; // rdi
  __int64 v90; // rax
  int v91; // eax
  BOOL v92; // edi
  __int64 v93; // rax
  int v94; // eax
  unsigned int v95; // eax
  wchar_t v96; // r8
  int v97; // eax
  struct tagDSFile *v98; // rdx
  const struct tagDownloadJobError *v99; // r9
  int v100; // eax
  struct tagDSFileState *v101; // rax
  unsigned int IndexOf; // eax
  int v103; // [rsp+20h] [rbp-E0h]
  int v104; // [rsp+30h] [rbp-D0h]
  unsigned int *v105; // [rsp+38h] [rbp-C8h]
  int v106; // [rsp+40h] [rbp-C0h]
  bool IsPatchUpdateHandler; // [rsp+70h] [rbp-90h]
  char v108; // [rsp+71h] [rbp-8Fh]
  bool v109; // [rsp+73h] [rbp-8Dh] BYREF
  int v110; // [rsp+74h] [rbp-8Ch] BYREF
  char v111; // [rsp+78h] [rbp-88h]
  bool v112; // [rsp+79h] [rbp-87h] BYREF
  char v113; // [rsp+7Ah] [rbp-86h]
  int v114; // [rsp+7Ch] [rbp-84h]
  int v115; // [rsp+80h] [rbp-80h]
  wchar_t **v116; // [rsp+88h] [rbp-78h] BYREF
  struct tagDSFileState *v117; // [rsp+90h] [rbp-70h] BYREF
  int v118; // [rsp+98h] [rbp-68h] BYREF
  wchar_t **v119; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v120; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t **v121; // [rsp+B0h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  struct tagDSFile *v123; // [rsp+C0h] [rbp-40h] BYREF
  struct CUpdateDownloadJob *v124; // [rsp+C8h] [rbp-38h] BYREF
  struct tagDSUpdateMetadata *v125; // [rsp+D0h] [rbp-30h] BYREF
  struct tagDSFileState *v126; // [rsp+D8h] [rbp-28h]
  struct _GUID *v127; // [rsp+E0h] [rbp-20h]
  const struct tagDownloadJobError *v128; // [rsp+E8h] [rbp-18h]
  __int128 v129; // [rsp+F0h] [rbp-10h] BYREF
  struct tagDSFileState *v130; // [rsp+100h] [rbp+0h]
  __int128 v131; // [rsp+108h] [rbp+8h] BYREF
  int v132; // [rsp+118h] [rbp+18h]
  struct _GUID v133; // [rsp+11Ch] [rbp+1Ch]
  void *v134; // [rsp+130h] [rbp+30h]
  struct CUpdateDownloadJob *v135; // [rsp+140h] [rbp+40h]
  __int64 v136; // [rsp+148h] [rbp+48h]
  int v137; // [rsp+150h] [rbp+50h]
  __int16 v138; // [rsp+154h] [rbp+54h]
  char *v139; // [rsp+160h] [rbp+60h] BYREF
  char *v140; // [rsp+168h] [rbp+68h]
  struct _GUID v141; // [rsp+170h] [rbp+70h]
  void *v142; // [rsp+180h] [rbp+80h]
  __int64 v143; // [rsp+188h] [rbp+88h]
  unsigned int v144; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned int v145; // [rsp+1B4h] [rbp+B4h] BYREF
  void *v146[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v147; // [rsp+1C8h] [rbp+C8h]
  struct ISusUpdateDownloadRequest *v148; // [rsp+1D0h] [rbp+D0h] BYREF
  struct _GUID v149; // [rsp+1D8h] [rbp+D8h] BYREF
  int v150; // [rsp+1E8h] [rbp+E8h]
  struct _BG_JOB_PROGRESS lpMem; // [rsp+1F0h] [rbp+F0h] BYREF
  IUnknown *ppOldObject[2]; // [rsp+208h] [rbp+108h] BYREF
  struct _GUID v153; // [rsp+218h] [rbp+118h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+228h] [rbp+128h] BYREF
  _OWORD v155[2]; // [rsp+230h] [rbp+130h] BYREF
  char v156[144]; // [rsp+250h] [rbp+150h] BYREF
  wchar_t v157[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v128 = a4;
  v115 = a3;
  v127 = a2;
  v7 = 0;
  v8 = 0;
  v126 = 0;
  v118 = 0;
  v145 = 0;
  ppOldObject[0] = 0;
  ppOldObject[1] = 0;
  v9 = 0;
  v124 = 0;
  v148 = 0;
  v114 = 1;
  v113 = 0;
  v109 = 0;
  v119 = 0;
  v120 = 0;
  v111 = 0;
  SystemTimeAsFileTime = 0;
  v10 = 0;
  v11 = 0;
  v125 = 0;
  IsPatchUpdateHandler = 0;
  v112 = 0;
  memset(&lpMem, 0, sizeof(lpMem));
  if ( CoSwitchCallContext(0, &ppOldObject[1]) >= 0 )
  {
    LODWORD(ppOldObject[0]) = 1;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
    v7 = 1;
    v14 = v127
        ? CAgentDownloadManager::FindDownloadJobByJobID(this, v127, &v124)
        : CAgentDownloadManager::FindDownloadJobByUpdateID(this, a5, &v124);
    v9 = v124;
    if ( v14 )
    {
      v15 = (struct _GUID *)(*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(**((_QWORD **)v124 + 13) + 40LL))(
                              *((_QWORD *)v124 + 13),
                              v12,
                              v13,
                              0);
      pv = v15;
      v149 = *(struct _GUID *)((char *)v9 + 8);
      v150 = *((_DWORD *)v9 + 6);
      v153 = *(struct _GUID *)((char *)v9 + 28);
      v116 = (wchar_t **)*((_QWORD *)v9 + 6);
      updated = CAgentDownloadManager::SetUpdateSandboxInUse(
                  this,
                  (const struct tagDSGlobalUpdateId *)&v149,
                  (const wchar_t *)v116,
                  1);
      v110 = updated;
      if ( updated < 0 )
        goto LABEL_201;
      v109 = 1;
      if ( v128 )
      {
        v17 = *((_DWORD *)v128 + 2);
        v115 = v17;
        if ( v17 >= 0 )
        {
          v17 = -2145099767;
          v115 = -2145099767;
        }
      }
      else
      {
        v17 = v115;
        if ( v115 >= 0 )
          goto LABEL_20;
      }
      if ( v128 )
      {
        v18 = Trace::UpdateIdToString::UpdateIdToString(
                (Trace::UpdateIdToString *)v156,
                (const struct tagDSGlobalUpdateId *)&v149);
        v19 = Trace::GuidToString::GuidToString((Trace::GuidToString *)&v139, v15);
        JobTypeAsString = CUpdateDownloadJob::GetJobTypeAsString(v9);
        v106 = v18;
        WUTrace(
          0,
          0,
          2,
          3,
          0,
          L"%ws job {%ws} failed, updateId = %ws, hr = 0x%08lX. File URL = %ws, local path = %ws, The response headers = %ws",
          JobTypeAsString,
          v19);
        Progress = CUpdateDownloadJob::GetProgress(v9, &lpMem, &v145);
        BytesTransferred = lpMem.BytesTransferred;
        if ( Progress >= 0 )
          WUTrace(
            0,
            0,
            2,
            4,
            0,
            L"  Progress failure bytes total = %I64u, bytes transferred = %I64u",
            lpMem.BytesTotal,
            lpMem.BytesTransferred);
        v23 = *((_DWORD *)v9 + 147);
        if ( v23 < *((_DWORD *)v9 + 148) && *((_DWORD *)v9 + 138) == 12 )
        {
          v24 = BytesTransferred == 0;
          v25 = (struct CUpdateDownloadJob *)((char *)v9 + 8);
          if ( !v24 )
          {
            v10 = 1;
            *((_DWORD *)v9 + 147) = v23 + 1;
            goto LABEL_27;
          }
          goto LABEL_24;
        }
        v10 = 0;
LABEL_26:
        v25 = (struct CUpdateDownloadJob *)((char *)v9 + 8);
LABEL_27:
        v34 = (struct tagDSFile *)operator new(0x1D0u, (const struct std::nothrow_t *)&std::nothrow);
        v123 = v34;
        if ( v34 )
        {
          v8 = DownloadReportingInfo::DownloadReportingInfo(v34);
          v126 = v8;
          v117 = v8;
          if ( v8 )
          {
            CAgentDownloadManager::GetUpdateReportingInfoHelper(
              this,
              v25,
              0,
              0,
              v9,
              (CAgentDownloadManager *)((char *)this + 552),
              v8);
            v117 = v8;
          }
        }
        else
        {
          v117 = 0;
          v8 = 0;
          v126 = 0;
        }
        CDownloadRegulator::RemoveUpdateFromSuspensionList(*((CDownloadRegulator **)this + 259), &v149);
        CAgentDownloadManager::RemoveUpdateRequest(this, v25);
        if ( !v10 )
        {
          CAgentDownloadManager::RemoveDownloadJobFromTable(this, v9, 1);
          if ( !*((_BYTE *)v9 + 536) )
          {
            v35 = (const struct _GUID *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v9 + 13) + 40LL))(*((_QWORD *)v9 + 13));
            CAgentDownloadManager::RemoveDownloadJobFromDatastore(this, v35);
          }
        }
        updated = CAgentDownloadManager::GetUpdateMetadata(
                    this,
                    &v149,
                    *((_BYTE *)this + 1856) != 0 ? 3876 : 3620,
                    0,
                    &v153,
                    &v125);
        v110 = updated;
        v11 = v125;
        if ( updated >= 0 )
        {
          IsPatchUpdateHandler = CAgentDownloadManager::IsPatchUpdateHandler(
                                   this,
                                   (struct tagDSUpdateMetadata *)((char *)v125 + 120));
          updated = CAgentDownloadManager::GetApprovedPayloadHashListForUpdate(
                      this,
                      &v153,
                      v11,
                      &v120,
                      (wchar_t *const **)&v119);
          v110 = updated;
          if ( updated < 0 )
            goto LABEL_201;
          v36 = IsPatchUpdateHandler;
          if ( IsPatchUpdateHandler )
          {
            v37 = *((_QWORD *)this + 27);
            if ( v148 )
            {
              (*(void (__fastcall **)(struct ISusUpdateDownloadRequest *, __int64, __int64, _QWORD))(*(_QWORD *)v148 + 16LL))(
                v148,
                v12,
                v13,
                0);
              v148 = 0;
            }
            updated = CUHHandlerManager::GetHandler(
                        v37,
                        *((unsigned int *)v11 + 30),
                        v13,
                        1,
                        &GUID_dde28533_d0b1_4b84_8610_2d24fcdcb9c1,
                        &v148);
            v110 = updated;
            if ( updated < 0 )
              goto LABEL_201;
            v144 = 1;
            (*(void (__fastcall **)(struct ISusUpdateDownloadRequest *, struct tagDSUpdateMetadata *, unsigned int *, _QWORD))(*(_QWORD *)v148 + 128LL))(
              v148,
              v11,
              &v144,
              0);
            v38 = v144 == 1;
            v114 = v38;
            v25 = (struct CUpdateDownloadJob *)((char *)v9 + 8);
            v36 = IsPatchUpdateHandler;
          }
          else
          {
            v38 = v114;
          }
          v39 = v115;
          if ( v115 >= 0 || !v36 || v38 )
          {
LABEL_48:
            if ( updated < 0 || (v41 = IsPatchUpdateHandler, v39 < 0) && IsPatchUpdateHandler )
            {
              if ( !v10 )
              {
                updated = CUpdateDownloadJob::Cancel(v9);
                v110 = updated;
              }
              goto LABEL_183;
            }
            v108 = 1;
            memset(v157, 0, 520);
            updated = CAgentDownloadManager::GetUpdateDownloadPath(
                        this,
                        (const struct tagDSGlobalUpdateId *)&v149,
                        (const wchar_t *)v116,
                        v157,
                        0x104u);
            v110 = updated;
            v43 = 0;
            if ( updated < 0 )
              goto LABEL_201;
            if ( IsPatchUpdateHandler && !v114 && !*((_BYTE *)v9 + 536) )
            {
              updated = CAgentDownloadManager::HandleTempFileCleanup(
                          v42,
                          v9,
                          v148,
                          (const struct tagDSGlobalUpdateId *)&v149,
                          v11,
                          v157);
              v110 = updated;
              v43 = 0;
              if ( updated < 0 )
                goto LABEL_201;
            }
            if ( v10 )
            {
LABEL_60:
              if ( *((_BYTE *)v9 + 512) )
                goto LABEL_183;
              if ( v41 )
              {
                v45 = v114;
                if ( !v114 )
                {
                  v144 = 0;
                  v116 = 0;
                  v121 = 0;
                  lpMem.BytesTotal = (UINT64)&CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::`vftable';
                  lpMem.BytesTransferred = 0;
                  *(_QWORD *)&lpMem.FilesTotal = 0;
                  v146[0] = &CBSTRList::`vftable';
                  v146[1] = 0;
                  v147 = 0;
                  pv = 0;
                  LODWORD(v155[0]) = 0;
                  *(struct _GUID *)((char *)v155 + 4) = v149;
                  DWORD1(v155[1]) = v150;
                  updated = CUpdateDownloadJob::GetFileLocalNamesAndDigests(v9, &v144, &v116, &v121);
                  v110 = updated;
                  if ( updated < 0 )
                  {
                    CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::~CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>(v146);
                    CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>(&lpMem);
                    goto LABEL_202;
                  }
                  v51 = v144;
                  v52 = v116;
                  if ( v116 || !v144 )
                  {
                    CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::RemoveArraySection(&lpMem);
                    SusFree((void *)lpMem.BytesTransferred);
                    lpMem.BytesTransferred = (UINT64)v52;
                    lpMem.FilesTransferred = v51;
                    lpMem.FilesTotal = v51;
                  }
                  v53 = v121;
                  if ( v121 || !v51 )
                  {
                    CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::RemoveArraySection(v146);
                    SusFree(v146[1]);
                    v146[1] = v53;
                    HIDWORD(v147) = v51;
                    LODWORD(v147) = v51;
                  }
                  CAgentDownloadManager::GetFlightData(
                    this,
                    &v153,
                    (const struct tagDsqUpdateId *)v155,
                    (wchar_t **)&pv,
                    0);
                  v144 = 0;
                  v54 = pv;
                  if ( !v51 )
                    goto LABEL_94;
LABEL_78:
                  v55 = v117;
                  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
                  v56 = Trace::UpdateIdToString::UpdateIdToString(
                          (Trace::UpdateIdToString *)v156,
                          (const struct tagDSGlobalUpdateId *)&v149);
                  WUTrace(0, 0, 2, 5, 0, L"Calling HandleDownloadJobCompletion for update %ws", v56);
                  v139 = 0;
                  v140 = 0;
                  v143 = 0;
                  v141 = v153;
                  v142 = v54;
                  v57 = 0;
                  if ( *((_DWORD *)v55 + 41) )
                    v57 = **((_QWORD **)v55 + 19);
                  v143 = v57;
                  v139 = (char *)v55 + 200;
                  v140 = (char *)v55 + 329;
                  LOBYTE(v104) = 1;
                  v58 = v146[1];
                  (*(void (__fastcall **)(_QWORD, wchar_t *, _QWORD, _QWORD, _QWORD, _QWORD, int))(**((_QWORD **)v9 + 13)
                                                                                                 + 304LL))(
                    *((_QWORD *)v9 + 13),
                    v157,
                    *(_QWORD *)(lpMem.BytesTransferred + 8LL * v144),
                    0,
                    *((_QWORD *)v146[1] + v144),
                    0,
                    v104);
                  updated = (*(__int64 (__fastcall **)(struct ISusUpdateDownloadRequest *, struct tagDSUpdateMetadata *, wchar_t *, _QWORD, _QWORD, char *, char **))(*(_QWORD *)v148 + 56LL))(
                              v148,
                              v11,
                              v157,
                              *(_QWORD *)(lpMem.BytesTransferred + 8LL * v144),
                              v58[v144],
                              (char *)this + 96,
                              &v139);
                  v110 = updated;
                  v59 = Trace::UpdateIdToString::UpdateIdToString(
                          (Trace::UpdateIdToString *)v156,
                          (const struct tagDSGlobalUpdateId *)&v149);
                  WUTrace(0, 0, 2, 5, updated, L"HandleDownloadJobCompletion for update %ws", v59);
                  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
                  if ( updated >= 0 )
                  {
                    if ( !v120 )
                      goto LABEL_92;
                    if ( !v119 )
                      goto LABEL_92;
                    v60 = SysStringByteLen(*((BSTR *)v146[1] + v144));
                    v61 = v60;
                    LODWORD(v121) = v60;
                    v62 = (wchar_t **)*((_QWORD *)v146[1] + v144);
                    v116 = v62;
                    v63 = 0;
                    v145 = 0;
                    if ( !*((_DWORD *)v11 + 116) )
                      goto LABEL_92;
                    v64 = *((_QWORD *)v11 + 59);
                    while ( 1 )
                    {
                      v65 = v64 + 248LL * v63;
                      v123 = (struct tagDSFile *)v65;
                      if ( *(_DWORD *)v65 == (_DWORD)v61 )
                      {
                        if ( !memcmp(*(const void **)(v65 + 8), v62, v61) )
                        {
                          if ( !IsFileInApprovalList(v123, v120, (const wchar_t *const *)v119) )
                          {
                            updated = -2145124254;
                            v110 = -2145124254;
                            DeleteFileW(*(LPCWSTR *)(lpMem.BytesTransferred + 8LL * v144));
                          }
LABEL_92:
                          if ( updated < 0 )
                            break;
                          if ( ++v144 >= v51 )
                            goto LABEL_94;
                          goto LABEL_78;
                        }
                        v63 = v145;
                        v61 = (unsigned int)v121;
                        v64 = *((_QWORD *)v11 + 59);
                        v62 = v116;
                      }
                      v145 = ++v63;
                      if ( v63 >= *((_DWORD *)v11 + 116) )
                        goto LABEL_92;
                    }
                  }
                  if ( CAgentDownloadManager::CanRetryWithDifferentCDNForError(this, &v153, updated) )
                  {
                    if ( !*((_BYTE *)v9 + 577)
                      && (!*((_BYTE *)v9 + 576) || (v66 = (_WORD *)*((_QWORD *)v9 + 23)) == 0 || !*v66) )
                    {
                      v111 = 1;
                      if ( v54 )
                        CoTaskMemFree(v54);
                      CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::~CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>(v146);
                      CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>(&lpMem);
                      goto LABEL_201;
                    }
                    v67 = (const struct _GUID *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v9 + 13) + 40LL))(*((_QWORD *)v9 + 13));
                    v68 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v156, v67);
                    v69 = Trace::UpdateIdToString::UpdateIdToString(
                            (Trace::UpdateIdToString *)&v129,
                            (const struct tagDSGlobalUpdateId *)&v149);
                    WUTrace(
                      0,
                      0,
                      2,
                      1,
                      updated,
                      L"All available CDNs for the update %ws are tried but the download job %ws still failed.",
                      v69,
                      v68);
                  }
                  (*(void (__fastcall **)(struct ISusUpdateDownloadRequest *, struct tagDSUpdateMetadata *, wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v148 + 112LL))(
                    v148,
                    v11,
                    v157,
                    (unsigned int)updated,
                    0);
LABEL_94:
                  if ( updated == -2147467263 )
                  {
                    updated = 0;
                    v110 = 0;
                  }
                  else
                  {
                    v108 = 0;
                  }
                  if ( v54 )
                    CoTaskMemFree(v54);
                  CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>::~CSusArrayList<wchar_t *,CSusArrayBSTRListItemOpDelete>(v146);
                  CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>(&lpMem);
                  v41 = IsPatchUpdateHandler;
                }
              }
              if ( !v108 )
                goto LABEL_183;
              v116 = 0;
              v117 = 0;
              v144 = 0;
              updated = CUpdateDownloadJob::ValidateCompletedFiles(
                          v9,
                          v120,
                          v119,
                          (struct tagDsqFileId **)&v116,
                          &v117,
                          &v144,
                          &v118);
              v110 = updated;
              if ( updated < 0 )
                goto LABEL_183;
              v145 = 0;
              if ( (int)CAgentDownloadManager::IsUpdateDownloaded(
                          this,
                          (struct CUpdateDownloadJob *)((char *)v9 + 8),
                          (int *)&v145,
                          0) < 0 )
                goto LABEL_115;
              if ( v145 )
              {
                WUTrace(0, 0, 2, 4, 0, L"Update is already marked complete; skipping moving working sandbox.");
                goto LABEL_115;
              }
              if ( !v144 || v41 && v118 < 0 )
                goto LABEL_115;
              v75 = 0;
              if ( !*((_DWORD *)v9 + 28) )
              {
LABEL_165:
                if ( updated < 0 )
                  goto LABEL_171;
                if ( *((_DWORD *)v9 + 29) || *((_BYTE *)v9 + 560) )
                {
                  if ( *((_DWORD *)v9 + 28) )
                    v85 = CUpdateDownloadJob::MovePatchFilesToDownloadDirectory(v9);
                  else
                    v85 = CUpdateDownloadJob::MoveUpdateFilesToDownloadDirectory(v9);
                  updated = v85;
                  if ( v85 >= 0 )
                    goto LABEL_170;
                }
                else
                {
                  updated = -2145095681;
                }
                WUTrace("CUpdateDownloadJob::MoveCompletedFiles", 2566, 2, 1, updated, L"Method failed");
LABEL_170:
                v110 = updated;
LABEL_171:
                if ( v75 )
                {
                  LeaveCriticalSection(v75[2]);
                  AllocatedLock::~AllocatedLock((AllocatedLock *)v75);
                  operator delete(v75, (const struct std::nothrow_t *)0x20);
                }
                if ( !v41 )
                {
                  v71 = v117;
                  v70 = v116;
                  if ( updated >= 0 )
                  {
                    updated = CAgentDownloadManager::UpdateFileStatesInDatastore(
                                this,
                                (const struct LockedUpdateId *)&v149,
                                v144,
                                (const struct tagDsqFileId *)v116,
                                v117);
                    v110 = updated;
                  }
                  goto LABEL_116;
                }
LABEL_115:
                v70 = v116;
                v71 = v117;
LABEL_116:
                if ( v144 )
                {
                  v72 = (LPVOID *)((char *)v71 + 16);
                  v73 = (LPVOID *)(v70 + 1);
                  v74 = (wchar_t **)v144;
                  v119 = (wchar_t **)v144;
                  do
                  {
                    if ( *v73 )
                    {
                      CoTaskMemFree(*v73);
                      v74 = v119;
                    }
                    if ( *v72 )
                    {
                      CoTaskMemFree(*v72);
                      v74 = v119;
                    }
                    v73 += 2;
                    v72 += 7;
                    v74 = (wchar_t **)((char *)v74 - 1);
                    v119 = v74;
                  }
                  while ( v74 );
                }
                SusFree(v116);
                SusFree(v117);
LABEL_183:
                CAgentDownloadManager::PersistBytesDownloadedForUpdateFromJob(this, v9, 1);
                v13 = (unsigned int)v115;
                if ( v115 >= 0 )
                {
                  if ( updated < 0 )
                    goto LABEL_201;
                  v86 = v118;
                  if ( v118 < 0 )
                  {
                    if ( CAgentDownloadManager::CanRetryWithDifferentCDNForError(this, &v153, v118) )
                    {
                      if ( *((_BYTE *)v9 + 577)
                        || *((_BYTE *)v9 + 576) && (v87 = (_WORD *)*((_QWORD *)v9 + 23)) != 0 && *v87 )
                      {
                        v88 = (const struct _GUID *)(*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(**((_QWORD **)v9 + 13) + 40LL))(
                                                      *((_QWORD *)v9 + 13),
                                                      v12,
                                                      v13,
                                                      0);
                        v89 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v156, v88);
                        v90 = Trace::UpdateIdToString::UpdateIdToString(
                                (Trace::UpdateIdToString *)&v129,
                                (const struct tagDSGlobalUpdateId *)&v149);
                        WUTrace(
                          0,
                          0,
                          2,
                          1,
                          updated,
                          L"All available CDNs for the update %ws are tried but the download job %ws still failed.",
                          v90,
                          v89);
                      }
                      else
                      {
                        v111 = 1;
                      }
                    }
                    updated = v86;
                    v110 = v86;
                  }
                }
                else
                {
                  updated = v115;
                  v110 = v115;
                }
                if ( updated >= 0 )
                {
                  CAgentDownloadManager::CancelDownloadJobsForUpdate(
                    this,
                    (struct CUpdateDownloadJob *)((char *)v9 + 8));
                  *(_OWORD *)v146 = *(_OWORD *)((char *)v9 + 8);
                  LODWORD(v147) = *((_DWORD *)v9 + 6);
                  v91 = CAgentDownloadManager::SetUpdateExpiration(this, v146, *((_QWORD *)v9 + 6), 1);
                  if ( v91 < 0 )
                    WUTrace(0, 0, 2, 3, v91, L"SetUpdateExpiration.");
                  if ( v11 )
                  {
                    DsqFreeObject(v11, 1u, 0x2FAFu, 1);
                    SusFree(v11);
                  }
                  v11 = 0;
                  v125 = 0;
                }
                goto LABEL_201;
              }
              v76 = (char *)this + 1560;
              v119 = 0;
              EnterCriticalSection((LPCRITICAL_SECTION)this + 39);
              v77 = 0;
              v78 = *((_DWORD *)this + 407);
              if ( v78 )
              {
                while ( v77 < v78 )
                {
                  v79 = *((_QWORD *)v76 + 7) + 32LL * v77;
                  updated = 0;
                  if ( *(_QWORD *)(v79 + 4) == *(_QWORD *)&v149.Data1
                    && *(_QWORD *)(v79 + 12) == *(_QWORD *)v149.Data4
                    && *(_DWORD *)v79 )
                  {
                    goto LABEL_150;
                  }
                  v80 = v119;
                  if ( !*(_DWORD *)v79 )
                  {
                    if ( !v119 )
                      v80 = (wchar_t **)v79;
                    v119 = v80;
                  }
                  if ( ++v77 >= v78 )
                  {
                    if ( v80 )
                    {
                      v79 = (__int64)v80;
                      goto LABEL_150;
                    }
                    v76 = (char *)this + 1560;
                    goto LABEL_147;
                  }
                  v76 = (char *)this + 1560;
                }
              }
              else
              {
LABEL_147:
                v145 = 0;
                memset(v155, 0, sizeof(v155));
                updated = (*(__int64 (__fastcall **)(char *, _OWORD *, unsigned int *))(*((_QWORD *)v76 + 6) + 8LL))(
                            v76 + 48,
                            v155,
                            &v145);
                if ( updated < 0 )
                  goto LABEL_143;
                if ( v145 < *((_DWORD *)this + 407) )
                {
                  v79 = *((_QWORD *)this + 202) + 32LL * v145;
                  updated = 0;
LABEL_150:
                  if ( !*(_QWORD *)(v79 + 24) )
                  {
                    v82 = (struct _RTL_CRITICAL_SECTION *)operator new(
                                                            0x28u,
                                                            (const struct std::nothrow_t *)&std::nothrow);
                    *(_QWORD *)(v79 + 24) = v82;
                    if ( !v82 )
                    {
                      updated = -2147024882;
                      goto LABEL_143;
                    }
                    if ( !InitializeCriticalSectionAndSpinCount(v82, 0x80000FA0) )
                    {
                      LastError = GetLastError();
                      updated = (unsigned __int16)LastError | 0x80070000;
                      if ( LastError <= 0 )
                        updated = LastError;
                      if ( updated >= 0 )
                        updated = -2147418113;
                      goto LABEL_143;
                    }
                  }
                  *(struct _GUID *)(v79 + 4) = v149;
                  v75 = (LPCRITICAL_SECTION *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
                  v123 = (struct tagDSFile *)v75;
                  v81 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1560);
                  if ( v75 )
                  {
                    v84 = *(struct _RTL_CRITICAL_SECTION **)(v79 + 24);
                    *(struct _GUID *)v75 = v149;
                    v75[2] = v84;
                    v75[3] = v81;
                    if ( ++*(_DWORD *)v79 == 1 )
                      ++*((_DWORD *)this + 408);
                  }
                  else
                  {
                    v75 = 0;
                    updated = -2147024882;
                  }
                  goto LABEL_144;
                }
              }
              updated = -2145124345;
LABEL_143:
              v81 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1560);
LABEL_144:
              LeaveCriticalSection(v81);
              v110 = updated;
              if ( updated < 0 )
                v75 = 0;
              else
                EnterCriticalSection(v75[2]);
              v41 = IsPatchUpdateHandler;
              goto LABEL_165;
            }
            v44 = *((_BYTE *)v9 + 504);
            if ( v44 && IsPatchUpdateHandler )
            {
              v113 = 1;
              *((_BYTE *)v9 + 560) = 1;
              goto LABEL_60;
            }
            v113 = 0;
            if ( v44 )
            {
              v46 = Trace::UpdateIdToString::UpdateIdToString(
                      (Trace::UpdateIdToString *)v156,
                      (const struct tagDSGlobalUpdateId *)&v149);
              v47 = (const struct _GUID *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v9 + 13) + 40LL))(*((_QWORD *)v9 + 13));
              v48 = Trace::GuidToString::GuidToString((Trace::GuidToString *)&v139, v47);
              v49 = CUpdateDownloadJob::GetJobTypeAsString(v9);
              v106 = v46;
              WUTrace(0, 0, 2, 4, 0, L"Setting %ws job %ws as the last job for update %ws", v49, v48);
              CUpdateDownloadJob::SetAsLastJobForUpdate(v9);
              v41 = IsPatchUpdateHandler;
            }
            updated = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)v9 + 13) + 24LL))(
                        *((_QWORD *)v9 + 13),
                        v12,
                        v13,
                        v43);
            v110 = updated;
            if ( updated >= 0 )
            {
              *((_DWORD *)v9 + 29) = 1;
              goto LABEL_60;
            }
            WUTrace(0, 0, 2, 1, updated, L"Complete.");
            v50 = CUpdateDownloadJob::Cancel(v9);
            if ( v50 < 0 )
              WUTrace(0, 0, 2, 5, v50, L"Cancel after Complete");
LABEL_201:
            v45 = v114;
LABEL_202:
            if ( !v109 )
            {
LABEL_233:
              v7 = 1;
              goto LABEL_234;
            }
            if ( v45 )
              SusDeleteDirectoryW(*((const wchar_t **)v9 + 27), 1, 1, 0, 1, 0, 0, 0, v106);
            v92 = IsPatchUpdateHandler;
            if ( updated < 0 )
            {
              if ( v111 )
              {
                *(_OWORD *)v146 = *(_OWORD *)((char *)v9 + 8);
                LODWORD(v147) = *((_DWORD *)v9 + 6);
                v93 = Trace::UpdateIdToString::UpdateIdToString(
                        (Trace::UpdateIdToString *)&v129,
                        (const struct tagDSGlobalUpdateId *)v146);
                LODWORD(v105) = updated;
                WUTrace(
                  0,
                  0,
                  2,
                  4,
                  0,
                  L"HandleDownloadJobCompletion: will retry with different CDN for update %ws error 0x%x",
                  v93,
                  v105);
                v109 = 0;
                v118 = 0;
                memset(v156, 0, 129);
                v145 = 0;
                if ( v9 != (struct CUpdateDownloadJob *)-376LL )
                  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 384));
                v94 = *((_DWORD *)v9 + 111);
                if ( v94 )
                {
                  v95 = *(_DWORD *)(*((_QWORD *)v9 + 54) + 4LL * (unsigned int)(v94 - 1));
                  LODWORD(v121) = v95;
                  if ( v9 != (struct CUpdateDownloadJob *)-376LL )
                  {
                    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 384));
                    v95 = (unsigned int)v121;
                  }
                }
                else
                {
                  if ( v9 != (struct CUpdateDownloadJob *)-376LL )
                    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 384));
                  v95 = -1;
                }
                CAgentDownloadManager::GetMatchingCallProperties(
                  this,
                  (struct CUpdateDownloadJob *)((char *)v9 + 8),
                  v95,
                  &v109,
                  (enum tagNetworkCostPolicy *)&v118,
                  v156,
                  0,
                  &v145);
                pv = 0;
                v97 = DelimitedStringFromStringArray(
                        *((wchar_t *const **)v9 + 20),
                        *((_DWORD *)v9 + 43),
                        v96,
                        (wchar_t **)&pv);
                v98 = (struct tagDSFile *)pv;
                if ( v97 < 0 )
                  v98 = 0;
                v123 = v98;
                CSusMap<DownloadManagerUpdateID,CDownloadDirNameCache::CCacheEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpDelete<CDownloadDirNameCache::CCacheEntry *>>::Add(
                  (char *)this + 1880,
                  (char *)v9 + 8,
                  &v123);
                LOBYTE(v103) = v109;
                CAgentDownloadManager::QueueUpdateForCDNListRefresh(
                  this,
                  v9,
                  (unsigned int)updated,
                  (unsigned int)v118,
                  v103,
                  v156,
                  v145);
                goto LABEL_232;
              }
              if ( v112
                || (v145 = 1,
                    WUTrace(0, 0, 2, 5, updated, L"Downloading job"),
                    CAgentDownloadManager::RetryFailedJob(this, updated, v9, v99, (int *)&v145),
                    MapWinHttpErrorToSusError(updated, updated, &v110),
                    v145) )
              {
LABEL_232:
                CAgentDownloadManager::NotifyDownloadCallsOfJobDeletion(this, v9);
                *(_OWORD *)v146 = *(_OWORD *)((char *)v9 + 8);
                LODWORD(v147) = *((_DWORD *)v9 + 6);
                CAgentDownloadManager::SetUpdateSandboxInUse(
                  this,
                  (const struct tagDSGlobalUpdateId *)v146,
                  *((const wchar_t **)v9 + 6),
                  0);
                goto LABEL_233;
              }
              updated = v110;
              CAgentDownloadManager::OnUpdateDownloadError(
                this,
                (struct CUpdateDownloadJob *)((char *)v9 + 8),
                v110,
                0,
                0);
              v92 = 0;
            }
            v129 = 0;
            v130 = 0;
            v134 = 0;
            v131 = 0;
            v132 = 0;
            v133 = c_idSrvNone;
            v135 = 0;
            v136 = 0;
            v137 = 0;
            v138 = 101;
            DownloadManagerUpdateID::operator=(&v131, (char *)v9 + 8);
            LODWORD(v129) = v92;
            if ( !v127
              || (v100 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v9 + 13) + 240LL))(*((_QWORD *)v9 + 13)),
                  DWORD1(v129) = 1,
                  !v100) )
            {
              DWORD1(v129) = 0;
            }
            DWORD2(v129) = updated;
            if ( v113 )
            {
              v135 = v9;
              _InterlockedIncrement((volatile signed __int32 *)v9 + 139);
              (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v9 + 13) + 32LL))(*((_QWORD *)v9 + 13), 0);
            }
            v101 = v8;
            v8 = 0;
            v126 = 0;
            v130 = v101;
            if ( v128 )
            {
              LODWORD(v136) = 1;
              HIDWORD(v136) = *((_DWORD *)v128 + 3);
            }
            *(_OWORD *)v146 = *(_OWORD *)((char *)v9 + 8);
            LODWORD(v147) = *((_DWORD *)v9 + 6);
            IndexOf = CSusMap<tagDSGlobalUpdateId,DownloadJobCompletionInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CAgentDownloadManager::CSusArrayListItemOpDownloadJobCompletion>::GetIndexOf(
                        (char *)this + 1432,
                        v146);
            CSusMap<tagDSGlobalUpdateId,DownloadJobCompletionInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CAgentDownloadManager::CSusArrayListItemOpDownloadJobCompletion>::RemoveAt(
              (char *)this + 1432,
              IndexOf,
              0);
            *(_OWORD *)v146 = *(_OWORD *)((char *)v9 + 8);
            LODWORD(v147) = *((_DWORD *)v9 + 6);
            if ( (int)CSusMap<tagDSGlobalUpdateId,DownloadJobCompletionInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CAgentDownloadManager::CSusArrayListItemOpDownloadJobCompletion>::Add(
                        (char *)this + 1432,
                        v146,
                        &v129) >= 0 )
              DownloadManagerWorkItemEvent::ScheduleWorkItemTask(*((DownloadManagerWorkItemEvent **)this + 183), 0x80u);
            if ( v134 )
              SusFree(v134);
            goto LABEL_232;
          }
          CAgentDownloadManager::CallHandlerForDownloadJobFailure(this, v25, v115, &v112);
          if ( v112 )
          {
            v40 = Trace::UpdateIdToString::UpdateIdToString(
                    (Trace::UpdateIdToString *)v156,
                    (const struct tagDSGlobalUpdateId *)&v149);
            WUTrace(
              0,
              0,
              2,
              4,
              0,
              L"Handler is expecting a GDR to handle the download job failure for update %ws...",
              v40);
          }
        }
        v39 = v115;
        goto LABEL_48;
      }
      if ( v17 < 0 )
      {
        v26 = Trace::UpdateIdToString::UpdateIdToString(
                (Trace::UpdateIdToString *)v156,
                (const struct tagDSGlobalUpdateId *)&v149);
        v27 = Trace::GuidToString::GuidToString((Trace::GuidToString *)&v139, v15);
        v28 = CUpdateDownloadJob::GetJobTypeAsString(v9);
        v106 = v26;
        WUTrace(0, 0, 2, 3, v17, L"%ws job {%ws} had an out of band error, updateId = %ws", v28, v27);
        goto LABEL_26;
      }
LABEL_20:
      v29 = Trace::UpdateIdToString::UpdateIdToString(
              (Trace::UpdateIdToString *)v156,
              (const struct tagDSGlobalUpdateId *)&v149);
      v30 = Trace::GuidToString::GuidToString((Trace::GuidToString *)&v139, v15);
      v31 = CUpdateDownloadJob::GetJobTypeAsString(v9);
      v106 = v29;
      WUTrace(0, 0, 2, 4, 0, L"%ws job {%ws} completed successfully, updateId = %ws", v31, v30);
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)v9 + 13) + 312LL))(*((_QWORD *)v9 + 13)) )
      {
        v32 = Trace::GuidToString::GuidToString((Trace::GuidToString *)&v139, (const struct _GUID *)pv);
        v33 = CUpdateDownloadJob::GetJobTypeAsString(v9);
        WUTrace(
          0,
          0,
          2,
          4,
          0,
          L"%ws job %ws sent partial download completion callback. Requesting the remaining payload to be downloaded.",
          v33,
          v32);
        v115 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v9 + 13) + 320LL))(*((_QWORD *)v9 + 13));
        if ( v115 >= 0 )
        {
          *(_OWORD *)v146 = *(_OWORD *)((char *)v9 + 8);
          LODWORD(v147) = *((_DWORD *)v9 + 6);
          CAgentDownloadManager::SetUpdateSandboxInUse(
            this,
            (const struct tagDSGlobalUpdateId *)v146,
            *((const wchar_t **)v9 + 6),
            0);
LABEL_237:
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
          goto LABEL_238;
        }
      }
      v25 = (struct CUpdateDownloadJob *)((char *)v9 + 8);
      CAgentDownloadManager::OnUpdateDownloadProgress(this, (struct CUpdateDownloadJob *)((char *)v9 + 8), 0);
LABEL_24:
      v10 = 0;
      goto LABEL_27;
    }
  }
LABEL_234:
  if ( a6 )
    CAgentDownloadManager::QueueCheckAllCallDownloadStatesWorkItem(this);
  if ( v7 )
    goto LABEL_237;
LABEL_238:
  if ( v11 )
  {
    DsqFreeObject(v11, 1u, 0x2FAFu, 1);
    SusFree(v11);
  }
  if ( v148 )
  {
    (*(void (__fastcall **)(struct ISusUpdateDownloadRequest *, __int64, __int64, _QWORD))(*(_QWORD *)v148 + 16LL))(
      v148,
      v12,
      v13,
      0);
    v148 = 0;
  }
  if ( v9 && _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 139, 0xFFFFFFFF) == 1 )
  {
    CUpdateDownloadJob::~CUpdateDownloadJob(v9);
    operator delete(v9, (const struct std::nothrow_t *)0x280);
  }
  if ( LODWORD(ppOldObject[0]) )
    CoSwitchCallContext(ppOldObject[1], &ppOldObject[1]);
  if ( v8 )
  {
    DownloadReportingInfo::~DownloadReportingInfo(v8);
    operator delete(v8, (const struct std::nothrow_t *)0x1D0);
  }
}

```

## disassembly

```asm
0x1800a1254  push    rbp
0x1800a1256  push    rbx
0x1800a1257  push    rsi
0x1800a1258  push    rdi
0x1800a1259  push    r12
0x1800a125b  push    r13
0x1800a125d  push    r14
0x1800a125f  push    r15
0x1800a1261  lea     rbp, [rsp-408h]
0x1800a1269  sub     rsp, 508h
0x1800a1270  mov     rax, cs:__security_cookie
0x1800a1277  xor     rax, rsp
0x1800a127a  mov     [rbp+440h+var_50], rax
0x1800a1281  mov     [rbp+440h+var_458], r9
0x1800a1285  mov     [rbp+440h+var_4C0], r8d
0x1800a1289  mov     [rbp+440h+var_460], rdx
0x1800a128d  mov     r13, rcx
0x1800a1290  mov     rdi, [rbp+440h+arg_20]
0x1800a1297  xor     eax, eax
0x1800a1299  mov     r12b, al
0x1800a129c  mov     r14d, eax
0x1800a129f  mov     [rbp+440h+var_468], rax
0x1800a12a3  mov     [rbp+440h+var_4A8], eax
0x1800a12a6  mov     [rbp+440h+var_38C], eax
0x1800a12ac  xorps   xmm0, xmm0
0x1800a12af  movups  xmmword ptr [rbp+440h+ppOldObject], xmm0
0x1800a12b6  mov     dword ptr [rbp+440h+ppOldObject], eax
0x1800a12bc  mov     [rbp+440h+ppOldObject+8], rax
0x1800a12c3  mov     ebx, eax
0x1800a12c5  mov     [rbp+440h+var_478], rax
0x1800a12c9  mov     [rbp+440h+var_370], rax
0x1800a12d0  mov     [rsp+540h+var_4C4], 1
0x1800a12d8  mov     [rsp+540h+var_4C6], al
0x1800a12dc  mov     [rsp+540h+var_4CD], al
0x1800a12e0  mov     [rbp+440h+var_4A0], rax
0x1800a12e4  mov     [rbp+440h+var_498], eax
0x1800a12e7  mov     [rsp+540h+var_4C8], al
0x1800a12eb  mov     qword ptr [rbp+440h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800a12f2  mov     r15b, al
0x1800a12f5  mov     esi, eax
0x1800a12f7  mov     [rbp+440h+var_470], rax
0x1800a12fb  mov     [rsp+540h+var_4D0], al
0x1800a12ff  mov     [rsp+540h+var_4C7], al
0x1800a1303  movups  xmmword ptr [rbp+440h+lpMem], xmm0
0x1800a130a  mov     [rbp+440h+var_340], rax
0x1800a1311  lea     rdx, [rbp+440h+ppOldObject+8]; ppOldObject
0x1800a1318  xor     ecx, ecx; pNewObject
0x1800a131a  call    cs:__imp_CoSwitchCallContext
0x1800a1320  xor     r9d, r9d
0x1800a1323  test    eax, eax
0x1800a1325  js      loc_1800A2AB4
0x1800a132b  mov     dword ptr [rbp+440h+ppOldObject], 1
0x1800a1335  lea     rcx, [rbp+440h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a133c  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a1342  lea     rcx, [r13+270h]; lpCriticalSection
0x1800a1349  call    cs:__imp_EnterCriticalSection
0x1800a134f  mov     r12b, 1
0x1800a1352  mov     [rsp+540h+var_4CE], r12b
0x1800a1357  mov     rax, [rbp+440h+var_460]
0x1800a135b  lea     r8, [rbp+440h+var_478]; struct CUpdateDownloadJob **
0x1800a135f  mov     rcx, r13; this
0x1800a1362  test    rax, rax
0x1800a1365  jnz     short loc_1800A1371
0x1800a1367  mov     rdx, rdi; struct DownloadManagerUpdateID *
0x1800a136a  call    ?FindDownloadJobByUpdateID@CAgentDownloadManager@@AEAA_NAEBUDownloadManagerUpdateID@@PEAPEAVCUpdateDownloadJob@@@Z; CAgentDownloadManager::FindDownloadJobByUpdateID(DownloadManagerUpdateID const &,CUpdateDownloadJob * *)
0x1800a136f  jmp     short loc_1800A1379
0x1800a1371  mov     rdx, rax; struct _GUID *
0x1800a1374  call    ?FindDownloadJobByJobID@CAgentDownloadManager@@AEAA_NAEBU_GUID@@PEAPEAVCUpdateDownloadJob@@@Z; CAgentDownloadManager::FindDownloadJobByJobID(_GUID const &,CUpdateDownloadJob * *)
0x1800a1379  xor     r9d, r9d
0x1800a137c  mov     rbx, [rbp+440h+var_478]
0x1800a1380  test    al, al
0x1800a1382  jz      loc_1800A2AB4
0x1800a1388  mov     rcx, [rbx+68h]
0x1800a138c  mov     rax, [rcx]
0x1800a138f  mov     rax, [rax+28h]
0x1800a1393  call    _guard_dispatch_icall
0x1800a1398  mov     rdi, rax
0x1800a139b  mov     [rbp+440h+pv], rax
0x1800a139f  movups  xmm0, xmmword ptr [rbx+8]
0x1800a13a3  movups  xmmword ptr [rbp+440h+var_368.Data1], xmm0
0x1800a13aa  mov     eax, [rbx+18h]
0x1800a13ad  mov     [rbp+440h+var_358], eax
0x1800a13b3  movups  xmm0, xmmword ptr [rbx+1Ch]
0x1800a13b7  movdqu  xmmword ptr [rbp+440h+var_328.Data1], xmm0
0x1800a13bf  mov     rax, [rbx+30h]
0x1800a13c3  mov     [rbp+440h+var_4B8], rax
0x1800a13c7  mov     r9b, r12b; bool
0x1800a13ca  mov     r8, rax; wchar_t *
0x1800a13cd  lea     rdx, [rbp+440h+var_368]; struct tagDSGlobalUpdateId *
0x1800a13d4  mov     rcx, r13; this
0x1800a13d7  call    ?SetUpdateSandboxInUse@CAgentDownloadManager@@QEAAJAEBUtagDSGlobalUpdateId@@PEB_W_N@Z; CAgentDownloadManager::SetUpdateSandboxInUse(tagDSGlobalUpdateId const &,wchar_t const *,bool)
0x1800a13dc  mov     r12d, eax
0x1800a13df  mov     [rsp+540h+var_4CC], eax
0x1800a13e3  xor     r9d, r9d
0x1800a13e6  test    eax, eax
0x1800a13e8  js      loc_1800A26C0
0x1800a13ee  mov     [rsp+540h+var_4CD], 1
0x1800a13f3  mov     rax, [rbp+440h+var_458]
0x1800a13f7  test    rax, rax
0x1800a13fa  jz      short loc_1800A1415
0x1800a13fc  mov     r12d, [rax+8]
0x1800a1400  mov     [rbp+440h+var_4C0], r12d
0x1800a1404  test    r12d, r12d
0x1800a1407  js      short loc_1800A1422
0x1800a1409  mov     r12d, 80246009h
0x1800a140f  mov     [rbp+440h+var_4C0], r12d
0x1800a1413  jmp     short loc_1800A1422
0x1800a1415  mov     r12d, [rbp+440h+var_4C0]
0x1800a1419  test    r12d, r12d
0x1800a141c  jns     loc_1800A15B0
0x1800a1422  test    rax, rax
0x1800a1425  jz      loc_1800A1545
0x1800a142b  mov     r14, [rax+20h]
0x1800a142f  mov     r15, [rax+10h]
0x1800a1433  mov     r12, [rax+18h]
0x1800a1437  lea     rdx, [rbp+440h+var_368]; struct tagDSGlobalUpdateId *
0x1800a143e  lea     rcx, [rbp+440h+var_2F0]; this
0x1800a1445  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800a144a  mov     rsi, rax
0x1800a144d  mov     rdx, rdi; struct _GUID *
0x1800a1450  lea     rcx, [rbp+440h+var_3E0]; this
0x1800a1454  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800a1459  mov     rdi, rax
0x1800a145c  mov     rcx, rbx; this
0x1800a145f  call    ?GetJobTypeAsString@CUpdateDownloadJob@@QEBAPEB_WXZ; CUpdateDownloadJob::GetJobTypeAsString(void)
0x1800a1464  mov     [rsp+540h+var_4E0], r14
0x1800a1469  mov     [rsp+540h+var_4E8], r15
0x1800a146e  mov     [rsp+540h+var_4F0], r12
0x1800a1473  mov     r8d, [rbp+440h+var_4C0]
0x1800a1477  mov     [rsp+540h+var_4F8], r8d
0x1800a147c  mov     qword ptr [rsp+540h+var_500], rsi; int
0x1800a1481  mov     [rsp+540h+var_508], rdi
0x1800a1486  mov     [rsp+540h+var_510], rax
0x1800a148b  lea     rax, aWsJobWsFailedU; "%ws job {%ws} failed, updateId = %ws, h"...
0x1800a1492  mov     [rsp+540h+var_518], rax
0x1800a1497  xor     r12d, r12d
0x1800a149a  mov     [rsp+540h+var_520], r12
0x1800a149f  lea     esi, [r12+2]
0x1800a14a4  lea     r9d, [r12+3]
0x1800a14a9  mov     r8d, esi
0x1800a14ac  xor     edx, edx
0x1800a14ae  xor     ecx, ecx
0x1800a14b0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800a14b5  lea     r8, [rbp+440h+var_38C]; unsigned int *
0x1800a14bc  lea     rdx, [rbp+440h+lpMem]; struct _BG_JOB_PROGRESS *
0x1800a14c3  mov     rcx, rbx; this
0x1800a14c6  call    ?GetProgress@CUpdateDownloadJob@@QEAAJPEAU_BG_JOB_PROGRESS@@PEAK@Z; CUpdateDownloadJob::GetProgress(_BG_JOB_PROGRESS *,ulong *)
0x1800a14cb  mov     rdi, [rbp+440h+lpMem+8]
0x1800a14d2  test    eax, eax
0x1800a14d4  js      short loc_1800A1509
0x1800a14d6  mov     [rsp+540h+var_508], rdi
0x1800a14db  mov     rax, [rbp+440h+lpMem]
0x1800a14e2  mov     [rsp+540h+var_510], rax
0x1800a14e7  lea     rax, aProgressFailur; "  Progress failure bytes total = %I64u,"...
0x1800a14ee  mov     [rsp+540h+var_518], rax
0x1800a14f3  mov     [rsp+540h+var_520], r12
0x1800a14f8  lea     r9d, [r12+4]
0x1800a14fd  mov     r8d, esi
0x1800a1500  xor     edx, edx
0x1800a1502  xor     ecx, ecx
0x1800a1504  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800a1509  mov     eax, [rbx+24Ch]
0x1800a150f  cmp     eax, [rbx+250h]
0x1800a1515  jnb     loc_1800A16D5
0x1800a151b  cmp     dword ptr [rbx+228h], 0Ch
0x1800a1522  jnz     loc_1800A16D5
0x1800a1528  test    rdi, rdi
0x1800a152b  lea     rdi, [rbx+8]
0x1800a152f  jz      loc_1800A16D0
0x1800a1535  mov     r15b, 1
0x1800a1538  inc     eax
0x1800a153a  mov     [rbx+24Ch], eax
0x1800a1540  jmp     loc_1800A16DC
0x1800a1545  test    r12d, r12d
0x1800a1548  jns     short loc_1800A15B0
0x1800a154a  lea     rdx, [rbp+440h+var_368]; struct tagDSGlobalUpdateId *
0x1800a1551  lea     rcx, [rbp+440h+var_2F0]; this
0x1800a1558  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800a155d  mov     rsi, rax
0x1800a1560  mov     rdx, rdi; struct _GUID *
0x1800a1563  lea     rcx, [rbp+440h+var_3E0]; this
0x1800a1567  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800a156c  mov     rdi, rax
0x1800a156f  mov     rcx, rbx; this
0x1800a1572  call    ?GetJobTypeAsString@CUpdateDownloadJob@@QEBAPEB_WXZ; CUpdateDownloadJob::GetJobTypeAsString(void)
0x1800a1577  mov     qword ptr [rsp+540h+var_500], rsi
0x1800a157c  mov     [rsp+540h+var_508], rdi
0x1800a1581  mov     [rsp+540h+var_510], rax
0x1800a1586  lea     rax, aWsJobWsHadAnOu; "%ws job {%ws} had an out of band error,"...
0x1800a158d  mov     [rsp+540h+var_518], rax
0x1800a1592  mov     dword ptr [rsp+540h+var_520], r12d
0x1800a1597  xor     edx, edx
0x1800a1599  xor     ecx, ecx
0x1800a159b  lea     r9d, [rdx+3]
0x1800a159f  lea     r8d, [rdx+2]
0x1800a15a3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800a15a8  xor     r12d, r12d
0x1800a15ab  jmp     loc_1800A16D8
0x1800a15b0  lea     rdx, [rbp+440h+var_368]; struct tagDSGlobalUpdateId *
0x1800a15b7  lea     rcx, [rbp+440h+var_2F0]; this
0x1800a15be  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800a15c3  mov     r15, rax
0x1800a15c6  mov     rdx, rdi; struct _GUID *
0x1800a15c9  lea     rcx, [rbp+440h+var_3E0]; this
0x1800a15cd  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800a15d2  mov     rdi, rax
0x1800a15d5  mov     rcx, rbx; this
0x1800a15d8  call    ?GetJobTypeAsString@CUpdateDownloadJob@@QEBAPEB_WXZ; CUpdateDownloadJob::GetJobTypeAsString(void)
0x1800a15dd  mov     qword ptr [rsp+540h+var_500], r15
0x1800a15e2  mov     [rsp+540h+var_508], rdi
0x1800a15e7  mov     [rsp+540h+var_510], rax
0x1800a15ec  lea     rax, aWsJobWsComplet; "%ws job {%ws} completed successfully, u"...
0x1800a15f3  mov     [rsp+540h+var_518], rax
0x1800a15f8  xor     r12d, r12d
0x1800a15fb  mov     [rsp+540h+var_520], r12
0x1800a1600  lea     r9d, [r12+4]
0x1800a1605  lea     r15d, [r12+2]
0x1800a160a  mov     r8d, r15d
0x1800a160d  xor     edx, edx
0x1800a160f  xor     ecx, ecx
0x1800a1611  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800a1616  mov     rcx, [rbx+68h]
0x1800a161a  mov     rax, [rcx]
0x1800a161d  mov     rax, [rax+138h]
0x1800a1624  call    _guard_dispatch_icall
0x1800a1629  test    al, al
0x1800a162b  jz      loc_1800A16BE
0x1800a1631  mov     rdx, [rbp+440h+pv]; struct _GUID *
0x1800a1635  lea     rcx, [rbp+440h+var_3E0]; this
0x1800a1639  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800a163e  mov     rdi, rax
0x1800a1641  mov     rcx, rbx; this
0x1800a1644  call    ?GetJobTypeAsString@CUpdateDownloadJob@@QEBAPEB_WXZ; CUpdateDownloadJob::GetJobTypeAsString(void)
0x1800a1649  mov     [rsp+540h+var_508], rdi
0x1800a164e  mov     [rsp+540h+var_510], rax
0x1800a1653  lea     rax, aWsJobWsSentPar; "%ws job %ws sent partial download compl"...
0x1800a165a  mov     [rsp+540h+var_518], rax
0x1800a165f  mov     [rsp+540h+var_520], r12
0x1800a1664  lea     r9d, [r12+4]
0x1800a1669  mov     r8d, r15d
0x1800a166c  xor     edx, edx
0x1800a166e  xor     ecx, ecx
0x1800a1670  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800a1675  mov     rcx, [rbx+68h]
0x1800a1679  mov     rax, [rcx]
0x1800a167c  mov     rax, [rax+140h]
0x1800a1683  call    _guard_dispatch_icall
0x1800a1688  mov     [rbp+440h+var_4C0], eax
0x1800a168b  test    eax, eax
0x1800a168d  js      short loc_1800A16BE
0x1800a168f  movups  xmm0, xmmword ptr [rbx+8]
0x1800a1693  movups  xmmword ptr [rbp+440h+var_388], xmm0
0x1800a169a  mov     eax, [rbx+18h]
0x1800a169d  mov     dword ptr [rbp+440h+var_378], eax
0x1800a16a3  xor     r9d, r9d; bool
0x1800a16a6  mov     r8, [rbx+30h]; wchar_t *
0x1800a16aa  lea     rdx, [rbp+440h+var_388]; struct tagDSGlobalUpdateId *
0x1800a16b1  mov     rcx, r13; this
0x1800a16b4  call    ?SetUpdateSandboxInUse@CAgentDownloadManager@@QEAAJAEBUtagDSGlobalUpdateId@@PEB_W_N@Z; CAgentDownloadManager::SetUpdateSandboxInUse(tagDSGlobalUpdateId const &,wchar_t const *,bool)
0x1800a16b9  jmp     loc_1800A2ACD
0x1800a16be  xor     r8d, r8d; int
0x1800a16c1  lea     rdi, [rbx+8]
0x1800a16c5  mov     rdx, rdi; struct DownloadManagerUpdateID *
0x1800a16c8  mov     rcx, r13; this
0x1800a16cb  call    ?OnUpdateDownloadProgress@CAgentDownloadManager@@AEAAXAEBUDownloadManagerUpdateID@@H@Z; CAgentDownloadManager::OnUpdateDownloadProgress(DownloadManagerUpdateID const &,int)
0x1800a16d0  mov     r15b, r12b
0x1800a16d3  jmp     short loc_1800A16DC
0x1800a16d5  mov     r15b, r12b
0x1800a16d8  lea     rdi, [rbx+8]
0x1800a16dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a16e3  mov     ecx, 1D0h; unsigned __int64
0x1800a16e8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a16ed  mov     [rbp+440h+var_480], rax
0x1800a16f1  test    rax, rax
0x1800a16f4  jz      short loc_1800A173B
0x1800a16f6  mov     rcx, rax; this
0x1800a16f9  call    ??0DownloadReportingInfo@@QEAA@XZ; DownloadReportingInfo::DownloadReportingInfo(void)
0x1800a16fe  mov     r14, rax
0x1800a1701  mov     [rbp+440h+var_468], rax
0x1800a1705  mov     [rbp+440h+var_4B0], rax
0x1800a1709  test    rax, rax
0x1800a170c  jz      short loc_1800A1746
0x1800a170e  lea     rax, [r13+228h]
0x1800a1715  mov     [rsp+540h+var_510], r14; struct DownloadReportingInfo *
0x1800a171a  mov     [rsp+540h+var_518], rax; struct DownloadCallMap *
0x1800a171f  mov     [rsp+540h+var_520], rbx; struct CUpdateDownloadJob *
0x1800a1724  xor     r9d, r9d; unsigned int
0x1800a1727  xor     r8d, r8d; bool
0x1800a172a  mov     rdx, rdi; struct DownloadManagerUpdateID *
0x1800a172d  mov     rcx, r13; this
0x1800a1730  call    ?GetUpdateReportingInfoHelper@CAgentDownloadManager@@AEAAXAEBUDownloadManagerUpdateID@@_NKPEAVCUpdateDownloadJob@@AEAVDownloadCallMap@@PEAVDownloadReportingInfo@@@Z; CAgentDownloadManager::GetUpdateReportingInfoHelper(DownloadManagerUpdateID const &,bool,ulong,CUpdateDownloadJob *,DownloadCallMap &,DownloadReportingInfo *)
0x1800a1735  mov     [rbp+440h+var_4B0], r14
0x1800a1739  jmp     short loc_1800A1746
0x1800a173b  mov     [rbp+440h+var_4B0], r12
0x1800a173f  mov     r14, r12
0x1800a1742  mov     [rbp+440h+var_468], r12
0x1800a1746  lea     rdx, [rbp+440h+var_368]; struct _GUID *
0x1800a174d  mov     rcx, [r13+818h]; this
0x1800a1754  call    ?RemoveUpdateFromSuspensionList@CDownloadRegulator@@QEAAXAEBU_GUID@@@Z; CDownloadRegulator::RemoveUpdateFromSuspensionList(_GUID const &)
0x1800a1759  mov     rdx, rdi; struct DownloadManagerUpdateID *
  ... truncated ...
```
