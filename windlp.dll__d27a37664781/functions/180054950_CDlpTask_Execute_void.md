# CDlpTask::Execute(void)

- ea: `0x180054950`
- end: `0x180055b6d`
- name: `?Execute@CDlpTask@@UEAAJXZ`
- size: `4637`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001cd24`
- `0x18001fd60`
- `0x180049d6c`
- `0x180049f34`
- `0x180054950`
- `0x180057498`
- `0x180058910`
- `0x180059134`
- `0x180066a38`
- `0x18006d76c`
- `0x18007d89c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180055556`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180055556`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054a0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054e84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800551f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055358`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005560e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800557fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055849`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055886`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055938`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054a0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054e84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800551f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055358`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005560e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800557fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055849`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055886`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055938`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054e23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005503a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005537c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005557a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055826`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055876`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005590e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800559a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055b4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054e23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005503a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005537c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005557a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055826`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055876`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005590e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800559a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055b4a`

## string_xrefs

- `0x1800549f0`: `DlpTask: Entering Execute Method`
- `0x180054f14`: `DlpTask: Suspending task after prepare...`
- `0x180054e04`: `DlpTask: Preparing Files...`
- `0x180054c3f`: `DlpTask: Transport not set. Skipping download phase.`
- `0x180054a65`: `CDlpTask::Execute`
- `0x1800557cb`: `CDlpTask::Execute`
- `0x180055a4f`: `CDlpTask::Execute`
- `0x180055541`: `DlpTask: Executing Actions...`
- `0x18005532d`: `DlpTask: Suspending task after transfer...`
- `0x180055233`: `DlpTask: Suspending task during transfer...`
- `0x180054fc2`: `DlpTask: Transferring Files...`
- `0x180055aeb`: `DlpTask: Leaving Execute Method`
- `0x18005564f`: `DlpTask: Suspending task during action...`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDlpTask::Execute(CDlpTask *this)
{
  char *v2; // r14
  char *v3; // rbx
  __int64 v4; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  int updated; // edi
  __int64 v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // r12d
  __int64 (__fastcall *v11)(char *); // rax
  int v12; // r13d
  unsigned int v13; // eax
  _QWORD *v14; // rsi
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  struct _RTL_CRITICAL_SECTION *v22; // r12
  __int64 v23; // rax
  __int64 v24; // rax
  struct _RTL_CRITICAL_SECTION *v25; // r13
  enum WINDLP_INTERRUPT_REASON *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  unsigned int v29; // esi
  unsigned int v30; // eax
  __int64 v31; // rax
  enum WINDLP_INTERRUPT_REASON *v32; // rdx
  __int64 v33; // rax
  int v34; // eax
  int v35; // esi
  int v36; // ecx
  unsigned int v37; // esi
  int v38; // eax
  unsigned int v39; // esi
  int v40; // eax
  __int64 v41; // rax
  int v43; // [rsp+20h] [rbp-69h]
  int v44; // [rsp+20h] [rbp-69h]
  int v45; // [rsp+20h] [rbp-69h]
  int v46; // [rsp+28h] [rbp-61h]
  int v47; // [rsp+28h] [rbp-61h]
  int v48; // [rsp+28h] [rbp-61h]
  __int64 v49; // [rsp+48h] [rbp-41h] BYREF
  int v50; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v51[3]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v52; // [rsp+70h] [rbp-19h]
  int v53; // [rsp+88h] [rbp-1h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp+Fh] BYREF
  int v55; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v56; // [rsp+F8h] [rbp+6Fh] BYREF
  int v57; // [rsp+100h] [rbp+77h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+108h] [rbp+7Fh] BYREF

  v52 = 0;
  v51[1] = &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable';
  v2 = (char *)this + 816;
  v51[2] = (char *)this + 816;
  v51[0] = 0;
  v49 = 0;
  v56 = 0;
  v55 = 0;
  v57 = 0;
  SystemTimeAsFileTime = 0;
  v50 = 0;
  v3 = (char *)this + 176;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
  {
    v4 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    CDlpLogT<CEmptyType>::DlpLogFormat(v4, 2, L"DlpTask: Entering Execute Method");
  }
  v5 = (struct _RTL_CRITICAL_SECTION *)(v2 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
  LODWORD(v52) = 1;
  updated = CDlpTask::CheckInitialized(this, (enum WINDLP_STATE *)&v56);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      goto LABEL_227;
    v7 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    v8 = 0;
    if ( !v7 )
      goto LABEL_9;
    v46 = updated;
    v43 = 1399;
    goto LABEL_7;
  }
  v10 = v56;
  if ( v56 == -1073741824 )
  {
    updated = -2147023661;
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      goto LABEL_226;
    v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    v17 = 0;
    if ( !v16 )
      goto LABEL_225;
    v47 = -2147023661;
    v44 = 1410;
LABEL_223:
    v40 = CDlpLogT<CEmptyType>::DlpLogFormat(v16, 4, L"%s(%d): Result = 0x%X", L"CDlpTask::Execute", v44, v47);
    v17 = (unsigned int)v40;
    if ( v40 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v40);
    goto LABEL_225;
  }
  if ( (v56 & 0xFFFFFFFB) != 0 )
  {
    v11 = *(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL);
    if ( v56 != 6 )
    {
      updated = -2147019873;
      if ( !v11(v3) )
        goto LABEL_227;
      v7 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
      v8 = 0;
      if ( v7 )
      {
        v46 = -2147019873;
        v43 = 1418;
        goto LABEL_7;
      }
LABEL_9:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
      goto LABEL_227;
    }
    updated = -1048575740;
    if ( !v11(v3) )
      goto LABEL_227;
    v7 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    v8 = 0;
    if ( !v7 )
      goto LABEL_9;
    v46 = -1048575740;
    v43 = 1414;
LABEL_7:
    v9 = CDlpLogT<CEmptyType>::DlpLogFormat(v7, 4, L"%s(%d): Result = 0x%X", L"CDlpTask::Execute", v43, v46);
    v8 = (unsigned int)v9;
    if ( v9 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9);
    goto LABEL_9;
  }
  v12 = *((_DWORD *)this + 91);
  v13 = *((_DWORD *)this + 95);
  v56 = v13;
  if ( !v12 && !v13 )
  {
    updated = -2147024637;
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      goto LABEL_227;
    v7 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    v8 = 0;
    if ( !v7 )
      goto LABEL_9;
    v46 = -2147024637;
    v43 = 1432;
    goto LABEL_7;
  }
  v14 = (_QWORD *)((char *)this + 1488);
  v15 = WINDLP_TRANSPORT_NONE;
  if ( v12 )
  {
    if ( WINDLP_TRANSPORT_NONE != *v14 )
      goto LABEL_37;
    if ( !*((_QWORD *)this + 187) )
    {
      updated = -2147024883;
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
        goto LABEL_226;
      v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
      v17 = 0;
      if ( !v16 )
        goto LABEL_225;
      v47 = -2147024883;
      v44 = 1436;
      goto LABEL_223;
    }
  }
  if ( WINDLP_TRANSPORT_NONE == *v14 )
  {
    if ( !*((_QWORD *)this + 187) )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      {
        v18 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
        CDlpLogT<CEmptyType>::DlpLogFormat(v18, 2, L"DlpTask: Transport not set. Skipping download phase.");
      }
      v15 = WINDLP_TRANSPORT_NONE;
    }
    if ( v15 == *v14 && !*((_QWORD *)this + 187) )
      goto LABEL_47;
  }
LABEL_37:
  updated = (*(__int64 (__fastcall **)(CDlpTask *, _QWORD *))(*(_QWORD *)this + 216LL))(this, v51);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      goto LABEL_226;
    v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    v17 = 0;
    if ( !v16 )
      goto LABEL_225;
    v47 = updated;
    v44 = 1447;
    goto LABEL_223;
  }
  updated = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v51[0] + 24LL))(v51[0], &v55);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      goto LABEL_226;
    v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    v17 = 0;
    if ( !v16 )
      goto LABEL_225;
    v47 = updated;
    v44 = 1448;
    goto LABEL_223;
  }
  if ( (v55 & 0xFFFFFFF9) != 0 || v55 == 2 )
  {
    updated = -2147024875;
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      goto LABEL_226;
    v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    v17 = 0;
    if ( !v16 )
      goto LABEL_225;
    v47 = -2147024875;
    v44 = 1451;
    goto LABEL_223;
  }
LABEL_47:
  lpCriticalSection = (LPCRITICAL_SECTION)(v2 + 8);
  *((_QWORD *)this + 176) = 0;
  if ( WINDLP_TRANSPORT_NONE == *v14 && !*((_QWORD *)this + 187) )
    goto LABEL_118;
  if ( v10 == 4 )
  {
    if ( !*((_DWORD *)this + 354) )
      goto LABEL_118;
  }
  else
  {
    updated = CDlpTask::UpdateState(this, 1);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
        goto LABEL_181;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
      v20 = 0;
      if ( !v19 )
        goto LABEL_180;
      v48 = updated;
      v45 = 1471;
      goto LABEL_178;
    }
    if ( v12 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      {
        v21 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
        CDlpLogT<CEmptyType>::DlpLogFormat(v21, 2, L"DlpTask: Preparing Files...");
      }
      v22 = lpCriticalSection;
      if ( (_DWORD)v52 )
      {
        LeaveCriticalSection(lpCriticalSection);
        LODWORD(v52) = 0;
      }
      updated = CDlpTask::ExecutePrepare(this);
      if ( updated < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
          goto LABEL_181;
        v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
        v20 = 0;
        if ( !v19 )
          goto LABEL_180;
        v48 = updated;
        v45 = 1483;
        goto LABEL_178;
      }
      EnterCriticalSection(v22);
      LODWORD(v52) = 1;
    }
    updated = CDlpTask::UpdateState(this, 2);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
        goto LABEL_181;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
      v20 = 0;
      if ( !v19 )
        goto LABEL_180;
      v48 = updated;
      v45 = 1492;
      goto LABEL_178;
    }
    if ( *((_DWORD *)this + 353) )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      {
        v23 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
        CDlpLogT<CEmptyType>::DlpLogFormat(v23, 2, L"DlpTask: Suspending task after prepare...");
      }
LABEL_71:
      updated = 0;
      goto LABEL_181;
    }
  }
  updated = CDlpTask::UpdateState(this, 3);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      goto LABEL_181;
    v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    v20 = 0;
    if ( !v19 )
      goto LABEL_180;
    v48 = updated;
    v45 = 1510;
    goto LABEL_178;
  }
  if ( v12 )
  {
    if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
    {
      v24 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
      CDlpLogT<CEmptyType>::DlpLogFormat(v24, 2, L"DlpTask: Transferring Files...");
    }
    updated = CDlpTask::ReportDiagTime(this, 4097, (char *)this + 1488);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
        goto LABEL_181;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
      v20 = 0;
      if ( !v19 )
        goto LABEL_180;
      v48 = updated;
      v45 = 1518;
      goto LABEL_178;
    }
    v25 = lpCriticalSection;
    if ( (_DWORD)v52 )
    {
      LeaveCriticalSection(lpCriticalSection);
      LODWORD(v52) = 0;
    }
    updated = (*(__int64 (__fastcall **)(char *, __int64, CDlpTask *))(*((_QWORD *)this + 2) + 24LL))(
                (char *)this + 16,
                65538,
                this);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
        goto LABEL_181;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
      v20 = 0;
      if ( !v19 )
        goto LABEL_180;
      v48 = updated;
      v45 = 1526;
      goto LABEL_178;
    }
    *((_DWORD *)this + 354) = 1;
    updated = CDlpTask::ExecuteTransfer(this);
    CDlpTask::ReportDiagTime(this, 4098, (char *)this + 1488);
    CDlpTask::ReportDiagTime(this, 4096, (char *)this + 1488);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
        goto LABEL_181;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
      v20 = 0;
      if ( !v19 )
        goto LABEL_180;
      v48 = updated;
      v45 = 1539;
      goto LABEL_178;
    }
    updated = CDlpTask::CheckUserInterrupt(this, v26);
    if ( updated == -2147023661 )
    {
      if ( *((_DWORD *)this + 353) )
      {
LABEL_96:
        updated = (*(__int64 (__fastcall **)(char *, __int64, CDlpTask *))(*((_QWORD *)this + 2) + 24LL))(
                    (char *)this + 16,
                    65540,
                    this);
        if ( updated < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
            goto LABEL_181;
          v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
          v20 = 0;
          if ( !v19 )
            goto LABEL_180;
          v48 = updated;
          v45 = 1550;
          goto LABEL_178;
        }
        EnterCriticalSection(v25);
        LODWORD(v52) = 1;
        if ( *((_DWORD *)this + 353) )
        {
          if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
          {
            v27 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
            CDlpLogT<CEmptyType>::DlpLogFormat(v27, 2, L"DlpTask: Suspending task during transfer...");
          }
          updated = CDlpTask::UpdateState(this, 4);
          if ( updated >= 0 )
            goto LABEL_71;
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
            goto LABEL_181;
          v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
          v20 = 0;
          if ( !v19 )
            goto LABEL_180;
          v48 = updated;
          v45 = 1561;
LABEL_178:
          v34 = CDlpLogT<CEmptyType>::DlpLogFormat(v19, 4, L"%s(%d): Result = 0x%X", L"CDlpTask::Execute", v45, v48);
          v20 = (unsigned int)v34;
          if ( v34 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v34);
          goto LABEL_180;
        }
        *((_DWORD *)this + 354) = 0;
        updated = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v51[0] + 24LL))(v51[0], &v55);
        if ( updated < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
            goto LABEL_181;
          v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
          v20 = 0;
          if ( !v19 )
            goto LABEL_180;
          v48 = updated;
          v45 = 1571;
          goto LABEL_178;
        }
        if ( v55 != 6 )
        {
          if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
          {
            v28 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
            CDlpLogT<CEmptyType>::DlpLogFormat(v28, 2, L"DlpTask: Suspending task after transfer...");
          }
          goto LABEL_71;
        }
        goto LABEL_119;
      }
    }
    else if ( updated >= 0 )
    {
      goto LABEL_96;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      goto LABEL_181;
    v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    v20 = 0;
    if ( !v19 )
      goto LABEL_180;
    v48 = updated;
    v45 = 1546;
    goto LABEL_178;
  }
LABEL_118:
  v25 = lpCriticalSection;
LABEL_119:
  if ( !v56 )
    goto LABEL_174;
  v29 = 0;
  LODWORD(lpCriticalSection) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  v53 = 1;
  *((_DWORD *)this + 218) = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v53 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
    v53 = 0;
  }
  updated = CDlpTask::UpdateState(this, 3);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      goto LABEL_181;
    v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    v20 = 0;
    if ( !v19 )
      goto LABEL_180;
    v48 = updated;
    v45 = 1590;
    goto LABEL_178;
  }
  if ( !v56 )
  {
LABEL_174:
    updated = CDlpTask::UpdateState(this, 6);
    if ( updated >= 0 || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      goto LABEL_181;
    v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    v20 = 0;
    if ( !v19 )
      goto LABEL_180;
    v48 = updated;
    v45 = 1669;
    goto LABEL_178;
  }
  while ( 1 )
  {
    if ( v49 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      v49 = 0;
    }
    updated = (*(__int64 (__fastcall **)(CDlpTask *, _QWORD, __int64 *))(*(_QWORD *)this + 120LL))(this, v29, &v49);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
        goto LABEL_181;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
      v20 = 0;
      if ( v19 )
      {
        v48 = updated;
        v45 = 1599;
        goto LABEL_178;
      }
      goto LABEL_180;
    }
    updated = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 24LL))(v49, &v57);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
        goto LABEL_181;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
      v20 = 0;
      if ( v19 )
      {
        v48 = updated;
        v45 = 1603;
        goto LABEL_178;
      }
      goto LABEL_180;
    }
    if ( v57 == -21037378 || !v57 )
      break;
    if ( v57 != 6 )
    {
      if ( v57 != 4 )
      {
        updated = -2147019873;
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
          goto LABEL_181;
        v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
        v20 = 0;
        if ( v19 )
        {
          v48 = -2147019873;
          v45 = 1607;
          goto LABEL_178;
        }
        goto LABEL_180;
      }
      break;
    }
LABEL_136:
    updated = CDword::Increment((CDlpTask *)((char *)this + 872), (unsigned int *)&lpCriticalSection);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
        goto LABEL_181;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
      v20 = 0;
      if ( v19 )
      {
        v48 = updated;
        v45 = 1615;
        goto LABEL_178;
      }
      goto LABEL_180;
    }
    v29 = (unsigned int)lpCriticalSection;
    v30 = v56;
    if ( (unsigned int)lpCriticalSection >= v56 )
      goto LABEL_146;
  }
  if ( v57 == 6 )
    goto LABEL_136;
  v30 = v56;
LABEL_146:
  if ( v29 >= v30 )
    goto LABEL_174;
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
  {
    v31 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    CDlpLogT<CEmptyType>::DlpLogFormat(v31, 2, L"DlpTask: Executing Actions...");
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *((struct _FILETIME *)this + 185) = SystemTimeAsFileTime;
  if ( (_DWORD)v52 )
  {
    LeaveCriticalSection(v25);
    LODWORD(v52) = 0;
  }
  updated = CDlpTask::ExecuteActions(this);
  CDlpTask::ReportDiagTime(this, 0x2000, 0);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      goto LABEL_181;
    v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    v20 = 0;
    if ( v19 )
    {
      v48 = updated;
      v45 = 1643;
      goto LABEL_178;
    }
    goto LABEL_180;
  }
  updated = CDlpTask::CheckUserInterrupt(this, v32);
  if ( updated == -2147023661 )
  {
    if ( *((_DWORD *)this + 353) )
      goto LABEL_157;
LABEL_165:
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
      goto LABEL_181;
    v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    v20 = 0;
    if ( v19 )
    {
      v48 = updated;
      v45 = 1650;
      goto LABEL_178;
    }
    goto LABEL_180;
  }
  if ( updated < 0 )
    goto LABEL_165;
LABEL_157:
  EnterCriticalSection(v25);
  LODWORD(v52) = 1;
  if ( !*((_DWORD *)this + 353) )
    goto LABEL_174;
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
  {
    v33 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    CDlpLogT<CEmptyType>::DlpLogFormat(v33, 2, L"DlpTask: Suspending task during action...");
  }
  updated = CDlpTask::UpdateState(this, 4);
  if ( updated >= 0 )
    goto LABEL_71;
  if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
    goto LABEL_181;
  v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
  v20 = 0;
  if ( v19 )
  {
    v48 = updated;
    v45 = 1661;
    goto LABEL_178;
  }
LABEL_180:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v20);
LABEL_181:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  v53 = 1;
  v35 = *((_DWORD *)this + 74);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v53 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
    v53 = 0;
  }
  if ( v35 != -1073741824 )
  {
    if ( updated >= 0 )
      goto LABEL_226;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
    v53 = 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v38 = *((_DWORD *)this + 74);
    if ( v38 == -1 || v38 == -21037378 )
    {
      v39 = 0;
    }
    else
    {
      if ( v38 == -858993460 )
      {
        v39 = -1048575735;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(3246391561LL);
        goto LABEL_212;
      }
      v39 = 0;
      if ( v38 != -1073741824 )
        *((_DWORD *)this + 75) = v38;
    }
    *((_DWORD *)this + 74) = -1;
LABEL_212:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v39);
    if ( v53 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
      v53 = 0;
    }
    if ( (v39 & 0x80000000) != 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v39);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v39);
    CDlpTask::InternalSetError(this, updated);
    goto LABEL_226;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v53 = 1;
  if ( updated < 0 )
    *((_DWORD *)this + 26) = updated;
  else
    *((_DWORD *)this + 26) = -2147023661;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v53 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
    v53 = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  v53 = 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v36 = *((_DWORD *)this + 74);
  if ( v36 == -858993460 || v36 == -21037378 )
  {
    v37 = 0;
    goto LABEL_191;
  }
  if ( v36 == -1 )
  {
    v37 = -1048575734;
LABEL_197:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v37);
  }
  else
  {
    v37 = 0;
    if ( ((v36 + 0x40000000) & 0xBFFFFFFF) != 0 )
    {
      v37 = -2147019873;
      goto LABEL_197;
    }
LABEL_191:
    *((_DWORD *)this + 74) = -858993460;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v37);
  if ( v53 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
    v53 = 0;
  }
  if ( (v37 & 0x80000000) != 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v37);
  v17 = v37;
LABEL_225:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v17);
LABEL_226:
  v5 = (struct _RTL_CRITICAL_SECTION *)(v2 + 8);
LABEL_227:
  v50 = updated;
  (**((void (__fastcall ***)(char *, __int64, _QWORD, int *, _QWORD, _DWORD))this + 2))(
    (char *)this + 16,
    12288,
    0,
    &v50,
    0,
    0);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 163) + 280LL))(*((_QWORD *)this + 163), 0);
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3) )
  {
    v41 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
    CDlpLogT<CEmptyType>::DlpLogFormat(v41, 2, L"DlpTask: Leaving Execute Method");
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)updated);
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v49 = 0;
  }
  if ( v51[0] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v51[0] + 16LL))(v51[0]);
    v51[0] = 0;
  }
  if ( (_DWORD)v52 )
  {
    LeaveCriticalSection(v5);
    LODWORD(v52) = 0;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180054950  push    rbp
0x180054952  push    rbx
0x180054953  push    rsi
0x180054954  push    rdi
0x180054955  push    r12
0x180054957  push    r13
0x180054959  push    r14
0x18005495b  push    r15
0x18005495d  lea     rbp, [rsp-1Fh]
0x180054962  sub     rsp, 0A8h
0x180054969  mov     r15, rcx
0x18005496c  xorps   xmm0, xmm0
0x18005496f  xor     eax, eax
0x180054971  movups  [rbp+57h+var_80], xmm0
0x180054975  mov     [rbp+57h+var_70], rax
0x180054979  lea     rax, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x180054980  mov     qword ptr [rbp+57h+var_80], rax
0x180054984  lea     r14, [rcx+330h]
0x18005498b  mov     qword ptr [rbp+57h+var_80+8], r14
0x18005498f  mov     [rbp+57h+var_88], 0
0x180054997  mov     [rbp+57h+var_98], 0
0x18005499f  mov     [rbp+57h+arg_8], 0
0x1800549a6  mov     [rbp+57h+arg_0], 0
0x1800549ad  mov     [rbp+57h+arg_10], 0
0x1800549b4  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800549bc  mov     [rbp+57h+var_90], 0
0x1800549c3  lea     rbx, [rcx+0B0h]
0x1800549ca  mov     rax, [rbx]
0x1800549cd  mov     rcx, rbx
0x1800549d0  mov     rax, [rax+10h]
0x1800549d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549d9  test    rax, rax
0x1800549dc  jz      short loc_180054A01
0x1800549de  mov     rax, [rbx]
0x1800549e1  mov     rcx, rbx
0x1800549e4  mov     rax, [rax+10h]
0x1800549e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549ed  mov     rcx, rax
0x1800549f0  lea     r8, aDlptaskEnterin; "DlpTask: Entering Execute Method"
0x1800549f7  mov     edx, 2
0x1800549fc  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180054a01  lea     rsi, [r14+8]
0x180054a05  mov     [rbp+57h+var_A0], rsi
0x180054a09  mov     rcx, rsi; lpCriticalSection
0x180054a0c  call    cs:__imp_EnterCriticalSection
0x180054a12  mov     dword ptr [rbp+57h+var_70], 1
0x180054a19  lea     rdx, [rbp+57h+arg_8]; enum WINDLP_STATE *
0x180054a1d  mov     rcx, r15; this
0x180054a20  call    ?CheckInitialized@CDlpTask@@AEAAJPEAW4WINDLP_STATE@@@Z; CDlpTask::CheckInitialized(WINDLP_STATE *)
0x180054a25  mov     edi, eax
0x180054a27  test    eax, eax
0x180054a29  jns     short loc_180054A95
0x180054a2b  mov     rcx, [rbx]
0x180054a2e  mov     rax, [rcx+10h]
0x180054a32  mov     rcx, rbx
0x180054a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a3a  test    rax, rax
0x180054a3d  jz      loc_180055A7E
0x180054a43  mov     rcx, [rbx]
0x180054a46  mov     rax, [rcx+10h]
0x180054a4a  mov     rcx, rbx
0x180054a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a52  xor     ecx, ecx
0x180054a54  test    rax, rax
0x180054a57  jz      short loc_180054A8B
0x180054a59  mov     [rsp+0E0h+var_B8], edi
0x180054a5d  mov     dword ptr [rsp+0E0h+var_C0], 577h
0x180054a65  lea     r9, aCdlptaskExecut_3; "CDlpTask::Execute"
0x180054a6c  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180054a73  mov     edx, 4
0x180054a78  mov     rcx, rax
0x180054a7b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180054a80  test    eax, eax
0x180054a82  mov     ecx, eax
0x180054a84  jns     short loc_180054A8B
0x180054a86  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180054a8b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180054a90  jmp     loc_180055A7E
0x180054a95  mov     r12d, [rbp+57h+arg_8]
0x180054a99  cmp     r12d, 0C0000000h
0x180054aa0  jz      loc_180055A12
0x180054aa6  test    r12d, 0FFFFFFFBh
0x180054aad  jz      loc_180054B3B
0x180054ab3  mov     rax, [rbx]
0x180054ab6  mov     rcx, rbx
0x180054ab9  mov     rax, [rax+10h]
0x180054abd  cmp     r12d, 6
0x180054ac1  jz      short loc_180054AFD
0x180054ac3  mov     edi, 8007139Fh
0x180054ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054acd  test    rax, rax
0x180054ad0  jz      loc_180055A7E
0x180054ad6  mov     rax, [rbx]
0x180054ad9  mov     rcx, rbx
0x180054adc  mov     rax, [rax+10h]
0x180054ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ae5  xor     ecx, ecx
0x180054ae7  test    rax, rax
0x180054aea  jz      short loc_180054A8B
0x180054aec  mov     [rsp+0E0h+var_B8], edi
0x180054af0  mov     dword ptr [rsp+0E0h+var_C0], 58Ah
0x180054af8  jmp     loc_180054A65
0x180054afd  mov     edi, 0C1800104h
0x180054b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b07  test    rax, rax
0x180054b0a  jz      loc_180055A7E
0x180054b10  mov     rax, [rbx]
0x180054b13  mov     rcx, rbx
0x180054b16  mov     rax, [rax+10h]
0x180054b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b1f  xor     ecx, ecx
0x180054b21  test    rax, rax
0x180054b24  jz      loc_180054A8B
0x180054b2a  mov     [rsp+0E0h+var_B8], edi
0x180054b2e  mov     dword ptr [rsp+0E0h+var_C0], 586h
0x180054b36  jmp     loc_180054A65
0x180054b3b  mov     r13d, [r15+16Ch]
0x180054b42  mov     eax, [r15+17Ch]
0x180054b49  mov     [rbp+57h+arg_8], eax
0x180054b4c  test    r13d, r13d
0x180054b4f  jnz     short loc_180054B9D
0x180054b51  test    eax, eax
0x180054b53  jnz     short loc_180054B9D
0x180054b55  mov     edi, 80070103h
0x180054b5a  mov     rax, [rbx]
0x180054b5d  mov     rcx, rbx
0x180054b60  mov     rax, [rax+10h]
0x180054b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b69  test    rax, rax
0x180054b6c  jz      loc_180055A7E
0x180054b72  mov     rax, [rbx]
0x180054b75  mov     rcx, rbx
0x180054b78  mov     rax, [rax+10h]
0x180054b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b81  xor     ecx, ecx
0x180054b83  test    rax, rax
0x180054b86  jz      loc_180054A8B
0x180054b8c  mov     [rsp+0E0h+var_B8], edi
0x180054b90  mov     dword ptr [rsp+0E0h+var_C0], 598h
0x180054b98  jmp     loc_180054A65
0x180054b9d  lea     rsi, [r15+5D0h]
0x180054ba4  mov     rcx, cs:qword_1800926A0
0x180054bab  mov     rax, cs:WINDLP_TRANSPORT_NONE
0x180054bb2  test    r13d, r13d
0x180054bb5  jz      short loc_180054C0E
0x180054bb7  cmp     rax, [rsi]
0x180054bba  jnz     loc_180054C6D
0x180054bc0  cmp     rcx, [rsi+8]
0x180054bc4  jnz     short loc_180054C0E
0x180054bc6  mov     edi, 8007000Dh
0x180054bcb  mov     rax, [rbx]
0x180054bce  mov     rcx, rbx
0x180054bd1  mov     rax, [rax+10h]
0x180054bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bda  test    rax, rax
0x180054bdd  jz      loc_180055A7A
0x180054be3  mov     rax, [rbx]
0x180054be6  mov     rcx, rbx
0x180054be9  mov     rax, [rax+10h]
0x180054bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bf2  xor     ecx, ecx
0x180054bf4  test    rax, rax
0x180054bf7  jz      loc_180055A75
0x180054bfd  mov     [rsp+0E0h+var_B8], edi
0x180054c01  mov     dword ptr [rsp+0E0h+var_C0], 59Ch
0x180054c09  jmp     loc_180055A4F
0x180054c0e  cmp     rax, [rsi]
0x180054c11  jnz     short loc_180054C6D
0x180054c13  cmp     rcx, [rsi+8]
0x180054c17  jnz     short loc_180054C5E
0x180054c19  mov     rax, [rbx]
0x180054c1c  mov     rcx, rbx
0x180054c1f  mov     rax, [rax+10h]
0x180054c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c28  test    rax, rax
0x180054c2b  jz      short loc_180054C50
0x180054c2d  mov     rax, [rbx]
0x180054c30  mov     rcx, rbx
0x180054c33  mov     rax, [rax+10h]
0x180054c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c3c  mov     rcx, rax
0x180054c3f  lea     r8, aDlptaskTranspo; "DlpTask: Transport not set. Skipping do"...
0x180054c46  mov     edx, 2
0x180054c4b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180054c50  mov     rax, cs:WINDLP_TRANSPORT_NONE
0x180054c57  mov     rcx, cs:qword_1800926A0
0x180054c5e  cmp     rax, [rsi]
0x180054c61  jnz     short loc_180054C6D
0x180054c63  cmp     rcx, [rsi+8]
0x180054c67  jz      loc_180054D40
0x180054c6d  mov     rax, [r15]
0x180054c70  lea     rdx, [rbp+57h+var_88]
0x180054c74  mov     rcx, r15
0x180054c77  mov     rax, [rax+0D8h]
0x180054c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c83  mov     edi, eax
0x180054c85  test    eax, eax
0x180054c87  jns     short loc_180054CCC
0x180054c89  mov     rax, [rbx]
0x180054c8c  mov     rcx, rbx
0x180054c8f  mov     rax, [rax+10h]
0x180054c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c98  test    rax, rax
0x180054c9b  jz      loc_180055A7A
0x180054ca1  mov     rax, [rbx]
0x180054ca4  mov     rcx, rbx
0x180054ca7  mov     rax, [rax+10h]
0x180054cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054cb0  xor     ecx, ecx
0x180054cb2  test    rax, rax
0x180054cb5  jz      loc_180055A75
0x180054cbb  mov     [rsp+0E0h+var_B8], edi
0x180054cbf  mov     dword ptr [rsp+0E0h+var_C0], 5A7h
0x180054cc7  jmp     loc_180055A4F
0x180054ccc  mov     rcx, [rbp+57h+var_88]
0x180054cd0  mov     rax, [rcx]
0x180054cd3  lea     rdx, [rbp+57h+arg_0]
0x180054cd7  mov     rax, [rax+18h]
0x180054cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ce0  mov     edi, eax
0x180054ce2  test    eax, eax
0x180054ce4  jns     short loc_180054D29
0x180054ce6  mov     rax, [rbx]
0x180054ce9  mov     rcx, rbx
0x180054cec  mov     rax, [rax+10h]
0x180054cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054cf5  test    rax, rax
0x180054cf8  jz      loc_180055A7A
0x180054cfe  mov     rax, [rbx]
0x180054d01  mov     rcx, rbx
0x180054d04  mov     rax, [rax+10h]
0x180054d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054d0d  xor     ecx, ecx
0x180054d0f  test    rax, rax
0x180054d12  jz      loc_180055A75
0x180054d18  mov     [rsp+0E0h+var_B8], edi
0x180054d1c  mov     dword ptr [rsp+0E0h+var_C0], 5A8h
0x180054d24  jmp     loc_180055A4F
0x180054d29  test    [rbp+57h+arg_0], 0FFFFFFF9h
0x180054d30  jnz     loc_1800559D1
0x180054d36  cmp     [rbp+57h+arg_0], 2
0x180054d3a  jz      loc_1800559D1
0x180054d40  lea     rax, [r14+8]
0x180054d44  mov     [rbp+57h+lpCriticalSection], rax
0x180054d48  mov     qword ptr [r15+580h], 0
0x180054d53  mov     rax, cs:WINDLP_TRANSPORT_NONE
0x180054d5a  mov     r14d, 4
0x180054d60  cmp     rax, [rsi]
0x180054d63  jnz     short loc_180054D76
0x180054d65  mov     rax, cs:qword_1800926A0
0x180054d6c  cmp     rax, [rsi+8]
0x180054d70  jz      loc_180055339
0x180054d76  cmp     r12d, r14d
0x180054d79  jz      loc_180054F2F
0x180054d7f  mov     edx, 1
0x180054d84  mov     rcx, r15
0x180054d87  call    ?UpdateState@CDlpTask@@AEAAJW4WINDLP_STATE@@PEAW42@@Z; CDlpTask::UpdateState(WINDLP_STATE,WINDLP_STATE *)
0x180054d8c  mov     edi, eax
0x180054d8e  test    eax, eax
0x180054d90  jns     short loc_180054DD5
0x180054d92  mov     rax, [rbx]
0x180054d95  mov     rcx, rbx
0x180054d98  mov     rax, [rax+10h]
0x180054d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054da1  test    rax, rax
0x180054da4  jz      loc_1800557F4
0x180054daa  mov     rax, [rbx]
0x180054dad  mov     rcx, rbx
0x180054db0  mov     rax, [rax+10h]
0x180054db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054db9  xor     ecx, ecx
0x180054dbb  test    rax, rax
0x180054dbe  jz      loc_1800557EF
0x180054dc4  mov     [rsp+0E0h+var_B8], edi
0x180054dc8  mov     dword ptr [rsp+0E0h+var_C0], 5BFh
0x180054dd0  jmp     loc_1800557CB
0x180054dd5  test    r13d, r13d
0x180054dd8  jz      loc_180054E91
0x180054dde  mov     rax, [rbx]
0x180054de1  mov     rcx, rbx
0x180054de4  mov     rax, [rax+10h]
0x180054de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ded  test    rax, rax
0x180054df0  jz      short loc_180054E15
0x180054df2  mov     rax, [rbx]
0x180054df5  mov     rcx, rbx
0x180054df8  mov     rax, [rax+10h]
0x180054dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e01  mov     rcx, rax
0x180054e04  lea     r8, aDlptaskPrepari; "DlpTask: Preparing Files..."
0x180054e0b  mov     edx, 2
0x180054e10  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180054e15  mov     eax, dword ptr [rbp+57h+var_70]
0x180054e18  mov     r12, [rbp+57h+lpCriticalSection]
0x180054e1c  test    eax, eax
0x180054e1e  jz      short loc_180054E30
0x180054e20  mov     rcx, r12; lpCriticalSection
0x180054e23  call    cs:__imp_LeaveCriticalSection
0x180054e29  mov     dword ptr [rbp+57h+var_70], 0
0x180054e30  mov     rcx, r15; this
  ... truncated ...
```
