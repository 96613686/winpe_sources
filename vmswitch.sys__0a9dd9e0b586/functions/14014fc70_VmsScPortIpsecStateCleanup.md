# VmsScPortIpsecStateCleanup

- ea: `0x14014fc70`
- end: `0x140150150`
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
- `0x1400f2fa8`
- `0x14013f1e4`
- `0x14014f500`
- `0x14014fc70`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14014fdee`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14014fdee`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014fe2e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014fe7b`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014fecb`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014fe2e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014fe7b`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14014fecb`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14014fd54`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14014fd54`
- `NDIS!NdisReleaseReadWriteLock` at `0x14014ff7a`
- `NDIS!NdisReleaseReadWriteLock` at `0x14014ff7a`
- `NDIS!NdisAcquireReadWriteLock` at `0x14014fd39`
- `NDIS!NdisAcquireReadWriteLock` at `0x14014fd39`
- `NDIS!NdisReleaseRWLock` at `0x140150002`
- `NDIS!NdisReleaseRWLock` at `0x140150016`
- `NDIS!NdisReleaseRWLock` at `0x140150116`
- `NDIS!NdisReleaseRWLock` at `0x14015012f`
- `NDIS!NdisReleaseRWLock` at `0x140150002`
- `NDIS!NdisReleaseRWLock` at `0x140150016`
- `NDIS!NdisReleaseRWLock` at `0x140150116`
- `NDIS!NdisReleaseRWLock` at `0x14015012f`

## string_xrefs

- `0x14014ff3a`: `cacheDelListIterator == &cacheDelListHead`

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
0x14014fc70  push    rbp
0x14014fc72  push    rbx
0x14014fc73  push    rsi
0x14014fc74  push    rdi
0x14014fc75  push    r12
0x14014fc77  push    r13
0x14014fc79  push    r14
0x14014fc7b  push    r15
0x14014fc7d  lea     rbp, [rsp-1Fh]
0x14014fc82  sub     rsp, 98h
0x14014fc89  xor     eax, eax
0x14014fc8b  xor     r15d, r15d
0x14014fc8e  xorps   xmm0, xmm0
0x14014fc91  mov     dword ptr [rbp+57h+LockState.LockState], r15d
0x14014fc95  xorps   xmm1, xmm1
0x14014fc98  mov     [rbp+57h+Context.Signature], rax
0x14014fc9c  movups  xmmword ptr [rbp+57h+Context.ChainHead], xmm0
0x14014fca0  mov     [rbp+57h+var_60], rax
0x14014fca4  mov     r12b, r15b
0x14014fca7  movups  [rbp+57h+var_70], xmm1
0x14014fcab  mov     word ptr [rbp+57h+arg_8.OldIrql], ax
0x14014fcaf  mov     r13b, r15b
0x14014fcb2  movups  [rbp+57h+var_80], xmm0
0x14014fcb6  mov     [rbp+57h+arg_8.Flags], al
0x14014fcb9  mov     rdi, rcx
0x14014fcbc  mov     [rbp+57h+arg_0], r15b
0x14014fcc0  mov     word ptr [rbp+57h+arg_10.OldIrql], ax
0x14014fcc4  mov     [rbp+57h+arg_10.Flags], al
0x14014fcc7  call    VmsOmAssertIoctlMutexIsHeld
0x14014fccc  lea     r8, [rbp+57h+Signature]
0x14014fcd0  mov     [rbp+57h+Signature], r15
0x14014fcd4  lea     edx, [r15+8]
0x14014fcd8  mov     rcx, rdi
0x14014fcdb  call    VmsScpIpsecGenericUpdateHash
0x14014fce0  lea     rax, [rbp+57h+var_80]
0x14014fce4  mov     qword ptr [rbp+57h+var_80+8], rax
0x14014fce8  lea     rax, [rbp+57h+var_80]
0x14014fcec  mov     qword ptr [rbp+57h+var_80], rax
0x14014fcf0  mov     rax, [rdi+4D8h]
0x14014fcf7  mov     rsi, [rax+10A8h]
0x14014fcfe  mov     [rbp+57h+var_88], rsi
0x14014fd02  test    rsi, rsi
0x14014fd05  jz      short loc_14014FD1D
0x14014fd07  xor     r8d, r8d
0x14014fd0a  lea     rdx, [rbp+57h+arg_10]
0x14014fd0e  mov     rcx, rsi
0x14014fd11  call    VmsOmObjectLockExclusive
0x14014fd16  mov     r13b, 1
0x14014fd19  mov     [rbp+57h+arg_0], r13b
0x14014fd1d  mov     r8b, r13b
0x14014fd20  lea     rdx, [rbp+57h+arg_8]
0x14014fd24  mov     rcx, rdi
0x14014fd27  call    VmsOmObjectLockExclusive
0x14014fd2c  lea     r8, [rbp+57h+LockState]; LockState
0x14014fd30  mov     dl, 1; fWrite
0x14014fd32  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x14014fd39  call    cs:__imp_NdisAcquireReadWriteLock
0x14014fd40  nop     dword ptr [rax+rax+00h]
0x14014fd45  mov     rdx, [rbp+57h+Signature]; Signature
0x14014fd49  lea     r8, [rbp+57h+Context]; Context
0x14014fd4d  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1; HashTable
0x14014fd54  call    cs:__imp_RtlLookupEntryHashTable
0x14014fd5b  nop     dword ptr [rax+rax+00h]
0x14014fd60  mov     rbx, rax
0x14014fd63  mov     rcx, cs:WPP_GLOBAL_Control
0x14014fd6a  lea     rax, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014fd71  mov     dl, [rcx+29h]
0x14014fd74  dec     dl
0x14014fd76  cmp     dl, 2
0x14014fd79  ja      short loc_14014FD82
0x14014fd7b  cmp     [rcx+48h], r15w
0x14014fd80  jz      short loc_14014FDA1
0x14014fd82  mov     rcx, [rcx+40h]
0x14014fd86  mov     r9d, 2Fh ; '/'
0x14014fd8c  mov     [rsp+0D0h+var_A8], rdi
0x14014fd91  xor     edx, edx
0x14014fd93  mov     [rsp+0D0h+var_B0], rax
0x14014fd98  lea     r8d, [r9-1Ah]
0x14014fd9c  call    WPP_RECORDER_SF_I
0x14014fda1  test    rbx, rbx
0x14014fda4  jz      short loc_14014FE02
0x14014fda6  cmp     [rbx+58h], rdi
0x14014fdaa  jnz     short loc_14014FDE3
0x14014fdac  lock inc dword ptr [rbx+50h]
0x14014fdb0  lock inc dword ptr [rbx+0A4h]
0x14014fdb7  mov     rcx, qword ptr [rbp+57h+var_80]
0x14014fdbb  lea     rax, [rbp+57h+var_80]
0x14014fdbf  cmp     [rcx+8], rax
0x14014fdc3  jnz     loc_140150107
0x14014fdc9  lea     rax, [rbx+30h]
0x14014fdcd  inc     r12b
0x14014fdd0  mov     [rax], rcx
0x14014fdd3  lea     rdx, [rbp+57h+var_80]
0x14014fdd7  mov     [rbx+38h], rdx
0x14014fddb  mov     [rcx+8], rax
0x14014fddf  mov     qword ptr [rbp+57h+var_80], rax
0x14014fde3  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1; HashTable
0x14014fdea  lea     rdx, [rbp+57h+Context]; Context
0x14014fdee  call    cs:__imp_RtlGetNextEntryHashTable
0x14014fdf5  nop     dword ptr [rax+rax+00h]
0x14014fdfa  mov     rbx, rax
0x14014fdfd  test    rax, rax
0x14014fe00  jnz     short loc_14014FDA6
0x14014fe02  mov     r14, qword ptr [rbp+57h+var_80]
0x14014fe06  test    r12b, r12b
0x14014fe09  jz      loc_14014FF2A
0x14014fe0f  lea     rsi, aSuccess; "success"
0x14014fe16  lea     r13, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014fe1d  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; HashTable
0x14014fe24  lea     rbx, [r14-48h]
0x14014fe28  mov     rdx, rbx; Entry
0x14014fe2b  xor     r8d, r8d; Context
0x14014fe2e  call    cs:__imp_RtlRemoveEntryHashTable
0x14014fe35  nop     dword ptr [rax+rax+00h]
0x14014fe3a  test    al, al
0x14014fe3c  jnz     short loc_14014FE63
0x14014fe3e  mov     rcx, cs:VmsIfrPortLog
0x14014fe45  mov     r9d, 30h ; '0'
0x14014fe4b  mov     [rsp+0D0h+var_A8], rsi
0x14014fe50  mov     [rsp+0D0h+var_B0], r13
0x14014fe55  lea     r8d, [r9-1Dh]
0x14014fe59  call    WPP_RECORDER_SF_s
0x14014fe5e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14014fe63  xor     edx, edx
0x14014fe65  mov     rcx, rbx; P
0x14014fe68  call    VmsScIpsecOffloadSaDeRef
0x14014fe6d  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredContext; HashTable
0x14014fe74  lea     rdx, [rbx+30h]; Entry
0x14014fe78  xor     r8d, r8d; Context
0x14014fe7b  call    cs:__imp_RtlRemoveEntryHashTable
0x14014fe82  nop     dword ptr [rax+rax+00h]
0x14014fe87  test    al, al
0x14014fe89  jnz     short loc_14014FEB0
0x14014fe8b  mov     rcx, cs:VmsIfrPortLog
0x14014fe92  mov     r9d, 31h ; '1'
0x14014fe98  mov     [rsp+0D0h+var_A8], rsi
0x14014fe9d  mov     [rsp+0D0h+var_B0], r13
0x14014fea2  lea     r8d, [r9-1Eh]
0x14014fea6  call    WPP_RECORDER_SF_s
0x14014feab  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14014feb0  mov     edx, 1
0x14014feb5  mov     rcx, rbx; P
0x14014feb8  call    VmsScIpsecOffloadSaDeRef
0x14014febd  mov     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1; HashTable
0x14014fec4  lea     rdx, [rbx+18h]; Entry
0x14014fec8  xor     r8d, r8d; Context
0x14014fecb  call    cs:__imp_RtlRemoveEntryHashTable
0x14014fed2  nop     dword ptr [rax+rax+00h]
0x14014fed7  test    al, al
0x14014fed9  jnz     short loc_14014FF00
0x14014fedb  mov     rcx, cs:VmsIfrPortLog
0x14014fee2  mov     r9d, 32h ; '2'
0x14014fee8  mov     [rsp+0D0h+var_A8], rsi
0x14014feed  mov     [rsp+0D0h+var_B0], r13
0x14014fef2  lea     r8d, [r9-1Fh]
0x14014fef6  call    WPP_RECORDER_SF_s
0x14014fefb  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "success")
0x14014ff00  mov     edx, 2
0x14014ff05  mov     rcx, rbx; P
0x14014ff08  call    VmsScIpsecOffloadSaDeRef
0x14014ff0d  mov     r14, [r14]
0x14014ff10  inc     r15b
0x14014ff13  dec     dword ptr [rdi+18E0h]
0x14014ff19  cmp     r15b, r12b
0x14014ff1c  jb      loc_14014FE1D
0x14014ff22  mov     rsi, [rbp+57h+var_88]
0x14014ff26  mov     r13b, [rbp+57h+arg_0]
0x14014ff2a  lea     rax, [rbp+57h+var_80]
0x14014ff2e  cmp     r14, rax
0x14014ff31  jz      short loc_14014FF68
0x14014ff33  mov     rcx, cs:VmsIfrPortLog
0x14014ff3a  lea     rax, aCachedellistit; "cacheDelListIterator == &cacheDelListHe"...
0x14014ff41  mov     r9d, 33h ; '3'
0x14014ff47  mov     [rsp+0D0h+var_A8], rax
0x14014ff4c  lea     rbx, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014ff53  mov     [rsp+0D0h+var_B0], rbx
0x14014ff58  lea     r8d, [r9-20h]
0x14014ff5c  call    WPP_RECORDER_SF_s
0x14014ff61  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "cacheDelListIterator == &cacheDelListHead")
0x14014ff66  jmp     short loc_14014FF6F
0x14014ff68  lea     rbx, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x14014ff6f  lea     rdx, [rbp+57h+LockState]; LockState
0x14014ff73  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Lock
0x14014ff7a  call    cs:__imp_NdisReleaseReadWriteLock
0x14014ff81  nop     dword ptr [rax+rax+00h]
0x14014ff86  xor     r15d, r15d
0x14014ff89  cmp     [rdi+18E0h], r15d
0x14014ff90  jz      short loc_14014FFC5
0x14014ff92  mov     rcx, cs:VmsIfrPortLog
0x14014ff99  lea     rax, aPorttocleanupO; "PortToCleanup->OffloadFeatureStatus.Ips"...
0x14014ffa0  mov     [rsp+0D0h+var_A8], rax
0x14014ffa5  lea     r9d, [r15+34h]
0x14014ffa9  lea     r8d, [r15+13h]
0x14014ffad  mov     [rsp+0D0h+var_B0], rbx
0x14014ffb2  call    WPP_RECORDER_SF_s
0x14014ffb7  cmp     [rdi+18E0h], r15d
0x14014ffbe  jz      short loc_14014FFC5
0x14014ffc0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "PortToCleanup->OffloadFeatureStatus.IpsecCurrentOffloadSaCount == 0")
0x14014ffc5  test    rsi, rsi
0x14014ffc8  jz      loc_14015010E
0x14014ffce  cmp     dword ptr [rsi+44h], 1
0x14014ffd2  jnz     loc_14015010E
0x14014ffd8  mov     rbx, [rdi+4E8h]
0x14014ffdf  test    rbx, rbx
0x14014ffe2  jz      short loc_14014FFED
0x14014ffe4  cmp     dword ptr [rbx+758h], 1
0x14014ffeb  jz      short loc_14014FFF0
0x14014ffed  mov     rbx, r15
0x14014fff0  mov     dl, 1
0x14014fff2  mov     rcx, rsi
0x14014fff5  call    VmsOmpObjectReference
0x14014fffa  mov     rcx, [rdi+38h]; Lock
0x14014fffe  lea     rdx, [rbp+57h+arg_8]; LockState
0x140150002  call    cs:__imp_NdisReleaseRWLock
0x140150009  nop     dword ptr [rax+rax+00h]
0x14015000e  mov     rcx, [rsi+38h]; Lock
0x140150012  lea     rdx, [rbp+57h+arg_10]; LockState
0x140150016  call    cs:__imp_NdisReleaseRWLock
0x14015001d  nop     dword ptr [rax+rax+00h]
0x140150022  mov     r14b, r15b
0x140150025  test    r12b, r12b
0x140150028  jz      loc_1401500FB
0x14015002e  xor     r13d, r13d
0x140150031  mov     rax, qword ptr [rbp+57h+var_80]
0x140150035  lea     rcx, [rbp+57h+var_80]
0x140150039  mov     r8d, 18h
0x14015003f  cmp     [rax+8], rcx
0x140150043  jnz     loc_140150107
0x140150049  mov     rcx, [rax]
0x14015004c  cmp     [rcx+8], rax
0x140150050  jnz     loc_140150107
0x140150056  mov     qword ptr [rbp+57h+var_80], rcx
0x14015005a  lea     rdx, [rbp+57h+var_80]
0x14015005e  mov     [rcx+8], rdx
0x140150062  lea     r15, [rax-48h]
0x140150066  mov     dword ptr [rbp+57h+var_70], 180180h
0x14015006d  lea     r9, [rbp+57h+var_70]
0x140150071  mov     qword ptr [rbp+57h+var_70+8], r13
0x140150075  mov     rdx, rsi
0x140150078  mov     rax, [r15+58h]
0x14015007c  mov     rcx, rbx
0x14015007f  mov     dword ptr [rsp+0D0h+var_B0], r8d
0x140150084  mov     r8d, 0FC030203h
0x14015008a  mov     [rbp+57h+var_60], rax
0x14015008e  call    VmsPtIpsecSendDirectOidToExternalNic
0x140150093  mov     rcx, cs:WPP_GLOBAL_Control
0x14015009a  mov     al, [rcx+29h]
0x14015009d  dec     al
0x14015009f  cmp     al, 2
0x1401500a1  ja      short loc_1401500AA
0x1401500a3  cmp     [rcx+48h], r13w
0x1401500a8  jz      short loc_1401500E2
0x1401500aa  mov     rax, [r15+58h]
0x1401500ae  mov     r9d, 35h ; '5'
0x1401500b4  mov     rcx, [rcx+40h]
0x1401500b8  xor     edx, edx
0x1401500ba  mov     [rsp+0D0h+var_98], rdi
0x1401500bf  mov     [rsp+0D0h+var_A0], rax
0x1401500c4  mov     rax, [r15+60h]
0x1401500c8  lea     r8d, [r9-20h]
0x1401500cc  mov     [rsp+0D0h+var_A8], rax
0x1401500d1  lea     rax, WPP_4902e3e58ec537298ea0e310d4cd91f0_Traceguids
0x1401500d8  mov     [rsp+0D0h+var_B0], rax
0x1401500dd  call    WPP_RECORDER_SF_qqq
0x1401500e2  mov     edx, 6
0x1401500e7  mov     rcx, r15; P
0x1401500ea  call    VmsScIpsecOffloadSaDeRef
0x1401500ef  inc     r14b
0x1401500f2  cmp     r14b, r12b
0x1401500f5  jb      loc_140150031
0x1401500fb  mov     dl, 1
0x1401500fd  mov     rcx, rsi
0x140150100  call    VmsOmpObjectDereference
0x140150105  jmp     short loc_14015013B
0x140150107  mov     ecx, 3
0x14015010c  int     29h; Win8: RtlFailFast(ecx)
0x14015010e  mov     rcx, [rdi+38h]; Lock
0x140150112  lea     rdx, [rbp+57h+arg_8]; LockState
0x140150116  call    cs:__imp_NdisReleaseRWLock
0x14015011d  nop     dword ptr [rax+rax+00h]
0x140150122  test    r13b, r13b
0x140150125  jz      short loc_14015013B
0x140150127  mov     rcx, [rsi+38h]; Lock
0x14015012b  lea     rdx, [rbp+57h+arg_10]; LockState
0x14015012f  call    cs:__imp_NdisReleaseRWLock
0x140150136  nop     dword ptr [rax+rax+00h]
0x14015013b  add     rsp, 98h
0x140150142  pop     r15
0x140150144  pop     r14
0x140150146  pop     r13
0x140150148  pop     r12
0x14015014a  pop     rdi
0x14015014b  pop     rsi
0x14015014c  pop     rbx
0x14015014d  pop     rbp
0x14015014e  retn
```
