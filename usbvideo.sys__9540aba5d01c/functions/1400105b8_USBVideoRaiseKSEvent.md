# USBVideoRaiseKSEvent

- ea: `0x1400105b8`
- end: `0x140010d7b`
- name: `USBVideoRaiseKSEvent`
- size: `1987`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x140014b20`

## callees

- `0x14000d194`
- `0x1400105b8`
- `0x140019d34`
- `0x14001ab4c`
- `0x14001b118`
- `0x14001b15c`
- `0x14001b2f4`
- `0x1400204cc`
- `0x140021b48`
- `0x14005bdd4`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140010968`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400109ec`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140010968`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400109ec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400107d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010a4f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400107d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010a4f`
- `ntoskrnl!IoQueueWorkItem` at `0x140010932`
- `ntoskrnl!IoQueueWorkItem` at `0x140010932`
- `ntoskrnl!IoFreeWorkItem` at `0x14001094c`
- `ntoskrnl!IoFreeWorkItem` at `0x14001094c`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400108ab`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400108ab`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140010890`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140010890`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400108d3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400108d3`
- `ntoskrnl!KeSetEvent` at `0x14001074a`
- `ntoskrnl!KeSetEvent` at `0x14001074a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001081d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010a87`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001081d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010a87`
- `ntoskrnl!KeClearEvent` at `0x14001075d`
- `ntoskrnl!KeClearEvent` at `0x14001075d`
- `ks!KsGenerateEvent` at `0x14001080b`
- `ks!KsGenerateEvent` at `0x140010a6a`
- `ks!KsGenerateEvent` at `0x14001080b`
- `ks!KsGenerateEvent` at `0x140010a6a`

## pseudocode

```c
__int64 __fastcall USBVideoRaiseKSEvent(unsigned __int8 *a1, __int64 *a2)
{
  __int64 v2; // r13
  unsigned int v4; // r12d
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rax
  KIRQL v8; // bp
  struct _KSEVENT_ENTRY *v9; // rcx
  __int64 v10; // rax
  struct _IO_WORKITEM *WorkItem; // rbp
  _QWORD *PoolWithTag; // rax
  void *v13; // r14
  unsigned __int8 *Unit; // rax
  unsigned __int8 v15; // al
  KIRQL v16; // al
  struct _KSEVENT_ENTRY *v17; // rcx
  KIRQL v18; // si
  unsigned __int8 v19; // al
  __int64 PinNumberForInterface; // r14
  __int64 VideoStreamingInputHeader; // rax
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rbp
  char v26; // al
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx

  v2 = *a2;
  v4 = 0;
  v5 = *(_QWORD *)(*a2 + 16);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v5);
  if ( *a1 == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v5);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, *a1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 86, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, a1[1]);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, a1[2]);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, a1[3]);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    89,
                    WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
                    a1[4]);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  WPP_SF_q(
                    WPP_GLOBAL_Control->AttachedDevice,
                    90,
                    WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
                    a1 + 5);
              }
            }
          }
        }
      }
    }
    KeSetEvent(*(PRKEVENT *)(v5 + 656), 0, 0);
    KeClearEvent(*(PRKEVENT *)(v5 + 656));
    v7 = *(_QWORD *)(v5 + 880);
    if ( v7 && a1[1] == *(_BYTE *)(*(_QWORD *)(v7 + 32) + 3LL) && !a1[2] )
    {
      if ( a1[4] )
      {
LABEL_38:
        v10 = *(_QWORD *)(v5 + 888);
        if ( v10 )
        {
          if ( a1[1] == *(_BYTE *)(*(_QWORD *)(v10 + 32) + 3LL) && !a1[2] && !a1[4] && a1[3] == 17 )
          {
            v4 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 768), PrivacyNotificationWorkItemHandler, File, 1u, 0x20u);
            if ( (v4 & 0x80000000) == 0 )
            {
              WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(v2 + 24));
              if ( WorkItem )
              {
                PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, 0x10u, 0x56425355u);
                v13 = PoolWithTag;
                if ( PoolWithTag )
                {
                  PoolWithTag[1] = v5;
                  *PoolWithTag = WorkItem;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      92,
                      WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
                      v5);
                  }
                  IoQueueWorkItem(WorkItem, PrivacyNotificationWorkItemHandler, DelayedWorkQueue, v13);
                }
                else
                {
                  v4 = -1073741670;
                  IoFreeWorkItem(WorkItem);
                  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 768), PrivacyNotificationWorkItemHandler, 0x20u);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    WPP_SF_qD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      93,
                      WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
                      v5,
                      -1073741670);
                  }
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v5);
                IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 768), PrivacyNotificationWorkItemHandler, 0x20u);
              }
            }
          }
        }
        if ( *(_QWORD *)(v5 + 384) )
        {
          Unit = GetUnit(*(PUSB_CONFIGURATION_DESCRIPTOR *)(v5 + 32), a1[1]);
          if ( Unit )
          {
            if ( Unit[2] == 2 && *((_WORD *)Unit + 2) == 514 )
            {
              v15 = a1[3];
              if ( v15 == 2 || v15 == 4 )
              {
                v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 392));
                v17 = *(struct _KSEVENT_ENTRY **)(v5 + 384);
                v18 = v16;
                if ( v17 )
                {
                  KsGenerateEvent(v17);
                  *(_QWORD *)(v5 + 384) = 0;
                }
                KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 392), v18);
              }
            }
          }
        }
        return v4;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v5);
      LOBYTE(v6) = a1[3];
      MSXURaiseEvent(v5, v6);
    }
    if ( !a1[4] )
    {
      v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 392));
      v9 = *(struct _KSEVENT_ENTRY **)(v5 + 376);
      *(_QWORD *)(v5 + 401) = *(_QWORD *)a1;
      *(_DWORD *)(v5 + 409) = *((_DWORD *)a1 + 2);
      *(_BYTE *)(v5 + 413) = a1[12];
      if ( v9 )
        KsGenerateEvent(v9);
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 392), v8);
    }
    goto LABEL_38;
  }
  if ( *a1 != 2 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      return v4;
    v28 = 107;
LABEL_117:
    WPP_SF_q(v27->AttachedDevice, v28, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v5);
    return v4;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v5);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, *a1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, a1[1]);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, a1[2]);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, a1 + 3);
        }
      }
    }
  }
  if ( a1[2] )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        106,
        WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
        v5,
        a1[1],
        a1[3]);
    return v4;
  }
  v19 = a1[3];
  if ( v19 != 1 )
  {
    if ( !v19 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 105, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v5, a1[1]);
    return v4;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v5, a1[1]);
  LOBYTE(a2) = a1[1];
  PinNumberForInterface = (unsigned int)GetPinNumberForInterface(*(_QWORD *)(v5 + 32), a2);
  VideoStreamingInputHeader = GetVideoStreamingInputHeader(PinNumberForInterface, *(_QWORD *)(v5 + 32));
  v24 = VideoStreamingInputHeader;
  if ( VideoStreamingInputHeader )
  {
    v26 = *(_BYTE *)(VideoStreamingInputHeader + 9);
    if ( v26 == 3 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v5);
      LOBYTE(v22) = 2;
    }
    else
    {
      LOBYTE(v22) = 0;
      if ( v26 == 2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v5);
        LOBYTE(v22) = 1;
      }
    }
    if ( (unsigned __int8)(*(_BYTE *)(v24 + 9) - 2) > 1u )
      return v4;
    LOBYTE(v23) = a1[1];
    if ( (int)QueueStillImageWorkItem(v2, v5, v22, v23, *(_BYTE *)(v24 + 9), PinNumberForInterface) >= 0 )
      return v4;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      return v4;
    v28 = 104;
    goto LABEL_117;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v5);
  return 0;
}

```

## disassembly

```asm
0x1400105b8  push    rbx
0x1400105ba  push    rbp
0x1400105bb  push    rsi
0x1400105bc  push    rdi
0x1400105bd  push    r12
0x1400105bf  push    r13
0x1400105c1  push    r14
0x1400105c3  push    r15
0x1400105c5  sub     rsp, 38h
0x1400105c9  mov     r13, [rdx]
0x1400105cc  xor     esi, esi
0x1400105ce  mov     rbx, rcx
0x1400105d1  mov     r12d, esi
0x1400105d4  mov     rdi, [r13+10h]
0x1400105d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400105df  lea     r15, WPP_GLOBAL_Control
0x1400105e6  lea     r14, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x1400105ed  mov     bpl, 5
0x1400105f0  cmp     rcx, r15
0x1400105f3  jz      short loc_14001060D
0x1400105f5  cmp     [rcx+29h], bpl
0x1400105f9  jb      short loc_14001060D
0x1400105fb  mov     rcx, [rcx+18h]
0x1400105ff  lea     edx, [rsi+53h]
0x140010602  mov     r9, rdi
0x140010605  mov     r8, r14
0x140010608  call    WPP_SF_q
0x14001060d  mov     al, [rbx]
0x14001060f  cmp     al, 1
0x140010611  jnz     loc_140010A98
0x140010617  mov     rcx, cs:WPP_GLOBAL_Control
0x14001061e  mov     bpl, 4
0x140010621  cmp     rcx, r15
0x140010624  jz      loc_14001073E
0x14001062a  cmp     [rcx+29h], bpl
0x14001062e  jb      short loc_140010644
0x140010630  mov     rcx, [rcx+18h]
0x140010634  mov     edx, 54h ; 'T'
0x140010639  mov     r9, rdi
0x14001063c  mov     r8, r14
0x14001063f  call    WPP_SF_q
0x140010644  mov     rcx, cs:WPP_GLOBAL_Control
0x14001064b  cmp     rcx, r15
0x14001064e  jz      loc_14001073E
0x140010654  cmp     [rcx+29h], bpl
0x140010658  jb      short loc_14001066F
0x14001065a  movzx   r9d, byte ptr [rbx]
0x14001065e  mov     edx, 55h ; 'U'
0x140010663  mov     rcx, [rcx+18h]
0x140010667  mov     r8, r14
0x14001066a  call    WPP_SF_d
0x14001066f  mov     rcx, cs:WPP_GLOBAL_Control
0x140010676  cmp     rcx, r15
0x140010679  jz      loc_14001073E
0x14001067f  cmp     [rcx+29h], bpl
0x140010683  jb      short loc_14001069B
0x140010685  movzx   r9d, byte ptr [rbx+1]
0x14001068a  mov     edx, 56h ; 'V'
0x14001068f  mov     rcx, [rcx+18h]
0x140010693  mov     r8, r14
0x140010696  call    WPP_SF_d
0x14001069b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400106a2  cmp     rcx, r15
0x1400106a5  jz      loc_14001073E
0x1400106ab  cmp     [rcx+29h], bpl
0x1400106af  jb      short loc_1400106C7
0x1400106b1  movzx   r9d, byte ptr [rbx+2]
0x1400106b6  mov     edx, 57h ; 'W'
0x1400106bb  mov     rcx, [rcx+18h]
0x1400106bf  mov     r8, r14
0x1400106c2  call    WPP_SF_d
0x1400106c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400106ce  cmp     rcx, r15
0x1400106d1  jz      short loc_14001073E
0x1400106d3  cmp     [rcx+29h], bpl
0x1400106d7  jb      short loc_1400106EF
0x1400106d9  movzx   r9d, byte ptr [rbx+3]
0x1400106de  mov     edx, 58h ; 'X'
0x1400106e3  mov     rcx, [rcx+18h]
0x1400106e7  mov     r8, r14
0x1400106ea  call    WPP_SF_d
0x1400106ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400106f6  cmp     rcx, r15
0x1400106f9  jz      short loc_14001073E
0x1400106fb  cmp     [rcx+29h], bpl
0x1400106ff  jb      short loc_140010717
0x140010701  movzx   r9d, byte ptr [rbx+4]
0x140010706  mov     edx, 59h ; 'Y'
0x14001070b  mov     rcx, [rcx+18h]
0x14001070f  mov     r8, r14
0x140010712  call    WPP_SF_d
0x140010717  mov     rcx, cs:WPP_GLOBAL_Control
0x14001071e  cmp     rcx, r15
0x140010721  jz      short loc_14001073E
0x140010723  cmp     [rcx+29h], bpl
0x140010727  jb      short loc_14001073E
0x140010729  mov     rcx, [rcx+18h]
0x14001072d  lea     r9, [rbx+5]
0x140010731  mov     edx, 5Ah ; 'Z'
0x140010736  mov     r8, r14
0x140010739  call    WPP_SF_q
0x14001073e  mov     rcx, [rdi+290h]; Event
0x140010745  xor     r8d, r8d; Wait
0x140010748  xor     edx, edx; Increment
0x14001074a  call    cs:__imp_KeSetEvent
0x140010751  nop     dword ptr [rax+rax+00h]
0x140010756  mov     rcx, [rdi+290h]; Event
0x14001075d  call    cs:__imp_KeClearEvent
0x140010764  nop     dword ptr [rax+rax+00h]
0x140010769  mov     rax, [rdi+370h]
0x140010770  test    rax, rax
0x140010773  jz      short loc_1400107C2
0x140010775  mov     rax, [rax+20h]
0x140010779  mov     cl, [rax+3]
0x14001077c  cmp     [rbx+1], cl
0x14001077f  jnz     short loc_1400107C2
0x140010781  cmp     [rbx+2], sil
0x140010785  jnz     short loc_1400107C2
0x140010787  cmp     [rbx+4], sil
0x14001078b  jnz     loc_140010829
0x140010791  mov     rcx, cs:WPP_GLOBAL_Control
0x140010798  cmp     rcx, r15
0x14001079b  jz      short loc_1400107B7
0x14001079d  cmp     [rcx+29h], bpl
0x1400107a1  jb      short loc_1400107B7
0x1400107a3  mov     rcx, [rcx+18h]
0x1400107a7  mov     edx, 5Bh ; '['
0x1400107ac  mov     r9, rdi
0x1400107af  mov     r8, r14
0x1400107b2  call    WPP_SF_q
0x1400107b7  mov     dl, [rbx+3]
0x1400107ba  mov     rcx, rdi
0x1400107bd  call    MSXURaiseEvent
0x1400107c2  cmp     [rbx+4], sil
0x1400107c6  jnz     short loc_140010829
0x1400107c8  lea     rsi, [rdi+188h]
0x1400107cf  mov     rcx, rsi; SpinLock
0x1400107d2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400107d9  nop     dword ptr [rax+rax+00h]
0x1400107de  movsd   xmm0, qword ptr [rbx]
0x1400107e2  mov     bpl, al
0x1400107e5  mov     rcx, [rdi+178h]; EventEntry
0x1400107ec  movsd   qword ptr [rdi+191h], xmm0
0x1400107f4  mov     eax, [rbx+8]
0x1400107f7  mov     [rdi+199h], eax
0x1400107fd  mov     al, [rbx+0Ch]
0x140010800  mov     [rdi+19Dh], al
0x140010806  test    rcx, rcx
0x140010809  jz      short loc_140010817
0x14001080b  call    cs:__imp_KsGenerateEvent
0x140010812  nop     dword ptr [rax+rax+00h]
0x140010817  mov     dl, bpl; NewIrql
0x14001081a  mov     rcx, rsi; SpinLock
0x14001081d  call    cs:__imp_KeReleaseSpinLock
0x140010824  nop     dword ptr [rax+rax+00h]
0x140010829  mov     rax, [rdi+378h]
0x140010830  mov     sil, 2
0x140010833  test    rax, rax
0x140010836  jz      loc_1400109F8
0x14001083c  mov     rax, [rax+20h]
0x140010840  mov     cl, [rax+3]
0x140010843  cmp     [rbx+1], cl
0x140010846  jnz     loc_1400109F8
0x14001084c  cmp     [rbx+2], r12b
0x140010850  jnz     loc_1400109F8
0x140010856  cmp     [rbx+4], r12b
0x14001085a  jnz     loc_1400109F8
0x140010860  cmp     byte ptr [rbx+3], 11h
0x140010864  jnz     loc_1400109F8
0x14001086a  lea     r15, [rdi+300h]
0x140010871  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x140010879  mov     rcx, r15; RemoveLock
0x14001087c  lea     r8, File; File
0x140010883  mov     r9d, 1; Line
0x140010889  lea     rdx, PrivacyNotificationWorkItemHandler; Tag
0x140010890  call    cs:__imp_IoAcquireRemoveLockEx
0x140010897  nop     dword ptr [rax+rax+00h]
0x14001089c  mov     r12d, eax
0x14001089f  test    eax, eax
0x1400108a1  js      loc_1400109F8
0x1400108a7  mov     rcx, [r13+18h]; DeviceObject
0x1400108ab  call    cs:__imp_IoAllocateWorkItem
0x1400108b2  nop     dword ptr [rax+rax+00h]
0x1400108b7  mov     rbp, rax
0x1400108ba  test    rax, rax
0x1400108bd  jz      loc_1400109AF
0x1400108c3  mov     edx, 10h; NumberOfBytes
0x1400108c8  mov     ecx, 600h; PoolType
0x1400108cd  mov     r8d, 56425355h; Tag
0x1400108d3  call    cs:__imp_ExAllocatePoolWithTag
0x1400108da  nop     dword ptr [rax+rax+00h]
0x1400108df  mov     r14, rax
0x1400108e2  test    rax, rax
0x1400108e5  jz      short loc_140010943
0x1400108e7  mov     [rax+8], rdi
0x1400108eb  mov     [rax], rbp
0x1400108ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400108f5  lea     rax, WPP_GLOBAL_Control
0x1400108fc  cmp     rcx, rax
0x1400108ff  jz      short loc_14001091F
0x140010901  cmp     byte ptr [rcx+29h], 4
0x140010905  jb      short loc_14001091F
0x140010907  mov     rcx, [rcx+18h]
0x14001090b  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140010912  mov     edx, 5Ch ; '\'
0x140010917  mov     r9, rdi
0x14001091a  call    WPP_SF_q
0x14001091f  mov     r9, r14; Context
0x140010922  lea     rdx, PrivacyNotificationWorkItemHandler; WorkerRoutine
0x140010929  mov     r8d, 1; QueueType
0x14001092f  mov     rcx, rbp; IoWorkItem
0x140010932  call    cs:__imp_IoQueueWorkItem
0x140010939  nop     dword ptr [rax+rax+00h]
0x14001093e  jmp     loc_1400109F8
0x140010943  mov     rcx, rbp; IoWorkItem
0x140010946  mov     r12d, 0C000009Ah
0x14001094c  call    cs:__imp_IoFreeWorkItem
0x140010953  nop     dword ptr [rax+rax+00h]
0x140010958  mov     r8d, 20h ; ' '; RemlockSize
0x14001095e  lea     rdx, PrivacyNotificationWorkItemHandler; Tag
0x140010965  mov     rcx, r15; RemoveLock
0x140010968  call    cs:__imp_IoReleaseRemoveLockEx
0x14001096f  nop     dword ptr [rax+rax+00h]
0x140010974  mov     rcx, cs:WPP_GLOBAL_Control
0x14001097b  lea     rax, WPP_GLOBAL_Control
0x140010982  cmp     rcx, rax
0x140010985  jz      short loc_1400109F8
0x140010987  cmp     [rcx+29h], sil
0x14001098b  jb      short loc_1400109F8
0x14001098d  mov     rcx, [rcx+18h]
0x140010991  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140010998  mov     edx, 5Dh ; ']'
0x14001099d  mov     [rsp+78h+RemlockSize], 0C000009Ah
0x1400109a5  mov     r9, rdi
0x1400109a8  call    WPP_SF_qD
0x1400109ad  jmp     short loc_1400109F8
0x1400109af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400109b6  lea     rax, WPP_GLOBAL_Control
0x1400109bd  cmp     rcx, rax
0x1400109c0  jz      short loc_1400109DC
0x1400109c2  cmp     [rcx+29h], sil
0x1400109c6  jb      short loc_1400109DC
0x1400109c8  mov     rcx, [rcx+18h]
0x1400109cc  mov     edx, 5Eh ; '^'
0x1400109d1  mov     r9, rdi
0x1400109d4  mov     r8, r14
0x1400109d7  call    WPP_SF_q
0x1400109dc  mov     r8d, 20h ; ' '; RemlockSize
0x1400109e2  lea     rdx, PrivacyNotificationWorkItemHandler; Tag
0x1400109e9  mov     rcx, r15; RemoveLock
0x1400109ec  call    cs:__imp_IoReleaseRemoveLockEx
0x1400109f3  nop     dword ptr [rax+rax+00h]
0x1400109f8  cmp     qword ptr [rdi+180h], 0
0x140010a00  jz      loc_140010D66
0x140010a06  movzx   edx, byte ptr [rbx+1]
0x140010a0a  mov     rcx, [rdi+20h]; ConfigurationDescriptor
0x140010a0e  call    GetUnit
0x140010a13  test    rax, rax
0x140010a16  jz      loc_140010D66
0x140010a1c  cmp     [rax+2], sil
0x140010a20  jnz     loc_140010D66
0x140010a26  mov     ecx, 202h
0x140010a2b  cmp     [rax+4], cx
0x140010a2f  jnz     loc_140010D66
0x140010a35  mov     al, [rbx+3]
0x140010a38  cmp     al, sil
0x140010a3b  jz      short loc_140010A45
0x140010a3d  cmp     al, 4
0x140010a3f  jnz     loc_140010D66
0x140010a45  lea     rbx, [rdi+188h]
0x140010a4c  mov     rcx, rbx; SpinLock
0x140010a4f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010a56  nop     dword ptr [rax+rax+00h]
0x140010a5b  mov     rcx, [rdi+180h]; EventEntry
0x140010a62  mov     sil, al
0x140010a65  test    rcx, rcx
0x140010a68  jz      short loc_140010A81
0x140010a6a  call    cs:__imp_KsGenerateEvent
0x140010a71  nop     dword ptr [rax+rax+00h]
0x140010a76  mov     qword ptr [rdi+180h], 0
0x140010a81  mov     dl, sil; NewIrql
0x140010a84  mov     rcx, rbx; SpinLock
0x140010a87  call    cs:__imp_KeReleaseSpinLock
0x140010a8e  nop     dword ptr [rax+rax+00h]
0x140010a93  jmp     loc_140010D66
0x140010a98  mov     sil, 2
0x140010a9b  cmp     al, sil
0x140010a9e  jnz     loc_140010D40
0x140010aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x140010aab  cmp     rcx, r15
0x140010aae  jz      loc_140010B70
0x140010ab4  cmp     [rcx+29h], bpl
0x140010ab8  jb      short loc_140010ACE
0x140010aba  mov     rcx, [rcx+18h]
0x140010abe  mov     edx, 5Fh ; '_'
0x140010ac3  mov     r9, rdi
0x140010ac6  mov     r8, r14
0x140010ac9  call    WPP_SF_q
0x140010ace  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ad5  cmp     rcx, r15
  ... truncated ...
```
