# CWwanService::Initialize(tlx::shared_any<tlx::file_handle_traits>)

- ea: `0x180014fe8`
- end: `0x1800159a9`
- name: `?Initialize@CWwanService@@QEAAKV?$shared_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `2497`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800127bc`

## callees

- `0x180012300`
- `0x180013004`
- `0x180014134`
- `0x180014198`
- `0x1800141bc`
- `0x1800141e0`
- `0x180014204`
- `0x180014228`
- `0x180014270`
- `0x1800142c0`
- `0x1800142f0`
- `0x180014338`
- `0x180014380`
- `0x1800143a4`
- `0x1800143c8`
- `0x1800143ec`
- `0x180014f1c`
- `0x180014fe8`
- `0x1800159b0`
- `0x180017160`
- `0x18001c540`
- `0x1800769a4`
- `0x180077224`
- `0x18007d4c4`
- `0x180085904`
- `0x18008a6fc`
- `0x18008a790`
- `0x18009e098`
- `0x1800aab04`
- `0x1800b6678`
- `0x1800b67e0`
- `0x1800b78ec`
- `0x1800c0464`
- `0x1800c0768`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001533d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001533d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001534b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001534b`
- `MobileNetworking!HtCreateHandleTable` at `0x180015062`
- `MobileNetworking!HtCreateHandleTable` at `0x180015062`
- `MobileNetworking!InitializeTimers` at `0x180015012`
- `MobileNetworking!InitializeTimers` at `0x180015012`

## string_xrefs

- `0x180015073`: `onecoreuap\net\wwan\service\core\wwansvc.cpp`
- `0x180015110`: `onecoreuap\net\wwan\service\core\wwansvc.cpp`
- `0x1800151b4`: `onecoreuap\net\wwan\service\core\wwansvc.cpp`
- `0x18001522c`: `onecoreuap\net\wwan\service\core\wwansvc.cpp`
- `0x1800152ae`: `onecoreuap\net\wwan\service\core\wwansvc.cpp`
- `0x18001535c`: `onecoreuap\net\wwan\service\core\wwansvc.cpp`
- `0x1800153f6`: `onecoreuap\net\wwan\service\core\wwansvc.cpp`
- `0x18001549a`: `onecoreuap\net\wwan\service\core\wwansvc.cpp`
- `0x180015610`: `onecoreuap\net\wwan\service\core\wwansvc.cpp`
- `0x180015785`: `onecoreuap\net\wwan\service\core\wwansvc.cpp`
- `0x1800158ff`: `onecoreuap\net\wwan\service\core\wwansvc.cpp`
- `0x180015972`: `onecoreuap\net\wwan\service\core\wwansvc.cpp`
- `0x18001554e`: `CWwanService::Initialize`
- `0x1800156c7`: `CWwanService::Initialize`
- `0x180015838`: `CWwanService::Initialize`
- `0x18001582f`: `WWANSVC Modules Initialization Completed`
- `0x18001518a`: `WWAN Plugin Initialization complete 0x%08X`
- `0x1800158ec`: `WWAN Plugin register handle failed  %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CWwanService::Initialize(_BYTE *a1, __int64 *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // edi
  unsigned int HandleTable; // eax
  unsigned int v8; // edi
  utl::_RefCountBase *v9; // rcx
  utl::_RefCountBase *v10; // rcx
  unsigned int v12; // eax
  utl::_RefCountBase *v13; // rcx
  unsigned int started; // eax
  unsigned int v15; // edi
  unsigned int v16; // eax
  utl::_RefCountBase *v17; // rcx
  unsigned int v18; // eax
  utl::_RefCountBase *v19; // rcx
  unsigned int v20; // eax
  utl::_RefCountBase *v21; // rcx
  DWORD LastError; // eax
  utl::_RefCountBase *v23; // rcx
  unsigned int v24; // eax
  utl::_RefCountBase *v25; // rcx
  unsigned int v26; // eax
  utl::_RefCountBase *v27; // rcx
  CWwanManager *v28; // r8
  __int64 v29; // rcx
  unsigned int v30; // eax
  utl::_RefCountBase *v31; // rcx
  CWwanAoAcHelper *Instance; // rax
  utl::_RefCountBase *v33; // rcx
  unsigned int v34; // eax
  utl::_RefCountBase *v35; // rcx
  utl::_RefCountBase *v36; // rcx
  utl::_RefCountBase *v37; // rcx
  utl::_RefCountBase *v38; // rcx
  unsigned int v39[4]; // [rsp+20h] [rbp-89h] BYREF
  _BYTE v40[16]; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v41[16]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v42[16]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v43[16]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v44[16]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v45[16]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v46[16]; // [rsp+90h] [rbp-19h] BYREF
  _BYTE v47[16]; // [rsp+A0h] [rbp-9h] BYREF
  _BYTE v48[16]; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v49; // [rsp+C0h] [rbp+17h] BYREF
  char *v50; // [rsp+C8h] [rbp+1Fh]
  _BYTE v51[16]; // [rsp+D0h] [rbp+27h] BYREF
  _BYTE v52[32]; // [rsp+E0h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  char v54; // [rsp+120h] [rbp+77h] BYREF

  v54 = 1;
  v4 = InitializeTimers(&g_hTimerContext);
  v6 = v4;
  if ( v4 )
  {
    if ( (WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits & 1) != 0 )
      McTemplateU0sd_EventWriteTransfer(v5, WwanTm_c18, "WwanTimerInit", v4);
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x71,
           (unsigned int)"onecoreuap\\net\\wwan\\service\\core\\wwansvc.cpp",
           (const char *)v6,
           v39[0]);
    v38 = (utl::_RefCountBase *)a2[1];
    if ( v38 )
      utl::_RefCountBase::_DecStrong(v38);
    return v8;
  }
  if ( (WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits & 1) != 0 )
    McTemplateU0s_EventWriteTransfer(&WwanControlGuid_Context, WwanTm_c14, "WwanTimerInit");
  tlx::undo_group::make_undo__CWwanService::Initialize_::_2_::_lambda_9___(&v54, v39);
  HandleTable = HtCreateHandleTable(0, 100, &g_hHandleTable);
  if ( HandleTable )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x76,
           (unsigned int)"onecoreuap\\net\\wwan\\service\\core\\wwansvc.cpp",
           (const char *)HandleTable,
           v39[0]);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
    v9 = (utl::_RefCountBase *)a2[1];
    if ( v9 )
      utl::_RefCountBase::_DecStrong(v9);
    return v8;
  }
  tlx::undo_group::make_undo__CWwanService::Initialize_::_2_::_lambda_9___(&v54, v40);
  g_pWwanThreadpool = (PTP_CALLBACK_ENVIRON)WwanInitThreadpool();
  if ( !g_pWwanThreadpool )
  {
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
    v10 = (utl::_RefCountBase *)a2[1];
    if ( v10 )
      utl::_RefCountBase::_DecStrong(v10);
    return 1450;
  }
  tlx::undo_group::make_undo__CWwanService::Initialize_::_2_::_lambda_9___(&v54, v41);
  v12 = WwanPmInit();
  if ( v12 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x8B,
           (unsigned int)"onecoreuap\\net\\wwan\\service\\core\\wwansvc.cpp",
           (const char *)v12,
           v39[0]);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___(v41);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
    v13 = (utl::_RefCountBase *)a2[1];
    if ( v13 )
      utl::_RefCountBase::_DecStrong(v13);
    return v8;
  }
  tlx::undo_group::make_undo__CWwanService::Initialize_::_2_::_lambda_9___(&v54, v42);
  g_nlaContext = 0;
  started = StartMonitoringNetprofmService();
  v15 = started;
  if ( started )
  {
    WwanLog::Error("WwanNlaPlgInit", 0, L"WWAN Plugin register handle failed  %x", started);
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x90,
           (unsigned int)"onecoreuap\\net\\wwan\\service\\core\\wwansvc.cpp",
           (const char *)v15,
           v39[0]);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___(v42);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___(v41);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
    v37 = (utl::_RefCountBase *)a2[1];
    if ( v37 )
      utl::_RefCountBase::_DecStrong(v37);
    return v8;
  }
  WwanLog::Info("WwanNlaPlgInit", 0, L"WWAN Plugin Initialization complete 0x%08X", 0);
  tlx::undo_group::make_undo__CWwanService::Initialize_::_2_::_lambda_9___(&v54, v43);
  v16 = WwanDimInit();
  if ( v16 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x95,
           (unsigned int)"onecoreuap\\net\\wwan\\service\\core\\wwansvc.cpp",
           (const char *)v16,
           v39[0]);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___(v43);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___(v42);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___(v41);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
    v17 = (utl::_RefCountBase *)a2[1];
    if ( v17 )
      utl::_RefCountBase::_DecStrong(v17);
    return v8;
  }
  tlx::undo_group::make_undo__CWwanService::Initialize_::_2_::_lambda_9___(&v54, v44);
  v18 = WwanNhInit();
  if ( v18 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x9A,
           (unsigned int)"onecoreuap\\net\\wwan\\service\\core\\wwansvc.cpp",
           (const char *)v18,
           v39[0]);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___(v44);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___(v43);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___(v42);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___(v41);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
    v19 = (utl::_RefCountBase *)a2[1];
    if ( v19 )
      utl::_RefCountBase::_DecStrong(v19);
    return v8;
  }
  tlx::undo_group::make_undo__CWwanService::Initialize_::_2_::_lambda_9___(&v54, v45);
  v20 = WwanSapMgrInit();
  if ( v20 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x9F,
           (unsigned int)"onecoreuap\\net\\wwan\\service\\core\\wwansvc.cpp",
           (const char *)v20,
           v39[0]);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___(v45);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___(v44);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___(v43);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___(v42);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___(v41);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
    v21 = (utl::_RefCountBase *)a2[1];
    if ( v21 )
      utl::_RefCountBase::_DecStrong(v21);
    return v8;
  }
  tlx::undo_group::make_undo__CWwanService::Initialize_::_2_::_lambda_9___(&v54, v46);
  dword_1801528A8 = 0;
  if ( !InitializeCriticalSectionAndSpinCount(&stru_180152880, 0) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xA4,
             (unsigned int)"onecoreuap\\net\\wwan\\service\\core\\wwansvc.cpp",
             (const char *)LastError,
             v39[0]);
      tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___(v46);
      tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___(v45);
      tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___(v44);
      tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___(v43);
      tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___(v42);
      tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___(v41);
      tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
      tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
      v23 = (utl::_RefCountBase *)a2[1];
      if ( v23 )
        utl::_RefCountBase::_DecStrong(v23);
      return v8;
    }
  }
  tlx::undo_group::make_undo__CWwanService::Initialize_::_2_::_lambda_9___(&v54, v47);
  v24 = WwanGPInit();
  if ( v24 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xB2,
           (unsigned int)"onecoreuap\\net\\wwan\\service\\core\\wwansvc.cpp",
           (const char *)v24,
           v39[0]);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___(v47);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___(v46);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___(v45);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___(v44);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___(v43);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___(v42);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___(v41);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
    v25 = (utl::_RefCountBase *)a2[1];
    if ( v25 )
      utl::_RefCountBase::_DecStrong(v25);
    return v8;
  }
  tlx::undo_group::make_undo__CWwanService::Initialize_::_2_::_lambda_9___(&v54, v48);
  v26 = MBAEUpdaterInit();
  if ( v26 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xB7,
           (unsigned int)"onecoreuap\\net\\wwan\\service\\core\\wwansvc.cpp",
           (const char *)v26,
           v39[0]);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_10___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_10___(v48);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___(v47);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___(v46);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___(v45);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___(v44);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___(v43);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___(v42);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___(v41);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
    v27 = (utl::_RefCountBase *)a2[1];
    if ( v27 )
      utl::_RefCountBase::_DecStrong(v27);
    return v8;
  }
  tlx::undo_group::make_undo__CWwanService::Initialize_::_2_::_lambda_9___(&v54, v51);
  if ( !CWwanManager::GetInstance() )
  {
    WwanLog::Error("CWwanService::Initialize", 0, L"Failed to get CWwanManager instance.");
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_11___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_11___(v51);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_10___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_10___(v48);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___(v47);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___(v46);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___(v45);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___(v44);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___(v43);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___(v42);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___(v41);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
LABEL_52:
    v33 = (utl::_RefCountBase *)a2[1];
    if ( v33 )
      utl::_RefCountBase::_DecStrong(v33);
    return 14;
  }
  tlx::undo_group::make_undo__CWwanService::Initialize_::_2_::_lambda_9___(&v54, v52);
  v29 = a2[1];
  v49 = *a2;
  v50 = (char *)v29;
  if ( v29 )
    _InterlockedIncrement((volatile signed __int32 *)(v29 + 8));
  v30 = CWwanManager::Initialize(v28, &v49);
  if ( v30 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xC8,
           (unsigned int)"onecoreuap\\net\\wwan\\service\\core\\wwansvc.cpp",
           (const char *)v30,
           v39[0]);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_12___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_12___(v52);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_11___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_11___(v51);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_10___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_10___(v48);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___(v47);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___(v46);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___(v45);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___(v44);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___(v43);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___(v42);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___(v41);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
    v31 = (utl::_RefCountBase *)a2[1];
    if ( v31 )
      utl::_RefCountBase::_DecStrong(v31);
    return v8;
  }
  Instance = CWwanAoAcHelper::GetInstance();
  if ( !Instance )
  {
    WwanLog::Error("CWwanService::Initialize", 0, L"Failed to get CWwanAoAcHelper instance.");
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_12___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_12___(v52);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_11___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_11___(v51);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_10___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_10___(v48);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___(v47);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___(v46);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___(v45);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___(v44);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___(v43);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___(v42);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___(v41);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
    goto LABEL_52;
  }
  v50 = &v54;
  v34 = CWwanAoAcHelper::Initialize(Instance);
  if ( v34 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xD6,
           (unsigned int)"onecoreuap\\net\\wwan\\service\\core\\wwansvc.cpp",
           (const char *)v34,
           v39[0]);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_13___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_13___(&v49);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_12___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_12___(v52);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_11___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_11___(v51);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_10___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_10___(v48);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___(v47);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___(v46);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___(v45);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___(v44);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___(v43);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___(v42);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___(v41);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
    tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
    v35 = (utl::_RefCountBase *)a2[1];
    if ( v35 )
      utl::_RefCountBase::_DecStrong(v35);
    return v8;
  }
  WwanLog::Info("CWwanService::Initialize", 0, L"WWANSVC Modules Initialization Completed");
  WwanUtilities::DeleteOldLogCopies();
  v54 = 0;
  *a1 = 1;
  tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_13___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_13___(&v49);
  tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_12___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_12___(v52);
  tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_11___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_11___(v51);
  tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_10___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_10___(v48);
  tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_9___(v47);
  tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_8___(v46);
  tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_7___(v45);
  tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_6___(v44);
  tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_5___(v43);
  tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_4___(v42);
  tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_3___(v41);
  tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_2___(v40);
  tlx::_UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___::__UndoInGroup__CWwanService::Initialize_::_2_::_lambda_1___(v39);
  v36 = (utl::_RefCountBase *)a2[1];
  if ( v36 )
    utl::_RefCountBase::_DecStrong(v36);
  return 0;
}

```

## disassembly

```asm
0x180014fe8  mov     [rsp-8+arg_0], rbx
0x180014fed  mov     [rsp-8+arg_8], rdx
0x180014ff2  push    rbp
0x180014ff3  push    rsi
0x180014ff4  push    rdi
0x180014ff5  lea     rbp, [rsp-47h]
0x180014ffa  sub     rsp, 0F0h
0x180015001  mov     rbx, rdx
0x180015004  mov     rsi, rcx
0x180015007  mov     [rbp+57h+arg_10], 1
0x18001500b  lea     rcx, g_hTimerContext
0x180015012  call    cs:__imp_InitializeTimers
0x180015018  mov     edi, eax
0x18001501a  test    eax, eax
0x18001501c  jnz     loc_18001594C
0x180015022  test    cs:WwanControlGuid_61954a80b9663f9147495ff35ed68ca1EnableBits, 1
0x180015029  jz      short loc_180015045
0x18001502b  lea     r8, aWwantimerinit; "WwanTimerInit"
0x180015032  lea     rdx, WwanTm_c14
0x180015039  lea     rcx, WwanControlGuid_Context
0x180015040  call    McTemplateU0s_EventWriteTransfer
0x180015045  lea     rdx, [rsp+100h+var_E0]
0x18001504a  lea     rcx, [rbp+57h+arg_10]
0x18001504e  call    tlx__undo_group__make_undo__CWwanService__Initialize____2____lambda_9___
0x180015053  nop
0x180015054  lea     r8, g_hHandleTable
0x18001505b  mov     edx, 64h ; 'd'
0x180015060  xor     ecx, ecx
0x180015062  call    cs:__imp_HtCreateHandleTable
0x180015068  test    eax, eax
0x18001506a  jz      short loc_1800150A5
0x18001506c  mov     rcx, [rbp+5Fh]; this
0x180015070  mov     r9d, eax; char *
0x180015073  lea     r8, aOnecoreuapNetW_8; "onecoreuap\\net\\wwan\\service\\core\\w"...
0x18001507a  mov     edx, 76h ; 'v'; void *
0x18001507f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015084  mov     edi, eax
0x180015086  lea     rcx, [rsp+100h+var_E0]
0x18001508b  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_1_______UndoInGroup__CWwanService__Initialize____2____lambda_1___
0x180015090  nop
0x180015091  mov     rcx, [rbx+8]; this
0x180015095  test    rcx, rcx
0x180015098  jz      short loc_1800150A0
0x18001509a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18001509f  nop
0x1800150a0  jmp     loc_180015994
0x1800150a5  lea     rdx, [rbp+57h+var_D0]
0x1800150a9  lea     rcx, [rbp+57h+arg_10]
0x1800150ad  call    tlx__undo_group__make_undo__CWwanService__Initialize____2____lambda_9___
0x1800150b2  nop
0x1800150b3  call    ?WwanInitThreadpool@@YAPEAU_WWAN_TP@@XZ; WwanInitThreadpool(void)
0x1800150b8  mov     cs:?g_pWwanThreadpool@@3PEAU_WWAN_TP@@EA, rax; _WWAN_TP * g_pWwanThreadpool
0x1800150bf  test    rax, rax
0x1800150c2  jnz     short loc_1800150F2
0x1800150c4  lea     rcx, [rbp+57h+var_D0]
0x1800150c8  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_2_______UndoInGroup__CWwanService__Initialize____2____lambda_2___
0x1800150cd  nop
0x1800150ce  lea     rcx, [rsp+100h+var_E0]
0x1800150d3  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_1_______UndoInGroup__CWwanService__Initialize____2____lambda_1___
0x1800150d8  nop
0x1800150d9  mov     rcx, [rbx+8]; this
0x1800150dd  test    rcx, rcx
0x1800150e0  jz      short loc_1800150E8
0x1800150e2  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800150e7  nop
0x1800150e8  mov     eax, 5AAh
0x1800150ed  jmp     loc_180015996
0x1800150f2  lea     rdx, [rbp+57h+var_C0]
0x1800150f6  lea     rcx, [rbp+57h+arg_10]
0x1800150fa  call    tlx__undo_group__make_undo__CWwanService__Initialize____2____lambda_9___
0x1800150ff  nop
0x180015100  call    WwanPmInit
0x180015105  test    eax, eax
0x180015107  jz      short loc_180015156
0x180015109  mov     rcx, [rbp+5Fh]; this
0x18001510d  mov     r9d, eax; char *
0x180015110  lea     r8, aOnecoreuapNetW_8; "onecoreuap\\net\\wwan\\service\\core\\w"...
0x180015117  mov     edx, 8Bh; void *
0x18001511c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015121  mov     edi, eax
0x180015123  lea     rcx, [rbp+57h+var_C0]
0x180015127  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_3_______UndoInGroup__CWwanService__Initialize____2____lambda_3___
0x18001512c  nop
0x18001512d  lea     rcx, [rbp+57h+var_D0]
0x180015131  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_2_______UndoInGroup__CWwanService__Initialize____2____lambda_2___
0x180015136  nop
0x180015137  lea     rcx, [rsp+100h+var_E0]
0x18001513c  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_1_______UndoInGroup__CWwanService__Initialize____2____lambda_1___
0x180015141  nop
0x180015142  mov     rcx, [rbx+8]; this
0x180015146  test    rcx, rcx
0x180015149  jz      short loc_180015151
0x18001514b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180015150  nop
0x180015151  jmp     loc_180015994
0x180015156  lea     rdx, [rbp+57h+var_B0]
0x18001515a  lea     rcx, [rbp+57h+arg_10]
0x18001515e  call    tlx__undo_group__make_undo__CWwanService__Initialize____2____lambda_9___
0x180015163  nop
0x180015164  xorps   xmm0, xmm0
0x180015167  movdqu  cs:?g_nlaContext@@3UWWAN_NLA_PLUGIN_CTXT_BLOCK@@A, xmm0; WWAN_NLA_PLUGIN_CTXT_BLOCK g_nlaContext
0x18001516f  call    ?StartMonitoringNetprofmService@@YAKXZ; StartMonitoringNetprofmService(void)
0x180015174  mov     edi, eax
0x180015176  xor     edx, edx; struct _GUID *
0x180015178  lea     rcx, aWwannlaplginit; "WwanNlaPlgInit"
0x18001517f  test    eax, eax
0x180015181  jnz     loc_1800158E9
0x180015187  xor     r9d, r9d
0x18001518a  lea     r8, aWwanPluginInit; "WWAN Plugin Initialization complete 0x%"...
0x180015191  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180015196  lea     rdx, [rbp+57h+var_A0]
0x18001519a  lea     rcx, [rbp+57h+arg_10]
0x18001519e  call    tlx__undo_group__make_undo__CWwanService__Initialize____2____lambda_9___
0x1800151a3  nop
0x1800151a4  call    ?WwanDimInit@@YAKXZ; WwanDimInit(void)
0x1800151a9  test    eax, eax
0x1800151ab  jz      short loc_18001520E
0x1800151ad  mov     rcx, [rbp+5Fh]; this
0x1800151b1  mov     r9d, eax; char *
0x1800151b4  lea     r8, aOnecoreuapNetW_8; "onecoreuap\\net\\wwan\\service\\core\\w"...
0x1800151bb  mov     edx, 95h; void *
0x1800151c0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800151c5  mov     edi, eax
0x1800151c7  lea     rcx, [rbp+57h+var_A0]
0x1800151cb  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_5_______UndoInGroup__CWwanService__Initialize____2____lambda_5___
0x1800151d0  nop
0x1800151d1  lea     rcx, [rbp+57h+var_B0]
0x1800151d5  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_4_______UndoInGroup__CWwanService__Initialize____2____lambda_4___
0x1800151da  nop
0x1800151db  lea     rcx, [rbp+57h+var_C0]
0x1800151df  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_3_______UndoInGroup__CWwanService__Initialize____2____lambda_3___
0x1800151e4  nop
0x1800151e5  lea     rcx, [rbp+57h+var_D0]
0x1800151e9  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_2_______UndoInGroup__CWwanService__Initialize____2____lambda_2___
0x1800151ee  nop
0x1800151ef  lea     rcx, [rsp+100h+var_E0]
0x1800151f4  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_1_______UndoInGroup__CWwanService__Initialize____2____lambda_1___
0x1800151f9  nop
0x1800151fa  mov     rcx, [rbx+8]; this
0x1800151fe  test    rcx, rcx
0x180015201  jz      short loc_180015209
0x180015203  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180015208  nop
0x180015209  jmp     loc_180015994
0x18001520e  lea     rdx, [rbp+57h+var_90]
0x180015212  lea     rcx, [rbp+57h+arg_10]
0x180015216  call    tlx__undo_group__make_undo__CWwanService__Initialize____2____lambda_9___
0x18001521b  nop
0x18001521c  call    ?WwanNhInit@@YAKXZ; WwanNhInit(void)
0x180015221  test    eax, eax
0x180015223  jz      short loc_180015290
0x180015225  mov     rcx, [rbp+5Fh]; this
0x180015229  mov     r9d, eax; char *
0x18001522c  lea     r8, aOnecoreuapNetW_8; "onecoreuap\\net\\wwan\\service\\core\\w"...
0x180015233  mov     edx, 9Ah; void *
0x180015238  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001523d  mov     edi, eax
0x18001523f  lea     rcx, [rbp+57h+var_90]
0x180015243  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_6_______UndoInGroup__CWwanService__Initialize____2____lambda_6___
0x180015248  nop
0x180015249  lea     rcx, [rbp+57h+var_A0]
0x18001524d  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_5_______UndoInGroup__CWwanService__Initialize____2____lambda_5___
0x180015252  nop
0x180015253  lea     rcx, [rbp+57h+var_B0]
0x180015257  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_4_______UndoInGroup__CWwanService__Initialize____2____lambda_4___
0x18001525c  nop
0x18001525d  lea     rcx, [rbp+57h+var_C0]
0x180015261  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_3_______UndoInGroup__CWwanService__Initialize____2____lambda_3___
0x180015266  nop
0x180015267  lea     rcx, [rbp+57h+var_D0]
0x18001526b  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_2_______UndoInGroup__CWwanService__Initialize____2____lambda_2___
0x180015270  nop
0x180015271  lea     rcx, [rsp+100h+var_E0]
0x180015276  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_1_______UndoInGroup__CWwanService__Initialize____2____lambda_1___
0x18001527b  nop
0x18001527c  mov     rcx, [rbx+8]; this
0x180015280  test    rcx, rcx
0x180015283  jz      short loc_18001528B
0x180015285  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18001528a  nop
0x18001528b  jmp     loc_180015994
0x180015290  lea     rdx, [rbp+57h+var_80]
0x180015294  lea     rcx, [rbp+57h+arg_10]
0x180015298  call    tlx__undo_group__make_undo__CWwanService__Initialize____2____lambda_9___
0x18001529d  nop
0x18001529e  call    ?WwanSapMgrInit@@YAKXZ; WwanSapMgrInit(void)
0x1800152a3  test    eax, eax
0x1800152a5  jz      short loc_18001531C
0x1800152a7  mov     rcx, [rbp+5Fh]; this
0x1800152ab  mov     r9d, eax; char *
0x1800152ae  lea     r8, aOnecoreuapNetW_8; "onecoreuap\\net\\wwan\\service\\core\\w"...
0x1800152b5  mov     edx, 9Fh; void *
0x1800152ba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800152bf  mov     edi, eax
0x1800152c1  lea     rcx, [rbp+57h+var_80]
0x1800152c5  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_7_______UndoInGroup__CWwanService__Initialize____2____lambda_7___
0x1800152ca  nop
0x1800152cb  lea     rcx, [rbp+57h+var_90]
0x1800152cf  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_6_______UndoInGroup__CWwanService__Initialize____2____lambda_6___
0x1800152d4  nop
0x1800152d5  lea     rcx, [rbp+57h+var_A0]
0x1800152d9  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_5_______UndoInGroup__CWwanService__Initialize____2____lambda_5___
0x1800152de  nop
0x1800152df  lea     rcx, [rbp+57h+var_B0]
0x1800152e3  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_4_______UndoInGroup__CWwanService__Initialize____2____lambda_4___
0x1800152e8  nop
0x1800152e9  lea     rcx, [rbp+57h+var_C0]
0x1800152ed  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_3_______UndoInGroup__CWwanService__Initialize____2____lambda_3___
0x1800152f2  nop
0x1800152f3  lea     rcx, [rbp+57h+var_D0]
0x1800152f7  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_2_______UndoInGroup__CWwanService__Initialize____2____lambda_2___
0x1800152fc  nop
0x1800152fd  lea     rcx, [rsp+100h+var_E0]
0x180015302  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_1_______UndoInGroup__CWwanService__Initialize____2____lambda_1___
0x180015307  nop
0x180015308  mov     rcx, [rbx+8]; this
0x18001530c  test    rcx, rcx
0x18001530f  jz      short loc_180015317
0x180015311  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180015316  nop
0x180015317  jmp     loc_180015994
0x18001531c  lea     rdx, [rbp+57h+var_70]
0x180015320  lea     rcx, [rbp+57h+arg_10]
0x180015324  call    tlx__undo_group__make_undo__CWwanService__Initialize____2____lambda_9___
0x180015329  nop
0x18001532a  mov     cs:dword_1801528A8, 0
0x180015334  xor     edx, edx; dwSpinCount
0x180015336  lea     rcx, stru_180152880; lpCriticalSection
0x18001533d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180015343  test    eax, eax
0x180015345  jnz     loc_1800153D4
0x18001534b  call    cs:__imp_GetLastError
0x180015351  test    eax, eax
0x180015353  jz      short loc_1800153D4
0x180015355  mov     rcx, [rbp+5Fh]; this
0x180015359  mov     r9d, eax; char *
0x18001535c  lea     r8, aOnecoreuapNetW_8; "onecoreuap\\net\\wwan\\service\\core\\w"...
0x180015363  mov     edx, 0A4h; void *
0x180015368  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001536d  mov     edi, eax
0x18001536f  lea     rcx, [rbp+57h+var_70]
0x180015373  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_8_______UndoInGroup__CWwanService__Initialize____2____lambda_8___
0x180015378  nop
0x180015379  lea     rcx, [rbp+57h+var_80]
0x18001537d  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_7_______UndoInGroup__CWwanService__Initialize____2____lambda_7___
0x180015382  nop
0x180015383  lea     rcx, [rbp+57h+var_90]
0x180015387  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_6_______UndoInGroup__CWwanService__Initialize____2____lambda_6___
0x18001538c  nop
0x18001538d  lea     rcx, [rbp+57h+var_A0]
0x180015391  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_5_______UndoInGroup__CWwanService__Initialize____2____lambda_5___
0x180015396  nop
0x180015397  lea     rcx, [rbp+57h+var_B0]
0x18001539b  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_4_______UndoInGroup__CWwanService__Initialize____2____lambda_4___
0x1800153a0  nop
0x1800153a1  lea     rcx, [rbp+57h+var_C0]
0x1800153a5  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_3_______UndoInGroup__CWwanService__Initialize____2____lambda_3___
0x1800153aa  nop
0x1800153ab  lea     rcx, [rbp+57h+var_D0]
0x1800153af  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_2_______UndoInGroup__CWwanService__Initialize____2____lambda_2___
0x1800153b4  nop
0x1800153b5  lea     rcx, [rsp+100h+var_E0]
0x1800153ba  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_1_______UndoInGroup__CWwanService__Initialize____2____lambda_1___
0x1800153bf  nop
0x1800153c0  mov     rcx, [rbx+8]; this
0x1800153c4  test    rcx, rcx
0x1800153c7  jz      short loc_1800153CF
0x1800153c9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800153ce  nop
0x1800153cf  jmp     loc_180015994
0x1800153d4  lea     rdx, [rbp+57h+var_60]
0x1800153d8  lea     rcx, [rbp+57h+arg_10]
0x1800153dc  call    tlx__undo_group__make_undo__CWwanService__Initialize____2____lambda_9___
0x1800153e1  nop
0x1800153e2  call    WwanGPInit
0x1800153e7  test    eax, eax
0x1800153e9  jz      loc_180015478
0x1800153ef  mov     rcx, [rbp+5Fh]; this
0x1800153f3  mov     r9d, eax; char *
0x1800153f6  lea     r8, aOnecoreuapNetW_8; "onecoreuap\\net\\wwan\\service\\core\\w"...
0x1800153fd  mov     edx, 0B2h; void *
0x180015402  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015407  mov     edi, eax
0x180015409  lea     rcx, [rbp+57h+var_60]
0x18001540d  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_9_______UndoInGroup__CWwanService__Initialize____2____lambda_9___
0x180015412  nop
0x180015413  lea     rcx, [rbp+57h+var_70]
0x180015417  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_8_______UndoInGroup__CWwanService__Initialize____2____lambda_8___
0x18001541c  nop
0x18001541d  lea     rcx, [rbp+57h+var_80]
0x180015421  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_7_______UndoInGroup__CWwanService__Initialize____2____lambda_7___
0x180015426  nop
0x180015427  lea     rcx, [rbp+57h+var_90]
0x18001542b  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_6_______UndoInGroup__CWwanService__Initialize____2____lambda_6___
0x180015430  nop
0x180015431  lea     rcx, [rbp+57h+var_A0]
0x180015435  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_5_______UndoInGroup__CWwanService__Initialize____2____lambda_5___
0x18001543a  nop
0x18001543b  lea     rcx, [rbp+57h+var_B0]
0x18001543f  call    tlx___UndoInGroup__CWwanService__Initialize____2____lambda_4_______UndoInGroup__CWwanService__Initialize____2____lambda_4___
  ... truncated ...
```
