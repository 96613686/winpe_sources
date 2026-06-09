# CSatelliteSpeesExecutor::InitSpeesInternal(void)

- ea: `0x10040a520`
- end: `0x10040ac22`
- name: `?InitSpeesInternal@CSatelliteSpeesExecutor@@AEAAJXZ`
- size: `1794`
- prototype: `__int64 __fastcall(CSatelliteSpeesExecutor *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x100408970`

## callees

- `0x1004078d0`
- `0x100407f40`
- `0x100408080`
- `0x10040a520`
- `0x10040b8a0`
- `0x10040b9b0`
- `0x10040bbb0`
- `0x100411350`
- `0x1004759c0`
- `0x100479870`
- `0x10047ed10`
- `0x10047ede0`
- `0x100487cd6`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040a5c9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040a65f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040a711`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040a809`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040a89b`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040a5c9`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040a65f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040a711`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040a809`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10040a89b`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10040a6db`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10040a9d6`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10040abb6`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10040a6db`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10040a9d6`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10040abb6`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x10040a991`
- `sqldk!?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z` at `0x10040a991`
- `sqldk!SystemThread_TlsIndex` at `0x10040a567`
- `sqldk!SystemThread_TlsIndex` at `0x10040a5ff`
- `sqldk!SystemThread_TlsIndex` at `0x10040a90d`
- `sqldk!SystemThread_TlsIndex` at `0x10040aacf`
- `sqldk!SystemThread_TlsOffset` at `0x10040a570`
- `sqldk!SystemThread_TlsOffset` at `0x10040a608`
- `sqldk!SystemThread_TlsOffset` at `0x10040a916`
- `sqldk!SystemThread_TlsOffset` at `0x10040aad8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040a58b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040a623`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040a931`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040aaf3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040a58b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040a623`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040a931`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040aaf3`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CSatelliteSpeesExecutor::InitSpeesInternal(CSatelliteSpeesExecutor *this)
{
  int v2; // r15d
  struct IMemObj *v3; // r12
  __int64 v4; // rbx
  __int64 v5; // rax
  CSQLSatelliteSessionBasedMsgQueueConnection *v6; // rax
  CSQLSatelliteSessionBasedMsgQueueConnection *v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rax
  _QWORD *v10; // rax
  BlobMessageMgr *v11; // rbx
  _QWORD *v12; // rax
  BlobMessageMgr *v13; // rdi
  _QWORD *v14; // r14
  void (__fastcall ***v15)(_QWORD, __int64); // rsi
  CSatelliteSessionContext *v16; // rax
  CSatelliteSessionContext *v17; // rbx
  _QWORD *v18; // rax
  MessageTelemetry *v19; // rdi
  __int64 v20; // rsi
  __int64 v21; // rax
  CSQLSatelliteSessionBasedMsgQueueConnection *v22; // rsi
  char *v23; // r8
  __int64 MemObject; // rax
  void *v25; // rsi
  __int64 v26; // rbx
  MessageTelemetry *v27; // rcx
  __int64 v28; // rax
  CSatelliteSpeesExecutor *v29; // rcx
  __int64 v30; // rdx
  char *v31; // r8
  __int16 v32; // ax
  CSatelliteSpeesExecutor *v33; // rax
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v36; // rdx
  BlobMessageMgr *v37; // rbx
  void (__fastcall ***v38)(_QWORD, __int64); // rcx
  CSQLSatelliteSessionBasedMsgQueueConnection *v39; // rcx
  __int64 v40; // rax
  int v42; // [rsp+20h] [rbp-50h]
  CSatelliteSessionContext *v43; // [rsp+30h] [rbp-40h]
  MessageTelemetry *v44; // [rsp+38h] [rbp-38h]
  CSQLSatelliteSessionBasedMsgQueueConnection *v45; // [rsp+40h] [rbp-30h]
  CSQLSatelliteSessionBasedMsgQueueConnection *v46; // [rsp+C0h] [rbp+50h]

  v2 = -2147024882;
  v3 = (struct IMemObj *)CSatelliteGlobalContext::sm_pmo;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  v6 = (CSQLSatelliteSessionBasedMsgQueueConnection *)operator new(
                                                        0x450u,
                                                        *(struct IMemObj **)(*(_QWORD *)(v5 + 992) + 320LL),
                                                        1,
                                                        "Sql\\Ntdbms\\extensibility\\satellite\\src\\SatelliteExecutor.cpp",
                                                        926,
                                                        6u);
  if ( v6 )
    v7 = CSQLSatelliteSessionBasedMsgQueueConnection::CSQLSatelliteSessionBasedMsgQueueConnection(v6);
  else
    v7 = 0;
  v46 = v7;
  v45 = v7;
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  v10 = operator new(
          0x60u,
          *(struct IMemObj **)(*(_QWORD *)(v9 + 992) + 320LL),
          1,
          "Sql\\Ntdbms\\extensibility\\satellite\\src\\SatelliteExecutor.cpp",
          928,
          6u);
  v11 = (BlobMessageMgr *)v10;
  if ( v10 )
  {
    *v10 = 0;
    v12 = v10 + 1;
    v12[1] = v12;
    *v12 = v12;
    *((_QWORD *)v11 + 3) = 0;
    *((_QWORD *)v11 + 6) = (char *)v11 + 40;
    *((_QWORD *)v11 + 5) = (char *)v11 + 40;
    *((_QWORD *)v11 + 7) = 0;
    *((_DWORD *)v11 + 16) = 0;
    *((_DWORD *)v11 + 17) = 1;
    *((_QWORD *)v11 + 9) = 0;
    *((_QWORD *)v11 + 4) = &EventAutoInternal<SuspendQueueSLock>::`vftable';
    *((_WORD *)v11 + 40) = 1;
    *((_QWORD *)v11 + 11) = 0;
  }
  else
  {
    v11 = 0;
  }
  v13 = CSatelliteSpeesExecutor::sm_pBlobMessageMgr;
  if ( CSatelliteSpeesExecutor::sm_pBlobMessageMgr != v11 && CSatelliteSpeesExecutor::sm_pBlobMessageMgr )
  {
    BlobMessageMgr::~BlobMessageMgr(CSatelliteSpeesExecutor::sm_pBlobMessageMgr);
    operator delete(v13, 0x60u);
  }
  CSatelliteSpeesExecutor::sm_pBlobMessageMgr = v11;
  v14 = operator new(0xD38u, v3, 1, "Sql\\Ntdbms\\extensibility\\satellite\\src\\SatelliteExecutor.cpp", 933, 6u);
  if ( v14 )
  {
    *v14 = &CSatelliteCargoContextBase::`vftable';
    CSQLSatelliteCommunication::CSQLSatelliteCommunication((CSQLSatelliteCommunication *)(v14 + 1));
    CSQLSatelliteCommunication::CSQLSatelliteCommunication((CSQLSatelliteCommunication *)(v14 + 203));
    v14[405] = 0;
    *((_DWORD *)v14 + 812) = 0;
    v14[407] = 0;
    v14[408] = v3;
    v14[409] = 0;
    *((_DWORD *)v14 + 820) = 0;
    v14[411] = 0;
    v14[412] = 0;
    *v14 = &CSatelliteCargoContext::`vftable';
    v14[413] = 0;
    v14[414] = 0;
    v14[415] = 0;
    v14[416] = 0;
    v14[417] = 0;
    v14[418] = 0;
    v14[421] = v14 + 420;
    v14[420] = v14 + 420;
    *((_WORD *)v14 + 1688) = 0;
    *((_BYTE *)v14 + 3378) = 0;
  }
  else
  {
    v14 = 0;
  }
  v15 = (void (__fastcall ***)(_QWORD, __int64))v14;
  v16 = (CSatelliteSessionContext *)operator new(
                                      0x130u,
                                      v3,
                                      1,
                                      "Sql\\Ntdbms\\extensibility\\satellite\\src\\SatelliteExecutor.cpp",
                                      936,
                                      6u);
  if ( v16 )
    v17 = CSatelliteSessionContext::CSatelliteSessionContext(v16);
  else
    v17 = 0;
  v43 = v17;
  if ( v46 && v14 && CSatelliteSpeesExecutor::sm_pBlobMessageMgr && v17 )
  {
    BlobMessageMgr::sm_pBlobMessageMgr = CSatelliteSpeesExecutor::sm_pBlobMessageMgr;
    CSQLSatelliteConnection::m_messageHandlerTask = (void *(*)(void *))BlobMessageMgr::MessageHandlerTask;
    v18 = operator new(0x288u, v3, 1, "Sql\\Ntdbms\\extensibility\\satellite\\src\\SatelliteExecutor.cpp", 948, 6u);
    v19 = (MessageTelemetry *)v18;
    if ( v18 )
    {
      *v18 = 0;
      memset_0(v18 + 1, 0, 0x270u);
    }
    else
    {
      v19 = 0;
    }
    v44 = v19;
    if ( v19 && (int)MessageTelemetry::InitRingBuffer(v19, v3, (const struct _GUID *)this + 196) >= 0 )
    {
      _mm_lfence();
      if ( !CSatelliteCargoContext::Init((CSatelliteCargoContext *)v14) )
        goto LABEL_60;
      v20 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v21 = *(_QWORD *)(v20 + 256);
      if ( !v21 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v21 = *(_QWORD *)(v20 + 256);
      }
      v22 = v46;
      v2 = CSQLSatelliteSessionBasedMsgQueueConnection::Init(v46, *(struct IMemObj **)(*(_QWORD *)(v21 + 992) + 320LL));
      if ( v2 < 0 )
        goto LABEL_60;
      v23 = (char *)CSatelliteGlobalContext::sm_memoryClerk + 64;
      if ( !CSatelliteGlobalContext::sm_memoryClerk )
        v23 = 0;
      LOWORD(v42) = 128;
      MemObject = MemoryObjectFactory::CreateMemObject(319, 6, v23, 8, v42);
      if ( MemObject )
      {
        _mm_lfence();
        *((_QWORD *)this + 263) = MemObject;
        v43 = 0;
        if ( *((CSatelliteSessionContext **)this + 260) != v17 )
        {
          _mm_lfence();
          v25 = (void *)*((_QWORD *)this + 260);
          if ( v25 )
          {
            CSatelliteSessionContext::~CSatelliteSessionContext(*((CSatelliteSessionContext **)this + 260));
            operator delete(v25, 0x130u);
          }
          v22 = v46;
        }
        *((_QWORD *)this + 260) = v17;
        *(_QWORD *)v17 = *((_QWORD *)this + 263);
        v44 = 0;
        v26 = *((_QWORD *)this + 260);
        v27 = *(MessageTelemetry **)(v26 + 296);
        if ( v27 != v19 && v27 )
          MessageTelemetry::`scalar deleting destructor'(v27, 1u);
        *(_QWORD *)(v26 + 296) = v19;
        *(_OWORD *)(*((_QWORD *)this + 260) + 8LL) = *((_OWORD *)this + 196);
        v45 = 0;
        CAutoRefc<CSQLSatelliteSessionBasedMsgQueueConnection>::operator=((char *)this + 2056, v22);
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 257) + 32LL));
        v28 = -1;
        do
          ++v28;
        while ( *((_WORD *)this + v28 + 1311) );
        if ( v28 )
        {
          _mm_lfence();
          v29 = (CSatelliteSpeesExecutor *)(*((_QWORD *)this + 257) + 402LL);
          v30 = 255;
          v31 = (char *)(this - v29);
          do
          {
            if ( v30 == -2147483391 )
              break;
            v32 = *(_WORD *)((char *)v29 + (_QWORD)v31 + 2622);
            if ( !v32 )
              break;
            *(_WORD *)v29 = v32;
            v29 = (CSatelliteSpeesExecutor *)((char *)v29 + 2);
            --v30;
          }
          while ( v30 );
          v33 = (CSatelliteSpeesExecutor *)((char *)v29 - 2);
          if ( v30 )
            v33 = v29;
          *(_WORD *)v33 = 0;
        }
        v34 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v35 = *(_QWORD *)(v34 + 256);
        if ( !v35 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v35 = *(_QWORD *)(v34 + 256);
        }
        v36 = *((_QWORD *)this + 257);
        v37 = CSatelliteSpeesExecutor::sm_pBlobMessageMgr;
        *(_QWORD *)CSatelliteSpeesExecutor::sm_pBlobMessageMgr = *(_QWORD *)(*(_QWORD *)(v35 + 992) + 320LL);
        *((_BYTE *)v37 + 80) = 1;
        CAutoRefc<CSQLSatelliteSessionBasedMsgQueueConnection>::operator=((char *)v37 + 88, v36);
        *((_QWORD *)v37 + 2) = (char *)v37 + 8;
        *((_QWORD *)v37 + 1) = (char *)v37 + 8;
        *((_BYTE *)v37 + 81) = 1;
        v15 = 0;
        if ( *((_QWORD **)this + 259) != v14 )
        {
          _mm_lfence();
          v38 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 259);
          if ( v38 )
            (**v38)(v38, 1);
          v15 = 0;
        }
        *((_QWORD *)this + 259) = v14;
        v2 = 0;
        *((_BYTE *)this + 3152) = 1;
      }
      else
      {
LABEL_60:
        v15 = (void (__fastcall ***)(_QWORD, __int64))v14;
      }
      v19 = v44;
      v17 = v43;
    }
    if ( v19 )
      MessageTelemetry::`scalar deleting destructor'(v19, 1u);
  }
  if ( v17 )
  {
    CSatelliteSessionContext::~CSatelliteSessionContext(v17);
    operator delete(v17, 0x130u);
  }
  if ( v15 )
    (**v15)(v15, 1);
  v39 = v45;
  if ( v45 && _InterlockedExchangeAdd((volatile signed __int32 *)v45 + 8, 0xFFFFFFFF) == 1 )
  {
    if ( *((_QWORD *)v45 + 2) )
    {
      TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(*((_QWORD *)v45 + 3), v45);
      v40 = *(_QWORD *)v45;
      v39 = v45;
    }
    else
    {
      v40 = *(_QWORD *)v45;
    }
    (*(void (__fastcall **)(CSQLSatelliteSessionBasedMsgQueueConnection *))(v40 + 24))(v39);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x10040a520  push    rbp
0x10040a522  push    rsi
0x10040a523  push    rdi
0x10040a524  push    r12
0x10040a526  push    r13
0x10040a528  push    r14
0x10040a52a  push    r15
0x10040a52c  mov     rbp, rsp
0x10040a52f  sub     rsp, 70h
0x10040a533  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x10040a53b  mov     [rsp+70h+arg_0], rbx
0x10040a543  mov     r13, rcx
0x10040a546  mov     r15d, 8007000Eh
0x10040a54c  mov     r12, cs:?sm_pmo@CSatelliteGlobalContext@@0PEAVIMemObj@@EA; IMemObj * CSatelliteGlobalContext::sm_pmo
0x10040a553  mov     [rbp+var_20], r12
0x10040a557  mov     [rbp+arg_8], 39Eh
0x10040a55e  mov     r8, gs:58h
0x10040a567  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040a56e  mov     edx, [rax]
0x10040a570  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040a577  mov     ebx, [rax]
0x10040a579  add     rbx, [r8+rdx*8]
0x10040a57d  mov     rax, [rbx+100h]
0x10040a584  test    rax, rax
0x10040a587  jnz     short loc_10040A598
0x10040a589  xor     ecx, ecx
0x10040a58b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040a591  mov     rax, [rbx+100h]
0x10040a598  mov     rax, [rax+3E0h]
0x10040a59f  mov     rdx, [rax+140h]
0x10040a5a6  mov     [rbp+var_18], rdx
0x10040a5aa  mov     [rsp+70h+var_48], 6
0x10040a5af  mov     [rsp+70h+var_50], 39Eh
0x10040a5b7  lea     r9, aSqlNtdbmsExten; "Sql\\Ntdbms\\extensibility\\satellite\\"...
0x10040a5be  mov     ecx, 450h
0x10040a5c3  mov     r8d, 1
0x10040a5c9  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10040a5cf  mov     [rbp+var_10], rax
0x10040a5d3  xor     esi, esi
0x10040a5d5  test    rax, rax
0x10040a5d8  jz      short loc_10040A5E4
0x10040a5da  mov     rcx, rax; this
0x10040a5dd  call    ??0CSQLSatelliteSessionBasedMsgQueueConnection@@QEAA@XZ; CSQLSatelliteSessionBasedMsgQueueConnection::CSQLSatelliteSessionBasedMsgQueueConnection(void)
0x10040a5e2  jmp     short loc_10040A5E7
0x10040a5e4  mov     rax, rsi
0x10040a5e7  mov     [rbp+arg_10], rax
0x10040a5eb  mov     [rbp+var_30], rax
0x10040a5ef  mov     [rbp+arg_8], 3A0h
0x10040a5f6  mov     rdx, gs:58h
0x10040a5ff  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040a606  mov     ecx, [rax]
0x10040a608  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040a60f  mov     ebx, [rax]
0x10040a611  add     rbx, [rdx+rcx*8]
0x10040a615  mov     rax, [rbx+100h]
0x10040a61c  test    rax, rax
0x10040a61f  jnz     short loc_10040A630
0x10040a621  xor     ecx, ecx
0x10040a623  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040a629  mov     rax, [rbx+100h]
0x10040a630  mov     rax, [rax+3E0h]
0x10040a637  mov     rdx, [rax+140h]
0x10040a63e  mov     [rbp+var_10], rdx
0x10040a642  mov     [rsp+70h+var_48], 6
0x10040a647  mov     [rsp+70h+var_50], 3A0h
0x10040a64f  lea     r9, aSqlNtdbmsExten; "Sql\\Ntdbms\\extensibility\\satellite\\"...
0x10040a656  mov     ecx, 60h ; '`'
0x10040a65b  lea     r8d, [rcx-5Fh]
0x10040a65f  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10040a665  mov     rbx, rax
0x10040a668  mov     [rbp+var_18], rax
0x10040a66c  test    rax, rax
0x10040a66f  jz      short loc_10040A6B7
0x10040a671  mov     [rax], rsi
0x10040a674  add     rax, 8
0x10040a678  mov     [rax+8], rax
0x10040a67c  mov     [rax], rax
0x10040a67f  mov     [rbx+18h], rsi
0x10040a683  lea     rax, [rbx+28h]
0x10040a687  mov     [rax+8], rax
0x10040a68b  mov     [rax], rax
0x10040a68e  mov     [rbx+38h], rsi
0x10040a692  mov     [rbx+40h], esi
0x10040a695  mov     dword ptr [rbx+44h], 1
0x10040a69c  mov     [rbx+48h], rsi
0x10040a6a0  lea     rax, ??_7?$EventAutoInternal@USuspendQueueSLock@@@@6B@; const EventAutoInternal<SuspendQueueSLock>::`vftable'
0x10040a6a7  mov     [rbx+20h], rax
0x10040a6ab  mov     word ptr [rbx+50h], 1
0x10040a6b1  mov     [rbx+58h], rsi
0x10040a6b5  jmp     short loc_10040A6BA
0x10040a6b7  mov     rbx, rsi
0x10040a6ba  mov     rdi, cs:?sm_pBlobMessageMgr@CSatelliteSpeesExecutor@@0V?$CAutoP@VBlobMessageMgr@@@@A; CAutoP<BlobMessageMgr> CSatelliteSpeesExecutor::sm_pBlobMessageMgr
0x10040a6c1  cmp     rdi, rbx
0x10040a6c4  jz      short loc_10040A6E1
0x10040a6c6  test    rdi, rdi
0x10040a6c9  jz      short loc_10040A6E1
0x10040a6cb  mov     rcx, rdi; this
0x10040a6ce  call    ??1BlobMessageMgr@@QEAA@XZ; BlobMessageMgr::~BlobMessageMgr(void)
0x10040a6d3  mov     edx, 60h ; '`'
0x10040a6d8  mov     rcx, rdi
0x10040a6db  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10040a6e1  mov     cs:?sm_pBlobMessageMgr@CSatelliteSpeesExecutor@@0V?$CAutoP@VBlobMessageMgr@@@@A, rbx; CAutoP<BlobMessageMgr> CSatelliteSpeesExecutor::sm_pBlobMessageMgr
0x10040a6e8  mov     [rbp+arg_8], 3A5h
0x10040a6ef  mov     [rsp+70h+var_48], 6
0x10040a6f4  mov     [rsp+70h+var_50], 3A5h
0x10040a6fc  lea     r9, aSqlNtdbmsExten; "Sql\\Ntdbms\\extensibility\\satellite\\"...
0x10040a703  mov     r8d, 1
0x10040a709  mov     rdx, r12
0x10040a70c  mov     ecx, 0D38h
0x10040a711  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10040a717  mov     r14, rax
0x10040a71a  mov     [rbp+var_10], rax
0x10040a71e  test    rax, rax
0x10040a721  jz      loc_10040A7D6
0x10040a727  lea     rax, ??_7CSatelliteCargoContextBase@@6B@; const CSatelliteCargoContextBase::`vftable'
0x10040a72e  mov     [r14], rax
0x10040a731  lea     rcx, [r14+8]; this
0x10040a735  call    ??0CSQLSatelliteCommunication@@QEAA@XZ; CSQLSatelliteCommunication::CSQLSatelliteCommunication(void)
0x10040a73a  nop
0x10040a73b  lea     rcx, [r14+658h]; this
0x10040a742  call    ??0CSQLSatelliteCommunication@@QEAA@XZ; CSQLSatelliteCommunication::CSQLSatelliteCommunication(void)
0x10040a747  nop
0x10040a748  mov     [r14+0CA8h], rsi
0x10040a74f  mov     [r14+0CB0h], esi
0x10040a756  mov     [r14+0CB8h], rsi
0x10040a75d  mov     [r14+0CC0h], r12
0x10040a764  mov     [r14+0CC8h], rsi
0x10040a76b  mov     [r14+0CD0h], esi
0x10040a772  mov     [r14+0CD8h], rsi
0x10040a779  mov     [r14+0CE0h], rsi
0x10040a780  lea     rax, ??_7CSatelliteCargoContext@@6B@; const CSatelliteCargoContext::`vftable'
0x10040a787  mov     [r14], rax
0x10040a78a  mov     [r14+0CE8h], rsi
0x10040a791  mov     [r14+0CF0h], rsi
0x10040a798  mov     [r14+0CF8h], rsi
0x10040a79f  mov     [r14+0D00h], rsi
0x10040a7a6  mov     [r14+0D08h], rsi
0x10040a7ad  mov     [r14+0D10h], rsi
0x10040a7b4  lea     rax, [r14+0D20h]
0x10040a7bb  mov     [rax+8], rax
0x10040a7bf  mov     [rax], rax
0x10040a7c2  mov     word ptr [r14+0D30h], 0
0x10040a7cc  mov     byte ptr [r14+0D32h], 0
0x10040a7d4  jmp     short loc_10040A7D9
0x10040a7d6  mov     r14, rsi
0x10040a7d9  mov     rsi, r14
0x10040a7dc  mov     [rbp+arg_18], r14
0x10040a7e0  mov     [rbp+arg_8], 3A8h
0x10040a7e7  mov     [rsp+70h+var_48], 6
0x10040a7ec  mov     [rsp+70h+var_50], 3A8h
0x10040a7f4  lea     r9, aSqlNtdbmsExten; "Sql\\Ntdbms\\extensibility\\satellite\\"...
0x10040a7fb  mov     r8d, 1
0x10040a801  mov     rdx, r12
0x10040a804  mov     ecx, 130h
0x10040a809  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10040a80f  mov     [rbp+var_10], rax
0x10040a813  test    rax, rax
0x10040a816  jz      short loc_10040A825
0x10040a818  mov     rcx, rax; this
0x10040a81b  call    ??0CSatelliteSessionContext@@QEAA@XZ; CSatelliteSessionContext::CSatelliteSessionContext(void)
0x10040a820  mov     rbx, rax
0x10040a823  jmp     short loc_10040A827
0x10040a825  xor     ebx, ebx
0x10040a827  mov     [rbp+var_40], rbx
0x10040a82b  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x10040a832  cmp     [rbp+arg_10], 0
0x10040a837  jz      loc_10040ABA1
0x10040a83d  test    r14, r14
0x10040a840  jz      loc_10040ABA1
0x10040a846  mov     rax, cs:?sm_pBlobMessageMgr@CSatelliteSpeesExecutor@@0V?$CAutoP@VBlobMessageMgr@@@@A; CAutoP<BlobMessageMgr> CSatelliteSpeesExecutor::sm_pBlobMessageMgr
0x10040a84d  test    rax, rax
0x10040a850  jz      loc_10040ABA1
0x10040a856  test    rbx, rbx
0x10040a859  jz      loc_10040ABA1
0x10040a85f  mov     cs:?sm_pBlobMessageMgr@BlobMessageMgr@@0PEAV1@EA, rax; BlobMessageMgr * BlobMessageMgr::sm_pBlobMessageMgr
0x10040a866  lea     rax, ?MessageHandlerTask@BlobMessageMgr@@SAPEAXPEAX@Z; BlobMessageMgr::MessageHandlerTask(void *)
0x10040a86d  mov     cs:?m_messageHandlerTask@CSQLSatelliteConnection@@2P6APEAXPEAX@ZEA, rax; void * (*CSQLSatelliteConnection::m_messageHandlerTask)(void *)
0x10040a874  mov     [rbp+arg_8], 3B4h
0x10040a87b  mov     [rsp+70h+var_48], 6
0x10040a880  mov     [rsp+70h+var_50], 3B4h
0x10040a888  lea     r9, aSqlNtdbmsExten; "Sql\\Ntdbms\\extensibility\\satellite\\"...
0x10040a88f  lea     r8d, [rdi+2]
0x10040a893  mov     rdx, r12
0x10040a896  mov     ecx, 288h
0x10040a89b  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10040a8a1  mov     rdi, rax
0x10040a8a4  mov     [rbp+var_10], rax
0x10040a8a8  test    rax, rax
0x10040a8ab  jz      short loc_10040A8C8
0x10040a8ad  mov     qword ptr [rax], 0
0x10040a8b4  lea     rcx, [rax+8]; void *
0x10040a8b8  xor     edx, edx; Val
0x10040a8ba  mov     r8d, 270h; Size
0x10040a8c0  call    memset_0
0x10040a8c5  nop
0x10040a8c6  jmp     short loc_10040A8CA
0x10040a8c8  xor     edi, edi
0x10040a8ca  mov     [rbp+var_38], rdi
0x10040a8ce  test    rdi, rdi
0x10040a8d1  jz      loc_10040AB88
0x10040a8d7  lea     r8, [r13+0C40h]; struct _GUID *
0x10040a8de  mov     rdx, r12; struct IMemObj *
0x10040a8e1  mov     rcx, rdi; this
0x10040a8e4  call    ?InitRingBuffer@MessageTelemetry@@QEAAJPEAVIMemObj@@AEBU_GUID@@@Z; MessageTelemetry::InitRingBuffer(IMemObj *,_GUID const &)
0x10040a8e9  test    eax, eax
0x10040a8eb  js      loc_10040AB88
0x10040a8f1  lfence
0x10040a8f4  mov     rcx, r14; this
0x10040a8f7  call    ?Init@CSatelliteCargoContext@@QEAA_NXZ; CSatelliteCargoContext::Init(void)
0x10040a8fc  test    al, al
0x10040a8fe  jz      loc_10040AB7C
0x10040a904  mov     rdx, gs:58h
0x10040a90d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040a914  mov     ecx, [rax]
0x10040a916  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040a91d  mov     esi, [rax]
0x10040a91f  add     rsi, [rdx+rcx*8]
0x10040a923  mov     rax, [rsi+100h]
0x10040a92a  test    rax, rax
0x10040a92d  jnz     short loc_10040A93E
0x10040a92f  xor     ecx, ecx
0x10040a931  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040a937  mov     rax, [rsi+100h]
0x10040a93e  mov     rax, [rax+3E0h]
0x10040a945  mov     rdx, [rax+140h]; struct IMemObj *
0x10040a94c  mov     rsi, [rbp+arg_10]
0x10040a950  mov     rcx, rsi; this
0x10040a953  call    ?Init@CSQLSatelliteSessionBasedMsgQueueConnection@@QEAAJPEAVIMemObj@@@Z; CSQLSatelliteSessionBasedMsgQueueConnection::Init(IMemObj *)
0x10040a958  mov     r15d, eax
0x10040a95b  test    eax, eax
0x10040a95d  js      loc_10040AB7C
0x10040a963  mov     rcx, cs:?sm_memoryClerk@CSatelliteGlobalContext@@0PEAVMemoryClerk@@EA; MemoryClerk * CSatelliteGlobalContext::sm_memoryClerk
0x10040a96a  mov     eax, 80h
0x10040a96f  lea     r9d, [rax-78h]
0x10040a973  lea     r8, [rcx+40h]
0x10040a977  test    rcx, rcx
0x10040a97a  mov     r12d, 0
0x10040a980  cmovz   r8, r12
0x10040a984  mov     word ptr [rsp+70h+var_50], ax
0x10040a989  lea     edx, [rax-7Ah]
0x10040a98c  mov     ecx, 13Fh
0x10040a991  call    cs:__imp_?CreateMemObject@MemoryObjectFactory@@SAPEAVIMemObj@@W4SOSHOST_MEMOBJ_ID@@KPEAVPageAllocator@@FF@Z; MemoryObjectFactory::CreateMemObject(SOSHOST_MEMOBJ_ID,ulong,PageAllocator *,short,short)
0x10040a997  test    rax, rax
0x10040a99a  jz      loc_10040AB7C
0x10040a9a0  lfence
0x10040a9a3  mov     [r13+838h], rax
0x10040a9aa  mov     [rbp+var_40], r12
0x10040a9ae  cmp     [r13+820h], rbx
0x10040a9b5  jz      short loc_10040A9E0
0x10040a9b7  lfence
0x10040a9ba  mov     rsi, [r13+820h]
0x10040a9c1  test    rsi, rsi
0x10040a9c4  jz      short loc_10040A9DC
0x10040a9c6  mov     rcx, rsi; this
0x10040a9c9  call    ??1CSatelliteSessionContext@@QEAA@XZ; CSatelliteSessionContext::~CSatelliteSessionContext(void)
0x10040a9ce  mov     edx, 130h
0x10040a9d3  mov     rcx, rsi
0x10040a9d6  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10040a9dc  mov     rsi, [rbp+arg_10]
0x10040a9e0  mov     [r13+820h], rbx
0x10040a9e7  mov     rax, [r13+838h]
0x10040a9ee  mov     [rbx], rax
0x10040a9f1  mov     [rbp+var_38], r12
0x10040a9f5  mov     rbx, [r13+820h]
0x10040a9fc  mov     rcx, [rbx+128h]; this
0x10040aa03  cmp     rcx, rdi
0x10040aa06  jz      short loc_10040AA17
0x10040aa08  test    rcx, rcx
0x10040aa0b  jz      short loc_10040AA17
0x10040aa0d  mov     edx, 1; unsigned int
0x10040aa12  call    ??_GMessageTelemetry@@QEAAPEAXI@Z; MessageTelemetry::`scalar deleting destructor'(uint)
0x10040aa17  mov     [rbx+128h], rdi
0x10040aa1e  mov     rax, [r13+820h]
0x10040aa25  movups  xmm0, xmmword ptr [r13+0C40h]
0x10040aa2d  movups  xmmword ptr [rax+8], xmm0
0x10040aa31  mov     [rbp+var_30], r12
0x10040aa35  mov     rdx, rsi
0x10040aa38  lea     rcx, [r13+808h]
0x10040aa3f  call    ??4?$CAutoRefc@VCSQLSatelliteSessionBasedMsgQueueConnection@@@@QEAAPEAVCSQLSatelliteSessionBasedMsgQueueConnection@@PEAV1@@Z; CAutoRefc<CSQLSatelliteSessionBasedMsgQueueConnection>::operator=(CSQLSatelliteSessionBasedMsgQueueConnection *)
0x10040aa44  mov     rax, [r13+808h]
0x10040aa4b  lock inc dword ptr [rax+20h]
0x10040aa4f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10040aa56  nop     word ptr [rax+rax+00000000h]
0x10040aa60  inc     rax
0x10040aa63  cmp     [r13+rax*2+0A3Eh], r12w
0x10040aa6c  jnz     short loc_10040AA60
0x10040aa6e  test    rax, rax
0x10040aa71  jz      short loc_10040AAC6
0x10040aa73  lfence
0x10040aa76  mov     rcx, [r13+808h]
0x10040aa7d  add     rcx, 192h
0x10040aa84  mov     edx, 0FFh
0x10040aa89  mov     r8, r13
0x10040aa8c  sub     r8, rcx
0x10040aa8f  nop
0x10040aa90  lea     rax, [rdx+7FFFFEFFh]
0x10040aa97  test    rax, rax
0x10040aa9a  jz      short loc_10040AAB7
0x10040aa9c  movzx   eax, word ptr [r8+rcx+0A3Eh]
0x10040aaa5  test    ax, ax
  ... truncated ...
```
