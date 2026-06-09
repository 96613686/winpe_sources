# IppGetAllBestRouteParameters

- ea: `0x140028bf0`
- end: `0x1400299b1`
- name: `IppGetAllBestRouteParameters`
- size: `3521`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x14002a450`
- `0x14002a860`

## callees

- `0x140027d90`
- `0x140028bf0`
- `0x140029bb0`
- `0x14002a4f0`
- `0x14002ad30`
- `0x14002b280`
- `0x14002f4f0`
- `0x140030050`
- `0x140030410`
- `0x140030580`
- `0x140030da0`
- `0x140032740`
- `0x14004b308`
- `0x14004bc20`
- `0x140067d00`
- `0x14006e130`
- `0x14006e1e0`
- `0x14010135c`
- `0x1401bf390`
- `0x1401bf5c0`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140028c6d`
- `ntoskrnl!KfRaiseIrql` at `0x140028d9e`
- `ntoskrnl!KfRaiseIrql` at `0x1400291ea`
- `ntoskrnl!KfRaiseIrql` at `0x140028c6d`
- `ntoskrnl!KfRaiseIrql` at `0x140028d9e`
- `ntoskrnl!KfRaiseIrql` at `0x1400291ea`
- `ntoskrnl!KeLowerIrql` at `0x140028d1d`
- `ntoskrnl!KeLowerIrql` at `0x140028e1c`
- `ntoskrnl!KeLowerIrql` at `0x1400293b0`
- `ntoskrnl!KeLowerIrql` at `0x14002963b`
- `ntoskrnl!KeLowerIrql` at `0x14002982b`
- `ntoskrnl!KeLowerIrql` at `0x140029906`
- `ntoskrnl!KeLowerIrql` at `0x140028d1d`
- `ntoskrnl!KeLowerIrql` at `0x140028e1c`
- `ntoskrnl!KeLowerIrql` at `0x1400293b0`
- `ntoskrnl!KeLowerIrql` at `0x14002963b`
- `ntoskrnl!KeLowerIrql` at `0x14002982b`
- `ntoskrnl!KeLowerIrql` at `0x140029906`
- `ntoskrnl!IoQueueWorkItem` at `0x1400297e3`
- `ntoskrnl!IoQueueWorkItem` at `0x14002985c`
- `ntoskrnl!IoQueueWorkItem` at `0x1400297e3`
- `ntoskrnl!IoQueueWorkItem` at `0x14002985c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140028cac`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140028cac`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140028cc0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140028cc0`
- `ntoskrnl!KeTestSpinLock` at `0x140028c91`
- `ntoskrnl!KeTestSpinLock` at `0x140028c91`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x140028e6a`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x140028e6a`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140028d6f`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140028d6f`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140028c56`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140028d8d`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140028c56`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140028d8d`

## pseudocode

```c
__int64 __fastcall IppGetAllBestRouteParameters(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
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
  void *v40; // rbx
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
  __int64 v57; // r9
  _DWORD *v58; // r14
  __int64 v59; // rcx
  bool v60; // zf
  __int64 v61; // r13
  __int64 BestSourceAddressOnHost; // rax
  _QWORD *v63; // r13
  _QWORD *v64; // r8
  __int64 v65; // r8
  PVOID v66; // rax
  __int64 v67; // rcx
  int v68; // edx
  int v69; // eax
  int v70; // ebx
  IN6_ADDR *v71; // rcx
  int v72; // eax
  __int64 v73; // rdx
  char *v74; // rdx
  char v75; // al
  char v76; // al
  char v77; // al
  __int64 v78; // rax
  int v79; // ecx
  __int64 v80; // r9
  int v81; // [rsp+28h] [rbp-B1h]
  KIRQL v82; // [rsp+50h] [rbp-89h]
  char v83; // [rsp+50h] [rbp-89h]
  KIRQL v84; // [rsp+51h] [rbp-88h]
  unsigned int v85; // [rsp+58h] [rbp-81h] BYREF
  _QWORD *v86; // [rsp+60h] [rbp-79h]
  __int64 v87; // [rsp+68h] [rbp-71h]
  IN6_ADDR *a; // [rsp+70h] [rbp-69h] BYREF
  PVOID v89; // [rsp+78h] [rbp-61h]
  IN6_ADDR *v90; // [rsp+80h] [rbp-59h]
  PVOID P; // [rsp+88h] [rbp-51h]
  _DWORD *v92; // [rsp+90h] [rbp-49h]
  __int64 v93; // [rsp+98h] [rbp-41h]
  PVOID Context; // [rsp+A0h] [rbp-39h]
  void *v95; // [rsp+A8h] [rbp-31h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B0h] [rbp-29h] BYREF

  ThreadObjectCompartmentId = a2;
  v93 = a5;
  v10 = 0;
  v90 = a6;
  v92 = (_DWORD *)a3;
  v89 = (PVOID)a1;
  v85 = a4;
  v95 = a8;
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
  v87 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  RouteFromPath = 0;
  v86 = 0;
  Context = 0;
  P = 0;
  NdisGetThreadObjectCompartmentScope(KeGetCurrentThread(), &LockHandle, (char *)&LockHandle.LockQueue.Next + 4);
  Next_high = HIDWORD(LockHandle.LockQueue.Next);
  if ( !HIDWORD(LockHandle.LockQueue.Next) )
    Next_high = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
  v19 = v16 + 19880;
  v82 = KfRaiseIrql(2u);
  RtlAcquireReadLockAtDpcLevel((PKSPIN_LOCK)(v16 + 19880));
  v20 = (_QWORD **)(*(_QWORD *)(v16 + 19872) + 16LL * (Next_high & (unsigned int)(*(_DWORD *)(v16 + 19868) - 1)));
  for ( j = *v20; ; j = (_QWORD *)*j )
  {
    if ( j == v20 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v19 + 8));
      KeLowerIrql(v82);
      goto LABEL_20;
    }
    v22 = j - 6;
    if ( *((_DWORD *)j - 12) == Next_high )
      break;
  }
  if ( _InterlockedIncrement64(v22 + 4) <= 1 )
    __fastfail(0xEu);
  _InterlockedDecrement((volatile signed __int32 *)(v19 + 8));
  KeLowerIrql(v82);
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
    v29 = v90;
    v26 = a7 & 0xFFFFFFF | (v28(v90) << 28);
    goto LABEL_23;
  }
  if ( a7 >> 28 != v28(v90) )
    goto LABEL_127;
  v29 = v90;
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
    v76 = IN6_IS_ADDR_LOOPBACK(v29);
  else
    v76 = v29->u.Byte[0] == 127;
  if ( v76 )
  {
    if ( (v26 & 0xFFFFFFF) != 0 )
      goto LABEL_127;
    v30 = v15[7] ^ v26;
LABEL_26:
    v26 ^= v30 & 0xFFFFFFF;
  }
  v31 = (int *)v89;
  v32 = (__int64)v92;
  if ( (*((unsigned int (__fastcall **)(_DWORD *))v89 + 22))(v92) )
  {
    if ( !(unsigned __int8)IppCanonicalizeScopeId(v15, v92, &v85) )
      goto LABEL_127;
    AddressInScope = IppFindAddressInScope(v15, v85, v32);
    v87 = AddressInScope;
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
    if ( !v93 )
    {
      v33 = 0;
      goto LABEL_30;
    }
    Context = (PVOID)IppFindInterfaceByLuid(v89);
    v33 = (_DWORD **)Context;
    if ( !Context )
    {
      NextHopAtDpcHelper = -1073741275;
      v41 = 0;
      AddressInScope = 0;
      goto LABEL_59;
    }
LABEL_156:
    v78 = v26 >> 28;
    if ( (unsigned int)v78 <= 1 )
    {
      v79 = *((_DWORD *)v33 + 2);
    }
    else if ( (unsigned int)v78 >= 0xE )
    {
      v79 = **v33;
    }
    else
    {
      _mm_lfence();
      v79 = *((_DWORD *)v33 + v78 + 192) & 0xFFFFFFF;
    }
    if ( (v26 & 0xFFFFFFF) != 0 )
    {
      if ( (v26 & 0xFFFFFFF) != v79 )
      {
        NextHopAtDpcHelper = -1073741811;
        goto LABEL_57;
      }
    }
    else
    {
      v26 ^= (v26 ^ v79) & 0xFFFFFFF;
    }
  }
LABEL_30:
  if ( (*(unsigned int (__fastcall **)(IN6_ADDR *))(*((_QWORD *)v15 + 5) + 176LL))(v90) )
  {
    if ( !(*(unsigned int (__fastcall **)(IN6_ADDR *))(*((_QWORD *)v15 + 5) + 176LL))(v90) )
      goto LABEL_55;
    v34 = v87;
    v35 = v26;
    v36 = v33;
    if ( !v87 )
      goto LABEL_33;
    if ( *(_DWORD *)(v87 + 24) != 1 )
      goto LABEL_55;
    if ( v33 )
    {
      if ( v33 == *(_DWORD ***)(v87 + 8) )
        goto LABEL_50;
LABEL_55:
      NextHopAtDpcHelper = -1073741305;
      goto LABEL_57;
    }
    v36 = *(_DWORD ***)(v87 + 8);
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
        v34 = v87;
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
    v37 = IppFindOrCreatePath(v15, v90, v35, v33, v34, &a);
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
      v86 = *(_QWORD **)v10->u.Byte;
      v39 = v86[4];
      if ( (_InterlockedExchangeAdd64(
              (volatile signed __int64 *)(*(_QWORD *)v39
                                        + (unsigned int)(*(_DWORD *)(v39 + 16)
                                                       * (HIDWORD(KeGetPcr()[1].LockArray) % *(_DWORD *)(v39 + 20)))),
              2u)
          & 1) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(v39 + 24), 2u);
LABEL_41:
      v40 = v95;
      if ( v95 )
      {
        if ( v31 == &Ipv4Global )
        {
          memset(v95, 0, 0x68u);
          if ( RouteFromPath )
            NextHopAtDpcHelper = IppFillUnicastRouteData(
                                   (_DWORD)v31,
                                   (_DWORD)RouteFromPath,
                                   0,
                                   (_DWORD)v40,
                                   (__int64)v40 + 48,
                                   (__int64)v40 + 76,
                                   (__int64)v40 + 84);
          v41 = v86;
          v42 = 0;
          v43 = (IN6_ADDR **)v86[2];
          v89 = (PVOID)v86[1];
          v44 = *(_QWORD *)v89;
          a = *v43;
          v93 = *(_QWORD *)(v44 + 40);
          v45 = (*(__int64 (**)(void))(v93 + 168))();
          v46 = v45;
          if ( v45 != 14 )
          {
            v75 = *(_WORD *)(v93 + 28) == 23 ? IN6_IS_ADDR_LOOPBACK(a) : a->u.Byte[0] == 127;
            if ( !v75 )
            {
              if ( (int)v46 <= 1 )
              {
                v42 = *((_DWORD *)v89 + 2) & 0xFFFFFFF;
              }
              else if ( (int)v46 >= 14 )
              {
                v42 = **(_DWORD **)v89 & 0xFFFFFFF;
              }
              else
              {
                v42 = *((_DWORD *)v89 + v46 + 192) & 0xFFFFFFF;
              }
            }
          }
          v47 = v95;
          *((_DWORD *)v95 + 23) = v42;
          v47[24] = **(_DWORD **)v41[2];
          AddressInScope = v87;
        }
        else
        {
          memset(v95, 0, 0x98u);
          if ( RouteFromPath )
            NextHopAtDpcHelper = IppFillUnicastRouteData(
                                   (_DWORD)v31,
                                   (_DWORD)RouteFromPath,
                                   0,
                                   (_DWORD)v40,
                                   (__int64)v40 + 72,
                                   (__int64)v40 + 100,
                                   (__int64)v40 + 120);
          v41 = v86;
          v70 = 0;
          v71 = *(IN6_ADDR **)v86[2];
          v89 = (PVOID)v86[1];
          a = v71;
          v93 = *(_QWORD *)(*(_QWORD *)v89 + 40LL);
          v72 = (*(__int64 (**)(void))(v93 + 168))();
          v73 = v72;
          if ( v72 != 14 )
          {
            v77 = *(_WORD *)(v93 + 28) == 23 ? IN6_IS_ADDR_LOOPBACK(a) : a->u.Byte[0] == 127;
            if ( !v77 )
            {
              if ( (int)v73 <= 1 )
              {
                v70 = *((_DWORD *)v89 + 2) & 0xFFFFFFF;
              }
              else if ( (int)v73 >= 14 )
              {
                v70 = **(_DWORD **)v89 & 0xFFFFFFF;
              }
              else
              {
                v70 = *((_DWORD *)v89 + v73 + 192) & 0xFFFFFFF;
              }
            }
          }
          v74 = (char *)v95;
          *((_DWORD *)v95 + 32) = v70;
          AddressInScope = v87;
          *(_OWORD *)(v74 + 132) = *(_OWORD *)*(_QWORD *)v41[2];
        }
      }
      else
      {
        v41 = v86;
        AddressInScope = v87;
      }
      goto LABEL_59;
    }
  }
  v54 = KfRaiseIrql(2u);
  v89 = 0;
  v55 = 0;
  v84 = v54;
  while ( 2 )
  {
    a = 0;
LABEL_76:
    v85 = 0;
    v56 = Context;
    LOBYTE(v81) = v55 ^ 1;
    NextHopAtDpcHelper = IppFindNextHopAtDpcHelper(v15, Context, v90, v26, v87, v81);
    if ( NextHopAtDpcHelper >= 0 )
    {
      v58 = v89;
      v59 = (__int64)v56;
      v83 = 0;
      P = (PVOID)v87;
      v60 = *(_DWORD *)v89 == 1634496585;
      v92 = v56;
      if ( v60 && *((_DWORD *)v89 + 6) == 4 )
      {
        v59 = *((_QWORD *)v89 + 1);
        v92 = (_DWORD *)v59;
      }
      v61 = *((_QWORD *)v89 + 1);
      v93 = v61;
      if ( v87 )
      {
        v65 = *(_QWORD *)(v87 + 32);
        if ( (_InterlockedExchangeAdd64(
                (volatile signed __int64 *)(*(_QWORD *)v65
                                          + (unsigned int)(*(_DWORD *)(v65 + 16)
                                                         * (HIDWORD(KeGetPcr()[1].LockArray) % *(_DWORD *)(v65 + 20)))),
                2u)
            & 1) != 0 )
          _InterlockedAdd64((volatile signed __int64 *)(v65 + 24), 2u);
      }
      else
      {
        if ( !v59 )
        {
          BestSourceAddressOnHost = IppFindBestSourceAddressOnHost(v61, v90, v89, 0);
          v55 = 0;
          v63 = (_QWORD *)BestSourceAddressOnHost;
          v64 = P;
          goto LABEL_93;
        }
        P = (PVOID)IppFindBestSourceAddressOnInterface(v59, v90);
        v64 = P;
        if ( !P )
        {
          v63 = 0;
          v55 = 0;
          goto LABEL_93;
        }
      }
      LOBYTE(v57) = 1;
      v66 = (PVOID)IppFindBestSourceAddressOnHost(v61, v90, v58, v57);
      v64 = P;
      if ( v66 == P )
      {
        if ( v92 != (_DWORD *)v61 )
          LOBYTE(v85) = v85 | 2;
      }
      else
      {
        LOBYTE(v85) = v85 | 1;
      }
      if ( v66 )
      {
        IppDereferenceLocalAddress(v66);
        v64 = P;
      }
      v67 = *(_DWORD *)(v64[2] + 8LL) >> 28;
      if ( (unsigned int)v67 <= 1 )
      {
        v68 = v92[2];
        v69 = *(_DWORD *)(v61 + 8);
      }
      else if ( (unsigned int)v67 >= 0xE )
      {
        v68 = **(_DWORD **)v92;
        v69 = **(_DWORD **)v61;
      }
      else
      {
        v68 = v92[v67 + 192] & 0xFFFFFFF;
        v69 = *(_DWORD *)(v61 + 4 * v67 + 768) & 0xFFFFFFF;
      }
      if ( v69 == v68 )
      {
        v55 = 0;
        v63 = v64;
      }
      else
      {
        IppDereferenceLocalAddress(v64);
        v64 = P;
        v55 = 1;
        v83 = 1;
        v63 = 0;
      }
LABEL_93:
      v86 = v63;
      if ( (BYTE5(WPP_MAIN_CB.Reserved) & 0x20) != 0 )
      {
        if ( v63 )
          v80 = *(_QWORD *)v63[2];
        else
          LODWORD(v80) = 0;
        if ( v64 )
          v64 = *(_QWORD **)v64[2];
        IppLogSrcAddrLookupEvent(*(_QWORD *)v93, (_DWORD)v90, (_DWORD)v64, v80, (__int64)v92, v93, v85);
        v55 = v83;
      }
      if ( !v55 )
      {
        if ( v63 )
        {
          RouteFromPath = a;
          P = v58;
          KeLowerIrql(v84);
          NextHopAtDpcHelper = 0;
          goto LABEL_41;
        }
        NextHopAtDpcHelper = -1073741251;
        break;
      }
      if ( *v58 == 1634496585 )
      {
        IppDereferenceLocalAddress(v58);
      }
      else
      {
        if ( *v58 != 1701736521 )
          goto LABEL_112;
        IppDereferenceNeighbor(v58);
      }
      v55 = v83;
LABEL_112:
      if ( a )
      {
        IppDereferenceRoute(a);
        v55 = v83;
        continue;
      }
      goto LABEL_76;
    }
    break;
  }
  RouteFromPath = 0;
  v86 = 0;
  P = 0;
  if ( a )
    IppDereferenceRoute(a);
  if ( v89 )
  {
    if ( *(_DWORD *)v89 == 1634496585 )
    {
      IppDereferenceLocalAddress(v89);
    }
    else if ( *(_DWORD *)v89 == 1701736521 )
    {
      IppDereferenceNeighbor(v89);
    }
  }
  KeLowerIrql(v84);
LABEL_57:
  AddressInScope = v87;
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
    AddressInScope = v87;
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
0x140028bf0  push    rbp
0x140028bf2  push    rbx
0x140028bf3  push    rsi
0x140028bf4  push    rdi
0x140028bf5  push    r12
0x140028bf7  push    r14
0x140028bf9  push    r15
0x140028bfb  lea     rbp, [rsp-7]
0x140028c00  sub     rsp, 0E0h
0x140028c07  mov     rax, cs:__security_cookie
0x140028c0e  xor     rax, rsp
0x140028c11  mov     [rbp+37h+var_48], rax
0x140028c15  mov     rax, [rbp+37h+arg_20]
0x140028c19  xor     r12d, r12d
0x140028c1c  mov     esi, edx
0x140028c1e  mov     [rbp+37h+var_78], rax
0x140028c22  mov     rax, [rbp+37h+arg_28]
0x140028c26  mov     rdi, rcx
0x140028c29  mov     rdx, [rbp+37h+arg_38]
0x140028c2d  mov     r15d, r12d
0x140028c30  mov     [rbp+37h+var_90], rax
0x140028c34  mov     [rbp+37h+var_80], r8
0x140028c38  mov     [rbp+37h+var_98], rcx
0x140028c3c  mov     [rsp+110h+var_B8], r9d
0x140028c41  mov     [rbp+37h+var_68], rdx
0x140028c45  mov     [rbp+37h+a], r12
0x140028c49  test    esi, esi
0x140028c4b  jnz     short loc_140028C64
0x140028c4d  mov     rcx, gs:188h
0x140028c56  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140028c5d  nop     dword ptr [rax+rax+00h]
0x140028c62  mov     esi, eax
0x140028c64  mov     cl, 2; NewIrql
0x140028c66  lea     rbx, [rdi+4DA8h]
0x140028c6d  call    cs:__imp_KfRaiseIrql
0x140028c74  nop     dword ptr [rax+rax+00h]
0x140028c79  movzx   r14d, al
0x140028c7d  xorps   xmm0, xmm0
0x140028c80  xor     eax, eax
0x140028c82  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rax
0x140028c86  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x140028c8a  lock inc dword ptr [rbx+8]
0x140028c8e  mov     rcx, rbx; SpinLock
0x140028c91  call    cs:__imp_KeTestSpinLock
0x140028c98  nop     dword ptr [rax+rax+00h]
0x140028c9d  test    al, al
0x140028c9f  jnz     short loc_140028CCC
0x140028ca1  lock dec dword ptr [rbx+8]
0x140028ca5  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x140028ca9  mov     rcx, rbx; SpinLock
0x140028cac  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140028cb3  nop     dword ptr [rax+rax+00h]
0x140028cb8  lock inc dword ptr [rbx+8]
0x140028cbc  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x140028cc0  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140028cc7  nop     dword ptr [rax+rax+00h]
0x140028ccc  mov     edx, [rdi+4D9Ch]
0x140028cd2  dec     edx
0x140028cd4  mov     eax, esi
0x140028cd6  and     rdx, rax
0x140028cd9  shl     rdx, 4
0x140028cdd  add     rdx, [rdi+4DA0h]
0x140028ce4  mov     rax, [rdx]
0x140028ce7  cmp     rax, rdx
0x140028cea  jz      loc_140029633
0x140028cf0  cmp     [rax-30h], esi
0x140028cf3  lea     rdi, [rax-30h]
0x140028cf7  jnz     loc_1400296C8
0x140028cfd  mov     eax, 1
0x140028d02  lock xadd [rdi+20h], rax
0x140028d08  inc     rax
0x140028d0b  cmp     rax, 1
0x140028d0f  jle     loc_14002993A
0x140028d15  lock dec dword ptr [rbx+8]
0x140028d19  movzx   ecx, r14b; NewIrql
0x140028d1d  call    cs:__imp_KeLowerIrql
0x140028d24  nop     dword ptr [rax+rax+00h]
0x140028d29  test    rdi, rdi
0x140028d2c  jz      loc_140029647
0x140028d32  mov     rbx, [rdi+28h]
0x140028d36  lea     r8, [rbp+37h+LockHandle.LockQueue.Next+4]
0x140028d3a  xorps   xmm0, xmm0
0x140028d3d  mov     [rsp+110h+var_38], r13
0x140028d45  xor     eax, eax
0x140028d47  mov     [rbp+37h+var_A8], r12
0x140028d4b  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x140028d4f  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rax
0x140028d53  lea     rdx, [rbp+37h+LockHandle]
0x140028d57  mov     rcx, gs:188h
0x140028d60  mov     r13, r12
0x140028d63  mov     [rbp+37h+var_B0], r12
0x140028d67  mov     [rbp+37h+Context], r12
0x140028d6b  mov     [rbp+37h+P], r12
0x140028d6f  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x140028d76  nop     dword ptr [rax+rax+00h]
0x140028d7b  mov     r14d, dword ptr [rbp+37h+LockHandle.LockQueue.Next+4]
0x140028d7f  test    r14d, r14d
0x140028d82  jnz     short loc_140028D9C
0x140028d84  mov     rcx, gs:188h
0x140028d8d  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140028d94  nop     dword ptr [rax+rax+00h]
0x140028d99  mov     r14d, eax
0x140028d9c  mov     cl, 2; NewIrql
0x140028d9e  call    cs:__imp_KfRaiseIrql
0x140028da5  nop     dword ptr [rax+rax+00h]
0x140028daa  lea     r12, [rbx+4DA8h]
0x140028db1  mov     [rsp+110h+var_C0], al
0x140028db5  mov     rcx, r12; SpinLock
0x140028db8  call    RtlAcquireReadLockAtDpcLevel
0x140028dbd  mov     r8d, [rbx+4D9Ch]
0x140028dc4  dec     r8d
0x140028dc7  mov     ecx, r14d
0x140028dca  and     r8, rcx
0x140028dcd  shl     r8, 4
0x140028dd1  add     r8, [rbx+4DA0h]
0x140028dd8  mov     rcx, [r8]
0x140028ddb  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x140028de2  cmp     rcx, r8
0x140028de5  jz      loc_1400298FB
0x140028deb  cmp     [rcx-30h], r14d
0x140028def  lea     rbx, [rcx-30h]
0x140028df3  jnz     loc_1400296E0
0x140028df9  mov     eax, 1
0x140028dfe  lock xadd [rbx+20h], rax
0x140028e04  inc     rax
0x140028e07  cmp     rax, 1
0x140028e0b  jle     loc_140029946
0x140028e11  movzx   ecx, [rsp+110h+var_C0]; NewIrql
0x140028e16  lock dec dword ptr [r12+8]
0x140028e1c  call    cs:__imp_KeLowerIrql
0x140028e23  nop     dword ptr [rax+rax+00h]
0x140028e28  test    rbx, rbx
0x140028e2b  jz      short loc_140028E54
0x140028e2d  movups  xmm0, xmmword ptr [rbx+4]
0x140028e31  mov     rax, rsi
0x140028e34  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Lock], xmm0
0x140028e38  lock xadd [rbx+20h], rax
0x140028e3e  sub     rax, 1
0x140028e42  jg      short loc_140028E54
0x140028e44  test    rax, rax
0x140028e47  jz      loc_140029845
0x140028e4d  mov     ecx, 0Eh
0x140028e52  int     29h; Win8: RtlFailFast(ecx)
0x140028e54  mov     ecx, [rdi]
0x140028e56  lea     rax, [rbp+37h+LockHandle]
0x140028e5a  mov     r9b, 1
0x140028e5d  mov     [rsp+110h+var_F0], rax
0x140028e62  movzx   r8d, r9b
0x140028e66  lea     rdx, [rdi+4]
0x140028e6a  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x140028e71  nop     dword ptr [rax+rax+00h]
0x140028e76  test    al, al
0x140028e78  jz      loc_1400295C1
0x140028e7e  mov     ebx, [rbp+37h+arg_30]
0x140028e81  mov     r14d, ebx
0x140028e84  mov     r12, [rdi+28h]
0x140028e88  shr     r14d, 1Ch
0x140028e8c  mov     rax, [r12+0A8h]
0x140028e94  test    r14d, r14d
0x140028e97  jnz     loc_14002986D
0x140028e9d  mov     r14, [rbp+37h+var_90]
0x140028ea1  mov     rcx, r14
0x140028ea4  call    _guard_dispatch_icall
0x140028ea9  mov     ecx, ebx
0x140028eab  shl     eax, 1Ch
0x140028eae  and     ecx, 0FFFFFFFh
0x140028eb4  mov     ebx, eax
0x140028eb6  or      ebx, ecx
0x140028eb8  mov     eax, ebx
0x140028eba  and     eax, 0F0000000h
0x140028ebf  cmp     eax, 0E0000000h
0x140028ec4  jnz     loc_140029510
0x140028eca  test    ebx, 0FFFFFFFh
0x140028ed0  jnz     loc_1400295B0
0x140028ed6  mov     eax, ebx
0x140028ed8  xor     eax, [rdi]
0x140028eda  and     eax, 0FFFFFFFh
0x140028edf  xor     ebx, eax
0x140028ee1  mov     r12, [rbp+37h+var_98]
0x140028ee5  mov     r14, [rbp+37h+var_80]
0x140028ee9  mov     rcx, r14
0x140028eec  mov     rax, [r12+0B0h]
0x140028ef4  call    _guard_dispatch_icall
0x140028ef9  test    eax, eax
0x140028efb  jnz     loc_140029598
0x140028f01  mov     rdx, [rbp+37h+var_78]
0x140028f05  test    rdx, rdx
0x140028f08  jnz     loc_14002968A
0x140028f0e  mov     r14, r13
0x140028f11  mov     rax, [rdi+28h]
0x140028f15  mov     rcx, [rbp+37h+var_90]
0x140028f19  mov     rax, [rax+0B0h]
0x140028f20  call    _guard_dispatch_icall
0x140028f25  test    eax, eax
0x140028f27  jz      loc_1400291E8
0x140028f2d  mov     rax, [rdi+28h]
0x140028f31  mov     rcx, [rbp+37h+var_90]
0x140028f35  mov     rax, [rax+0B0h]
0x140028f3c  call    _guard_dispatch_icall
0x140028f41  test    eax, eax
0x140028f43  jz      loc_1400290FC
0x140028f49  mov     rax, [rbp+37h+var_A8]
0x140028f4d  mov     r8d, ebx
0x140028f50  mov     rcx, r14
0x140028f53  test    rax, rax
0x140028f56  jnz     loc_1400290AD
0x140028f5c  test    rcx, rcx
0x140028f5f  jnz     loc_1400290C2
0x140028f65  test    rax, rax
0x140028f68  jz      short loc_140028F6E
0x140028f6a  mov     r14, [rax+8]
0x140028f6e  mov     rdx, [rbp+37h+var_90]
0x140028f72  lea     rcx, [rbp+37h+a]
0x140028f76  mov     [rsp+110h+var_E8], rcx
0x140028f7b  mov     r9, r14
0x140028f7e  mov     rcx, rdi
0x140028f81  mov     [rsp+110h+var_F0], rax
0x140028f86  call    IppFindOrCreatePath
0x140028f8b  mov     r15, [rbp+37h+a]
0x140028f8f  mov     r14d, 0C0000225h
0x140028f95  cmp     eax, r14d
0x140028f98  jz      loc_140029104
0x140028f9e  mov     r14d, eax
0x140028fa1  test    eax, eax
0x140028fa3  js      loc_14002910A
0x140028fa9  mov     rcx, r15
0x140028fac  call    IppGetRouteFromPath
0x140028fb1  mov     r13, rax
0x140028fb4  test    rax, rax
0x140028fb7  jz      loc_1400291E8
0x140028fbd  mov     rax, [r15]
0x140028fc0  xor     edx, edx
0x140028fc2  mov     [rbp+37h+var_B0], rax
0x140028fc6  mov     r8, [rax+20h]
0x140028fca  mov     eax, gs:1A4h
0x140028fd2  div     dword ptr [r8+14h]
0x140028fd6  mov     eax, 2
0x140028fdb  imul    edx, [r8+10h]
0x140028fe0  mov     ecx, edx
0x140028fe2  add     rcx, [r8]
0x140028fe5  lock xadd [rcx], rax
0x140028fea  test    al, 1
0x140028fec  jz      short loc_140028FF4
0x140028fee  lock add qword ptr [r8+18h], 2
0x140028ff4  mov     rbx, [rbp+37h+var_68]
0x140028ff8  test    rbx, rbx
0x140028ffb  jz      loc_1400299A4
0x140029001  lea     rax, Ipv4Global
0x140029008  xor     edx, edx; Val
0x14002900a  mov     rcx, rbx; void *
0x14002900d  cmp     r12, rax
0x140029010  jnz     loc_1400293C4
0x140029016  mov     r8d, 68h ; 'h'; Size
0x14002901c  call    memset
0x140029021  test    r13, r13
0x140029024  jz      short loc_140029055
0x140029026  lea     r8, [rbx+30h]
0x14002902a  mov     r9, rbx
0x14002902d  lea     rax, [rbx+54h]
0x140029031  mov     rcx, r12
0x140029034  mov     [rsp+110h+var_E0], rax
0x140029039  lea     rdx, [rbx+4Ch]
0x14002903d  mov     [rsp+110h+var_E8], rdx
0x140029042  mov     rdx, r13
0x140029045  mov     [rsp+110h+var_F0], r8
0x14002904a  xor     r8d, r8d
0x14002904d  call    IppFillUnicastRouteData
0x140029052  mov     r14d, eax
0x140029055  mov     r12, [rbp+37h+var_B0]
0x140029059  xor     ebx, ebx
0x14002905b  mov     rax, [r12+8]
0x140029060  mov     rcx, [r12+10h]
0x140029065  mov     [rbp+37h+var_98], rax
0x140029069  mov     rdx, [rax]
0x14002906c  mov     rcx, [rcx]
0x14002906f  mov     [rbp+37h+a], rcx
0x140029073  mov     rax, [rdx+28h]
0x140029077  mov     [rbp+37h+var_78], rax
0x14002907b  mov     rax, [rax+0A8h]
0x140029082  call    _guard_dispatch_icall
0x140029087  movsxd  rdx, eax
0x14002908a  cmp     edx, 0Eh
0x14002908d  jnz     loc_140029488
0x140029093  mov     rdx, [rbp+37h+var_68]
0x140029097  mov     [rdx+5Ch], ebx
0x14002909a  mov     rax, [r12+10h]
0x14002909f  mov     rcx, [rax]
0x1400290a2  mov     eax, [rcx]
0x1400290a4  mov     [rdx+60h], eax
0x1400290a7  mov     rax, [rbp+37h+var_A8]
0x1400290ab  jmp     short loc_140029111
0x1400290ad  cmp     dword ptr [rax+18h], 1
0x1400290b1  jnz     short loc_1400290FC
0x1400290b3  test    r14, r14
0x1400290b6  jz      loc_140029681
0x1400290bc  cmp     r14, [rax+8]
0x1400290c0  jnz     short loc_1400290FC
0x1400290c2  mov     edx, ebx
0x1400290c4  shr     edx, 1Ch
0x1400290c7  cmp     edx, 1
  ... truncated ...
```
