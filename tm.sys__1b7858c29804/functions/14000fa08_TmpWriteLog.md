# TmpWriteLog

- ea: `0x14000fa08`
- end: `0x14000febf`
- name: `TmpWriteLog`
- size: `1207`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, char, ULONG cReserveRecords, PLONGLONG, PCLFS_LSN plsn1)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001f3e8`

## callees

- `0x140001330`
- `0x14000df30`
- `0x14000f59c`
- `0x14000fa08`

## import_xrefs

- `CLFS!ClfsReserveAndAppendLog` at `0x14000fc3e`
- `CLFS!ClfsReserveAndAppendLog` at `0x14000fc3e`
- `CLFS!ClfsLsnGreater` at `0x14000fd20`
- `CLFS!ClfsLsnGreater` at `0x14000fd20`
- `CLFS!ClfsReserveAndAppendLogAligned` at `0x14000fd00`
- `CLFS!ClfsReserveAndAppendLogAligned` at `0x14000fd00`
- `CLFS!ClfsMgmtHandleLogFileFull` at `0x14000fe26`
- `CLFS!ClfsMgmtHandleLogFileFull` at `0x14000fe26`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000fa59`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000fa59`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000fbaf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000fdc7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000fbaf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000fdc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fe9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021c44`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fe9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021c44`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fc63`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fd6e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fdaf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fe0f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fe56`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fe7b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021c1d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fc63`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fd6e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fdaf`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fe0f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fe56`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fe7b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021c1d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000fe87`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021c2d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000fe87`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021c2d`
- `ntoskrnl!ObfReferenceObject` at `0x14000fe00`
- `ntoskrnl!ObfReferenceObject` at `0x14000fe00`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000fad0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000fad0`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000fb23`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14000fb23`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000fb68`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000fb68`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000fb89`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000fb89`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000fc7e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000fc7e`
- `ntoskrnl!KeResetEvent` at `0x14000fdf1`
- `ntoskrnl!KeResetEvent` at `0x14000fdf1`

## pseudocode

```c
__int64 __fastcall TmpWriteLog(
        __int64 a1,
        CLFS_WRITE_ENTRY *a2,
        ULONG a3,
        _QWORD *a4,
        int a5,
        int a6,
        char a7,
        ULONG cReserveRecords,
        PLONGLONG a9,
        PCLFS_LSN plsn1)
{
  __int64 v10; // rbx
  char v11; // di
  unsigned int v12; // r12d
  _QWORD *PoolWithTag; // r14
  __int64 v14; // rsi
  NTSTATUS appended; // ebx
  NTSTATUS v16; // eax
  unsigned int v17; // eax
  __int64 rgcbReservation; // [rsp+60h] [rbp-58h] BYREF
  _QWORD *v20; // [rsp+68h] [rbp-50h]
  __int64 v21; // [rsp+70h] [rbp-48h]
  char v26; // [rsp+F0h] [rbp+38h]

  v10 = a1;
  rgcbReservation = 0;
  v11 = 0;
  v26 = 0;
  v12 = 0;
  PoolWithTag = 0;
  v20 = 0;
  v21 = *(_QWORD *)(a1 + 512);
  v14 = v21;
  KeEnterCriticalRegion();
  while ( 1 )
  {
    ++v12;
    if ( (*(_DWORD *)(v14 + 888) & 4) != 0 || v11 )
    {
      v11 = 0;
      if ( !a6 )
      {
        if ( (*(_DWORD *)(v14 + 132) & 4) != 0 )
          goto LABEL_6;
        PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x10u, 0x41576D54u);
        v20 = PoolWithTag;
        if ( !PoolWithTag )
        {
          appended = -1073741670;
          goto LABEL_35;
        }
        *PoolWithTag = v14 + 688;
        PoolWithTag[1] = v10;
        if ( KeWaitForMultipleObjects(2u, (PVOID *)PoolWithTag, WaitAny, UserRequest, 0, 0, 0, 0) == 1 )
        {
          appended = -1073741536;
          goto LABEL_35;
        }
        if ( (*(_DWORD *)(v14 + 132) & 4) != 0 )
        {
LABEL_6:
          appended = -1072037844;
          goto LABEL_35;
        }
        appended = *(_DWORD *)(v14 + 892);
        if ( appended < 0 )
          goto LABEL_35;
      }
    }
    ExAcquireFastMutex((PFAST_MUTEX)(v14 + 592));
    *a4 = *(_QWORD *)(v14 + 584);
    ExReleaseFastMutex((PFAST_MUTEX)(v14 + 592));
    if ( (*(_DWORD *)(v14 + 888) & 2) == 0 )
    {
      ExAcquireResourceExclusiveLite((PERESOURCE)(v14 + 784), 1u);
      v11 = 1;
      if ( (*(_DWORD *)(v14 + 888) & 2) == 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 15, WPP_b6c3014efb2237c03ead876b767ed07b_Traceguids, v14);
        rgcbReservation = 32;
        appended = ClfsReserveAndAppendLog(*(PVOID *)(v14 + 160), 0, 0, 0, 0, 1u, &rgcbReservation, 0, 0);
        if ( appended < 0 )
          goto LABEL_35;
        _InterlockedOr((volatile signed __int32 *)(v14 + 888), 2u);
      }
      ExReleaseResourceLite((PERESOURCE)(v14 + 784));
    }
    ExAcquireResourceSharedLite((PERESOURCE)(v14 + 784), 1u);
    v11 = 1;
    v16 = ClfsReserveAndAppendLogAligned(
            *(PVOID *)(v14 + 160),
            a2,
            a3,
            8u,
            0,
            0,
            cReserveRecords,
            a9,
            (a6 != 0 ? 4 : 0) | (a5 != 0 ? 2 : 0),
            plsn1);
    appended = v16;
    if ( v16 >= 0 )
      break;
    if ( v16 == -1073741670 && v12 < 0xA )
    {
      ExReleaseResourceLite((PERESOURCE)(v14 + 784));
      v10 = a1;
      v11 = v26;
    }
    else
    {
      if ( v16 != -1072037859 )
        goto LABEL_35;
      v26 = 1;
      ExReleaseResourceLite((PERESOURCE)(v14 + 784));
      ExAcquireResourceExclusiveLite((PERESOURCE)(v14 + 784), 1u);
      if ( (*(_DWORD *)(v14 + 888) & 4) != 0 )
      {
        ExReleaseResourceLite((PERESOURCE)(v14 + 784));
      }
      else
      {
        _InterlockedOr((volatile signed __int32 *)(v14 + 888), 4u);
        KeResetEvent((PRKEVENT)(v14 + 688));
        ObfReferenceObject((PVOID)v14);
        ExReleaseResourceLite((PERESOURCE)(v14 + 784));
        v17 = ClfsMgmtHandleLogFileFull(*(CLFS_MGMT_CLIENT *)(v14 + 168));
        if ( v17 != 259 )
          TmpLogGrowthCompletedNotification(*(_QWORD *)(v14 + 152), v17, 0, v14);
      }
      v10 = a1;
    }
  }
  if ( ClfsLsnGreater(plsn1, (const CLFS_LSN *)(v14 + 648)) )
  {
    TmpInsertTransactionLsnList(a1, plsn1);
    _InterlockedOr((volatile signed __int32 *)(v14 + 132), 0x100u);
  }
  else
  {
    appended = -1072103333;
  }
LABEL_35:
  if ( v11 )
    ExReleaseResourceLite((PERESOURCE)(v14 + 784));
  KeLeaveCriticalRegion();
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14000fa08  mov     rax, rsp
0x14000fa0b  mov     [rax+20h], r9
0x14000fa0f  mov     [rax+18h], r8d
0x14000fa13  mov     [rax+10h], rdx
0x14000fa17  mov     [rax+8], rcx
0x14000fa1b  push    rbx
0x14000fa1c  push    rsi
0x14000fa1d  push    rdi
0x14000fa1e  push    r12
0x14000fa20  push    r13
0x14000fa22  push    r14
0x14000fa24  push    r15
0x14000fa26  sub     rsp, 80h
0x14000fa2d  mov     rbx, rcx
0x14000fa30  mov     qword ptr [rax-58h], 0
0x14000fa38  mov     byte ptr [rax-68h], 0
0x14000fa3c  xor     dil, dil
0x14000fa3f  mov     [rax+38h], dil
0x14000fa43  xor     r12d, r12d
0x14000fa46  xor     r14d, r14d
0x14000fa49  mov     [rax-50h], r14
0x14000fa4d  mov     rsi, [rcx+200h]
0x14000fa54  mov     [rsp+0B8h+var_48], rsi
0x14000fa59  call    cs:__imp_KeEnterCriticalRegion
0x14000fa60  nop     dword ptr [rax+rax+00h]
0x14000fa65  lea     r15, [rsi+310h]
0x14000fa6c  mov     r13, [rsp+0B8h+plsn1]
0x14000fa74  inc     r12d
0x14000fa77  mov     [rsp+0B8h+var_60], r12d
0x14000fa7c  mov     [rsp+0B8h+var_5C], r12d
0x14000fa81  mov     eax, [rsi+378h]
0x14000fa87  test    al, 4
0x14000fa89  jnz     short loc_14000FA94
0x14000fa8b  test    dil, dil
0x14000fa8e  jz      loc_14000FB5E
0x14000fa94  xor     edi, edi
0x14000fa96  cmp     [rsp+0B8h+arg_28], edi
0x14000fa9d  jnz     loc_14000FB5E
0x14000faa3  mov     eax, [rsi+84h]
0x14000faa9  test    al, 4
0x14000faab  jz      short loc_14000FAC0
0x14000faad  mov     ebx, 0C01A002Ch
0x14000fab2  mov     [rsp+0B8h+var_64], ebx
0x14000fab6  mov     [rsp+0B8h+var_68], dil
0x14000fabb  jmp     loc_14000FE73
0x14000fac0  mov     edx, 10h; NumberOfBytes
0x14000fac5  mov     ecx, 200h; PoolType
0x14000faca  mov     r8d, 41576D54h; Tag
0x14000fad0  call    cs:__imp_ExAllocatePoolWithTag
0x14000fad7  nop     dword ptr [rax+rax+00h]
0x14000fadc  mov     r14, rax
0x14000fadf  mov     [rsp+0B8h+var_50], rax
0x14000fae4  test    rax, rax
0x14000fae7  jnz     short loc_14000FAF0
0x14000fae9  mov     ebx, 0C000009Ah
0x14000faee  jmp     short loc_14000FAB2
0x14000faf0  lea     rax, [rsi+2B0h]
0x14000faf7  mov     [r14], rax
0x14000fafa  mov     [r14+8], rbx
0x14000fafe  mov     [rsp+0B8h+WaitBlockArray], rdi; WaitBlockArray
0x14000fb03  mov     [rsp+0B8h+Timeout], rdi; Timeout
0x14000fb08  mov     [rsp+0B8h+Alertable], dil; Alertable
0x14000fb0d  mov     [rsp+0B8h+WaitMode], dil; WaitMode
0x14000fb12  mov     r9d, 6; WaitReason
0x14000fb18  lea     r8d, [r9-5]; WaitType
0x14000fb1c  mov     rdx, r14; Object
0x14000fb1f  lea     ecx, [r9-4]; Count
0x14000fb23  call    cs:__imp_KeWaitForMultipleObjects
0x14000fb2a  nop     dword ptr [rax+rax+00h]
0x14000fb2f  mov     [rsp+0B8h+var_64], eax
0x14000fb33  cmp     eax, 1
0x14000fb36  jnz     short loc_14000FB42
0x14000fb38  mov     ebx, 0C0000120h
0x14000fb3d  jmp     loc_14000FAB2
0x14000fb42  mov     eax, [rsi+84h]
0x14000fb48  test    al, 4
0x14000fb4a  jnz     loc_14000FAAD
0x14000fb50  mov     ebx, [rsi+37Ch]
0x14000fb56  test    ebx, ebx
0x14000fb58  js      loc_14000FAB2
0x14000fb5e  lea     rbx, [rsi+250h]
0x14000fb65  mov     rcx, rbx; FastMutex
0x14000fb68  call    cs:__imp_ExAcquireFastMutex
0x14000fb6f  nop     dword ptr [rax+rax+00h]
0x14000fb74  mov     rax, [rsi+248h]
0x14000fb7b  mov     rcx, [rsp+0B8h+arg_18]
0x14000fb83  mov     [rcx], rax
0x14000fb86  mov     rcx, rbx; FastMutex
0x14000fb89  call    cs:__imp_ExReleaseFastMutex
0x14000fb90  nop     dword ptr [rax+rax+00h]
0x14000fb95  mov     eax, [rsi+378h]
0x14000fb9b  test    al, 2
0x14000fb9d  jnz     loc_14000FC79
0x14000fba3  lea     r12, [rsi+310h]
0x14000fbaa  mov     dl, 1; Wait
0x14000fbac  mov     rcx, r12; Resource
0x14000fbaf  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000fbb6  nop     dword ptr [rax+rax+00h]
0x14000fbbb  mov     dil, 1
0x14000fbbe  mov     [rsp+0B8h+var_68], dil
0x14000fbc3  mov     eax, [rsi+378h]
0x14000fbc9  test    al, 2
0x14000fbcb  jnz     loc_14000FC60
0x14000fbd1  lea     rax, WPP_GLOBAL_Control
0x14000fbd8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fbdf  cmp     rcx, rax
0x14000fbe2  jz      short loc_14000FC04
0x14000fbe4  mov     eax, [rcx+2Ch]
0x14000fbe7  test    dil, al
0x14000fbea  jz      short loc_14000FC04
0x14000fbec  mov     edx, 0Fh
0x14000fbf1  mov     r9, rsi
0x14000fbf4  lea     r8, WPP_b6c3014efb2237c03ead876b767ed07b_Traceguids
0x14000fbfb  mov     rcx, [rcx+18h]
0x14000fbff  call    WPP_SF_q
0x14000fc04  mov     [rsp+0B8h+rgcbReservation], 20h ; ' '
0x14000fc0d  xor     ecx, ecx
0x14000fc0f  mov     [rsp+0B8h+plsn], rcx; plsn
0x14000fc14  mov     dword ptr [rsp+0B8h+WaitBlockArray], ecx; fFlags
0x14000fc18  lea     rax, [rsp+0B8h+rgcbReservation]
0x14000fc1d  mov     [rsp+0B8h+Timeout], rax; rgcbReservation
0x14000fc22  mov     dword ptr [rsp+0B8h+Alertable], 1; cReserveRecords
0x14000fc2a  mov     qword ptr [rsp+0B8h+WaitMode], rcx; plsnPrevious
0x14000fc2f  xor     r9d, r9d; plsnUndoNext
0x14000fc32  xor     r8d, r8d; cWriteEntries
0x14000fc35  xor     edx, edx; rgWriteEntries
0x14000fc37  mov     rcx, [rsi+0A0h]; pvMarshalContext
0x14000fc3e  call    cs:__imp_ClfsReserveAndAppendLog
0x14000fc45  nop     dword ptr [rax+rax+00h]
0x14000fc4a  mov     ebx, eax
0x14000fc4c  mov     [rsp+0B8h+var_64], eax
0x14000fc50  test    eax, eax
0x14000fc52  js      loc_14000FE73
0x14000fc58  lock or dword ptr [rsi+378h], 2
0x14000fc60  mov     rcx, r12; Resource
0x14000fc63  call    cs:__imp_ExReleaseResourceLite
0x14000fc6a  nop     dword ptr [rax+rax+00h]
0x14000fc6f  mov     [rsp+0B8h+var_68], 0
0x14000fc74  mov     r12d, [rsp+0B8h+var_60]
0x14000fc79  mov     dl, 1; Wait
0x14000fc7b  mov     rcx, r15; Resource
0x14000fc7e  call    cs:__imp_ExAcquireResourceSharedLite
0x14000fc85  nop     dword ptr [rax+rax+00h]
0x14000fc8a  mov     dil, 1
0x14000fc8d  mov     [rsp+0B8h+var_68], dil
0x14000fc92  mov     eax, [rsp+0B8h+arg_20]
0x14000fc99  neg     eax
0x14000fc9b  sbb     edx, edx
0x14000fc9d  and     edx, 2
0x14000fca0  mov     eax, [rsp+0B8h+arg_28]
0x14000fca7  neg     eax
0x14000fca9  sbb     ecx, ecx
0x14000fcab  and     ecx, 4
0x14000fcae  or      edx, ecx
0x14000fcb0  mov     [rsp+0B8h+var_70], r13; plsn
0x14000fcb5  mov     dword ptr [rsp+0B8h+plsn], edx; fFlags
0x14000fcb9  mov     rax, [rsp+0B8h+arg_40]
0x14000fcc1  mov     [rsp+0B8h+WaitBlockArray], rax; rgcbReservation
0x14000fcc6  mov     eax, [rsp+0B8h+cReserveRecords]
0x14000fccd  mov     dword ptr [rsp+0B8h+Timeout], eax; cReserveRecords
0x14000fcd1  mov     qword ptr [rsp+0B8h+Alertable], 0; plsnPrevious
0x14000fcda  mov     qword ptr [rsp+0B8h+WaitMode], 0; plsnUndoNext
0x14000fce3  mov     r9d, 8; cbEntryAlignment
0x14000fce9  mov     r8d, [rsp+0B8h+cWriteEntries]; cWriteEntries
0x14000fcf1  mov     rdx, [rsp+0B8h+rgWriteEntries]; rgWriteEntries
0x14000fcf9  mov     rcx, [rsi+0A0h]; pvMarshalContext
0x14000fd00  call    cs:__imp_ClfsReserveAndAppendLogAligned
0x14000fd07  nop     dword ptr [rax+rax+00h]
0x14000fd0c  mov     ebx, eax
0x14000fd0e  mov     [rsp+0B8h+var_64], eax
0x14000fd12  test    eax, eax
0x14000fd14  js      short loc_14000FD5E
0x14000fd16  lea     rdx, [rsi+288h]; plsn2
0x14000fd1d  mov     rcx, r13; plsn1
0x14000fd20  call    cs:__imp_ClfsLsnGreater
0x14000fd27  nop     dword ptr [rax+rax+00h]
0x14000fd2c  test    al, al
0x14000fd2e  jz      short loc_14000FD50
0x14000fd30  mov     rdx, r13
0x14000fd33  mov     rcx, [rsp+0B8h+arg_0]
0x14000fd3b  call    TmpInsertTransactionLsnList
0x14000fd40  lock or dword ptr [rsi+84h], 100h
0x14000fd4b  jmp     loc_14000FE73
0x14000fd50  mov     ebx, 0C019005Bh
0x14000fd55  mov     [rsp+0B8h+var_64], ebx
0x14000fd59  jmp     loc_14000FE73
0x14000fd5e  cmp     eax, 0C000009Ah
0x14000fd63  jnz     short loc_14000FD94
0x14000fd65  cmp     r12d, 0Ah
0x14000fd69  jnb     short loc_14000FD94
0x14000fd6b  mov     rcx, r15; Resource
0x14000fd6e  call    cs:__imp_ExReleaseResourceLite
0x14000fd75  nop     dword ptr [rax+rax+00h]
0x14000fd7a  mov     [rsp+0B8h+var_68], 0
0x14000fd7f  mov     rbx, [rsp+0B8h+arg_0]
0x14000fd87  mov     dil, [rsp+0B8h+arg_30]
0x14000fd8f  jmp     loc_14000FA74
0x14000fd94  cmp     eax, 0C01A001Dh
0x14000fd99  jnz     loc_14000FE73
0x14000fd9f  mov     [rsp+0B8h+arg_30], dil
0x14000fda7  mov     [rsp+0B8h+var_67], dil
0x14000fdac  mov     rcx, r15; Resource
0x14000fdaf  call    cs:__imp_ExReleaseResourceLite
0x14000fdb6  nop     dword ptr [rax+rax+00h]
0x14000fdbb  xor     ebx, ebx
0x14000fdbd  mov     [rsp+0B8h+var_68], bl
0x14000fdc1  mov     dl, dil; Wait
0x14000fdc4  mov     rcx, r15; Resource
0x14000fdc7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000fdce  nop     dword ptr [rax+rax+00h]
0x14000fdd3  mov     [rsp+0B8h+var_68], dil
0x14000fdd8  mov     eax, [rsi+378h]
0x14000fdde  test    al, 4
0x14000fde0  jnz     short loc_14000FE53
0x14000fde2  lock or dword ptr [rsi+378h], 4
0x14000fdea  lea     rcx, [rsi+2B0h]; Event
0x14000fdf1  call    cs:__imp_KeResetEvent
0x14000fdf8  nop     dword ptr [rax+rax+00h]
0x14000fdfd  mov     rcx, rsi; Object
0x14000fe00  call    cs:__imp_ObfReferenceObject
0x14000fe07  nop     dword ptr [rax+rax+00h]
0x14000fe0c  mov     rcx, r15; Resource
0x14000fe0f  call    cs:__imp_ExReleaseResourceLite
0x14000fe16  nop     dword ptr [rax+rax+00h]
0x14000fe1b  mov     [rsp+0B8h+var_68], bl
0x14000fe1f  mov     rcx, [rsi+0A8h]; Client
0x14000fe26  call    cs:__imp_ClfsMgmtHandleLogFileFull
0x14000fe2d  nop     dword ptr [rax+rax+00h]
0x14000fe32  mov     [rsp+0B8h+var_64], eax
0x14000fe36  cmp     eax, 103h
0x14000fe3b  jz      short loc_14000FE66
0x14000fe3d  mov     r9, rsi
0x14000fe40  xor     r8d, r8d
0x14000fe43  mov     edx, eax
0x14000fe45  mov     rcx, [rsi+98h]
0x14000fe4c  call    TmpLogGrowthCompletedNotification
0x14000fe51  jmp     short loc_14000FE66
0x14000fe53  mov     rcx, r15; Resource
0x14000fe56  call    cs:__imp_ExReleaseResourceLite
0x14000fe5d  nop     dword ptr [rax+rax+00h]
0x14000fe62  mov     [rsp+0B8h+var_68], bl
0x14000fe66  mov     rbx, [rsp+0B8h+arg_0]
0x14000fe6e  jmp     loc_14000FA74
0x14000fe73  test    dil, dil
0x14000fe76  jz      short loc_14000FE87
0x14000fe78  mov     rcx, r15; Resource
0x14000fe7b  call    cs:__imp_ExReleaseResourceLite
0x14000fe82  nop     dword ptr [rax+rax+00h]
0x14000fe87  call    cs:__imp_KeLeaveCriticalRegion
0x14000fe8e  nop     dword ptr [rax+rax+00h]
0x14000fe93  test    r14, r14
0x14000fe96  jz      short loc_14000FEA9
0x14000fe98  xor     edx, edx; Tag
0x14000fe9a  mov     rcx, r14; P
0x14000fe9d  call    cs:__imp_ExFreePoolWithTag
0x14000fea4  nop     dword ptr [rax+rax+00h]
0x14000fea9  mov     eax, ebx
0x14000feab  add     rsp, 80h
0x14000feb2  pop     r15
0x14000feb4  pop     r14
0x14000feb6  pop     r13
0x14000feb8  pop     r12
0x14000feba  pop     rdi
0x14000febb  pop     rsi
0x14000febc  pop     rbx
0x14000febd  retn
0x140021c03  push    rbp
0x140021c05  sub     rsp, 50h
0x140021c09  mov     rbp, rdx
0x140021c0c  cmp     byte ptr [rbp+50h], 0
0x140021c10  jz      short loc_140021C2D
0x140021c12  mov     rcx, [rbp+70h]
0x140021c16  add     rcx, 310h; Resource
0x140021c1d  call    cs:__imp_ExReleaseResourceLite
0x140021c24  nop     dword ptr [rax+rax+00h]
0x140021c29  mov     byte ptr [rbp+50h], 0
0x140021c2d  call    cs:__imp_KeLeaveCriticalRegion
0x140021c34  nop     dword ptr [rax+rax+00h]
0x140021c39  mov     rcx, [rbp+68h]; P
0x140021c3d  test    rcx, rcx
0x140021c40  jz      short loc_140021C51
0x140021c42  xor     edx, edx; Tag
0x140021c44  call    cs:__imp_ExFreePoolWithTag
0x140021c4b  nop     dword ptr [rax+rax+00h]
0x140021c50  nop
0x140021c51  add     rsp, 50h
0x140021c55  pop     rbp
0x140021c56  retn
```
