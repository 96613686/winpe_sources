# SQL_SOSNonYieldRMCallback(__int64,ResourceClerk const *,SchedulerMonitor::Track const * volatile)

- ea: `0x100406750`
- end: `0x100406c21`
- name: `?SQL_SOSNonYieldRMCallback@@YAX_JPEBVResourceClerk@@REBVTrack@SchedulerMonitor@@@Z`
- size: `1233`
- prototype: `void __fastcall(__int64, const struct ResourceClerk *, const struct SchedulerMonitor::Track *volatile)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, installer_update`

## callees

- `0x100401580`
- `0x100402ec0`
- `0x100403fa0`
- `0x1004043d0`
- `0x1004044e0`
- `0x100404ed0`
- `0x100405500`
- `0x100406750`
- `0x100407490`
- `0x100407ea0`
- `0x100408810`
- `0x1004403d0`
- `0x100440860`
- `0x1004534f8`

## import_xrefs

- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x100406a43`
- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x100406a43`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x100406937`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x100406937`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x1004068f6`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x1004068f6`
- `sqldk!?GetWaitString@SOS_WaitInfo@@QEBAPEB_WXZ` at `0x100406b8b`
- `sqldk!?GetWaitString@SOS_WaitInfo@@QEBAPEB_WXZ` at `0x100406b8b`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100406ac5`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x1004068ef`
- `sqldk!?sm_CpuConsumers@SOS_PublicGlobals@@2JC` at `0x1004067e8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100406ad1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100406ad1`

## string_xrefs

- `0x10040691e`: `CopyThreadStackForDump: Core dump requested by user. Target Thread Id: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SQL_SOSNonYieldRMCallback(
        __int64 a1,
        const struct ResourceClerk *a2,
        struct SchedulerMonitor::Track *a3)
{
  unsigned int v5; // ebx
  char v6; // si
  int v7; // esi
  void *v8; // rsp
  char v9; // r14
  bool v10; // bl
  DWORD v11; // esi
  struct SchedulerMonitor::Track *v12; // r15
  struct SchedulerMonitor::Track *v13; // rsi
  __int64 v14; // rcx
  _QWORD *v15; // rbx
  int v16; // eax
  const wchar_t *v17; // r14
  const wchar_t *v18; // r12
  unsigned __int64 v19; // rsi
  __int64 v20; // rdi
  __int64 v21; // rbx
  const wchar_t *WaitString; // rax
  unsigned __int8 v23[131024]; // [rsp+40h] [rbp-20010h] BYREF
  struct SchedulerMonitor::Track *v24; // [rsp+20050h] [rbp+0h]
  unsigned int v25; // [rsp+20058h] [rbp+8h] BYREF
  _QWORD *v26; // [rsp+20060h] [rbp+10h] BYREF
  int v27; // [rsp+20068h] [rbp+18h]
  unsigned int v28[4]; // [rsp+20070h] [rbp+20h] BYREF
  unsigned __int16 v29; // [rsp+20080h] [rbp+30h]
  int v30; // [rsp+20084h] [rbp+34h]
  int v31; // [rsp+20088h] [rbp+38h] BYREF
  __int64 v32; // [rsp+20090h] [rbp+40h]
  __int64 v33; // [rsp+20098h] [rbp+48h]
  __int64 v34; // [rsp+200A0h] [rbp+50h]
  __int64 v35; // [rsp+200A8h] [rbp+58h]
  __int64 v36; // [rsp+200B0h] [rbp+60h]
  int v37; // [rsp+200C0h] [rbp+70h] BYREF
  char Buffer[268]; // [rsp+200C4h] [rbp+74h] BYREF
  _BYTE v39[4]; // [rsp+201D0h] [rbp+180h] BYREF
  int v40; // [rsp+201D4h] [rbp+184h]
  int v41; // [rsp+201E0h] [rbp+190h]
  __int64 v42; // [rsp+201E8h] [rbp+198h]
  __int64 v43; // [rsp+201F0h] [rbp+1A0h]
  _BYTE v44[1232]; // [rsp+20200h] [rbp+1B0h] BYREF
  _BYTE v45[1232]; // [rsp+206D0h] [rbp+680h] BYREF
  __int64 v46; // [rsp+20BA0h] [rbp+B50h]
  int v47; // [rsp+20BA8h] [rbp+B58h]
  __int64 (*v48[32])(void); // [rsp+20BB0h] [rbp+B60h] BYREF

  v36 = -2;
  v24 = a3;
  v5 = *(_DWORD *)a3 - *((_DWORD *)a3 + 102);
  v6 = *(_BYTE *)(qword_10049F340 + 157) >> 6;
  NonYieldSystemInformation::UpdateNonYieldRingBuffer(
    (NonYieldSystemInformation *)NonYieldSystemInformation::sm_NonYieldSystemInfo,
    a3,
    *(struct SOS_Node **)(*((_QWORD *)a3 + 50) + 992LL),
    v5,
    0xCu);
  v7 = v6 & 1;
  if ( (v7 || SOS_PublicGlobals::sm_CpuConsumers <= 0) && *((_DWORD *)v24 + 102) && v5 == 12 * (v5 / 0xC) )
  {
    SQL_SOSWorkerContext::SQL_SOSWorkerContext((SQL_SOSWorkerContext *)v28, *((struct Worker **)v24 + 50));
    v39[0] = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v46 = 0;
    v47 = 0;
    memset_0(v44, 0, sizeof(v44));
    memset_0(v45, 0, sizeof(v45));
    memset_0(v48, 0, sizeof(v48));
    v8 = alloca(131088);
    v9 = 0;
    v25 = 0;
    v10 = (!dword_1004A3658 || v7) && (*(_BYTE *)(qword_10049F340 + 157) & 0x10) == 0;
    v11 = v28[0];
    if ( (*(_BYTE *)(qword_10049F340 + 317) & 0x10) != 0
      && OsInfo::IsXPlatInstance(SOS_OS_OsInfo)
      && v10
      && (*(_BYTE *)(qword_10049F340 + 319) & 1) == 0 )
    {
      v37 = 753;
      StringCchPrintfA(
        Buffer,
        0x100u,
        "CopyThreadStackForDump: Core dump requested by user. Target Thread Id: 0x%08X",
        v11);
      SOS_OS::TriggerDump((const struct SYSTEM_SQLPAL_TRIGGER_DUMP_INFO *)&v37);
    }
    if ( CopiedStackInfo::CopyThreadStackForDump((CopiedStackInfo *)v39, v23, 0x20000u, v11, v48, 0x20u, &v25) )
    {
      v9 = 1;
      NonYieldSystemInformation::StoreCopiedNonYieldStackRingBuffer(
        NonYieldSystemInformation::sm_NonYieldSystemInfo,
        2,
        v48,
        v25,
        v28[0],
        v30,
        *(_QWORD *)(*((_QWORD *)v24 + 50) + 600LL),
        *((_QWORD *)v24 + 50),
        0,
        0,
        *((_QWORD *)v24 + 47),
        *((_QWORD *)v24 + 48));
    }
    if ( v10 )
    {
      dword_1004A3658 = 1;
      v47 = 263;
      stackTrace(0, 0, L"Stalled Resource Monitor", 672, 6, 0, 263, 0, v39);
    }
    if ( v9 )
    {
      LogSystemMetadataNotSentToClient(L"Copied stack");
      LogFramesRVA(v48, v25, 0);
    }
    v12 = v24;
    v13 = v24;
    v31 = 0x400000;
    v32 = 0;
    v34 = 0;
    v33 = 0;
    v35 = 0;
    v14 = *(_QWORD *)(*((_QWORD *)v24 + 50) + 600LL);
    v26 = 0;
    v27 = 0;
    SOS_Task::GetWaitInformationImpl(v14, &v26, &v31, 0);
    v15 = v26;
    if ( v26 && v27 )
    {
      if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v16 = rand();
        if ( v16 == 5 * (v16 / 5) )
          Spinlock<11,2,268435714>::UpdateStatSnapshot();
      }
      *v15 = 0;
      v26 = 0;
      v27 = 0;
    }
    if ( a2 )
    {
      v17 = (const wchar_t *)(*(__int64 (__fastcall **)(const struct ResourceClerk *))(*(_QWORD *)a2 + 16LL))(a2);
      v18 = (const wchar_t *)(*(__int64 (__fastcall **)(const struct ResourceClerk *))(*(_QWORD *)a2 + 24LL))(a2);
    }
    else
    {
      v17 = L"N/A";
      v18 = L"N/A";
    }
    v19 = (__int64)((unsigned __int128)(*((__int64 *)v13 + 21) * (__int128)0x346DC5D63886594BLL) >> 64) >> 11;
    v20 = *((_QWORD *)v12 + 48) / 10000LL;
    v21 = *((_QWORD *)v12 + 47) / 10000LL;
    WaitString = SOS_WaitInfo::GetWaitString((SOS_WaitInfo *)&v31);
    scierrlog(0x45E3u, v28[0], *((_QWORD *)v24 + 50), v29, a1 / 1024, WaitString, v18, v17, v21, v20, (v19 >> 63) + v19);
  }
}

```

## disassembly

```asm
0x100406750  push    rbp
0x100406752  push    rsi
0x100406753  push    rdi
0x100406754  push    r12
0x100406756  push    r13
0x100406758  push    r14
0x10040675a  push    r15
0x10040675c  sub     rsp, 0CD0h
0x100406763  lea     rbp, [rsp+60h]
0x100406768  mov     [rbp+0CA0h+var_C40], 0FFFFFFFFFFFFFFFEh
0x100406770  mov     [rbp+0CA0h+arg_18], rbx
0x100406777  mov     rax, cs:__security_cookie
0x10040677e  xor     rax, rbp
0x100406781  mov     [rbp+0CA0h+var_40], rax
0x100406788  mov     rdi, rdx
0x10040678b  mov     r13, rcx
0x10040678e  mov     [rbp+0CA0h+var_CA0], r8
0x100406792  mov     rcx, [rbp+0CA0h+var_CA0]
0x100406796  mov     rax, [rbp+0CA0h+var_CA0]
0x10040679a  mov     ebx, [rax]
0x10040679c  sub     ebx, [rcx+198h]
0x1004067a2  mov     rax, cs:qword_10049F340
0x1004067a9  movzx   ecx, byte ptr [rax+9Dh]
0x1004067b0  shr     cl, 6
0x1004067b3  movzx   esi, cl
0x1004067b6  mov     rax, [rbp+0CA0h+var_CA0]
0x1004067ba  mov     r8, [rax+190h]
0x1004067c1  mov     [rsp+0D00h+var_CE0], 0Ch; unsigned int
0x1004067c9  mov     r9d, ebx; unsigned int
0x1004067cc  mov     r8, [r8+3E0h]; struct SOS_Node *
0x1004067d3  mov     rdx, [rbp+0CA0h+var_CA0]; struct SchedulerMonitor::Track *
0x1004067d7  lea     rcx, ?sm_NonYieldSystemInfo@NonYieldSystemInformation@@0V1@A; this
0x1004067de  call    ?UpdateNonYieldRingBuffer@NonYieldSystemInformation@@QEAAXPEBVTrack@SchedulerMonitor@@PEAVSOS_Node@@IK@Z; NonYieldSystemInformation::UpdateNonYieldRingBuffer(SchedulerMonitor::Track const *,SOS_Node *,uint,ulong)
0x1004067e3  and     esi, 1
0x1004067e6  jnz     short loc_1004067F9
0x1004067e8  mov     rax, cs:__imp_?sm_CpuConsumers@SOS_PublicGlobals@@2JC; long volatile SOS_PublicGlobals::sm_CpuConsumers
0x1004067ef  mov     ecx, [rax]
0x1004067f1  test    ecx, ecx
0x1004067f3  jg      loc_100406BF8
0x1004067f9  mov     rax, [rbp+0CA0h+var_CA0]
0x1004067fd  cmp     dword ptr [rax+198h], 0
0x100406804  jz      loc_100406BF8
0x10040680a  mov     eax, 0AAAAAAABh
0x10040680f  mul     ebx
0x100406811  shr     edx, 3
0x100406814  lea     eax, [rdx+rdx*2]
0x100406817  shl     eax, 2
0x10040681a  cmp     ebx, eax
0x10040681c  jnz     loc_100406BF8
0x100406822  mov     rdx, [rbp+0CA0h+var_CA0]
0x100406826  mov     rdx, [rdx+190h]; struct Worker *
0x10040682d  lea     rcx, [rbp+0CA0h+var_C80]; this
0x100406831  call    ??0SQL_SOSWorkerContext@@QEAA@PEAVWorker@@@Z; SQL_SOSWorkerContext::SQL_SOSWorkerContext(Worker *)
0x100406836  mov     [rbp+0CA0h+var_B20], 0
0x10040683d  xor     r12d, r12d
0x100406840  mov     [rbp+0CA0h+var_B1C], r12d
0x100406847  mov     [rbp+0CA0h+var_B10], r12d
0x10040684e  mov     [rbp+0CA0h+var_B08], r12
0x100406855  mov     [rbp+0CA0h+var_B00], r12
0x10040685c  mov     [rbp+0CA0h+var_150], r12
0x100406863  mov     [rbp+0CA0h+var_148], r12d
0x10040686a  xor     edx, edx; Val
0x10040686c  mov     r8d, 4D0h; Size
0x100406872  lea     rcx, [rbp+0CA0h+var_AF0]; void *
0x100406879  call    memset_0
0x10040687e  xor     edx, edx; Val
0x100406880  mov     r8d, 4D0h; Size
0x100406886  lea     rcx, [rbp+0CA0h+var_620]; void *
0x10040688d  call    memset_0
0x100406892  nop
0x100406893  xor     edx, edx; Val
0x100406895  mov     r8d, 100h; Size
0x10040689b  lea     rcx, [rbp+0CA0h+var_140]; void *
0x1004068a2  call    memset_0
0x1004068a7  mov     eax, 20010h
0x1004068ac  call    _alloca_probe
0x1004068b1  sub     rsp, rax
0x1004068b4  lea     r15, [rsp+20D10h+var_20CB0]
0x1004068b9  xor     r14b, r14b
0x1004068bc  mov     [rbp+0CA0h+var_C98], r12d
0x1004068c0  mov     rax, cs:qword_10049F340
0x1004068c7  cmp     cs:dword_1004A3658, r12d
0x1004068ce  jz      short loc_1004068D4
0x1004068d0  test    esi, esi
0x1004068d2  jz      short loc_1004068E1
0x1004068d4  test    byte ptr [rax+9Dh], 10h
0x1004068db  jnz     short loc_1004068E1
0x1004068dd  mov     bl, 1
0x1004068df  jmp     short loc_1004068E3
0x1004068e1  xor     bl, bl
0x1004068e3  mov     esi, [rbp+0CA0h+var_C80]
0x1004068e6  test    byte ptr [rax+13Dh], 10h
0x1004068ed  jz      short loc_10040693D
0x1004068ef  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x1004068f6  call    cs:__imp_?IsXPlatInstance@OsInfo@@QEBA?B_NXZ; OsInfo::IsXPlatInstance(void)
0x1004068fc  test    al, al
0x1004068fe  jz      short loc_10040693D
0x100406900  test    bl, bl
0x100406902  jz      short loc_10040693D
0x100406904  mov     rax, cs:qword_10049F340
0x10040690b  test    byte ptr [rax+13Fh], 1
0x100406912  jnz     short loc_10040693D
0x100406914  mov     [rbp+0CA0h+var_C30], 2F1h
0x10040691b  mov     r9d, esi
0x10040691e  lea     r8, aCopythreadstac; "CopyThreadStackForDump: Core dump reque"...
0x100406925  mov     edx, 100h; unsigned __int64
0x10040692a  lea     rcx, [rbp+0CA0h+Buffer]; Buffer
0x10040692e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x100406933  lea     rcx, [rbp+0CA0h+var_C30]
0x100406937  call    cs:__imp_?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z; SOS_OS::TriggerDump(SYSTEM_SQLPAL_TRIGGER_DUMP_INFO const *)
0x10040693d  lea     rax, [rbp+0CA0h+var_C98]
0x100406941  mov     [rsp+20D10h+var_20CE0], rax; unsigned int *
0x100406946  mov     [rsp+20D10h+var_20CE8], 20h ; ' '; unsigned int
0x10040694e  lea     rax, [rbp+0CA0h+var_140]
0x100406955  mov     [rsp+20D10h+var_20CF0], rax; __int64 (**)(void)
0x10040695a  mov     r9d, esi; unsigned int
0x10040695d  mov     r8d, 20000h; unsigned __int64
0x100406963  mov     rdx, r15; unsigned __int8 *
0x100406966  lea     rcx, [rbp+0CA0h+var_B20]; this
0x10040696d  call    ?CopyThreadStackForDump@CopiedStackInfo@@QEAA_NPEAE_KKPEAP6A_JXZIAEAI@Z; CopiedStackInfo::CopyThreadStackForDump(uchar *,unsigned __int64,ulong,__int64 (**)(void),uint,uint &)
0x100406972  test    al, al
0x100406974  jz      short loc_1004069F4
0x100406976  mov     r14b, 1
0x100406979  mov     rcx, [rbp+0CA0h+var_CA0]
0x10040697d  mov     rdx, [rbp+0CA0h+var_CA0]
0x100406981  mov     r8, [rbp+0CA0h+var_CA0]
0x100406985  mov     rax, [rbp+0CA0h+var_CA0]
0x100406989  mov     r9, [rax+190h]
0x100406990  mov     rax, [rcx+180h]
0x100406997  mov     [rsp+20D10h+var_20CB8], rax
0x10040699c  mov     rax, [rdx+178h]
0x1004069a3  mov     [rsp+20D10h+var_20CC0], rax
0x1004069a8  mov     dword ptr [rsp+20D10h+var_20CC8], r12d
0x1004069ad  mov     dword ptr [rsp+20D10h+var_20CD0], r12d
0x1004069b2  mov     rax, [r8+190h]
0x1004069b9  mov     [rsp+20D10h+var_20CD8], rax
0x1004069be  mov     rax, [r9+258h]
0x1004069c5  mov     [rsp+20D10h+var_20CE0], rax
0x1004069ca  mov     eax, [rbp+0CA0h+var_C6C]
0x1004069cd  mov     [rsp+20D10h+var_20CE8], eax
0x1004069d1  mov     eax, [rbp+0CA0h+var_C80]
0x1004069d4  mov     dword ptr [rsp+20D10h+var_20CF0], eax
0x1004069d8  mov     r9d, [rbp+0CA0h+var_C98]
0x1004069dc  lea     r8, [rbp+0CA0h+var_140]
0x1004069e3  mov     edx, 2
0x1004069e8  lea     rcx, ?sm_NonYieldSystemInfo@NonYieldSystemInformation@@0V1@A; NonYieldSystemInformation NonYieldSystemInformation::sm_NonYieldSystemInfo
0x1004069ef  call    ?StoreCopiedNonYieldStackRingBuffer@NonYieldSystemInformation@@QEAAXW4NonYieldType@SQLSOS_NonYieldCopiedStackRecord@@PEAP6A_JXZIKKPEAVSOS_Task@@PEAVWorker@@KJ_K4@Z; NonYieldSystemInformation::StoreCopiedNonYieldStackRingBuffer(SQLSOS_NonYieldCopiedStackRecord::NonYieldType,__int64 (**)(void),uint,ulong,ulong,SOS_Task *,Worker *,ulong,long,unsigned __int64,unsigned __int64)
0x1004069f4  test    bl, bl
0x1004069f6  jz      short loc_100406A49
0x1004069f8  mov     cs:dword_1004A3658, 1
0x100406a02  mov     [rbp+0CA0h+var_148], 107h
0x100406a0c  lea     rax, [rbp+0CA0h+var_B20]
0x100406a13  mov     [rsp+20D10h+var_20CD0], rax
0x100406a18  mov     [rsp+20D10h+var_20CD8], r12
0x100406a1d  mov     dword ptr [rsp+20D10h+var_20CE0], 107h
0x100406a25  mov     qword ptr [rsp+20D10h+var_20CE8], r12
0x100406a2a  mov     dword ptr [rsp+20D10h+var_20CF0], 6
0x100406a32  mov     r9d, 2A0h
0x100406a38  lea     r8, aStalledResourc; "Stalled Resource Monitor"
0x100406a3f  xor     edx, edx
0x100406a41  xor     ecx, ecx
0x100406a43  call    cs:__imp_?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z; stackTrace(SOS_Task *,ExecutionContext *,wchar_t const *,ulong,StackTraceClass,CDStream *,WatsonBucketHint,_GUID const *,CopiedStackInfo *)
0x100406a49  test    r14b, r14b
0x100406a4c  jz      short loc_100406A6C
0x100406a4e  lea     rcx, aCopiedStack; "Copied stack"
0x100406a55  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x100406a5a  xor     r8d, r8d; struct CDStream *
0x100406a5d  mov     edx, [rbp+0CA0h+var_C98]; unsigned int
0x100406a60  lea     rcx, [rbp+0CA0h+var_140]; __int64 (**)(void)
0x100406a67  call    ?LogFramesRVA@@YAXPEBQ6A_JXZKPEAVCDStream@@@Z; LogFramesRVA(__int64 (*const *)(void),ulong,CDStream *)
0x100406a6c  mov     r15, [rbp+0CA0h+var_CA0]
0x100406a70  mov     rsi, [rbp+0CA0h+var_CA0]
0x100406a74  mov     [rbp+0CA0h+var_C68], 400000h
0x100406a7b  mov     [rbp+0CA0h+var_C60], r12
0x100406a7f  mov     [rbp+0CA0h+var_C50], r12
0x100406a83  mov     [rbp+0CA0h+var_C58], r12
0x100406a87  mov     [rbp+0CA0h+var_C48], r12
0x100406a8b  mov     rax, [rbp+0CA0h+var_CA0]
0x100406a8f  mov     rcx, [rax+190h]
0x100406a96  mov     rcx, [rcx+258h]
0x100406a9d  mov     [rbp+0CA0h+var_C90], r12
0x100406aa1  mov     [rbp+0CA0h+var_C88], r12d
0x100406aa5  xor     r9d, r9d
0x100406aa8  lea     r8, [rbp+0CA0h+var_C68]
0x100406aac  lea     rdx, [rbp+0CA0h+var_C90]
0x100406ab0  call    ?GetWaitInformationImpl@SOS_Task@@AEAA?AW4SOS_RESULT@@AEAV?$SpinlockHolder@$0L@$01$0BAAAABAC@@@PEAVSOS_WaitInfo@@PEAV?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SOS_Task::GetWaitInformationImpl(SpinlockHolder<11,2,268435714> &,SOS_WaitInfo *,SOS_Ticks<InterruptTicks<unsigned __int64>,-3> *)
0x100406ab5  nop
0x100406ab6  mov     rbx, [rbp+0CA0h+var_C90]
0x100406aba  test    rbx, rbx
0x100406abd  jz      short loc_100406B03
0x100406abf  cmp     [rbp+0CA0h+var_C88], 0
0x100406ac3  jz      short loc_100406B03
0x100406ac5  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x100406acc  cmp     byte ptr [rax], 0
0x100406acf  jz      short loc_100406AF8
0x100406ad1  call    cs:__imp_rand
0x100406ad7  mov     r8d, eax
0x100406ada  mov     eax, 66666667h
0x100406adf  imul    r8d
0x100406ae2  sar     edx, 1
0x100406ae4  mov     ecx, edx
0x100406ae6  shr     ecx, 1Fh
0x100406ae9  add     edx, ecx
0x100406aeb  lea     ecx, [rdx+rdx*4]
0x100406aee  cmp     r8d, ecx
0x100406af1  jnz     short loc_100406AF8
0x100406af3  call    ?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ; Spinlock<11,2,268435714>::UpdateStatSnapshot(void)
0x100406af8  mov     [rbx], r12
0x100406afb  mov     [rbp+0CA0h+var_C90], r12
0x100406aff  mov     [rbp+0CA0h+var_C88], r12d
0x100406b03  test    rdi, rdi
0x100406b06  jz      short loc_100406B22
0x100406b08  mov     rax, [rdi]
0x100406b0b  mov     rcx, rdi
0x100406b0e  call    qword ptr [rax+10h]
0x100406b11  mov     r14, rax
0x100406b14  mov     rdx, [rdi]
0x100406b17  mov     rcx, rdi
0x100406b1a  call    qword ptr [rdx+18h]
0x100406b1d  mov     r12, rax
0x100406b20  jmp     short loc_100406B2C
0x100406b22  lea     r14, aNA; "N/A"
0x100406b29  mov     r12, r14
0x100406b2c  mov     r8, 346DC5D63886594Bh
0x100406b36  mov     rax, r8
0x100406b39  imul    qword ptr [rsi+0A8h]
0x100406b40  mov     rsi, rdx
0x100406b43  sar     rsi, 0Bh
0x100406b47  mov     rcx, rsi
0x100406b4a  shr     rcx, 3Fh
0x100406b4e  add     rsi, rcx
0x100406b51  mov     rax, r8
0x100406b54  imul    qword ptr [r15+180h]
0x100406b5b  mov     rdi, rdx
0x100406b5e  sar     rdi, 0Bh
0x100406b62  mov     rcx, rdi
0x100406b65  shr     rcx, 3Fh
0x100406b69  add     rdi, rcx
0x100406b6c  mov     rax, r8
0x100406b6f  imul    qword ptr [r15+178h]
0x100406b76  mov     rbx, rdx
0x100406b79  sar     rbx, 0Bh
0x100406b7d  mov     rcx, rbx
0x100406b80  shr     rcx, 3Fh
0x100406b84  add     rbx, rcx
0x100406b87  lea     rcx, [rbp+0CA0h+var_C68]
0x100406b8b  call    cs:__imp_?GetWaitString@SOS_WaitInfo@@QEBAPEB_WXZ; SOS_WaitInfo::GetWaitString(void)
0x100406b91  mov     rcx, rax
0x100406b94  mov     rax, r13
0x100406b97  cqo
0x100406b99  and     edx, 3FFh
0x100406b9f  add     rax, rdx
0x100406ba2  sar     rax, 0Ah
0x100406ba6  movzx   r9d, [rbp+0CA0h+var_C70]
0x100406bab  mov     r8, [rbp+0CA0h+var_CA0]
0x100406baf  mov     [rsp+20D10h+var_20CC0], rsi
0x100406bb4  mov     [rsp+20D10h+var_20CC8], rdi
0x100406bb9  mov     [rsp+20D10h+var_20CD0], rbx
0x100406bbe  mov     [rsp+20D10h+var_20CD8], r14
0x100406bc3  mov     [rsp+20D10h+var_20CE0], r12
0x100406bc8  mov     qword ptr [rsp+20D10h+var_20CE8], rcx
0x100406bcd  mov     [rsp+20D10h+var_20CF0], rax
0x100406bd2  mov     r8, [r8+190h]
0x100406bd9  mov     edx, [rbp+0CA0h+var_C80]
0x100406bdc  mov     ecx, 45E3h; unsigned int
0x100406be1  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100406be6  nop
0x100406be7  mov     [rbp+0CA0h+var_B20], 0
0x100406bee  mov     [rbp+0CA0h+var_148], 0
0x100406bf8  mov     rcx, [rbp+0CA0h+var_40]
0x100406bff  xor     rcx, rbp; StackCookie
0x100406c02  call    __security_check_cookie
0x100406c07  mov     rbx, [rbp+0CA0h+arg_18]
0x100406c0e  lea     rsp, [rbp+0C70h]
0x100406c15  pop     r15
0x100406c17  pop     r14
0x100406c19  pop     r13
0x100406c1b  pop     r12
0x100406c1d  pop     rdi
0x100406c1e  pop     rsi
0x100406c1f  pop     rbp
0x100406c20  retn
```
