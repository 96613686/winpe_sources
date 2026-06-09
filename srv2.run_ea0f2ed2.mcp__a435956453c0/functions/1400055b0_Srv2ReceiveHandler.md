# Srv2ReceiveHandler

- ea: `0x1400055b0`
- end: `0x140005f0e`
- name: `Srv2ReceiveHandler`
- size: `2398`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140004020`
- `0x140004814`
- `0x140004960`
- `0x140004aa8`
- `0x140005070`
- `0x1400051dc`
- `0x1400055b0`
- `0x140005f20`
- `0x140006218`
- `0x140006ad0`
- `0x1400119e0`
- `0x1400181f0`
- `0x1400189b0`
- `0x1400222ec`
- `0x1400225c4`
- `0x140022618`
- `0x1400226e4`
- `0x140022f0c`
- `0x140038680`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140005a1e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140005d75`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140005a1e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140005d75`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a5bf`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a5bf`
- `ntoskrnl!KeLowerIrql` at `0x140005914`
- `ntoskrnl!KeLowerIrql` at `0x140005914`
- `ntoskrnl!KfRaiseIrql` at `0x1400058f5`
- `ntoskrnl!KfRaiseIrql` at `0x1400058f5`
- `ntoskrnl!RtlInitAnsiString` at `0x140005c88`
- `ntoskrnl!RtlInitAnsiString` at `0x140005c88`
- `ntoskrnl!IoClearActivityIdThread` at `0x140005be0`
- `ntoskrnl!IoClearActivityIdThread` at `0x140005be0`
- `ntoskrnl!IoSetActivityIdThread` at `0x140005bb2`
- `ntoskrnl!IoSetActivityIdThread` at `0x140005bb2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140005a3a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140005d91`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140005a3a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140005d91`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400057b0`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400057b0`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14000583c`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140005af8`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14000583c`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140005af8`
- `HAL!KeQueryPerformanceCounter` at `0x140005c51`
- `HAL!KeQueryPerformanceCounter` at `0x140005c51`
- `srvnet!SrvAdminAllowAnonymousAccess` at `0x140005ce2`
- `srvnet!SrvAdminAllowAnonymousAccess` at `0x140005ce2`
- `srvnet!SrvNetIsTdiConnection` at `0x140005b3d`
- `srvnet!SrvNetIsTdiConnection` at `0x140005b3d`

## string_xrefs

- `0x140005c6e`: `Srv2PostToThreadPool`
- `0x140005d54`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Srv2ReceiveHandler(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        _DWORD *a5,
        char *Src,
        __int64 a7,
        _QWORD *a8)
{
  char v8; // r15
  size_t v9; // rsi
  __int64 WorkItem; // rax
  __int64 v12; // rbx
  __int64 v13; // r15
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // r15
  unsigned __int16 v19; // ax
  __int16 v20; // ax
  unsigned int v21; // r13d
  PEX_SPIN_LOCK v22; // rdi
  unsigned __int64 v23; // r12
  KIRQL v24; // al
  unsigned __int64 v25; // rdx
  KIRQL v26; // r10
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  __int64 v29; // r8
  char v30; // r12
  int v31; // edx
  signed __int16 v32; // ax
  KIRQL v33; // bl
  int v35; // edi
  __int64 v36; // rcx
  __int64 v37; // rdx
  unsigned __int64 v38; // rdi
  bool v39; // zf
  __int64 v40; // rdi
  __int64 v41; // rdi
  _OWORD *v42; // rax
  unsigned int v43; // eax
  unsigned __int64 v44; // rax
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v46; // rdx
  __int64 v47; // rax
  int v48; // edx
  int v49; // ecx
  __int64 v50; // rdi
  int v51; // eax
  int v52; // edi
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  struct _STRING v54; // xmm0
  int v55; // [rsp+20h] [rbp-68h]
  struct _STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF
  struct _STRING v57; // [rsp+50h] [rbp-38h] BYREF
  char v58; // [rsp+A8h] [rbp+20h]

  v8 = 0;
  v9 = a4;
  v58 = 0;
  *a8 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_DqDq(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a4, a2, a3, a7);
  }
  if ( (unsigned int)v9 < 4 )
  {
LABEL_40:
    v33 = KfRaiseIrql(2u);
    Srv2CloseConnection((PVOID)a2);
    KeLowerIrql(v33);
    *a5 = 0;
    if ( !v8 )
      return 3221226011LL;
    return 3221225489LL;
  }
  switch ( *(_DWORD *)Src )
  {
    case 0x424D53FD:
      if ( (unsigned int)v9 < 0x34 )
        goto LABEL_40;
      break;
    case 0x424D53FC:
      if ( (unsigned int)v9 < 0x10 )
        goto LABEL_40;
      break;
    case 0x424D53FE:
      if ( (unsigned int)v9 < 0x40 || *((_WORD *)Src + 6) >= 0x14u )
        goto LABEL_40;
      break;
    default:
      if ( *(_DWORD *)Src != 1112364031 || (unsigned int)v9 < 0x21 || Src[4] != 114 )
        goto LABEL_40;
      break;
  }
  WorkItem = Srv2AllocateWorkItem(a2);
  v12 = WorkItem;
  if ( !WorkItem )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, &WPP_8c61ecf697593902513841fcaa61ed76_Traceguids, a2);
    }
    goto LABEL_40;
  }
  if ( a7 )
  {
    *(_DWORD *)(WorkItem + 484) |= 3u;
    *(_QWORD *)(WorkItem + 312) = a7;
    *(_QWORD *)(WorkItem + 304) = a7;
    v58 = 1;
  }
  else
  {
    if ( (unsigned int)v9 > *(_DWORD *)(*(_QWORD *)(WorkItem + 304) + 32LL)
      && (int)Srv2AllocateReceiveBuffer(WorkItem, (unsigned int)v9, 0) < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          &WPP_8c61ecf697593902513841fcaa61ed76_Traceguids,
          (unsigned int)v9,
          a2);
      }
      goto LABEL_39;
    }
    memmove(*(void **)(*(_QWORD *)(v12 + 304) + 24LL), Src, v9);
    *(_DWORD *)(*(_QWORD *)(v12 + 304) + 36LL) = v9;
    if ( (Microsoft_Windows_SMBServerEnableBits & 0x10) != 0 )
    {
      v42 = (_OWORD *)IoSetActivityIdThread(0);
      if ( v42 )
      {
        *(_WORD *)(*(_QWORD *)(v12 + 304) + 22LL) = 1;
        *(_OWORD *)(*(_QWORD *)(v12 + 304) + 100LL) = *v42;
      }
      IoClearActivityIdThread(v42);
    }
  }
  v13 = -1;
  _InterlockedIncrement((volatile signed __int32 *)Srv2HotGlobals + 32
                                                                  * (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray)
                                                                  + 12);
  if ( *(_DWORD *)Src == 1112364029 )
  {
    v13 = *(_QWORD *)(Src + 44);
    *(_OWORD *)(v12 + 264) = *(_OWORD *)(Src + 4);
    *(_OWORD *)(v12 + 280) = *(_OWORD *)(Src + 20);
    if ( !*(_BYTE *)(a2 + 510) || (unsigned __int8)SrvNetIsTdiConnection(*(_QWORD *)(a2 + 480)) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, &WPP_8c61ecf697593902513841fcaa61ed76_Traceguids, a2);
      }
      goto LABEL_38;
    }
    if ( (unsigned __int8)Srv2TryPostDecryptMessage(v12) )
      goto LABEL_73;
    v51 = Srv2DecryptData(v12);
    if ( v51 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          &WPP_8c61ecf697593902513841fcaa61ed76_Traceguids,
          (unsigned int)v51,
          a2);
      }
      goto LABEL_38;
    }
    *(_DWORD *)(v12 + 484) |= 0x1000u;
  }
  if ( **(_DWORD **)(*(_QWORD *)(v12 + 304) + 24LL) != 1112364028 )
  {
LABEL_11:
    if ( v13 != -1 && (int)Srv2VerifyPostTransformData(v12, v13) < 0 )
      goto LABEL_38;
    v14 = *(_QWORD *)(v12 + 304);
    v15 = *(_QWORD *)(v14 + 24);
    v16 = *(_QWORD *)(*(_QWORD *)(v12 + 96) + 496LL);
    v17 = *(unsigned int *)(v14 + 36);
    *(_QWORD *)(v12 + 528) = Smb2CleanupWorkItem;
    *(_WORD *)(v12 + 488) = 1;
    *(_WORD *)(v12 + 490) = *(_WORD *)(v15 + 14);
    if ( (unsigned int)v17 > 4 )
    {
      if ( *(_DWORD *)v15 == 1112364031 )
      {
        v35 = 0;
        if ( *(_WORD *)(v16 + 44) != 0xFFFF )
          v35 = -1073741616;
        if ( v35 == -1073741616 )
          goto LABEL_69;
        goto LABEL_45;
      }
      if ( (unsigned int)v17 >= 0x40 )
      {
        v18 = *(_QWORD *)(v12 + 560);
        if ( *(_BYTE *)v18 )
          goto LABEL_45;
        v19 = *(_WORD *)(v15 + 12);
        if ( v19 < 0x14u )
        {
          *(_WORD *)(v18 + 14) = v19;
          *(_QWORD *)(v18 + 176) = *(_QWORD *)(v15 + 24);
          if ( *(_WORD *)(v15 + 12) != 12 )
          {
            if ( (*(_BYTE *)(v16 + 49) & 2) != 0 )
            {
              v20 = *(_WORD *)(v15 + 6);
              if ( v20 )
                *(_WORD *)(v12 + 488) = v20;
            }
            v21 = *(unsigned __int16 *)(v12 + 488);
            if ( !*(_WORD *)(v12 + 488) )
              goto LABEL_69;
            v22 = *(PEX_SPIN_LOCK *)v16;
            v23 = *(_QWORD *)(v15 + 24);
            v24 = ExAcquireSpinLockShared(*(PEX_SPIN_LOCK *)v16);
            v25 = *((_QWORD *)v22 + 1);
            v26 = v24;
            if ( v23 < v25 || v23 > *((_QWORD *)v22 + 2) )
              goto LABEL_68;
            v27 = *((unsigned int *)v22 + 6) - v25 + v23;
            v28 = *((unsigned int *)v22 + 8);
            v29 = (unsigned int)(v27 - v28);
            if ( v27 < v28 )
              v29 = (unsigned int)v27;
            if ( (_DWORD)v29 == -1 || v21 > 1 && ((v44 = v23 + v21 - 1, v44 < v23) || v44 > *((_QWORD *)v22 + 2)) )
            {
LABEL_68:
              ExReleaseSpinLockShared(v22, v26);
              goto LABEL_69;
            }
            v30 = 0;
            v31 = 0;
            while ( 1 )
            {
              v32 = _InterlockedCompareExchange16((volatile signed __int16 *)(2 * v29 + *((_QWORD *)v22 + 5)), 2, 0);
              if ( v32 )
              {
                if ( v32 == 2
                  || v31
                  || _InterlockedCompareExchange16((volatile signed __int16 *)(2 * v29 + *((_QWORD *)v22 + 5)), 2, 1) != 1 )
                {
                  goto LABEL_68;
                }
                v30 = 1;
              }
              if ( ++v31 == v21 )
                break;
              v43 = v29 + 1;
              v29 = 0;
              if ( v43 != *((_DWORD *)v22 + 8) )
                v29 = v43;
            }
            ExReleaseSpinLockShared(v22, v26);
            *(_BYTE *)v18 = 1;
            if ( v30 )
              *(_DWORD *)(v12 + 480) = 1;
LABEL_45:
            if ( (*(_DWORD *)(v12 + 484) & 0x1000) != 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
              DestinationString.Buffer = (PCHAR)16;
              *(_QWORD *)&DestinationString.Length = v12 + 280;
              v54 = DestinationString;
              DestinationString.Buffer = (PCHAR)16;
              *(_QWORD *)&DestinationString.Length = v12 + 264;
              v57 = v54;
              WPP_SF_q_zb__zb_(
                (_DWORD)AttachedDevice,
                29,
                (unsigned int)&WPP_8c61ecf697593902513841fcaa61ed76_Traceguids,
                v12,
                (__int64)&DestinationString,
                (__int64)&v57);
            }
            v36 = *(_QWORD *)(v12 + 304);
            *(_DWORD *)(v12 + 408) = *(_DWORD *)(v36 + 36);
            v37 = *(unsigned int *)(v36 + 36);
            if ( (unsigned int)v37 < 0x40
              || (v38 = *(unsigned int *)(*(_QWORD *)(v36 + 24) + 20LL), (unsigned int)v38 <= 0x40)
              || v38 >= v37 - 64 )
            {
              LODWORD(v38) = *(_DWORD *)(v36 + 36);
            }
            else if ( (_DWORD)v38 != (_DWORD)v37
                   && (int)Srv2PlainTextCompoundReceiveHandler(v12, (unsigned int)v38, v17, v16) < 0 )
            {
LABEL_38:
              v8 = v58;
LABEL_39:
              Srv2DereferenceWorkItem(v12);
              goto LABEL_40;
            }
            v39 = *(_DWORD *)(v12 + 8) == 5;
            *(_QWORD *)(v12 + 48) = Srv2ProcessPacket;
            *(_DWORD *)(v12 + 400) = v38;
            *(_DWORD *)(v12 + 404) = v38;
            *(_BYTE *)(v12 + 472) = 1;
            *(_DWORD *)(v12 + 72) = 0;
            if ( v39 )
            {
              v39 = *(_BYTE *)(v12 + 600) == 0;
              DestinationString = 0;
              if ( !v39 )
              {
                PerformanceCounter = KeQueryPerformanceCounter(0);
                LOBYTE(v46) = 1;
                v47 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SRV2_PERF_UPDATE_PERF_COUNTER)(
                        v12 + 584,
                        v46,
                        (LARGE_INTEGER)PerformanceCounter.QuadPart);
                *(_BYTE *)(v12 + 712) = 1;
                *(_QWORD *)(v12 + 720) = v47;
                RtlInitAnsiString(&DestinationString, "Srv2PostToThreadPool");
                if ( (Microsoft_Windows_SMBServerEnableBits & 4) != 0 )
                  McTemplateK0qqhsr2_EtwWriteTransfer(
                    v49,
                    v48,
                    v12 + 584,
                    1,
                    135,
                    DestinationString.Length,
                    (__int64)DestinationString.Buffer);
              }
            }
            v40 = *(_QWORD *)(*(_QWORD *)(v12 + 64) + 136LL);
            v41 = *(_QWORD *)(v40 + 8LL * KeGetCurrentNodeNumber() + 8);
            if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v41 + 16), (PSLIST_ENTRY)(v12 + 32))
              && *(_WORD *)(v41 + 66) )
            {
              goto LABEL_55;
            }
            goto LABEL_73;
          }
          if ( *(_BYTE *)(*(_QWORD *)(v12 + 96) + 510LL)
            || (unsigned __int8)SrvAdminAllowAnonymousAccess(v14, v15, v17, v16) )
          {
            goto LABEL_45;
          }
        }
      }
    }
LABEL_69:
    *(_DWORD *)(v12 + 488) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        28,
        &WPP_8c61ecf697593902513841fcaa61ed76_Traceguids,
        *(_QWORD *)(v12 + 96));
    }
    goto LABEL_38;
  }
  if ( KeGetCurrentIrql() <= 1u )
  {
    v52 = Srv2DecompressData(v12);
    if ( v52 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          27,
          &WPP_8c61ecf697593902513841fcaa61ed76_Traceguids,
          (unsigned int)v52,
          *(_QWORD *)(v12 + 96));
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          &WPP_8c61ecf697593902513841fcaa61ed76_Traceguids,
          (unsigned int)v52,
          a2);
      }
      goto LABEL_38;
    }
    *(_DWORD *)(v12 + 484) |= 0x40u;
    goto LABEL_11;
  }
  v39 = *(_DWORD *)(v12 + 8) == 5;
  *(_QWORD *)(v12 + 48) = Srv2DecompressMessageWorker;
  *(_QWORD *)(v12 + 256) = v13;
  *(_DWORD *)(v12 + 72) = 0;
  if ( v39 )
  {
    LOBYTE(v55) = 1;
    SRV2_PERF_ENTER_EX(v12 + 584, 1, 391, "Srv2PostToThreadPool", v55);
  }
  v50 = *(_QWORD *)(*(_QWORD *)(v12 + 64) + 136LL);
  v41 = *(_QWORD *)(v50 + 8LL * KeGetCurrentNodeNumber() + 8);
  if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v41 + 16), (PSLIST_ENTRY)(v12 + 32)) && *(_WORD *)(v41 + 66) )
LABEL_55:
    RfspThreadPoolNodeWakeIdleWorker(v41);
LABEL_73:
  if ( !a7 )
  {
    *a5 = v9;
    return 0;
  }
  return 3221225489LL;
}

```

## disassembly

```asm
0x1400055b0  push    rbp
0x1400055b2  push    rsi
0x1400055b3  push    r12
0x1400055b5  push    r14
0x1400055b7  push    r15
0x1400055b9  sub     rsp, 60h
0x1400055bd  mov     rax, [rsp+88h+arg_38]
0x1400055c5  xor     r15b, r15b
0x1400055c8  mov     esi, r9d
0x1400055cb  mov     r14, rdx
0x1400055ce  mov     [rsp+88h+arg_18], r15b
0x1400055d6  mov     qword ptr [rax], 0
0x1400055dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400055e4  lea     r12, WPP_GLOBAL_Control
0x1400055eb  mov     rbp, [rsp+88h+arg_30]
0x1400055f3  cmp     rcx, r12
0x1400055f6  jnz     loc_14000586E
0x1400055fc  mov     [rsp+88h+arg_0], rbx
0x140005604  mov     [rsp+88h+arg_8], rdi
0x14000560c  mov     [rsp+88h+arg_10], r13
0x140005614  cmp     esi, 4
0x140005617  jb      loc_140005ABE
0x14000561d  mov     rdi, [rsp+88h+Src]
0x140005625  mov     eax, [rdi]
0x140005627  cmp     eax, 424D53FDh
0x14000562c  jnz     loc_140005A8B
0x140005632  cmp     esi, 34h ; '4'
0x140005635  jb      loc_140005ABE
0x14000563b  mov     rcx, r14
0x14000563e  call    Srv2AllocateWorkItem
0x140005643  mov     rbx, rax
0x140005646  test    rax, rax
0x140005649  jz      loc_140005DD1
0x14000564f  mov     r13d, 1
0x140005655  test    rbp, rbp
0x140005658  jnz     loc_140005A69
0x14000565e  mov     rax, [rax+130h]
0x140005665  cmp     esi, [rax+20h]
0x140005668  ja      loc_140005B81
0x14000566e  mov     rcx, [rbx+130h]
0x140005675  mov     r8, rsi; Size
0x140005678  mov     rdx, rdi; Src
0x14000567b  mov     rcx, [rcx+18h]; void *
0x14000567f  call    memmove
0x140005684  mov     rax, [rbx+130h]
0x14000568b  mov     [rax+24h], esi
0x14000568e  test    cs:Microsoft_Windows_SMBServerEnableBits, 10h
0x140005695  jnz     loc_140005BB0
0x14000569b  mov     eax, gs:1A4h
0x1400056a3  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1400056aa  mov     ecx, eax
0x1400056ac  mov     rax, cs:Srv2HotGlobals
0x1400056b3  shl     rcx, 7
0x1400056b7  lock inc dword ptr [rcx+rax+30h]
0x1400056bc  cmp     dword ptr [rdi], 424D53FDh
0x1400056c2  jz      loc_1400058A5
0x1400056c8  mov     rax, [rbx+130h]
0x1400056cf  mov     rcx, [rax+18h]
0x1400056d3  cmp     dword ptr [rcx], 424D53FCh
0x1400056d9  jz      loc_14003A5BF
0x1400056df  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1400056e3  jnz     loc_140005EBC
0x1400056e9  mov     rcx, [rbx+130h]
0x1400056f0  mov     rax, [rbx+60h]
0x1400056f4  mov     rdx, [rcx+18h]
0x1400056f8  mov     r9, [rax+1F0h]
0x1400056ff  lea     rax, Smb2CleanupWorkItem
0x140005706  mov     r8d, [rcx+24h]
0x14000570a  mov     [rbx+210h], rax
0x140005711  mov     [rbx+1E8h], r13w
0x140005719  movzx   eax, word ptr [rdx+0Eh]
0x14000571d  mov     [rbx+1EAh], ax
0x140005724  cmp     r8d, 4
0x140005728  jbe     loc_140005B0B
0x14000572e  cmp     dword ptr [rdx], 424D53FFh
0x140005734  jz      loc_140005962
0x14000573a  cmp     r8d, 40h ; '@'
0x14000573e  jb      loc_140005B0B
0x140005744  mov     r15, [rbx+230h]
0x14000574b  cmp     byte ptr [r15], 0
0x14000574f  jnz     loc_140005986
0x140005755  movzx   eax, word ptr [rdx+0Ch]
0x140005759  cmp     ax, 14h
0x14000575d  jnb     loc_140005B0B
0x140005763  mov     [r15+0Eh], ax
0x140005768  mov     rax, [rdx+18h]
0x14000576c  mov     [r15+0B0h], rax
0x140005773  cmp     word ptr [rdx+0Ch], 0Ch
0x140005778  jz      loc_140005CD1
0x14000577e  test    byte ptr [r9+31h], 2
0x140005783  jz      short loc_140005795
0x140005785  movzx   eax, word ptr [rdx+6]
0x140005789  test    ax, ax
0x14000578c  jz      short loc_140005795
0x14000578e  mov     [rbx+1E8h], ax
0x140005795  movzx   r13d, word ptr [rbx+1E8h]
0x14000579d  test    r13d, r13d
0x1400057a0  jz      loc_140005B0B
0x1400057a6  mov     rdi, [r9]
0x1400057a9  mov     r12, [rdx+18h]
0x1400057ad  mov     rcx, rdi; SpinLock
0x1400057b0  call    cs:__imp_ExAcquireSpinLockShared
0x1400057b7  nop     dword ptr [rax+rax+00h]
0x1400057bc  mov     rdx, [rdi+8]
0x1400057c0  movzx   r10d, al
0x1400057c4  cmp     r12, rdx
0x1400057c7  jb      loc_140005AF1
0x1400057cd  cmp     r12, [rdi+10h]
0x1400057d1  ja      loc_140005AF1
0x1400057d7  mov     ecx, [rdi+18h]
0x1400057da  sub     rcx, rdx
0x1400057dd  lea     rdx, [rcx+r12]
0x1400057e1  mov     ecx, [rdi+20h]
0x1400057e4  mov     r8d, edx
0x1400057e7  sub     r8d, ecx
0x1400057ea  cmp     rdx, rcx
0x1400057ed  cmovb   r8d, edx
0x1400057f1  cmp     r8d, 0FFFFFFFFh
0x1400057f5  jz      loc_140005AF1
0x1400057fb  cmp     r13d, 1
0x1400057ff  ja      loc_140005C30
0x140005805  xor     r12b, r12b
0x140005808  mov     r11d, 2
0x14000580e  xor     edx, edx
0x140005810  mov     rcx, [rdi+28h]
0x140005814  lea     r9, [r8+r8]
0x140005818  xor     eax, eax
0x14000581a  lock cmpxchg [r9+rcx], r11w
0x140005821  test    ax, ax
0x140005824  jnz     loc_140005AC8
0x14000582a  inc     edx
0x14000582c  cmp     edx, r13d
0x14000582f  jnz     loc_140005BF1
0x140005835  movzx   edx, r10b; OldIrql
0x140005839  mov     rcx, rdi; SpinLock
0x14000583c  call    cs:__imp_ExReleaseSpinLockShared
0x140005843  nop     dword ptr [rax+rax+00h]
0x140005848  test    r12b, r12b
0x14000584b  mov     byte ptr [r15], 1
0x14000584f  lea     r12, WPP_GLOBAL_Control
0x140005856  mov     r13d, 1
0x14000585c  jz      loc_140005986
0x140005862  mov     [rbx+1E0h], r13d
0x140005869  jmp     loc_140005986
0x14000586e  test    dword ptr [rcx+2Ch], 200h
0x140005875  jz      loc_1400055FC
0x14000587b  cmp     byte ptr [rcx+29h], 2
0x14000587f  jb      loc_1400055FC
0x140005885  mov     rcx, [rcx+18h]
0x140005889  mov     r9d, esi
0x14000588c  mov     [rsp+88h+var_58], rbp
0x140005891  mov     dword ptr [rsp+88h+var_60], r8d
0x140005896  mov     [rsp+88h+var_68], r14
0x14000589b  call    WPP_SF_DqDq
0x1400058a0  jmp     loc_1400055FC
0x1400058a5  movups  xmm0, xmmword ptr [rdi+4]
0x1400058a9  mov     r15, [rdi+2Ch]
0x1400058ad  movups  xmmword ptr [rbx+108h], xmm0
0x1400058b4  movups  xmm0, xmmword ptr [rdi+14h]
0x1400058b8  movups  xmmword ptr [rbx+118h], xmm0
0x1400058bf  cmp     byte ptr [r14+1FEh], 0
0x1400058c7  jnz     loc_140005B36
0x1400058cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400058d4  cmp     rcx, r12
0x1400058d7  jnz     loc_140005E4F
0x1400058dd  mov     edi, 7
0x1400058e2  movzx   r15d, [rsp+88h+arg_18]
0x1400058eb  mov     rcx, rbx
0x1400058ee  call    Srv2DereferenceWorkItem
0x1400058f3  mov     cl, 2; NewIrql
0x1400058f5  call    cs:__imp_KfRaiseIrql
0x1400058fc  nop     dword ptr [rax+rax+00h]
0x140005901  xor     r8d, r8d
0x140005904  mov     edx, edi
0x140005906  mov     rcx, r14; P
0x140005909  movzx   ebx, al
0x14000590c  call    Srv2CloseConnection
0x140005911  movzx   ecx, bl; NewIrql
0x140005914  call    cs:__imp_KeLowerIrql
0x14000591b  nop     dword ptr [rax+rax+00h]
0x140005920  mov     rax, [rsp+88h+arg_20]
0x140005928  mov     dword ptr [rax], 0
0x14000592e  test    r15b, r15b
0x140005931  jnz     loc_140005B77
0x140005937  mov     eax, 0C000021Bh
0x14000593c  mov     r13, [rsp+88h+arg_10]
0x140005944  mov     rdi, [rsp+88h+arg_8]
0x14000594c  mov     rbx, [rsp+88h+arg_0]
0x140005954  add     rsp, 60h
0x140005958  pop     r15
0x14000595a  pop     r14
0x14000595c  pop     r12
0x14000595e  pop     rsi
0x14000595f  pop     rbp
0x140005960  retn
0x140005962  xor     edi, edi
0x140005964  mov     ecx, 0FFFFh
0x140005969  cmp     [r9+2Ch], cx
0x14000596e  mov     eax, 0C00000D0h
0x140005973  cmovnz  edi, eax
0x140005976  cmp     edi, eax
0x140005978  jz      loc_140005B10
0x14000597e  test    edi, edi
0x140005980  js      loc_140005B18
0x140005986  test    dword ptr [rbx+1E4h], 1000h
0x140005990  jz      short loc_1400059A9
0x140005992  mov     rcx, cs:WPP_GLOBAL_Control
0x140005999  cmp     rcx, r12
0x14000599c  jz      short loc_1400059A9
0x14000599e  mov     eax, [rcx+2Ch]
0x1400059a1  test    al, 1
0x1400059a3  jnz     loc_14003A63C
0x1400059a9  mov     rcx, [rbx+130h]
0x1400059b0  mov     eax, [rcx+24h]
0x1400059b3  mov     [rbx+198h], eax
0x1400059b9  mov     edx, [rcx+24h]
0x1400059bc  cmp     edx, 40h ; '@'
0x1400059bf  jb      short loc_1400059D1
0x1400059c1  mov     rax, [rcx+18h]
0x1400059c5  mov     edi, [rax+14h]
0x1400059c8  cmp     edi, 40h ; '@'
0x1400059cb  ja      loc_140005C04
0x1400059d1  mov     edi, edx
0x1400059d3  cmp     dword ptr [rbx+8], 5
0x1400059d7  lea     rax, Srv2ProcessPacket
0x1400059de  mov     [rbx+30h], rax
0x1400059e2  mov     [rbx+190h], edi
0x1400059e8  mov     [rbx+194h], edi
0x1400059ee  mov     byte ptr [rbx+1D8h], 1
0x1400059f5  mov     dword ptr [rbx+48h], 0
0x1400059fc  jnz     short loc_140005A13
0x1400059fe  cmp     byte ptr [rbx+258h], 0
0x140005a05  xorps   xmm0, xmm0
0x140005a08  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x140005a0d  jnz     loc_140005C4F
0x140005a13  mov     rax, [rbx+40h]
0x140005a17  mov     rdi, [rax+88h]
0x140005a1e  call    cs:__imp_KeGetCurrentNodeNumber
0x140005a25  nop     dword ptr [rax+rax+00h]
0x140005a2a  movzx   eax, ax
0x140005a2d  lea     rdx, [rbx+20h]; ListEntry
0x140005a31  mov     rdi, [rdi+rax*8+8]
0x140005a36  lea     rcx, [rdi+10h]; ListHead
0x140005a3a  call    cs:__imp_ExpInterlockedPushEntrySList
0x140005a41  nop     dword ptr [rax+rax+00h]
0x140005a46  test    rax, rax
0x140005a49  jnz     loc_140005B61
0x140005a4f  movzx   edx, word ptr [rdi+42h]
0x140005a53  cmp     ax, dx
0x140005a56  jz      loc_140005B61
0x140005a5c  mov     rcx, rdi
0x140005a5f  call    RfspThreadPoolNodeWakeIdleWorker
0x140005a64  jmp     loc_140005B61
0x140005a69  or      dword ptr [rax+1E4h], 3
0x140005a70  mov     [rax+138h], rbp
0x140005a77  mov     [rax+130h], rbp
0x140005a7e  mov     [rsp+88h+arg_18], r13b
0x140005a86  jmp     loc_14000569B
0x140005a8b  sub     eax, 424D53FCh
0x140005a90  jz      loc_140005DC3
0x140005a96  sub     eax, 2
0x140005a99  jnz     short loc_140005AB5
0x140005a9b  cmp     esi, 40h ; '@'
0x140005a9e  jb      short loc_140005ABE
0x140005aa0  cmp     word ptr [rdi+0Ch], 14h
0x140005aa5  jb      loc_14000563B
0x140005aab  mov     edi, 6
0x140005ab0  jmp     loc_1400058F3
0x140005ab5  cmp     eax, 1
0x140005ab8  jz      loc_140005DAB
0x140005abe  mov     edi, 6
0x140005ac3  jmp     loc_1400058F3
0x140005ac8  cmp     ax, r11w
0x140005acc  jz      short loc_140005AF1
0x140005ace  test    edx, edx
0x140005ad0  jnz     short loc_140005AF1
0x140005ad2  mov     rcx, [rdi+28h]
0x140005ad6  mov     eax, 1
0x140005adb  lock cmpxchg [r9+rcx], r11w
0x140005ae2  cmp     ax, 1
0x140005ae6  jnz     short loc_140005AF1
0x140005ae8  movzx   r12d, al
0x140005aec  jmp     loc_14000582A
0x140005af1  movzx   edx, r10b; OldIrql
0x140005af5  mov     rcx, rdi; SpinLock
0x140005af8  call    cs:__imp_ExReleaseSpinLockShared
0x140005aff  nop     dword ptr [rax+rax+00h]
0x140005b04  lea     r12, WPP_GLOBAL_Control
0x140005b0b  mov     edi, 0C00000D0h
0x140005b10  xor     eax, eax
0x140005b12  mov     [rbx+1E8h], eax
0x140005b18  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b1f  cmp     rcx, r12
0x140005b22  jnz     loc_140005ED9
0x140005b28  test    edi, edi
0x140005b2a  jns     short loc_140005B61
0x140005b2c  mov     edi, 6
0x140005b31  jmp     loc_1400058E2
0x140005b36  mov     rcx, [r14+1E0h]
0x140005b3d  call    cs:__imp_SrvNetIsTdiConnection
  ... truncated ...
```
