# WinNatCreateSessionEntry

- ea: `0x140009b04`
- end: `0x14000a631`
- name: `WinNatCreateSessionEntry`
- size: `2861`
- prototype: `char *__fastcall(__int64, __int64, __int16 *, __int16 *, __int64, __int16 *, __int16 *, char, unsigned __int8, int *, __int64)`
- caller_count: `3`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003830`
- `0x140006f04`
- `0x14001c4e4`

## callees

- `0x140004648`
- `0x140004c40`
- `0x14000623c`
- `0x140008a7c`
- `0x140009178`
- `0x140009b04`
- `0x14000a638`
- `0x14000b220`
- `0x14000b80c`
- `0x14000b8d0`
- `0x14000bb38`
- `0x14000bf78`
- `0x14000c554`
- `0x14000c990`
- `0x14000caa0`
- `0x14000e488`
- `0x140018bf0`
- `0x1400199fc`
- `0x140019be8`
- `0x14001aaa8`
- `0x14001ab70`
- `0x14001b4b4`
- `0x14001ede0`
- `0x14001f440`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000a293`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000a293`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009c4d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a1ed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a61d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009c4d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a1ed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000a61d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a1aa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000a1aa`
- `ntoskrnl!KeInitializeSpinLock` at `0x140009fff`
- `ntoskrnl!KeInitializeSpinLock` at `0x140009fff`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140009d9e`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140009d9e`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14000a2fb`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14000a31c`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14000a33d`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14000a2fb`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14000a31c`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14000a33d`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140009d75`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140009d75`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140009e8e`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140009e8e`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x14000a5cb`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x14000a5cb`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x14000a271`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x14000a271`

## pseudocode

```c
char *__fastcall WinNatCreateSessionEntry(
        __int64 a1,
        __int64 a2,
        __int16 *a3,
        __int16 *a4,
        __int64 a5,
        __int16 *a6,
        __int16 *a7,
        char a8,
        unsigned __int8 a9,
        int *a10,
        __int64 a11)
{
  __int16 v11; // ax
  unsigned __int8 v13; // r12
  unsigned int v15; // ebx
  int v16; // edx
  __int64 v17; // rdx
  __int64 v18; // rcx
  struct _LIST_ENTRY **v19; // rdi
  __int64 v20; // r8
  int Binding; // ebx
  int v22; // eax
  __int64 *v23; // rbx
  bool v24; // zf
  unsigned __int64 v25; // rbx
  _OWORD *ErrorLogEntry; // rax
  __int64 v28; // rcx
  char *v29; // rax
  __int64 v30; // rsi
  __int64 v31; // rdx
  __int64 v32; // r8
  _DWORD *v33; // r10
  __int64 v34; // rdx
  _DWORD *v35; // r11
  int v36; // eax
  __int64 v37; // rdx
  __int16 *v38; // rax
  __int64 v39; // rdx
  unsigned int v40; // eax
  _WORD *v41; // rdi
  char v42; // r12
  _WORD *v43; // rbx
  char v44; // r8
  char v45; // cl
  _WORD *v46; // rax
  int v47; // r9d
  _WORD *v48; // rsi
  __int64 v49; // r10
  __int16 v50; // ax
  int v51; // edx
  __int16 v52; // ax
  char v53; // r10
  int v54; // r9d
  int v55; // r8d
  int v56; // edx
  char v57; // cl
  __int64 v58; // rdi
  __int64 v59; // rcx
  __int64 i; // rdx
  __int64 v61; // rcx
  int v62; // edx
  __int64 v63; // rax
  int v64; // esi
  __int16 *v65; // rcx
  int v66; // r8d
  int *v67; // r14
  int v68; // edx
  int v69; // ecx
  int v70; // r9d
  __int16 *v71; // rcx
  int v72; // r8d
  int v73; // ecx
  int v74; // eax
  int v75; // ecx
  char v76; // [rsp+70h] [rbp-90h]
  int *v77; // [rsp+78h] [rbp-88h]
  __int16 *v78; // [rsp+80h] [rbp-80h]
  unsigned int v79; // [rsp+80h] [rbp-80h]
  unsigned int v80; // [rsp+88h] [rbp-78h]
  unsigned int Signature; // [rsp+90h] [rbp-70h]
  _WORD *v83; // [rsp+98h] [rbp-68h]
  char *v84; // [rsp+A0h] [rbp-60h]
  size_t v86; // [rsp+B8h] [rbp-48h]
  struct _KLOCK_QUEUE_HANDLE v87; // [rsp+C0h] [rbp-40h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD v89[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v90[16]; // [rsp+110h] [rbp+10h] BYREF
  __int16 v91[16]; // [rsp+130h] [rbp+30h] BYREF
  __int16 v92[16]; // [rsp+150h] [rbp+50h] BYREF

  v11 = *a4;
  v13 = a8;
  memset(v89, 0, 28);
  v78 = a3;
  memset(&v87, 0, sizeof(v87));
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( *a3 != v11 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(0, a2);
    a3 = v78;
  }
  if ( a10 )
  {
    v15 = a10[14];
    v16 = *a10;
  }
  else
  {
    v15 = 0;
    v16 = 1;
  }
  v19 = WinNatAcquireBinding(a1, v16, a3, a5, a8, a2, v15, a11);
  if ( !v19 )
    return 0;
  v76 = 0;
  if ( dword_1400264E8 > 0 && ((_BYTE)v19[11] & 1) != 0 && !a6 )
  {
    if ( !a2 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v18, v17);
    RtlAcquireScalableWriteLock(a1 + 832, &LockHandle);
    Binding = WinNatAllocateBinding(a1 + 768, (__int64)v19, a2, v15, 0, (_OWORD *)a11);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( Binding < 0 )
      return 0;
    v13 = a8;
    v76 = 1;
    v18 = WORD1(v19[13]->Flink);
    LOWORD(v89[0]) = 2;
    DWORD1(v89[0]) = *(_DWORD *)(a11 + 80);
    WORD1(v89[0]) = v18;
  }
  v22 = *((_DWORD *)v19 + 23);
  v23 = (__int64 *)(a1 + 128);
  if ( a10 )
    v24 = v22 == *a10;
  else
    v24 = v22 == 1;
  if ( !v24 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v18, v17);
  if ( (*(_BYTE *)(a1 + 756) & 2) != 0 )
  {
    if ( !SessionSizeLimit )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v18, v17);
    if ( (unsigned __int64)(a9 != 0 ? 0x18 : 0) + 336 + SessionSize > SessionSizeLimit )
    {
      if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_WINNAT_ETW_PROVIDER_Context,
          v17,
          v20,
          L"Session allocation failed due size limit");
      v25 = MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x3E8;
      if ( !SessionLimitEventLoggedTick || (unsigned int)(v25 - SessionLimitEventLoggedTick) > 0x15180 )
      {
        ErrorLogEntry = IoAllocateErrorLogEntry(WinNatDriverObject, 0x30u);
        if ( ErrorLogEntry )
        {
          *ErrorLogEntry = 0;
          ErrorLogEntry[1] = 0;
          ErrorLogEntry[2] = 0;
          *((_DWORD *)ErrorLogEntry + 3) = -2147466648;
          IoWriteErrorLogEntry(ErrorLogEntry);
          SessionLimitEventLoggedTick = v25;
        }
      }
      if ( (unsigned __int8)WinNatReleaseBinding(v19) )
        WinNatCleanupBinding(v19);
      return 0;
    }
  }
  if ( a9 )
    v28 = *v23;
  else
    v28 = *(_QWORD *)(a1 + 136);
  v29 = (char *)PplAllocateFromLookasideList(v28, v17);
  v84 = v29;
  v30 = (__int64)v29;
  if ( !v29 )
  {
    if ( (unsigned __int8)WinNatReleaseBinding(v19) )
      WinNatCleanupBinding(v19);
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_WINNAT_ETW_PROVIDER_Context, v31, v32, L"Session allocation failed");
    return 0;
  }
  v86 = a9 != 0 ? 360LL : 336LL;
  memset(v29, 0, v86);
  *(_DWORD *)(v30 + 120) = v13;
  *(_QWORD *)v30 = 1;
  *(_QWORD *)(v30 + 80) = v19;
  *(_BYTE *)(v30 + 256) = a9;
  *(_QWORD *)(v30 + 288) = v23;
  KeQuerySystemTimePrecise(v30 + 272);
  v24 = *(_DWORD *)(v30 + 120) == 17;
  v33 = (_DWORD *)(v30 + 124);
  v77 = (int *)(v30 + 136);
  *(_QWORD *)(v30 + 264) = v19[9][7].Flink[26].Blink;
  if ( v24 )
  {
    *v33 = HIDWORD(v19[9][7].Flink[23].Flink);
    v34 = (MEMORY[0xFFFFF78000000008] / 0x2710uLL * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
    *(_DWORD *)(v30 + 136) = HIDWORD(v19[9][7].Flink[23].Flink)
                           + ((v34 + ((MEMORY[0xFFFFF78000000008] / 0x2710uLL - v34) >> 1)) >> 9);
  }
  else
  {
    v77 = (int *)(v30 + 136);
  }
  v35 = (_DWORD *)(v30 + 136);
  if ( *(_DWORD *)(v30 + 120) == 6 )
  {
    *(_DWORD *)(v30 + 128) = HIDWORD(v19[9][7].Flink[23].Blink);
    *v33 = v19[9][7].Flink[23].Blink;
    *(_DWORD *)(v30 + 136) = MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x3E8 + 6;
  }
  v36 = *(_DWORD *)(v30 + 120);
  if ( v36 == 1 || (v35 = (_DWORD *)(v30 + 136), v36 == 58) )
  {
    *v33 = v19[9][7].Flink[24].Flink;
    v37 = (MEMORY[0xFFFFF78000000008] / 0x2710uLL * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
    *v35 = LODWORD(v19[9][7].Flink[24].Flink) + ((v37 + ((MEMORY[0xFFFFF78000000008] / 0x2710uLL - v37) >> 1)) >> 9);
  }
  KeInitializeSpinLock((PKSPIN_LOCK)(v30 + 240));
  v38 = (__int16 *)v89;
  if ( !v76 )
    v38 = a6;
  WinNatFillSessionAddresses(v30, (__int64)v19, v78, a4, v38, a7, a9);
  Signature = WinNatComputeSessionKeyFromSockaddr(v23, v78, a4);
  v79 = WinNatComputeSessionKeyFromTransportAddr(v23, *(_QWORD *)(v30 + 112), *(_QWORD *)(v30 + 104));
  if ( a10 )
    v39 = (unsigned int)*a10;
  else
    v39 = 1;
  v40 = WinNatComputeAddressFilterKeyFromTransportAddr(v23, v39, *(_QWORD *)(v30 + 104), *(_QWORD *)(v30 + 112));
  v41 = *(_WORD **)(v30 + 112);
  v42 = 4;
  v43 = *(_WORD **)(v30 + 96);
  v44 = 4;
  v80 = v40;
  v45 = 4;
  v46 = *(_WORD **)(v30 + 104);
  v47 = 4;
  v48 = *(_WORD **)(v30 + 88);
  v83 = v46;
  if ( *v41 != 2 )
    v44 = 16;
  v49 = (__int64)(v46 + 2);
  v24 = *v46 == 2;
  v50 = v46[1];
  if ( !v24 )
    v45 = 16;
  if ( *v43 != 2 )
    v47 = 16;
  v51 = 4;
  if ( *v48 != 2 )
    v51 = 16;
  v52 = WinNatFixupChecksum((int)v48 + 4, v51, (int)v43 + 4, v47, v48[1], v49, v45, (__int64)(v41 + 2), v44, v50);
  v53 = 4;
  v54 = 4;
  v55 = (_DWORD)v41 + 4;
  *((_WORD *)v84 + 126) = v52;
  v56 = 16;
  v57 = 4;
  if ( *v43 != 2 )
    v53 = 16;
  if ( *v48 != 2 )
    v57 = 16;
  if ( *v41 != 2 )
    v54 = 16;
  if ( *v83 != 2 )
    v42 = 16;
  LOBYTE(v56) = v42;
  v58 = a1 + 128;
  *((_WORD *)v84 + 127) = WinNatFixupChecksum(
                            (int)v83 + 4,
                            v56,
                            v55,
                            v54,
                            v83[1],
                            (__int64)(v48 + 2),
                            v57,
                            (__int64)(v43 + 2),
                            v53,
                            v48[1]);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 192), &v87);
  for ( i = 0; (int)i <= *(_DWORD *)(a1 + 200); i = (unsigned int)(i + 1) )
  {
    v59 = (__int64)(int)i << 6;
    while ( *(_DWORD *)(v59 + v58 + 128) )
      ;
  }
  if ( (*(_BYTE *)(a1 + 756) & 1) != 0 )
  {
    KeReleaseInStackQueuedSpinLock(&v87);
    if ( !(unsigned __int8)WinNatReleaseBinding(*((_QWORD *)v84 + 10)) )
      *((_QWORD *)v84 + 10) = 0;
    WinNatLibCleanupSession(v84);
    return 0;
  }
  if ( a10 )
  {
    *(_OWORD *)(v84 + 8) = *(_OWORD *)a10;
    *(_OWORD *)(v84 + 24) = *((_OWORD *)a10 + 1);
    *(_OWORD *)(v84 + 40) = *((_OWORD *)a10 + 2);
    *(_OWORD *)(v84 + 56) = *((_OWORD *)a10 + 3);
    *((_QWORD *)v84 + 9) = *((_QWORD *)a10 + 8);
  }
  else
  {
    *((_DWORD *)v84 + 2) = 1;
    if ( *((_DWORD *)v84 + 17) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v59, i);
  }
  RtlInitializeTimerWheelEntry(*(_QWORD *)(a1 + 600), v84 + 144, 0, 0);
  if ( (*(_BYTE *)(a1 + 756) & 2) != 0 )
    SessionSize += v86;
  v61 = 136LL * KeGetCurrentProcessorNumberEx(0);
  ++*(_QWORD *)(v61 + *(_QWORD *)(a1 + 1344) + 72);
  ++*(_QWORD *)(v61 + *(_QWORD *)(a1 + 1344) + 80);
  v62 = *((_DWORD *)v84 + 30);
  v63 = *(_QWORD *)(a1 + 1344);
  if ( v62 == 6 )
  {
    ++*(_DWORD *)(v61 + v63);
  }
  else if ( v62 == 17 )
  {
    ++*(_DWORD *)(v61 + v63 + 24);
  }
  else
  {
    ++*(_DWORD *)(v61 + v63 + 48);
  }
  RtlInsertEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 512), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v84 + 7, Signature, 0);
  RtlInsertEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 520), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v84 + 8, v79, 0);
  RtlInsertEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 528), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v84 + 9, v80, 0);
  if ( _InterlockedIncrement64((volatile signed __int64 *)v84) <= 1 )
    __fastfail(0xEu);
  v64 = 28;
  if ( (Microsoft_Windows_WinNatEnableBits & 1) == 0 )
    goto LABEL_104;
  if ( !dword_140026104 )
    goto LABEL_104;
  v65 = (__int16 *)*((_QWORD *)v84 + 11);
  memset(v90, 0, 28);
  memset(v92, 0, 28);
  memset(v89, 0, 28);
  memset(v91, 0, 28);
  WinNatCopyTransportAddrToSockAddr(v65, v90);
  WinNatCopyTransportAddrToSockAddr(*((__int16 **)v84 + 12), v92);
  WinNatCopyTransportAddrToSockAddr(*((__int16 **)v84 + 13), (__int16 *)v89);
  WinNatCopyTransportAddrToSockAddr(*((__int16 **)v84 + 14), v91);
  if ( dword_140026104 != 1 )
    goto LABEL_104;
  if ( (Microsoft_Windows_WinNatEnableBits & 1) != 0 )
  {
    v67 = v77;
    if ( (v84[132] & 1) != 0 )
      LOBYTE(v68) = 0;
    else
      v68 = *v77 - MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x3E8;
    v69 = 28;
    v70 = 28;
    if ( LOWORD(v89[0]) == 2 )
      v69 = 16;
    if ( v90[0] == 2 )
      v70 = 16;
    McTemplateK0qbr0br0qbr3br3qqqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      (unsigned int)WINNAT_SESSION_CREATE,
      v66,
      v70,
      (__int64)v90,
      (__int64)v92,
      v69,
      (__int64)v89,
      (__int64)v91,
      *((_DWORD *)v84 + 30),
      v68,
      *((_DWORD *)v84 + 62),
      *((_DWORD *)v84 + 2));
  }
  else
  {
LABEL_104:
    v67 = v77;
  }
  if ( (*(_BYTE *)(a1 + 756) & 2) != 0 && (Microsoft_Windows_WinNatEnableBits & 0x40) != 0 )
  {
    v71 = (__int16 *)*((_QWORD *)v84 + 11);
    memset(v89, 0, 28);
    memset(v91, 0, 28);
    memset(v90, 0, 28);
    memset(v92, 0, 28);
    WinNatCopyTransportAddrToSockAddr(v71, (__int16 *)v89);
    WinNatCopyTransportAddrToSockAddr(*((__int16 **)v84 + 12), v91);
    WinNatCopyTransportAddrToSockAddr(*((__int16 **)v84 + 13), v90);
    WinNatCopyTransportAddrToSockAddr(*((__int16 **)v84 + 14), v92);
    if ( (Microsoft_Windows_WinNatEnableBits & 0x40) != 0 )
    {
      v73 = 28;
      if ( v90[0] == 2 )
        v73 = 16;
      if ( LOWORD(v89[0]) == 2 )
        v64 = 16;
      McTemplateK0qbr0br0qbr3br3q_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        (unsigned int)WINNAT_SESSION_CREATE_OPERATIONAL,
        v72,
        v64,
        (__int64)v89,
        (__int64)v91,
        v73,
        (__int64)v90,
        (__int64)v92,
        *((_DWORD *)v84 + 30));
    }
  }
  v74 = *v67;
  if ( !*v67 )
    v74 = 1;
  v75 = *((_DWORD *)v84 + 40);
  *((_DWORD *)v84 + 41) = v74;
  if ( !v75 || v74 - v75 < 0 )
    RtlIndicateTimerWheelEntryTimerStart(*(_QWORD *)(a1 + 600), v84 + 144);
  if ( (unsigned __int8)WinNatIsTimerRestartNeeded(v58, v84) )
    WinNatRestartSessionTimer(v58, (unsigned int)*v67);
  if ( (unsigned __int8)WinNatHashTableRestructureRequired(*(_QWORD *)(a1 + 512))
    || (unsigned __int8)WinNatHashTableRestructureRequired(*(_QWORD *)(a1 + 520)) )
  {
    WinNatScheduleRestructureDpc(a1);
  }
  KeReleaseInStackQueuedSpinLock(&v87);
  return v84;
}

```

## disassembly

```asm
0x140009b04  push    rbp
0x140009b06  push    rbx
0x140009b07  push    rsi
0x140009b08  push    rdi
0x140009b09  push    r12
0x140009b0b  push    r13
0x140009b0d  push    r14
0x140009b0f  push    r15
0x140009b11  lea     rbp, [rsp-88h]
0x140009b19  sub     rsp, 188h
0x140009b20  mov     rax, cs:__security_cookie
0x140009b27  xor     rax, rsp
0x140009b2a  mov     [rbp+0C0h+var_50], rax
0x140009b2e  movzx   eax, word ptr [r9]
0x140009b32  mov     rsi, rcx
0x140009b35  mov     r14, [rbp+0C0h+arg_48]
0x140009b3c  xorps   xmm1, xmm1
0x140009b3f  mov     r12b, [rbp+0C0h+arg_38]
0x140009b46  xorps   xmm0, xmm0
0x140009b49  mov     rdi, [rbp+0C0h+arg_20]
0x140009b50  mov     r15, rdx
0x140009b53  mov     r13, [rbp+0C0h+arg_50]
0x140009b5a  mov     [rbp+0C0h+var_118], rcx
0x140009b5e  mov     rcx, [rbp+0C0h+arg_28]
0x140009b65  mov     [rbp+0C0h+var_138], rcx
0x140009b69  mov     rcx, [rbp+0C0h+arg_30]
0x140009b70  mov     [rbp+0C0h+Signature], rcx
0x140009b74  xor     ecx, ecx
0x140009b76  movups  [rbp+0C0h+var_D0], xmm1
0x140009b7a  mov     [rbp+0C0h+var_128], r9
0x140009b7e  mov     [rbp+0C0h+var_140], r8
0x140009b82  mov     [rbp+0C0h+var_110], r14
0x140009b86  mov     [rsp+1C0h+var_14F], r12b
0x140009b8b  movups  xmmword ptr [rbp+0C0h+var_100.LockQueue.Next], xmm0
0x140009b8f  mov     qword ptr [rbp+0C0h+var_100.OldIrql], rcx
0x140009b93  movups  [rbp+0C0h+var_D0+0Ch], xmm1
0x140009b97  mov     qword ptr [rbp+0C0h+LockHandle.OldIrql], rcx
0x140009b9b  movups  xmmword ptr [rbp+0C0h+LockHandle.LockQueue.Next], xmm0
0x140009b9f  cmp     [r8], ax
0x140009ba3  jz      short loc_140009BAE
0x140009ba5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140009baa  mov     r8, [rbp+0C0h+var_140]
0x140009bae  test    r14, r14
0x140009bb1  jz      short loc_140009BBC
0x140009bb3  mov     ebx, [r14+38h]
0x140009bb7  mov     edx, [r14]
0x140009bba  jmp     short loc_140009BC1
0x140009bbc  xor     ebx, ebx
0x140009bbe  lea     edx, [rbx+1]
0x140009bc1  mov     [rsp+1C0h+var_188], r13
0x140009bc6  mov     r9, rdi
0x140009bc9  mov     [rsp+1C0h+var_190], ebx
0x140009bcd  mov     rcx, rsi
0x140009bd0  mov     [rsp+1C0h+var_198], r15
0x140009bd5  mov     byte ptr [rsp+1C0h+var_1A0], r12b
0x140009bda  call    WinNatAcquireBinding
0x140009bdf  mov     rdi, rax
0x140009be2  xor     eax, eax
0x140009be4  test    rdi, rdi
0x140009be7  jz      loc_140009DC4
0x140009bed  cmp     cs:dword_1400264E8, eax
0x140009bf3  mov     [rsp+1C0h+var_150], al
0x140009bf7  jle     loc_140009C87
0x140009bfd  test    byte ptr [rdi+58h], 1
0x140009c01  jz      loc_140009C87
0x140009c07  cmp     [rbp+0C0h+var_138], rax
0x140009c0b  jnz     short loc_140009C87
0x140009c0d  lea     r12, [rsi+300h]
0x140009c14  test    r15, r15
0x140009c17  jnz     short loc_140009C1E
0x140009c19  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140009c1e  lea     rcx, [r12+40h]
0x140009c23  lea     rdx, [rbp+0C0h+LockHandle]
0x140009c27  call    RtlAcquireScalableWriteLock
0x140009c2c  mov     r9d, ebx
0x140009c2f  mov     [rsp+1C0h+var_198], r13
0x140009c34  mov     r8, r15
0x140009c37  mov     byte ptr [rsp+1C0h+var_1A0], 0
0x140009c3c  mov     rdx, rdi
0x140009c3f  mov     rcx, r12
0x140009c42  call    WinNatAllocateBinding
0x140009c47  lea     rcx, [rbp+0C0h+LockHandle]; LockHandle
0x140009c4b  mov     ebx, eax
0x140009c4d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140009c54  nop     dword ptr [rax+rax+00h]
0x140009c59  test    ebx, ebx
0x140009c5b  js      loc_140009DC4
0x140009c61  mov     rax, [rdi+68h]
0x140009c65  mov     r12b, [rsp+1C0h+var_14F]
0x140009c6a  mov     [rsp+1C0h+var_150], 1
0x140009c6f  movzx   ecx, word ptr [rax+2]
0x140009c73  mov     eax, 2
0x140009c78  mov     word ptr [rbp+0C0h+var_D0], ax
0x140009c7c  mov     eax, [r13+50h]
0x140009c80  mov     dword ptr [rbp+0C0h+var_D0+4], eax
0x140009c83  mov     word ptr [rbp+0C0h+var_D0+2], cx
0x140009c87  mov     eax, [rdi+5Ch]
0x140009c8a  lea     rbx, [rsi+80h]
0x140009c91  test    r14, r14
0x140009c94  jnz     short loc_140009C9B
0x140009c96  cmp     eax, 1
0x140009c99  jmp     short loc_140009C9E
0x140009c9b  cmp     eax, [r14]
0x140009c9e  jz      short loc_140009CA5
0x140009ca0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140009ca5  test    byte ptr [rbx+274h], 2
0x140009cac  mov     r13d, 150h
0x140009cb2  mov     r15b, [rbp+0C0h+arg_40]
0x140009cb9  jz      loc_140009DE7
0x140009cbf  mov     al, r15b
0x140009cc2  neg     al
0x140009cc4  sbb     rsi, rsi
0x140009cc7  and     esi, 18h
0x140009cca  add     rsi, r13
0x140009ccd  cmp     cs:SessionSizeLimit, 0
0x140009cd5  jnz     short loc_140009CDC
0x140009cd7  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140009cdc  mov     rcx, cs:SessionSize
0x140009ce3  add     rcx, rsi
0x140009ce6  cmp     rcx, cs:SessionSizeLimit
0x140009ced  jbe     loc_140009DE7
0x140009cf3  mov     ecx, 1
0x140009cf8  cmp     cs:dword_140026104, ecx
0x140009cfe  jnz     short loc_140009D1C
0x140009d00  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140009d07  jz      short loc_140009D1C
0x140009d09  lea     r9, aSessionAllocat_0; "Session allocation failed due size limi"...
0x140009d10  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140009d17  call    McTemplateK0z_EtwWriteTransfer
0x140009d1c  mov     rcx, 0FFFFF78000000008h
0x140009d26  mov     rax, 346DC5D63886594Bh
0x140009d30  mov     rcx, [rcx]
0x140009d33  mul     rcx
0x140009d36  mov     ecx, cs:SessionLimitEventLoggedTick
0x140009d3c  mov     rax, 624DD2F1A9FBE77h
0x140009d46  mov     rbx, rdx
0x140009d49  shr     rbx, 0Bh
0x140009d4d  mul     rbx
0x140009d50  sub     rbx, rdx
0x140009d53  shr     rbx, 1
0x140009d56  add     rbx, rdx
0x140009d59  shr     rbx, 9
0x140009d5d  test    ecx, ecx
0x140009d5f  jz      short loc_140009D6C
0x140009d61  mov     eax, ebx
0x140009d63  sub     eax, ecx
0x140009d65  cmp     eax, 15180h
0x140009d6a  jbe     short loc_140009DB0
0x140009d6c  mov     rcx, cs:WinNatDriverObject; IoObject
0x140009d73  mov     dl, 30h ; '0'; EntrySize
0x140009d75  call    cs:__imp_IoAllocateErrorLogEntry
0x140009d7c  nop     dword ptr [rax+rax+00h]
0x140009d81  test    rax, rax
0x140009d84  jz      short loc_140009DB0
0x140009d86  xorps   xmm0, xmm0
0x140009d89  mov     rcx, rax; ElEntry
0x140009d8c  movups  xmmword ptr [rax], xmm0
0x140009d8f  movups  xmmword ptr [rax+10h], xmm0
0x140009d93  movups  xmmword ptr [rax+20h], xmm0
0x140009d97  mov     dword ptr [rax+0Ch], 80004268h
0x140009d9e  call    cs:__imp_IoWriteErrorLogEntry
0x140009da5  nop     dword ptr [rax+rax+00h]
0x140009daa  mov     cs:SessionLimitEventLoggedTick, ebx
0x140009db0  mov     rcx, rdi
0x140009db3  call    WinNatReleaseBinding
0x140009db8  test    al, al
0x140009dba  jz      short loc_140009DC4
0x140009dbc  mov     rcx, rdi
0x140009dbf  call    WinNatCleanupBinding
0x140009dc4  xor     eax, eax
0x140009dc6  mov     rcx, [rbp+0C0h+var_50]
0x140009dca  xor     rcx, rsp; StackCookie
0x140009dcd  call    __security_check_cookie
0x140009dd2  add     rsp, 188h
0x140009dd9  pop     r15
0x140009ddb  pop     r14
0x140009ddd  pop     r13
0x140009ddf  pop     r12
0x140009de1  pop     rdi
0x140009de2  pop     rsi
0x140009de3  pop     rbx
0x140009de4  pop     rbp
0x140009de5  retn
0x140009de7  test    r15b, r15b
0x140009dea  jnz     short loc_140009DF2
0x140009dec  mov     rcx, [rbx+8]
0x140009df0  jmp     short loc_140009DF5
0x140009df2  mov     rcx, [rbx]
0x140009df5  call    PplAllocateFromLookasideList
0x140009dfa  mov     [rbp+0C0h+var_120], rax
0x140009dfe  mov     rsi, rax
0x140009e01  test    rax, rax
0x140009e04  jnz     short loc_140009E48
0x140009e06  mov     rcx, rdi
0x140009e09  call    WinNatReleaseBinding
0x140009e0e  test    al, al
0x140009e10  jz      short loc_140009E1A
0x140009e12  mov     rcx, rdi
0x140009e15  call    WinNatCleanupBinding
0x140009e1a  mov     ecx, 1
0x140009e1f  cmp     cs:dword_140026104, ecx
0x140009e25  jnz     short loc_140009DC4
0x140009e27  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140009e2e  jz      short loc_140009DC4
0x140009e30  lea     r9, aSessionAllocat; "Session allocation failed"
0x140009e37  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140009e3e  call    McTemplateK0z_EtwWriteTransfer
0x140009e43  jmp     loc_140009DC4
0x140009e48  mov     al, r15b
0x140009e4b  mov     rcx, rsi; void *
0x140009e4e  neg     al
0x140009e50  sbb     rax, rax
0x140009e53  xor     edx, edx; Val
0x140009e55  and     eax, 18h
0x140009e58  add     rax, r13
0x140009e5b  mov     r8, rax; Size
0x140009e5e  mov     [rbp+0C0h+var_108], rax
0x140009e62  call    memset
0x140009e67  movzx   eax, r12b
0x140009e6b  lea     rcx, [rsi+110h]
0x140009e72  mov     [rsi+78h], eax
0x140009e75  mov     qword ptr [rsi], 1
0x140009e7c  mov     [rsi+50h], rdi
0x140009e80  mov     [rsi+100h], r15b
0x140009e87  mov     [rsi+120h], rbx
0x140009e8e  call    cs:__imp_KeQuerySystemTimePrecise
0x140009e95  nop     dword ptr [rax+rax+00h]
0x140009e9a  cmp     dword ptr [rsi+78h], 11h
0x140009e9e  lea     r9, [rsi+88h]
0x140009ea5  mov     rax, [rdi+48h]
0x140009ea9  lea     r10, [rsi+7Ch]
0x140009ead  mov     [rsp+1C0h+var_148], r9
0x140009eb2  mov     r13, 0FFFFF78000000008h
0x140009ebc  mov     r8, 346DC5D63886594Bh
0x140009ec6  mov     r12, 624DD2F1A9FBE77h
0x140009ed0  mov     rcx, [rax+70h]
0x140009ed4  mov     rax, [rcx+1A8h]
0x140009edb  mov     [rsi+108h], rax
0x140009ee2  jnz     short loc_140009F37
0x140009ee4  mov     rax, [rdi+48h]
0x140009ee8  mov     rcx, [rax+70h]
0x140009eec  mov     eax, [rcx+174h]
0x140009ef2  mov     [r10], eax
0x140009ef5  mov     rax, r8
0x140009ef8  mov     rcx, [r13+0]
0x140009efc  mul     rcx
0x140009eff  mov     rax, r12
0x140009f02  mov     r8, rdx
0x140009f05  shr     r8, 0Bh
0x140009f09  mul     r8
0x140009f0c  mov     rax, [rdi+48h]
0x140009f10  sub     r8, rdx
0x140009f13  shr     r8, 1
0x140009f16  add     r8, rdx
0x140009f19  mov     rcx, [rax+70h]
0x140009f1d  shr     r8, 9
0x140009f21  add     r8d, [rcx+174h]
0x140009f28  mov     [r9], r8d
0x140009f2b  mov     r8, 346DC5D63886594Bh
0x140009f35  jmp     short loc_140009F3C
0x140009f37  mov     [rsp+1C0h+var_148], r9
0x140009f3c  cmp     dword ptr [rsi+78h], 6
0x140009f40  jnz     short loc_140009F9A
0x140009f42  mov     rax, [rdi+48h]
0x140009f46  lea     r11, [rsi+88h]
0x140009f4d  mov     rcx, [rax+70h]
0x140009f51  mov     eax, [rcx+17Ch]
0x140009f57  mov     [rsi+80h], eax
0x140009f5d  mov     rax, [rdi+48h]
0x140009f61  mov     rcx, [rax+70h]
0x140009f65  mov     eax, [rcx+178h]
0x140009f6b  mov     [r10], eax
0x140009f6e  mov     rax, r8
0x140009f71  mov     rcx, [r13+0]
0x140009f75  mul     rcx
0x140009f78  mov     rax, r12
0x140009f7b  mov     rcx, rdx
0x140009f7e  shr     rcx, 0Bh
0x140009f82  mul     rcx
0x140009f85  sub     rcx, rdx
0x140009f88  shr     rcx, 1
0x140009f8b  add     rcx, rdx
0x140009f8e  shr     rcx, 9
0x140009f92  add     ecx, 6
0x140009f95  mov     [r11], ecx
0x140009f98  jmp     short loc_140009F9D
0x140009f9a  mov     r11, r9
0x140009f9d  mov     eax, [rsi+78h]
0x140009fa0  mov     ecx, 1
0x140009fa5  cmp     eax, ecx
0x140009fa7  jz      short loc_140009FB1
0x140009fa9  mov     r11, r9
0x140009fac  cmp     eax, 3Ah ; ':'
0x140009faf  jnz     short loc_140009FF8
0x140009fb1  mov     rax, [rdi+48h]
0x140009fb5  mov     rcx, [rax+70h]
0x140009fb9  mov     eax, [rcx+180h]
0x140009fbf  mov     [r10], eax
0x140009fc2  mov     rax, r8
0x140009fc5  mov     rcx, [r13+0]
  ... truncated ...
```
