# Smb2ScavengerThread

- ea: `0x14000b3f0`
- end: `0x14000bb78`
- name: `Smb2ScavengerThread`
- size: `1928`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x1400054c8`
- `0x140006ad0`
- `0x14000ae60`
- `0x14000b3f0`
- `0x14000bb80`
- `0x14000bbb8`
- `0x14000bec0`
- `0x14000c070`
- `0x14000c450`
- `0x14001a6d4`
- `0x140020578`
- `0x140020be8`
- `0x140020e78`
- `0x1400222ec`
- `0x140023338`
- `0x140025760`
- `0x1400293c8`
- `0x140029660`
- `0x140029a88`
- `0x1400384d0`
- `0x14005a3e8`
- `0x140077020`
- `0x140077118`

## import_xrefs

- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14003ae40`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14003ae40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b476`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b4ca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b52c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b621`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b6fd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003ad88`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b476`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b4ca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b52c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b621`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b6fd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003ad88`
- `ntoskrnl!KeSetEvent` at `0x14000bb32`
- `ntoskrnl!KeSetEvent` at `0x14000bb32`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b4aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b4fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b593`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b65c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b6da`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b721`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bb1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bb67`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ad65`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b4aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b4fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b593`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b65c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b6da`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b721`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bb1a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bb67`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003ad65`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14000b5b7`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14000b5b7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000b7cd`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000b7cd`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b80e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b8ec`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b80e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b8ec`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14000b68b`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14000b68b`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14000b935`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14000b935`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14000b8ce`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14000b955`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14000b8ce`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14000b955`
- `srvnet!SrvLibUpdateIdleLogic` at `0x14000b60e`
- `srvnet!SrvLibUpdateIdleLogic` at `0x14000b60e`
- `srvnet!SrvAdminTakeActionToAllowPowerDown` at `0x14000b848`
- `srvnet!SrvAdminTakeActionToAllowPowerDown` at `0x14000b848`
- `srvnet!SrvLibMarkServerAsIdle` at `0x14000bb51`
- `srvnet!SrvLibMarkServerAsIdle` at `0x14000bb51`

## string_xrefs

- `0x14003ad0a`: `Idle session, no open files`

## pseudocode

```c
void Smb2ScavengerThread()
{
  char v0; // r15
  int v1; // ebx
  __int64 v2; // rsi
  unsigned int v3; // ebp
  __int64 v4; // rdi
  _QWORD *Instance; // rax
  KIRQL v6; // al
  __int64 v7; // rdi
  KIRQL v8; // bp
  __int64 *v9; // rax
  __int64 v10; // r14
  KIRQL v11; // al
  struct _DEVICE_OBJECT *DpcData; // r8
  KIRQL v13; // r9
  volatile signed __int64 *p_Lock; // rbp
  signed __int64 k; // rdx
  unsigned int v16; // eax
  ULONG MaximumProcessorCount; // eax
  bool v18; // r9
  KIRQL v19; // al
  KIRQL v20; // bl
  __int64 v21; // rdi
  __int64 *v22; // rbx
  void **v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  void **v26; // r12
  volatile signed __int64 **v27; // r12
  void (__fastcall *v28)(void *); // rax
  int v29; // edx
  int v30; // r8d
  signed __int64 v31; // rcx
  __int64 v32; // r13
  __int64 v33; // rax
  PVOID v34; // r14
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  __int64 *v38; // r8
  _QWORD **v39; // r8
  _QWORD *j; // rcx
  __int64 v41; // rax
  __int64 v42; // r10
  ULONG m; // r11d
  _QWORD *v44; // r14
  __int64 v45; // rdx
  __int64 v46; // rdi
  const wchar_t *v47; // rcx
  __int64 Next; // rdi
  int v49; // eax
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // r8
  void *v52; // rdx
  unsigned __int64 v53; // rax
  __int64 v54; // [rsp+50h] [rbp-48h] BYREF
  PVOID Context; // [rsp+58h] [rbp-40h]
  KIRQL v56; // [rsp+A8h] [rbp+10h]
  int v57; // [rsp+B0h] [rbp+18h]
  __int64 i; // [rsp+B8h] [rbp+20h] BYREF

  v0 = 0;
  v1 = Smb2LiveDumpFlags & 1;
  v57 = v1;
  v2 = MEMORY[0xFFFFF78000000014];
  if ( !byte_14004B71A )
  {
    v3 = 0;
    v4 = MEMORY[0xFFFFF78000000014] - qword_14004B700;
    do
    {
      Instance = (_QWORD *)Srv2GetInstance(v3);
      Context = Instance;
      if ( Instance )
      {
        if ( *(_BYTE *)Instance )
        {
          Srv2DereferenceInstance(Instance);
        }
        else
        {
          v22 = (__int64 *)Instance[20];
          i = 0;
LABEL_53:
          v32 = *v22;
          v56 = 0;
          v33 = *(_QWORD *)(*v22 + 120) & i;
          for ( i = v33; ; v33 = i )
          {
            v54 = v33;
            v23 = (void **)RfspTable64Enumerate(
                             v32,
                             (unsigned int)&v54,
                             (unsigned int)&i,
                             0,
                             *(_QWORD *)(v32 + 16),
                             0,
                             0,
                             1);
            v26 = v23;
            if ( !v23 )
              break;
            if ( !*(_QWORD *)(v32 + 160) )
            {
              v27 = (volatile signed __int64 **)*v23;
LABEL_43:
              if ( !v27 )
                break;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_qiiid(
                  WPP_GLOBAL_Control->AttachedDevice,
                  v24,
                  v25,
                  v27,
                  v4,
                  v27[19],
                  v27[2],
                  *((_DWORD *)v27 + 28));
              }
              if ( v2 > (__int64)v27[19] )
              {
                ++*(_DWORD *)(Srv2Statistics + 40);
                v35 = (int)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_q(
                    WPP_GLOBAL_Control->AttachedDevice,
                    11,
                    &WPP_be414516cac2331e8cbf8ad61f1e9a3c_Traceguids,
                    v27);
                }
                if ( (byte_14004C339 & 0x10) != 0 )
                  McTemplateK0iqz_EtwWriteTransfer(
                    v35,
                    v24,
                    v25,
                    (unsigned int)*v27,
                    v3,
                    (__int64)L"Kickoff time expired");
                Smb2CloseSession(v27, 2);
              }
              else if ( (unsigned __int8)SrvAdminTakeActionToAllowPowerDown() )
              {
                v36 = (int)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_q(
                    WPP_GLOBAL_Control->AttachedDevice,
                    12,
                    &WPP_be414516cac2331e8cbf8ad61f1e9a3c_Traceguids,
                    v27);
                }
                if ( (byte_14004C339 & 0x10) != 0 )
                  McTemplateK0iqz_EtwWriteTransfer(
                    v36,
                    v29,
                    v30,
                    (unsigned int)*v27,
                    v3,
                    (__int64)L"Idle power down policy");
                Smb2CloseSession(v27, 0);
              }
              else if ( *((_DWORD *)v27 + 28) || (__int64)v27[2] > v4 )
              {
                v0 = 1;
              }
              else
              {
                v37 = (int)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_q(
                    WPP_GLOBAL_Control->AttachedDevice,
                    13,
                    &WPP_be414516cac2331e8cbf8ad61f1e9a3c_Traceguids,
                    v27);
                }
                if ( (byte_14004C339 & 0x10) != 0 )
                  McTemplateK0iqz_EtwWriteTransfer(
                    v37,
                    v29,
                    v30,
                    (unsigned int)*v27,
                    v3,
                    (__int64)L"Idle session, no open files");
                Smb2CloseSession(v27, 1);
              }
              v31 = _InterlockedDecrement64(v27[3]);
              if ( v31 == -1 )
              {
                __int2c();
              }
              else if ( !v31 )
              {
                Smb2FreeSession(v27);
              }
              goto LABEL_53;
            }
            if ( (*(_BYTE *)(v32 + 152) & 0x40) != 0 )
              v56 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)v32);
            else
              ExAcquirePushLockSharedEx(v32, 0);
            v27 = (volatile signed __int64 **)*v26;
            if ( ((unsigned __int8)v27 & 3) == 0 )
            {
              v28 = *(void (__fastcall **)(void *))(v32 + 160);
              if ( v28 )
                v28(v27);
              if ( (*(_BYTE *)(v32 + 152) & 0x40) != 0 )
                ExReleaseSpinLockShared((PEX_SPIN_LOCK)v32, v56);
              else
                ExReleasePushLockSharedEx(v32, 0);
              goto LABEL_43;
            }
            if ( (*(_BYTE *)(v32 + 152) & 0x40) != 0 )
              ExReleaseSpinLockShared((PEX_SPIN_LOCK)v32, v56);
            else
              ExReleasePushLockSharedEx(v32, 0);
          }
          v34 = Context;
          Smb2ScavengerProcessSyncRedirectTreeConnects(*((_QWORD *)Context + 20));
          Srv2DereferenceInstance(v34);
        }
      }
      ++v3;
    }
    while ( v3 < 6 );
    v6 = KeAcquireSpinLockRaiseToDpc(&Smb2ClientPendingListLock);
    v1 = v57;
    while ( (__int64 *)Smb2ClientPendingList != &Smb2ClientPendingList )
    {
      v21 = Smb2ClientPendingList - 64;
      if ( *(_QWORD *)(Smb2ClientPendingList + 56) > v2 )
      {
        v0 = 1;
        break;
      }
      if ( ((_InterlockedExchangeAdd64((volatile signed __int64 *)v21, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        __int2c();
      if ( !*(_BYTE *)(v21 + 104) )
        *(_BYTE *)(v21 + 104) = 1;
      KeReleaseSpinLock(&Smb2ClientPendingListLock, v6);
      Smb2CloseClient(v21);
      Smb2DereferenceClient(v21);
      v6 = KeAcquireSpinLockRaiseToDpc(&Smb2ClientPendingListLock);
    }
    KeReleaseSpinLock(&Smb2ClientPendingListLock, v6);
    v7 = MEMORY[0xFFFFF78000000014];
    v8 = KeAcquireSpinLockRaiseToDpc(&Smb2ObjectContextListLock);
    v9 = (__int64 *)Smb2ObjectContextList;
    while ( v9 != &Smb2ObjectContextList )
    {
      v38 = v9;
      v9 = (__int64 *)*v9;
      v39 = (_QWORD **)(v38 + 2);
      for ( j = *v39; j != v39; j = (_QWORD *)*j )
      {
        v44 = j - 3;
        if ( *((_DWORD *)j - 3) == 220 )
        {
          v45 = v44[6];
          if ( v45 )
          {
            if ( v45 <= v7 )
            {
              Smb2ReferenceShareLockState(j - 3);
              KeReleaseSpinLock(&Smb2ObjectContextListLock, v8);
              Smb2ClearSharesForSlowIOReal(v44);
              Smb2DereferenceShareLockState(v44);
              v8 = KeAcquireSpinLockRaiseToDpc(&Smb2ObjectContextListLock);
              v9 = (__int64 *)Smb2ObjectContextList;
              break;
            }
          }
        }
      }
    }
    KeReleaseSpinLock(&Smb2ObjectContextListLock, v8);
  }
  v10 = v2 - LastStalledIoDumpCapturedTime;
  if ( !LastStalledIoDumpCapturedTime )
    v10 = 0x7FFFFFFFFFFFFFFFLL;
  v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.SystemArgument2);
  DpcData = (struct _DEVICE_OBJECT *)WPP_MAIN_CB.Dpc.DpcData;
  v13 = v11;
  while ( DpcData != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Dpc.DpcData )
  {
    p_Lock = (volatile signed __int64 *)&DpcData[-2].DeviceLock.Header.Lock;
    for ( k = (unsigned int)_InterlockedCompareExchange64(
                              (volatile signed __int64 *)&DpcData[-2].DeviceLock.Header.Lock,
                              0,
                              0); k; k = v16 )
    {
      v16 = _InterlockedCompareExchange64(p_Lock, k + 1, k);
      if ( v16 == k )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.SystemArgument2, v13);
        goto LABEL_17;
      }
    }
    DpcData = *(struct _DEVICE_OBJECT **)&DpcData->Type;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.SystemArgument2, v13);
  p_Lock = 0;
LABEL_17:
  while ( p_Lock )
  {
    if ( v10 >= 18000000000LL && (unsigned __int8)Smb2IsLiveDumpEnabled(1) )
    {
      if ( **((_BYTE **)p_Lock + 8) == 2 )
      {
        v41 = 120;
        if ( (unsigned int)Smb2StalledIoLiveDumpThresholdInSeconds < 0x78 )
          v41 = (unsigned int)Smb2StalledIoLiveDumpThresholdInSeconds;
      }
      else
      {
        v41 = (unsigned int)Smb2StalledIoLiveDumpThresholdInSeconds;
      }
      v46 = Srv2ConnectionFindInProgressWorkItem(p_Lock, Smb2MatchStalledIoWorkItem, 10000000 * v41);
      if ( v46 )
      {
        if ( **((_BYTE **)p_Lock + 8) >= 6u )
          v47 = L"UNKNOWN";
        else
          v47 = INSTANCE_NAMES[**((unsigned __int8 **)p_Lock + 8)];
        v49 = DbgkWerCaptureLiveKernelDump(v47, 405, 1, v46, 0, 0, 0, 0, v1);
        if ( v49 < 0 )
        {
          if ( v49 == -1073741790 )
          {
            v50 = 0;
            v53 = _InterlockedCompareExchange64(&Smb2StalledIoLiveDumpFailedEventThrottle, 0, 0);
            while ( 1 )
            {
              if ( v53 )
              {
                if ( v53 >= MEMORY[0xFFFFF78000000320] )
                  break;
                v50 = MEMORY[0xFFFFF78000000320] - v53;
                if ( MEMORY[0xFFFFF78000000320] - v53 < qword_14004B728 )
                  break;
              }
              v51 = v53;
              v53 = _InterlockedCompareExchange64(
                      &Smb2StalledIoLiveDumpFailedEventThrottle,
                      MEMORY[0xFFFFF78000000320],
                      v53);
              if ( v53 == v51 )
              {
                if ( byte_14004C339 >= 0 )
                  break;
                v52 = &SRV2_EVENT_LIVE_DUMP_THROTTLED;
                goto LABEL_126;
              }
            }
          }
        }
        else
        {
          LastStalledIoDumpCapturedTime = v2;
          if ( (byte_14004C339 & 0x40) != 0 )
          {
            v52 = &SRV2_EVENT_LIVE_DUMP_SUCCEEDED;
LABEL_126:
            McTemplateK0q_EtwWriteTransfer(v50, v52, v51, 1);
          }
        }
        Srv2DereferenceWorkItem(v46);
        Srv2DereferenceConnection((PVOID)p_Lock);
        break;
      }
    }
    else
    {
      Smb2LogEventForStalledWorkItem(p_Lock);
    }
    Next = Srv2GlobalConnectionListGetNext(p_Lock);
    Srv2DereferenceConnection((PVOID)p_Lock);
    p_Lock = (volatile signed __int64 *)Next;
  }
  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  v18 = 1;
  if ( Smb2StartIdleTimeoutInSec )
  {
    v42 = 0;
    for ( m = 0;
          m < MaximumProcessorCount;
          v42 += *((unsigned int *)Srv2HotGlobals + 32 * (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) + 12) )
    {
      ++m;
    }
    v18 = v42 == qword_14004B710;
    qword_14004B710 = v42;
  }
  else
  {
    qword_14004B710 = 0;
  }
  SrvLibUpdateIdleLogic(&Smb2IdleLogic, v18, (unsigned int)Smb2StartIdleTimeoutInSec);
  v19 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v20 = v19;
  if ( byte_14004B71A )
  {
    LOBYTE(word_14004B718) = 0;
    KeReleaseSpinLock(&SpinLock, v19);
    KeSetEvent(&Object, 0, 0);
  }
  else
  {
    LOBYTE(word_14004B718) = v0;
    if ( v0 )
    {
      KeReleaseSpinLock(&SpinLock, v19);
      KeSetCoalescableTimer(&Timer, (LARGE_INTEGER)-450000000LL, 0, 0x1388u, &Dpc);
    }
    else
    {
      word_14004B718 = 0;
      SrvLibMarkServerAsIdle(&Smb2IdleLogic);
      KeReleaseSpinLock(&SpinLock, v20);
    }
  }
}

```

## disassembly

```asm
0x14000b3f0  mov     rax, rsp
0x14000b3f3  push    rbx
0x14000b3f4  push    r15
0x14000b3f6  sub     rsp, 88h
0x14000b3fd  mov     ebx, cs:Smb2LiveDumpFlags
0x14000b403  xor     r15b, r15b
0x14000b406  mov     [rax+8], rbp
0x14000b40a  and     ebx, 1
0x14000b40d  mov     [rax-18h], rsi
0x14000b411  mov     [rax-20h], rdi
0x14000b415  mov     [rax-28h], r12
0x14000b419  xor     r12d, r12d
0x14000b41c  mov     [rax-30h], r13
0x14000b420  mov     r13, 0FFFFF78000000014h
0x14000b42a  mov     [rax-38h], r14
0x14000b42e  mov     [rsp+98h+arg_10], ebx
0x14000b435  mov     rsi, [r13+0]
0x14000b439  cmp     cs:byte_14004B71A, r12b
0x14000b440  jnz     loc_14000B507
0x14000b446  mov     rdi, rsi
0x14000b449  mov     ebp, r12d
0x14000b44c  sub     rdi, cs:qword_14004B700
0x14000b453  mov     ecx, ebp
0x14000b455  call    Srv2GetInstance
0x14000b45a  mov     [rsp+98h+Context], rax
0x14000b45f  test    rax, rax
0x14000b462  jnz     loc_14000B73D
0x14000b468  inc     ebp
0x14000b46a  cmp     ebp, 6
0x14000b46d  jb      short loc_14000B453
0x14000b46f  lea     rcx, Smb2ClientPendingListLock; SpinLock
0x14000b476  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b47d  nop     dword ptr [rax+rax+00h]
0x14000b482  mov     ebx, [rsp+98h+arg_10]
0x14000b489  lea     rbp, Smb2ClientPendingList
0x14000b490  mov     rcx, cs:Smb2ClientPendingList
0x14000b497  movzx   edx, al; NewIrql
0x14000b49a  cmp     rcx, rbp
0x14000b49d  jnz     loc_14000B6A3
0x14000b4a3  lea     rcx, Smb2ClientPendingListLock; SpinLock
0x14000b4aa  call    cs:__imp_KeReleaseSpinLock
0x14000b4b1  nop     dword ptr [rax+rax+00h]
0x14000b4b6  mov     rdi, 0FFFFF78000000014h
0x14000b4c0  lea     rcx, Smb2ObjectContextListLock; SpinLock
0x14000b4c7  mov     rdi, [rdi]
0x14000b4ca  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b4d1  nop     dword ptr [rax+rax+00h]
0x14000b4d6  movzx   ebp, al
0x14000b4d9  lea     r13, Smb2ObjectContextList
0x14000b4e0  mov     rax, cs:Smb2ObjectContextList
0x14000b4e7  cmp     rax, r13
0x14000b4ea  jnz     loc_14000BAA4
0x14000b4f0  movzx   edx, bpl; NewIrql
0x14000b4f4  lea     rcx, Smb2ObjectContextListLock; SpinLock
0x14000b4fb  call    cs:__imp_KeReleaseSpinLock
0x14000b502  nop     dword ptr [rax+rax+00h]
0x14000b507  mov     rax, cs:LastStalledIoDumpCapturedTime
0x14000b50e  mov     rcx, 7FFFFFFFFFFFFFFFh
0x14000b518  mov     r14, rsi
0x14000b51b  sub     r14, rax
0x14000b51e  test    rax, rax
0x14000b521  cmovz   r14, rcx
0x14000b525  lea     rcx, WPP_MAIN_CB.Dpc.SystemArgument2; SpinLock
0x14000b52c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b533  nop     dword ptr [rax+rax+00h]
0x14000b538  mov     r8, cs:WPP_MAIN_CB.Dpc.DpcData
0x14000b53f  lea     r10, WPP_MAIN_CB.Dpc.DpcData
0x14000b546  movzx   r9d, al
0x14000b54a  cmp     r8, r10
0x14000b54d  jz      loc_14000B716
0x14000b553  lea     rbp, [r8-188h]
0x14000b55a  mov     rcx, r12
0x14000b55d  xor     eax, eax
0x14000b55f  lock cmpxchg [rbp+0], rcx
0x14000b565  mov     edx, eax
0x14000b567  test    rdx, rdx
0x14000b56a  jz      loc_14000B735
0x14000b570  lea     rcx, [rdx+1]
0x14000b574  mov     rax, rdx
0x14000b577  lock cmpxchg [rbp+0], rcx
0x14000b57d  mov     ecx, eax
0x14000b57f  cmp     rcx, rdx
0x14000b582  jnz     loc_14000B70E
0x14000b588  movzx   edx, r9b; NewIrql
0x14000b58c  lea     rcx, WPP_MAIN_CB.Dpc.SystemArgument2; SpinLock
0x14000b593  call    cs:__imp_KeReleaseSpinLock
0x14000b59a  nop     dword ptr [rax+rax+00h]
0x14000b59f  mov     r13, 430E23400h
0x14000b5a9  test    rbp, rbp
0x14000b5ac  jnz     loc_14000BAB6
0x14000b5b2  mov     ecx, 0FFFFh; GroupNumber
0x14000b5b7  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14000b5be  nop     dword ptr [rax+rax+00h]
0x14000b5c3  cmp     cs:Smb2StartIdleTimeoutInSec, 0
0x14000b5ca  mov     r9b, 1
0x14000b5cd  mov     r14, [rsp+98h+var_38]
0x14000b5d2  mov     r8d, eax
0x14000b5d5  mov     r13, [rsp+98h+var_30]
0x14000b5da  mov     rdi, [rsp+98h+var_20]
0x14000b5df  mov     rsi, [rsp+98h+var_18]
0x14000b5e7  mov     rbp, [rsp+98h+arg_0]
0x14000b5ef  jnz     loc_14000BAF5
0x14000b5f5  mov     cs:qword_14004B710, r12
0x14000b5fc  mov     r8d, cs:Smb2StartIdleTimeoutInSec
0x14000b603  lea     rcx, Smb2IdleLogic
0x14000b60a  movzx   edx, r9b
0x14000b60e  call    cs:__imp_SrvLibUpdateIdleLogic
0x14000b615  nop     dword ptr [rax+rax+00h]
0x14000b61a  lea     rcx, SpinLock; SpinLock
0x14000b621  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b628  nop     dword ptr [rax+rax+00h]
0x14000b62d  cmp     cs:byte_14004B71A, 0
0x14000b634  movzx   ebx, al
0x14000b637  mov     r12, [rsp+98h+var_28]
0x14000b63c  jnz     loc_14000BB09
0x14000b642  mov     byte ptr cs:word_14004B718, r15b
0x14000b649  test    r15b, r15b
0x14000b64c  jz      loc_14000BB43
0x14000b652  movzx   edx, al; NewIrql
0x14000b655  lea     rcx, SpinLock; SpinLock
0x14000b65c  call    cs:__imp_KeReleaseSpinLock
0x14000b663  nop     dword ptr [rax+rax+00h]
0x14000b668  lea     rax, Dpc
0x14000b66f  mov     r9d, 1388h; TolerableDelay
0x14000b675  xor     r8d, r8d; Period
0x14000b678  mov     [rsp+98h+Dpc], rax; Dpc
0x14000b67d  mov     rdx, 0FFFFFFFFE52D8B80h; DueTime
0x14000b684  lea     rcx, Timer; Timer
0x14000b68b  call    cs:__imp_KeSetCoalescableTimer
0x14000b692  nop     dword ptr [rax+rax+00h]
0x14000b697  add     rsp, 88h
0x14000b69e  pop     r15
0x14000b6a0  pop     rbx
0x14000b6a1  retn
0x14000b6a3  cmp     [rcx+38h], rsi
0x14000b6a7  lea     rdi, [rcx-40h]
0x14000b6ab  jg      loc_14000BA9C
0x14000b6b1  mov     eax, 1
0x14000b6b6  lock xadd [rdi], rax
0x14000b6bb  add     rax, 2
0x14000b6bf  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000b6c5  jnz     short loc_14000B6C9
0x14000b6c7  int     2Ch; Windows NT - assertion failure
0x14000b6c9  cmp     byte ptr [rdi+68h], 0
0x14000b6cd  jz      loc_14000BA93
0x14000b6d3  lea     rcx, Smb2ClientPendingListLock; SpinLock
0x14000b6da  call    cs:__imp_KeReleaseSpinLock
0x14000b6e1  nop     dword ptr [rax+rax+00h]
0x14000b6e6  mov     rcx, rdi
0x14000b6e9  call    Smb2CloseClient
0x14000b6ee  mov     rcx, rdi
0x14000b6f1  call    Smb2DereferenceClient
0x14000b6f6  lea     rcx, Smb2ClientPendingListLock; SpinLock
0x14000b6fd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b704  nop     dword ptr [rax+rax+00h]
0x14000b709  jmp     loc_14000B490
0x14000b70e  mov     rdx, rcx
0x14000b711  jmp     loc_14000B567
0x14000b716  movzx   edx, r9b; NewIrql
0x14000b71a  lea     rcx, WPP_MAIN_CB.Dpc.SystemArgument2; SpinLock
0x14000b721  call    cs:__imp_KeReleaseSpinLock
0x14000b728  nop     dword ptr [rax+rax+00h]
0x14000b72d  mov     rbp, r12
0x14000b730  jmp     loc_14000B59F
0x14000b735  mov     r8, [r8]
0x14000b738  jmp     loc_14000B54A
0x14000b73d  cmp     byte ptr [rax], 0
0x14000b740  jnz     loc_14000B928
0x14000b746  mov     rbx, [rax+0A0h]
0x14000b74d  lea     r14, WPP_GLOBAL_Control
0x14000b754  mov     [rsp+98h+arg_18], r12
0x14000b75c  jmp     loc_14000B895
0x14000b761  mov     [rsp+98h+var_48], rax
0x14000b766  nop     word ptr [rax+rax+00000000h]
0x14000b770  mov     rax, [r13+10h]
0x14000b774  lea     r8, [rsp+98h+arg_18]
0x14000b77c  mov     byte ptr [rsp+98h+var_60], 1
0x14000b781  lea     rdx, [rsp+98h+var_48]
0x14000b786  mov     [rsp+98h+var_68], r12
0x14000b78b  xor     r9d, r9d
0x14000b78e  mov     [rsp+98h+var_70], r12
0x14000b793  mov     rcx, r13
0x14000b796  mov     [rsp+98h+Dpc], rax
0x14000b79b  call    RfspTable64Enumerate
0x14000b7a0  mov     r12, rax
0x14000b7a3  test    rax, rax
0x14000b7a6  jz      loc_14000B8FA
0x14000b7ac  cmp     qword ptr [r13+0A0h], 0
0x14000b7b4  jz      loc_14000B966
0x14000b7ba  test    byte ptr [r13+98h], 40h
0x14000b7c2  mov     rcx, r13; SpinLock
0x14000b7c5  jnz     loc_14000B935
0x14000b7cb  xor     edx, edx
0x14000b7cd  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000b7d4  nop     dword ptr [rax+rax+00h]
0x14000b7d9  mov     r12, [r12]
0x14000b7dd  test    r12b, 3
0x14000b7e1  jnz     loc_14000B8B9
0x14000b7e7  mov     rax, [r13+0A0h]
0x14000b7ee  test    rax, rax
0x14000b7f1  jz      short loc_14000B7FB
0x14000b7f3  mov     rcx, r12
0x14000b7f6  call    _guard_dispatch_icall
0x14000b7fb  test    byte ptr [r13+98h], 40h
0x14000b803  mov     rcx, r13; SpinLock
0x14000b806  jnz     loc_14000B94D
0x14000b80c  xor     edx, edx
0x14000b80e  call    cs:__imp_ExReleasePushLockSharedEx
0x14000b815  nop     dword ptr [rax+rax+00h]
0x14000b81a  test    r12, r12
0x14000b81d  jz      loc_14000B8FA
0x14000b823  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b82a  cmp     rcx, r14
0x14000b82d  jz      short loc_14000B83A
0x14000b82f  mov     eax, [rcx+2Ch]
0x14000b832  test    al, 1
0x14000b834  jnz     loc_14000B96E
0x14000b83a  cmp     rsi, [r12+98h]
0x14000b842  jg      loc_14000B9AE
0x14000b848  call    cs:__imp_SrvAdminTakeActionToAllowPowerDown
0x14000b84f  nop     dword ptr [rax+rax+00h]
0x14000b854  test    al, al
0x14000b856  jnz     loc_14000B9FB
0x14000b85c  cmp     dword ptr [r12+70h], 0
0x14000b862  jz      loc_14000BA3E
0x14000b868  mov     r15b, 1
0x14000b86b  mov     rax, [r12+18h]
0x14000b870  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000b877  lock xadd [rax], rcx
0x14000b87c  dec     rcx
0x14000b87f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000b883  jnb     loc_14000BA8C
0x14000b889  test    rcx, rcx
0x14000b88c  jz      loc_14000B91B
0x14000b892  xor     r12d, r12d
0x14000b895  mov     rax, [rsp+98h+arg_18]
0x14000b89d  mov     r13, [rbx]
0x14000b8a0  mov     [rsp+98h+arg_8], 0
0x14000b8a8  and     rax, [r13+78h]
0x14000b8ac  mov     [rsp+98h+arg_18], rax
0x14000b8b4  jmp     loc_14000B761
0x14000b8b9  test    byte ptr [r13+98h], 40h
0x14000b8c1  mov     rcx, r13; SpinLock
0x14000b8c4  jz      short loc_14000B8EA
0x14000b8c6  movzx   edx, [rsp+98h+arg_8]; OldIrql
0x14000b8ce  call    cs:__imp_ExReleaseSpinLockShared
0x14000b8d5  nop     dword ptr [rax+rax+00h]
0x14000b8da  mov     rax, [rsp+98h+arg_18]
0x14000b8e2  xor     r12d, r12d
0x14000b8e5  jmp     loc_14000B761
0x14000b8ea  xor     edx, edx
0x14000b8ec  call    cs:__imp_ExReleasePushLockSharedEx
0x14000b8f3  nop     dword ptr [rax+rax+00h]
0x14000b8f8  jmp     short loc_14000B8DA
0x14000b8fa  mov     r14, [rsp+98h+Context]
0x14000b8ff  mov     rcx, [r14+0A0h]
0x14000b906  call    Smb2ScavengerProcessSyncRedirectTreeConnects
0x14000b90b  mov     rcx, r14; Context
0x14000b90e  call    Srv2DereferenceInstance
0x14000b913  xor     r12d, r12d
0x14000b916  jmp     loc_14000B468
0x14000b91b  mov     rcx, r12; P
0x14000b91e  call    Smb2FreeSession
0x14000b923  jmp     loc_14000B892
0x14000b928  mov     rcx, rax; Context
0x14000b92b  call    Srv2DereferenceInstance
0x14000b930  jmp     loc_14000B468
0x14000b935  call    cs:__imp_ExAcquireSpinLockShared
0x14000b93c  nop     dword ptr [rax+rax+00h]
0x14000b941  mov     [rsp+98h+arg_8], al
0x14000b948  jmp     loc_14000B7D9
0x14000b94d  movzx   edx, [rsp+98h+arg_8]; OldIrql
0x14000b955  call    cs:__imp_ExReleaseSpinLockShared
0x14000b95c  nop     dword ptr [rax+rax+00h]
0x14000b961  jmp     loc_14000B81A
0x14000b966  mov     r12, [rax]
0x14000b969  jmp     loc_14000B81A
0x14000b96e  cmp     byte ptr [rcx+29h], 4
0x14000b972  jb      loc_14000B83A
0x14000b978  mov     eax, [r12+70h]
0x14000b97d  mov     r9, r12
0x14000b980  mov     rcx, [rcx+18h]
0x14000b984  mov     dword ptr [rsp+98h+var_60], eax
0x14000b988  mov     rax, [r12+10h]
0x14000b98d  mov     [rsp+98h+var_68], rax
0x14000b992  mov     rax, [r12+98h]
0x14000b99a  mov     [rsp+98h+var_70], rax
0x14000b99f  mov     [rsp+98h+Dpc], rdi
0x14000b9a4  call    WPP_SF_qiiid
0x14000b9a9  jmp     loc_14000B83A
0x14000b9ae  mov     rax, cs:Srv2Statistics
0x14000b9b5  inc     dword ptr [rax+28h]
0x14000b9b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b9bf  cmp     rcx, r14
0x14000b9c2  jz      loc_14003AC96
0x14000b9c8  mov     eax, [rcx+2Ch]
0x14000b9cb  test    al, 1
0x14000b9cd  jz      loc_14003AC96
0x14000b9d3  cmp     byte ptr [rcx+29h], 2
0x14000b9d7  jb      loc_14003AC96
  ... truncated ...
```
