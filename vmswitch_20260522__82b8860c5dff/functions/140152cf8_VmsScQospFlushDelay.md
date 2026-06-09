# VmsScQospFlushDelay

- ea: `0x140152cf8`
- end: `0x140152fee`
- name: `VmsScQospFlushDelay`
- size: `758`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140153118`

## callees

- `0x140018330`
- `0x140027a64`
- `0x14006b084`
- `0x14006dec8`
- `0x1400749f4`
- `0x14008497c`
- `0x14008faa8`
- `0x140090bd0`
- `0x140152be0`
- `0x140152cf8`
- `0x1401b6b9c`
- `0x1401b6be8`
- `0x1401b7214`
- `0x1401b7284`
- `0x1401b72dc`
- `0x1401b731c`
- `0x1401b7f60`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x140152e46`
- `NDIS!NdisReleaseRWLock` at `0x140152ead`
- `NDIS!NdisReleaseRWLock` at `0x140152f0f`
- `NDIS!NdisReleaseRWLock` at `0x140152e46`
- `NDIS!NdisReleaseRWLock` at `0x140152ead`
- `NDIS!NdisReleaseRWLock` at `0x140152f0f`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152e09`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152ef1`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152e09`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152ef1`

## pseudocode

```c
__int64 __fastcall VmsScQospFlushDelay(unsigned int a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v4; // rcx
  __int64 v5; // r12
  PNDIS_RW_LOCK_EX *BufferChainingDpc; // rdi
  unsigned __int64 ProcessorHistory; // rax
  _QWORD *v8; // rbx
  __int64 result; // rax
  __int64 v10; // r8
  _QWORD *v11; // rcx
  __int64 v12; // r13
  _QWORD *v13; // rbx
  __int64 v14; // rsi
  bool v15; // zf
  __int64 v16; // rdx
  int v17; // edx
  int v18; // r9d
  int v19; // edx
  __int64 v20; // r9
  _QWORD *v21; // rax
  __int64 v22; // [rsp+30h] [rbp-39h] BYREF
  __int64 v23; // [rsp+38h] [rbp-31h] BYREF
  __int64 v24; // [rsp+40h] [rbp-29h] BYREF
  __int64 v25; // [rsp+48h] [rbp-21h]
  _QWORD *v26; // [rsp+50h] [rbp-19h]
  _OWORD v27[2]; // [rsp+58h] [rbp-11h] BYREF
  int v28; // [rsp+78h] [rbp+Fh]
  struct _LOCK_STATE_EX LockState; // [rsp+D0h] [rbp+67h] BYREF
  struct _LOCK_STATE_EX v30; // [rsp+D8h] [rbp+6Fh] BYREF
  _QWORD *v31; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v32; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = (unsigned __int64)a1 << 6;
  v28 = 0;
  LOBYTE(a3) = 1;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v5 = 0;
  *(_WORD *)&v30.OldIrql = 0;
  BufferChainingDpc = 0;
  v30.Flags = 0;
  ProcessorHistory = WPP_MAIN_CB.Dpc.ProcessorHistory;
  memset(v27, 0, sizeof(v27));
  v24 = 0;
  v8 = *(_QWORD **)(v4 + WPP_MAIN_CB.Dpc.ProcessorHistory);
  *(_QWORD *)(v4 + WPP_MAIN_CB.Dpc.ProcessorHistory) = 0;
  *(_QWORD *)(v4 + ProcessorHistory + 8) = 0;
  v23 = 0;
  result = QosTimerGetCurrentTime(a1, 0, a3);
  v25 = result;
  if ( v8 )
  {
    do
    {
      v11 = (_QWORD *)*v8;
      v12 = v8[56];
      v13 = v8 - 4;
      v26 = v11;
      LOBYTE(v10) = 1;
      VmsOmObjectLockExclusive(v12, &v30, v10);
      *((_DWORD *)v13 + 123) &= ~4u;
      v14 = 0;
      v15 = (v13[61] & 1) == 0;
      v32 = 0;
      v22 = 0;
      LODWORD(v31) = 0;
      if ( v15 )
      {
        if ( *((_DWORD *)v13 + 116) )
          BufferChainingDpc = *(PNDIS_RW_LOCK_EX **)(*(_QWORD *)(v13[60] + 1240LL) + 8680LL);
        else
          BufferChainingDpc = (PNDIS_RW_LOCK_EX *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
        if ( (unsigned __int8)QosFlowNeedQueueFeedback(v13 + 5, v25, v27) && BufferChainingDpc )
        {
          NdisAcquireRWLockWrite(*BufferChainingDpc, &LockState, 0);
          if ( (unsigned __int8)QosLineNeedSignal(BufferChainingDpc + 1, a1) )
            QosLineSignalExternalEvent(BufferChainingDpc + 1, a1);
          QosLineQueryQueueFeedback(BufferChainingDpc + 1, v16, v27);
          NdisReleaseRWLock(*BufferChainingDpc, &LockState);
          QosTbcAdjustSendWindow(v13 + 5, v27);
        }
        QosFlowProcessQueuedNetBufferLists((_DWORD)v13 + 40, a1, (unsigned int)&v32, (unsigned int)&v31, (__int64)&v22);
        if ( v22 )
        {
          VmsScQosDropNbls((_DWORD)v13, (_DWORD)BufferChainingDpc, v22, (unsigned int)&v23, -536862685);
          v5 = v23;
        }
        v14 = v32;
      }
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v12 + 56), &v30);
      if ( v5 )
        VmsNblHelperRefCountDecrementMany(v5, 1);
      if ( v14 )
      {
        if ( (unsigned __int8)QosLineNeedSignal(BufferChainingDpc + 1, a1) )
        {
          NdisAcquireRWLockWrite(*BufferChainingDpc, &LockState, 1u);
          QosLineSignalExternalEvent(BufferChainingDpc + 1, a1);
          NdisReleaseRWLock(*BufferChainingDpc, &LockState);
        }
        QosLineSendNetBufferLists((_DWORD)BufferChainingDpc + 8, v17, v14, v18, (__int64)&v24, (__int64)&v22);
        if ( !v13[59] )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v19,
            19,
            11,
            (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
            (__int64)"flow->Nic != NULL");
          if ( !v13[59] )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        v31 = 0;
        VmsScQosCompleteNbls(v13, BufferChainingDpc, v24, &v31);
        if ( v31 )
        {
          LODWORD(v20) = 0;
          v21 = v31;
          do
          {
            v21 = (_QWORD *)*v21;
            v20 = (unsigned int)(v20 + 1);
          }
          while ( v21 );
          VmsScQospSendProcessedNbls(*((unsigned int *)v13 + 116), v13[59], v31, v20);
        }
      }
      VmsScQospDereferenceFlow(v13);
      result = (__int64)v26;
      v8 = v26;
    }
    while ( v26 );
  }
  return result;
}

```

## disassembly

```asm
0x140152cf8  push    rbp
0x140152cfa  push    rbx
0x140152cfb  push    rsi
0x140152cfc  push    rdi
0x140152cfd  push    r12
0x140152cff  push    r13
0x140152d01  push    r14
0x140152d03  push    r15
0x140152d05  lea     rbp, [rsp-1Fh]
0x140152d0a  sub     rsp, 88h
0x140152d11  xor     eax, eax
0x140152d13  mov     r15d, ecx
0x140152d16  xor     r14d, r14d
0x140152d19  mov     ecx, ecx
0x140152d1b  shl     rcx, 6
0x140152d1f  xorps   xmm0, xmm0
0x140152d22  mov     [rbp+57h+var_48], eax
0x140152d25  mov     r8b, 1
0x140152d28  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x140152d2c  xor     edx, edx
0x140152d2e  mov     [rbp+57h+LockState.Flags], al
0x140152d31  mov     r12d, r14d
0x140152d34  mov     word ptr [rbp+57h+arg_8.OldIrql], ax
0x140152d38  mov     edi, r14d
0x140152d3b  mov     [rbp+57h+arg_8.Flags], al
0x140152d3e  mov     rax, cs:WPP_MAIN_CB.Dpc.ProcessorHistory
0x140152d45  movups  [rbp+57h+var_68], xmm0
0x140152d49  mov     [rbp+57h+var_80], r14
0x140152d4d  movups  [rbp+57h+var_58], xmm0
0x140152d51  mov     rbx, [rcx+rax]
0x140152d55  mov     [rcx+rax], r14
0x140152d59  mov     [rcx+rax+8], r14
0x140152d5e  mov     ecx, r15d
0x140152d61  mov     [rbp+57h+var_88], r14
0x140152d65  call    QosTimerGetCurrentTime
0x140152d6a  mov     [rbp+57h+var_78], rax
0x140152d6e  test    rbx, rbx
0x140152d71  jz      loc_140152FD9
0x140152d77  mov     rcx, [rbx]
0x140152d7a  lea     rdx, [rbp+57h+arg_8]
0x140152d7e  mov     r13, [rbx+1C0h]
0x140152d85  add     rbx, 0FFFFFFFFFFFFFFE0h
0x140152d89  mov     [rbp+57h+var_70], rcx
0x140152d8d  mov     r8b, 1
0x140152d90  mov     rcx, r13
0x140152d93  call    VmsOmObjectLockExclusive
0x140152d98  and     dword ptr [rbx+1ECh], 0FFFFFFFBh
0x140152d9f  mov     rsi, r14
0x140152da2  test    byte ptr [rbx+1E8h], 1
0x140152da9  mov     [rbp+57h+arg_18], r14
0x140152dad  mov     [rbp+57h+var_90], r14
0x140152db1  mov     dword ptr [rbp+57h+arg_10], r14d
0x140152db5  jnz     loc_140152EA5
0x140152dbb  cmp     [rbx+1D0h], r14d
0x140152dc2  jnz     short loc_140152DCD
0x140152dc4  mov     rdi, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140152dcb  jmp     short loc_140152DE2
0x140152dcd  mov     rax, [rbx+1E0h]
0x140152dd4  mov     rcx, [rax+4D8h]
0x140152ddb  mov     rdi, [rcx+21E8h]
0x140152de2  mov     rdx, [rbp+57h+var_78]
0x140152de6  lea     r14, [rbx+28h]
0x140152dea  mov     rcx, r14
0x140152ded  lea     r8, [rbp+57h+var_68]
0x140152df1  call    QosFlowNeedQueueFeedback
0x140152df6  test    al, al
0x140152df8  jz      short loc_140152E5E
0x140152dfa  test    rdi, rdi
0x140152dfd  jz      short loc_140152E5E
0x140152dff  mov     rcx, [rdi]; Lock
0x140152e02  lea     rdx, [rbp+57h+LockState]; LockState
0x140152e06  xor     r8d, r8d; Flags
0x140152e09  call    cs:__imp_NdisAcquireRWLockWrite
0x140152e10  nop     dword ptr [rax+rax+00h]
0x140152e15  lea     rsi, [rdi+8]
0x140152e19  mov     edx, r15d
0x140152e1c  mov     rcx, rsi
0x140152e1f  call    QosLineNeedSignal
0x140152e24  test    al, al
0x140152e26  jz      short loc_140152E33
0x140152e28  mov     edx, r15d
0x140152e2b  mov     rcx, rsi
0x140152e2e  call    QosLineSignalExternalEvent
0x140152e33  lea     r8, [rbp+57h+var_68]
0x140152e37  mov     rcx, rsi
0x140152e3a  call    QosLineQueryQueueFeedback
0x140152e3f  mov     rcx, [rdi]; Lock
0x140152e42  lea     rdx, [rbp+57h+LockState]; LockState
0x140152e46  call    cs:__imp_NdisReleaseRWLock
0x140152e4d  nop     dword ptr [rax+rax+00h]
0x140152e52  lea     rdx, [rbp+57h+var_68]
0x140152e56  mov     rcx, r14
0x140152e59  call    QosTbcAdjustSendWindow
0x140152e5e  lea     rax, [rbp+57h+var_90]
0x140152e62  mov     edx, r15d
0x140152e65  lea     r9, [rbp+57h+arg_10]
0x140152e69  mov     [rsp+0C0h+var_A0], rax
0x140152e6e  lea     r8, [rbp+57h+arg_18]
0x140152e72  mov     rcx, r14
0x140152e75  call    QosFlowProcessQueuedNetBufferLists
0x140152e7a  mov     r8, [rbp+57h+var_90]
0x140152e7e  xor     r14d, r14d
0x140152e81  test    r8, r8
0x140152e84  jz      short loc_140152EA1
0x140152e86  lea     r9, [rbp+57h+var_88]
0x140152e8a  mov     dword ptr [rsp+0C0h+var_A0], 0E0002023h
0x140152e92  mov     rdx, rdi
0x140152e95  mov     rcx, rbx
0x140152e98  call    VmsScQosDropNbls
0x140152e9d  mov     r12, [rbp+57h+var_88]
0x140152ea1  mov     rsi, [rbp+57h+arg_18]
0x140152ea5  mov     rcx, [r13+38h]; Lock
0x140152ea9  lea     rdx, [rbp+57h+arg_8]; LockState
0x140152ead  call    cs:__imp_NdisReleaseRWLock
0x140152eb4  nop     dword ptr [rax+rax+00h]
0x140152eb9  test    r12, r12
0x140152ebc  jz      short loc_140152ECB
0x140152ebe  mov     edx, 1
0x140152ec3  mov     rcx, r12
0x140152ec6  call    VmsNblHelperRefCountDecrementMany
0x140152ecb  test    rsi, rsi
0x140152ece  jz      loc_140152FC1
0x140152ed4  lea     r14, [rdi+8]
0x140152ed8  mov     edx, r15d
0x140152edb  mov     rcx, r14
0x140152ede  call    QosLineNeedSignal
0x140152ee3  test    al, al
0x140152ee5  jz      short loc_140152F1B
0x140152ee7  mov     rcx, [rdi]; Lock
0x140152eea  lea     rdx, [rbp+57h+LockState]; LockState
0x140152eee  mov     r8b, 1; Flags
0x140152ef1  call    cs:__imp_NdisAcquireRWLockWrite
0x140152ef8  nop     dword ptr [rax+rax+00h]
0x140152efd  mov     edx, r15d
0x140152f00  mov     rcx, r14
0x140152f03  call    QosLineSignalExternalEvent
0x140152f08  mov     rcx, [rdi]; Lock
0x140152f0b  lea     rdx, [rbp+57h+LockState]; LockState
0x140152f0f  call    cs:__imp_NdisReleaseRWLock
0x140152f16  nop     dword ptr [rax+rax+00h]
0x140152f1b  lea     rax, [rbp+57h+var_90]
0x140152f1f  mov     r8, rsi
0x140152f22  mov     [rsp+0C0h+var_98], rax
0x140152f27  mov     rcx, r14
0x140152f2a  lea     rax, [rbp+57h+var_80]
0x140152f2e  mov     [rsp+0C0h+var_A0], rax
0x140152f33  call    QosLineSendNetBufferLists
0x140152f38  xor     r14d, r14d
0x140152f3b  cmp     [rbx+1D8h], r14
0x140152f42  jnz     short loc_140152F7E
0x140152f44  mov     rcx, cs:VmsIfrLog
0x140152f4b  lea     rax, aFlowNicNull; "flow->Nic != NULL"
0x140152f52  mov     [rsp+0C0h+var_98], rax
0x140152f57  lea     r9d, [r14+0Bh]
0x140152f5b  lea     rax, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x140152f62  lea     r8d, [r14+13h]
0x140152f66  mov     [rsp+0C0h+var_A0], rax
0x140152f6b  call    WPP_RECORDER_SF_s
0x140152f70  cmp     [rbx+1D8h], r14
0x140152f77  jnz     short loc_140152F7E
0x140152f79  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "flow->Nic != ((void *)0)")
0x140152f7e  mov     r8, [rbp+57h+var_80]
0x140152f82  lea     r9, [rbp+57h+arg_10]
0x140152f86  mov     rdx, rdi
0x140152f89  mov     [rbp+57h+arg_10], r14
0x140152f8d  mov     rcx, rbx
0x140152f90  call    VmsScQosCompleteNbls
0x140152f95  mov     r8, [rbp+57h+arg_10]
0x140152f99  test    r8, r8
0x140152f9c  jz      short loc_140152FC1
0x140152f9e  mov     r9d, r14d
0x140152fa1  mov     rax, r8
0x140152fa4  mov     rax, [rax]
0x140152fa7  inc     r9d
0x140152faa  test    rax, rax
0x140152fad  jnz     short loc_140152FA4
0x140152faf  mov     rdx, [rbx+1D8h]
0x140152fb6  mov     ecx, [rbx+1D0h]
0x140152fbc  call    VmsScQospSendProcessedNbls
0x140152fc1  mov     rcx, rbx
0x140152fc4  call    VmsScQospDereferenceFlow
0x140152fc9  mov     rax, [rbp+57h+var_70]
0x140152fcd  mov     rbx, rax
0x140152fd0  test    rax, rax
0x140152fd3  jnz     loc_140152D77
0x140152fd9  add     rsp, 88h
0x140152fe0  pop     r15
0x140152fe2  pop     r14
0x140152fe4  pop     r13
0x140152fe6  pop     r12
0x140152fe8  pop     rdi
0x140152fe9  pop     rsi
0x140152fea  pop     rbx
0x140152feb  pop     rbp
0x140152fec  retn
```
