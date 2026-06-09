# RaidAdapterPowerUpDeviceCompletionLastStep

- ea: `0x14000f4bc`
- end: `0x14000fa77`
- name: `RaidAdapterPowerUpDeviceCompletionLastStep`
- size: `1467`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `3`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000f180`
- `0x140010230`
- `0x1400a4470`

## callees

- `0x140004b4c`
- `0x14000f4bc`
- `0x140025400`
- `0x140028f3c`
- `0x14002c1c0`
- `0x14002d320`
- `0x14002eea0`
- `0x140048fac`
- `0x140063c74`
- `0x140068154`
- `0x14006d1c0`
- `0x14006d298`
- `0x14006f610`
- `0x1400848c4`
- `0x1400a2fb4`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000fa27`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000fa27`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000f5f5`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000f698`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000f5f5`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000f698`
- `ntoskrnl!KeSetEvent` at `0x14000f9f5`
- `ntoskrnl!KeSetEvent` at `0x14000f9f5`
- `ntoskrnl!KeLowerIrql` at `0x14000f54f`
- `ntoskrnl!KeLowerIrql` at `0x14000f54f`
- `ntoskrnl!KfRaiseIrql` at `0x14000f535`
- `ntoskrnl!KfRaiseIrql` at `0x14000f535`
- `ntoskrnl!IofCompleteRequest` at `0x14000f952`
- `ntoskrnl!IofCompleteRequest` at `0x14000f952`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000fa43`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000fa43`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f56d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f56d`
- `ntoskrnl!IoReportInterruptActive` at `0x14000f653`
- `ntoskrnl!IoReportInterruptActive` at `0x14000f653`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f583`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f583`

## pseudocode

```c
void __fastcall RaidAdapterPowerUpDeviceCompletionLastStep(PIRP Irp, __int64 a2)
{
  char v4; // r13
  KIRQL v5; // bl
  unsigned int LowPart; // ebx
  int v7; // edx
  int v8; // ecx
  __int64 v9; // rax
  bool v10; // zf
  unsigned __int64 v11; // rcx
  _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  int *Information; // rax
  int v14; // ecx
  __int64 *v15; // rdx
  _IO_SECURITY_CONTEXT *SecurityContext; // rdx
  unsigned int AccessState; // r12d
  unsigned __int8 v18; // r10
  char *v19; // r11
  char v20; // r15
  _ACCESS_STATE *v21; // r9
  unsigned int v22; // r14d
  unsigned __int64 DesiredAccess; // rbx
  __int64 v24; // r8
  int v25; // ecx
  char SecurityQos; // cl
  char v27; // bl
  char Flags; // r11
  unsigned __int8 *p_SecurityEvaluated; // rax
  char LowPart_high; // r8
  char *v31; // r8
  unsigned int v32; // eax
  char v33; // al
  PSLIST_ENTRY v34; // rbx
  IRP *Next; // rdx
  unsigned __int64 v36; // r8
  signed __int32 v37; // eax
  signed __int32 v38; // ett
  unsigned int v39; // r8d
  PSLIST_ENTRY v40; // rax
  __int64 v41; // [rsp+60h] [rbp-29h] BYREF
  __int64 v42; // [rsp+68h] [rbp-21h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+78h] [rbp-11h] BYREF
  __int128 v44; // [rsp+90h] [rbp+7h] BYREF

  LODWORD(v42) = 0;
  v41 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v4 = 0;
  if ( (unsigned __int8)RaidIsAdapterControlSupported(a2 + 360, 2) )
    RaidAdapterRestartAdapter(a2);
  else
    RaidAdapterReInitialize(a2);
  RaidResumeAdapterQueue(a2, 0, 0);
  v5 = KfRaiseIrql(2u);
  RaidAdapterRestartQueues(a2, 0);
  KeLowerIrql(v5);
  LowPart = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a2 + 80), &LockHandle);
  *(_DWORD *)(a2 + 332) = LowPart;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  StorSetDevicePowerState(*(_QWORD *)(a2 + 8), LowPart);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      28,
      WPP_24f186e44650306b933e2c903810ea21_Traceguids,
      a2,
      Irp,
      Irp->IoStatus.Status);
  }
  if ( StorEtwLoggingEnabled )
  {
    v44 = 0;
    IoGetActivityIdIrp(Irp, &v44);
    if ( (byte_140177432 & 0x10) != 0 )
      McTemplateK0qpd_EtwWriteTransfer(
        v8,
        v7,
        (unsigned int)&v44,
        *(_DWORD *)(a2 + 56),
        (char)Irp,
        Irp->IoStatus.Status);
  }
  if ( (*(_BYTE *)(a2 + 109) & 1) != 0 )
  {
    LODWORD(v41) = *(_DWORD *)(a2 + 860);
    if ( *(_BYTE *)(a2 + 4433) )
      v9 = *(_QWORD *)(a2 + 4416);
    else
      v9 = *(_QWORD *)(a2 + 848);
    v42 = v9;
    IoReportInterruptActive(&v41);
  }
  if ( *(_DWORD *)(a2 + 96) && *(_QWORD *)(a2 + 5080) )
    RaidUpdateCrashDumpPowerReady(a2);
  v10 = StorEtwLoggingEnabled == 0;
  *((_BYTE *)&Irp->Tail.CompletionKey + 21) = -84;
  if ( v10 )
    goto LABEL_83;
  v44 = 0;
  IoGetActivityIdIrp(Irp, &v44);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  switch ( CurrentStackLocation->MajorFunction )
  {
    case 0xEu:
      if ( (byte_140177432 & 8) == 0 )
        break;
      v15 = EventNonReadWriteRequestComplete;
LABEL_82:
      McTemplateK0pd_EtwWriteTransfer(v11, v15, &v44, Irp, Irp->IoStatus.Status);
      break;
    case 0xFu:
      if ( byte_140177431 >= 0 )
        break;
      SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
      if ( BYTE2(SecurityContext->SecurityQos) == 40 )
      {
        if ( SecurityContext->FullCreateOptions )
          break;
        AccessState = (unsigned int)SecurityContext[2].AccessState;
        if ( !AccessState )
          break;
        v18 = 0;
        v19 = 0;
        v20 = 0;
        v21 = 0;
        v22 = 0;
        while ( 1 )
        {
          v11 = *((unsigned int *)&SecurityContext[5].SecurityQos + v22);
          if ( (unsigned int)v11 >= 0x80 )
          {
            DesiredAccess = SecurityContext->DesiredAccess;
            if ( (unsigned int)v11 < (unsigned int)DesiredAccess )
            {
              v24 = (unsigned int)v11;
              v25 = *(_DWORD *)((char *)&SecurityContext->SecurityQos + v11) - 64;
              if ( v25 )
              {
                LODWORD(v11) = v25 - 1;
                if ( (_DWORD)v11 )
                {
                  if ( (_DWORD)v11 == 1 )
                  {
                    LODWORD(v11) = v24 + 40;
                    if ( v24 + 40 <= DesiredAccess )
                    {
                      if ( *(_DWORD *)((char *)&SecurityContext->AccessState + v24 + 4) )
                        v19 = (char *)&SecurityContext[1].AccessState + v24;
                      v21 = *(_ACCESS_STATE **)((char *)&SecurityContext[1].SecurityQos + v24);
                      goto LABEL_46;
                    }
                  }
                }
                else
                {
                  LODWORD(v11) = v24 + 56;
                  if ( v24 + 56 <= DesiredAccess )
                  {
                    v4 = 1;
                    if ( *((_BYTE *)&SecurityContext->AccessState + v24 + 2) )
                      v19 = (char *)&SecurityContext[1] + v24;
                    v20 = *((_BYTE *)&SecurityContext->AccessState + v24);
                    v21 = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v24);
                    v18 = *((_BYTE *)&SecurityContext->AccessState + v24 + 1);
                  }
                }
              }
              else
              {
                LODWORD(v11) = v24 + 40;
                if ( v24 + 40 <= DesiredAccess )
                {
                  if ( *((_BYTE *)&SecurityContext->AccessState + v24 + 2) )
                    v19 = (char *)&SecurityContext[1] + v24;
                  v21 = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v24);
LABEL_46:
                  v20 = *((_BYTE *)&SecurityContext->AccessState + v24);
                  v18 = *((_BYTE *)&SecurityContext->AccessState + v24 + 1);
LABEL_54:
                  if ( v19 )
                  {
                    SecurityQos = *v19;
                    goto LABEL_60;
                  }
                  goto LABEL_83;
                }
              }
              if ( v4 )
                goto LABEL_54;
            }
          }
          if ( ++v22 >= AccessState )
            goto LABEL_54;
        }
      }
      SecurityQos = (char)SecurityContext[3].SecurityQos;
      v21 = SecurityContext[1].AccessState;
      v18 = BYTE3(SecurityContext->AccessState);
      v20 = BYTE4(SecurityContext->SecurityQos);
      if ( BYTE2(SecurityContext->SecurityQos) )
        break;
LABEL_60:
      LOBYTE(v11) = SecurityQos - 8;
      if ( (v11 & 0x5D) != 0 )
        break;
      v27 = BYTE3(SecurityContext->SecurityQos);
      if ( v27 == 1 || !v21 || !v18 )
        goto LABEL_78;
      LOBYTE(SecurityContext) = 0;
      v11 = (unsigned __int64)v21 + v18;
      Flags = 0;
      p_SecurityEvaluated = &v21->SecurityEvaluated;
      LowPart_high = 0;
      if ( (unsigned __int8)((v21->OperationID.LowPart & 0x7F) - 114) <= 1u )
      {
        if ( (unsigned __int64)p_SecurityEvaluated <= v11 )
        {
          Flags = BYTE2(v21->OperationID.LowPart);
          LOBYTE(SecurityContext) = BYTE1(v21->OperationID.LowPart) & 0xF;
          LowPart_high = HIBYTE(v21->OperationID.LowPart);
LABEL_75:
          v33 = 1;
          goto LABEL_77;
        }
      }
      else if ( (unsigned __int64)p_SecurityEvaluated <= v11 )
      {
        v31 = (char *)&v21->Flags + 1;
        LOBYTE(SecurityContext) = BYTE2(v21->OperationID.LowPart) & 0xF;
        v32 = v18;
        if ( (unsigned int)HIBYTE(v21->OperationID.HighPart) + 8 <= v18 )
          v32 = HIBYTE(v21->OperationID.HighPart) + 8;
        v11 = (unsigned __int64)v21 + v32;
        if ( (unsigned __int64)v31 <= v11 )
          Flags = v21->Flags;
        if ( (unsigned __int64)&v21->Flags + 2 > v11 )
          LowPart_high = 0;
        else
          LowPart_high = *v31;
        goto LABEL_75;
      }
      v33 = 0;
LABEL_77:
      if ( v33 )
      {
LABEL_79:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v11,
          (_DWORD)SecurityContext,
          (unsigned int)&v44,
          (_DWORD)Irp,
          Irp->IoStatus.Status,
          v27,
          v20,
          (char)SecurityContext,
          Flags,
          LowPart_high,
          (char)Irp);
        break;
      }
LABEL_78:
      LOBYTE(SecurityContext) = 0;
      Flags = 0;
      LowPart_high = 0;
      goto LABEL_79;
    case 0x1Bu:
      if ( CurrentStackLocation->MinorFunction == 7 && !CurrentStackLocation->Parameters.Read.Length )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          Information = (int *)Irp->IoStatus.Information;
          if ( Information )
            v14 = *Information;
          else
            v14 = 0;
          McTemplateK0pqd_EtwWriteTransfer(
            v14,
            (_DWORD)CurrentStackLocation,
            (unsigned int)&v44,
            (_DWORD)Irp,
            v14,
            Irp->IoStatus.Status);
        }
        break;
      }
      if ( (byte_140177432 & 0x20) != 0 )
      {
        v15 = EventPnpRequestComplete;
        goto LABEL_82;
      }
      break;
  }
LABEL_83:
  IofCompleteRequest(Irp, 0);
LABEL_92:
  while ( 1 )
  {
    v40 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(a2 + 5008));
    if ( !v40 )
      break;
    v34 = v40 - 129;
    if ( *((_BYTE *)&v40[-2].Next + 9) )
    {
      Next = (IRP *)v34[128].Next;
      v34[128].Next = 0;
      *((_BYTE *)&v34[127].Next + 9) = 0;
      _interlockedbittestandset((volatile signed __int32 *)&v34[32], 7u);
      RaidUnitProcessSetDevicePowerIrp(&v40[-129], Next);
      _interlockedbittestandreset((volatile signed __int32 *)&v34[32], 7u);
      v36 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
      v37 = *(_DWORD *)(v36 + *((_QWORD *)&v34[2].Next + 1));
      while ( (v37 & 1) == 0 )
      {
        v38 = v37;
        v37 = _InterlockedCompareExchange(
                (volatile signed __int32 *)(v36 + *((_QWORD *)&v34[2].Next + 1)),
                v37 - 2,
                v37);
        if ( v38 == v37 )
          goto LABEL_92;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v34[64].Next + 2, 0xFFFFFFFF) == 1 )
        KeSetEvent((PRKEVENT)(&v34[32].Next + 1), 0, 0);
    }
    else if ( *((_BYTE *)&v34[127].Next + 8) )
    {
      v39 = *((_DWORD *)&v34[127].Next + 3);
      *((_BYTE *)&v34[127].Next + 8) = 0;
      StorPortUnitIdleState((__int64)&v40[-129], 0, v39);
    }
  }
  ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a2 + 320));
}

```

## disassembly

```asm
0x14000f4bc  mov     [rsp-8+arg_10], rbx
0x14000f4c1  push    rbp
0x14000f4c2  push    rsi
0x14000f4c3  push    rdi
0x14000f4c4  push    r12
0x14000f4c6  push    r13
0x14000f4c8  push    r14
0x14000f4ca  push    r15
0x14000f4cc  lea     rbp, [rsp-27h]
0x14000f4d1  sub     rsp, 0B0h
0x14000f4d8  mov     rax, cs:__security_cookie
0x14000f4df  xor     rax, rsp
0x14000f4e2  mov     [rbp+57h+var_40], rax
0x14000f4e6  xor     eax, eax
0x14000f4e8  mov     rdi, rcx
0x14000f4eb  mov     rsi, rdx
0x14000f4ee  mov     qword ptr [rbp+57h+var_7C], rax
0x14000f4f2  xorps   xmm0, xmm0
0x14000f4f5  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14000f4f9  lea     rcx, [rdx+168h]
0x14000f500  mov     [rbp-29h], rax
0x14000f504  lea     edx, [rax+2]
0x14000f507  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14000f50b  call    RaidIsAdapterControlSupported
0x14000f510  xor     r13d, r13d
0x14000f513  mov     rcx, rsi
0x14000f516  test    al, al
0x14000f518  jz      short loc_14000F521
0x14000f51a  call    RaidAdapterRestartAdapter
0x14000f51f  jmp     short loc_14000F526
0x14000f521  call    RaidAdapterReInitialize
0x14000f526  xor     r8d, r8d
0x14000f529  xor     edx, edx
0x14000f52b  mov     rcx, rsi
0x14000f52e  call    RaidResumeAdapterQueue
0x14000f533  mov     cl, 2; NewIrql
0x14000f535  call    cs:__imp_KfRaiseIrql
0x14000f53c  nop     dword ptr [rax+rax+00h]
0x14000f541  xor     edx, edx
0x14000f543  mov     rcx, rsi
0x14000f546  mov     bl, al
0x14000f548  call    RaidAdapterRestartQueues
0x14000f54d  mov     cl, bl; NewIrql
0x14000f54f  call    cs:__imp_KeLowerIrql
0x14000f556  nop     dword ptr [rax+rax+00h]
0x14000f55b  mov     rax, [rdi+0B8h]
0x14000f562  lea     rcx, [rsi+50h]; SpinLock
0x14000f566  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14000f56a  mov     ebx, [rax+18h]
0x14000f56d  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000f574  nop     dword ptr [rax+rax+00h]
0x14000f579  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000f57d  mov     [rsi+14Ch], ebx
0x14000f583  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000f58a  nop     dword ptr [rax+rax+00h]
0x14000f58f  mov     rcx, [rsi+8]
0x14000f593  mov     edx, ebx
0x14000f595  call    StorSetDevicePowerState
0x14000f59a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f5a1  lea     rax, WPP_GLOBAL_Control
0x14000f5a8  cmp     rcx, rax
0x14000f5ab  jz      short loc_14000F5DE
0x14000f5ad  mov     eax, [rcx+2Ch]
0x14000f5b0  test    al, 4
0x14000f5b2  jz      short loc_14000F5DE
0x14000f5b4  cmp     byte ptr [rcx+29h], 4
0x14000f5b8  jb      short loc_14000F5DE
0x14000f5ba  mov     eax, [rdi+30h]
0x14000f5bd  lea     r8, WPP_24f186e44650306b933e2c903810ea21_Traceguids
0x14000f5c4  mov     rcx, [rcx+18h]
0x14000f5c8  mov     edx, 1Ch
0x14000f5cd  mov     [rsp+0E0h+var_B8], eax
0x14000f5d1  mov     r9, rsi
0x14000f5d4  mov     [rsp+0E0h+var_C0], rdi
0x14000f5d9  call    WPP_SF_qqD
0x14000f5de  cmp     cs:StorEtwLoggingEnabled, r13b
0x14000f5e5  jz      short loc_14000F623
0x14000f5e7  xorps   xmm0, xmm0
0x14000f5ea  lea     rdx, [rbp+57h+var_50]
0x14000f5ee  mov     rcx, rdi
0x14000f5f1  movups  [rbp+57h+var_50], xmm0
0x14000f5f5  call    cs:__imp_IoGetActivityIdIrp
0x14000f5fc  nop     dword ptr [rax+rax+00h]
0x14000f601  test    cs:byte_140177432, 10h
0x14000f608  jz      short loc_14000F623
0x14000f60a  mov     eax, [rdi+30h]
0x14000f60d  lea     r8, [rbp+57h+var_50]
0x14000f611  mov     r9d, [rsi+38h]
0x14000f615  mov     [rsp+0E0h+var_B8], eax
0x14000f619  mov     [rsp+0E0h+var_C0], rdi
0x14000f61e  call    McTemplateK0qpd_EtwWriteTransfer
0x14000f623  test    byte ptr [rsi+6Dh], 1
0x14000f627  jz      short loc_14000F65F
0x14000f629  mov     eax, [rsi+35Ch]
0x14000f62f  mov     [rbp+57h+var_80], eax
0x14000f632  cmp     [rsi+1151h], r13b
0x14000f639  jz      short loc_14000F644
0x14000f63b  mov     rax, [rsi+1140h]
0x14000f642  jmp     short loc_14000F64B
0x14000f644  mov     rax, [rsi+350h]
0x14000f64b  lea     rcx, [rbp+57h+var_80]
0x14000f64f  mov     qword ptr [rbp+57h+var_7C+4], rax
0x14000f653  call    cs:__imp_IoReportInterruptActive
0x14000f65a  nop     dword ptr [rax+rax+00h]
0x14000f65f  cmp     [rsi+60h], r13d
0x14000f663  jbe     short loc_14000F676
0x14000f665  cmp     [rsi+13D8h], r13
0x14000f66c  jz      short loc_14000F676
0x14000f66e  mov     rcx, rsi
0x14000f671  call    RaidUpdateCrashDumpPowerReady
0x14000f676  cmp     cs:StorEtwLoggingEnabled, r13b
0x14000f67d  mov     byte ptr [rdi+8Dh], 0ACh
0x14000f684  jz      loc_14000F94D
0x14000f68a  xorps   xmm0, xmm0
0x14000f68d  lea     rdx, [rbp+57h+var_50]
0x14000f691  mov     rcx, rdi
0x14000f694  movups  [rbp+57h+var_50], xmm0
0x14000f698  call    cs:__imp_IoGetActivityIdIrp
0x14000f69f  nop     dword ptr [rax+rax+00h]
0x14000f6a4  mov     rdx, [rdi+0B8h]
0x14000f6ab  movzx   eax, byte ptr [rdx]
0x14000f6ae  sub     eax, 0Eh
0x14000f6b1  jz      loc_14000F92A
0x14000f6b7  sub     eax, 1
0x14000f6ba  jz      short loc_14000F723
0x14000f6bc  cmp     eax, 0Ch
0x14000f6bf  jnz     loc_14000F94D
0x14000f6c5  cmp     byte ptr [rdx+1], 7
0x14000f6c9  jnz     short loc_14000F70A
0x14000f6cb  cmp     [rdx+8], r13d
0x14000f6cf  jnz     short loc_14000F70A
0x14000f6d1  test    cs:byte_140177432, 40h
0x14000f6d8  jz      loc_14000F94D
0x14000f6de  mov     rax, [rdi+38h]
0x14000f6e2  test    rax, rax
0x14000f6e5  jz      short loc_14000F6EB
0x14000f6e7  mov     ecx, [rax]
0x14000f6e9  jmp     short loc_14000F6EE
0x14000f6eb  mov     ecx, r13d
0x14000f6ee  mov     eax, [rdi+30h]
0x14000f6f1  lea     r8, [rbp+57h+var_50]
0x14000f6f5  mov     [rsp+0E0h+var_B8], eax
0x14000f6f9  mov     r9, rdi
0x14000f6fc  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x14000f700  call    McTemplateK0pqd_EtwWriteTransfer
0x14000f705  jmp     loc_14000F94D
0x14000f70a  test    cs:byte_140177432, 20h
0x14000f711  jz      loc_14000F94D
0x14000f717  lea     rdx, EventPnpRequestComplete
0x14000f71e  jmp     loc_14000F93A
0x14000f723  cmp     cs:byte_140177431, r13b
0x14000f72a  jge     loc_14000F94D
0x14000f730  mov     rdx, [rdx+8]
0x14000f734  movzx   eax, byte ptr [rdx+2]
0x14000f738  cmp     al, 28h ; '('
0x14000f73a  jnz     loc_14000F82F
0x14000f740  cmp     [rdx+14h], r13d
0x14000f744  jnz     loc_14000F94D
0x14000f74a  mov     r12d, [rdx+38h]
0x14000f74e  test    r12d, r12d
0x14000f751  jz      loc_14000F94D
0x14000f757  mov     r10b, r13b
0x14000f75a  mov     r11, r13
0x14000f75d  mov     r15b, r13b
0x14000f760  mov     r9, r13
0x14000f763  mov     r14d, r13d
0x14000f766  mov     eax, r14d
0x14000f769  mov     ecx, [rdx+rax*4+78h]
0x14000f76d  cmp     ecx, 80h
0x14000f773  jb      loc_14000F7FA
0x14000f779  mov     ebx, [rdx+10h]
0x14000f77c  cmp     ecx, ebx
0x14000f77e  jnb     short loc_14000F7FA
0x14000f780  mov     r8d, ecx
0x14000f783  mov     ecx, [rcx+rdx]
0x14000f786  sub     ecx, 40h ; '@'
0x14000f789  jz      short loc_14000F7EC
0x14000f78b  sub     ecx, 1
0x14000f78e  jz      short loc_14000F7C0
0x14000f790  cmp     ecx, 1
0x14000f793  jnz     short loc_14000F7F5
0x14000f795  lea     rcx, [r8+28h]
0x14000f799  cmp     rcx, rbx
0x14000f79c  ja      short loc_14000F7F5
0x14000f79e  xor     r13d, r13d
0x14000f7a1  cmp     [r8+rdx+0Ch], r13d
0x14000f7a6  jbe     short loc_14000F7AF
0x14000f7a8  lea     r11, [rdx+20h]
0x14000f7ac  add     r11, r8
0x14000f7af  mov     r9, [r8+rdx+18h]
0x14000f7b4  mov     r15b, [r8+rdx+8]
0x14000f7b9  mov     r10b, [r8+rdx+9]
0x14000f7be  jmp     short loc_14000F809
0x14000f7c0  lea     rcx, [r8+38h]
0x14000f7c4  cmp     rcx, rbx
0x14000f7c7  ja      short loc_14000F7F5
0x14000f7c9  cmp     byte ptr [r8+rdx+0Ah], 0
0x14000f7cf  mov     r13b, 1
0x14000f7d2  jbe     short loc_14000F7DB
0x14000f7d4  lea     r11, [rdx+18h]
0x14000f7d8  add     r11, r8
0x14000f7db  mov     r15b, [r8+rdx+8]
0x14000f7e0  mov     r9, [r8+rdx+10h]
0x14000f7e5  mov     r10b, [r8+rdx+9]
0x14000f7ea  jmp     short loc_14000F7F5
0x14000f7ec  lea     rcx, [r8+28h]
0x14000f7f0  cmp     rcx, rbx
0x14000f7f3  jbe     short loc_14000F817
0x14000f7f5  test    r13b, r13b
0x14000f7f8  jnz     short loc_14000F806
0x14000f7fa  inc     r14d
0x14000f7fd  cmp     r14d, r12d
0x14000f800  jb      loc_14000F766
0x14000f806  xor     r13d, r13d
0x14000f809  test    r11, r11
0x14000f80c  jz      loc_14000F94D
0x14000f812  mov     cl, [r11]
0x14000f815  jmp     short loc_14000F846
0x14000f817  xor     r13d, r13d
0x14000f81a  cmp     [r8+rdx+0Ah], r13b
0x14000f81f  jbe     short loc_14000F828
0x14000f821  lea     r11, [rdx+18h]
0x14000f825  add     r11, r8
0x14000f828  mov     r9, [r8+rdx+10h]
0x14000f82d  jmp     short loc_14000F7B4
0x14000f82f  mov     cl, [rdx+48h]
0x14000f832  mov     r9, [rdx+20h]
0x14000f836  mov     r10b, [rdx+0Bh]
0x14000f83a  mov     r15b, [rdx+4]
0x14000f83e  test    eax, eax
0x14000f840  jnz     loc_14000F94D
0x14000f846  sub     cl, 8
0x14000f849  test    cl, 5Dh
0x14000f84c  jnz     loc_14000F94D
0x14000f852  mov     bl, [rdx+3]
0x14000f855  cmp     bl, 1
0x14000f858  jz      loc_14000F8F0
0x14000f85e  test    r9, r9
0x14000f861  jz      loc_14000F8F0
0x14000f867  test    r10b, r10b
0x14000f86a  jz      loc_14000F8F0
0x14000f870  mov     al, [r9]
0x14000f873  mov     dl, r13b
0x14000f876  and     al, 7Fh
0x14000f878  movzx   ecx, r10b
0x14000f87c  sub     al, 72h ; 'r'
0x14000f87e  add     rcx, r9
0x14000f881  cmp     al, 1
0x14000f883  mov     r11b, r13b
0x14000f886  lea     rax, [r9+8]
0x14000f88a  mov     r8b, r13b
0x14000f88d  jbe     short loc_14000F8D1
0x14000f88f  cmp     rax, rcx
0x14000f892  ja      short loc_14000F8E9
0x14000f894  movzx   ecx, byte ptr [r9+7]
0x14000f899  lea     r8, [r9+0Dh]
0x14000f89d  mov     dl, [r9+2]
0x14000f8a1  add     ecx, 8
0x14000f8a4  and     dl, 0Fh
0x14000f8a7  movzx   eax, r10b
0x14000f8ab  cmp     ecx, eax
0x14000f8ad  cmovbe  eax, ecx
0x14000f8b0  mov     ecx, eax
0x14000f8b2  add     rcx, r9
0x14000f8b5  cmp     r8, rcx
0x14000f8b8  ja      short loc_14000F8BE
0x14000f8ba  mov     r11b, [r9+0Ch]
0x14000f8be  lea     rax, [r9+0Eh]
0x14000f8c2  cmp     rax, rcx
0x14000f8c5  ja      short loc_14000F8CC
0x14000f8c7  mov     r8b, [r8]
0x14000f8ca  jmp     short loc_14000F8E5
0x14000f8cc  mov     r8b, r13b
0x14000f8cf  jmp     short loc_14000F8E5
0x14000f8d1  cmp     rax, rcx
0x14000f8d4  ja      short loc_14000F8E9
0x14000f8d6  mov     dl, [r9+1]
0x14000f8da  mov     r11b, [r9+2]
0x14000f8de  and     dl, 0Fh
0x14000f8e1  mov     r8b, [r9+3]
0x14000f8e5  mov     al, 1
0x14000f8e7  jmp     short loc_14000F8EC
0x14000f8e9  mov     al, r13b
0x14000f8ec  test    al, al
0x14000f8ee  jnz     short loc_14000F8F9
0x14000f8f0  mov     dl, r13b
0x14000f8f3  mov     r11b, r13b
0x14000f8f6  mov     r8b, r13b
0x14000f8f9  mov     eax, [rdi+30h]
0x14000f8fc  mov     r9, rdi
0x14000f8ff  mov     [rsp+0E0h+var_90], rdi
0x14000f904  mov     [rsp+0E0h+var_98], r8b
0x14000f909  lea     r8, [rbp+57h+var_50]
0x14000f90d  mov     [rsp+0E0h+var_A0], r11b
0x14000f912  mov     [rsp+0E0h+var_A8], dl
0x14000f916  mov     [rsp+0E0h+var_B0], r15b
0x14000f91b  mov     byte ptr [rsp+0E0h+var_B8], bl
0x14000f91f  mov     dword ptr [rsp+0E0h+var_C0], eax
0x14000f923  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x14000f928  jmp     short loc_14000F94D
  ... truncated ...
```
