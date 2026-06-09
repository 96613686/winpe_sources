# CSQLSatelliteConnection::OpenTcpConnectionAndStartPacketProcessorTask(IMemObj *,wchar_t const *,ulong,CSQLSatelliteConnection *,SNI_Conn * *,_GUID *,bool)

- ea: `0x1004730b0`
- end: `0x100473339`
- name: `?OpenTcpConnectionAndStartPacketProcessorTask@CSQLSatelliteConnection@@SAJPEAVIMemObj@@PEB_WKPEAV1@PEAPEAVSNI_Conn@@PEAU_GUID@@_N@Z`
- size: `649`
- prototype: `int __fastcall(struct IMemObj *, const wchar_t *, unsigned int, struct CSQLSatelliteConnection *, struct SNI_Conn **, struct _GUID *, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1004089b0`

## callees

- `0x10040bd60`
- `0x100455f90`
- `0x1004730b0`
- `0x100473340`
- `0x100478330`
- `0x100478670`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x10047323a`
- `KERNEL32!GetCurrentThreadId` at `0x10047323a`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004732b9`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x1004732b9`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x100473224`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x100473224`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047310b`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047310b`
- `sqldk!SystemThread_TlsIndex` at `0x1004731b2`
- `sqldk!SystemThread_TlsOffset` at `0x1004731bb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004731d4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004731d4`

## string_xrefs

- `0x1004730f7`: `Sql\Ntdbms\extensibility\common\src\communisatellite.cpp`
- `0x100473257`: `StartPacketProcessorTask`
- `0x1004732bf`: `Failed to enqueue SatellitePacketProcessorTask.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall CSQLSatelliteConnection::OpenTcpConnectionAndStartPacketProcessorTask(
        struct IMemObj *a1,
        const wchar_t *a2,
        unsigned int a3,
        struct CSQLSatelliteConnection *a4,
        struct SNI_Conn **a5,
        struct _GUID *a6,
        bool a7)
{
  _DWORD *v11; // rax
  _DWORD *v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rsi
  __int64 v15; // rdi
  __int64 v16; // rcx
  unsigned int v17; // eax
  unsigned int v18; // edi
  int v19; // esi
  __int64 v20; // r14
  __int128 v22; // [rsp+30h] [rbp-158h] BYREF
  __int64 v23; // [rsp+40h] [rbp-148h]
  unsigned int v24; // [rsp+48h] [rbp-140h]
  DWORD CurrentThreadId; // [rsp+4Ch] [rbp-13Ch]
  const char *v26; // [rsp+50h] [rbp-138h]
  int v27; // [rsp+58h] [rbp-130h]
  __int64 v28; // [rsp+60h] [rbp-128h]
  _DWORD *v29; // [rsp+68h] [rbp-120h]
  _BYTE v30[216]; // [rsp+70h] [rbp-118h] BYREF
  int v31; // [rsp+148h] [rbp-40h]
  __int64 v32; // [rsp+150h] [rbp-38h]
  __int64 v33; // [rsp+1A8h] [rbp+20h] BYREF

  v28 = -2;
  LODWORD(v33) = 3921;
  v11 = operator new(0x70u, a1, 1, "Sql\\Ntdbms\\extensibility\\common\\src\\communisatellite.cpp", 3921, 6u);
  v12 = v11;
  v29 = v11;
  if ( v11 )
  {
    v11[2] = 1;
    *(_QWORD *)v11 = &SatellitePacketList::`vftable';
    v13 = 0;
    *((_QWORD *)v11 + 2) = 0;
    *((_QWORD *)v11 + 3) = 0;
    *((_QWORD *)v11 + 6) = v11 + 10;
    *((_QWORD *)v11 + 5) = v11 + 10;
    *((_QWORD *)v11 + 7) = 0;
    v11[16] = 0;
    v11[17] = 1;
    *((_QWORD *)v11 + 9) = 0;
    *((_QWORD *)v11 + 4) = &EventAutoInternal<SuspendQueueSLock>::`vftable';
    *((_QWORD *)v11 + 10) = 0;
    *((_BYTE *)v11 + 88) = 0;
    *((_QWORD *)v11 + 12) = 0;
    *((_QWORD *)v11 + 13) = 0;
  }
  else
  {
    v13 = 0;
    v12 = 0;
  }
  *((_QWORD *)a4 + 122) = v12;
  if ( !v12 )
    return -2147024882;
  (*(void (__fastcall **)(struct IMemObj *))(*(_QWORD *)a1 + 8LL))(a1);
  *(_QWORD *)(*((_QWORD *)a4 + 122) + 104LL) = a1;
  v14 = *((_QWORD *)a4 + 122);
  v33 = 0;
  v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v16 = *(_QWORD *)(v15 + 256);
  if ( !v16 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v16 = *(_QWORD *)(v15 + 256);
  }
  v17 = SOS_Node::EnqueueTaskDirect(*(_QWORD *)(v16 + 992), SatellitePacketProcessorTask, v14, 688, &v33, 0);
  v18 = v17;
  if ( !v17 )
  {
    v13 = v33;
LABEL_16:
    *(_QWORD *)(*((_QWORD *)a4 + 122) + 96LL) = v13;
    return CSQLSatelliteConnection::OpenTcpConnection(a2, a3, a4, a5, a6, a7);
  }
  v19 = HRESULT_FROM_SOS_RESULT_Uncommon(v17);
  if ( g_extensibilityErrorRingBuffer )
  {
    v22 = 0;
    v23 = 0;
    v24 = v18;
    CurrentThreadId = GetCurrentThreadId();
    v26 = "StartPacketProcessorTask";
    v27 = 3838;
    v20 = g_extensibilityErrorRingBuffer;
    v31 = 0;
    v32 = 0;
    if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
      StackFrames<24>::CaptureCurrent(v30, 1);
    if ( (dword_1005113AC & 0x10) != 0 )
      ExtensibilityErrorRecord::FireMatchingEvent(&v22, v30);
    SOS_RingBuffer::StoreRecordInternalWithoutEvent(v20, &v22, v30);
  }
  FireTraceEvent(1, v18, 0, L"Failed to enqueue SatellitePacketProcessorTask.");
  if ( v19 >= 0 )
    goto LABEL_16;
  return v19;
}

```

## disassembly

```asm
0x1004730b0  mov     rax, rsp
0x1004730b3  mov     [rax+8], rcx
0x1004730b7  push    rsi
0x1004730b8  push    rdi
0x1004730b9  push    r12
0x1004730bb  push    r14
0x1004730bd  push    r15
0x1004730bf  sub     rsp, 160h
0x1004730c6  mov     [rsp+188h+var_128], 0FFFFFFFFFFFFFFFEh
0x1004730cf  mov     [rax+10h], rbx
0x1004730d3  mov     [rax+18h], rbp
0x1004730d7  mov     rbp, r9
0x1004730da  mov     r15d, r8d
0x1004730dd  mov     r12, rdx
0x1004730e0  mov     rdi, rcx
0x1004730e3  mov     dword ptr [rax+20h], 0F51h
0x1004730ea  mov     [rsp+188h+var_160], 6
0x1004730ef  mov     dword ptr [rsp+188h+var_168], 0F51h
0x1004730f7  lea     r9, aSqlNtdbmsExten_8; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x1004730fe  mov     r8d, 1
0x100473104  mov     rdx, rcx
0x100473107  lea     ecx, [r8+6Fh]
0x10047310b  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100473111  mov     rdx, rax
0x100473114  mov     [rsp+188h+var_120], rax
0x100473119  test    rax, rax
0x10047311c  jz      short loc_100473172
0x10047311e  mov     dword ptr [rax+8], 1
0x100473125  lea     rax, ??_7SatellitePacketList@@6B@; const SatellitePacketList::`vftable'
0x10047312c  mov     [rdx], rax
0x10047312f  xor     ebx, ebx
0x100473131  mov     [rdx+10h], rbx
0x100473135  mov     [rdx+18h], rbx
0x100473139  lea     rax, [rdx+28h]
0x10047313d  mov     [rax+8], rax
0x100473141  mov     [rax], rax
0x100473144  mov     [rdx+38h], rbx
0x100473148  mov     [rdx+40h], ebx
0x10047314b  mov     dword ptr [rdx+44h], 1
0x100473152  mov     [rdx+48h], rbx
0x100473156  lea     rax, ??_7?$EventAutoInternal@USuspendQueueSLock@@@@6B@; const EventAutoInternal<SuspendQueueSLock>::`vftable'
0x10047315d  mov     [rdx+20h], rax
0x100473161  mov     [rdx+50h], rbx
0x100473165  mov     [rdx+58h], bl
0x100473168  mov     [rdx+60h], rbx
0x10047316c  mov     [rdx+68h], rbx
0x100473170  jmp     short loc_100473176
0x100473172  xor     ebx, ebx
0x100473174  mov     edx, ebx
0x100473176  mov     [rbp+3D0h], rdx
0x10047317d  test    rdx, rdx
0x100473180  jz      loc_100473318
0x100473186  mov     rax, [rdi]
0x100473189  mov     rcx, rdi
0x10047318c  call    qword ptr [rax+8]
0x10047318f  mov     rax, [rbp+3D0h]
0x100473196  mov     [rax+68h], rdi
0x10047319a  mov     rsi, [rbp+3D0h]
0x1004731a1  mov     [rsp+188h+arg_18], rbx
0x1004731a9  mov     rdx, gs:58h
0x1004731b2  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004731b9  mov     ecx, [rax]
0x1004731bb  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004731c2  mov     edi, [rax]
0x1004731c4  add     rdi, [rdx+rcx*8]
0x1004731c8  mov     rcx, [rdi+100h]
0x1004731cf  test    rcx, rcx
0x1004731d2  jnz     short loc_1004731E1
0x1004731d4  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004731da  mov     rcx, [rdi+100h]
0x1004731e1  mov     qword ptr [rsp+188h+var_160], rbx
0x1004731e6  lea     rax, [rsp+188h+arg_18]
0x1004731ee  mov     [rsp+188h+var_168], rax
0x1004731f3  mov     r9d, 2B0h
0x1004731f9  mov     r8, rsi
0x1004731fc  lea     rdx, ?SatellitePacketProcessorTask@@YAPEAXPEAX@Z; SatellitePacketProcessorTask(void *)
0x100473203  mov     rcx, [rcx+3E0h]
0x10047320a  call    ?EnqueueTaskDirect@SOS_Node@@QEAA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@PEAPEAX@Z; SOS_Node::EnqueueTaskDirect(void * (*)(void *),void *,ulong,SOS_Task * *,void * *)
0x10047320f  mov     edi, eax
0x100473211  test    eax, eax
0x100473213  jnz     short loc_100473222
0x100473215  mov     rbx, [rsp+188h+arg_18]
0x10047321d  jmp     loc_1004732D8
0x100473222  mov     ecx, edi
0x100473224  call    cs:__imp_?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z; HRESULT_FROM_SOS_RESULT_Uncommon(SOS_RESULT)
0x10047322a  mov     esi, eax
0x10047322c  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100473234  jz      loc_1004732BF
0x10047323a  call    cs:__imp_GetCurrentThreadId
0x100473240  xorps   xmm0, xmm0
0x100473243  xor     ecx, ecx
0x100473245  movups  [rsp+188h+var_158], xmm0
0x10047324a  mov     [rsp+188h+var_148], rcx
0x10047324f  mov     [rsp+188h+var_140], edi
0x100473253  mov     [rsp+188h+var_13C], eax
0x100473257  lea     rax, aStartpacketpro; "StartPacketProcessorTask"
0x10047325e  mov     [rsp+188h+var_138], rax
0x100473263  mov     [rsp+188h+var_130], 0EFEh
0x10047326b  mov     r14, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100473272  mov     [rsp+188h+var_40], ebx
0x100473279  mov     [rsp+188h+var_38], rbx
0x100473281  cmp     [r14+40h], rcx
0x100473285  jz      short loc_100473294
0x100473287  lea     edx, [rcx+1]
0x10047328a  lea     rcx, [rsp+188h+var_118]
0x10047328f  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x100473294  test    byte ptr cs:dword_1005113AC, 10h
0x10047329b  jz      short loc_1004732AC
0x10047329d  lea     rdx, [rsp+188h+var_118]
0x1004732a2  lea     rcx, [rsp+188h+var_158]
0x1004732a7  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x1004732ac  lea     r8, [rsp+188h+var_118]
0x1004732b1  lea     rdx, [rsp+188h+var_158]
0x1004732b6  mov     rcx, r14
0x1004732b9  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x1004732bf  lea     r9, aFailedToEnqueu; "Failed to enqueue SatellitePacketProces"...
0x1004732c6  xor     r8d, r8d
0x1004732c9  mov     edx, edi
0x1004732cb  lea     ecx, [r8+1]
0x1004732cf  call    ?FireTraceEvent@@YAXW4ExtensibilityTraceLevel@@JPEBU_GUID@@PEB_WZZ; FireTraceEvent(ExtensibilityTraceLevel,long,_GUID const *,wchar_t const *,...)
0x1004732d4  test    esi, esi
0x1004732d6  js      short loc_100473314
0x1004732d8  mov     rax, [rbp+3D0h]
0x1004732df  mov     [rax+60h], rbx
0x1004732e3  movzx   eax, [rsp+188h+arg_30]
0x1004732eb  mov     [rsp+188h+var_160], al; bool
0x1004732ef  mov     rax, [rsp+188h+arg_28]
0x1004732f7  mov     [rsp+188h+var_168], rax; struct _GUID *
0x1004732fc  mov     r9, [rsp+188h+arg_20]; struct SNI_Conn **
0x100473304  mov     r8, rbp; struct CSQLSatelliteConnection *
0x100473307  mov     edx, r15d; unsigned int
0x10047330a  mov     rcx, r12; wchar_t *
0x10047330d  call    ?OpenTcpConnection@CSQLSatelliteConnection@@SAJPEB_WKPEAV1@PEAPEAVSNI_Conn@@PEAU_GUID@@_N@Z; CSQLSatelliteConnection::OpenTcpConnection(wchar_t const *,ulong,CSQLSatelliteConnection *,SNI_Conn * *,_GUID *,bool)
0x100473312  jmp     short loc_10047331D
0x100473314  mov     eax, esi
0x100473316  jmp     short loc_10047331D
0x100473318  mov     eax, 8007000Eh
0x10047331d  lea     r11, [rsp+188h+var_28]
0x100473325  mov     rbx, [r11+38h]
0x100473329  mov     rbp, [r11+40h]
0x10047332d  mov     rsp, r11
0x100473330  pop     r15
0x100473332  pop     r14
0x100473334  pop     r12
0x100473336  pop     rdi
0x100473337  pop     rsi
0x100473338  retn
```
