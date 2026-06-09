# InetAcquireWildcardPortUnderLock

- ea: `0x14005d620`
- end: `0x14005e013`
- name: `InetAcquireWildcardPortUnderLock`
- size: `2547`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005c758`

## callees

- `0x14005d620`
- `0x14005e124`
- `0x14005e190`
- `0x14005e300`
- `0x14005e360`
- `0x14005e5a0`
- `0x14005ea60`
- `0x140060600`
- `0x1400606a4`
- `0x140095af0`
- `0x14014f600`
- `0x1401527b4`
- `0x1401528fc`
- `0x140152cc8`
- `0x14015a758`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!RtlClearBit` at `0x1401c526b`
- `ntoskrnl!RtlClearBit` at `0x1401c526b`
- `ntoskrnl!RtlTestBit` at `0x14005de49`
- `ntoskrnl!RtlTestBit` at `0x14005de49`
- `ntoskrnl!RtlFindClearBits` at `0x14005d75d`
- `ntoskrnl!RtlFindClearBits` at `0x14005ddf9`
- `ntoskrnl!RtlFindClearBits` at `0x14005d75d`
- `ntoskrnl!RtlFindClearBits` at `0x14005ddf9`
- `ntoskrnl!RtlSetBit` at `0x14005d93a`
- `ntoskrnl!RtlSetBit` at `0x14005d93a`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005def0`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005def0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d7db`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005da93`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005dcbb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d7db`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005da93`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005dcbb`
- `ntoskrnl!PsGetProcessId` at `0x14005df03`
- `ntoskrnl!PsGetProcessId` at `0x14005df03`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d94a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d9f7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005dab7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005db74`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005db8f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005dc51`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005dcee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e001`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d94a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d9f7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005dab7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005db74`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005db8f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005dc51`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005dcee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e001`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14005d6c3`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14005d6c3`
- `NETIO!NetioNcmQueryRtcPortRange` at `0x14005dad1`
- `NETIO!NetioNcmQueryRtcPortRange` at `0x14005dad1`
- `NETIO!NetioNcmIsOwningProcessRtcApp` at `0x14005dae1`
- `NETIO!NetioNcmIsOwningProcessRtcApp` at `0x14005dae1`
- `NETIO!NetioNcmQueryRtcPortHint` at `0x14005dd15`
- `NETIO!NetioNcmQueryRtcPortHint` at `0x14005dd81`
- `NETIO!NetioNcmQueryRtcPortHint` at `0x14005dd15`
- `NETIO!NetioNcmQueryRtcPortHint` at `0x14005dd81`
- `NETIO!NetioNcmStoreRtcPortHint` at `0x14005decf`
- `NETIO!NetioNcmStoreRtcPortHint` at `0x14005decf`
- `cng!SystemPrng` at `0x14005d709`
- `cng!SystemPrng` at `0x14005d709`

## pseudocode

```c
__int64 __fastcall InetAcquireWildcardPortUnderLock(
        __int64 a1,
        int a2,
        __int64 a3,
        struct _KPROCESS *a4,
        _WORD *a5,
        unsigned __int16 a6,
        __int64 a7,
        __int64 a8,
        unsigned __int8 a9,
        char a10)
{
  char v11; // r14
  char v12; // bl
  char v13; // r12
  unsigned __int16 v14; // r15
  int v15; // esi
  char i; // si
  ULONG ClearBits; // eax
  unsigned __int64 v18; // rdi
  ULONG v19; // ecx
  __int64 v20; // rbx
  __int64 v21; // r14
  unsigned int *v22; // rsi
  char v23; // al
  int *v24; // r15
  int v25; // ecx
  int v26; // esi
  int v27; // r12d
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // r8d
  int v32; // eax
  int v33; // edx
  int v34; // ecx
  int v35; // r8d
  int v36; // r12d
  unsigned int v37; // eax
  unsigned int v38; // edi
  unsigned int v39; // eax
  int v40; // ecx
  int v41; // ecx
  __int64 v42; // rcx
  char ProcessSequenceNumber; // si
  unsigned int ProcessId; // r9d
  int v46; // [rsp+20h] [rbp-C9h]
  char v47; // [rsp+50h] [rbp-99h]
  char v48; // [rsp+51h] [rbp-98h]
  unsigned __int8 v49; // [rsp+52h] [rbp-97h]
  char v50; // [rsp+53h] [rbp-96h]
  __int16 v51; // [rsp+54h] [rbp-95h] BYREF
  unsigned __int16 v52[2]; // [rsp+58h] [rbp-91h] BYREF
  ULONG HintIndex; // [rsp+5Ch] [rbp-8Dh] BYREF
  char v54; // [rsp+60h] [rbp-89h]
  _WORD v55[2]; // [rsp+64h] [rbp-85h] BYREF
  int v56; // [rsp+68h] [rbp-81h] BYREF
  int v57; // [rsp+6Ch] [rbp-7Dh]
  int v58; // [rsp+70h] [rbp-79h]
  int v59; // [rsp+74h] [rbp-75h]
  PRTL_BITMAP BitMapHeader; // [rsp+78h] [rbp-71h]
  __int64 v61; // [rsp+80h] [rbp-69h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-61h] BYREF
  __int64 v63; // [rsp+A0h] [rbp-49h]
  PEPROCESS Process; // [rsp+A8h] [rbp-41h]
  unsigned int *v65; // [rsp+B0h] [rbp-39h]
  __int64 v66; // [rsp+B8h] [rbp-31h]
  _WORD *v67; // [rsp+C0h] [rbp-29h]
  _WORD v68[2]; // [rsp+C8h] [rbp-21h] BYREF
  int v69; // [rsp+CCh] [rbp-1Dh]
  int v70; // [rsp+D0h] [rbp-19h]
  __int128 v71; // [rsp+D8h] [rbp-11h] BYREF

  v61 = a8;
  v11 = 0;
  v59 = a2;
  v12 = 0;
  v67 = a5;
  v13 = a2;
  Process = a4;
  BitMapHeader = (PRTL_BITMAP)(a1 + 208);
  v66 = a3;
  v14 = 0;
  v63 = a7;
  HintIndex = 0;
  v51 = 0;
  v47 = 0;
  v56 = 0;
  v49 = 0;
  v48 = 0;
  v58 = -1073741303;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( a7 && a10 && *(_QWORD *)(a7 + 40) )
  {
    BitMapHeader = *(PRTL_BITMAP *)(a7 + 40);
    v47 = 1;
  }
  if ( (unsigned __int8)NetioNcmFastCheckIsAoAcCapable() )
  {
    NetioNcmQueryRtcPortRange(&v56, *(unsigned int *)(a1 + 104));
    if ( ((unsigned __int8)NetioNcmIsOwningProcessRtcApp(Process) || (v13 & 0x40) != 0) && (v13 & 4) == 0 )
    {
      v11 = 1;
      v49 = 1;
    }
    else
    {
      v12 = 1;
      v48 = 1;
    }
  }
  v50 = 0;
  v54 = 0;
  v15 = v13 & 4;
  v57 = v15;
LABEL_4:
  if ( v15 )
  {
    v52[0] = 0;
    SystemPrng(v52, 2);
    HintIndex = v52[0] % (unsigned int)*(unsigned __int16 *)(a1 + 146)
              + (unsigned __int16)__ROR2__(*(_WORD *)(a1 + 144), 8);
  }
  else if ( v11 )
  {
    NetioNcmQueryRtcPortHint(&HintIndex, *(unsigned int *)(a1 + 104));
  }
  else
  {
    HintIndex = *(_DWORD *)(a1 + 204);
  }
LABEL_6:
  for ( i = v47; ; i = v47 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            if ( v14 >= 3u
              || (ClearBits = RtlFindClearBits((PRTL_BITMAP)(a1 + 208), 1u, HintIndex), v18 = ClearBits, ClearBits == -1) )
            {
LABEL_92:
              v38 = v58;
              if ( v58 != -1073741303 )
                return v38;
              goto LABEL_120;
            }
            if ( ClearBits < HintIndex )
              v51 = ++v14;
            if ( !v12 )
              break;
            v37 = (unsigned __int16)__ROR2__(v56, 8);
            if ( (unsigned int)v18 < v37 || (unsigned int)v18 >= (unsigned __int16)(HIWORD(v56) + v37) )
              break;
            HintIndex = (unsigned __int16)(HIWORD(v56) + v37);
          }
          if ( !i )
            break;
          v39 = RtlFindClearBits(BitMapHeader, 1u, v18);
          if ( v39 == -1 )
            goto LABEL_92;
          if ( v39 == (_DWORD)v18 )
            break;
          if ( v39 < (unsigned int)v18 )
            v51 = ++v14;
          HintIndex = v39;
        }
        v19 = (unsigned __int16)__ROR2__(*(_WORD *)(a1 + 144), 8);
        if ( (unsigned int)v18 >= v19 )
          break;
        HintIndex = v19;
      }
      if ( (unsigned int)v18 < v19 + *(unsigned __int16 *)(a1 + 146) )
        break;
      ++v14;
      HintIndex = v19;
      v51 = v14;
    }
    LOBYTE(v52[0]) = 0;
    v20 = *(_QWORD *)(a1 + 8 * (v18 >> 8) + 224);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v20, &LockHandle);
    while ( *(_DWORD *)(v20 + 8) )
      ;
    v21 = 32LL * (unsigned __int8)v18;
    v22 = (unsigned int *)(v21 + *(_QWORD *)(v20 + 24));
    v65 = v22;
    if ( !*(_WORD *)(v20 + 16) || (unsigned __int8)IsEmptyAssignment(v22) )
    {
      v23 = v52[0];
    }
    else
    {
      if ( !v47 || RtlTestBit(BitMapHeader, v18) || (*v22 & 1) == 0 )
      {
        HintIndex = *(_DWORD *)(a1 + 204);
        if ( (*v22 & 1) != 0 )
          HintIndex = v18 + 1;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        goto LABEL_64;
      }
      v23 = 1;
      LOBYTE(v52[0]) = 1;
    }
    if ( !v50 && *(_QWORD *)(v20 + 24) && *v22 >= 0x20 )
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v54 = 1;
      HintIndex = v18 + 1;
LABEL_64:
      v11 = v49;
      goto LABEL_82;
    }
    if ( v66 )
    {
      v24 = &v56;
      v55[0] = 0;
      if ( !v49 )
        v24 = (int *)(a1 + 144);
      v25 = WfpAleValidateWildcardPort((_DWORD)v24, v66, a6, v63, __ROR2__(v18, 8), (__int64)&v51, (__int64)v55);
      if ( !v25 )
      {
        v26 = 0;
        goto LABEL_25;
      }
      v40 = v25 - 1;
      if ( v40 )
      {
        v41 = v40 - 1;
        if ( !v41 )
        {
          v26 = 2;
LABEL_25:
          if ( dword_1402201D4 )
          {
            v71 = 0;
            if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 12) & 8) != 0 )
            {
              *(_QWORD *)&v71 = v24;
              McTemplateK0ppqqq_EtwWriteTransfer(
                &MICROSOFT_TCPIP_PROVIDER_Context,
                &INET_INSPECT_PORT,
                &v71,
                v24,
                v66,
                17,
                v26,
                0);
            }
          }
          if ( v26 == 1 )
          {
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            return 3221225506LL;
          }
          if ( v26 == 3 )
          {
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            v14 = v51;
            v12 = v48;
            v11 = v49;
            HintIndex = (unsigned __int16)__ROR2__(v55[0], 8);
            goto LABEL_6;
          }
          v14 = v51;
          v22 = v65;
          v23 = v52[0];
          goto LABEL_31;
        }
        if ( v41 == 1 )
        {
          v26 = 3;
          goto LABEL_25;
        }
      }
      v26 = 1;
      goto LABEL_25;
    }
LABEL_31:
    if ( !v23 )
    {
      if ( !(unsigned __int8)InitializeAssignmentArray(v20) )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        return 3221225626LL;
      }
      v27 = v59;
      v22 = (unsigned int *)(v21 + *(_QWORD *)(v20 + 24));
      v65 = v22;
      v28 = *v22;
      if ( v47 )
      {
        v29 = v28 & 0xFFFFFFE0 | 1;
      }
      else
      {
        if ( (v59 & 8) != 0 )
        {
          *v22 = v28 & 0xFFFFFFE0 | 2;
          InitializeAssignmentPerProcEndpointTable(v22);
          goto LABEL_37;
        }
        v29 = v28 & 0xFFFFFFE0;
      }
      *v22 = v29;
LABEL_37:
      InsertEndpointInAssignment(a1, (_DWORD)v22, v61, a9, a6, v63, v27);
      ++*(_WORD *)(v20 + 16);
      goto LABEL_38;
    }
    LOBYTE(v27) = v59;
    InsertEndpointInAssignment(a1, (_DWORD)v22, v61, a9, a6, v63, v59);
LABEL_38:
    RtlSetBit(BitMapHeader, v18);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v11 = v49;
    v30 = ((int)v18 + 1) % 0xFFFFu;
    if ( v49 )
    {
      v42 = (unsigned __int16)__ROR2__(v56, 8);
      if ( v30 >= (unsigned int)v42 )
        v42 = v30;
      NetioNcmStoreRtcPortHint(v42, *(unsigned int *)(a1 + 104));
    }
    else
    {
      _InterlockedExchange((volatile __int32 *)(a1 + 204), v30);
    }
    if ( !PortTrackerEnabled )
      goto LABEL_41;
    *(_QWORD *)&v71 = 0;
    v55[0] = 0;
    v69 = *(_DWORD *)(a1 + 104);
    v32 = 16;
    v68[0] = v18 + (unsigned int)v18 / 0xFFFF;
    v68[1] = v68[0];
    if ( (v27 & 0x10) != 0 )
      v32 = 32;
    v70 = v32;
    v58 = PtClientReservePortRange(v68, &v71, v55);
    v36 = v58;
    if ( !v58 )
      break;
    if ( SBYTE1(WPP_MAIN_CB.Reserved) < 0 )
    {
      if ( Process )
      {
        ProcessSequenceNumber = PsGetProcessSequenceNumber(Process);
        ProcessId = (unsigned int)PsGetProcessId(Process);
      }
      else
      {
        ProcessSequenceNumber = -1;
        ProcessId = -1;
      }
      McTemplateK0qqqqhhx_EtwWriteTransfer(
        v34,
        v33,
        v35,
        ProcessId,
        v36,
        v70,
        *(_DWORD *)(a1 + 104),
        v68[0],
        1,
        ProcessSequenceNumber);
      v22 = v65;
    }
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v20, &LockHandle);
    while ( *(_DWORD *)(v20 + 8) )
      ;
    RemoveEndpointFromAssignment(v22, v61);
    if ( (unsigned __int8)IsEmptyAssignment(v22) )
    {
      if ( (*v22 & 2) != 0 )
        CleanupAssignmentPerProcEndpointTable();
      *v22 &= 0xFFFFFFE0;
      if ( (*(_WORD *)(v20 + 16))-- == 1 )
        DereferenceAssignmentArray(v20);
      RtlClearBit(BitMapHeader, v18);
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v36 != -1073740024 )
    {
      if ( v36 != -1073741801 && v36 != 258 )
      {
        v12 = v48;
        v38 = -1073741303;
        v58 = -1073741303;
LABEL_120:
        if ( v11 )
        {
          v11 = 0;
          v14 = 0;
          v49 = 0;
          v51 = 0;
          if ( (BYTE3(WPP_MAIN_CB.Reserved) & 0x10) != 0 )
          {
            LOWORD(v46) = 0;
            McTemplateK0qh_EtwWriteTransfer(
              &MICROSOFT_TCPIP_PROVIDER_Context,
              &TCP_RTC_PORT_RANGE_ASSIGNMENT,
              &MICROSOFT_TCPIP_PROVIDER,
              0,
              v46);
          }
          goto LABEL_91;
        }
        if ( v12 )
        {
          v12 = 0;
          v48 = 0;
LABEL_90:
          v14 = 0;
          v51 = 0;
LABEL_91:
          v15 = v57;
          goto LABEL_4;
        }
        if ( !v50 && v54 == 1 )
        {
          v50 = 1;
          goto LABEL_90;
        }
        InetLogThrottledPortPoolEvent(*(unsigned int *)(a1 + 200), a1 + 192);
        return v38;
      }
      return 3221225626LL;
    }
    if ( !v49 )
    {
      v12 = v48;
      HintIndex = *(_DWORD *)(a1 + 204);
      goto LABEL_6;
    }
    NetioNcmQueryRtcPortHint(&HintIndex, *(unsigned int *)(a1 + 104));
LABEL_82:
    v12 = v48;
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v20, &LockHandle);
  while ( *(_DWORD *)(v20 + 8) )
    ;
  *(_QWORD *)(v61 + 8) = v71;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_41:
  *v67 = __ROR2__(v18, 8);
  if ( (BYTE6(WPP_MAIN_CB.Reserved) & 2) != 0 && v50 == 1 && v22 && *v22 >= 0x20 )
    McTemplateK0phqp_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      (unsigned int)&TCP_ASSIGNED_WEAK_REFERENCE_PORT,
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER,
      0,
      v18,
      0,
      0);
  if ( v49 )
  {
    if ( (BYTE3(WPP_MAIN_CB.Reserved) & 0x10) != 0 )
    {
      LOWORD(v46) = v18;
      McTemplateK0qh_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        &TCP_RTC_PORT_RANGE_ASSIGNMENT,
        &MICROSOFT_TCPIP_PROVIDER,
        v49,
        v46);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14005d620  mov     [rsp-8+arg_8], rbx
0x14005d625  push    rbp
0x14005d626  push    rsi
0x14005d627  push    rdi
0x14005d628  push    r12
0x14005d62a  push    r13
0x14005d62c  push    r14
0x14005d62e  push    r15
0x14005d630  lea     rbp, [rsp-7]
0x14005d635  sub     rsp, 0F0h
0x14005d63c  mov     rax, cs:__security_cookie
0x14005d643  xor     rax, rsp
0x14005d646  mov     [rbp+37h+var_38], rax
0x14005d64a  mov     rax, [rbp+37h+arg_20]
0x14005d64e  mov     r13, rcx
0x14005d651  mov     rcx, [rbp+37h+arg_38]
0x14005d655  xor     sil, sil
0x14005d658  mov     [rbp+37h+var_A0], rcx
0x14005d65c  xor     r14b, r14b
0x14005d65f  xor     ecx, ecx
0x14005d661  mov     [rbp+37h+var_AC], edx
0x14005d664  xor     bl, bl
0x14005d666  mov     [rbp+37h+var_60], rax
0x14005d66a  mov     rax, [rbp+37h+arg_30]
0x14005d66e  mov     r12d, edx
0x14005d671  xor     edx, edx
0x14005d673  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rcx
0x14005d677  mov     [rbp+37h+Process], r9
0x14005d67b  lea     rcx, [r13+0D0h]
0x14005d682  mov     [rbp+37h+BitMapHeader], rcx
0x14005d686  xorps   xmm0, xmm0
0x14005d689  mov     [rbp+37h+var_68], r8
0x14005d68d  mov     r15d, edx
0x14005d690  mov     [rbp+37h+var_80], rax
0x14005d694  mov     [rsp+120h+HintIndex], edx
0x14005d698  mov     [rsp+120h+var_CC], dx
0x14005d69d  mov     [rsp+120h+var_D0], sil
0x14005d6a2  mov     [rsp+120h+var_B8], edx
0x14005d6a6  mov     [rsp+120h+var_CE], r14b
0x14005d6ab  mov     [rsp+120h+var_CF], bl
0x14005d6af  mov     [rbp+37h+var_B0], 0C0000209h
0x14005d6b6  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x14005d6ba  test    rax, rax
0x14005d6bd  jnz     loc_14005DD36
0x14005d6c3  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x14005d6ca  nop     dword ptr [rax+rax+00h]
0x14005d6cf  test    al, al
0x14005d6d1  jnz     loc_14005DAC8
0x14005d6d7  mov     [rsp+120h+var_CD], sil
0x14005d6dc  mov     [rsp+120h+var_C0], sil
0x14005d6e1  mov     esi, r12d
0x14005d6e4  and     esi, 4
0x14005d6e7  mov     r12d, 1
0x14005d6ed  mov     [rbp+37h+var_B4], esi
0x14005d6f0  test    esi, esi
0x14005d6f2  jz      loc_14005DA14
0x14005d6f8  xor     eax, eax
0x14005d6fa  lea     rcx, [rsp+120h+var_C8]
0x14005d6ff  mov     edx, 2
0x14005d704  mov     [rsp+120h+var_C8], ax
0x14005d709  call    cs:__imp_SystemPrng
0x14005d710  nop     dword ptr [rax+rax+00h]
0x14005d715  movzx   eax, word ptr [r13+90h]
0x14005d71d  xor     edx, edx
0x14005d71f  movzx   ecx, word ptr [r13+92h]
0x14005d727  ror     ax, 8
0x14005d72b  movzx   r8d, ax
0x14005d72f  movzx   eax, [rsp+120h+var_C8]
0x14005d734  div     ecx
0x14005d736  add     r8d, edx
0x14005d739  mov     [rsp+120h+HintIndex], r8d
0x14005d73e  movzx   esi, [rsp+120h+var_D0]
0x14005d743  cmp     r15w, 3
0x14005d748  jnb     loc_14005DDB3
0x14005d74e  mov     r8d, [rsp+120h+HintIndex]; HintIndex
0x14005d753  lea     rcx, [r13+0D0h]; BitMapHeader
0x14005d75a  mov     edx, r12d; NumberToFind
0x14005d75d  call    cs:__imp_RtlFindClearBits
0x14005d764  nop     dword ptr [rax+rax+00h]
0x14005d769  mov     edi, eax
0x14005d76b  cmp     eax, 0FFFFFFFFh
0x14005d76e  jz      loc_14005DDB3
0x14005d774  cmp     edi, [rsp+120h+HintIndex]
0x14005d778  jb      loc_14005DDE0
0x14005d77e  test    bl, bl
0x14005d780  jnz     loc_14005DBC1
0x14005d786  test    sil, sil
0x14005d789  jnz     loc_14005DDEF
0x14005d78f  lea     r12, [r13+90h]
0x14005d796  movzx   eax, word ptr [r12]
0x14005d79b  ror     ax, 8
0x14005d79f  movzx   ecx, ax
0x14005d7a2  cmp     edi, ecx
0x14005d7a4  jb      loc_14005DE27
0x14005d7aa  movzx   eax, word ptr [r13+92h]
0x14005d7b2  add     eax, ecx
0x14005d7b4  cmp     edi, eax
0x14005d7b6  jnb     loc_14005DE30
0x14005d7bc  mov     rbx, rdi
0x14005d7bf  mov     byte ptr [rsp+120h+var_C8], 0
0x14005d7c4  shr     rbx, 8
0x14005d7c8  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x14005d7cc  movzx   esi, dil
0x14005d7d0  mov     rbx, [r13+rbx*8+0E0h]
0x14005d7d8  mov     rcx, rbx; SpinLock
0x14005d7db  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005d7e2  nop     dword ptr [rax+rax+00h]
0x14005d7e7  mov     eax, [rbx+8]
0x14005d7ea  test    eax, eax
0x14005d7ec  jnz     short loc_14005D7E7
0x14005d7ee  mov     r14, rsi
0x14005d7f1  mov     rsi, [rbx+18h]
0x14005d7f5  shl     r14, 5
0x14005d7f9  add     rsi, r14
0x14005d7fc  mov     [rbp+37h+var_70], rsi
0x14005d800  cmp     [rbx+10h], ax
0x14005d804  jnz     loc_14005DB41
0x14005d80a  movzx   eax, byte ptr [rsp+120h+var_C8]
0x14005d80f  cmp     [rsp+120h+var_CD], 0
0x14005d814  jz      loc_14005D9DF
0x14005d81a  mov     rcx, [rbp+37h+var_68]
0x14005d81e  test    rcx, rcx
0x14005d821  jz      loc_14005D8BF
0x14005d827  mov     r9, [rbp+37h+var_80]
0x14005d82b  lea     rdx, [rsp+120h+var_BC]
0x14005d830  movzx   r8d, [rbp+37h+arg_28]
0x14005d835  lea     r15, [rsp+120h+var_B8]
0x14005d83a  xor     eax, eax
0x14005d83c  mov     [rsp+120h+var_F0], rdx
0x14005d841  cmp     [rsp+120h+var_CE], al
0x14005d845  lea     rdx, [rsp+120h+var_CC]
0x14005d84a  mov     [rsp+120h+var_BC], ax
0x14005d84f  movzx   eax, di
0x14005d852  cmovz   r15, r12
0x14005d856  mov     [rsp+120h+var_F8], rdx
0x14005d85b  ror     ax, 8
0x14005d85f  mov     rdx, rcx
0x14005d862  mov     rcx, r15
0x14005d865  mov     word ptr [rsp+120h+var_100], ax
0x14005d86a  call    WfpAleValidateWildcardPort
0x14005d86f  mov     ecx, eax
0x14005d871  mov     r12d, 1
0x14005d877  test    eax, eax
0x14005d879  jnz     loc_14005DE7E
0x14005d87f  xor     esi, esi
0x14005d881  cmp     cs:dword_1402201D4, 0
0x14005d888  jz      short loc_14005D89E
0x14005d88a  test    byte ptr cs:WPP_MAIN_CB+14Ch, 8
0x14005d891  xorps   xmm0, xmm0
0x14005d894  movups  [rbp+37h+var_48], xmm0
0x14005d898  jnz     loc_14005DC67
0x14005d89e  cmp     esi, 1
0x14005d8a1  jz      loc_14005DC4D
0x14005d8a7  cmp     esi, 3
0x14005d8aa  jz      loc_14005DB8B
0x14005d8b0  movzx   r15d, [rsp+120h+var_CC]
0x14005d8b6  mov     rsi, [rbp+37h+var_70]
0x14005d8ba  movzx   eax, byte ptr [rsp+120h+var_C8]
0x14005d8bf  test    al, al
0x14005d8c1  jnz     loc_14005DB0A
0x14005d8c7  mov     rcx, rbx
0x14005d8ca  call    InitializeAssignmentArray
0x14005d8cf  test    al, al
0x14005d8d1  jz      loc_14005DFFD
0x14005d8d7  mov     rsi, [rbx+18h]
0x14005d8db  mov     r12d, [rbp+37h+var_AC]
0x14005d8df  add     rsi, r14
0x14005d8e2  cmp     [rsp+120h+var_D0], 0
0x14005d8e7  mov     [rbp+37h+var_70], rsi
0x14005d8eb  mov     eax, [rsi]
0x14005d8ed  jnz     loc_14005DBED
0x14005d8f3  test    r12b, 8
0x14005d8f7  jnz     loc_14005DEA3
0x14005d8fd  and     eax, 0FFFFFFE0h
0x14005d900  mov     [rsi], eax
0x14005d902  mov     rax, [rbp+37h+var_80]
0x14005d906  mov     rdx, rsi
0x14005d909  movzx   r9d, [rbp+37h+arg_40]
0x14005d911  mov     rcx, r13
0x14005d914  mov     r8, [rbp+37h+var_A0]
0x14005d918  mov     dword ptr [rsp+120h+var_F0], r12d
0x14005d91d  mov     [rsp+120h+var_F8], rax
0x14005d922  movzx   eax, [rbp+37h+arg_28]
0x14005d926  mov     word ptr [rsp+120h+var_100], ax
0x14005d92b  call    InsertEndpointInAssignment
0x14005d930  inc     word ptr [rbx+10h]
0x14005d934  mov     rcx, [rbp+37h+BitMapHeader]; BitMapHeader
0x14005d938  mov     edx, edi; BitNumber
0x14005d93a  call    cs:__imp_RtlSetBit
0x14005d941  nop     dword ptr [rax+rax+00h]
0x14005d946  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14005d94a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005d951  nop     dword ptr [rax+rax+00h]
0x14005d956  movzx   r14d, [rsp+120h+var_CE]
0x14005d95c  lea     r8d, [rdi+1]
0x14005d960  mov     eax, 80008001h
0x14005d965  mul     r8d
0x14005d968  shr     edx, 0Fh
0x14005d96b  imul    eax, edx, 0FFFFh
0x14005d971  sub     r8d, eax
0x14005d974  test    r14b, r14b
0x14005d977  jnz     loc_14005DEB8
0x14005d97d  xchg    r8d, [r13+0CCh]
0x14005d984  cmp     cs:PortTrackerEnabled, 0
0x14005d98b  jnz     loc_14005DA2D
0x14005d991  mov     rcx, [rbp+37h+var_60]
0x14005d995  movzx   eax, di
0x14005d998  ror     ax, 8
0x14005d99c  mov     [rcx], ax
0x14005d99f  test    byte ptr cs:WPP_MAIN_CB.Reserved+6, 2
0x14005d9a6  jnz     loc_14005DBF8
0x14005d9ac  test    r14b, r14b
0x14005d9af  jnz     loc_14005DFC9
0x14005d9b5  xor     eax, eax
0x14005d9b7  mov     rcx, [rbp+37h+var_38]
0x14005d9bb  xor     rcx, rsp; StackCookie
0x14005d9be  call    __security_check_cookie
0x14005d9c3  mov     rbx, [rsp+120h+arg_8]
0x14005d9cb  add     rsp, 0F0h
0x14005d9d2  pop     r15
0x14005d9d4  pop     r14
0x14005d9d6  pop     r13
0x14005d9d8  pop     r12
0x14005d9da  pop     rdi
0x14005d9db  pop     rsi
0x14005d9dc  pop     rbp
0x14005d9dd  retn
0x14005d9df  cmp     qword ptr [rbx+18h], 0
0x14005d9e4  jz      loc_14005D81A
0x14005d9ea  cmp     dword ptr [rsi], 20h ; ' '
0x14005d9ed  jb      loc_14005D81A
0x14005d9f3  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14005d9f7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005d9fe  nop     dword ptr [rax+rax+00h]
0x14005da03  lea     eax, [rdi+1]
0x14005da06  mov     [rsp+120h+var_C0], 1
0x14005da0b  mov     [rsp+120h+HintIndex], eax
0x14005da0f  jmp     loc_14005DB80
0x14005da14  test    r14b, r14b
0x14005da17  jnz     loc_14005DD78
0x14005da1d  mov     eax, [r13+0CCh]
0x14005da24  mov     [rsp+120h+HintIndex], eax
0x14005da28  jmp     loc_14005D73E
0x14005da2d  xor     eax, eax
0x14005da2f  mov     qword ptr [rbp+37h+var_48], 0
0x14005da37  mov     [rsp+120h+var_BC], ax
0x14005da3c  lea     r8, [rsp+120h+var_BC]
0x14005da41  mov     eax, 80008001h
0x14005da46  mov     ecx, 20h ; ' '
0x14005da4b  mul     edi
0x14005da4d  mov     eax, [r13+68h]
0x14005da51  shr     edx, 0Fh
0x14005da54  add     dx, di
0x14005da57  mov     [rbp+37h+var_54], eax
0x14005da5a  mov     eax, 10h
0x14005da5f  mov     [rbp+37h+var_58], dx
0x14005da63  mov     [rbp+37h+var_56], dx
0x14005da67  test    r12b, 10h
0x14005da6b  lea     rdx, [rbp+37h+var_48]
0x14005da6f  cmovnz  eax, ecx
0x14005da72  lea     rcx, [rbp+37h+var_58]
0x14005da76  mov     [rbp+37h+var_50], eax
0x14005da79  call    PtClientReservePortRange
0x14005da7e  mov     [rbp+37h+var_B0], eax
0x14005da81  mov     r12d, eax
0x14005da84  test    eax, eax
0x14005da86  jnz     loc_14005DCA7
0x14005da8c  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x14005da90  mov     rcx, rbx; SpinLock
0x14005da93  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005da9a  nop     dword ptr [rax+rax+00h]
0x14005da9f  nop
0x14005daa0  mov     eax, [rbx+8]
0x14005daa3  test    eax, eax
0x14005daa5  jnz     short loc_14005DAA0
0x14005daa7  mov     rcx, [rbp+37h+var_A0]
0x14005daab  mov     rax, qword ptr [rbp+37h+var_48]
0x14005daaf  mov     [rcx+8], rax
0x14005dab3  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14005dab7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005dabe  nop     dword ptr [rax+rax+00h]
0x14005dac3  jmp     loc_14005D991
0x14005dac8  mov     edx, [r13+68h]
0x14005dacc  lea     rcx, [rsp+120h+var_B8]
0x14005dad1  call    cs:__imp_NetioNcmQueryRtcPortRange
0x14005dad8  nop     dword ptr [rax+rax+00h]
0x14005dadd  mov     rcx, [rbp+37h+Process]
0x14005dae1  call    cs:__imp_NetioNcmIsOwningProcessRtcApp
0x14005dae8  nop     dword ptr [rax+rax+00h]
0x14005daed  test    al, al
0x14005daef  jnz     loc_14005DDC9
0x14005daf5  test    r12b, 40h
0x14005daf9  jnz     loc_14005DDC9
0x14005daff  mov     bl, 1
0x14005db01  mov     [rsp+120h+var_CF], bl
0x14005db05  jmp     loc_14005D6D7
0x14005db0a  mov     rax, [rbp+37h+var_80]
0x14005db0e  mov     rdx, rsi
0x14005db11  mov     r12d, [rbp+37h+var_AC]
0x14005db15  mov     rcx, r13
  ... truncated ...
```
