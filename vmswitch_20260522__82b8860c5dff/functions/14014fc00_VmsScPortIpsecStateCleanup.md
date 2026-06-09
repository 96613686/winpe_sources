# VmsScPortIpsecStateCleanup

- ea: `0x14014fc00`
- end: `0x1401500e0`
- name: `VmsScPortIpsecStateCleanup`
- size: `1248`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140087f10`

## callees

- `0x14001484c`
- `0x140014988`
- `0x140027a64`
- `0x14003c378`
- `0x14006b084`
- `0x140070100`
- `0x1400845f8`
- `0x14008497c`
- `0x1400f2f38`
- `0x14013f174`
- `0x14014f490`
- `0x14014fc00`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14014fd7e`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14014fd7e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014fdbe`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014fe0b`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014fe5b`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014fdbe`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014fe0b`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014fe5b`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14014fce4`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14014fce4`
- `NDIS!NdisReleaseReadWriteLock` at `0x14014ff0a`
- `NDIS!NdisReleaseReadWriteLock` at `0x14014ff0a`
- `NDIS!NdisAcquireReadWriteLock` at `0x14014fcc9`
- `NDIS!NdisAcquireReadWriteLock` at `0x14014fcc9`
- `NDIS!NdisReleaseRWLock` at `0x14014ff92`
- `NDIS!NdisReleaseRWLock` at `0x14014ffa6`
- `NDIS!NdisReleaseRWLock` at `0x1401500a6`
- `NDIS!NdisReleaseRWLock` at `0x1401500bf`
- `NDIS!NdisReleaseRWLock` at `0x14014ff92`
- `NDIS!NdisReleaseRWLock` at `0x14014ffa6`
- `NDIS!NdisReleaseRWLock` at `0x1401500a6`
- `NDIS!NdisReleaseRWLock` at `0x1401500bf`

## string_xrefs

- `0x14014feca`: `cacheDelListIterator == &cacheDelListHead`

## pseudocode

```c
void __fastcall VmsScPortIpsecStateCleanup(__int64 a1)
{
  unsigned __int8 v1; // r15
  unsigned __int8 v2; // r12
  char v3; // r13
  __int64 v5; // r8
  __int64 v6; // rsi
  PRTL_DYNAMIC_HASH_TABLE_ENTRY NextEntryHashTable; // rbx
  int v8; // edx
  __int64 v9; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *Flink; // r14
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v11; // rbx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rdx
  char v18; // r14
  __int64 v19; // rax
  __int64 v20; // rcx
  _QWORD *v21; // r15
  ULONG_PTR Signature; // [rsp+40h] [rbp-39h] BYREF
  __int64 v23; // [rsp+48h] [rbp-31h]
  __int128 v24; // [rsp+50h] [rbp-29h] BYREF
  __int128 v25; // [rsp+60h] [rbp-19h] BYREF
  __int64 v26; // [rsp+70h] [rbp-9h]
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+78h] [rbp-1h] BYREF
  char v28; // [rsp+E0h] [rbp+67h]
  struct _LOCK_STATE_EX v29; // [rsp+E8h] [rbp+6Fh] BYREF
  struct _LOCK_STATE_EX v30; // [rsp+F0h] [rbp+77h] BYREF
  struct _LOCK_STATE LockState; // [rsp+F8h] [rbp+7Fh] BYREF

  v1 = 0;
  LockState = 0;
  memset(&Context, 0, sizeof(Context));
  v26 = 0;
  v2 = 0;
  v25 = 0;
  *(_WORD *)&v29.OldIrql = 0;
  v3 = 0;
  v24 = 0;
  v29.Flags = 0;
  v28 = 0;
  *(_WORD *)&v30.OldIrql = 0;
  v30.Flags = 0;
  VmsOmAssertIoctlMutexIsHeld();
  Signature = 0;
  VmsScpIpsecGenericUpdateHash(a1, 8, &Signature);
  *((_QWORD *)&v24 + 1) = &v24;
  *(_QWORD *)&v24 = &v24;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 1240) + 4264LL);
  v23 = v6;
  if ( v6 )
  {
    VmsOmObjectLockExclusive(v6, &v30, 0);
    v3 = 1;
    v28 = 1;
  }
  LOBYTE(v5) = v3;
  VmsOmObjectLockExclusive(a1, &v29, v5);
  NdisAcquireReadWriteLock((PNDIS_RW_LOCK)&WPP_MAIN_CB.Dpc.DpcData, 1u, &LockState);
  NextEntryHashTable = RtlLookupEntryHashTable(
                         (PRTL_DYNAMIC_HASH_TABLE)WPP_MAIN_CB.Dpc.SystemArgument1,
                         Signature,
                         &Context);
  LOBYTE(v8) = BYTE1(WPP_GLOBAL_Control->Timer) - 1;
  if ( (unsigned __int8)v8 > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_I(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      21,
      47,
      (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
      a1);
  for ( ;
        NextEntryHashTable;
        NextEntryHashTable = RtlGetNextEntryHashTable(
                               (PRTL_DYNAMIC_HASH_TABLE)WPP_MAIN_CB.Dpc.SystemArgument1,
                               &Context) )
  {
    if ( NextEntryHashTable[3].Signature == a1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&NextEntryHashTable[3].Linkage.Blink);
      _InterlockedIncrement((volatile signed __int32 *)&NextEntryHashTable[6].Signature + 1);
      v9 = v24;
      if ( *(__int128 **)(v24 + 8) != &v24 )
        goto LABEL_38;
      ++v2;
      NextEntryHashTable[2].Linkage.Flink = (_LIST_ENTRY *)v24;
      NextEntryHashTable[2].Linkage.Blink = (_LIST_ENTRY *)&v24;
      *(_QWORD *)(v9 + 8) = NextEntryHashTable + 2;
      *(_QWORD *)&v24 = NextEntryHashTable + 2;
    }
  }
  Flink = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)v24;
  if ( v2 )
  {
    do
    {
      v11 = Flink - 3;
      if ( !RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)WPP_MAIN_CB.Dpc.DeferredRoutine, Flink - 3, 0) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrPortLog,
          v12,
          19,
          48,
          (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
          (__int64)"success");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      VmsScIpsecOffloadSaDeRef(&Flink[-3]);
      if ( !RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)WPP_MAIN_CB.Dpc.DeferredContext, v11 + 2, 0) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrPortLog,
          v13,
          19,
          49,
          (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
          (__int64)"success");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      VmsScIpsecOffloadSaDeRef(&Flink[-3]);
      if ( !RtlRemoveEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)WPP_MAIN_CB.Dpc.SystemArgument1, v11 + 1, 0) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrPortLog,
          v14,
          19,
          50,
          (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
          (__int64)"success");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      VmsScIpsecOffloadSaDeRef(&Flink[-3]);
      Flink = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)Flink->Linkage.Flink;
      ++v1;
      --*(_DWORD *)(a1 + 6368);
    }
    while ( v1 < v2 );
    v6 = v23;
    v3 = v28;
  }
  if ( Flink != (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)&v24 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrPortLog,
      v8,
      19,
      51,
      (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
      (__int64)"cacheDelListIterator == &cacheDelListHead");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  NdisReleaseReadWriteLock((PNDIS_RW_LOCK)&WPP_MAIN_CB.Dpc.DpcData, &LockState);
  if ( *(_DWORD *)(a1 + 6368) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrPortLog,
      v15,
      19,
      52,
      (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
      (__int64)"PortToCleanup->OffloadFeatureStatus.IpsecCurrentOffloadSaCount == 0");
    if ( *(_DWORD *)(a1 + 6368) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( v6 && *(_DWORD *)(v6 + 68) == 1 )
  {
    v16 = *(_QWORD *)(a1 + 1256);
    if ( !v16 || *(_DWORD *)(v16 + 1880) != 1 )
      LODWORD(v16) = 0;
    LOBYTE(v15) = 1;
    VmsOmpObjectReference(v6, v15);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &v29);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 56), &v30);
    v18 = 0;
    if ( v2 )
    {
      while ( 1 )
      {
        v19 = v24;
        if ( *(__int128 **)(v24 + 8) != &v24 )
          break;
        v20 = *(_QWORD *)v24;
        if ( *(_QWORD *)(*(_QWORD *)v24 + 8LL) != (_QWORD)v24 )
          break;
        *(_QWORD *)&v24 = *(_QWORD *)v24;
        *(_QWORD *)(v20 + 8) = &v24;
        v21 = (_QWORD *)(v19 - 72);
        LODWORD(v25) = 1573248;
        *((_QWORD *)&v25 + 1) = 0;
        v26 = *(_QWORD *)(v19 - 72 + 88);
        VmsPtIpsecSendDirectOidToExternalNic(v16, v6, -66911741, (unsigned int)&v25, 24);
        if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_qqq(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            21,
            53,
            (__int64)WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids,
            v21[12],
            v21[11],
            a1);
        VmsScIpsecOffloadSaDeRef(v21);
        if ( (unsigned __int8)++v18 >= v2 )
          goto LABEL_37;
      }
LABEL_38:
      __fastfail(3u);
    }
LABEL_37:
    LOBYTE(v17) = 1;
    VmsOmpObjectDereference(v6, v17);
  }
  else
  {
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &v29);
    if ( v3 )
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 56), &v30);
  }
}

```

## disassembly

```asm
0x14014fc00  push    rbp
0x14014fc02  push    rbx
0x14014fc03  push    rsi
0x14014fc04  push    rdi
0x14014fc05  push    r12
0x14014fc07  push    r13
0x14014fc09  push    r14
0x14014fc0b  push    r15
0x14014fc0d  lea     rbp, [rsp-1Fh]
0x14014fc12  sub     rsp, 98h
0x14014fc19  xor     eax, eax
0x14014fc1b  xor     r15d, r15d
0x14014fc1e  xorps   xmm0, xmm0
0x14014fc21  mov     dword ptr [rbp+57h+LockState.LockState], r15d
0x14014fc25  xorps   xmm1, xmm1
0x14014fc28  mov     [rbp+57h+Context.Signature], rax
0x14014fc2c  movups  xmmword ptr [rbp+57h+Context.ChainHead], xmm0
0x14014fc30  mov     [rbp+57h+var_60], rax
0x14014fc34  mov     r12b, r15b
0x14014fc37  movups  [rbp+57h+var_70], xmm1
0x14014fc3b  mov     word ptr [rbp+57h+arg_8.OldIrql], ax
0x14014fc3f  mov     r13b, r15b
0x14014fc42  movups  [rbp+57h+var_80], xmm0
0x14014fc46  mov     [rbp+57h+arg_8.Flags], al
0x14014fc49  mov     rdi, rcx
0x14014fc4c  mov     [rbp+57h+arg_0], r15b
0x14014fc50  mov     word ptr [rbp+57h+arg_10.OldIrql], ax
0x14014fc54  mov     [rbp+57h+arg_10.Flags], al
0x14014fc57  call    VmsOmAssertIoctlMutexIsHeld
0x14014fc5c  lea     r8, [rbp+57h+Signature]
0x14014fc60  mov     [rbp+57h+Signature], r15
0x14014fc64  lea     edx, [r15+8]
0x14014fc68  mov     rcx, rdi
0x14014fc6b  call    VmsScpIpsecGenericUpdateHash
0x14014fc70  lea     rax, [rbp+57h+var_80]
0x14014fc74  mov     qword ptr [rbp+57h+var_80+8], rax
0x14014fc78  lea     rax, [rbp+57h+var_80]
0x14014fc7c  mov     qword ptr [rbp+57h+var_80], rax
0x14014fc80  mov     rax, [rdi+4D8h]
0x14014fc87  mov     rsi, [rax+10A8h]
0x14014fc8e  mov     [rbp+57h+var_88], rsi
0x14014fc92  test    rsi, rsi
0x14014fc95  jz      short loc_14014FCAD
0x14014fc97  xor     r8d, r8d
0x14014fc9a  lea     rdx, [rbp+57h+arg_10]
0x14014fc9e  mov     rcx, rsi
0x14014fca1  call    VmsOmObjectLockExclusive
0x14014fca6  mov     r13b, 1
0x14014fca9  mov     [rbp+57h+arg_0], r13b
0x14014fcad  mov     r8b, r13b
0x14014fcb0  lea     rdx, [rbp+57h+arg_8]
0x14014fcb4  mov     rcx, rdi
0x14014fcb7  call    VmsOmObjectLockExclusive
0x14014fcbc  lea     r8, [rbp+57h+LockState]; LockState
0x14014fcc0  mov     dl, 1; fWrite
0x14014fcc2  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x14014fcc9  call    cs:__imp_NdisAcquireReadWriteLock
0x14014fcd0  nop     dword ptr [rax+rax+00h]
0x14014fcd5  mov     rdx, [rbp+57h+Signature]; Signature
0x14014fcd9  lea     r8, [rbp+57h+Context]; Context
0x14014fcdd  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1; HashTable
0x14014fce4  call    cs:__imp_RtlLookupEntryHashTable
0x14014fceb  nop     dword ptr [rax+rax+00h]
0x14014fcf0  mov     rbx, rax
0x14014fcf3  mov     rcx, cs:WPP_GLOBAL_Control
0x14014fcfa  lea     rax, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014fd01  mov     dl, [rcx+29h]
0x14014fd04  dec     dl
0x14014fd06  cmp     dl, 2
0x14014fd09  ja      short loc_14014FD12
0x14014fd0b  cmp     [rcx+48h], r15w
0x14014fd10  jz      short loc_14014FD31
0x14014fd12  mov     rcx, [rcx+40h]
0x14014fd16  mov     r9d, 2Fh ; '/'
0x14014fd1c  mov     [rsp+0D0h+var_A8], rdi
0x14014fd21  xor     edx, edx
0x14014fd23  mov     [rsp+0D0h+var_B0], rax
0x14014fd28  lea     r8d, [r9-1Ah]
0x14014fd2c  call    WPP_RECORDER_SF_I
0x14014fd31  test    rbx, rbx
0x14014fd34  jz      short loc_14014FD92
0x14014fd36  cmp     [rbx+58h], rdi
0x14014fd3a  jnz     short loc_14014FD73
0x14014fd3c  lock inc dword ptr [rbx+50h]
0x14014fd40  lock inc dword ptr [rbx+0A4h]
0x14014fd47  mov     rcx, qword ptr [rbp+57h+var_80]
0x14014fd4b  lea     rax, [rbp+57h+var_80]
0x14014fd4f  cmp     [rcx+8], rax
0x14014fd53  jnz     loc_140150097
0x14014fd59  lea     rax, [rbx+30h]
0x14014fd5d  inc     r12b
0x14014fd60  mov     [rax], rcx
0x14014fd63  lea     rdx, [rbp+57h+var_80]
0x14014fd67  mov     [rbx+38h], rdx
0x14014fd6b  mov     [rcx+8], rax
0x14014fd6f  mov     qword ptr [rbp+57h+var_80], rax
0x14014fd73  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1; HashTable
0x14014fd7a  lea     rdx, [rbp+57h+Context]; Context
0x14014fd7e  call    cs:__imp_RtlGetNextEntryHashTable
0x14014fd85  nop     dword ptr [rax+rax+00h]
0x14014fd8a  mov     rbx, rax
0x14014fd8d  test    rax, rax
0x14014fd90  jnz     short loc_14014FD36
0x14014fd92  mov     r14, qword ptr [rbp+57h+var_80]
0x14014fd96  test    r12b, r12b
0x14014fd99  jz      loc_14014FEBA
0x14014fd9f  lea     rsi, aSuccess; "success"
0x14014fda6  lea     r13, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014fdad  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; HashTable
0x14014fdb4  lea     rbx, [r14-48h]
0x14014fdb8  mov     rdx, rbx; Entry
0x14014fdbb  xor     r8d, r8d; Context
0x14014fdbe  call    cs:__imp_RtlRemoveEntryHashTable
0x14014fdc5  nop     dword ptr [rax+rax+00h]
0x14014fdca  test    al, al
0x14014fdcc  jnz     short loc_14014FDF3
0x14014fdce  mov     rcx, cs:VmsIfrPortLog
0x14014fdd5  mov     r9d, 30h ; '0'
0x14014fddb  mov     [rsp+0D0h+var_A8], rsi
0x14014fde0  mov     [rsp+0D0h+var_B0], r13
0x14014fde5  lea     r8d, [r9-1Dh]
0x14014fde9  call    WPP_RECORDER_SF_s
0x14014fdee  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14014fdf3  xor     edx, edx
0x14014fdf5  mov     rcx, rbx; P
0x14014fdf8  call    VmsScIpsecOffloadSaDeRef
0x14014fdfd  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredContext; HashTable
0x14014fe04  lea     rdx, [rbx+30h]; Entry
0x14014fe08  xor     r8d, r8d; Context
0x14014fe0b  call    cs:__imp_RtlRemoveEntryHashTable
0x14014fe12  nop     dword ptr [rax+rax+00h]
0x14014fe17  test    al, al
0x14014fe19  jnz     short loc_14014FE40
0x14014fe1b  mov     rcx, cs:VmsIfrPortLog
0x14014fe22  mov     r9d, 31h ; '1'
0x14014fe28  mov     [rsp+0D0h+var_A8], rsi
0x14014fe2d  mov     [rsp+0D0h+var_B0], r13
0x14014fe32  lea     r8d, [r9-1Eh]
0x14014fe36  call    WPP_RECORDER_SF_s
0x14014fe3b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14014fe40  mov     edx, 1
0x14014fe45  mov     rcx, rbx; P
0x14014fe48  call    VmsScIpsecOffloadSaDeRef
0x14014fe4d  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1; HashTable
0x14014fe54  lea     rdx, [rbx+18h]; Entry
0x14014fe58  xor     r8d, r8d; Context
0x14014fe5b  call    cs:__imp_RtlRemoveEntryHashTable
0x14014fe62  nop     dword ptr [rax+rax+00h]
0x14014fe67  test    al, al
0x14014fe69  jnz     short loc_14014FE90
0x14014fe6b  mov     rcx, cs:VmsIfrPortLog
0x14014fe72  mov     r9d, 32h ; '2'
0x14014fe78  mov     [rsp+0D0h+var_A8], rsi
0x14014fe7d  mov     [rsp+0D0h+var_B0], r13
0x14014fe82  lea     r8d, [r9-1Fh]
0x14014fe86  call    WPP_RECORDER_SF_s
0x14014fe8b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14014fe90  mov     edx, 2
0x14014fe95  mov     rcx, rbx; P
0x14014fe98  call    VmsScIpsecOffloadSaDeRef
0x14014fe9d  mov     r14, [r14]
0x14014fea0  inc     r15b
0x14014fea3  dec     dword ptr [rdi+18E0h]
0x14014fea9  cmp     r15b, r12b
0x14014feac  jb      loc_14014FDAD
0x14014feb2  mov     rsi, [rbp+57h+var_88]
0x14014feb6  mov     r13b, [rbp+57h+arg_0]
0x14014feba  lea     rax, [rbp+57h+var_80]
0x14014febe  cmp     r14, rax
0x14014fec1  jz      short loc_14014FEF8
0x14014fec3  mov     rcx, cs:VmsIfrPortLog
0x14014feca  lea     rax, aCachedellistit; "cacheDelListIterator == &cacheDelListHe"...
0x14014fed1  mov     r9d, 33h ; '3'
0x14014fed7  mov     [rsp+0D0h+var_A8], rax
0x14014fedc  lea     rbx, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014fee3  mov     [rsp+0D0h+var_B0], rbx
0x14014fee8  lea     r8d, [r9-20h]
0x14014feec  call    WPP_RECORDER_SF_s
0x14014fef1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "cacheDelListIterator == &cacheDelListHead")
0x14014fef6  jmp     short loc_14014FEFF
0x14014fef8  lea     rbx, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014feff  lea     rdx, [rbp+57h+LockState]; LockState
0x14014ff03  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x14014ff0a  call    cs:__imp_NdisReleaseReadWriteLock
0x14014ff11  nop     dword ptr [rax+rax+00h]
0x14014ff16  xor     r15d, r15d
0x14014ff19  cmp     [rdi+18E0h], r15d
0x14014ff20  jz      short loc_14014FF55
0x14014ff22  mov     rcx, cs:VmsIfrPortLog
0x14014ff29  lea     rax, aPorttocleanupO; "PortToCleanup->OffloadFeatureStatus.Ips"...
0x14014ff30  mov     [rsp+0D0h+var_A8], rax
0x14014ff35  lea     r9d, [r15+34h]
0x14014ff39  lea     r8d, [r15+13h]
0x14014ff3d  mov     [rsp+0D0h+var_B0], rbx
0x14014ff42  call    WPP_RECORDER_SF_s
0x14014ff47  cmp     [rdi+18E0h], r15d
0x14014ff4e  jz      short loc_14014FF55
0x14014ff50  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "PortToCleanup->OffloadFeatureStatus.IpsecCurrentOffloadSaCount == 0")
0x14014ff55  test    rsi, rsi
0x14014ff58  jz      loc_14015009E
0x14014ff5e  cmp     dword ptr [rsi+44h], 1
0x14014ff62  jnz     loc_14015009E
0x14014ff68  mov     rbx, [rdi+4E8h]
0x14014ff6f  test    rbx, rbx
0x14014ff72  jz      short loc_14014FF7D
0x14014ff74  cmp     dword ptr [rbx+758h], 1
0x14014ff7b  jz      short loc_14014FF80
0x14014ff7d  mov     rbx, r15
0x14014ff80  mov     dl, 1
0x14014ff82  mov     rcx, rsi
0x14014ff85  call    VmsOmpObjectReference
0x14014ff8a  mov     rcx, [rdi+38h]; Lock
0x14014ff8e  lea     rdx, [rbp+57h+arg_8]; LockState
0x14014ff92  call    cs:__imp_NdisReleaseRWLock
0x14014ff99  nop     dword ptr [rax+rax+00h]
0x14014ff9e  mov     rcx, [rsi+38h]; Lock
0x14014ffa2  lea     rdx, [rbp+57h+arg_10]; LockState
0x14014ffa6  call    cs:__imp_NdisReleaseRWLock
0x14014ffad  nop     dword ptr [rax+rax+00h]
0x14014ffb2  mov     r14b, r15b
0x14014ffb5  test    r12b, r12b
0x14014ffb8  jz      loc_14015008B
0x14014ffbe  xor     r13d, r13d
0x14014ffc1  mov     rax, qword ptr [rbp+57h+var_80]
0x14014ffc5  lea     rcx, [rbp+57h+var_80]
0x14014ffc9  mov     r8d, 18h
0x14014ffcf  cmp     [rax+8], rcx
0x14014ffd3  jnz     loc_140150097
0x14014ffd9  mov     rcx, [rax]
0x14014ffdc  cmp     [rcx+8], rax
0x14014ffe0  jnz     loc_140150097
0x14014ffe6  mov     qword ptr [rbp+57h+var_80], rcx
0x14014ffea  lea     rdx, [rbp+57h+var_80]
0x14014ffee  mov     [rcx+8], rdx
0x14014fff2  lea     r15, [rax-48h]
0x14014fff6  mov     dword ptr [rbp+57h+var_70], 180180h
0x14014fffd  lea     r9, [rbp+57h+var_70]
0x140150001  mov     qword ptr [rbp+57h+var_70+8], r13
0x140150005  mov     rdx, rsi
0x140150008  mov     rax, [r15+58h]
0x14015000c  mov     rcx, rbx
0x14015000f  mov     dword ptr [rsp+0D0h+var_B0], r8d
0x140150014  mov     r8d, 0FC030203h
0x14015001a  mov     [rbp+57h+var_60], rax
0x14015001e  call    VmsPtIpsecSendDirectOidToExternalNic
0x140150023  mov     rcx, cs:WPP_GLOBAL_Control
0x14015002a  mov     al, [rcx+29h]
0x14015002d  dec     al
0x14015002f  cmp     al, 2
0x140150031  ja      short loc_14015003A
0x140150033  cmp     [rcx+48h], r13w
0x140150038  jz      short loc_140150072
0x14015003a  mov     rax, [r15+58h]
0x14015003e  mov     r9d, 35h ; '5'
0x140150044  mov     rcx, [rcx+40h]
0x140150048  xor     edx, edx
0x14015004a  mov     [rsp+0D0h+var_98], rdi
0x14015004f  mov     [rsp+0D0h+var_A0], rax
0x140150054  mov     rax, [r15+60h]
0x140150058  lea     r8d, [r9-20h]
0x14015005c  mov     [rsp+0D0h+var_A8], rax
0x140150061  lea     rax, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x140150068  mov     [rsp+0D0h+var_B0], rax
0x14015006d  call    WPP_RECORDER_SF_qqq
0x140150072  mov     edx, 6
0x140150077  mov     rcx, r15; P
0x14015007a  call    VmsScIpsecOffloadSaDeRef
0x14015007f  inc     r14b
0x140150082  cmp     r14b, r12b
0x140150085  jb      loc_14014FFC1
0x14015008b  mov     dl, 1
0x14015008d  mov     rcx, rsi
0x140150090  call    VmsOmpObjectDereference
0x140150095  jmp     short loc_1401500CB
0x140150097  mov     ecx, 3
0x14015009c  int     29h; Win8: RtlFailFast(ecx)
0x14015009e  mov     rcx, [rdi+38h]; Lock
0x1401500a2  lea     rdx, [rbp+57h+arg_8]; LockState
0x1401500a6  call    cs:__imp_NdisReleaseRWLock
0x1401500ad  nop     dword ptr [rax+rax+00h]
0x1401500b2  test    r13b, r13b
0x1401500b5  jz      short loc_1401500CB
0x1401500b7  mov     rcx, [rsi+38h]; Lock
0x1401500bb  lea     rdx, [rbp+57h+arg_10]; LockState
0x1401500bf  call    cs:__imp_NdisReleaseRWLock
0x1401500c6  nop     dword ptr [rax+rax+00h]
0x1401500cb  add     rsp, 98h
0x1401500d2  pop     r15
0x1401500d4  pop     r14
0x1401500d6  pop     r13
0x1401500d8  pop     r12
0x1401500da  pop     rdi
0x1401500db  pop     rsi
0x1401500dc  pop     rbx
0x1401500dd  pop     rbp
0x1401500de  retn
```
