# SatellitePacketProcessorTask(void *)

- ea: `0x100470c20`
- end: `0x100470f93`
- name: `?SatellitePacketProcessorTask@@YAPEAXPEAX@Z`
- size: `883`
- prototype: `void *__fastcall(SatellitePacketList *this)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x10040bbb0`
- `0x10041f180`
- `0x100455f90`
- `0x1004700c0`
- `0x100470c20`
- `0x1004721d0`
- `0x1004737e0`
- `0x100478330`
- `0x100478670`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x100470d66`
- `KERNEL32!GetCurrentThreadId` at `0x100470ea9`
- `KERNEL32!GetCurrentThreadId` at `0x100470d66`
- `KERNEL32!GetCurrentThreadId` at `0x100470ea9`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100470dda`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100470f25`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100470dda`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100470f25`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x100470e75`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x100470e75`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100470c86`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100470e65`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100470c86`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x100470e65`

## string_xrefs

- `0x100470e82`: `SatellitePacketProcessorTask is exiting.`
- `0x100470f7a`: `SatellitePacketProcessorTask is exiting.`
- `0x100470ec2`: `SatellitePacketProcessorTask`
- `0x100470d4d`: `SNI read failed with error %d, at CSQLSatelliteConnection::ProcessSatellitePackets\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall SatellitePacketProcessorTask(SatellitePacketList *this)
{
  unsigned int v2; // esi
  unsigned int v3; // eax
  struct SNI_Packet *PacketsList; // rax
  struct CSQLSatelliteConnection *v5; // rbx
  int v6; // r14d
  struct SNI_Packet *v7; // rcx
  struct SNI_Packet *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // rdi
  DWORD v11; // eax
  __int64 v12; // rbx
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h]
  __int64 v17; // [rsp+40h] [rbp-C0h]
  __int64 v18; // [rsp+48h] [rbp-B8h]
  __int64 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h]
  unsigned int v22; // [rsp+70h] [rbp-90h]
  DWORD v23; // [rsp+74h] [rbp-8Ch]
  const char *v24; // [rsp+78h] [rbp-88h]
  int v25; // [rsp+80h] [rbp-80h]
  __int128 v26; // [rsp+88h] [rbp-78h] BYREF
  __int64 v27; // [rsp+98h] [rbp-68h]
  unsigned int v28; // [rsp+A0h] [rbp-60h]
  DWORD v29; // [rsp+A4h] [rbp-5Ch]
  const char *v30; // [rsp+A8h] [rbp-58h]
  int v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  _BYTE v33[216]; // [rsp+C0h] [rbp-40h] BYREF
  int v34; // [rsp+198h] [rbp+98h]
  __int64 v35; // [rsp+1A0h] [rbp+A0h]
  _BYTE v36[216]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v37; // [rsp+288h] [rbp+188h]
  __int64 v38; // [rsp+290h] [rbp+190h]
  struct CSQLSatelliteConnection *v39; // [rsp+2E8h] [rbp+1E8h] BYREF
  struct SNI_Packet *v40; // [rsp+2F0h] [rbp+1F0h] BYREF

  v32 = -2;
  v2 = 0;
  v15 = 4195533;
  v16 = 0;
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v3 = WaitableBase::Wait((char *)this + 32, 0xFFFFFFFFLL, &v15, 0, 1);
  if ( v3 )
  {
LABEL_26:
    v2 = HRESULT_FROM_SOS_RESULT_Uncommon(v3);
  }
  else
  {
    while ( !*((_BYTE *)this + 88) )
    {
      v39 = 0;
      PacketsList = SatellitePacketList::GetPacketsList(this, &v39);
      v5 = v39;
      if ( PacketsList )
      {
        v40 = PacketsList;
        v2 = 0;
        v6 = CSQLSatelliteConnection::ReadCallBackInternal(v39, &v40);
        if ( v6 == 997 )
        {
          v2 = 0;
        }
        else
        {
          if ( v6 )
          {
            if ( v6 > 0 )
              v2 = (unsigned __int16)v6 | 0x80070000;
            else
              v2 = v6;
            v7 = v40;
            if ( v40 )
            {
              do
              {
                v8 = (struct SNI_Packet *)*((_QWORD *)v7 + 26);
                *((_QWORD *)v7 + 26) = 0;
                SNIPacketRelease(v7);
                v7 = v8;
              }
              while ( v8 );
            }
            CSQLSatelliteConnection::AbortConnection(
              v5,
              L"SNI read failed with error %d, at CSQLSatelliteConnection::ProcessSatellitePackets\n",
              (unsigned int)v6);
            if ( g_extensibilityErrorRingBuffer )
            {
              CurrentThreadId = GetCurrentThreadId();
              v20 = 0;
              v21 = 0;
              v22 = v2;
              v23 = CurrentThreadId;
              v24 = "CSQLSatelliteConnection::ProcessSatellitePackets";
              v25 = 1694;
              v10 = g_extensibilityErrorRingBuffer;
              v34 = 0;
              v35 = 0;
              if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
                StackFrames<24>::CaptureCurrent(v33, 1);
              if ( (dword_1005113AC & 0x10) != 0 )
                ExtensibilityErrorRecord::FireMatchingEvent(&v20, v33);
              SOS_RingBuffer::StoreRecordInternalWithoutEvent(v10, &v20, v33);
            }
            FireTraceEvent(1, v2, (char *)v5 + 932, L"ProcessSatellitePackets Failed.");
          }
          if ( (v2 & 0x80000000) != 0 )
          {
            if ( v5 && _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 8, 0xFFFFFFFF) == 1 )
            {
              if ( *((_QWORD *)v5 + 2) )
                TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(
                  *((_QWORD *)v5 + 3),
                  v5);
              (*(void (__fastcall **)(struct CSQLSatelliteConnection *))(*(_QWORD *)v5 + 24LL))(v5);
            }
            FireTraceEvent(v2 >> 31, v2, 0, L"SatellitePacketProcessorTask is exiting.");
            goto LABEL_28;
          }
        }
      }
      if ( v5 && _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 8, 0xFFFFFFFF) == 1 )
      {
        if ( *((_QWORD *)v5 + 2) )
          TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(*((_QWORD *)v5 + 3), v5);
        (*(void (__fastcall **)(struct CSQLSatelliteConnection *))(*(_QWORD *)v5 + 24LL))(v5);
      }
      v15 = 4195533;
      v16 = 0;
      v18 = 0;
      v17 = 0;
      v19 = 0;
      LOBYTE(v14) = 1;
      v3 = WaitableBase::Wait((char *)this + 32, 0xFFFFFFFFLL, &v15, 0, v14);
      if ( v3 )
        goto LABEL_26;
    }
  }
  FireTraceEvent(v2 >> 31, v2, 0, L"SatellitePacketProcessorTask is exiting.");
  if ( (v2 & 0x80000000) != 0 )
  {
LABEL_28:
    if ( g_extensibilityErrorRingBuffer )
    {
      v11 = GetCurrentThreadId();
      v26 = 0;
      v27 = 0;
      v28 = v2;
      v29 = v11;
      v30 = "SatellitePacketProcessorTask";
      v31 = 452;
      v12 = g_extensibilityErrorRingBuffer;
      v37 = 0;
      v38 = 0;
      if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
        StackFrames<24>::CaptureCurrent(v36, 1);
      if ( (dword_1005113AC & 0x10) != 0 )
        ExtensibilityErrorRecord::FireMatchingEvent(&v26, v36);
      SOS_RingBuffer::StoreRecordInternalWithoutEvent(v12, &v26, v36);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x100470c20  push    rbp
0x100470c22  push    rsi
0x100470c23  push    rdi
0x100470c24  push    r12
0x100470c26  push    r13
0x100470c28  push    r14
0x100470c2a  push    r15
0x100470c2c  lea     rbp, [rsp-1A0h]
0x100470c34  sub     rsp, 2A0h
0x100470c3b  mov     [rbp+1D0h+var_218], 0FFFFFFFFFFFFFFFEh
0x100470c43  mov     [rsp+2D0h+arg_18], rbx
0x100470c4b  mov     r13, rcx
0x100470c4e  xor     r14d, r14d
0x100470c51  mov     esi, r14d
0x100470c54  mov     [rsp+2D0h+var_2A0], 4004CDh
0x100470c5c  mov     [rsp+2D0h+var_298], r14
0x100470c61  mov     [rsp+2D0h+var_288], r14
0x100470c66  mov     [rsp+2D0h+var_290], r14
0x100470c6b  mov     [rsp+2D0h+var_280], r14
0x100470c70  mov     byte ptr [rsp+2D0h+var_2B0], 1
0x100470c75  xor     r9d, r9d
0x100470c78  lea     r8, [rsp+2D0h+var_2A0]
0x100470c7d  mov     edx, 0FFFFFFFFh
0x100470c82  add     rcx, 20h ; ' '
0x100470c86  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x100470c8c  test    eax, eax
0x100470c8e  jnz     loc_100470E73
0x100470c94  lea     r15d, [r14-1]
0x100470c98  lea     rdi, aCsqlsatellitec_3; "CSQLSatelliteConnection::ProcessSatelli"...
0x100470c9f  cmp     byte ptr [r13+58h], 0
0x100470ca4  jnz     loc_100470E7D
0x100470caa  mov     [rbp+1D0h+arg_8], r14
0x100470cb1  lea     rdx, [rbp+1D0h+arg_8]; struct CSQLSatelliteConnection **
0x100470cb8  mov     rcx, r13; this
0x100470cbb  call    ?GetPacketsList@SatellitePacketList@@QEAAPEAVSNI_Packet@@PEAPEAVCSQLSatelliteConnection@@@Z; SatellitePacketList::GetPacketsList(CSQLSatelliteConnection * *)
0x100470cc0  mov     rbx, [rbp+1D0h+arg_8]
0x100470cc7  test    rax, rax
0x100470cca  jz      loc_100470E05
0x100470cd0  mov     [rbp+1D0h+arg_10], rax
0x100470cd7  mov     esi, r14d
0x100470cda  lea     rdx, [rbp+1D0h+arg_10]; struct SNI_Packet **
0x100470ce1  mov     rcx, rbx; this
0x100470ce4  call    ?ReadCallBackInternal@CSQLSatelliteConnection@@AEAAKPEAPEAVSNI_Packet@@@Z; CSQLSatelliteConnection::ReadCallBackInternal(SNI_Packet * *)
0x100470ce9  mov     r14d, eax
0x100470cec  cmp     eax, 3E5h
0x100470cf1  jnz     short loc_100470CFE
0x100470cf3  xor     r14d, r14d
0x100470cf6  mov     esi, r14d
0x100470cf9  jmp     loc_100470E05
0x100470cfe  test    r14d, r14d
0x100470d01  jz      loc_100470DFA
0x100470d07  jg      short loc_100470D0E
0x100470d09  mov     esi, r14d
0x100470d0c  jmp     short loc_100470D18
0x100470d0e  movzx   esi, r14w
0x100470d12  or      esi, 80070000h
0x100470d18  mov     rcx, [rbp+1D0h+arg_10]; struct SNI_Packet *
0x100470d1f  test    rcx, rcx
0x100470d22  jz      short loc_100470D4A
0x100470d24  mov     rdi, [rcx+0D0h]
0x100470d2b  mov     qword ptr [rcx+0D0h], 0
0x100470d36  call    SNIPacketRelease
0x100470d3b  mov     rcx, rdi
0x100470d3e  test    rdi, rdi
0x100470d41  jnz     short loc_100470D24
0x100470d43  lea     rdi, aCsqlsatellitec_3; "CSQLSatelliteConnection::ProcessSatelli"...
0x100470d4a  mov     r8d, r14d
0x100470d4d  lea     rdx, aSniReadFailedW_1; "SNI read failed with error %d, at CSQLS"...
0x100470d54  mov     rcx, rbx; this
0x100470d57  call    ?AbortConnection@CSQLSatelliteConnection@@QEAAXPEB_WZZ; CSQLSatelliteConnection::AbortConnection(wchar_t const *,...)
0x100470d5c  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100470d64  jz      short loc_100470DE0
0x100470d66  call    cs:__imp_GetCurrentThreadId
0x100470d6c  xorps   xmm0, xmm0
0x100470d6f  xor     ecx, ecx
0x100470d71  movups  [rsp+2D0h+var_278], xmm0
0x100470d76  mov     [rsp+2D0h+var_268], rcx
0x100470d7b  mov     [rsp+2D0h+var_260], esi
0x100470d7f  mov     [rsp+2D0h+var_25C], eax
0x100470d83  mov     [rsp+2D0h+var_258], rdi
0x100470d88  mov     [rbp+1D0h+var_250], 69Eh
0x100470d8f  mov     rdi, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100470d96  xor     eax, eax
0x100470d98  mov     [rbp+1D0h+var_138], eax
0x100470d9e  mov     [rbp+1D0h+var_130], rax
0x100470da5  cmp     [rdi+40h], rax
0x100470da9  jz      short loc_100470DB7
0x100470dab  lea     edx, [rcx+1]
0x100470dae  lea     rcx, [rbp+1D0h+var_210]
0x100470db2  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x100470db7  test    byte ptr cs:dword_1005113AC, 10h
0x100470dbe  jz      short loc_100470DCE
0x100470dc0  lea     rdx, [rbp+1D0h+var_210]
0x100470dc4  lea     rcx, [rsp+2D0h+var_278]
0x100470dc9  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x100470dce  lea     r8, [rbp+1D0h+var_210]
0x100470dd2  lea     rdx, [rsp+2D0h+var_278]
0x100470dd7  mov     rcx, rdi
0x100470dda  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x100470de0  lea     r8, [rbx+3A4h]
0x100470de7  lea     r9, aProcesssatelli; "ProcessSatellitePackets Failed."
0x100470dee  mov     edx, esi
0x100470df0  mov     ecx, 1
0x100470df5  call    ?FireTraceEvent@@YAXW4ExtensibilityTraceLevel@@JPEBU_GUID@@PEB_WZZ; FireTraceEvent(ExtensibilityTraceLevel,long,_GUID const *,wchar_t const *,...)
0x100470dfa  test    esi, esi
0x100470dfc  js      loc_100470F48
0x100470e02  xor     r14d, r14d
0x100470e05  test    rbx, rbx
0x100470e08  jz      short loc_100470E33
0x100470e0a  mov     eax, r15d
0x100470e0d  lock xadd [rbx+20h], eax
0x100470e12  cmp     eax, 1
0x100470e15  jnz     short loc_100470E33
0x100470e17  cmp     qword ptr [rbx+10h], 0
0x100470e1c  jz      short loc_100470E2A
0x100470e1e  mov     rdx, rbx
0x100470e21  mov     rcx, [rbx+18h]
0x100470e25  call    ?RemoveElem@?$TList@VSqlSatelliteConnectionList@@VCSQLSatelliteConnection@@$07UTListSLock@@@@QEAAXPEAVCSQLSatelliteConnection@@@Z; TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(CSQLSatelliteConnection *)
0x100470e2a  mov     rax, [rbx]
0x100470e2d  mov     rcx, rbx
0x100470e30  call    qword ptr [rax+18h]
0x100470e33  mov     [rsp+2D0h+var_2A0], 4004CDh
0x100470e3b  mov     [rsp+2D0h+var_298], r14
0x100470e40  mov     [rsp+2D0h+var_288], r14
0x100470e45  mov     [rsp+2D0h+var_290], r14
0x100470e4a  mov     [rsp+2D0h+var_280], r14
0x100470e4f  mov     byte ptr [rsp+2D0h+var_2B0], 1
0x100470e54  xor     r9d, r9d
0x100470e57  lea     r8, [rsp+2D0h+var_2A0]
0x100470e5c  mov     edx, 0FFFFFFFFh
0x100470e61  lea     rcx, [r13+20h]
0x100470e65  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x100470e6b  test    eax, eax
0x100470e6d  jz      loc_100470C98
0x100470e73  mov     ecx, eax
0x100470e75  call    cs:__imp_?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z; HRESULT_FROM_SOS_RESULT_Uncommon(SOS_RESULT)
0x100470e7b  mov     esi, eax
0x100470e7d  mov     ecx, esi
0x100470e7f  shr     ecx, 1Fh
0x100470e82  lea     r9, aSatellitepacke; "SatellitePacketProcessorTask is exiting"...
0x100470e89  xor     r8d, r8d
0x100470e8c  mov     edx, esi
0x100470e8e  call    ?FireTraceEvent@@YAXW4ExtensibilityTraceLevel@@JPEBU_GUID@@PEB_WZZ; FireTraceEvent(ExtensibilityTraceLevel,long,_GUID const *,wchar_t const *,...)
0x100470e93  test    esi, esi
0x100470e95  jns     loc_100470F2B
0x100470e9b  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100470ea3  jz      loc_100470F2B
0x100470ea9  call    cs:__imp_GetCurrentThreadId
0x100470eaf  xorps   xmm0, xmm0
0x100470eb2  xor     ecx, ecx
0x100470eb4  movups  [rbp+1D0h+var_248], xmm0
0x100470eb8  mov     [rbp+1D0h+var_238], rcx
0x100470ebc  mov     [rbp+1D0h+var_230], esi
0x100470ebf  mov     [rbp+1D0h+var_22C], eax
0x100470ec2  lea     rax, aSatellitepacke_0; "SatellitePacketProcessorTask"
0x100470ec9  mov     [rbp+1D0h+var_228], rax
0x100470ecd  mov     [rbp+1D0h+var_220], 1C4h
0x100470ed4  mov     rbx, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x100470edb  mov     [rbp+1D0h+var_48], r14d
0x100470ee2  mov     [rbp+1D0h+var_40], r14
0x100470ee9  cmp     [rbx+40h], rcx
0x100470eed  jz      short loc_100470EFE
0x100470eef  lea     edx, [rcx+1]
0x100470ef2  lea     rcx, [rbp+1D0h+var_120]
0x100470ef9  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x100470efe  test    byte ptr cs:dword_1005113AC, 10h
0x100470f05  jz      short loc_100470F17
0x100470f07  lea     rdx, [rbp+1D0h+var_120]
0x100470f0e  lea     rcx, [rbp+1D0h+var_248]
0x100470f12  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x100470f17  lea     r8, [rbp+1D0h+var_120]
0x100470f1e  lea     rdx, [rbp+1D0h+var_248]
0x100470f22  mov     rcx, rbx
0x100470f25  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x100470f2b  xor     eax, eax
0x100470f2d  mov     rbx, [rsp+2D0h+arg_18]
0x100470f35  add     rsp, 2A0h
0x100470f3c  pop     r15
0x100470f3e  pop     r14
0x100470f40  pop     r13
0x100470f42  pop     r12
0x100470f44  pop     rdi
0x100470f45  pop     rsi
0x100470f46  pop     rbp
0x100470f47  retn
0x100470f48  test    rbx, rbx
0x100470f4b  jz      short loc_100470F75
0x100470f4d  lock xadd [rbx+20h], r15d
0x100470f53  cmp     r15d, 1
0x100470f57  jnz     short loc_100470F75
0x100470f59  cmp     qword ptr [rbx+10h], 0
0x100470f5e  jz      short loc_100470F6C
0x100470f60  mov     rdx, rbx
0x100470f63  mov     rcx, [rbx+18h]
0x100470f67  call    ?RemoveElem@?$TList@VSqlSatelliteConnectionList@@VCSQLSatelliteConnection@@$07UTListSLock@@@@QEAAXPEAVCSQLSatelliteConnection@@@Z; TList<SqlSatelliteConnectionList,CSQLSatelliteConnection,8,TListSLock>::RemoveElem(CSQLSatelliteConnection *)
0x100470f6c  mov     rax, [rbx]
0x100470f6f  mov     rcx, rbx
0x100470f72  call    qword ptr [rax+18h]
0x100470f75  mov     ecx, esi
0x100470f77  shr     ecx, 1Fh
0x100470f7a  lea     r9, aSatellitepacke; "SatellitePacketProcessorTask is exiting"...
0x100470f81  xor     r8d, r8d
0x100470f84  mov     edx, esi
0x100470f86  call    ?FireTraceEvent@@YAXW4ExtensibilityTraceLevel@@JPEBU_GUID@@PEB_WZZ; FireTraceEvent(ExtensibilityTraceLevel,long,_GUID const *,wchar_t const *,...)
0x100470f8b  xor     r14d, r14d
0x100470f8e  jmp     loc_100470E9B
```
