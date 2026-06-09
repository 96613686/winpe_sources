# VmsMpNicSendNetBufferLists

- ea: `0x1400135e0`
- end: `0x14001400b`
- name: `VmsMpNicSendNetBufferLists`
- size: `2603`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140010940`
- `0x140012a90`
- `0x140012b70`
- `0x140012ca4`
- `0x140012d18`
- `0x14001319c`
- `0x1400135e0`
- `0x140014330`
- `0x14001484c`
- `0x140014988`
- `0x140017ca8`
- `0x14001d1b8`
- `0x14001e598`
- `0x140024b60`
- `0x140027a64`
- `0x14002ca0c`
- `0x14002fe4c`
- `0x1400338e0`
- `0x14005fc3c`
- `0x14008497c`
- `0x1401158a0`
- `0x1401159bc`
- `0x1401298a8`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140013697`
- `ntoskrnl!KeBugCheckEx` at `0x14001383f`
- `ntoskrnl!KeBugCheckEx` at `0x140013697`
- `ntoskrnl!KeBugCheckEx` at `0x14001383f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001364d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013678`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001378c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400137ef`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013820`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013b30`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001364d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013678`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001378c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400137ef`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013820`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140013b30`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013637`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013637`
- `NDIS!NdisAcquireRWLockRead` at `0x140013a84`
- `NDIS!NdisAcquireRWLockRead` at `0x140013ad2`
- `NDIS!NdisAcquireRWLockRead` at `0x140013c91`
- `NDIS!NdisAcquireRWLockRead` at `0x140013a84`
- `NDIS!NdisAcquireRWLockRead` at `0x140013ad2`
- `NDIS!NdisAcquireRWLockRead` at `0x140013c91`
- `NDIS!NdisReleaseRWLock` at `0x140013b0a`
- `NDIS!NdisReleaseRWLock` at `0x140013ba1`
- `NDIS!NdisReleaseRWLock` at `0x140013bee`
- `NDIS!NdisReleaseRWLock` at `0x140013cb5`
- `NDIS!NdisReleaseRWLock` at `0x140013b0a`
- `NDIS!NdisReleaseRWLock` at `0x140013ba1`
- `NDIS!NdisReleaseRWLock` at `0x140013bee`
- `NDIS!NdisReleaseRWLock` at `0x140013cb5`

## pseudocode

```c
void __fastcall VmsMpNicSendNetBufferLists(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  char v4; // r12
  __int64 v6; // rbx
  int v7; // edx
  ULONG CurrentProcessorNumber; // eax
  ULONG_PTR v9; // rdi
  ULONG v10; // eax
  __int64 v11; // r13
  const char *v12; // rdx
  int v13; // eax
  __int16 v14; // r14
  int NetBufferListContext; // eax
  int v16; // r9d
  unsigned __int64 v17; // rdx
  int v18; // r8d
  __int64 v19; // rbx
  __int64 *v20; // r13
  ULONG v21; // eax
  ULONG_PTR v22; // rbx
  ULONG v23; // eax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  _QWORD *v28; // r12
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  char v33; // r15
  int v34; // r14d
  _QWORD *v35; // rax
  __int64 v36; // rdi
  __int64 v37; // rdx
  __int64 v38; // rdx
  struct _NDIS_RW_LOCK_EX *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  __int64 v42; // rax
  __int64 v43; // rax
  struct _NDIS_RW_LOCK_EX *v44; // rcx
  char *v45; // rcx
  char *v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  _QWORD *v50; // r14
  int v51; // r12d
  __int64 v52; // r13
  int v53; // eax
  int v54; // r9d
  int v55; // edx
  __int64 v56; // r11
  __int64 v57; // rax
  __int64 v58; // rcx
  char v59; // [rsp+40h] [rbp-49h]
  unsigned int v60; // [rsp+44h] [rbp-45h]
  int v61; // [rsp+44h] [rbp-45h]
  char v62; // [rsp+48h] [rbp-41h]
  struct _LOCK_STATE_EX v63; // [rsp+4Ch] [rbp-3Dh] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v65; // [rsp+54h] [rbp-35h] BYREF
  __int64 *v66; // [rsp+58h] [rbp-31h] BYREF
  __int64 v67; // [rsp+60h] [rbp-29h] BYREF
  __int64 *v68; // [rsp+68h] [rbp-21h] BYREF
  int v69; // [rsp+70h] [rbp-19h] BYREF
  __int64 v70; // [rsp+78h] [rbp-11h]
  __int64 v71; // [rsp+80h] [rbp-9h]
  __int64 v72; // [rsp+88h] [rbp-1h]
  __int64 v73; // [rsp+90h] [rbp+7h] BYREF
  __int64 v74; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v75; // [rsp+A0h] [rbp+17h]
  __int64 *v76; // [rsp+A8h] [rbp+1Fh] BYREF
  void *retaddr; // [rsp+E8h] [rbp+5Fh]
  unsigned int v79; // [rsp+108h] [rbp+7Fh]

  v4 = 0;
  v74 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  v6 = a2;
  LockState.Flags = 0;
  *(_WORD *)&v63.OldIrql = 0;
  v63.Flags = 0;
  v67 = 0;
  v79 = a4 & 1;
  v65 = 0;
  v69 = 0;
  if ( (a4 & 1) != 0 || KeGetCurrentIrql() == 2 )
  {
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v9 = CurrentProcessorNumber;
    if ( CurrentProcessorNumber == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, CurrentProcessorNumber)
      || (v45 = (char *)VmsPlanCpuTable + 5440 * v9) == 0 )
    {
      v10 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v9, v10, 0, 0);
    }
    v59 = 1;
    v61 = 1;
    NetDispatchProfilerEnter(v45 + 1152, 1);
  }
  else
  {
    v61 = 0;
    v59 = 0;
  }
  v71 = *(_QWORD *)(a1 + 3312);
  if ( !v71 )
  {
    WPP_RECORDER_SF_s(VmsIfrLog, v7, 19, 74, (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids, (__int64)"mpExt");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v76 = &v67;
  v20 = 0;
  v68 = 0;
  v33 = 0;
  v73 = 0;
  v67 = 0;
  LODWORD(v66) = 0;
  if ( (VmsDiagnosticFlags & 1) == 0 || !v6 )
    goto LABEL_55;
  v42 = *(_QWORD *)(v6 + 288);
  if ( v42 )
  {
    v43 = *(_QWORD *)(v42 + 16);
    if ( v43 )
    {
      *(_QWORD *)(v43 + 176) = "VmsMpNicSendNetBufferLists";
      *(_DWORD *)(v43 + 184) = 4412;
      *(_QWORD *)(v43 + 168) = retaddr;
      goto LABEL_79;
    }
LABEL_55:
    v34 = 0;
    v35 = (_QWORD *)v6;
    if ( !v6 )
      goto LABEL_57;
    goto LABEL_56;
  }
LABEL_79:
  v34 = 0;
  v35 = (_QWORD *)v6;
  do
  {
LABEL_56:
    v35 = (_QWORD *)*v35;
    ++v34;
  }
  while ( v35 );
LABEL_57:
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState, 0);
  if ( *(_DWORD *)(a1 + 68) != 1 || *(_DWORD *)(a1 + 1880) != 1 )
  {
    v36 = 0;
LABEL_73:
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
    LOBYTE(v40) = 1;
    VmsPktReportDroppedNblChain(a1, v6, v40, 4, 17, -536862603);
    v41 = 0;
LABEL_74:
    VmsMpNicSendNetBufferListsCompleteWithRss(a1, (__int64 *)v6, v61, v41);
    goto LABEL_20;
  }
  v36 = *(_QWORD *)(a1 + 1888);
  v75 = *(_QWORD *)(a1 + 1984);
  if ( !(unsigned __int8)VmsMpNicIsStarted(a1) )
    goto LABEL_73;
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v36 + 56), &v63, 0);
  if ( *(_DWORD *)(v36 + 68) == 2 || *(_DWORD *)(v36 + 4272) != 3 )
  {
    v4 = 1;
  }
  else
  {
    LOBYTE(v37) = 12;
    VmsOmpObjectReference(v36, v37);
    v33 = 1;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v36 + 56), &v63);
  if ( v4 )
    goto LABEL_73;
  if ( a1 != -1232 )
    _InterlockedAdd64(
      (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6) + *(_QWORD *)(a1 + 1256) + 16),
      v34);
  if ( ((*(_DWORD *)(a1 + 1872) - 1) & 0xFFFFFFFD) != 0 )
    __fastfail(0xC0000024);
  v38 = 0;
  v72 = 0;
  if ( *(_QWORD *)(a1 + 6320) )
  {
    v38 = a1 + 5696;
    v72 = a1 + 5696;
  }
  v39 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 56);
  v70 = *(_QWORD *)(v38 + 640);
  NdisReleaseRWLock(v39, &LockState);
  v18 = 0;
  if ( *(_DWORD *)(v36 + 8916) )
  {
    v44 = *(struct _NDIS_RW_LOCK_EX **)(v36 + 56);
    v71 = v36 + 56;
    NdisAcquireRWLockRead(v44, &v63, 0);
    if ( (*(_BYTE *)(v36 + 1232) & 1) == 0 )
    {
      v50 = (_QWORD *)v6;
      v51 = 0;
      if ( v6 )
      {
        v52 = v75;
        do
        {
          v53 = VmsPDConvertNblToPDBuffer(v50, v52, &v74, &v66);
          if ( v53 >= 0 )
          {
            v51 += (int)v66;
            VmsPDAppendPDBuffers(&v76, v74);
            if ( VmsEtwTraceDatapath )
            {
              if ( (v57 = *(_QWORD *)(a1 + 1984)) != 0 && *(_BYTE *)(v57 + 10864) || !VmsEtwTraceFiltersExist )
                VmsEtwTraceNblReceiveDeliver(
                  &VM_PD_BUFFER_RECEIVE,
                  a1 + 616,
                  (v36 + 72) & -(__int64)(v36 != 0),
                  (v36 + 616) & -(__int64)(v36 != 0),
                  v56);
            }
          }
          else
          {
            LOBYTE(v54) = 1;
            VmsPktReportDroppedPacketEx(a1, (_DWORD)v50, 1, v54, v53, -536862667);
          }
          v50 = (_QWORD *)*v50;
        }
        while ( v50 );
        v6 = a2;
        v20 = v68;
        if ( v51 )
        {
          v58 = v67;
          if ( !v67 )
          {
            WPP_RECORDER_SF_s(
              VmsIfrLog,
              v55,
              19,
              75,
              (__int64)WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids,
              (__int64)"sendPDBuffer != NULL");
            v58 = v67;
            if ( !v67 )
            {
              MicrosoftTelemetryAssertTriggeredNoArgsKM();
              v58 = v67;
            }
          }
          VmsPDInjectBuffersFromExtension(v58, 0, 0, 0);
        }
      }
    }
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)v71, &v63);
    v41 = 2;
    goto LABEL_74;
  }
  v60 = 0;
  v66 = &v73;
  v28 = &v68;
  v62 = v70 & 1;
  if ( !v6 )
    goto LABEL_20;
  v11 = v72;
  v14 = -1;
  do
  {
    v12 = *(const char **)v6;
    v70 = *(_QWORD *)v6;
    if ( (VmsDiagnosticFlags & 1) != 0 )
    {
      if ( v12 )
      {
        v24 = *((_QWORD *)v12 + 36);
        if ( v24 )
        {
          v25 = *(_QWORD *)(v24 + 16);
          if ( v25 )
          {
            v12 = "VmsMpNicSendNetBufferLists";
            *(_DWORD *)(v25 + 184) = 4501;
            *(_QWORD *)(v25 + 176) = "VmsMpNicSendNetBufferLists";
            *(_QWORD *)(v25 + 168) = retaddr;
          }
        }
      }
    }
    *(_QWORD *)v6 = 0;
    if ( !*(_QWORD *)(v6 + 288) )
    {
      VmsMpCommonSanitizeNblOffloadInfo(retaddr, v12, v6);
      *(_WORD *)(v6 + 258) = *(_WORD *)(v71 + 456);
      v13 = *(_DWORD *)(v6 + 208);
      if ( v13 )
        v14 = v13 & 0x7F;
      NetBufferListContext = VmsMpNicPvtAllocateNetBufferListContext(a1, v6);
      if ( NetBufferListContext < 0 )
      {
        LOBYTE(v16) = 1;
        VmsPktReportDroppedPacketEx(a1, v6, 1, v16, NetBufferListContext, -536862668);
        *v28 = v6;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( *(_QWORD *)v6 )
          {
            v47 = *(_QWORD *)(*(_QWORD *)v6 + 288LL);
            if ( v47 )
            {
              v48 = *(_QWORD *)(v47 + 16);
              if ( v48 )
              {
                v17 = (unsigned __int64)"VmsMpNicSendNetBufferLists";
                *(_DWORD *)(v48 + 184) = 4552;
                *(_QWORD *)(v48 + 176) = "VmsMpNicSendNetBufferLists";
                *(_QWORD *)(v48 + 168) = retaddr;
              }
            }
          }
        }
        v28 = (_QWORD *)v6;
      }
      else
      {
        VmsMpNicPvtStoreOriginalNblOob(v6);
        v18 = 0;
        *v66 = v6;
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( *(_QWORD *)v6 )
          {
            v26 = *(_QWORD *)(*(_QWORD *)v6 + 288LL);
            if ( v26 )
            {
              v27 = *(_QWORD *)(v26 + 16);
              if ( v27 )
              {
                v17 = (unsigned __int64)"VmsMpNicSendNetBufferLists";
                *(_DWORD *)(v27 + 184) = 4559;
                *(_QWORD *)(v27 + 176) = "VmsMpNicSendNetBufferLists";
                *(_QWORD *)(v27 + 168) = retaddr;
              }
            }
          }
        }
        ++v60;
        v66 = (__int64 *)v6;
        if ( !VmsEtwTraceDatapath )
          goto LABEL_13;
        v49 = *(_QWORD *)(a1 + 1984);
        if ( !v49 || !*(_BYTE *)(v49 + 10864) )
        {
          if ( VmsEtwTraceFiltersExist )
            goto LABEL_13;
        }
        if ( !v33 )
          goto LABEL_13;
        VmsTrcTransferNblActivityId(v6, a1);
        VmsEtwTraceNblReceiveDeliver(
          &VM_NBL_RECEIVE,
          a1 + 616,
          (v36 + 72) & -(__int64)(v36 != 0),
          (v36 + 616) & -(__int64)(v36 != 0),
          v6);
      }
      v18 = 0;
LABEL_13:
      if ( *(_WORD *)(v6 + 258) )
      {
        VmsRouterCountNetBufferListBytesAndPackets(v6, &v65, &v69);
        v18 = 0;
        if ( !v62 )
          v14 = -2;
        v31 = *(_QWORD *)(v11 + 624);
        v32 = 0;
        v17 = v65;
        if ( v31 )
        {
          if ( v14 == -1 )
          {
            v32 = v11 + 400;
          }
          else if ( v14 == -2 )
          {
            v32 = v11 + 176;
          }
          else
          {
            v32 = v31 + 224LL * v14;
          }
        }
        _InterlockedAdd64((volatile signed __int64 *)(v32 + 72), v65);
      }
      v14 = -1;
      goto LABEL_15;
    }
    LOBYTE(v18) = 1;
    VmsPktReportDroppedNbl(a1, v6, v18, 22, 16, -536862669);
    *v28 = v6;
    if ( (VmsDiagnosticFlags & 1) != 0 )
    {
      if ( *(_QWORD *)v6 )
      {
        v29 = *(_QWORD *)(*(_QWORD *)v6 + 288LL);
        if ( v29 )
        {
          v30 = *(_QWORD *)(v29 + 16);
          if ( v30 )
          {
            v17 = (unsigned __int64)"VmsMpNicSendNetBufferLists";
            *(_DWORD *)(v30 + 184) = 4518;
            *(_QWORD *)(v30 + 176) = "VmsMpNicSendNetBufferLists";
            *(_QWORD *)(v30 + 168) = retaddr;
          }
        }
      }
    }
    v28 = (_QWORD *)v6;
    v18 = 0;
LABEL_15:
    v6 = v70;
  }
  while ( v70 );
  v19 = v73;
  if ( v73 )
  {
    if ( a1 != -1232 )
      _InterlockedAdd64(
        (volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                  + *(_QWORD *)(a1 + 1256)
                                  + 8),
        (int)v60);
    VmsExtPtRouteNetBufferListsWithBwCap(a1, v19, v60, v79);
    v20 = v68;
  }
  else
  {
    v20 = v68;
  }
LABEL_20:
  if ( v33 )
  {
    LOBYTE(v17) = 12;
    VmsOmpObjectDereference(v36, v17);
  }
  if ( v20 )
    VmsMpNicSendNetBufferListsCompleteWithRss(a1, v20, 0, 2);
  if ( v59 )
  {
    v21 = KeGetCurrentProcessorNumberEx(0);
    v22 = v21;
    if ( v21 == -1
      || !(unsigned __int8)VmsCpuSetContainsProcessor(VmsKnownProcessors, v21)
      || (v46 = (char *)VmsPlanCpuTable + 5440 * v22) == 0 )
    {
      v23 = KeGetCurrentProcessorNumberEx(0);
      KeBugCheckEx(0x121u, v22, v23, 0, 0);
    }
    NetDispatchProfilerLeave(v46 + 1152);
  }
}

```

## disassembly

```asm
0x1400135e0  mov     [rsp-8+arg_0], rbx
0x1400135e5  mov     [rsp-8+arg_8], rdx
0x1400135ea  push    rbp
0x1400135eb  push    rsi
0x1400135ec  push    rdi
0x1400135ed  push    r12
0x1400135ef  push    r13
0x1400135f1  push    r14
0x1400135f3  push    r15
0x1400135f5  lea     rbp, [rsp-27h]
0x1400135fa  sub     rsp, 0B0h
0x140013601  xor     r12d, r12d
0x140013604  mov     rsi, rcx
0x140013607  xor     ecx, ecx
0x140013609  mov     [rbp+57h+var_48], r12
0x14001360d  mov     eax, r9d
0x140013610  mov     word ptr [rbp+57h+LockState.OldIrql], cx
0x140013614  mov     rbx, rdx
0x140013617  mov     [rbp+57h+LockState.Flags], cl
0x14001361a  mov     word ptr [rbp+57h+var_94.OldIrql], cx
0x14001361e  lea     edi, [rcx+1]
0x140013621  mov     [rbp+57h+var_94.Flags], cl
0x140013624  and     eax, edi
0x140013626  mov     [rbp+57h+var_80], r12
0x14001362a  mov     [rbp+57h+arg_18], eax
0x14001362d  mov     [rbp+57h+var_8C], r12d
0x140013631  mov     [rbp+57h+var_70], r12d
0x140013635  jnz     short loc_14001364B
0x140013637  call    cs:__imp_KeGetCurrentIrql
0x14001363e  nop     dword ptr [rax+rax+00h]
0x140013643  cmp     al, 2
0x140013645  jnz     loc_140013D80
0x14001364b  xor     ecx, ecx; ProcNumber
0x14001364d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140013654  nop     dword ptr [rax+rax+00h]
0x140013659  mov     edi, eax
0x14001365b  cmp     eax, 0FFFFFFFFh
0x14001365e  jz      short loc_140013676
0x140013660  mov     edx, edi
0x140013662  lea     rcx, VmsKnownProcessors
0x140013669  call    VmsCpuSetContainsProcessor
0x14001366e  test    al, al
0x140013670  jnz     loc_140013CD3
0x140013676  xor     ecx, ecx; ProcNumber
0x140013678  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14001367f  nop     dword ptr [rax+rax+00h]
0x140013684  xor     r9d, r9d; BugCheckParameter3
0x140013687  mov     [rsp+0E0h+BugCheckParameter4], r12; BugCheckParameter4
0x14001368c  mov     r8d, eax; BugCheckParameter2
0x14001368f  mov     rdx, rdi; BugCheckParameter1
0x140013692  mov     ecx, 121h; BugCheckCode
0x140013697  call    cs:__imp_KeBugCheckEx
0x1400136a4  mov     r13, [rbp+57h+var_58]
0x1400136a8  or      r14d, 0FFFFFFFFh
0x1400136ac  mov     rdx, [rbx]
0x1400136af  mov     eax, cs:VmsDiagnosticFlags
0x1400136b5  mov     rcx, [rbp+5Fh]
0x1400136b9  mov     [rbp+57h+var_68], rdx
0x1400136bd  test    al, 1
0x1400136bf  jnz     loc_14001384C
0x1400136c5  mov     [rbx], r8
0x1400136c8  cmp     [rbx+120h], r8
0x1400136cf  jnz     loc_1400138E3
0x1400136d5  mov     r8, rbx
0x1400136d8  call    VmsMpCommonSanitizeNblOffloadInfo
0x1400136dd  mov     rax, [rbp+57h+var_60]
0x1400136e1  movzx   eax, word ptr [rax+1C8h]
0x1400136e8  mov     [rbx+102h], ax
0x1400136ef  mov     eax, [rbx+0D0h]
0x1400136f5  test    eax, eax
0x1400136f7  jz      short loc_140013702
0x1400136f9  movzx   r14d, ax
0x1400136fd  and     r14w, 7Fh
0x140013702  mov     rdx, rbx
0x140013705  mov     rcx, rsi
0x140013708  call    VmsMpNicPvtAllocateNetBufferListContext
0x14001370d  test    eax, eax
0x14001370f  js      loc_140013D10
0x140013715  mov     rcx, rbx
0x140013718  call    VmsMpNicPvtStoreOriginalNblOob
0x14001371d  mov     rax, [rbp+57h+var_88]
0x140013721  xor     r8d, r8d
0x140013724  mov     rcx, [rbp+5Fh]
0x140013728  mov     [rax], rbx
0x14001372b  mov     eax, cs:VmsDiagnosticFlags
0x140013731  test    al, 1
0x140013733  jnz     loc_140013896
0x140013739  inc     [rbp+57h+var_9C]
0x14001373c  mov     al, cs:VmsEtwTraceDatapath
0x140013742  mov     [rbp+57h+var_88], rbx
0x140013746  test    al, al
0x140013748  jnz     loc_140013DBE
0x14001374e  cmp     [rbx+102h], r8w
0x140013756  jnz     loc_140013962
0x14001375c  or      r14d, 0FFFFFFFFh
0x140013760  mov     rbx, [rbp+57h+var_68]
0x140013764  test    rbx, rbx
0x140013767  jnz     loc_1400136AC
0x14001376d  mov     rbx, [rbp+57h+var_50]
0x140013771  test    rbx, rbx
0x140013774  jz      loc_140013E6E
0x14001377a  lea     r13, [rsi+4D0h]
0x140013781  test    r13, r13
0x140013784  jz      loc_140013E65
0x14001378a  xor     ecx, ecx; ProcNumber
0x14001378c  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140013793  nop     dword ptr [rax+rax+00h]
0x140013798  movsxd  r14, [rbp+57h+var_9C]
0x14001379c  mov     ecx, eax
0x14001379e  mov     rdx, r14
0x1400137a1  mov     rax, [r13+18h]
0x1400137a5  shl     rcx, 6
0x1400137a9  lock add [rcx+rax+8], rdx
0x1400137af  mov     r9d, [rbp+57h+arg_18]
0x1400137b3  mov     r8d, r14d
0x1400137b6  mov     rdx, rbx
0x1400137b9  mov     rcx, rsi
0x1400137bc  call    VmsExtPtRouteNetBufferListsWithBwCap
0x1400137c1  mov     r13, [rbp+57h+var_78]
0x1400137c5  xor     r8d, r8d
0x1400137c8  test    r15b, r15b
0x1400137cb  jz      short loc_1400137DA
0x1400137cd  mov     dl, 0Ch
0x1400137cf  mov     rcx, rdi
0x1400137d2  call    VmsOmpObjectDereference
0x1400137d7  xor     r8d, r8d
0x1400137da  test    r13, r13
0x1400137dd  jnz     loc_140013FE8
0x1400137e3  cmp     [rbp+57h+var_A0], r8b
0x1400137e7  jz      loc_1400139C8
0x1400137ed  xor     ecx, ecx; ProcNumber
0x1400137ef  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400137f6  nop     dword ptr [rax+rax+00h]
0x1400137fb  mov     ebx, eax
0x1400137fd  cmp     eax, 0FFFFFFFFh
0x140013800  jz      loc_140014004
0x140013806  mov     edx, ebx
0x140013808  lea     rcx, VmsKnownProcessors
0x14001380f  call    VmsCpuSetContainsProcessor
0x140013814  xor     edi, edi
0x140013816  test    al, al
0x140013818  jnz     loc_140013CEC
0x14001381e  xor     ecx, ecx; ProcNumber
0x140013820  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140013827  nop     dword ptr [rax+rax+00h]
0x14001382c  xor     r9d, r9d; BugCheckParameter3
0x14001382f  mov     [rsp+0E0h+BugCheckParameter4], rdi; BugCheckParameter4
0x140013834  mov     r8d, eax; BugCheckParameter2
0x140013837  mov     rdx, rbx; BugCheckParameter1
0x14001383a  mov     ecx, 121h; BugCheckCode
0x14001383f  call    cs:__imp_KeBugCheckEx
0x14001384c  test    rdx, rdx
0x14001384f  jz      loc_1400136C5
0x140013855  mov     rax, [rdx+120h]
0x14001385c  test    rax, rax
0x14001385f  jz      loc_1400136C5
0x140013865  mov     rax, [rax+10h]
0x140013869  test    rax, rax
0x14001386c  jz      loc_1400136C5
0x140013872  lea     rdx, aVmsmpnicsendne_1; "VmsMpNicSendNetBufferLists"
0x140013879  mov     dword ptr [rax+0B8h], 1195h
0x140013883  mov     [rax+0B0h], rdx
0x14001388a  mov     [rax+0A8h], rcx
0x140013891  jmp     loc_1400136C5
0x140013896  mov     rax, [rbx]
0x140013899  test    rax, rax
0x14001389c  jz      loc_140013739
0x1400138a2  mov     rax, [rax+120h]
0x1400138a9  test    rax, rax
0x1400138ac  jz      loc_140013739
0x1400138b2  mov     rax, [rax+10h]
0x1400138b6  test    rax, rax
0x1400138b9  jz      loc_140013739
0x1400138bf  lea     rdx, aVmsmpnicsendne_1; "VmsMpNicSendNetBufferLists"
0x1400138c6  mov     dword ptr [rax+0B8h], 11CFh
0x1400138d0  mov     [rax+0B0h], rdx
0x1400138d7  mov     [rax+0A8h], rcx
0x1400138de  jmp     loc_140013739
0x1400138e3  mov     dword ptr [rsp+0E0h+var_B8], 0E0002033h
0x1400138eb  mov     r9d, 16h
0x1400138f1  mov     r8b, 1
0x1400138f4  mov     dword ptr [rsp+0E0h+BugCheckParameter4], 0E0000010h
0x1400138fc  mov     rdx, rbx
0x1400138ff  mov     rcx, rsi
0x140013902  call    VmsPktReportDroppedNbl
0x140013907  mov     rcx, [rbp+5Fh]
0x14001390b  mov     [r12], rbx
0x14001390f  mov     eax, cs:VmsDiagnosticFlags
0x140013915  test    al, 1
0x140013917  jnz     short loc_140013924
0x140013919  mov     r12, rbx
0x14001391c  xor     r8d, r8d
0x14001391f  jmp     loc_140013760
0x140013924  mov     rax, [rbx]
0x140013927  test    rax, rax
0x14001392a  jz      short loc_140013919
0x14001392c  mov     rax, [rax+120h]
0x140013933  test    rax, rax
0x140013936  jz      short loc_140013919
0x140013938  mov     rax, [rax+10h]
0x14001393c  test    rax, rax
0x14001393f  jz      short loc_140013919
0x140013941  lea     rdx, aVmsmpnicsendne_1; "VmsMpNicSendNetBufferLists"
0x140013948  mov     dword ptr [rax+0B8h], 11A6h
0x140013952  mov     [rax+0B0h], rdx
0x140013959  mov     [rax+0A8h], rcx
0x140013960  jmp     short loc_140013919
0x140013962  lea     r8, [rbp+57h+var_70]
0x140013966  mov     rcx, rbx
0x140013969  lea     rdx, [rbp+57h+var_8C]
0x14001396d  call    VmsRouterCountNetBufferListBytesAndPackets
0x140013972  xor     r8d, r8d
0x140013975  lea     r9d, [r8-2]
0x140013979  cmp     [rbp+57h+var_98], r8b
0x14001397d  jz      loc_140013E5C
0x140013983  mov     rcx, [r13+270h]
0x14001398a  mov     rax, r8
0x14001398d  mov     edx, [rbp+57h+var_8C]
0x140013990  test    rcx, rcx
0x140013993  jz      short loc_1400139B2
0x140013995  or      eax, 0FFFFFFFFh
0x140013998  cmp     r14w, ax
0x14001399c  jz      short loc_1400139E4
0x14001399e  cmp     r14w, r9w
0x1400139a2  jz      short loc_1400139ED
0x1400139a4  movsx   rax, r14w
0x1400139a8  imul    rax, 0E0h
0x1400139af  add     rax, rcx
0x1400139b2  lock add [rax+48h], rdx
0x1400139b7  jmp     loc_14001375C
0x1400139bc  add     rcx, 480h
0x1400139c3  call    NetDispatchProfilerLeave
0x1400139c8  mov     rbx, [rsp+0E0h+arg_0]
0x1400139d0  add     rsp, 0B0h
0x1400139d7  pop     r15
0x1400139d9  pop     r14
0x1400139db  pop     r13
0x1400139dd  pop     r12
0x1400139df  pop     rdi
0x1400139e0  pop     rsi
0x1400139e1  pop     rbp
0x1400139e2  retn
0x1400139e4  lea     rax, [r13+190h]
0x1400139eb  jmp     short loc_1400139B2
0x1400139ed  lea     rax, [r13+0B0h]
0x1400139f4  jmp     short loc_1400139B2
0x1400139f6  mov     edi, 1
0x1400139fb  add     rcx, 480h
0x140013a02  mov     edx, edi
0x140013a04  mov     [rbp+57h+var_A0], dil
0x140013a08  mov     [rbp+57h+var_9C], edi
0x140013a0b  call    NetDispatchProfilerEnter
0x140013a10  mov     rax, [rsi+0CF0h]
0x140013a17  lea     rcx, WPP_ab3e086a36173e28d54643860b7e4b9f_Traceguids
0x140013a1e  mov     [rbp+57h+var_60], rax
0x140013a22  test    rax, rax
0x140013a25  jz      loc_140013D8D
0x140013a2b  mov     rcx, [rbp+5Fh]
0x140013a2f  lea     rax, [rbp+57h+var_80]
0x140013a33  mov     [rbp+57h+var_38], rax
0x140013a37  lea     rdx, aVmsmpnicsendne_1; "VmsMpNicSendNetBufferLists"
0x140013a3e  mov     eax, cs:VmsDiagnosticFlags
0x140013a44  mov     r13, r12
0x140013a47  mov     [rbp+57h+var_78], r12
0x140013a4b  mov     r15b, r12b
0x140013a4e  mov     [rbp+57h+var_50], r12
0x140013a52  mov     [rbp+57h+var_80], r12
0x140013a56  mov     dword ptr [rbp+57h+var_88], r12d
0x140013a5a  test    dil, al
0x140013a5d  jnz     loc_140013C35
0x140013a63  mov     r14d, r12d
0x140013a66  mov     rax, rbx
0x140013a69  test    rbx, rbx
0x140013a6c  jz      short loc_140013A79
0x140013a6e  mov     rax, [rax]
0x140013a71  add     r14d, edi
0x140013a74  test    rax, rax
0x140013a77  jnz     short loc_140013A6E
0x140013a79  mov     rcx, [rsi+38h]; Lock
0x140013a7d  lea     rdx, [rbp+57h+LockState]; LockState
0x140013a81  xor     r8d, r8d; Flags
0x140013a84  call    cs:__imp_NdisAcquireRWLockRead
0x140013a8b  nop     dword ptr [rax+rax+00h]
0x140013a90  cmp     [rsi+44h], edi
0x140013a93  jnz     loc_140013BE3
0x140013a99  cmp     [rsi+758h], edi
0x140013a9f  jnz     loc_140013BE3
0x140013aa5  mov     rax, [rsi+7C0h]
0x140013aac  mov     rcx, rsi
0x140013aaf  mov     rdi, [rsi+760h]
0x140013ab6  mov     [rbp+57h+var_40], rax
0x140013aba  call    VmsMpNicIsStarted
0x140013abf  test    al, al
0x140013ac1  jz      loc_140013BE6
0x140013ac7  mov     rcx, [rdi+38h]; Lock
0x140013acb  lea     rdx, [rbp+57h+var_94]; LockState
0x140013acf  xor     r8d, r8d; Flags
0x140013ad2  call    cs:__imp_NdisAcquireRWLockRead
0x140013ad9  nop     dword ptr [rax+rax+00h]
0x140013ade  cmp     dword ptr [rdi+44h], 2
  ... truncated ...
```
