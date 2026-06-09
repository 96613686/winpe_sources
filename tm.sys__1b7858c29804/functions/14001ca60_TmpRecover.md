# TmpRecover

- ea: `0x14001ca60`
- end: `0x14001d50a`
- name: `TmpRecover`
- size: `2730`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x14001a630`

## callees

- `0x1400011dc`
- `0x140001264`
- `0x140001a0c`
- `0x140001a3c`
- `0x140001aec`
- `0x1400024c2`
- `0x1400024e0`
- `0x140002940`
- `0x14000c9ac`
- `0x14000cbf8`
- `0x14000e288`
- `0x14000e634`
- `0x14000eee4`
- `0x14000f59c`
- `0x140015fc8`
- `0x14001ca60`

## import_xrefs

- `CLFS!ClfsGetLogFileInformation` at `0x14001d2dd`
- `CLFS!ClfsGetLogFileInformation` at `0x14001d2dd`
- `CLFS!ClfsLsnEqual` at `0x14001d307`
- `CLFS!ClfsLsnEqual` at `0x14001d307`
- `CLFS!ClfsReadLogRecord` at `0x14001cbe3`
- `CLFS!ClfsReadLogRecord` at `0x14001d378`
- `CLFS!ClfsReadLogRecord` at `0x14001cbe3`
- `CLFS!ClfsReadLogRecord` at `0x14001d378`
- `CLFS!ClfsReadNextLogRecord` at `0x14001ccbc`
- `CLFS!ClfsReadNextLogRecord` at `0x14001ccbc`
- `CLFS!ClfsTerminateReadLog` at `0x14001d2ae`
- `CLFS!ClfsTerminateReadLog` at `0x14001d481`
- `CLFS!ClfsTerminateReadLog` at `0x1400215e2`
- `CLFS!ClfsTerminateReadLog` at `0x14001d2ae`
- `CLFS!ClfsTerminateReadLog` at `0x14001d481`
- `CLFS!ClfsTerminateReadLog` at `0x1400215e2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d0f9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d0f9`
- `ntoskrnl!KeReleaseMutex` at `0x14001d114`
- `ntoskrnl!KeReleaseMutex` at `0x14001d114`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ce76`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d123`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ce76`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d123`
- `ntoskrnl!ObfReferenceObject` at `0x14001d0d7`
- `ntoskrnl!ObfReferenceObject` at `0x14001d0d7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001cc18`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001cc18`
- `ntoskrnl!ZwClose` at `0x14001d26c`
- `ntoskrnl!ZwClose` at `0x14001d403`
- `ntoskrnl!ZwClose` at `0x14001d467`
- `ntoskrnl!ZwClose` at `0x1400215c2`
- `ntoskrnl!ZwClose` at `0x1400215f6`
- `ntoskrnl!ZwClose` at `0x14001d26c`
- `ntoskrnl!ZwClose` at `0x14001d403`
- `ntoskrnl!ZwClose` at `0x14001d467`
- `ntoskrnl!ZwClose` at `0x1400215c2`
- `ntoskrnl!ZwClose` at `0x1400215f6`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001cb32`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001cb32`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ce51`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ce51`

## pseudocode

```c
NTSTATUS __fastcall TmpRecover(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  PVOID v4; // r13
  int v5; // r12d
  int v6; // r15d
  NTSTATUS result; // eax
  _QWORD *v8; // r14
  NTSTATUS inserted; // edi
  __int64 v10; // r8
  _QWORD *PoolWithTag; // rcx
  _QWORD *v12; // r8
  NTSTATUS v13; // eax
  __int64 v14; // r8
  int v15; // ebx
  int v16; // r8d
  __int64 v17; // r12
  int v18; // ebx
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // r12
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // [rsp+0h] [rbp-1A8h] BYREF
  KPROCESSOR_MODE AccessMode[8]; // [rsp+28h] [rbp-180h]
  int v29; // [rsp+50h] [rbp-158h]
  CLS_RECORD_TYPE peRecordType[4]; // [rsp+54h] [rbp-154h] BYREF
  int v31; // [rsp+58h] [rbp-150h]
  int v32; // [rsp+5Ch] [rbp-14Ch]
  char v33; // [rsp+60h] [rbp-148h] BYREF
  NTSTATUS LogFileInformation; // [rsp+64h] [rbp-144h]
  ULONG pcbReadBuffer; // [rsp+68h] [rbp-140h] BYREF
  HANDLE TransactionHandle; // [rsp+70h] [rbp-138h] BYREF
  int v37; // [rsp+78h] [rbp-130h]
  PVOID pvReadContext; // [rsp+80h] [rbp-128h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp-120h] BYREF
  PVOID ppvReadBuffer; // [rsp+90h] [rbp-118h] BYREF
  ULONG pcbInfoBuffer; // [rsp+98h] [rbp-110h] BYREF
  int v42[2]; // [rsp+A0h] [rbp-108h] BYREF
  int v43[2]; // [rsp+A8h] [rbp-100h] BYREF
  int v44[2]; // [rsp+B0h] [rbp-F8h] BYREF
  CLFS_LSN plsnPrevious; // [rsp+B8h] [rbp-F0h] BYREF
  CLFS_LSN plsnUndoNext; // [rsp+C0h] [rbp-E8h] BYREF
  PVOID Object; // [rsp+C8h] [rbp-E0h] BYREF
  int v48; // [rsp+D0h] [rbp-D8h]
  int v49; // [rsp+D4h] [rbp-D4h]
  int v50; // [rsp+D8h] [rbp-D0h]
  int v51; // [rsp+DCh] [rbp-CCh]
  _QWORD *v52; // [rsp+E0h] [rbp-C8h]
  __int64 *v53; // [rsp+E8h] [rbp-C0h]
  CLFS_INFORMATION pinfoBuffer; // [rsp+F0h] [rbp-B8h] BYREF

  v53 = &v27;
  v2 = a2;
  v52 = a2;
  pvReadContext = 0;
  pcbReadBuffer = 0;
  plsnUndoNext.ullOffset = 0;
  plsnPrevious.ullOffset = 0;
  peRecordType[0] = 0;
  TransactionHandle = 0;
  v33 = 0;
  ppvReadBuffer = 0;
  *(_QWORD *)v42 = 0;
  *(_QWORD *)v44 = 0;
  *(_QWORD *)v43 = 0;
  v29 = 0;
  v37 = 0;
  LODWORD(v4) = 0;
  v31 = 0;
  v5 = 0;
  v32 = 0;
  v6 = 0;
  Handle = 0;
  result = ObOpenObjectByPointer(
             (PVOID)a1,
             0x200u,
             0,
             0xF003Fu,
             (POBJECT_TYPE)TmTransactionManagerObjectType,
             0,
             &Handle);
  if ( result < 0 )
    return result;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_qi(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      23,
      WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids,
      a1,
      *(_QWORD *)(a1 + 656));
  peRecordType[0] = 3;
  v8 = (_QWORD *)(a1 + 656);
  inserted = ClfsReadLogRecord(
               *(PVOID *)(a1 + 160),
               (PCLFS_LSN)(a1 + 656),
               ClfsContextForward,
               &ppvReadBuffer,
               &pcbReadBuffer,
               peRecordType,
               &plsnUndoNext,
               &plsnPrevious,
               &pvReadContext);
  LogFileInformation = inserted;
  if ( inserted )
  {
    if ( inserted == -1073741807 )
      goto LABEL_14;
    goto LABEL_21;
  }
  do
  {
    if ( (peRecordType[0] & 2) != 0 )
    {
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, 0x18u, 0x72526D54u);
      if ( PoolWithTag )
      {
        *PoolWithTag = *v8;
        v12 = *(_QWORD **)(a1 + 920);
        if ( *v12 != a1 + 912 )
          __fastfail(3u);
        PoolWithTag[1] = a1 + 912;
        PoolWithTag[2] = v12;
        *v12 = PoolWithTag + 1;
        *(_QWORD *)(a1 + 920) = PoolWithTag + 1;
        _InterlockedAnd((volatile signed __int32 *)(a1 + 132), 0xFFFFFEFF);
        goto LABEL_10;
      }
      local_unwind_0(v53, &loc_14001D460);
LABEL_21:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 24, v10, (unsigned int)inserted);
      goto LABEL_14;
    }
    TransactionHandle = 0;
    v4 = 0;
    inserted = TmpConstructLogRecordForRecovery(
                 (_DWORD)ppvReadBuffer,
                 pcbReadBuffer,
                 (unsigned int)v42,
                 (unsigned int)v44,
                 (__int64)v43);
    LogFileInformation = inserted;
    if ( inserted < 0 )
    {
      v6 = 1;
      goto LABEL_13;
    }
    v17 = *(_QWORD *)v42;
    if ( v2 && *(_QWORD *)(*(_QWORD *)v42 + 24LL) > *v2 )
      goto LABEL_60;
    *(_QWORD *)(a1 + 664) = *v8;
    v18 = *(_DWORD *)(v17 + 4);
    LOBYTE(v16) = v18 != 4;
    v19 = TmpRecoverTransactionFromLogRecord(
            v17,
            pcbReadBuffer,
            v16,
            (int)Handle,
            a1,
            &TransactionHandle,
            (__int64)&v33);
    inserted = v19;
    LogFileInformation = v19;
    if ( v18 == 4 && v19 == -1073741772 )
    {
      inserted = 0;
      LogFileInformation = 0;
    }
    else if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 25, v20, (unsigned int)v19);
      goto LABEL_56;
    }
    if ( TransactionHandle )
    {
      Object = 0;
      inserted = ObReferenceObjectByHandle(TransactionHandle, 0, (POBJECT_TYPE)TmTransactionObjectType, 0, &Object, 0);
      v4 = Object;
      LogFileInformation = inserted;
      if ( inserted < 0 )
        goto LABEL_60;
      ObfDereferenceObject(Object);
    }
    if ( v4 )
    {
      v21 = *((_QWORD *)v4 + 64);
      if ( v21 )
      {
        if ( v21 != a1 )
        {
          inserted = -1072103341;
          LogFileInformation = -1072103341;
LABEL_60:
          v5 = v32;
LABEL_13:
          LODWORD(v4) = v31;
          goto LABEL_14;
        }
      }
      else
      {
        inserted = TmpInsertTxTransactionManager((PVOID)a1);
        LogFileInformation = inserted;
      }
      if ( *((_QWORD *)v4 + 64) )
      {
        TmpInsertTransactionLsnList(v4, a1 + 656);
        _InterlockedOr((volatile signed __int32 *)(a1 + 132), 0x100u);
      }
      *((_DWORD *)v4 + 48) = 10;
    }
    switch ( *(_DWORD *)(v17 + 4) )
    {
      case 2:
        _InterlockedOr((volatile signed __int32 *)v4 + 49, 0x100000u);
        v15 = v29 + 1;
        v29 = v15;
        v51 = v15;
        if ( v33 == 1 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 26, WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids);
          inserted = -1072103376;
          LogFileInformation = -1072103376;
        }
        else
        {
          inserted = TmpRecoverAllEnlistmentRecordsInLogRecord(
                       v17,
                       pcbReadBuffer,
                       v44[0],
                       v43[0],
                       (__int64)TransactionHandle,
                       *(HANDLE *)AccessMode,
                       v33,
                       (__int64)Handle,
                       a1);
          LogFileInformation = inserted;
          if ( inserted >= 0 )
          {
            *((_DWORD *)v4 + 48) = 4;
            *((_QWORD *)v4 + 65) = pcbReadBuffer;
LABEL_84:
            v5 = v32;
            goto LABEL_50;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 27, v24, (unsigned int)inserted);
            v5 = v32;
            LODWORD(v4) = v31;
            goto LABEL_93;
          }
        }
        v5 = v32;
        LODWORD(v4) = v31;
        goto LABEL_93;
      case 3:
        _InterlockedOr((volatile signed __int32 *)v4 + 49, 0x200000u);
        v50 = ++v37;
        *(_QWORD *)(a1 + 584) = *(_QWORD *)(v17 + 24);
        if ( !v33 )
        {
          inserted = TmpRecoverAllEnlistmentRecordsInLogRecord(
                       v17,
                       pcbReadBuffer,
                       v44[0],
                       v43[0],
                       (__int64)TransactionHandle,
                       *(HANDLE *)AccessMode,
                       0,
                       (__int64)Handle,
                       a1);
          LogFileInformation = inserted;
          if ( inserted < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 28, v22, (unsigned int)inserted);
              v5 = v32;
              LODWORD(v4) = v31;
              goto LABEL_14;
            }
LABEL_56:
            v5 = v32;
LABEL_57:
            LODWORD(v4) = v31;
            goto LABEL_14;
          }
        }
        *((_DWORD *)v4 + 48) = 5;
        v23 = *((_QWORD *)v4 + 30);
        if ( v23 )
        {
          ObfReferenceObject(*((PVOID *)v4 + 30));
          KeWaitForSingleObject((PVOID)(v23 + 64), Executive, 0, 0, 0);
          TmpFinalizeEnlistment((PVOID)v23);
          KeReleaseMutex((PRKMUTEX)(v23 + 64), 0);
          ObfDereferenceObject((PVOID)v23);
        }
        *((_DWORD *)v4 + 59) = *((_DWORD *)v4 + 54);
        *((_DWORD *)v4 + 126) = 2;
        *((_QWORD *)v4 + 65) = 0;
        break;
      case 4:
        v48 = ++v31;
        if ( TransactionHandle )
        {
          *((_QWORD *)v4 + 65) = 0;
          inserted = TmpForgetTransaction(v4);
          LogFileInformation = inserted;
          v5 = v32;
          if ( inserted < 0 )
            goto LABEL_13;
          v5 = v32 + 1;
          v32 = v5;
          v49 = v5;
          goto LABEL_49;
        }
        break;
      default:
        if ( *(_DWORD *)(v17 + 4) == 7 || WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          break;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0 )
        {
          v15 = v29;
          goto LABEL_84;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 29, v20, *(unsigned int *)(v17 + 4));
        break;
    }
    v5 = v32;
LABEL_49:
    v15 = v29;
LABEL_50:
    if ( inserted )
    {
      LODWORD(v4) = v31;
      goto LABEL_93;
    }
    v2 = v52;
LABEL_10:
    if ( TransactionHandle )
    {
      ZwClose(TransactionHandle);
      TransactionHandle = 0;
    }
    peRecordType[0] = 3;
    v13 = ClfsReadNextLogRecord(
            pvReadContext,
            &ppvReadBuffer,
            &pcbReadBuffer,
            peRecordType,
            0,
            &plsnUndoNext,
            &plsnPrevious,
            (PCLFS_LSN)(a1 + 656));
    inserted = v13;
    LogFileInformation = v13;
    if ( v13 == -1073741807 )
      goto LABEL_13;
    if ( v13 == -1072037869 )
    {
      memset(&pinfoBuffer, 0, sizeof(pinfoBuffer));
      pcbInfoBuffer = 120;
      ClfsTerminateReadLog(pvReadContext);
      pvReadContext = 0;
      LogFileInformation = ClfsGetLogFileInformation(*(PLOG_FILE_OBJECT *)(a1 + 152), &pinfoBuffer, &pcbInfoBuffer);
      *(_QWORD *)(a1 + 656) = pinfoBuffer.BaseLsn.ullOffset;
      if ( ClfsLsnEqual((const CLFS_LSN *)(a1 + 656), &pinfoBuffer.LastLsn) )
      {
        inserted = -1073741807;
        LogFileInformation = -1073741807;
        goto LABEL_13;
      }
      inserted = ClfsReadLogRecord(
                   *(PVOID *)(a1 + 160),
                   (PCLFS_LSN)(a1 + 656),
                   ClfsContextForward,
                   &ppvReadBuffer,
                   &pcbReadBuffer,
                   peRecordType,
                   &plsnUndoNext,
                   &plsnPrevious,
                   &pvReadContext);
      LogFileInformation = inserted;
      if ( inserted < 0 )
        goto LABEL_13;
    }
  }
  while ( !inserted );
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0 )
    goto LABEL_57;
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 30, v14, (unsigned int)inserted);
  LODWORD(v4) = v31;
LABEL_14:
  v15 = v29;
LABEL_93:
  if ( TransactionHandle )
  {
    ZwClose(TransactionHandle);
    TransactionHandle = 0;
  }
  if ( pvReadContext )
    ClfsTerminateReadLog(pvReadContext);
  ZwClose(Handle);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
    WPP_SF_qdddd(*((_QWORD *)WPP_GLOBAL_Control + 3), v25, v26, a1, v37, v15, (_DWORD)v4, v5);
  if ( v6 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 32, v26, a1, v6);
  if ( inserted == -1072103339 )
  {
    if ( TmpShutdownOccurred )
      return -1073741077;
  }
  return inserted;
}

```

## disassembly

```asm
0x14001ca60  mov     r11, rsp
0x14001ca63  mov     [r11+10h], rbx
0x14001ca67  mov     [r11+18h], rsi
0x14001ca6b  push    rdi
0x14001ca6c  push    r12
0x14001ca6e  push    r13
0x14001ca70  push    r14
0x14001ca72  push    r15
0x14001ca74  sub     rsp, 180h
0x14001ca7b  mov     rax, cs:__security_cookie
0x14001ca82  xor     rax, rsp
0x14001ca85  mov     [rsp+1A8h+var_38], rax
0x14001ca8d  mov     [rsp+1A8h+var_C0], rsp
0x14001ca95  mov     rbx, rdx
0x14001ca98  mov     [rsp+1A8h+var_C8], rdx
0x14001caa0  mov     rsi, rcx
0x14001caa3  xor     eax, eax
0x14001caa5  mov     [r11-128h], rax
0x14001caac  mov     [rsp+1A8h+pcbReadBuffer], eax
0x14001cab0  mov     [r11-0E8h], rax
0x14001cab7  mov     [r11-0F0h], rax
0x14001cabe  mov     [rsp+1A8h+peRecordType], al
0x14001cac2  mov     [rsp+1A8h+TransactionHandle], rax
0x14001cac7  mov     byte ptr [rsp+1A8h+var_148], al
0x14001cacb  mov     [r11-118h], rax
0x14001cad2  mov     [r11-108h], rax
0x14001cad9  mov     [r11-0F8h], rax
0x14001cae0  mov     [r11-100h], rax
0x14001cae7  mov     [rsp+1A8h+var_158], eax
0x14001caeb  mov     [rsp+1A8h+var_130], eax
0x14001caef  mov     r13d, eax
0x14001caf2  mov     [rsp+1A8h+var_150], eax
0x14001caf6  mov     r12d, eax
0x14001caf9  mov     [rsp+1A8h+var_14C], eax
0x14001cafd  mov     r15d, eax
0x14001cb00  mov     [r11-120h], rax
0x14001cb07  lea     rax, [r11-120h]
0x14001cb0e  mov     [rsp+1A8h+Handle], rax; Handle
0x14001cb13  mov     [rsp+1A8h+AccessMode], r12b; AccessMode
0x14001cb18  mov     rax, cs:TmTransactionManagerObjectType
0x14001cb1f  mov     [rsp+1A8h+ObjectType], rax; ObjectType
0x14001cb24  mov     r9d, 0F003Fh; DesiredAccess
0x14001cb2a  xor     r8d, r8d; PassedAccessState
0x14001cb2d  mov     edx, 200h; HandleAttributes
0x14001cb32  call    cs:__imp_ObOpenObjectByPointer
0x14001cb39  nop     dword ptr [rax+rax+00h]
0x14001cb3e  test    eax, eax
0x14001cb40  js      loc_14001D432
0x14001cb46  lea     rax, WPP_GLOBAL_Control
0x14001cb4d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cb54  cmp     rcx, rax
0x14001cb57  jz      short loc_14001CB84
0x14001cb59  mov     eax, [rcx+2Ch]
0x14001cb5c  test    al, 1
0x14001cb5e  jz      short loc_14001CB84
0x14001cb60  mov     edx, 17h
0x14001cb65  mov     rax, [rsi+290h]
0x14001cb6c  mov     [rsp+1A8h+ObjectType], rax
0x14001cb71  mov     r9, rsi
0x14001cb74  lea     r8, WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids
0x14001cb7b  mov     rcx, [rcx+18h]
0x14001cb7f  call    WPP_SF_qi
0x14001cb84  mov     [rsp+1A8h+peRecordType], 3
0x14001cb89  lea     r14, [rsi+290h]
0x14001cb90  lea     rax, [rsp+1A8h+pvReadContext]
0x14001cb98  mov     [rsp+1A8h+ppvReadContext], rax; ppvReadContext
0x14001cb9d  lea     rax, [rsp+1A8h+var_F0]
0x14001cba5  mov     [rsp+1A8h+plsnPrevious], rax; plsnPrevious
0x14001cbaa  lea     rax, [rsp+1A8h+plsnUndoNext]
0x14001cbb2  mov     [rsp+1A8h+Handle], rax; plsnUndoNext
0x14001cbb7  lea     rax, [rsp+1A8h+peRecordType]
0x14001cbbc  mov     qword ptr [rsp+1A8h+AccessMode], rax; peRecordType
0x14001cbc1  lea     rax, [rsp+1A8h+pcbReadBuffer]
0x14001cbc6  mov     [rsp+1A8h+ObjectType], rax; pcbReadBuffer
0x14001cbcb  lea     r9, [rsp+1A8h+ppvReadBuffer]; ppvReadBuffer
0x14001cbd3  mov     r8d, 3; peContextMode
0x14001cbd9  mov     rdx, r14; plsnFirst
0x14001cbdc  mov     rcx, [rsi+0A0h]; pvMarshalContext
0x14001cbe3  call    cs:__imp_ClfsReadLogRecord
0x14001cbea  nop     dword ptr [rax+rax+00h]
0x14001cbef  mov     edi, eax
0x14001cbf1  mov     dword ptr [rsp+1A8h+var_148+4], eax
0x14001cbf5  test    eax, eax
0x14001cbf7  jnz     loc_14001CCEA
0x14001cbfd  test    [rsp+1A8h+peRecordType], 2
0x14001cc02  jz      loc_14001CD54
0x14001cc08  mov     edx, 18h; NumberOfBytes
0x14001cc0d  mov     ecx, 1; PoolType
0x14001cc12  mov     r8d, 72526D54h; Tag
0x14001cc18  call    cs:__imp_ExAllocatePoolWithTag
0x14001cc1f  nop     dword ptr [rax+rax+00h]
0x14001cc24  mov     rcx, rax
0x14001cc27  test    rax, rax
0x14001cc2a  jz      loc_14001CD0C
0x14001cc30  mov     rax, [r14]
0x14001cc33  mov     [rcx], rax
0x14001cc36  lea     rdx, [rsi+390h]
0x14001cc3d  mov     r8, [rdx+8]
0x14001cc41  cmp     [r8], rdx
0x14001cc44  jnz     loc_14001CD4D
0x14001cc4a  lea     rax, [rcx+8]
0x14001cc4e  mov     [rax], rdx
0x14001cc51  mov     [rax+8], r8
0x14001cc55  mov     [r8], rax
0x14001cc58  mov     [rdx+8], rax
0x14001cc5c  lock and dword ptr [rsi+84h], 0FFFFFEFFh
0x14001cc67  mov     rcx, [rsp+1A8h+TransactionHandle]; Handle
0x14001cc6c  test    rcx, rcx
0x14001cc6f  jnz     loc_14001D26C
0x14001cc75  mov     [rsp+1A8h+peRecordType], 3
0x14001cc7a  mov     [rsp+1A8h+plsnPrevious], r14; plsnRecord
0x14001cc7f  lea     rax, [rsp+1A8h+var_F0]
0x14001cc87  mov     [rsp+1A8h+Handle], rax; plsnPrevious
0x14001cc8c  lea     rax, [rsp+1A8h+plsnUndoNext]
0x14001cc94  mov     qword ptr [rsp+1A8h+AccessMode], rax; plsnUndoNext
0x14001cc99  mov     [rsp+1A8h+ObjectType], 0; plsnUser
0x14001cca2  lea     r9, [rsp+1A8h+peRecordType]; peRecordType
0x14001cca7  lea     r8, [rsp+1A8h+pcbReadBuffer]; pcbBuffer
0x14001ccac  lea     rdx, [rsp+1A8h+ppvReadBuffer]; ppvBuffer
0x14001ccb4  mov     rcx, [rsp+1A8h+pvReadContext]; pvReadContext
0x14001ccbc  call    cs:__imp_ClfsReadNextLogRecord
0x14001ccc3  nop     dword ptr [rax+rax+00h]
0x14001ccc8  mov     edi, eax
0x14001ccca  mov     dword ptr [rsp+1A8h+var_148+4], eax
0x14001ccce  cmp     eax, 0C0000011h
0x14001ccd3  jnz     short loc_14001CCF4
0x14001ccd5  mov     r13d, [rsp+1A8h+var_150]
0x14001ccda  lea     r14, WPP_GLOBAL_Control
0x14001cce1  mov     ebx, [rsp+1A8h+var_158]
0x14001cce5  jmp     loc_14001D3E0
0x14001ccea  cmp     edi, 0C0000011h
0x14001ccf0  jz      short loc_14001CCDA
0x14001ccf2  jmp     short loc_14001CD20
0x14001ccf4  cmp     eax, 0C01A0013h
0x14001ccf9  jz      loc_14001D286
0x14001ccff  test    edi, edi
0x14001cd01  jnz     loc_14001D397
0x14001cd07  jmp     loc_14001CBFD
0x14001cd0c  lea     rdx, loc_14001D460
0x14001cd13  mov     rcx, [rsp+1A8h+var_C0]
0x14001cd1b  call    _local_unwind_0
0x14001cd20  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd27  lea     r14, WPP_GLOBAL_Control
0x14001cd2e  cmp     rcx, r14
0x14001cd31  jz      short loc_14001CCE1
0x14001cd33  mov     eax, [rcx+2Ch]
0x14001cd36  test    al, 8
0x14001cd38  jz      short loc_14001CCE1
0x14001cd3a  mov     edx, 18h
0x14001cd3f  mov     r9d, edi
0x14001cd42  mov     rcx, [rcx+18h]
0x14001cd46  call    WPP_SF_d
0x14001cd4b  jmp     short loc_14001CCE1
0x14001cd4d  mov     ecx, 3
0x14001cd52  int     29h; Win8: RtlFailFast(ecx)
0x14001cd54  mov     [rsp+1A8h+TransactionHandle], 0
0x14001cd5d  xor     r13d, r13d
0x14001cd60  lea     rax, [rsp+1A8h+var_100]
0x14001cd68  mov     [rsp+1A8h+ObjectType], rax
0x14001cd6d  lea     r9, [rsp+1A8h+var_F8]
0x14001cd75  lea     r8, [rsp+1A8h+var_108]
0x14001cd7d  mov     edx, [rsp+1A8h+pcbReadBuffer]
0x14001cd81  mov     rcx, [rsp+1A8h+ppvReadBuffer]
0x14001cd89  call    TmpConstructLogRecordForRecovery
0x14001cd8e  mov     edi, eax
0x14001cd90  mov     dword ptr [rsp+1A8h+var_148+4], eax
0x14001cd94  test    eax, eax
0x14001cd96  jns     short loc_14001CDA3
0x14001cd98  mov     r15d, 1
0x14001cd9e  jmp     loc_14001CCD5
0x14001cda3  mov     r12, qword ptr [rsp+1A8h+var_108]
0x14001cdab  test    rbx, rbx
0x14001cdae  jz      short loc_14001CDBE
0x14001cdb0  mov     rax, [rbx]
0x14001cdb3  cmp     [r12+18h], rax
0x14001cdb8  jg      loc_14001CF99
0x14001cdbe  mov     rax, [r14]
0x14001cdc1  mov     [rsi+298h], rax
0x14001cdc8  mov     ebx, [r12+4]
0x14001cdcd  cmp     ebx, 4
0x14001cdd0  setnz   r8b; int
0x14001cdd4  lea     rax, [rsp+1A8h+var_148]
0x14001cdd9  mov     [rsp+1A8h+Handle], rax; __int64
0x14001cdde  lea     rax, [rsp+1A8h+TransactionHandle]
0x14001cde3  mov     qword ptr [rsp+1A8h+AccessMode], rax; TransactionHandle
0x14001cde8  mov     [rsp+1A8h+ObjectType], rsi; __int64
0x14001cded  mov     r9, [rsp+1A8h+var_120]; int
0x14001cdf5  mov     edx, [rsp+1A8h+pcbReadBuffer]; int
0x14001cdf9  mov     rcx, r12; int
0x14001cdfc  call    TmpRecoverTransactionFromLogRecord
0x14001ce01  mov     edi, eax
0x14001ce03  mov     dword ptr [rsp+1A8h+var_148+4], eax
0x14001ce07  cmp     ebx, 4
0x14001ce0a  jnz     loc_14001CF45
0x14001ce10  cmp     eax, 0C0000034h
0x14001ce15  jnz     loc_14001CF45
0x14001ce1b  xor     edi, edi
0x14001ce1d  mov     dword ptr [rsp+1A8h+var_148+4], edi
0x14001ce21  mov     rcx, [rsp+1A8h+TransactionHandle]; Handle
0x14001ce26  test    rcx, rcx
0x14001ce29  jz      short loc_14001CE82
0x14001ce2b  mov     r8, cs:TmTransactionObjectType; ObjectType
0x14001ce32  mov     [rsp+1A8h+Object], r13
0x14001ce3a  mov     qword ptr [rsp+1A8h+AccessMode], r13; HANDLE
0x14001ce3f  lea     rax, [rsp+1A8h+Object]
0x14001ce47  mov     [rsp+1A8h+ObjectType], rax; Object
0x14001ce4c  xor     r9d, r9d; AccessMode
0x14001ce4f  xor     edx, edx; DesiredAccess
0x14001ce51  call    cs:__imp_ObReferenceObjectByHandle
0x14001ce58  nop     dword ptr [rax+rax+00h]
0x14001ce5d  mov     edi, eax
0x14001ce5f  mov     r13, [rsp+1A8h+Object]
0x14001ce67  mov     dword ptr [rsp+1A8h+var_148+4], eax
0x14001ce6b  test    eax, eax
0x14001ce6d  js      loc_14001CF99
0x14001ce73  mov     rcx, r13; Object
0x14001ce76  call    cs:__imp_ObfDereferenceObject
0x14001ce7d  nop     dword ptr [rax+rax+00h]
0x14001ce82  test    r13, r13
0x14001ce85  jz      short loc_14001CED3
0x14001ce87  mov     rax, [r13+200h]
0x14001ce8e  test    rax, rax
0x14001ce91  jnz     loc_14001CF87
0x14001ce97  mov     rdx, r13
0x14001ce9a  mov     rcx, rsi; Object
0x14001ce9d  call    TmpInsertTxTransactionManager
0x14001cea2  mov     edi, eax
0x14001cea4  mov     dword ptr [rsp+1A8h+var_148+4], eax
0x14001cea8  cmp     qword ptr [r13+200h], 0
0x14001ceb0  jz      short loc_14001CEC8
0x14001ceb2  mov     rdx, r14
0x14001ceb5  mov     rcx, r13
0x14001ceb8  call    TmpInsertTransactionLsnList
0x14001cebd  lock or dword ptr [rsi+84h], 100h
0x14001cec8  mov     dword ptr [r13+0C0h], 0Ah
0x14001ced3  mov     r9d, [r12+4]
0x14001ced8  mov     ecx, r9d
0x14001cedb  sub     ecx, 2
0x14001cede  jz      loc_14001D158
0x14001cee4  sub     ecx, 1
0x14001cee7  jz      loc_14001D000
0x14001ceed  sub     ecx, 1
0x14001cef0  jz      loc_14001CFA3
0x14001cef6  cmp     ecx, 3
0x14001cef9  jz      short loc_14001CF27
0x14001cefb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cf02  lea     rax, WPP_GLOBAL_Control
0x14001cf09  cmp     rcx, rax
0x14001cf0c  jz      short loc_14001CF27
0x14001cf0e  mov     eax, [rcx+2Ch]
0x14001cf11  test    al, 8
0x14001cf13  jz      loc_14001D25E
0x14001cf19  mov     edx, 1Dh
0x14001cf1e  mov     rcx, [rcx+18h]
0x14001cf22  call    WPP_SF_d
0x14001cf27  mov     r12d, [rsp+1A8h+var_14C]
0x14001cf2c  mov     ebx, [rsp+1A8h+var_158]
0x14001cf30  test    edi, edi
0x14001cf32  jnz     loc_14001D3D4
0x14001cf38  mov     rbx, [rsp+1A8h+var_C8]
0x14001cf40  jmp     loc_14001CC67
0x14001cf45  test    edi, edi
0x14001cf47  jns     loc_14001CE21
0x14001cf4d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cf54  lea     r14, WPP_GLOBAL_Control
0x14001cf5b  cmp     rcx, r14
0x14001cf5e  jz      short loc_14001CF78
0x14001cf60  mov     eax, [rcx+2Ch]
0x14001cf63  test    al, 8
0x14001cf65  jz      short loc_14001CF78
0x14001cf67  mov     edx, 19h
0x14001cf6c  mov     r9d, edi
0x14001cf6f  mov     rcx, [rcx+18h]
0x14001cf73  call    WPP_SF_d
0x14001cf78  mov     r12d, [rsp+1A8h+var_14C]
0x14001cf7d  mov     r13d, [rsp+1A8h+var_150]
0x14001cf82  jmp     loc_14001CCE1
0x14001cf87  cmp     rax, rsi
0x14001cf8a  jz      loc_14001CEA8
0x14001cf90  mov     edi, 0C0190053h
0x14001cf95  mov     dword ptr [rsp+1A8h+var_148+4], edi
0x14001cf99  mov     r12d, [rsp+1A8h+var_14C]
0x14001cf9e  jmp     loc_14001CCD5
0x14001cfa3  mov     eax, [rsp+1A8h+var_150]
0x14001cfa7  inc     eax
0x14001cfa9  mov     [rsp+1A8h+var_150], eax
0x14001cfad  mov     [rsp+1A8h+var_D8], eax
0x14001cfb4  cmp     [rsp+1A8h+TransactionHandle], 0
0x14001cfba  jz      loc_14001CF27
0x14001cfc0  mov     qword ptr [r13+208h], 0
0x14001cfcb  xor     r8d, r8d
0x14001cfce  xor     edx, edx
0x14001cfd0  mov     rcx, r13; Object
0x14001cfd3  call    TmpForgetTransaction
0x14001cfd8  mov     edi, eax
0x14001cfda  mov     dword ptr [rsp+1A8h+var_148+4], eax
0x14001cfde  mov     r12d, [rsp+1A8h+var_14C]
0x14001cfe3  test    eax, eax
0x14001cfe5  js      loc_14001CCD5
0x14001cfeb  inc     r12d
  ... truncated ...
```
