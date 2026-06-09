# VmsExtMpSendNetBufferLists

- ea: `0x14001e8f0`
- end: `0x14001f246`
- name: `VmsExtMpSendNetBufferLists`
- size: `2390`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140017ca8`
- `0x140018330`
- `0x140018558`
- `0x140019560`
- `0x1400195e0`
- `0x14001a49c`
- `0x14001d1b8`
- `0x14001d520`
- `0x14001e8f0`
- `0x140027a64`
- `0x14002a170`
- `0x14002a1fc`
- `0x14002c5d4`
- `0x14002fd8c`
- `0x1400329f0`
- `0x14003308c`
- `0x14008497c`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001eb10`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001eb10`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001eaab`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001efed`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001eaab`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001efed`
- `NDIS!NdisAcquireRWLockRead` at `0x14001eaca`
- `NDIS!NdisAcquireRWLockRead` at `0x14001eaca`
- `NDIS!NdisReleaseRWLock` at `0x14001eb3a`
- `NDIS!NdisReleaseRWLock` at `0x14001eb3a`

## string_xrefs

- `0x14001ebc8`: `VmsNblHelperAppendNblsMoveLast`
- `0x14001ed4e`: `VmsNblHelperAppendNblsMoveLast`
- `0x14001edcc`: `VmsNblHelperAppendNblsMoveLast`
- `0x14001ef27`: `(curNblContext->Flags & (VMS_NBL_ROUTING_CONTEXT_FLAG_NEEDS_FILTER_EGRESS_COMPLETION | VMS_NBL_ROUTING_CONTEXT_FLAG_NEEDS_MP_INGRESS_COMPLETION | VMS_NBL_ROUTING_CONTEXT_FLAG_NEEDS_PT_EGRESS_COMPLETION | VMS_NBL_ROUTING_CONTEXT_FLAG_RESTORE_HANDLE_ON_EGRESS_COMPLETE)) == 0`

## pseudocode

```c
void __fastcall VmsExtMpSendNetBufferLists(__int64 a1, __int64 *a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // r12
  __int64 v5; // r9
  const char *v6; // r10
  __int64 *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rsi
  int v12; // r15d
  char v13; // r12
  __int64 *v14; // r14
  __int64 v15; // rdi
  __int64 v16; // rdi
  __int64 *v17; // rax
  int v18; // edx
  UCHAR v19; // r8
  int v20; // r12d
  char v21; // bl
  int v22; // edi
  char v23; // r14
  __int64 v24; // rdx
  __int64 v25; // r9
  __int64 v26; // r11
  __int64 *v27; // rbx
  struct _NET_BUFFER_LIST *v28; // rcx
  __int64 *v29; // rcx
  unsigned int v30; // ebx
  __int64 *v31; // rdi
  __int16 *v32; // r10
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  _QWORD *v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 *v43; // rdi
  __int64 v44; // rax
  __int64 v45; // rax
  char v46; // r14
  __int64 v47; // rax
  __int64 v48; // r15
  int v49; // edx
  _QWORD *i; // rdi
  __int64 *j; // rdi
  __int64 v52; // rax
  __int64 v53; // r8
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 LockState; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v58; // [rsp+38h] [rbp-48h]
  __int64 *v59; // [rsp+40h] [rbp-40h] BYREF
  struct _NET_BUFFER_LIST *v60; // [rsp+48h] [rbp-38h] BYREF
  struct _NET_BUFFER_LIST *v61; // [rsp+50h] [rbp-30h] BYREF
  __int64 *v62; // [rsp+58h] [rbp-28h] BYREF
  __int64 *v63; // [rsp+60h] [rbp-20h] BYREF
  __int64 **v64; // [rsp+68h] [rbp-18h]
  struct _NET_BUFFER_LIST **v65; // [rsp+70h] [rbp-10h] BYREF
  __int64 **v66; // [rsp+78h] [rbp-8h] BYREF
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+38h]
  char v68; // [rsp+C0h] [rbp+40h]
  char v69; // [rsp+C8h] [rbp+48h]
  unsigned int v70; // [rsp+D8h] [rbp+58h] BYREF

  v70 = a4;
  v4 = a4;
  v5 = 0;
  LOWORD(LockState) = 0;
  BYTE2(LockState) = 0;
  v6 = "VmsExtMpSendNetBufferLists";
  v8 = a2;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( a2 )
    {
      v33 = a2[36];
      if ( v33 )
      {
        v34 = *(_QWORD *)(v33 + 16);
        if ( v34 )
        {
          *(_QWORD *)(v34 + 176) = "VmsExtMpSendNetBufferLists";
          *(_DWORD *)(v34 + 184) = 3720;
          *(_QWORD *)(v34 + 168) = retaddr;
        }
      }
    }
  }
  v59 = 0;
  v62 = 0;
  v69 = v4 & 1;
  v66 = &v59;
  v65 = &v60;
  v64 = &v63;
  v60 = 0;
  v63 = 0;
  BYTE4(LockState) = 0;
  if ( (v4 & 0x20) != 0 )
  {
    if ( VmsVerifierEnabled && !(unsigned __int8)VmsNblHelperVerifySingleSourcePort(a2) )
    {
      VmsTrcVerifierFailure(40972, v8, v4, a1);
      v5 = 0;
      v6 = "VmsExtMpSendNetBufferLists";
    }
    v68 = 1;
  }
  else
  {
    v68 = VmsNblHelperVerifySingleSourcePort(a2);
    if ( v68 )
      v70 = v4 | 0x20;
  }
  if ( *((_WORD *)v8 + 149) == (_WORD)v5 )
  {
    v11 = *(_QWORD *)(a1 + 6480);
  }
  else
  {
    v9 = v8[36];
    v10 = v5;
    if ( v9 )
      v10 = *(_QWORD *)(v9 + 16);
    v11 = *(_QWORD *)(v10 + 24);
  }
  if ( *(_DWORD *)(v11 + 1872) == 2 || *(_BYTE *)(v11 + 4072) == (_BYTE)v5 )
    LOWORD(v12) = *((_WORD *)v8 + 129);
  else
    v12 = *(_DWORD *)(v11 + 4188);
  v13 = v68;
  v58 = v5;
  do
  {
    v14 = (__int64 *)*v8;
    if ( (VmsDiagnosticFlags & 1) != 0 )
    {
      if ( v14 )
      {
        v35 = v14[36];
        if ( v35 )
        {
          v36 = *(_QWORD *)(v35 + 16);
          if ( v36 )
          {
            *(_QWORD *)(v36 + 176) = v6;
            *(_DWORD *)(v36 + 184) = 3801;
            *(_QWORD *)(v36 + 168) = retaddr;
          }
        }
      }
    }
    *v8 = v5;
    v15 = v8[36];
    if ( v15 )
      v16 = *(_QWORD *)(v15 + 16);
    else
      v16 = v5;
    *(_DWORD *)(v16 + 16) = *((unsigned __int16 *)v8 + 129);
    if ( v13 )
    {
      *((_WORD *)v8 + 129) = v12;
    }
    else if ( *((_WORD *)v8 + 149) != (_WORD)v5 && *(_DWORD *)(v11 + 1872) != 2 && *(_BYTE *)(v11 + 4072) != (_BYTE)v5 )
    {
      *((_WORD *)v8 + 129) = *(_WORD *)(*(_QWORD *)(v16 + 24) + 4188LL);
    }
    if ( (*(_DWORD *)v16 & 0x4B0) != 0 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        (unsigned int)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
        19,
        103,
        (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
        "(curNblContext->Flags & (VMS_NBL_ROUTING_CONTEXT_FLAG_NEEDS_FILTER_EGRESS_COMPLETION | VMS_NBL_ROUTING_CONTEXT_F"
        "LAG_NEEDS_MP_INGRESS_COMPLETION | VMS_NBL_ROUTING_CONTEXT_FLAG_NEEDS_PT_EGRESS_COMPLETION | VMS_NBL_ROUTING_CONT"
        "EXT_FLAG_RESTORE_HANDLE_ON_EGRESS_COMPLETE)) == 0",
        LockState);
      if ( (*(_DWORD *)v16 & 0x4B0) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    *(_DWORD *)v16 |= 0x80u;
    if ( (*(_DWORD *)v16 & 0x200) == 0 )
    {
      if ( *(_QWORD *)(v16 + 8) != v8[15] )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          (unsigned int)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
          19,
          104,
          (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
          "curNblContext->OriginalSourceHandle == curNbl->SourceHandle");
        if ( *(_QWORD *)(v16 + 8) != v8[15] )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      *(_DWORD *)v16 |= 0x800u;
      if ( (*(_BYTE *)(a1 + 1232) & 8) != 0 )
        *((_DWORD *)v8 + 75) |= 0x100u;
    }
    v5 = 0;
    if ( (VmsDiagnosticFlags & 1) != 0 )
    {
      v37 = v8[36];
      if ( v37 )
      {
        v38 = *(_QWORD *)(v37 + 16);
        if ( v38 )
        {
          *(_DWORD *)(v38 + 184) = 2646;
          *(_QWORD *)(v38 + 176) = "VmsNblHelperAppendNblsMoveLast";
          *(_QWORD *)(v38 + 168) = retaddr;
        }
      }
    }
    *v64 = v8;
    do
    {
      v17 = (__int64 *)*v8;
      v64 = (__int64 **)v8;
      v8 = v17;
    }
    while ( v17 );
    ++v58;
    v6 = "VmsExtMpSendNetBufferLists";
    v13 = v68;
    v8 = v14;
  }
  while ( v14 );
  if ( v69 )
  {
    if ( KeGetCurrentIrql() != 2 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v18,
        19,
        24,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        "KeGetCurrentIrql() == DISPATCH_LEVEL");
      if ( KeGetCurrentIrql() != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v19 = 1;
  }
  else
  {
    v19 = 0;
  }
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 56), (PLOCK_STATE_EX)&LockState, v19);
  v20 = v70;
  v21 = *(_BYTE *)(a1 + 1232) & 1;
  v22 = *(_DWORD *)(a1 + 8916);
  v23 = BYTE4(LockState);
  if ( VmsRequiredExtensionNotPresentDrop && *(_DWORD *)(v11 + 1872) == 3 && *(_BYTE *)(a1 + 5195) != 1 )
    v23 = 1;
  if ( !v21 && v22 != 1 && !v23 )
    _InterlockedAdd64(
      (volatile signed __int64 *)(*(_QWORD *)(a1 + 6472) + ((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6) + 24),
      v58);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), (PLOCK_STATE_EX)&LockState);
  v26 = 0;
  if ( v21 )
  {
    v30 = -536870883;
  }
  else if ( v22 == 1 )
  {
    v30 = -536870881;
  }
  else
  {
    if ( !v23 )
    {
      v27 = v63;
      if ( (*(_BYTE *)(a1 + 1232) & 8) != 0 || !v63 )
      {
        if ( v68 )
        {
          if ( v63 )
          {
            LOBYTE(v25) = 1;
            VmsIoExtForwardNetBufferLists(v11, (_DWORD)v63, v20, v25, (__int64)&v61, (__int64)&v62);
            v28 = v61;
            if ( (VmsDiagnosticFlags & 1) != 0 )
            {
              if ( v61 )
              {
                v39 = v61->NetBufferListInfo[18];
                if ( v39 )
                {
                  v40 = v39[2];
                  if ( v40 )
                  {
                    *(_DWORD *)(v40 + 184) = 2646;
                    *(_QWORD *)(v40 + 176) = "VmsNblHelperAppendNblsMoveLast";
                    *(_QWORD *)(v40 + 168) = retaddr;
                  }
                }
              }
            }
            v60 = v28;
            v29 = v62;
            if ( (VmsDiagnosticFlags & 1) != 0 )
            {
              if ( v62 )
              {
                v41 = v62[36];
                if ( v41 )
                {
                  v42 = *(_QWORD *)(v41 + 16);
                  if ( v42 )
                  {
                    *(_QWORD *)(v42 + 176) = "VmsNblHelperAppendNblsMoveLast";
                    *(_DWORD *)(v42 + 184) = 2646;
                    *(_QWORD *)(v42 + 168) = retaddr;
                  }
                }
              }
            }
            v59 = v29;
          }
        }
        else if ( v63 )
        {
          do
          {
            v43 = (__int64 *)*v27;
            if ( (VmsDiagnosticFlags & 1) != 0 )
            {
              if ( v43 )
              {
                v44 = v43[36];
                if ( v44 )
                {
                  v45 = *(_QWORD *)(v44 + 16);
                  if ( v45 )
                  {
                    *(_QWORD *)(v45 + 176) = "VmsExtMpSendNetBufferLists";
                    *(_DWORD *)(v45 + 184) = 4099;
                    *(_QWORD *)(v45 + 168) = retaddr;
                  }
                }
              }
            }
            *v27 = v26;
            if ( (*((_DWORD *)v27 + 75) & 0x100) != 0 )
            {
              if ( *((_WORD *)v27 + 149) == (_WORD)v26 )
              {
                v54 = *(_QWORD *)(a1 + 6480);
              }
              else
              {
                v55 = v27[36];
                if ( v55 )
                  v56 = *(_QWORD *)(v55 + 16);
                else
                  v56 = v26;
                v54 = *(_QWORD *)(v56 + 24);
              }
              VmsIoExtForwardNetBufferLists(v54, (_DWORD)v27, v20, 0, (__int64)&v61, (__int64)&v62);
              VmsNblHelperAppendNblsMoveLast(&v65, v61);
              VmsNblHelperAppendNblsMoveLast(&v66, v62);
              v26 = 0;
            }
            else
            {
              VmsNblHelperAppendNblsMoveLast(&v65, v27);
            }
            v27 = v43;
          }
          while ( v43 );
        }
      }
      else
      {
        if ( (v20 & 0x10) != 0 || (unsigned __int8)VmsNblHelperIsDestinationGroup(v63, v24) )
          v46 = 1;
        else
          v46 = v26;
        if ( *(_DWORD *)(a1 + 1432) != (_DWORD)v26 )
        {
          if ( v46 )
          {
            v47 = v27[36];
            v48 = v26;
            if ( v47 )
              v48 = *(_QWORD *)(v47 + 16);
            LOBYTE(v25) = v69;
            if ( (unsigned __int8)VmsRouterAddMonitorDestinations(v11, *(_QWORD *)(v11 + 1984), v48 + 40, v25) == 1 )
            {
              VmsNblHelperUpdateDestinationForwardingDetail(v27);
              if ( *v27 )
              {
                if ( *(_DWORD *)(v48 + 68) <= 1u )
                {
                  WPP_RECORDER_SF_s(
                    VmsIfrLog,
                    v49,
                    19,
                    105,
                    (__int64)WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids,
                    "destList->DestinationArray.NumDestinations > 1");
                  if ( *(_DWORD *)(v48 + 68) <= 1u )
                    MicrosoftTelemetryAssertTriggeredNoArgsKM();
                }
                for ( i = (_QWORD *)*v27; i; i = (_QWORD *)*i )
                  VmsNblHelperCopyNblDestinations(*(_QWORD *)(v11 + 1888), i, v48 + 40);
              }
              v46 = 0;
            }
          }
          else
          {
            for ( j = v27; j; v26 = 0 )
            {
              v52 = j[36];
              v53 = v26;
              if ( v52 )
                v53 = *(_QWORD *)(v52 + 16);
              LOBYTE(v25) = v69;
              VmsRouterAddMonitorDestinations(v11, *(_QWORD *)(v11 + 1984), v53 + 40, v25);
              VmsNblHelperUpdateDestinationForwardingDetail(j);
              j = (__int64 *)*j;
            }
          }
        }
        VmsExtMpIndicatePackets(a1, (struct _NET_BUFFER_LIST *)v27, v20, v46);
      }
      if ( v60 )
        VmsExtMpIndicatePackets(a1, v60, v20, 0);
      if ( v59 )
        VmsNblHelperRefCountDecrementMany(v59, 1);
      return;
    }
    v30 = -536870876;
  }
  v31 = v63;
  if ( v63 )
  {
    LOBYTE(v25) = 1;
    VmsPktReportDroppedPacketEx(v11, (_DWORD)v63, 2, v25, v30, -536862716);
    VmsExtIoPacketRouted(v31, 0);
  }
  if ( v59 )
  {
    v70 = 0;
    VmsPktGetDropReason(v30, &v70);
    VmsPktReportDroppedNblChain(v11, v32, 1, v70, v30, -536862715);
    VmsExtIoPacketRouted(v59, 0);
  }
}

```

## disassembly

```asm
0x14001e8f0  mov     [rsp-38h+arg_10], rbx
0x14001e8f5  mov     [rsp-38h+arg_18], r9d
0x14001e8fa  push    rbp
0x14001e8fb  push    rsi
0x14001e8fc  push    rdi
0x14001e8fd  push    r12
0x14001e8ff  push    r13
0x14001e901  push    r14
0x14001e903  push    r15
0x14001e905  mov     rbp, rsp
0x14001e908  sub     rsp, 80h
0x14001e90f  xor     eax, eax
0x14001e911  mov     r12d, r9d
0x14001e914  xor     r9d, r9d
0x14001e917  mov     word ptr [rbp+LockState.OldIrql], ax
0x14001e91b  mov     [rbp+LockState.Flags], al
0x14001e91e  lea     r10, aVmsextmpsendne; "VmsExtMpSendNetBufferLists"
0x14001e925  mov     eax, cs:VmsDiagnosticFlags
0x14001e92b  mov     r13, rcx
0x14001e92e  mov     rcx, [rbp+38h]
0x14001e932  mov     rbx, rdx
0x14001e935  lea     edi, [r9+1]
0x14001e939  mov     [rbp+var_40], r9
0x14001e93d  mov     [rbp+var_38], r9
0x14001e941  mov     [rbp+var_30], r9
0x14001e945  test    dil, al
0x14001e948  jnz     loc_14001EC9C
0x14001e94e  mov     al, r12b
0x14001e951  mov     [rbp+var_40], r9
0x14001e955  and     al, dil
0x14001e958  mov     [rbp+var_28], r9
0x14001e95c  mov     [rbp+arg_8], al
0x14001e95f  lea     rax, [rbp+var_40]
0x14001e963  mov     [rbp+var_8], rax
0x14001e967  lea     rax, [rbp+var_38]
0x14001e96b  mov     [rbp+var_10], rax
0x14001e96f  lea     rax, [rbp+var_20]
0x14001e973  mov     [rbp+var_18], rax
0x14001e977  mov     [rbp+var_38], r9
0x14001e97b  mov     [rbp+var_20], r9
0x14001e97f  mov     byte ptr [rbp+var_4C], r9b
0x14001e983  test    r12b, 20h
0x14001e987  jz      loc_14001EC24
0x14001e98d  cmp     cs:VmsVerifierEnabled, r9b
0x14001e994  jnz     loc_14001EEA7
0x14001e99a  mov     [rbp+arg_0], dil
0x14001e99e  cmp     [rbx+12Ah], r9w
0x14001e9a6  jz      loc_14001EE33
0x14001e9ac  mov     rax, [rbx+120h]
0x14001e9b3  mov     rsi, r9
0x14001e9b6  test    rax, rax
0x14001e9b9  jz      short loc_14001E9BF
0x14001e9bb  mov     rsi, [rax+10h]
0x14001e9bf  mov     rsi, [rsi+18h]
0x14001e9c3  cmp     dword ptr [rsi+750h], 2
0x14001e9ca  jnz     loc_14001ED7A
0x14001e9d0  movzx   r15d, word ptr [rbx+102h]
0x14001e9d8  mov     r12b, [rbp+arg_0]
0x14001e9dc  lea     rdx, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x14001e9e3  mov     [rbp+var_48], r9d
0x14001e9e7  mov     eax, cs:VmsDiagnosticFlags
0x14001e9ed  mov     r14, [rbx]
0x14001e9f0  mov     rcx, [rbp+38h]
0x14001e9f4  test    dil, al
0x14001e9f7  jnz     loc_14001ECEE
0x14001e9fd  mov     [rbx], r9
0x14001ea00  mov     rdi, [rbx+120h]
0x14001ea07  test    rdi, rdi
0x14001ea0a  jz      loc_14001EED9
0x14001ea10  mov     rdi, [rdi+10h]
0x14001ea14  movzx   eax, word ptr [rbx+102h]
0x14001ea1b  mov     [rdi+10h], eax
0x14001ea1e  test    r12b, r12b
0x14001ea21  jz      loc_14001EEE1
0x14001ea27  mov     [rbx+102h], r15w
0x14001ea2f  test    dword ptr [rdi], 4B0h
0x14001ea35  jnz     loc_14001EF20
0x14001ea3b  bts     dword ptr [rdi], 7
0x14001ea3f  test    dword ptr [rdi], 200h
0x14001ea45  jz      loc_14001EF60
0x14001ea4b  mov     eax, cs:VmsDiagnosticFlags
0x14001ea51  mov     edi, 1
0x14001ea56  mov     rcx, [rbp+38h]
0x14001ea5a  xor     r9d, r9d
0x14001ea5d  test    dil, al
0x14001ea60  jnz     loc_14001ED31
0x14001ea66  mov     r12, [rbp+var_18]
0x14001ea6a  mov     [r12], rbx
0x14001ea6e  mov     rax, [rbx]
0x14001ea71  mov     [rbp+var_18], rbx
0x14001ea75  mov     rbx, rax
0x14001ea78  test    rax, rax
0x14001ea7b  jnz     short loc_14001EA6E
0x14001ea7d  add     [rbp+var_48], edi
0x14001ea80  lea     r10, aVmsextmpsendne; "VmsExtMpSendNetBufferLists"
0x14001ea87  mov     r12b, [rbp+arg_0]
0x14001ea8b  mov     rbx, r14
0x14001ea8e  lea     rdx, WPP_211e17b6d37e3e8765befcac8f9ff3e2_Traceguids
0x14001ea95  test    r14, r14
0x14001ea98  jnz     loc_14001E9E7
0x14001ea9e  mov     r15b, [rbp+arg_8]
0x14001eaa2  test    r15b, r15b
0x14001eaa5  jz      loc_14001ED72
0x14001eaab  call    cs:__imp_KeGetCurrentIrql
0x14001eab2  nop     dword ptr [rax+rax+00h]
0x14001eab7  cmp     al, 2
0x14001eab9  jnz     loc_14001EFBF
0x14001eabf  mov     r8b, dil; Flags
0x14001eac2  mov     rcx, [r13+38h]; Lock
0x14001eac6  lea     rdx, [rbp+LockState]; LockState
0x14001eaca  call    cs:__imp_NdisAcquireRWLockRead
0x14001ead1  nop     dword ptr [rax+rax+00h]
0x14001ead6  mov     bl, [r13+4D0h]
0x14001eadd  mov     eax, 1
0x14001eae2  mov     r12d, [rbp+arg_18]
0x14001eae6  and     bl, dil
0x14001eae9  cmp     cs:VmsRequiredExtensionNotPresentDrop, 0
0x14001eaf0  mov     edi, [r13+22D4h]
0x14001eaf7  mov     r14d, [rbp+var_4C]
0x14001eafb  jnz     loc_14001F00B
0x14001eb01  test    bl, bl
0x14001eb03  jnz     short loc_14001EB32
0x14001eb05  cmp     edi, eax
0x14001eb07  jz      short loc_14001EB32
0x14001eb09  test    r14b, r14b
0x14001eb0c  jnz     short loc_14001EB32
0x14001eb0e  xor     ecx, ecx; ProcNumber
0x14001eb10  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14001eb17  nop     dword ptr [rax+rax+00h]
0x14001eb1c  mov     ecx, [rbp+var_48]
0x14001eb1f  mov     edx, eax
0x14001eb21  mov     rax, [r13+1948h]
0x14001eb28  shl     rdx, 6
0x14001eb2c  lock add [rax+rdx+18h], rcx
0x14001eb32  mov     rcx, [r13+38h]; Lock
0x14001eb36  lea     rdx, [rbp+LockState]; LockState
0x14001eb3a  call    cs:__imp_NdisReleaseRWLock
0x14001eb41  nop     dword ptr [rax+rax+00h]
0x14001eb46  xor     r11d, r11d
0x14001eb49  lea     r8d, [r11+1]
0x14001eb4d  test    bl, bl
0x14001eb4f  jnz     loc_14001EC44
0x14001eb55  cmp     edi, r8d
0x14001eb58  jz      loc_14001F20A
0x14001eb5e  test    r14b, r14b
0x14001eb61  jnz     loc_14001F200
0x14001eb67  test    byte ptr [r13+4D0h], 8
0x14001eb6f  mov     rbx, [rbp+var_20]
0x14001eb73  jz      loc_14001F02C
0x14001eb79  cmp     [rbp+arg_0], r11b
0x14001eb7d  jz      loc_14001F16B
0x14001eb83  test    rbx, rbx
0x14001eb86  jz      short loc_14001EBEE
0x14001eb88  lea     rax, [rbp+var_28]
0x14001eb8c  mov     r9b, r8b
0x14001eb8f  mov     [rsp+80h+var_58], rax
0x14001eb94  mov     r8d, r12d
0x14001eb97  lea     rax, [rbp+var_30]
0x14001eb9b  mov     rdx, rbx
0x14001eb9e  mov     rcx, rsi
0x14001eba1  mov     [rsp+80h+var_60], rax
0x14001eba6  call    VmsIoExtForwardNetBufferLists
0x14001ebab  mov     eax, cs:VmsDiagnosticFlags
0x14001ebb1  mov     r8d, 1
0x14001ebb7  mov     rcx, [rbp+var_30]
0x14001ebbb  mov     rdx, [rbp+38h]
0x14001ebbf  test    r8b, al
0x14001ebc2  jnz     loc_14001EDA6
0x14001ebc8  lea     r9, aVmsnblhelperap; "VmsNblHelperAppendNblsMoveLast"
0x14001ebcf  mov     eax, cs:VmsDiagnosticFlags
0x14001ebd5  mov     rdx, [rbp+38h]
0x14001ebd9  mov     [rbp+var_38], rcx
0x14001ebdd  mov     rcx, [rbp+var_28]
0x14001ebe1  test    r8b, al
0x14001ebe4  jnz     loc_14001EDF0
0x14001ebea  mov     [rbp+var_40], rcx
0x14001ebee  mov     rdx, [rbp+var_38]
0x14001ebf2  test    rdx, rdx
0x14001ebf5  jnz     loc_14001ED93
0x14001ebfb  mov     rcx, [rbp+var_40]
0x14001ebff  test    rcx, rcx
0x14001ec02  jnz     loc_14001ECDF
0x14001ec08  mov     rbx, [rsp+80h+arg_10]
0x14001ec10  add     rsp, 80h
0x14001ec17  pop     r15
0x14001ec19  pop     r14
0x14001ec1b  pop     r13
0x14001ec1d  pop     r12
0x14001ec1f  pop     rdi
0x14001ec20  pop     rsi
0x14001ec21  pop     rbp
0x14001ec22  retn
0x14001ec24  mov     rcx, rbx
0x14001ec27  call    VmsNblHelperVerifySingleSourcePort
0x14001ec2c  mov     [rbp+arg_0], al
0x14001ec2f  test    al, al
0x14001ec31  jz      loc_14001E99E
0x14001ec37  or      r12d, 20h
0x14001ec3b  mov     [rbp+arg_18], r12d
0x14001ec3f  jmp     loc_14001E99E
0x14001ec44  mov     ebx, 0E000001Dh
0x14001ec49  mov     rdi, [rbp+var_20]
0x14001ec4d  test    rdi, rdi
0x14001ec50  jnz     loc_14001F214
0x14001ec56  mov     r10, [rbp+var_40]
0x14001ec5a  test    r10, r10
0x14001ec5d  jz      short loc_14001EC08
0x14001ec5f  lea     rdx, [rbp+arg_18]
0x14001ec63  mov     [rbp+arg_18], r11d
0x14001ec67  mov     ecx, ebx
0x14001ec69  call    VmsPktGetDropReason
0x14001ec6e  mov     r9d, [rbp+arg_18]
0x14001ec72  mov     r8b, 1
0x14001ec75  mov     rcx, rsi
0x14001ec78  mov     dword ptr [rsp+80h+var_58], 0E0002005h
0x14001ec80  mov     rdx, r10
0x14001ec83  mov     dword ptr [rsp+80h+var_60], ebx
0x14001ec87  call    VmsPktReportDroppedNblChain
0x14001ec8c  mov     rcx, [rbp+var_40]
0x14001ec90  xor     edx, edx
0x14001ec92  call    VmsExtIoPacketRouted
0x14001ec97  jmp     loc_14001EC08
0x14001ec9c  test    rbx, rbx
0x14001ec9f  jz      loc_14001E94E
0x14001eca5  mov     rax, [rdx+120h]
0x14001ecac  test    rax, rax
0x14001ecaf  jz      loc_14001E94E
0x14001ecb5  mov     rax, [rax+10h]
0x14001ecb9  test    rax, rax
0x14001ecbc  jz      loc_14001E94E
0x14001ecc2  mov     [rax+0B0h], r10
0x14001ecc9  mov     dword ptr [rax+0B8h], 0E88h
0x14001ecd3  mov     [rax+0A8h], rcx
0x14001ecda  jmp     loc_14001E94E
0x14001ecdf  mov     edx, 1
0x14001ece4  call    VmsNblHelperRefCountDecrementMany
0x14001ece9  jmp     loc_14001EC08
0x14001ecee  test    r14, r14
0x14001ecf1  jz      loc_14001E9FD
0x14001ecf7  mov     rax, [r14+120h]
0x14001ecfe  test    rax, rax
0x14001ed01  jz      loc_14001E9FD
0x14001ed07  mov     rax, [rax+10h]
0x14001ed0b  test    rax, rax
0x14001ed0e  jz      loc_14001E9FD
0x14001ed14  mov     [rax+0B0h], r10
0x14001ed1b  mov     dword ptr [rax+0B8h], 0ED9h
0x14001ed25  mov     [rax+0A8h], rcx
0x14001ed2c  jmp     loc_14001E9FD
0x14001ed31  mov     rax, [rbx+120h]
0x14001ed38  test    rax, rax
0x14001ed3b  jz      loc_14001EA66
0x14001ed41  mov     rax, [rax+10h]
0x14001ed45  test    rax, rax
0x14001ed48  jz      loc_14001EA66
0x14001ed4e  lea     rdx, aVmsnblhelperap; "VmsNblHelperAppendNblsMoveLast"
0x14001ed55  mov     dword ptr [rax+0B8h], 0A56h
0x14001ed5f  mov     [rax+0B0h], rdx
0x14001ed66  mov     [rax+0A8h], rcx
0x14001ed6d  jmp     loc_14001EA66
0x14001ed72  xor     r8d, r8d
0x14001ed75  jmp     loc_14001EAC2
0x14001ed7a  cmp     [rsi+0FE8h], r9b
0x14001ed81  jz      loc_14001E9D0
0x14001ed87  mov     r15d, [rsi+105Ch]
0x14001ed8e  jmp     loc_14001E9D8
0x14001ed93  xor     r9d, r9d
0x14001ed96  mov     r8d, r12d
0x14001ed99  mov     rcx, r13
0x14001ed9c  call    VmsExtMpIndicatePackets
0x14001eda1  jmp     loc_14001EBFB
0x14001eda6  test    rcx, rcx
0x14001eda9  jz      loc_14001EBC8
0x14001edaf  mov     rax, [rcx+120h]
0x14001edb6  test    rax, rax
0x14001edb9  jz      loc_14001EBC8
0x14001edbf  mov     rax, [rax+10h]
0x14001edc3  test    rax, rax
0x14001edc6  jz      loc_14001EBC8
0x14001edcc  lea     r9, aVmsnblhelperap; "VmsNblHelperAppendNblsMoveLast"
0x14001edd3  mov     dword ptr [rax+0B8h], 0A56h
0x14001eddd  mov     [rax+0B0h], r9
0x14001ede4  mov     [rax+0A8h], rdx
0x14001edeb  jmp     loc_14001EBCF
0x14001edf0  test    rcx, rcx
0x14001edf3  jz      loc_14001EBEA
0x14001edf9  mov     rax, [rcx+120h]
0x14001ee00  test    rax, rax
0x14001ee03  jz      loc_14001EBEA
0x14001ee09  mov     rax, [rax+10h]
0x14001ee0d  test    rax, rax
0x14001ee10  jz      loc_14001EBEA
0x14001ee16  mov     [rax+0B0h], r9
0x14001ee1d  mov     dword ptr [rax+0B8h], 0A56h
0x14001ee27  mov     [rax+0A8h], rdx
0x14001ee2e  jmp     loc_14001EBEA
0x14001ee33  mov     rsi, [r13+1950h]
0x14001ee3a  jmp     loc_14001E9C3
0x14001ee3f  mov     eax, cs:VmsDiagnosticFlags
0x14001ee45  mov     rdi, [rbx]
  ... truncated ...
```
