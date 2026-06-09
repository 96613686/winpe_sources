# ComTaskHost::StartTaskWorker(void)

- ea: `0x140004a30`
- end: `0x140004ce7`
- name: `?StartTaskWorker@ComTaskHost@@AEAAJXZ`
- size: `695`
- prototype: `__int64 __fastcall(ComTaskHost *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140004940`

## callees

- `0x140004a30`
- `0x140005270`
- `0x1400058d0`
- `0x140009370`
- `0x140009be0`
- `0x140009c94`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004b37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004b56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004c5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004b37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004b56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004c5f`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x140004b40`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x140004b40`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140004b61`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140004c6a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140004b61`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140004c6a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x140004c33`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x140004c33`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x140004c3b`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x140004c3b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140004aa5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140004aa5`

## pseudocode

```c
__int64 __fastcall ComTaskHost::StartTaskWorker(ComTaskHost *this)
{
  volatile signed __int64 *v2; // rbp
  HRESULT Instance; // esi
  __int64 *v4; // rax
  __int64 v5; // r8
  int v6; // edx
  int v7; // ebx
  HANDLE CurrentThread; // rax
  int ThreadPriority; // edi
  HANDLE v10; // rax
  signed __int64 v11; // rax
  signed __int64 v12; // rbx
  signed __int64 v13; // rax
  _QWORD *v14; // rcx
  __int64 v15; // r8
  signed __int64 v16; // rax
  __int64 *v17; // rcx
  __int64 v18; // r8
  HANDLE v19; // rax
  char ppv; // [rsp+20h] [rbp-58h]
  char v22; // [rsp+28h] [rbp-50h]
  __int64 v23; // [rsp+30h] [rbp-48h]
  HANDLE Timer[7]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v25; // [rsp+88h] [rbp+10h] BYREF
  signed __int64 v26; // [rsp+90h] [rbp+18h]

  v25 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids, this);
  v2 = (volatile signed __int64 *)((char *)this + 72);
  Instance = CoCreateInstance(
               (const IID *const)((char *)this + 24),
               0,
               (*((_BYTE *)this + 48) != 0) + 4,
               &GUID_839d7762_5121_4009_9234_4f0d19394f04,
               (LPVOID *)this + 9);
  if ( Instance < 0 )
    goto LABEL_33;
  Instance = (**(__int64 (__fastcall ***)(ComTaskHost *, GUID *, __int64 *))this)(
               this,
               &GUID_00000000_0000_0000_c000_000000000046,
               &v25);
  if ( Instance < 0 )
    goto LABEL_33;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v4 = (__int64 *)*((_QWORD *)this + 7);
    if ( v4 )
      v5 = *v4;
    else
      v5 = 0;
    v6 = v25;
    v23 = v5;
    v22 = v25;
    ppv = _InterlockedCompareExchange64(v2, 0, 0);
    WPP_SF_qqqS(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v5, (_DWORD)this, ppv, v22, v23);
  }
  v7 = *((_DWORD *)this + 16);
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  if ( ThreadPriority != 0x7FFFFFFF )
  {
    v10 = GetCurrentThread();
    if ( !SetThreadPriority(v10, v7) )
      ThreadPriority = 0x7FFFFFFF;
  }
  v11 = _InterlockedCompareExchange64(v2, 0, 0);
  v12 = v11;
  v26 = v11;
  if ( v11 )
    (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v11 + 8LL))(v11);
  if ( *((_BYTE *)this + 48) )
  {
    v13 = _InterlockedCompareExchange64(v2, 0, 0);
    v14 = (_QWORD *)*((_QWORD *)this + 7);
    v15 = v14 ? *v14 : 0LL;
    Instance = (*(__int64 (__fastcall **)(signed __int64, __int64, __int64))(*(_QWORD *)v13 + 24LL))(v13, v25, v15);
  }
  else
  {
    ComCallAutoCancel::ComCallAutoCancel(Timer);
    v16 = _InterlockedCompareExchange64(v2, 0, 0);
    v17 = (__int64 *)*((_QWORD *)this + 7);
    if ( v17 )
      v18 = *v17;
    else
      v18 = 0;
    Instance = (*(__int64 (__fastcall **)(signed __int64, __int64, __int64))(*(_QWORD *)v16 + 24LL))(v16, v25, v18);
    if ( Timer[0] )
    {
      DeleteTimerQueueTimer(0, Timer[0], (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      CoDisableCallCancellation(0);
    }
  }
  if ( v12 )
    (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( ThreadPriority != 0x7FFFFFFF )
  {
    v19 = GetCurrentThread();
    SetThreadPriority(v19, ThreadPriority);
  }
  if ( Instance < 0 )
  {
LABEL_33:
    ComTaskHost::HandleReportingState(this, (unsigned int)Instance, 2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids,
        this,
        Instance);
  }
  else
  {
    Instance = 0;
  }
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140004a30  mov     [rsp+arg_18], rbx
0x140004a35  push    rbp
0x140004a36  push    rsi
0x140004a37  push    rdi
0x140004a38  push    r14
0x140004a3a  push    r15
0x140004a3c  sub     rsp, 50h
0x140004a40  mov     r14, rcx
0x140004a43  mov     [rsp+78h+arg_8], 0
0x140004a4f  lea     r15, WPP_GLOBAL_Control
0x140004a56  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a5d  cmp     rcx, r15
0x140004a60  jz      short loc_140004A80
0x140004a62  test    byte ptr [rcx+1Ch], 4
0x140004a66  jz      short loc_140004A80
0x140004a68  mov     edx, 0Eh
0x140004a6d  mov     r9, r14
0x140004a70  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x140004a77  mov     rcx, [rcx+10h]
0x140004a7b  call    WPP_SF_q
0x140004a80  lea     rbp, [r14+48h]
0x140004a84  xor     r8d, r8d
0x140004a87  cmp     [r14+30h], r8b
0x140004a8b  setnz   r8b
0x140004a8f  add     r8d, 4; dwClsContext
0x140004a93  lea     rcx, [r14+18h]; rclsid
0x140004a97  mov     [rsp+78h+ppv], rbp; ppv
0x140004a9c  lea     r9, _GUID_839d7762_5121_4009_9234_4f0d19394f04; riid
0x140004aa3  xor     edx, edx; pUnkOuter
0x140004aa5  call    cs:__imp_CoCreateInstance
0x140004aab  mov     esi, eax
0x140004aad  test    eax, eax
0x140004aaf  js      loc_140004C78
0x140004ab5  mov     rax, [r14]
0x140004ab8  lea     r8, [rsp+78h+arg_8]
0x140004ac0  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140004ac7  mov     rcx, r14
0x140004aca  mov     rax, [rax]
0x140004acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ad2  mov     esi, eax
0x140004ad4  test    eax, eax
0x140004ad6  js      loc_140004C78
0x140004adc  mov     rax, cs:WPP_GLOBAL_Control
0x140004ae3  cmp     rax, r15
0x140004ae6  jz      short loc_140004B33
0x140004ae8  test    byte ptr [rax+1Ch], 4
0x140004aec  jz      short loc_140004B33
0x140004aee  mov     rax, [r14+38h]
0x140004af2  test    rax, rax
0x140004af5  jz      short loc_140004AFC
0x140004af7  mov     r8, [rax]
0x140004afa  jmp     short loc_140004AFF
0x140004afc  xor     r8d, r8d
0x140004aff  mov     rdx, [rsp+78h+arg_8]
0x140004b07  xor     ecx, ecx
0x140004b09  xor     eax, eax
0x140004b0b  lock cmpxchg [rbp+0], rcx
0x140004b11  mov     [rsp+78h+var_48], r8
0x140004b16  mov     [rsp+78h+var_50], rdx
0x140004b1b  mov     [rsp+78h+ppv], rax
0x140004b20  mov     r9, r14
0x140004b23  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b2a  mov     rcx, [rcx+10h]
0x140004b2e  call    WPP_SF_qqqS
0x140004b33  mov     ebx, [r14+40h]
0x140004b37  call    cs:__imp_GetCurrentThread
0x140004b3d  mov     rcx, rax; hThread
0x140004b40  call    cs:__imp_GetThreadPriority
0x140004b46  mov     edi, eax
0x140004b48  mov     [rsp+78h+arg_0], eax
0x140004b4f  cmp     eax, 7FFFFFFFh
0x140004b54  jz      short loc_140004B77
0x140004b56  call    cs:__imp_GetCurrentThread
0x140004b5c  mov     rcx, rax; hThread
0x140004b5f  mov     edx, ebx; nPriority
0x140004b61  call    cs:__imp_SetThreadPriority
0x140004b67  test    eax, eax
0x140004b69  jnz     short loc_140004B77
0x140004b6b  mov     edi, 7FFFFFFFh
0x140004b70  mov     [rsp+78h+arg_0], edi
0x140004b77  xor     ecx, ecx
0x140004b79  xor     eax, eax
0x140004b7b  lock cmpxchg [rbp+0], rcx
0x140004b81  mov     rbx, rax
0x140004b84  mov     [rsp+78h+arg_10], rax
0x140004b8c  jz      short loc_140004B9E
0x140004b8e  mov     rax, [rax]
0x140004b91  mov     rcx, rbx
0x140004b94  mov     rax, [rax+8]
0x140004b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b9d  nop
0x140004b9e  cmp     byte ptr [r14+30h], 0
0x140004ba3  jz      short loc_140004BDE
0x140004ba5  xor     ecx, ecx
0x140004ba7  xor     eax, eax
0x140004ba9  lock cmpxchg [rbp+0], rcx
0x140004baf  mov     rcx, [rax]
0x140004bb2  mov     r9, [rcx+18h]
0x140004bb6  mov     rcx, [r14+38h]
0x140004bba  test    rcx, rcx
0x140004bbd  jz      short loc_140004BC4
0x140004bbf  mov     r8, [rcx]
0x140004bc2  jmp     short loc_140004BC7
0x140004bc4  xor     r8d, r8d
0x140004bc7  mov     rdx, [rsp+78h+arg_8]
0x140004bcf  mov     rcx, rax
0x140004bd2  mov     rax, r9
0x140004bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004bda  mov     esi, eax
0x140004bdc  jmp     short loc_140004C42
0x140004bde  lea     rcx, [rsp+78h+Timer]; Parameter
0x140004be3  call    ??0ComCallAutoCancel@@QEAA@XZ; ComCallAutoCancel::ComCallAutoCancel(void)
0x140004be8  nop
0x140004be9  xor     ecx, ecx
0x140004beb  xor     eax, eax
0x140004bed  lock cmpxchg [rbp+0], rcx
0x140004bf3  mov     rcx, [rax]
0x140004bf6  mov     r9, [rcx+18h]
0x140004bfa  mov     rcx, [r14+38h]
0x140004bfe  test    rcx, rcx
0x140004c01  jz      short loc_140004C08
0x140004c03  mov     r8, [rcx]
0x140004c06  jmp     short loc_140004C0B
0x140004c08  xor     r8d, r8d
0x140004c0b  mov     rdx, [rsp+78h+arg_8]
0x140004c13  mov     rcx, rax
0x140004c16  mov     rax, r9
0x140004c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c1e  mov     esi, eax
0x140004c20  mov     rdx, [rsp+78h+Timer]; Timer
0x140004c25  test    rdx, rdx
0x140004c28  jz      short loc_140004C42
0x140004c2a  xor     ecx, ecx; TimerQueue
0x140004c2c  mov     r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x140004c33  call    cs:__imp_DeleteTimerQueueTimer
0x140004c39  xor     ecx, ecx; pReserved
0x140004c3b  call    cs:__imp_CoDisableCallCancellation
0x140004c41  nop
0x140004c42  test    rbx, rbx
0x140004c45  jz      short loc_140004C57
0x140004c47  mov     rax, [rbx]
0x140004c4a  mov     rcx, rbx
0x140004c4d  mov     rax, [rax+10h]
0x140004c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c56  nop
0x140004c57  cmp     edi, 7FFFFFFFh
0x140004c5d  jz      short loc_140004C70
0x140004c5f  call    cs:__imp_GetCurrentThread
0x140004c65  mov     edx, edi; nPriority
0x140004c67  mov     rcx, rax; hThread
0x140004c6a  call    cs:__imp_SetThreadPriority
0x140004c70  test    esi, esi
0x140004c72  js      short loc_140004C78
0x140004c74  xor     esi, esi
0x140004c76  jmp     short loc_140004CB7
0x140004c78  mov     r8d, 2
0x140004c7e  mov     edx, esi
0x140004c80  mov     rcx, r14
0x140004c83  call    ?HandleReportingState@ComTaskHost@@AEAAJJW4StateType@1@@Z; ComTaskHost::HandleReportingState(long,ComTaskHost::StateType)
0x140004c88  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c8f  cmp     rcx, r15
0x140004c92  jz      short loc_140004CB7
0x140004c94  test    byte ptr [rcx+1Ch], 1
0x140004c98  jz      short loc_140004CB7
0x140004c9a  mov     edx, 10h
0x140004c9f  mov     dword ptr [rsp+78h+ppv], esi
0x140004ca3  mov     r9, r14
0x140004ca6  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x140004cad  mov     rcx, [rcx+10h]
0x140004cb1  call    WPP_SF_qD
0x140004cb6  nop
0x140004cb7  mov     rcx, [rsp+78h+arg_8]
0x140004cbf  test    rcx, rcx
0x140004cc2  jz      short loc_140004CD1
0x140004cc4  mov     rax, [rcx]
0x140004cc7  mov     rax, [rax+10h]
0x140004ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004cd0  nop
0x140004cd1  mov     eax, esi
0x140004cd3  mov     rbx, [rsp+78h+arg_18]
0x140004cdb  add     rsp, 50h
0x140004cdf  pop     r15
0x140004ce1  pop     r14
0x140004ce3  pop     rdi
0x140004ce4  pop     rsi
0x140004ce5  pop     rbp
0x140004ce6  retn
```
