# RaidUnitProcessSetDevicePowerIrpComplete

- ea: `0x14000528c`
- end: `0x14000597b`
- name: `RaidUnitProcessSetDevicePowerIrpComplete`
- size: `1775`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140004b4c`

## callees

- `0x14000528c`
- `0x140005c50`
- `0x1400121e4`
- `0x140014200`
- `0x140014420`
- `0x1400172d0`
- `0x14002cb18`
- `0x14003c4cc`
- `0x140063c74`
- `0x14006d1c0`
- `0x14006d298`
- `0x14006f610`
- `0x14006f780`
- `0x1400848c4`
- `0x1400a3114`
- `0x1400a4128`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1400053ae`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400055b1`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400053ae`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400055b1`
- `ntoskrnl!IofCompleteRequest` at `0x1400053e8`
- `ntoskrnl!IofCompleteRequest` at `0x1400053e8`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140005465`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400054a2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400054fe`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140005465`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400054a2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400054fe`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400052e2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400052e2`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140005893`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140005893`
- `ntoskrnl!PoSetPowerState` at `0x140005302`
- `ntoskrnl!PoSetPowerState` at `0x140005302`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000531b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140005529`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000531b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140005529`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000585d`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000585d`

## pseudocode

```c
__int64 __fastcall RaidUnitProcessSetDevicePowerIrpComplete(PVOID Context, PIRP Irp)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  char v5; // r13
  POWER_STATE v6; // ebx
  struct _DEVICE_OBJECT *v7; // rcx
  char v8; // r14
  __int64 v9; // r8
  __int64 v10; // r9
  bool v11; // zf
  unsigned __int64 v12; // rcx
  _IO_STACK_LOCATION *v13; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // ebx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // edx
  int v24; // ecx
  __int64 *v25; // rdx
  int *Information; // rax
  int v27; // ecx
  char SecurityQos; // cl
  _ACCESS_STATE *AccessState; // r9
  unsigned __int8 v30; // r10
  char v31; // di
  char v32; // bl
  _IO_SECURITY_CONTEXT *SecurityContext; // rdx
  char Flags; // r11
  unsigned __int8 *p_SecurityEvaluated; // rax
  char LowPart_high; // r8
  char *v37; // r8
  unsigned int v38; // eax
  __int64 v39; // r8
  int v40; // ecx
  unsigned int v41; // r15d
  char *v42; // r11
  unsigned int v43; // r12d
  unsigned __int64 DesiredAccess; // rbx
  PIO_WORKITEM WorkItem; // rax
  struct _IO_WORKITEM *v46; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-9h] BYREF
  __int128 v48; // [rsp+78h] [rbp+Fh] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v5 = 0;
  Irp->IoStatus.Status = 0;
  v6.SystemState = (_SYSTEM_POWER_STATE)CurrentStackLocation->Parameters.Power.State;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)Context + 6, &LockHandle);
  v7 = (struct _DEVICE_OBJECT *)*((_QWORD *)Context + 1);
  v8 = 1;
  *((POWER_STATE *)Context + 137) = v6;
  PoSetPowerState(v7, DevicePowerState, v6);
  if ( v6.SystemState == PowerSystemWorking && *((char *)Context + 504) < 0 )
  {
    RaidResumeUnitQueue(Context);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    RaidUnitRestartQueue(Context, 0);
  }
  else
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  if ( *((_DWORD *)Context + 137) == 1 )
  {
    if ( (unsigned __int8)RaidUnitCheckAndAcquirePoFx(Context) )
    {
      if ( (*(_DWORD *)(*((_QWORD *)Context + 234) + 32LL) & 0x100) != 0 )
      {
        ++*((_DWORD *)Context + 838);
        if ( !_interlockedbittestandset((volatile signed __int32 *)Context + 128, 1u) )
        {
          WorkItem = IoAllocateWorkItem(*((PDEVICE_OBJECT *)Context + 1));
          v46 = WorkItem;
          if ( WorkItem )
          {
            RaUnitAcquireRemoveLock(Context, WorkItem, 0);
            IoQueueWorkItemEx(v46, RaidUnitSavePowerCycleCountWorker, DelayedWorkQueue, Context);
          }
        }
        *(_DWORD *)(*((_QWORD *)Context + 234) + 32LL) &= ~0x200u;
      }
      if ( !(unsigned __int8)RaidUnitCheckAndAcquirePoFx(Context)
        || (v18 = *(_DWORD *)(*((_QWORD *)Context + 234) + 32LL) >> 1,
            ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 233)),
            (v18 & 1) != 0) )
      {
        if ( *((_BYTE *)Context + 759) )
        {
          *((_BYTE *)Context + 759) = 0;
          RaUnitUnlockForwardIo(Context, 2);
          RaidUnitRestartQueue(Context, 0);
        }
      }
      StorPortUnitPoFxD0Completion(v16, v15, v17, Context);
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)Context + 3) + 6092LL));
      v21 = *((_QWORD *)Context + 3);
      if ( (*(_BYTE *)(v21 + 110) & 0x40) != 0 )
      {
        LOBYTE(v20) = 1;
        RaidAdapterPoFxSetDeviceIdleTimeout(v21, 0xFFFFFFFFLL, v19, v20);
      }
      ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 233));
    }
    else if ( *((_BYTE *)Context + 759) )
    {
      *((_BYTE *)Context + 759) = 0;
      RaUnitUnlockForwardIo(Context, 2);
      RaidUnitRestartQueue(Context, 0);
    }
    if ( *((_DWORD *)Context + 260) )
      RaidUpdateCrashDumpPowerReady(*((_QWORD *)Context + 3));
  }
  else
  {
    if ( !*((_BYTE *)Context + 759) )
    {
      RaidPowerLockDeviceQueue();
      RaUnitLockForwardIo(Context, 2);
    }
    if ( *((_DWORD *)Context + 260) )
      RaidUpdateCrashDumpPowerReady(*((_QWORD *)Context + 3));
    if ( (unsigned __int8)RaidUnitCheckAndAcquirePoFx(Context) )
    {
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)Context + 3) + 6092LL), 1u);
      v22 = *((_QWORD *)Context + 3);
      if ( (*(_BYTE *)(v22 + 110) & 0x40) != 0 && *(_DWORD *)(v22 + 6092) == *(_DWORD *)(v22 + 168) )
      {
        LOBYTE(v10) = 1;
        RaidAdapterPoFxSetDeviceIdleTimeout(v22, 0, v9, v10);
      }
      ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 233));
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_24f186e44650306b933e2c903810ea21_Traceguids, Context, Irp, 0);
  }
  if ( StorEtwLoggingEnabled )
  {
    v48 = 0;
    IoGetActivityIdIrp(Irp, &v48);
    if ( (byte_140177432 & 0x10) != 0 )
      McTemplateK0quuupd_EtwWriteTransfer(
        v24,
        v23,
        (unsigned int)&v48,
        *(_DWORD *)(*((_QWORD *)Context + 3) + 56LL),
        *((_BYTE *)Context + 104),
        *((_BYTE *)Context + 105),
        *((_BYTE *)Context + 106),
        (char)Irp);
  }
  v11 = StorEtwLoggingEnabled == 0;
  *((_BYTE *)&Irp->Tail.CompletionKey + 21) = -84;
  Irp->IoStatus.Status = 0;
  if ( v11 )
    goto LABEL_15;
  v48 = 0;
  IoGetActivityIdIrp(Irp, &v48);
  v13 = Irp->Tail.Overlay.CurrentStackLocation;
  if ( v13->MajorFunction == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_15;
    v25 = EventNonReadWriteRequestComplete;
    goto LABEL_39;
  }
  if ( v13->MajorFunction != 15 )
  {
    if ( v13->MajorFunction != 27 )
      goto LABEL_15;
    if ( v13->MinorFunction == 7 && !v13->Parameters.Read.Length )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        Information = (int *)Irp->IoStatus.Information;
        if ( Information )
          v27 = *Information;
        else
          v27 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v27, (_DWORD)v13, (unsigned int)&v48, (_DWORD)Irp, v27, Irp->IoStatus.Status);
      }
      goto LABEL_15;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_15;
    v25 = EventPnpRequestComplete;
LABEL_39:
    McTemplateK0pd_EtwWriteTransfer(v12, v25, &v48, Irp, Irp->IoStatus.Status);
    goto LABEL_15;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_15;
  SecurityContext = v13->Parameters.Create.SecurityContext;
  if ( BYTE2(SecurityContext->SecurityQos) != 40 )
  {
    SecurityQos = (char)SecurityContext[3].SecurityQos;
    AccessState = SecurityContext[1].AccessState;
    v30 = BYTE3(SecurityContext->AccessState);
    v31 = BYTE4(SecurityContext->SecurityQos);
    if ( !BYTE2(SecurityContext->SecurityQos) )
      goto LABEL_49;
    goto LABEL_15;
  }
  if ( SecurityContext->FullCreateOptions )
    goto LABEL_15;
  v43 = (unsigned int)SecurityContext[2].AccessState;
  if ( !v43 )
    goto LABEL_15;
  v30 = 0;
  v42 = 0;
  v31 = 0;
  AccessState = 0;
  v41 = 0;
  while ( 1 )
  {
    v12 = *((unsigned int *)&SecurityContext[5].SecurityQos + v41);
    if ( (unsigned int)v12 >= 0x80 )
    {
      DesiredAccess = SecurityContext->DesiredAccess;
      if ( (unsigned int)v12 < (unsigned int)DesiredAccess )
        break;
    }
LABEL_66:
    if ( ++v41 >= v43 )
      goto LABEL_67;
  }
  v39 = *((unsigned int *)&SecurityContext[5].SecurityQos + v41);
  v40 = *(_DWORD *)((char *)&SecurityContext->SecurityQos + v12) - 64;
  if ( v40 )
  {
    LODWORD(v12) = v40 - 1;
    if ( (_DWORD)v12 )
    {
      if ( (_DWORD)v12 == 1 )
      {
        LODWORD(v12) = v39 + 40;
        if ( v39 + 40 <= DesiredAccess )
        {
          if ( *(_DWORD *)((char *)&SecurityContext->AccessState + v39 + 4) )
            v42 = (char *)&SecurityContext[1].AccessState + v39;
          AccessState = *(_ACCESS_STATE **)((char *)&SecurityContext[1].SecurityQos + v39);
          goto LABEL_77;
        }
      }
    }
    else
    {
      LODWORD(v12) = v39 + 56;
      if ( v39 + 56 <= DesiredAccess )
      {
        v5 = 1;
        if ( *((_BYTE *)&SecurityContext->AccessState + v39 + 2) )
          v42 = (char *)&SecurityContext[1] + v39;
        v31 = *((_BYTE *)&SecurityContext->AccessState + v39);
        AccessState = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v39);
        v30 = *((_BYTE *)&SecurityContext->AccessState + v39 + 1);
      }
    }
    goto LABEL_65;
  }
  LODWORD(v12) = v39 + 40;
  if ( v39 + 40 > DesiredAccess )
  {
LABEL_65:
    if ( v5 )
      goto LABEL_67;
    goto LABEL_66;
  }
  if ( *((_BYTE *)&SecurityContext->AccessState + v39 + 2) )
    v42 = (char *)&SecurityContext[1] + v39;
  AccessState = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v39);
LABEL_77:
  v31 = *((_BYTE *)&SecurityContext->AccessState + v39);
  v30 = *((_BYTE *)&SecurityContext->AccessState + v39 + 1);
LABEL_67:
  if ( !v42 )
    goto LABEL_15;
  SecurityQos = *v42;
LABEL_49:
  LOBYTE(v12) = SecurityQos - 8;
  if ( (v12 & 0x5D) != 0 )
    goto LABEL_15;
  v32 = BYTE3(SecurityContext->SecurityQos);
  if ( v32 == 1 || !AccessState || !v30 )
    goto LABEL_87;
  LOBYTE(SecurityContext) = 0;
  v12 = (unsigned __int64)AccessState + v30;
  Flags = 0;
  p_SecurityEvaluated = &AccessState->SecurityEvaluated;
  LowPart_high = 0;
  if ( (unsigned __int8)((AccessState->OperationID.LowPart & 0x7F) - 114) <= 1u )
  {
    if ( (unsigned __int64)p_SecurityEvaluated <= v12 )
    {
      Flags = BYTE2(AccessState->OperationID.LowPart);
      LOBYTE(SecurityContext) = BYTE1(AccessState->OperationID.LowPart) & 0xF;
      LowPart_high = HIBYTE(AccessState->OperationID.LowPart);
      goto LABEL_102;
    }
    goto LABEL_101;
  }
  if ( (unsigned __int64)p_SecurityEvaluated > v12 )
  {
LABEL_101:
    v8 = 0;
    goto LABEL_102;
  }
  v37 = (char *)&AccessState->Flags + 1;
  LOBYTE(SecurityContext) = BYTE2(AccessState->OperationID.LowPart) & 0xF;
  v38 = v30;
  if ( (unsigned int)HIBYTE(AccessState->OperationID.HighPart) + 8 <= v30 )
    v38 = HIBYTE(AccessState->OperationID.HighPart) + 8;
  v12 = (unsigned __int64)AccessState + v38;
  if ( (unsigned __int64)v37 <= v12 )
    Flags = AccessState->Flags;
  if ( (unsigned __int64)&AccessState->Flags + 2 > v12 )
    LowPart_high = 0;
  else
    LowPart_high = *v37;
LABEL_102:
  if ( !v8 )
  {
LABEL_87:
    LOBYTE(SecurityContext) = 0;
    Flags = 0;
    LowPart_high = 0;
  }
  McTemplateK0pduuuuup_EtwWriteTransfer(
    v12,
    (_DWORD)SecurityContext,
    (unsigned int)&v48,
    (_DWORD)Irp,
    Irp->IoStatus.Status,
    v32,
    v31,
    (char)SecurityContext,
    Flags,
    LowPart_high,
    (char)Irp);
LABEL_15:
  IofCompleteRequest(Irp, 0);
  return 0;
}

```

## disassembly

```asm
0x14000528c  mov     [rsp-8+arg_10], rbx
0x140005291  push    rbp
0x140005292  push    rsi
0x140005293  push    rdi
0x140005294  push    r12
0x140005296  push    r13
0x140005298  push    r14
0x14000529a  push    r15
0x14000529c  lea     rbp, [rsp-27h]
0x1400052a1  sub     rsp, 90h
0x1400052a8  mov     rax, cs:__security_cookie
0x1400052af  xor     rax, rsp
0x1400052b2  mov     [rbp+57h+var_38], rax
0x1400052b6  xor     eax, eax
0x1400052b8  xorps   xmm0, xmm0
0x1400052bb  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x1400052bf  mov     rsi, rdx
0x1400052c2  mov     rax, [rdx+0B8h]
0x1400052c9  mov     rdi, rcx
0x1400052cc  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x1400052d0  xor     r13d, r13d
0x1400052d3  add     rcx, 30h ; '0'; SpinLock
0x1400052d7  mov     [rdx+30h], r13d
0x1400052db  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x1400052df  mov     ebx, [rax+18h]
0x1400052e2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400052e9  nop     dword ptr [rax+rax+00h]
0x1400052ee  mov     rcx, [rdi+8]; DeviceObject
0x1400052f2  lea     r14d, [r13+1]
0x1400052f6  mov     edx, r14d; Type
0x1400052f9  mov     [rdi+224h], ebx
0x1400052ff  mov     r8d, ebx; State
0x140005302  call    cs:__imp_PoSetPowerState
0x140005309  nop     dword ptr [rax+rax+00h]
0x14000530e  cmp     ebx, r14d
0x140005311  jz      loc_14000550F
0x140005317  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000531b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140005322  nop     dword ptr [rax+rax+00h]
0x140005327  cmp     [rdi+224h], r14d
0x14000532e  jz      loc_14000541E
0x140005334  lea     rcx, [rdi+2D0h]
0x14000533b  mov     al, [rcx+27h]
0x14000533e  test    al, al
0x140005340  jz      loc_1400058E7
0x140005346  cmp     [rdi+410h], r13d
0x14000534d  jbe     short loc_140005358
0x14000534f  mov     rcx, [rdi+18h]
0x140005353  call    RaidUpdateCrashDumpPowerReady
0x140005358  mov     rcx, rdi
0x14000535b  call    RaidUnitCheckAndAcquirePoFx
0x140005360  test    al, al
0x140005362  jnz     loc_1400054C9
0x140005368  mov     rcx, cs:WPP_GLOBAL_Control
0x14000536f  lea     rax, WPP_GLOBAL_Control
0x140005376  cmp     rcx, rax
0x140005379  jnz     loc_1400058FE
0x14000537f  cmp     cs:StorEtwLoggingEnabled, r13b
0x140005386  jnz     loc_1400055A3
0x14000538c  cmp     cs:StorEtwLoggingEnabled, r13b
0x140005393  mov     byte ptr [rsi+8Dh], 0ACh
0x14000539a  mov     [rsi+30h], r13d
0x14000539e  jz      short loc_1400053E3
0x1400053a0  xorps   xmm0, xmm0
0x1400053a3  lea     rdx, [rbp+57h+var_48]
0x1400053a7  mov     rcx, rsi
0x1400053aa  movups  [rbp+57h+var_48], xmm0
0x1400053ae  call    cs:__imp_IoGetActivityIdIrp
0x1400053b5  nop     dword ptr [rax+rax+00h]
0x1400053ba  mov     rdx, [rsi+0B8h]
0x1400053c1  movzx   eax, byte ptr [rdx]
0x1400053c4  sub     eax, 0Eh
0x1400053c7  jz      loc_1400055FA
0x1400053cd  sub     eax, r14d
0x1400053d0  jnz     loc_140005626
0x1400053d6  cmp     cs:byte_140177431, r13b
0x1400053dd  jl      loc_14000593A
0x1400053e3  xor     edx, edx; PriorityBoost
0x1400053e5  mov     rcx, rsi; Irp
0x1400053e8  call    cs:__imp_IofCompleteRequest
0x1400053ef  nop     dword ptr [rax+rax+00h]
0x1400053f4  xor     eax, eax
0x1400053f6  mov     rcx, [rbp+57h+var_38]
0x1400053fa  xor     rcx, rsp; StackCookie
0x1400053fd  call    __security_check_cookie
0x140005402  mov     rbx, [rsp+0C0h+arg_10]
0x14000540a  add     rsp, 90h
0x140005411  pop     r15
0x140005413  pop     r14
0x140005415  pop     r13
0x140005417  pop     r12
0x140005419  pop     rdi
0x14000541a  pop     rsi
0x14000541b  pop     rbp
0x14000541c  retn
0x14000541e  mov     rcx, rdi
0x140005421  call    RaidUnitCheckAndAcquirePoFx
0x140005426  test    al, al
0x140005428  jz      loc_140005544
0x14000542e  mov     rax, [rdi+750h]
0x140005435  test    dword ptr [rax+20h], 100h
0x14000543c  jnz     loc_140005577
0x140005442  mov     rcx, rdi
0x140005445  call    RaidUnitCheckAndAcquirePoFx
0x14000544a  test    al, al
0x14000544c  jz      loc_1400058A4
0x140005452  mov     rax, [rdi+750h]
0x140005459  mov     rcx, [rdi+748h]; RunRefCacheAware
0x140005460  mov     ebx, [rax+20h]
0x140005463  shr     ebx, 1
0x140005465  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14000546c  nop     dword ptr [rax+rax+00h]
0x140005471  test    r14b, bl
0x140005474  jnz     loc_1400058A4
0x14000547a  mov     r9, rdi
0x14000547d  call    StorPortUnitPoFxD0Completion
0x140005482  mov     rax, [rdi+18h]
0x140005486  lock dec dword ptr [rax+17CCh]
0x14000548d  mov     rcx, [rdi+18h]
0x140005491  test    byte ptr [rcx+6Eh], 40h
0x140005495  jnz     loc_1400058D7
0x14000549b  mov     rcx, [rdi+748h]; RunRefCacheAware
0x1400054a2  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400054a9  nop     dword ptr [rax+rax+00h]
0x1400054ae  cmp     [rdi+410h], r13d
0x1400054b5  jbe     loc_140005368
0x1400054bb  mov     rcx, [rdi+18h]
0x1400054bf  call    RaidUpdateCrashDumpPowerReady
0x1400054c4  jmp     loc_140005368
0x1400054c9  mov     rax, [rdi+18h]
0x1400054cd  lock add [rax+17CCh], r14d
0x1400054d5  mov     rcx, [rdi+18h]
0x1400054d9  test    byte ptr [rcx+6Eh], 40h
0x1400054dd  jz      short loc_1400054F7
0x1400054df  mov     eax, [rcx+0A8h]
0x1400054e5  cmp     [rcx+17CCh], eax
0x1400054eb  jnz     short loc_1400054F7
0x1400054ed  mov     r9b, r14b
0x1400054f0  xor     edx, edx
0x1400054f2  call    RaidAdapterPoFxSetDeviceIdleTimeout
0x1400054f7  mov     rcx, [rdi+748h]; RunRefCacheAware
0x1400054fe  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140005505  nop     dword ptr [rax+rax+00h]
0x14000550a  jmp     loc_140005368
0x14000550f  mov     al, [rdi+1F8h]
0x140005515  test    al, al
0x140005517  jns     loc_140005317
0x14000551d  mov     rcx, rdi
0x140005520  call    RaidResumeUnitQueue
0x140005525  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140005529  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140005530  nop     dword ptr [rax+rax+00h]
0x140005535  xor     edx, edx
0x140005537  mov     rcx, rdi
0x14000553a  call    RaidUnitRestartQueue
0x14000553f  jmp     loc_140005327
0x140005544  mov     al, [rdi+2F7h]
0x14000554a  test    al, al
0x14000554c  jz      loc_1400054AE
0x140005552  mov     eax, r13d
0x140005555  mov     edx, 2
0x14000555a  xchg    al, [rdi+2F7h]
0x140005560  mov     rcx, rdi
0x140005563  call    RaUnitUnlockForwardIo
0x140005568  xor     edx, edx
0x14000556a  mov     rcx, rdi
0x14000556d  call    RaidUnitRestartQueue
0x140005572  jmp     loc_1400054AE
0x140005577  add     [rdi+0D18h], r14d
0x14000557e  lock bts dword ptr [rdi+200h], 1
0x140005587  setb    al
0x14000558a  test    al, al
0x14000558c  jz      loc_140005859
0x140005592  mov     rax, [rdi+750h]
0x140005599  btr     dword ptr [rax+20h], 9
0x14000559e  jmp     loc_140005442
0x1400055a3  xorps   xmm0, xmm0
0x1400055a6  lea     rdx, [rbp+57h+var_48]
0x1400055aa  mov     rcx, rsi
0x1400055ad  movups  [rbp+57h+var_48], xmm0
0x1400055b1  call    cs:__imp_IoGetActivityIdIrp
0x1400055b8  nop     dword ptr [rax+rax+00h]
0x1400055bd  test    cs:byte_140177432, 10h
0x1400055c4  jz      loc_14000538C
0x1400055ca  mov     al, [rdi+6Ah]
0x1400055cd  lea     r8, [rbp+57h+var_48]
0x1400055d1  mov     r9, [rdi+18h]
0x1400055d5  mov     [rsp+0C0h+var_88], rsi
0x1400055da  mov     [rsp+0C0h+var_90], al
0x1400055de  mov     al, [rdi+69h]
0x1400055e1  mov     r9d, [r9+38h]
0x1400055e5  mov     byte ptr [rsp+0C0h+var_98], al
0x1400055e9  mov     al, [rdi+68h]
0x1400055ec  mov     byte ptr [rsp+0C0h+var_A0], al
0x1400055f0  call    McTemplateK0quuupd_EtwWriteTransfer
0x1400055f5  jmp     loc_14000538C
0x1400055fa  test    cs:byte_140177432, 8
0x140005601  jz      loc_1400053E3
0x140005607  lea     rdx, EventNonReadWriteRequestComplete
0x14000560e  mov     eax, [rsi+30h]
0x140005611  lea     r8, [rbp+57h+var_48]
0x140005615  mov     r9, rsi
0x140005618  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14000561c  call    McTemplateK0pd_EtwWriteTransfer
0x140005621  jmp     loc_1400053E3
0x140005626  cmp     eax, 0Ch
0x140005629  jnz     loc_1400053E3
0x14000562f  cmp     byte ptr [rdx+1], 7
0x140005633  jz      short loc_14000564B
0x140005635  test    cs:byte_140177432, 20h
0x14000563c  jz      loc_1400053E3
0x140005642  lea     rdx, EventPnpRequestComplete
0x140005649  jmp     short loc_14000560E
0x14000564b  cmp     [rdx+8], r13d
0x14000564f  jnz     short loc_140005635
0x140005651  test    cs:byte_140177432, 40h
0x140005658  jz      loc_1400053E3
0x14000565e  mov     rax, [rsi+38h]
0x140005662  test    rax, rax
0x140005665  jz      loc_14014C1C0
0x14000566b  mov     ecx, [rax]
0x14000566d  jmp     loc_14014C1C3
0x140005672  mov     cl, [rdx+48h]
0x140005675  mov     r9, [rdx+20h]
0x140005679  mov     r10b, [rdx+0Bh]
0x14000567d  mov     dil, [rdx+4]
0x140005681  test    eax, eax
0x140005683  jnz     loc_1400053E3
0x140005689  sub     cl, 8
0x14000568c  test    cl, 5Dh
0x14000568f  jnz     loc_1400053E3
0x140005695  mov     bl, [rdx+3]
0x140005698  cmp     bl, r14b
0x14000569b  jz      loc_14000581C
0x1400056a1  test    r9, r9
0x1400056a4  jz      loc_14000581C
0x1400056aa  test    r10b, r10b
0x1400056ad  jz      loc_14000581C
0x1400056b3  mov     al, [r9]
0x1400056b6  mov     dl, r13b
0x1400056b9  and     al, 7Fh
0x1400056bb  movzx   ecx, r10b
0x1400056bf  sub     al, 72h ; 'r'
0x1400056c1  add     rcx, r9
0x1400056c4  cmp     al, r14b
0x1400056c7  mov     r11b, r13b
0x1400056ca  lea     rax, [r9+8]
0x1400056ce  mov     r8b, r13b
0x1400056d1  jbe     loc_140005954
0x1400056d7  cmp     rax, rcx
0x1400056da  ja      loc_14000596A
0x1400056e0  movzx   ecx, byte ptr [r9+7]
0x1400056e5  lea     r8, [r9+0Dh]
0x1400056e9  mov     dl, [r9+2]
0x1400056ed  add     ecx, 8
0x1400056f0  and     dl, 0Fh
0x1400056f3  movzx   eax, r10b
0x1400056f7  cmp     ecx, eax
0x1400056f9  cmovbe  eax, ecx
0x1400056fc  mov     ecx, eax
0x1400056fe  add     rcx, r9
0x140005701  cmp     r8, rcx
0x140005704  ja      short loc_14000570A
0x140005706  mov     r11b, [r9+0Ch]
0x14000570a  lea     rax, [r9+0Eh]
0x14000570e  cmp     rax, rcx
0x140005711  ja      loc_14000594F
0x140005717  mov     r8b, [r8]
0x14000571a  jmp     loc_14000596D
0x14000571f  mov     r8, rcx
0x140005722  mov     ecx, [rcx+rdx]
0x140005725  sub     ecx, 40h ; '@'
0x140005728  jz      short loc_14000578E
0x14000572a  sub     ecx, r14d
0x14000572d  jz      short loc_140005762
0x14000572f  cmp     ecx, r14d
0x140005732  jnz     short loc_14000573D
0x140005734  lea     rcx, [r8+28h]
0x140005738  cmp     rcx, rbx
0x14000573b  jbe     short loc_1400057B2
0x14000573d  test    r13b, r13b
0x140005740  jnz     short loc_14000574E
0x140005742  add     r15d, r14d
0x140005745  cmp     r15d, r12d
0x140005748  jb      loc_1400057F9
0x14000574e  xor     r13d, r13d
0x140005751  test    r11, r11
0x140005754  jz      loc_1400053E3
0x14000575a  mov     cl, [r11]
0x14000575d  jmp     loc_140005689
0x140005762  lea     rcx, [r8+38h]
0x140005766  cmp     rcx, rbx
0x140005769  ja      short loc_14000573D
0x14000576b  cmp     byte ptr [r8+rdx+0Ah], 0
0x140005771  mov     r13b, r14b
0x140005774  jbe     short loc_14000577D
0x140005776  lea     r11, [rdx+18h]
0x14000577a  add     r11, r8
0x14000577d  mov     dil, [r8+rdx+8]
0x140005782  mov     r9, [r8+rdx+10h]
  ... truncated ...
```
