# IppGetAllBestRouteParameters

- ea: `0x140028e90`
- end: `0x140029c51`
- name: `IppGetAllBestRouteParameters`
- size: `3521`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x14002a6f0`
- `0x14002ab00`

## callees

- `0x140028030`
- `0x140028e90`
- `0x140029e50`
- `0x14002a790`
- `0x14002afd0`
- `0x14002b520`
- `0x14002f790`
- `0x1400302f0`
- `0x1400306b0`
- `0x140030820`
- `0x140031040`
- `0x1400329e0`
- `0x14004b5a8`
- `0x14004bec0`
- `0x140067fa0`
- `0x14006e3d0`
- `0x14006e480`
- `0x14010137c`
- `0x1401bf4d0`
- `0x1401bf700`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140028f0d`
- `ntoskrnl!KfRaiseIrql` at `0x14002903e`
- `ntoskrnl!KfRaiseIrql` at `0x14002948a`
- `ntoskrnl!KfRaiseIrql` at `0x140028f0d`
- `ntoskrnl!KfRaiseIrql` at `0x14002903e`
- `ntoskrnl!KfRaiseIrql` at `0x14002948a`
- `ntoskrnl!KeLowerIrql` at `0x140028fbd`
- `ntoskrnl!KeLowerIrql` at `0x1400290bc`
- `ntoskrnl!KeLowerIrql` at `0x140029650`
- `ntoskrnl!KeLowerIrql` at `0x1400298db`
- `ntoskrnl!KeLowerIrql` at `0x140029acb`
- `ntoskrnl!KeLowerIrql` at `0x140029ba6`
- `ntoskrnl!KeLowerIrql` at `0x140028fbd`
- `ntoskrnl!KeLowerIrql` at `0x1400290bc`
- `ntoskrnl!KeLowerIrql` at `0x140029650`
- `ntoskrnl!KeLowerIrql` at `0x1400298db`
- `ntoskrnl!KeLowerIrql` at `0x140029acb`
- `ntoskrnl!KeLowerIrql` at `0x140029ba6`
- `ntoskrnl!IoQueueWorkItem` at `0x140029a83`
- `ntoskrnl!IoQueueWorkItem` at `0x140029afc`
- `ntoskrnl!IoQueueWorkItem` at `0x140029a83`
- `ntoskrnl!IoQueueWorkItem` at `0x140029afc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140028f4c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140028f4c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140028f60`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140028f60`
- `ntoskrnl!KeTestSpinLock` at `0x140028f31`
- `ntoskrnl!KeTestSpinLock` at `0x140028f31`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x14002910a`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x14002910a`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14002900f`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14002900f`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140028ef6`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14002902d`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140028ef6`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14002902d`

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
0x140028e90  push    rbp
0x140028e92  push    rbx
0x140028e93  push    rsi
0x140028e94  push    rdi
0x140028e95  push    r12
0x140028e97  push    r14
0x140028e99  push    r15
0x140028e9b  lea     rbp, [rsp-7]
0x140028ea0  sub     rsp, 0E0h
0x140028ea7  mov     rax, cs:__security_cookie
0x140028eae  xor     rax, rsp
0x140028eb1  mov     [rbp+37h+var_48], rax
0x140028eb5  mov     rax, [rbp+37h+arg_20]
0x140028eb9  xor     r12d, r12d
0x140028ebc  mov     esi, edx
0x140028ebe  mov     [rbp+37h+var_78], rax
0x140028ec2  mov     rax, [rbp+37h+arg_28]
0x140028ec6  mov     rdi, rcx
0x140028ec9  mov     rdx, [rbp+37h+arg_38]
0x140028ecd  mov     r15d, r12d
0x140028ed0  mov     [rbp+37h+var_90], rax
0x140028ed4  mov     [rbp+37h+var_80], r8
0x140028ed8  mov     [rbp+37h+var_98], rcx
0x140028edc  mov     [rsp+110h+var_B8], r9d
0x140028ee1  mov     [rbp+37h+var_68], rdx
0x140028ee5  mov     [rbp+37h+a], r12
0x140028ee9  test    esi, esi
0x140028eeb  jnz     short loc_140028F04
0x140028eed  mov     rcx, gs:188h
0x140028ef6  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140028efd  nop     dword ptr [rax+rax+00h]
0x140028f02  mov     esi, eax
0x140028f04  mov     cl, 2; NewIrql
0x140028f06  lea     rbx, [rdi+4DA8h]
0x140028f0d  call    cs:__imp_KfRaiseIrql
0x140028f14  nop     dword ptr [rax+rax+00h]
0x140028f19  movzx   r14d, al
0x140028f1d  xorps   xmm0, xmm0
0x140028f20  xor     eax, eax
0x140028f22  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rax
0x140028f26  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x140028f2a  lock inc dword ptr [rbx+8]
0x140028f2e  mov     rcx, rbx; SpinLock
0x140028f31  call    cs:__imp_KeTestSpinLock
0x140028f38  nop     dword ptr [rax+rax+00h]
0x140028f3d  test    al, al
0x140028f3f  jnz     short loc_140028F6C
0x140028f41  lock dec dword ptr [rbx+8]
0x140028f45  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x140028f49  mov     rcx, rbx; SpinLock
0x140028f4c  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140028f53  nop     dword ptr [rax+rax+00h]
0x140028f58  lock inc dword ptr [rbx+8]
0x140028f5c  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x140028f60  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140028f67  nop     dword ptr [rax+rax+00h]
0x140028f6c  mov     edx, [rdi+4D9Ch]
0x140028f72  dec     edx
0x140028f74  mov     eax, esi
0x140028f76  and     rdx, rax
0x140028f79  shl     rdx, 4
0x140028f7d  add     rdx, [rdi+4DA0h]
0x140028f84  mov     rax, [rdx]
0x140028f87  cmp     rax, rdx
0x140028f8a  jz      loc_1400298D3
0x140028f90  cmp     [rax-30h], esi
0x140028f93  lea     rdi, [rax-30h]
0x140028f97  jnz     loc_140029968
0x140028f9d  mov     eax, 1
0x140028fa2  lock xadd [rdi+20h], rax
0x140028fa8  inc     rax
0x140028fab  cmp     rax, 1
0x140028faf  jle     loc_140029BDA
0x140028fb5  lock dec dword ptr [rbx+8]
0x140028fb9  movzx   ecx, r14b; NewIrql
0x140028fbd  call    cs:__imp_KeLowerIrql
0x140028fc4  nop     dword ptr [rax+rax+00h]
0x140028fc9  test    rdi, rdi
0x140028fcc  jz      loc_1400298E7
0x140028fd2  mov     rbx, [rdi+28h]
0x140028fd6  lea     r8, [rbp+37h+LockHandle.LockQueue.Next+4]
0x140028fda  xorps   xmm0, xmm0
0x140028fdd  mov     [rsp+110h+var_38], r13
0x140028fe5  xor     eax, eax
0x140028fe7  mov     [rbp+37h+var_A8], r12
0x140028feb  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x140028fef  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rax
0x140028ff3  lea     rdx, [rbp+37h+LockHandle]
0x140028ff7  mov     rcx, gs:188h
0x140029000  mov     r13, r12
0x140029003  mov     [rbp+37h+var_B0], r12
0x140029007  mov     [rbp+37h+Context], r12
0x14002900b  mov     [rbp+37h+P], r12
0x14002900f  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x140029016  nop     dword ptr [rax+rax+00h]
0x14002901b  mov     r14d, dword ptr [rbp+37h+LockHandle.LockQueue.Next+4]
0x14002901f  test    r14d, r14d
0x140029022  jnz     short loc_14002903C
0x140029024  mov     rcx, gs:188h
0x14002902d  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140029034  nop     dword ptr [rax+rax+00h]
0x140029039  mov     r14d, eax
0x14002903c  mov     cl, 2; NewIrql
0x14002903e  call    cs:__imp_KfRaiseIrql
0x140029045  nop     dword ptr [rax+rax+00h]
0x14002904a  lea     r12, [rbx+4DA8h]
0x140029051  mov     [rsp+110h+var_C0], al
0x140029055  mov     rcx, r12; SpinLock
0x140029058  call    RtlAcquireReadLockAtDpcLevel
0x14002905d  mov     r8d, [rbx+4D9Ch]
0x140029064  dec     r8d
0x140029067  mov     ecx, r14d
0x14002906a  and     r8, rcx
0x14002906d  shl     r8, 4
0x140029071  add     r8, [rbx+4DA0h]
0x140029078  mov     rcx, [r8]
0x14002907b  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x140029082  cmp     rcx, r8
0x140029085  jz      loc_140029B9B
0x14002908b  cmp     [rcx-30h], r14d
0x14002908f  lea     rbx, [rcx-30h]
0x140029093  jnz     loc_140029980
0x140029099  mov     eax, 1
0x14002909e  lock xadd [rbx+20h], rax
0x1400290a4  inc     rax
0x1400290a7  cmp     rax, 1
0x1400290ab  jle     loc_140029BE6
0x1400290b1  movzx   ecx, [rsp+110h+var_C0]; NewIrql
0x1400290b6  lock dec dword ptr [r12+8]
0x1400290bc  call    cs:__imp_KeLowerIrql
0x1400290c3  nop     dword ptr [rax+rax+00h]
0x1400290c8  test    rbx, rbx
0x1400290cb  jz      short loc_1400290F4
0x1400290cd  movups  xmm0, xmmword ptr [rbx+4]
0x1400290d1  mov     rax, rsi
0x1400290d4  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Lock], xmm0
0x1400290d8  lock xadd [rbx+20h], rax
0x1400290de  sub     rax, 1
0x1400290e2  jg      short loc_1400290F4
0x1400290e4  test    rax, rax
0x1400290e7  jz      loc_140029AE5
0x1400290ed  mov     ecx, 0Eh
0x1400290f2  int     29h; Win8: RtlFailFast(ecx)
0x1400290f4  mov     ecx, [rdi]
0x1400290f6  lea     rax, [rbp+37h+LockHandle]
0x1400290fa  mov     r9b, 1
0x1400290fd  mov     [rsp+110h+var_F0], rax
0x140029102  movzx   r8d, r9b
0x140029106  lea     rdx, [rdi+4]
0x14002910a  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x140029111  nop     dword ptr [rax+rax+00h]
0x140029116  test    al, al
0x140029118  jz      loc_140029861
0x14002911e  mov     ebx, [rbp+37h+arg_30]
0x140029121  mov     r14d, ebx
0x140029124  mov     r12, [rdi+28h]
0x140029128  shr     r14d, 1Ch
0x14002912c  mov     rax, [r12+0A8h]
0x140029134  test    r14d, r14d
0x140029137  jnz     loc_140029B0D
0x14002913d  mov     r14, [rbp+37h+var_90]
0x140029141  mov     rcx, r14
0x140029144  call    _guard_dispatch_icall
0x140029149  mov     ecx, ebx
0x14002914b  shl     eax, 1Ch
0x14002914e  and     ecx, 0FFFFFFFh
0x140029154  mov     ebx, eax
0x140029156  or      ebx, ecx
0x140029158  mov     eax, ebx
0x14002915a  and     eax, 0F0000000h
0x14002915f  cmp     eax, 0E0000000h
0x140029164  jnz     loc_1400297B0
0x14002916a  test    ebx, 0FFFFFFFh
0x140029170  jnz     loc_140029850
0x140029176  mov     eax, ebx
0x140029178  xor     eax, [rdi]
0x14002917a  and     eax, 0FFFFFFFh
0x14002917f  xor     ebx, eax
0x140029181  mov     r12, [rbp+37h+var_98]
0x140029185  mov     r14, [rbp+37h+var_80]
0x140029189  mov     rcx, r14
0x14002918c  mov     rax, [r12+0B0h]
0x140029194  call    _guard_dispatch_icall
0x140029199  test    eax, eax
0x14002919b  jnz     loc_140029838
0x1400291a1  mov     rdx, [rbp+37h+var_78]
0x1400291a5  test    rdx, rdx
0x1400291a8  jnz     loc_14002992A
0x1400291ae  mov     r14, r13
0x1400291b1  mov     rax, [rdi+28h]
0x1400291b5  mov     rcx, [rbp+37h+var_90]
0x1400291b9  mov     rax, [rax+0B0h]
0x1400291c0  call    _guard_dispatch_icall
0x1400291c5  test    eax, eax
0x1400291c7  jz      loc_140029488
0x1400291cd  mov     rax, [rdi+28h]
0x1400291d1  mov     rcx, [rbp+37h+var_90]
0x1400291d5  mov     rax, [rax+0B0h]
0x1400291dc  call    _guard_dispatch_icall
0x1400291e1  test    eax, eax
0x1400291e3  jz      loc_14002939C
0x1400291e9  mov     rax, [rbp+37h+var_A8]
0x1400291ed  mov     r8d, ebx
0x1400291f0  mov     rcx, r14
0x1400291f3  test    rax, rax
0x1400291f6  jnz     loc_14002934D
0x1400291fc  test    rcx, rcx
0x1400291ff  jnz     loc_140029362
0x140029205  test    rax, rax
0x140029208  jz      short loc_14002920E
0x14002920a  mov     r14, [rax+8]
0x14002920e  mov     rdx, [rbp+37h+var_90]
0x140029212  lea     rcx, [rbp+37h+a]
0x140029216  mov     [rsp+110h+var_E8], rcx
0x14002921b  mov     r9, r14
0x14002921e  mov     rcx, rdi
0x140029221  mov     [rsp+110h+var_F0], rax
0x140029226  call    IppFindOrCreatePath
0x14002922b  mov     r15, [rbp+37h+a]
0x14002922f  mov     r14d, 0C0000225h
0x140029235  cmp     eax, r14d
0x140029238  jz      loc_1400293A4
0x14002923e  mov     r14d, eax
0x140029241  test    eax, eax
0x140029243  js      loc_1400293AA
0x140029249  mov     rcx, r15
0x14002924c  call    IppGetRouteFromPath
0x140029251  mov     r13, rax
0x140029254  test    rax, rax
0x140029257  jz      loc_140029488
0x14002925d  mov     rax, [r15]
0x140029260  xor     edx, edx
0x140029262  mov     [rbp+37h+var_B0], rax
0x140029266  mov     r8, [rax+20h]
0x14002926a  mov     eax, gs:1A4h
0x140029272  div     dword ptr [r8+14h]
0x140029276  mov     eax, 2
0x14002927b  imul    edx, [r8+10h]
0x140029280  mov     ecx, edx
0x140029282  add     rcx, [r8]
0x140029285  lock xadd [rcx], rax
0x14002928a  test    al, 1
0x14002928c  jz      short loc_140029294
0x14002928e  lock add qword ptr [r8+18h], 2
0x140029294  mov     rbx, [rbp+37h+var_68]
0x140029298  test    rbx, rbx
0x14002929b  jz      loc_140029C44
0x1400292a1  lea     rax, Ipv4Global
0x1400292a8  xor     edx, edx; Val
0x1400292aa  mov     rcx, rbx; void *
0x1400292ad  cmp     r12, rax
0x1400292b0  jnz     loc_140029664
0x1400292b6  mov     r8d, 68h ; 'h'; Size
0x1400292bc  call    memset
0x1400292c1  test    r13, r13
0x1400292c4  jz      short loc_1400292F5
0x1400292c6  lea     r8, [rbx+30h]
0x1400292ca  mov     r9, rbx
0x1400292cd  lea     rax, [rbx+54h]
0x1400292d1  mov     rcx, r12
0x1400292d4  mov     [rsp+110h+var_E0], rax
0x1400292d9  lea     rdx, [rbx+4Ch]
0x1400292dd  mov     [rsp+110h+var_E8], rdx
0x1400292e2  mov     rdx, r13
0x1400292e5  mov     [rsp+110h+var_F0], r8
0x1400292ea  xor     r8d, r8d
0x1400292ed  call    IppFillUnicastRouteData
0x1400292f2  mov     r14d, eax
0x1400292f5  mov     r12, [rbp+37h+var_B0]
0x1400292f9  xor     ebx, ebx
0x1400292fb  mov     rax, [r12+8]
0x140029300  mov     rcx, [r12+10h]
0x140029305  mov     [rbp+37h+var_98], rax
0x140029309  mov     rdx, [rax]
0x14002930c  mov     rcx, [rcx]
0x14002930f  mov     [rbp+37h+a], rcx
0x140029313  mov     rax, [rdx+28h]
0x140029317  mov     [rbp+37h+var_78], rax
0x14002931b  mov     rax, [rax+0A8h]
0x140029322  call    _guard_dispatch_icall
0x140029327  movsxd  rdx, eax
0x14002932a  cmp     edx, 0Eh
0x14002932d  jnz     loc_140029728
0x140029333  mov     rdx, [rbp+37h+var_68]
0x140029337  mov     [rdx+5Ch], ebx
0x14002933a  mov     rax, [r12+10h]
0x14002933f  mov     rcx, [rax]
0x140029342  mov     eax, [rcx]
0x140029344  mov     [rdx+60h], eax
0x140029347  mov     rax, [rbp+37h+var_A8]
0x14002934b  jmp     short loc_1400293B1
0x14002934d  cmp     dword ptr [rax+18h], 1
0x140029351  jnz     short loc_14002939C
0x140029353  test    r14, r14
0x140029356  jz      loc_140029921
0x14002935c  cmp     r14, [rax+8]
0x140029360  jnz     short loc_14002939C
0x140029362  mov     edx, ebx
0x140029364  shr     edx, 1Ch
0x140029367  cmp     edx, 1
  ... truncated ...
```
