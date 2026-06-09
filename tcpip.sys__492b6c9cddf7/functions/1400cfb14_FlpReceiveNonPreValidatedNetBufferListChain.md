# FlpReceiveNonPreValidatedNetBufferListChain

- ea: `0x1400cfb14`
- end: `0x1400d009a`
- name: `FlpReceiveNonPreValidatedNetBufferListChain`
- size: `1414`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400ce290`

## callees

- `0x140063050`
- `0x140090f50`
- `0x140091040`
- `0x1400c28c0`
- `0x1400cfb14`
- `0x1400d00a0`
- `0x1400d00d0`
- `0x1400d0190`
- `0x1400d01e0`
- `0x14011fcfc`
- `0x140149630`
- `0x140149764`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400cfcb9`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc69a`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc7a1`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc835`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc929`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400cfcb9`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc69a`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc7a1`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc835`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401cc929`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400cfdad`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400cffb1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc702`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc7f3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc80d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc885`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc96d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400cfdad`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400cffb1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc702`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc7f3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc80d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc885`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401cc96d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400cfb9b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400cfb9b`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400cfb70`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400cfb70`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc67f`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc787`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc90e`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc985`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc67f`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc787`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc90e`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1401cc985`
- `NETIO!NetioCopyNetBufferListInformation` at `0x1400cfdec`
- `NETIO!NetioCopyNetBufferListInformation` at `0x1400cfdec`
- `NETIO!NetioCompleteCopyNetBufferListChain` at `0x1401cc658`
- `NETIO!NetioAllocateAndReferenceCopyNetBufferListEx` at `0x1400cfdce`
- `NETIO!NetioAllocateAndReferenceCopyNetBufferListEx` at `0x1400cfdce`
- `NETIO!NetioInitializeNetBufferListContext` at `0x1400cfc41`
- `NETIO!NetioInitializeNetBufferListContext` at `0x1400cfc41`
- `NETIO!NetioUpdateNetBufferListContext` at `0x1401cc660`
- `NETIO!NetioUpdateNetBufferListContext` at `0x1401cc660`
- `NETIO!WfpNblInfoClearFlags` at `0x1400cfedd`
- `NETIO!WfpNblInfoClearFlags` at `0x1400cfedd`

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
0x1400cfb14  mov     [rsp-8+arg_18], r9
0x1400cfb19  mov     [rsp-8+arg_10], r8
0x1400cfb1e  push    rbp
0x1400cfb1f  push    rbx
0x1400cfb20  push    rsi
0x1400cfb21  push    rdi
0x1400cfb22  push    r12
0x1400cfb24  push    r13
0x1400cfb26  push    r14
0x1400cfb28  push    r15
0x1400cfb2a  lea     rbp, [rsp-17h]
0x1400cfb2f  sub     rsp, 0B8h
0x1400cfb36  mov     rbx, rcx
0x1400cfb39  mov     r12, r9
0x1400cfb3c  xor     ecx, ecx
0x1400cfb3e  mov     r14, rdx
0x1400cfb41  mov     [rbp+4Fh+var_48], rcx
0x1400cfb45  mov     edi, ecx
0x1400cfb47  mov     [rbp+4Fh+var_80], ecx
0x1400cfb4a  mov     r13d, ecx
0x1400cfb4d  mov     [rbp+4Fh+var_A8], cx
0x1400cfb51  mov     esi, ecx
0x1400cfb53  mov     [rbp+4Fh+var_A4], cx
0x1400cfb57  mov     [rbp+4Fh+var_50], rcx
0x1400cfb5b  mov     [rbp+4Fh+var_88], rcx
0x1400cfb5f  mov     [rbp+4Fh+var_98], rcx
0x1400cfb63  mov     [rbp+4Fh+var_90], rcx
0x1400cfb67  mov     [rbp+4Fh+var_A0], ecx
0x1400cfb6a  mov     [rbp+4Fh+var_B0], ecx
0x1400cfb6d  mov     [rbp+4Fh+Count], ecx
0x1400cfb70  call    cs:__imp_KeGetCurrentIrql
0x1400cfb77  nop     dword ptr [rax+rax+00h]
0x1400cfb7c  mov     rcx, [rbx+20h]
0x1400cfb80  cmp     al, 2
0x1400cfb82  mov     [rbp+4Fh+var_AC], al
0x1400cfb85  setnb   r15b
0x1400cfb89  mov     [rbp+4Fh+var_58], rsi
0x1400cfb8d  mov     [rbp+4Fh+arg_0], r15b
0x1400cfb91  movzx   eax, word ptr [rcx+5Ch]
0x1400cfb95  xor     ecx, ecx; ProcNumber
0x1400cfb97  mov     [rbp+4Fh+var_AA], ax
0x1400cfb9b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400cfba2  nop     dword ptr [rax+rax+00h]
0x1400cfba7  mov     [rbp+4Fh+var_78], eax
0x1400cfbaa  lea     rcx, [rbp+4Fh+var_50]
0x1400cfbae  mov     [rbp+4Fh+var_70], rcx
0x1400cfbb2  lea     rax, [rbp+4Fh+var_88]
0x1400cfbb6  mov     [rbp+4Fh+var_60], rax
0x1400cfbba  lea     rax, [rbp+4Fh+var_98]
0x1400cfbbe  mov     [rbp+4Fh+var_68], rax
0x1400cfbc2  test    r14, r14
0x1400cfbc5  jz      loc_1400CFCDC
0x1400cfbcb  mov     r12d, [rbp+4Fh+arg_20]
0x1400cfbcf  mov     rdi, r14
0x1400cfbd2  and     r12d, 2
0x1400cfbd6  mov     esi, r12d
0x1400cfbd9  mov     rax, [rdi+8]
0x1400cfbdd  mov     r14, [r14]
0x1400cfbe0  mov     [rbp+4Fh+arg_8], r14
0x1400cfbe4  cmp     qword ptr [rax], 0
0x1400cfbe8  jnz     loc_1401CC588
0x1400cfbee  mov     [rsp+0F0h+var_C8], rdi
0x1400cfbf3  lea     r9, [rbp+4Fh+var_A4]
0x1400cfbf7  lea     r8, [rbp+4Fh+var_A8]
0x1400cfbfb  mov     [rsp+0F0h+var_D0], rbx
0x1400cfc00  lea     rdx, [rbp+4Fh+var_80]
0x1400cfc04  lea     rcx, [rbp+4Fh+var_48]
0x1400cfc08  call    FlpParsePacket
0x1400cfc0d  test    al, al
0x1400cfc0f  jz      loc_1400CFE04
0x1400cfc15  mov     rcx, rbx
0x1400cfc18  call    FlpFilterInterface
0x1400cfc1d  test    al, al
0x1400cfc1f  jnz     loc_1400CFFCB
0x1400cfc25  test    esi, esi
0x1400cfc27  jnz     loc_1400CFDBB
0x1400cfc2d  mov     rax, [rbp+4Fh+arg_10]
0x1400cfc31  test    rax, rax
0x1400cfc34  jz      short loc_1400CFC4D
0x1400cfc36  mov     r9, rbx
0x1400cfc39  mov     r8, rax
0x1400cfc3c  xor     edx, edx
0x1400cfc3e  mov     rcx, rdi
0x1400cfc41  call    cs:__imp_NetioInitializeNetBufferListContext
0x1400cfc48  nop     dword ptr [rax+rax+00h]
0x1400cfc4d  bts     dword ptr [rdi+88h], 1Dh
0x1400cfc55  mov     rdx, rbx
0x1400cfc58  mov     rcx, rdi
0x1400cfc5b  call    FlpUpdateNblRealArrivalInterface
0x1400cfc60  cmp     [rbp+4Fh+var_80], 0
0x1400cfc64  jnz     loc_1400CFFF7
0x1400cfc6a  movzx   edx, [rbp+4Fh+var_A8]
0x1400cfc6e  inc     r13d
0x1400cfc71  mov     rcx, [rdi+8]
0x1400cfc75  mov     dword ptr [rdi+8Ch], 0
0x1400cfc7f  call    NetioAdvanceNetBuffer
0x1400cfc84  mov     eax, 806h
0x1400cfc89  cmp     [rbp+4Fh+var_A4], ax
0x1400cfc8d  jz      loc_1400CFEAA
0x1400cfc93  mov     rax, [rbp+4Fh+var_68]
0x1400cfc97  inc     [rbp+4Fh+var_B0]
0x1400cfc9a  mov     [rbp+4Fh+var_68], rdi
0x1400cfc9e  mov     [rax], rdi
0x1400cfca1  mov     rdi, r14
0x1400cfca4  test    r14, r14
0x1400cfca7  jnz     loc_1400CFBD9
0x1400cfcad  test    r13d, r13d
0x1400cfcb0  jz      short loc_1400CFCCD
0x1400cfcb2  mov     rcx, [rbx+48h]; RunRefCacheAware
0x1400cfcb6  mov     edx, r13d; Count
0x1400cfcb9  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400cfcc0  nop     dword ptr [rax+rax+00h]
0x1400cfcc5  test    al, al
0x1400cfcc7  jz      loc_1400D0019
0x1400cfccd  mov     rdi, [rbp+4Fh+var_98]
0x1400cfcd1  mov     esi, [rbp+4Fh+var_B0]
0x1400cfcd4  mov     rax, [rbp+4Fh+var_68]
0x1400cfcd8  mov     r12, [rbp+4Fh+arg_18]
0x1400cfcdc  add     [r12], r13d
0x1400cfce0  xor     r13d, r13d
0x1400cfce3  test    rdi, rdi
0x1400cfce6  jz      short loc_1400CFD65
0x1400cfce8  mov     [rax], r13
0x1400cfceb  cmp     [rbx+3B0h], r13d
0x1400cfcf2  jnz     loc_1400D0065
0x1400cfcf8  mov     rax, [rbx+120h]
0x1400cfcff  mov     rcx, [rax+100h]
0x1400cfd06  test    rcx, rcx
0x1400cfd09  jz      short loc_1400CFD16
0x1400cfd0b  mov     al, [rcx+18h]
0x1400cfd0e  test    al, al
0x1400cfd10  jz      loc_1401CC691
0x1400cfd16  mov     r14d, [rbp+4Fh+arg_20]
0x1400cfd1a  mov     r8d, esi
0x1400cfd1d  movzx   edx, [rbp+4Fh+var_AA]
0x1400cfd21  mov     r9d, r14d
0x1400cfd24  mov     ecx, [rbp+4Fh+var_78]
0x1400cfd27  mov     byte ptr [rsp+0F0h+var_D0], r15b
0x1400cfd2c  call    FlpUpdateSlowPathCounters
0x1400cfd31  mov     r8, [rbx+20h]
0x1400cfd35  lea     r12, IpFlcReceivePackets
0x1400cfd3c  mov     rdx, [rbp+4Fh+var_98]
0x1400cfd40  mov     rax, [r8+0D8h]
0x1400cfd47  mov     r8b, r15b
0x1400cfd4a  mov     rcx, [rax+8]
0x1400cfd4e  mov     rax, [rcx+40h]
0x1400cfd52  mov     rcx, [rbx+130h]
0x1400cfd59  cmp     rax, r12
0x1400cfd5c  jz      short loc_1400CFD9D
0x1400cfd5e  call    _guard_dispatch_icall
0x1400cfd63  jmp     short loc_1400CFD69
0x1400cfd65  mov     r14d, [rbp+4Fh+arg_20]
0x1400cfd69  cmp     [rbp+4Fh+var_88], r13
0x1400cfd6d  jnz     loc_1400CFE15
0x1400cfd73  mov     eax, [rbp+4Fh+Count]
0x1400cfd76  test    eax, eax
0x1400cfd78  jnz     short loc_1400CFDA7
0x1400cfd7a  mov     r12, [rbp+4Fh+arg_10]
0x1400cfd7e  cmp     [rbp+4Fh+var_50], r13
0x1400cfd82  jnz     loc_1400CFEB7
0x1400cfd88  add     rsp, 0B8h
0x1400cfd8f  pop     r15
0x1400cfd91  pop     r14
0x1400cfd93  pop     r13
0x1400cfd95  pop     r12
0x1400cfd97  pop     rdi
0x1400cfd98  pop     rsi
0x1400cfd99  pop     rbx
0x1400cfd9a  pop     rbp
0x1400cfd9b  retn
0x1400cfd9d  xor     r9d, r9d
0x1400cfda0  call    IppReceivePackets
0x1400cfda5  jmp     short loc_1400CFD69
0x1400cfda7  mov     rcx, [rbx+48h]; RunRef
0x1400cfdab  mov     edx, eax; Count
0x1400cfdad  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400cfdb4  nop     dword ptr [rax+rax+00h]
0x1400cfdb9  jmp     short loc_1400CFD7A
0x1400cfdbb  mov     r9b, r15b
0x1400cfdbe  lea     rdx, FlpFreeNetBufferListChain
0x1400cfdc5  mov     r8, rbx
0x1400cfdc8  mov     rcx, rdi
0x1400cfdcb  mov     r14, rdi
0x1400cfdce  call    cs:__imp_NetioAllocateAndReferenceCopyNetBufferListEx
0x1400cfdd5  nop     dword ptr [rax+rax+00h]
0x1400cfdda  mov     rdi, rax
0x1400cfddd  mov     rdx, r14
0x1400cfde0  test    rax, rax
0x1400cfde3  jz      loc_1400CFE6A
0x1400cfde9  mov     rcx, rax
0x1400cfdec  call    cs:__imp_NetioCopyNetBufferListInformation
0x1400cfdf3  nop     dword ptr [rax+rax+00h]
0x1400cfdf8  inc     [rbp+4Fh+Count]
0x1400cfdfb  mov     r14, [rbp+4Fh+arg_8]
0x1400cfdff  jmp     loc_1400CFC55
0x1400cfe04  test    r12d, r12d
0x1400cfe07  jz      loc_1400D0004
0x1400cfe0d  mov     esi, r12d
0x1400cfe10  jmp     loc_1400CFCA1
0x1400cfe15  mov     rax, [rbp+4Fh+var_60]
0x1400cfe19  mov     [rax], r13
0x1400cfe1c  cmp     [rbx+3B0h], r13d
0x1400cfe23  jnz     loc_1400D008B
0x1400cfe29  mov     rax, [rbx+120h]
0x1400cfe30  mov     rcx, [rax+100h]
0x1400cfe37  test    rcx, rcx
0x1400cfe3a  jz      short loc_1400CFE47
0x1400cfe3c  mov     al, [rcx+18h]
0x1400cfe3f  test    al, al
0x1400cfe41  jz      loc_1401CC82C
0x1400cfe47  mov     rax, [rbx+20h]
0x1400cfe4b  mov     r8b, r15b
0x1400cfe4e  mov     rdx, [rbp+4Fh+var_88]
0x1400cfe52  mov     rcx, [rbx+120h]
0x1400cfe59  mov     rax, [rax+1A0h]
0x1400cfe60  call    _guard_dispatch_icall
0x1400cfe65  jmp     loc_1400CFD73
0x1400cfe6a  mov     rcx, [rbx+120h]
0x1400cfe71  mov     r9d, 1
0x1400cfe77  mov     [rsp+0F0h+var_B8], 0E0004001h
0x1400cfe7f  mov     r8d, r9d
0x1400cfe82  mov     eax, [rcx+0CCh]
0x1400cfe88  mov     [rsp+0F0h+var_C0], eax
0x1400cfe8c  mov     dword ptr [rsp+0F0h+var_C8], 0
0x1400cfe94  mov     dword ptr [rsp+0F0h+var_D0], 7
0x1400cfe9c  call    FlpLogPacketDiscardWithType
0x1400cfea1  mov     r14, [rbp+4Fh+arg_8]
0x1400cfea5  jmp     loc_1400CFCA1
0x1400cfeaa  mov     rax, [rbp+4Fh+var_60]
0x1400cfeae  mov     [rbp+4Fh+var_60], rdi
0x1400cfeb2  jmp     loc_1400CFC9E
0x1400cfeb7  cmp     [rbp+4Fh+var_AC], 2
0x1400cfebb  mov     r14d, r13d
0x1400cfebe  mov     rax, [rbp+4Fh+var_70]
0x1400cfec2  setnb   r14b
0x1400cfec6  mov     [rax], r13
0x1400cfec9  mov     rsi, [rbp+4Fh+var_50]
0x1400cfecd  mov     rdi, rsi
0x1400cfed0  test    rsi, rsi
0x1400cfed3  jz      short loc_1400CFEF1
0x1400cfed5  mov     edx, 1
0x1400cfeda  mov     rcx, rdi
0x1400cfedd  call    cs:__imp_WfpNblInfoClearFlags
0x1400cfee4  nop     dword ptr [rax+rax+00h]
0x1400cfee9  mov     rdi, [rdi]
0x1400cfeec  test    rdi, rdi
0x1400cfeef  jnz     short loc_1400CFED5
0x1400cfef1  test    r12, r12
0x1400cfef4  jz      loc_1401CC97F
0x1400cfefa  mov     r9d, [rbp+4Fh+var_A0]
0x1400cfefe  mov     r8d, r14d
0x1400cff01  mov     rdx, rsi
0x1400cff04  mov     rcx, rbx
0x1400cff07  call    FlpNdisReturnNetBufferListsWrapper
0x1400cff0c  jmp     loc_1400CFD88
0x1400cff11  mov     rcx, [rdi+100h]
0x1400cff18  test    rcx, rcx
0x1400cff1b  jz      short loc_1400CFF28
0x1400cff1d  mov     al, [rcx+18h]
0x1400cff20  test    al, al
0x1400cff22  jz      loc_1401CC798
0x1400cff28  mov     r9d, [rbp+4Fh+arg_20]
0x1400cff2c  movzx   edx, r13w
0x1400cff30  mov     ecx, [rbp+4Fh+var_78]
0x1400cff33  mov     r8d, [rbp+4Fh+var_B0]
0x1400cff37  mov     byte ptr [rsp+0F0h+var_D0], r15b
0x1400cff3c  call    FlpUpdateSlowPathCounters
0x1400cff41  mov     r8, [rbx+20h]
0x1400cff45  mov     rdx, [rbp+4Fh+var_90]
0x1400cff49  mov     rax, [r8+0D8h]
0x1400cff50  mov     r8b, r15b
0x1400cff53  mov     rcx, [rax+8]
0x1400cff57  mov     rax, [rcx+40h]
0x1400cff5b  mov     rcx, [rdi+90h]
0x1400cff62  cmp     rax, r12
0x1400cff65  jnz     loc_1401CC801
0x1400cff6b  xor     r9d, r9d
0x1400cff6e  call    IppReceivePackets
0x1400cff73  nop
0x1400cff74  jmp     loc_1401CC806
0x1400cff79  mov     rcx, [rdi+100h]
0x1400cff80  test    rcx, rcx
0x1400cff83  jz      short loc_1400CFF90
0x1400cff85  mov     al, [rcx+18h]
0x1400cff88  test    al, al
0x1400cff8a  jz      loc_1401CC920
0x1400cff90  mov     rax, [rbx+20h]
0x1400cff94  mov     r8b, r15b
0x1400cff97  mov     rdx, [rbp+4Fh+var_90]
0x1400cff9b  mov     rcx, rdi
0x1400cff9e  mov     rax, [rax+1A0h]
0x1400cffa5  call    _guard_dispatch_icall
0x1400cffaa  mov     edx, [rbp+4Fh+var_B0]; Count
0x1400cffad  mov     rcx, [rdi+38h]; RunRef
0x1400cffb1  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400cffb8  nop     dword ptr [rax+rax+00h]
0x1400cffbd  test    rsi, rsi
0x1400cffc0  jnz     loc_1401CC897
0x1400cffc6  jmp     loc_1400CFD73
0x1400cffcb  mov     edx, [rbp+4Fh+var_80]
  ... truncated ...
```
