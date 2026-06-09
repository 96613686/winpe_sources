# TcpMatchReceive

- ea: `0x140030160`
- end: `0x140030fd6`
- name: `TcpMatchReceive`
- size: `3702`
- prototype: `void(unsigned __int64, ...)`
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x1400649c4`

## callees

- `0x14000a8f0`
- `0x14000de40`
- `0x14002f9e0`
- `0x14002fe38`
- `0x140030160`
- `0x140030fdc`
- `0x140031160`
- `0x140031300`
- `0x140031340`
- `0x140063db0`
- `0x1400644d0`
- `0x140095d30`
- `0x140096000`
- `0x1400a2910`
- `0x1400d1120`
- `0x1400d13e8`
- `0x1400e0850`
- `0x1400ed04c`
- `0x1400fba9c`
- `0x1400fc7b8`
- `0x1400fd22c`
- `0x14014e558`
- `0x14015c448`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400308ae`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140030c6d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400308ae`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140030c6d`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140030777`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140030777`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003034d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140030a68`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140030e3d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003034d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140030a68`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140030e3d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140030926`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140030e7d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140030fa3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140030926`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140030e7d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140030fa3`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140030951`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140030ea3`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140030f8f`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140030951`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140030ea3`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140030f8f`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14003029b`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14003057d`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140030d8a`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14003029b`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14003057d`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140030d8a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003024e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003041d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400305cc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400308e7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140030af1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140030ca2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003024e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003041d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400305cc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400308e7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140030af1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140030ca2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140030262`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140030431`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140030609`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140030912`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140030ac4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140030cd3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140030262`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140030431`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140030609`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140030912`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140030ac4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140030cd3`
- `ntoskrnl!KeTestSpinLock` at `0x140030233`
- `ntoskrnl!KeTestSpinLock` at `0x140030402`
- `ntoskrnl!KeTestSpinLock` at `0x140030233`
- `ntoskrnl!KeTestSpinLock` at `0x140030402`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140030f25`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140030f56`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140030f25`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140030f56`
- `NETIO!RtlComputeToeplitzHash` at `0x1400304df`
- `NETIO!RtlComputeToeplitzHash` at `0x140030507`
- `NETIO!RtlComputeToeplitzHash` at `0x14003052f`
- `NETIO!RtlComputeToeplitzHash` at `0x1400307de`
- `NETIO!RtlComputeToeplitzHash` at `0x140030828`
- `NETIO!RtlComputeToeplitzHash` at `0x14003085a`
- `NETIO!RtlComputeToeplitzHash` at `0x140030978`
- `NETIO!RtlComputeToeplitzHash` at `0x14003098b`
- `NETIO!RtlComputeToeplitzHash` at `0x1400309b3`
- `NETIO!RtlComputeToeplitzHash` at `0x140030c42`
- `NETIO!RtlComputeToeplitzHash` at `0x1400304df`
- `NETIO!RtlComputeToeplitzHash` at `0x140030507`
- `NETIO!RtlComputeToeplitzHash` at `0x14003052f`
- `NETIO!RtlComputeToeplitzHash` at `0x1400307de`
- `NETIO!RtlComputeToeplitzHash` at `0x140030828`
- `NETIO!RtlComputeToeplitzHash` at `0x14003085a`
- `NETIO!RtlComputeToeplitzHash` at `0x140030978`
- `NETIO!RtlComputeToeplitzHash` at `0x14003098b`
- `NETIO!RtlComputeToeplitzHash` at `0x1400309b3`
- `NETIO!RtlComputeToeplitzHash` at `0x140030c42`

## pseudocode

```c
void TcpMatchReceive(unsigned __int64 a1, ...)
{
  __int64 v1; // rbx
  unsigned __int8 v2; // dl
  __int64 v4; // rax
  _QWORD *v5; // r15
  ULONG_PTR v6; // r13
  int v7; // ecx
  __int16 v8; // r12
  __int64 v9; // rsi
  PKSPIN_LOCK *v10; // rsi
  PKSPIN_LOCK v11; // rdi
  ULONG_PTR v12; // r12
  struct _RTL_DYNAMIC_HASH_TABLE *v13; // r13
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rdi
  _QWORD *v17; // rdx
  _QWORD *v18; // rcx
  _QWORD *v19; // r8
  bool v20; // al
  __int16 v21; // r12
  __int64 v22; // rsi
  PKSPIN_LOCK v23; // rdi
  __int64 v24; // rdx
  __int64 v25; // r12
  __int64 v26; // rsi
  __int64 v27; // r8
  int v28; // edi
  int v29; // eax
  __int64 v30; // r9
  PRTL_DYNAMIC_HASH_TABLE_ENTRY j; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v32; // rdi
  ULONG_PTR v33; // r13
  __int16 v34; // r12
  PKSPIN_LOCK v35; // rdi
  __int64 v36; // rax
  PKSPIN_LOCK v37; // rdi
  unsigned int v38; // r12d
  __int64 CompartmentUnderLock; // r13
  unsigned __int64 v40; // rdi
  PKSPIN_LOCK v41; // r13
  __int64 v42; // r12
  __int64 v43; // rdi
  __int64 v44; // r15
  __int64 v45; // rsi
  unsigned __int8 v46; // r13
  unsigned __int64 v47; // r12
  __int64 v48; // rax
  unsigned __int64 v49; // rdi
  unsigned __int64 v50; // r13
  __int64 v51; // rdx
  __int64 v52; // r12
  __int64 v53; // rdi
  int v54; // eax
  __int16 v55; // di
  unsigned int v56; // r12d
  __int64 v57; // r9
  int v58; // eax
  __int64 v59; // r9
  int v60; // ebx
  int v61; // eax
  __int64 v62; // rcx
  ULONG_PTR v63; // r12
  ULONG_PTR v64; // rdi
  int *v65; // rdi
  PKSPIN_LOCK v66; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v67; // r12
  __int16 v68; // r12
  PKSPIN_LOCK v69; // rdi
  __int64 v70; // rdi
  int v71; // r9d
  int v72; // eax
  __int64 v73; // rax
  unsigned int v74; // edi
  PKSPIN_LOCK v75; // rdi
  unsigned int v76; // eax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY k; // rax
  __int64 v78; // rcx
  char *v79; // r12
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int16 v83; // [rsp+28h] [rbp-B9h]
  __int64 v84; // [rsp+30h] [rbp-B1h]
  char v85; // [rsp+40h] [rbp-A1h]
  char v86; // [rsp+41h] [rbp-A0h]
  __int16 v87; // [rsp+48h] [rbp-99h] BYREF
  ULONG_PTR Signature; // [rsp+50h] [rbp-91h]
  __int16 v89; // [rsp+58h] [rbp-89h] BYREF
  __int16 v90; // [rsp+60h] [rbp-81h] BYREF
  __int64 v91; // [rsp+68h] [rbp-79h]
  PKSPIN_LOCK *PartitionFromKey; // [rsp+70h] [rbp-71h]
  __int16 v93; // [rsp+78h] [rbp-69h] BYREF
  __int64 v94; // [rsp+80h] [rbp-61h]
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+90h] [rbp-51h] BYREF
  struct _KLOCK_QUEUE_HANDLE v96; // [rsp+A8h] [rbp-39h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+C0h] [rbp-21h] BYREF
  __int64 v98; // [rsp+D8h] [rbp-9h]
  PKSPIN_LOCK v99; // [rsp+E0h] [rbp-1h]
  __int64 v100; // [rsp+E8h] [rbp+7h]
  _QWORD *v101; // [rsp+138h] [rbp+57h] BYREF
  va_list va; // [rsp+138h] [rbp+57h]
  _QWORD *v103; // [rsp+140h] [rbp+5Fh]
  int *v104; // [rsp+148h] [rbp+67h]
  __int64 v105; // [rsp+150h] [rbp+6Fh]
  __int64 v106; // [rsp+158h] [rbp+77h]
  __int64 v107; // [rsp+160h] [rbp+7Fh]
  va_list va1; // [rsp+168h] [rbp+87h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v101 = va_arg(va1, _QWORD *);
  v103 = va_arg(va1, _QWORD *);
  v104 = va_arg(va1, int *);
  v105 = va_arg(va1, _QWORD);
  v106 = va_arg(va1, _QWORD);
  v107 = va_arg(va1, _QWORD);
  v1 = (__int64)v101;
  v2 = 0;
  memset(&Context, 0, sizeof(Context));
  v86 = 0;
  v85 = 0;
  memset(&v96, 0, sizeof(v96));
  v4 = v101[1];
  v5 = v103;
  v6 = v101[11];
  Signature = v6;
  v7 = *(_DWORD *)(v4 + 216);
  if ( (_BYTE)v7 == 1 )
  {
    if ( (v7 & 0x3200) == 0 )
    {
      if ( (v7 & 0xD00) == 0 )
        goto LABEL_2;
      v2 = 1;
      v85 = 1;
    }
    v86 = 1;
    if ( (v107 & 2) != 0 || *(_DWORD *)(a1 + 204) != 1 )
    {
      v90 = v105;
      v89 = v106;
      v24 = v101[4];
      v25 = v101[3];
      v26 = *(_QWORD *)(v24 + 48);
      if ( !v26 )
        LODWORD(v26) = RtlComputeToeplitzHash(
                         TcpToeplitzHashContext,
                         **(_QWORD **)(v24 + 16),
                         *(unsigned __int16 *)(a1 + 72),
                         *(unsigned __int16 *)(a1 + 72));
      v27 = *(unsigned __int16 *)(a1 + 72);
      if ( *(_WORD *)(a1 + 24) == 23 )
      {
        v28 = v26 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, v25, v27, 0);
        v29 = RtlComputeToeplitzHash(TcpToeplitzHashContext, &v89, 2, 32);
        v30 = 34;
      }
      else
      {
        v28 = v26 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, v25, v27, 0);
        v29 = RtlComputeToeplitzHash(TcpToeplitzHashContext, &v89, 2, 8);
        v30 = 10;
      }
      v6 = v28 ^ v29 ^ (unsigned int)RtlComputeToeplitzHash(TcpToeplitzHashContext, &v90, 2, v30) | 0x80000000LL;
      v2 = 0;
      Signature = v6;
      v85 = 0;
      v86 = 0;
    }
  }
LABEL_2:
  v100 = v2;
  v98 = 8LL * v2 + 8;
LABEL_3:
  while ( 2 )
  {
    while ( 2 )
    {
      while ( 2 )
      {
        v8 = PartitionCount;
        if ( (unsigned int)Feature_TCPIP_DPC_EfficientCore__private_IsEnabledDeviceUsageInline()
          && (unsigned __int8)NetioNcmFastCheckIsAoAcCapable()
          && (unsigned __int16)PowerEfficientPartitionIndex < (unsigned __int16)PartitionCount )
        {
          v9 = 3LL * (unsigned __int16)PowerEfficientPartitionIndex;
        }
        else
        {
          v9 = 3 * (v6 % (unsigned __int16)PartitionCount);
        }
        v10 = (PKSPIN_LOCK *)((char *)PartitionTable + 64 * v9);
        PartitionFromKey = v10;
        memset(&LockHandle, 0, sizeof(LockHandle));
        v11 = *v10;
        _InterlockedIncrement((volatile signed __int32 *)*v10 + 2);
        if ( !KeTestSpinLock(v11) )
        {
          _InterlockedDecrement((volatile signed __int32 *)v11 + 2);
          KeAcquireInStackQueuedSpinLockAtDpcLevel(v11, &LockHandle);
          _InterlockedIncrement((volatile signed __int32 *)v11 + 2);
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        }
        if ( v8 != PartitionCount )
        {
          do
          {
            _InterlockedDecrement((volatile signed __int32 *)*v10 + 2);
            v21 = PartitionCount;
            if ( (unsigned int)Feature_TCPIP_DPC_EfficientCore__private_IsEnabledDeviceUsageInline()
              && (unsigned __int8)NetioNcmFastCheckIsAoAcCapable()
              && (unsigned __int16)PowerEfficientPartitionIndex < (unsigned __int16)PartitionCount )
            {
              v22 = 3LL * (unsigned __int16)PowerEfficientPartitionIndex;
            }
            else
            {
              v22 = 3 * (v6 % (unsigned __int16)PartitionCount);
            }
            v10 = (PKSPIN_LOCK *)((char *)PartitionTable + 64 * v22);
            memset(&LockHandle, 0, sizeof(LockHandle));
            v23 = *v10;
            _InterlockedIncrement((volatile signed __int32 *)*v10 + 2);
            if ( !KeTestSpinLock(v23) )
            {
              _InterlockedDecrement((volatile signed __int32 *)v23 + 2);
              KeAcquireInStackQueuedSpinLockAtDpcLevel(v23, &LockHandle);
              _InterlockedIncrement((volatile signed __int32 *)v23 + 2);
              KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
            }
          }
          while ( v21 != PartitionCount );
          PartitionFromKey = v10;
        }
        v12 = Signature;
        v13 = *(struct _RTL_DYNAMIC_HASH_TABLE **)((char *)v10 + v98);
        *(_OWORD *)&Context.ChainHead = 0;
        for ( i = RtlLookupEntryHashTable(v13, Signature, &Context); i; i = RtlGetNextEntryHashTable(v13, &Context) )
        {
          v15 = 48;
          if ( v85 )
            v15 = 72;
          v16 = (unsigned __int64)&i[v15 / 0xFFFFFFFFFFFFFFE8uLL];
          if ( HIWORD(i[v15 / 0xFFFFFFFFFFFFFFE8uLL + 4].Signature) == (_WORD)v106
            && *(_WORD *)(v16 + 116) == (_WORD)v105
            && *(_QWORD *)(v16 + 24) == a1 )
          {
            v17 = *(_QWORD **)(v16 + 32);
            if ( *(_QWORD *)(*v17 + 16LL) == *(_QWORD *)(*(_QWORD *)(v1 + 32) + 16LL) )
            {
              v18 = *(_QWORD **)(v1 + 24);
              v19 = (_QWORD *)v17[2];
              if ( *(_WORD *)(a1 + 24) == 23 )
                v20 = v19[1] == v18[1] && *v19 == *v18;
              else
                v20 = *(_DWORD *)v19 == *(_DWORD *)v18;
              if ( v20 )
              {
                if ( _InterlockedIncrement64((volatile signed __int64 *)(v16 + 8)) <= 1 )
                  __fastfail(0xEu);
                _InterlockedDecrement((volatile signed __int32 *)*v10 + 2);
                KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v16);
                if ( (*(_DWORD *)(v16 + 120) & 2) != 0 )
                {
                  TcpTcbReceive(a1, v16, (_QWORD **)va, v5, v104, 0);
                  v1 = (__int64)v101;
                  if ( v101 == v5 )
                    return;
                  v6 = v12;
                }
                else
                {
                  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v16);
                  TcpDereferenceTcb(v16);
                  v6 = v12;
                }
                goto LABEL_3;
              }
            }
          }
        }
        if ( !v13[3].NumEntries )
        {
LABEL_41:
          *(_OWORD *)&Context.ChainHead = 0;
          for ( j = RtlLookupEntryHashTable(v13 + 1, v12, &Context); ; j = RtlGetNextEntryHashTable(v13 + 1, &Context) )
          {
            v32 = j;
            if ( !j )
              goto LABEL_43;
            v67 = j;
            if ( v85 )
              v67 = j - 1;
            if ( LOWORD(v67[3].Linkage.Blink) == (_WORD)v106
              && HIWORD(v67[3].Linkage.Flink) == (_WORD)v105
              && v67[2].Linkage.Flink == (struct _LIST_ENTRY *)a1
              && *(_QWORD *)(v67[3].Signature + 16) == *(_QWORD *)(*(_QWORD *)(v1 + 32) + 16LL)
              && (unsigned __int8)INET_ADDR_EQUAL(*(unsigned __int16 *)(a1 + 24), &v67[4], *(_QWORD *)(v1 + 24)) )
            {
              break;
            }
          }
          if ( _InterlockedIncrement64((volatile signed __int64 *)&v67[2].Signature) <= 1 )
            __fastfail(0xEu);
          _InterlockedDecrement((volatile signed __int32 *)*v10 + 2);
          KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&v67[2].Linkage.Blink);
          if ( !BYTE1(v67[3].Linkage.Flink) )
          {
            KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&v67[2].Linkage.Blink);
            TcpDereferenceTimeWaitTcb(v67);
            v6 = Signature;
            continue;
          }
          if ( !(unsigned __int8)TcpTimeWaitTcbReceive(a1, v67, (_QWORD **)va, v5) )
            goto LABEL_101;
          v1 = (__int64)v101;
          if ( v32 )
          {
            if ( (v107 & 2) == 0 )
              goto LABEL_109;
          }
          else
          {
LABEL_43:
            _InterlockedDecrement((volatile signed __int32 *)*v10 + 2);
            if ( (v107 & 2) == 0 )
            {
LABEL_109:
              v63 = Signature;
              goto LABEL_110;
            }
            v33 = Signature;
            v34 = PartitionCount;
            PartitionFromKey = (PKSPIN_LOCK *)TcpGetPartitionFromKey(Signature);
            v10 = PartitionFromKey;
            v35 = *PartitionFromKey;
            KeAcquireInStackQueuedSpinLockAtDpcLevel(*PartitionFromKey, &v96);
            while ( *((_DWORD *)v35 + 2) )
              ;
            if ( v34 != PartitionCount )
            {
              do
              {
                KeReleaseInStackQueuedSpinLockFromDpcLevel(&v96);
                v68 = PartitionCount;
                PartitionFromKey = (PKSPIN_LOCK *)TcpGetPartitionFromKey(v33);
                v10 = PartitionFromKey;
                v69 = *PartitionFromKey;
                KeAcquireInStackQueuedSpinLockAtDpcLevel(*PartitionFromKey, &v96);
                while ( *((_DWORD *)v69 + 2) )
                  ;
              }
              while ( v68 != PartitionCount );
            }
            if ( *((_DWORD *)v10 + 36) == 4096 )
              *((_DWORD *)v10 + 36) = *v104;
            KeReleaseInStackQueuedSpinLockFromDpcLevel(&v96);
          }
          v36 = *(_QWORD *)(v1 + 32);
          v37 = TcpCompartmentSet;
          LOBYTE(v87) = 0;
          LODWORD(v91) = 0;
          v38 = ***(_DWORD ***)(v36 + 8);
          if ( v38 == 1 )
          {
            CompartmentUnderLock = TcpCompartmentSet[41];
          }
          else
          {
            RtlAcquireScalableReadLock(TcpCompartmentSet);
            CompartmentUnderLock = InetGetCompartmentUnderLock(v37, v38, 0);
            RtlReleaseScalableReadLock(v37, (unsigned int)v91, (unsigned __int8)v87);
          }
          v91 = *(_QWORD *)(v1 + 32);
          v40 = (unsigned __int16)__ROR2__(v105, 8);
          v94 = **(_QWORD **)(CompartmentUnderLock + 32);
          v99 = *(PKSPIN_LOCK *)(v94 + 8 * (v40 >> 8) + 224);
          v41 = v99;
          RtlAcquireReadLockAtDpcLevel(v99);
          if ( !*((_WORD *)v41 + 8) )
          {
            _InterlockedDecrement((volatile signed __int32 *)v41 + 2);
            goto LABEL_124;
          }
          v42 = v41[3] + 32LL * (unsigned __int8)v40;
          if ( !*(_QWORD *)(v42 + 16)
            || (*(_DWORD *)v42 & 2) == 0
            || !*(_QWORD *)(v42 + 24)
            || ((v80 = LookupEndpointFromPerProcEndpointTable(
                         v41[3] + 32LL * (unsigned __int8)v40,
                         *(unsigned __int16 *)(a1 + 24),
                         *(_QWORD *)(v91 + 16),
                         0),
                 (v43 = v80) == 0)
             || !(unsigned __int8)ReferenceEndpointInAssignmentIfMatched(v94, v80, a1, v91, 2))
            && ((v81 = LookupEndpointFromPerProcEndpointTable(v42, *(unsigned __int16 *)(a1 + 24), 0, 0),
                 (v43 = v81) == 0)
             || !(unsigned __int8)ReferenceEndpointInAssignmentIfMatched(v94, v81, a1, v91, 2))
            && ((v82 = LookupEndpointFromPerProcEndpointTable(v42, 0, 0, 0), (v43 = v82) == 0)
             || !(unsigned __int8)ReferenceEndpointInAssignmentIfMatched(v94, v82, a1, v91, 2)) )
          {
            v43 = *(_QWORD *)(v42 + 16);
            if ( v43 )
            {
              v44 = v94;
              v45 = v91;
              while ( 1 )
              {
                v87 = 0;
                v46 = v43 & 3;
                if ( (v43 & 3) != 0 )
                {
                  v47 = v43 & 0xFFFFFFFFFFFFFFFCuLL;
                  v48 = (*(__int64 (__fastcall **)(unsigned __int64, _QWORD, __int16 *))(v44 + 112))(
                          v43 & 0xFFFFFFFFFFFFFFFCuLL,
                          v46,
                          &v87);
                  if ( v48 != -1
                    && (!v87 || v87 == *(_WORD *)(a1 + 24))
                    && (!v48 || v48 == *(_QWORD *)(v45 + 16))
                    && v46 == 2
                    && (*(_DWORD *)(v47 + 16) & 2) == 0
                    && (*(unsigned __int8 (__fastcall **)(unsigned __int64, __int64, unsigned __int64, __int64, _QWORD))(v44 + 128))(
                         v43 & 0xFFFFFFFFFFFFFFFCuLL,
                         2,
                         a1,
                         v45,
                         0) )
                  {
LABEL_66:
                    v5 = v103;
                    v10 = PartitionFromKey;
                    v41 = v99;
                    break;
                  }
                }
                else
                {
                  v47 = v43 & 0xFFFFFFFFFFFFFFFCuLL;
                }
                v43 = *(_QWORD *)v47;
                if ( !*(_QWORD *)v47 )
                  goto LABEL_66;
              }
            }
          }
          _InterlockedDecrement((volatile signed __int32 *)v41 + 2);
          v49 = v43 & 0xFFFFFFFFFFFFFFFCuLL;
          if ( !v49 )
            goto LABEL_124;
          v50 = v49 - 128;
          if ( ExAcquireRundownProtection((PEX_RUNDOWN_REF)(v49 - 128)) )
          {
            if ( v49 == 128 )
            {
LABEL_124:
              v63 = Signature;
              v65 = v104;
              goto LABEL_125;
            }
            RtlAcquireReadLockAtDpcLevel((PKSPIN_LOCK)(v50 + 8));
            if ( (*(_BYTE *)(v50 + 32) & 5) == 5 )
            {
              v51 = *(_QWORD *)(v1 + 32);
              if ( v85 )
              {
                v64 = Signature;
                LOBYTE(v83) = 1;
                v63 = (unsigned int)TcpComputeHashKey(a1, v51, *(_QWORD *)(v1 + 24), (unsigned __int16)v106, v105, v83);
              }
              else
              {
                v52 = *(_QWORD *)(v51 + 48);
                v53 = *(_QWORD *)(v1 + 24);
                if ( !v52 )
                  LODWORD(v52) = RtlComputeToeplitzHash(
                                   TcpToeplitzHashContext,
                                   **(_QWORD **)(v51 + 16),
                                   *(unsigned __int16 *)(a1 + 72),
                                   *(unsigned __int16 *)(a1 + 72));
                v54 = RtlComputeToeplitzHash(TcpToeplitzHashContext, v53, *(unsigned __int16 *)(a1 + 72), 0);
                v55 = *(_WORD *)(a1 + 24);
                v56 = v54 ^ v52;
                v57 = 32;
                v93 = v105;
                v87 = v106;
                if ( v55 != 23 )
                  v57 = 8;
                v58 = RtlComputeToeplitzHash(TcpToeplitzHashContext, &v87, 2, v57);
                v59 = 34;
                v60 = v58;
                if ( v55 != 23 )
                  v59 = 10;
                v61 = RtlComputeToeplitzHash(TcpToeplitzHashContext, &v93, 2, v59);
                v62 = v56;
                v63 = Signature;
                v64 = v62 ^ (v60 ^ v61) & 0x7FFFFFC0 | 0x80000000LL;
              }
              v84 = v64;
              v65 = v104;
              TcpListenerReceive(a1, (struct _EX_RUNDOWN_REF *)v50, (__int64 *)va, v5, v104, v63, v84);
              ExReleaseRundownProtection((PEX_RUNDOWN_REF)v50);
              TcpDereferenceListener(v50);
              v1 = (__int64)v101;
              if ( v101 == v5 )
              {
                if ( *v65 == *((_DWORD *)v10 + 36) )
                {
                  v66 = *v10;
                  KeAcquireInStackQueuedSpinLockAtDpcLevel(*v10, &v96);
                  while ( *((_DWORD *)v66 + 2) )
                    ;
                  if ( *v65 == *((_DWORD *)v10 + 36) )
                    *((_DWORD *)v10 + 36) = 4096;
                  KeReleaseInStackQueuedSpinLockFromDpcLevel(&v96);
                }
                return;
              }
LABEL_125:
              if ( *v65 == *((_DWORD *)v10 + 36) )
              {
                v75 = *v10;
                KeAcquireInStackQueuedSpinLockAtDpcLevel(*v10, &v96);
                while ( *((_DWORD *)v75 + 2) )
                  ;
                if ( *v104 == *((_DWORD *)v10 + 36) )
                  *((_DWORD *)v10 + 36) = 4096;
                KeReleaseInStackQueuedSpinLockFromDpcLevel(&v96);
              }
LABEL_110:
              if ( v86 )
              {
                if ( *(_DWORD *)(a1 + 204) == 1 )
                {
                  LOBYTE(v83) = v100 ^ 1;
                  v76 = TcpComputeHashKey(
                          a1,
                          *(_QWORD *)(v1 + 32),
                          *(_QWORD *)(v1 + 24),
                          (unsigned __int16)v106,
                          v105,
                          v83);
                  if ( v76 != v63 )
                  {
                    v6 = v76;
                    Signature = v76;
                    *(_DWORD *)(a1 + 204) = 0;
                    continue;
                  }
                }
              }
              for ( ; (_QWORD *)v1 != v5; v1 = *(_QWORD *)v1 )
              {
                v70 = *(_QWORD *)(v1 + 80);
                *(_DWORD *)(*(_QWORD *)(v1 + 8) + 140LL) = 1073741862;
                TcpLogPacketDiscard(a1, v1, 4, 3758114048LL);
                v72 = InetInspectRespondDatagram(
                        0,
                        0,
                        *(unsigned __int16 *)(a1 + 24),
                        v71,
                        *(_WORD *)(v70 + 2),
                        *(_WORD *)v70,
                        v1,
                        4 * (*(unsigned __int8 *)(v70 + 12) >> 4));
                if ( (*(_BYTE *)(v70 + 13) & 4) == 0 && v72 == 1 )
                  TcpResetSend(
                    0,
                    v70,
                    a1,
                    *(_QWORD *)(v1 + 32),
                    *(_QWORD *)(v1 + 24),
                    *(_DWORD *)(v1 + 20),
                    *(_BYTE *)(v1 + 16) & 1,
                    0);
                if ( (*(_BYTE *)(v1 + 16) & 8) == 0 )
                {
                  v73 = *(_QWORD *)(v1 + 80);
                  if ( v73 )
                  {
                    v74 = 4 * (*(unsigned __int8 *)(v73 + 12) >> 4);
                    NetioRetreatNetBuffer(*(_QWORD *)(*(_QWORD *)(v1 + 8) + 8LL), v74, 0);
                    *(_DWORD *)(v1 + 48) -= v74;
                  }
                }
              }
              return;
            }
            _InterlockedDecrement((volatile signed __int32 *)(v50 + 16));
            ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v49 - 128));
          }
          TcpDereferenceListener(v49 - 128);
          goto LABEL_124;
        }
        break;
      }
      *(_OWORD *)&Context.ChainHead = 0;
      for ( k = RtlLookupEntryHashTable(v13 + 3, v12, &Context); ; k = RtlGetNextEntryHashTable(v13 + 3, &Context) )
      {
        if ( !k )
        {
          v12 = Signature;
          goto LABEL_41;
        }
        v78 = 16;
        if ( v85 )
          v78 = 40;
        v79 = (char *)k - v78;
        if ( *(_WORD *)((char *)&k[5].Linkage.Blink - v78 + 6) == (_WORD)v106
          && *((_WORD *)v79 + 66) == (_WORD)v105
          && *((_QWORD *)v79 + 9) == a1
          && *(_QWORD *)(*((_QWORD *)v79 + 10) + 16LL) == *(_QWORD *)(*(_QWORD *)(v1 + 32) + 16LL)
          && (unsigned __int8)INET_ADDR_EQUAL(*(unsigned __int16 *)(a1 + 24), v79 + 112, *(_QWORD *)(v1 + 24)) )
        {
          break;
        }
      }
      if ( _InterlockedIncrement64((volatile signed __int64 *)v79 + 1) <= 1 )
        __fastfail(0xEu);
      _InterlockedDecrement((volatile signed __int32 *)*v10 + 2);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v79);
      if ( (v79[138] & 1) == 0 )
      {
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v79);
        TcpDereferenceSynTcb(v79);
        v6 = Signature;
        continue;
      }
      break;
    }
    TcpSynTcbReceive(a1, v79, (_QWORD **)va, v5, v104);
LABEL_101:
    v1 = (__int64)v101;
    if ( v101 != v5 )
    {
      v6 = Signature;
      continue;
    }
    break;
  }
}

```

## disassembly

```asm
0x140030160  mov     [rsp-8+arg_0], rbx
0x140030165  mov     [rsp-8+arg_18], r9
0x14003016a  mov     [rsp-8+arg_10], r8
0x14003016f  mov     [rsp-8+arg_8], rdx
0x140030174  push    rbp
0x140030175  push    rsi
0x140030176  push    rdi
0x140030177  push    r12
0x140030179  push    r13
0x14003017b  push    r14
0x14003017d  push    r15
0x14003017f  lea     rbp, [rsp-0Fh]
0x140030184  sub     rsp, 0F0h
0x14003018b  xor     eax, eax
0x14003018d  mov     rbx, rdx
0x140030190  mov     [rbp+3Fh+Context.Signature], rax
0x140030194  xor     dl, dl
0x140030196  mov     qword ptr [rbp+3Fh+var_78.OldIrql], rax
0x14003019a  xorps   xmm0, xmm0
0x14003019d  movups  xmmword ptr [rbp+3Fh+Context.ChainHead], xmm0
0x1400301a1  mov     [rsp+120h+var_DF], al
0x1400301a5  mov     r14, rcx
0x1400301a8  xorps   xmm1, xmm1
0x1400301ab  mov     [rsp+120h+var_E0], dl
0x1400301af  movups  xmmword ptr [rbp+3Fh+var_78.LockQueue.Next], xmm1
0x1400301b3  mov     rax, [rbx+8]
0x1400301b7  mov     r15, r8
0x1400301ba  mov     r13, [rbx+58h]
0x1400301be  mov     [rsp+120h+Signature], r13
0x1400301c3  mov     ecx, [rax+0D8h]
0x1400301c9  cmp     cl, 1
0x1400301cc  jz      loc_140030475
0x1400301d2  movzx   eax, dl
0x1400301d5  mov     [rbp+3Fh+var_38], rax
0x1400301d9  lea     rax, ds:8[rax*8]
0x1400301e1  mov     [rbp+3Fh+var_48], rax
0x1400301e5  movzx   r12d, cs:PartitionCount
0x1400301ed  call    Feature_TCPIP_DPC_EfficientCore__private_IsEnabledDeviceUsageInline
0x1400301f2  test    eax, eax
0x1400301f4  jnz     loc_140030F25
0x1400301fa  movzx   ecx, cs:PartitionCount
0x140030201  mov     rax, r13
0x140030204  xor     edx, edx
0x140030206  div     rcx
0x140030209  lea     rsi, [rdx+rdx*2]
0x14003020d  shl     rsi, 6
0x140030211  xorps   xmm0, xmm0
0x140030214  add     rsi, cs:PartitionTable
0x14003021b  xor     eax, eax
0x14003021d  mov     [rbp+3Fh+var_B0], rsi
0x140030221  movups  xmmword ptr [rbp+3Fh+LockHandle.LockQueue.Next], xmm0
0x140030225  mov     qword ptr [rbp+3Fh+LockHandle.OldIrql], rax
0x140030229  mov     rdi, [rsi]
0x14003022c  lock inc dword ptr [rdi+8]
0x140030230  mov     rcx, rdi; SpinLock
0x140030233  call    cs:__imp_KeTestSpinLock
0x14003023a  nop     dword ptr [rax+rax+00h]
0x14003023f  test    al, al
0x140030241  jnz     short loc_14003026E
0x140030243  lock dec dword ptr [rdi+8]
0x140030247  lea     rdx, [rbp+3Fh+LockHandle]; LockHandle
0x14003024b  mov     rcx, rdi; SpinLock
0x14003024e  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140030255  nop     dword ptr [rax+rax+00h]
0x14003025a  lock inc dword ptr [rdi+8]
0x14003025e  lea     rcx, [rbp+3Fh+LockHandle]; LockHandle
0x140030262  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140030269  nop     dword ptr [rax+rax+00h]
0x14003026e  cmp     r12w, cs:PartitionCount
0x140030276  jnz     loc_1400303B1
0x14003027c  mov     rax, [rbp+3Fh+var_48]
0x140030280  lea     r8, [rbp+3Fh+Context]; Context
0x140030284  mov     r12, [rsp+120h+Signature]
0x140030289  xorps   xmm0, xmm0
0x14003028c  mov     rdx, r12; Signature
0x14003028f  mov     r13, [rsi+rax]
0x140030293  mov     rcx, r13; HashTable
0x140030296  movdqu  xmmword ptr [rbp+3Fh+Context.ChainHead], xmm0
0x14003029b  call    cs:__imp_RtlLookupEntryHashTable
0x1400302a2  nop     dword ptr [rax+rax+00h]
0x1400302a7  mov     rdi, rax
0x1400302aa  test    rax, rax
0x1400302ad  jz      loc_14003055C
0x1400302b3  cmp     [rsp+120h+var_E0], 0
0x1400302b8  mov     eax, 48h ; 'H'
0x1400302bd  mov     ecx, 30h ; '0'
0x1400302c2  cmovnz  ecx, eax
0x1400302c5  movzx   eax, word ptr [rbp+3Fh+arg_28]
0x1400302c9  sub     rdi, rcx
0x1400302cc  cmp     [rdi+76h], ax
0x1400302d0  jnz     loc_14003094A
0x1400302d6  movzx   eax, word ptr [rbp+3Fh+arg_20]
0x1400302da  cmp     [rdi+74h], ax
0x1400302de  jnz     loc_14003094A
0x1400302e4  cmp     [rdi+18h], r14
0x1400302e8  jnz     loc_14003094A
0x1400302ee  mov     rdx, [rdi+20h]
0x1400302f2  mov     rax, [rbx+20h]
0x1400302f6  mov     rcx, [rdx]
0x1400302f9  mov     rax, [rax+10h]
0x1400302fd  cmp     [rcx+10h], rax
0x140030301  jnz     loc_14003094A
0x140030307  cmp     word ptr [r14+18h], 17h
0x14003030d  mov     rcx, [rbx+18h]
0x140030311  mov     r8, [rdx+10h]
0x140030315  jz      loc_140030454
0x14003031b  mov     eax, [rcx]
0x14003031d  cmp     [r8], eax
0x140030320  setz    al
0x140030323  test    al, al
0x140030325  jz      loc_14003094A
0x14003032b  mov     eax, 1
0x140030330  lock xadd [rdi+8], rax
0x140030336  inc     rax
0x140030339  cmp     rax, 1
0x14003033d  jle     loc_1400309CA
0x140030343  mov     rax, [rsi]
0x140030346  mov     rcx, rdi; SpinLock
0x140030349  lock dec dword ptr [rax+8]
0x14003034d  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140030354  nop     dword ptr [rax+rax+00h]
0x140030359  mov     eax, [rdi+78h]
0x14003035c  test    al, 2
0x14003035e  jz      loc_140030923
0x140030364  mov     rax, [rbp+3Fh+arg_18]
0x140030368  lea     r8, [rbp+3Fh+arg_8]
0x14003036c  mov     [rsp+120h+var_F8], 0
0x140030375  mov     r9, r15
0x140030378  mov     rdx, rdi
0x14003037b  mov     [rsp+120h+var_100], rax
0x140030380  mov     rcx, r14
0x140030383  call    TcpTcbReceive
0x140030388  mov     rbx, [rbp+3Fh+arg_8]
0x14003038c  cmp     rbx, r15
0x14003038f  jnz     loc_140030942
0x140030395  mov     rbx, [rsp+120h+arg_0]
0x14003039d  add     rsp, 0F0h
0x1400303a4  pop     r15
0x1400303a6  pop     r14
0x1400303a8  pop     r13
0x1400303aa  pop     r12
0x1400303ac  pop     rdi
0x1400303ad  pop     rsi
0x1400303ae  pop     rbp
0x1400303af  retn
0x1400303b1  mov     rax, [rsi]
0x1400303b4  lock dec dword ptr [rax+8]
0x1400303b8  movzx   r12d, cs:PartitionCount
0x1400303c0  call    Feature_TCPIP_DPC_EfficientCore__private_IsEnabledDeviceUsageInline
0x1400303c5  test    eax, eax
0x1400303c7  jnz     loc_140030F56
0x1400303cd  movzx   ecx, cs:PartitionCount
0x1400303d4  mov     rax, r13
0x1400303d7  xor     edx, edx
0x1400303d9  div     rcx
0x1400303dc  lea     rsi, [rdx+rdx*2]
0x1400303e0  shl     rsi, 6
0x1400303e4  xorps   xmm0, xmm0
0x1400303e7  add     rsi, cs:PartitionTable
0x1400303ee  xor     eax, eax
0x1400303f0  movups  xmmword ptr [rbp+3Fh+LockHandle.LockQueue.Next], xmm0
0x1400303f4  mov     qword ptr [rbp+3Fh+LockHandle.OldIrql], rax
0x1400303f8  mov     rdi, [rsi]
0x1400303fb  lock inc dword ptr [rdi+8]
0x1400303ff  mov     rcx, rdi; SpinLock
0x140030402  call    cs:__imp_KeTestSpinLock
0x140030409  nop     dword ptr [rax+rax+00h]
0x14003040e  test    al, al
0x140030410  jnz     short loc_14003043D
0x140030412  lock dec dword ptr [rdi+8]
0x140030416  lea     rdx, [rbp+3Fh+LockHandle]; LockHandle
0x14003041a  mov     rcx, rdi; SpinLock
0x14003041d  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140030424  nop     dword ptr [rax+rax+00h]
0x140030429  lock inc dword ptr [rdi+8]
0x14003042d  lea     rcx, [rbp+3Fh+LockHandle]; LockHandle
0x140030431  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140030438  nop     dword ptr [rax+rax+00h]
0x14003043d  cmp     r12w, cs:PartitionCount
0x140030445  jnz     loc_1400303B1
0x14003044b  mov     [rbp+3Fh+var_B0], rsi
0x14003044f  jmp     loc_14003027C
0x140030454  mov     rax, [rcx+8]
0x140030458  cmp     [r8+8], rax
0x14003045c  jnz     loc_140030D44
0x140030462  mov     rax, [rcx]
0x140030465  cmp     [r8], rax
0x140030468  jnz     loc_140030D44
0x14003046e  mov     al, 1
0x140030470  jmp     loc_140030323
0x140030475  test    ecx, 3200h
0x14003047b  jz      loc_140030F0E
0x140030481  test    byte ptr [rbp+3Fh+arg_30], 2
0x140030485  mov     [rsp+120h+var_DF], 1
0x14003048a  jnz     short loc_14003049A
0x14003048c  cmp     dword ptr [r14+0CCh], 1
0x140030494  jz      loc_1400301D2
0x14003049a  movzx   eax, word ptr [rbp+3Fh+arg_20]
0x14003049e  mov     [rsp+120h+var_C0], ax
0x1400304a3  movzx   eax, word ptr [rbp+3Fh+arg_28]
0x1400304a7  mov     [rsp+120h+var_C8], ax
0x1400304ac  mov     rdx, [rbx+20h]
0x1400304b0  mov     r12, [rbx+18h]
0x1400304b4  mov     rsi, [rdx+30h]
0x1400304b8  test    rsi, rsi
0x1400304bb  jz      loc_140030962
0x1400304c1  movzx   r8d, word ptr [r14+48h]
0x1400304c6  lea     rcx, TcpToeplitzHashContext
0x1400304cd  xor     r9d, r9d
0x1400304d0  mov     rdx, r12
0x1400304d3  cmp     word ptr [r14+18h], 17h
0x1400304d9  jz      loc_14003098B
0x1400304df  call    cs:__imp_RtlComputeToeplitzHash
0x1400304e6  nop     dword ptr [rax+rax+00h]
0x1400304eb  mov     r9d, 8
0x1400304f1  lea     rdx, [rsp+120h+var_C8]
0x1400304f6  mov     edi, eax
0x1400304f8  lea     rcx, TcpToeplitzHashContext
0x1400304ff  xor     edi, esi
0x140030501  mov     r8d, 2
0x140030507  call    cs:__imp_RtlComputeToeplitzHash
0x14003050e  nop     dword ptr [rax+rax+00h]
0x140030513  mov     r9d, 0Ah
0x140030519  mov     esi, eax
0x14003051b  lea     rdx, [rsp+120h+var_C0]
0x140030520  mov     r8d, 2
0x140030526  lea     rcx, TcpToeplitzHashContext
0x14003052d  xor     esi, edi
0x14003052f  call    cs:__imp_RtlComputeToeplitzHash
0x140030536  nop     dword ptr [rax+rax+00h]
0x14003053b  xor     eax, esi
0x14003053d  mov     r13d, eax
0x140030540  mov     eax, 80000000h
0x140030545  or      r13, rax
0x140030548  xor     dl, dl
0x14003054a  mov     [rsp+120h+Signature], r13
0x14003054f  mov     [rsp+120h+var_E0], dl
0x140030553  mov     [rsp+120h+var_DF], dl
0x140030557  jmp     loc_1400301D2
0x14003055c  cmp     dword ptr [r13+8Ch], 0
0x140030564  jnz     loc_140030D77
0x14003056a  xorps   xmm0, xmm0
0x14003056d  lea     r8, [rbp+3Fh+Context]; Context
0x140030571  mov     rdx, r12; Signature
0x140030574  lea     rcx, [r13+28h]; HashTable
0x140030578  movdqu  xmmword ptr [rbp+3Fh+Context.ChainHead], xmm0
0x14003057d  call    cs:__imp_RtlLookupEntryHashTable
0x140030584  nop     dword ptr [rax+rax+00h]
0x140030589  mov     rdi, rax
0x14003058c  test    rax, rax
0x14003058f  jnz     loc_1400309D6
0x140030595  mov     rax, [rsi]
0x140030598  lock dec dword ptr [rax+8]
0x14003059c  test    byte ptr [rbp+3Fh+arg_30], 2
0x1400305a0  jz      loc_140030B2A
0x1400305a6  mov     r13, [rsp+120h+Signature]
0x1400305ab  movzx   r12d, cs:PartitionCount
0x1400305b3  mov     rcx, r13
0x1400305b6  call    TcpGetPartitionFromKey
0x1400305bb  lea     rdx, [rbp+3Fh+var_78]; LockHandle
0x1400305bf  mov     [rbp+3Fh+var_B0], rax
0x1400305c3  mov     rsi, rax
0x1400305c6  mov     rdi, [rax]
0x1400305c9  mov     rcx, rdi; SpinLock
0x1400305cc  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400305d3  nop     dword ptr [rax+rax+00h]
0x1400305d8  mov     ecx, [rdi+8]
0x1400305db  test    ecx, ecx
0x1400305dd  jnz     short loc_1400305D8
0x1400305df  cmp     r12w, cs:PartitionCount
0x1400305e7  jnz     loc_140030AC0
0x1400305ed  cmp     dword ptr [rsi+90h], 1000h
0x1400305f7  jnz     short loc_140030605
0x1400305f9  mov     rax, [rbp+3Fh+arg_18]
0x1400305fd  mov     eax, [rax]
0x1400305ff  mov     [rsi+90h], eax
0x140030605  lea     rcx, [rbp+3Fh+var_78]; LockHandle
0x140030609  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140030610  nop     dword ptr [rax+rax+00h]
0x140030615  mov     rax, [rbx+20h]
0x140030619  mov     rdi, cs:TcpCompartmentSet
0x140030620  mov     byte ptr [rsp+120h+var_D8], 0
0x140030625  mov     dword ptr [rbp+3Fh+var_B8], 0
0x14003062c  mov     rcx, [rax+8]
0x140030630  mov     rax, [rcx]
0x140030633  mov     r12d, [rax]
0x140030636  cmp     r12d, 1
0x14003063a  jnz     loc_140030EB4
0x140030640  mov     r13, [rdi+148h]
0x140030647  mov     rax, [rbx+20h]
0x14003064b  mov     [rbp+3Fh+var_B8], rax
0x14003064f  mov     rax, [r13+20h]
0x140030653  mov     rcx, [rax]
0x140030656  movzx   eax, word ptr [rbp+3Fh+arg_20]
0x14003065a  ror     ax, 8
0x14003065e  movzx   edi, ax
0x140030661  mov     [rbp+3Fh+var_A0], rcx
0x140030665  mov     eax, edi
0x140030667  shr     rax, 8
0x14003066b  mov     r13, [rcx+rax*8+0E0h]
  ... truncated ...
```
