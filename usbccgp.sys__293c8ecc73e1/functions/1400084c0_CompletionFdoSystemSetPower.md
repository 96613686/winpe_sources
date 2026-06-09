# CompletionFdoSystemSetPower

- ea: `0x1400084c0`
- end: `0x14000880a`
- name: `CompletionFdoSystemSetPower`
- size: `842`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1400054a0`
- `0x1400059e4`
- `0x140007020`
- `0x140007c38`
- `0x1400084c0`
- `0x1400092ec`
- `0x1400099a8`
- `0x14000b4bc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000863c`
- `ntoskrnl!IofCompleteRequest` at `0x14000863c`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140008627`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140008627`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140008663`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140008663`
- `ntoskrnl!KeReadStateEvent` at `0x14000871e`
- `ntoskrnl!KeReadStateEvent` at `0x14000871e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400085ec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400085ec`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000860f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000860f`

## pseudocode

```c
__int64 __fastcall CompletionFdoSystemSetPower(__int64 a1, IRP *a2, __int64 a3)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // r15
  IRP *v5; // rbp
  _IO_STATUS_BLOCK *p_IoStatus; // r12
  int Status; // eax
  unsigned int LowPart; // r15d
  int v9; // edx
  POWER_STATE v10; // ebx
  int v11; // eax
  int v12; // edx
  int v13; // r15d
  char v14; // r13
  _IO_STATUS_BLOCK *v15; // r15
  int v16; // eax
  int v17; // edx
  KIRQL v18; // r14
  LONG StateEvent; // eax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = a2;
  if ( a2->PendingReturned )
    CurrentStackLocation->Control |= 1u;
  p_IoStatus = &a2->IoStatus;
  Status = a2->IoStatus.Status;
  if ( Status < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qD(
        *(_QWORD *)(a3 + 1368),
        (_DWORD)a2,
        8,
        15,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *(_QWORD *)(a3 + 32),
        Status);
    }
    goto LABEL_24;
  }
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 1 )
  {
    v14 = 0;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = &a2->IoStatus;
    }
    else
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_qLL(
        *(_QWORD *)(a3 + 1368),
        (_DWORD)a2,
        3,
        18,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *(_QWORD *)(a3 + 32),
        1,
        1);
      v15 = &v5->IoStatus;
    }
    v16 = FdoSendSetPowerRequest((POWER_STATE)1, 0);
    if ( v16 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = 2;
      WPP_RECORDER_SF_qD(
        *(_QWORD *)(a3 + 1368),
        v17,
        8,
        19,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *(_QWORD *)(a3 + 32),
        v16);
    }
    v13 = v15->Status;
    v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 344));
    if ( (*(_DWORD *)(a3 + 1228) & 1) != 0 )
    {
      StateEvent = KeReadStateEvent((PRKEVENT)(a3 + 312));
      *(_DWORD *)(a3 + 1228) &= ~1u;
      if ( StateEvent )
        v14 = 1;
      else
        *(_DWORD *)(a3 + 1228) |= 4u;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 344), v18);
    if ( v14 )
      AllocateWorker(a3, IdleTimerEnableWorker, 0);
    goto LABEL_20;
  }
  if ( LowPart != 2 && LowPart != 3 && LowPart != 4 && LowPart - 5 > 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qL(
        *(_QWORD *)(a3 + 1368),
        (_DWORD)a2,
        8,
        20,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *(_QWORD *)(a3 + 32),
        LowPart);
    }
LABEL_24:
    v13 = p_IoStatus->Status;
LABEL_20:
    PoStartNextPowerIrp(v5);
    p_IoStatus->Status = v13;
    IofCompleteRequest(v5, 0);
    UsbcReleaseRemoveLock(a3, v5);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a3 + 200), v5, 0x20u);
    return 3221225494LL;
  }
  v10.SystemState = MapSystemStateToDeviceState(a3, LowPart);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 4;
    WPP_RECORDER_SF_qLL(
      *(_QWORD *)(a3 + 1368),
      v9,
      3,
      16,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      *(_QWORD *)(a3 + 32),
      LowPart,
      v10.SystemState);
  }
  v11 = FdoSendSetPowerRequest(v10, CallbackFdoDeviceSetDx);
  v13 = v11;
  if ( v11 != 259 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_qD(
        *(_QWORD *)(a3 + 1368),
        v12,
        8,
        17,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *(_QWORD *)(a3 + 32),
        v11);
    }
    goto LABEL_20;
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400084c0  push    rbx
0x1400084c2  push    rbp
0x1400084c3  push    rsi
0x1400084c4  push    rdi
0x1400084c5  push    r12
0x1400084c7  push    r13
0x1400084c9  push    r14
0x1400084cb  push    r15
0x1400084cd  sub     rsp, 48h
0x1400084d1  cmp     byte ptr [rdx+41h], 0
0x1400084d5  mov     rdi, r8
0x1400084d8  mov     r15, [rdx+0B8h]
0x1400084df  mov     rbp, rdx
0x1400084e2  mov     ebx, 1
0x1400084e7  jz      short loc_1400084ED
0x1400084e9  or      [r15+3], bl
0x1400084ed  lea     r12, [rdx+30h]
0x1400084f1  mov     eax, [r12]
0x1400084f5  test    eax, eax
0x1400084f7  js      loc_1400086A0
0x1400084fd  mov     r15d, [r15+18h]
0x140008501  mov     ecx, r15d
0x140008504  sub     ecx, ebx
0x140008506  jz      loc_1400085A7
0x14000850c  sub     ecx, ebx
0x14000850e  jz      short loc_140008524
0x140008510  sub     ecx, ebx
0x140008512  jz      short loc_140008524
0x140008514  sub     ecx, ebx
0x140008516  jz      short loc_140008524
0x140008518  sub     ecx, ebx
0x14000851a  jz      short loc_140008524
0x14000851c  cmp     ecx, ebx
0x14000851e  jnz     loc_140008686
0x140008524  mov     edx, r15d
0x140008527  mov     rcx, rdi
0x14000852a  call    MapSystemStateToDeviceState
0x14000852f  mov     ebx, eax
0x140008531  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140008538  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000853f  lea     r14, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140008546  jnz     loc_1400086E3
0x14000854c  mov     r9, rdi
0x14000854f  lea     rdx, CallbackFdoDeviceSetDx; CompletionFunction
0x140008556  mov     r8, rbp
0x140008559  mov     ecx, ebx; PowerState
0x14000855b  call    FdoSendSetPowerRequest
0x140008560  mov     r15d, eax
0x140008563  cmp     eax, 103h
0x140008568  jz      loc_14000866F
0x14000856e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140008575  jz      loc_140008624
0x14000857b  mov     rcx, [rdi+20h]
0x14000857f  mov     r9d, 11h
0x140008585  mov     [rsp+88h+var_58], eax
0x140008589  mov     dl, 2
0x14000858b  mov     [rsp+88h+var_60], rcx
0x140008590  mov     rcx, [rdi+558h]
0x140008597  lea     r8d, [r9-9]
0x14000859b  mov     [rsp+88h+var_68], r14
0x1400085a0  call    WPP_RECORDER_SF_qD
0x1400085a5  jmp     short loc_140008624
0x1400085a7  xor     r13b, r13b
0x1400085aa  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400085b1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400085b8  lea     r14, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x1400085bf  jnz     loc_140008741
0x1400085c5  mov     r15, r12
0x1400085c8  mov     r9, rdi
0x1400085cb  xor     r8d, r8d
0x1400085ce  xor     edx, edx; CompletionFunction
0x1400085d0  mov     ecx, ebx; PowerState
0x1400085d2  call    FdoSendSetPowerRequest
0x1400085d7  test    eax, eax
0x1400085d9  js      loc_1400087B7
0x1400085df  mov     r15d, [r15]
0x1400085e2  lea     rsi, [rdi+158h]
0x1400085e9  mov     rcx, rsi; SpinLock
0x1400085ec  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400085f3  nop     dword ptr [rax+rax+00h]
0x1400085f8  mov     ecx, [rdi+4CCh]
0x1400085fe  mov     r14b, al
0x140008601  test    bl, cl
0x140008603  jnz     loc_140008717
0x140008609  mov     dl, r14b; NewIrql
0x14000860c  mov     rcx, rsi; SpinLock
0x14000860f  call    cs:__imp_KeReleaseSpinLock
0x140008616  nop     dword ptr [rax+rax+00h]
0x14000861b  test    r13b, r13b
0x14000861e  jnz     loc_1400087F3
0x140008624  mov     rcx, rbp; Irp
0x140008627  call    cs:__imp_PoStartNextPowerIrp
0x14000862e  nop     dword ptr [rax+rax+00h]
0x140008633  xor     edx, edx; PriorityBoost
0x140008635  mov     [r12], r15d
0x140008639  mov     rcx, rbp; Irp
0x14000863c  call    cs:__imp_IofCompleteRequest
0x140008643  nop     dword ptr [rax+rax+00h]
0x140008648  mov     rdx, rbp
0x14000864b  mov     rcx, rdi
0x14000864e  call    UsbcReleaseRemoveLock
0x140008653  lea     rcx, [rdi+0C8h]; RemoveLock
0x14000865a  mov     r8d, 20h ; ' '; RemlockSize
0x140008660  mov     rdx, rbp; Tag
0x140008663  call    cs:__imp_IoReleaseRemoveLockEx
0x14000866a  nop     dword ptr [rax+rax+00h]
0x14000866f  mov     eax, 0C0000016h
0x140008674  add     rsp, 48h
0x140008678  pop     r15
0x14000867a  pop     r14
0x14000867c  pop     r13
0x14000867e  pop     r12
0x140008680  pop     rdi
0x140008681  pop     rsi
0x140008682  pop     rbp
0x140008683  pop     rbx
0x140008684  retn
0x140008686  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000868d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140008694  jnz     loc_140008780
0x14000869a  mov     r15d, [r12]
0x14000869e  jmp     short loc_140008624
0x1400086a0  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400086a7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400086ae  jz      short loc_14000869A
0x1400086b0  mov     rcx, [rdi+558h]
0x1400086b7  lea     r14, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x1400086be  mov     [rsp+88h+var_58], eax
0x1400086c2  mov     r9d, 0Fh
0x1400086c8  mov     rax, [r8+20h]
0x1400086cc  mov     dl, 2
0x1400086ce  mov     [rsp+88h+var_60], rax
0x1400086d3  mov     [rsp+88h+var_68], r14
0x1400086d8  lea     r8d, [r9-7]
0x1400086dc  call    WPP_RECORDER_SF_qD
0x1400086e1  jmp     short loc_14000869A
0x1400086e3  mov     rax, [rdi+20h]
0x1400086e7  mov     r9d, 10h
0x1400086ed  mov     rcx, [rdi+558h]
0x1400086f4  mov     dl, 4
0x1400086f6  mov     [rsp+88h+var_50], ebx
0x1400086fa  mov     [rsp+88h+var_58], r15d
0x1400086ff  mov     [rsp+88h+var_60], rax
0x140008704  lea     r8d, [r9-0Dh]
0x140008708  mov     [rsp+88h+var_68], r14
0x14000870d  call    WPP_RECORDER_SF_qLL
0x140008712  jmp     loc_14000854C
0x140008717  lea     rcx, [rdi+138h]; Event
0x14000871e  call    cs:__imp_KeReadStateEvent
0x140008725  nop     dword ptr [rax+rax+00h]
0x14000872a  and     dword ptr [rdi+4CCh], 0FFFFFFFEh
0x140008731  test    eax, eax
0x140008733  jnz     short loc_140008778
0x140008735  or      dword ptr [rdi+4CCh], 4
0x14000873c  jmp     loc_140008609
0x140008741  mov     rax, [r8+20h]
0x140008745  mov     r9d, 12h
0x14000874b  mov     rcx, [rdi+558h]
0x140008752  mov     dl, 4
0x140008754  mov     [rsp+88h+var_50], ebx
0x140008758  mov     [rsp+88h+var_58], ebx
0x14000875c  mov     [rsp+88h+var_60], rax
0x140008761  lea     r8d, [r9-0Fh]
0x140008765  mov     [rsp+88h+var_68], r14
0x14000876a  call    WPP_RECORDER_SF_qLL
0x14000876f  lea     r15, [rbp+30h]
0x140008773  jmp     loc_1400085C8
0x140008778  mov     r13b, bl
0x14000877b  jmp     loc_140008609
0x140008780  mov     rax, [r8+20h]
0x140008784  lea     r14, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000878b  mov     rcx, [rdi+558h]
0x140008792  mov     r9d, 14h
0x140008798  mov     [rsp+88h+var_58], r15d
0x14000879d  mov     dl, 2
0x14000879f  mov     [rsp+88h+var_60], rax
0x1400087a4  mov     [rsp+88h+var_68], r14
0x1400087a9  lea     r8d, [r9-0Ch]
0x1400087ad  call    WPP_RECORDER_SF_qL
0x1400087b2  jmp     loc_14000869A
0x1400087b7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400087be  jz      loc_1400085DF
0x1400087c4  mov     rcx, [rdi+558h]
0x1400087cb  mov     r9d, 13h
0x1400087d1  mov     [rsp+88h+var_58], eax
0x1400087d5  mov     dl, 2
0x1400087d7  mov     rax, [rdi+20h]
0x1400087db  mov     [rsp+88h+var_60], rax
0x1400087e0  lea     r8d, [r9-0Bh]
0x1400087e4  mov     [rsp+88h+var_68], r14
0x1400087e9  call    WPP_RECORDER_SF_qD
0x1400087ee  jmp     loc_1400085DF
0x1400087f3  xor     r8d, r8d
0x1400087f6  lea     rdx, IdleTimerEnableWorker
0x1400087fd  mov     rcx, rdi
0x140008800  call    AllocateWorker
0x140008805  jmp     loc_140008624
```
