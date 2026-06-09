# PgmConnect

- ea: `0x140005e3c`
- end: `0x1400067ee`
- name: `PgmConnect`
- size: `2482`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007d90`

## callees

- `0x140001030`
- `0x1400023b8`
- `0x140004dc0`
- `0x140005068`
- `0x1400052e4`
- `0x1400054d0`
- `0x140005e3c`
- `0x1400067f4`
- `0x140006dbc`
- `0x140006e34`
- `0x1400091f8`
- `0x14000948c`
- `0x14001bcec`
- `0x140036d5c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140006359`
- `ntoskrnl!KeInitializeEvent` at `0x140006359`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400066d6`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000670c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400066d6`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14000670c`
- `ntoskrnl!ExAllocatePool2` at `0x14000616b`
- `ntoskrnl!ExAllocatePool2` at `0x14000616b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f49`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f73`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f90`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000605c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400060a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006235`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000633d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006695`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006796`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f49`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f73`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f90`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000605c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400060a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006235`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000633d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006695`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006796`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005edb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005f35`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005f5f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006008`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000607d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006479`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005edb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005f35`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005f5f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006008`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000607d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006479`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006210`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006426`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006210`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006426`

## pseudocode

```c
__int64 __fastcall PgmConnect(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  unsigned int v5; // edx
  _DWORD *v6; // rcx
  __int64 v7; // rdi
  __int64 v9; // rsi
  KIRQL v10; // r15
  int FECContext; // r14d
  KIRQL v12; // al
  KIRQL v13; // al
  int v14; // eax
  struct _DEVICE_OBJECT *v15; // rbx
  unsigned int v16; // r12d
  struct _DEVICE_OBJECT *NextDevice; // rcx
  unsigned int v18; // r12d
  __int16 v19; // cx
  __int64 v20; // rax
  __int64 Pool2; // rax
  int v22; // ecx
  void *v23; // rcx
  __int16 v24; // cx
  _QWORD *v25; // rax
  _QWORD *v26; // rax
  _QWORD *v27; // rax
  __int64 v28; // r8
  KIRQL v29; // al
  unsigned __int64 v30; // rdx
  KIRQL v31; // r10
  __int64 v32; // r9
  unsigned __int64 v33; // r8
  __int64 v34; // rax
  unsigned __int64 v35; // kr00_8
  unsigned __int64 v36; // r8
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // r8
  __int64 v40; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v41; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v42; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v43; // [rsp+B8h] [rbp+58h]

  v41 = a2;
  v40 = a1;
  v3 = *(_QWORD *)(a3 + 16);
  v42 = 0;
  LOWORD(v41) = 0;
  v4 = *(_QWORD *)(a3 + 48);
  v5 = *(_DWORD *)(v3 + 32);
  v6 = *(_DWORD **)(v3 + 40);
  LODWORD(v40) = 1172;
  v7 = *(_QWORD *)(v4 + 24);
  v43 = v7;
  if ( !GetIpAddress(v6, v5, &v42, &v41) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids, v7);
    return 3221225991LL;
  }
  v9 = 0;
  v10 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( v7
    && *(_DWORD *)(v7 + 16) == 1397966163
    && (v9 = *(_QWORD *)(v7 + 24)) != 0
    && *(_DWORD *)(v9 + 16) == 1380205633
    && (*(_DWORD *)(v9 + 56) & 1) == 0 )
  {
    FECContext = -1073741670;
    v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 424));
    ++*(_DWORD *)(v9 + 20);
    KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 424), v12);
    v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 360));
    ++*(_DWORD *)(v7 + 20);
    KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 360), v13);
    if ( (*(_DWORD *)(v9 + 56) & 0x10) == 0 )
    {
      KeReleaseSpinLock(&SpinLock, v10);
      v14 = PgmSetTcpInfo(*(_QWORD *)(v9 + 88), 5, &v40);
      FECContext = v14;
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            22,
            WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids,
            (unsigned int)v14);
LABEL_16:
        PgmDereferenceSessionCommon(v7);
        PgmDereferenceAddress((KSPIN_LOCK *)v9);
        return (unsigned int)FECContext;
      }
      v10 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    }
    if ( !*(_DWORD *)(v9 + 240) )
    {
      FECContext = -1073741255;
      v15 = (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.32;
      v16 = 0;
      do
      {
        v15 = *(struct _DEVICE_OBJECT **)&v15->Type;
        if ( v15 == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy )
          break;
        NextDevice = v15->NextDevice;
        if ( NextDevice != (struct _DEVICE_OBJECT *)&v15->NextDevice )
        {
          v16 = _byteswap_ulong((unsigned int)NextDevice->NextDevice);
          KeReleaseSpinLock(&SpinLock, v10);
          FECContext = SetSenderMCastOutIf(v9, v16);
          v10 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
        }
      }
      while ( !v16 );
      v7 = v43;
      if ( FECContext < 0 )
      {
        KeReleaseSpinLock(&SpinLock, v10);
        PgmDereferenceSessionCommon(v7);
        PgmDereferenceAddress((KSPIN_LOCK *)v9);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids, v16);
        return 3221225473LL;
      }
    }
    v18 = v42;
    *(_DWORD *)(*(_QWORD *)(v7 + 40) + 40LL) = _byteswap_ulong(v42);
    v19 = __ROR2__(v41, 8);
    *(_WORD *)(v9 + 238) = v19;
    *(_WORD *)(*(_QWORD *)(v7 + 40) + 48LL) = v19;
    *(_DWORD *)(*(_QWORD *)(v7 + 40) + 44LL) = *(_DWORD *)(v9 + 240);
    *(_WORD *)(v7 + 156) = *(_WORD *)(v9 + 300);
    v20 = *(unsigned __int8 *)(v9 + 304);
    *(_BYTE *)(v7 + 160) = v20;
    if ( *(_BYTE *)(v9 + 305) )
    {
      Pool2 = ExAllocatePool2(64, 8 * v20 + 16, 812476240);
      *(_QWORD *)(*(_QWORD *)(v7 + 40) + 424LL) = Pool2;
      if ( !Pool2
        || (FECContext = CreateFECContext(v7 + 112, *(unsigned __int8 *)(v7 + 160), *(unsigned __int16 *)(v7 + 156), 0),
            FECContext < 0) )
      {
        v23 = *(void **)(*(_QWORD *)(v7 + 40) + 424LL);
        if ( v23 )
        {
          ExFreePoolWithTag(v23, 0);
          *(_QWORD *)(*(_QWORD *)(v7 + 40) + 424LL) = 0;
        }
        KeReleaseSpinLock(&SpinLock, v10);
        PgmDereferenceSessionCommon(v7);
        PgmDereferenceAddress((KSPIN_LOCK *)v9);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_DqDD(
            WPP_GLOBAL_Control->AttachedDevice,
            24,
            (unsigned __int16)v41,
            (unsigned int)FECContext,
            v7,
            v18,
            (unsigned __int16)v41);
        return 3221225626LL;
      }
      *(_BYTE *)(v7 + 161) = *(_BYTE *)(v9 + 305);
      *(_WORD *)(v7 + 158) = *(_WORD *)(v9 + 302);
      *(_DWORD *)(*(_QWORD *)(v7 + 40) + 196LL) |= 0x200u;
      *(_DWORD *)(*(_QWORD *)(v7 + 40) + 180LL) = -1;
      *(_DWORD *)(*(_QWORD *)(v7 + 40) + 108LL) = (*(_DWORD *)(v9 + 248) + 55) & 0xFFFFFFF8;
      v22 = *(_DWORD *)(v9 + 248) - 70;
    }
    else
    {
      *(_DWORD *)(*(_QWORD *)(v7 + 40) + 108LL) = (*(_DWORD *)(v9 + 248) + 39) & 0xFFFFFFF8;
      v22 = *(_DWORD *)(v9 + 248) - 56;
    }
    *(_DWORD *)(*(_QWORD *)(v7 + 40) + 112LL) = v22;
    *(_WORD *)(v7 + 70) = HIWORD(WPP_MAIN_CB.Dpc.DpcData);
    v24 = ++HIWORD(WPP_MAIN_CB.Dpc.DpcData);
    if ( *(_WORD *)(v7 + 70) == *(_WORD *)(v9 + 238) )
    {
      *(_WORD *)(v7 + 70) = v24;
      ++HIWORD(WPP_MAIN_CB.Dpc.DpcData);
    }
    v25 = (_QWORD *)(*(_QWORD *)(v7 + 40) + 248LL);
    v25[1] = v25;
    *v25 = v25;
    v26 = (_QWORD *)(*(_QWORD *)(v7 + 40) + 232LL);
    v26[1] = v26;
    *v26 = v26;
    v27 = (_QWORD *)(*(_QWORD *)(v7 + 40) + 216LL);
    v27[1] = v27;
    *v27 = v27;
    LODWORD(v40) = *(_DWORD *)(v9 + 256);
    KeReleaseSpinLock(&SpinLock, v10);
    KeInitializeEvent((PRKEVENT)(*(_QWORD *)(v7 + 40) + 704LL), SynchronizationEvent, 0);
    FECContext = PgmSetTcpInfo(*(_QWORD *)(v9 + 64), 2, &v40);
    if ( FECContext < 0 || (FECContext = PgmSetTcpInfo(*(_QWORD *)(v9 + 88), 2, &v40), FECContext < 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids,
          (unsigned int)FECContext);
      goto LABEL_48;
    }
    FECContext = PgmCreateDataFileAndMapSection(v9, v7);
    if ( FECContext < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_DqDD(
          WPP_GLOBAL_Control->AttachedDevice,
          25,
          v28,
          (unsigned int)FECContext,
          v7,
          v18,
          (unsigned __int16)v41);
LABEL_48:
      if ( *(_BYTE *)(v9 + 305) )
      {
        DestroyFECContext(v7 + 112);
        ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(v7 + 40) + 424LL), 0);
        *(_QWORD *)(*(_QWORD *)(v7 + 40) + 424LL) = 0;
      }
      goto LABEL_16;
    }
    v29 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v30 = *(_QWORD *)(v9 + 272);
    v31 = v29;
    v32 = *(_QWORD *)(v7 + 40);
    v33 = (20 * v30) >> 3;
    if ( v33 < *(unsigned int *)(v32 + 108) )
    {
      *(_QWORD *)(v32 + 304) = ((v30 >> 3) + *(unsigned int *)(v9 + 248) - 1LL) / v33;
      v34 = *(_QWORD *)(v7 + 40);
      if ( !*(_QWORD *)(v34 + 304) )
        *(_QWORD *)(v34 + 304) = 1;
    }
    else
    {
      *(_QWORD *)(v32 + 304) = 1;
    }
    *(_DWORD *)(*(_QWORD *)(v7 + 40) + 412LL) = (unsigned int)(20
                                                             * *(_DWORD *)(v9 + 272)
                                                             * *(_DWORD *)(*(_QWORD *)(v7 + 40) + 304LL)) >> 3;
    *(_DWORD *)(*(_QWORD *)(v7 + 40) + 416LL) = *(_DWORD *)(*(_QWORD *)(v7 + 40) + 412LL);
    *(_DWORD *)(*(_QWORD *)(v7 + 40) + 420LL) = *(_DWORD *)(*(_QWORD *)(v7 + 40) + 412LL) >> 8;
    *(_QWORD *)(*(_QWORD *)(v7 + 40) + 360LL) = *(_QWORD *)(*(_QWORD *)(v7 + 40) + 304LL);
    *(_DWORD *)(*(_QWORD *)(v7 + 40) + 408LL) = *(_DWORD *)(*(_QWORD *)(v7 + 40) + 412LL);
    *(_QWORD *)(*(_QWORD *)(v7 + 40) + 368LL) = 0;
    *(_QWORD *)(*(_QWORD *)(v7 + 40) + 376LL) = 25;
    *(_QWORD *)(*(_QWORD *)(v7 + 40) + 392LL) = 50;
    *(_QWORD *)(*(_QWORD *)(v7 + 40) + 400LL) = 750;
    *(_QWORD *)(*(_QWORD *)(v7 + 40) + 384LL) = *(_QWORD *)(*(_QWORD *)(v7 + 40) + 392LL);
    v35 = *(_QWORD *)(v9 + 288);
    v36 = v35 * *(unsigned int *)(v9 + 296) / 0x64;
    *(_QWORD *)(*(_QWORD *)(v7 + 40) + 328LL) = v35 / 0x14;
    *(_QWORD *)(*(_QWORD *)(v7 + 40) + 320LL) = v36 / 0x14;
    *(_QWORD *)(*(_QWORD *)(v7 + 40) + 344LL) = *(_QWORD *)(*(_QWORD *)(v7 + 40) + 320LL)
                                              + *(_QWORD *)(*(_QWORD *)(v7 + 40) + 328LL);
    *(_QWORD *)(*(_QWORD *)(v7 + 40) + 336LL) = 3;
    v37 = *(unsigned int *)(v9 + 252);
    if ( (_DWORD)v37 )
    {
      *(_DWORD *)(*(_QWORD *)(v7 + 40) + 176LL) = *(_QWORD *)(*(_QWORD *)(v7 + 40) + 96LL) * v37 / 0xC8uLL;
      *(_DWORD *)(*(_QWORD *)(v7 + 40) + 200LL) |= 8u;
      *(_DWORD *)(*(_QWORD *)(v7 + 40) + 204LL) += 8;
      *(_DWORD *)(*(_QWORD *)(v7 + 40) + 196LL) |= 8u;
    }
    v38 = *(_QWORD *)(v7 + 40);
    *(_DWORD *)(v7 + 32) |= 0x18u;
    *(_QWORD *)(v38 + 136) = 0;
    *(_QWORD *)(*(_QWORD *)(v7 + 40) + 128LL) = 0;
    KeReleaseSpinLock(&SpinLock, v31);
    ExInitializeNPagedLookasideList(
      (PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(v7 + 40) + 448LL),
      0,
      0,
      0x200u,
      *(unsigned int *)(*(_QWORD *)(v7 + 40) + 108LL),
      0x326D6750u,
      0x64u);
    ExInitializeNPagedLookasideList(
      (PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(v7 + 40) + 576LL),
      0,
      0,
      0x200u,
      0xA0u,
      0x326D6750u,
      0x64u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_qDdddddd(
        WPP_GLOBAL_Control->AttachedDevice,
        *(_QWORD *)(v7 + 40),
        v39,
        v7,
        v18,
        *(_DWORD *)(v9 + 272),
        *(_DWORD *)(v9 + 280),
        *(_DWORD *)(v9 + 288),
        *(_DWORD *)(*(_QWORD *)(v7 + 40) + 304LL),
        *(_DWORD *)(*(_QWORD *)(v7 + 40) + 412LL),
        *(_DWORD *)(*(_QWORD *)(v7 + 40) + 408LL));
    PgmDereferenceSessionCommon(v7);
    PgmDereferenceAddress((KSPIN_LOCK *)v9);
    return 0;
  }
  else
  {
    KeReleaseSpinLock(&SpinLock, v10);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids, v7, v9);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x140005e3c  mov     [rsp-38h+arg_8], rdx
0x140005e41  mov     [rsp-38h+arg_0], rcx
0x140005e46  push    rbp
0x140005e47  push    rbx
0x140005e48  push    rsi
0x140005e49  push    rdi
0x140005e4a  push    r12
0x140005e4c  push    r14
0x140005e4e  push    r15
0x140005e50  mov     rbp, rsp
0x140005e53  sub     rsp, 60h
0x140005e57  mov     rcx, [r8+10h]
0x140005e5b  lea     r9, [rbp+arg_8]
0x140005e5f  xor     eax, eax
0x140005e61  mov     [rbp+arg_10], 0
0x140005e68  mov     word ptr [rbp+arg_8], ax
0x140005e6c  mov     rax, [r8+30h]
0x140005e70  lea     r8, [rbp+arg_10]
0x140005e74  mov     edx, [rcx+20h]
0x140005e77  mov     rcx, [rcx+28h]
0x140005e7b  mov     dword ptr [rbp+arg_0], 494h
0x140005e82  mov     rdi, [rax+18h]
0x140005e86  mov     [rbp+arg_18], rdi
0x140005e8a  call    GetIpAddress
0x140005e8f  test    al, al
0x140005e91  jnz     short loc_140005ECF
0x140005e93  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e9a  lea     rbx, WPP_GLOBAL_Control
0x140005ea1  cmp     rcx, rbx
0x140005ea4  jz      short loc_140005EC5
0x140005ea6  mov     eax, [rcx+2Ch]
0x140005ea9  test    al, 2
0x140005eab  jz      short loc_140005EC5
0x140005ead  mov     rcx, [rcx+18h]
0x140005eb1  lea     r8, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids
0x140005eb8  mov     edx, 14h
0x140005ebd  mov     r9, rdi
0x140005ec0  call    WPP_SF_q
0x140005ec5  mov     eax, 0C0000207h
0x140005eca  jmp     loc_1400067DE
0x140005ecf  lea     r12, SpinLock
0x140005ed6  xor     esi, esi
0x140005ed8  mov     rcx, r12; SpinLock
0x140005edb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005ee2  nop     dword ptr [rax+rax+00h]
0x140005ee7  mov     r15b, al
0x140005eea  test    rdi, rdi
0x140005eed  jz      loc_140006790
0x140005ef3  cmp     dword ptr [rdi+10h], 53534553h
0x140005efa  jnz     loc_140006790
0x140005f00  mov     rsi, [rdi+18h]
0x140005f04  test    rsi, rsi
0x140005f07  jz      loc_140006790
0x140005f0d  cmp     dword ptr [rsi+10h], 52444441h
0x140005f14  jnz     loc_140006790
0x140005f1a  mov     eax, [rsi+38h]
0x140005f1d  test    al, 1
0x140005f1f  jnz     loc_140006790
0x140005f25  lea     rbx, [rsi+1A8h]
0x140005f2c  mov     r14d, 0C000009Ah
0x140005f32  mov     rcx, rbx; SpinLock
0x140005f35  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005f3c  nop     dword ptr [rax+rax+00h]
0x140005f41  inc     dword ptr [rsi+14h]
0x140005f44  mov     rcx, rbx; SpinLock
0x140005f47  mov     dl, al; NewIrql
0x140005f49  call    cs:__imp_KeReleaseSpinLock
0x140005f50  nop     dword ptr [rax+rax+00h]
0x140005f55  lea     rbx, [rdi+168h]
0x140005f5c  mov     rcx, rbx; SpinLock
0x140005f5f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005f66  nop     dword ptr [rax+rax+00h]
0x140005f6b  inc     dword ptr [rdi+14h]
0x140005f6e  mov     rcx, rbx; SpinLock
0x140005f71  mov     dl, al; NewIrql
0x140005f73  call    cs:__imp_KeReleaseSpinLock
0x140005f7a  nop     dword ptr [rax+rax+00h]
0x140005f7f  mov     eax, [rsi+38h]
0x140005f82  test    al, 10h
0x140005f84  jnz     loc_140006017
0x140005f8a  mov     dl, r15b; NewIrql
0x140005f8d  mov     rcx, r12; SpinLock
0x140005f90  call    cs:__imp_KeReleaseSpinLock
0x140005f97  nop     dword ptr [rax+rax+00h]
0x140005f9c  mov     rcx, [rsi+58h]
0x140005fa0  lea     r8, [rbp+arg_0]
0x140005fa4  mov     r9d, 4
0x140005faa  lea     edx, [r9+1]
0x140005fae  call    PgmSetTcpInfo
0x140005fb3  mov     r14d, eax
0x140005fb6  test    eax, eax
0x140005fb8  jns     short loc_140006005
0x140005fba  mov     rcx, cs:WPP_GLOBAL_Control
0x140005fc1  lea     rbx, WPP_GLOBAL_Control
0x140005fc8  cmp     rcx, rbx
0x140005fcb  jz      short loc_140005FED
0x140005fcd  mov     edx, [rcx+2Ch]
0x140005fd0  test    dl, 2
0x140005fd3  jz      short loc_140005FED
0x140005fd5  mov     rcx, [rcx+18h]
0x140005fd9  lea     r8, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids
0x140005fe0  mov     edx, 16h
0x140005fe5  mov     r9d, eax
0x140005fe8  call    WPP_SF_d
0x140005fed  mov     rcx, rdi
0x140005ff0  call    PgmDereferenceSessionCommon
0x140005ff5  mov     rcx, rsi; P
0x140005ff8  call    PgmDereferenceAddress
0x140005ffd  mov     eax, r14d
0x140006000  jmp     loc_1400067DE
0x140006005  mov     rcx, r12; SpinLock
0x140006008  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000600f  nop     dword ptr [rax+rax+00h]
0x140006014  mov     r15b, al
0x140006017  cmp     dword ptr [rsi+0F0h], 0
0x14000601e  jnz     loc_1400060FC
0x140006024  lea     rdi, WPP_MAIN_CB.DeviceQueue.20h
0x14000602b  mov     r14d, 0C0000239h
0x140006031  mov     rbx, rdi
0x140006034  xor     r12d, r12d
0x140006037  mov     rbx, [rbx]
0x14000603a  cmp     rbx, rdi
0x14000603d  jz      short loc_140006091
0x14000603f  lea     rax, [rbx+10h]
0x140006043  mov     rcx, [rax]
0x140006046  cmp     rcx, rax
0x140006049  jz      short loc_14000608C
0x14000604b  mov     r12d, [rcx+10h]
0x14000604f  mov     dl, r15b; NewIrql
0x140006052  lea     rcx, SpinLock; SpinLock
0x140006059  bswap   r12d
0x14000605c  call    cs:__imp_KeReleaseSpinLock
0x140006063  nop     dword ptr [rax+rax+00h]
0x140006068  mov     edx, r12d
0x14000606b  mov     rcx, rsi
0x14000606e  call    SetSenderMCastOutIf
0x140006073  lea     rcx, SpinLock; SpinLock
0x14000607a  mov     r14d, eax
0x14000607d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006084  nop     dword ptr [rax+rax+00h]
0x140006089  mov     r15b, al
0x14000608c  test    r12d, r12d
0x14000608f  jz      short loc_140006037
0x140006091  mov     rdi, [rbp+arg_18]
0x140006095  test    r14d, r14d
0x140006098  jns     short loc_1400060FC
0x14000609a  mov     dl, r15b; NewIrql
0x14000609d  lea     rcx, SpinLock; SpinLock
0x1400060a4  call    cs:__imp_KeReleaseSpinLock
0x1400060ab  nop     dword ptr [rax+rax+00h]
0x1400060b0  mov     rcx, rdi
0x1400060b3  call    PgmDereferenceSessionCommon
0x1400060b8  mov     rcx, rsi; P
0x1400060bb  call    PgmDereferenceAddress
0x1400060c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060c7  lea     rbx, WPP_GLOBAL_Control
0x1400060ce  cmp     rcx, rbx
0x1400060d1  jz      short loc_1400060F2
0x1400060d3  mov     eax, [rcx+2Ch]
0x1400060d6  test    al, 2
0x1400060d8  jz      short loc_1400060F2
0x1400060da  mov     rcx, [rcx+18h]
0x1400060de  lea     r8, WPP_ffb0ebbf543c30978a27a610893f40c5_Traceguids
0x1400060e5  mov     edx, 17h
0x1400060ea  mov     r9d, r12d
0x1400060ed  call    WPP_SF_d
0x1400060f2  mov     eax, 0C0000001h
0x1400060f7  jmp     loc_1400067DE
0x1400060fc  mov     rax, [rdi+28h]
0x140006100  mov     r12d, [rbp+arg_10]
0x140006104  mov     ecx, r12d
0x140006107  bswap   ecx
0x140006109  mov     [rax+28h], ecx
0x14000610c  movzx   ecx, word ptr [rbp+arg_8]
0x140006110  ror     cx, 8
0x140006114  mov     [rsi+0EEh], cx
0x14000611b  mov     rax, [rdi+28h]
0x14000611f  mov     [rax+30h], cx
0x140006123  mov     eax, [rsi+0F0h]
0x140006129  mov     rcx, [rdi+28h]
0x14000612d  mov     [rcx+2Ch], eax
0x140006130  movzx   eax, word ptr [rsi+12Ch]
0x140006137  mov     [rdi+9Ch], ax
0x14000613e  movzx   eax, byte ptr [rsi+130h]
0x140006145  mov     [rdi+0A0h], al
0x14000614b  cmp     byte ptr [rsi+131h], 0
0x140006152  jz      loc_14000629B
0x140006158  lea     rdx, ds:10h[rax*8]
0x140006160  mov     ecx, 40h ; '@'
0x140006165  mov     r8d, 306D6750h
0x14000616b  call    cs:__imp_ExAllocatePool2
0x140006172  nop     dword ptr [rax+rax+00h]
0x140006177  mov     rcx, [rdi+28h]
0x14000617b  mov     [rcx+1A8h], rax
0x140006182  test    rax, rax
0x140006185  jz      short loc_1400061FE
0x140006187  movzx   r8d, word ptr [rdi+9Ch]
0x14000618f  lea     rcx, [rdi+70h]
0x140006193  movzx   edx, byte ptr [rdi+0A0h]
0x14000619a  xor     r9d, r9d
0x14000619d  call    CreateFECContext
0x1400061a2  mov     r14d, eax
0x1400061a5  test    eax, eax
0x1400061a7  js      short loc_1400061FE
0x1400061a9  mov     al, [rsi+131h]
0x1400061af  mov     [rdi+0A1h], al
0x1400061b5  movzx   eax, word ptr [rsi+12Eh]
0x1400061bc  mov     [rdi+9Eh], ax
0x1400061c3  mov     rax, [rdi+28h]
0x1400061c7  bts     dword ptr [rax+0C4h], 9
0x1400061cf  mov     rax, [rdi+28h]
0x1400061d3  mov     dword ptr [rax+0B4h], 0FFFFFFFFh
0x1400061dd  mov     ecx, [rsi+0F8h]
0x1400061e3  mov     rax, [rdi+28h]
0x1400061e7  add     ecx, 37h ; '7'
0x1400061ea  and     ecx, 0FFFFFFF8h
0x1400061ed  mov     [rax+6Ch], ecx
0x1400061f0  mov     ecx, [rsi+0F8h]
0x1400061f6  sub     ecx, 46h ; 'F'
0x1400061f9  jmp     loc_1400062B7
0x1400061fe  mov     rax, [rdi+28h]
0x140006202  mov     rcx, [rax+1A8h]; P
0x140006209  test    rcx, rcx
0x14000620c  jz      short loc_14000622B
0x14000620e  xor     edx, edx; Tag
0x140006210  call    cs:__imp_ExFreePoolWithTag
0x140006217  nop     dword ptr [rax+rax+00h]
0x14000621c  mov     rax, [rdi+28h]
0x140006220  mov     qword ptr [rax+1A8h], 0
0x14000622b  mov     dl, r15b; NewIrql
0x14000622e  lea     rcx, SpinLock; SpinLock
0x140006235  call    cs:__imp_KeReleaseSpinLock
0x14000623c  nop     dword ptr [rax+rax+00h]
0x140006241  mov     rcx, rdi
0x140006244  call    PgmDereferenceSessionCommon
0x140006249  mov     rcx, rsi; P
0x14000624c  call    PgmDereferenceAddress
0x140006251  mov     rcx, cs:WPP_GLOBAL_Control
0x140006258  lea     rbx, WPP_GLOBAL_Control
0x14000625f  cmp     rcx, rbx
0x140006262  jz      short loc_140006291
0x140006264  mov     edx, [rcx+2Ch]
0x140006267  test    dl, 2
0x14000626a  jz      short loc_140006291
0x14000626c  movzx   r8d, word ptr [rbp+arg_8]
0x140006271  mov     edx, 18h
0x140006276  mov     rcx, [rcx+18h]
0x14000627a  mov     r9d, r14d
0x14000627d  mov     dword ptr [rsp+60h+Depth], r8d
0x140006282  mov     [rsp+60h+Tag], r12d
0x140006287  mov     [rsp+60h+Size], rdi
0x14000628c  call    WPP_SF_DqDD
0x140006291  mov     eax, 0C000009Ah
0x140006296  jmp     loc_1400067DE
0x14000629b  mov     ecx, [rsi+0F8h]
0x1400062a1  mov     rax, [rdi+28h]
0x1400062a5  add     ecx, 27h ; '''
0x1400062a8  and     ecx, 0FFFFFFF8h
0x1400062ab  mov     [rax+6Ch], ecx
0x1400062ae  mov     ecx, [rsi+0F8h]
0x1400062b4  sub     ecx, 38h ; '8'
0x1400062b7  mov     rax, [rdi+28h]
0x1400062bb  mov     ebx, 1
0x1400062c0  mov     [rax+70h], ecx
0x1400062c3  movzx   eax, word ptr cs:WPP_MAIN_CB.Dpc.DpcData+6
0x1400062ca  mov     [rdi+46h], ax
0x1400062ce  movzx   ecx, word ptr cs:WPP_MAIN_CB.Dpc.DpcData+6
0x1400062d5  add     cx, bx
0x1400062d8  mov     word ptr cs:WPP_MAIN_CB.Dpc.DpcData+6, cx
0x1400062df  movzx   eax, word ptr [rsi+0EEh]
0x1400062e6  cmp     [rdi+46h], ax
0x1400062ea  jnz     short loc_1400062F7
0x1400062ec  mov     [rdi+46h], cx
0x1400062f0  add     word ptr cs:WPP_MAIN_CB.Dpc.DpcData+6, bx
0x1400062f7  mov     rax, [rdi+28h]
0x1400062fb  lea     rcx, SpinLock; SpinLock
0x140006302  add     rax, 0F8h
0x140006308  mov     dl, r15b; NewIrql
0x14000630b  mov     [rax+8], rax
0x14000630f  mov     [rax], rax
0x140006312  mov     rax, [rdi+28h]
0x140006316  add     rax, 0E8h
0x14000631c  mov     [rax+8], rax
0x140006320  mov     [rax], rax
0x140006323  mov     rax, [rdi+28h]
0x140006327  add     rax, 0D8h
0x14000632d  mov     [rax+8], rax
0x140006331  mov     [rax], rax
0x140006334  mov     eax, [rsi+100h]
0x14000633a  mov     dword ptr [rbp+arg_0], eax
0x14000633d  call    cs:__imp_KeReleaseSpinLock
0x140006344  nop     dword ptr [rax+rax+00h]
0x140006349  mov     rcx, [rdi+28h]
0x14000634d  xor     r8d, r8d; State
0x140006350  add     rcx, 2C0h; Event
0x140006357  mov     edx, ebx; Type
0x140006359  call    cs:__imp_KeInitializeEvent
0x140006360  nop     dword ptr [rax+rax+00h]
0x140006365  mov     rcx, [rsi+40h]
0x140006369  lea     r8, [rbp+arg_0]
  ... truncated ...
```
