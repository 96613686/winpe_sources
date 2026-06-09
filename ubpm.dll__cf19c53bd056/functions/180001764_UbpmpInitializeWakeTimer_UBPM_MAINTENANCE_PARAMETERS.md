# UbpmpInitializeWakeTimer(_UBPM_MAINTENANCE_PARAMETERS *)

- ea: `0x180001764`
- end: `0x180001d68`
- name: `?UbpmpInitializeWakeTimer@@YAKPEAU_UBPM_MAINTENANCE_PARAMETERS@@@Z`
- size: `1540`
- prototype: `unsigned int __fastcall(struct _UBPM_MAINTENANCE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180036a90`

## callees

- `0x180001764`
- `0x180001d70`
- `0x180001db8`
- `0x180013180`
- `0x180016d80`
- `0x18001f520`
- `0x180032e38`
- `0x18003488c`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlRandomEx` at `0x180001b9c`
- `ntdll!RtlRandomEx` at `0x180001b9c`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800019ce`
- `ntdll!RtlReleaseSRWLockShared` at `0x180001a21`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800019ce`
- `ntdll!RtlReleaseSRWLockShared` at `0x180001a21`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800019bb`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800019bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001aca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001be9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001aca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001be9`
- `EventAggregation!EACreateAggregateEvent` at `0x18000196f`
- `EventAggregation!EACreateAggregateEvent` at `0x18000196f`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180001b21`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180001b21`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180001bdf`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180001bdf`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001ac0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180001ac0`
- `DABAPI!DabRegisterTriggerConsumer` at `0x180001914`
- `DABAPI!DabRegisterTriggerConsumer` at `0x180001914`
- `TimeBrokerClient!TbCreateCEvent` at `0x180001cd5`
- `TimeBrokerClient!TbCreateCEvent` at `0x180001cd5`

## pseudocode

```c
__int64 __fastcall UbpmpInitializeWakeTimer(struct _UBPM_MAINTENANCE_PARAMETERS *a1)
{
  char v2; // r15
  bool v3; // r12
  unsigned int v4; // esi
  unsigned int v5; // eax
  DWORD LastError; // ebx
  _UNKNOWN **i; // rbx
  void *v9; // rcx
  _BYTE *v10; // rdx
  void *v11; // rcx
  __int128 v12; // xmm0
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  DWORD dwLowDateTime; // ecx
  __int64 v16; // rax
  unsigned int v17; // eax
  int v18; // eax
  PVOID v19; // rcx
  struct _FILETIME v20; // [rsp+30h] [rbp-D0h]
  _FILETIME FileTime; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v24; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v25; // [rsp+68h] [rbp-98h]
  __int128 v26; // [rsp+78h] [rbp-88h]
  __m256i v27; // [rsp+90h] [rbp-70h] BYREF
  SYSTEMTIME v28; // [rsp+B0h] [rbp-50h]
  __int128 v29; // [rsp+C0h] [rbp-40h]
  __int128 v30; // [rsp+D0h] [rbp-30h]
  __int128 v31; // [rsp+E0h] [rbp-20h]
  __int128 v32; // [rsp+F0h] [rbp-10h]
  __int128 v33; // [rsp+100h] [rbp+0h]
  __int128 v34; // [rsp+110h] [rbp+10h]
  __int128 v35; // [rsp+120h] [rbp+20h]
  __int128 v36; // [rsp+130h] [rbp+30h]
  __int128 v37; // [rsp+140h] [rbp+40h]
  __int128 v38; // [rsp+150h] [rbp+50h]
  __int128 v39; // [rsp+160h] [rbp+60h]
  __int128 v40; // [rsp+170h] [rbp+70h]
  __int64 v41; // [rsp+180h] [rbp+80h]
  __int128 v42; // [rsp+190h] [rbp+90h] BYREF
  __int128 v43; // [rsp+1A0h] [rbp+A0h]
  __int128 v44; // [rsp+1B0h] [rbp+B0h]
  __int64 v45; // [rsp+1C0h] [rbp+C0h]
  const wchar_t *v46; // [rsp+1D0h] [rbp+D0h] BYREF
  int v47; // [rsp+1D8h] [rbp+D8h]
  unsigned int v48; // [rsp+1DCh] [rbp+DCh]
  int v49; // [rsp+1E0h] [rbp+E0h]
  int v50; // [rsp+1E4h] [rbp+E4h]
  __int128 v51; // [rsp+1E8h] [rbp+E8h]
  int v52; // [rsp+208h] [rbp+108h]
  __int128 *v53; // [rsp+210h] [rbp+110h]
  SYSTEMTIME SystemTime[3]; // [rsp+220h] [rbp+120h] BYREF
  __int128 v55; // [rsp+250h] [rbp+150h]
  __int128 v56; // [rsp+260h] [rbp+160h]
  __int128 v57; // [rsp+270h] [rbp+170h]
  __int128 v58; // [rsp+280h] [rbp+180h]
  _OWORD v59[8]; // [rsp+290h] [rbp+190h] BYREF
  __int64 v60; // [rsp+310h] [rbp+210h]

  memset_0(SystemTime, 0, 0xF8u);
  v23 = 0;
  memset_0(&v46, 0, 0x48u);
  v2 = 0;
  v45 = 0;
  v3 = 0;
  FileTime = 0;
  LocalFileTime = 0;
  v4 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  if ( *((_BYTE *)a1 + 38) )
  {
    UbpmpAcquireListLockShared();
    for ( i = (_UNKNOWN **)g_leConsumerListHead; i != &g_leConsumerListHead; i = (_UNKNOWN **)*i )
    {
      RtlAcquireSRWLockShared(i + 5);
      v9 = i[2];
      if ( *((_QWORD *)v9 + 6) )
      {
        if ( (*((_BYTE *)v9 + 16) & 1) == 0 )
        {
          v10 = *(_BYTE **)(*((_QWORD *)v9 + 5) + 32LL);
          if ( v10 )
          {
            if ( (*v10 & 0x10) != 0 )
            {
              v2 = 1;
              v3 = UbpmUtilsSearchMultiString(*((PCNZWCH *)v9 + 1), g_CriticalTasks) != 0;
              ReportTaskEvent(v11, &MSCHED_TASK_WAKEUP_REQUESTED, *((const unsigned __int16 **)i[2] + 1));
              RtlReleaseSRWLockShared(i + 5);
              break;
            }
          }
        }
      }
      RtlReleaseSRWLockShared(i + 5);
    }
    UbpmpReleaseListLockShared();
  }
  if ( *((_BYTE *)a1 + 39) )
    v4 = *((unsigned __int16 *)a1 + 18) + 60 * (*((unsigned __int16 *)a1 + 17) + 60 * *((unsigned __int16 *)a1 + 16));
  if ( !v2 && g_pCriticalActions.Data4[0] )
  {
    memset_0(SystemTime, 0, 0xF8u);
    *(_DWORD *)&SystemTime[0].wYear = 4;
    DWORD2(v57) = 1;
    StringCbCopyW((unsigned __int16 *)v59 + 2, 0x80u, L"TsMaintWakeTimer");
    v12 = *(_OWORD *)a1;
    *(_DWORD *)&SystemTime[1].wHour = *((_DWORD *)a1 + 4);
    *(_OWORD *)&SystemTime[0].wHour = v12;
    *(_DWORD *)&SystemTime[1].wSecond = 60;
    BYTE5(v55) = 1;
    if ( SystemTimeToFileTime((const SYSTEMTIME *)&SystemTime[0].wHour, &FileTime) )
    {
      if ( FileTimeToLocalFileTime(&FileTime, &LocalFileTime) )
      {
        dwLowDateTime = LocalFileTime.dwLowDateTime;
        v20 = LocalFileTime;
        if ( v4 )
        {
          if ( !Seed )
            Seed = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
          v16 = 10000000LL * (RtlRandomEx(&Seed) % v4) + *(_QWORD *)&v20;
          dwLowDateTime = v16;
        }
        else
        {
          HIDWORD(v16) = LocalFileTime.dwHighDateTime;
        }
        FileTime.dwLowDateTime = dwLowDateTime;
        FileTime.dwHighDateTime = HIDWORD(v16);
        if ( FileTimeToSystemTime(&FileTime, (LPSYSTEMTIME)&SystemTime[0].wHour) )
        {
          v27 = *(__m256i *)&SystemTime[0].wYear;
          v41 = v60;
          v28 = SystemTime[2];
          v30 = v56;
          v29 = v55;
          v32 = v58;
          v31 = v57;
          v34 = v59[1];
          v33 = v59[0];
          v36 = v59[3];
          v35 = v59[2];
          v38 = v59[5];
          v37 = v59[4];
          v40 = v59[7];
          v39 = v59[6];
          v17 = TbCreateCEvent(&v27, &g_MaintenancePilot);
          if ( !v17 )
          {
LABEL_8:
            v42 = g_MaintenancePilot;
            *(_QWORD *)&v44 = &UbpmpMaintenanceRetriggerTasksCallback;
            v43 = 0u;
            *((_QWORD *)&v44 + 1) = 0;
            v45 = 0;
            return (unsigned int)EACreateAggregateEvent(&v42, &qword_18004CB10);
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids, v17);
          goto LABEL_6;
        }
        LastError = GetLastError();
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return LastError;
        v14 = 15;
      }
      else
      {
        LastError = GetLastError();
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return LastError;
        v14 = 14;
      }
    }
    else
    {
      LastError = GetLastError();
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return LastError;
      v14 = 13;
    }
    WPP_SF_d(v13[2], v14, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids, LastError);
    return LastError;
  }
LABEL_6:
  v23 = 0;
  memset_0(&v46, 0, 0x48u);
  LODWORD(v26) = 0;
  v46 = L"Maintenance Timer";
  v53 = &v23;
  v49 = *((_DWORD *)a1 + 4);
  *(_QWORD *)&v24 = qword_18004C330;
  *((_QWORD *)&v24 + 1) = L"Maintenance Activator";
  LODWORD(v23) = 5;
  v52 = 4;
  v50 = -1;
  v47 = 16;
  v48 = v4;
  v25 = 0;
  v51 = *(_OWORD *)a1;
  if ( v2 )
  {
    v18 = 2;
    if ( v3 )
      v18 = 34;
    LODWORD(v25) = v18;
  }
  DWORD1(v26) = 1;
  *((_QWORD *)&v26 + 1) = &v46;
  v5 = DabRegisterTriggerConsumer(0xFFFF, 1, &v24, &g_MaintenancePilot, &qword_18004CB08);
  if ( !v5 )
    goto LABEL_8;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids, v5);
  MicrosoftTelemetryAssertTriggeredNoArgs(v19);
  return 0;
}

```

## disassembly

```asm
0x180001764  push    rbp
0x180001766  push    rbx
0x180001767  push    rsi
0x180001768  push    rdi
0x180001769  push    r12
0x18000176b  push    r13
0x18000176d  push    r14
0x18000176f  push    r15
0x180001771  lea     rbp, [rsp-238h]
0x180001779  sub     rsp, 338h
0x180001780  mov     rax, cs:__security_cookie
0x180001787  xor     rax, rsp
0x18000178a  mov     [rbp+270h+var_50], rax
0x180001791  mov     rdi, rcx
0x180001794  xor     edx, edx; Val
0x180001796  lea     rcx, [rbp+270h+SystemTime]; void *
0x18000179d  mov     r8d, 0F8h; Size
0x1800017a3  call    memset_0
0x1800017a8  xor     edx, edx; Val
0x1800017aa  lea     rcx, [rbp+270h+var_1A0]; void *
0x1800017b1  xorps   xmm0, xmm0
0x1800017b4  movups  [rsp+370h+var_328], xmm0
0x1800017b9  lea     r8d, [rdx+48h]; Size
0x1800017bd  call    memset_0
0x1800017c2  xor     r13d, r13d
0x1800017c5  xor     eax, eax
0x1800017c7  xorps   xmm0, xmm0
0x1800017ca  xorps   xmm1, xmm1
0x1800017cd  mov     r15b, r13b
0x1800017d0  mov     [rbp+270h+var_1B0], rax
0x1800017d7  mov     r12b, r13b
0x1800017da  mov     qword ptr [rsp+370h+FileTime.dwLowDateTime], r13
0x1800017df  lea     r14d, [rax+1]
0x1800017e3  mov     qword ptr [rsp+370h+LocalFileTime.dwLowDateTime], r13
0x1800017e8  mov     esi, r13d
0x1800017eb  mov     [rsp+370h+var_340], r13
0x1800017f0  movups  [rsp+370h+var_318], xmm0
0x1800017f5  movups  [rsp+370h+var_308], xmm0
0x1800017fa  movups  [rsp+370h+var_2F8], xmm0
0x1800017ff  movups  [rbp+270h+var_1E0], xmm1
0x180001806  movups  [rbp+270h+var_1D0], xmm1
0x18000180d  movups  [rbp+270h+var_1C0], xmm1
0x180001814  cmp     [rdi+26h], r13b
0x180001818  jnz     loc_18000199C
0x18000181e  cmp     [rdi+27h], r13b
0x180001822  jnz     loc_180001A37
0x180001828  lea     rbx, WPP_GLOBAL_Control
0x18000182f  test    r15b, r15b
0x180001832  jnz     short loc_180001841
0x180001834  cmp     cs:?g_pCriticalActions@@3PEAU_GUID@@EA.Data4, r13b; _GUID * g_pCriticalActions ...
0x18000183b  jnz     loc_180001A52
0x180001841  xor     edx, edx; Val
0x180001843  lea     rcx, [rbp+270h+var_1A0]; void *
0x18000184a  xorps   xmm0, xmm0
0x18000184d  movups  [rsp+370h+var_328], xmm0
0x180001852  lea     r8d, [rdx+48h]; Size
0x180001856  call    memset_0
0x18000185b  mov     dword ptr [rsp+370h+var_2F8], r13d
0x180001860  lea     rax, aMaintenanceTim; "Maintenance Timer"
0x180001867  mov     [rbp+270h+var_1A0], rax
0x18000186e  lea     rax, [rsp+370h+var_328]
0x180001873  mov     [rbp+270h+var_160], rax
0x18000187a  xorps   xmm0, xmm0
0x18000187d  mov     eax, [rdi+10h]
0x180001880  mov     [rbp+270h+var_190], eax
0x180001886  lea     rax, qword_18004C330
0x18000188d  mov     qword ptr [rsp+370h+var_318], rax
0x180001892  lea     rax, aMaintenanceAct; "Maintenance Activator"
0x180001899  mov     qword ptr [rsp+370h+var_318+8], rax
0x18000189e  mov     dword ptr [rsp+370h+var_328], 5
0x1800018a6  mov     [rbp+270h+var_168], 4
0x1800018b0  mov     [rbp+270h+var_18C], 0FFFFFFFFh
0x1800018ba  mov     [rbp+270h+var_198], 10h
0x1800018c4  mov     [rbp+270h+var_194], esi
0x1800018ca  movdqu  [rsp+370h+var_308], xmm0
0x1800018d0  movups  xmm0, xmmword ptr [rdi]
0x1800018d3  movdqu  [rbp+270h+var_188], xmm0
0x1800018db  test    r15b, r15b
0x1800018de  jnz     loc_180001D1A
0x1800018e4  lea     rax, [rbp+270h+var_1A0]
0x1800018eb  mov     dword ptr [rsp+370h+var_2F8+4], r14d
0x1800018f0  mov     qword ptr [rbp+270h+var_2F8+8], rax
0x1800018f4  lea     r9, ?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x1800018fb  lea     rax, qword_18004CB08
0x180001902  mov     edx, r14d
0x180001905  lea     r8, [rsp+370h+var_318]
0x18000190a  mov     [rsp+370h+var_350], rax
0x18000190f  mov     ecx, 0FFFFh
0x180001914  call    cs:__imp_DabRegisterTriggerConsumer
0x18000191a  test    eax, eax
0x18000191c  jnz     loc_180001D31
0x180001922  mov     rax, cs:?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x180001929  lea     rdx, qword_18004CB10
0x180001930  mov     qword ptr [rbp+270h+var_1E0], rax
0x180001937  lea     rcx, [rbp+270h+var_1E0]
0x18000193e  lea     rax, ?UbpmpMaintenanceRetriggerTasksCallback@@YAXPEAXU_CBROKERED_EVENT_ID@@00K@Z; UbpmpMaintenanceRetriggerTasksCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong)
0x180001945  mov     qword ptr [rbp+270h+var_1E0+8], r13
0x18000194c  mov     qword ptr [rbp+270h+var_1C0], rax
0x180001953  mov     qword ptr [rbp+270h+var_1D0+8], r13
0x18000195a  mov     qword ptr [rbp+270h+var_1D0], r13
0x180001961  mov     qword ptr [rbp+270h+var_1C0+8], r13
0x180001968  mov     [rbp+270h+var_1B0], r13
0x18000196f  call    cs:__imp_EACreateAggregateEvent
0x180001975  mov     ebx, eax
0x180001977  mov     eax, ebx
0x180001979  mov     rcx, [rbp+270h+var_50]
0x180001980  xor     rcx, rsp; StackCookie
0x180001983  call    __security_check_cookie
0x180001988  add     rsp, 338h
0x18000198f  pop     r15
0x180001991  pop     r14
0x180001993  pop     r13
0x180001995  pop     r12
0x180001997  pop     rdi
0x180001998  pop     rsi
0x180001999  pop     rbx
0x18000199a  pop     rbp
0x18000199b  retn
0x18000199c  call    UbpmpAcquireListLockShared
0x1800019a1  mov     rbx, cs:g_leConsumerListHead
0x1800019a8  lea     rax, g_leConsumerListHead
0x1800019af  cmp     rbx, rax
0x1800019b2  jz      short loc_180001A27
0x1800019b4  lea     r14, [rbx+28h]
0x1800019b8  mov     rcx, r14
0x1800019bb  call    cs:__imp_RtlAcquireSRWLockShared
0x1800019c1  mov     rcx, [rbx+10h]
0x1800019c5  cmp     [rcx+30h], r13
0x1800019c9  jnz     short loc_1800019D9
0x1800019cb  mov     rcx, r14
0x1800019ce  call    cs:__imp_RtlReleaseSRWLockShared
0x1800019d4  mov     rbx, [rbx]
0x1800019d7  jmp     short loc_1800019A8
0x1800019d9  test    byte ptr [rcx+10h], 1
0x1800019dd  jnz     short loc_1800019CB
0x1800019df  mov     rax, [rcx+28h]
0x1800019e3  mov     rdx, [rax+20h]
0x1800019e7  test    rdx, rdx
0x1800019ea  jz      short loc_1800019CB
0x1800019ec  test    byte ptr [rdx], 10h
0x1800019ef  jz      short loc_1800019CB
0x1800019f1  mov     rdx, cs:?g_CriticalTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; lpString1
0x1800019f8  mov     r15b, 1
0x1800019fb  mov     rcx, [rcx+8]; lpString2
0x1800019ff  call    ?UbpmUtilsSearchMultiString@@YAEPEBG0@Z; UbpmUtilsSearchMultiString(ushort const *,ushort const *)
0x180001a04  mov     r8, [rbx+10h]
0x180001a08  lea     rdx, MSCHED_TASK_WAKEUP_REQUESTED; struct _EVENT_DESCRIPTOR *
0x180001a0f  test    al, al
0x180001a11  setnz   r12b
0x180001a15  mov     r8, [r8+8]; unsigned __int16 *
0x180001a19  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBG@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180001a1e  mov     rcx, r14
0x180001a21  call    cs:__imp_RtlReleaseSRWLockShared
0x180001a27  call    UbpmpReleaseListLockShared
0x180001a2c  mov     r14d, 1
0x180001a32  jmp     loc_18000181E
0x180001a37  movzx   eax, word ptr [rdi+20h]
0x180001a3b  imul    ecx, eax, 3Ch ; '<'
0x180001a3e  movzx   eax, word ptr [rdi+22h]
0x180001a42  add     ecx, eax
0x180001a44  movzx   eax, word ptr [rdi+24h]
0x180001a48  imul    esi, ecx, 3Ch ; '<'
0x180001a4b  add     esi, eax
0x180001a4d  jmp     loc_180001828
0x180001a52  xor     edx, edx; Val
0x180001a54  lea     rcx, [rbp+270h+SystemTime]; void *
0x180001a5b  mov     r8d, 0F8h; Size
0x180001a61  call    memset_0
0x180001a66  lea     r8, aTsmaintwaketim; "TsMaintWakeTimer"
0x180001a6d  mov     dword ptr [rbp+270h+SystemTime.wYear], 4
0x180001a77  mov     edx, 80h; unsigned __int64
0x180001a7c  mov     [rbp+270h+var_F8], r14d
0x180001a83  lea     rcx, [rbp+270h+var_DC]; unsigned __int16 *
0x180001a8a  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180001a8f  movups  xmm0, xmmword ptr [rdi]
0x180001a92  mov     eax, [rdi+10h]
0x180001a95  lea     rdx, [rsp+370h+FileTime]; lpFileTime
0x180001a9a  lea     rcx, [rbp+270h+SystemTime.wHour]; lpSystemTime
0x180001aa1  mov     [rbp+270h+var_138], eax
0x180001aa7  movdqu  xmmword ptr [rbp+270h+SystemTime.wHour], xmm0
0x180001aaf  mov     [rbp+270h+var_134], 3Ch ; '<'
0x180001ab9  mov     [rbp+270h+var_11B], r14b
0x180001ac0  call    cs:__imp_SystemTimeToFileTime
0x180001ac6  test    eax, eax
0x180001ac8  jnz     short loc_180001B17
0x180001aca  call    cs:__imp_GetLastError
0x180001ad0  mov     ebx, eax
0x180001ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ad9  lea     rax, WPP_GLOBAL_Control
0x180001ae0  cmp     rcx, rax
0x180001ae3  jz      loc_180001977
0x180001ae9  test    [rcx+1Ch], r14b
0x180001aed  jz      loc_180001977
0x180001af3  mov     edx, 0Dh
0x180001af8  jmp     short loc_180001AFF
0x180001afa  mov     edx, 0Fh
0x180001aff  mov     rcx, [rcx+10h]
0x180001b03  lea     r8, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids
0x180001b0a  mov     r9d, ebx
0x180001b0d  call    WPP_SF_d
0x180001b12  jmp     loc_180001977
0x180001b17  lea     rdx, [rsp+370h+LocalFileTime]; lpLocalFileTime
0x180001b1c  lea     rcx, [rsp+370h+FileTime]; lpFileTime
0x180001b21  call    cs:__imp_FileTimeToLocalFileTime
0x180001b27  test    eax, eax
0x180001b29  jnz     short loc_180001B5B
0x180001b2b  call    cs:__imp_GetLastError
0x180001b31  mov     ebx, eax
0x180001b33  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b3a  lea     rax, WPP_GLOBAL_Control
0x180001b41  cmp     rcx, rax
0x180001b44  jz      loc_180001977
0x180001b4a  test    [rcx+1Ch], r14b
0x180001b4e  jz      loc_180001977
0x180001b54  mov     edx, 0Eh
0x180001b59  jmp     short loc_180001AFF
0x180001b5b  mov     eax, [rsp+370h+LocalFileTime.dwHighDateTime]
0x180001b5f  mov     ecx, [rsp+370h+LocalFileTime.dwLowDateTime]
0x180001b63  mov     dword ptr [rsp+370h+var_340+4], eax
0x180001b67  mov     dword ptr [rsp+370h+var_340], ecx
0x180001b6b  test    esi, esi
0x180001b6d  jz      short loc_180001BC2
0x180001b6f  cmp     cs:Seed, r13d
0x180001b76  jnz     short loc_180001B95
0x180001b78  mov     eax, 7FFE0320h
0x180001b7d  mov     rax, [rax]
0x180001b80  mov     ecx, ds:7FFE0004h
0x180001b87  imul    rcx, rax
0x180001b8b  shr     rcx, 18h
0x180001b8f  mov     cs:Seed, ecx
0x180001b95  lea     rcx, Seed; Seed
0x180001b9c  call    cs:__imp_RtlRandomEx
0x180001ba2  xor     edx, edx
0x180001ba4  div     esi
0x180001ba6  mov     rax, [rsp+370h+var_340]
0x180001bab  mov     ecx, edx
0x180001bad  imul    rdx, rcx, 989680h
0x180001bb4  add     rax, rdx
0x180001bb7  mov     [rsp+370h+var_340], rax
0x180001bbc  mov     ecx, dword ptr [rsp+370h+var_340]
0x180001bc0  jmp     short loc_180001BC7
0x180001bc2  mov     rax, [rsp+370h+var_340]
0x180001bc7  shr     rax, 20h
0x180001bcb  lea     rdx, [rbp+270h+SystemTime.wHour]; lpSystemTime
0x180001bd2  mov     [rsp+370h+FileTime.dwLowDateTime], ecx
0x180001bd6  lea     rcx, [rsp+370h+FileTime]; lpFileTime
0x180001bdb  mov     [rsp+370h+FileTime.dwHighDateTime], eax
0x180001bdf  call    cs:__imp_FileTimeToSystemTime
0x180001be5  test    eax, eax
0x180001be7  jnz     short loc_180001C17
0x180001be9  call    cs:__imp_GetLastError
0x180001bef  mov     ebx, eax
0x180001bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bf8  lea     rax, WPP_GLOBAL_Control
0x180001bff  cmp     rcx, rax
0x180001c02  jz      loc_180001977
0x180001c08  test    [rcx+1Ch], r14b
0x180001c0c  jz      loc_180001977
0x180001c12  jmp     loc_180001AFA
0x180001c17  movaps  xmm0, xmmword ptr [rbp+270h+SystemTime.wYear]
0x180001c1e  lea     rdx, ?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x180001c25  movaps  xmm1, xmmword ptr [rbp+130h]
0x180001c2c  lea     rcx, [rbp+270h+var_2E0]
0x180001c30  mov     rax, [rbp+270h+var_60]
0x180001c37  movups  [rbp+270h+var_2E0], xmm0
0x180001c3b  mov     [rbp+270h+var_1F0], rax
0x180001c42  movaps  xmm0, [rbp+270h+var_130]
0x180001c49  movups  [rbp+270h+var_2C0], xmm0
0x180001c4d  movaps  xmm0, [rbp+270h+var_110]
0x180001c54  movups  [rbp+270h+var_2D0], xmm1
0x180001c58  movaps  xmm1, xmmword ptr [rbp+150h]
0x180001c5f  movups  [rbp+270h+var_2A0], xmm0
0x180001c63  movaps  xmm0, [rbp+270h+var_F0]
0x180001c6a  movups  [rbp+270h+var_2B0], xmm1
0x180001c6e  movaps  xmm1, xmmword ptr [rbp+170h]
0x180001c75  movups  [rbp+270h+var_280], xmm0
0x180001c79  movaps  xmm0, [rbp+270h+var_D0]
0x180001c80  movups  [rbp+270h+var_290], xmm1
0x180001c84  movaps  xmm1, xmmword ptr [rbp+190h]
0x180001c8b  movups  [rbp+270h+var_260], xmm0
0x180001c8f  movaps  xmm0, [rbp+270h+var_B0]
0x180001c96  movups  [rbp+270h+var_270], xmm1
0x180001c9a  movaps  xmm1, [rbp+270h+var_C0]
0x180001ca1  movups  [rbp+270h+var_240], xmm0
0x180001ca5  movaps  xmm0, [rbp+270h+var_90]
0x180001cac  movups  [rbp+270h+var_250], xmm1
0x180001cb0  movaps  xmm1, [rbp+270h+var_A0]
0x180001cb7  movups  [rbp+270h+var_220], xmm0
0x180001cbb  movaps  xmm0, [rbp+270h+var_70]
0x180001cc2  movups  [rbp+270h+var_230], xmm1
0x180001cc6  movaps  xmm1, [rbp+270h+var_80]
0x180001ccd  movups  [rbp+270h+var_200], xmm0
0x180001cd1  movups  [rbp+270h+var_210], xmm1
0x180001cd5  call    cs:__imp_TbCreateCEvent
0x180001cdb  test    eax, eax
0x180001cdd  jz      loc_180001922
0x180001ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x180001cea  cmp     rcx, rbx
0x180001ced  jz      loc_180001841
0x180001cf3  test    [rcx+1Ch], r14b
  ... truncated ...
```
