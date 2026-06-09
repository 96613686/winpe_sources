# CAgentDownloadManager::Init(bool,ISusDatastore *,CUHHandlerManager *,CReporter *,CSusEventSystem *,ISusPersistentTimeoutScheduler *,CAgentProtocolTalker *,CNetworkCostManager *,CIdleTimer *,CWorkItemManager *,IDownloadHeartbeat *,CodeIntegrityUpdateApprovalList *)

- ea: `0x180098504`
- end: `0x18009908c`
- name: `?Init@CAgentDownloadManager@@QEAAJ_NPEAUISusDatastore@@PEAVCUHHandlerManager@@PEAVCReporter@@PEAVCSusEventSystem@@PEAVISusPersistentTimeoutScheduler@@PEAVCAgentProtocolTalker@@PEAVCNetworkCostManager@@PEAVCIdleTimer@@PEAVCWorkItemManager@@PEAUIDownloadHeartbeat@@PEAVCodeIntegrityUpdateApprovalList@@@Z`
- size: `2952`
- prototype: `__int64 __usercall@<rax>(CAgentDownloadManager *__hidden this@<rcx>, bool@<dl>, struct ISusDatastore *@<r8>, struct CUHHandlerManager *@<r9>, struct CReporter *, struct CSusEventSystem *, struct ISusPersistentTimeoutScheduler *, struct CAgentProtocolTalker *, struct CNetworkCostManager *, struct CIdleTimer *, struct CWorkItemManager *, struct IDownloadHeartbeat *, struct CodeIntegrityUpdateApprovalList *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001f688`

## callees

- `0x18000def4`
- `0x1800189f0`
- `0x18008dd78`
- `0x180098504`
- `0x1800991d0`
- `0x1800ab45c`
- `0x1800ac088`
- `0x1800eaf80`
- `0x1800eb0a4`
- `0x1800f1c54`
- `0x1800f2490`
- `0x1800f4534`
- `0x1800f488c`
- `0x180113ae8`
- `0x180113cf4`
- `0x180116648`
- `0x18012b618`
- `0x1801bc428`
- `0x180238960`
- `0x180238984`
- `0x180239110`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009869e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800987ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009885c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180098cd1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009869e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800987ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009885c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180098cd1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180098d14`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180098d14`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800986f4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800986f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800985e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800986b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800986c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009886b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098f51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009900e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800985e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800986b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800986c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009886b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098f51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009900e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098801`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098dcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098ef6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098f2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098801`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098dcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098ef6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098f2f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800985d7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180098648`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800985d7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180098648`

## string_xrefs

- `0x180098da3`: `Handler manager failed to create handler %d, disabling`
- `0x18009905a`: `CAgentDownloadManager::Init`
- `0x18009862a`: `SharedFileCache`
- `0x180098fe9`: `C:\__w\1\s\src\Client\Engine\Agent\DownloadRegulator.cpp`
- `0x1800985bc`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAgentDownloadManager::Init(
        CAgentDownloadManager *this,
        char a2,
        struct ISusDatastore *a3,
        struct CUHHandlerManager *a4,
        struct CReporter *a5,
        struct CSusEventSystem *a6,
        struct ISusPersistentTimeoutScheduler *a7,
        struct CAgentProtocolTalker *a8,
        struct CNetworkCostManager *a9,
        struct CIdleTimer *a10,
        struct CWorkItemManager *a11,
        struct IDownloadHeartbeat *a12,
        struct CodeIntegrityUpdateApprovalList *a13)
{
  signed int CombinedPath; // ebx
  const WCHAR *v16; // r14
  int SusBaseDirectoryW; // eax
  signed int LastError; // eax
  signed int v19; // ecx
  LPCWSTR *v20; // rdi
  void *v21; // rcx
  signed int v22; // eax
  signed int v23; // ecx
  HANDLE EventW; // rax
  signed int v25; // eax
  signed int v26; // ecx
  signed int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  HANDLE v30; // rbx
  void *v31; // rcx
  signed int v32; // eax
  signed int v33; // ecx
  HANDLE v34; // rax
  signed int v35; // eax
  signed int v36; // ecx
  unsigned int v37; // r8d
  CDownloadJobManager *v38; // rdx
  __int64 v39; // rax
  CDownloadJobManager *v40; // rax
  __int64 v41; // rdi
  void (__fastcall ***v42)(_QWORD, __int64); // rcx
  CDownloadJobManager *v43; // rax
  __int64 v44; // rdi
  void (__fastcall ***v45)(_QWORD, __int64); // rcx
  CDownloadJobManager *v46; // rax
  __int64 v47; // rdi
  void (__fastcall ***v48)(_QWORD, __int64); // rcx
  _QWORD *v49; // rax
  __int64 v50; // rdx
  _QWORD *v51; // rbx
  void **v52; // r8
  void (__fastcall ***v53)(_QWORD, __int64, void **); // rcx
  _QWORD *v54; // rax
  _QWORD *v55; // rbx
  __int64 v56; // rdx
  __int64 v57; // rcx
  _QWORD *v58; // rax
  __int64 v59; // r8
  _QWORD *v60; // rbx
  __int64 v61; // rdx
  _QWORD *v62; // rax
  __int64 v63; // rdx
  void (__fastcall ***v64)(_QWORD, __int64); // rcx
  void (__fastcall ***v65)(_QWORD, __int64); // rcx
  unsigned int i; // r14d
  void *v67; // rdi
  int Handler; // eax
  HANDLE v69; // r15
  char *v70; // rbx
  CDownloadJobManager *v71; // rdi
  void *v72; // rcx
  CDownloadRegulator *v73; // rax
  CDownloadRegulator *v74; // rdi
  signed int v75; // eax
  signed int v76; // ecx
  signed int v77; // eax
  void *v78; // rbx
  signed int v79; // eax
  signed int v80; // edx
  int v82; // [rsp+20h] [rbp-50h]
  int v83; // [rsp+20h] [rbp-50h]
  CDownloadJobManager *v85; // [rsp+48h] [rbp-28h] BYREF
  struct CUHHandlerManager *v86; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v87; // [rsp+58h] [rbp-18h] BYREF
  int v88; // [rsp+5Ch] [rbp-14h] BYREF
  __int64 v89; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v86 = a4;
  if ( !a3 || !a4 || !a5 || !a6 || !a8 || !a9 || !a10 || !a11 || !a12 || !a13 )
  {
    CombinedPath = -2147467261;
    goto LABEL_169;
  }
  v16 = (const WCHAR *)((char *)this + 664);
  SusBaseDirectoryW = GetSusBaseDirectoryW((wchar_t *)this + 332, 0x104u, L"Download", (unsigned int *)a4);
  CombinedPath = SusBaseDirectoryW;
  if ( SusBaseDirectoryW < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
      (const char *)(unsigned int)SusBaseDirectoryW,
      v82);
    goto LABEL_168;
  }
  if ( !CreateDirectoryW(v16, 0) )
  {
    LastError = GetLastError();
    v19 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v19 = LastError;
    if ( v19 >= 0 )
      goto LABEL_28;
    CombinedPath = 0;
    if ( v19 != -2147024713 )
      CombinedPath = v19;
    if ( CombinedPath < 0 )
      goto LABEL_168;
  }
  v20 = (LPCWSTR *)((char *)this + 1184);
  v21 = (void *)*((_QWORD *)this + 148);
  if ( v21 )
  {
    SusFree(v21);
    *v20 = 0;
  }
  CombinedPath = CreateCombinedPath(v16, L"SharedFileCache", (wchar_t **)this + 148);
  if ( CombinedPath < 0 )
    goto LABEL_168;
  if ( !CreateDirectoryW(*v20, 0) )
  {
    v22 = GetLastError();
    v23 = (unsigned __int16)v22 | 0x80070000;
    if ( v22 <= 0 )
      v23 = v22;
    if ( v23 >= 0 )
    {
LABEL_28:
      CombinedPath = -2147418113;
      goto LABEL_169;
    }
    CombinedPath = 0;
    if ( v23 != -2147024713 )
      CombinedPath = v23;
    if ( CombinedPath < 0 )
    {
LABEL_168:
      if ( CombinedPath == -2147023649 )
      {
LABEL_170:
        WUTrace("CAgentDownloadManager::Init", 13828, 2, 1, CombinedPath, L"Method failed");
        return (unsigned int)CombinedPath;
      }
LABEL_169:
      CAgentDownloadManager::Uninit(this);
      goto LABEL_170;
    }
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 25) = EventW;
  if ( EventW )
  {
    if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 39, 0x80000FA0) )
    {
      v79 = GetLastError();
      v80 = (unsigned __int16)v79 | 0x80070000;
      if ( v79 <= 0 )
        v80 = v79;
      if ( v80 >= 0 )
        v80 = -2147418113;
      CombinedPath = v80;
      goto LABEL_168;
    }
    *((_DWORD *)this + 400) = 1;
    *((_BYTE *)this + 1856) = a2;
    (*(void (__fastcall **)(struct ISusDatastore *))(*(_QWORD *)a3 + 8LL))(a3);
    v28 = *((_QWORD *)this + 26);
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    *((_QWORD *)this + 26) = a3;
    *((_QWORD *)this + 27) = v86;
    *((_QWORD *)this + 28) = a5;
    *((_QWORD *)this + 31) = a8;
    *((_QWORD *)this + 32) = a9;
    *((_QWORD *)this + 29) = a6;
    *((_QWORD *)this + 30) = a7;
    v29 = *((_QWORD *)this + 3);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    *((_QWORD *)this + 3) = a12;
    (*(void (__fastcall **)(struct IDownloadHeartbeat *))(*(_QWORD *)a12 + 8LL))(a12);
    *((_QWORD *)this + 233) = a13;
    WUTrace(0, 0, 2, 5, 0, L"Initializing BITS callback handler.");
    *((_QWORD *)this + 8) = this;
    v30 = CreateEventW(0, 1, 1, 0);
    v31 = (void *)*((_QWORD *)this + 7);
    if ( v31 )
      CloseHandle(v31);
    *((_QWORD *)this + 7) = v30;
    if ( v30 )
    {
      CombinedPath = CDownloadManagerCallbackHandler::InitInnerHandlers((CAgentDownloadManager *)((char *)this + 48));
      if ( CombinedPath >= 0 )
      {
        *((_DWORD *)this + 22) = 1;
        v34 = CreateEventW(0, 1, 1, 0);
        *((_QWORD *)this + 15) = v34;
        if ( !v34 )
        {
          v35 = GetLastError();
          v36 = (unsigned __int16)v35 | 0x80070000;
          if ( v35 <= 0 )
            v36 = v35;
          if ( v36 >= 0 )
            v36 = -2147418113;
          CombinedPath = v36;
          goto LABEL_168;
        }
        *((_QWORD *)this + 17) = this;
        *((_QWORD *)this + 18) = a11;
        *((_DWORD *)this + 32) = 1;
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 12) + 8LL))((char *)this + 96);
        CAgentDownloadManager::DeleteInstallDirectory((void **)this, 0, v37);
        *((_DWORD *)this + 9) = 0;
        v38 = (CDownloadJobManager *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
        v85 = v38;
        if ( v38 )
        {
          v39 = *((_QWORD *)this + 31);
          *(_QWORD *)v38 = &CSearchCancelObject::`vftable';
          *((_QWORD *)v38 + 1) = v39;
        }
        else
        {
          v38 = 0;
        }
        *((_QWORD *)this + 162) = v38;
        if ( !v38 )
          goto LABEL_65;
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 153) + 8LL))((char *)this + 1224);
        v40 = (CDownloadJobManager *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
        v85 = v40;
        if ( v40 )
          v41 = DownloadManagerWorkItemEvent::DownloadManagerWorkItemEvent(v40, 0, *((_QWORD *)this + 29));
        else
          v41 = 0;
        v42 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 183);
        if ( v42 )
          (**v42)(v42, 1);
        *((_QWORD *)this + 183) = v41;
        if ( !v41 )
          goto LABEL_65;
        v43 = (CDownloadJobManager *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
        v85 = v43;
        if ( v43 )
          v44 = DownloadManagerWorkItemEvent::DownloadManagerWorkItemEvent(v43, 6, *((_QWORD *)this + 29));
        else
          v44 = 0;
        v45 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 184);
        if ( v45 )
          (**v45)(v45, 1);
        *((_QWORD *)this + 184) = v44;
        if ( !v44 )
          goto LABEL_65;
        v46 = (CDownloadJobManager *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
        v85 = v46;
        if ( v46 )
          v47 = DownloadManagerWorkItemEvent::DownloadManagerWorkItemEvent(v46, 7, *((_QWORD *)this + 29));
        else
          v47 = 0;
        v48 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 185);
        if ( v48 )
          (**v48)(v48, 1);
        *((_QWORD *)this + 185) = v47;
        if ( !v47 )
          goto LABEL_65;
        v49 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
        v51 = v49;
        v85 = (CDownloadJobManager *)v49;
        v52 = &CTimeoutEvent::`vftable';
        if ( v49 )
        {
          v50 = *((_QWORD *)this + 29);
          v49[1] = 0;
          v49[2] = 0;
          memset(v49 + 4, 0, 0x10u);
          *((_DWORD *)v49 + 6) = 1;
          v49[6] = 1;
          v49[7] = 0;
          *v49 = &CTimeoutEvent::`vftable';
          v49[8] = v50;
        }
        else
        {
          v51 = 0;
        }
        v53 = (void (__fastcall ***)(_QWORD, __int64, void **))*((_QWORD *)this + 178);
        if ( v53 )
          (**v53)(v53, 1, &CTimeoutEvent::`vftable');
        *((_QWORD *)this + 178) = v51;
        if ( !v51 )
          goto LABEL_65;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_FixLeakCServiceRegulator_54293478>::__private_IsEnabled(
                                `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_FixLeakCServiceRegulator_54293478>::GetImpl'::`2'::impl,
                                v50,
                                v52) )
        {
          v54 = operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
          v55 = v54;
          v85 = (CDownloadJobManager *)v54;
          if ( v54 )
          {
            v56 = *((_QWORD *)this + 29);
            v54[1] = 0;
            v54[2] = 0;
            memset(v54 + 4, 0, 0x10u);
            *((_DWORD *)v54 + 6) = 1;
            v54[6] = 0;
            v54[7] = 0;
            v54[8] = v56;
            *v54 = &CPersistentTimeoutEvent::`vftable';
            v54[9] = a7;
            *((_OWORD *)v54 + 5) = xmmword_1802783D0;
            v54[12] = 6;
            *((_DWORD *)v54 + 26) = 0;
            *((_DWORD *)v54 + 27) = 1;
          }
          else
          {
            v55 = 0;
          }
          v57 = *((_QWORD *)this + 177);
          if ( v57 && _InterlockedExchangeAdd((volatile signed __int32 *)(v57 + 108), 0xFFFFFFFF) == 1 )
            (**(void (__fastcall ***)(__int64, __int64))v57)(v57, 1);
          *((_QWORD *)this + 177) = v55;
        }
        else
        {
          v62 = operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
          v55 = v62;
          v85 = (CDownloadJobManager *)v62;
          if ( v62 )
          {
            v63 = *((_QWORD *)this + 29);
            v62[1] = 0;
            v62[2] = 0;
            memset(v62 + 4, 0, 0x10u);
            *((_DWORD *)v62 + 6) = 1;
            v62[6] = 0;
            v62[7] = 0;
            v62[8] = v63;
            *v62 = &CPersistentTimeoutEvent::`vftable';
            v62[9] = a7;
            *((_OWORD *)v62 + 5) = xmmword_1802783D0;
            v62[12] = 6;
            *((_DWORD *)v62 + 26) = 0;
            *((_DWORD *)v62 + 27) = 1;
          }
          else
          {
            v55 = 0;
          }
          v64 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 176);
          if ( v64 )
            (**v64)(v64, 1);
          *((_QWORD *)this + 176) = v55;
        }
        if ( !v55 )
          goto LABEL_65;
        v58 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
        v60 = v58;
        v85 = (CDownloadJobManager *)v58;
        if ( v58 )
        {
          v61 = *((_QWORD *)this + 29);
          v58[1] = 0;
          v58[2] = 0;
          memset(v58 + 4, 0, 0x10u);
          *((_DWORD *)v58 + 6) = 1;
          v58[6] = 1;
          v58[7] = 0;
          *v58 = &CTimeoutEvent::`vftable';
          v58[8] = v61;
        }
        else
        {
          v60 = 0;
        }
        v65 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 216);
        if ( v65 )
          (**v65)(v65, 1);
        *((_QWORD *)this + 216) = v60;
        if ( !v60 )
          goto LABEL_65;
        for ( i = 0; i < 0xD; ++i )
        {
          v87 = i;
          v89 = 0;
          v67 = 0;
          v85 = 0;
          Handler = CUHHandlerManager::GetHandler(
                      *((_QWORD *)this + 27),
                      i,
                      v59,
                      0,
                      &GUID_dde28533_d0b1_4b84_8610_2d24fcdcb9c1,
                      &v89);
          if ( Handler < 0 )
          {
            if ( Handler != -2147467262 && Handler != -2145091574 )
              WUTrace(0, 0, 2, 3, Handler, L"Handler manager failed to create handler %d, disabling");
          }
          else
          {
            v69 = CreateEventW(0, 1, 0, 0);
            v67 = v69;
            if ( !v69 )
            {
              v75 = GetLastError();
              v76 = (unsigned __int16)v75 | 0x80070000;
              if ( v75 <= 0 )
                v76 = v75;
              if ( v76 >= 0 )
              {
                CombinedPath = -2147467259;
              }
              else
              {
                v77 = GetLastError();
                CombinedPath = (unsigned __int16)v77 | 0x80070000;
                if ( v77 <= 0 )
                  CombinedPath = v77;
              }
              if ( v89 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
              goto LABEL_154;
            }
            v70 = (char *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
            v85 = (CDownloadJobManager *)v70;
            if ( v70 )
            {
              v67 = 0;
              *(_QWORD *)v70 = &CSusLock::`vftable';
              InitializeCriticalSection((LPCRITICAL_SECTION)(v70 + 8));
              *((_QWORD *)v70 + 7) = 0;
              *((_QWORD *)v70 + 8) = 0;
              *((_QWORD *)v70 + 6) = &CSusSortedArrayList<CSusMap<DownloadManagerUpdateID,DownloadRequestMapEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpInterfacePtr<DownloadRequestMapEntry *>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,DownloadRequestMapEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpInterfacePtr<DownloadRequestMapEntry *>>::CMapEntryOps>::`vftable';
              *((_DWORD *)v70 + 18) = 0;
              *((_QWORD *)v70 + 10) = 0;
              *((_QWORD *)v70 + 11) = ((unsigned __int64)this + 8) & -(__int64)(this != 0);
              *((_QWORD *)v70 + 12) = v69;
            }
            else
            {
              v70 = 0;
            }
            v86 = (struct CUHHandlerManager *)v70;
            if ( !v70 )
            {
              CombinedPath = -2147024882;
              WuSmartPtr::XPtrBase<HandlerDownloadRequestMap,WuSmartPtr::Policies::STPolicy<HandlerDownloadRequestMap>>::~XPtrBase<HandlerDownloadRequestMap,WuSmartPtr::Policies::STPolicy<HandlerDownloadRequestMap>>(&v86);
              if ( v67 )
                CloseHandle(v67);
              if ( v89 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
              goto LABEL_169;
            }
            v85 = (CDownloadJobManager *)v70;
            CombinedPath = CSusMap<long,CEventNamespaceDefinition const *,CSusSortedArrayListItemOpsBasic<long>,CSusArrayListItemOpNoop<CEventNamespaceDefinition const *>>::Add(
                             (char *)this + 584,
                             &v87,
                             &v85);
            if ( CombinedPath < 0 )
            {
              WuSmartPtr::XPtrBase<HandlerDownloadRequestMap,WuSmartPtr::Policies::STPolicy<HandlerDownloadRequestMap>>::~XPtrBase<HandlerDownloadRequestMap,WuSmartPtr::Policies::STPolicy<HandlerDownloadRequestMap>>(&v86);
              if ( v67 )
                CloseHandle(v67);
              if ( v89 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
              goto LABEL_168;
            }
            v86 = 0;
            WuSmartPtr::XPtrBase<HandlerDownloadRequestMap,WuSmartPtr::Policies::STPolicy<HandlerDownloadRequestMap>>::~XPtrBase<HandlerDownloadRequestMap,WuSmartPtr::Policies::STPolicy<HandlerDownloadRequestMap>>(&v86);
          }
          if ( v67 )
            CloseHandle(v67);
          if ( v89 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
        }
        v88 = 0;
        CombinedPath = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 26) + 96LL))(
                         *((_QWORD *)this + 26),
                         &v88);
        if ( CombinedPath < 0 )
          goto LABEL_168;
        *((_DWORD *)this + 468) = (unsigned int)(720 * v88) >> 14;
        v71 = (CDownloadJobManager *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
        v85 = v71;
        v72 = (void *)*((_QWORD *)this + 253);
        if ( v72 )
          operator delete(v72, (const struct std::nothrow_t *)0x48);
        *((_QWORD *)this + 253) = v71;
        if ( !v71 )
          goto LABEL_65;
        CombinedPath = CDownloadJobManager::Init(v71, this);
        if ( CombinedPath < 0 )
          goto LABEL_168;
        v73 = (CDownloadRegulator *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
        v85 = v73;
        if ( v73 )
          v74 = CDownloadRegulator::CDownloadRegulator(
                  v73,
                  *((struct ISusDatastore **)this + 26),
                  *((struct CSusEventSystem **)this + 29),
                  *((struct ISusPersistentTimeoutScheduler **)this + 30),
                  *((struct CAgentProtocolTalker **)this + 31),
                  *((void **)this + 25),
                  *((struct ISusNetworkCostManager **)this + 32));
        else
          v74 = 0;
        v78 = (void *)*((_QWORD *)this + 259);
        if ( v78 )
        {
          CDownloadRegulator::~CDownloadRegulator(*((CDownloadRegulator **)this + 259));
          operator delete(v78, (const struct std::nothrow_t *)0xD8);
        }
        *((_QWORD *)this + 259) = v74;
        if ( !v74 )
        {
LABEL_65:
          CombinedPath = -2147024882;
          goto LABEL_169;
        }
        if ( *((_BYTE *)v74 + 48) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDE,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\DownloadRegulator.cpp",
            (const char *)0x800704DFLL,
            v83);
          CombinedPath = -2147023649;
          goto LABEL_170;
        }
        *((_BYTE *)v74 + 48) = 1;
        CombinedPath = 0;
        *((_DWORD *)this + 4) = 1;
        return (unsigned int)CombinedPath;
      }
    }
    else
    {
      v32 = GetLastError();
      v33 = (unsigned __int16)v32 | 0x80070000;
      if ( v32 <= 0 )
        v33 = v32;
      if ( v33 >= 0 )
        v33 = -2147418113;
      CombinedPath = v33;
    }
    CDownloadManagerCallbackHandler::Uninit((CAgentDownloadManager *)((char *)this + 48));
    goto LABEL_168;
  }
  v25 = GetLastError();
  v26 = (unsigned __int16)v25 | 0x80070000;
  if ( v25 <= 0 )
    v26 = v25;
  if ( v26 >= 0 )
  {
    CombinedPath = -2147467259;
  }
  else
  {
    v27 = GetLastError();
    CombinedPath = (unsigned __int16)v27 | 0x80070000;
    if ( v27 <= 0 )
      CombinedPath = v27;
  }
LABEL_154:
  if ( CombinedPath < 0 )
    goto LABEL_168;
  return (unsigned int)CombinedPath;
}

```

## disassembly

```asm
0x180098504  mov     [rsp-38h+arg_8], rbx
0x180098509  push    rbp
0x18009850a  push    rsi
0x18009850b  push    rdi
0x18009850c  push    r12
0x18009850e  push    r13
0x180098510  push    r14
0x180098512  push    r15
0x180098514  mov     rbp, rsp
0x180098517  sub     rsp, 70h
0x18009851b  mov     rax, cs:__security_cookie
0x180098522  xor     rax, rsp
0x180098525  mov     [rbp+var_8], rax
0x180098529  mov     rax, r9
0x18009852c  mov     [rbp+var_20], rax
0x180098530  mov     r15, r8
0x180098533  mov     [rbp+var_30], dl
0x180098536  mov     rsi, rcx
0x180098539  xor     edi, edi
0x18009853b  test    r8, r8
0x18009853e  jnz     short loc_18009854A
0x180098540  mov     ebx, 80004003h
0x180098545  jmp     loc_180099033
0x18009854a  test    rax, rax
0x18009854d  jz      short loc_180098540
0x18009854f  mov     r12, [rbp+arg_20]
0x180098553  test    r12, r12
0x180098556  jz      short loc_180098540
0x180098558  mov     r13, [rbp+arg_28]
0x18009855c  test    r13, r13
0x18009855f  jz      short loc_180098540
0x180098561  cmp     [rbp+arg_38], rdi
0x180098565  jz      short loc_180098540
0x180098567  cmp     [rbp+arg_40], rdi
0x18009856e  jz      short loc_180098540
0x180098570  cmp     [rbp+arg_48], rdi
0x180098577  jz      short loc_180098540
0x180098579  cmp     [rbp+arg_50], rdi
0x180098580  jz      short loc_180098540
0x180098582  cmp     [rbp+arg_58], rdi
0x180098589  jz      short loc_180098540
0x18009858b  cmp     [rbp+arg_60], rdi
0x180098592  jz      short loc_180098540
0x180098594  lea     r14, [rcx+298h]
0x18009859b  lea     r8, aDownload_0; "Download"
0x1800985a2  mov     edx, 104h; unsigned int
0x1800985a7  mov     rcx, r14; wchar_t *
0x1800985aa  call    ?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z; GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)
0x1800985af  mov     ebx, eax
0x1800985b1  test    eax, eax
0x1800985b3  jns     short loc_1800985D2
0x1800985b5  mov     rcx, [rbp+38h]; this
0x1800985b9  mov     r9d, eax; char *
0x1800985bc  lea     r8, aCW1SSrcClientL_50; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800985c3  mov     edx, 0B1h; void *
0x1800985c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800985cd  jmp     loc_18009902B
0x1800985d2  xor     edx, edx; lpSecurityAttributes
0x1800985d4  mov     rcx, r14; lpPathName
0x1800985d7  call    cs:__imp_CreateDirectoryW
0x1800985dd  test    eax, eax
0x1800985df  jnz     short loc_18009860C
0x1800985e1  call    cs:__imp_GetLastError
0x1800985e7  movzx   ecx, ax
0x1800985ea  or      ecx, 80070000h
0x1800985f0  test    eax, eax
0x1800985f2  cmovle  ecx, eax
0x1800985f5  test    ecx, ecx
0x1800985f7  jns     short loc_18009866D
0x1800985f9  mov     ebx, edi
0x1800985fb  cmp     ecx, 800700B7h
0x180098601  cmovnz  ebx, ecx
0x180098604  test    ebx, ebx
0x180098606  js      loc_18009902B
0x18009860c  lea     rdi, [rsi+4A0h]
0x180098613  mov     rcx, [rdi]; lpMem
0x180098616  test    rcx, rcx
0x180098619  jz      short loc_180098627
0x18009861b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180098620  mov     qword ptr [rdi], 0
0x180098627  mov     r8, rdi; wchar_t **
0x18009862a  lea     rdx, aSharedfilecach; "SharedFileCache"
0x180098631  mov     rcx, r14; wchar_t *
0x180098634  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x180098639  mov     ebx, eax
0x18009863b  test    eax, eax
0x18009863d  js      loc_18009902B
0x180098643  xor     edx, edx; lpSecurityAttributes
0x180098645  mov     rcx, [rdi]; lpPathName
0x180098648  call    cs:__imp_CreateDirectoryW
0x18009864e  test    eax, eax
0x180098650  jnz     short loc_18009868C
0x180098652  call    cs:__imp_GetLastError
0x180098658  movzx   ecx, ax
0x18009865b  mov     r14d, 80070000h
0x180098661  or      ecx, r14d
0x180098664  test    eax, eax
0x180098666  cmovle  ecx, eax
0x180098669  test    ecx, ecx
0x18009866b  js      short loc_180098677
0x18009866d  mov     ebx, 8000FFFFh
0x180098672  jmp     loc_180099033
0x180098677  xor     ebx, ebx
0x180098679  cmp     ecx, 800700B7h
0x18009867f  cmovnz  ebx, ecx
0x180098682  test    ebx, ebx
0x180098684  js      loc_18009902B
0x18009868a  jmp     short loc_180098692
0x18009868c  mov     r14d, 80070000h
0x180098692  xor     r9d, r9d; lpName
0x180098695  xor     r8d, r8d; bInitialState
0x180098698  lea     edx, [r9+1]; bManualReset
0x18009869c  xor     ecx, ecx; lpEventAttributes
0x18009869e  call    cs:__imp_CreateEventW
0x1800986a4  mov     [rsi+0C8h], rax
0x1800986ab  test    rax, rax
0x1800986ae  jnz     short loc_1800986E5
0x1800986b0  call    cs:__imp_GetLastError
0x1800986b6  movzx   ecx, ax
0x1800986b9  or      ecx, r14d
0x1800986bc  test    eax, eax
0x1800986be  cmovle  ecx, eax
0x1800986c1  test    ecx, ecx
0x1800986c3  jns     short loc_1800986DB
0x1800986c5  call    cs:__imp_GetLastError
0x1800986cb  movzx   ebx, ax
0x1800986ce  or      ebx, r14d
0x1800986d1  test    eax, eax
0x1800986d3  cmovle  ebx, eax
0x1800986d6  jmp     loc_180098F9A
0x1800986db  mov     ebx, 80004005h
0x1800986e0  jmp     loc_180098F9A
0x1800986e5  lea     rdi, [rsi+618h]
0x1800986ec  mov     edx, 80000FA0h; dwSpinCount
0x1800986f1  mov     rcx, rdi; lpCriticalSection
0x1800986f4  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800986fa  test    eax, eax
0x1800986fc  jz      loc_18009900E
0x180098702  mov     dword ptr [rdi+28h], 1
0x180098709  mov     al, [rbp+var_30]
0x18009870c  mov     [rsi+740h], al
0x180098712  mov     rax, [r15]
0x180098715  mov     rcx, r15
0x180098718  mov     rax, [rax+8]
0x18009871c  call    _guard_dispatch_icall
0x180098721  mov     rcx, [rsi+0D0h]
0x180098728  test    rcx, rcx
0x18009872b  jz      short loc_180098739
0x18009872d  mov     rax, [rcx]
0x180098730  mov     rax, [rax+10h]
0x180098734  call    _guard_dispatch_icall
0x180098739  mov     [rsi+0D0h], r15
0x180098740  mov     rax, [rbp+var_20]
0x180098744  mov     [rsi+0D8h], rax
0x18009874b  mov     [rsi+0E0h], r12
0x180098752  mov     rax, [rbp+arg_38]
0x180098756  mov     [rsi+0F8h], rax
0x18009875d  mov     rax, [rbp+arg_40]
0x180098764  mov     [rsi+100h], rax
0x18009876b  mov     [rsi+0E8h], r13
0x180098772  mov     r14, [rbp+arg_30]
0x180098776  mov     [rsi+0F0h], r14
0x18009877d  mov     rcx, [rsi+18h]
0x180098781  xor     r12d, r12d
0x180098784  test    rcx, rcx
0x180098787  jz      short loc_180098795
0x180098789  mov     rax, [rcx]
0x18009878c  mov     rax, [rax+10h]
0x180098790  call    _guard_dispatch_icall
0x180098795  mov     rcx, [rbp+arg_58]
0x18009879c  mov     [rsi+18h], rcx
0x1800987a0  mov     rax, [rcx]
0x1800987a3  mov     rax, [rax+8]
0x1800987a7  call    _guard_dispatch_icall
0x1800987ac  mov     rax, [rbp+arg_60]
0x1800987b3  mov     [rsi+748h], rax
0x1800987ba  lea     rax, aInitializingBi; "Initializing BITS callback handler."
0x1800987c1  mov     [rsp+70h+var_48], rax
0x1800987c6  mov     [rsp+70h+var_50], r12
0x1800987cb  xor     edx, edx
0x1800987cd  xor     ecx, ecx
0x1800987cf  lea     r9d, [rdx+5]
0x1800987d3  lea     r8d, [rdx+2]
0x1800987d7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800987dc  mov     [rsi+40h], rsi
0x1800987e0  xor     r9d, r9d; lpName
0x1800987e3  lea     r13d, [r9+1]
0x1800987e7  mov     r8d, r13d; bInitialState
0x1800987ea  mov     edx, r13d; bManualReset
0x1800987ed  xor     ecx, ecx; lpEventAttributes
0x1800987ef  call    cs:__imp_CreateEventW
0x1800987f5  mov     rbx, rax
0x1800987f8  mov     rcx, [rsi+38h]; hObject
0x1800987fc  test    rcx, rcx
0x1800987ff  jz      short loc_180098807
0x180098801  call    cs:__imp_CloseHandle
0x180098807  mov     [rsi+38h], rbx
0x18009880b  test    rbx, rbx
0x18009880e  jnz     short loc_18009883E
0x180098810  call    cs:__imp_GetLastError
0x180098816  movzx   ecx, ax
0x180098819  or      ecx, 80070000h
0x18009881f  test    eax, eax
0x180098821  cmovle  ecx, eax
0x180098824  mov     ebx, 8000FFFFh
0x180098829  test    ecx, ecx
0x18009882b  cmovns  ecx, ebx
0x18009882e  mov     ebx, ecx
0x180098830  lea     rcx, [rsi+30h]; this
0x180098834  call    ?Uninit@CDownloadManagerCallbackHandler@@QEAAXXZ; CDownloadManagerCallbackHandler::Uninit(void)
0x180098839  jmp     loc_18009902B
0x18009883e  lea     rcx, [rsi+30h]; this
0x180098842  call    ?InitInnerHandlers@CDownloadManagerCallbackHandler@@AEAAJXZ; CDownloadManagerCallbackHandler::InitInnerHandlers(void)
0x180098847  mov     ebx, eax
0x180098849  test    eax, eax
0x18009884b  js      short loc_180098830
0x18009884d  mov     [rsi+58h], r13d
0x180098851  xor     r9d, r9d; lpName
0x180098854  mov     r8d, r13d; bInitialState
0x180098857  mov     edx, r13d; bManualReset
0x18009885a  xor     ecx, ecx; lpEventAttributes
0x18009885c  call    cs:__imp_CreateEventW
0x180098862  mov     [rsi+78h], rax
0x180098866  test    rax, rax
0x180098869  jnz     short loc_180098890
0x18009886b  call    cs:__imp_GetLastError
0x180098871  movzx   ecx, ax
0x180098874  or      ecx, 80070000h
0x18009887a  test    eax, eax
0x18009887c  cmovle  ecx, eax
0x18009887f  mov     ebx, 8000FFFFh
0x180098884  test    ecx, ecx
0x180098886  cmovns  ecx, ebx
0x180098889  mov     ebx, ecx
0x18009888b  jmp     loc_18009902B
0x180098890  mov     [rsi+88h], rsi
0x180098897  mov     rax, [rbp+arg_50]
0x18009889e  mov     [rsi+90h], rax
0x1800988a5  mov     [rsi+80h], r13d
0x1800988ac  mov     rax, [rsi+60h]
0x1800988b0  lea     rcx, [rsi+60h]
0x1800988b4  mov     rax, [rax+8]
0x1800988b8  call    _guard_dispatch_icall
0x1800988bd  xor     edx, edx; struct _GUID *
0x1800988bf  mov     rcx, rsi; this
0x1800988c2  call    ?DeleteInstallDirectory@CAgentDownloadManager@@AEAAJPEAU_GUID@@@Z; CAgentDownloadManager::DeleteInstallDirectory(_GUID *)
0x1800988c7  mov     [rsi+24h], r12d
0x1800988cb  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800988d2  mov     rdx, r15; struct std::nothrow_t *
0x1800988d5  mov     ecx, 10h; unsigned __int64
0x1800988da  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800988df  mov     rdx, rax
0x1800988e2  mov     [rbp+var_28], rax
0x1800988e6  test    rax, rax
0x1800988e9  jz      short loc_180098902
0x1800988eb  mov     rax, [rsi+0F8h]
0x1800988f2  lea     rcx, ??_7CSearchCancelObject@@6B@; const CSearchCancelObject::`vftable'
0x1800988f9  mov     [rdx], rcx
0x1800988fc  mov     [rdx+8], rax
0x180098900  jmp     short loc_180098905
0x180098902  mov     rdx, r12
0x180098905  mov     [rsi+510h], rdx
0x18009890c  test    rdx, rdx
0x18009890f  jnz     short loc_18009891B
0x180098911  mov     ebx, 8007000Eh
0x180098916  jmp     loc_180099033
0x18009891b  lea     rcx, [rsi+4C8h]
0x180098922  mov     rax, [rcx]
0x180098925  mov     rax, [rax+8]
0x180098929  call    _guard_dispatch_icall
0x18009892e  mov     rdx, r15; struct std::nothrow_t *
0x180098931  mov     ebx, 88h
0x180098936  mov     ecx, ebx; unsigned __int64
0x180098938  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009893d  mov     [rbp+var_28], rax
0x180098941  test    rax, rax
0x180098944  jz      short loc_18009895C
0x180098946  mov     r8, [rsi+0E8h]
0x18009894d  xor     edx, edx
0x18009894f  mov     rcx, rax
0x180098952  call    ??0DownloadManagerWorkItemEvent@@QEAA@W4tagWorkItemType@@AEAVCSusEventSystem@@@Z; DownloadManagerWorkItemEvent::DownloadManagerWorkItemEvent(tagWorkItemType,CSusEventSystem &)
0x180098957  mov     rdi, rax
0x18009895a  jmp     short loc_18009895F
0x18009895c  mov     rdi, r12
0x18009895f  mov     rcx, [rsi+5B8h]
0x180098966  test    rcx, rcx
0x180098969  jz      short loc_180098979
0x18009896b  mov     rax, [rcx]
0x18009896e  mov     edx, r13d
0x180098971  mov     rax, [rax]
0x180098974  call    _guard_dispatch_icall
0x180098979  mov     [rsi+5B8h], rdi
0x180098980  test    rdi, rdi
0x180098983  jz      short loc_180098911
0x180098985  mov     rdx, r15; struct std::nothrow_t *
0x180098988  mov     rcx, rbx; unsigned __int64
0x18009898b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180098990  mov     [rbp+var_28], rax
0x180098994  test    rax, rax
0x180098997  jz      short loc_1800989B2
  ... truncated ...
```
