# SQL_SOSStuckDispatcherCallback(SOS_DispatcherBase const * const)

- ea: `0x100406c30`
- end: `0x10040700f`
- name: `?SQL_SOSStuckDispatcherCallback@@YAXQEBVSOS_DispatcherBase@@@Z`
- size: `991`
- prototype: `void __fastcall(const struct SOS_DispatcherBase *const)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update`

## callees

- `0x100401580`
- `0x100402ec0`
- `0x100403fa0`
- `0x1004043d0`
- `0x1004044e0`
- `0x100405500`
- `0x100406c30`
- `0x100407ea0`
- `0x1004403d0`
- `0x100440860`
- `0x1004534f8`

## import_xrefs

- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x100406eeb`
- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x100406eeb`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x100406df8`
- `sqldk!?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z` at `0x100406df8`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100406db7`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100406db7`
- `sqldk!?GetTrack@SOS_DispatcherBase@@QEBAAEBVTrack@SchedulerMonitor@@XZ` at `0x100406c9c`
- `sqldk!?GetTrack@SOS_DispatcherBase@@QEBAAEBVTrack@SchedulerMonitor@@XZ` at `0x100406c9c`
- `sqldk!?g_featureSwitchesDk@@3VCFeatureSwitchesDk@@A` at `0x100406c81`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100406db0`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x100406d84`

## string_xrefs

- `0x100406ddf`: `CopyThreadStackForDump: Core dump requested by user. Target Thread Id: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SQL_SOSStuckDispatcherCallback(SOS_DispatcherBase *a1)
{
  BOOL v2; // ebx
  const struct SchedulerMonitor::Track *Track; // rdi
  unsigned int v4; // ecx
  void *v5; // rsp
  char v6; // r15
  bool v7; // bl
  DWORD v8; // r14d
  void (__fastcall ***v9)(_QWORD, _BYTE *); // rax
  __int64 v10; // r8
  unsigned int v11[2]; // [rsp+8h] [rbp-20048h]
  unsigned __int8 v12[131088]; // [rsp+40h] [rbp-20010h] BYREF
  unsigned int v13; // [rsp+20050h] [rbp+0h] BYREF
  unsigned int v14[4]; // [rsp+20058h] [rbp+8h] BYREF
  unsigned __int16 v15; // [rsp+20068h] [rbp+18h]
  int v16; // [rsp+2006Ch] [rbp+1Ch]
  __int64 v17; // [rsp+20070h] [rbp+20h]
  _BYTE v18[24]; // [rsp+20078h] [rbp+28h] BYREF
  __int64 v19; // [rsp+20090h] [rbp+40h]
  int v20; // [rsp+200A0h] [rbp+50h] BYREF
  char Buffer[268]; // [rsp+200A4h] [rbp+54h] BYREF
  _BYTE v22[4]; // [rsp+201B0h] [rbp+160h] BYREF
  int v23; // [rsp+201B4h] [rbp+164h]
  int v24; // [rsp+201C0h] [rbp+170h]
  __int64 v25; // [rsp+201C8h] [rbp+178h]
  __int64 v26; // [rsp+201D0h] [rbp+180h]
  _BYTE v27[1232]; // [rsp+201E0h] [rbp+190h] BYREF
  _BYTE v28[1232]; // [rsp+206B0h] [rbp+660h] BYREF
  __int64 v29; // [rsp+20B80h] [rbp+B30h]
  int v30; // [rsp+20B88h] [rbp+B38h]
  __int64 (*v31[32])(void); // [rsp+20B90h] [rbp+B40h] BYREF

  v17 = -2;
  v2 = 0;
  if ( *((_BYTE *)&g_featureSwitchesDk + 82) )
    v2 = *(_DWORD *)((*(__int64 (__fastcall **)(SOS_DispatcherBase *))(*(_QWORD *)a1 + 8LL))(a1) + 40) != 0;
  Track = SOS_DispatcherBase::GetTrack(a1);
  v4 = 24;
  if ( (*(_BYTE *)(qword_10049F340 + 456) & 0x40) == 0 )
    v4 = 12;
  if ( !((*(_DWORD *)Track - *((_DWORD *)Track + 102)) % v4) )
  {
    SQL_SOSWorkerContext::SQL_SOSWorkerContext((SQL_SOSWorkerContext *)v14, *((struct Worker **)Track + 50));
    memset_0(v31, 0, sizeof(v31));
    v5 = alloca(131088);
    v6 = 0;
    v13 = 0;
    v22[0] = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v29 = 0;
    v30 = 0;
    memset_0(v27, 0, sizeof(v27));
    memset_0(v28, 0, sizeof(v28));
    v7 = (!dword_1004A364C || (*(_BYTE *)(qword_10049F340 + 157) & 0x40) != 0)
      && (SOS_Tracing_osTrace & 0x40) == 0
      && !v2
      && (*(_BYTE *)(qword_10049F340 + 157) & 0x10) == 0;
    v8 = v14[0];
    if ( (*(_BYTE *)(qword_10049F340 + 317) & 0x10) != 0
      && OsInfo::IsXPlatInstance(SOS_OS_OsInfo)
      && v7
      && (*(_BYTE *)(qword_10049F340 + 319) & 1) == 0 )
    {
      v20 = 753;
      StringCchPrintfA(
        Buffer,
        0x100u,
        "CopyThreadStackForDump: Core dump requested by user. Target Thread Id: 0x%08X",
        v8);
      SOS_OS::TriggerDump((const struct SYSTEM_SQLPAL_TRIGGER_DUMP_INFO *)&v20);
    }
    if ( CopiedStackInfo::CopyThreadStackForDump((CopiedStackInfo *)v22, v12, 0x20000u, v8, v31, 0x20u, &v13) )
    {
      v6 = 1;
      NonYieldSystemInformation::StoreCopiedNonYieldStackRingBuffer(
        NonYieldSystemInformation::sm_NonYieldSystemInfo,
        3,
        v31,
        v13,
        v8,
        v16,
        *(_QWORD *)(*((_QWORD *)Track + 50) + 600LL),
        *((_QWORD *)Track + 50),
        0,
        0,
        *((_QWORD *)Track + 47),
        *((_QWORD *)Track + 48));
    }
    if ( v7 )
    {
      dword_1004A364C = 1;
      v30 = 264;
      stackTrace(0, 0, L"Stalled Dispatcher", 672, 7, 0, 264, 0, v22);
    }
    if ( v6 )
    {
      LogSystemMetadataNotSentToClient(L"Copied stack");
      LogFramesRVA(v31, v13, 0);
    }
    v9 = (void (__fastcall ***)(_QWORD, _BYTE *))(*(__int64 (__fastcall **)(SOS_DispatcherBase *))(*(_QWORD *)a1 + 8LL))(a1);
    (**v9)(v9, v18);
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(v19 + 2 * v10) );
    v11[0] = v15;
    scierrlog(
      0x45E6u,
      v8,
      2 * v10,
      v19,
      *((_QWORD *)Track + 50),
      *(_QWORD *)v11,
      *((_QWORD *)Track + 47) / 10000LL,
      *((_QWORD *)Track + 48) / 10000LL,
      *((_QWORD *)Track + 21) / 10000LL);
  }
}

```

## disassembly

```asm
0x100406c30  push    rbp
0x100406c32  push    r12
0x100406c34  push    r13
0x100406c36  push    r14
0x100406c38  push    r15
0x100406c3a  sub     rsp, 0CB0h
0x100406c41  lea     rbp, [rsp+60h]
0x100406c46  mov     [rbp+0C70h+var_C50], 0FFFFFFFFFFFFFFFEh
0x100406c4e  mov     [rbp+0C70h+arg_8], rbx
0x100406c55  mov     [rbp+0C70h+arg_10], rsi
0x100406c5c  mov     [rbp+0C70h+arg_18], rdi
0x100406c63  mov     rax, cs:__security_cookie
0x100406c6a  xor     rax, rbp
0x100406c6d  mov     [rbp+0C70h+var_30], rax
0x100406c74  mov     rsi, rcx
0x100406c77  xor     r13d, r13d
0x100406c7a  mov     ebx, r13d
0x100406c7d  lea     edi, [r13+1]
0x100406c81  mov     rax, cs:__imp_?g_featureSwitchesDk@@3VCFeatureSwitchesDk@@A; CFeatureSwitchesDk g_featureSwitchesDk
0x100406c88  cmp     [rax+52h], bl
0x100406c8b  jz      short loc_100406C99
0x100406c8d  mov     rax, [rcx]
0x100406c90  call    qword ptr [rax+8]
0x100406c93  cmp     [rax+28h], ebx
0x100406c96  cmovnz  ebx, edi
0x100406c99  mov     rcx, rsi
0x100406c9c  call    cs:__imp_?GetTrack@SOS_DispatcherBase@@QEBAAEBVTrack@SchedulerMonitor@@XZ; SOS_DispatcherBase::GetTrack(void)
0x100406ca2  mov     rdi, rax
0x100406ca5  mov     rcx, cs:qword_10049F340
0x100406cac  mov     eax, [rax]
0x100406cae  sub     eax, [rdi+198h]
0x100406cb4  test    byte ptr [rcx+1C8h], 40h
0x100406cbb  mov     ecx, 18h
0x100406cc0  mov     edx, 0Ch
0x100406cc5  cmovz   ecx, edx
0x100406cc8  xor     edx, edx
0x100406cca  div     ecx
0x100406ccc  test    edx, edx
0x100406cce  jnz     loc_100406FDA
0x100406cd4  mov     rdx, [rdi+190h]; struct Worker *
0x100406cdb  lea     rcx, [rbp+0C70h+var_C68]; this
0x100406cdf  call    ??0SQL_SOSWorkerContext@@QEAA@PEAVWorker@@@Z; SQL_SOSWorkerContext::SQL_SOSWorkerContext(Worker *)
0x100406ce4  xor     edx, edx; Val
0x100406ce6  mov     r8d, 100h; Size
0x100406cec  lea     rcx, [rbp+0C70h+var_130]; void *
0x100406cf3  call    memset_0
0x100406cf8  mov     eax, 20010h
0x100406cfd  call    _alloca_probe
0x100406d02  sub     rsp, rax
0x100406d05  lea     r12, [rsp+20CE0h+var_20C80]
0x100406d0a  xor     r15b, r15b
0x100406d0d  mov     [rbp+0C70h+var_C70], r13d
0x100406d11  mov     [rbp+0C70h+var_B10], r13b
0x100406d18  mov     [rbp+0C70h+var_B0C], r13d
0x100406d1f  mov     [rbp+0C70h+var_B00], r13d
0x100406d26  mov     [rbp+0C70h+var_AF8], r13
0x100406d2d  mov     [rbp+0C70h+var_AF0], r13
0x100406d34  mov     [rbp+0C70h+var_140], r13
0x100406d3b  mov     [rbp+0C70h+var_138], r13d
0x100406d42  xor     edx, edx; Val
0x100406d44  mov     r8d, 4D0h; Size
0x100406d4a  lea     rcx, [rbp+0C70h+var_AE0]; void *
0x100406d51  call    memset_0
0x100406d56  xor     edx, edx; Val
0x100406d58  mov     r8d, 4D0h; Size
0x100406d5e  lea     rcx, [rbp+0C70h+var_610]; void *
0x100406d65  call    memset_0
0x100406d6a  nop
0x100406d6b  mov     rax, cs:qword_10049F340
0x100406d72  cmp     cs:dword_1004A364C, 0
0x100406d79  jz      short loc_100406D84
0x100406d7b  test    byte ptr [rax+9Dh], 40h
0x100406d82  jz      short loc_100406DA1
0x100406d84  mov     rcx, cs:__imp_?SOS_Tracing_osTrace@@3KA; ulong SOS_Tracing_osTrace
0x100406d8b  test    byte ptr [rcx], 40h
0x100406d8e  jnz     short loc_100406DA1
0x100406d90  test    ebx, ebx
0x100406d92  jnz     short loc_100406DA1
0x100406d94  test    byte ptr [rax+9Dh], 10h
0x100406d9b  jnz     short loc_100406DA1
0x100406d9d  mov     bl, 1
0x100406d9f  jmp     short loc_100406DA3
0x100406da1  xor     bl, bl
0x100406da3  mov     r14d, [rbp+0C70h+var_C68]
0x100406da7  test    byte ptr [rax+13Dh], 10h
0x100406dae  jz      short loc_100406DFE
0x100406db0  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100406db7  call    cs:__imp_?IsXPlatInstance@OsInfo@@QEBA?B_NXZ; OsInfo::IsXPlatInstance(void)
0x100406dbd  test    al, al
0x100406dbf  jz      short loc_100406DFE
0x100406dc1  test    bl, bl
0x100406dc3  jz      short loc_100406DFE
0x100406dc5  mov     rax, cs:qword_10049F340
0x100406dcc  test    byte ptr [rax+13Fh], 1
0x100406dd3  jnz     short loc_100406DFE
0x100406dd5  mov     [rbp+0C70h+var_C20], 2F1h
0x100406ddc  mov     r9d, r14d
0x100406ddf  lea     r8, aCopythreadstac; "CopyThreadStackForDump: Core dump reque"...
0x100406de6  mov     edx, 100h; unsigned __int64
0x100406deb  lea     rcx, [rbp+0C70h+Buffer]; Buffer
0x100406def  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x100406df4  lea     rcx, [rbp+0C70h+var_C20]
0x100406df8  call    cs:__imp_?TriggerDump@SOS_OS@@SA_NPEBUSYSTEM_SQLPAL_TRIGGER_DUMP_INFO@@@Z; SOS_OS::TriggerDump(SYSTEM_SQLPAL_TRIGGER_DUMP_INFO const *)
0x100406dfe  lea     rax, [rbp+0C70h+var_C70]
0x100406e02  mov     [rsp+20CE0h+var_20CB0], rax; unsigned int *
0x100406e07  mov     [rsp+20CE0h+var_20CB8], 20h ; ' '; unsigned int
0x100406e0f  lea     rax, [rbp+0C70h+var_130]
0x100406e16  mov     [rsp+20CE0h+var_20CC0], rax; __int64 (**)(void)
0x100406e1b  mov     r9d, r14d; unsigned int
0x100406e1e  mov     r8d, 20000h; unsigned __int64
0x100406e24  mov     rdx, r12; unsigned __int8 *
0x100406e27  lea     rcx, [rbp+0C70h+var_B10]; this
0x100406e2e  call    ?CopyThreadStackForDump@CopiedStackInfo@@QEAA_NPEAE_KKPEAP6A_JXZIAEAI@Z; CopiedStackInfo::CopyThreadStackForDump(uchar *,unsigned __int64,ulong,__int64 (**)(void),uint,uint &)
0x100406e33  test    al, al
0x100406e35  jz      short loc_100406E9C
0x100406e37  mov     r15b, 1
0x100406e3a  mov     rcx, [rdi+190h]
0x100406e41  mov     rax, [rdi+180h]
0x100406e48  mov     [rsp+20CE0h+var_20C88], rax
0x100406e4d  mov     rax, [rdi+178h]
0x100406e54  mov     [rsp+20CE0h+var_20C90], rax
0x100406e59  mov     [rsp+20CE0h+var_20C98], r13d
0x100406e5e  mov     dword ptr [rsp+20CE0h+var_20CA0], r13d
0x100406e63  mov     [rsp+20CE0h+var_20CA8], rcx
0x100406e68  mov     rax, [rcx+258h]
0x100406e6f  mov     [rsp+20CE0h+var_20CB0], rax
0x100406e74  mov     eax, [rbp+0C70h+var_C54]
0x100406e77  mov     [rsp+20CE0h+var_20CB8], eax
0x100406e7b  mov     dword ptr [rsp+20CE0h+var_20CC0], r14d
0x100406e80  mov     r9d, [rbp+0C70h+var_C70]
0x100406e84  lea     r8, [rbp+0C70h+var_130]
0x100406e8b  mov     edx, 3
0x100406e90  lea     rcx, ?sm_NonYieldSystemInfo@NonYieldSystemInformation@@0V1@A; NonYieldSystemInformation NonYieldSystemInformation::sm_NonYieldSystemInfo
0x100406e97  call    ?StoreCopiedNonYieldStackRingBuffer@NonYieldSystemInformation@@QEAAXW4NonYieldType@SQLSOS_NonYieldCopiedStackRecord@@PEAP6A_JXZIKKPEAVSOS_Task@@PEAVWorker@@KJ_K4@Z; NonYieldSystemInformation::StoreCopiedNonYieldStackRingBuffer(SQLSOS_NonYieldCopiedStackRecord::NonYieldType,__int64 (**)(void),uint,ulong,ulong,SOS_Task *,Worker *,ulong,long,unsigned __int64,unsigned __int64)
0x100406e9c  test    bl, bl
0x100406e9e  jz      short loc_100406EF1
0x100406ea0  mov     cs:dword_1004A364C, 1
0x100406eaa  mov     [rbp+0C70h+var_138], 108h
0x100406eb4  lea     rax, [rbp+0C70h+var_B10]
0x100406ebb  mov     [rsp+20CE0h+var_20CA0], rax
0x100406ec0  mov     [rsp+20CE0h+var_20CA8], r13
0x100406ec5  mov     dword ptr [rsp+20CE0h+var_20CB0], 108h
0x100406ecd  mov     qword ptr [rsp+20CE0h+var_20CB8], r13
0x100406ed2  mov     dword ptr [rsp+20CE0h+var_20CC0], 7
0x100406eda  mov     r9d, 2A0h
0x100406ee0  lea     r8, aStalledDispatc; "Stalled Dispatcher"
0x100406ee7  xor     edx, edx
0x100406ee9  xor     ecx, ecx
0x100406eeb  call    cs:__imp_?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z; stackTrace(SOS_Task *,ExecutionContext *,wchar_t const *,ulong,StackTraceClass,CDStream *,WatsonBucketHint,_GUID const *,CopiedStackInfo *)
0x100406ef1  test    r15b, r15b
0x100406ef4  jz      short loc_100406F14
0x100406ef6  lea     rcx, aCopiedStack; "Copied stack"
0x100406efd  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x100406f02  xor     r8d, r8d; struct CDStream *
0x100406f05  mov     edx, [rbp+0C70h+var_C70]; unsigned int
0x100406f08  lea     rcx, [rbp+0C70h+var_130]; __int64 (**)(void)
0x100406f0f  call    ?LogFramesRVA@@YAXPEBQ6A_JXZKPEAVCDStream@@@Z; LogFramesRVA(__int64 (*const *)(void),ulong,CDStream *)
0x100406f14  mov     rax, [rsi]
0x100406f17  mov     rcx, rsi
0x100406f1a  call    qword ptr [rax+8]
0x100406f1d  mov     r8, [rax]
0x100406f20  lea     rdx, [rbp+0C70h+var_C48]
0x100406f24  mov     rcx, rax
0x100406f27  call    qword ptr [r8]
0x100406f2a  mov     r9, [rbp+0C70h+var_C30]
0x100406f2e  mov     r8, 0FFFFFFFFFFFFFFFFh
0x100406f35  inc     r8
0x100406f38  cmp     word ptr [r9+r8*2], 0
0x100406f3e  jnz     short loc_100406F35
0x100406f40  add     r8, r8
0x100406f43  mov     rbx, 346DC5D63886594Bh
0x100406f4d  mov     rax, rbx
0x100406f50  imul    qword ptr [rdi+0A8h]
0x100406f57  mov     r11, rdx
0x100406f5a  sar     r11, 0Bh
0x100406f5e  mov     rcx, r11
0x100406f61  shr     rcx, 3Fh
0x100406f65  add     r11, rcx
0x100406f68  mov     rax, rbx
0x100406f6b  imul    qword ptr [rdi+180h]
0x100406f72  mov     r10, rdx
0x100406f75  sar     r10, 0Bh
0x100406f79  mov     rcx, r10
0x100406f7c  shr     rcx, 3Fh
0x100406f80  add     r10, rcx
0x100406f83  mov     rax, rbx
0x100406f86  imul    qword ptr [rdi+178h]
0x100406f8d  sar     rdx, 0Bh
0x100406f91  mov     rax, rdx
0x100406f94  shr     rax, 3Fh
0x100406f98  add     rdx, rax
0x100406f9b  movzx   eax, [rbp+0C70h+var_C58]
0x100406f9f  mov     [rsp+20CE0h+var_20CA0], r11
0x100406fa4  mov     [rsp+20CE0h+var_20CA8], r10
0x100406fa9  mov     [rsp+20CE0h+var_20CB0], rdx
0x100406fae  mov     [rsp+20CE0h+var_20CB8], eax
0x100406fb2  mov     rax, [rdi+190h]
0x100406fb9  mov     [rsp+20CE0h+var_20CC0], rax
0x100406fbe  mov     edx, r14d
0x100406fc1  mov     ecx, 45E6h; unsigned int
0x100406fc6  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100406fcb  nop
0x100406fcc  mov     [rbp+0C70h+var_B10], 0
0x100406fd3  mov     [rbp+0C70h+var_138], r13d
0x100406fda  mov     rcx, [rbp+0C70h+var_30]
0x100406fe1  xor     rcx, rbp; StackCookie
0x100406fe4  call    __security_check_cookie
0x100406fe9  mov     rbx, [rbp+0C70h+arg_8]
0x100406ff0  mov     rsi, [rbp+0C70h+arg_10]
0x100406ff7  mov     rdi, [rbp+0C70h+arg_18]
0x100406ffe  lea     rsp, [rbp+0C50h]
0x100407005  pop     r15
0x100407007  pop     r14
0x100407009  pop     r13
0x10040700b  pop     r12
0x10040700d  pop     rbp
0x10040700e  retn
```
