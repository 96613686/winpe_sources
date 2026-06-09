# IppGetAllBestRouteParameters

- ea: `0x140076f20`
- end: `0x140077ce1`
- name: `IppGetAllBestRouteParameters`
- size: `3521`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x140078780`
- `0x140078b90`

## callees

- `0x140027240`
- `0x14002f9e0`
- `0x140050b50`
- `0x140050c00`
- `0x140071db0`
- `0x140072910`
- `0x140072cd0`
- `0x140072e40`
- `0x140073660`
- `0x140075fd0`
- `0x140076f20`
- `0x140077ee0`
- `0x140078820`
- `0x140079060`
- `0x1400795b0`
- `0x14007ab60`
- `0x14010aafc`
- `0x14010dfbc`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140076f9d`
- `ntoskrnl!KfRaiseIrql` at `0x1400770ce`
- `ntoskrnl!KfRaiseIrql` at `0x14007751a`
- `ntoskrnl!KfRaiseIrql` at `0x140076f9d`
- `ntoskrnl!KfRaiseIrql` at `0x1400770ce`
- `ntoskrnl!KfRaiseIrql` at `0x14007751a`
- `ntoskrnl!KeLowerIrql` at `0x14007704d`
- `ntoskrnl!KeLowerIrql` at `0x14007714c`
- `ntoskrnl!KeLowerIrql` at `0x1400776e0`
- `ntoskrnl!KeLowerIrql` at `0x14007796b`
- `ntoskrnl!KeLowerIrql` at `0x140077b5b`
- `ntoskrnl!KeLowerIrql` at `0x140077c36`
- `ntoskrnl!KeLowerIrql` at `0x14007704d`
- `ntoskrnl!KeLowerIrql` at `0x14007714c`
- `ntoskrnl!KeLowerIrql` at `0x1400776e0`
- `ntoskrnl!KeLowerIrql` at `0x14007796b`
- `ntoskrnl!KeLowerIrql` at `0x140077b5b`
- `ntoskrnl!KeLowerIrql` at `0x140077c36`
- `ntoskrnl!IoQueueWorkItem` at `0x140077b13`
- `ntoskrnl!IoQueueWorkItem` at `0x140077b8c`
- `ntoskrnl!IoQueueWorkItem` at `0x140077b13`
- `ntoskrnl!IoQueueWorkItem` at `0x140077b8c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140076fdc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140076fdc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140076ff0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140076ff0`
- `ntoskrnl!KeTestSpinLock` at `0x140076fc1`
- `ntoskrnl!KeTestSpinLock` at `0x140076fc1`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x14007719a`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x14007719a`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14007709f`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14007709f`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140076f86`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400770bd`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140076f86`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400770bd`

## pseudocode

```c
__int64 __fastcall IppGetAllBestRouteParameters(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        _DWORD **a5,
        IN6_ADDR *a6,
        unsigned int a7,
        void *a8)
{
  int ThreadObjectCompartmentId; // esi
  IN6_ADDR *v10; // r15
  __int64 v11; // rbx
  KIRQL v12; // r14
  _QWORD **v13; // rdx
  _QWORD *i; // rax
  unsigned int *v15; // rdi
  __int64 v16; // rbx
  IN6_ADDR *RouteFromPath; // r13
  int Next_high; // r14d
  __int64 v19; // r12
  _QWORD **v20; // r8
  _QWORD *j; // rcx
  _QWORD *v22; // rbx
  signed __int64 v23; // rax
  bool v24; // cc
  signed __int64 v25; // rax
  unsigned int v26; // ebx
  __int64 v27; // r12
  unsigned int (__fastcall *v28)(IN6_ADDR *); // rax
  IN6_ADDR *v29; // r14
  int v30; // eax
  int *v31; // r12
  __int64 v32; // r14
  _DWORD **v33; // r14
  __int64 v34; // rax
  __int64 v35; // r8
  _DWORD **v36; // rcx
  int v37; // eax
  int NextHopAtDpcHelper; // r14d
  __int64 v39; // r8
  unsigned int *v40; // rbx
  _QWORD *v41; // r12
  int v42; // ebx
  IN6_ADDR **v43; // rcx
  __int64 v44; // rdx
  int v45; // eax
  __int64 v46; // rdx
  _DWORD *v47; // rdx
  __int64 AddressInScope; // rax
  __int64 v49; // rdx
  int v50; // edx
  signed __int64 v51; // rsi
  signed __int64 v52; // rsi
  KIRQL v54; // al
  char v55; // cl
  _DWORD *v56; // r13
  _DWORD *v57; // r14
  __int64 v58; // rcx
  bool v59; // zf
  _DWORD **v60; // r13
  __int64 BestSourceAddressOnHost; // rax
  _QWORD *v62; // r13
  _QWORD *v63; // r8
  __int64 v64; // r8
  PVOID v65; // rax
  __int64 v66; // rcx
  int v67; // edx
  int v68; // eax
  int v69; // ebx
  IN6_ADDR *v70; // rcx
  int v71; // eax
  __int64 v72; // rdx
  char *v73; // rdx
  char v74; // al
  char v75; // al
  char v76; // al
  __int64 v77; // rax
  int v78; // ecx
  __int64 v79; // r9
  int v80; // [rsp+28h] [rbp-B1h]
  KIRQL v81; // [rsp+50h] [rbp-89h]
  char v82; // [rsp+50h] [rbp-89h]
  KIRQL v83; // [rsp+51h] [rbp-88h]
  unsigned int v84; // [rsp+58h] [rbp-81h] BYREF
  _QWORD *v85; // [rsp+60h] [rbp-79h]
  __int64 v86; // [rsp+68h] [rbp-71h]
  IN6_ADDR *a; // [rsp+70h] [rbp-69h] BYREF
  PVOID v88; // [rsp+78h] [rbp-61h]
  IN6_ADDR *v89; // [rsp+80h] [rbp-59h]
  PVOID P; // [rsp+88h] [rbp-51h]
  _DWORD *v91; // [rsp+90h] [rbp-49h]
  _DWORD **v92; // [rsp+98h] [rbp-41h]
  PVOID Context; // [rsp+A0h] [rbp-39h]
  void *v94; // [rsp+A8h] [rbp-31h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B0h] [rbp-29h] BYREF

  ThreadObjectCompartmentId = a2;
  v92 = a5;
  v10 = 0;
  v89 = a6;
  v91 = (_DWORD *)a3;
  v88 = (PVOID)a1;
  v84 = a4;
  v94 = a8;
  a = 0;
  if ( !a2 )
    ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
  v11 = a1 + 19880;
  v12 = KfRaiseIrql(2u);
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 19888));
  if ( !KeTestSpinLock((PKSPIN_LOCK)(a1 + 19880)) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 19888));
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 19880), &LockHandle);
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 19888));
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  v13 = (_QWORD **)(*(_QWORD *)(a1 + 19872)
                  + 16LL * (ThreadObjectCompartmentId & (unsigned int)(*(_DWORD *)(a1 + 19868) - 1)));
  for ( i = *v13; ; i = (_QWORD *)*i )
  {
    if ( i == v13 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v11 + 8));
      KeLowerIrql(v12);
      return 3221226021LL;
    }
    v15 = (unsigned int *)(i - 6);
    if ( *((_DWORD *)i - 12) == ThreadObjectCompartmentId )
      break;
  }
  if ( _InterlockedIncrement64((volatile signed __int64 *)v15 + 4) <= 1 )
    __fastfail(0xEu);
  _InterlockedDecrement((volatile signed __int32 *)(v11 + 8));
  KeLowerIrql(v12);
  if ( !v15 )
    return 3221226021LL;
  v16 = *((_QWORD *)v15 + 5);
  v86 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  RouteFromPath = 0;
  v85 = 0;
  Context = 0;
  P = 0;
  NdisGetThreadObjectCompartmentScope(KeGetCurrentThread(), &LockHandle, (char *)&LockHandle.LockQueue.Next + 4);
  Next_high = HIDWORD(LockHandle.LockQueue.Next);
  if ( !HIDWORD(LockHandle.LockQueue.Next) )
    Next_high = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
  v19 = v16 + 19880;
  v81 = KfRaiseIrql(2u);
  RtlAcquireReadLockAtDpcLevel((PKSPIN_LOCK)(v16 + 19880));
  v20 = (_QWORD **)(*(_QWORD *)(v16 + 19872) + 16LL * (Next_high & (unsigned int)(*(_DWORD *)(v16 + 19868) - 1)));
  for ( j = *v20; ; j = (_QWORD *)*j )
  {
    if ( j == v20 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v19 + 8));
      KeLowerIrql(v81);
      goto LABEL_20;
    }
    v22 = j - 6;
    if ( *((_DWORD *)j - 12) == Next_high )
      break;
  }
  if ( _InterlockedIncrement64(v22 + 4) <= 1 )
    __fastfail(0xEu);
  _InterlockedDecrement((volatile signed __int32 *)(v19 + 8));
  KeLowerIrql(v81);
  if ( v22 )
  {
    *(_OWORD *)&LockHandle.LockQueue.Lock = *(_OWORD *)((char *)v22 + 4);
    v23 = _InterlockedExchangeAdd64(v22 + 4, 0xFFFFFFFFFFFFFFFFuLL);
    v24 = v23 <= 1;
    v25 = v23 - 1;
    if ( v24 )
    {
      if ( v25 )
        __fastfail(0xEu);
      IoQueueWorkItem((PIO_WORKITEM)v22[16], IppCleanupCompartmentWorkerRoutine, DelayedWorkQueue, v22);
    }
  }
LABEL_20:
  if ( !(unsigned __int8)NetioIsCompartmentAccessibleByThread(*v15, v15 + 1, 1) )
  {
    NextHopAtDpcHelper = -1073741275;
    v41 = 0;
    AddressInScope = 0;
    goto LABEL_59;
  }
  v26 = a7;
  v27 = *((_QWORD *)v15 + 5);
  v28 = *(unsigned int (__fastcall **)(IN6_ADDR *))(v27 + 168);
  if ( !(a7 >> 28) )
  {
    v29 = v89;
    v26 = a7 & 0xFFFFFFF | (v28(v89) << 28);
    goto LABEL_23;
  }
  if ( a7 >> 28 != v28(v89) )
    goto LABEL_127;
  v29 = v89;
LABEL_23:
  if ( (v26 & 0xF0000000) == 0xE0000000 )
  {
    if ( (v26 & 0xFFFFFFF) == 0 )
    {
      v30 = *v15 ^ v26;
      goto LABEL_26;
    }
LABEL_127:
    NextHopAtDpcHelper = -1073741811;
    v41 = 0;
    AddressInScope = 0;
    goto LABEL_59;
  }
  if ( *(_WORD *)(v27 + 28) == 23 )
    v75 = IN6_IS_ADDR_LOOPBACK(v29);
  else
    v75 = v29->u.Byte[0] == 127;
  if ( v75 )
  {
    if ( (v26 & 0xFFFFFFF) != 0 )
      goto LABEL_127;
    v30 = v15[7] ^ v26;
LABEL_26:
    v26 ^= v30 & 0xFFFFFFF;
  }
  v31 = (int *)v88;
  v32 = (__int64)v91;
  if ( (*((unsigned int (__fastcall **)(_DWORD *))v88 + 22))(v91) )
  {
    if ( !(unsigned __int8)IppCanonicalizeScopeId(v15, v91, &v84) )
      goto LABEL_127;
    AddressInScope = IppFindAddressInScope(v15, v84, v32);
    v86 = AddressInScope;
    if ( !AddressInScope )
    {
      NextHopAtDpcHelper = -1073741275;
      goto LABEL_58;
    }
    if ( *(_DWORD *)(AddressInScope + 24) != 1 )
    {
      NextHopAtDpcHelper = -1073741811;
      goto LABEL_58;
    }
    v33 = *(_DWORD ***)(AddressInScope + 8);
    Context = v33;
    if ( _InterlockedIncrement64((volatile signed __int64 *)v33 + 19) <= 1 )
      __fastfail(0xEu);
    if ( v33 )
      goto LABEL_156;
  }
  else
  {
    if ( !v92 )
    {
      v33 = 0;
      goto LABEL_30;
    }
    Context = (PVOID)IppFindInterfaceByLuid(v88, v92);
    v33 = (_DWORD **)Context;
    if ( !Context )
    {
      NextHopAtDpcHelper = -1073741275;
      v41 = 0;
      AddressInScope = 0;
      goto LABEL_59;
    }
LABEL_156:
    v77 = v26 >> 28;
    if ( (unsigned int)v77 <= 1 )
    {
      v78 = *((_DWORD *)v33 + 2);
    }
    else if ( (unsigned int)v77 >= 0xE )
    {
      v78 = **v33;
    }
    else
    {
      _mm_lfence();
      v78 = *((_DWORD *)v33 + v77 + 192) & 0xFFFFFFF;
    }
    if ( (v26 & 0xFFFFFFF) != 0 )
    {
      if ( (v26 & 0xFFFFFFF) != v78 )
      {
        NextHopAtDpcHelper = -1073741811;
        goto LABEL_57;
      }
    }
    else
    {
      v26 ^= (v26 ^ v78) & 0xFFFFFFF;
    }
  }
LABEL_30:
  if ( (*(unsigned int (__fastcall **)(IN6_ADDR *))(*((_QWORD *)v15 + 5) + 176LL))(v89) )
  {
    if ( !(*(unsigned int (__fastcall **)(IN6_ADDR *))(*((_QWORD *)v15 + 5) + 176LL))(v89) )
      goto LABEL_55;
    v34 = v86;
    v35 = v26;
    v36 = v33;
    if ( !v86 )
      goto LABEL_33;
    if ( *(_DWORD *)(v86 + 24) != 1 )
      goto LABEL_55;
    if ( v33 )
    {
      if ( v33 == *(_DWORD ***)(v86 + 8) )
        goto LABEL_50;
LABEL_55:
      NextHopAtDpcHelper = -1073741305;
      goto LABEL_57;
    }
    v36 = *(_DWORD ***)(v86 + 8);
LABEL_33:
    if ( v36 )
    {
LABEL_50:
      v49 = v26 >> 28;
      if ( (unsigned int)v49 <= 1 )
      {
        v50 = *((_DWORD *)v36 + 2);
      }
      else if ( (unsigned int)v49 >= 0xE )
      {
        v50 = **v36;
        v34 = v86;
      }
      else
      {
        v50 = *((_DWORD *)v36 + v49 + 192) & 0xFFFFFFF;
      }
      if ( (v26 & 0xFFFFFFF) != 0 )
      {
        if ( (v26 & 0xFFFFFFF) != v50 )
          goto LABEL_55;
      }
      else
      {
        v35 = v26 ^ (v26 ^ v50) & 0xFFFFFFF;
      }
    }
    if ( v34 )
      v33 = *(_DWORD ***)(v34 + 8);
    v37 = IppFindOrCreatePath(v15, v89, v35, v33, v34, &a);
    v10 = a;
    if ( v37 == -1073741275 )
    {
      NextHopAtDpcHelper = -1073741252;
      goto LABEL_57;
    }
    NextHopAtDpcHelper = v37;
    if ( v37 < 0 )
      goto LABEL_57;
    RouteFromPath = (IN6_ADDR *)IppGetRouteFromPath(a);
    if ( RouteFromPath )
    {
      v85 = *(_QWORD **)v10->u.Byte;
      v39 = v85[4];
      if ( (_InterlockedExchangeAdd64(
              (volatile signed __int64 *)(*(_QWORD *)v39
                                        + (unsigned int)(*(_DWORD *)(v39 + 16)
                                                       * (HIDWORD(KeGetPcr()[1].LockArray) % *(_DWORD *)(v39 + 20)))),
              2u)
          & 1) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(v39 + 24), 2u);
LABEL_41:
      v40 = (unsigned int *)v94;
      if ( v94 )
      {
        if ( v31 == &Ipv4Global )
        {
          memset(v94, 0, 0x68u);
          if ( RouteFromPath )
            NextHopAtDpcHelper = IppFillUnicastRouteData(
                                   (__int64)v31,
                                   (__int64)RouteFromPath,
                                   0,
                                   (__int64)v40,
                                   (__int64)(v40 + 12),
                                   v40 + 19,
                                   v40 + 21);
          v41 = v85;
          v42 = 0;
          v43 = (IN6_ADDR **)v85[2];
          v88 = (PVOID)v85[1];
          v44 = *(_QWORD *)v88;
          a = *v43;
          v92 = *(_DWORD ***)(v44 + 40);
          v45 = ((__int64 (*)(void))v92[21])();
          v46 = v45;
          if ( v45 != 14 )
          {
            v74 = *((_WORD *)v92 + 14) == 23 ? IN6_IS_ADDR_LOOPBACK(a) : a->u.Byte[0] == 127;
            if ( !v74 )
            {
              if ( (int)v46 <= 1 )
              {
                v42 = *((_DWORD *)v88 + 2) & 0xFFFFFFF;
              }
              else if ( (int)v46 >= 14 )
              {
                v42 = **(_DWORD **)v88 & 0xFFFFFFF;
              }
              else
              {
                v42 = *((_DWORD *)v88 + v46 + 192) & 0xFFFFFFF;
              }
            }
          }
          v47 = v94;
          *((_DWORD *)v94 + 23) = v42;
          v47[24] = **(_DWORD **)v41[2];
          AddressInScope = v86;
        }
        else
        {
          memset(v94, 0, 0x98u);
          if ( RouteFromPath )
            NextHopAtDpcHelper = IppFillUnicastRouteData(
                                   (__int64)v31,
                                   (__int64)RouteFromPath,
                                   0,
                                   (__int64)v40,
                                   (__int64)(v40 + 18),
                                   v40 + 25,
                                   (_QWORD *)v40 + 15);
          v41 = v85;
          v69 = 0;
          v70 = *(IN6_ADDR **)v85[2];
          v88 = (PVOID)v85[1];
          a = v70;
          v92 = *(_DWORD ***)(*(_QWORD *)v88 + 40LL);
          v71 = ((__int64 (*)(void))v92[21])();
          v72 = v71;
          if ( v71 != 14 )
          {
            v76 = *((_WORD *)v92 + 14) == 23 ? IN6_IS_ADDR_LOOPBACK(a) : a->u.Byte[0] == 127;
            if ( !v76 )
            {
              if ( (int)v72 <= 1 )
              {
                v69 = *((_DWORD *)v88 + 2) & 0xFFFFFFF;
              }
              else if ( (int)v72 >= 14 )
              {
                v69 = **(_DWORD **)v88 & 0xFFFFFFF;
              }
              else
              {
                v69 = *((_DWORD *)v88 + v72 + 192) & 0xFFFFFFF;
              }
            }
          }
          v73 = (char *)v94;
          *((_DWORD *)v94 + 32) = v69;
          AddressInScope = v86;
          *(_OWORD *)(v73 + 132) = *(_OWORD *)*(_QWORD *)v41[2];
        }
      }
      else
      {
        v41 = v85;
        AddressInScope = v86;
      }
      goto LABEL_59;
    }
  }
  v54 = KfRaiseIrql(2u);
  v88 = 0;
  v55 = 0;
  v83 = v54;
  while ( 2 )
  {
    a = 0;
LABEL_76:
    v84 = 0;
    v56 = Context;
    LOBYTE(v80) = v55 ^ 1;
    NextHopAtDpcHelper = IppFindNextHopAtDpcHelper(v15, Context, v89, v26, v86, v80);
    if ( NextHopAtDpcHelper >= 0 )
    {
      v57 = v88;
      v58 = (__int64)v56;
      v82 = 0;
      P = (PVOID)v86;
      v59 = *(_DWORD *)v88 == 1634496585;
      v91 = v56;
      if ( v59 && *((_DWORD *)v88 + 6) == 4 )
      {
        v58 = *((_QWORD *)v88 + 1);
        v91 = (_DWORD *)v58;
      }
      v60 = (_DWORD **)*((_QWORD *)v88 + 1);
      v92 = v60;
      if ( v86 )
      {
        v64 = *(_QWORD *)(v86 + 32);
        if ( (_InterlockedExchangeAdd64(
                (volatile signed __int64 *)(*(_QWORD *)v64
                                          + (unsigned int)(*(_DWORD *)(v64 + 16)
                                                         * (HIDWORD(KeGetPcr()[1].LockArray) % *(_DWORD *)(v64 + 20)))),
                2u)
            & 1) != 0 )
          _InterlockedAdd64((volatile signed __int64 *)(v64 + 24), 2u);
      }
      else
      {
        if ( !v58 )
        {
          BestSourceAddressOnHost = IppFindBestSourceAddressOnHost((__int64 *)v60, v89, (__int64)v88, 0);
          v55 = 0;
          v62 = (_QWORD *)BestSourceAddressOnHost;
          v63 = P;
          goto LABEL_93;
        }
        P = (PVOID)IppFindBestSourceAddressOnInterface(v58, v89);
        v63 = P;
        if ( !P )
        {
          v62 = 0;
          v55 = 0;
          goto LABEL_93;
        }
      }
      v65 = (PVOID)IppFindBestSourceAddressOnHost((__int64 *)v60, v89, (__int64)v57, 1);
      v63 = P;
      if ( v65 == P )
      {
        if ( v91 != (_DWORD *)v60 )
          LOBYTE(v84) = v84 | 2;
      }
      else
      {
        LOBYTE(v84) = v84 | 1;
      }
      if ( v65 )
      {
        IppDereferenceLocalAddress(v65);
        v63 = P;
      }
      v66 = *(_DWORD *)(v63[2] + 8LL) >> 28;
      if ( (unsigned int)v66 <= 1 )
      {
        v67 = v91[2];
        v68 = *((_DWORD *)v60 + 2);
      }
      else if ( (unsigned int)v66 >= 0xE )
      {
        v67 = **(_DWORD **)v91;
        v68 = **v60;
      }
      else
      {
        v67 = v91[v66 + 192] & 0xFFFFFFF;
        v68 = *((_DWORD *)v60 + v66 + 192) & 0xFFFFFFF;
      }
      if ( v68 == v67 )
      {
        v55 = 0;
        v62 = v63;
      }
      else
      {
        IppDereferenceLocalAddress(v63);
        v63 = P;
        v55 = 1;
        v82 = 1;
        v62 = 0;
      }
LABEL_93:
      v85 = v62;
      if ( (BYTE5(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x20) != 0 )
      {
        if ( v62 )
          v79 = *(_QWORD *)v62[2];
        else
          LODWORD(v79) = 0;
        if ( v63 )
          v63 = *(_QWORD **)v63[2];
        IppLogSrcAddrLookupEvent((unsigned int)*v92, (_DWORD)v89, (_DWORD)v63, v79, (__int64)v91, (__int64)v92, v84);
        v55 = v82;
      }
      if ( !v55 )
      {
        if ( v62 )
        {
          RouteFromPath = a;
          P = v57;
          KeLowerIrql(v83);
          NextHopAtDpcHelper = 0;
          goto LABEL_41;
        }
        NextHopAtDpcHelper = -1073741251;
        break;
      }
      if ( *v57 == 1634496585 )
      {
        IppDereferenceLocalAddress(v57);
      }
      else
      {
        if ( *v57 != 1701736521 )
          goto LABEL_112;
        IppDereferenceNeighbor(v57);
      }
      v55 = v82;
LABEL_112:
      if ( a )
      {
        IppDereferenceRoute(a);
        v55 = v82;
        continue;
      }
      goto LABEL_76;
    }
    break;
  }
  RouteFromPath = 0;
  v85 = 0;
  P = 0;
  if ( a )
    IppDereferenceRoute(a);
  if ( v88 )
  {
    if ( *(_DWORD *)v88 == 1634496585 )
    {
      IppDereferenceLocalAddress(v88);
    }
    else if ( *(_DWORD *)v88 == 1701736521 )
    {
      IppDereferenceNeighbor(v88);
    }
  }
  KeLowerIrql(v83);
LABEL_57:
  AddressInScope = v86;
LABEL_58:
  v41 = 0;
LABEL_59:
  v51 = _InterlockedExchangeAdd64((volatile signed __int64 *)v15 + 4, 0xFFFFFFFFFFFFFFFFuLL);
  v24 = v51 <= 1;
  v52 = v51 - 1;
  if ( v24 )
  {
    if ( v52 )
      __fastfail(0xEu);
    IoQueueWorkItem(*((PIO_WORKITEM *)v15 + 16), IppCleanupCompartmentWorkerRoutine, DelayedWorkQueue, v15);
    AddressInScope = v86;
  }
  if ( AddressInScope )
    IppDereferenceLocalAddress(AddressInScope);
  if ( Context )
    IppDereferenceInterface(Context);
  if ( v10 )
  {
    *(_DWORD *)&v10[6].u.Word[4] = MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x1F4;
    IppDereferencePathPrimitive(v10);
  }
  if ( RouteFromPath )
    IppDereferenceRoute(RouteFromPath);
  if ( v41 )
    IppDereferenceLocalAddress(v41);
  if ( P )
  {
    if ( *(_DWORD *)P == 1634496585 )
    {
      IppDereferenceLocalAddress(P);
    }
    else if ( *(_DWORD *)P == 1701736521 )
    {
      IppDereferenceNeighbor(P);
    }
  }
  return (unsigned int)NextHopAtDpcHelper;
}

```

## disassembly

```asm
0x140076f20  push    rbp
0x140076f22  push    rbx
0x140076f23  push    rsi
0x140076f24  push    rdi
0x140076f25  push    r12
0x140076f27  push    r14
0x140076f29  push    r15
0x140076f2b  lea     rbp, [rsp-7]
0x140076f30  sub     rsp, 0E0h
0x140076f37  mov     rax, cs:__security_cookie
0x140076f3e  xor     rax, rsp
0x140076f41  mov     [rbp+37h+var_48], rax
0x140076f45  mov     rax, [rbp+37h+arg_20]
0x140076f49  xor     r12d, r12d
0x140076f4c  mov     esi, edx
0x140076f4e  mov     [rbp+37h+var_78], rax
0x140076f52  mov     rax, [rbp+37h+arg_28]
0x140076f56  mov     rdi, rcx
0x140076f59  mov     rdx, [rbp+37h+arg_38]
0x140076f5d  mov     r15d, r12d
0x140076f60  mov     [rbp+37h+var_90], rax
0x140076f64  mov     [rbp+37h+var_80], r8
0x140076f68  mov     [rbp+37h+var_98], rcx
0x140076f6c  mov     [rsp+110h+var_B8], r9d
0x140076f71  mov     [rbp+37h+var_68], rdx
0x140076f75  mov     [rbp+37h+a], r12
0x140076f79  test    esi, esi
0x140076f7b  jnz     short loc_140076F94
0x140076f7d  mov     rcx, gs:188h
0x140076f86  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140076f8d  nop     dword ptr [rax+rax+00h]
0x140076f92  mov     esi, eax
0x140076f94  mov     cl, 2; NewIrql
0x140076f96  lea     rbx, [rdi+4DA8h]
0x140076f9d  call    cs:__imp_KfRaiseIrql
0x140076fa4  nop     dword ptr [rax+rax+00h]
0x140076fa9  movzx   r14d, al
0x140076fad  xorps   xmm0, xmm0
0x140076fb0  xor     eax, eax
0x140076fb2  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rax
0x140076fb6  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x140076fba  lock inc dword ptr [rbx+8]
0x140076fbe  mov     rcx, rbx; SpinLock
0x140076fc1  call    cs:__imp_KeTestSpinLock
0x140076fc8  nop     dword ptr [rax+rax+00h]
0x140076fcd  test    al, al
0x140076fcf  jnz     short loc_140076FFC
0x140076fd1  lock dec dword ptr [rbx+8]
0x140076fd5  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x140076fd9  mov     rcx, rbx; SpinLock
0x140076fdc  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140076fe3  nop     dword ptr [rax+rax+00h]
0x140076fe8  lock inc dword ptr [rbx+8]
0x140076fec  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x140076ff0  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140076ff7  nop     dword ptr [rax+rax+00h]
0x140076ffc  mov     edx, [rdi+4D9Ch]
0x140077002  dec     edx
0x140077004  mov     eax, esi
0x140077006  and     rdx, rax
0x140077009  shl     rdx, 4
0x14007700d  add     rdx, [rdi+4DA0h]
0x140077014  mov     rax, [rdx]
0x140077017  cmp     rax, rdx
0x14007701a  jz      loc_140077963
0x140077020  cmp     [rax-30h], esi
0x140077023  lea     rdi, [rax-30h]
0x140077027  jnz     loc_1400779F8
0x14007702d  mov     eax, 1
0x140077032  lock xadd [rdi+20h], rax
0x140077038  inc     rax
0x14007703b  cmp     rax, 1
0x14007703f  jle     loc_140077C6A
0x140077045  lock dec dword ptr [rbx+8]
0x140077049  movzx   ecx, r14b; NewIrql
0x14007704d  call    cs:__imp_KeLowerIrql
0x140077054  nop     dword ptr [rax+rax+00h]
0x140077059  test    rdi, rdi
0x14007705c  jz      loc_140077977
0x140077062  mov     rbx, [rdi+28h]
0x140077066  lea     r8, [rbp+37h+LockHandle.LockQueue.Next+4]
0x14007706a  xorps   xmm0, xmm0
0x14007706d  mov     [rsp+110h+var_38], r13
0x140077075  xor     eax, eax
0x140077077  mov     [rbp+37h+var_A8], r12
0x14007707b  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x14007707f  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rax
0x140077083  lea     rdx, [rbp+37h+LockHandle]
0x140077087  mov     rcx, gs:188h
0x140077090  mov     r13, r12
0x140077093  mov     [rbp+37h+var_B0], r12
0x140077097  mov     [rbp+37h+Context], r12
0x14007709b  mov     [rbp+37h+P], r12
0x14007709f  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x1400770a6  nop     dword ptr [rax+rax+00h]
0x1400770ab  mov     r14d, dword ptr [rbp+37h+LockHandle.LockQueue.Next+4]
0x1400770af  test    r14d, r14d
0x1400770b2  jnz     short loc_1400770CC
0x1400770b4  mov     rcx, gs:188h
0x1400770bd  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400770c4  nop     dword ptr [rax+rax+00h]
0x1400770c9  mov     r14d, eax
0x1400770cc  mov     cl, 2; NewIrql
0x1400770ce  call    cs:__imp_KfRaiseIrql
0x1400770d5  nop     dword ptr [rax+rax+00h]
0x1400770da  lea     r12, [rbx+4DA8h]
0x1400770e1  mov     [rsp+110h+var_C0], al
0x1400770e5  mov     rcx, r12; SpinLock
0x1400770e8  call    RtlAcquireReadLockAtDpcLevel
0x1400770ed  mov     r8d, [rbx+4D9Ch]
0x1400770f4  dec     r8d
0x1400770f7  mov     ecx, r14d
0x1400770fa  and     r8, rcx
0x1400770fd  shl     r8, 4
0x140077101  add     r8, [rbx+4DA0h]
0x140077108  mov     rcx, [r8]
0x14007710b  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x140077112  cmp     rcx, r8
0x140077115  jz      loc_140077C2B
0x14007711b  cmp     [rcx-30h], r14d
0x14007711f  lea     rbx, [rcx-30h]
0x140077123  jnz     loc_140077A10
0x140077129  mov     eax, 1
0x14007712e  lock xadd [rbx+20h], rax
0x140077134  inc     rax
0x140077137  cmp     rax, 1
0x14007713b  jle     loc_140077C76
0x140077141  movzx   ecx, [rsp+110h+var_C0]; NewIrql
0x140077146  lock dec dword ptr [r12+8]
0x14007714c  call    cs:__imp_KeLowerIrql
0x140077153  nop     dword ptr [rax+rax+00h]
0x140077158  test    rbx, rbx
0x14007715b  jz      short loc_140077184
0x14007715d  movups  xmm0, xmmword ptr [rbx+4]
0x140077161  mov     rax, rsi
0x140077164  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Lock], xmm0
0x140077168  lock xadd [rbx+20h], rax
0x14007716e  sub     rax, 1
0x140077172  jg      short loc_140077184
0x140077174  test    rax, rax
0x140077177  jz      loc_140077B75
0x14007717d  mov     ecx, 0Eh
0x140077182  int     29h; Win8: RtlFailFast(ecx)
0x140077184  mov     ecx, [rdi]
0x140077186  lea     rax, [rbp+37h+LockHandle]
0x14007718a  mov     r9b, 1
0x14007718d  mov     [rsp+110h+var_F0], rax
0x140077192  movzx   r8d, r9b
0x140077196  lea     rdx, [rdi+4]
0x14007719a  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1400771a1  nop     dword ptr [rax+rax+00h]
0x1400771a6  test    al, al
0x1400771a8  jz      loc_1400778F1
0x1400771ae  mov     ebx, [rbp+37h+arg_30]
0x1400771b1  mov     r14d, ebx
0x1400771b4  mov     r12, [rdi+28h]
0x1400771b8  shr     r14d, 1Ch
0x1400771bc  mov     rax, [r12+0A8h]
0x1400771c4  test    r14d, r14d
0x1400771c7  jnz     loc_140077B9D
0x1400771cd  mov     r14, [rbp+37h+var_90]
0x1400771d1  mov     rcx, r14
0x1400771d4  call    _guard_dispatch_icall
0x1400771d9  mov     ecx, ebx
0x1400771db  shl     eax, 1Ch
0x1400771de  and     ecx, 0FFFFFFFh
0x1400771e4  mov     ebx, eax
0x1400771e6  or      ebx, ecx
0x1400771e8  mov     eax, ebx
0x1400771ea  and     eax, 0F0000000h
0x1400771ef  cmp     eax, 0E0000000h
0x1400771f4  jnz     loc_140077840
0x1400771fa  test    ebx, 0FFFFFFFh
0x140077200  jnz     loc_1400778E0
0x140077206  mov     eax, ebx
0x140077208  xor     eax, [rdi]
0x14007720a  and     eax, 0FFFFFFFh
0x14007720f  xor     ebx, eax
0x140077211  mov     r12, [rbp+37h+var_98]
0x140077215  mov     r14, [rbp+37h+var_80]
0x140077219  mov     rcx, r14
0x14007721c  mov     rax, [r12+0B0h]
0x140077224  call    _guard_dispatch_icall
0x140077229  test    eax, eax
0x14007722b  jnz     loc_1400778C8
0x140077231  mov     rdx, [rbp+37h+var_78]
0x140077235  test    rdx, rdx
0x140077238  jnz     loc_1400779BA
0x14007723e  mov     r14, r13
0x140077241  mov     rax, [rdi+28h]
0x140077245  mov     rcx, [rbp+37h+var_90]
0x140077249  mov     rax, [rax+0B0h]
0x140077250  call    _guard_dispatch_icall
0x140077255  test    eax, eax
0x140077257  jz      loc_140077518
0x14007725d  mov     rax, [rdi+28h]
0x140077261  mov     rcx, [rbp+37h+var_90]
0x140077265  mov     rax, [rax+0B0h]
0x14007726c  call    _guard_dispatch_icall
0x140077271  test    eax, eax
0x140077273  jz      loc_14007742C
0x140077279  mov     rax, [rbp+37h+var_A8]
0x14007727d  mov     r8d, ebx
0x140077280  mov     rcx, r14
0x140077283  test    rax, rax
0x140077286  jnz     loc_1400773DD
0x14007728c  test    rcx, rcx
0x14007728f  jnz     loc_1400773F2
0x140077295  test    rax, rax
0x140077298  jz      short loc_14007729E
0x14007729a  mov     r14, [rax+8]
0x14007729e  mov     rdx, [rbp+37h+var_90]
0x1400772a2  lea     rcx, [rbp+37h+a]
0x1400772a6  mov     [rsp+110h+var_E8], rcx
0x1400772ab  mov     r9, r14
0x1400772ae  mov     rcx, rdi
0x1400772b1  mov     [rsp+110h+var_F0], rax
0x1400772b6  call    IppFindOrCreatePath
0x1400772bb  mov     r15, [rbp+37h+a]
0x1400772bf  mov     r14d, 0C0000225h
0x1400772c5  cmp     eax, r14d
0x1400772c8  jz      loc_140077434
0x1400772ce  mov     r14d, eax
0x1400772d1  test    eax, eax
0x1400772d3  js      loc_14007743A
0x1400772d9  mov     rcx, r15
0x1400772dc  call    IppGetRouteFromPath
0x1400772e1  mov     r13, rax
0x1400772e4  test    rax, rax
0x1400772e7  jz      loc_140077518
0x1400772ed  mov     rax, [r15]
0x1400772f0  xor     edx, edx
0x1400772f2  mov     [rbp+37h+var_B0], rax
0x1400772f6  mov     r8, [rax+20h]
0x1400772fa  mov     eax, gs:1A4h
0x140077302  div     dword ptr [r8+14h]
0x140077306  mov     eax, 2
0x14007730b  imul    edx, [r8+10h]
0x140077310  mov     ecx, edx
0x140077312  add     rcx, [r8]
0x140077315  lock xadd [rcx], rax
0x14007731a  test    al, 1
0x14007731c  jz      short loc_140077324
0x14007731e  lock add qword ptr [r8+18h], 2
0x140077324  mov     rbx, [rbp+37h+var_68]
0x140077328  test    rbx, rbx
0x14007732b  jz      loc_140077CD4
0x140077331  lea     rax, Ipv4Global
0x140077338  xor     edx, edx; Val
0x14007733a  mov     rcx, rbx; void *
0x14007733d  cmp     r12, rax
0x140077340  jnz     loc_1400776F4
0x140077346  mov     r8d, 68h ; 'h'; Size
0x14007734c  call    memset
0x140077351  test    r13, r13
0x140077354  jz      short loc_140077385
0x140077356  lea     r8, [rbx+30h]
0x14007735a  mov     r9, rbx
0x14007735d  lea     rax, [rbx+54h]
0x140077361  mov     rcx, r12
0x140077364  mov     [rsp+110h+var_E0], rax
0x140077369  lea     rdx, [rbx+4Ch]
0x14007736d  mov     [rsp+110h+var_E8], rdx
0x140077372  mov     rdx, r13
0x140077375  mov     [rsp+110h+var_F0], r8
0x14007737a  xor     r8d, r8d
0x14007737d  call    IppFillUnicastRouteData
0x140077382  mov     r14d, eax
0x140077385  mov     r12, [rbp+37h+var_B0]
0x140077389  xor     ebx, ebx
0x14007738b  mov     rax, [r12+8]
0x140077390  mov     rcx, [r12+10h]
0x140077395  mov     [rbp+37h+var_98], rax
0x140077399  mov     rdx, [rax]
0x14007739c  mov     rcx, [rcx]
0x14007739f  mov     [rbp+37h+a], rcx
0x1400773a3  mov     rax, [rdx+28h]
0x1400773a7  mov     [rbp+37h+var_78], rax
0x1400773ab  mov     rax, [rax+0A8h]
0x1400773b2  call    _guard_dispatch_icall
0x1400773b7  movsxd  rdx, eax
0x1400773ba  cmp     edx, 0Eh
0x1400773bd  jnz     loc_1400777B8
0x1400773c3  mov     rdx, [rbp+37h+var_68]
0x1400773c7  mov     [rdx+5Ch], ebx
0x1400773ca  mov     rax, [r12+10h]
0x1400773cf  mov     rcx, [rax]
0x1400773d2  mov     eax, [rcx]
0x1400773d4  mov     [rdx+60h], eax
0x1400773d7  mov     rax, [rbp+37h+var_A8]
0x1400773db  jmp     short loc_140077441
0x1400773dd  cmp     dword ptr [rax+18h], 1
0x1400773e1  jnz     short loc_14007742C
0x1400773e3  test    r14, r14
0x1400773e6  jz      loc_1400779B1
0x1400773ec  cmp     r14, [rax+8]
0x1400773f0  jnz     short loc_14007742C
0x1400773f2  mov     edx, ebx
0x1400773f4  shr     edx, 1Ch
0x1400773f7  cmp     edx, 1
  ... truncated ...
```
