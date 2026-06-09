# SQL_SOSNonYieldIOCPCallback(SchedulerMonitor::Track const * volatile)

- ea: `0x100406350`
- end: `0x100406709`
- name: `?SQL_SOSNonYieldIOCPCallback@@YAXREBVTrack@SchedulerMonitor@@@Z`
- size: `953`
- prototype: `void __fastcall(const struct SchedulerMonitor::Track *volatile)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update`

## callees

- `0x100401580`
- `0x100402ec0`
- `0x100403fa0`
- `0x1004043d0`
- `0x1004044e0`
- `0x100405500`
- `0x100406350`
- `0x100407490`
- `0x100407ea0`
- `0x1004403d0`
- `0x100440860`
- `0x1004534f8`

## import_xrefs

- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x100406618`
- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x100406618`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x10040650b`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x10040650b`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x1004064c9`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x1004064c9`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x1004064c2`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x10040649e`

## string_xrefs

- `0x1004064f2`: `CopyThreadStackForDump: Core dump requested by user. Target Thread Id: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SQL_SOSNonYieldIOCPCallback(struct SchedulerMonitor::Track *a1)
{
  unsigned int v1; // ebx
  void *v2; // rsp
  char v3; // si
  bool v4; // bl
  unsigned __int8 v5[131024]; // [rsp+40h] [rbp-20010h] BYREF
  struct SchedulerMonitor::Track *v6; // [rsp+20050h] [rbp+0h]
  unsigned int v7; // [rsp+20058h] [rbp+8h] BYREF
  unsigned int v8[4]; // [rsp+20060h] [rbp+10h] BYREF
  unsigned __int16 v9; // [rsp+20070h] [rbp+20h]
  int v10; // [rsp+20074h] [rbp+24h]
  __int64 v11; // [rsp+20078h] [rbp+28h]
  int v12; // [rsp+20080h] [rbp+30h] BYREF
  char Buffer[268]; // [rsp+20084h] [rbp+34h] BYREF
  _BYTE v14[4]; // [rsp+20190h] [rbp+140h] BYREF
  int v15; // [rsp+20194h] [rbp+144h]
  int v16; // [rsp+201A0h] [rbp+150h]
  __int64 v17; // [rsp+201A8h] [rbp+158h]
  __int64 v18; // [rsp+201B0h] [rbp+160h]
  _BYTE v19[1232]; // [rsp+201C0h] [rbp+170h] BYREF
  _BYTE v20[1232]; // [rsp+20690h] [rbp+640h] BYREF
  __int64 v21; // [rsp+20B60h] [rbp+B10h]
  int v22; // [rsp+20B68h] [rbp+B18h]
  __int64 (*v23[32])(void); // [rsp+20B70h] [rbp+B20h] BYREF

  v11 = -2;
  v6 = a1;
  v1 = 12;
  if ( (*(_BYTE *)(qword_10049F340 + 456) & 0x40) == 0 )
    v1 = 2;
  NonYieldSystemInformation::UpdateNonYieldRingBuffer(
    (NonYieldSystemInformation *)NonYieldSystemInformation::sm_NonYieldSystemInfo,
    v6,
    *(struct SOS_Node **)(*((_QWORD *)v6 + 50) + 992LL),
    *(_DWORD *)v6,
    v1);
  if ( !(*(_DWORD *)v6 % v1) )
  {
    SQL_SOSWorkerContext::SQL_SOSWorkerContext((SQL_SOSWorkerContext *)v8, *((struct Worker **)v6 + 50));
    memset_0(v23, 0, sizeof(v23));
    v2 = alloca(131088);
    v3 = 0;
    v7 = 0;
    v14[0] = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v21 = 0;
    v22 = 0;
    memset_0(v19, 0, sizeof(v19));
    memset_0(v20, 0, sizeof(v20));
    v4 = (!dword_1004A3648 || (*(_BYTE *)(qword_10049F340 + 157) & 0x40) != 0)
      && (SOS_Tracing_osTrace & 0x40) == 0
      && (*(_BYTE *)(qword_10049F340 + 157) & 0x10) == 0;
    if ( (*(_BYTE *)(qword_10049F340 + 317) & 0x10) != 0
      && OsInfo::IsXPlatInstance(SOS_OS_OsInfo)
      && v4
      && (*(_BYTE *)(qword_10049F340 + 319) & 1) == 0 )
    {
      v12 = 753;
      StringCchPrintfA(
        Buffer,
        0x100u,
        "CopyThreadStackForDump: Core dump requested by user. Target Thread Id: 0x%08X",
        v8[0]);
      SOS_OS::TriggerDump((const struct SYSTEM_SQLPAL_TRIGGER_DUMP_INFO *)&v12);
    }
    if ( CopiedStackInfo::CopyThreadStackForDump((CopiedStackInfo *)v14, v5, 0x20000u, v8[0], v23, 0x20u, &v7) )
    {
      v3 = 1;
      NonYieldSystemInformation::StoreCopiedNonYieldStackRingBuffer(
        NonYieldSystemInformation::sm_NonYieldSystemInfo,
        1,
        v23,
        v7,
        v8[0],
        v10,
        *(_QWORD *)(*((_QWORD *)v6 + 50) + 600LL),
        *((_QWORD *)v6 + 50),
        0,
        0,
        *((_QWORD *)v6 + 47),
        *((_QWORD *)v6 + 48));
    }
    if ( v4 )
    {
      dword_1004A3648 = 1;
      v22 = 259;
      stackTrace(0, 0, L"Stalled IOCP Listener", 672, 4, 0, 259, 0, v14);
    }
    if ( v3 )
    {
      LogSystemMetadataNotSentToClient(L"Copied stack");
      LogFramesRVA(v23, v7, 0);
    }
    scierrlog(
      0x45DFu,
      v8[0],
      *((_QWORD *)v6 + 50),
      v9,
      *((_QWORD *)v6 + 47) / 10000LL,
      *((_QWORD *)v6 + 48) / 10000LL,
      *((_QWORD *)v6 + 21) / 10000LL);
  }
}

```

## disassembly

```asm
0x100406350  push    rbp
0x100406352  push    r14
0x100406354  push    r15
0x100406356  sub     rsp, 0C90h
0x10040635d  lea     rbp, [rsp+60h]
0x100406362  mov     [rbp+0C40h+var_C18], 0FFFFFFFFFFFFFFFEh
0x10040636a  mov     [rbp+0C40h+arg_8], rbx
0x100406371  mov     [rbp+0C40h+arg_10], rsi
0x100406378  mov     rax, cs:__security_cookie
0x10040637f  xor     rax, rbp
0x100406382  mov     [rbp+0C40h+var_20], rax
0x100406389  mov     [rbp+0C40h+var_C40], rcx
0x10040638d  mov     rax, cs:qword_10049F340
0x100406394  test    byte ptr [rax+1C8h], 40h
0x10040639b  mov     ebx, 0Ch
0x1004063a0  mov     eax, 2
0x1004063a5  cmovz   ebx, eax
0x1004063a8  mov     rcx, [rbp+0C40h+var_C40]
0x1004063ac  mov     rax, [rbp+0C40h+var_C40]
0x1004063b0  mov     r8, [rax+190h]
0x1004063b7  mov     [rsp+0CA0h+var_C80], ebx; unsigned int
0x1004063bb  mov     r9d, [rcx]; unsigned int
0x1004063be  mov     r8, [r8+3E0h]; struct SOS_Node *
0x1004063c5  mov     rdx, [rbp+0C40h+var_C40]; struct SchedulerMonitor::Track *
0x1004063c9  lea     rcx, ?sm_NonYieldSystemInfo@NonYieldSystemInformation@@0V1@A; this
0x1004063d0  call    ?UpdateNonYieldRingBuffer@NonYieldSystemInformation@@QEAAXPEBVTrack@SchedulerMonitor@@PEAVSOS_Node@@IK@Z; NonYieldSystemInformation::UpdateNonYieldRingBuffer(SchedulerMonitor::Track const *,SOS_Node *,uint,ulong)
0x1004063d5  mov     rax, [rbp+0C40h+var_C40]
0x1004063d9  xor     edx, edx
0x1004063db  mov     eax, [rax]
0x1004063dd  div     ebx
0x1004063df  test    edx, edx
0x1004063e1  jnz     loc_1004066DF
0x1004063e7  mov     rdx, [rbp+0C40h+var_C40]
0x1004063eb  mov     rdx, [rdx+190h]; struct Worker *
0x1004063f2  lea     rcx, [rbp+0C40h+var_C30]; this
0x1004063f6  call    ??0SQL_SOSWorkerContext@@QEAA@PEAVWorker@@@Z; SQL_SOSWorkerContext::SQL_SOSWorkerContext(Worker *)
0x1004063fb  xor     edx, edx; Val
0x1004063fd  mov     r8d, 100h; Size
0x100406403  lea     rcx, [rbp+0C40h+var_120]; void *
0x10040640a  call    memset_0
0x10040640f  mov     eax, 20010h
0x100406414  call    _alloca_probe
0x100406419  sub     rsp, rax
0x10040641c  lea     r14, [rsp+20CB0h+var_20C50]
0x100406421  xor     sil, sil
0x100406424  xor     r15d, r15d
0x100406427  mov     [rbp+0C40h+var_C38], r15d
0x10040642b  mov     [rbp+0C40h+var_B00], sil
0x100406432  mov     [rbp+0C40h+var_AFC], r15d
0x100406439  mov     [rbp+0C40h+var_AF0], r15d
0x100406440  mov     [rbp+0C40h+var_AE8], r15
0x100406447  mov     [rbp+0C40h+var_AE0], r15
0x10040644e  mov     [rbp+0C40h+var_130], r15
0x100406455  mov     [rbp+0C40h+var_128], r15d
0x10040645c  xor     edx, edx; Val
0x10040645e  mov     r8d, 4D0h; Size
0x100406464  lea     rcx, [rbp+0C40h+var_AD0]; void *
0x10040646b  call    memset_0
0x100406470  xor     edx, edx; Val
0x100406472  mov     r8d, 4D0h; Size
0x100406478  lea     rcx, [rbp+0C40h+var_600]; void *
0x10040647f  call    memset_0
0x100406484  nop
0x100406485  mov     rax, cs:qword_10049F340
0x10040648c  cmp     cs:dword_1004A3648, r15d
0x100406493  jz      short loc_10040649E
0x100406495  test    byte ptr [rax+9Dh], 40h
0x10040649c  jz      short loc_1004064B7
0x10040649e  mov     rcx, cs:__imp_?SOS_Tracing_osTrace@@3KA; ulong SOS_Tracing_osTrace
0x1004064a5  test    byte ptr [rcx], 40h
0x1004064a8  jnz     short loc_1004064B7
0x1004064aa  test    byte ptr [rax+9Dh], 10h
0x1004064b1  jnz     short loc_1004064B7
0x1004064b3  mov     bl, 1
0x1004064b5  jmp     short loc_1004064B9
0x1004064b7  xor     bl, bl
0x1004064b9  test    byte ptr [rax+13Dh], 10h
0x1004064c0  jz      short loc_100406511
0x1004064c2  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x1004064c9  call    cs:__imp_?IsXPlatInstance@OsInfo@@QEBA?B_NXZ; OsInfo::IsXPlatInstance(void)
0x1004064cf  test    al, al
0x1004064d1  jz      short loc_100406511
0x1004064d3  test    bl, bl
0x1004064d5  jz      short loc_100406511
0x1004064d7  mov     rax, cs:qword_10049F340
0x1004064de  test    byte ptr [rax+13Fh], 1
0x1004064e5  jnz     short loc_100406511
0x1004064e7  mov     [rbp+0C40h+var_C10], 2F1h
0x1004064ee  mov     r9d, [rbp+0C40h+var_C30]
0x1004064f2  lea     r8, aCopythreadstac; "CopyThreadStackForDump: Core dump reque"...
0x1004064f9  mov     edx, 100h; unsigned __int64
0x1004064fe  lea     rcx, [rbp+0C40h+Buffer]; Buffer
0x100406502  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x100406507  lea     rcx, [rbp+0C40h+var_C10]
0x10040650b  call    cs:__imp_?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z; SOS_OS::TriggerDump(SYSTEM_SQLPAL_TRIGGER_DUMP_INFO const *)
0x100406511  lea     rax, [rbp+0C40h+var_C38]
0x100406515  mov     [rsp+20CB0h+var_20C80], rax; unsigned int *
0x10040651a  mov     [rsp+20CB0h+var_20C88], 20h ; ' '; unsigned int
0x100406522  lea     rax, [rbp+0C40h+var_120]
0x100406529  mov     [rsp+20CB0h+var_20C90], rax; __int64 (**)(void)
0x10040652e  mov     r9d, [rbp+0C40h+var_C30]; unsigned int
0x100406532  mov     r8d, 20000h; unsigned __int64
0x100406538  mov     rdx, r14; unsigned __int8 *
0x10040653b  lea     rcx, [rbp+0C40h+var_B00]; this
0x100406542  call    ?CopyThreadStackForDump@CopiedStackInfo@@QEAA_NPEAE_KKPEAP6A_JXZIAEAI@Z; CopiedStackInfo::CopyThreadStackForDump(uchar *,unsigned __int64,ulong,__int64 (**)(void),uint,uint &)
0x100406547  test    al, al
0x100406549  jz      short loc_1004065C9
0x10040654b  mov     sil, 1
0x10040654e  mov     rcx, [rbp+0C40h+var_C40]
0x100406552  mov     rdx, [rbp+0C40h+var_C40]
0x100406556  mov     r8, [rbp+0C40h+var_C40]
0x10040655a  mov     rax, [rbp+0C40h+var_C40]
0x10040655e  mov     r9, [rax+190h]
0x100406565  mov     rax, [rcx+180h]
0x10040656c  mov     [rsp+20CB0h+var_20C58], rax
0x100406571  mov     rax, [rdx+178h]
0x100406578  mov     [rsp+20CB0h+var_20C60], rax
0x10040657d  mov     [rsp+20CB0h+var_20C68], r15d
0x100406582  mov     dword ptr [rsp+20CB0h+var_20C70], r15d
0x100406587  mov     rax, [r8+190h]
0x10040658e  mov     [rsp+20CB0h+var_20C78], rax
0x100406593  mov     rax, [r9+258h]
0x10040659a  mov     [rsp+20CB0h+var_20C80], rax
0x10040659f  mov     eax, [rbp+0C40h+var_C1C]
0x1004065a2  mov     [rsp+20CB0h+var_20C88], eax
0x1004065a6  mov     eax, [rbp+0C40h+var_C30]
0x1004065a9  mov     dword ptr [rsp+20CB0h+var_20C90], eax
0x1004065ad  mov     r9d, [rbp+0C40h+var_C38]
0x1004065b1  lea     r8, [rbp+0C40h+var_120]
0x1004065b8  mov     edx, 1
0x1004065bd  lea     rcx, ?sm_NonYieldSystemInfo@NonYieldSystemInformation@@0V1@A; NonYieldSystemInformation NonYieldSystemInformation::sm_NonYieldSystemInfo
0x1004065c4  call    ?StoreCopiedNonYieldStackRingBuffer@NonYieldSystemInformation@@QEAAXW4NonYieldType@SQLSOS_NonYieldCopiedStackRecord@@PEAP6A_JXZIKKPEAVSOS_Task@@PEAVWorker@@KJ_K4@Z; NonYieldSystemInformation::StoreCopiedNonYieldStackRingBuffer(SQLSOS_NonYieldCopiedStackRecord::NonYieldType,__int64 (**)(void),uint,ulong,ulong,SOS_Task *,Worker *,ulong,long,unsigned __int64,unsigned __int64)
0x1004065c9  test    bl, bl
0x1004065cb  jz      short loc_10040661E
0x1004065cd  mov     cs:dword_1004A3648, 1
0x1004065d7  mov     [rbp+0C40h+var_128], 103h
0x1004065e1  lea     rax, [rbp+0C40h+var_B00]
0x1004065e8  mov     [rsp+20CB0h+var_20C70], rax
0x1004065ed  mov     [rsp+20CB0h+var_20C78], r15
0x1004065f2  mov     dword ptr [rsp+20CB0h+var_20C80], 103h
0x1004065fa  mov     qword ptr [rsp+20CB0h+var_20C88], r15
0x1004065ff  mov     dword ptr [rsp+20CB0h+var_20C90], 4
0x100406607  mov     r9d, 2A0h
0x10040660d  lea     r8, aStalledIocpLis; "Stalled IOCP Listener"
0x100406614  xor     edx, edx
0x100406616  xor     ecx, ecx
0x100406618  call    cs:__imp_?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z; stackTrace(SOS_Task *,ExecutionContext *,wchar_t const *,ulong,StackTraceClass,CDStream *,WatsonBucketHint,_GUID const *,CopiedStackInfo *)
0x10040661e  test    sil, sil
0x100406621  jz      short loc_100406641
0x100406623  lea     rcx, aCopiedStack; "Copied stack"
0x10040662a  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x10040662f  xor     r8d, r8d; struct CDStream *
0x100406632  mov     edx, [rbp+0C40h+var_C38]; unsigned int
0x100406635  lea     rcx, [rbp+0C40h+var_120]; __int64 (**)(void)
0x10040663c  call    ?LogFramesRVA@@YAXPEBQ6A_JXZKPEAVCDStream@@@Z; LogFramesRVA(__int64 (*const *)(void),ulong,CDStream *)
0x100406641  mov     r8, [rbp+0C40h+var_C40]
0x100406645  mov     rax, [rbp+0C40h+var_C40]
0x100406649  mov     rcx, [rax+0A8h]
0x100406650  mov     r9, 346DC5D63886594Bh
0x10040665a  mov     rax, r9
0x10040665d  imul    rcx
0x100406660  mov     r11, rdx
0x100406663  sar     r11, 0Bh
0x100406667  mov     rcx, r11
0x10040666a  shr     rcx, 3Fh
0x10040666e  add     r11, rcx
0x100406671  mov     rax, r9
0x100406674  imul    qword ptr [r8+180h]
0x10040667b  mov     r10, rdx
0x10040667e  sar     r10, 0Bh
0x100406682  mov     rcx, r10
0x100406685  shr     rcx, 3Fh
0x100406689  add     r10, rcx
0x10040668c  mov     rax, r9
0x10040668f  imul    qword ptr [r8+178h]
0x100406696  sar     rdx, 0Bh
0x10040669a  mov     rax, rdx
0x10040669d  shr     rax, 3Fh
0x1004066a1  add     rdx, rax
0x1004066a4  movzx   r9d, [rbp+0C40h+var_C20]
0x1004066a9  mov     r8, [rbp+0C40h+var_C40]
0x1004066ad  mov     [rsp+20CB0h+var_20C80], r11
0x1004066b2  mov     qword ptr [rsp+20CB0h+var_20C88], r10
0x1004066b7  mov     [rsp+20CB0h+var_20C90], rdx
0x1004066bc  mov     r8, [r8+190h]
0x1004066c3  mov     edx, [rbp+0C40h+var_C30]
0x1004066c6  mov     ecx, 45DFh; unsigned int
0x1004066cb  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1004066d0  nop
0x1004066d1  mov     [rbp+0C40h+var_B00], 0
0x1004066d8  mov     [rbp+0C40h+var_128], r15d
0x1004066df  mov     rcx, [rbp+0C40h+var_20]
0x1004066e6  xor     rcx, rbp; StackCookie
0x1004066e9  call    __security_check_cookie
0x1004066ee  mov     rbx, [rbp+0C40h+arg_8]
0x1004066f5  mov     rsi, [rbp+0C40h+arg_10]
0x1004066fc  lea     rsp, [rbp+0C30h]
0x100406703  pop     r15
0x100406705  pop     r14
0x100406707  pop     rbp
0x100406708  retn
```
