# VmsOmSwitchDelete

- ea: `0x1400fc970`
- end: `0x1400fceed`
- name: `VmsOmSwitchDelete`
- size: `1405`
- prototype: ``
- caller_count: `4`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400b2d78`
- `0x1400fb990`
- `0x140105aac`
- `0x140108c38`

## callees

- `0x14001484c`
- `0x140027a64`
- `0x14002e45c`
- `0x1400313cc`
- `0x14003c134`
- `0x140047204`
- `0x14006b084`
- `0x14006e100`
- `0x140070b04`
- `0x140072e60`
- `0x14008497c`
- `0x14008d698`
- `0x1400eb424`
- `0x1400fb810`
- `0x1400fc970`
- `0x1400fd548`
- `0x1400fda70`
- `0x1400fdc50`
- `0x1401064dc`
- `0x140106f38`
- `0x140106fe4`
- `0x140107358`
- `0x140151ebc`
- `0x140188054`
- `0x14018d298`
- `0x1401b9240`
- `0x1401bb6a4`
- `0x1401bbb64`
- `0x1401bbc40`
- `0x1401bbe10`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400fcc33`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400fcc33`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fcbda`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fcbda`
- `ntoskrnl!KeReleaseMutex` at `0x1400fcdd1`
- `ntoskrnl!KeReleaseMutex` at `0x1400fcdd1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400fcd65`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400fcd65`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400fcc8f`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400fccb9`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400fcc8f`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400fccb9`
- `NDIS!NdisReleaseRWLock` at `0x1400fcb26`
- `NDIS!NdisReleaseRWLock` at `0x1400fcb3f`
- `NDIS!NdisReleaseRWLock` at `0x1400fcbef`
- `NDIS!NdisReleaseRWLock` at `0x1401bcb01`
- `NDIS!NdisReleaseRWLock` at `0x1401bcb29`
- `NDIS!NdisReleaseRWLock` at `0x1400fcb26`
- `NDIS!NdisReleaseRWLock` at `0x1400fcb3f`
- `NDIS!NdisReleaseRWLock` at `0x1400fcbef`
- `NDIS!NdisReleaseRWLock` at `0x1401bcb01`
- `NDIS!NdisReleaseRWLock` at `0x1401bcb29`

## pseudocode

```c
__int64 __fastcall VmsOmSwitchDelete(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  char v8; // r13
  __int64 v9; // r8
  __int64 v10; // rbx
  __int64 v11; // rdx
  int v12; // ecx
  void *v13; // rcx
  __int64 *i; // rax
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  int v18; // edx
  int v19; // r8d
  int v20; // r9d
  char *v21; // rdi
  __int64 v22; // rsi
  void *v23; // rdi
  char *v24; // rbx
  int v25; // edx
  int v26; // r8d
  __int64 v27; // rdx
  _BYTE v29[32]; // [rsp+0h] [rbp-1B8h] BYREF
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-198h]
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp-178h] BYREF
  unsigned int SwitchUnsafe; // [rsp+44h] [rbp-174h]
  struct _LOCK_STATE_EX v33; // [rsp+48h] [rbp-170h] BYREF
  char v34[4]; // [rsp+4Ch] [rbp-16Ch]
  void *Src; // [rsp+50h] [rbp-168h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-160h] BYREF
  _BYTE *v37; // [rsp+68h] [rbp-150h]
  __int64 v38; // [rsp+70h] [rbp-148h]
  _BYTE v39[256]; // [rsp+80h] [rbp-138h] BYREF

  v37 = v29;
  v38 = a1;
  SwitchUnsafe = -1073741823;
  Src = 0;
  *(_WORD *)&v33.OldIrql = 0;
  v33.Flags = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *(_DWORD *)v34 = 0;
  v8 = 0;
  VmsUtilLockShared(a1, &v33, 0);
  SwitchUnsafe = VmsOmFindSwitchUnsafe(a1, &Src);
  if ( SwitchUnsafe )
  {
    SwitchUnsafe = -1073741772;
    *(_DWORD *)v34 = 5;
    local_unwind_0(v29, &loc_1400FCDF0);
  }
  LOBYTE(v9) = 1;
  v10 = (__int64)Src;
  VmsOmObjectLockExclusive(Src, &LockState, v9);
  if ( *(_DWORD *)(v10 + 68) == 2 )
  {
    LOBYTE(v11) = 4;
    WPP_RECORDER_SF_Z(VmsIfrLog, v11, 18, 29, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids, a1);
    SwitchUnsafe = -1073741738;
    *(_DWORD *)v34 = 10;
    local_unwind_0(v37, &loc_1400FCDF0);
  }
  if ( a4 )
  {
    v12 = *(_DWORD *)(v10 + 4276);
    if ( ((v12 - 1) & 0xFFFFFFFC) == 0 && v12 != 2 )
    {
      v10 = 20;
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_Z(VmsIfrLog, v11, 20, 30, (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids, a1);
      SwitchUnsafe = -1073741436;
      *(_DWORD *)v34 = 20;
      local_unwind_0(v37, &loc_1400FCDF0);
    }
  }
  *(_QWORD *)(v10 + 1480) = a3;
  *(_QWORD *)(v10 + 1488) = a2;
  if ( !VmsIsUnloadForServicing )
  {
    LOBYTE(v11) = 2;
    v8 = VmsOmObjectPrepareForConfigStore(v10, v11, 2);
  }
  *(_DWORD *)(v10 + 68) = 2;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v10 + 56), &LockState);
  NdisReleaseRWLock(VmsOmObjectListLock, &v33);
  if ( !VmsIsUnloadForServicing )
    VmsOmMarkObjectConfigDeletion(v10 + 72, 0, 0);
  v13 = *(void **)(v10 + 9352);
  if ( v13 )
  {
    NvIoShutdownWorkerQueue(v13);
    *(_QWORD *)(v10 + 9352) = 0;
  }
  while ( 1 )
  {
    memset(v39, 0, 0xFEu);
    *(_QWORD *)&DestinationString.Length = 16646144;
    DestinationString.Buffer = (wchar_t *)v39;
    VmsOmObjectLockShared(v10, &LockState, 0);
    for ( i = *(__int64 **)(v10 + 1416); i != (__int64 *)(v10 + 1416); i = (__int64 *)*i )
    {
      if ( *((_DWORD *)i + 17) != 2 )
      {
        RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(i + 9));
        break;
      }
    }
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v10 + 56), &LockState);
    if ( !DestinationString.Length )
      break;
    VmsOmPortDelete(v10 + 72, &DestinationString, 0, 0);
  }
  VmsOmSwitchCleanupDefaultObjects(v10);
  if ( *(_BYTE *)(v10 + 1408) )
  {
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v10 + 1280));
    *(_BYTE *)(v10 + 1408) = 0;
  }
  VmsOmpSwitchStormLimitUninitialize(v10);
  VmsOmpRscStructsFree(v10 + 9184);
  v15 = *(void **)(v10 + 8680);
  if ( v15 )
  {
    VmsScQosDeleteLine(v15);
    *(_QWORD *)(v10 + 8680) = 0;
  }
  VmsOmpDestroyInMemoryPropertiesHashTable((PRTL_DYNAMIC_HASH_TABLE)(v10 + 8576));
  v16 = *(void **)(v10 + 5184);
  if ( v16 )
  {
    NdisFreeMemoryWithTag(v16, 0x74527356u);
    *(_QWORD *)(v10 + 5184) = 0;
    *(_DWORD *)(v10 + 5176) = 0;
  }
  v17 = *(void **)(v10 + 9224);
  if ( v17 )
  {
    NdisFreeMemoryWithTag(v17, 0x63507356u);
    *(_QWORD *)(v10 + 9224) = 0;
    *(_DWORD *)(v10 + 9220) = 0;
  }
  VmsExtIoDeleteEdgeCounters(v10);
  PktMonClientComponentUnregister((void *)(v10 + 6408));
  PktCapClientUninitialize(v10 + 9008);
  if ( *(_BYTE *)(v10 + 8904) && !VmsIsUnloadForServicing )
  {
    if ( !VmsPDClientHandle )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v18,
        19,
        31,
        (__int64)WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids,
        (__int64)"VmsPDClientHandle != NULL");
      if ( !VmsPDClientHandle )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
    if ( *(_QWORD *)(v10 + 8928) )
    {
      (*(void (**)(void))(VmsPDPlatformDispatch + 160))();
      *(_QWORD *)(v10 + 8928) = 0;
    }
    if ( !--VmsPDSwitchCount )
    {
      (*(void (__fastcall **)(__int64))(VmsPDPlatformDispatch + 232))(VmsPDClientHandle);
      VmsPDClientHandle = 0;
      VmsPDPlatformDispatch = 0;
    }
    KeReleaseMutex(&VmsOmIoctlMutex, 0);
  }
  if ( v8 == 1 )
    VmsOmSwitchStoreConfig((void *)v10);
  v21 = 0;
  v22 = v38;
  if ( SwitchUnsafe )
  {
    WPP_RECORDER_SF_Zld(SwitchUnsafe, v18, v19, v20, (_DWORD)Timeout, v38, a4, SwitchUnsafe);
    if ( Src )
      v21 = (char *)Src + 616;
    VmsEtwTraceSwitchFailure(&VM_DELETE_SWITCH_FAILED, v34[0], v22, (__int64)v21);
  }
  else
  {
    v23 = Src;
    v24 = (char *)Src + 616;
    VmsEtwTraceSwitchSuccess(
      (unsigned int)VM_SWITCH_SUCCESSFULLY_DELETED,
      *((unsigned __int8 *)Src + 1232),
      v19,
      v38,
      (__int64)Src + 616,
      *((_BYTE *)Src + 1232),
      *((_DWORD *)Src + 2286));
    WPP_RECORDER_SF_ZZq(VmsIfrLog, v25, v26, 32, (_DWORD)Timeout, v22, (__int64)v24, (char)v23);
    LOBYTE(v27) = -1;
    VmsOmpObjectDereference(v23, v27);
  }
  VmsTraceLoggingSwitchDelete(v22, SwitchUnsafe);
  return SwitchUnsafe;
}

```

## disassembly

```asm
0x1400fc970  mov     [rsp+arg_8], rbx
0x1400fc975  mov     [rsp+arg_10], rsi
0x1400fc97a  mov     [rsp+arg_18], r9b
0x1400fc97f  push    rdi
0x1400fc980  push    r12
0x1400fc982  push    r13
0x1400fc984  push    r14
0x1400fc986  push    r15
0x1400fc988  sub     rsp, 190h
0x1400fc98f  mov     rax, cs:__security_cookie
0x1400fc996  xor     rax, rsp
0x1400fc999  mov     [rsp+1B8h+var_38], rax
0x1400fc9a1  mov     [rsp+1B8h+var_150], rsp
0x1400fc9a6  mov     r14b, r9b
0x1400fc9a9  mov     r15, r8
0x1400fc9ac  mov     r12, rdx
0x1400fc9af  mov     rsi, rcx
0x1400fc9b2  mov     [rsp+1B8h+var_148], rcx
0x1400fc9b7  mov     [rsp+1B8h+var_174], 0C0000001h
0x1400fc9bf  xor     edi, edi
0x1400fc9c1  mov     [rsp+1B8h+Src], rdi
0x1400fc9c6  xor     eax, eax
0x1400fc9c8  mov     word ptr [rsp+1B8h+var_170.OldIrql], ax
0x1400fc9cd  mov     [rsp+1B8h+var_170.Flags], al
0x1400fc9d1  mov     word ptr [rsp+1B8h+LockState.OldIrql], ax
0x1400fc9d6  mov     [rsp+1B8h+LockState.Flags], al
0x1400fc9da  mov     dword ptr [rsp+1B8h+var_16C], edi
0x1400fc9de  mov     r13b, dil
0x1400fc9e1  xor     r8d, r8d
0x1400fc9e4  lea     rdx, [rsp+1B8h+var_170]
0x1400fc9e9  call    VmsUtilLockShared
0x1400fc9ee  lea     rdx, [rsp+1B8h+Src]
0x1400fc9f3  mov     rcx, rsi
0x1400fc9f6  call    VmsOmFindSwitchUnsafe
0x1400fc9fb  mov     [rsp+1B8h+var_174], eax
0x1400fc9ff  test    eax, eax
0x1400fca01  jz      short loc_1400FCA23
0x1400fca03  mov     [rsp+1B8h+var_174], 0C0000034h
0x1400fca0b  mov     dword ptr [rsp+1B8h+var_16C], 5
0x1400fca13  lea     rdx, loc_1400FCDF0
0x1400fca1a  mov     rcx, rsp
0x1400fca1d  call    _local_unwind_0
0x1400fca22  nop
0x1400fca23  mov     r8b, 1
0x1400fca26  lea     rdx, [rsp+1B8h+LockState]
0x1400fca2b  mov     rbx, [rsp+1B8h+Src]
0x1400fca30  mov     rcx, rbx
0x1400fca33  call    VmsOmObjectLockExclusive
0x1400fca38  cmp     dword ptr [rbx+44h], 2
0x1400fca3c  jnz     short loc_1400FCA88
0x1400fca3e  mov     r9d, 1Dh
0x1400fca44  mov     [rsp+1B8h+var_190], rsi
0x1400fca49  lea     rax, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fca50  mov     [rsp+1B8h+Timeout], rax
0x1400fca55  lea     r8d, [r9-0Bh]
0x1400fca59  mov     dl, 4
0x1400fca5b  mov     rcx, cs:VmsIfrLog
0x1400fca62  call    WPP_RECORDER_SF_Z
0x1400fca67  mov     [rsp+1B8h+var_174], 0C0000056h
0x1400fca6f  mov     dword ptr [rsp+1B8h+var_16C], 0Ah
0x1400fca77  lea     rdx, loc_1400FCDF0
0x1400fca7e  mov     rcx, [rsp+1B8h+var_150]
0x1400fca83  call    _local_unwind_0
0x1400fca88  test    r14b, r14b
0x1400fca8b  jz      short loc_1400FCAEB
0x1400fca8d  mov     ecx, [rbx+10B4h]
0x1400fca93  lea     eax, [rcx-1]
0x1400fca96  test    eax, 0FFFFFFFCh
0x1400fca9b  jnz     short loc_1400FCAEB
0x1400fca9d  cmp     ecx, 2
0x1400fcaa0  jz      short loc_1400FCAEB
0x1400fcaa2  mov     r9d, 1Eh
0x1400fcaa8  mov     [rsp+1B8h+var_190], rsi
0x1400fcaad  lea     rax, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fcab4  mov     [rsp+1B8h+Timeout], rax
0x1400fcab9  lea     ebx, [r9-0Ah]
0x1400fcabd  mov     r8d, ebx
0x1400fcac0  mov     dl, 2
0x1400fcac2  mov     rcx, cs:VmsIfrLog
0x1400fcac9  call    WPP_RECORDER_SF_Z
0x1400fcace  mov     [rsp+1B8h+var_174], 0C0000184h
0x1400fcad6  mov     dword ptr [rsp+1B8h+var_16C], ebx
0x1400fcada  lea     rdx, loc_1400FCDF0
0x1400fcae1  mov     rcx, [rsp+1B8h+var_150]
0x1400fcae6  call    _local_unwind_0
0x1400fcaeb  mov     [rbx+5C8h], r15
0x1400fcaf2  mov     [rbx+5D0h], r12
0x1400fcaf9  cmp     cs:VmsIsUnloadForServicing, dil
0x1400fcb00  jnz     short loc_1400FCB16
0x1400fcb02  mov     r8d, 2
0x1400fcb08  mov     dl, r8b
0x1400fcb0b  mov     rcx, rbx
0x1400fcb0e  call    VmsOmObjectPrepareForConfigStore
0x1400fcb13  mov     r13b, al
0x1400fcb16  mov     dword ptr [rbx+44h], 2
0x1400fcb1d  lea     rdx, [rsp+1B8h+LockState]; LockState
0x1400fcb22  mov     rcx, [rbx+38h]; Lock
0x1400fcb26  call    cs:__imp_NdisReleaseRWLock
0x1400fcb2d  nop     dword ptr [rax+rax+00h]
0x1400fcb32  nop
0x1400fcb33  lea     rdx, [rsp+1B8h+var_170]; LockState
0x1400fcb38  mov     rcx, cs:VmsOmObjectListLock; Lock
0x1400fcb3f  call    cs:__imp_NdisReleaseRWLock
0x1400fcb46  nop     dword ptr [rax+rax+00h]
0x1400fcb4b  cmp     cs:VmsIsUnloadForServicing, dil
0x1400fcb52  jnz     short loc_1400FCB62
0x1400fcb54  lea     rcx, [rbx+48h]
0x1400fcb58  xor     r8d, r8d
0x1400fcb5b  xor     edx, edx
0x1400fcb5d  call    VmsOmMarkObjectConfigDeletion
0x1400fcb62  mov     rcx, [rbx+2488h]; void *
0x1400fcb69  test    rcx, rcx
0x1400fcb6c  jz      short loc_1400FCB7A
0x1400fcb6e  call    NvIoShutdownWorkerQueue
0x1400fcb73  mov     [rbx+2488h], rdi
0x1400fcb7a  mov     esi, 0FEh
0x1400fcb7f  mov     r8, rsi; Size
0x1400fcb82  xor     edx, edx; Val
0x1400fcb84  lea     rcx, [rsp+1B8h+var_138]; void *
0x1400fcb8c  call    memset
0x1400fcb91  mov     qword ptr [rsp+1B8h+DestinationString.Length], 0FE0000h
0x1400fcb9a  lea     rax, [rsp+1B8h+var_138]
0x1400fcba2  mov     [rsp+1B8h+DestinationString.Buffer], rax
0x1400fcba7  xor     r8d, r8d
0x1400fcbaa  lea     rdx, [rsp+1B8h+LockState]
0x1400fcbaf  mov     rcx, rbx
0x1400fcbb2  call    VmsOmObjectLockShared
0x1400fcbb7  lea     rcx, [rbx+588h]
0x1400fcbbe  mov     rax, [rcx]
0x1400fcbc1  cmp     rax, rcx
0x1400fcbc4  jz      short loc_1400FCBE6
0x1400fcbc6  lea     rdx, [rax+48h]; SourceString
0x1400fcbca  cmp     dword ptr [rax+44h], 2
0x1400fcbce  jnz     short loc_1400FCBD5
0x1400fcbd0  mov     rax, [rax]
0x1400fcbd3  jmp     short loc_1400FCBC1
0x1400fcbd5  lea     rcx, [rsp+1B8h+DestinationString]; DestinationString
0x1400fcbda  call    cs:__imp_RtlCopyUnicodeString
0x1400fcbe1  nop     dword ptr [rax+rax+00h]
0x1400fcbe6  lea     rdx, [rsp+1B8h+LockState]; LockState
0x1400fcbeb  mov     rcx, [rbx+38h]; Lock
0x1400fcbef  call    cs:__imp_NdisReleaseRWLock
0x1400fcbf6  nop     dword ptr [rax+rax+00h]
0x1400fcbfb  cmp     [rsp+1B8h+DestinationString.Length], di
0x1400fcc00  jbe     short loc_1400FCC1B
0x1400fcc02  lea     rcx, [rbx+48h]
0x1400fcc06  xor     r9d, r9d
0x1400fcc09  xor     r8d, r8d
0x1400fcc0c  lea     rdx, [rsp+1B8h+DestinationString]
0x1400fcc11  call    VmsOmPortDelete
0x1400fcc16  jmp     loc_1400FCB7F
0x1400fcc1b  mov     rcx, rbx
0x1400fcc1e  call    VmsOmSwitchCleanupDefaultObjects
0x1400fcc23  cmp     [rbx+580h], dil
0x1400fcc2a  jz      short loc_1400FCC46
0x1400fcc2c  lea     rcx, [rbx+500h]; Lookaside
0x1400fcc33  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400fcc3a  nop     dword ptr [rax+rax+00h]
0x1400fcc3f  mov     [rbx+580h], dil
0x1400fcc46  mov     rcx, rbx
0x1400fcc49  call    VmsOmpSwitchStormLimitUninitialize
0x1400fcc4e  lea     rcx, [rbx+23E0h]
0x1400fcc55  call    VmsOmpRscStructsFree
0x1400fcc5a  mov     rcx, [rbx+21E8h]; P
0x1400fcc61  test    rcx, rcx
0x1400fcc64  jz      short loc_1400FCC72
0x1400fcc66  call    VmsScQosDeleteLine
0x1400fcc6b  mov     [rbx+21E8h], rdi
0x1400fcc72  lea     rcx, [rbx+2180h]; HashTable
0x1400fcc79  call    VmsOmpDestroyInMemoryPropertiesHashTable
0x1400fcc7e  mov     rcx, [rbx+1440h]; VirtualAddress
0x1400fcc85  test    rcx, rcx
0x1400fcc88  jz      short loc_1400FCCA8
0x1400fcc8a  mov     edx, 74527356h; Tag
0x1400fcc8f  call    cs:__imp_NdisFreeMemoryWithTag
0x1400fcc96  nop     dword ptr [rax+rax+00h]
0x1400fcc9b  mov     [rbx+1440h], rdi
0x1400fcca2  mov     [rbx+1438h], edi
0x1400fcca8  mov     rcx, [rbx+2408h]; VirtualAddress
0x1400fccaf  test    rcx, rcx
0x1400fccb2  jz      short loc_1400FCCD2
0x1400fccb4  mov     edx, 63507356h; Tag
0x1400fccb9  call    cs:__imp_NdisFreeMemoryWithTag
0x1400fccc0  nop     dword ptr [rax+rax+00h]
0x1400fccc5  mov     [rbx+2408h], rdi
0x1400fcccc  mov     [rbx+2404h], edi
0x1400fccd2  mov     rcx, rbx
0x1400fccd5  call    VmsExtIoDeleteEdgeCounters
0x1400fccda  lea     rcx, [rbx+1908h]; void *
0x1400fcce1  call    PktMonClientComponentUnregister
0x1400fcce6  lea     rcx, [rbx+2330h]
0x1400fcced  call    PktCapClientUninitialize
0x1400fccf2  cmp     [rbx+22C8h], dil
0x1400fccf9  jz      loc_1400FCDDD
0x1400fccff  cmp     cs:VmsIsUnloadForServicing, dil
0x1400fcd06  jnz     loc_1400FCDDD
0x1400fcd0c  cmp     cs:VmsPDClientHandle, rdi
0x1400fcd13  jnz     short loc_1400FCD51
0x1400fcd15  mov     r9d, 1Fh
0x1400fcd1b  lea     rax, aVmspdclienthan; "VmsPDClientHandle != NULL"
0x1400fcd22  mov     [rsp+1B8h+var_190], rax
0x1400fcd27  lea     rax, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fcd2e  mov     [rsp+1B8h+Timeout], rax
0x1400fcd33  lea     r8d, [r9-0Ch]
0x1400fcd37  mov     rcx, cs:VmsIfrLog
0x1400fcd3e  call    WPP_RECORDER_SF_s
0x1400fcd43  cmp     cs:VmsPDClientHandle, rdi
0x1400fcd4a  jnz     short loc_1400FCD51
0x1400fcd4c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmsPDClientHandle != ((void *)0)")
0x1400fcd51  mov     [rsp+1B8h+Timeout], rdi; Timeout
0x1400fcd56  xor     r9d, r9d; Alertable
0x1400fcd59  xor     r8d, r8d; WaitMode
0x1400fcd5c  xor     edx, edx; WaitReason
0x1400fcd5e  lea     rcx, VmsOmIoctlMutex; Object
0x1400fcd65  call    cs:__imp_KeWaitForSingleObject
0x1400fcd6c  nop     dword ptr [rax+rax+00h]
0x1400fcd71  mov     rcx, [rbx+22E0h]
0x1400fcd78  test    rcx, rcx
0x1400fcd7b  jz      short loc_1400FCD97
0x1400fcd7d  mov     rax, cs:VmsPDPlatformDispatch
0x1400fcd84  mov     rax, [rax+0A0h]
0x1400fcd8b  call    _guard_dispatch_icall
0x1400fcd90  mov     [rbx+22E0h], rdi
0x1400fcd97  add     cs:VmsPDSwitchCount, 0FFFFFFFFh
0x1400fcd9e  jnz     short loc_1400FCDC8
0x1400fcda0  mov     rax, cs:VmsPDPlatformDispatch
0x1400fcda7  mov     rax, [rax+0E8h]
0x1400fcdae  mov     rcx, cs:VmsPDClientHandle
0x1400fcdb5  call    _guard_dispatch_icall
0x1400fcdba  mov     cs:VmsPDClientHandle, rdi
0x1400fcdc1  mov     cs:VmsPDPlatformDispatch, rdi
0x1400fcdc8  xor     edx, edx; Wait
0x1400fcdca  lea     rcx, VmsOmIoctlMutex; Mutex
0x1400fcdd1  call    cs:__imp_KeReleaseMutex
0x1400fcdd8  nop     dword ptr [rax+rax+00h]
0x1400fcddd  cmp     r13b, 1
0x1400fcde1  jnz     short loc_1400FCDF0
0x1400fcde3  mov     edx, 2
0x1400fcde8  mov     rcx, rbx; Src
0x1400fcdeb  call    VmsOmSwitchStoreConfig
0x1400fcdf0  mov     ecx, [rsp+1B8h+var_174]
0x1400fcdf4  xor     edi, edi
0x1400fcdf6  mov     rsi, [rsp+1B8h+var_148]
0x1400fcdfb  test    ecx, ecx
0x1400fcdfd  jnz     short loc_1400FCE61
0x1400fcdff  mov     rdi, [rsp+1B8h+Src]
0x1400fce04  lea     rbx, [rdi+268h]
0x1400fce0b  movzx   edx, byte ptr [rdi+4D0h]
0x1400fce12  mov     eax, [rdi+23B8h]
0x1400fce18  mov     dword ptr [rsp+1B8h+var_188], eax
0x1400fce1c  mov     dword ptr [rsp+1B8h+var_190], edx
0x1400fce20  mov     [rsp+1B8h+Timeout], rbx
0x1400fce25  mov     r9, rsi
0x1400fce28  lea     rcx, VM_SWITCH_SUCCESSFULLY_DELETED
0x1400fce2f  call    VmsEtwTraceSwitchSuccess
0x1400fce34  mov     r9d, 20h ; ' '
0x1400fce3a  mov     [rsp+1B8h+var_180], rdi
0x1400fce3f  mov     [rsp+1B8h+var_188], rbx
0x1400fce44  mov     [rsp+1B8h+var_190], rsi
0x1400fce49  mov     rcx, cs:VmsIfrLog
0x1400fce50  call    WPP_RECORDER_SF_ZZq
0x1400fce55  mov     dl, 0FFh
0x1400fce57  mov     rcx, rdi
0x1400fce5a  call    VmsOmpObjectDereference
0x1400fce5f  jmp     short loc_1400FCEAF
0x1400fce61  movzx   eax, [rsp+1B8h+arg_18]
0x1400fce69  mov     dword ptr [rsp+1B8h+var_180], ecx
0x1400fce6d  mov     dword ptr [rsp+1B8h+var_188], eax
0x1400fce71  mov     [rsp+1B8h+var_190], rsi
0x1400fce76  call    WPP_RECORDER_SF_Zld
0x1400fce7b  mov     rax, [rsp+1B8h+Src]
0x1400fce80  test    rax, rax
0x1400fce83  jz      short loc_1400FCE8C
0x1400fce85  lea     rdi, [rax+268h]
0x1400fce8c  mov     [rsp+1B8h+var_188], rdi; __int64
0x1400fce91  mov     [rsp+1B8h+var_190], rsi; __int64
0x1400fce96  mov     eax, dword ptr [rsp+1B8h+var_16C]
0x1400fce9a  mov     dword ptr [rsp+1B8h+Timeout], eax; char
0x1400fce9e  lea     r9, [rsp+1B8h+var_174]
0x1400fcea3  lea     rcx, VM_DELETE_SWITCH_FAILED; EventDescriptor
0x1400fceaa  call    VmsEtwTraceSwitchFailure
0x1400fceaf  mov     edx, [rsp+1B8h+var_174]
0x1400fceb3  mov     rcx, rsi
0x1400fceb6  call    VmsTraceLoggingSwitchDelete
0x1400fcebb  mov     eax, [rsp+1B8h+var_174]
0x1400fcebf  mov     rcx, [rsp+1B8h+var_38]
0x1400fcec7  xor     rcx, rsp; StackCookie
0x1400fceca  call    __security_check_cookie
0x1400fcecf  lea     r11, [rsp+1B8h+var_28]
0x1400fced7  mov     rbx, [r11+38h]
0x1400fcedb  mov     rsi, [r11+40h]
0x1400fcedf  mov     rsp, r11
0x1400fcee2  pop     r15
0x1400fcee4  pop     r14
0x1400fcee6  pop     r13
0x1400fcee8  pop     r12
0x1400fceea  pop     rdi
0x1400fceeb  retn
0x1401bcaec  push    rbp
0x1401bcaee  sub     rsp, 40h
  ... truncated ...
```
