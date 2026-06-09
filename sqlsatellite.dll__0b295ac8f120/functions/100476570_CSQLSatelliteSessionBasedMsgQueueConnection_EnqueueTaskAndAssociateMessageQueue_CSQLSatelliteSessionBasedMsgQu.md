# CSQLSatelliteSessionBasedMsgQueueConnection::EnqueueTaskAndAssociateMessageQueue(CSQLSatelliteSessionBasedMsgQueueConnection *)

- ea: `0x100476570`
- end: `0x100476735`
- name: `?EnqueueTaskAndAssociateMessageQueue@CSQLSatelliteSessionBasedMsgQueueConnection@@QEAAJPEAV1@@Z`
- size: `453`
- prototype: `__int64 __fastcall(CSQLSatelliteSessionBasedMsgQueueConnection *__hidden this, struct CSQLSatelliteSessionBasedMsgQueueConnection *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x100475fd0`

## callees

- `0x10040bbb0`
- `0x10040bd60`
- `0x100455f90`
- `0x100476570`
- `0x100477b20`
- `0x100478330`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x10047665c`
- `KERNEL32!GetCurrentThreadId` at `0x10047665c`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004766dc`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004766dc`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x100476646`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x100476646`
- `sqldk!SystemThread_TlsIndex` at `0x1004765e1`
- `sqldk!SystemThread_TlsOffset` at `0x1004765ea`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100476603`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100476603`

## string_xrefs

- `0x100476679`: `CSQLSatelliteSessionBasedMsgQueueConnection::EnqueueTaskAndAssociateMessageQueue`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSQLSatelliteSessionBasedMsgQueueConnection::EnqueueTaskAndAssociateMessageQueue(
        CSQLSatelliteSessionBasedMsgQueueConnection *this,
        struct CSQLSatelliteSessionBasedMsgQueueConnection *a2)
{
  unsigned int v3; // esi
  signed __int32 i; // ecx
  void *(*v5)(void *); // rbp
  __int64 v6; // rdi
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rdi
  __int128 v12; // [rsp+30h] [rbp-148h] BYREF
  __int64 v13; // [rsp+40h] [rbp-138h]
  unsigned int v14; // [rsp+48h] [rbp-130h]
  DWORD CurrentThreadId; // [rsp+4Ch] [rbp-12Ch]
  const char *v16; // [rsp+50h] [rbp-128h]
  int v17; // [rsp+58h] [rbp-120h]
  __int64 v18; // [rsp+60h] [rbp-118h]
  _BYTE v19[216]; // [rsp+70h] [rbp-108h] BYREF
  int v20; // [rsp+148h] [rbp-30h]
  __int64 v21; // [rsp+150h] [rbp-28h]
  __int64 v22; // [rsp+188h] [rbp+10h] BYREF

  v18 = -2;
  v3 = 0;
  v22 = 0;
  for ( i = *((_DWORD *)a2 + 8); i; i = *((_DWORD *)a2 + 8) )
  {
    if ( i == _InterlockedCompareExchange((volatile signed __int32 *)a2 + 8, i + 1, i) )
      break;
    _mm_pause();
  }
  v5 = CSQLSatelliteConnection::m_messageHandlerTask;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = SOS_Node::EnqueueTaskDirect(*(_QWORD *)(v7 + 992), v5, a2, 512, &v22, 0);
  v9 = v8;
  if ( v8 )
  {
    v3 = HRESULT_FROM_SOS_RESULT_Uncommon(v8);
    if ( g_extensibilityErrorRingBuffer )
    {
      v12 = 0;
      v13 = 0;
      v14 = v9;
      CurrentThreadId = GetCurrentThreadId();
      v16 = "CSQLSatelliteSessionBasedMsgQueueConnection::EnqueueTaskAndAssociateMessageQueue";
      v17 = 7187;
      v10 = g_extensibilityErrorRingBuffer;
      v20 = 0;
      v21 = 0;
      if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
        StackFrames<24>::CaptureCurrent(v19, 1);
      if ( (dword_1005113AC & 0x10) != 0 )
        ExtensibilityErrorRecord::FireMatchingEvent(&v12, v19);
      SOS_RingBuffer::StoreRecordInternalWithoutEvent(v10, &v12, v19);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 8, 0xFFFFFFFF) == 1 )
    {
      if ( *((_QWORD *)a2 + 2) )
        TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(*((_QWORD *)a2 + 3), a2);
      (*(void (__fastcall **)(struct CSQLSatelliteSessionBasedMsgQueueConnection *))(*(_QWORD *)a2 + 24LL))(a2);
    }
  }
  CAutoRefc<SOS_Task>::~CAutoRefc<SOS_Task>(&v22);
  return v3;
}

```

## disassembly

```asm
0x100476570  mov     rax, rsp
0x100476573  push    rsi
0x100476574  push    rdi
0x100476575  push    r14
0x100476577  sub     rsp, 160h
0x10047657e  mov     [rsp+178h+var_118], 0FFFFFFFFFFFFFFFEh
0x100476587  mov     [rax+18h], rbx
0x10047658b  mov     [rax+20h], rbp
0x10047658f  mov     rbx, rdx
0x100476592  xor     r14d, r14d
0x100476595  mov     esi, r14d
0x100476598  mov     [rax+10h], r14
0x10047659c  mov     ecx, [rdx+20h]
0x10047659f  test    ecx, ecx
0x1004765a1  jz      short loc_1004765C7
0x1004765a3  nop     dword ptr [rax+00h]
0x1004765a7  nop     word ptr [rax+rax+00000000h]
0x1004765b0  lea     edx, [rcx+1]
0x1004765b3  mov     eax, ecx
0x1004765b5  lock cmpxchg [rbx+20h], edx
0x1004765ba  cmp     ecx, eax
0x1004765bc  jz      short loc_1004765CA
0x1004765be  pause
0x1004765c0  mov     ecx, [rbx+20h]
0x1004765c3  test    ecx, ecx
0x1004765c5  jnz     short loc_1004765B0
0x1004765c7  mov     edx, r14d
0x1004765ca  mov     [rsp+178h+arg_0], edx
0x1004765d1  mov     rbp, cs:?m_messageHandlerTask@CSQLSatelliteConnection@@2P6APEAXPEAX@ZEA; void * (*CSQLSatelliteConnection::m_messageHandlerTask)(void *)
0x1004765d8  mov     rdx, gs:58h
0x1004765e1  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004765e8  mov     ecx, [rax]
0x1004765ea  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004765f1  mov     edi, [rax]
0x1004765f3  add     rdi, [rdx+rcx*8]
0x1004765f7  mov     rcx, [rdi+100h]
0x1004765fe  test    rcx, rcx
0x100476601  jnz     short loc_100476610
0x100476603  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100476609  mov     rcx, [rdi+100h]
0x100476610  mov     [rsp+178h+var_150], r14
0x100476615  lea     rax, [rsp+178h+arg_8]
0x10047661d  mov     [rsp+178h+var_158], rax
0x100476622  mov     r9d, 200h
0x100476628  mov     r8, rbx
0x10047662b  mov     rdx, rbp
0x10047662e  mov     rcx, [rcx+3E0h]
0x100476635  call    ?EnqueueTaskDirect@SOS_Node@@QEAA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@PEAPEAX@Z; SOS_Node::EnqueueTaskDirect(void * (*)(void *),void *,ulong,SOS_Task * *,void * *)
0x10047663a  mov     edi, eax
0x10047663c  test    eax, eax
0x10047663e  jz      loc_10047670E
0x100476644  mov     ecx, eax
0x100476646  call    cs:__imp_?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z; HRESULT_FROM_SOS_RESULT_Uncommon(SOS_RESULT)
0x10047664c  mov     esi, eax
0x10047664e  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100476656  jz      loc_1004766E2
0x10047665c  call    cs:__imp_GetCurrentThreadId
0x100476662  xorps   xmm0, xmm0
0x100476665  xor     ecx, ecx
0x100476667  movups  [rsp+178h+var_148], xmm0
0x10047666c  mov     [rsp+178h+var_138], rcx
0x100476671  mov     [rsp+178h+var_130], edi
0x100476675  mov     [rsp+178h+var_12C], eax
0x100476679  lea     rax, aCsqlsatellites; "CSQLSatelliteSessionBasedMsgQueueConnec"...
0x100476680  mov     [rsp+178h+var_128], rax
0x100476685  mov     [rsp+178h+var_120], 1C13h
0x10047668d  mov     rdi, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100476694  mov     [rsp+178h+var_30], r14d
0x10047669c  mov     [rsp+178h+var_28], r14
0x1004766a4  cmp     [rdi+40h], rcx
0x1004766a8  jz      short loc_1004766B7
0x1004766aa  lea     edx, [rcx+1]
0x1004766ad  lea     rcx, [rsp+178h+var_108]
0x1004766b2  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x1004766b7  test    byte ptr cs:dword_1005113AC, 10h
0x1004766be  jz      short loc_1004766CF
0x1004766c0  lea     rdx, [rsp+178h+var_108]
0x1004766c5  lea     rcx, [rsp+178h+var_148]
0x1004766ca  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x1004766cf  lea     r8, [rsp+178h+var_108]
0x1004766d4  lea     rdx, [rsp+178h+var_148]
0x1004766d9  mov     rcx, rdi
0x1004766dc  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x1004766e2  mov     eax, 0FFFFFFFFh
0x1004766e7  lock xadd [rbx+20h], eax
0x1004766ec  cmp     eax, 1
0x1004766ef  jnz     short loc_10047670E
0x1004766f1  cmp     qword ptr [rbx+10h], 0
0x1004766f6  jz      short loc_100476704
0x1004766f8  mov     rdx, rbx
0x1004766fb  mov     rcx, [rbx+18h]
0x1004766ff  call    ?RemoveElem@?$TList@VSqlSatelliteConnectionList@@VCSQLSatelliteConnection@@$07UTListSLock@@@@QEAAXPEAVCSQLSatelliteConnection@@@Z; TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(CSQLSatelliteConnection *)
0x100476704  mov     rax, [rbx]
0x100476707  mov     rcx, rbx
0x10047670a  call    qword ptr [rax+18h]
0x10047670d  nop
0x10047670e  lea     rcx, [rsp+178h+arg_8]
0x100476716  call    ??1?$CAutoRefc@VSOS_Task@@@@QEAA@XZ; CAutoRefc<SOS_Task>::~CAutoRefc<SOS_Task>(void)
0x10047671b  mov     eax, esi
0x10047671d  lea     r11, [rsp+178h+var_18]
0x100476725  mov     rbx, [r11+30h]
0x100476729  mov     rbp, [r11+38h]
0x10047672d  mov     rsp, r11
0x100476730  pop     r14
0x100476732  pop     rdi
0x100476733  pop     rsi
0x100476734  retn
```
