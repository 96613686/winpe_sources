# CSQLSatelliteSessionBasedMsgQueueConnection::AddMessageToQueue(uchar *,SNI_Packet *,bool *)

- ea: `0x100475fd0`
- end: `0x10047634c`
- name: `?AddMessageToQueue@CSQLSatelliteSessionBasedMsgQueueConnection@@UEAAJPEAEPEAVSNI_Packet@@PEA_N@Z`
- size: `892`
- prototype: `__int64 __fastcall(CSQLSatelliteSessionBasedMsgQueueConnection *__hidden this, unsigned __int8 *, struct SNI_Packet *, bool *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x10040bbb0`
- `0x10040d680`
- `0x100415950`
- `0x100415a50`
- `0x100415c70`
- `0x100455f90`
- `0x100475fd0`
- `0x100476390`
- `0x100476570`
- `0x100478330`
- `0x100478670`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10047610d`
- `KERNEL32!QueryPerformanceCounter` at `0x100476160`
- `KERNEL32!QueryPerformanceCounter` at `0x10047610d`
- `KERNEL32!QueryPerformanceCounter` at `0x100476160`
- `KERNEL32!GetCurrentThreadId` at `0x1004762a0`
- `KERNEL32!GetCurrentThreadId` at `0x1004762a0`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004761cd`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100476316`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100476316`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004760fd`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10047614f`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100476122`
- `sqldk!SystemThread_TlsIndex` at `0x1004760cf`
- `sqldk!SystemThread_TlsOffset` at `0x1004760d8`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004760b0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004761d9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004761d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSQLSatelliteSessionBasedMsgQueueConnection::AddMessageToQueue(
        CSQLSatelliteSessionBasedMsgQueueConnection *this,
        unsigned __int8 *a2,
        struct SNI_Packet *a3,
        bool *a4)
{
  bool *v4; // rsi
  int MessageQueueBySessionId; // edi
  unsigned __int8 *v6; // r14
  char v7; // r13
  _DWORD *v8; // r15
  volatile signed __int64 *v9; // r14
  LARGE_INTEGER v10; // rbx
  signed __int64 UniqueThread_low; // r12
  __int64 v12; // rsi
  __int64 v13; // r8
  LARGE_INTEGER v14; // rax
  LONGLONG v15; // rcx
  char *v16; // rcx
  int v17; // eax
  struct CSQLSatelliteSessionBasedMsgQueueConnection *v18; // rbx
  CSQLSatelliteSessionBasedMsgQueueConnection *v19; // rcx
  int v20; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v22; // rsi
  bool *v24; // [rsp+20h] [rbp-E0h]
  struct CSQLSatelliteSessionBasedMsgQueueConnection *v25; // [rsp+30h] [rbp-D0h] BYREF
  char *v26; // [rsp+38h] [rbp-C8h]
  int v27; // [rsp+40h] [rbp-C0h]
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-B8h] BYREF
  LARGE_INTEGER v29; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v30; // [rsp+58h] [rbp-A8h]
  __int128 v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+78h] [rbp-88h]
  DWORD v34; // [rsp+7Ch] [rbp-84h]
  const char *v35; // [rsp+80h] [rbp-80h]
  int v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+90h] [rbp-70h]
  _BYTE v38[216]; // [rsp+A0h] [rbp-60h] BYREF
  int v39; // [rsp+178h] [rbp+78h]
  __int64 v40; // [rsp+180h] [rbp+80h]
  bool v41; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int8 *v42; // [rsp+1E8h] [rbp+E8h]
  struct SNI_Packet *v43; // [rsp+1F0h] [rbp+F0h]
  bool *v44; // [rsp+1F8h] [rbp+F8h]

  v44 = a4;
  v43 = a3;
  v42 = a2;
  v37 = -2;
  v4 = a4;
  MessageQueueBySessionId = 0;
  v6 = a2 + 8;
  v30 = a2 + 8;
  v25 = 0;
  v41 = 0;
  v7 = 0;
  *a4 = 0;
  if ( *((_BYTE *)this + 1097) )
  {
    v25 = this;
  }
  else
  {
    MessageQueueBySessionId = CSQLSatelliteSessionBasedMsgQueueConnection::GetMessageQueueBySessionId(
                                this,
                                (struct _GUID *)(a2 + 8),
                                &v25,
                                CSQLSatelliteConnection::m_messageHandlerTask != 0,
                                &v41);
    v7 = 1;
    if ( MessageQueueBySessionId < 0 )
    {
LABEL_38:
      _mm_lfence();
      v20 = *((_WORD *)v42 + 1) & 0x7FFF;
      if ( MessageQueueBySessionId != -2147023660 || v20 != 4 )
      {
        _mm_lfence();
        if ( g_extensibilityErrorRingBuffer )
        {
          CurrentThreadId = GetCurrentThreadId();
          v31 = 0;
          v32 = 0;
          v33 = MessageQueueBySessionId;
          v34 = CurrentThreadId;
          v35 = "CSQLSatelliteSessionBasedMsgQueueConnection::AddMessageToQueue";
          v36 = 6960;
          v22 = g_extensibilityErrorRingBuffer;
          v39 = 0;
          v40 = 0;
          if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
            StackFrames<24>::CaptureCurrent(v38, 1);
          if ( (dword_1005113AC & 0x10) != 0 )
            ExtensibilityErrorRecord::FireMatchingEvent(&v31, v38);
          SOS_RingBuffer::StoreRecordInternalWithoutEvent(v22, &v31, v38);
        }
        LODWORD(v24) = v20;
        FireTraceEvent(
          1,
          (unsigned int)MessageQueueBySessionId,
          v6,
          L"AddMessageToQueue failed. MessageType: %d.\n",
          v24);
      }
      return (unsigned int)MessageQueueBySessionId;
    }
    this = v25;
  }
  v8 = (_DWORD *)((char *)this + 80);
  v9 = (volatile signed __int64 *)((char *)this + 72);
  v26 = (char *)this + 72;
  v27 = 0;
  v10.QuadPart = 0;
  UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
  if ( *((_DWORD *)this + 18) || _InterlockedCompareExchange64(v9, UniqueThread_low, 0) )
  {
    v12 = 0;
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
    {
      v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( v13 && *(_QWORD *)(v13 + 272) == v13 )
        v12 = *(_QWORD *)(v13 + 256);
      if ( v12 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v10 = PerformanceCount;
        }
        else
        {
          v10.QuadPart = MEMORY[0x7FFE0008];
        }
      }
    }
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<8,19,258>::SpinToAcquireWithExponentialBackoff(v9, UniqueThread_low);
    else
      Spinlock<8,19,258>::SpinToAcquireOptimistic(v9, v12, UniqueThread_low);
    if ( v12 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v29);
        v14 = v29;
      }
      else
      {
        v14.QuadPart = MEMORY[0x7FFE0008];
      }
      v15 = v14.QuadPart - v10.QuadPart;
      if ( v14.QuadPart < (unsigned __int64)v10.QuadPart )
        v15 = 0;
      *(_QWORD *)(v12 + 3192) += v15;
      v4 = v44;
    }
    else
    {
      v4 = v44;
    }
  }
  v27 = 1;
  ++v8[4];
  v16 = (char *)v43 + 56;
  *((_QWORD *)v43 + 7) = *(_QWORD *)v8;
  *(_QWORD *)(*(_QWORD *)v8 + 8LL) = v16;
  *(_QWORD *)v8 = v16;
  *((_QWORD *)v16 + 1) = v8;
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v17 = rand();
    if ( v17 == 5 * (v17 / 5) )
      Spinlock<8,19,258>::UpdateStatSnapshot();
  }
  *v9 = 0;
  v26 = 0;
  v27 = 0;
  v18 = v25;
  EventAutoInternal<SuspendQueueSLock>::SignalAll((char *)v25 + 104);
  *v4 = 1;
  if ( v41 )
    MessageQueueBySessionId = CSQLSatelliteSessionBasedMsgQueueConnection::EnqueueTaskAndAssociateMessageQueue(v19, v18);
  if ( v7 && _InterlockedExchangeAdd((volatile signed __int32 *)v18 + 8, 0xFFFFFFFF) == 1 )
  {
    if ( *((_QWORD *)v18 + 2) )
      TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(*((_QWORD *)v18 + 3), v18);
    (*(void (__fastcall **)(struct CSQLSatelliteSessionBasedMsgQueueConnection *))(*(_QWORD *)v18 + 24LL))(v18);
  }
  if ( MessageQueueBySessionId < 0 )
  {
    v6 = v30;
    goto LABEL_38;
  }
  return (unsigned int)MessageQueueBySessionId;
}

```

## disassembly

```asm
0x100475fd0  mov     [rsp-8+arg_18], r9
0x100475fd5  mov     [rsp-8+arg_10], r8
0x100475fda  mov     [rsp-8+arg_8], rdx
0x100475fdf  push    rbp
0x100475fe0  push    rbx
0x100475fe1  push    rsi
0x100475fe2  push    rdi
0x100475fe3  push    r12
0x100475fe5  push    r13
0x100475fe7  push    r14
0x100475fe9  push    r15
0x100475feb  lea     rbp, [rsp-98h]
0x100475ff3  sub     rsp, 198h
0x100475ffa  mov     [rbp+0D0h+var_140], 0FFFFFFFFFFFFFFFEh
0x100476002  mov     rsi, r9
0x100476005  xor     r12d, r12d
0x100476008  mov     edi, r12d
0x10047600b  lea     r14, [rdx+8]
0x10047600f  mov     [rsp+1D0h+var_178], r14
0x100476014  mov     [rsp+1D0h+var_1A0], r12
0x100476019  mov     [rbp+0D0h+arg_0], dil
0x100476020  mov     al, 1
0x100476022  xor     r13b, r13b
0x100476025  mov     [r9], dil
0x100476028  movzx   eax, al
0x10047602b  cmp     cs:?m_messageHandlerTask@CSQLSatelliteConnection@@2P6APEAXPEAX@ZEA, rdi; void * (*CSQLSatelliteConnection::m_messageHandlerTask)(void *)
0x100476032  cmovz   eax, r12d
0x100476036  cmp     [rcx+449h], dil
0x10047603d  jz      short loc_100476046
0x10047603f  mov     [rsp+1D0h+var_1A0], rcx
0x100476044  jmp     short loc_100476075
0x100476046  lea     rdx, [rbp+0D0h+arg_0]
0x10047604d  mov     [rsp+1D0h+var_1B0], rdx; bool *
0x100476052  movzx   r9d, al; bool
0x100476056  lea     r8, [rsp+1D0h+var_1A0]; struct CSQLSatelliteSessionBasedMsgQueueConnection **
0x10047605b  mov     rdx, r14; struct _GUID *
0x10047605e  call    ?GetMessageQueueBySessionId@CSQLSatelliteSessionBasedMsgQueueConnection@@QEAAJPEAU_GUID@@PEAPEAV1@_NPEA_N@Z; CSQLSatelliteSessionBasedMsgQueueConnection::GetMessageQueueBySessionId(_GUID *,CSQLSatelliteSessionBasedMsgQueueConnection * *,bool,bool *)
0x100476063  mov     edi, eax
0x100476065  mov     r13b, 1
0x100476068  test    eax, eax
0x10047606a  js      loc_10047626E
0x100476070  mov     rcx, [rsp+1D0h+var_1A0]
0x100476075  lea     r15, [rcx+50h]
0x100476079  lea     r14, [rcx+48h]
0x10047607d  mov     [rsp+1D0h+var_198], r14
0x100476082  mov     [rsp+1D0h+var_190], r12d
0x100476087  mov     rbx, r12
0x10047608a  mov     eax, gs:48h
0x100476092  mov     r12d, eax
0x100476095  mov     eax, [r14]
0x100476098  test    eax, eax
0x10047609a  jnz     short loc_1004760B0
0x10047609c  xor     eax, eax
0x10047609e  lock cmpxchg [r14], r12
0x1004760a3  mov     eax, ebx
0x1004760a5  setz    al
0x1004760a8  test    eax, eax
0x1004760aa  jnz     loc_10047619F
0x1004760b0  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004760b7  mov     ecx, [rax]
0x1004760b9  and     ecx, 84h
0x1004760bf  xor     esi, esi
0x1004760c1  cmp     cl, 84h
0x1004760c4  jnz     short loc_100476122
0x1004760c6  mov     rdx, gs:58h
0x1004760cf  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004760d6  mov     ecx, [rax]
0x1004760d8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004760df  mov     r8d, [rax]
0x1004760e2  add     r8, [rdx+rcx*8]
0x1004760e6  jz      short loc_1004760F8
0x1004760e8  cmp     [r8+110h], r8
0x1004760ef  jnz     short loc_1004760F8
0x1004760f1  mov     rsi, [r8+100h]
0x1004760f8  test    rsi, rsi
0x1004760fb  jz      short loc_100476122
0x1004760fd  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100476104  cmp     [rax], ebx
0x100476106  jz      short loc_10047611A
0x100476108  lea     rcx, [rsp+1D0h+PerformanceCount]; lpPerformanceCount
0x10047610d  call    cs:__imp_QueryPerformanceCounter
0x100476113  mov     rbx, qword ptr [rsp+1D0h+PerformanceCount]
0x100476118  jmp     short loc_100476122
0x10047611a  mov     rbx, ds:7FFE0008h
0x100476122  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100476129  mov     rcx, r14
0x10047612c  cmp     byte ptr [rax+0C7h], 0
0x100476133  jge     short loc_100476142
0x100476135  mov     r8, r12
0x100476138  mov     rdx, rsi
0x10047613b  call    ?SpinToAcquireOptimistic@?$Spinlock@$07$0BD@$0BAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<8,19,258>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x100476140  jmp     short loc_10047614A
0x100476142  mov     rdx, r12
0x100476145  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$07$0BD@$0BAC@@@AEAAX_K@Z; Spinlock<8,19,258>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x10047614a  test    rsi, rsi
0x10047614d  jz      short loc_100476198
0x10047614f  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100476156  cmp     dword ptr [rax], 0
0x100476159  jz      short loc_10047616D
0x10047615b  lea     rcx, [rsp+1D0h+var_180]; lpPerformanceCount
0x100476160  call    cs:__imp_QueryPerformanceCounter
0x100476166  mov     rax, qword ptr [rsp+1D0h+var_180]
0x10047616b  jmp     short loc_100476175
0x10047616d  mov     rax, ds:7FFE0008h
0x100476175  mov     rcx, rax
0x100476178  sub     rcx, rbx
0x10047617b  cmp     rax, rbx
0x10047617e  mov     r12d, 0
0x100476184  cmovb   rcx, r12
0x100476188  add     [rsi+0C78h], rcx
0x10047618f  mov     rsi, [rbp+0D0h+arg_18]
0x100476196  jmp     short loc_1004761A2
0x100476198  mov     rsi, [rbp+0D0h+arg_18]
0x10047619f  xor     r12d, r12d
0x1004761a2  mov     [rsp+1D0h+var_190], 1
0x1004761aa  inc     dword ptr [r15+10h]
0x1004761ae  mov     rcx, [rbp+0D0h+arg_10]
0x1004761b5  add     rcx, 38h ; '8'
0x1004761b9  mov     rax, [r15]
0x1004761bc  mov     [rcx], rax
0x1004761bf  mov     rax, [r15]
0x1004761c2  mov     [rax+8], rcx
0x1004761c6  mov     [r15], rcx
0x1004761c9  mov     [rcx+8], r15
0x1004761cd  mov     rax, cs:__imp_?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_SpinlockStatSnapshot
0x1004761d4  cmp     byte ptr [rax], 0
0x1004761d7  jz      short loc_100476200
0x1004761d9  call    cs:__imp_rand
0x1004761df  mov     r8d, eax
0x1004761e2  mov     eax, 66666667h
0x1004761e7  imul    r8d
0x1004761ea  sar     edx, 1
0x1004761ec  mov     ecx, edx
0x1004761ee  shr     ecx, 1Fh
0x1004761f1  add     edx, ecx
0x1004761f3  lea     ecx, [rdx+rdx*4]
0x1004761f6  cmp     r8d, ecx
0x1004761f9  jnz     short loc_100476200
0x1004761fb  call    ?UpdateStatSnapshot@?$Spinlock@$07$0BD@$0BAC@@@AEAAXXZ; Spinlock<8,19,258>::UpdateStatSnapshot(void)
0x100476200  mov     [r14], r12
0x100476203  mov     [rsp+1D0h+var_198], r12
0x100476208  mov     [rsp+1D0h+var_190], r12d
0x10047620d  mov     rbx, [rsp+1D0h+var_1A0]
0x100476212  lea     rcx, [rbx+68h]
0x100476216  call    ?SignalAll@?$EventAutoInternal@USuspendQueueSLock@@@@QEAAXXZ; EventAutoInternal<SuspendQueueSLock>::SignalAll(void)
0x10047621b  mov     byte ptr [rsi], 1
0x10047621e  cmp     [rbp+0D0h+arg_0], 0
0x100476225  jz      short loc_100476231
0x100476227  mov     rdx, rbx; struct CSQLSatelliteSessionBasedMsgQueueConnection *
0x10047622a  call    ?EnqueueTaskAndAssociateMessageQueue@CSQLSatelliteSessionBasedMsgQueueConnection@@QEAAJPEAV1@@Z; CSQLSatelliteSessionBasedMsgQueueConnection::EnqueueTaskAndAssociateMessageQueue(CSQLSatelliteSessionBasedMsgQueueConnection *)
0x10047622f  mov     edi, eax
0x100476231  test    r13b, r13b
0x100476234  jz      short loc_100476261
0x100476236  mov     eax, 0FFFFFFFFh
0x10047623b  lock xadd [rbx+20h], eax
0x100476240  cmp     eax, 1
0x100476243  jnz     short loc_100476261
0x100476245  cmp     qword ptr [rbx+10h], 0
0x10047624a  jz      short loc_100476258
0x10047624c  mov     rdx, rbx
0x10047624f  mov     rcx, [rbx+18h]
0x100476253  call    ?RemoveElem@?$TList@VSqlSatelliteConnectionList@@VCSQLSatelliteConnection@@$07UTListSLock@@@@QEAAXPEAVCSQLSatelliteConnection@@@Z; TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(CSQLSatelliteConnection *)
0x100476258  mov     rax, [rbx]
0x10047625b  mov     rcx, rbx
0x10047625e  call    qword ptr [rax+18h]
0x100476261  test    edi, edi
0x100476263  jns     loc_100476336
0x100476269  mov     r14, [rsp+1D0h+var_178]
0x10047626e  lfence
0x100476271  mov     rax, [rbp+0D0h+arg_8]
0x100476278  movzx   ebx, word ptr [rax+2]
0x10047627c  and     ebx, 7FFFh
0x100476282  cmp     edi, 800704D4h
0x100476288  jnz     short loc_100476293
0x10047628a  cmp     ebx, 4
0x10047628d  jz      loc_100476336
0x100476293  lfence
0x100476296  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x10047629e  jz      short loc_10047631C
0x1004762a0  call    cs:__imp_GetCurrentThreadId
0x1004762a6  xorps   xmm0, xmm0
0x1004762a9  xor     ecx, ecx
0x1004762ab  movups  [rsp+1D0h+var_170], xmm0
0x1004762b0  mov     [rsp+1D0h+var_160], rcx
0x1004762b5  mov     [rsp+1D0h+var_158], edi
0x1004762b9  mov     [rsp+1D0h+var_154], eax
0x1004762bd  lea     rax, aCsqlsatellites_0; "CSQLSatelliteSessionBasedMsgQueueConnec"...
0x1004762c4  mov     [rbp+0D0h+var_150], rax
0x1004762c8  mov     [rbp+0D0h+var_148], 1B30h
0x1004762cf  mov     rsi, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x1004762d6  mov     [rbp+0D0h+var_58], r12d
0x1004762da  mov     [rbp+0D0h+var_50], r12
0x1004762e1  cmp     [rsi+40h], rcx
0x1004762e5  jz      short loc_1004762F3
0x1004762e7  lea     edx, [rcx+1]
0x1004762ea  lea     rcx, [rbp+0D0h+var_130]
0x1004762ee  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x1004762f3  test    byte ptr cs:dword_1005113AC, 10h
0x1004762fa  jz      short loc_10047630A
0x1004762fc  lea     rdx, [rbp+0D0h+var_130]
0x100476300  lea     rcx, [rsp+1D0h+var_170]
0x100476305  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x10047630a  lea     r8, [rbp+0D0h+var_130]
0x10047630e  lea     rdx, [rsp+1D0h+var_170]
0x100476313  mov     rcx, rsi
0x100476316  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x10047631c  mov     dword ptr [rsp+1D0h+var_1B0], ebx
0x100476320  lea     r9, aAddmessagetoqu; "AddMessageToQueue failed. MessageType: "...
0x100476327  mov     r8, r14
0x10047632a  mov     edx, edi
0x10047632c  mov     ecx, 1
0x100476331  call    ?FireTraceEvent@@YAXW4ExtensibilityTraceLevel@@JPEBU_GUID@@PEB_WZZ; FireTraceEvent(ExtensibilityTraceLevel,long,_GUID const *,wchar_t const *,...)
0x100476336  mov     eax, edi
0x100476338  add     rsp, 198h
0x10047633f  pop     r15
0x100476341  pop     r14
0x100476343  pop     r13
0x100476345  pop     r12
0x100476347  pop     rdi
0x100476348  pop     rsi
0x100476349  pop     rbx
0x10047634a  pop     rbp
0x10047634b  retn
```
