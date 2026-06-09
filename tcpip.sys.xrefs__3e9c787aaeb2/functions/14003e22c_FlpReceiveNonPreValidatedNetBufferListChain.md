# FlpReceiveNonPreValidatedNetBufferListChain

- ea: `0x14003e22c`
- end: `0x14003e7b2`
- name: `FlpReceiveNonPreValidatedNetBufferListChain`
- size: `1414`
- prototype: `void __fastcall(__int64, _QWORD *, __int64, _DWORD *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400ffc20`

## callees

- `0x14003d510`
- `0x14003d600`
- `0x14003e22c`
- `0x14003e7c0`
- `0x14003e7f0`
- `0x14003e8b0`
- `0x14004c0b0`
- `0x14007ef10`
- `0x1400cc4b0`
- `0x140126cc4`
- `0x14014b8b0`
- `0x14014b9e4`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14003e3d1`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401c54f2`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401c55f9`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401c568d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401c5781`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14003e3d1`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401c54f2`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401c55f9`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401c568d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401c5781`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003e2b3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14003e2b3`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003e288`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003e288`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14003e4c5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14003e6c9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401c555a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401c564b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401c5665`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401c56dd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401c57c5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14003e4c5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14003e6c9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401c555a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401c564b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401c5665`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401c56dd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401c57c5`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401c54d7`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401c55df`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401c5766`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401c57dd`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401c54d7`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401c55df`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401c5766`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401c57dd`
- `NETIO!NetioCopyNetBufferListInformation` at `0x14003e504`
- `NETIO!NetioCopyNetBufferListInformation` at `0x14003e504`
- `NETIO!NetioCompleteCopyNetBufferListChain` at `0x1401c54b0`
- `NETIO!NetioAllocateAndReferenceCopyNetBufferListEx` at `0x14003e4e6`
- `NETIO!NetioAllocateAndReferenceCopyNetBufferListEx` at `0x14003e4e6`
- `NETIO!NetioInitializeNetBufferListContext` at `0x14003e359`
- `NETIO!NetioInitializeNetBufferListContext` at `0x14003e359`
- `NETIO!NetioUpdateNetBufferListContext` at `0x1401c54b8`
- `NETIO!NetioUpdateNetBufferListContext` at `0x1401c54b8`
- `NETIO!WfpNblInfoClearFlags` at `0x14003e5f5`
- `NETIO!WfpNblInfoClearFlags` at `0x14003e5f5`

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
  bool v13; // r15
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
  unsigned __int16 v62[2]; // [rsp+48h] [rbp-59h] BYREF
  __int16 v63; // [rsp+4Ch] [rbp-55h] BYREF
  unsigned int v64; // [rsp+50h] [rbp-51h]
  _QWORD *v65; // [rsp+58h] [rbp-49h] BYREF
  _QWORD *v66; // [rsp+60h] [rbp-41h] BYREF
  __int64 v67; // [rsp+68h] [rbp-39h] BYREF
  int v68; // [rsp+70h] [rbp-31h] BYREF
  ULONG Count; // [rsp+74h] [rbp-2Dh]
  ULONG CurrentProcessorNumber; // [rsp+78h] [rbp-29h]
  __int64 *v71; // [rsp+80h] [rbp-21h]
  __int64 *v72; // [rsp+88h] [rbp-19h]
  __int64 *v73; // [rsp+90h] [rbp-11h]
  __int64 v74; // [rsp+98h] [rbp-9h] BYREF
  _QWORD *v75; // [rsp+A0h] [rbp-1h] BYREF
  __int64 v76[9]; // [rsp+A8h] [rbp+7h] BYREF
  bool v77; // [rsp+100h] [rbp+5Fh]
  _QWORD *v78; // [rsp+108h] [rbp+67h]

  v6 = a4;
  v76[0] = 0;
  v8 = 0;
  v68 = 0;
  v9 = 0;
  v62[0] = 0;
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
            IppReceivePackets(v28, v65, v13, 0);
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
              FlpFlsInterceptReceivePackets(v51, (_DWORD)v66, v53, v54, 0, v13, a5);
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
                IppReceivePackets(v40, v66, v13, 0);
              else
                ((void (__fastcall *)(__int64, _QWORD *, __int64))v39)(v40, v66, v38);
            }
            ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v51 + 56), v59);
          }
          else
          {
            FlpLogPacketDiscardWithType(
              *(_QWORD *)(a1 + 288),
              (_DWORD)v66,
              1,
              v59,
              14,
              *(_DWORD *)(a1 + 1180),
              3,
              -536854527);
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
                (*(void (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)(a1 + 32) + 416LL))(v56, v66, v55);
              }
              ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v56 + 56), v59);
            }
            else
            {
              FlpLogPacketDiscardWithType(
                *(_QWORD *)(a1 + 288),
                (_DWORD)v66,
                1,
                v59,
                14,
                *(_DWORD *)(a1 + 1180),
                7,
                -536854527);
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
    if ( !FlpParsePacket(v76, &v68, v62, &v63, a1, v17) )
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
      if ( !(unsigned __int8)FlpAcceptPacket(v76[0], v68, a1, v19, 0, v17) )
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
    v20 = v62[0];
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
0x14003e22c  mov     [rsp-8+arg_18], r9
0x14003e231  mov     [rsp-8+arg_10], r8
0x14003e236  push    rbp
0x14003e237  push    rbx
0x14003e238  push    rsi
0x14003e239  push    rdi
0x14003e23a  push    r12
0x14003e23c  push    r13
0x14003e23e  push    r14
0x14003e240  push    r15
0x14003e242  lea     rbp, [rsp-17h]
0x14003e247  sub     rsp, 0B8h
0x14003e24e  mov     rbx, rcx
0x14003e251  mov     r12, r9
0x14003e254  xor     ecx, ecx
0x14003e256  mov     r14, rdx
0x14003e259  mov     [rbp+4Fh+var_48], rcx
0x14003e25d  mov     edi, ecx
0x14003e25f  mov     [rbp+4Fh+var_80], ecx
0x14003e262  mov     r13d, ecx
0x14003e265  mov     [rbp+4Fh+var_A8], cx
0x14003e269  mov     esi, ecx
0x14003e26b  mov     [rbp+4Fh+var_A4], cx
0x14003e26f  mov     [rbp+4Fh+var_50], rcx
0x14003e273  mov     [rbp+4Fh+var_88], rcx
0x14003e277  mov     [rbp+4Fh+var_98], rcx
0x14003e27b  mov     [rbp+4Fh+var_90], rcx
0x14003e27f  mov     [rbp+4Fh+var_A0], ecx
0x14003e282  mov     [rbp+4Fh+var_B0], ecx
0x14003e285  mov     [rbp+4Fh+Count], ecx
0x14003e288  call    cs:__imp_KeGetCurrentIrql
0x14003e28f  nop     dword ptr [rax+rax+00h]
0x14003e294  mov     rcx, [rbx+20h]
0x14003e298  cmp     al, 2
0x14003e29a  mov     [rbp+4Fh+var_AC], al
0x14003e29d  setnb   r15b
0x14003e2a1  mov     [rbp+4Fh+var_58], rsi
0x14003e2a5  mov     [rbp+4Fh+arg_0], r15b
0x14003e2a9  movzx   eax, word ptr [rcx+5Ch]
0x14003e2ad  xor     ecx, ecx; ProcNumber
0x14003e2af  mov     [rbp+4Fh+var_AA], ax
0x14003e2b3  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14003e2ba  nop     dword ptr [rax+rax+00h]
0x14003e2bf  mov     [rbp+4Fh+var_78], eax
0x14003e2c2  lea     rcx, [rbp+4Fh+var_50]
0x14003e2c6  mov     [rbp+4Fh+var_70], rcx
0x14003e2ca  lea     rax, [rbp+4Fh+var_88]
0x14003e2ce  mov     [rbp+4Fh+var_60], rax
0x14003e2d2  lea     rax, [rbp+4Fh+var_98]
0x14003e2d6  mov     [rbp+4Fh+var_68], rax
0x14003e2da  test    r14, r14
0x14003e2dd  jz      loc_14003E3F4
0x14003e2e3  mov     r12d, [rbp+4Fh+arg_20]
0x14003e2e7  mov     rdi, r14
0x14003e2ea  and     r12d, 2
0x14003e2ee  mov     esi, r12d
0x14003e2f1  mov     rax, [rdi+8]
0x14003e2f5  mov     r14, [r14]
0x14003e2f8  mov     [rbp+4Fh+arg_8], r14
0x14003e2fc  cmp     qword ptr [rax], 0
0x14003e300  jnz     loc_1401C53E0
0x14003e306  mov     [rsp+0F0h+var_C8], rdi
0x14003e30b  lea     r9, [rbp+4Fh+var_A4]
0x14003e30f  lea     r8, [rbp+4Fh+var_A8]
0x14003e313  mov     [rsp+0F0h+var_D0], rbx
0x14003e318  lea     rdx, [rbp+4Fh+var_80]
0x14003e31c  lea     rcx, [rbp+4Fh+var_48]
0x14003e320  call    FlpParsePacket
0x14003e325  test    al, al
0x14003e327  jz      loc_14003E51C
0x14003e32d  mov     rcx, rbx
0x14003e330  call    FlpFilterInterface
0x14003e335  test    al, al
0x14003e337  jnz     loc_14003E6E3
0x14003e33d  test    esi, esi
0x14003e33f  jnz     loc_14003E4D3
0x14003e345  mov     rax, [rbp+4Fh+arg_10]
0x14003e349  test    rax, rax
0x14003e34c  jz      short loc_14003E365
0x14003e34e  mov     r9, rbx
0x14003e351  mov     r8, rax
0x14003e354  xor     edx, edx
0x14003e356  mov     rcx, rdi
0x14003e359  call    cs:__imp_NetioInitializeNetBufferListContext
0x14003e360  nop     dword ptr [rax+rax+00h]
0x14003e365  bts     dword ptr [rdi+88h], 1Dh
0x14003e36d  mov     rdx, rbx
0x14003e370  mov     rcx, rdi
0x14003e373  call    FlpUpdateNblRealArrivalInterface
0x14003e378  cmp     [rbp+4Fh+var_80], 0
0x14003e37c  jnz     loc_14003E70F
0x14003e382  movzx   edx, [rbp+4Fh+var_A8]
0x14003e386  inc     r13d
0x14003e389  mov     rcx, [rdi+8]
0x14003e38d  mov     dword ptr [rdi+8Ch], 0
0x14003e397  call    NetioAdvanceNetBuffer
0x14003e39c  mov     eax, 806h
0x14003e3a1  cmp     [rbp+4Fh+var_A4], ax
0x14003e3a5  jz      loc_14003E5C2
0x14003e3ab  mov     rax, [rbp+4Fh+var_68]
0x14003e3af  inc     [rbp+4Fh+var_B0]
0x14003e3b2  mov     [rbp+4Fh+var_68], rdi
0x14003e3b6  mov     [rax], rdi
0x14003e3b9  mov     rdi, r14
0x14003e3bc  test    r14, r14
0x14003e3bf  jnz     loc_14003E2F1
0x14003e3c5  test    r13d, r13d
0x14003e3c8  jz      short loc_14003E3E5
0x14003e3ca  mov     rcx, [rbx+48h]; RunRefCacheAware
0x14003e3ce  mov     edx, r13d; Count
0x14003e3d1  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x14003e3d8  nop     dword ptr [rax+rax+00h]
0x14003e3dd  test    al, al
0x14003e3df  jz      loc_14003E731
0x14003e3e5  mov     rdi, [rbp+4Fh+var_98]
0x14003e3e9  mov     esi, [rbp+4Fh+var_B0]
0x14003e3ec  mov     rax, [rbp+4Fh+var_68]
0x14003e3f0  mov     r12, [rbp+4Fh+arg_18]
0x14003e3f4  add     [r12], r13d
0x14003e3f8  xor     r13d, r13d
0x14003e3fb  test    rdi, rdi
0x14003e3fe  jz      short loc_14003E47D
0x14003e400  mov     [rax], r13
0x14003e403  cmp     [rbx+3B0h], r13d
0x14003e40a  jnz     loc_14003E77D
0x14003e410  mov     rax, [rbx+120h]
0x14003e417  mov     rcx, [rax+100h]
0x14003e41e  test    rcx, rcx
0x14003e421  jz      short loc_14003E42E
0x14003e423  mov     al, [rcx+18h]
0x14003e426  test    al, al
0x14003e428  jz      loc_1401C54E9
0x14003e42e  mov     r14d, [rbp+4Fh+arg_20]
0x14003e432  mov     r8d, esi
0x14003e435  movzx   edx, [rbp+4Fh+var_AA]
0x14003e439  mov     r9d, r14d
0x14003e43c  mov     ecx, [rbp+4Fh+var_78]
0x14003e43f  mov     byte ptr [rsp+0F0h+var_D0], r15b
0x14003e444  call    FlpUpdateSlowPathCounters
0x14003e449  mov     r8, [rbx+20h]
0x14003e44d  lea     r12, IpFlcReceivePackets
0x14003e454  mov     rdx, [rbp+4Fh+var_98]
0x14003e458  mov     rax, [r8+0D8h]
0x14003e45f  mov     r8b, r15b
0x14003e462  mov     rcx, [rax+8]
0x14003e466  mov     rax, [rcx+40h]
0x14003e46a  mov     rcx, [rbx+130h]
0x14003e471  cmp     rax, r12
0x14003e474  jz      short loc_14003E4B5
0x14003e476  call    _guard_dispatch_icall
0x14003e47b  jmp     short loc_14003E481
0x14003e47d  mov     r14d, [rbp+4Fh+arg_20]
0x14003e481  cmp     [rbp+4Fh+var_88], r13
0x14003e485  jnz     loc_14003E52D
0x14003e48b  mov     eax, [rbp+4Fh+Count]
0x14003e48e  test    eax, eax
0x14003e490  jnz     short loc_14003E4BF
0x14003e492  mov     r12, [rbp+4Fh+arg_10]
0x14003e496  cmp     [rbp+4Fh+var_50], r13
0x14003e49a  jnz     loc_14003E5CF
0x14003e4a0  add     rsp, 0B8h
0x14003e4a7  pop     r15
0x14003e4a9  pop     r14
0x14003e4ab  pop     r13
0x14003e4ad  pop     r12
0x14003e4af  pop     rdi
0x14003e4b0  pop     rsi
0x14003e4b1  pop     rbx
0x14003e4b2  pop     rbp
0x14003e4b3  retn
0x14003e4b5  xor     r9d, r9d
0x14003e4b8  call    IppReceivePackets
0x14003e4bd  jmp     short loc_14003E481
0x14003e4bf  mov     rcx, [rbx+48h]; RunRef
0x14003e4c3  mov     edx, eax; Count
0x14003e4c5  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x14003e4cc  nop     dword ptr [rax+rax+00h]
0x14003e4d1  jmp     short loc_14003E492
0x14003e4d3  mov     r9b, r15b
0x14003e4d6  lea     rdx, FlpFreeNetBufferListChain
0x14003e4dd  mov     r8, rbx
0x14003e4e0  mov     rcx, rdi
0x14003e4e3  mov     r14, rdi
0x14003e4e6  call    cs:__imp_NetioAllocateAndReferenceCopyNetBufferListEx
0x14003e4ed  nop     dword ptr [rax+rax+00h]
0x14003e4f2  mov     rdi, rax
0x14003e4f5  mov     rdx, r14
0x14003e4f8  test    rax, rax
0x14003e4fb  jz      loc_14003E582
0x14003e501  mov     rcx, rax
0x14003e504  call    cs:__imp_NetioCopyNetBufferListInformation
0x14003e50b  nop     dword ptr [rax+rax+00h]
0x14003e510  inc     [rbp+4Fh+Count]
0x14003e513  mov     r14, [rbp+4Fh+arg_8]
0x14003e517  jmp     loc_14003E36D
0x14003e51c  test    r12d, r12d
0x14003e51f  jz      loc_14003E71C
0x14003e525  mov     esi, r12d
0x14003e528  jmp     loc_14003E3B9
0x14003e52d  mov     rax, [rbp+4Fh+var_60]
0x14003e531  mov     [rax], r13
0x14003e534  cmp     [rbx+3B0h], r13d
0x14003e53b  jnz     loc_14003E7A3
0x14003e541  mov     rax, [rbx+120h]
0x14003e548  mov     rcx, [rax+100h]
0x14003e54f  test    rcx, rcx
0x14003e552  jz      short loc_14003E55F
0x14003e554  mov     al, [rcx+18h]
0x14003e557  test    al, al
0x14003e559  jz      loc_1401C5684
0x14003e55f  mov     rax, [rbx+20h]
0x14003e563  mov     r8b, r15b
0x14003e566  mov     rdx, [rbp+4Fh+var_88]
0x14003e56a  mov     rcx, [rbx+120h]
0x14003e571  mov     rax, [rax+1A0h]
0x14003e578  call    _guard_dispatch_icall
0x14003e57d  jmp     loc_14003E48B
0x14003e582  mov     rcx, [rbx+120h]
0x14003e589  mov     r9d, 1
0x14003e58f  mov     [rsp+0F0h+var_B8], 0E0004001h
0x14003e597  mov     r8d, r9d
0x14003e59a  mov     eax, [rcx+0CCh]
0x14003e5a0  mov     [rsp+0F0h+var_C0], eax
0x14003e5a4  mov     dword ptr [rsp+0F0h+var_C8], 0
0x14003e5ac  mov     dword ptr [rsp+0F0h+var_D0], 7
0x14003e5b4  call    FlpLogPacketDiscardWithType
0x14003e5b9  mov     r14, [rbp+4Fh+arg_8]
0x14003e5bd  jmp     loc_14003E3B9
0x14003e5c2  mov     rax, [rbp+4Fh+var_60]
0x14003e5c6  mov     [rbp+4Fh+var_60], rdi
0x14003e5ca  jmp     loc_14003E3B6
0x14003e5cf  cmp     [rbp+4Fh+var_AC], 2
0x14003e5d3  mov     r14d, r13d
0x14003e5d6  mov     rax, [rbp+4Fh+var_70]
0x14003e5da  setnb   r14b
0x14003e5de  mov     [rax], r13
0x14003e5e1  mov     rsi, [rbp+4Fh+var_50]
0x14003e5e5  mov     rdi, rsi
0x14003e5e8  test    rsi, rsi
0x14003e5eb  jz      short loc_14003E609
0x14003e5ed  mov     edx, 1
0x14003e5f2  mov     rcx, rdi
0x14003e5f5  call    cs:__imp_WfpNblInfoClearFlags
0x14003e5fc  nop     dword ptr [rax+rax+00h]
0x14003e601  mov     rdi, [rdi]
0x14003e604  test    rdi, rdi
0x14003e607  jnz     short loc_14003E5ED
0x14003e609  test    r12, r12
0x14003e60c  jz      loc_1401C57D7
0x14003e612  mov     r9d, [rbp+4Fh+var_A0]
0x14003e616  mov     r8d, r14d
0x14003e619  mov     rdx, rsi
0x14003e61c  mov     rcx, rbx
0x14003e61f  call    FlpNdisReturnNetBufferListsWrapper
0x14003e624  jmp     loc_14003E4A0
0x14003e629  mov     rcx, [rdi+100h]
0x14003e630  test    rcx, rcx
0x14003e633  jz      short loc_14003E640
0x14003e635  mov     al, [rcx+18h]
0x14003e638  test    al, al
0x14003e63a  jz      loc_1401C55F0
0x14003e640  mov     r9d, [rbp+4Fh+arg_20]
0x14003e644  movzx   edx, r13w
0x14003e648  mov     ecx, [rbp+4Fh+var_78]
0x14003e64b  mov     r8d, [rbp+4Fh+var_B0]
0x14003e64f  mov     byte ptr [rsp+0F0h+var_D0], r15b
0x14003e654  call    FlpUpdateSlowPathCounters
0x14003e659  mov     r8, [rbx+20h]
0x14003e65d  mov     rdx, [rbp+4Fh+var_90]
0x14003e661  mov     rax, [r8+0D8h]
0x14003e668  mov     r8b, r15b
0x14003e66b  mov     rcx, [rax+8]
0x14003e66f  mov     rax, [rcx+40h]
0x14003e673  mov     rcx, [rdi+90h]
0x14003e67a  cmp     rax, r12
0x14003e67d  jnz     loc_1401C5659
0x14003e683  xor     r9d, r9d
0x14003e686  call    IppReceivePackets
0x14003e68b  nop
0x14003e68c  jmp     loc_1401C565E
0x14003e691  mov     rcx, [rdi+100h]
0x14003e698  test    rcx, rcx
0x14003e69b  jz      short loc_14003E6A8
0x14003e69d  mov     al, [rcx+18h]
0x14003e6a0  test    al, al
0x14003e6a2  jz      loc_1401C5778
0x14003e6a8  mov     rax, [rbx+20h]
0x14003e6ac  mov     r8b, r15b
0x14003e6af  mov     rdx, [rbp+4Fh+var_90]
0x14003e6b3  mov     rcx, rdi
0x14003e6b6  mov     rax, [rax+1A0h]
0x14003e6bd  call    _guard_dispatch_icall
0x14003e6c2  mov     edx, [rbp+4Fh+var_B0]; Count
0x14003e6c5  mov     rcx, [rdi+38h]; RunRef
0x14003e6c9  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x14003e6d0  nop     dword ptr [rax+rax+00h]
0x14003e6d5  test    rsi, rsi
0x14003e6d8  jnz     loc_1401C56EF
0x14003e6de  jmp     loc_14003E48B
0x14003e6e3  mov     edx, [rbp+4Fh+var_80]
  ... truncated ...
```
