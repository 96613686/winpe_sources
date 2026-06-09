# CWindowsSecurityPrimaryInfo::GetNtGroupsViaAuthZ(IMemObj *)

- ea: `0x1013974c0`
- end: `0x10139824f`
- name: `?GetNtGroupsViaAuthZ@CWindowsSecurityPrimaryInfo@@QEAAXPEAVIMemObj@@@Z`
- size: `3471`
- prototype: `void __fastcall(CWindowsSecurityPrimaryInfo *__hidden this, struct IMemObj *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1013970b0`

## callees

- `0x100401070`
- `0x100401433`
- `0x100403080`
- `0x1004076a0`
- `0x100430d60`
- `0x100754350`
- `0x101394d50`
- `0x1013974c0`

## import_xrefs

- `AUTHZ!AuthzFreeResourceManager` at `0x101398205`
- `AUTHZ!AuthzFreeResourceManager` at `0x101398205`
- `AUTHZ!AuthzFreeContext` at `0x10139821a`
- `AUTHZ!AuthzFreeContext` at `0x10139821a`
- `AUTHZ!AuthzInitializeResourceManager` at `0x101397647`
- `AUTHZ!AuthzInitializeResourceManager` at `0x101397647`
- `AUTHZ!AuthzGetInformationFromContext` at `0x101397bcd`
- `AUTHZ!AuthzGetInformationFromContext` at `0x101397dd7`
- `AUTHZ!AuthzGetInformationFromContext` at `0x101397bcd`
- `AUTHZ!AuthzGetInformationFromContext` at `0x101397dd7`
- `AUTHZ!AuthzInitializeContextFromToken` at `0x101397a0e`
- `AUTHZ!AuthzInitializeContextFromToken` at `0x101397a0e`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x101397818`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x101397818`
- `KERNEL32!GetCurrentProcess` at `0x101397849`
- `KERNEL32!GetCurrentProcess` at `0x101397849`
- `KERNEL32!GetLastError` at `0x101397658`
- `KERNEL32!GetLastError` at `0x10139782d`
- `KERNEL32!GetLastError` at `0x101397866`
- `KERNEL32!GetLastError` at `0x1013978c1`
- `KERNEL32!GetLastError` at `0x101397980`
- `KERNEL32!GetLastError` at `0x101397a20`
- `KERNEL32!GetLastError` at `0x101397bde`
- `KERNEL32!GetLastError` at `0x101397de8`
- `KERNEL32!GetLastError` at `0x101397658`
- `KERNEL32!GetLastError` at `0x10139782d`
- `KERNEL32!GetLastError` at `0x101397866`
- `KERNEL32!GetLastError` at `0x1013978c1`
- `KERNEL32!GetLastError` at `0x101397980`
- `KERNEL32!GetLastError` at `0x101397a20`
- `KERNEL32!GetLastError` at `0x101397bde`
- `KERNEL32!GetLastError` at `0x101397de8`
- `ADVAPI32!GetLengthSid` at `0x101398178`
- `ADVAPI32!GetLengthSid` at `0x101398178`
- `ADVAPI32!EqualSid` at `0x1013979c5`
- `ADVAPI32!EqualSid` at `0x1013979c5`
- `ADVAPI32!GetTokenInformation` at `0x1013978b3`
- `ADVAPI32!GetTokenInformation` at `0x101397976`
- `ADVAPI32!GetTokenInformation` at `0x1013978b3`
- `ADVAPI32!GetTokenInformation` at `0x101397976`
- `ADVAPI32!OpenProcessToken` at `0x10139785c`
- `ADVAPI32!OpenProcessToken` at `0x10139785c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1013980fc`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1013980fc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1013976d3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101397aa9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101397c5e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101397e7b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1013976d3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101397aa9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101397c5e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101397e7b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10139794c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101397c7d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101397eb7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10139819b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10139794c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101397c7d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101397eb7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10139819b`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1013975a7`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10139776f`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101397b35`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101397d30`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101397fa0`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x1013975a7`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10139776f`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101397b35`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101397d30`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x101397fa0`
- `sqldk!SystemThread_TlsIndex` at `0x101397566`
- `sqldk!SystemThread_TlsIndex` at `0x1013975bc`
- `sqldk!SystemThread_TlsIndex` at `0x10139772e`
- `sqldk!SystemThread_TlsIndex` at `0x101397784`
- `sqldk!SystemThread_TlsIndex` at `0x1013978fe`
- `sqldk!SystemThread_TlsIndex` at `0x101397af4`
- `sqldk!SystemThread_TlsIndex` at `0x101397b4d`
- `sqldk!SystemThread_TlsIndex` at `0x101397cec`
- `sqldk!SystemThread_TlsIndex` at `0x101397d48`
- `sqldk!SystemThread_TlsIndex` at `0x101397f5c`
- `sqldk!SystemThread_TlsIndex` at `0x101397fb8`
- `sqldk!SystemThread_TlsOffset` at `0x10139756f`
- `sqldk!SystemThread_TlsOffset` at `0x1013975c5`
- `sqldk!SystemThread_TlsOffset` at `0x101397737`
- `sqldk!SystemThread_TlsOffset` at `0x10139778d`
- `sqldk!SystemThread_TlsOffset` at `0x101397907`
- `sqldk!SystemThread_TlsOffset` at `0x101397afd`
- `sqldk!SystemThread_TlsOffset` at `0x101397b56`
- `sqldk!SystemThread_TlsOffset` at `0x101397cf5`
- `sqldk!SystemThread_TlsOffset` at `0x101397d51`
- `sqldk!SystemThread_TlsOffset` at `0x101397f65`
- `sqldk!SystemThread_TlsOffset` at `0x101397fc1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10139758a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1013975e0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397752`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1013977a8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397922`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397b18`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397b71`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397d10`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397d6c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397f80`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397fdc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10139758a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1013975e0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397752`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1013977a8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397922`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397b18`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397b71`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397d10`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397d6c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397f80`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101397fdc`
- `sqldk!??_V@YAXPEAX@Z` at `0x1013979ae`
- `sqldk!??_V@YAXPEAX@Z` at `0x1013979db`
- `sqldk!??_V@YAXPEAX@Z` at `0x101397c8d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1013981f4`
- `sqldk!??_V@YAXPEAX@Z` at `0x1013979ae`
- `sqldk!??_V@YAXPEAX@Z` at `0x1013979db`
- `sqldk!??_V@YAXPEAX@Z` at `0x101397c8d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1013981f4`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x10139814f`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x101398167`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x10139814f`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x101398167`

## string_xrefs

- `0x1013978e4`: `GetTokenInformation`
- `0x10139799e`: `GetTokenInformation`
- `0x10139787d`: `DwCheckAndGetProcessToken`
- `0x1013978dd`: `DwCheckAndGetProcessToken`
- `0x101397997`: `DwCheckAndGetProcessToken`
- `0x101397884`: `OpenProcessToken`
- `0x10139793e`: `sql\ntdbms\msql\security\src\secnt.cpp`
- `0x101397c73`: `sql\ntdbms\msql\security\src\secnt.cpp`
- `0x101397eaa`: `sql\ntdbms\msql\security\src\secnt.cpp`
- `0x1013980ed`: `sql\ntdbms\msql\security\src\secnt.cpp`
- `0x10139818c`: `sql\ntdbms\msql\security\src\secnt.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
void __fastcall CWindowsSecurityPrimaryInfo::GetNtGroupsViaAuthZ(CWindowsSecurityPrimaryInfo *this, struct IMemObj *a2)
{
  struct IMemObj *v2; // rsi
  DWORD v4; // r15d
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // rdx
  BOOL v10; // edi
  DWORD LastError; // ebx
  unsigned int v12; // eax
  int v13; // ecx
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rdx
  BOOL v19; // r14d
  DWORD v20; // ebx
  void *v21; // rsi
  HANDLE CurrentProcess; // rax
  DWORD v23; // eax
  __int64 v24; // rbx
  __int64 v25; // rdx
  PSID *v26; // rdi
  BOOL v27; // ebx
  void *v28; // rsi
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rbx
  __int64 v33; // rdx
  BOOL InformationFromContext; // edi
  DWORD v35; // ebx
  unsigned int *v36; // r15
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rbx
  __int64 v41; // rdx
  BOOL v42; // edi
  DWORD v43; // ebx
  unsigned __int64 v44; // rax
  void *v45; // rax
  unsigned int v46; // ecx
  unsigned int i; // r12d
  __int64 v48; // rbx
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rbx
  __int64 v52; // rdx
  unsigned int v53; // ecx
  _QWORD *v54; // rax
  _QWORD *v55; // rdx
  __int64 v56; // r14
  unsigned __int64 LengthSid; // rdi
  void *v58; // rbx
  PAUTHZ_RESOURCE_MANAGER_HANDLE phAuthzResourceManager; // [rsp+28h] [rbp-D8h]
  PAUTHZ_RESOURCE_MANAGER_HANDLE phAuthzResourceManagera; // [rsp+28h] [rbp-D8h]
  DWORD ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pSizeRequired; // [rsp+44h] [rbp-BCh] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct IMemObj *v64; // [rsp+50h] [rbp-B0h]
  int *v65; // [rsp+58h] [rbp-A8h]
  AUTHZ_RESOURCE_MANAGER_HANDLE hAuthzResourceManager[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v67; // [rsp+70h] [rbp-90h]
  int v68; // [rsp+80h] [rbp-80h] BYREF
  __int64 v69; // [rsp+88h] [rbp-78h]
  int v70; // [rsp+90h] [rbp-70h] BYREF
  int v71; // [rsp+94h] [rbp-6Ch]
  __int64 v72; // [rsp+98h] [rbp-68h]
  int v73; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v74; // [rsp+A8h] [rbp-58h]
  __int64 v75; // [rsp+B0h] [rbp-50h]
  __int64 v76; // [rsp+B8h] [rbp-48h]
  __int64 v77; // [rsp+C0h] [rbp-40h]
  bool v78; // [rsp+D0h] [rbp-30h]
  int v79; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v80; // [rsp+E8h] [rbp-18h]
  int v81; // [rsp+F0h] [rbp-10h] BYREF
  int v82; // [rsp+F4h] [rbp-Ch]
  __int64 v83; // [rsp+F8h] [rbp-8h]
  int v84; // [rsp+100h] [rbp+0h] BYREF
  __int64 v85; // [rsp+108h] [rbp+8h]
  __int64 v86; // [rsp+110h] [rbp+10h]
  __int64 v87; // [rsp+118h] [rbp+18h]
  __int64 v88; // [rsp+120h] [rbp+20h]
  bool v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+140h] [rbp+40h] BYREF
  __int64 v91; // [rsp+148h] [rbp+48h]
  int v92; // [rsp+150h] [rbp+50h] BYREF
  int v93; // [rsp+154h] [rbp+54h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  int v95; // [rsp+160h] [rbp+60h] BYREF
  __int64 v96; // [rsp+168h] [rbp+68h]
  __int64 v97; // [rsp+170h] [rbp+70h]
  __int64 v98; // [rsp+178h] [rbp+78h]
  __int64 v99; // [rsp+180h] [rbp+80h]
  bool v100; // [rsp+190h] [rbp+90h]
  int v101; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v102; // [rsp+1A8h] [rbp+A8h]
  int v103; // [rsp+1B0h] [rbp+B0h] BYREF
  int v104; // [rsp+1B4h] [rbp+B4h]
  __int64 v105; // [rsp+1B8h] [rbp+B8h]
  int v106; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v107; // [rsp+1C8h] [rbp+C8h]
  __int64 v108; // [rsp+1D0h] [rbp+D0h]
  __int64 v109; // [rsp+1D8h] [rbp+D8h]
  __int64 v110; // [rsp+1E0h] [rbp+E0h]
  bool v111; // [rsp+1F0h] [rbp+F0h]
  int v112; // [rsp+200h] [rbp+100h] BYREF
  __int64 v113; // [rsp+208h] [rbp+108h]
  int v114; // [rsp+210h] [rbp+110h] BYREF
  int v115; // [rsp+214h] [rbp+114h]
  __int64 v116; // [rsp+218h] [rbp+118h]
  int v117; // [rsp+220h] [rbp+120h] BYREF
  __int64 v118; // [rsp+228h] [rbp+128h]
  __int64 v119; // [rsp+230h] [rbp+130h]
  __int64 v120; // [rsp+238h] [rbp+138h]
  __int64 v121; // [rsp+240h] [rbp+140h]
  bool v122; // [rsp+250h] [rbp+150h]
  PSID pSid[2]; // [rsp+260h] [rbp+160h]
  __int64 v124; // [rsp+270h] [rbp+170h]
  struct IMemObj *v125; // [rsp+278h] [rbp+178h]
  int *v126; // [rsp+280h] [rbp+180h]
  _QWORD *v127; // [rsp+288h] [rbp+188h]
  wchar_t v128[72]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t v129[136]; // [rsp+320h] [rbp+220h] BYREF

  v124 = -2;
  v2 = a2;
  v64 = a2;
  v125 = a2;
  *(_OWORD *)hAuthzResourceManager = 0;
  pSizeRequired = 0;
  v67 = 0;
  v4 = 0;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v68, 1);
  TokenHandle = &v70;
  v73 = 536871411;
  v74 = 0;
  v76 = 0;
  v75 = 0;
  v77 = 0;
  v78 = 0;
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v6 = *(_QWORD *)(v5 + 256);
  if ( !v6 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v6 = *(_QWORD *)(v5 + 256);
  }
  v7 = *(_QWORD *)(v6 + 600);
  if ( v7 )
    v78 = (unsigned int)SOS_Task::PushWait(v7, &v73) == 0;
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  v72 = v9;
  v71 = (*(_DWORD *)(v9 + 800) >> 11) & 1;
  if ( v71 || (*(_BYTE *)(v9 + 800) & 4) == 0 )
  {
    v70 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v9 + 608) + 8LL))(*(_QWORD *)(v9 + 608));
  }
  else
  {
    v70 = 0;
  }
  v10 = AuthzInitializeResourceManager(1u, 0, 0, 0, L"My SQL Resource", hAuthzResourceManager);
  if ( v10 )
    LastError = 0;
  else
    LastError = GetLastError();
  TokenHandle = &v70;
  if ( v70 )
  {
    if ( v71 )
      *(_DWORD *)(v72 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v72 + 608) + 16LL))(
        *(_QWORD *)(v72 + 608),
        v72,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v73);
  *(_DWORD *)(v69 + 616) &= ~v68;
  if ( !v10 )
  {
    LODWORD(phAuthzResourceManager) = LastError;
    ex_raise(154, 4, 16, 18, *((_QWORD *)this + 4), phAuthzResourceManager);
  }
  v12 = *((_DWORD *)this + 19);
  if ( v12 <= 8 )
  {
    v13 = 404;
    if ( _bittest(&v13, v12) )
      v4 = 2;
  }
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v79, 1);
  TokenHandle = &v81;
  v84 = 536871410;
  v85 = 0;
  v87 = 0;
  v86 = 0;
  v88 = 0;
  v89 = 0;
  v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v15 = *(_QWORD *)(v14 + 256);
  if ( !v15 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v15 = *(_QWORD *)(v14 + 256);
  }
  v16 = *(_QWORD *)(v15 + 600);
  if ( v16 )
    v89 = (unsigned int)SOS_Task::PushWait(v16, &v84) == 0;
  v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v18 = *(_QWORD *)(v17 + 256);
  if ( !v18 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v18 = *(_QWORD *)(v17 + 256);
  }
  v83 = v18;
  v82 = (*(_DWORD *)(v18 + 800) >> 11) & 1;
  if ( v82 || (*(_BYTE *)(v18 + 800) & 4) == 0 )
  {
    v81 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v18 + 608) + 8LL))(*(_QWORD *)(v18 + 608));
  }
  else
  {
    v81 = 0;
  }
  v19 = AuthzInitializeContextFromSid(
          v4,
          *((PSID *)this + 10),
          hAuthzResourceManager[0],
          0,
          Identifier,
          0,
          (PAUTHZ_CLIENT_CONTEXT_HANDLE)&hAuthzResourceManager[1]);
  if ( v19 )
  {
    v20 = 0;
    goto LABEL_55;
  }
  v20 = GetLastError();
  if ( v20 == 1212 )
  {
    v21 = (void *)*((_QWORD *)this + 10);
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      ReturnLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &ReturnLength) )
      {
        v20 = 1359;
        goto LABEL_54;
      }
      v23 = GetLastError();
      v20 = v23;
      if ( v23 == 122 )
      {
        v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v25 = *(_QWORD *)(v24 + 256);
        if ( !v25 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v25 = *(_QWORD *)(v24 + 256);
        }
        v26 = (PSID *)operator new[](
                        ReturnLength,
                        *(struct IMemObj **)(v25 + 1000),
                        "sql\\ntdbms\\msql\\security\\src\\secnt.cpp",
                        287,
                        3u);
        v65 = (int *)v26;
        if ( GetTokenInformation(TokenHandle, TokenUser, v26, ReturnLength, &ReturnLength) )
        {
          v27 = EqualSid(*v26, v21);
          v28 = 0;
          if ( v27 )
            v28 = TokenHandle;
          operator delete[](v26);
          if ( v27 )
          {
            v19 = AuthzInitializeContextFromToken(
                    v4,
                    v28,
                    hAuthzResourceManager[0],
                    0,
                    Identifier,
                    0,
                    (PAUTHZ_CLIENT_CONTEXT_HANDLE)&hAuthzResourceManager[1]);
            if ( v19 )
              v20 = 0;
            else
              v20 = GetLastError();
            goto LABEL_54;
          }
          goto LABEL_46;
        }
        v20 = GetLastError();
        CSECErrorRingBufferManager::StoreRecord(
          L"GetTokenInformation",
          L"DwCheckAndGetProcessToken",
          v20,
          CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
          0);
        operator delete[](v26);
      }
      else
      {
        CSECErrorRingBufferManager::StoreRecord(
          L"GetTokenInformation",
          L"DwCheckAndGetProcessToken",
          v23,
          CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
          0);
      }
    }
    else
    {
      v20 = GetLastError();
      CSECErrorRingBufferManager::StoreRecord(
        L"OpenProcessToken",
        L"DwCheckAndGetProcessToken",
        v20,
        CSECErrorRingBufferManager::sm_CSECCryptoErrorToWideNames,
        0);
    }
    if ( v20 )
    {
LABEL_54:
      v2 = v64;
      goto LABEL_55;
    }
LABEL_46:
    v20 = 1212;
    goto LABEL_54;
  }
LABEL_55:
  v65 = &v81;
  if ( v81 )
  {
    if ( v82 )
      *(_DWORD *)(v83 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v83 + 608) + 16LL))(
        *(_QWORD *)(v83 + 608),
        v83,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v84);
  *(_DWORD *)(v80 + 616) &= ~v79;
  if ( !v19 )
  {
    LODWORD(phAuthzResourceManagera) = v20;
    ex_raise(154, 4, 16, 19, *((_QWORD *)this + 4), phAuthzResourceManagera);
  }
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v90, 1);
  v65 = &v92;
  v95 = 536871409;
  v96 = 0;
  v98 = 0;
  v97 = 0;
  v99 = 0;
  v100 = 0;
  v29 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v30 = *(_QWORD *)(v29 + 256);
  if ( !v30 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v30 = *(_QWORD *)(v29 + 256);
  }
  v31 = *(_QWORD *)(v30 + 600);
  if ( v31 )
    v100 = (unsigned int)SOS_Task::PushWait(v31, &v95) == 0;
  v32 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v33 = *(_QWORD *)(v32 + 256);
  if ( !v33 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v33 = *(_QWORD *)(v32 + 256);
  }
  v94 = v33;
  v93 = (*(_DWORD *)(v33 + 800) >> 11) & 1;
  if ( v93 || (*(_BYTE *)(v33 + 800) & 4) == 0 )
  {
    v92 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v33 + 608) + 8LL))(*(_QWORD *)(v33 + 608));
  }
  else
  {
    v92 = 0;
  }
  InformationFromContext = AuthzGetInformationFromContext(
                             (AUTHZ_CLIENT_CONTEXT_HANDLE)hAuthzResourceManager[1],
                             AuthzContextInfoGroupsSids,
                             0,
                             &pSizeRequired,
                             0);
  if ( InformationFromContext )
    v35 = 0;
  else
    v35 = GetLastError();
  v65 = &v92;
  if ( v92 )
  {
    if ( v93 )
      *(_DWORD *)(v94 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v94 + 608) + 16LL))(
        *(_QWORD *)(v94 + 608),
        v94,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v95);
  *(_DWORD *)(v91 + 616) &= ~v90;
  if ( !InformationFromContext && v35 != 122 )
  {
    LODWORD(phAuthzResourceManagera) = v35;
    ex_raise(154, 4, 16, 20, *((_QWORD *)this + 4), phAuthzResourceManagera);
  }
  v36 = (unsigned int *)operator new[](pSizeRequired, v2, "sql\\ntdbms\\msql\\security\\src\\secnt.cpp", 2206, 3u);
  if ( v36 )
    operator delete[](0);
  v67 = v36;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v101, 1);
  v65 = &v103;
  v106 = 536871409;
  v107 = 0;
  v109 = 0;
  v108 = 0;
  v110 = 0;
  v111 = 0;
  v37 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v38 = *(_QWORD *)(v37 + 256);
  if ( !v38 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v38 = *(_QWORD *)(v37 + 256);
  }
  v39 = *(_QWORD *)(v38 + 600);
  if ( v39 )
    v111 = (unsigned int)SOS_Task::PushWait(v39, &v106) == 0;
  v40 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v41 = *(_QWORD *)(v40 + 256);
  if ( !v41 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v41 = *(_QWORD *)(v40 + 256);
  }
  v105 = v41;
  v104 = (*(_DWORD *)(v41 + 800) >> 11) & 1;
  if ( v104 || (*(_BYTE *)(v41 + 800) & 4) == 0 )
  {
    v103 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v41 + 608) + 8LL))(*(_QWORD *)(v41 + 608));
  }
  else
  {
    v103 = 0;
  }
  v42 = AuthzGetInformationFromContext(
          (AUTHZ_CLIENT_CONTEXT_HANDLE)hAuthzResourceManager[1],
          AuthzContextInfoGroupsSids,
          pSizeRequired,
          &pSizeRequired,
          v36);
  if ( v42 )
    v43 = 0;
  else
    v43 = GetLastError();
  v65 = &v103;
  if ( v103 )
  {
    if ( v104 )
      *(_DWORD *)(v105 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v105 + 608) + 16LL))(
        *(_QWORD *)(v105 + 608),
        v105,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v106);
  *(_DWORD *)(v102 + 616) &= ~v101;
  if ( !v42 )
  {
    LODWORD(phAuthzResourceManagera) = v43;
    ex_raise(154, 4, 16, 21, *((_QWORD *)this + 4), phAuthzResourceManagera);
  }
  if ( *v36 )
  {
    v44 = 8LL * *v36;
    if ( !is_mul_ok(*v36, 8u) )
      v44 = -1;
    v45 = operator new[](v44, v2, "sql\\ntdbms\\msql\\security\\src\\secnt.cpp", 2227, 3u);
    *((_QWORD *)this + 12) = v45;
    v46 = *v36;
    *((_DWORD *)this + 26) = *v36;
    memset_0(v45, 0, 8 * v46);
    for ( i = 0; i < *v36; v2 = v64 )
    {
      v129[0] = 0;
      v128[0] = 0;
      ReturnLength = 2;
      Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v112, 1);
      v65 = &v114;
      v117 = 536871408;
      v118 = 0;
      v120 = 0;
      v119 = 0;
      v121 = 0;
      v122 = 0;
      v48 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v49 = *(_QWORD *)(v48 + 256);
      if ( !v49 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v49 = *(_QWORD *)(v48 + 256);
      }
      v50 = *(_QWORD *)(v49 + 600);
      if ( v50 )
        v122 = (unsigned int)SOS_Task::PushWait(v50, &v117) == 0;
      v51 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v52 = *(_QWORD *)(v51 + 256);
      if ( !v52 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v52 = *(_QWORD *)(v51 + 256);
      }
      v116 = v52;
      v53 = *(_DWORD *)(v52 + 800);
      v115 = (v53 >> 11) & 1;
      if ( (v53 & 0x800) != 0 || (*(_BYTE *)(v52 + 800) & 4) == 0 )
      {
        v114 = 1;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v52 + 608) + 8LL))(*(_QWORD *)(v52 + 608));
      }
      else
      {
        v114 = 0;
      }
      LookupAccountSidInternal(
        0,
        *(unsigned __int8 **)&v36[4 * i + 2],
        v129,
        v128,
        71,
        (enum _SID_NAME_USE *)&ReturnLength);
      v126 = &v114;
      if ( v114 )
      {
        if ( v115 )
          *(_DWORD *)(v116 + 800) |= 0x800u;
        else
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v116 + 608) + 16LL))(
            *(_QWORD *)(v116 + 608),
            v116,
            1);
      }
      SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v117);
      *(_DWORD *)(v113 + 616) &= ~v112;
      *(_OWORD *)pSid = *(_OWORD *)&v36[4 * i + 2];
      LODWORD(TokenHandle) = 2076;
      v54 = operator new(0x38u, v2, "sql\\ntdbms\\msql\\security\\src\\secnt.cpp", 2076, 3u);
      v55 = v54;
      v127 = v54;
      if ( v54 )
      {
        *v54 = &CWSPSingleInfo::`vftable';
        v54[1] = 0;
        v54[3] = 0;
        v54[5] = 0;
        *((_DWORD *)v54 + 12) = 0;
      }
      else
      {
        v55 = 0;
      }
      *(_QWORD *)(*((_QWORD *)this + 12) + 8LL * *((unsigned int *)this + 27)) = v55;
      v56 = *(_QWORD *)(*((_QWORD *)this + 12) + 8LL * *((unsigned int *)this + 27));
      *(_QWORD *)(v56 + 8) = WszFromWsz(v2, v128, (int *)(v56 + 16));
      *(_QWORD *)(v56 + 24) = WszFromWsz(v2, v129, (int *)(v56 + 32));
      LengthSid = (int)GetLengthSid(pSid[0]);
      v58 = operator new[](LengthSid, v64, "sql\\ntdbms\\msql\\security\\src\\secnt.cpp", 1850, 3u);
      memcpy_s(v58, LengthSid, pSid[0], LengthSid);
      *(_QWORD *)(v56 + 40) = v58;
      *(_DWORD *)(v56 + 36) = ReturnLength;
      *(_DWORD *)(v56 + 48) = pSid[1];
      ++*((_DWORD *)this + 27);
      ++i;
    }
  }
  operator delete[](v36);
  if ( hAuthzResourceManager[0] )
  {
    AuthzFreeResourceManager(hAuthzResourceManager[0]);
    hAuthzResourceManager[0] = 0;
  }
  if ( hAuthzResourceManager[1] )
    AuthzFreeContext((AUTHZ_CLIENT_CONTEXT_HANDLE)hAuthzResourceManager[1]);
}

```

## disassembly

```asm
0x1013974c0  push    rbp
0x1013974c2  push    rsi
0x1013974c3  push    rdi
0x1013974c4  push    r12
0x1013974c6  push    r13
0x1013974c8  push    r14
0x1013974ca  push    r15
0x1013974cc  lea     rbp, [rsp-340h]
0x1013974d4  sub     rsp, 440h
0x1013974db  mov     [rbp+370h+var_200], 0FFFFFFFFFFFFFFFEh
0x1013974e6  mov     [rsp+470h+arg_10], rbx
0x1013974ee  mov     rax, cs:__security_cookie
0x1013974f5  xor     rax, rsp
0x1013974f8  mov     [rbp+370h+var_40], rax
0x1013974ff  mov     rsi, rdx
0x101397502  mov     [rsp+470h+var_420], rdx
0x101397507  mov     r13, rcx
0x10139750a  mov     [rbp+370h+var_1F8], rdx
0x101397511  xorps   xmm0, xmm0
0x101397514  movdqu  xmmword ptr [rsp+470h+hAuthzResourceManager], xmm0
0x10139751a  xor     r12d, r12d
0x10139751d  mov     [rsp+470h+pSizeRequired], r12d
0x101397522  mov     [rsp+470h+var_400], r12
0x101397527  mov     r15d, r12d
0x10139752a  lea     edx, [r12+1]
0x10139752f  lea     rcx, [rbp+370h+var_3F0]
0x101397533  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x101397538  nop
0x101397539  lea     rax, [rbp+370h+var_3E0]
0x10139753d  mov     [rsp+470h+TokenHandle], rax
0x101397542  mov     [rbp+370h+var_3D0], 200001F3h
0x101397549  mov     [rbp+370h+var_3C8], r12
0x10139754d  mov     [rbp+370h+var_3B8], r12
0x101397551  mov     [rbp+370h+var_3C0], r12
0x101397555  mov     [rbp+370h+var_3B0], r12
0x101397559  mov     [rbp+370h+var_3A0], r12b
0x10139755d  mov     rdx, gs:58h
0x101397566  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10139756d  mov     ecx, [rax]
0x10139756f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101397576  mov     ebx, [rax]
0x101397578  add     rbx, [rdx+rcx*8]
0x10139757c  mov     rax, [rbx+100h]
0x101397583  test    rax, rax
0x101397586  jnz     short loc_101397597
0x101397588  xor     ecx, ecx
0x10139758a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101397590  mov     rax, [rbx+100h]
0x101397597  mov     rcx, [rax+258h]
0x10139759e  test    rcx, rcx
0x1013975a1  jz      short loc_1013975B3
0x1013975a3  lea     rdx, [rbp+370h+var_3D0]
0x1013975a7  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x1013975ad  test    eax, eax
0x1013975af  setz    [rbp+370h+var_3A0]
0x1013975b3  mov     rdx, gs:58h
0x1013975bc  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1013975c3  mov     ecx, [rax]
0x1013975c5  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1013975cc  mov     ebx, [rax]
0x1013975ce  add     rbx, [rdx+rcx*8]
0x1013975d2  mov     rdx, [rbx+100h]
0x1013975d9  test    rdx, rdx
0x1013975dc  jnz     short loc_1013975ED
0x1013975de  xor     ecx, ecx
0x1013975e0  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1013975e6  mov     rdx, [rbx+100h]
0x1013975ed  mov     [rbp+370h+var_3D8], rdx
0x1013975f1  mov     eax, [rdx+320h]
0x1013975f7  shr     eax, 0Bh
0x1013975fa  and     eax, 1
0x1013975fd  mov     [rbp+370h+var_3DC], eax
0x101397600  jnz     short loc_101397611
0x101397602  test    byte ptr [rdx+320h], 4
0x101397609  jz      short loc_101397611
0x10139760b  mov     [rbp+370h+var_3E0], r12d
0x10139760f  jmp     short loc_101397626
0x101397611  mov     [rbp+370h+var_3E0], 1
0x101397618  mov     rcx, [rdx+260h]
0x10139761f  mov     rax, [rcx]
0x101397622  call    qword ptr [rax+8]
0x101397625  nop
0x101397626  lea     rax, [rsp+470h+hAuthzResourceManager]
0x10139762b  mov     [rsp+470h+phAuthzResourceManager], rax; phAuthzResourceManager
0x101397630  lea     rax, szResourceManagerName; "My SQL Resource"
0x101397637  mov     [rsp+470h+szResourceManagerName], rax; szResourceManagerName
0x10139763c  xor     r9d, r9d; pfnFreeDynamicGroups
0x10139763f  xor     r8d, r8d; pfnComputeDynamicGroups
0x101397642  xor     edx, edx; pfnDynamicAccessCheck
0x101397644  lea     ecx, [rdx+1]; Flags
0x101397647  call    cs:__imp_AuthzInitializeResourceManager
0x10139764d  mov     edi, eax
0x10139764f  test    eax, eax
0x101397651  jz      short loc_101397658
0x101397653  mov     ebx, r12d
0x101397656  jmp     short loc_101397660
0x101397658  call    cs:__imp_GetLastError
0x10139765e  mov     ebx, eax
0x101397660  lea     rax, [rbp+370h+var_3E0]
0x101397664  mov     [rsp+470h+TokenHandle], rax
0x101397669  cmp     [rbp+370h+var_3E0], 0
0x10139766d  jz      short loc_101397699
0x10139766f  mov     rdx, [rbp+370h+var_3D8]
0x101397673  mov     rcx, [rdx+260h]
0x10139767a  cmp     [rbp+370h+var_3DC], 0
0x10139767e  jz      short loc_10139768C
0x101397680  or      dword ptr [rdx+320h], 800h
0x10139768a  jmp     short loc_101397699
0x10139768c  mov     rax, [rcx]
0x10139768f  mov     r8d, 1
0x101397695  call    qword ptr [rax+10h]
0x101397698  nop
0x101397699  lea     rcx, [rbp+370h+var_3D0]; this
0x10139769d  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x1013976a2  nop
0x1013976a3  mov     ecx, [rbp+370h+var_3F0]
0x1013976a6  not     ecx
0x1013976a8  mov     rax, [rbp+370h+var_3E8]
0x1013976ac  and     [rax+268h], ecx
0x1013976b2  test    edi, edi
0x1013976b4  jnz     short loc_1013976D9
0x1013976b6  mov     rax, [r13+20h]
0x1013976ba  mov     dword ptr [rsp+470h+phAuthzResourceManager], ebx
0x1013976be  mov     [rsp+470h+szResourceManagerName], rax
0x1013976c3  lea     edx, [rdi+4]
0x1013976c6  mov     ecx, 9Ah
0x1013976cb  lea     r9d, [rdi+12h]
0x1013976cf  lea     r8d, [rdi+10h]
0x1013976d3  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1013976d9  mov     eax, [r13+4Ch]
0x1013976dd  cmp     eax, 8
0x1013976e0  ja      short loc_1013976F2
0x1013976e2  mov     ecx, 194h
0x1013976e7  bt      ecx, eax
0x1013976ea  jnb     short loc_1013976F2
0x1013976ec  mov     r15d, 2
0x1013976f2  mov     edx, 1
0x1013976f7  lea     rcx, [rbp+370h+var_390]
0x1013976fb  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x101397700  nop
0x101397701  lea     rax, [rbp+370h+var_380]
0x101397705  mov     [rsp+470h+TokenHandle], rax
0x10139770a  mov     [rbp+370h+var_370], 200001F2h
0x101397711  mov     [rbp+370h+var_368], r12
0x101397715  mov     [rbp+370h+var_358], r12
0x101397719  mov     [rbp+370h+var_360], r12
0x10139771d  mov     [rbp+370h+var_350], r12
0x101397721  mov     [rbp+370h+var_340], 0
0x101397725  mov     rdx, gs:58h
0x10139772e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101397735  mov     ecx, [rax]
0x101397737  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10139773e  mov     ebx, [rax]
0x101397740  add     rbx, [rdx+rcx*8]
0x101397744  mov     rax, [rbx+100h]
0x10139774b  test    rax, rax
0x10139774e  jnz     short loc_10139775F
0x101397750  xor     ecx, ecx
0x101397752  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101397758  mov     rax, [rbx+100h]
0x10139775f  mov     rcx, [rax+258h]
0x101397766  test    rcx, rcx
0x101397769  jz      short loc_10139777B
0x10139776b  lea     rdx, [rbp+370h+var_370]
0x10139776f  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x101397775  test    eax, eax
0x101397777  setz    [rbp+370h+var_340]
0x10139777b  mov     rdx, gs:58h
0x101397784  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10139778b  mov     ecx, [rax]
0x10139778d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101397794  mov     ebx, [rax]
0x101397796  add     rbx, [rdx+rcx*8]
0x10139779a  mov     rdx, [rbx+100h]
0x1013977a1  test    rdx, rdx
0x1013977a4  jnz     short loc_1013977B5
0x1013977a6  xor     ecx, ecx
0x1013977a8  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1013977ae  mov     rdx, [rbx+100h]
0x1013977b5  mov     [rbp+370h+var_378], rdx
0x1013977b9  mov     eax, [rdx+320h]
0x1013977bf  shr     eax, 0Bh
0x1013977c2  and     eax, 1
0x1013977c5  mov     [rbp+370h+var_37C], eax
0x1013977c8  jnz     short loc_1013977D9
0x1013977ca  test    byte ptr [rdx+320h], 4
0x1013977d1  jz      short loc_1013977D9
0x1013977d3  mov     [rbp+370h+var_380], r12d
0x1013977d7  jmp     short loc_1013977EE
0x1013977d9  mov     [rbp+370h+var_380], 1
0x1013977e0  mov     rcx, [rdx+260h]
0x1013977e7  mov     rax, [rcx]
0x1013977ea  call    qword ptr [rax+8]
0x1013977ed  nop
0x1013977ee  lea     rax, [rsp+470h+hAuthzResourceManager+8]
0x1013977f3  mov     [rsp+470h+phAuthzClientContext], rax; phAuthzClientContext
0x1013977f8  mov     [rsp+470h+phAuthzResourceManager], r12; DynamicGroupArgs
0x1013977fd  mov     rax, qword ptr cs:Identifier.LowPart
0x101397804  mov     [rsp+470h+szResourceManagerName], rax; Identifier
0x101397809  xor     r9d, r9d; pExpirationTime
0x10139780c  mov     r8, [rsp+470h+hAuthzResourceManager]; hAuthzResourceManager
0x101397811  mov     rdx, [r13+50h]; UserSid
0x101397815  mov     ecx, r15d; Flags
0x101397818  call    cs:__imp_AuthzInitializeContextFromSid
0x10139781e  mov     r14d, eax
0x101397821  test    eax, eax
0x101397823  jz      short loc_10139782D
0x101397825  mov     ebx, r12d
0x101397828  jmp     loc_101397A34
0x10139782d  call    cs:__imp_GetLastError
0x101397833  mov     ebx, eax
0x101397835  cmp     eax, 4BCh
0x10139783a  jnz     loc_101397A34
0x101397840  mov     rsi, [r13+50h]
0x101397844  mov     [rsp+470h+TokenHandle], r12
0x101397849  call    cs:__imp_GetCurrentProcess
0x10139784f  mov     rcx, rax; ProcessHandle
0x101397852  lea     r8, [rsp+470h+TokenHandle]; TokenHandle
0x101397857  mov     edx, 8; DesiredAccess
0x10139785c  call    cs:__imp_OpenProcessToken
0x101397862  test    eax, eax
0x101397864  jnz     short loc_101397895
0x101397866  call    cs:__imp_GetLastError
0x10139786c  mov     ebx, eax
0x10139786e  mov     dword ptr [rsp+470h+szResourceManagerName], r12d; int
0x101397873  mov     r9, cs:?sm_CSECCryptoErrorToWideNames@CSECErrorRingBufferManager@@2PAPEA_WA; wchar_t *
0x10139787a  mov     r8d, eax; unsigned int
0x10139787d  lea     rdx, ?wszDwCheckAndGetProcessToken@CSECErrorAPI@@2QB_WB; "DwCheckAndGetProcessToken"
0x101397884  lea     rcx, ?wszOpenProcessToken@CSECErrorAPI@@2QB_WB; "OpenProcessToken"
0x10139788b  call    ?StoreRecord@CSECErrorRingBufferManager@@SAXPEB_W0KPEA_WH@Z; CSECErrorRingBufferManager::StoreRecord(wchar_t const *,wchar_t const *,ulong,wchar_t *,int)
0x101397890  jmp     loc_1013979B4
0x101397895  mov     [rsp+470h+ReturnLength], r12d
0x10139789a  lea     rax, [rsp+470h+ReturnLength]
0x10139789f  mov     [rsp+470h+szResourceManagerName], rax; ReturnLength
0x1013978a4  xor     r9d, r9d; TokenInformationLength
0x1013978a7  xor     r8d, r8d; TokenInformation
0x1013978aa  lea     edx, [r9+1]; TokenInformationClass
0x1013978ae  mov     rcx, [rsp+470h+TokenHandle]; TokenHandle
0x1013978b3  call    cs:__imp_GetTokenInformation
0x1013978b9  test    eax, eax
0x1013978bb  jnz     loc_101397A2A
0x1013978c1  call    cs:__imp_GetLastError
0x1013978c7  mov     ebx, eax
0x1013978c9  cmp     eax, 7Ah ; 'z'
0x1013978cc  jz      short loc_1013978F5
0x1013978ce  mov     dword ptr [rsp+470h+szResourceManagerName], r12d; int
0x1013978d3  mov     r9, cs:?sm_CSECCryptoErrorToWideNames@CSECErrorRingBufferManager@@2PAPEA_WA; wchar_t *
0x1013978da  mov     r8d, eax; unsigned int
0x1013978dd  lea     rdx, ?wszDwCheckAndGetProcessToken@CSECErrorAPI@@2QB_WB; "DwCheckAndGetProcessToken"
0x1013978e4  lea     rcx, ?wszGetTokenInformation@CSECErrorAPI@@2QB_WB; "GetTokenInformation"
0x1013978eb  call    ?StoreRecord@CSECErrorRingBufferManager@@SAXPEB_W0KPEA_WH@Z; CSECErrorRingBufferManager::StoreRecord(wchar_t const *,wchar_t const *,ulong,wchar_t *,int)
0x1013978f0  jmp     loc_1013979B4
0x1013978f5  mov     rdx, gs:58h
0x1013978fe  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101397905  mov     ecx, [rax]
0x101397907  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10139790e  mov     ebx, [rax]
0x101397910  add     rbx, [rdx+rcx*8]
0x101397914  mov     rdx, [rbx+100h]
0x10139791b  test    rdx, rdx
0x10139791e  jnz     short loc_10139792F
0x101397920  xor     ecx, ecx
0x101397922  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x101397928  mov     rdx, [rbx+100h]
0x10139792f  mov     ecx, [rsp+470h+ReturnLength]
0x101397933  mov     byte ptr [rsp+470h+szResourceManagerName], 3
0x101397938  mov     r9d, 11Fh
0x10139793e  lea     r8, aSqlNtdbmsMsqlS_86; "sql\\ntdbms\\msql\\security\\src\\secnt"...
0x101397945  mov     rdx, [rdx+3E8h]
0x10139794c  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x101397952  mov     rdi, rax
0x101397955  mov     [rsp+470h+var_418], rax
0x10139795a  lea     rax, [rsp+470h+ReturnLength]
0x10139795f  mov     [rsp+470h+szResourceManagerName], rax; ReturnLength
0x101397964  mov     r9d, [rsp+470h+ReturnLength]; TokenInformationLength
0x101397969  mov     r8, rdi; TokenInformation
0x10139796c  mov     edx, 1; TokenInformationClass
0x101397971  mov     rcx, [rsp+470h+TokenHandle]; TokenHandle
0x101397976  call    cs:__imp_GetTokenInformation
0x10139797c  test    eax, eax
0x10139797e  jnz     short loc_1013979BF
0x101397980  call    cs:__imp_GetLastError
0x101397986  mov     ebx, eax
0x101397988  mov     dword ptr [rsp+470h+szResourceManagerName], r12d; int
0x10139798d  mov     r9, cs:?sm_CSECCryptoErrorToWideNames@CSECErrorRingBufferManager@@2PAPEA_WA; wchar_t *
0x101397994  mov     r8d, eax; unsigned int
0x101397997  lea     rdx, ?wszDwCheckAndGetProcessToken@CSECErrorAPI@@2QB_WB; "DwCheckAndGetProcessToken"
0x10139799e  lea     rcx, ?wszGetTokenInformation@CSECErrorAPI@@2QB_WB; "GetTokenInformation"
0x1013979a5  call    ?StoreRecord@CSECErrorRingBufferManager@@SAXPEB_W0KPEA_WH@Z; CSECErrorRingBufferManager::StoreRecord(wchar_t const *,wchar_t const *,ulong,wchar_t *,int)
0x1013979aa  nop
0x1013979ab  mov     rcx, rdi
0x1013979ae  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1013979b4  test    ebx, ebx
0x1013979b6  jnz     short loc_101397A2F
0x1013979b8  mov     ebx, 4BCh
0x1013979bd  jmp     short loc_101397A2F
0x1013979bf  mov     rdx, rsi; pSid2
0x1013979c2  mov     rcx, [rdi]; pSid1
0x1013979c5  call    cs:__imp_EqualSid
0x1013979cb  mov     ebx, eax
  ... truncated ...
```
