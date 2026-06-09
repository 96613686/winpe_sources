# _sensorControlThreadRoutine

- ea: `0x180047580`
- end: `0x1800488ca`
- name: `_sensorControlThreadRoutine`
- size: `4938`
- prototype: `__int64 __fastcall(struct thread_inside_functions *, CBiometricUnit **)`
- caller_count: `0`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ab6c`
- `0x18000b450`
- `0x18000e040`
- `0x18000f110`
- `0x180014938`
- `0x180016234`
- `0x18001741c`
- `0x180023d88`
- `0x180026494`
- `0x180028b20`
- `0x180028df4`
- `0x18002b01c`
- `0x18003a258`
- `0x18003cb9c`
- `0x1800471c4`
- `0x180047580`
- `0x180055878`
- `0x1800559c8`
- `0x18005dad0`
- `0x180060dc8`
- `0x180060f78`
- `0x180068f60`
- `0x180069330`
- `0x18006963c`
- `0x18006b0b5`
- `0x18006b0c1`
- `0x18006e4c4`
- `0x180078b88`
- `0x180078bb8`
- `0x180078d98`
- `0x18007a92c`
- `0x18007cb10`
- `0x18007cd50`
- `0x180081c00`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800479c0`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800479c0`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180047956`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180047956`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004807f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800482c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800484b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004807f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800482c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800484b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048001`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048001`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047fe0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180047fe0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180048204`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180048204`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180048038`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004827c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004846a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180048038`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004827c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004846a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180047ff3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800486a1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180047ff3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800486a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800479ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800479f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800479ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800479f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800479e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800479e7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800477ff`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800477ff`
- `ntdll!RtlIsMultiSessionSku` at `0x180047bc8`
- `ntdll!RtlIsMultiSessionSku` at `0x180047bc8`

## string_xrefs

- `0x180047f21`: `CBiometricUnit::OnActivationComplete`
- `0x1800475c8`: `_sensorControlThreadRoutine`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sensorControlThreadRoutine(struct thread_inside_functions *a1, CBiometricUnit **a2)
{
  struct thread_inside_functions *v3; // r13
  CBiometricUnit *v4; // rax
  struct CBiometricUnit *v5; // rcx
  void **v6; // rdx
  __int64 v7; // rax
  int v8; // eax
  CBiometricUnit *v9; // rdx
  unsigned __int32 *v10; // roff
  unsigned __int32 v11; // eax
  __int64 v12; // rcx
  unsigned __int32 v13; // ett
  CBiometricUnit *v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  HANDLE WaitableTimer; // r10
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // r8
  signed int LastError; // eax
  signed int v25; // eax
  int v26; // ebx
  __int64 v27; // rax
  __int64 (*v28)(void); // rax
  __int64 v29; // rax
  __int64 (*v30)(void); // rax
  __int64 v31; // rax
  __int64 (*v32)(void); // rax
  int v33; // eax
  _QWORD *v34; // rdi
  __int64 v35; // rax
  void (__fastcall *v36)(_QWORD *, _QWORD *, __int64); // rax
  __int64 v37; // rax
  void (__fastcall *v38)(_QWORD *, _QWORD *, __int64); // rax
  __int64 v39; // rax
  void (__fastcall *v40)(_QWORD *, CBiometricUnit *, __int64); // rax
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rbx
  char *v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  bool v47; // bl
  unsigned __int64 v48; // rdx
  void *Ptr; // rcx
  CBiometricUnit *v50; // r13
  unsigned __int64 v51; // rbx
  unsigned __int64 v52; // r14
  char *v53; // rdi
  size_t v54; // rbx
  __int64 v55; // rsi
  unsigned __int64 v56; // rdx
  size_t v57; // rcx
  _QWORD *v58; // rdi
  void *v59; // rax
  size_t v60; // rbx
  unsigned __int64 v61; // rdx
  void *v62; // rcx
  __int64 v63; // rdx
  CBiometricUnit *v64; // rdi
  int v65; // esi
  unsigned int v66; // edi
  CBiometricUnit *v67; // rdi
  RTL_SRWLOCK *v68; // rsi
  __int64 v69; // rdx
  signed __int32 v70; // eax
  signed __int32 v71; // ett
  __int64 v72; // rbx
  __int64 v73; // rax
  void (__fastcall *v74)(__int64, int *, __int64); // rax
  unsigned __int64 v75; // rdx
  void *v76; // rax
  int v77; // eax
  int v78; // esi
  int v79; // eax
  CBiometricUnit *v80; // rbx
  RTL_SRWLOCK *v81; // rsi
  __int64 v82; // rdx
  signed __int32 v83; // eax
  signed __int32 v84; // ett
  volatile signed __int32 *QuadPart; // rbx
  __int64 v86; // rdi
  __int64 v87; // rcx
  volatile signed __int32 *v88; // rdi
  volatile signed __int32 *v89; // rdi
  CBiometricUnit *v90; // rbx
  RTL_SRWLOCK *v91; // r14
  __int64 v92; // rdx
  signed __int32 v93; // eax
  signed __int32 v94; // ett
  LARGE_INTEGER v95; // rdi
  int v96; // eax
  __int64 v97; // rcx
  volatile signed __int32 *v98; // rdi
  volatile signed __int32 *v99; // rdi
  CBiometricUnit *v100; // rdx
  __int64 v101; // rcx
  bool v102; // zf
  __int64 v103; // rcx
  volatile signed __int32 *v104; // r15
  __int64 v105; // rax
  void (*v106)(void); // rax
  CBiometricUnit *v107; // rdx
  __int64 v108; // rax
  void (*v109)(void); // rax
  CBiometricUnit *v110; // rdx
  __int64 v111; // rax
  void (*v112)(void); // rax
  unsigned __int64 v113; // rdx
  void *v114; // rcx
  volatile signed __int32 *v115; // rbx
  int v117; // [rsp+40h] [rbp-C0h] BYREF
  bool v118; // [rsp+44h] [rbp-BCh] BYREF
  CBiometricUnit *v119[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v120; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v121; // [rsp+5Ch] [rbp-A4h] BYREF
  __int128 v122; // [rsp+60h] [rbp-A0h] BYREF
  int v123; // [rsp+70h] [rbp-90h] BYREF
  __int128 v124; // [rsp+78h] [rbp-88h] BYREF
  LARGE_INTEGER DueTime[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v126; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v127[2]; // [rsp+A0h] [rbp-60h] BYREF
  int *v128; // [rsp+B0h] [rbp-50h]
  void *v129[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v130; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v131; // [rsp+D0h] [rbp-30h]
  int v132; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v133; // [rsp+E4h] [rbp-1Ch]
  __int64 v134; // [rsp+ECh] [rbp-14h]
  __int64 v135; // [rsp+F4h] [rbp-Ch]
  __int64 v136; // [rsp+FCh] [rbp-4h]
  __int64 v137; // [rsp+104h] [rbp+4h]
  __int64 v138; // [rsp+10Ch] [rbp+Ch]
  __int64 v139; // [rsp+114h] [rbp+14h]
  __int64 v140; // [rsp+11Ch] [rbp+1Ch]
  __int64 v141; // [rsp+124h] [rbp+24h]
  int v142; // [rsp+12Ch] [rbp+2Ch]
  _BYTE v143[152]; // [rsp+130h] [rbp+30h] BYREF
  void *v144; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned __int64 v145; // [rsp+1D8h] [rbp+D8h]
  unsigned __int64 v146; // [rsp+1E0h] [rbp+E0h]
  int v147; // [rsp+1E8h] [rbp+E8h]
  int v148; // [rsp+1ECh] [rbp+ECh]
  int v149; // [rsp+298h] [rbp+198h]
  int v150; // [rsp+2A0h] [rbp+1A0h]
  struct _EVENT_DATA_DESCRIPTOR UserData[2]; // [rsp+340h] [rbp+240h] BYREF
  int *v152; // [rsp+360h] [rbp+260h]
  __int64 v153; // [rsp+368h] [rbp+268h]
  void **v154; // [rsp+370h] [rbp+270h]
  int v155; // [rsp+378h] [rbp+278h]
  int v156; // [rsp+37Ch] [rbp+27Ch]
  char EventDescriptor[37]; // [rsp+380h] [rbp+280h] BYREF
  char v158[32]; // [rsp+3A8h] [rbp+2A8h] BYREF

  v3 = a1;
  *(_QWORD *)&v122 = a1;
  v117 = 0;
  v123 = 0;
  strcpy(v158, "_sensorControlThreadRoutine");
  v127[0] = v158;
  v127[1] = &v123;
  v128 = &v117;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_ssd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      (unsigned int)&WPP_566f084f5ddc338ee0719b550e217f05_Traceguids,
      (_DWORD)WPP_pszIndent,
      (__int64)v158,
      *v128);
  }
  v123 = 1;
  v126 = v127;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *(_OWORD *)v119 = 0;
  v4 = a2[1];
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)v4 + 2);
  v119[0] = *a2;
  v119[1] = a2[1];
  *((_DWORD *)v119[0] + 744) = 1;
  v5 = v119[0];
  if ( !v119[0] )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v5 = v119[0];
  }
  *(_OWORD *)v129 = 0;
  v130 = 0;
  v131 = 7;
  LOWORD(v129[0]) = 0;
  CBiometricUnit::DisplayName(v5);
  if ( (unsigned int)dword_18010F170 > 4 )
  {
    v6 = v129;
    if ( v131 > 7 )
      v6 = (void **)v129[0];
    v120 = *((_DWORD *)v119[0] + 20);
    if ( v6 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *((_WORD *)v6 + v7) );
      v8 = 2 * v7 + 2;
    }
    else
    {
      v6 = (void **)byte_1800DC1E0;
      v8 = 2;
    }
    v154 = v6;
    v155 = v8;
    v156 = 0;
    v152 = &v120;
    v153 = 4;
    *(_DWORD *)EventDescriptor = 184549376;
    *(_DWORD *)&EventDescriptor[4] = 4;
    *(_QWORD *)&EventDescriptor[8] = 0;
    UserData[0].Ptr = (ULONGLONG)off_18010F178;
    *(_QWORD *)&UserData[0].Size = *(unsigned __int16 *)off_18010F178 | 0x200000000LL;
    UserData[1].Ptr = (ULONGLONG)&unk_1800ED868;
    *(_QWORD *)&UserData[1].Size = 0x100000039LL;
    v121 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)EventDescriptor, 0, 0, 4u, UserData);
  }
  v9 = v119[0];
  v10 = (unsigned __int32 *)((char *)v119[0] + 40);
  _m_prefetchw((char *)v119[0] + 40);
  v11 = *v10;
  do
  {
    v12 = v11;
    v13 = v11;
    v11 = _InterlockedCompareExchange((volatile signed __int32 *)v9 + 10, v11, v11);
  }
  while ( v13 != v11 );
  if ( v11 )
  {
    v117 = -2147467259;
    goto LABEL_66;
  }
  if ( v117 >= 0 )
  {
    v14 = v119[0];
    v121 = 0;
    v120 = 0;
    strcpy((char *)UserData, "CBiometricUnit::StartTimer");
    *(_QWORD *)EventDescriptor = UserData;
    *(_QWORD *)&EventDescriptor[8] = &v120;
    *(_QWORD *)&EventDescriptor[16] = &v121;
    *(CBiometricUnit **)&EventDescriptor[24] = v119[0];
    WppTraceIndent(v12, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_ssdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        **(_DWORD **)&EventDescriptor[16],
        (_DWORD)WPP_pszIndent,
        (__int64)UserData,
        **(_DWORD **)&EventDescriptor[16],
        *(_DWORD *)(*(_QWORD *)&EventDescriptor[24] + 80LL));
    }
    v120 = 1;
    *(_QWORD *)&v124 = EventDescriptor;
    CBiometricUnit::StopTimer(v14);
    v15 = *((_QWORD *)v14 + 344);
    if ( *(_DWORD *)(v15 + 68) )
    {
      if ( *(_DWORD *)(v15 + 72) )
        v16 = *(_QWORD *)(v15 + 40);
      else
        v16 = *(_QWORD *)(v15 + 8);
      v17 = *(_QWORD *)(8LL * *(_QWORD *)(v15 + 80) + v16);
    }
    else
    {
      v17 = 0;
    }
    if ( *(_DWORD *)(v17 + 124) )
    {
      WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
      *((_QWORD *)v14 + 353) = WaitableTimer;
      if ( WaitableTimer )
      {
        v19 = *((_QWORD *)v14 + 344);
        if ( *(_DWORD *)(v19 + 68) )
        {
          v20 = *(_QWORD *)(v19 + 80);
          if ( *(_DWORD *)(v19 + 72) )
            v21 = *(_QWORD *)(v19 + 40);
          else
            v21 = *(_QWORD *)(v19 + 8);
          v22 = *(_QWORD *)(v21 + 8 * v20);
        }
        else
        {
          v22 = 0;
        }
        v23 = *(int *)(v22 + 124);
        DueTime[0].QuadPart = -10000 * v23;
        if ( !SetWaitableTimer(WaitableTimer, DueTime, v23, 0, 0, 0) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v121 = LastError;
          CloseHandle(*((HANDLE *)v14 + 353));
          *((_QWORD *)v14 + 353) = 0;
        }
      }
      else
      {
        v25 = GetLastError();
        if ( v25 > 0 )
          v25 = (unsigned __int16)v25 | 0x80070000;
        v121 = v25;
      }
    }
    v26 = v121;
    WppTraceUnwinder__lambda_67fc72e7a70e3ae32856a086953e5605____::_WppTraceUnwinder__lambda_67fc72e7a70e3ae32856a086953e5605____(&v124);
    v117 = v26;
    if ( v26 >= 0 )
    {
      *((_DWORD *)v119[0] + 744) = 2;
      v12 = *((_QWORD *)v119[0] + 338) + 16LL;
      if ( *((_QWORD *)v119[0] + 338) != -16 )
      {
        v27 = *(_QWORD *)(*((_QWORD *)v119[0] + 338) + 56LL);
        if ( v27 )
        {
          v28 = *(__int64 (**)(void))(v27 + 208);
          if ( !v28 )
            goto LABEL_62;
          v117 = v28();
          if ( v117 < 0 )
            goto LABEL_66;
          *((_DWORD *)v119[0] + 744) = 3;
          v12 = *((_QWORD *)v119[0] + 338) + 16LL;
          if ( *((_QWORD *)v119[0] + 338) != -16 )
          {
            v29 = *(_QWORD *)(*((_QWORD *)v119[0] + 338) + 48LL);
            if ( v29 )
            {
              v30 = *(__int64 (**)(void))(v29 + 232);
              if ( !v30 )
                goto LABEL_62;
              v117 = v30();
              if ( v117 < 0 )
                goto LABEL_66;
              *((_DWORD *)v119[0] + 744) = 4;
              v12 = *((_QWORD *)v119[0] + 338) + 16LL;
              if ( *((_QWORD *)v119[0] + 338) != -16 )
              {
                v31 = *(_QWORD *)(*((_QWORD *)v119[0] + 338) + 40LL);
                if ( v31 )
                {
                  v32 = *(__int64 (**)(void))(v31 + 176);
                  if ( v32 )
                  {
                    v33 = v32();
                    goto LABEL_65;
                  }
LABEL_62:
                  v33 = -2147467263;
LABEL_65:
                  v117 = v33;
                  goto LABEL_66;
                }
              }
            }
          }
        }
      }
      v33 = -2147467261;
      goto LABEL_65;
    }
  }
LABEL_66:
  v34 = (_QWORD *)*((_QWORD *)v119[0] + 338);
  if ( v34 != (_QWORD *)-16LL )
  {
    v35 = v34[5];
    if ( v35 )
    {
      if ( v34 != (_QWORD *)-1080LL )
      {
        v36 = *(void (__fastcall **)(_QWORD *, _QWORD *, __int64))(v35 + 192);
        if ( v36 )
          v36(v34 + 2, v34 + 135, 1080);
      }
    }
    v37 = v34[6];
    if ( v37 )
    {
      if ( v34 != (_QWORD *)-2160LL )
      {
        v38 = *(void (__fastcall **)(_QWORD *, _QWORD *, __int64))(v37 + 248);
        if ( v38 )
          v38(v34 + 2, v34 + 270, 36);
      }
    }
    v9 = (CBiometricUnit *)((char *)v34 + 2196);
    v39 = v34[7];
    if ( v39 )
    {
      if ( v34 != (_QWORD *)-2196LL )
      {
        v40 = *(void (__fastcall **)(_QWORD *, CBiometricUnit *, __int64))(v39 + 224);
        if ( v40 )
          v40(v34 + 2, v9, 12);
      }
    }
  }
  if ( v117 >= 0 )
  {
    if ( !(unsigned __int8)RtlIsMultiSessionSku(v12, v9) )
      v117 = CBiometricUnit::ProvisionAuthValue(v119[0]);
    if ( v117 >= 0 )
    {
      v12 = (__int64)v119[0];
      if ( (*((_DWORD *)v119[0] + 24) & 0x200) != 0 )
      {
        if ( *((_QWORD *)v119[0] + 365) )
        {
          v118 = 0;
          v117 = CBiometricUnit::EstablishSecureConnection(v119[0], &v118);
          v41 = *((_QWORD *)v119[0] + 344);
          if ( *(_DWORD *)(v41 + 68) )
          {
            if ( *(_DWORD *)(v41 + 72) )
              v42 = *(_QWORD *)(v41 + 40);
            else
              v42 = *(_QWORD *)(v41 + 8);
            v43 = *(_QWORD *)(8LL * *(_QWORD *)(v41 + 80) + v42);
          }
          else
          {
            v43 = 0;
          }
          v44 = (char *)v119[0] + 100;
          memset(UserData, 0, sizeof(UserData));
          v45 = -1;
          do
            ++v45;
          while ( *(_WORD *)&v44[2 * v45] );
          std::wstring::_Construct<1,unsigned short const *>(UserData, v44, v45);
          v46 = v43;
          v47 = v118;
          CBioTraceLogging::OnSecureConnection((unsigned int)v117, v118, UserData, v46);
          if ( *(_QWORD *)&UserData[1].Size > 7u )
          {
            v48 = 2LL * *(_QWORD *)&UserData[1].Size + 2;
            if ( v48 < 0x1000 )
            {
              Ptr = (void *)UserData[0].Ptr;
            }
            else
            {
              Ptr = *(void **)(UserData[0].Ptr - 8);
              if ( UserData[0].Ptr - (unsigned __int64)Ptr - 8 > 0x1F )
                __fastfail(5u);
              v48 = 2LL * *(_QWORD *)&UserData[1].Size + 41;
            }
            operator delete(Ptr, v48);
          }
          CEtwEvent::CEtwEvent((CEtwEvent *)v143);
          v50 = v119[0];
          if ( !v119[0] )
            goto LABEL_131;
          CBiometricUnit::DisplayName(v119[0]);
          v150 = *((_DWORD *)v50 + 22);
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
            goto LABEL_131;
          v51 = -1;
          do
            ++v51;
          while ( *((_WORD *)v50 + v51 + 50) );
          v52 = v146;
          if ( v51 <= v146 )
          {
            v53 = (char *)&v144;
            if ( v146 > 7 )
              v53 = (char *)v144;
            v145 = v51;
            v54 = 2 * v51;
            memmove_0(v53, (char *)v50 + 100, v54);
            *(_WORD *)&v53[v54] = 0;
            goto LABEL_130;
          }
          v55 = 0x7FFFFFFFFFFFFFFELL;
          if ( v51 > 0x7FFFFFFFFFFFFFFELL )
            std::_Xlen_string();
          if ( (v51 | 7) > 0x7FFFFFFFFFFFFFFELL || (v56 = v146 >> 1, v146 > 0x7FFFFFFFFFFFFFFELL - (v146 >> 1)) )
          {
            v57 = -2;
          }
          else
          {
            v55 = v51 | 7;
            if ( (v51 | 7) < v146 + v56 )
              v55 = v146 + v56;
            if ( (unsigned __int64)(v55 + 1) > 0x7FFFFFFFFFFFFFFFLL )
              goto LABEL_271;
            v57 = 2 * (v55 + 1);
            if ( !v57 )
            {
              v58 = 0;
              goto LABEL_122;
            }
          }
          if ( v57 < 0x1000 )
          {
            v58 = operator new(v57);
            goto LABEL_122;
          }
          if ( v57 + 39 >= v57 )
          {
            v59 = operator new(v57 + 39);
            if ( !v59 )
              goto LABEL_126;
            v58 = (_QWORD *)(((unsigned __int64)v59 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *(v58 - 1) = v59;
LABEL_122:
            v145 = v51;
            v146 = v55;
            v60 = 2 * v51;
            memcpy_0(v58, (char *)v50 + 100, v60);
            *(_WORD *)((char *)v58 + v60) = 0;
            if ( v52 <= 7 )
            {
LABEL_129:
              v144 = v58;
LABEL_130:
              v147 = *((_DWORD *)v50 + 746);
              v148 = *(_DWORD *)(*((_QWORD *)v50 + 344) + 96LL);
              v47 = v118;
LABEL_131:
              v149 = v117;
              if ( v117 < 0 )
              {
                v63 = 1609;
              }
              else if ( v47 )
              {
                v63 = 1608;
              }
              else
              {
                v63 = 1607;
              }
              CEtwEvent::Write(v143, v63, 1);
              CEtwEvent::~CEtwEvent((CEtwEvent *)v143);
              v3 = (struct thread_inside_functions *)v122;
              goto LABEL_137;
            }
            v61 = 2 * v52 + 2;
            if ( v61 < 0x1000 )
            {
              v62 = v144;
              goto LABEL_128;
            }
            v62 = (void *)*((_QWORD *)v144 - 1);
            if ( (unsigned __int64)((_BYTE *)v144 - (_BYTE *)v62 - 8) <= 0x1F )
            {
              v61 = 2 * v52 + 41;
LABEL_128:
              operator delete(v62, v61);
              goto LABEL_129;
            }
LABEL_126:
            __fastfail(5u);
          }
LABEL_271:
          std::_Throw_bad_array_new_length();
        }
      }
    }
  }
LABEL_137:
  v64 = v119[0];
  v65 = v117;
  v120 = 0;
  strcpy(EventDescriptor, "CBiometricUnit::OnActivationComplete");
  UserData[0].Ptr = (ULONGLONG)EventDescriptor;
  *(_QWORD *)&UserData[0].Size = &v120;
  UserData[1].Ptr = (ULONGLONG)v119[0];
  WppTraceIndent(v12, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_ssd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      (unsigned int)&WPP_566f084f5ddc338ee0719b550e217f05_Traceguids,
      (_DWORD)WPP_pszIndent,
      (__int64)EventDescriptor,
      *(_DWORD *)(UserData[1].Ptr + 80));
  }
  v120 = 1;
  *(_QWORD *)&v122 = UserData;
  AcquireSRWLockExclusive((PSRWLOCK)v64 + 1);
  *((_DWORD *)v64 + 714) = v65;
  SetEvent(*((HANDLE *)v64 + 356));
  if ( v64 != (CBiometricUnit *)-8LL )
    ReleaseSRWLockExclusive((PSRWLOCK)v64 + 1);
  WppTraceUnwinder__lambda_551466ffac7ad21d784a5e58d7a313e0____::_WppTraceUnwinder__lambda_551466ffac7ad21d784a5e58d7a313e0____(&v122);
  v66 = v117;
  if ( v117 >= 0 )
  {
    *((_DWORD *)v119[0] + 744) = 5;
    v67 = v119[0];
    v68 = (RTL_SRWLOCK *)((char *)v119[0] + 8);
    AcquireSRWLockShared((PSRWLOCK)v119[0] + 1);
    v124 = 0;
    v69 = *((_QWORD *)v67 + 9);
    if ( v69 && (v70 = *(_DWORD *)(v69 + 8)) != 0 )
    {
      while ( 1 )
      {
        v71 = v70;
        v70 = _InterlockedCompareExchange((volatile signed __int32 *)(v69 + 8), v70 + 1, v70);
        if ( v71 == v70 )
          break;
        if ( !v70 )
          goto LABEL_148;
      }
      v72 = *((_QWORD *)v67 + 8);
      v124 = *((_OWORD *)v67 + 4);
    }
    else
    {
LABEL_148:
      v72 = v124;
    }
    if ( v68 )
      ReleaseSRWLockShared(v68);
    if ( v72 && *(_DWORD *)(v72 + 32) == 1 && (*(_BYTE *)(*((_QWORD *)v119[0] + 338) + 2160LL) & 2) != 0 )
    {
      memset(UserData, 0, 24);
      v117 = CAccountManager::EnumAccountPolicies(*((_DWORD *)v119[0] + 22));
      if ( v117 < 0 )
      {
        v117 = 0;
        v133 = 0;
        v134 = 0;
        v135 = 0;
        v136 = 0;
        v137 = 0;
        v138 = 0;
        v139 = 0;
        v140 = 0;
        v141 = 0;
        v132 = 1;
        v142 = 0;
        if ( *((_QWORD *)v119[0] + 338) != -16 )
        {
          v73 = *(_QWORD *)(*((_QWORD *)v119[0] + 338) + 48LL);
          if ( v73 )
          {
            v74 = *(void (__fastcall **)(__int64, int *, __int64))(v73 + 312);
            if ( v74 )
              v74(*((_QWORD *)v119[0] + 338) + 16LL, &v132, 1);
          }
        }
      }
      else
      {
        WbioEngineSetAccountPolicy(
          *((_QWORD *)v119[0] + 338) + 16LL,
          UserData[0].Ptr,
          0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*(_QWORD *)&UserData[0].Size - UserData[0].Ptr) >> 4));
      }
      if ( UserData[0].Ptr )
      {
        v75 = 16 * ((__int64)(UserData[1].Ptr - UserData[0].Ptr) >> 4);
        if ( v75 < 0x1000 )
        {
          v76 = (void *)UserData[0].Ptr;
        }
        else
        {
          v76 = *(void **)(UserData[0].Ptr - 8);
          if ( UserData[0].Ptr - (unsigned __int64)v76 - 8 > 0x1F )
            __fastfail(5u);
          v75 += 39LL;
        }
        operator delete(v76, v75);
      }
    }
    *((_DWORD *)v119[0] + 744) = 6;
    ResetEvent(*((HANDLE *)v119[0] + 350));
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            do
            {
              if ( _InterlockedCompareExchange((volatile signed __int32 *)v3 + 26, 2, 2) != 2 )
              {
                SetEvent(*((HANDLE *)v119[0] + 350));
                CBiometricUnit::CleanUpBindings(v119[0], 1);
                *((_DWORD *)v119[0] + 744) = 7;
                v100 = v119[0];
                v101 = *((_QWORD *)v119[0] + 338);
                v102 = v101 == -16;
                v103 = v101 + 16;
                v104 = (volatile signed __int32 *)*((_QWORD *)&v124 + 1);
                if ( !v102 )
                {
                  v105 = *(_QWORD *)(v103 + 24);
                  if ( v105 )
                  {
                    v106 = *(void (**)(void))(v105 + 184);
                    if ( v106 )
                    {
                      v106();
                      v100 = v119[0];
                    }
                  }
                }
                *((_DWORD *)v100 + 744) = 8;
                v107 = v119[0];
                if ( *((_QWORD *)v119[0] + 338) != -16 )
                {
                  v108 = *(_QWORD *)(*((_QWORD *)v119[0] + 338) + 48LL);
                  if ( v108 )
                  {
                    v109 = *(void (**)(void))(v108 + 240);
                    if ( v109 )
                    {
                      v109();
                      v107 = v119[0];
                    }
                  }
                }
                *((_DWORD *)v107 + 744) = 9;
                v110 = v119[0];
                if ( *((_QWORD *)v119[0] + 338) != -16 )
                {
                  v111 = *(_QWORD *)(*((_QWORD *)v119[0] + 338) + 56LL);
                  if ( v111 )
                  {
                    v112 = *(void (**)(void))(v111 + 216);
                    if ( v112 )
                    {
                      v112();
                      v110 = v119[0];
                    }
                  }
                }
                *((_DWORD *)v110 + 744) = 10;
                *(_DWORD *)(*((_QWORD *)v119[0] + 358) + 28LL) = 0;
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v119[0] + 358) + 24LL))(*((_QWORD *)v119[0] + 358));
                CBiometricUnit::StopTimer(v119[0]);
                v66 = v117;
                if ( v104 )
                {
                  if ( _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v104)(v104);
                    if ( _InterlockedExchangeAdd(v104 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v104 + 8LL))(v104);
                  }
                }
                goto LABEL_259;
              }
              v77 = CBiometricUnit::WaitForNotification(v119[0], v3);
              v78 = v77;
            }
            while ( v77 == 10 || v77 == 2 );
            if ( v77 != 4 )
              break;
            v79 = *((_DWORD *)v119[0] + 24);
            if ( (v79 & 0x400) != 0 && (v79 & 0x100) == 0 )
              CBiometricUnit::SuspendAndWaitForPlatformResume(v119[0], v3);
          }
          if ( (unsigned int)(v77 - 6) <= 1 )
          {
            v90 = v119[0];
            v91 = (RTL_SRWLOCK *)((char *)v119[0] + 8);
            AcquireSRWLockShared((PSRWLOCK)v119[0] + 1);
            *(_OWORD *)&DueTime[0].LowPart = 0;
            v92 = *((_QWORD *)v90 + 7);
            if ( v92 && (v93 = *(_DWORD *)(v92 + 8)) != 0 )
            {
              while ( 1 )
              {
                v94 = v93;
                v93 = _InterlockedCompareExchange((volatile signed __int32 *)(v92 + 8), v93 + 1, v93);
                if ( v94 == v93 )
                  break;
                if ( !v93 )
                  goto LABEL_212;
              }
              v95 = *(LARGE_INTEGER *)((char *)v90 + 48);
              DueTime[0] = v95;
              QuadPart = (volatile signed __int32 *)*((_QWORD *)v90 + 7);
              DueTime[1].QuadPart = (LONGLONG)QuadPart;
            }
            else
            {
LABEL_212:
              v95 = DueTime[0];
              QuadPart = (volatile signed __int32 *)DueTime[1].QuadPart;
            }
            if ( v91 )
              ReleaseSRWLockShared(v91);
            if ( v95.QuadPart )
            {
              v122 = 0;
              CBiometricServiceProvider::SelectWorkItem(
                v95.LowPart,
                (unsigned int)EventDescriptor,
                (unsigned int)v119,
                (unsigned int)&v122,
                v78);
              if ( *(_QWORD *)EventDescriptor )
              {
                v96 = (*(__int64 (__fastcall **)(_QWORD, CBiometricUnit **, struct thread_inside_functions *))(**(_QWORD **)EventDescriptor + 8LL))(
                        *(_QWORD *)EventDescriptor,
                        v119,
                        v3);
                if ( v96 == 2 )
                {
                  WppTraceIndent(v97, 2);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  {
                    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_566f084f5ddc338ee0719b550e217f05_Traceguids);
                  }
                }
                else if ( v96 == 4 )
                {
                  WppTraceIndent(v97, 2);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  {
                    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_566f084f5ddc338ee0719b550e217f05_Traceguids);
                  }
                  CBiometricUnit::OnSpecificWorkRequest(v119[0]);
                }
              }
              v98 = *(volatile signed __int32 **)&EventDescriptor[8];
              if ( *(_QWORD *)&EventDescriptor[8] )
              {
                if ( _InterlockedExchangeAdd(
                       (volatile signed __int32 *)(*(_QWORD *)&EventDescriptor[8] + 8LL),
                       0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v98)(v98);
                  if ( _InterlockedExchangeAdd(v98 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v98 + 8LL))(v98);
                }
              }
              if ( (_QWORD)v122 )
                _InterlockedAnd((volatile signed __int32 *)(v122 + 204), 0);
              v99 = (volatile signed __int32 *)*((_QWORD *)&v122 + 1);
              if ( *((_QWORD *)&v122 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v122 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v99)(v99);
                  if ( _InterlockedExchangeAdd(v99 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v99 + 8LL))(v99);
                }
              }
            }
            goto LABEL_239;
          }
          if ( v77 == 8 )
            break;
          if ( v77 == 3 )
            CBiometricUnit::CleanUpBindings(v119[0], 0);
        }
        v80 = v119[0];
        v81 = (RTL_SRWLOCK *)((char *)v119[0] + 8);
        AcquireSRWLockShared((PSRWLOCK)v119[0] + 1);
        v122 = 0;
        v82 = *((_QWORD *)v80 + 7);
        if ( v82 && (v83 = *(_DWORD *)(v82 + 8)) != 0 )
        {
          while ( 1 )
          {
            v84 = v83;
            v83 = _InterlockedCompareExchange((volatile signed __int32 *)(v82 + 8), v83 + 1, v83);
            if ( v84 == v83 )
              break;
            if ( !v83 )
              goto LABEL_182;
          }
          v86 = *((_QWORD *)v80 + 6);
          *(_QWORD *)&v122 = v86;
          QuadPart = (volatile signed __int32 *)*((_QWORD *)v80 + 7);
          *((_QWORD *)&v122 + 1) = QuadPart;
        }
        else
        {
LABEL_182:
          QuadPart = (volatile signed __int32 *)*((_QWORD *)&v122 + 1);
          v86 = v122;
        }
        if ( v81 )
          ReleaseSRWLockShared(v81);
        if ( v86 )
          break;
LABEL_239:
        if ( QuadPart )
        {
          if ( _InterlockedExchangeAdd(QuadPart + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))QuadPart)(QuadPart);
            if ( _InterlockedExchangeAdd(QuadPart + 3, 0xFFFFFFFF) == 1 )
              goto LABEL_199;
          }
        }
      }
      CBiometricServiceProvider::GetScheduledWorkItem(v86, UserData, v119);
      if ( !UserData[0].Ptr
        || (*(unsigned int (__fastcall **)(ULONGLONG, CBiometricUnit **, struct thread_inside_functions *))(*(_QWORD *)UserData[0].Ptr + 8LL))(
             UserData[0].Ptr,
             v119,
             v3) != 2 )
      {
        v89 = *(volatile signed __int32 **)&UserData[0].Size;
        if ( *(_QWORD *)&UserData[0].Size )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&UserData[0].Size + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v89)(v89);
            if ( _InterlockedExchangeAdd(v89 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v89 + 8LL))(v89);
          }
        }
        goto LABEL_239;
      }
      WppTraceIndent(v87, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_566f084f5ddc338ee0719b550e217f05_Traceguids);
      }
      v88 = *(volatile signed __int32 **)&UserData[0].Size;
      if ( *(_QWORD *)&UserData[0].Size )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&UserData[0].Size + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v88)(v88);
          if ( _InterlockedExchangeAdd(v88 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v88 + 8LL))(v88);
        }
      }
      if ( QuadPart )
      {
        if ( _InterlockedExchangeAdd(QuadPart + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))QuadPart)(QuadPart);
          if ( _InterlockedExchangeAdd(QuadPart + 3, 0xFFFFFFFF) == 1 )
LABEL_199:
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)QuadPart + 8LL))(QuadPart);
        }
      }
    }
  }
LABEL_259:
  if ( v131 > 7 )
  {
    v113 = 2 * v131 + 2;
    if ( v113 < 0x1000 )
    {
      v114 = v129[0];
    }
    else
    {
      v114 = (void *)*((_QWORD *)v129[0] - 1);
      if ( (unsigned __int64)((char *)v129[0] - (char *)v114 - 8) > 0x1F )
        __fastfail(5u);
      v113 = 2 * v131 + 41;
    }
    operator delete(v114, v113);
  }
  LOWORD(v129[0]) = 0;
  v131 = 7;
  v130 = 0;
  v115 = (volatile signed __int32 *)v119[1];
  if ( v119[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v119[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v115)(v115);
      if ( _InterlockedExchangeAdd(v115 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v115 + 8LL))(v115);
    }
  }
  WppTraceUnwinder__lambda_e2e3c5cfb3336bb231e80068add62a10____::_WppTraceUnwinder__lambda_e2e3c5cfb3336bb231e80068add62a10____(&v126);
  return v66;
}

```

## disassembly

```asm
0x180047580  mov     [rsp-8+arg_10], rbx
0x180047585  push    rbp
0x180047586  push    rsi
0x180047587  push    rdi
0x180047588  push    r12
0x18004758a  push    r13
0x18004758c  push    r14
0x18004758e  push    r15
0x180047590  lea     rbp, [rsp-2D0h]
0x180047598  sub     rsp, 3D0h
0x18004759f  mov     rax, cs:__security_cookie
0x1800475a6  xor     rax, rsp
0x1800475a9  mov     [rbp+300h+var_38], rax
0x1800475b0  mov     rbx, rdx
0x1800475b3  mov     r13, rcx
0x1800475b6  mov     qword ptr [rsp+400h+var_3A0], rcx
0x1800475bb  xor     r14d, r14d
0x1800475be  mov     [rsp+400h+var_3C0], r14d
0x1800475c3  mov     [rsp+400h+var_390], r14d
0x1800475c8  movups  xmm0, xmmword ptr cs:aSensorcontrolt_0; "_sensorControlThreadRoutine"
0x1800475cf  movups  xmmword ptr [rbp+300h+var_58], xmm0
0x1800475d6  movups  xmm1, xmmword ptr cs:aSensorcontrolt_0+0Ch; "olThreadRoutine"
0x1800475dd  movups  xmmword ptr [rbp+300h+var_58+0Ch], xmm1
0x1800475e4  lea     rax, [rbp+300h+var_58]
0x1800475eb  mov     [rbp+300h+var_360], rax
0x1800475ef  lea     rax, [rsp+400h+var_390]
0x1800475f4  mov     [rbp+300h+var_358], rax
0x1800475f8  lea     rax, [rsp+400h+var_3C0]
0x1800475fd  mov     [rbp+300h+var_350], rax
0x180047601  xor     edx, edx
0x180047603  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180047608  lea     r15, WPP_GLOBAL_Control
0x18004760f  mov     rcx, cs:WPP_GLOBAL_Control
0x180047616  cmp     rcx, r15
0x180047619  jz      short loc_18004765B
0x18004761b  test    byte ptr [rcx+1Ch], 2
0x18004761f  jz      short loc_18004765B
0x180047621  cmp     byte ptr [rcx+19h], 5
0x180047625  jb      short loc_18004765B
0x180047627  mov     edx, 2Bh ; '+'
0x18004762c  mov     rax, [rbp+300h+var_350]
0x180047630  mov     r8d, [rax]
0x180047633  mov     dword ptr [rsp+400h+UserData], r8d
0x180047638  lea     rax, [rbp+300h+var_58]
0x18004763f  mov     qword ptr [rsp+400h+UserDataCount], rax
0x180047644  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18004764b  lea     r8, WPP_566f084f5ddc338ee0719b550e217f05_Traceguids
0x180047652  mov     rcx, [rcx+10h]
0x180047656  call    WPP_SF_ssd
0x18004765b  mov     [rsp+400h+var_390], 1
0x180047663  lea     rax, [rbp+300h+var_360]
0x180047667  mov     [rbp+300h+var_368], rax
0x18004766b  test    rbx, rbx
0x18004766e  jnz     short loc_180047675
0x180047670  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180047675  xorps   xmm0, xmm0
0x180047678  movdqu  xmmword ptr [rsp+400h+var_3B8], xmm0
0x18004767e  mov     rax, [rbx+8]
0x180047682  test    rax, rax
0x180047685  jz      short loc_18004768B
0x180047687  lock inc dword ptr [rax+8]
0x18004768b  mov     rcx, [rbx]
0x18004768e  mov     [rsp+400h+var_3B8], rcx
0x180047693  mov     rax, [rbx+8]
0x180047697  mov     [rsp+400h+var_3B8+8], rax
0x18004769c  mov     dword ptr [rcx+0BA0h], 1
0x1800476a6  mov     rcx, [rsp+400h+var_3B8]
0x1800476ab  test    rcx, rcx
0x1800476ae  jnz     short loc_1800476BA
0x1800476b0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800476b5  mov     rcx, [rsp+400h+var_3B8]; struct CBiometricUnit *
0x1800476ba  xorps   xmm0, xmm0
0x1800476bd  movups  xmmword ptr [rbp+300h+var_348], xmm0
0x1800476c1  mov     [rbp+300h+var_338], r14
0x1800476c5  mov     [rbp+300h+var_330], 7
0x1800476cd  mov     word ptr [rbp+300h+var_348], r14w
0x1800476d2  lea     rdx, [rbp+300h+var_348]
0x1800476d6  call    ?DisplayName@CBiometricUnit@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CBiometricUnit::DisplayName(std::wstring &)
0x1800476db  mov     eax, cs:dword_18010F170
0x1800476e1  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800476e8  cmp     eax, 4
0x1800476eb  jbe     loc_180047805
0x1800476f1  lea     rdx, [rbp+300h+var_348]
0x1800476f5  cmp     [rbp+300h+var_330], 7
0x1800476fa  cmova   rdx, [rbp+300h+var_348]
0x1800476ff  mov     rax, [rsp+400h+var_3B8]
0x180047704  mov     ecx, [rax+50h]
0x180047707  mov     [rsp+400h+var_3A8], ecx
0x18004770b  test    rdx, rdx
0x18004770e  jz      short loc_180047727
0x180047710  mov     rax, r12
0x180047713  lea     rax, [rax+1]
0x180047717  cmp     word ptr [rdx+rax*2], 0
0x18004771c  jnz     short loc_180047713
0x18004771e  lea     eax, ds:2[rax*2]
0x180047725  jmp     short loc_180047733
0x180047727  lea     rdx, byte_1800DC1E0
0x18004772e  mov     eax, 2
0x180047733  mov     [rbp+300h+var_90], rdx
0x18004773a  mov     [rbp+300h+var_88], eax
0x180047740  mov     [rbp+300h+var_84], r14d
0x180047747  lea     rax, [rsp+400h+var_3A8]
0x18004774c  mov     [rbp+300h+var_A0], rax
0x180047753  mov     [rbp+300h+var_98], 4
0x18004775e  mov     dword ptr [rbp+300h+EventDescriptor.Id], 0B000000h
0x180047768  movzx   eax, cs:word_1800ED85E
0x18004776f  mov     dword ptr [rbp+300h+EventDescriptor.Level], eax
0x180047775  mov     [rbp+300h+EventDescriptor.Keyword], r14
0x18004777c  mov     rax, cs:off_18010F178
0x180047783  mov     [rbp+300h+var_C0.Ptr], rax
0x18004778a  movzx   eax, word ptr [rax]
0x18004778d  mov     [rbp+300h+var_C0.Size], eax
0x180047793  mov     dword ptr [rbp+300h+var_C0.0Ch], 2
0x18004779d  lea     rax, unk_1800ED868
0x1800477a4  mov     [rbp+300h+var_B0], rax
0x1800477ab  mov     dword ptr [rbp+300h+var_A8], 39h ; '9'
0x1800477b5  mov     dword ptr [rbp+300h+var_A8+4], 1
0x1800477bf  lea     rax, _TraceLoggingMetadataEnd
0x1800477c6  lea     rcx, _TraceLoggingMetadata
0x1800477cd  sub     eax, ecx
0x1800477cf  mov     [rsp+400h+var_3A4], eax
0x1800477d3  mov     eax, [rsp+400h+var_3A4]
0x1800477d7  lea     rax, [rbp+300h+var_C0]
0x1800477de  mov     [rsp+400h+UserData], rax; UserData
0x1800477e3  mov     [rsp+400h+UserDataCount], 4; UserDataCount
0x1800477eb  xor     r9d, r9d; RelatedActivityId
0x1800477ee  xor     r8d, r8d; ActivityId
0x1800477f1  lea     rdx, [rbp+300h+EventDescriptor]; EventDescriptor
0x1800477f8  mov     rcx, cs:RegHandle; RegHandle
0x1800477ff  call    cs:__imp_EventWriteTransfer
0x180047805  mov     rdx, [rsp+400h+var_3B8]
0x18004780a  prefetchw byte ptr [rdx+28h]
0x18004780e  mov     eax, [rdx+28h]
0x180047811  mov     ecx, eax
0x180047813  lock cmpxchg [rdx+28h], ecx
0x180047818  jnz     short loc_180047811
0x18004781a  test    eax, eax
0x18004781c  jz      short loc_18004782B
0x18004781e  mov     [rsp+400h+var_3C0], 80004005h
0x180047826  jmp     loc_180047B09
0x18004782b  cmp     [rsp+400h+var_3C0], 0
0x180047830  jl      loc_180047B09
0x180047836  mov     rbx, [rsp+400h+var_3B8]
0x18004783b  mov     [rsp+400h+var_3A4], r14d
0x180047840  mov     [rsp+400h+var_3A8], r14d
0x180047845  movups  xmm0, xmmword ptr cs:aCbiometricunit_26; "CBiometricUnit::StartTimer"
0x18004784c  movups  xmmword ptr [rbp+300h+var_C0.Ptr], xmm0
0x180047853  movups  xmm1, xmmword ptr cs:aCbiometricunit_26+0Bh; "nit::StartTimer"
0x18004785a  movups  xmmword ptr [rbp+300h+var_C0.Size+3], xmm1
0x180047861  lea     rax, [rbp+300h+var_C0]
0x180047868  mov     qword ptr [rbp+300h+EventDescriptor.Id], rax
0x18004786f  lea     rax, [rsp+400h+var_3A8]
0x180047874  mov     [rbp+300h+EventDescriptor.Keyword], rax
0x18004787b  lea     rax, [rsp+400h+var_3A4]
0x180047880  mov     qword ptr [rbp+300h+var_70], rax
0x180047887  mov     qword ptr [rbp+300h+var_70+8], rbx
0x18004788e  xor     edx, edx
0x180047890  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180047895  mov     rcx, cs:WPP_GLOBAL_Control
0x18004789c  cmp     rcx, r15
0x18004789f  jz      short loc_1800478ED
0x1800478a1  test    byte ptr [rcx+1Ch], 2
0x1800478a5  jz      short loc_1800478ED
0x1800478a7  cmp     byte ptr [rcx+19h], 5
0x1800478ab  jb      short loc_1800478ED
0x1800478ad  mov     edx, 14h
0x1800478b2  mov     rax, qword ptr [rbp+300h+var_70+8]
0x1800478b9  mov     r8d, [rax+50h]
0x1800478bd  mov     [rsp+400h+var_3D0], r8d
0x1800478c2  mov     rax, qword ptr [rbp+300h+var_70]
0x1800478c9  mov     r8d, [rax]
0x1800478cc  mov     dword ptr [rsp+400h+UserData], r8d
0x1800478d1  lea     rax, [rbp+300h+var_C0]
0x1800478d8  mov     qword ptr [rsp+400h+UserDataCount], rax
0x1800478dd  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800478e4  mov     rcx, [rcx+10h]
0x1800478e8  call    WPP_SF_ssdd
0x1800478ed  mov     [rsp+400h+var_3A8], 1
0x1800478f5  lea     rax, [rbp+300h+EventDescriptor]
0x1800478fc  mov     qword ptr [rsp+400h+var_388], rax
0x180047901  mov     rcx, rbx; this
0x180047904  call    ?StopTimer@CBiometricUnit@@QEAAXXZ; CBiometricUnit::StopTimer(void)
0x180047909  mov     rcx, [rbx+0AC0h]
0x180047910  cmp     dword ptr [rcx+44h], 0
0x180047914  jz      short loc_18004793C
0x180047916  mov     rax, [rcx+50h]
0x18004791a  lea     rdx, ds:0[rax*8]
0x180047922  cmp     dword ptr [rcx+48h], 0
0x180047926  jz      short loc_180047932
0x180047928  mov     rax, [rcx+28h]
0x18004792c  mov     rcx, [rdx+rax]
0x180047930  jmp     short loc_18004793F
0x180047932  mov     rax, [rcx+8]
0x180047936  mov     rcx, [rdx+rax]
0x18004793a  jmp     short loc_18004793F
0x18004793c  mov     rcx, r14
0x18004793f  cmp     dword ptr [rcx+7Ch], 0
0x180047943  jz      loc_180047A0C
0x180047949  mov     r9d, 1F0003h; dwDesiredAccess
0x18004794f  xor     r8d, r8d; dwFlags
0x180047952  xor     edx, edx; lpTimerName
0x180047954  xor     ecx, ecx; lpTimerAttributes
0x180047956  call    cs:__imp_CreateWaitableTimerExW
0x18004795c  mov     r10, rax
0x18004795f  mov     [rbx+0B08h], rax
0x180047966  test    rax, rax
0x180047969  jz      loc_1800479F6
0x18004796f  mov     rax, [rbx+0AC0h]
0x180047976  cmp     dword ptr [rax+44h], 0
0x18004797a  jz      short loc_18004799A
0x18004797c  mov     rcx, [rax+50h]
0x180047980  cmp     dword ptr [rax+48h], 0
0x180047984  jz      short loc_180047990
0x180047986  mov     rax, [rax+28h]
0x18004798a  mov     r8, [rax+rcx*8]
0x18004798e  jmp     short loc_18004799D
0x180047990  mov     rax, [rax+8]
0x180047994  mov     r8, [rax+rcx*8]
0x180047998  jmp     short loc_18004799D
0x18004799a  mov     r8, r14
0x18004799d  movsxd  r8, dword ptr [r8+7Ch]; lPeriod
0x1800479a1  imul    rcx, r8, 0FFFFFFFFFFFFD8F0h
0x1800479a8  mov     qword ptr [rbp+300h+DueTime], rcx
0x1800479ac  mov     dword ptr [rsp+400h+UserData], r14d; fResume
0x1800479b1  mov     qword ptr [rsp+400h+UserDataCount], r14; lpArgToCompletionRoutine
0x1800479b6  xor     r9d, r9d; pfnCompletionRoutine
0x1800479b9  lea     rdx, [rbp+300h+DueTime]; lpDueTime
0x1800479bd  mov     rcx, r10; hTimer
0x1800479c0  call    cs:__imp_SetWaitableTimer
0x1800479c6  test    eax, eax
0x1800479c8  jnz     short loc_180047A0C
0x1800479ca  call    cs:__imp_GetLastError
0x1800479d0  test    eax, eax
0x1800479d2  jle     short loc_1800479DC
0x1800479d4  movzx   eax, ax
0x1800479d7  or      eax, 80070000h
0x1800479dc  mov     [rsp+400h+var_3A4], eax
0x1800479e0  mov     rcx, [rbx+0B08h]; hObject
0x1800479e7  call    cs:__imp_CloseHandle
0x1800479ed  mov     [rbx+0B08h], r14
0x1800479f4  jmp     short loc_180047A0C
0x1800479f6  call    cs:__imp_GetLastError
0x1800479fc  test    eax, eax
0x1800479fe  jle     short loc_180047A08
0x180047a00  movzx   eax, ax
0x180047a03  or      eax, 80070000h
0x180047a08  mov     [rsp+400h+var_3A4], eax
0x180047a0c  mov     ebx, [rsp+400h+var_3A4]
0x180047a10  lea     rcx, [rsp+400h+var_388]
0x180047a15  call    WppTraceUnwinder__lambda_67fc72e7a70e3ae32856a086953e5605_______WppTraceUnwinder__lambda_67fc72e7a70e3ae32856a086953e5605____
0x180047a1a  mov     [rsp+400h+var_3C0], ebx
0x180047a1e  test    ebx, ebx
0x180047a20  js      loc_180047B09
0x180047a26  mov     rax, [rsp+400h+var_3B8]
0x180047a2b  mov     dword ptr [rax+0BA0h], 2
0x180047a35  mov     rax, [rsp+400h+var_3B8]
0x180047a3a  mov     rcx, [rax+0A90h]
0x180047a41  add     rcx, 10h
0x180047a45  jz      loc_180047B00
0x180047a4b  mov     rax, [rcx+28h]
0x180047a4f  test    rax, rax
0x180047a52  jz      loc_180047B00
0x180047a58  mov     rax, [rax+0D0h]
0x180047a5f  test    rax, rax
0x180047a62  jz      loc_180047AF2
0x180047a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a6d  mov     [rsp+400h+var_3C0], eax
0x180047a71  test    eax, eax
0x180047a73  js      loc_180047B09
0x180047a79  mov     rax, [rsp+400h+var_3B8]
0x180047a7e  mov     dword ptr [rax+0BA0h], 3
0x180047a88  mov     rax, [rsp+400h+var_3B8]
0x180047a8d  mov     rcx, [rax+0A90h]
0x180047a94  add     rcx, 10h
0x180047a98  jz      short loc_180047B00
0x180047a9a  mov     rax, [rcx+20h]
0x180047a9e  test    rax, rax
0x180047aa1  jz      short loc_180047B00
0x180047aa3  mov     rax, [rax+0E8h]
0x180047aaa  test    rax, rax
0x180047aad  jz      short loc_180047AF2
0x180047aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ab4  mov     [rsp+400h+var_3C0], eax
0x180047ab8  test    eax, eax
0x180047aba  js      short loc_180047B09
0x180047abc  mov     rax, [rsp+400h+var_3B8]
0x180047ac1  mov     dword ptr [rax+0BA0h], 4
0x180047acb  mov     rax, [rsp+400h+var_3B8]
0x180047ad0  mov     rcx, [rax+0A90h]
0x180047ad7  add     rcx, 10h
0x180047adb  jz      short loc_180047B00
0x180047add  mov     rax, [rcx+18h]
0x180047ae1  test    rax, rax
0x180047ae4  jz      short loc_180047B00
0x180047ae6  mov     rax, [rax+0B0h]
0x180047aed  test    rax, rax
0x180047af0  jnz     short loc_180047AF9
0x180047af2  mov     eax, 80004001h
0x180047af7  jmp     short loc_180047B05
0x180047af9  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
