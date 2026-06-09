# RaidUnitCompleteIrpRequest

- ea: `0x14001edc0`
- end: `0x14001f298`
- name: `RaidUnitCompleteIrpRequest`
- size: `1240`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `5`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140003fc0`
- `0x140031670`
- `0x1400531d0`
- `0x140054460`
- `0x140058bd0`

## callees

- `0x1400016cc`
- `0x140003fc0`
- `0x140005c50`
- `0x140012590`
- `0x14001caf0`
- `0x14001edc0`
- `0x14001f2a0`
- `0x140021bf0`
- `0x140068798`
- `0x14006d1c0`
- `0x1400bd4bc`
- `0x1400bd588`
- `0x1400d139c`
- `0x1400d1608`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x14001f03b`
- `ntoskrnl!PoFxIdleComponent` at `0x14001f03b`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14014e002`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14014e002`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f14d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f14d`
- `ntoskrnl!KeSetEvent` at `0x14001f114`
- `ntoskrnl!KeSetEvent` at `0x14001f114`
- `ntoskrnl!IofCompleteRequest` at `0x14001eea2`
- `ntoskrnl!IofCompleteRequest` at `0x14001eea2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001f04e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001f04e`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14014e064`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14014e064`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x14001f0cc`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x14014e086`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x14001f0cc`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x14014e086`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014e0c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014e0c4`

## pseudocode

```c
__int64 __fastcall RaidUnitCompleteIrpRequest(PIRP Irp, unsigned int a2, __int64 a3, __int64 a4)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  __int64 v5; // rbx
  __int64 DeviceExtension; // rdi
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned __int64 v10; // r8
  signed __int32 v11; // eax
  signed __int32 v12; // ett
  __int64 result; // rax
  unsigned __int8 MajorFunction; // al
  char v15; // al
  char v16; // bl
  __int64 v17; // rsi
  unsigned __int8 v18; // bl
  unsigned __int64 v19; // r8
  signed __int32 v20; // eax
  signed __int32 v21; // ett
  __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 v24; // rcx
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 *v27; // rcx
  __int64 *v28; // r8
  __int64 v29; // rax
  __int64 v30; // r8
  int v31; // edx
  __int64 *v32; // rax
  int v33; // r9d
  unsigned int Length; // r15d
  int Status; // edx
  int v36; // ecx
  __int64 v37; // r15
  KIRQL v38; // r9
  __int64 v39; // [rsp+60h] [rbp-9h] BYREF
  __int64 *v40; // [rsp+68h] [rbp-1h]
  unsigned __int64 QpcTimeStamp; // [rsp+70h] [rbp+7h] BYREF
  _QWORD v42[2]; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v43; // [rsp+88h] [rbp+1Fh] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v40 = &v39;
  v39 = (__int64)&v39;
  v5 = a2;
  v42[0] = 0;
  QpcTimeStamp = 0;
  DeviceExtension = (__int64)CurrentStackLocation->DeviceObject->DeviceExtension;
  if ( StorEtwLoggingEnabled )
  {
    if ( (byte_140177431 & 1) != 0 )
      StorEtwIOIrpRequestServiceTimeEventData(Irp, 0, 0, a4);
    if ( *(_DWORD *)(DeviceExtension + 1940) && (byte_140177433 & 2) != 0 )
      StorEtwLogoIrpRequestServiceTimeEventData(Irp, 0, 0, a4);
    if ( (unsigned __int8)(CurrentStackLocation->MajorFunction - 3) <= 1u && byte_140177431 < 0 )
    {
      v43 = 0;
      IoGetActivityIdIrp(Irp, &v43);
      if ( byte_140177431 < 0 )
      {
        Status = Irp->IoStatus.Status;
        v36 = Status >> 31;
        LOBYTE(v36) = ((Status >> 31) & 3) + 1;
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v36,
          Status,
          (unsigned int)&v43,
          (_DWORD)Irp,
          Status,
          v36,
          (Status >> 31) & 2,
          0,
          0,
          0,
          (char)Irp);
      }
    }
  }
  if ( *(_DWORD *)(DeviceExtension + 2372) )
  {
    MajorFunction = CurrentStackLocation->MajorFunction;
    if ( CurrentStackLocation->MajorFunction == 4 )
    {
      v15 = 42;
    }
    else if ( MajorFunction == 3 )
    {
      v15 = 40;
    }
    else if ( MajorFunction == 9 )
    {
      v15 = 53;
    }
    else
    {
      v15 = 0;
    }
    StorpTelemetryCollectPerfData(0, 0, DeviceExtension, (_DWORD)Irp, v15);
  }
  if ( g_StorpTraceLoggingErrorDataEnabled && Irp->IoStatus.Status < 0 )
    StorpTelemetryCollectErrorData(DeviceExtension, Irp, 0, 0);
  if ( (*(_BYTE *)(DeviceExtension + 506) & 2) != 0 )
  {
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = -1073740534;
    _InterlockedIncrement64((volatile signed __int64 *)(DeviceExtension + 2232));
  }
  if ( *(_DWORD *)(*(_QWORD *)(DeviceExtension + 32) + 12LL) )
  {
    QpcTimeStamp = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
    v37 = _InterlockedExchange64((volatile __int64 *)(*(_QWORD *)(DeviceExtension + 32) + 16LL), QpcTimeStamp);
    if ( (int)IoGetIoAttributionHandle(Irp, v42) >= 0 )
      RaUnitAttributedIoComplete(DeviceExtension, (_DWORD)Irp, v42[0], QpcTimeStamp, v37);
  }
  if ( (qword_140176450 & 0x2000) != 0 )
  {
    v33 = Irp->IoStatus.Status;
    QpcTimeStamp = 0;
    DbgLogRequest(*(_QWORD *)(DeviceExtension + 24), 50, (_DWORD)Irp, v33, CurrentStackLocation->MajorFunction, 0, 0);
  }
  if ( (int)v5 < 0 )
  {
    if ( CurrentStackLocation->MajorFunction == 3 || (Length = 0, CurrentStackLocation->MajorFunction == 4) )
      Length = CurrentStackLocation->Parameters.Read.Length;
    v38 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(DeviceExtension + 32) + 24LL));
    --*(_DWORD *)(*(_QWORD *)(DeviceExtension + 32) + 4LL);
    *(_DWORD *)(*(_QWORD *)(DeviceExtension + 32) + 8LL) -= Length;
    while ( 1 )
    {
      v26 = *(_QWORD *)(DeviceExtension + 32);
      v27 = *(__int64 **)(v26 + 48);
      v28 = (__int64 *)(v26 + 48);
      if ( v27 == (__int64 *)(v26 + 48) || *(int *)(v26 + 4) >= 8 || *(int *)(v26 + 8) >= 0x40000 )
        break;
      if ( (__int64 *)v27[1] != v28 )
        goto LABEL_21;
      v29 = *v27;
      if ( *(__int64 **)(*v27 + 8) != v27 )
        goto LABEL_21;
      *v28 = v29;
      *(_QWORD *)(v29 + 8) = v28;
      v30 = v27[2];
      if ( *(_BYTE *)v30 == 3 || (v31 = 0, *(_BYTE *)v30 == 4) )
        v31 = *(_DWORD *)(v30 + 8);
      ++*(_DWORD *)(*(_QWORD *)(DeviceExtension + 32) + 4LL);
      *(_DWORD *)(*(_QWORD *)(DeviceExtension + 32) + 8LL) += v31;
      v32 = v40;
      if ( (__int64 *)*v40 != &v39 )
LABEL_21:
        __fastfail(3u);
      v27[1] = (__int64)v40;
      *v27 = (__int64)&v39;
      *v32 = (__int64)v27;
      v40 = v27;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v26 + 24), v38);
  }
  IofCompleteRequest(Irp, 0);
  if ( (*(_DWORD *)(*(_QWORD *)(DeviceExtension + 32) + 80LL) & 1) != 0 )
  {
    LODWORD(v5) = v5 & 0x7FFFFFFF;
    if ( _InterlockedExchangeAdd(
           (volatile signed __int32 *)((v5 << 6) + *(_QWORD *)(DeviceExtension + 40) + 4),
           0xFFFFFFFE) == 2
      && _InterlockedExchangeAdd(*(volatile signed __int32 **)(DeviceExtension + 32), 0xFFFFFFFC) == 4 )
    {
      v8 = *(_DWORD *)(*(_QWORD *)(DeviceExtension + 32) + 80LL) >> 1;
      LOBYTE(v8) = (*(_DWORD *)(*(_QWORD *)(DeviceExtension + 32) + 80LL) & 2) != 0;
      v16 = (*(_DWORD *)(*(_QWORD *)(DeviceExtension + 32) + 80LL) >> 1) & 2;
      if ( !_InterlockedCompareExchange(*(volatile signed __int32 **)(DeviceExtension + 32), 1, 0) )
      {
        v17 = *(_QWORD *)(DeviceExtension + 24);
        v18 = v8 | v16;
        if ( (v18 & 1) != 0 && (unsigned __int8)RaidUnitCheckAndAcquirePoFx(DeviceExtension) )
        {
          PoFxIdleComponent(**(_QWORD **)(DeviceExtension + 1872), 0, 0);
          ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(DeviceExtension + 1864));
        }
        if ( v18 >= 2u && *(_QWORD *)(v17 + 5024) )
          RaidAdapterPoFxIdleComponent(v17, 0, 0, v9);
        v19 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
        v20 = *(_DWORD *)(v19 + *(_QWORD *)(DeviceExtension + 40));
        while ( (v20 & 1) == 0 )
        {
          v8 = (unsigned int)(v20 - 2);
          v21 = v20;
          v20 = _InterlockedCompareExchange(
                  (volatile signed __int32 *)(v19 + *(_QWORD *)(DeviceExtension + 40)),
                  v8,
                  v20);
          if ( v21 == v20 )
            goto LABEL_18;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(DeviceExtension + 1032), 0xFFFFFFFF) == 1 )
          KeSetEvent((PRKEVENT)(DeviceExtension + 520), 0, 0);
      }
    }
  }
  else
  {
    v10 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
    v11 = *(_DWORD *)(v10 + *(_QWORD *)(DeviceExtension + 40) + 4);
    while ( (v11 & 1) == 0 )
    {
      v8 = (unsigned int)(v11 - 2);
      v12 = v11;
      v11 = _InterlockedCompareExchange(
              (volatile signed __int32 *)(v10 + *(_QWORD *)(DeviceExtension + 40) + 4),
              v8,
              v11);
      if ( v12 == v11 )
        goto LABEL_18;
    }
    _InterlockedAdd(*(volatile signed __int32 **)(DeviceExtension + 32), 0xFFFFFFFC);
  }
LABEL_18:
  if ( (*(_DWORD *)(*(_QWORD *)(DeviceExtension + 32) + 80LL) & 0x100) != 0
    && !(unsigned __int8)RaUnitCheckForwardIoOutstanding(DeviceExtension, v8) )
  {
    RaidStartNextIoPacket(DeviceExtension, 0, 1);
  }
  while ( 1 )
  {
    result = v39;
    if ( (__int64 *)v39 == &v39 )
      return result;
    if ( *(__int64 **)(v39 + 8) != &v39 )
      goto LABEL_21;
    v22 = *(_QWORD *)v39;
    if ( *(_QWORD *)(*(_QWORD *)v39 + 8LL) != v39 )
      goto LABEL_21;
    v39 = *(_QWORD *)v39;
    *(_QWORD *)(v22 + 8) = &v39;
    v23 = result - 168;
    if ( (int)IoGetIoAttributionHandle(result - 168, v42) >= 0 )
      RaUnitAttributedIoDequeued(v24, v23, v42[0]);
    RaidUnitSubmitIrpRequest(DeviceExtension, v23, 1, v25);
  }
}

```

## disassembly

```asm
0x14001edc0  mov     [rsp-8+arg_18], rbx
0x14001edc5  push    rbp
0x14001edc6  push    rsi
0x14001edc7  push    rdi
0x14001edc8  push    r12
0x14001edca  push    r14
0x14001edcc  lea     rbp, [rsp-37h]
0x14001edd1  sub     rsp, 0A0h
0x14001edd8  mov     rax, cs:__security_cookie
0x14001eddf  xor     rax, rsp
0x14001ede2  mov     [rbp+57h+var_28], rax
0x14001ede6  mov     rsi, [rcx+0B8h]
0x14001eded  lea     rax, [rbp+57h+var_60]
0x14001edf1  mov     [rbp+57h+var_58], rax
0x14001edf5  xor     r12d, r12d
0x14001edf8  cmp     cs:StorEtwLoggingEnabled, r12b
0x14001edff  lea     rax, [rbp+57h+var_60]
0x14001ee03  mov     [rbp+57h+var_60], rax
0x14001ee07  mov     ebx, edx
0x14001ee09  mov     [rbp+57h+var_48], r12
0x14001ee0d  mov     r14, rcx
0x14001ee10  mov     [rbp+57h+QpcTimeStamp], r12
0x14001ee14  mov     rax, [rsi+28h]
0x14001ee18  mov     rdi, [rax+40h]
0x14001ee1c  jz      short loc_14001EE45
0x14001ee1e  test    cs:byte_140177431, 1
0x14001ee25  jnz     loc_14001F1CD
0x14001ee2b  cmp     [rdi+794h], r12d
0x14001ee32  jnz     loc_14001F1DC
0x14001ee38  movzx   eax, byte ptr [rsi]
0x14001ee3b  sub     al, 3
0x14001ee3d  cmp     al, 1
0x14001ee3f  jbe     loc_14001EF99
0x14001ee45  cmp     [rdi+944h], r12d
0x14001ee4c  jnz     loc_14001EF78
0x14001ee52  cmp     cs:g_StorpTraceLoggingErrorDataEnabled, r12d
0x14001ee59  jnz     loc_14001EF58
0x14001ee5f  test    byte ptr [rdi+1FAh], 2
0x14001ee66  jnz     loc_14001F202
0x14001ee6c  mov     rax, [rdi+20h]
0x14001ee70  mov     [rsp+0C0h+arg_10], r15
0x14001ee78  mov     ecx, [rax+0Ch]
0x14001ee7b  test    ecx, ecx
0x14001ee7d  jnz     loc_14014E060
0x14001ee83  mov     rax, cs:qword_140176450
0x14001ee8a  bt      rax, 0Dh
0x14001ee8f  jb      loc_14001F21B
0x14001ee95  test    ebx, ebx
0x14001ee97  js      loc_14001F24E
0x14001ee9d  xor     edx, edx; PriorityBoost
0x14001ee9f  mov     rcx, r14; Irp
0x14001eea2  call    cs:__imp_IofCompleteRequest
0x14001eea9  nop     dword ptr [rax+rax+00h]
0x14001eeae  mov     rax, [rdi+20h]
0x14001eeb2  mov     r14d, 1
0x14001eeb8  mov     ecx, [rax+50h]
0x14001eebb  test    r14b, cl
0x14001eebe  jnz     loc_14001EFBF
0x14001eec4  mov     eax, gs:1A4h
0x14001eecc  mov     r8d, eax
0x14001eecf  mov     rax, [rdi+28h]
0x14001eed3  shl     r8, 6
0x14001eed7  mov     eax, [r8+rax+4]
0x14001eedc  nop     dword ptr [rax+00h]
0x14001eee0  test    r14b, al
0x14001eee3  jnz     loc_14001F269
0x14001eee9  mov     rcx, [rdi+28h]
0x14001eeed  lea     edx, [rax-2]
0x14001eef0  lock cmpxchg [r8+rcx+4], edx
0x14001eef7  jnz     short loc_14001EEE0
0x14001eef9  mov     rax, [rdi+20h]
0x14001eefd  test    dword ptr [rax+50h], 100h
0x14001ef04  jnz     loc_14001F276
0x14001ef0a  mov     rax, [rbp+57h+var_60]
0x14001ef0e  lea     rcx, [rbp+57h+var_60]
0x14001ef12  cmp     rax, rcx
0x14001ef15  jz      short loc_14001EF2C
0x14001ef17  lea     rcx, [rbp+57h+var_60]
0x14001ef1b  cmp     [rax+8], rcx
0x14001ef1f  jz      loc_14001F0A5
0x14001ef25  mov     ecx, 3
0x14001ef2a  int     29h; Win8: RtlFailFast(ecx)
0x14001ef2c  mov     r15, [rsp+0C0h+arg_10]
0x14001ef34  mov     rcx, [rbp+57h+var_28]
0x14001ef38  xor     rcx, rsp; StackCookie
0x14001ef3b  call    __security_check_cookie
0x14001ef40  mov     rbx, [rsp+0C0h+arg_18]
0x14001ef48  add     rsp, 0A0h
0x14001ef4f  pop     r14
0x14001ef51  pop     r12
0x14001ef53  pop     rdi
0x14001ef54  pop     rsi
0x14001ef55  pop     rbp
0x14001ef56  retn
0x14001ef58  cmp     [r14+30h], r12d
0x14001ef5c  jge     loc_14001EE5F
0x14001ef62  xor     r9d, r9d
0x14001ef65  xor     r8d, r8d
0x14001ef68  mov     rdx, r14
0x14001ef6b  mov     rcx, rdi
0x14001ef6e  call    StorpTelemetryCollectErrorData
0x14001ef73  jmp     loc_14001EE5F
0x14001ef78  movzx   eax, byte ptr [rsi]
0x14001ef7b  cmp     al, 4
0x14001ef7d  jnz     short loc_14001EFAB
0x14001ef7f  mov     al, 2Ah ; '*'
0x14001ef81  mov     r9, r14
0x14001ef84  mov     byte ptr [rsp+0C0h+var_A0], al
0x14001ef88  mov     r8, rdi
0x14001ef8b  xor     edx, edx
0x14001ef8d  xor     ecx, ecx
0x14001ef8f  call    StorpTelemetryCollectPerfData
0x14001ef94  jmp     loc_14001EE52
0x14001ef99  cmp     cs:byte_140177431, r12b
0x14001efa0  jge     loc_14001EE45
0x14001efa6  jmp     loc_14014DFF4
0x14001efab  cmp     al, 3
0x14001efad  jnz     short loc_14001EFB3
0x14001efaf  mov     al, 28h ; '('
0x14001efb1  jmp     short loc_14001EF81
0x14001efb3  cmp     al, 9
0x14001efb5  jz      loc_14001F1FB
0x14001efbb  xor     al, al
0x14001efbd  jmp     short loc_14001EF81
0x14001efbf  mov     rax, [rdi+28h]
0x14001efc3  btr     ebx, 1Fh
0x14001efc7  shl     rbx, 6
0x14001efcb  mov     ecx, 0FFFFFFFEh
0x14001efd0  lock xadd [rbx+rax+4], ecx
0x14001efd6  cmp     ecx, 2
0x14001efd9  jnz     loc_14001EEF9
0x14001efdf  mov     rax, [rdi+20h]
0x14001efe3  mov     ecx, 0FFFFFFFCh
0x14001efe8  lock xadd [rax], ecx
0x14001efec  cmp     ecx, 4
0x14001efef  jnz     loc_14001EEF9
0x14001eff5  mov     rcx, [rdi+20h]
0x14001eff9  mov     ebx, [rcx+50h]
0x14001effc  mov     edx, ebx
0x14001effe  shr     edx, 1
0x14001f000  shr     ebx, 1
0x14001f002  and     dl, r14b
0x14001f005  and     bl, 2
0x14001f008  xor     eax, eax
0x14001f00a  lock cmpxchg [rcx], r14d
0x14001f00f  jnz     loc_14001EEF9
0x14001f015  mov     rsi, [rdi+18h]
0x14001f019  or      bl, dl
0x14001f01b  test    r14b, bl
0x14001f01e  jz      short loc_14001F05A
0x14001f020  mov     rcx, rdi
0x14001f023  call    RaidUnitCheckAndAcquirePoFx
0x14001f028  test    al, al
0x14001f02a  jz      short loc_14001F05A
0x14001f02c  mov     rcx, [rdi+750h]
0x14001f033  xor     r8d, r8d
0x14001f036  xor     edx, edx
0x14001f038  mov     rcx, [rcx]
0x14001f03b  call    cs:__imp_PoFxIdleComponent
0x14001f042  nop     dword ptr [rax+rax+00h]
0x14001f047  mov     rcx, [rdi+748h]; RunRefCacheAware
0x14001f04e  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14001f055  nop     dword ptr [rax+rax+00h]
0x14001f05a  cmp     bl, 2
0x14001f05d  jb      short loc_14001F075
0x14001f05f  cmp     [rsi+13A0h], r12
0x14001f066  jz      short loc_14001F075
0x14001f068  xor     r8d, r8d
0x14001f06b  xor     edx, edx
0x14001f06d  mov     rcx, rsi
0x14001f070  call    RaidAdapterPoFxIdleComponent
0x14001f075  mov     eax, gs:1A4h
0x14001f07d  mov     r8d, eax
0x14001f080  mov     rax, [rdi+28h]
0x14001f084  shl     r8, 6
0x14001f088  mov     eax, [r8+rax]
0x14001f08c  test    r14b, al
0x14001f08f  jnz     short loc_14001F0F2
0x14001f091  mov     rcx, [rdi+28h]
0x14001f095  lea     edx, [rax-2]
0x14001f098  lock cmpxchg [r8+rcx], edx
0x14001f09e  jnz     short loc_14001F08C
0x14001f0a0  jmp     loc_14001EEF9
0x14001f0a5  mov     rcx, [rax]
0x14001f0a8  cmp     [rcx+8], rax
0x14001f0ac  jnz     loc_14001EF25
0x14001f0b2  mov     [rbp+57h+var_60], rcx
0x14001f0b6  lea     rdx, [rbp+57h+var_60]
0x14001f0ba  mov     [rcx+8], rdx
0x14001f0be  lea     rbx, [rax-0A8h]
0x14001f0c5  lea     rdx, [rbp+57h+var_48]
0x14001f0c9  mov     rcx, rbx
0x14001f0cc  call    cs:__imp_IoGetIoAttributionHandle
0x14001f0d3  nop     dword ptr [rax+rax+00h]
0x14001f0d8  test    eax, eax
0x14001f0da  js      loc_14014E0F1
0x14001f0e0  mov     r8, [rbp+57h+var_48]
0x14001f0e4  mov     rdx, rbx
0x14001f0e7  call    RaUnitAttributedIoDequeued
0x14001f0ec  nop
0x14001f0ed  jmp     loc_14014E0F1
0x14001f0f2  mov     eax, 0FFFFFFFFh
0x14001f0f7  lock xadd [rdi+408h], eax
0x14001f0ff  cmp     eax, r14d
0x14001f102  jnz     loc_14001EEF9
0x14001f108  lea     rcx, [rdi+208h]; Event
0x14001f10f  xor     r8d, r8d; Wait
0x14001f112  xor     edx, edx; Increment
0x14001f114  call    cs:__imp_KeSetEvent
0x14001f11b  nop     dword ptr [rax+rax+00h]
0x14001f120  jmp     loc_14001EEF9
0x14001f125  mov     rdx, [rdi+20h]
0x14001f129  mov     rcx, [rdx+30h]
0x14001f12d  lea     r8, [rdx+30h]
0x14001f131  cmp     rcx, r8
0x14001f134  jz      short loc_14001F145
0x14001f136  cmp     dword ptr [rdx+4], 8
0x14001f13a  jge     short loc_14001F145
0x14001f13c  cmp     dword ptr [rdx+8], 40000h
0x14001f143  jl      short loc_14001F15E
0x14001f145  lea     rcx, [rdx+18h]; SpinLock
0x14001f149  movzx   edx, r9b; NewIrql
0x14001f14d  call    cs:__imp_KeReleaseSpinLock
0x14001f154  nop     dword ptr [rax+rax+00h]
0x14001f159  jmp     loc_14001EE9D
0x14001f15e  cmp     [rcx+8], r8
0x14001f162  jnz     loc_14001EF25
0x14001f168  mov     rax, [rcx]
0x14001f16b  cmp     [rax+8], rcx
0x14001f16f  jnz     loc_14001EF25
0x14001f175  mov     [r8], rax
0x14001f178  mov     [rax+8], r8
0x14001f17c  mov     r8, [rcx+10h]
0x14001f180  movzx   eax, byte ptr [r8]
0x14001f184  cmp     al, 3
0x14001f186  jz      loc_14014E0E8
0x14001f18c  mov     edx, r12d
0x14001f18f  cmp     al, 4
0x14001f191  jz      loc_14014E0E8
0x14001f197  mov     rax, [rdi+20h]
0x14001f19b  inc     dword ptr [rax+4]
0x14001f19e  mov     rax, [rdi+20h]
0x14001f1a2  add     [rax+8], edx
0x14001f1a5  lea     rdx, [rbp+57h+var_60]
0x14001f1a9  mov     rax, [rbp+57h+var_58]
0x14001f1ad  cmp     [rax], rdx
0x14001f1b0  jnz     loc_14001EF25
0x14001f1b6  mov     [rcx+8], rax
0x14001f1ba  lea     rdx, [rbp+57h+var_60]
0x14001f1be  mov     [rcx], rdx
0x14001f1c1  mov     [rax], rcx
0x14001f1c4  mov     [rbp+57h+var_58], rcx
0x14001f1c8  jmp     loc_14001F125
0x14001f1cd  xor     r8d, r8d
0x14001f1d0  xor     edx, edx
0x14001f1d2  call    StorEtwIOIrpRequestServiceTimeEventData
0x14001f1d7  jmp     loc_14001EE2B
0x14001f1dc  test    cs:byte_140177433, 2
0x14001f1e3  jz      loc_14001EE38
0x14001f1e9  xor     r8d, r8d
0x14001f1ec  xor     edx, edx
0x14001f1ee  mov     rcx, r14
0x14001f1f1  call    StorEtwLogoIrpRequestServiceTimeEventData
0x14001f1f6  jmp     loc_14001EE38
0x14001f1fb  mov     al, 35h ; '5'
0x14001f1fd  jmp     loc_14001EF81
0x14001f202  mov     [r14+38h], r12
0x14001f206  mov     dword ptr [r14+30h], 0C000050Ah
0x14001f20e  lock inc qword ptr [rdi+8B8h]
0x14001f216  jmp     loc_14001EE6C
0x14001f21b  movsxd  r9, dword ptr [r14+30h]
0x14001f21f  mov     rax, r12
0x14001f222  mov     [rbp+57h+QpcTimeStamp], rax
0x14001f226  mov     r8, r14
0x14001f229  movzx   ecx, byte ptr [rsi]
0x14001f22c  mov     edx, 32h ; '2'
0x14001f231  mov     [rsp+0C0h+var_90], rax
0x14001f236  mov     [rsp+0C0h+var_98], r12
0x14001f23b  mov     [rsp+0C0h+var_A0], rcx
0x14001f240  mov     rcx, [rdi+18h]
0x14001f244  call    DbgLogRequest
0x14001f249  jmp     loc_14001EE95
0x14001f24e  movzx   eax, byte ptr [rsi]
0x14001f251  cmp     al, 3
0x14001f253  jz      loc_14014E0B8
0x14001f259  mov     r15d, r12d
0x14001f25c  cmp     al, 4
0x14001f25e  jz      loc_14014E0B8
0x14001f264  jmp     loc_14014E0BC
0x14001f269  mov     rax, [rdi+20h]
0x14001f26d  lock add dword ptr [rax], 0FFFFFFFCh
0x14001f271  jmp     loc_14001EEF9
0x14001f276  mov     rcx, rdi
0x14001f279  call    RaUnitCheckForwardIoOutstanding
0x14001f27e  test    al, al
0x14001f280  jnz     loc_14001EF0A
0x14001f286  mov     r8d, r14d
0x14001f289  xor     edx, edx
0x14001f28b  mov     rcx, rdi
0x14001f28e  call    RaidStartNextIoPacket
  ... truncated ...
```
