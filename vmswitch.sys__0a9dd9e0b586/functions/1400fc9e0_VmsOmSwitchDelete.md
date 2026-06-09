# VmsOmSwitchDelete

- ea: `0x1400fc9e0`
- end: `0x1400fcf5d`
- name: `VmsOmSwitchDelete`
- size: `1405`
- prototype: ``
- caller_count: `4`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400b2de8`
- `0x1400fba00`
- `0x140105b1c`
- `0x140108ca8`

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
- `0x1400eb494`
- `0x1400fb880`
- `0x1400fc9e0`
- `0x1400fd5b8`
- `0x1400fdae0`
- `0x1400fdcc0`
- `0x14010654c`
- `0x140106fa8`
- `0x140107054`
- `0x1401073c8`
- `0x140151f2c`
- `0x1401880c4`
- `0x14018d308`
- `0x1401b92b0`
- `0x1401bb714`
- `0x1401bbbd4`
- `0x1401bbcb0`
- `0x1401bbe80`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400fcca3`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400fcca3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fcc4a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400fcc4a`
- `ntoskrnl!KeReleaseMutex` at `0x1400fce41`
- `ntoskrnl!KeReleaseMutex` at `0x1400fce41`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400fcdd5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400fcdd5`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400fccff`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400fcd29`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400fccff`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400fcd29`
- `NDIS!NdisReleaseRWLock` at `0x1400fcb96`
- `NDIS!NdisReleaseRWLock` at `0x1400fcbaf`
- `NDIS!NdisReleaseRWLock` at `0x1400fcc5f`
- `NDIS!NdisReleaseRWLock` at `0x1401bcb81`
- `NDIS!NdisReleaseRWLock` at `0x1401bcba9`
- `NDIS!NdisReleaseRWLock` at `0x1400fcb96`
- `NDIS!NdisReleaseRWLock` at `0x1400fcbaf`
- `NDIS!NdisReleaseRWLock` at `0x1400fcc5f`
- `NDIS!NdisReleaseRWLock` at `0x1401bcb81`
- `NDIS!NdisReleaseRWLock` at `0x1401bcba9`

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
    local_unwind_0(v29, &loc_1400FCE60);
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
    local_unwind_0(v37, &loc_1400FCE60);
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
      local_unwind_0(v37, &loc_1400FCE60);
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
0x1400fc9e0  mov     [rsp+arg_8], rbx
0x1400fc9e5  mov     [rsp+arg_10], rsi
0x1400fc9ea  mov     [rsp+arg_18], r9b
0x1400fc9ef  push    rdi
0x1400fc9f0  push    r12
0x1400fc9f2  push    r13
0x1400fc9f4  push    r14
0x1400fc9f6  push    r15
0x1400fc9f8  sub     rsp, 190h
0x1400fc9ff  mov     rax, cs:__security_cookie
0x1400fca06  xor     rax, rsp
0x1400fca09  mov     [rsp+1B8h+var_38], rax
0x1400fca11  mov     [rsp+1B8h+var_150], rsp
0x1400fca16  mov     r14b, r9b
0x1400fca19  mov     r15, r8
0x1400fca1c  mov     r12, rdx
0x1400fca1f  mov     rsi, rcx
0x1400fca22  mov     [rsp+1B8h+var_148], rcx
0x1400fca27  mov     [rsp+1B8h+var_174], 0C0000001h
0x1400fca2f  xor     edi, edi
0x1400fca31  mov     [rsp+1B8h+Src], rdi
0x1400fca36  xor     eax, eax
0x1400fca38  mov     word ptr [rsp+1B8h+var_170.OldIrql], ax
0x1400fca3d  mov     [rsp+1B8h+var_170.Flags], al
0x1400fca41  mov     word ptr [rsp+1B8h+LockState.OldIrql], ax
0x1400fca46  mov     [rsp+1B8h+LockState.Flags], al
0x1400fca4a  mov     dword ptr [rsp+1B8h+var_16C], edi
0x1400fca4e  mov     r13b, dil
0x1400fca51  xor     r8d, r8d
0x1400fca54  lea     rdx, [rsp+1B8h+var_170]
0x1400fca59  call    VmsUtilLockShared
0x1400fca5e  lea     rdx, [rsp+1B8h+Src]
0x1400fca63  mov     rcx, rsi
0x1400fca66  call    VmsOmFindSwitchUnsafe
0x1400fca6b  mov     [rsp+1B8h+var_174], eax
0x1400fca6f  test    eax, eax
0x1400fca71  jz      short loc_1400FCA93
0x1400fca73  mov     [rsp+1B8h+var_174], 0C0000034h
0x1400fca7b  mov     dword ptr [rsp+1B8h+var_16C], 5
0x1400fca83  lea     rdx, loc_1400FCE60
0x1400fca8a  mov     rcx, rsp
0x1400fca8d  call    _local_unwind_0
0x1400fca92  nop
0x1400fca93  mov     r8b, 1
0x1400fca96  lea     rdx, [rsp+1B8h+LockState]
0x1400fca9b  mov     rbx, [rsp+1B8h+Src]
0x1400fcaa0  mov     rcx, rbx
0x1400fcaa3  call    VmsOmObjectLockExclusive
0x1400fcaa8  cmp     dword ptr [rbx+44h], 2
0x1400fcaac  jnz     short loc_1400FCAF8
0x1400fcaae  mov     r9d, 1Dh
0x1400fcab4  mov     [rsp+1B8h+var_190], rsi
0x1400fcab9  lea     rax, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fcac0  mov     [rsp+1B8h+Timeout], rax
0x1400fcac5  lea     r8d, [r9-0Bh]
0x1400fcac9  mov     dl, 4
0x1400fcacb  mov     rcx, cs:VmsIfrLog
0x1400fcad2  call    WPP_RECORDER_SF_Z
0x1400fcad7  mov     [rsp+1B8h+var_174], 0C0000056h
0x1400fcadf  mov     dword ptr [rsp+1B8h+var_16C], 0Ah
0x1400fcae7  lea     rdx, loc_1400FCE60
0x1400fcaee  mov     rcx, [rsp+1B8h+var_150]
0x1400fcaf3  call    _local_unwind_0
0x1400fcaf8  test    r14b, r14b
0x1400fcafb  jz      short loc_1400FCB5B
0x1400fcafd  mov     ecx, [rbx+10B4h]
0x1400fcb03  lea     eax, [rcx-1]
0x1400fcb06  test    eax, 0FFFFFFFCh
0x1400fcb0b  jnz     short loc_1400FCB5B
0x1400fcb0d  cmp     ecx, 2
0x1400fcb10  jz      short loc_1400FCB5B
0x1400fcb12  mov     r9d, 1Eh
0x1400fcb18  mov     [rsp+1B8h+var_190], rsi
0x1400fcb1d  lea     rax, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fcb24  mov     [rsp+1B8h+Timeout], rax
0x1400fcb29  lea     ebx, [r9-0Ah]
0x1400fcb2d  mov     r8d, ebx
0x1400fcb30  mov     dl, 2
0x1400fcb32  mov     rcx, cs:VmsIfrLog
0x1400fcb39  call    WPP_RECORDER_SF_Z
0x1400fcb3e  mov     [rsp+1B8h+var_174], 0C0000184h
0x1400fcb46  mov     dword ptr [rsp+1B8h+var_16C], ebx
0x1400fcb4a  lea     rdx, loc_1400FCE60
0x1400fcb51  mov     rcx, [rsp+1B8h+var_150]
0x1400fcb56  call    _local_unwind_0
0x1400fcb5b  mov     [rbx+5C8h], r15
0x1400fcb62  mov     [rbx+5D0h], r12
0x1400fcb69  cmp     cs:VmsIsUnloadForServicing, dil
0x1400fcb70  jnz     short loc_1400FCB86
0x1400fcb72  mov     r8d, 2
0x1400fcb78  mov     dl, r8b
0x1400fcb7b  mov     rcx, rbx
0x1400fcb7e  call    VmsOmObjectPrepareForConfigStore
0x1400fcb83  mov     r13b, al
0x1400fcb86  mov     dword ptr [rbx+44h], 2
0x1400fcb8d  lea     rdx, [rsp+1B8h+LockState]; LockState
0x1400fcb92  mov     rcx, [rbx+38h]; Lock
0x1400fcb96  call    cs:__imp_NdisReleaseRWLock
0x1400fcb9d  nop     dword ptr [rax+rax+00h]
0x1400fcba2  nop
0x1400fcba3  lea     rdx, [rsp+1B8h+var_170]; LockState
0x1400fcba8  mov     rcx, cs:VmsOmObjectListLock; Lock
0x1400fcbaf  call    cs:__imp_NdisReleaseRWLock
0x1400fcbb6  nop     dword ptr [rax+rax+00h]
0x1400fcbbb  cmp     cs:VmsIsUnloadForServicing, dil
0x1400fcbc2  jnz     short loc_1400FCBD2
0x1400fcbc4  lea     rcx, [rbx+48h]
0x1400fcbc8  xor     r8d, r8d
0x1400fcbcb  xor     edx, edx
0x1400fcbcd  call    VmsOmMarkObjectConfigDeletion
0x1400fcbd2  mov     rcx, [rbx+2488h]; void *
0x1400fcbd9  test    rcx, rcx
0x1400fcbdc  jz      short loc_1400FCBEA
0x1400fcbde  call    NvIoShutdownWorkerQueue
0x1400fcbe3  mov     [rbx+2488h], rdi
0x1400fcbea  mov     esi, 0FEh
0x1400fcbef  mov     r8, rsi; Size
0x1400fcbf2  xor     edx, edx; Val
0x1400fcbf4  lea     rcx, [rsp+1B8h+var_138]; void *
0x1400fcbfc  call    memset
0x1400fcc01  mov     qword ptr [rsp+1B8h+DestinationString.Length], 0FE0000h
0x1400fcc0a  lea     rax, [rsp+1B8h+var_138]
0x1400fcc12  mov     [rsp+1B8h+DestinationString.Buffer], rax
0x1400fcc17  xor     r8d, r8d
0x1400fcc1a  lea     rdx, [rsp+1B8h+LockState]
0x1400fcc1f  mov     rcx, rbx
0x1400fcc22  call    VmsOmObjectLockShared
0x1400fcc27  lea     rcx, [rbx+588h]
0x1400fcc2e  mov     rax, [rcx]
0x1400fcc31  cmp     rax, rcx
0x1400fcc34  jz      short loc_1400FCC56
0x1400fcc36  lea     rdx, [rax+48h]; SourceString
0x1400fcc3a  cmp     dword ptr [rax+44h], 2
0x1400fcc3e  jnz     short loc_1400FCC45
0x1400fcc40  mov     rax, [rax]
0x1400fcc43  jmp     short loc_1400FCC31
0x1400fcc45  lea     rcx, [rsp+1B8h+DestinationString]; DestinationString
0x1400fcc4a  call    cs:__imp_RtlCopyUnicodeString
0x1400fcc51  nop     dword ptr [rax+rax+00h]
0x1400fcc56  lea     rdx, [rsp+1B8h+LockState]; LockState
0x1400fcc5b  mov     rcx, [rbx+38h]; Lock
0x1400fcc5f  call    cs:__imp_NdisReleaseRWLock
0x1400fcc66  nop     dword ptr [rax+rax+00h]
0x1400fcc6b  cmp     [rsp+1B8h+DestinationString.Length], di
0x1400fcc70  jbe     short loc_1400FCC8B
0x1400fcc72  lea     rcx, [rbx+48h]
0x1400fcc76  xor     r9d, r9d
0x1400fcc79  xor     r8d, r8d
0x1400fcc7c  lea     rdx, [rsp+1B8h+DestinationString]
0x1400fcc81  call    VmsOmPortDelete
0x1400fcc86  jmp     loc_1400FCBEF
0x1400fcc8b  mov     rcx, rbx
0x1400fcc8e  call    VmsOmSwitchCleanupDefaultObjects
0x1400fcc93  cmp     [rbx+580h], dil
0x1400fcc9a  jz      short loc_1400FCCB6
0x1400fcc9c  lea     rcx, [rbx+500h]; Lookaside
0x1400fcca3  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400fccaa  nop     dword ptr [rax+rax+00h]
0x1400fccaf  mov     [rbx+580h], dil
0x1400fccb6  mov     rcx, rbx
0x1400fccb9  call    VmsOmpSwitchStormLimitUninitialize
0x1400fccbe  lea     rcx, [rbx+23E0h]
0x1400fccc5  call    VmsOmpRscStructsFree
0x1400fccca  mov     rcx, [rbx+21E8h]; P
0x1400fccd1  test    rcx, rcx
0x1400fccd4  jz      short loc_1400FCCE2
0x1400fccd6  call    VmsScQosDeleteLine
0x1400fccdb  mov     [rbx+21E8h], rdi
0x1400fcce2  lea     rcx, [rbx+2180h]; HashTable
0x1400fcce9  call    VmsOmpDestroyInMemoryPropertiesHashTable
0x1400fccee  mov     rcx, [rbx+1440h]; VirtualAddress
0x1400fccf5  test    rcx, rcx
0x1400fccf8  jz      short loc_1400FCD18
0x1400fccfa  mov     edx, 74527356h; Tag
0x1400fccff  call    cs:__imp_NdisFreeMemoryWithTag
0x1400fcd06  nop     dword ptr [rax+rax+00h]
0x1400fcd0b  mov     [rbx+1440h], rdi
0x1400fcd12  mov     [rbx+1438h], edi
0x1400fcd18  mov     rcx, [rbx+2408h]; VirtualAddress
0x1400fcd1f  test    rcx, rcx
0x1400fcd22  jz      short loc_1400FCD42
0x1400fcd24  mov     edx, 63507356h; Tag
0x1400fcd29  call    cs:__imp_NdisFreeMemoryWithTag
0x1400fcd30  nop     dword ptr [rax+rax+00h]
0x1400fcd35  mov     [rbx+2408h], rdi
0x1400fcd3c  mov     [rbx+2404h], edi
0x1400fcd42  mov     rcx, rbx
0x1400fcd45  call    VmsExtIoDeleteEdgeCounters
0x1400fcd4a  lea     rcx, [rbx+1908h]; void *
0x1400fcd51  call    PktMonClientComponentUnregister
0x1400fcd56  lea     rcx, [rbx+2330h]
0x1400fcd5d  call    PktCapClientUninitialize
0x1400fcd62  cmp     [rbx+22C8h], dil
0x1400fcd69  jz      loc_1400FCE4D
0x1400fcd6f  cmp     cs:VmsIsUnloadForServicing, dil
0x1400fcd76  jnz     loc_1400FCE4D
0x1400fcd7c  cmp     cs:VmsPDClientHandle, rdi
0x1400fcd83  jnz     short loc_1400FCDC1
0x1400fcd85  mov     r9d, 1Fh
0x1400fcd8b  lea     rax, aVmspdclienthan; "VmsPDClientHandle != NULL"
0x1400fcd92  mov     [rsp+1B8h+var_190], rax
0x1400fcd97  lea     rax, WPP_36fe39b6c6f63418e63dbb80804d1758_Traceguids
0x1400fcd9e  mov     [rsp+1B8h+Timeout], rax
0x1400fcda3  lea     r8d, [r9-0Ch]
0x1400fcda7  mov     rcx, cs:VmsIfrLog
0x1400fcdae  call    WPP_RECORDER_SF_s
0x1400fcdb3  cmp     cs:VmsPDClientHandle, rdi
0x1400fcdba  jnz     short loc_1400FCDC1
0x1400fcdbc  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "VmsPDClientHandle != ((void *)0)")
0x1400fcdc1  mov     [rsp+1B8h+Timeout], rdi; Timeout
0x1400fcdc6  xor     r9d, r9d; Alertable
0x1400fcdc9  xor     r8d, r8d; WaitMode
0x1400fcdcc  xor     edx, edx; WaitReason
0x1400fcdce  lea     rcx, VmsOmIoctlMutex; Object
0x1400fcdd5  call    cs:__imp_KeWaitForSingleObject
0x1400fcddc  nop     dword ptr [rax+rax+00h]
0x1400fcde1  mov     rcx, [rbx+22E0h]
0x1400fcde8  test    rcx, rcx
0x1400fcdeb  jz      short loc_1400FCE07
0x1400fcded  mov     rax, cs:VmsPDPlatformDispatch
0x1400fcdf4  mov     rax, [rax+0A0h]
0x1400fcdfb  call    _guard_dispatch_icall
0x1400fce00  mov     [rbx+22E0h], rdi
0x1400fce07  add     cs:VmsPDSwitchCount, 0FFFFFFFFh
0x1400fce0e  jnz     short loc_1400FCE38
0x1400fce10  mov     rax, cs:VmsPDPlatformDispatch
0x1400fce17  mov     rax, [rax+0E8h]
0x1400fce1e  mov     rcx, cs:VmsPDClientHandle
0x1400fce25  call    _guard_dispatch_icall
0x1400fce2a  mov     cs:VmsPDClientHandle, rdi
0x1400fce31  mov     cs:VmsPDPlatformDispatch, rdi
0x1400fce38  xor     edx, edx; Wait
0x1400fce3a  lea     rcx, VmsOmIoctlMutex; Mutex
0x1400fce41  call    cs:__imp_KeReleaseMutex
0x1400fce48  nop     dword ptr [rax+rax+00h]
0x1400fce4d  cmp     r13b, 1
0x1400fce51  jnz     short loc_1400FCE60
0x1400fce53  mov     edx, 2
0x1400fce58  mov     rcx, rbx; Src
0x1400fce5b  call    VmsOmSwitchStoreConfig
0x1400fce60  mov     ecx, [rsp+1B8h+var_174]
0x1400fce64  xor     edi, edi
0x1400fce66  mov     rsi, [rsp+1B8h+var_148]
0x1400fce6b  test    ecx, ecx
0x1400fce6d  jnz     short loc_1400FCED1
0x1400fce6f  mov     rdi, [rsp+1B8h+Src]
0x1400fce74  lea     rbx, [rdi+268h]
0x1400fce7b  movzx   edx, byte ptr [rdi+4D0h]
0x1400fce82  mov     eax, [rdi+23B8h]
0x1400fce88  mov     dword ptr [rsp+1B8h+var_188], eax
0x1400fce8c  mov     dword ptr [rsp+1B8h+var_190], edx
0x1400fce90  mov     [rsp+1B8h+Timeout], rbx
0x1400fce95  mov     r9, rsi
0x1400fce98  lea     rcx, VM_SWITCH_SUCCESSFULLY_DELETED
0x1400fce9f  call    VmsEtwTraceSwitchSuccess
0x1400fcea4  mov     r9d, 20h ; ' '
0x1400fceaa  mov     [rsp+1B8h+var_180], rdi
0x1400fceaf  mov     [rsp+1B8h+var_188], rbx
0x1400fceb4  mov     [rsp+1B8h+var_190], rsi
0x1400fceb9  mov     rcx, cs:VmsIfrLog
0x1400fcec0  call    WPP_RECORDER_SF_ZZq
0x1400fcec5  mov     dl, 0FFh
0x1400fcec7  mov     rcx, rdi
0x1400fceca  call    VmsOmpObjectDereference
0x1400fcecf  jmp     short loc_1400FCF1F
0x1400fced1  movzx   eax, [rsp+1B8h+arg_18]
0x1400fced9  mov     dword ptr [rsp+1B8h+var_180], ecx
0x1400fcedd  mov     dword ptr [rsp+1B8h+var_188], eax
0x1400fcee1  mov     [rsp+1B8h+var_190], rsi
0x1400fcee6  call    WPP_RECORDER_SF_Zld
0x1400fceeb  mov     rax, [rsp+1B8h+Src]
0x1400fcef0  test    rax, rax
0x1400fcef3  jz      short loc_1400FCEFC
0x1400fcef5  lea     rdi, [rax+268h]
0x1400fcefc  mov     [rsp+1B8h+var_188], rdi; __int64
0x1400fcf01  mov     [rsp+1B8h+var_190], rsi; __int64
0x1400fcf06  mov     eax, dword ptr [rsp+1B8h+var_16C]
0x1400fcf0a  mov     dword ptr [rsp+1B8h+Timeout], eax; char
0x1400fcf0e  lea     r9, [rsp+1B8h+var_174]
0x1400fcf13  lea     rcx, VM_DELETE_SWITCH_FAILED; EventDescriptor
0x1400fcf1a  call    VmsEtwTraceSwitchFailure
0x1400fcf1f  mov     edx, [rsp+1B8h+var_174]
0x1400fcf23  mov     rcx, rsi
0x1400fcf26  call    VmsTraceLoggingSwitchDelete
0x1400fcf2b  mov     eax, [rsp+1B8h+var_174]
0x1400fcf2f  mov     rcx, [rsp+1B8h+var_38]
0x1400fcf37  xor     rcx, rsp; StackCookie
0x1400fcf3a  call    __security_check_cookie
0x1400fcf3f  lea     r11, [rsp+1B8h+var_28]
0x1400fcf47  mov     rbx, [r11+38h]
0x1400fcf4b  mov     rsi, [r11+40h]
0x1400fcf4f  mov     rsp, r11
0x1400fcf52  pop     r15
0x1400fcf54  pop     r14
0x1400fcf56  pop     r13
0x1400fcf58  pop     r12
0x1400fcf5a  pop     rdi
0x1400fcf5b  retn
0x1401bcb6c  push    rbp
0x1401bcb6e  sub     rsp, 40h
  ... truncated ...
```
