# InetAcquireWildcardPortUnderLock

- ea: `0x14005d380`
- end: `0x14005dd73`
- name: `InetAcquireWildcardPortUnderLock`
- size: `2547`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005c4b8`

## callees

- `0x14005d380`
- `0x14005de84`
- `0x14005def0`
- `0x14005e060`
- `0x14005e0c0`
- `0x14005e300`
- `0x14005e7c0`
- `0x140060360`
- `0x140060404`
- `0x140094c40`
- `0x14014f4c0`
- `0x140152674`
- `0x1401527bc`
- `0x140152b88`
- `0x14015a618`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!RtlClearBit` at `0x1401c512b`
- `ntoskrnl!RtlClearBit` at `0x1401c512b`
- `ntoskrnl!RtlTestBit` at `0x14005dba9`
- `ntoskrnl!RtlTestBit` at `0x14005dba9`
- `ntoskrnl!RtlFindClearBits` at `0x14005d4bd`
- `ntoskrnl!RtlFindClearBits` at `0x14005db59`
- `ntoskrnl!RtlFindClearBits` at `0x14005d4bd`
- `ntoskrnl!RtlFindClearBits` at `0x14005db59`
- `ntoskrnl!RtlSetBit` at `0x14005d69a`
- `ntoskrnl!RtlSetBit` at `0x14005d69a`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005dc50`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005dc50`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d53b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d7f3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005da1b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d53b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005d7f3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005da1b`
- `ntoskrnl!PsGetProcessId` at `0x14005dc63`
- `ntoskrnl!PsGetProcessId` at `0x14005dc63`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d6aa`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d757`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d817`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d8d4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d8ef`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d9b1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005da4e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005dd61`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d6aa`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d757`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d817`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d8d4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d8ef`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005d9b1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005da4e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005dd61`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14005d423`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14005d423`
- `NETIO!NetioNcmQueryRtcPortRange` at `0x14005d831`
- `NETIO!NetioNcmQueryRtcPortRange` at `0x14005d831`
- `NETIO!NetioNcmIsOwningProcessRtcApp` at `0x14005d841`
- `NETIO!NetioNcmIsOwningProcessRtcApp` at `0x14005d841`
- `NETIO!NetioNcmQueryRtcPortHint` at `0x14005da75`
- `NETIO!NetioNcmQueryRtcPortHint` at `0x14005dae1`
- `NETIO!NetioNcmQueryRtcPortHint` at `0x14005da75`
- `NETIO!NetioNcmQueryRtcPortHint` at `0x14005dae1`
- `NETIO!NetioNcmStoreRtcPortHint` at `0x14005dc2f`
- `NETIO!NetioNcmStoreRtcPortHint` at `0x14005dc2f`
- `cng!SystemPrng` at `0x14005d469`
- `cng!SystemPrng` at `0x14005d469`

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
  if ( (BYTE6(WPP_MAIN_CB.Reserved) & 2) != 0 && v50 == 1 && v22 && *v22 >= 0x20 )
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
    if ( (BYTE3(WPP_MAIN_CB.Reserved) & 0x10) != 0 )
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
0x14005d380  mov     [rsp-8+arg_8], rbx
0x14005d385  push    rbp
0x14005d386  push    rsi
0x14005d387  push    rdi
0x14005d388  push    r12
0x14005d38a  push    r13
0x14005d38c  push    r14
0x14005d38e  push    r15
0x14005d390  lea     rbp, [rsp-7]
0x14005d395  sub     rsp, 0F0h
0x14005d39c  mov     rax, cs:__security_cookie
0x14005d3a3  xor     rax, rsp
0x14005d3a6  mov     [rbp+37h+var_38], rax
0x14005d3aa  mov     rax, [rbp+37h+arg_20]
0x14005d3ae  mov     r13, rcx
0x14005d3b1  mov     rcx, [rbp+37h+arg_38]
0x14005d3b5  xor     sil, sil
0x14005d3b8  mov     [rbp+37h+var_A0], rcx
0x14005d3bc  xor     r14b, r14b
0x14005d3bf  xor     ecx, ecx
0x14005d3c1  mov     [rbp+37h+var_AC], edx
0x14005d3c4  xor     bl, bl
0x14005d3c6  mov     [rbp+37h+var_60], rax
0x14005d3ca  mov     rax, [rbp+37h+arg_30]
0x14005d3ce  mov     r12d, edx
0x14005d3d1  xor     edx, edx
0x14005d3d3  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rcx
0x14005d3d7  mov     [rbp+37h+Process], r9
0x14005d3db  lea     rcx, [r13+0D0h]
0x14005d3e2  mov     [rbp+37h+BitMapHeader], rcx
0x14005d3e6  xorps   xmm0, xmm0
0x14005d3e9  mov     [rbp+37h+var_68], r8
0x14005d3ed  mov     r15d, edx
0x14005d3f0  mov     [rbp+37h+var_80], rax
0x14005d3f4  mov     [rsp+120h+HintIndex], edx
0x14005d3f8  mov     [rsp+120h+var_CC], dx
0x14005d3fd  mov     [rsp+120h+var_D0], sil
0x14005d402  mov     [rsp+120h+var_B8], edx
0x14005d406  mov     [rsp+120h+var_CE], r14b
0x14005d40b  mov     [rsp+120h+var_CF], bl
0x14005d40f  mov     [rbp+37h+var_B0], 0C0000209h
0x14005d416  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x14005d41a  test    rax, rax
0x14005d41d  jnz     loc_14005DA96
0x14005d423  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x14005d42a  nop     dword ptr [rax+rax+00h]
0x14005d42f  test    al, al
0x14005d431  jnz     loc_14005D828
0x14005d437  mov     [rsp+120h+var_CD], sil
0x14005d43c  mov     [rsp+120h+var_C0], sil
0x14005d441  mov     esi, r12d
0x14005d444  and     esi, 4
0x14005d447  mov     r12d, 1
0x14005d44d  mov     [rbp+37h+var_B4], esi
0x14005d450  test    esi, esi
0x14005d452  jz      loc_14005D774
0x14005d458  xor     eax, eax
0x14005d45a  lea     rcx, [rsp+120h+var_C8]
0x14005d45f  mov     edx, 2
0x14005d464  mov     [rsp+120h+var_C8], ax
0x14005d469  call    cs:__imp_SystemPrng
0x14005d470  nop     dword ptr [rax+rax+00h]
0x14005d475  movzx   eax, word ptr [r13+90h]
0x14005d47d  xor     edx, edx
0x14005d47f  movzx   ecx, word ptr [r13+92h]
0x14005d487  ror     ax, 8
0x14005d48b  movzx   r8d, ax
0x14005d48f  movzx   eax, [rsp+120h+var_C8]
0x14005d494  div     ecx
0x14005d496  add     r8d, edx
0x14005d499  mov     [rsp+120h+HintIndex], r8d
0x14005d49e  movzx   esi, [rsp+120h+var_D0]
0x14005d4a3  cmp     r15w, 3
0x14005d4a8  jnb     loc_14005DB13
0x14005d4ae  mov     r8d, [rsp+120h+HintIndex]; HintIndex
0x14005d4b3  lea     rcx, [r13+0D0h]; BitMapHeader
0x14005d4ba  mov     edx, r12d; NumberToFind
0x14005d4bd  call    cs:__imp_RtlFindClearBits
0x14005d4c4  nop     dword ptr [rax+rax+00h]
0x14005d4c9  mov     edi, eax
0x14005d4cb  cmp     eax, 0FFFFFFFFh
0x14005d4ce  jz      loc_14005DB13
0x14005d4d4  cmp     edi, [rsp+120h+HintIndex]
0x14005d4d8  jb      loc_14005DB40
0x14005d4de  test    bl, bl
0x14005d4e0  jnz     loc_14005D921
0x14005d4e6  test    sil, sil
0x14005d4e9  jnz     loc_14005DB4F
0x14005d4ef  lea     r12, [r13+90h]
0x14005d4f6  movzx   eax, word ptr [r12]
0x14005d4fb  ror     ax, 8
0x14005d4ff  movzx   ecx, ax
0x14005d502  cmp     edi, ecx
0x14005d504  jb      loc_14005DB87
0x14005d50a  movzx   eax, word ptr [r13+92h]
0x14005d512  add     eax, ecx
0x14005d514  cmp     edi, eax
0x14005d516  jnb     loc_14005DB90
0x14005d51c  mov     rbx, rdi
0x14005d51f  mov     byte ptr [rsp+120h+var_C8], 0
0x14005d524  shr     rbx, 8
0x14005d528  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x14005d52c  movzx   esi, dil
0x14005d530  mov     rbx, [r13+rbx*8+0E0h]
0x14005d538  mov     rcx, rbx; SpinLock
0x14005d53b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005d542  nop     dword ptr [rax+rax+00h]
0x14005d547  mov     eax, [rbx+8]
0x14005d54a  test    eax, eax
0x14005d54c  jnz     short loc_14005D547
0x14005d54e  mov     r14, rsi
0x14005d551  mov     rsi, [rbx+18h]
0x14005d555  shl     r14, 5
0x14005d559  add     rsi, r14
0x14005d55c  mov     [rbp+37h+var_70], rsi
0x14005d560  cmp     [rbx+10h], ax
0x14005d564  jnz     loc_14005D8A1
0x14005d56a  movzx   eax, byte ptr [rsp+120h+var_C8]
0x14005d56f  cmp     [rsp+120h+var_CD], 0
0x14005d574  jz      loc_14005D73F
0x14005d57a  mov     rcx, [rbp+37h+var_68]
0x14005d57e  test    rcx, rcx
0x14005d581  jz      loc_14005D61F
0x14005d587  mov     r9, [rbp+37h+var_80]
0x14005d58b  lea     rdx, [rsp+120h+var_BC]
0x14005d590  movzx   r8d, [rbp+37h+arg_28]
0x14005d595  lea     r15, [rsp+120h+var_B8]
0x14005d59a  xor     eax, eax
0x14005d59c  mov     [rsp+120h+var_F0], rdx
0x14005d5a1  cmp     [rsp+120h+var_CE], al
0x14005d5a5  lea     rdx, [rsp+120h+var_CC]
0x14005d5aa  mov     [rsp+120h+var_BC], ax
0x14005d5af  movzx   eax, di
0x14005d5b2  cmovz   r15, r12
0x14005d5b6  mov     [rsp+120h+var_F8], rdx
0x14005d5bb  ror     ax, 8
0x14005d5bf  mov     rdx, rcx
0x14005d5c2  mov     rcx, r15
0x14005d5c5  mov     word ptr [rsp+120h+var_100], ax
0x14005d5ca  call    WfpAleValidateWildcardPort
0x14005d5cf  mov     ecx, eax
0x14005d5d1  mov     r12d, 1
0x14005d5d7  test    eax, eax
0x14005d5d9  jnz     loc_14005DBDE
0x14005d5df  xor     esi, esi
0x14005d5e1  cmp     cs:dword_1402201D4, 0
0x14005d5e8  jz      short loc_14005D5FE
0x14005d5ea  test    byte ptr cs:WPP_MAIN_CB+14Ch, 8
0x14005d5f1  xorps   xmm0, xmm0
0x14005d5f4  movups  [rbp+37h+var_48], xmm0
0x14005d5f8  jnz     loc_14005D9C7
0x14005d5fe  cmp     esi, 1
0x14005d601  jz      loc_14005D9AD
0x14005d607  cmp     esi, 3
0x14005d60a  jz      loc_14005D8EB
0x14005d610  movzx   r15d, [rsp+120h+var_CC]
0x14005d616  mov     rsi, [rbp+37h+var_70]
0x14005d61a  movzx   eax, byte ptr [rsp+120h+var_C8]
0x14005d61f  test    al, al
0x14005d621  jnz     loc_14005D86A
0x14005d627  mov     rcx, rbx
0x14005d62a  call    InitializeAssignmentArray
0x14005d62f  test    al, al
0x14005d631  jz      loc_14005DD5D
0x14005d637  mov     rsi, [rbx+18h]
0x14005d63b  mov     r12d, [rbp+37h+var_AC]
0x14005d63f  add     rsi, r14
0x14005d642  cmp     [rsp+120h+var_D0], 0
0x14005d647  mov     [rbp+37h+var_70], rsi
0x14005d64b  mov     eax, [rsi]
0x14005d64d  jnz     loc_14005D94D
0x14005d653  test    r12b, 8
0x14005d657  jnz     loc_14005DC03
0x14005d65d  and     eax, 0FFFFFFE0h
0x14005d660  mov     [rsi], eax
0x14005d662  mov     rax, [rbp+37h+var_80]
0x14005d666  mov     rdx, rsi
0x14005d669  movzx   r9d, [rbp+37h+arg_40]
0x14005d671  mov     rcx, r13
0x14005d674  mov     r8, [rbp+37h+var_A0]
0x14005d678  mov     dword ptr [rsp+120h+var_F0], r12d
0x14005d67d  mov     [rsp+120h+var_F8], rax
0x14005d682  movzx   eax, [rbp+37h+arg_28]
0x14005d686  mov     word ptr [rsp+120h+var_100], ax
0x14005d68b  call    InsertEndpointInAssignment
0x14005d690  inc     word ptr [rbx+10h]
0x14005d694  mov     rcx, [rbp+37h+BitMapHeader]; BitMapHeader
0x14005d698  mov     edx, edi; BitNumber
0x14005d69a  call    cs:__imp_RtlSetBit
0x14005d6a1  nop     dword ptr [rax+rax+00h]
0x14005d6a6  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14005d6aa  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005d6b1  nop     dword ptr [rax+rax+00h]
0x14005d6b6  movzx   r14d, [rsp+120h+var_CE]
0x14005d6bc  lea     r8d, [rdi+1]
0x14005d6c0  mov     eax, 80008001h
0x14005d6c5  mul     r8d
0x14005d6c8  shr     edx, 0Fh
0x14005d6cb  imul    eax, edx, 0FFFFh
0x14005d6d1  sub     r8d, eax
0x14005d6d4  test    r14b, r14b
0x14005d6d7  jnz     loc_14005DC18
0x14005d6dd  xchg    r8d, [r13+0CCh]
0x14005d6e4  cmp     cs:PortTrackerEnabled, 0
0x14005d6eb  jnz     loc_14005D78D
0x14005d6f1  mov     rcx, [rbp+37h+var_60]
0x14005d6f5  movzx   eax, di
0x14005d6f8  ror     ax, 8
0x14005d6fc  mov     [rcx], ax
0x14005d6ff  test    byte ptr cs:WPP_MAIN_CB.Reserved+6, 2
0x14005d706  jnz     loc_14005D958
0x14005d70c  test    r14b, r14b
0x14005d70f  jnz     loc_14005DD29
0x14005d715  xor     eax, eax
0x14005d717  mov     rcx, [rbp+37h+var_38]
0x14005d71b  xor     rcx, rsp; StackCookie
0x14005d71e  call    __security_check_cookie
0x14005d723  mov     rbx, [rsp+120h+arg_8]
0x14005d72b  add     rsp, 0F0h
0x14005d732  pop     r15
0x14005d734  pop     r14
0x14005d736  pop     r13
0x14005d738  pop     r12
0x14005d73a  pop     rdi
0x14005d73b  pop     rsi
0x14005d73c  pop     rbp
0x14005d73d  retn
0x14005d73f  cmp     qword ptr [rbx+18h], 0
0x14005d744  jz      loc_14005D57A
0x14005d74a  cmp     dword ptr [rsi], 20h ; ' '
0x14005d74d  jb      loc_14005D57A
0x14005d753  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14005d757  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005d75e  nop     dword ptr [rax+rax+00h]
0x14005d763  lea     eax, [rdi+1]
0x14005d766  mov     [rsp+120h+var_C0], 1
0x14005d76b  mov     [rsp+120h+HintIndex], eax
0x14005d76f  jmp     loc_14005D8E0
0x14005d774  test    r14b, r14b
0x14005d777  jnz     loc_14005DAD8
0x14005d77d  mov     eax, [r13+0CCh]
0x14005d784  mov     [rsp+120h+HintIndex], eax
0x14005d788  jmp     loc_14005D49E
0x14005d78d  xor     eax, eax
0x14005d78f  mov     qword ptr [rbp+37h+var_48], 0
0x14005d797  mov     [rsp+120h+var_BC], ax
0x14005d79c  lea     r8, [rsp+120h+var_BC]
0x14005d7a1  mov     eax, 80008001h
0x14005d7a6  mov     ecx, 20h ; ' '
0x14005d7ab  mul     edi
0x14005d7ad  mov     eax, [r13+68h]
0x14005d7b1  shr     edx, 0Fh
0x14005d7b4  add     dx, di
0x14005d7b7  mov     [rbp+37h+var_54], eax
0x14005d7ba  mov     eax, 10h
0x14005d7bf  mov     [rbp+37h+var_58], dx
0x14005d7c3  mov     [rbp+37h+var_56], dx
0x14005d7c7  test    r12b, 10h
0x14005d7cb  lea     rdx, [rbp+37h+var_48]
0x14005d7cf  cmovnz  eax, ecx
0x14005d7d2  lea     rcx, [rbp+37h+var_58]
0x14005d7d6  mov     [rbp+37h+var_50], eax
0x14005d7d9  call    PtClientReservePortRange
0x14005d7de  mov     [rbp+37h+var_B0], eax
0x14005d7e1  mov     r12d, eax
0x14005d7e4  test    eax, eax
0x14005d7e6  jnz     loc_14005DA07
0x14005d7ec  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x14005d7f0  mov     rcx, rbx; SpinLock
0x14005d7f3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005d7fa  nop     dword ptr [rax+rax+00h]
0x14005d7ff  nop
0x14005d800  mov     eax, [rbx+8]
0x14005d803  test    eax, eax
0x14005d805  jnz     short loc_14005D800
0x14005d807  mov     rcx, [rbp+37h+var_A0]
0x14005d80b  mov     rax, qword ptr [rbp+37h+var_48]
0x14005d80f  mov     [rcx+8], rax
0x14005d813  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14005d817  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005d81e  nop     dword ptr [rax+rax+00h]
0x14005d823  jmp     loc_14005D6F1
0x14005d828  mov     edx, [r13+68h]
0x14005d82c  lea     rcx, [rsp+120h+var_B8]
0x14005d831  call    cs:__imp_NetioNcmQueryRtcPortRange
0x14005d838  nop     dword ptr [rax+rax+00h]
0x14005d83d  mov     rcx, [rbp+37h+Process]
0x14005d841  call    cs:__imp_NetioNcmIsOwningProcessRtcApp
0x14005d848  nop     dword ptr [rax+rax+00h]
0x14005d84d  test    al, al
0x14005d84f  jnz     loc_14005DB29
0x14005d855  test    r12b, 40h
0x14005d859  jnz     loc_14005DB29
0x14005d85f  mov     bl, 1
0x14005d861  mov     [rsp+120h+var_CF], bl
0x14005d865  jmp     loc_14005D437
0x14005d86a  mov     rax, [rbp+37h+var_80]
0x14005d86e  mov     rdx, rsi
0x14005d871  mov     r12d, [rbp+37h+var_AC]
0x14005d875  mov     rcx, r13
  ... truncated ...
```
