# RaidUnitAllocateResources

- ea: `0x140011974`
- end: `0x140011e84`
- name: `RaidUnitAllocateResources`
- size: `1296`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140011638`

## callees

- `0x14000684c`
- `0x14000ec74`
- `0x14000ff50`
- `0x140011974`
- `0x140011fc4`
- `0x1400120a0`
- `0x140012150`
- `0x1400290b0`
- `0x1401b9d20`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140011ca2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140011cdc`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140011ca2`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140011cdc`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011b8f`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011ba2`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011bbb`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011b8f`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011ba2`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011bbb`
- `ntoskrnl!KeInitializeTimer` at `0x140011a51`
- `ntoskrnl!KeInitializeTimer` at `0x140011acd`
- `ntoskrnl!KeInitializeTimer` at `0x140011ae0`
- `ntoskrnl!KeInitializeTimer` at `0x140011a51`
- `ntoskrnl!KeInitializeTimer` at `0x140011acd`
- `ntoskrnl!KeInitializeTimer` at `0x140011ae0`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140011cb5`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140011cb5`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140011c88`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140011c88`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140011e52`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140011e52`
- `ntoskrnl!KeInitializeEvent` at `0x1400119b2`
- `ntoskrnl!KeInitializeEvent` at `0x1400119b2`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140011b25`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140011b25`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400119f7`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400119f7`
- `ntoskrnl!KeInitializeDpc` at `0x140011a73`
- `ntoskrnl!KeInitializeDpc` at `0x140011a96`
- `ntoskrnl!KeInitializeDpc` at `0x140011ab7`
- `ntoskrnl!KeInitializeDpc` at `0x140011afe`
- `ntoskrnl!KeInitializeDpc` at `0x140011a73`
- `ntoskrnl!KeInitializeDpc` at `0x140011a96`
- `ntoskrnl!KeInitializeDpc` at `0x140011ab7`
- `ntoskrnl!KeInitializeDpc` at `0x140011afe`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140011e71`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140011e71`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011bcf`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011dd7`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011df7`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011e2c`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011bcf`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011dd7`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011df7`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011e2c`

## pseudocode

```c
__int64 __fastcall RaidUnitAllocateResources(__int64 a1)
{
  _DWORD **v1; // r15
  __int64 v2; // rbp
  __int64 v4; // rdx
  ULONG MaximumProcessorCount; // eax
  ULONG v6; // r8d
  __int64 v7; // rdx
  _QWORD *v8; // r14
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  int EventQueue; // ebx
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 v15; // r8
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 Pool; // rax
  USHORT CurrentNodeNumber; // ax
  PSLIST_ENTRY v20; // rax
  int v21; // edi
  unsigned int v22; // r14d
  unsigned int i; // ebx
  int v24; // ecx
  __int64 v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 ContiguousIoResources; // rax
  __int64 v30; // rdx
  __int64 v31; // rbx
  PIO_WORKITEM WorkItem; // rax
  PIO_WORKITEM v33; // rax
  struct _DEVICE_OBJECT *v34; // rcx
  PIO_WORKITEM v35; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *CacheAwareRundownProtection; // rax

  v1 = (_DWORD **)(a1 + 24);
  *(_DWORD *)(a1 + 1032) = 0x10000000;
  v2 = *(_QWORD *)(a1 + 24);
  *(_DWORD *)(a1 + 1824) = -1;
  KeInitializeEvent((PRKEVENT)(a1 + 520), SynchronizationEvent, 0);
  v4 = *(_QWORD *)(a1 + 32);
  if ( v4 )
  {
    *(_DWORD *)(v4 + 80) ^= (*(_DWORD *)(v4 + 80) ^ (unsigned __int8)g_OSisClient) & 1;
    **(_DWORD **)(a1 + 32) = 1;
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 32) + 80LL) & 1) != 0
      || (MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu), v6 = 0, !MaximumProcessorCount) )
    {
      v8 = v1;
    }
    else
    {
      do
      {
        v7 = v6++;
        *(_DWORD *)((v7 << 6) + *(_QWORD *)(a1 + 40) + 4) = 1;
      }
      while ( v6 < MaximumProcessorCount );
      v8 = (_QWORD *)(a1 + 24);
    }
    v9 = (_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL);
    v9[1] = v9;
    *v9 = v9;
    v10 = (_QWORD *)(*(_QWORD *)(a1 + 32) + 48LL);
    v10[1] = v10;
    *v10 = v10;
    KeInitializeTimer((PKTIMER)(*(_QWORD *)(a1 + 32) + 88LL));
    KeInitializeDpc((PRKDPC)(*(_QWORD *)(a1 + 32) + 152LL), RaidUnitPendingIrpDpcRoutine, *(PVOID *)(a1 + 8));
  }
  else
  {
    v8 = v1;
  }
  KeInitializeDpc((PRKDPC)(a1 + 1312), RaidUnitRestartQueueDpcRoutine, *(PVOID *)(a1 + 8));
  KeInitializeDpc((PRKDPC)(a1 + 1120), RaidUnitPendingDpcRoutine, *(PVOID *)(a1 + 8));
  KeInitializeTimer((PKTIMER)(a1 + 1056));
  KeInitializeTimer((PKTIMER)(a1 + 1184));
  KeInitializeDpc((PRKDPC)(a1 + 1248), RaidUnitPauseTimerDpcRoutine, *(PVOID *)(a1 + 8));
  KeSetCoalescableTimer((PKTIMER)(a1 + 1056), (LARGE_INTEGER)-20000000LL, 0x7D0u, 0x12Cu, (PKDPC)(a1 + 1120));
  EventQueue = StorCreateEventQueue(a1 + 560);
  if ( EventQueue < 0 )
    goto LABEL_18;
  if ( (unsigned __int8)RaidAdapterSupportsAbortCommand(*v8) )
    **(_DWORD **)(a1 + 560) |= 5u;
  if ( *(_DWORD *)v2 != 1094997074 || (*(_BYTE *)(v2 + 111) & 4) == 0 )
  {
    EventQueue = RaInitializeTagList(a1 + 576, (unsigned int)(*(_DWORD *)(v2 + 576) + 1), *(_QWORD *)(a1 + 8));
    if ( EventQueue < 0 )
      goto LABEL_18;
  }
  KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 48));
  KeInitializeSpinLock((PKSPIN_LOCK)(a1 + 1920));
  v12 = *(_QWORD *)(a1 + 32);
  if ( v12 )
  {
    KeInitializeSpinLock((PKSPIN_LOCK)(v12 + 24));
    v13 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(v13 + 64) = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(a1 + 8));
    if ( !*(_QWORD *)(*(_QWORD *)(a1 + 32) + 64LL) )
      goto LABEL_17;
  }
  v15 = *(unsigned int *)(v2 + 576);
  v16 = *(_QWORD *)(v2 + 1024);
  *(_QWORD *)(a1 + 704) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 712) = RaUnitStartIo;
  *(_DWORD *)(a1 + 912) = 0;
  RaidInitializeDeviceQueue(a1 + 720, v16, v15);
  v17 = *(_DWORD *)(v2 + 504);
  if ( v17 )
  {
    Pool = RaidAllocatePool(64, v17, 1163223378, *(_QWORD *)(a1 + 8));
    *(_QWORD *)(a1 + 16) = Pool;
    if ( !Pool )
    {
      EventQueue = -1073741801;
      goto LABEL_18;
    }
  }
  if ( *(_DWORD *)v2 != 1094997074 || (*(_BYTE *)(v2 + 111) & 4) == 0 )
  {
    CurrentNodeNumber = KeGetCurrentNodeNumber();
    v20 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(*(_QWORD *)(a1 + 576) + ((unsigned __int64)CurrentNodeNumber << 6)));
    if ( !v20 )
    {
      v21 = 0;
      v22 = KeQueryHighestNodeNumber() + 1;
      do
      {
        for ( i = 0; i < v22; ++i )
        {
          v20 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(*(_QWORD *)(a1 + 576) + ((unsigned __int64)i << 6)));
          if ( v20 )
            goto LABEL_32;
        }
        ++v21;
      }
      while ( v21 != 10 );
      goto LABEL_17;
    }
LABEL_32:
    v24 = *((_DWORD *)&v20->Next + 2);
    if ( v24 == -1 )
    {
LABEL_17:
      EventQueue = -1073741670;
LABEL_18:
      RaidUnitFreeResources(a1);
      return (unsigned int)EventQueue;
    }
    *(_DWORD *)(a1 + 1824) = v24;
  }
  v25 = 81;
  v26 = 81;
  if ( **v1 != 1314275652 )
    v26 = 127;
  v27 = (((*v1)[v26] + 7) & 0xFFFFFFF8) + 1200;
  v28 = (((*v1)[v26] + 7) & 0xFFFFFFF8) + 1344;
  if ( *(_BYTE *)(v2 + 466) != 1 )
    v28 = (unsigned int)v27;
  ContiguousIoResources = StorAllocateContiguousIoResources(v28, v27, v2);
  v31 = ContiguousIoResources;
  if ( !ContiguousIoResources )
    goto LABEL_17;
  *(_QWORD *)(a1 + 1840) = ContiguousIoResources + 48;
  *(_QWORD *)(a1 + 1848) = ContiguousIoResources + 944;
  *(_QWORD *)(a1 + 1832) = ContiguousIoResources + 1200;
  RaidZeroXrb(ContiguousIoResources + 48, v30, 0, 0);
  if ( *(_BYTE *)(v2 + 466) == 1 )
  {
    *(_DWORD *)(v31 + 792) = 144;
    if ( **v1 != 1314275652 )
      v25 = 127;
    *(_QWORD *)(v31 + 808) = v31 + (((*v1)[v25] + 7) & 0xFFFFFFF8) + 1200LL;
  }
  WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(a1 + 8));
  *(_QWORD *)(a1 + 1976) = WorkItem;
  if ( !WorkItem )
    goto LABEL_17;
  v33 = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(a1 + 8));
  *(_QWORD *)(a1 + 1992) = v33;
  if ( !v33 )
    goto LABEL_17;
  v34 = *(struct _DEVICE_OBJECT **)(a1 + 8);
  *(_QWORD *)(a1 + 2000) = 0;
  *(_DWORD *)(a1 + 2008) = 0;
  v35 = IoAllocateWorkItem(v34);
  *(_QWORD *)(a1 + 2016) = v35;
  if ( !v35 )
    goto LABEL_17;
  CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection(NonPagedPoolNx, 0x4F506152u);
  *(_QWORD *)(a1 + 1864) = CacheAwareRundownProtection;
  if ( !CacheAwareRundownProtection )
    goto LABEL_17;
  ExWaitForRundownProtectionReleaseCacheAware(CacheAwareRundownProtection);
  return 0;
}

```

## disassembly

```asm
0x140011974  push    rbx
0x140011976  push    rbp
0x140011977  push    rsi
0x140011978  push    rdi
0x140011979  push    r13
0x14001197b  push    r14
0x14001197d  push    r15
0x14001197f  sub     rsp, 30h
0x140011983  lea     r15, [rcx+18h]
0x140011987  mov     dword ptr [rcx+408h], 10000000h
0x140011991  mov     rbp, [r15]
0x140011994  xor     r8d, r8d; State
0x140011997  mov     rsi, rcx
0x14001199a  mov     dword ptr [rcx+720h], 0FFFFFFFFh
0x1400119a4  add     rcx, 208h; Event
0x1400119ab  lea     r13d, [r8+1]
0x1400119af  mov     edx, r13d; Type
0x1400119b2  call    cs:__imp_KeInitializeEvent
0x1400119b9  nop     dword ptr [rax+rax+00h]
0x1400119be  mov     rdx, [rsi+20h]
0x1400119c2  test    rdx, rdx
0x1400119c5  jz      loc_140011A81
0x1400119cb  mov     eax, [rdx+50h]
0x1400119ce  movzx   ecx, cs:g_OSisClient
0x1400119d5  xor     ecx, eax
0x1400119d7  and     ecx, r13d
0x1400119da  xor     ecx, eax
0x1400119dc  mov     [rdx+50h], ecx
0x1400119df  mov     rax, [rsi+20h]
0x1400119e3  mov     [rax], r13d
0x1400119e6  mov     rax, [rsi+20h]
0x1400119ea  mov     ecx, [rax+50h]
0x1400119ed  test    r13b, cl
0x1400119f0  jnz     short loc_140011A28
0x1400119f2  mov     ecx, 0FFFFh; GroupNumber
0x1400119f7  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400119fe  nop     dword ptr [rax+rax+00h]
0x140011a03  xor     r8d, r8d
0x140011a06  test    eax, eax
0x140011a08  jz      short loc_140011A28
0x140011a0a  mov     rcx, [rsi+28h]
0x140011a0e  mov     edx, r8d
0x140011a11  add     r8d, r13d
0x140011a14  shl     rdx, 6
0x140011a18  mov     [rdx+rcx+4], r13d
0x140011a1d  cmp     r8d, eax
0x140011a20  jb      short loc_140011A0A
0x140011a22  lea     r14, [rsi+18h]
0x140011a26  jmp     short loc_140011A2B
0x140011a28  mov     r14, r15
0x140011a2b  mov     rax, [rsi+20h]
0x140011a2f  add     rax, 20h ; ' '
0x140011a33  mov     [rax+8], rax
0x140011a37  mov     [rax], rax
0x140011a3a  mov     rax, [rsi+20h]
0x140011a3e  add     rax, 30h ; '0'
0x140011a42  mov     [rax+8], rax
0x140011a46  mov     [rax], rax
0x140011a49  mov     rcx, [rsi+20h]
0x140011a4d  add     rcx, 58h ; 'X'; Timer
0x140011a51  call    cs:__imp_KeInitializeTimer
0x140011a58  nop     dword ptr [rax+rax+00h]
0x140011a5d  mov     rcx, [rsi+20h]
0x140011a61  lea     rdx, RaidUnitPendingIrpDpcRoutine; DeferredRoutine
0x140011a68  mov     r8, [rsi+8]; DeferredContext
0x140011a6c  add     rcx, 98h; Dpc
0x140011a73  call    cs:__imp_KeInitializeDpc
0x140011a7a  nop     dword ptr [rax+rax+00h]
0x140011a7f  jmp     short loc_140011A84
0x140011a81  mov     r14, r15
0x140011a84  mov     r8, [rsi+8]; DeferredContext
0x140011a88  lea     rcx, [rsi+520h]; Dpc
0x140011a8f  lea     rdx, RaidUnitRestartQueueDpcRoutine; DeferredRoutine
0x140011a96  call    cs:__imp_KeInitializeDpc
0x140011a9d  nop     dword ptr [rax+rax+00h]
0x140011aa2  mov     r8, [rsi+8]; DeferredContext
0x140011aa6  lea     rdi, [rsi+460h]
0x140011aad  mov     rcx, rdi; Dpc
0x140011ab0  lea     rdx, RaidUnitPendingDpcRoutine; DeferredRoutine
0x140011ab7  call    cs:__imp_KeInitializeDpc
0x140011abe  nop     dword ptr [rax+rax+00h]
0x140011ac3  lea     rbx, [rsi+420h]
0x140011aca  mov     rcx, rbx; Timer
0x140011acd  call    cs:__imp_KeInitializeTimer
0x140011ad4  nop     dword ptr [rax+rax+00h]
0x140011ad9  lea     rcx, [rsi+4A0h]; Timer
0x140011ae0  call    cs:__imp_KeInitializeTimer
0x140011ae7  nop     dword ptr [rax+rax+00h]
0x140011aec  mov     r8, [rsi+8]; DeferredContext
0x140011af0  lea     rcx, [rsi+4E0h]; Dpc
0x140011af7  lea     rdx, RaidUnitPauseTimerDpcRoutine; DeferredRoutine
0x140011afe  call    cs:__imp_KeInitializeDpc
0x140011b05  nop     dword ptr [rax+rax+00h]
0x140011b0a  mov     rdx, 0FFFFFFFFFECED300h; DueTime
0x140011b11  mov     [rsp+68h+Dpc], rdi; Dpc
0x140011b16  mov     r9d, 12Ch; TolerableDelay
0x140011b1c  mov     r8d, 7D0h; Period
0x140011b22  mov     rcx, rbx; Timer
0x140011b25  call    cs:__imp_KeSetCoalescableTimer
0x140011b2c  nop     dword ptr [rax+rax+00h]
0x140011b31  lea     rdi, [rsi+230h]
0x140011b38  mov     rcx, rdi
0x140011b3b  call    StorCreateEventQueue
0x140011b40  mov     ebx, eax
0x140011b42  test    eax, eax
0x140011b44  js      loc_140011BEF
0x140011b4a  mov     rcx, [r14]
0x140011b4d  call    RaidAdapterSupportsAbortCommand
0x140011b52  test    al, al
0x140011b54  jz      short loc_140011B5C
0x140011b56  mov     rax, [rdi]
0x140011b59  or      dword ptr [rax], 5
0x140011b5c  mov     edi, 41445452h
0x140011b61  cmp     [rbp+0], edi
0x140011b64  jnz     short loc_140011B6C
0x140011b66  test    byte ptr [rbp+6Fh], 4
0x140011b6a  jnz     short loc_140011B8B
0x140011b6c  mov     edx, [rbp+240h]
0x140011b72  lea     rcx, [rsi+240h]
0x140011b79  mov     r8, [rsi+8]
0x140011b7d  add     edx, r13d
0x140011b80  call    RaInitializeTagList
0x140011b85  mov     ebx, eax
0x140011b87  test    eax, eax
0x140011b89  js      short loc_140011BEF
0x140011b8b  lea     rcx, [rsi+30h]; SpinLock
0x140011b8f  call    cs:__imp_KeInitializeSpinLock
0x140011b96  nop     dword ptr [rax+rax+00h]
0x140011b9b  lea     rcx, [rsi+780h]; SpinLock
0x140011ba2  call    cs:__imp_KeInitializeSpinLock
0x140011ba9  nop     dword ptr [rax+rax+00h]
0x140011bae  mov     rcx, [rsi+20h]
0x140011bb2  test    rcx, rcx
0x140011bb5  jz      short loc_140011C09
0x140011bb7  add     rcx, 18h; SpinLock
0x140011bbb  call    cs:__imp_KeInitializeSpinLock
0x140011bc2  nop     dword ptr [rax+rax+00h]
0x140011bc7  mov     rcx, [rsi+8]; DeviceObject
0x140011bcb  mov     rbx, [rsi+20h]
0x140011bcf  call    cs:__imp_IoAllocateWorkItem
0x140011bd6  nop     dword ptr [rax+rax+00h]
0x140011bdb  mov     [rbx+40h], rax
0x140011bdf  mov     rax, [rsi+20h]
0x140011be3  cmp     qword ptr [rax+40h], 0
0x140011be8  jnz     short loc_140011C09
0x140011bea  mov     ebx, 0C000009Ah
0x140011bef  mov     rcx, rsi
0x140011bf2  call    RaidUnitFreeResources
0x140011bf7  mov     eax, ebx
0x140011bf9  add     rsp, 30h
0x140011bfd  pop     r15
0x140011bff  pop     r14
0x140011c01  pop     r13
0x140011c03  pop     rdi
0x140011c04  pop     rsi
0x140011c05  pop     rbp
0x140011c06  pop     rbx
0x140011c07  retn
0x140011c09  mov     rax, [rsi+8]
0x140011c0d  lea     rcx, [rsi+2D0h]
0x140011c14  mov     r8d, [rbp+240h]
0x140011c1b  mov     rdx, [rbp+400h]
0x140011c22  mov     [rsi+2C0h], rax
0x140011c29  lea     rax, RaUnitStartIo
0x140011c30  mov     [rsi+2C8h], rax
0x140011c37  mov     dword ptr [rsi+390h], 0
0x140011c41  call    RaidInitializeDeviceQueue
0x140011c46  mov     eax, [rbp+1F8h]
0x140011c4c  test    eax, eax
0x140011c4e  jz      short loc_140011C79
0x140011c50  mov     r9, [rsi+8]
0x140011c54  mov     edx, eax
0x140011c56  mov     ecx, 40h ; '@'
0x140011c5b  mov     r8d, 45556152h
0x140011c61  call    RaidAllocatePool
0x140011c66  mov     [rsi+10h], rax
0x140011c6a  test    rax, rax
0x140011c6d  jnz     short loc_140011C79
0x140011c6f  mov     ebx, 0C0000017h
0x140011c74  jmp     loc_140011BEF
0x140011c79  cmp     [rbp+0], edi
0x140011c7c  jnz     short loc_140011C88
0x140011c7e  test    byte ptr [rbp+6Fh], 4
0x140011c82  jnz     loc_140011D11
0x140011c88  call    cs:__imp_KeGetCurrentNodeNumber
0x140011c8f  nop     dword ptr [rax+rax+00h]
0x140011c94  movzx   ecx, ax
0x140011c97  shl     rcx, 6
0x140011c9b  add     rcx, [rsi+240h]; ListHead
0x140011ca2  call    cs:__imp_ExpInterlockedPopEntrySList
0x140011ca9  nop     dword ptr [rax+rax+00h]
0x140011cae  test    rax, rax
0x140011cb1  jnz     short loc_140011CFF
0x140011cb3  xor     edi, edi
0x140011cb5  call    cs:__imp_KeQueryHighestNodeNumber
0x140011cbc  nop     dword ptr [rax+rax+00h]
0x140011cc1  movzx   r14d, ax
0x140011cc5  add     r14d, r13d
0x140011cc8  xor     ebx, ebx
0x140011cca  cmp     ebx, r14d
0x140011ccd  jnb     short loc_140011CF2
0x140011ccf  mov     ecx, ebx
0x140011cd1  shl     rcx, 6
0x140011cd5  add     rcx, [rsi+240h]; ListHead
0x140011cdc  call    cs:__imp_ExpInterlockedPopEntrySList
0x140011ce3  nop     dword ptr [rax+rax+00h]
0x140011ce8  test    rax, rax
0x140011ceb  jnz     short loc_140011CFF
0x140011ced  add     ebx, r13d
0x140011cf0  jmp     short loc_140011CCA
0x140011cf2  add     edi, r13d
0x140011cf5  cmp     edi, 0Ah
0x140011cf8  jnz     short loc_140011CC8
0x140011cfa  jmp     loc_140011BEA
0x140011cff  mov     ecx, [rax+8]
0x140011d02  cmp     ecx, 0FFFFFFFFh
0x140011d05  jz      loc_140011BEA
0x140011d0b  mov     [rsi+720h], ecx
0x140011d11  mov     rcx, [r15]
0x140011d14  mov     edx, 1FCh
0x140011d19  mov     r14d, 4E564144h
0x140011d1f  mov     edi, 144h
0x140011d24  mov     eax, edi
0x140011d26  mov     r8, rbp
0x140011d29  cmp     [rcx], r14d
0x140011d2c  cmovnz  eax, edx
0x140011d2f  mov     edx, [rax+rcx]
0x140011d32  mov     eax, 0FFFFFFF8h
0x140011d37  add     edx, 7
0x140011d3a  and     edx, eax
0x140011d3c  add     edx, 4B0h
0x140011d42  cmp     [rbp+1D2h], r13b
0x140011d49  lea     ecx, [rdx+90h]
0x140011d4f  cmovnz  ecx, edx
0x140011d52  call    StorAllocateContiguousIoResources
0x140011d57  mov     rbx, rax
0x140011d5a  test    rax, rax
0x140011d5d  jz      loc_140011BEA
0x140011d63  lea     rcx, [rax+30h]
0x140011d67  xor     r9d, r9d
0x140011d6a  add     rax, 3B0h
0x140011d70  mov     [rsi+730h], rcx
0x140011d77  mov     [rsi+738h], rax
0x140011d7e  xor     r8d, r8d
0x140011d81  lea     rax, [rbx+4B0h]
0x140011d88  mov     [rsi+728h], rax
0x140011d8f  call    RaidZeroXrb
0x140011d94  cmp     [rbp+1D2h], r13b
0x140011d9b  jnz     short loc_140011DD3
0x140011d9d  mov     dword ptr [rbx+318h], 90h
0x140011da7  mov     ecx, 1FCh
0x140011dac  mov     rax, [r15]
0x140011daf  cmp     [rax], r14d
0x140011db2  cmovnz  edi, ecx
0x140011db5  mov     ecx, [rdi+rax]
0x140011db8  mov     eax, 0FFFFFFF8h
0x140011dbd  add     ecx, 7
0x140011dc0  and     rax, rcx
0x140011dc3  add     rax, 4B0h
0x140011dc9  add     rax, rbx
0x140011dcc  mov     [rbx+328h], rax
0x140011dd3  mov     rcx, [rsi+8]; DeviceObject
0x140011dd7  call    cs:__imp_IoAllocateWorkItem
0x140011dde  nop     dword ptr [rax+rax+00h]
0x140011de3  mov     [rsi+7B8h], rax
0x140011dea  test    rax, rax
0x140011ded  jz      loc_140011BEA
0x140011df3  mov     rcx, [rsi+8]; DeviceObject
0x140011df7  call    cs:__imp_IoAllocateWorkItem
0x140011dfe  nop     dword ptr [rax+rax+00h]
0x140011e03  mov     [rsi+7C8h], rax
0x140011e0a  test    rax, rax
0x140011e0d  jz      loc_140011BEA
0x140011e13  mov     rcx, [rsi+8]; DeviceObject
0x140011e17  mov     qword ptr [rsi+7D0h], 0
0x140011e22  mov     dword ptr [rsi+7D8h], 0
0x140011e2c  call    cs:__imp_IoAllocateWorkItem
0x140011e33  nop     dword ptr [rax+rax+00h]
0x140011e38  mov     [rsi+7E0h], rax
0x140011e3f  test    rax, rax
0x140011e42  jz      loc_140011BEA
0x140011e48  mov     edx, 4F506152h; PoolTag
0x140011e4d  mov     ecx, 200h; PoolType
0x140011e52  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140011e59  nop     dword ptr [rax+rax+00h]
0x140011e5e  mov     [rsi+748h], rax
0x140011e65  test    rax, rax
0x140011e68  jz      loc_140011BEA
0x140011e6e  mov     rcx, rax; RunRef
0x140011e71  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140011e78  nop     dword ptr [rax+rax+00h]
0x140011e7d  xor     eax, eax
0x140011e7f  jmp     loc_140011BF9
```
