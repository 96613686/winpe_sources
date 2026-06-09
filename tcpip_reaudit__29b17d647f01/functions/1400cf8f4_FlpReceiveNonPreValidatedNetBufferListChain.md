# FlpReceiveNonPreValidatedNetBufferListChain

- ea: `0x1400cf8f4`
- end: `0x1400cfe7a`
- name: `FlpReceiveNonPreValidatedNetBufferListChain`
- size: `1414`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400ce070`

## callees

- `0x1400632f0`
- `0x140091e00`
- `0x140091ef0`
- `0x1400c26a0`
- `0x1400cf8f4`
- `0x1400cfe80`
- `0x1400cfeb0`
- `0x1400cff70`
- `0x1400cffc0`
- `0x14011fe3c`
- `0x1401497c0`
- `0x1401498f4`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400cfb8d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400cfd91`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc826`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc917`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc931`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc9a9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cca91`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400cfb8d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400cfd91`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc826`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc917`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc931`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc9a9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cca91`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400cfa99`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc7be`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc8c5`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc959`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cca4d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400cfa99`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc7be`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc8c5`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc959`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cca4d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400cf97b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400cf97b`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400cf950`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400cf950`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc7a3`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc8ab`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cca32`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401ccaa9`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc7a3`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc8ab`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cca32`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401ccaa9`
- `NETIO!NetioCopyNetBufferListInformation` at `0x1400cfbcc`
- `NETIO!NetioCopyNetBufferListInformation` at `0x1400cfbcc`
- `NETIO!NetioCompleteCopyNetBufferListChain` at `0x1401cc77c`
- `NETIO!NetioAllocateAndReferenceCopyNetBufferListEx` at `0x1400cfbae`
- `NETIO!NetioAllocateAndReferenceCopyNetBufferListEx` at `0x1400cfbae`
- `NETIO!NetioInitializeNetBufferListContext` at `0x1400cfa21`
- `NETIO!NetioInitializeNetBufferListContext` at `0x1400cfa21`
- `NETIO!NetioUpdateNetBufferListContext` at `0x1401cc784`
- `NETIO!NetioUpdateNetBufferListContext` at `0x1401cc784`
- `NETIO!WfpNblInfoClearFlags` at `0x1400cfcbd`
- `NETIO!WfpNblInfoClearFlags` at `0x1400cfcbd`

## pseudocode

```c
void __fastcall FlpReceiveNonPreValidatedNetBufferListChain(__int64 a1, _QWORD *a2, __int64 a3, _DWORD *a4, int a5)
{
  _DWORD *v6; // r12
  _QWORD *v8; // rdi
  ULONG v9; // r13d
  ULONG v10; // esi
  KIRQL CurrentIrql; // al
  __int64 v12; // rcx
  char v13; // r15
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 *v16; // rax
  __int64 v17; // rdi
  int v18; // esi
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 *v22; // rax
  __int64 v23; // rcx
  int v24; // r14d
  __int64 v25; // rax
  __int64 v26; // r8
  __int64 (__fastcall *v27)(); // rax
  __int64 v28; // rcx
  __int64 v29; // r12
  __int64 v30; // r14
  __int64 v31; // rax
  __int64 v32; // rcx
  BOOL v33; // r14d
  _QWORD *v34; // rsi
  _QWORD *i; // rdi
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // r8
  __int64 (__fastcall *v39)(); // rax
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 *v42; // rax
  _QWORD *v43; // rdx
  unsigned __int16 v44; // r13
  __int64 *v45; // rax
  __int64 v46; // rdi
  _QWORD *v47; // rdi
  __int64 (__fastcall *v48)(); // rdx
  int v49; // r8d
  int v50; // r9d
  __int64 v51; // rdi
  __int64 v52; // rdx
  int v53; // r8d
  int v54; // r9d
  __int64 v55; // r8
  __int64 v56; // rdi
  __int64 v57; // rsi
  __int64 v58; // rdx
  ULONG v59; // [rsp+40h] [rbp-61h] BYREF
  KIRQL v60; // [rsp+44h] [rbp-5Dh]
  unsigned __int16 v61; // [rsp+46h] [rbp-5Bh]
  unsigned __int16 v62; // [rsp+48h] [rbp-59h] BYREF
  __int16 v63; // [rsp+4Ch] [rbp-55h] BYREF
  unsigned int v64; // [rsp+50h] [rbp-51h]
  _QWORD *v65; // [rsp+58h] [rbp-49h] BYREF
  __int64 v66; // [rsp+60h] [rbp-41h] BYREF
  __int64 v67; // [rsp+68h] [rbp-39h] BYREF
  int v68; // [rsp+70h] [rbp-31h] BYREF
  ULONG Count; // [rsp+74h] [rbp-2Dh]
  ULONG CurrentProcessorNumber; // [rsp+78h] [rbp-29h]
  __int64 *v71; // [rsp+80h] [rbp-21h]
  __int64 *v72; // [rsp+88h] [rbp-19h]
  __int64 *v73; // [rsp+90h] [rbp-11h]
  __int64 v74; // [rsp+98h] [rbp-9h] BYREF
  _QWORD *v75; // [rsp+A0h] [rbp-1h] BYREF
  __int64 v76; // [rsp+A8h] [rbp+7h] BYREF
  bool v77; // [rsp+100h] [rbp+5Fh]
  _QWORD *v78; // [rsp+108h] [rbp+67h]

  v6 = a4;
  v76 = 0;
  v8 = 0;
  v68 = 0;
  v9 = 0;
  v62 = 0;
  v10 = 0;
  v63 = 0;
  v75 = 0;
  v67 = 0;
  v65 = 0;
  v66 = 0;
  v64 = 0;
  v59 = 0;
  Count = 0;
  CurrentIrql = KeGetCurrentIrql();
  v12 = *(_QWORD *)(a1 + 32);
  v60 = CurrentIrql;
  v13 = CurrentIrql >= 2u;
  v74 = 0;
  v77 = CurrentIrql >= 2u;
  v61 = *(_WORD *)(v12 + 92);
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v71 = (__int64 *)&v75;
  v73 = &v67;
  v16 = (__int64 *)&v65;
  v72 = (__int64 *)&v65;
  if ( !a2 )
  {
LABEL_19:
    *v6 += v9;
    if ( v8 )
    {
      *v16 = 0;
      if ( !*(_DWORD *)(a1 + 944) )
      {
        v23 = *(_QWORD *)(*(_QWORD *)(a1 + 288) + 256LL);
        if ( v23
          && !*(_BYTE *)(v23 + 24)
          && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v23 + 16), 1u) )
        {
          v50 = 2048;
          if ( v61 != 2 )
            LOWORD(v50) = -31011;
          v24 = a5;
          FlpFlsInterceptReceivePackets(*(_QWORD *)(a1 + 288), (_DWORD)v65, v49, v50, 0, v13, a5);
          ExReleaseRundownProtectionCacheAwareEx(
            *(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(*(_QWORD *)(a1 + 288) + 256LL) + 16LL),
            1u);
        }
        else
        {
          v24 = a5;
          FlpUpdateSlowPathCounters(CurrentProcessorNumber, v61, v10, a5, v13);
          v26 = *(_QWORD *)(a1 + 32);
          v25 = *(_QWORD *)(v26 + 216);
          LOBYTE(v26) = v13;
          v27 = *(__int64 (__fastcall **)())(*(_QWORD *)(v25 + 8) + 64LL);
          v28 = *(_QWORD *)(a1 + 304);
          if ( v27 == IpFlcReceivePackets )
            IppReceivePackets(v28, v65, v26, 0);
          else
            ((void (__fastcall *)(__int64, _QWORD *, __int64))v27)(v28, v65, v26);
        }
        goto LABEL_26;
      }
      if ( v65 )
      {
        v44 = v61;
        do
        {
          LOBYTE(v15) = v13;
          FlpSplitNetBufferListChainByIsolationId(
            a1,
            (unsigned int)&v65,
            v15,
            (unsigned int)&v66,
            (__int64)&v59,
            (__int64)&v74);
          v51 = v74;
          if ( v74 )
          {
            v36 = *(_QWORD *)(v74 + 256);
            if ( v36
              && !*(_BYTE *)(v36 + 24)
              && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v36 + 16), 1u) )
            {
              v54 = 2048;
              if ( v44 != 2 )
                LOWORD(v54) = -31011;
              FlpFlsInterceptReceivePackets(v51, v66, v53, v54, 0, v13, a5);
              ExReleaseRundownProtectionCacheAwareEx(
                *(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v51 + 256) + 16LL),
                1u);
            }
            else
            {
              FlpUpdateSlowPathCounters(CurrentProcessorNumber, v44, v59, a5, v13);
              v38 = *(_QWORD *)(a1 + 32);
              v37 = *(_QWORD *)(v38 + 216);
              LOBYTE(v38) = v13;
              v39 = *(__int64 (__fastcall **)())(*(_QWORD *)(v37 + 8) + 64LL);
              v40 = *(_QWORD *)(v51 + 144);
              if ( v39 == IpFlcReceivePackets )
                IppReceivePackets(v40, v66, v38, 0);
              else
                ((void (__fastcall *)(__int64, __int64, __int64))v39)(v40, v66, v38);
            }
            ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v51 + 56), v59);
          }
          else
          {
            FlpLogPacketDiscardWithType(*(_QWORD *)(a1 + 288), v66, 1, v59, 14, *(_DWORD *)(a1 + 1180), 3, -536854527);
            LOBYTE(v52) = v13;
            NetioDereferenceNetBufferListChain(v66, v52);
          }
        }
        while ( v65 );
      }
    }
    v24 = a5;
LABEL_26:
    if ( v67 )
    {
      *v73 = 0;
      if ( *(_DWORD *)(a1 + 944) )
      {
        if ( v67 )
        {
          do
          {
            LOBYTE(v15) = v13;
            FlpSplitNetBufferListChainByIsolationId(
              a1,
              (unsigned int)&v67,
              v15,
              (unsigned int)&v66,
              (__int64)&v59,
              (__int64)&v74);
            v56 = v74;
            v57 = v67;
            if ( v74 )
            {
              v41 = *(_QWORD *)(v74 + 256);
              if ( v41
                && !*(_BYTE *)(v41 + 24)
                && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v41 + 16), 1u) )
              {
                FlpFlsInterceptReceivePackets(v56, v57, v55, 2054, 0, v13, v24);
                ExReleaseRundownProtectionCacheAwareEx(
                  *(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v56 + 256) + 16LL),
                  1u);
              }
              else
              {
                LOBYTE(v55) = v13;
                (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)(a1 + 32) + 416LL))(v56, v66, v55);
              }
              ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v56 + 56), v59);
            }
            else
            {
              FlpLogPacketDiscardWithType(*(_QWORD *)(a1 + 288), v66, 1, v59, 14, *(_DWORD *)(a1 + 1180), 7, -536854527);
              LOBYTE(v58) = v13;
              NetioDereferenceNetBufferListChain(v66, v58);
            }
          }
          while ( v57 );
        }
      }
      else
      {
        v32 = *(_QWORD *)(*(_QWORD *)(a1 + 288) + 256LL);
        if ( v32
          && !*(_BYTE *)(v32 + 24)
          && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v32 + 16), 1u) )
        {
          FlpFlsInterceptReceivePackets(*(_QWORD *)(a1 + 288), v67, v15, 2054, 0, v13, v24);
          ExReleaseRundownProtectionCacheAwareEx(
            *(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(*(_QWORD *)(a1 + 288) + 256LL) + 16LL),
            1u);
        }
        else
        {
          LOBYTE(v15) = v13;
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)(a1 + 32) + 416LL))(
            *(_QWORD *)(a1 + 288),
            v67,
            v15);
        }
      }
    }
    if ( Count )
      ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 72), Count);
    v29 = a3;
    goto LABEL_30;
  }
  v17 = (__int64)a2;
  v18 = a5 & 2;
  do
  {
    a2 = (_QWORD *)*a2;
    v78 = a2;
    if ( **(_QWORD **)(v17 + 8) )
    {
      FlpLogPacketDiscardWithType(
        *(_QWORD *)(a1 + 288),
        v17,
        1,
        1,
        15,
        0,
        *(_DWORD *)(*(_QWORD *)(a1 + 288) + 204LL),
        -536854527);
      if ( (a5 & 2) == 0 )
      {
        v45 = v71;
        ++v64;
        v71 = (__int64 *)v17;
        *v45 = v17;
      }
LABEL_36:
      v18 = a5 & 2;
      goto LABEL_15;
    }
    if ( !(unsigned __int8)FlpParsePacket(
                             (unsigned int)&v76,
                             (unsigned int)&v68,
                             (unsigned int)&v62,
                             (unsigned int)&v63,
                             a1,
                             v17) )
    {
LABEL_35:
      if ( (a5 & 2) != 0 )
        goto LABEL_36;
      v42 = v71;
      ++v64;
      v71 = (__int64 *)v17;
      v18 = 0;
      *v42 = v17;
      goto LABEL_15;
    }
    if ( (unsigned __int8)FlpFilterInterface(a1) )
    {
      LOBYTE(v19) = v13;
      if ( !(unsigned __int8)FlpAcceptPacket(v76, v68, a1, v19, 0, v17) )
        goto LABEL_35;
      v18 = a5 & 2;
    }
    if ( v18 )
    {
      LOBYTE(v19) = v13;
      v30 = v17;
      v31 = NetioAllocateAndReferenceCopyNetBufferListEx(v17, FlpFreeNetBufferListChain, a1, v19);
      v17 = v31;
      if ( !v31 )
      {
        FlpLogPacketDiscardWithType(
          *(_QWORD *)(a1 + 288),
          v30,
          1,
          1,
          7,
          0,
          *(_DWORD *)(*(_QWORD *)(a1 + 288) + 204LL),
          -536854527);
        a2 = v78;
        goto LABEL_15;
      }
      NetioCopyNetBufferListInformation(v31, v30);
      ++Count;
      a2 = v78;
    }
    else
    {
      if ( a3 )
        NetioInitializeNetBufferListContext(v17, 0, a3, a1);
      *(_DWORD *)(v17 + 136) |= 0x20000000u;
    }
    FlpUpdateNblRealArrivalInterface(v17, a1);
    if ( v68 )
      *(_DWORD *)(v17 + 136) |= 0x40000000u;
    v20 = v62;
    ++v9;
    v21 = *(_QWORD *)(v17 + 8);
    *(_DWORD *)(v17 + 140) = 0;
    NetioAdvanceNetBuffer(v21, v20);
    if ( v63 == 2054 )
    {
      v22 = v73;
      v73 = (__int64 *)v17;
    }
    else
    {
      v22 = v72;
      ++v59;
      v72 = (__int64 *)v17;
    }
    *v22 = v17;
LABEL_15:
    v17 = (__int64)a2;
  }
  while ( a2 );
  if ( !v9 || ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 72), v9) )
  {
    v8 = v65;
    v10 = v59;
    v16 = v72;
    v6 = a4;
    goto LABEL_19;
  }
  v43 = v65;
  if ( v65 )
    FlpLogPacketDiscardWithType(*(_QWORD *)(a1 + 288), (_DWORD)v65, 1, v59, 8, 0, 3, -536854527);
  v46 = v67;
  if ( v67 )
    FlpLogPacketDiscardWithType(*(_QWORD *)(a1 + 288), v67, 1, v9 - v59, 8, 0, 7, -536854527);
  v29 = a3;
  *v72 = v46;
  v47 = v65;
  *v73 = 0;
  if ( v47 )
  {
    do
    {
      if ( a3 )
      {
        v48 = FlpCompleteNdisNetBufferListChain;
        if ( (a5 & 2) != 0 )
          v48 = (__int64 (__fastcall *)())NetioCompleteCopyNetBufferListChain;
        NetioUpdateNetBufferListContext(v47, v48, a1);
      }
      v47 = (_QWORD *)*v47;
    }
    while ( v47 );
    v13 = v77;
  }
  LOBYTE(v43) = v13;
  NetioDereferenceNetBufferListChain(v65, v43);
LABEL_30:
  if ( v75 )
  {
    v33 = v60 >= 2u;
    *v71 = 0;
    v34 = v75;
    for ( i = v75; i; i = (_QWORD *)*i )
      WfpNblInfoClearFlags(i, 1);
    if ( v29 )
    {
      FlpNdisReturnNetBufferListsWrapper(a1, v34, v33, v64);
    }
    else
    {
      LOBYTE(v14) = v13;
      NetioDereferenceNetBufferListChain(v34, v14);
    }
  }
}

```

## disassembly

```asm
0x1400cf8f4  mov     [rsp-8+arg_18], r9
0x1400cf8f9  mov     [rsp-8+arg_10], r8
0x1400cf8fe  push    rbp
0x1400cf8ff  push    rbx
0x1400cf900  push    rsi
0x1400cf901  push    rdi
0x1400cf902  push    r12
0x1400cf904  push    r13
0x1400cf906  push    r14
0x1400cf908  push    r15
0x1400cf90a  lea     rbp, [rsp-17h]
0x1400cf90f  sub     rsp, 0B8h
0x1400cf916  mov     rbx, rcx
0x1400cf919  mov     r12, r9
0x1400cf91c  xor     ecx, ecx
0x1400cf91e  mov     r14, rdx
0x1400cf921  mov     [rbp+4Fh+var_48], rcx
0x1400cf925  mov     edi, ecx
0x1400cf927  mov     [rbp+4Fh+var_80], ecx
0x1400cf92a  mov     r13d, ecx
0x1400cf92d  mov     [rbp+4Fh+var_A8], cx
0x1400cf931  mov     esi, ecx
0x1400cf933  mov     [rbp+4Fh+var_A4], cx
0x1400cf937  mov     [rbp+4Fh+var_50], rcx
0x1400cf93b  mov     [rbp+4Fh+var_88], rcx
0x1400cf93f  mov     [rbp+4Fh+var_98], rcx
0x1400cf943  mov     [rbp+4Fh+var_90], rcx
0x1400cf947  mov     [rbp+4Fh+var_A0], ecx
0x1400cf94a  mov     [rbp+4Fh+var_B0], ecx
0x1400cf94d  mov     [rbp+4Fh+Count], ecx
0x1400cf950  call    cs:__imp_KeGetCurrentIrql
0x1400cf957  nop     dword ptr [rax+rax+00h]
0x1400cf95c  mov     rcx, [rbx+20h]
0x1400cf960  cmp     al, 2
0x1400cf962  mov     [rbp+4Fh+var_AC], al
0x1400cf965  setnb   r15b
0x1400cf969  mov     [rbp+4Fh+var_58], rsi
0x1400cf96d  mov     [rbp+4Fh+arg_0], r15b
0x1400cf971  movzx   eax, word ptr [rcx+5Ch]
0x1400cf975  xor     ecx, ecx; ProcNumber
0x1400cf977  mov     [rbp+4Fh+var_AA], ax
0x1400cf97b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400cf982  nop     dword ptr [rax+rax+00h]
0x1400cf987  mov     [rbp+4Fh+var_78], eax
0x1400cf98a  lea     rcx, [rbp+4Fh+var_50]
0x1400cf98e  mov     [rbp+4Fh+var_70], rcx
0x1400cf992  lea     rax, [rbp+4Fh+var_88]
0x1400cf996  mov     [rbp+4Fh+var_60], rax
0x1400cf99a  lea     rax, [rbp+4Fh+var_98]
0x1400cf99e  mov     [rbp+4Fh+var_68], rax
0x1400cf9a2  test    r14, r14
0x1400cf9a5  jz      loc_1400CFABC
0x1400cf9ab  mov     r12d, [rbp+4Fh+arg_20]
0x1400cf9af  mov     rdi, r14
0x1400cf9b2  and     r12d, 2
0x1400cf9b6  mov     esi, r12d
0x1400cf9b9  mov     rax, [rdi+8]
0x1400cf9bd  mov     r14, [r14]
0x1400cf9c0  mov     [rbp+4Fh+arg_8], r14
0x1400cf9c4  cmp     qword ptr [rax], 0
0x1400cf9c8  jnz     loc_1401CC6AC
0x1400cf9ce  mov     [rsp+0F0h+var_C8], rdi
0x1400cf9d3  lea     r9, [rbp+4Fh+var_A4]
0x1400cf9d7  lea     r8, [rbp+4Fh+var_A8]
0x1400cf9db  mov     [rsp+0F0h+var_D0], rbx
0x1400cf9e0  lea     rdx, [rbp+4Fh+var_80]
0x1400cf9e4  lea     rcx, [rbp+4Fh+var_48]
0x1400cf9e8  call    FlpParsePacket
0x1400cf9ed  test    al, al
0x1400cf9ef  jz      loc_1400CFBE4
0x1400cf9f5  mov     rcx, rbx
0x1400cf9f8  call    FlpFilterInterface
0x1400cf9fd  test    al, al
0x1400cf9ff  jnz     loc_1400CFDAB
0x1400cfa05  test    esi, esi
0x1400cfa07  jnz     loc_1400CFB9B
0x1400cfa0d  mov     rax, [rbp+4Fh+arg_10]
0x1400cfa11  test    rax, rax
0x1400cfa14  jz      short loc_1400CFA2D
0x1400cfa16  mov     r9, rbx
0x1400cfa19  mov     r8, rax
0x1400cfa1c  xor     edx, edx
0x1400cfa1e  mov     rcx, rdi
0x1400cfa21  call    cs:__imp_NetioInitializeNetBufferListContext
0x1400cfa28  nop     dword ptr [rax+rax+00h]
0x1400cfa2d  bts     dword ptr [rdi+88h], 1Dh
0x1400cfa35  mov     rdx, rbx
0x1400cfa38  mov     rcx, rdi
0x1400cfa3b  call    FlpUpdateNblRealArrivalInterface
0x1400cfa40  cmp     [rbp+4Fh+var_80], 0
0x1400cfa44  jnz     loc_1400CFDD7
0x1400cfa4a  movzx   edx, [rbp+4Fh+var_A8]
0x1400cfa4e  inc     r13d
0x1400cfa51  mov     rcx, [rdi+8]
0x1400cfa55  mov     dword ptr [rdi+8Ch], 0
0x1400cfa5f  call    NetioAdvanceNetBuffer
0x1400cfa64  mov     eax, 806h
0x1400cfa69  cmp     [rbp+4Fh+var_A4], ax
0x1400cfa6d  jz      loc_1400CFC8A
0x1400cfa73  mov     rax, [rbp+4Fh+var_68]
0x1400cfa77  inc     [rbp+4Fh+var_B0]
0x1400cfa7a  mov     [rbp+4Fh+var_68], rdi
0x1400cfa7e  mov     [rax], rdi
0x1400cfa81  mov     rdi, r14
0x1400cfa84  test    r14, r14
0x1400cfa87  jnz     loc_1400CF9B9
0x1400cfa8d  test    r13d, r13d
0x1400cfa90  jz      short loc_1400CFAAD
0x1400cfa92  mov     rcx, [rbx+48h]; RunRefCacheAware
0x1400cfa96  mov     edx, r13d; Count
0x1400cfa99  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400cfaa0  nop     dword ptr [rax+rax+00h]
0x1400cfaa5  test    al, al
0x1400cfaa7  jz      loc_1400CFDF9
0x1400cfaad  mov     rdi, [rbp+4Fh+var_98]
0x1400cfab1  mov     esi, [rbp+4Fh+var_B0]
0x1400cfab4  mov     rax, [rbp+4Fh+var_68]
0x1400cfab8  mov     r12, [rbp+4Fh+arg_18]
0x1400cfabc  add     [r12], r13d
0x1400cfac0  xor     r13d, r13d
0x1400cfac3  test    rdi, rdi
0x1400cfac6  jz      short loc_1400CFB45
0x1400cfac8  mov     [rax], r13
0x1400cfacb  cmp     [rbx+3B0h], r13d
0x1400cfad2  jnz     loc_1400CFE45
0x1400cfad8  mov     rax, [rbx+120h]
0x1400cfadf  mov     rcx, [rax+100h]
0x1400cfae6  test    rcx, rcx
0x1400cfae9  jz      short loc_1400CFAF6
0x1400cfaeb  mov     al, [rcx+18h]
0x1400cfaee  test    al, al
0x1400cfaf0  jz      loc_1401CC7B5
0x1400cfaf6  mov     r14d, [rbp+4Fh+arg_20]
0x1400cfafa  mov     r8d, esi
0x1400cfafd  movzx   edx, [rbp+4Fh+var_AA]
0x1400cfb01  mov     r9d, r14d
0x1400cfb04  mov     ecx, [rbp+4Fh+var_78]
0x1400cfb07  mov     byte ptr [rsp+0F0h+var_D0], r15b
0x1400cfb0c  call    FlpUpdateSlowPathCounters
0x1400cfb11  mov     r8, [rbx+20h]
0x1400cfb15  lea     r12, IpFlcReceivePackets
0x1400cfb1c  mov     rdx, [rbp+4Fh+var_98]
0x1400cfb20  mov     rax, [r8+0D8h]
0x1400cfb27  mov     r8b, r15b
0x1400cfb2a  mov     rcx, [rax+8]
0x1400cfb2e  mov     rax, [rcx+40h]
0x1400cfb32  mov     rcx, [rbx+130h]
0x1400cfb39  cmp     rax, r12
0x1400cfb3c  jz      short loc_1400CFB7D
0x1400cfb3e  call    _guard_dispatch_icall
0x1400cfb43  jmp     short loc_1400CFB49
0x1400cfb45  mov     r14d, [rbp+4Fh+arg_20]
0x1400cfb49  cmp     [rbp+4Fh+var_88], r13
0x1400cfb4d  jnz     loc_1400CFBF5
0x1400cfb53  mov     eax, [rbp+4Fh+Count]
0x1400cfb56  test    eax, eax
0x1400cfb58  jnz     short loc_1400CFB87
0x1400cfb5a  mov     r12, [rbp+4Fh+arg_10]
0x1400cfb5e  cmp     [rbp+4Fh+var_50], r13
0x1400cfb62  jnz     loc_1400CFC97
0x1400cfb68  add     rsp, 0B8h
0x1400cfb6f  pop     r15
0x1400cfb71  pop     r14
0x1400cfb73  pop     r13
0x1400cfb75  pop     r12
0x1400cfb77  pop     rdi
0x1400cfb78  pop     rsi
0x1400cfb79  pop     rbx
0x1400cfb7a  pop     rbp
0x1400cfb7b  retn
0x1400cfb7d  xor     r9d, r9d
0x1400cfb80  call    IppReceivePackets
0x1400cfb85  jmp     short loc_1400CFB49
0x1400cfb87  mov     rcx, [rbx+48h]; RunRef
0x1400cfb8b  mov     edx, eax; Count
0x1400cfb8d  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400cfb94  nop     dword ptr [rax+rax+00h]
0x1400cfb99  jmp     short loc_1400CFB5A
0x1400cfb9b  mov     r9b, r15b
0x1400cfb9e  lea     rdx, FlpFreeNetBufferListChain
0x1400cfba5  mov     r8, rbx
0x1400cfba8  mov     rcx, rdi
0x1400cfbab  mov     r14, rdi
0x1400cfbae  call    cs:__imp_NetioAllocateAndReferenceCopyNetBufferListEx
0x1400cfbb5  nop     dword ptr [rax+rax+00h]
0x1400cfbba  mov     rdi, rax
0x1400cfbbd  mov     rdx, r14
0x1400cfbc0  test    rax, rax
0x1400cfbc3  jz      loc_1400CFC4A
0x1400cfbc9  mov     rcx, rax
0x1400cfbcc  call    cs:__imp_NetioCopyNetBufferListInformation
0x1400cfbd3  nop     dword ptr [rax+rax+00h]
0x1400cfbd8  inc     [rbp+4Fh+Count]
0x1400cfbdb  mov     r14, [rbp+4Fh+arg_8]
0x1400cfbdf  jmp     loc_1400CFA35
0x1400cfbe4  test    r12d, r12d
0x1400cfbe7  jz      loc_1400CFDE4
0x1400cfbed  mov     esi, r12d
0x1400cfbf0  jmp     loc_1400CFA81
0x1400cfbf5  mov     rax, [rbp+4Fh+var_60]
0x1400cfbf9  mov     [rax], r13
0x1400cfbfc  cmp     [rbx+3B0h], r13d
0x1400cfc03  jnz     loc_1400CFE6B
0x1400cfc09  mov     rax, [rbx+120h]
0x1400cfc10  mov     rcx, [rax+100h]
0x1400cfc17  test    rcx, rcx
0x1400cfc1a  jz      short loc_1400CFC27
0x1400cfc1c  mov     al, [rcx+18h]
0x1400cfc1f  test    al, al
0x1400cfc21  jz      loc_1401CC950
0x1400cfc27  mov     rax, [rbx+20h]
0x1400cfc2b  mov     r8b, r15b
0x1400cfc2e  mov     rdx, [rbp+4Fh+var_88]
0x1400cfc32  mov     rcx, [rbx+120h]
0x1400cfc39  mov     rax, [rax+1A0h]
0x1400cfc40  call    _guard_dispatch_icall
0x1400cfc45  jmp     loc_1400CFB53
0x1400cfc4a  mov     rcx, [rbx+120h]
0x1400cfc51  mov     r9d, 1
0x1400cfc57  mov     [rsp+0F0h+var_B8], 0E0004001h
0x1400cfc5f  mov     r8d, r9d
0x1400cfc62  mov     eax, [rcx+0CCh]
0x1400cfc68  mov     [rsp+0F0h+var_C0], eax
0x1400cfc6c  mov     dword ptr [rsp+0F0h+var_C8], 0
0x1400cfc74  mov     dword ptr [rsp+0F0h+var_D0], 7
0x1400cfc7c  call    FlpLogPacketDiscardWithType
0x1400cfc81  mov     r14, [rbp+4Fh+arg_8]
0x1400cfc85  jmp     loc_1400CFA81
0x1400cfc8a  mov     rax, [rbp+4Fh+var_60]
0x1400cfc8e  mov     [rbp+4Fh+var_60], rdi
0x1400cfc92  jmp     loc_1400CFA7E
0x1400cfc97  cmp     [rbp+4Fh+var_AC], 2
0x1400cfc9b  mov     r14d, r13d
0x1400cfc9e  mov     rax, [rbp+4Fh+var_70]
0x1400cfca2  setnb   r14b
0x1400cfca6  mov     [rax], r13
0x1400cfca9  mov     rsi, [rbp+4Fh+var_50]
0x1400cfcad  mov     rdi, rsi
0x1400cfcb0  test    rsi, rsi
0x1400cfcb3  jz      short loc_1400CFCD1
0x1400cfcb5  mov     edx, 1
0x1400cfcba  mov     rcx, rdi
0x1400cfcbd  call    cs:__imp_WfpNblInfoClearFlags
0x1400cfcc4  nop     dword ptr [rax+rax+00h]
0x1400cfcc9  mov     rdi, [rdi]
0x1400cfccc  test    rdi, rdi
0x1400cfccf  jnz     short loc_1400CFCB5
0x1400cfcd1  test    r12, r12
0x1400cfcd4  jz      loc_1401CCAA3
0x1400cfcda  mov     r9d, [rbp+4Fh+var_A0]
0x1400cfcde  mov     r8d, r14d
0x1400cfce1  mov     rdx, rsi
0x1400cfce4  mov     rcx, rbx
0x1400cfce7  call    FlpNdisReturnNetBufferListsWrapper
0x1400cfcec  jmp     loc_1400CFB68
0x1400cfcf1  mov     rcx, [rdi+100h]
0x1400cfcf8  test    rcx, rcx
0x1400cfcfb  jz      short loc_1400CFD08
0x1400cfcfd  mov     al, [rcx+18h]
0x1400cfd00  test    al, al
0x1400cfd02  jz      loc_1401CC8BC
0x1400cfd08  mov     r9d, [rbp+4Fh+arg_20]
0x1400cfd0c  movzx   edx, r13w
0x1400cfd10  mov     ecx, [rbp+4Fh+var_78]
0x1400cfd13  mov     r8d, [rbp+4Fh+var_B0]
0x1400cfd17  mov     byte ptr [rsp+0F0h+var_D0], r15b
0x1400cfd1c  call    FlpUpdateSlowPathCounters
0x1400cfd21  mov     r8, [rbx+20h]
0x1400cfd25  mov     rdx, [rbp+4Fh+var_90]
0x1400cfd29  mov     rax, [r8+0D8h]
0x1400cfd30  mov     r8b, r15b
0x1400cfd33  mov     rcx, [rax+8]
0x1400cfd37  mov     rax, [rcx+40h]
0x1400cfd3b  mov     rcx, [rdi+90h]
0x1400cfd42  cmp     rax, r12
0x1400cfd45  jnz     loc_1401CC925
0x1400cfd4b  xor     r9d, r9d
0x1400cfd4e  call    IppReceivePackets
0x1400cfd53  nop
0x1400cfd54  jmp     loc_1401CC92A
0x1400cfd59  mov     rcx, [rdi+100h]
0x1400cfd60  test    rcx, rcx
0x1400cfd63  jz      short loc_1400CFD70
0x1400cfd65  mov     al, [rcx+18h]
0x1400cfd68  test    al, al
0x1400cfd6a  jz      loc_1401CCA44
0x1400cfd70  mov     rax, [rbx+20h]
0x1400cfd74  mov     r8b, r15b
0x1400cfd77  mov     rdx, [rbp+4Fh+var_90]
0x1400cfd7b  mov     rcx, rdi
0x1400cfd7e  mov     rax, [rax+1A0h]
0x1400cfd85  call    _guard_dispatch_icall
0x1400cfd8a  mov     edx, [rbp+4Fh+var_B0]; Count
0x1400cfd8d  mov     rcx, [rdi+38h]; RunRef
0x1400cfd91  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400cfd98  nop     dword ptr [rax+rax+00h]
0x1400cfd9d  test    rsi, rsi
0x1400cfda0  jnz     loc_1401CC9BB
0x1400cfda6  jmp     loc_1400CFB53
0x1400cfdab  mov     edx, [rbp+4Fh+var_80]
  ... truncated ...
```
