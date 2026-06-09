# VmsExtMpIndicatePackets

- ea: `0x14001a49c`
- end: `0x14001ac9b`
- name: `VmsExtMpIndicatePackets`
- size: `2047`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400195e0`
- `0x14001e8f0`
- `0x14008ed90`

## callees

- `0x140017a7c`
- `0x140018558`
- `0x14001a49c`
- `0x140027a64`
- `0x14002c5d4`
- `0x14002fd8c`
- `0x14005c370`
- `0x140062a88`
- `0x14006b530`
- `0x14008497c`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a6b6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a6b6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001a746`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001a746`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001a63f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001a63f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001a602`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001ac00`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001a602`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001ac00`
- `NDIS!NdisMIndicateReceiveNetBufferLists` at `0x14001a69b`
- `NDIS!NdisMIndicateReceiveNetBufferLists` at `0x14001a821`
- `NDIS!NdisMIndicateReceiveNetBufferLists` at `0x14001a9df`
- `NDIS!NdisMIndicateReceiveNetBufferLists` at `0x14001ac47`
- `NDIS!NdisMIndicateReceiveNetBufferLists` at `0x14001ac8a`
- `NDIS!NdisMIndicateReceiveNetBufferLists` at `0x14001a69b`
- `NDIS!NdisMIndicateReceiveNetBufferLists` at `0x14001a821`
- `NDIS!NdisMIndicateReceiveNetBufferLists` at `0x14001a9df`
- `NDIS!NdisMIndicateReceiveNetBufferLists` at `0x14001ac47`
- `NDIS!NdisMIndicateReceiveNetBufferLists` at `0x14001ac8a`
- `NDIS!NdisAcquireRWLockRead` at `0x14001a621`
- `NDIS!NdisAcquireRWLockRead` at `0x14001a8db`
- `NDIS!NdisAcquireRWLockRead` at `0x14001a621`
- `NDIS!NdisAcquireRWLockRead` at `0x14001a8db`
- `NDIS!NdisReleaseRWLock` at `0x14001a66a`
- `NDIS!NdisReleaseRWLock` at `0x14001a90b`
- `NDIS!NdisReleaseRWLock` at `0x14001a96c`
- `NDIS!NdisReleaseRWLock` at `0x14001a66a`
- `NDIS!NdisReleaseRWLock` at `0x14001a90b`
- `NDIS!NdisReleaseRWLock` at `0x14001a96c`

## string_xrefs

- `0x14001ab36`: `(curNblContext->Flags & (VMS_NBL_ROUTING_CONTEXT_FLAG_NEEDS_FILTER_EGRESS_COMPLETION | VMS_NBL_ROUTING_CONTEXT_FLAG_NEEDS_PT_EGRESS_COMPLETION | VMS_NBL_ROUTING_CONTEXT_FLAG_RESTORE_HANDLE_ON_EGRESS_COMPLETE)) == 0`

## pseudocode

```c
void __fastcall VmsExtMpIndicatePackets(__int64 a1, struct _NET_BUFFER_LIST *a2, char a3, char a4)
{
  _DWORD *v4; // r11
  struct _NET_BUFFER_LIST *v5; // r13
  const char *v6; // rdx
  __int64 v10; // rcx
  _QWORD *v11; // rdi
  char v12; // r12
  ULONG ReceiveFlags; // esi
  _SLIST_HEADER *v14; // rbx
  ULONG v15; // esi
  unsigned __int64 Alignment; // r14
  _DWORD *v17; // r14
  unsigned __int64 v18; // r14
  int v19; // edx
  UCHAR v20; // r8
  char v21; // bl
  __int64 v22; // rdx
  _QWORD *v23; // rax
  __int64 v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // rcx
  _DWORD *v27; // rdx
  __int64 v28; // rax
  struct _NET_BUFFER_LIST *v29; // rdx
  unsigned int i; // ecx
  __int64 v31; // rax
  __int64 v32; // r14
  __int64 v33; // r13
  int v34; // eax
  __int64 v35; // r12
  __int64 NicHeaderAtIndex; // rax
  __int64 v37; // r8
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 j; // rbx
  struct _NET_BUFFER_LIST *v45; // rdx
  struct _LOCK_STATE_EX v46; // [rsp+30h] [rbp-39h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+34h] [rbp-35h] BYREF
  ULONG NumberOfNetBufferLists[2]; // [rsp+38h] [rbp-31h] BYREF
  int v49; // [rsp+40h] [rbp-29h]
  ULONG v50; // [rsp+44h] [rbp-25h]
  ULONG v51[4]; // [rsp+48h] [rbp-21h] BYREF
  ULONG *v52; // [rsp+58h] [rbp-11h]
  ULONG v53[4]; // [rsp+60h] [rbp-9h] BYREF
  ULONG *v54; // [rsp+70h] [rbp+7h]
  int v55; // [rsp+78h] [rbp+Fh]
  _UNKNOWN *retaddr; // [rsp+C8h] [rbp+5Fh]
  char v57; // [rsp+D0h] [rbp+67h]
  char v59; // [rsp+E0h] [rbp+77h]
  char v60; // [rsp+E8h] [rbp+7Fh]

  v4 = 0;
  *(_WORD *)&v46.OldIrql = 0;
  v46.Flags = 0;
  v5 = a2;
  LODWORD(v52) = 0;
  v6 = "VmsExtMpIndicatePackets";
  LODWORD(v54) = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v57 = 0;
  v59 = 0;
  v49 = 0;
  *(_OWORD *)v51 = 0;
  *(_OWORD *)v53 = 0;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( v5 )
    {
      v23 = v5->NetBufferListInfo[18];
      if ( v23 )
      {
        v24 = v23[2];
        if ( v24 )
        {
          *(_QWORD *)(v24 + 176) = "VmsExtMpIndicatePackets";
          *(_DWORD *)(v24 + 184) = 4378;
          *(_QWORD *)(v24 + 168) = retaddr;
        }
      }
    }
  }
  v10 = *(_QWORD *)(a1 + 9000);
  NumberOfNetBufferLists[0] = 0;
  v52 = 0;
  v54 = 0;
  *(_OWORD *)v51 = 0;
  *(_OWORD *)v53 = 0;
  if ( !v10 || (*(_BYTE *)(v10 + 204) & 2) == 0 && *(_DWORD *)(v10 + 256) != 3 )
  {
    v11 = 0;
    v12 = 0;
LABEL_4:
    v60 = v12;
    goto LABEL_5;
  }
  v52 = &v51[2];
  v25 = ExAllocateFromNPagedLookasideList(&g_ProtocolNicMemberNbls);
  v4 = 0;
  v11 = v25;
  if ( !v25 )
  {
    v12 = 1;
    v54 = &v53[2];
    goto LABEL_4;
  }
  memset(v25, 0, 0x600u);
  v4 = 0;
  v12 = 1;
  v6 = 0;
  v60 = 1;
  do
  {
    v26 = 3LL * (_QWORD)v6++;
    v11[v26 + 2] = &v11[v26 + 1];
  }
  while ( v6 != (const char *)64 );
LABEL_5:
  v55 = a3 & 1;
  ReceiveFlags = v55 | 0x8000;
  if ( (a3 & 0x20) == 0 )
    ReceiveFlags = a3 & 1;
  if ( a4 )
  {
    ReceiveFlags |= 0x4000u;
    v50 = ReceiveFlags;
    if ( VmsVerifierEnabled && !(unsigned __int8)VmsNblHelperIsDestinationGroup(v5, v6) )
    {
      VmsTrcVerifierFailure(40973, v5, ReceiveFlags, a1);
      v4 = 0;
    }
  }
  else
  {
    v50 = ReceiveFlags;
  }
  v14 = (_SLIST_HEADER *)v5;
  if ( v5 )
  {
    v15 = NumberOfNetBufferLists[0];
    do
    {
      Alignment = v14[18].Alignment;
      if ( Alignment )
        v17 = *(_DWORD **)(Alignment + 16);
      else
        v17 = v4;
      v14[7].Region = *(_QWORD *)(a1 + 4296);
      if ( (*v17 & 0x430) != 0 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          (_DWORD)v6,
          19,
          106,
          (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
          (__int64)"(curNblContext->Flags & (VMS_NBL_ROUTING_CONTEXT_FLAG_NEEDS_FILTER_EGRESS_COMPLETION | VMS_NBL_ROUTIN"
                   "G_CONTEXT_FLAG_NEEDS_PT_EGRESS_COMPLETION | VMS_NBL_ROUTING_CONTEXT_FLAG_RESTORE_HANDLE_ON_EGRESS_COMPLETE)) == 0");
        if ( (*v17 & 0x430) != 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
        v4 = 0;
      }
      if ( (*v17 & 0xA00) == 0 )
        *v17 |= 0x200u;
      if ( v12 )
      {
        *(_QWORD *)NumberOfNetBufferLists = v4;
        VmsExtMpNdisSwitchGetNblDestinations(a1, v14, NumberOfNetBufferLists);
        LODWORD(v6) = NumberOfNetBufferLists[0];
        v4 = 0;
        for ( i = 0; ; ++i )
        {
          if ( i >= *(_DWORD *)(*(_QWORD *)NumberOfNetBufferLists + 12LL) )
            goto LABEL_65;
          v31 = *(_QWORD *)(*(_QWORD *)NumberOfNetBufferLists + 16LL);
          v32 = *(_DWORD *)(*(_QWORD *)NumberOfNetBufferLists + 4LL) * i;
          v33 = *(_QWORD *)(v32 + v31 + 8);
          if ( v33 )
          {
            if ( *(_DWORD *)(v33 + 1872) == 2 )
              break;
          }
        }
        LOWORD(v32) = *(_WORD *)(v32 + v31 + 4);
        LOWORD(NumberOfNetBufferLists[0]) = v32;
        if ( (_WORD)v32 )
          goto LABEL_70;
        v34 = VmsTmDistributeOutgoingNbls(*(_QWORD *)(a1 + 9000), v14, NumberOfNetBufferLists);
        v4 = 0;
        if ( v34 )
        {
          LOWORD(v32) = NumberOfNetBufferLists[0];
          goto LABEL_70;
        }
        v35 = *(_QWORD *)(v33 + 3312);
        NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v33 + 56), &v46, 0);
        v32 = LOWORD(NumberOfNetBufferLists[0]);
        NicHeaderAtIndex = VmsPtGetNicHeaderAtIndex(v33, LOWORD(NumberOfNetBufferLists[0]));
        if ( NicHeaderAtIndex && *(_BYTE *)(NicHeaderAtIndex + 20) && *(_DWORD *)(v35 + 4 * v32 + 1632) == 3 )
        {
          VmsNblUpdateDestinationForSet(v14, v33, v37, (unsigned __int16)v32);
          NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v33 + 56), &v46);
          v12 = v60;
          v4 = 0;
LABEL_70:
          if ( (unsigned __int16)v32 > 0x3Fu )
          {
            WPP_RECORDER_SF_s(
              VmsIfrLog,
              (_DWORD)v6,
              19,
              107,
              (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
              (__int64)"nicIndex <= VMS_LBFO_SUPPORTED_TEAM_NICS");
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
            v4 = 0;
          }
          if ( v11 )
          {
            LODWORD(v6) = (_DWORD)retaddr;
            *(_QWORD *)v11[3 * (unsigned __int16)v32 + 2] = v14;
            ++LODWORD(v11[3 * (unsigned __int16)v32]);
            if ( (VmsDiagnosticFlags & 1) != 0 )
            {
              if ( v14->Alignment )
              {
                v38 = *(_QWORD *)(v14->Alignment + 288);
                if ( v38 )
                {
                  v39 = *(_QWORD *)(v38 + 16);
                  if ( v39 )
                  {
                    *(_DWORD *)(v39 + 184) = 4557;
                    *(_QWORD *)(v39 + 176) = "VmsExtMpIndicatePackets";
                    *(_QWORD *)(v39 + 168) = retaddr;
                  }
                }
              }
            }
            v11[3 * (unsigned __int16)v32 + 2] = v14;
          }
          else
          {
            *(_QWORD *)v54 = v14;
            ++v53[0];
            if ( (VmsDiagnosticFlags & 1) != 0 )
            {
              if ( v14->Alignment )
              {
                v40 = *(_QWORD *)(v14->Alignment + 288);
                if ( v40 )
                {
                  v41 = *(_QWORD *)(v40 + 16);
                  if ( v41 )
                  {
                    v6 = "VmsExtMpIndicatePackets";
                    *(_DWORD *)(v41 + 184) = 4563;
                    *(_QWORD *)(v41 + 176) = "VmsExtMpIndicatePackets";
                    *(_QWORD *)(v41 + 168) = retaddr;
                  }
                }
              }
            }
            v54 = (ULONG *)v14;
          }
          if ( v57 )
          {
            if ( (_WORD)v49 != (_WORD)v32 )
              v59 = 1;
          }
          else
          {
            LOWORD(v49) = v32;
            v57 = 1;
          }
          goto LABEL_17;
        }
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v33 + 56), &v46);
        v12 = v60;
        v4 = 0;
LABEL_65:
        *(_QWORD *)v52 = v14;
        ++v51[0];
        if ( (VmsDiagnosticFlags & 1) != 0 )
        {
          if ( v14->Alignment )
          {
            v42 = *(_QWORD *)(v14->Alignment + 288);
            if ( v42 )
            {
              v43 = *(_QWORD *)(v42 + 16);
              if ( v43 )
              {
                v6 = "VmsExtMpIndicatePackets";
                *(_DWORD *)(v43 + 184) = 4589;
                *(_QWORD *)(v43 + 176) = "VmsExtMpIndicatePackets";
                *(_QWORD *)(v43 + 168) = retaddr;
              }
            }
          }
        }
        v52 = (ULONG *)v14;
      }
LABEL_17:
      v14 = (_SLIST_HEADER *)v14->Alignment;
      ++v15;
    }
    while ( v14 );
    v5 = a2;
    NumberOfNetBufferLists[0] = v15;
    ReceiveFlags = v50;
  }
  if ( v12 )
  {
    *(_QWORD *)v52 = v4;
    if ( v11 )
    {
      v27 = v4;
      do
      {
        v28 = 3LL * (_QWORD)v27;
        v27 = (_DWORD *)((char *)v27 + 1);
        *(_QWORD *)v11[v28 + 2] = v4;
      }
      while ( v27 != (_DWORD *)64 );
    }
    else
    {
      *(_QWORD *)v54 = v4;
    }
  }
  v18 = NumberOfNetBufferLists[0];
  if ( !NumberOfNetBufferLists[0] )
  {
LABEL_29:
    if ( !v11 )
      return;
    goto LABEL_30;
  }
  if ( (_BYTE)v55 == (_BYTE)v4 )
  {
    v20 = 0;
  }
  else
  {
    if ( KeGetCurrentIrql() != 2 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v19,
        19,
        24,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
      if ( KeGetCurrentIrql() != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v20 = 1;
  }
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState, v20);
  if ( (*(_BYTE *)(a1 + 1232) & 1) != 0 )
  {
    v21 = 1;
  }
  else
  {
    v21 = 0;
    _InterlockedAdd64(
      (volatile signed __int64 *)(*(_QWORD *)(a1 + 6472) + ((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6) + 32),
      v18);
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
  if ( v21 )
  {
    LOBYTE(v22) = 1;
    VmsExtIoPacketRouted(v5, v22);
    goto LABEL_29;
  }
  if ( !v12 )
  {
    NdisMIndicateReceiveNetBufferLists(*(NDIS_HANDLE *)(a1 + 4296), v5, 0, v18, ReceiveFlags);
    goto LABEL_29;
  }
  if ( *(_QWORD *)&v51[2] )
    NdisMIndicateReceiveNetBufferLists(
      *(NDIS_HANDLE *)(a1 + 4296),
      *(PNET_BUFFER_LIST *)&v51[2],
      0,
      v51[0],
      ReceiveFlags);
  if ( v11 )
  {
    if ( v59 )
    {
      for ( j = 0; j != 64; ++j )
      {
        v45 = (struct _NET_BUFFER_LIST *)v11[3 * j + 1];
        if ( v45 )
          NdisMIndicateReceiveNetBufferLists(*(NDIS_HANDLE *)(a1 + 4296), v45, 0, v11[3 * j], ReceiveFlags);
      }
    }
    else
    {
      v29 = (struct _NET_BUFFER_LIST *)v11[3 * (unsigned __int16)v49 + 1];
      if ( v29 )
        NdisMIndicateReceiveNetBufferLists(
          *(NDIS_HANDLE *)(a1 + 4296),
          v29,
          0,
          v11[3 * (unsigned __int16)v49],
          ReceiveFlags);
    }
LABEL_30:
    ExFreeToNPagedLookasideList(&g_ProtocolNicMemberNbls, v11);
    return;
  }
  if ( *(_QWORD *)&v53[2] )
  {
    if ( v59 == 1 )
      ReceiveFlags &= ~0x4000u;
    NdisMIndicateReceiveNetBufferLists(
      *(NDIS_HANDLE *)(a1 + 4296),
      *(PNET_BUFFER_LIST *)&v53[2],
      0,
      v53[0],
      ReceiveFlags);
  }
}

```

## disassembly

```asm
0x14001a49c  mov     [rsp-8+arg_8], rdx
0x14001a4a1  push    rbp
0x14001a4a2  push    rbx
0x14001a4a3  push    rsi
0x14001a4a4  push    rdi
0x14001a4a5  push    r12
0x14001a4a7  push    r13
0x14001a4a9  push    r14
0x14001a4ab  push    r15
0x14001a4ad  lea     rbp, [rsp-1Fh]
0x14001a4b2  sub     rsp, 88h
0x14001a4b9  xor     eax, eax
0x14001a4bb  xor     r11d, r11d
0x14001a4be  xorps   xmm0, xmm0
0x14001a4c1  mov     word ptr [rbp+57h+var_90.OldIrql], ax
0x14001a4c5  mov     [rbp+57h+var_90.Flags], al
0x14001a4c8  mov     r13, rdx
0x14001a4cb  mov     dword ptr [rbp+57h+var_68], eax
0x14001a4ce  lea     rdx, aVmsextmpindica; "VmsExtMpIndicatePackets"
0x14001a4d5  mov     dword ptr [rbp+57h+var_50], eax
0x14001a4d8  mov     r15, rcx
0x14001a4db  mov     rcx, [rbp+5Fh]
0x14001a4df  mov     r14b, r9b
0x14001a4e2  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x14001a4e6  mov     ebx, r8d
0x14001a4e9  mov     [rbp+57h+LockState.Flags], al
0x14001a4ec  mov     eax, cs:VmsDiagnosticFlags
0x14001a4f2  mov     [rbp+57h+arg_0], r11b
0x14001a4f6  mov     [rbp+57h+arg_10], r11b
0x14001a4fa  mov     [rbp+57h+var_80], r11d
0x14001a4fe  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x14001a502  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14001a506  test    al, 1
0x14001a508  jnz     loc_14001A6DF
0x14001a50e  mov     rcx, [r15+2328h]
0x14001a515  xor     eax, eax
0x14001a517  mov     [rbp+57h+NumberOfNetBufferLists], r11d
0x14001a51b  xorps   xmm1, xmm1
0x14001a51e  mov     [rbp+57h+var_68], rax
0x14001a522  mov     [rbp+57h+var_50], rax
0x14001a526  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x14001a52a  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x14001a52e  test    rcx, rcx
0x14001a531  jnz     loc_14001A72A
0x14001a537  mov     rdi, r11
0x14001a53a  mov     r12b, r11b
0x14001a53d  mov     [rbp+57h+arg_18], r12b
0x14001a541  mov     eax, ebx
0x14001a543  and     eax, 1
0x14001a546  mov     esi, eax
0x14001a548  mov     [rbp+57h+var_48], eax
0x14001a54b  bts     esi, 0Fh
0x14001a54f  test    bl, 20h
0x14001a552  cmovz   esi, eax
0x14001a555  test    r14b, r14b
0x14001a558  jz      loc_14001A6D7
0x14001a55e  bts     esi, 0Eh
0x14001a562  cmp     cs:VmsVerifierEnabled, r11b
0x14001a569  mov     [rbp+57h+var_7C], esi
0x14001a56c  jnz     loc_14001AB05
0x14001a572  mov     rbx, r13
0x14001a575  test    r13, r13
0x14001a578  jz      short loc_14001A5E2
0x14001a57a  mov     esi, [rbp+57h+NumberOfNetBufferLists]
0x14001a57d  lea     rcx, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x14001a584  mov     r14, [rbx+120h]
0x14001a58b  test    r14, r14
0x14001a58e  jz      loc_14001AAA0
0x14001a594  mov     r14, [r14+10h]
0x14001a598  mov     rax, [r15+10C8h]
0x14001a59f  mov     [rbx+78h], rax
0x14001a5a3  test    dword ptr [r14], 430h
0x14001a5aa  jnz     loc_14001AB30
0x14001a5b0  mov     eax, [r14]
0x14001a5b3  test    eax, 0A00h
0x14001a5b8  jz      loc_14001AB6D
0x14001a5be  test    r12b, r12b
0x14001a5c1  jnz     loc_14001A844
0x14001a5c7  mov     rbx, [rbx]
0x14001a5ca  lea     rcx, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x14001a5d1  inc     esi
0x14001a5d3  test    rbx, rbx
0x14001a5d6  jnz     short loc_14001A584
0x14001a5d8  mov     r13, [rbp+57h+arg_8]
0x14001a5dc  mov     [rbp+57h+NumberOfNetBufferLists], esi
0x14001a5df  mov     esi, [rbp+57h+var_7C]
0x14001a5e2  test    r12b, r12b
0x14001a5e5  jnz     loc_14001A7AC
0x14001a5eb  mov     r14d, [rbp+57h+NumberOfNetBufferLists]
0x14001a5ef  test    r14d, r14d
0x14001a5f2  jz      loc_14001A6A7
0x14001a5f8  cmp     byte ptr [rbp+57h+var_48], r11b
0x14001a5fc  jz      loc_14001A722
0x14001a602  call    cs:__imp_KeGetCurrentIrql
0x14001a609  nop     dword ptr [rax+rax+00h]
0x14001a60e  cmp     al, 2
0x14001a610  jnz     loc_14001ABD2
0x14001a616  mov     r8b, 1; Flags
0x14001a619  mov     rcx, [r15+38h]; Lock
0x14001a61d  lea     rdx, [rbp+57h+LockState]; LockState
0x14001a621  call    cs:__imp_NdisAcquireRWLockRead
0x14001a628  nop     dword ptr [rax+rax+00h]
0x14001a62d  test    byte ptr [r15+4D0h], 1
0x14001a635  jnz     loc_14001AC1E
0x14001a63b  xor     ecx, ecx; ProcNumber
0x14001a63d  xor     bl, bl
0x14001a63f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14001a646  nop     dword ptr [rax+rax+00h]
0x14001a64b  mov     r8d, eax
0x14001a64e  mov     rcx, r14
0x14001a651  mov     rax, [r15+1948h]
0x14001a658  shl     r8, 6
0x14001a65c  lock add [rax+r8+20h], rcx
0x14001a662  mov     rcx, [r15+38h]; Lock
0x14001a666  lea     rdx, [rbp+57h+LockState]; LockState
0x14001a66a  call    cs:__imp_NdisReleaseRWLock
0x14001a671  nop     dword ptr [rax+rax+00h]
0x14001a676  test    bl, bl
0x14001a678  jnz     loc_14001A79D
0x14001a67e  test    r12b, r12b
0x14001a681  jnz     loc_14001A7D9
0x14001a687  mov     rcx, [r15+10C8h]; MiniportAdapterHandle
0x14001a68e  mov     r9d, r14d; NumberOfNetBufferLists
0x14001a691  xor     r8d, r8d; PortNumber
0x14001a694  mov     [rsp+0C0h+ReceiveFlags], esi; ReceiveFlags
0x14001a698  mov     rdx, r13; NetBufferList
0x14001a69b  call    cs:__imp_NdisMIndicateReceiveNetBufferLists
0x14001a6a2  nop     dword ptr [rax+rax+00h]
0x14001a6a7  test    rdi, rdi
0x14001a6aa  jz      short loc_14001A6C2
0x14001a6ac  mov     rdx, rdi; Entry
0x14001a6af  lea     rcx, g_ProtocolNicMemberNbls; Lookaside
0x14001a6b6  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001a6bd  nop     dword ptr [rax+rax+00h]
0x14001a6c2  add     rsp, 88h
0x14001a6c9  pop     r15
0x14001a6cb  pop     r14
0x14001a6cd  pop     r13
0x14001a6cf  pop     r12
0x14001a6d1  pop     rdi
0x14001a6d2  pop     rsi
0x14001a6d3  pop     rbx
0x14001a6d4  pop     rbp
0x14001a6d5  retn
0x14001a6d7  mov     [rbp+57h+var_7C], esi
0x14001a6da  jmp     loc_14001A572
0x14001a6df  test    r13, r13
0x14001a6e2  jz      loc_14001A50E
0x14001a6e8  mov     rax, [r13+120h]
0x14001a6ef  test    rax, rax
0x14001a6f2  jz      loc_14001A50E
0x14001a6f8  mov     rax, [rax+10h]
0x14001a6fc  test    rax, rax
0x14001a6ff  jz      loc_14001A50E
0x14001a705  mov     [rax+0B0h], rdx
0x14001a70c  mov     dword ptr [rax+0B8h], 111Ah
0x14001a716  mov     [rax+0A8h], rcx
0x14001a71d  jmp     loc_14001A50E
0x14001a722  xor     r8d, r8d
0x14001a725  jmp     loc_14001A619
0x14001a72a  test    byte ptr [rcx+0CCh], 2
0x14001a731  jz      loc_14001A832
0x14001a737  lea     rax, [rbp+57h+var_78+8]
0x14001a73b  lea     rcx, g_ProtocolNicMemberNbls; Lookaside
0x14001a742  mov     [rbp+57h+var_68], rax
0x14001a746  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001a74d  nop     dword ptr [rax+rax+00h]
0x14001a752  xor     r11d, r11d
0x14001a755  mov     rdi, rax
0x14001a758  test    rax, rax
0x14001a75b  jz      loc_14001AAF5
0x14001a761  xor     edx, edx; Val
0x14001a763  mov     r8d, 600h; Size
0x14001a769  mov     rcx, rax; void *
0x14001a76c  call    memset
0x14001a771  xor     r11d, r11d
0x14001a774  mov     r12b, 1
0x14001a777  mov     edx, r11d
0x14001a77a  mov     [rbp+57h+arg_18], r12b
0x14001a77e  lea     rcx, [rdx+rdx*2]
0x14001a782  inc     rdx
0x14001a785  lea     rax, [rdi+8]
0x14001a789  lea     rax, [rax+rcx*8]
0x14001a78d  mov     [rdi+rcx*8+10h], rax
0x14001a792  cmp     rdx, 40h ; '@'
0x14001a796  jnz     short loc_14001A77E
0x14001a798  jmp     loc_14001A541
0x14001a79d  mov     dl, 1
0x14001a79f  mov     rcx, r13
0x14001a7a2  call    VmsExtIoPacketRouted
0x14001a7a7  jmp     loc_14001A6A7
0x14001a7ac  mov     rax, [rbp+57h+var_68]
0x14001a7b0  mov     [rax], r11
0x14001a7b3  test    rdi, rdi
0x14001a7b6  jz      loc_14001A9F0
0x14001a7bc  mov     rdx, r11
0x14001a7bf  lea     rax, [rdx+rdx*2]
0x14001a7c3  inc     rdx
0x14001a7c6  mov     rcx, [rdi+rax*8+10h]
0x14001a7cb  mov     [rcx], r11
0x14001a7ce  cmp     rdx, 40h ; '@'
0x14001a7d2  jnz     short loc_14001A7BF
0x14001a7d4  jmp     loc_14001A5EB
0x14001a7d9  mov     rdx, qword ptr [rbp+57h+var_78+8]; NetBufferList
0x14001a7dd  test    rdx, rdx
0x14001a7e0  jnz     loc_14001A9CD
0x14001a7e6  test    rdi, rdi
0x14001a7e9  jz      loc_14001AC61
0x14001a7ef  cmp     [rbp+57h+arg_10], 0
0x14001a7f3  jnz     loc_14001AC25
0x14001a7f9  movzx   eax, word ptr [rbp+57h+var_80]
0x14001a7fd  lea     r9, [rax+rax*2]
0x14001a801  mov     rdx, [rdi+r9*8+8]; NetBufferList
0x14001a806  test    rdx, rdx
0x14001a809  jz      loc_14001A6AC
0x14001a80f  mov     r9d, [rdi+r9*8]; NumberOfNetBufferLists
0x14001a813  xor     r8d, r8d; PortNumber
0x14001a816  mov     rcx, [r15+10C8h]; MiniportAdapterHandle
0x14001a81d  mov     [rsp+0C0h+ReceiveFlags], esi; ReceiveFlags
0x14001a821  call    cs:__imp_NdisMIndicateReceiveNetBufferLists
0x14001a828  nop     dword ptr [rax+rax+00h]
0x14001a82d  jmp     loc_14001A6AC
0x14001a832  cmp     dword ptr [rcx+100h], 3
0x14001a839  jz      loc_14001A737
0x14001a83f  jmp     loc_14001A537
0x14001a844  lea     r8, [rbp+57h+NumberOfNetBufferLists]
0x14001a848  mov     qword ptr [rbp+57h+NumberOfNetBufferLists], r11
0x14001a84c  mov     rdx, rbx
0x14001a84f  mov     rcx, r15
0x14001a852  call    VmsExtMpNdisSwitchGetNblDestinations
0x14001a857  mov     rdx, qword ptr [rbp+57h+NumberOfNetBufferLists]
0x14001a85b  xor     r11d, r11d
0x14001a85e  mov     ecx, r11d
0x14001a861  mov     r8d, [rdx+0Ch]
0x14001a865  cmp     ecx, r8d
0x14001a868  jnb     loc_14001A91E
0x14001a86e  mov     rax, [rdx+10h]
0x14001a872  mov     r14d, ecx
0x14001a875  imul    r14d, [rdx+4]
0x14001a87a  mov     r13, [r14+rax+8]
0x14001a87f  test    r13, r13
0x14001a882  jz      loc_14001A943
0x14001a888  cmp     dword ptr [r13+750h], 2
0x14001a890  jnz     loc_14001A943
0x14001a896  movzx   r14d, word ptr [r14+rax+4]
0x14001a89c  mov     word ptr [rbp+57h+NumberOfNetBufferLists], r14w
0x14001a8a1  test    r14w, r14w
0x14001a8a5  jnz     loc_14001A97F
0x14001a8ab  mov     rcx, [r15+2328h]
0x14001a8b2  lea     r8, [rbp+57h+NumberOfNetBufferLists]
0x14001a8b6  mov     rdx, rbx
0x14001a8b9  call    VmsTmDistributeOutgoingNbls
0x14001a8be  xor     r11d, r11d
0x14001a8c1  test    eax, eax
0x14001a8c3  jnz     loc_14001AB79
0x14001a8c9  mov     rcx, [r13+38h]; Lock
0x14001a8cd  lea     rdx, [rbp+57h+var_90]; LockState
0x14001a8d1  mov     r12, [r13+0CF0h]
0x14001a8d8  xor     r8d, r8d; Flags
0x14001a8db  call    cs:__imp_NdisAcquireRWLockRead
0x14001a8e2  nop     dword ptr [rax+rax+00h]
0x14001a8e7  movzx   r14d, word ptr [rbp+57h+NumberOfNetBufferLists]
0x14001a8ec  mov     rcx, r13
0x14001a8ef  movzx   edx, r14w
0x14001a8f3  call    VmsPtGetNicHeaderAtIndex
0x14001a8f8  test    rax, rax
0x14001a8fb  jz      short loc_14001A903
0x14001a8fd  cmp     byte ptr [rax+14h], 0
0x14001a901  jnz     short loc_14001A94A
0x14001a903  mov     rcx, [r13+38h]; Lock
0x14001a907  lea     rdx, [rbp+57h+var_90]; LockState
0x14001a90b  call    cs:__imp_NdisReleaseRWLock
0x14001a912  nop     dword ptr [rax+rax+00h]
0x14001a917  mov     r12b, [rbp+57h+arg_18]
0x14001a91b  xor     r11d, r11d
0x14001a91e  mov     rax, [rbp+57h+var_68]
0x14001a922  mov     rcx, [rbp+5Fh]
0x14001a926  mov     [rax], rbx
0x14001a929  inc     [rbp+57h+var_78]
0x14001a92c  mov     eax, cs:VmsDiagnosticFlags
0x14001a932  test    al, 1
0x14001a934  jnz     loc_14001AAA8
0x14001a93a  mov     [rbp+57h+var_68], rbx
0x14001a93e  jmp     loc_14001A5C7
0x14001a943  inc     ecx
0x14001a945  jmp     loc_14001A865
0x14001a94a  cmp     dword ptr [r12+r14*4+660h], 3
0x14001a953  jnz     short loc_14001A903
0x14001a955  movzx   r9d, r14w
0x14001a959  mov     rdx, r13
0x14001a95c  mov     rcx, rbx
0x14001a95f  call    VmsNblUpdateDestinationForSet
0x14001a964  mov     rcx, [r13+38h]; Lock
0x14001a968  lea     rdx, [rbp+57h+var_90]; LockState
0x14001a96c  call    cs:__imp_NdisReleaseRWLock
0x14001a973  nop     dword ptr [rax+rax+00h]
0x14001a978  mov     r12b, [rbp+57h+arg_18]
0x14001a97c  xor     r11d, r11d
0x14001a97f  cmp     r14w, 3Fh ; '?'
0x14001a984  ja      loc_14001AB83
  ... truncated ...
```
