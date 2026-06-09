# MpUnload

- ea: `0x14007bef0`
- end: `0x14007c12e`
- name: `MpUnload`
- size: `574`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400049dc`
- `0x140006334`
- `0x14000c428`
- `0x140077660`
- `0x140079464`
- `0x140079540`
- `0x140079778`
- `0x14007a060`
- `0x14007b5a0`
- `0x14007bca4`
- `0x14007bef0`
- `0x14007c130`
- `0x14007d008`
- `0x14007d264`
- `0x14007f8a8`
- `0x14007fa84`
- `0x140080834`
- `0x1400820ec`
- `0x140083b94`
- `0x1400842d8`
- `0x140084638`
- `0x14008475c`
- `0x140084924`
- `0x140084b5c`
- `0x1400854f8`
- `0x140085588`
- `0x140088a2c`
- `0x140088b40`
- `0x1400896dc`
- `0x14008aa0c`
- `0x14008aaac`
- `0x14008b270`

## import_xrefs

- `ntoskrnl!KeFlushQueuedDpcs` at `0x14007bfc5`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14007bfc5`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14007c0ba`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14007c0ba`
- `ntoskrnl!KeCancelTimer` at `0x14007bf9b`
- `ntoskrnl!KeCancelTimer` at `0x14007bfb5`
- `ntoskrnl!KeCancelTimer` at `0x14007bf9b`
- `ntoskrnl!KeCancelTimer` at `0x14007bfb5`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x14007bf14`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x14007bf35`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x14007bf14`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x14007bf35`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14007bfdf`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14007bfdf`
- `ntoskrnl!PsRemoveLoadImageNotifyRoutine` at `0x14007bf48`
- `ntoskrnl!PsRemoveLoadImageNotifyRoutine` at `0x14007bf48`
- `ntoskrnl!KeBugCheckEx` at `0x14007c01d`
- `ntoskrnl!KeBugCheckEx` at `0x14007c01d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c074`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c0e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c074`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c0e1`

## pseudocode

```c
__int64 __fastcall MpUnload(char a1)
{
  ULONG_PTR v2; // r8

  if ( (a1 & 1) == 0 )
    return 3223060496LL;
  MpRemoveImageVerificationCallback();
  MpUnregisterRegCallback();
  PsRemoveCreateThreadNotifyRoutine((PCREATE_THREAD_NOTIFY_ROUTINE)MpCreateThreadNotifyRoutine);
  if ( *(_QWORD *)(MpData + 40) )
    PsRemoveCreateThreadNotifyRoutine(MpCreateThreadNotifyRoutineEx);
  PsRemoveLoadImageNotifyRoutine((PLOAD_IMAGE_NOTIFY_ROUTINE)MpLoadImageNotifyRoutine);
  MpRemoveProcessNotifyRoutine();
  MpObShutdown();
  MpFreeCommPorts();
  MpFgAuditShutdown();
  MpDlpDeleteNetworkRedirectionInfo();
  MpAsyncScanShutdown();
  MpTearDownFltMgr();
  MpDlpShutdown();
  MpHashLibReleaseImpl(MpHashLibData);
  MpSeqDetectCtxShutdown();
  KeCancelTimer((PKTIMER)(MpData + 688));
  if ( !KeCancelTimer((PKTIMER)(MpData + 688)) )
    KeFlushQueuedDpcs();
  KeRemoveQueueDpc((PRKDPC)(MpData + 624));
  v2 = *(_QWORD *)(MpData + 552);
  if ( v2 != MpData + 552 )
    KeBugCheckEx(0x108u, (ULONG_PTR)&MpData, v2, *(_QWORD *)(MpData + 560), 0);
  MpCleanupDriverInfo();
  MpFgCleanup();
  MpRegShutdown();
  MpPowerStatusUninitialize(*(PVOID *)(MpData + 2456));
  *(_QWORD *)(MpData + 2456) = 0;
  MpShutdownProcessExclusions();
  if ( MpAsyncScanData )
  {
    ExFreePoolWithTag(MpAsyncScanData, 0x6461504Du);
    MpAsyncScanData = 0;
  }
  MpAsyncShutdown();
  MpTxfCleanup();
  MpDeleteBootSectorCache();
  MpShutdownThreadTable();
  MpShutdownProcessTable();
  MpCleanupDocOpenRules();
  MpShutdownBoostManager();
  MpFsHardeningRelease();
  ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)&gs_CopyCacheLookaside);
  MpFreeGlobals();
  MpObRundownRelease();
  MpTraceLogRelease();
  ExFreePoolWithTag((PVOID)MpData, 0x6466504Du);
  McGenEventUnregister_EtwUnregister();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_b960013237753183ac7a6d55d666ce86_Traceguids);
  WppCleanupKm();
  return 0;
}

```

## disassembly

```asm
0x14007bef0  sub     rsp, 38h
0x14007bef4  test    cl, 1
0x14007bef7  jnz     short loc_14007BF03
0x14007bef9  mov     eax, 0C01C0010h
0x14007befe  jmp     loc_14007C128
0x14007bf03  call    MpRemoveImageVerificationCallback
0x14007bf08  call    MpUnregisterRegCallback
0x14007bf0d  lea     rcx, MpCreateThreadNotifyRoutine; NotifyRoutine
0x14007bf14  call    cs:__imp_PsRemoveCreateThreadNotifyRoutine
0x14007bf1b  nop     dword ptr [rax+rax+00h]
0x14007bf20  mov     rax, cs:MpData
0x14007bf27  cmp     qword ptr [rax+28h], 0
0x14007bf2c  jz      short loc_14007BF41
0x14007bf2e  lea     rcx, MpCreateThreadNotifyRoutineEx; NotifyRoutine
0x14007bf35  call    cs:__imp_PsRemoveCreateThreadNotifyRoutine
0x14007bf3c  nop     dword ptr [rax+rax+00h]
0x14007bf41  lea     rcx, MpLoadImageNotifyRoutine; NotifyRoutine
0x14007bf48  call    cs:__imp_PsRemoveLoadImageNotifyRoutine
0x14007bf4f  nop     dword ptr [rax+rax+00h]
0x14007bf54  call    MpRemoveProcessNotifyRoutine
0x14007bf59  call    MpObShutdown
0x14007bf5e  call    MpFreeCommPorts
0x14007bf63  call    MpFgAuditShutdown
0x14007bf68  call    MpDlpDeleteNetworkRedirectionInfo
0x14007bf6d  call    MpAsyncScanShutdown
0x14007bf72  call    MpTearDownFltMgr
0x14007bf77  call    MpDlpShutdown
0x14007bf7c  mov     rcx, cs:MpHashLibData; P
0x14007bf83  call    MpHashLibReleaseImpl
0x14007bf88  call    MpSeqDetectCtxShutdown
0x14007bf8d  mov     rcx, cs:MpData
0x14007bf94  add     rcx, 2B0h; PKTIMER
0x14007bf9b  call    cs:__imp_KeCancelTimer
0x14007bfa2  nop     dword ptr [rax+rax+00h]
0x14007bfa7  mov     rcx, cs:MpData
0x14007bfae  add     rcx, 2B0h; PKTIMER
0x14007bfb5  call    cs:__imp_KeCancelTimer
0x14007bfbc  nop     dword ptr [rax+rax+00h]
0x14007bfc1  test    al, al
0x14007bfc3  jnz     short loc_14007BFD1
0x14007bfc5  call    cs:__imp_KeFlushQueuedDpcs
0x14007bfcc  nop     dword ptr [rax+rax+00h]
0x14007bfd1  mov     rcx, cs:MpData
0x14007bfd8  add     rcx, 270h; Dpc
0x14007bfdf  call    cs:__imp_KeRemoveQueueDpc
0x14007bfe6  nop     dword ptr [rax+rax+00h]
0x14007bfeb  mov     r9, cs:MpData
0x14007bff2  lea     rax, [r9+228h]
0x14007bff9  mov     r8, [rax]; BugCheckParameter2
0x14007bffc  cmp     r8, rax
0x14007bfff  jz      short loc_14007C02A
0x14007c001  mov     r9, [r9+230h]; BugCheckParameter3
0x14007c008  lea     rdx, MpData; BugCheckParameter1
0x14007c00f  mov     ecx, 108h; BugCheckCode
0x14007c014  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x14007c01d  call    cs:__imp_KeBugCheckEx
0x14007c02a  call    MpCleanupDriverInfo
0x14007c02f  call    MpFgCleanup
0x14007c034  call    MpRegShutdown
0x14007c039  mov     rcx, cs:MpData
0x14007c040  mov     rcx, [rcx+998h]; Handle
0x14007c047  call    MpPowerStatusUninitialize
0x14007c04c  mov     rax, cs:MpData
0x14007c053  mov     qword ptr [rax+998h], 0
0x14007c05e  call    MpShutdownProcessExclusions
0x14007c063  mov     rcx, cs:MpAsyncScanData; P
0x14007c06a  test    rcx, rcx
0x14007c06d  jz      short loc_14007C08B
0x14007c06f  mov     edx, 6461504Dh; Tag
0x14007c074  call    cs:__imp_ExFreePoolWithTag
0x14007c07b  nop     dword ptr [rax+rax+00h]
0x14007c080  mov     cs:MpAsyncScanData, 0
0x14007c08b  call    MpAsyncShutdown
0x14007c090  call    MpTxfCleanup
0x14007c095  call    MpDeleteBootSectorCache
0x14007c09a  call    MpShutdownThreadTable
0x14007c09f  call    MpShutdownProcessTable
0x14007c0a4  call    MpCleanupDocOpenRules
0x14007c0a9  call    MpShutdownBoostManager
0x14007c0ae  call    MpFsHardeningRelease
0x14007c0b3  lea     rcx, gs_CopyCacheLookaside; Lookaside
0x14007c0ba  call    cs:__imp_ExDeleteLookasideListEx
0x14007c0c1  nop     dword ptr [rax+rax+00h]
0x14007c0c6  call    MpFreeGlobals
0x14007c0cb  call    MpObRundownRelease
0x14007c0d0  call    MpTraceLogRelease
0x14007c0d5  mov     rcx, cs:MpData; P
0x14007c0dc  mov     edx, 6466504Dh; Tag
0x14007c0e1  call    cs:__imp_ExFreePoolWithTag
0x14007c0e8  nop     dword ptr [rax+rax+00h]
0x14007c0ed  call    McGenEventUnregister_EtwUnregister
0x14007c0f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c0f9  lea     rax, WPP_GLOBAL_Control
0x14007c100  cmp     rcx, rax
0x14007c103  jz      short loc_14007C121
0x14007c105  mov     eax, [rcx+2Ch]
0x14007c108  test    al, 2
0x14007c10a  jz      short loc_14007C121
0x14007c10c  mov     rcx, [rcx+18h]
0x14007c110  lea     r8, WPP_b960013237753183ac7a6d55d666ce86_Traceguids
0x14007c117  mov     edx, 25h ; '%'
0x14007c11c  call    WPP_SF_
0x14007c121  call    WppCleanupKm
0x14007c126  xor     eax, eax
0x14007c128  add     rsp, 38h
0x14007c12c  retn
```
