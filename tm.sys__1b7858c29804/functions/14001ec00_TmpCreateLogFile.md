# TmpCreateLogFile

- ea: `0x14001ec00`
- end: `0x14001f36d`
- name: `TmpCreateLogFile`
- size: `1901`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14001ebb8`

## callees

- `0x140001618`
- `0x140001a3c`
- `0x140001aec`
- `0x140001b84`
- `0x1400024e0`
- `0x140002940`
- `0x14001d690`
- `0x14001dc64`
- `0x14001ea40`
- `0x14001ec00`
- `0x140021084`

## import_xrefs

- `CLFS!ClfsReserveAndAppendLog` at `0x14001f008`
- `CLFS!ClfsReserveAndAppendLog` at `0x14001f008`
- `CLFS!ClfsGetLogFileInformation` at `0x14001f088`
- `CLFS!ClfsGetLogFileInformation` at `0x14001f088`
- `CLFS!ClfsReadLogRecord` at `0x14001f172`
- `CLFS!ClfsReadLogRecord` at `0x14001f172`
- `CLFS!ClfsTerminateReadLog` at `0x14001f2ee`
- `CLFS!ClfsTerminateReadLog` at `0x14002189e`
- `CLFS!ClfsTerminateReadLog` at `0x14001f2ee`
- `CLFS!ClfsTerminateReadLog` at `0x14002189e`
- `CLFS!ClfsCreateLogFile` at `0x14001edb4`
- `CLFS!ClfsCreateLogFile` at `0x14001ee0b`
- `CLFS!ClfsCreateLogFile` at `0x14001edb4`
- `CLFS!ClfsCreateLogFile` at `0x14001ee0b`
- `CLFS!ClfsCreateMarshallingArea` at `0x14001ef85`
- `CLFS!ClfsCreateMarshallingArea` at `0x14001ef85`
- `CLFS!ClfsReadRestartArea` at `0x14001f0d9`
- `CLFS!ClfsReadRestartArea` at `0x14001f0d9`
- `CLFS!ClfsDeleteMarshallingArea` at `0x14001f320`
- `CLFS!ClfsDeleteMarshallingArea` at `0x140021906`
- `CLFS!ClfsDeleteMarshallingArea` at `0x14001f320`
- `CLFS!ClfsDeleteMarshallingArea` at `0x140021906`
- `CLFS!ClfsCloseLogFileObject` at `0x14001f33f`
- `CLFS!ClfsCloseLogFileObject` at `0x14002192e`
- `CLFS!ClfsCloseLogFileObject` at `0x14001f33f`
- `CLFS!ClfsCloseLogFileObject` at `0x14002192e`
- `CLFS!ClfsMgmtDeregisterManagedClient` at `0x14001f35a`
- `CLFS!ClfsMgmtDeregisterManagedClient` at `0x140021951`
- `CLFS!ClfsMgmtDeregisterManagedClient` at `0x14001f35a`
- `CLFS!ClfsMgmtDeregisterManagedClient` at `0x140021951`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f2d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002187e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f2d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002187e`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14001ed07`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14001ed07`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001ed2b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001ed2b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001ed43`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001ed57`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001ed43`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001ed57`

## pseudocode

```c
__int64 __fastcall TmpCreateLogFile(__int64 a1)
{
  int v2; // edx
  void *v4; // r12
  char v5; // r13
  SIZE_T v6; // rdx
  NTSTATUS appended; // ebx
  PLOG_FILE_OBJECT *v8; // r15
  __int64 v9; // r8
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  PVOID *v13; // r14
  __int64 v14; // r8
  NTSTATUS v15; // eax
  __int64 v16; // r8
  CLS_LSN BaseLsn; // rax
  NTSTATUS v18; // eax
  char v19; // al
  __int64 v20; // rcx
  void *v21; // rcx
  FILE_OBJECT *v22; // rcx
  CLS_RECORD_TYPE peRecordType[4]; // [rsp+60h] [rbp-138h] BYREF
  NTSTATUS LogFileInformation; // [rsp+64h] [rbp-134h]
  char v25; // [rsp+68h] [rbp-130h]
  UNICODE_STRING DestinationString; // [rsp+70h] [rbp-128h] BYREF
  PVOID ppvReadContext; // [rsp+80h] [rbp-118h] BYREF
  ULONG pcbInfoBuffer; // [rsp+88h] [rbp-110h] BYREF
  ULONG pcbRestartBuffer; // [rsp+8Ch] [rbp-10Ch] BYREF
  ULONG pcbReadBuffer; // [rsp+90h] [rbp-108h] BYREF
  PVOID ppvRestartBuffer; // [rsp+98h] [rbp-100h] BYREF
  __int64 rgcbReservation[2]; // [rsp+A0h] [rbp-F8h] BYREF
  CLFS_LSN plsn; // [rsp+B0h] [rbp-E8h] BYREF
  CLFS_LSN plsnPrevious; // [rsp+B8h] [rbp-E0h] BYREF
  CLFS_LSN plsnUndoNext; // [rsp+C0h] [rbp-D8h] BYREF
  PVOID ppvReadBuffer[3]; // [rsp+C8h] [rbp-D0h] BYREF
  CLFS_INFORMATION pinfoBuffer; // [rsp+E0h] [rbp-B8h] BYREF

  ppvReadBuffer[1] = (PVOID)a1;
  DestinationString = 0;
  ppvRestartBuffer = 0;
  pcbRestartBuffer = 0;
  ppvReadContext = 0;
  plsn.ullOffset = 0;
  rgcbReservation[0] = 0;
  memset(&pinfoBuffer, 0, sizeof(pinfoBuffer));
  pcbInfoBuffer = 120;
  peRecordType[0] = 0;
  v2 = *(unsigned __int16 *)(a1 + 136);
  if ( v2 + (unsigned int)TmpLogPrefix.Length > 0xFFFF )
    return 2147483653LL;
  LogFileInformation = 0;
  v4 = 0;
  rgcbReservation[1] = 0;
  v25 = 0;
  v5 = 0;
  v6 = (unsigned __int16)(TmpLogPrefix.Length + v2);
  DestinationString.MaximumLength = v6;
  DestinationString.Buffer = (wchar_t *)ExAllocatePoolWithQuotaTag((POOL_TYPE)9, v6, 0x6E4C6D54u);
  if ( !DestinationString.Buffer )
    return 3221225626LL;
  RtlCopyUnicodeString(&DestinationString, 0);
  RtlAppendUnicodeStringToString(&DestinationString, &TmpLogPrefix);
  appended = RtlAppendUnicodeStringToString(&DestinationString, (PCUNICODE_STRING)(a1 + 136));
  LogFileInformation = appended;
  if ( appended >= 0 )
  {
    v8 = (PLOG_FILE_OBJECT *)(a1 + 152);
    appended = ClfsCreateLogFile(
                 (PPLOG_FILE_OBJECT)(a1 + 152),
                 &DestinationString,
                 0xC0000000,
                 3u,
                 0,
                 1u,
                 0,
                 0,
                 0,
                 0,
                 0);
    LogFileInformation = appended;
    if ( appended == -1073741772 )
    {
      v5 = 1;
      appended = ClfsCreateLogFile(
                   (PPLOG_FILE_OBJECT)(a1 + 152),
                   &DestinationString,
                   0xC0000000,
                   3u,
                   0,
                   2u,
                   0,
                   0,
                   0,
                   0,
                   0);
      LogFileInformation = appended;
      if ( appended )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0 )
          goto LABEL_68;
        v11 = 33;
        goto LABEL_11;
      }
    }
    else if ( appended < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0 )
        goto LABEL_68;
      v11 = 34;
LABEL_11:
      WPP_SF_d(v10[3], v11, v9, (unsigned int)appended);
      goto LABEL_68;
    }
    appended = TmpIsClusteredTransactionManager(a1, peRecordType);
    LogFileInformation = appended;
    if ( appended < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 35, v12, (unsigned int)appended);
      goto LABEL_68;
    }
    if ( peRecordType[0] )
    {
      _InterlockedOr((volatile signed __int32 *)(a1 + 128), 0x100u);
      TmpStartKtmRm();
    }
    appended = TmpRegisterForLogManagement(a1);
    LogFileInformation = appended;
    if ( appended == -1073741771 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          36,
          WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids,
          a1,
          -1073741771);
      appended = -1072103376;
      LogFileInformation = -1072103376;
    }
    if ( appended < 0 )
      goto LABEL_68;
    v13 = (PVOID *)(a1 + 160);
    appended = ClfsCreateMarshallingArea(*v8, PagedPool, 0, 0, 0x10000u, 0x14u, 1u, (PVOID *)(a1 + 160));
    LogFileInformation = appended;
    if ( appended )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 37, v14, (unsigned int)appended);
      goto LABEL_68;
    }
    rgcbReservation[0] = 32;
    v15 = ClfsReserveAndAppendLog(*v13, 0, 0, 0, 0, 1u, rgcbReservation, 0, 0);
    LogFileInformation = v15;
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 38, v16, a1, v15);
    }
    else
    {
      _InterlockedOr((volatile signed __int32 *)(a1 + 888), 2u);
    }
    if ( v5 )
    {
      appended = TmpWriteRestartArea(a1, 0, 0);
      LogFileInformation = appended;
      if ( appended < 0 )
        goto LABEL_68;
      goto LABEL_64;
    }
    LogFileInformation = ClfsGetLogFileInformation(*v8, &pinfoBuffer, &pcbInfoBuffer);
    BaseLsn = pinfoBuffer.BaseLsn;
    *(_QWORD *)(a1 + 656) = pinfoBuffer.BaseLsn.ullOffset;
    *(CLS_LSN *)(a1 + 648) = BaseLsn;
    appended = ClfsReadRestartArea(*v13, &ppvRestartBuffer, &pcbRestartBuffer, &plsn, &ppvReadContext);
    LogFileInformation = appended;
    if ( appended != 1075445772 )
    {
      if ( appended < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            40,
            WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids,
            a1,
            appended);
        appended = -1072103376;
        goto LABEL_54;
      }
      v19 = 1;
LABEL_56:
      if ( !v19 )
        goto LABEL_64;
      if ( (*(_DWORD *)(a1 + 128) & 0x20) != 0 )
      {
        appended = TmpNamespaceRename(&TmpTmNamespace);
        LogFileInformation = appended;
        if ( appended < 0 )
          goto LABEL_68;
        _InterlockedAnd((volatile signed __int32 *)(a1 + 128), 0xFFFFFFDF);
        goto LABEL_64;
      }
      v20 = *(_QWORD *)((char *)ppvRestartBuffer + 12) - *(_QWORD *)(a1 + 112);
      if ( !v20 )
        v20 = *(_QWORD *)((char *)ppvRestartBuffer + 20) - *(_QWORD *)(a1 + 120);
      if ( !v20 )
      {
LABEL_64:
        if ( !appended )
          goto LABEL_68;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0 )
          goto LABEL_68;
        v11 = 41;
        goto LABEL_11;
      }
      appended = -1072103350;
LABEL_54:
      LogFileInformation = appended;
      goto LABEL_68;
    }
    plsnUndoNext.ullOffset = 0;
    plsnPrevious.ullOffset = 0;
    ppvReadBuffer[0] = 0;
    pcbReadBuffer = 0;
    peRecordType[0] = 3;
    v18 = ClfsReadLogRecord(
            *v13,
            (PCLFS_LSN)(a1 + 656),
            ClfsContextForward,
            ppvReadBuffer,
            &pcbReadBuffer,
            peRecordType,
            &plsnUndoNext,
            &plsnPrevious,
            &ppvReadContext);
    LogFileInformation = v18;
    if ( v18 != -1072037869 && v18 != -1073741807 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 3), 39, WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids, a1, v18);
      appended = -1072103376;
      LogFileInformation = -1072103376;
      goto LABEL_68;
    }
    appended = TmpWriteRestartArea(a1, 0, 0);
    LogFileInformation = appended;
    if ( appended >= 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)(a1 + 128), 0xFFFFFFDF);
      v19 = v25;
      goto LABEL_56;
    }
  }
LABEL_68:
  if ( DestinationString.Buffer )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    DestinationString.Buffer = 0;
  }
  if ( ppvReadContext )
    ClfsTerminateReadLog(ppvReadContext);
  if ( appended < 0 )
  {
    if ( *(_QWORD *)(a1 + 168) )
    {
      v4 = *(void **)(a1 + 168);
      *(_QWORD *)(a1 + 168) = 0;
    }
    v21 = *(void **)(a1 + 160);
    if ( v21 )
    {
      ClfsDeleteMarshallingArea(v21);
      *(_QWORD *)(a1 + 160) = 0;
    }
    v22 = *(FILE_OBJECT **)(a1 + 152);
    if ( v22 )
    {
      ClfsCloseLogFileObject(v22);
      *(_QWORD *)(a1 + 152) = 0;
    }
    if ( v4 )
      ClfsMgmtDeregisterManagedClient(v4);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14001ec00  mov     r11, rsp
0x14001ec03  mov     [r11+10h], rbx
0x14001ec07  mov     [r11+18h], rsi
0x14001ec0b  push    rdi
0x14001ec0c  push    r12
0x14001ec0e  push    r13
0x14001ec10  push    r14
0x14001ec12  push    r15
0x14001ec14  sub     rsp, 170h
0x14001ec1b  mov     rax, cs:__security_cookie
0x14001ec22  xor     rax, rsp
0x14001ec25  mov     [rsp+198h+var_38], rax
0x14001ec2d  mov     rdi, rcx
0x14001ec30  mov     [rsp+198h+var_C8], rcx
0x14001ec38  xorps   xmm0, xmm0
0x14001ec3b  movups  xmmword ptr [rsp+198h+DestinationString.Length], xmm0
0x14001ec40  xor     r14d, r14d
0x14001ec43  mov     [r11-100h], r14
0x14001ec4a  mov     [r11-10Ch], r14d
0x14001ec51  mov     [r11-118h], r14
0x14001ec58  mov     [r11-0E8h], r14
0x14001ec5f  mov     [r11-0F8h], r14
0x14001ec66  lea     ebx, [r14+78h]
0x14001ec6a  mov     r8d, ebx; Size
0x14001ec6d  xor     edx, edx; Val
0x14001ec6f  lea     rcx, [r11-0B8h]; void *
0x14001ec76  call    memset
0x14001ec7b  mov     [rsp+198h+pcbInfoBuffer], ebx
0x14001ec82  mov     [rsp+198h+peRecordType], r14b
0x14001ec87  lea     rbx, [rdi+88h]
0x14001ec8e  movzx   edx, word ptr [rbx]
0x14001ec91  movzx   r8d, cs:TmpLogPrefix.Length
0x14001ec99  lea     ecx, [rdx+r8]
0x14001ec9d  cmp     ecx, 0FFFFh
0x14001eca3  jbe     short loc_14001ECD8
0x14001eca5  mov     eax, 80000005h
0x14001ecaa  mov     rcx, [rsp+198h+var_38]
0x14001ecb2  xor     rcx, rsp; StackCookie
0x14001ecb5  call    __security_check_cookie
0x14001ecba  lea     r11, [rsp+198h+var_28]
0x14001ecc2  mov     rbx, [r11+38h]
0x14001ecc6  mov     rsi, [r11+40h]
0x14001ecca  mov     rsp, r11
0x14001eccd  pop     r15
0x14001eccf  pop     r14
0x14001ecd1  pop     r13
0x14001ecd3  pop     r12
0x14001ecd5  pop     rdi
0x14001ecd6  retn
0x14001ecd8  mov     [rsp+198h+var_134], r14d
0x14001ecdd  mov     r12, r14
0x14001ece0  mov     [rsp+198h+var_F0], r14
0x14001ece8  mov     [rsp+198h+var_130], r14b
0x14001eced  mov     r13b, r14b
0x14001ecf0  add     dx, r8w
0x14001ecf4  movzx   edx, dx; NumberOfBytes
0x14001ecf7  mov     [rsp+198h+DestinationString.MaximumLength], dx
0x14001ecfc  mov     ecx, 9; PoolType
0x14001ed01  mov     r8d, 6E4C6D54h; Tag
0x14001ed07  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x14001ed0e  nop     dword ptr [rax+rax+00h]
0x14001ed13  mov     [rsp+198h+DestinationString.Buffer], rax
0x14001ed18  test    rax, rax
0x14001ed1b  jnz     short loc_14001ED24
0x14001ed1d  mov     eax, 0C000009Ah
0x14001ed22  jmp     short loc_14001ECAA
0x14001ed24  xor     edx, edx; SourceString
0x14001ed26  lea     rcx, [rsp+198h+DestinationString]; DestinationString
0x14001ed2b  call    cs:__imp_RtlCopyUnicodeString
0x14001ed32  nop     dword ptr [rax+rax+00h]
0x14001ed37  lea     rdx, TmpLogPrefix; Source
0x14001ed3e  lea     rcx, [rsp+198h+DestinationString]; Destination
0x14001ed43  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001ed4a  nop     dword ptr [rax+rax+00h]
0x14001ed4f  mov     rdx, rbx; Source
0x14001ed52  lea     rcx, [rsp+198h+DestinationString]; Destination
0x14001ed57  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001ed5e  nop     dword ptr [rax+rax+00h]
0x14001ed63  mov     ebx, eax
0x14001ed65  mov     [rsp+198h+var_134], eax
0x14001ed69  test    eax, eax
0x14001ed6b  js      loc_14001F2C4
0x14001ed71  lea     r15, [rdi+98h]
0x14001ed78  mov     [rsp+198h+cbContext], r14d; cbContext
0x14001ed7d  mov     [rsp+198h+pvContext], r14; pvContext
0x14001ed82  mov     [rsp+198h+fLogOptionFlag], r14d; fLogOptionFlag
0x14001ed87  mov     [rsp+198h+fFlagsAndAttributes], r14d; fFlagsAndAttributes
0x14001ed8c  mov     [rsp+198h+fCreateOptions], r14d; fCreateOptions
0x14001ed91  mov     [rsp+198h+fCreateDisposition], 1; fCreateDisposition
0x14001ed99  mov     [rsp+198h+psdLogFile], r14; psdLogFile
0x14001ed9e  mov     esi, 0C0000000h
0x14001eda3  mov     r9d, 3; dwShareMode
0x14001eda9  mov     r8d, esi; fDesiredAccess
0x14001edac  lea     rdx, [rsp+198h+DestinationString]; puszLogFileName
0x14001edb1  mov     rcx, r15; pplfoLog
0x14001edb4  call    cs:__imp_ClfsCreateLogFile
0x14001edbb  nop     dword ptr [rax+rax+00h]
0x14001edc0  mov     ebx, eax
0x14001edc2  mov     [rsp+198h+var_134], eax
0x14001edc6  cmp     eax, 0C0000034h
0x14001edcb  jnz     loc_14001EE59
0x14001edd1  mov     r13b, 1
0x14001edd4  mov     [rsp+198h+cbContext], r14d; cbContext
0x14001edd9  mov     [rsp+198h+pvContext], r14; pvContext
0x14001edde  mov     [rsp+198h+fLogOptionFlag], r14d; fLogOptionFlag
0x14001ede3  mov     [rsp+198h+fFlagsAndAttributes], r14d; fFlagsAndAttributes
0x14001ede8  mov     [rsp+198h+fCreateOptions], r14d; fCreateOptions
0x14001eded  mov     [rsp+198h+fCreateDisposition], 2; fCreateDisposition
0x14001edf5  mov     [rsp+198h+psdLogFile], r14; psdLogFile
0x14001edfa  mov     r9d, 3; dwShareMode
0x14001ee00  mov     r8d, esi; fDesiredAccess
0x14001ee03  lea     rdx, [rsp+198h+DestinationString]; puszLogFileName
0x14001ee08  mov     rcx, r15; pplfoLog
0x14001ee0b  call    cs:__imp_ClfsCreateLogFile
0x14001ee12  nop     dword ptr [rax+rax+00h]
0x14001ee17  mov     ebx, eax
0x14001ee19  mov     [rsp+198h+var_134], eax
0x14001ee1d  test    eax, eax
0x14001ee1f  jz      short loc_14001EE86
0x14001ee21  lea     rsi, WPP_GLOBAL_Control
0x14001ee28  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ee2f  cmp     rcx, rsi
0x14001ee32  jz      loc_14001F2C4
0x14001ee38  mov     eax, [rcx+2Ch]
0x14001ee3b  test    al, 8
0x14001ee3d  jz      loc_14001F2C4
0x14001ee43  mov     edx, 21h ; '!'
0x14001ee48  mov     r9d, ebx
0x14001ee4b  mov     rcx, [rcx+18h]
0x14001ee4f  call    WPP_SF_d
0x14001ee54  jmp     loc_14001F2C4
0x14001ee59  test    ebx, ebx
0x14001ee5b  jns     short loc_14001EE86
0x14001ee5d  lea     rsi, WPP_GLOBAL_Control
0x14001ee64  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ee6b  cmp     rcx, rsi
0x14001ee6e  jz      loc_14001F2C4
0x14001ee74  mov     eax, [rcx+2Ch]
0x14001ee77  test    al, 8
0x14001ee79  jz      loc_14001F2C4
0x14001ee7f  mov     edx, 22h ; '"'
0x14001ee84  jmp     short loc_14001EE48
0x14001ee86  lea     rdx, [rsp+198h+peRecordType]
0x14001ee8b  mov     rcx, rdi
0x14001ee8e  call    TmpIsClusteredTransactionManager
0x14001ee93  mov     ebx, eax
0x14001ee95  mov     [rsp+198h+var_134], eax
0x14001ee99  test    eax, eax
0x14001ee9b  jns     short loc_14001EED5
0x14001ee9d  lea     rsi, WPP_GLOBAL_Control
0x14001eea4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eeab  cmp     rcx, rsi
0x14001eeae  jz      loc_14001F2C4
0x14001eeb4  mov     eax, [rcx+2Ch]
0x14001eeb7  test    al, 8
0x14001eeb9  jz      loc_14001F2C4
0x14001eebf  mov     edx, 23h ; '#'
0x14001eec4  mov     r9d, ebx
0x14001eec7  mov     rcx, [rcx+18h]
0x14001eecb  call    WPP_SF_d
0x14001eed0  jmp     loc_14001F2C4
0x14001eed5  cmp     [rsp+198h+peRecordType], r14b
0x14001eeda  jz      short loc_14001EEEC
0x14001eedc  lock or dword ptr [rdi+80h], 100h
0x14001eee7  call    TmpStartKtmRm
0x14001eeec  mov     rcx, rdi
0x14001eeef  call    TmpRegisterForLogManagement
0x14001eef4  mov     ebx, eax
0x14001eef6  mov     [rsp+198h+var_134], eax
0x14001eefa  cmp     eax, 0C0000035h
0x14001eeff  jnz     short loc_14001EF46
0x14001ef01  lea     rsi, WPP_GLOBAL_Control
0x14001ef08  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ef0f  cmp     rcx, rsi
0x14001ef12  jz      short loc_14001EF3B
0x14001ef14  mov     eax, [rcx+2Ch]
0x14001ef17  test    al, 8
0x14001ef19  jz      short loc_14001EF3B
0x14001ef1b  mov     edx, 24h ; '$'
0x14001ef20  mov     dword ptr [rsp+198h+psdLogFile], 0C0000035h
0x14001ef28  mov     r9, rdi
0x14001ef2b  lea     r8, WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids
0x14001ef32  mov     rcx, [rcx+18h]
0x14001ef36  call    WPP_SF_qD
0x14001ef3b  mov     ebx, 0C0190030h
0x14001ef40  mov     [rsp+198h+var_134], ebx
0x14001ef44  jmp     short loc_14001EF4D
0x14001ef46  lea     rsi, WPP_GLOBAL_Control
0x14001ef4d  test    ebx, ebx
0x14001ef4f  js      loc_14001F2C4
0x14001ef55  lea     r14, [rdi+0A0h]
0x14001ef5c  mov     qword ptr [rsp+198h+fFlagsAndAttributes], r14; ppvMarshalContext
0x14001ef61  mov     eax, 1
0x14001ef66  mov     [rsp+198h+fCreateOptions], eax; cMaxReadBuffers
0x14001ef6a  mov     [rsp+198h+fCreateDisposition], 14h; cMaxWriteBuffers
0x14001ef72  mov     dword ptr [rsp+198h+psdLogFile], 10000h; cbMarshallingBuffer
0x14001ef7a  xor     r9d, r9d; pfnFreeBuffer
0x14001ef7d  xor     r8d, r8d; pfnAllocBuffer
0x14001ef80  mov     edx, eax; ePoolType
0x14001ef82  mov     rcx, [r15]; plfoLog
0x14001ef85  call    cs:__imp_ClfsCreateMarshallingArea
0x14001ef8c  nop     dword ptr [rax+rax+00h]
0x14001ef91  mov     ebx, eax
0x14001ef93  mov     [rsp+198h+var_134], eax
0x14001ef97  test    eax, eax
0x14001ef99  jz      short loc_14001EFCC
0x14001ef9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001efa2  cmp     rcx, rsi
0x14001efa5  jz      loc_14001F2C1
0x14001efab  mov     eax, [rcx+2Ch]
0x14001efae  test    al, 8
0x14001efb0  jz      loc_14001F2C1
0x14001efb6  mov     edx, 25h ; '%'
0x14001efbb  mov     r9d, ebx
0x14001efbe  mov     rcx, [rcx+18h]
0x14001efc2  call    WPP_SF_d
0x14001efc7  jmp     loc_14001F2C1
0x14001efcc  mov     [rsp+198h+rgcbReservation], 20h ; ' '
0x14001efd8  xor     ebx, ebx
0x14001efda  mov     qword ptr [rsp+198h+fLogOptionFlag], rbx; plsn
0x14001efdf  mov     [rsp+198h+fFlagsAndAttributes], ebx; fFlags
0x14001efe3  lea     rax, [rsp+198h+rgcbReservation]
0x14001efeb  mov     qword ptr [rsp+198h+fCreateOptions], rax; rgcbReservation
0x14001eff0  mov     [rsp+198h+fCreateDisposition], 1; cReserveRecords
0x14001eff8  mov     [rsp+198h+psdLogFile], rbx; plsnPrevious
0x14001effd  xor     r9d, r9d; plsnUndoNext
0x14001f000  xor     r8d, r8d; cWriteEntries
0x14001f003  xor     edx, edx; rgWriteEntries
0x14001f005  mov     rcx, [r14]; pvMarshalContext
0x14001f008  call    cs:__imp_ClfsReserveAndAppendLog
0x14001f00f  nop     dword ptr [rax+rax+00h]
0x14001f014  mov     [rsp+198h+var_134], eax
0x14001f018  test    eax, eax
0x14001f01a  jz      short loc_14001F045
0x14001f01c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f023  cmp     rcx, rsi
0x14001f026  jz      short loc_14001F04D
0x14001f028  mov     edx, [rcx+2Ch]
0x14001f02b  test    dl, 8
0x14001f02e  jz      short loc_14001F04D
0x14001f030  lea     edx, [rbx+26h]
0x14001f033  mov     dword ptr [rsp+198h+psdLogFile], eax
0x14001f037  mov     r9, rdi
0x14001f03a  mov     rcx, [rcx+18h]
0x14001f03e  call    WPP_SF_qd
0x14001f043  jmp     short loc_14001F04D
0x14001f045  lock or dword ptr [rdi+378h], 2
0x14001f04d  test    r13b, r13b
0x14001f050  jz      short loc_14001F075
0x14001f052  xor     r8d, r8d
0x14001f055  xor     edx, edx
0x14001f057  mov     rcx, rdi
0x14001f05a  call    TmpWriteRestartArea
0x14001f05f  mov     ebx, eax
0x14001f061  mov     [rsp+198h+var_134], eax
0x14001f065  xor     r14d, r14d
0x14001f068  test    eax, eax
0x14001f06a  jns     loc_14001F2A0
0x14001f070  jmp     loc_14001F2C4
0x14001f075  lea     r8, [rsp+198h+pcbInfoBuffer]; pcbInfoBuffer
0x14001f07d  lea     rdx, [rsp+198h+pinfoBuffer]; pinfoBuffer
0x14001f085  mov     rcx, [r15]; plfoLog
0x14001f088  call    cs:__imp_ClfsGetLogFileInformation
0x14001f08f  nop     dword ptr [rax+rax+00h]
0x14001f094  mov     [rsp+198h+var_134], eax
0x14001f098  lea     r15, [rdi+290h]
0x14001f09f  mov     rax, qword ptr [rsp+198h+pinfoBuffer.BaseLsn]
0x14001f0a7  mov     [r15], rax
0x14001f0aa  mov     [rdi+288h], rax
0x14001f0b1  lea     rax, [rsp+198h+ppvReadContext]
0x14001f0b9  mov     [rsp+198h+psdLogFile], rax; ppvReadContext
0x14001f0be  lea     r9, [rsp+198h+plsn]; plsn
0x14001f0c6  lea     r8, [rsp+198h+pcbRestartBuffer]; pcbRestartBuffer
0x14001f0ce  lea     rdx, [rsp+198h+ppvRestartBuffer]; ppvRestartBuffer
0x14001f0d6  mov     rcx, [r14]; pvMarshalContext
0x14001f0d9  call    cs:__imp_ClfsReadRestartArea
0x14001f0e0  nop     dword ptr [rax+rax+00h]
0x14001f0e5  mov     ebx, eax
0x14001f0e7  mov     [rsp+198h+var_134], eax
0x14001f0eb  cmp     eax, 401A000Ch
0x14001f0f0  jnz     loc_14001F1FA
0x14001f0f6  xor     eax, eax
0x14001f0f8  mov     qword ptr [rsp+198h+plsnUndoNext], rax
0x14001f100  mov     qword ptr [rsp+198h+plsnPrevious], rax
0x14001f108  mov     [rsp+198h+peRecordType], al
0x14001f10c  mov     [rsp+198h+ppvReadBuffer], rax
0x14001f114  mov     [rsp+198h+pcbReadBuffer], eax
0x14001f11b  mov     [rsp+198h+peRecordType], 3
0x14001f120  lea     rax, [rsp+198h+ppvReadContext]
0x14001f128  mov     qword ptr [rsp+198h+fLogOptionFlag], rax; ppvReadContext
0x14001f12d  lea     rax, [rsp+198h+plsnPrevious]
0x14001f135  mov     qword ptr [rsp+198h+fFlagsAndAttributes], rax; plsnPrevious
0x14001f13a  lea     rax, [rsp+198h+plsnUndoNext]
0x14001f142  mov     qword ptr [rsp+198h+fCreateOptions], rax; plsnUndoNext
0x14001f147  lea     rax, [rsp+198h+peRecordType]
0x14001f14c  mov     qword ptr [rsp+198h+fCreateDisposition], rax; peRecordType
0x14001f151  lea     rax, [rsp+198h+pcbReadBuffer]
0x14001f159  mov     [rsp+198h+psdLogFile], rax; pcbReadBuffer
0x14001f15e  lea     r9, [rsp+198h+ppvReadBuffer]; ppvReadBuffer
0x14001f166  mov     r8d, 3; peContextMode
  ... truncated ...
```
