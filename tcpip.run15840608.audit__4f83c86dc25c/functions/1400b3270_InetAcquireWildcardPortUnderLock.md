# InetAcquireWildcardPortUnderLock

- ea: `0x1400b3270`
- end: `0x1400b3c63`
- name: `InetAcquireWildcardPortUnderLock`
- size: `2547`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b23f8`

## callees

- `0x14005d040`
- `0x1400b3270`
- `0x1400b3d74`
- `0x1400b3de0`
- `0x1400b3f50`
- `0x1400b3fb0`
- `0x1400b41f0`
- `0x1400b46b0`
- `0x1400b6b20`
- `0x1400b6bc4`
- `0x140151200`
- `0x140154694`
- `0x1401547dc`
- `0x140154ba8`
- `0x14015c4e8`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!RtlClearBit` at `0x1401cf007`
- `ntoskrnl!RtlClearBit` at `0x1401cf007`
- `ntoskrnl!RtlTestBit` at `0x1400b3a99`
- `ntoskrnl!RtlTestBit` at `0x1400b3a99`
- `ntoskrnl!RtlFindClearBits` at `0x1400b33ad`
- `ntoskrnl!RtlFindClearBits` at `0x1400b3a49`
- `ntoskrnl!RtlFindClearBits` at `0x1400b33ad`
- `ntoskrnl!RtlFindClearBits` at `0x1400b3a49`
- `ntoskrnl!RtlSetBit` at `0x1400b358a`
- `ntoskrnl!RtlSetBit` at `0x1400b358a`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400b3b40`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400b3b40`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b342b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b36e3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b390b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b342b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b36e3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b390b`
- `ntoskrnl!PsGetProcessId` at `0x1400b3b53`
- `ntoskrnl!PsGetProcessId` at `0x1400b3b53`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b359a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b3647`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b3707`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b37c4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b37df`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b38a1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b393e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b3c51`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b359a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b3647`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b3707`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b37c4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b37df`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b38a1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b393e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b3c51`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x1400b3313`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x1400b3313`
- `NETIO!NetioNcmQueryRtcPortRange` at `0x1400b3721`
- `NETIO!NetioNcmQueryRtcPortRange` at `0x1400b3721`
- `NETIO!NetioNcmIsOwningProcessRtcApp` at `0x1400b3731`
- `NETIO!NetioNcmIsOwningProcessRtcApp` at `0x1400b3731`
- `NETIO!NetioNcmQueryRtcPortHint` at `0x1400b3965`
- `NETIO!NetioNcmQueryRtcPortHint` at `0x1400b39d1`
- `NETIO!NetioNcmQueryRtcPortHint` at `0x1400b3965`
- `NETIO!NetioNcmQueryRtcPortHint` at `0x1400b39d1`
- `NETIO!NetioNcmStoreRtcPortHint` at `0x1400b3b1f`
- `NETIO!NetioNcmStoreRtcPortHint` at `0x1400b3b1f`
- `cng!SystemPrng` at `0x1400b3359`
- `cng!SystemPrng` at `0x1400b3359`

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
          if ( dword_1402241D4 )
          {
            v71 = 0;
            if ( (BYTE4(WPP_MAIN_CB.Dpc.DeferredContext) & 8) != 0 )
            {
              *(_QWORD *)&v71 = v24;
              McTemplateK0ppqqq_EtwWriteTransfer(
                &MICROSOFT_TCPIP_PROVIDER_Context,
                INET_INSPECT_PORT,
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
    if ( SBYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
          if ( (BYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x10) != 0 )
          {
            LOWORD(v46) = 0;
            McTemplateK0qh_EtwWriteTransfer(
              &MICROSOFT_TCPIP_PROVIDER_Context,
              TCP_RTC_PORT_RANGE_ASSIGNMENT,
              MICROSOFT_TCPIP_PROVIDER,
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
  if ( (BYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) & 2) != 0 && v50 == 1 && v22 && *v22 >= 0x20 )
    McTemplateK0phqp_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      (unsigned int)TCP_ASSIGNED_WEAK_REFERENCE_PORT,
      (unsigned int)MICROSOFT_TCPIP_PROVIDER,
      0,
      v18,
      0,
      0);
  if ( v49 )
  {
    if ( (BYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x10) != 0 )
    {
      LOWORD(v46) = v18;
      McTemplateK0qh_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCP_RTC_PORT_RANGE_ASSIGNMENT,
        MICROSOFT_TCPIP_PROVIDER,
        v49,
        v46);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400b3270  mov     [rsp-8+arg_8], rbx
0x1400b3275  push    rbp
0x1400b3276  push    rsi
0x1400b3277  push    rdi
0x1400b3278  push    r12
0x1400b327a  push    r13
0x1400b327c  push    r14
0x1400b327e  push    r15
0x1400b3280  lea     rbp, [rsp-7]
0x1400b3285  sub     rsp, 0F0h
0x1400b328c  mov     rax, cs:__security_cookie
0x1400b3293  xor     rax, rsp
0x1400b3296  mov     [rbp+37h+var_38], rax
0x1400b329a  mov     rax, [rbp+37h+arg_20]
0x1400b329e  mov     r13, rcx
0x1400b32a1  mov     rcx, [rbp+37h+arg_38]
0x1400b32a5  xor     sil, sil
0x1400b32a8  mov     [rbp+37h+var_A0], rcx
0x1400b32ac  xor     r14b, r14b
0x1400b32af  xor     ecx, ecx
0x1400b32b1  mov     [rbp+37h+var_AC], edx
0x1400b32b4  xor     bl, bl
0x1400b32b6  mov     [rbp+37h+var_60], rax
0x1400b32ba  mov     rax, [rbp+37h+arg_30]
0x1400b32be  mov     r12d, edx
0x1400b32c1  xor     edx, edx
0x1400b32c3  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rcx
0x1400b32c7  mov     [rbp+37h+Process], r9
0x1400b32cb  lea     rcx, [r13+0D0h]
0x1400b32d2  mov     [rbp+37h+BitMapHeader], rcx
0x1400b32d6  xorps   xmm0, xmm0
0x1400b32d9  mov     [rbp+37h+var_68], r8
0x1400b32dd  mov     r15d, edx
0x1400b32e0  mov     [rbp+37h+var_80], rax
0x1400b32e4  mov     [rsp+120h+HintIndex], edx
0x1400b32e8  mov     [rsp+120h+var_CC], dx
0x1400b32ed  mov     [rsp+120h+var_D0], sil
0x1400b32f2  mov     [rsp+120h+var_B8], edx
0x1400b32f6  mov     [rsp+120h+var_CE], r14b
0x1400b32fb  mov     [rsp+120h+var_CF], bl
0x1400b32ff  mov     [rbp+37h+var_B0], 0C0000209h
0x1400b3306  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x1400b330a  test    rax, rax
0x1400b330d  jnz     loc_1400B3986
0x1400b3313  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x1400b331a  nop     dword ptr [rax+rax+00h]
0x1400b331f  test    al, al
0x1400b3321  jnz     loc_1400B3718
0x1400b3327  mov     [rsp+120h+var_CD], sil
0x1400b332c  mov     [rsp+120h+var_C0], sil
0x1400b3331  mov     esi, r12d
0x1400b3334  and     esi, 4
0x1400b3337  mov     r12d, 1
0x1400b333d  mov     [rbp+37h+var_B4], esi
0x1400b3340  test    esi, esi
0x1400b3342  jz      loc_1400B3664
0x1400b3348  xor     eax, eax
0x1400b334a  lea     rcx, [rsp+120h+var_C8]
0x1400b334f  mov     edx, 2
0x1400b3354  mov     [rsp+120h+var_C8], ax
0x1400b3359  call    cs:__imp_SystemPrng
0x1400b3360  nop     dword ptr [rax+rax+00h]
0x1400b3365  movzx   eax, word ptr [r13+90h]
0x1400b336d  xor     edx, edx
0x1400b336f  movzx   ecx, word ptr [r13+92h]
0x1400b3377  ror     ax, 8
0x1400b337b  movzx   r8d, ax
0x1400b337f  movzx   eax, [rsp+120h+var_C8]
0x1400b3384  div     ecx
0x1400b3386  add     r8d, edx
0x1400b3389  mov     [rsp+120h+HintIndex], r8d
0x1400b338e  movzx   esi, [rsp+120h+var_D0]
0x1400b3393  cmp     r15w, 3
0x1400b3398  jnb     loc_1400B3A03
0x1400b339e  mov     r8d, [rsp+120h+HintIndex]; HintIndex
0x1400b33a3  lea     rcx, [r13+0D0h]; BitMapHeader
0x1400b33aa  mov     edx, r12d; NumberToFind
0x1400b33ad  call    cs:__imp_RtlFindClearBits
0x1400b33b4  nop     dword ptr [rax+rax+00h]
0x1400b33b9  mov     edi, eax
0x1400b33bb  cmp     eax, 0FFFFFFFFh
0x1400b33be  jz      loc_1400B3A03
0x1400b33c4  cmp     edi, [rsp+120h+HintIndex]
0x1400b33c8  jb      loc_1400B3A30
0x1400b33ce  test    bl, bl
0x1400b33d0  jnz     loc_1400B3811
0x1400b33d6  test    sil, sil
0x1400b33d9  jnz     loc_1400B3A3F
0x1400b33df  lea     r12, [r13+90h]
0x1400b33e6  movzx   eax, word ptr [r12]
0x1400b33eb  ror     ax, 8
0x1400b33ef  movzx   ecx, ax
0x1400b33f2  cmp     edi, ecx
0x1400b33f4  jb      loc_1400B3A77
0x1400b33fa  movzx   eax, word ptr [r13+92h]
0x1400b3402  add     eax, ecx
0x1400b3404  cmp     edi, eax
0x1400b3406  jnb     loc_1400B3A80
0x1400b340c  mov     rbx, rdi
0x1400b340f  mov     byte ptr [rsp+120h+var_C8], 0
0x1400b3414  shr     rbx, 8
0x1400b3418  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x1400b341c  movzx   esi, dil
0x1400b3420  mov     rbx, [r13+rbx*8+0E0h]
0x1400b3428  mov     rcx, rbx; SpinLock
0x1400b342b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400b3432  nop     dword ptr [rax+rax+00h]
0x1400b3437  mov     eax, [rbx+8]
0x1400b343a  test    eax, eax
0x1400b343c  jnz     short loc_1400B3437
0x1400b343e  mov     r14, rsi
0x1400b3441  mov     rsi, [rbx+18h]
0x1400b3445  shl     r14, 5
0x1400b3449  add     rsi, r14
0x1400b344c  mov     [rbp+37h+var_70], rsi
0x1400b3450  cmp     [rbx+10h], ax
0x1400b3454  jnz     loc_1400B3791
0x1400b345a  movzx   eax, byte ptr [rsp+120h+var_C8]
0x1400b345f  cmp     [rsp+120h+var_CD], 0
0x1400b3464  jz      loc_1400B362F
0x1400b346a  mov     rcx, [rbp+37h+var_68]
0x1400b346e  test    rcx, rcx
0x1400b3471  jz      loc_1400B350F
0x1400b3477  mov     r9, [rbp+37h+var_80]
0x1400b347b  lea     rdx, [rsp+120h+var_BC]
0x1400b3480  movzx   r8d, [rbp+37h+arg_28]
0x1400b3485  lea     r15, [rsp+120h+var_B8]
0x1400b348a  xor     eax, eax
0x1400b348c  mov     [rsp+120h+var_F0], rdx
0x1400b3491  cmp     [rsp+120h+var_CE], al
0x1400b3495  lea     rdx, [rsp+120h+var_CC]
0x1400b349a  mov     [rsp+120h+var_BC], ax
0x1400b349f  movzx   eax, di
0x1400b34a2  cmovz   r15, r12
0x1400b34a6  mov     [rsp+120h+var_F8], rdx
0x1400b34ab  ror     ax, 8
0x1400b34af  mov     rdx, rcx
0x1400b34b2  mov     rcx, r15
0x1400b34b5  mov     word ptr [rsp+120h+var_100], ax
0x1400b34ba  call    WfpAleValidateWildcardPort
0x1400b34bf  mov     ecx, eax
0x1400b34c1  mov     r12d, 1
0x1400b34c7  test    eax, eax
0x1400b34c9  jnz     loc_1400B3ACE
0x1400b34cf  xor     esi, esi
0x1400b34d1  cmp     cs:dword_1402241D4, 0
0x1400b34d8  jz      short loc_1400B34EE
0x1400b34da  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+4, 8
0x1400b34e1  xorps   xmm0, xmm0
0x1400b34e4  movups  [rbp+37h+var_48], xmm0
0x1400b34e8  jnz     loc_1400B38B7
0x1400b34ee  cmp     esi, 1
0x1400b34f1  jz      loc_1400B389D
0x1400b34f7  cmp     esi, 3
0x1400b34fa  jz      loc_1400B37DB
0x1400b3500  movzx   r15d, [rsp+120h+var_CC]
0x1400b3506  mov     rsi, [rbp+37h+var_70]
0x1400b350a  movzx   eax, byte ptr [rsp+120h+var_C8]
0x1400b350f  test    al, al
0x1400b3511  jnz     loc_1400B375A
0x1400b3517  mov     rcx, rbx
0x1400b351a  call    InitializeAssignmentArray
0x1400b351f  test    al, al
0x1400b3521  jz      loc_1400B3C4D
0x1400b3527  mov     rsi, [rbx+18h]
0x1400b352b  mov     r12d, [rbp+37h+var_AC]
0x1400b352f  add     rsi, r14
0x1400b3532  cmp     [rsp+120h+var_D0], 0
0x1400b3537  mov     [rbp+37h+var_70], rsi
0x1400b353b  mov     eax, [rsi]
0x1400b353d  jnz     loc_1400B383D
0x1400b3543  test    r12b, 8
0x1400b3547  jnz     loc_1400B3AF3
0x1400b354d  and     eax, 0FFFFFFE0h
0x1400b3550  mov     [rsi], eax
0x1400b3552  mov     rax, [rbp+37h+var_80]
0x1400b3556  mov     rdx, rsi
0x1400b3559  movzx   r9d, [rbp+37h+arg_40]
0x1400b3561  mov     rcx, r13
0x1400b3564  mov     r8, [rbp+37h+var_A0]
0x1400b3568  mov     dword ptr [rsp+120h+var_F0], r12d
0x1400b356d  mov     [rsp+120h+var_F8], rax
0x1400b3572  movzx   eax, [rbp+37h+arg_28]
0x1400b3576  mov     word ptr [rsp+120h+var_100], ax
0x1400b357b  call    InsertEndpointInAssignment
0x1400b3580  inc     word ptr [rbx+10h]
0x1400b3584  mov     rcx, [rbp+37h+BitMapHeader]; BitMapHeader
0x1400b3588  mov     edx, edi; BitNumber
0x1400b358a  call    cs:__imp_RtlSetBit
0x1400b3591  nop     dword ptr [rax+rax+00h]
0x1400b3596  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x1400b359a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400b35a1  nop     dword ptr [rax+rax+00h]
0x1400b35a6  movzx   r14d, [rsp+120h+var_CE]
0x1400b35ac  lea     r8d, [rdi+1]
0x1400b35b0  mov     eax, 80008001h
0x1400b35b5  mul     r8d
0x1400b35b8  shr     edx, 0Fh
0x1400b35bb  imul    eax, edx, 0FFFFh
0x1400b35c1  sub     r8d, eax
0x1400b35c4  test    r14b, r14b
0x1400b35c7  jnz     loc_1400B3B08
0x1400b35cd  xchg    r8d, [r13+0CCh]
0x1400b35d4  cmp     cs:PortTrackerEnabled, 0
0x1400b35db  jnz     loc_1400B367D
0x1400b35e1  mov     rcx, [rbp+37h+var_60]
0x1400b35e5  movzx   eax, di
0x1400b35e8  ror     ax, 8
0x1400b35ec  mov     [rcx], ax
0x1400b35ef  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+6, 2
0x1400b35f6  jnz     loc_1400B3848
0x1400b35fc  test    r14b, r14b
0x1400b35ff  jnz     loc_1400B3C19
0x1400b3605  xor     eax, eax
0x1400b3607  mov     rcx, [rbp+37h+var_38]
0x1400b360b  xor     rcx, rsp; StackCookie
0x1400b360e  call    __security_check_cookie
0x1400b3613  mov     rbx, [rsp+120h+arg_8]
0x1400b361b  add     rsp, 0F0h
0x1400b3622  pop     r15
0x1400b3624  pop     r14
0x1400b3626  pop     r13
0x1400b3628  pop     r12
0x1400b362a  pop     rdi
0x1400b362b  pop     rsi
0x1400b362c  pop     rbp
0x1400b362d  retn
0x1400b362f  cmp     qword ptr [rbx+18h], 0
0x1400b3634  jz      loc_1400B346A
0x1400b363a  cmp     dword ptr [rsi], 20h ; ' '
0x1400b363d  jb      loc_1400B346A
0x1400b3643  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x1400b3647  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400b364e  nop     dword ptr [rax+rax+00h]
0x1400b3653  lea     eax, [rdi+1]
0x1400b3656  mov     [rsp+120h+var_C0], 1
0x1400b365b  mov     [rsp+120h+HintIndex], eax
0x1400b365f  jmp     loc_1400B37D0
0x1400b3664  test    r14b, r14b
0x1400b3667  jnz     loc_1400B39C8
0x1400b366d  mov     eax, [r13+0CCh]
0x1400b3674  mov     [rsp+120h+HintIndex], eax
0x1400b3678  jmp     loc_1400B338E
0x1400b367d  xor     eax, eax
0x1400b367f  mov     qword ptr [rbp+37h+var_48], 0
0x1400b3687  mov     [rsp+120h+var_BC], ax
0x1400b368c  lea     r8, [rsp+120h+var_BC]
0x1400b3691  mov     eax, 80008001h
0x1400b3696  mov     ecx, 20h ; ' '
0x1400b369b  mul     edi
0x1400b369d  mov     eax, [r13+68h]
0x1400b36a1  shr     edx, 0Fh
0x1400b36a4  add     dx, di
0x1400b36a7  mov     [rbp+37h+var_54], eax
0x1400b36aa  mov     eax, 10h
0x1400b36af  mov     [rbp+37h+var_58], dx
0x1400b36b3  mov     [rbp+37h+var_56], dx
0x1400b36b7  test    r12b, 10h
0x1400b36bb  lea     rdx, [rbp+37h+var_48]
0x1400b36bf  cmovnz  eax, ecx
0x1400b36c2  lea     rcx, [rbp+37h+var_58]
0x1400b36c6  mov     [rbp+37h+var_50], eax
0x1400b36c9  call    PtClientReservePortRange
0x1400b36ce  mov     [rbp+37h+var_B0], eax
0x1400b36d1  mov     r12d, eax
0x1400b36d4  test    eax, eax
0x1400b36d6  jnz     loc_1400B38F7
0x1400b36dc  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x1400b36e0  mov     rcx, rbx; SpinLock
0x1400b36e3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400b36ea  nop     dword ptr [rax+rax+00h]
0x1400b36ef  nop
0x1400b36f0  mov     eax, [rbx+8]
0x1400b36f3  test    eax, eax
0x1400b36f5  jnz     short loc_1400B36F0
0x1400b36f7  mov     rcx, [rbp+37h+var_A0]
0x1400b36fb  mov     rax, qword ptr [rbp+37h+var_48]
0x1400b36ff  mov     [rcx+8], rax
0x1400b3703  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x1400b3707  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400b370e  nop     dword ptr [rax+rax+00h]
0x1400b3713  jmp     loc_1400B35E1
0x1400b3718  mov     edx, [r13+68h]
0x1400b371c  lea     rcx, [rsp+120h+var_B8]
0x1400b3721  call    cs:__imp_NetioNcmQueryRtcPortRange
0x1400b3728  nop     dword ptr [rax+rax+00h]
0x1400b372d  mov     rcx, [rbp+37h+Process]
0x1400b3731  call    cs:__imp_NetioNcmIsOwningProcessRtcApp
0x1400b3738  nop     dword ptr [rax+rax+00h]
0x1400b373d  test    al, al
0x1400b373f  jnz     loc_1400B3A19
0x1400b3745  test    r12b, 40h
0x1400b3749  jnz     loc_1400B3A19
0x1400b374f  mov     bl, 1
0x1400b3751  mov     [rsp+120h+var_CF], bl
0x1400b3755  jmp     loc_1400B3327
0x1400b375a  mov     rax, [rbp+37h+var_80]
0x1400b375e  mov     rdx, rsi
0x1400b3761  mov     r12d, [rbp+37h+var_AC]
0x1400b3765  mov     rcx, r13
  ... truncated ...
```
