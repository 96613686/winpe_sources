# VmsScQospFlushDelay

- ea: `0x140152d68`
- end: `0x14015305e`
- name: `VmsScQospFlushDelay`
- size: `758`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140153188`

## callees

- `0x140018330`
- `0x140027a64`
- `0x14006b084`
- `0x14006dec8`
- `0x1400749f4`
- `0x14008497c`
- `0x14008faa8`
- `0x140090bd0`
- `0x140152c50`
- `0x140152d68`
- `0x1401b6c0c`
- `0x1401b6c58`
- `0x1401b7284`
- `0x1401b72f4`
- `0x1401b734c`
- `0x1401b738c`
- `0x1401b7fd0`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x140152eb6`
- `NDIS!NdisReleaseRWLock` at `0x140152f1d`
- `NDIS!NdisReleaseRWLock` at `0x140152f7f`
- `NDIS!NdisReleaseRWLock` at `0x140152eb6`
- `NDIS!NdisReleaseRWLock` at `0x140152f1d`
- `NDIS!NdisReleaseRWLock` at `0x140152f7f`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152e79`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152f61`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152e79`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152f61`

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
0x140152d68  push    rbp
0x140152d6a  push    rbx
0x140152d6b  push    rsi
0x140152d6c  push    rdi
0x140152d6d  push    r12
0x140152d6f  push    r13
0x140152d71  push    r14
0x140152d73  push    r15
0x140152d75  lea     rbp, [rsp-1Fh]
0x140152d7a  sub     rsp, 88h
0x140152d81  xor     eax, eax
0x140152d83  mov     r15d, ecx
0x140152d86  xor     r14d, r14d
0x140152d89  mov     ecx, ecx
0x140152d8b  shl     rcx, 6
0x140152d8f  xorps   xmm0, xmm0
0x140152d92  mov     [rbp+57h+var_48], eax
0x140152d95  mov     r8b, 1
0x140152d98  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x140152d9c  xor     edx, edx
0x140152d9e  mov     [rbp+57h+LockState.Flags], al
0x140152da1  mov     r12d, r14d
0x140152da4  mov     word ptr [rbp+57h+arg_8.OldIrql], ax
0x140152da8  mov     edi, r14d
0x140152dab  mov     [rbp+57h+arg_8.Flags], al
0x140152dae  mov     rax, cs:WPP_MAIN_CB.Dpc.ProcessorHistory
0x140152db5  movups  [rbp+57h+var_68], xmm0
0x140152db9  mov     [rbp+57h+var_80], r14
0x140152dbd  movups  [rbp+57h+var_58], xmm0
0x140152dc1  mov     rbx, [rcx+rax]
0x140152dc5  mov     [rcx+rax], r14
0x140152dc9  mov     [rcx+rax+8], r14
0x140152dce  mov     ecx, r15d
0x140152dd1  mov     [rbp+57h+var_88], r14
0x140152dd5  call    QosTimerGetCurrentTime
0x140152dda  mov     [rbp+57h+var_78], rax
0x140152dde  test    rbx, rbx
0x140152de1  jz      loc_140153049
0x140152de7  mov     rcx, [rbx]
0x140152dea  lea     rdx, [rbp+57h+arg_8]
0x140152dee  mov     r13, [rbx+1C0h]
0x140152df5  add     rbx, 0FFFFFFFFFFFFFFE0h
0x140152df9  mov     [rbp+57h+var_70], rcx
0x140152dfd  mov     r8b, 1
0x140152e00  mov     rcx, r13
0x140152e03  call    VmsOmObjectLockExclusive
0x140152e08  and     dword ptr [rbx+1ECh], 0FFFFFFFBh
0x140152e0f  mov     rsi, r14
0x140152e12  test    byte ptr [rbx+1E8h], 1
0x140152e19  mov     [rbp+57h+arg_18], r14
0x140152e1d  mov     [rbp+57h+var_90], r14
0x140152e21  mov     dword ptr [rbp+57h+arg_10], r14d
0x140152e25  jnz     loc_140152F15
0x140152e2b  cmp     [rbx+1D0h], r14d
0x140152e32  jnz     short loc_140152E3D
0x140152e34  mov     rdi, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140152e3b  jmp     short loc_140152E52
0x140152e3d  mov     rax, [rbx+1E0h]
0x140152e44  mov     rcx, [rax+4D8h]
0x140152e4b  mov     rdi, [rcx+21E8h]
0x140152e52  mov     rdx, [rbp+57h+var_78]
0x140152e56  lea     r14, [rbx+28h]
0x140152e5a  mov     rcx, r14
0x140152e5d  lea     r8, [rbp+57h+var_68]
0x140152e61  call    QosFlowNeedQueueFeedback
0x140152e66  test    al, al
0x140152e68  jz      short loc_140152ECE
0x140152e6a  test    rdi, rdi
0x140152e6d  jz      short loc_140152ECE
0x140152e6f  mov     rcx, [rdi]; Lock
0x140152e72  lea     rdx, [rbp+57h+LockState]; LockState
0x140152e76  xor     r8d, r8d; Flags
0x140152e79  call    cs:__imp_NdisAcquireRWLockWrite
0x140152e80  nop     dword ptr [rax+rax+00h]
0x140152e85  lea     rsi, [rdi+8]
0x140152e89  mov     edx, r15d
0x140152e8c  mov     rcx, rsi
0x140152e8f  call    QosLineNeedSignal
0x140152e94  test    al, al
0x140152e96  jz      short loc_140152EA3
0x140152e98  mov     edx, r15d
0x140152e9b  mov     rcx, rsi
0x140152e9e  call    QosLineSignalExternalEvent
0x140152ea3  lea     r8, [rbp+57h+var_68]
0x140152ea7  mov     rcx, rsi
0x140152eaa  call    QosLineQueryQueueFeedback
0x140152eaf  mov     rcx, [rdi]; Lock
0x140152eb2  lea     rdx, [rbp+57h+LockState]; LockState
0x140152eb6  call    cs:__imp_NdisReleaseRWLock
0x140152ebd  nop     dword ptr [rax+rax+00h]
0x140152ec2  lea     rdx, [rbp+57h+var_68]
0x140152ec6  mov     rcx, r14
0x140152ec9  call    QosTbcAdjustSendWindow
0x140152ece  lea     rax, [rbp+57h+var_90]
0x140152ed2  mov     edx, r15d
0x140152ed5  lea     r9, [rbp+57h+arg_10]
0x140152ed9  mov     [rsp+0C0h+var_A0], rax
0x140152ede  lea     r8, [rbp+57h+arg_18]
0x140152ee2  mov     rcx, r14
0x140152ee5  call    QosFlowProcessQueuedNetBufferLists
0x140152eea  mov     r8, [rbp+57h+var_90]
0x140152eee  xor     r14d, r14d
0x140152ef1  test    r8, r8
0x140152ef4  jz      short loc_140152F11
0x140152ef6  lea     r9, [rbp+57h+var_88]
0x140152efa  mov     dword ptr [rsp+0C0h+var_A0], 0E0002023h
0x140152f02  mov     rdx, rdi
0x140152f05  mov     rcx, rbx
0x140152f08  call    VmsScQosDropNbls
0x140152f0d  mov     r12, [rbp+57h+var_88]
0x140152f11  mov     rsi, [rbp+57h+arg_18]
0x140152f15  mov     rcx, [r13+38h]; Lock
0x140152f19  lea     rdx, [rbp+57h+arg_8]; LockState
0x140152f1d  call    cs:__imp_NdisReleaseRWLock
0x140152f24  nop     dword ptr [rax+rax+00h]
0x140152f29  test    r12, r12
0x140152f2c  jz      short loc_140152F3B
0x140152f2e  mov     edx, 1
0x140152f33  mov     rcx, r12
0x140152f36  call    VmsNblHelperRefCountDecrementMany
0x140152f3b  test    rsi, rsi
0x140152f3e  jz      loc_140153031
0x140152f44  lea     r14, [rdi+8]
0x140152f48  mov     edx, r15d
0x140152f4b  mov     rcx, r14
0x140152f4e  call    QosLineNeedSignal
0x140152f53  test    al, al
0x140152f55  jz      short loc_140152F8B
0x140152f57  mov     rcx, [rdi]; Lock
0x140152f5a  lea     rdx, [rbp+57h+LockState]; LockState
0x140152f5e  mov     r8b, 1; Flags
0x140152f61  call    cs:__imp_NdisAcquireRWLockWrite
0x140152f68  nop     dword ptr [rax+rax+00h]
0x140152f6d  mov     edx, r15d
0x140152f70  mov     rcx, r14
0x140152f73  call    QosLineSignalExternalEvent
0x140152f78  mov     rcx, [rdi]; Lock
0x140152f7b  lea     rdx, [rbp+57h+LockState]; LockState
0x140152f7f  call    cs:__imp_NdisReleaseRWLock
0x140152f86  nop     dword ptr [rax+rax+00h]
0x140152f8b  lea     rax, [rbp+57h+var_90]
0x140152f8f  mov     r8, rsi
0x140152f92  mov     [rsp+0C0h+var_98], rax
0x140152f97  mov     rcx, r14
0x140152f9a  lea     rax, [rbp+57h+var_80]
0x140152f9e  mov     [rsp+0C0h+var_A0], rax
0x140152fa3  call    QosLineSendNetBufferLists
0x140152fa8  xor     r14d, r14d
0x140152fab  cmp     [rbx+1D8h], r14
0x140152fb2  jnz     short loc_140152FEE
0x140152fb4  mov     rcx, cs:VmsIfrLog
0x140152fbb  lea     rax, aFlowNicNull; "flow->Nic != NULL"
0x140152fc2  mov     [rsp+0C0h+var_98], rax
0x140152fc7  lea     r9d, [r14+0Bh]
0x140152fcb  lea     rax, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x140152fd2  lea     r8d, [r14+13h]
0x140152fd6  mov     [rsp+0C0h+var_A0], rax
0x140152fdb  call    WPP_RECORDER_SF_s
0x140152fe0  cmp     [rbx+1D8h], r14
0x140152fe7  jnz     short loc_140152FEE
0x140152fe9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "flow->Nic != ((void *)0)")
0x140152fee  mov     r8, [rbp+57h+var_80]
0x140152ff2  lea     r9, [rbp+57h+arg_10]
0x140152ff6  mov     rdx, rdi
0x140152ff9  mov     [rbp+57h+arg_10], r14
0x140152ffd  mov     rcx, rbx
0x140153000  call    VmsScQosCompleteNbls
0x140153005  mov     r8, [rbp+57h+arg_10]
0x140153009  test    r8, r8
0x14015300c  jz      short loc_140153031
0x14015300e  mov     r9d, r14d
0x140153011  mov     rax, r8
0x140153014  mov     rax, [rax]
0x140153017  inc     r9d
0x14015301a  test    rax, rax
0x14015301d  jnz     short loc_140153014
0x14015301f  mov     rdx, [rbx+1D8h]
0x140153026  mov     ecx, [rbx+1D0h]
0x14015302c  call    VmsScQospSendProcessedNbls
0x140153031  mov     rcx, rbx
0x140153034  call    VmsScQospDereferenceFlow
0x140153039  mov     rax, [rbp+57h+var_70]
0x14015303d  mov     rbx, rax
0x140153040  test    rax, rax
0x140153043  jnz     loc_140152DE7
0x140153049  add     rsp, 88h
0x140153050  pop     r15
0x140153052  pop     r14
0x140153054  pop     r13
0x140153056  pop     r12
0x140153058  pop     rdi
0x140153059  pop     rsi
0x14015305a  pop     rbx
0x14015305b  pop     rbp
0x14015305c  retn
```
