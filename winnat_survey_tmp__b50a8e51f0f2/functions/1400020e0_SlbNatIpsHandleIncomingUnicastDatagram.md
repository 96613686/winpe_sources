# SlbNatIpsHandleIncomingUnicastDatagram

- ea: `0x1400020e0`
- end: `0x14000381c`
- name: `SlbNatIpsHandleIncomingUnicastDatagram`
- size: `5948`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `32`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140001c30`
- `0x1400020e0`

## callees

- `0x140001120`
- `0x1400011e0`
- `0x1400020e0`
- `0x140003830`
- `0x140004094`
- `0x1400042a0`
- `0x140004e60`
- `0x140006030`
- `0x140006340`
- `0x140006558`
- `0x140006764`
- `0x140006b40`
- `0x140006b74`
- `0x140006c80`
- `0x140006f04`
- `0x1400077fc`
- `0x14000c328`
- `0x14000caa0`
- `0x140011bf8`
- `0x140014e38`
- `0x14001515c`
- `0x140015400`
- `0x140015550`
- `0x1400199fc`
- `0x14001d450`
- `0x14001ede0`
- `0x14001ef70`
- `0x14001f020`
- `0x14002d008`
- `0x14002d040`
- `0x14002d304`
- `0x14002d36c`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140002f3f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140002f3f`
- `ntoskrnl!KeTestSpinLock` at `0x1400028b6`
- `ntoskrnl!KeTestSpinLock` at `0x1400028b6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400028da`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400028da`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400028ef`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400028ef`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140002125`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000219b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400030b0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140002125`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000219b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400030b0`
- `ntoskrnl!KeLowerIrql` at `0x140002aa0`
- `ntoskrnl!KeLowerIrql` at `0x140002aa0`
- `ntoskrnl!KfRaiseIrql` at `0x14000286b`
- `ntoskrnl!KfRaiseIrql` at `0x14000286b`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400029fb`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400029fb`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140002a42`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140002a42`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000265f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400026d9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002810`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002dab`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002e27`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000265f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400026d9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002810`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002dab`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002e27`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400026b3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002734`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400027c4`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002df8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002e6d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002e82`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400026b3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002734`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400027c4`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002df8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002e6d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002e82`
- `NETIO!RtlComputeToeplitzHash` at `0x140002936`
- `NETIO!RtlComputeToeplitzHash` at `0x140002960`
- `NETIO!RtlComputeToeplitzHash` at `0x1400029a0`
- `NETIO!RtlComputeToeplitzHash` at `0x1400029c9`
- `NETIO!RtlComputeToeplitzHash` at `0x140002936`
- `NETIO!RtlComputeToeplitzHash` at `0x140002960`
- `NETIO!RtlComputeToeplitzHash` at `0x1400029a0`
- `NETIO!RtlComputeToeplitzHash` at `0x1400029c9`

## pseudocode

```c
void __fastcall SlbNatIpsHandleIncomingUnicastDatagram(__int64 a1)
{
  ULONG CurrentProcessorNumber; // eax
  __int64 v3; // rdx
  __int64 v4; // rsi
  int v5; // r15d
  __int64 v6; // rdi
  _QWORD *v7; // rcx
  char v8; // al
  __int64 v9; // rdx
  __int64 v10; // rcx
  _QWORD *v11; // rsi
  _QWORD *v12; // rdi
  __int64 v13; // r15
  unsigned int v14; // r14d
  _QWORD *v15; // rax
  __int64 v16; // rdx
  unsigned __int64 v17; // r14
  int v18; // eax
  _QWORD *v19; // rax
  __int64 v20; // r13
  __int64 v21; // rax
  __int64 v22; // rsi
  _WORD *v23; // r15
  _WORD *v24; // rdi
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 p_Blink; // rdi
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 SessionEntry; // rax
  unsigned __int8 v36; // r15
  __int64 v37; // rax
  unsigned __int8 v38; // cl
  __int64 v39; // r8
  __int64 v40; // rdx
  int v41; // ecx
  __int64 v42; // rcx
  __int64 v43; // r14
  unsigned __int8 v44; // r15
  char *v45; // r13
  KIRQL v46; // al
  unsigned int LockArray_high; // ecx
  __int64 v48; // rax
  __int64 v49; // rcx
  volatile signed __int32 *v50; // r13
  _WORD *v51; // rdx
  bool v52; // zf
  volatile signed __int64 *v53; // r13
  __int64 v54; // r8
  int v55; // edi
  int v56; // eax
  _WORD *v57; // rdx
  bool v58; // zf
  unsigned int v59; // eax
  int v60; // edi
  int v61; // eax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY NextEntryHashTable; // rdi
  _QWORD *v63; // rax
  _QWORD *v64; // rax
  _DWORD *v65; // r13
  __int16 v66; // ax
  bool v67; // di
  _BYTE *v68; // r13
  PRTL_DYNAMIC_HASH_TABLE_ENTRY SessionForExternalPacket; // rax
  __int64 v70; // rdx
  __int64 v71; // rcx
  bool v72; // r13
  __int64 v73; // rcx
  unsigned __int8 v74; // al
  int v75; // eax
  __int128 v76; // xmm0
  _QWORD *v77; // rax
  __int64 v78; // rax
  int v79; // eax
  __int64 v80; // rdx
  __int64 v81; // rcx
  __int64 v82; // rbx
  signed __int64 v83; // rax
  signed __int64 v84; // rax
  __int64 v85; // rcx
  void (__fastcall *v86)(__int64); // rax
  int v87; // eax
  __int64 *v88; // rcx
  __int64 v89; // rcx
  __int64 v90; // rdi
  __int64 v91; // rax
  int v92; // r9d
  _QWORD *v93; // rcx
  _QWORD *v94; // rax
  char v95; // al
  __int64 v96; // r14
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // rax
  unsigned __int8 v100; // r15
  __int64 v101; // rdx
  __int64 v102; // rcx
  unsigned int v103; // eax
  _QWORD *v104; // rdx
  __int64 v105; // r8
  __int64 v106; // r9
  __int64 v107; // rcx
  char v108; // al
  __int64 v109; // rcx
  signed __int64 v110; // rax
  signed __int64 v111; // rax
  __int64 v112; // rdx
  __int64 v113; // r13
  __int64 v114; // r8
  bool v115; // cc
  __int64 v116; // r14
  bool v117; // cl
  __int64 v118; // r15
  _QWORD *v119; // rax
  __int64 v120; // r14
  int v121; // edx
  _DWORD *v122; // rcx
  _DWORD *v123; // rcx
  int v124; // eax
  unsigned __int8 v125; // r8
  int v126; // r8d
  __int64 v127; // rdx
  __int64 v128; // rax
  __int64 v129; // rcx
  char v130; // al
  unsigned __int8 v131; // r15
  __int64 v132; // rax
  __int64 v133; // rdx
  unsigned int v134; // eax
  __int64 v135; // r9
  __int64 v136; // rcx
  BOOL v137; // edx
  int v138; // eax
  _QWORD *v139; // rax
  _DWORD *v140; // [rsp+30h] [rbp-89h]
  unsigned __int8 v141; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int8 v142; // [rsp+51h] [rbp-68h]
  unsigned __int8 v143; // [rsp+52h] [rbp-67h]
  _DWORD *v144; // [rsp+58h] [rbp-61h] BYREF
  ULONG v145; // [rsp+60h] [rbp-59h]
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+68h] [rbp-51h]
  __int64 v147; // [rsp+70h] [rbp-49h]
  __int128 v148; // [rsp+78h] [rbp-41h] BYREF
  _QWORD *v149; // [rsp+88h] [rbp-31h]
  __int64 v150; // [rsp+90h] [rbp-29h]
  __int128 v151; // [rsp+98h] [rbp-21h] BYREF
  __int128 v152; // [rsp+A8h] [rbp-11h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B8h] [rbp-1h] BYREF
  __int128 v154; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v155; // [rsp+E0h] [rbp+27h]

  LOBYTE(v149) = 0;
  v150 = *(_QWORD *)(a1 + 40);
  v148 = 0;
  v151 = 0;
  v152 = 0;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v4 = *(_QWORD *)(a1 + 56);
  v5 = CurrentProcessorNumber;
  v145 = CurrentProcessorNumber;
  v6 = *((_QWORD *)qword_1400263D8 + 169) + 232LL * CurrentProcessorNumber;
  v7 = *(_QWORD **)(v4 + 8);
  if ( *v7 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v7, v3);
  v8 = WinNatParseNb(*(PNET_BUFFER *)(v4 + 8), (__int64 *)v6, 1, 5u);
  v11 = *(_QWORD **)(a1 + 56);
  if ( !v8 || !v6 )
  {
    v12 = *(_QWORD **)(a1 + 56);
    v13 = KeGetCurrentProcessorNumberEx(0);
    v14 = 1;
    v154 = 0;
    LOBYTE(v155) = 0;
    if ( Microsoft_Windows_WinNatEnableBits < 0 && *(_WORD *)a1 == 2 )
      SlbNatIpsLogIPv4Datagram(
        *(_DWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32),
        *(_QWORD *)(a1 + 40),
        0,
        0,
        (__int64)v11,
        1,
        1);
    v15 = (_QWORD *)*v11;
    if ( *v11 )
    {
      do
      {
        v15 = (_QWORD *)*v15;
        ++v14;
      }
      while ( v15 );
    }
    LOBYTE(v154) = 0;
    *((_QWORD *)&v154 + 1) = v11;
    v155 = 0;
    if ( gAccount && v11 )
    {
      do
      {
        _InterlockedIncrement64(&gNBLDrop);
        v12 = (_QWORD *)*v12;
      }
      while ( v12 );
    }
    (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 32LL))(
      *(_QWORD *)(a1 + 8),
      *(_QWORD *)(a1 + 48),
      &v154);
    v16 = 136 * v13;
    *(_QWORD *)((char *)qword_140026B68 + v16 + 104) += v14;
    *(_DWORD *)((char *)qword_140026B68 + v16 + 64) += v14;
    return;
  }
  LOBYTE(v148) = 0;
  *((_QWORD *)&v148 + 1) = v11;
  v149 = v11;
  v52 = (*(_BYTE *)(v6 + 212) & 1) == 0;
  v17 = *(unsigned __int8 *)(v6 + 16);
  v141 = 0;
  if ( !v52 )
  {
    v18 = *(_DWORD *)(v6 + 220);
    LOBYTE(v10) = *(_DWORD *)(a1 + 160) == v18;
    v52 = *(_WORD *)(v6 + 224) == 0;
    v141 = v10;
    if ( v52 )
      *(_DWORD *)(a1 + 160) = v18;
    else
      v141 = v10;
  }
  if ( (*(_BYTE *)(v6 + 212) & 1) != 0 )
  {
    if ( *(_DWORD *)(a1 + 160) != *(_DWORD *)(v6 + 220) )
    {
      *(_DWORD *)(a1 + 160) = 0;
      if ( (xmmword_1400262E0 & 4) != 0 )
        WPP_SF_d(1026, 31, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, *(unsigned int *)(v6 + 220));
      if ( gAccount )
      {
        v19 = (_QWORD *)*((_QWORD *)&v148 + 1);
        if ( *((_QWORD *)&v148 + 1) )
        {
          do
          {
            _InterlockedIncrement64(&gNBLReturn);
            v19 = (_QWORD *)*v19;
          }
          while ( v19 );
        }
      }
      (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 40LL))(
        *(_QWORD *)(a1 + 8),
        *(_QWORD *)(a1 + 48),
        &v148);
      return;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 160) = 0;
  }
  if ( (*(_BYTE *)(v6 + 212) & 3) == 1 )
    *(_DWORD *)(a1 + 160) = 0;
  v20 = 0x400000000020042LL;
  if ( (unsigned __int8)v17 > 0x3Au
    || !_bittest64(&v20, v17)
    || (*(_BYTE *)(v6 + 212) & 1) != 0 && !BYTE2(dword_140026B78) )
  {
    if ( *(_QWORD *)(a1 + 64) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v10, v9);
    if ( (byte_140026BED & 4) != 0 && *(_WORD *)a1 == 2 )
    {
      v137 = (unsigned __int8)v17 > 0x3Au || !_bittest64(&v20, v17);
      v138 = 19;
      if ( !v137 )
        v138 = 2;
      SlbNatIpsLogIPv4Datagram(
        *(_DWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32),
        *(_QWORD *)(a1 + 40),
        0,
        0,
        *(_QWORD *)(a1 + 56),
        2,
        v138);
    }
    if ( gAccount )
    {
      v139 = (_QWORD *)*((_QWORD *)&v148 + 1);
      if ( *((_QWORD *)&v148 + 1) )
      {
        do
        {
          _InterlockedIncrement64(&gNBLReturn);
          v139 = (_QWORD *)*v139;
        }
        while ( v139 );
      }
    }
    goto LABEL_368;
  }
  v142 = v17;
  if ( *(_BYTE *)(v6 + 213) )
  {
    v21 = SlbNatLibParseICMPInnerPacket((__int64)qword_1400263D8, v6, (__int64)v11, v5);
    v22 = v21;
    if ( !v21 )
    {
      if ( (xmmword_1400262E0 & 4) != 0 )
        WPP_SF_(1026, 32, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids);
      goto LABEL_37;
    }
    LOBYTE(v17) = *(_BYTE *)(v21 + 16);
    v23 = (_WORD *)(v21 + 152);
    v147 = v6;
    *(_QWORD *)&v154 = v21 + 180;
    v24 = (_WORD *)(v21 + 180);
  }
  else
  {
    v22 = v6;
    v147 = 0;
    v23 = (_WORD *)(v6 + 180);
    v24 = (_WORD *)(v6 + 152);
    *(_QWORD *)&v154 = v24;
  }
  v25 = *(_QWORD *)(a1 + 40);
  v143 = 0;
  if ( v25 )
  {
    if ( dword_1400264E8 <= 0 )
    {
      if ( *(_DWORD *)(v25 + 40) )
        goto LABEL_43;
    }
    else if ( (*(_DWORD *)(v25 + 24) & 4) == 0 )
    {
LABEL_43:
      v26 = *(_QWORD *)(a1 + 80);
      if ( v26 && (unsigned __int8)WinNatIsMatchingSession(1, (_DWORD)v24, (_DWORD)v23, 0, v17, v26 + 184, v141) )
      {
        p_Blink = *(_QWORD *)(a1 + 80);
        if ( (*(_BYTE *)(v22 + 212) & 1) != 0 && (xmmword_1400262E0 & 4) != 0 )
          WPP_SF_dq(v28, 35, v29, *(unsigned int *)(v22 + 220), *(_QWORD *)(a1 + 80));
        if ( !p_Blink )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v28, v27);
LABEL_175:
        v78 = *(_QWORD *)(a1 + 112);
        v38 = 0;
        v141 = 0;
        if ( v78 == *(_QWORD *)(p_Blink + 32) && v78 )
          goto LABEL_226;
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
        v40 = *(_QWORD *)(p_Blink + 32);
        if ( v40 )
        {
          (*(void (__fastcall **)(_QWORD, __int64, __int128 *))(*(_QWORD *)(a1 + 16) + 112LL))(
            *(_QWORD *)(a1 + 8),
            v40,
            &v151);
          *(_DWORD *)(a1 + 120) = DWORD1(v152);
          v79 = v152;
        }
        else
        {
          v79 = 0;
          LODWORD(v152) = 0;
        }
        if ( *(_QWORD *)(p_Blink + 32) && *(_DWORD *)(p_Blink + 16) == v79 )
        {
          v44 = v142;
        }
        else
        {
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
          v44 = v142;
          if ( !(unsigned __int8)SlbNatIpsRefreshInternalNexthop(a1, v142, p_Blink) )
            return;
          KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
        }
        v43 = *(_QWORD *)(p_Blink + 32);
        goto LABEL_186;
      }
      if ( v147 && (*(_BYTE *)(v22 + 212) & 1) == 0 )
      {
        v144 = qword_1400263D8;
        v45 = (char *)qword_1400263D8 + 192;
        v46 = KfRaiseIrql(2u);
        LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
        v141 = v46;
        v48 = LockArray_high;
        v49 = LockArray_high & *((_DWORD *)v45 + 2);
        v150 = v48;
        v50 = (volatile signed __int32 *)&v45[64 * v49 + 64];
        memset(&LockHandle, 0, sizeof(LockHandle));
        _InterlockedIncrement(v50);
        if ( !KeTestSpinLock((PKSPIN_LOCK)v144 + 24) )
        {
          _InterlockedDecrement(v50);
          KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v144 + 24, &LockHandle);
          _InterlockedIncrement(v50);
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        }
        v51 = v24 + 2;
        v52 = *v24 == 2;
        memset(&LockHandle, 0, sizeof(LockHandle));
        v53 = 0;
        if ( !v52 )
          v51 = v24 + 4;
        v54 = 4;
        if ( !v52 )
          v54 = 16;
        v55 = RtlComputeToeplitzHash(v144 + 134, v51, v54, 0);
        v56 = RtlComputeToeplitzHash(v144 + 134, v154 + 2, 2, 0);
        v57 = v23 + 2;
        v58 = *v23 == 2;
        LODWORD(HashTable) = v55 ^ v56;
        if ( !v58 )
          v57 = v23 + 4;
        v59 = 4;
        if ( !v58 )
          v59 = 16;
        v60 = (unsigned int)HashTable ^ RtlComputeToeplitzHash(v144 + 134, v57, v59, 0);
        v61 = RtlComputeToeplitzHash(v144 + 134, v23 + 1, 2, 0);
        HashTable = (PRTL_DYNAMIC_HASH_TABLE)*((_QWORD *)v144 + 65);
        LockHandle.LockQueue = 0;
        NextEntryHashTable = RtlLookupEntryHashTable(
                               HashTable,
                               v60 ^ v61 | 0x80000000,
                               (PRTL_DYNAMIC_HASH_TABLE_CONTEXT)&LockHandle);
        if ( NextEntryHashTable )
        {
          while ( !(unsigned __int8)WinNatIsMatchingSession(
                                      1,
                                      v154,
                                      (_DWORD)v23,
                                      0,
                                      v17,
                                      (__int64)NextEntryHashTable,
                                      0) )
          {
            v53 = 0;
            NextEntryHashTable = RtlGetNextEntryHashTable(HashTable, (PRTL_DYNAMIC_HASH_TABLE_CONTEXT)&LockHandle);
            if ( !NextEntryHashTable )
              goto LABEL_124;
          }
          v53 = (volatile signed __int64 *)&NextEntryHashTable[-8];
          if ( NextEntryHashTable != (PRTL_DYNAMIC_HASH_TABLE_ENTRY)192 && _InterlockedIncrement64(v53) <= 1 )
            __fastfail(0xEu);
        }
LABEL_124:
        _InterlockedDecrement(&v144[16 * ((unsigned int)v150 & v144[50]) + 64]);
        KeLowerIrql(v141);
        if ( !v53 || (p_Blink = (__int64)(v53 + 1), v53 == (volatile signed __int64 *)-8LL) )
        {
          if ( gAccount )
          {
            v63 = (_QWORD *)*((_QWORD *)&v148 + 1);
            if ( *((_QWORD *)&v148 + 1) )
            {
              do
              {
                _InterlockedIncrement64(&gNBLReturn);
                v63 = (_QWORD *)*v63;
              }
              while ( v63 );
            }
          }
          goto LABEL_368;
        }
        goto LABEL_175;
      }
      v141 = 0;
      if ( (*(_BYTE *)(v22 + 212) & 1) != 0 && *(_WORD *)(v22 + 224) )
      {
        if ( (xmmword_1400262E0 & 4) != 0 )
          WPP_SF_d(1026, 36, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, *(unsigned int *)(v22 + 220));
        if ( gAccount )
        {
          v64 = (_QWORD *)*((_QWORD *)&v148 + 1);
          if ( *((_QWORD *)&v148 + 1) )
          {
            do
            {
              _InterlockedIncrement64(&gNBLReturn);
              v64 = (_QWORD *)*v64;
            }
            while ( v64 );
          }
        }
        goto LABEL_368;
      }
      v65 = 0;
      v144 = 0;
      if ( v150 )
      {
        v65 = (_DWORD *)(v150 + 36);
        v144 = (_DWORD *)(v150 + 36);
      }
      if ( (_BYTE)v17 != *(_BYTE *)(a1 + 104) )
        goto LABEL_146;
      v66 = *v23;
      if ( *v23 != *(_WORD *)(a1 + 88) )
        goto LABEL_146;
      if ( v66 == 2 )
      {
        if ( v23[1] != *(_WORD *)(a1 + 90) )
          goto LABEL_146;
        v73 = 0;
        while ( 1 )
        {
          v74 = *((_BYTE *)v23 + v73++ + 4);
          if ( v74 != *((_BYTE *)v23 + v73 + 3) )
            break;
          if ( v73 == 4 )
          {
            v75 = 0;
            goto LABEL_160;
          }
        }
        v75 = v74 < *((_BYTE *)v23 + v73 + 3) ? -1 : 1;
LABEL_160:
        if ( v75 )
          goto LABEL_146;
      }
      else if ( v66 != 23 || v23[1] != *(_WORD *)(a1 + 90) || memcmp(v23 + 4, v23 + 4, 0x10u) )
      {
LABEL_146:
        v67 = dword_1400264E8 > 0;
        v140 = v65;
        v68 = (_BYTE *)v154;
        LODWORD(HashTable) = *(_DWORD *)(a1 + 32);
        v150 = (__int64)qword_1400263D8;
        SessionForExternalPacket = WinNatGetSessionForExternalPacket(
                                     (__int64)qword_1400263D8,
                                     (_BYTE *)v154,
                                     v23,
                                     0,
                                     v17,
                                     &v141,
                                     v140,
                                     (int)HashTable);
        if ( v67 && !SessionForExternalPacket )
        {
          v154 = *(_OWORD *)v23;
          DWORD1(v154) = 0;
          SessionForExternalPacket = WinNatGetSessionForExternalPacket(
                                       v150,
                                       v68,
                                       &v154,
                                       (__int64)v23,
                                       v17,
                                       &v141,
                                       v144,
                                       (int)HashTable);
        }
        p_Blink = (__int64)&SessionForExternalPacket->Linkage.Blink;
        if ( !SessionForExternalPacket )
          p_Blink = 0;
        v72 = p_Blink == 0;
        if ( p_Blink )
        {
          if ( (*(_BYTE *)(p_Blink + 64) & 2) == 0 )
          {
            if ( v147 )
              MicrosoftTelemetryAssertTriggeredNoArgsKM(v71, v70);
            SlbNatIpsCheckHairpinning(p_Blink, 0, a1, v22);
          }
          goto LABEL_175;
        }
        if ( v141 )
        {
          SlbNatIpsDropDatagram(a1, *(_QWORD *)(a1 + 56), v142, 6);
          return;
        }
LABEL_162:
        if ( (byte_140026BED & 4) != 0 && *(_WORD *)a1 == 2 )
          SlbNatIpsLogIPv4Datagram(
            *(_DWORD *)(a1 + 24),
            *(_DWORD *)(a1 + 32),
            *(_QWORD *)(a1 + 40),
            0,
            0,
            *(_QWORD *)(a1 + 56),
            2,
            21);
        if ( v72 )
        {
          v76 = *(_OWORD *)v23;
          *(_BYTE *)(a1 + 104) = v17;
          *(_OWORD *)(a1 + 88) = v76;
        }
        if ( gAccount )
        {
          v77 = (_QWORD *)*((_QWORD *)&v148 + 1);
          if ( *((_QWORD *)&v148 + 1) )
          {
            do
            {
              _InterlockedIncrement64(&gNBLReturn);
              v77 = (_QWORD *)*v77;
            }
            while ( v77 );
          }
        }
        goto LABEL_368;
      }
      v72 = 0;
      goto LABEL_162;
    }
  }
  if ( *(_QWORD *)(a1 + 64) )
    goto LABEL_43;
  v31 = *(_QWORD *)(a1 + 80);
  if ( v31
    && (unsigned __int8)WinNatIsMatchingSession(*(_DWORD *)(a1 + 24), (_DWORD)v24, (_DWORD)v23, 1, v17, v31 + 160, v141) )
  {
    p_Blink = *(_QWORD *)(a1 + 80);
    if ( (*(_BYTE *)(v22 + 212) & 1) != 0 && (xmmword_1400262E0 & 4) != 0 )
      WPP_SF_dq(v33, 33, v34, *(unsigned int *)(v22 + 220), *(_QWORD *)(a1 + 80));
    if ( !p_Blink )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v33, v32);
  }
  else
  {
    if ( (*(_BYTE *)(v22 + 212) & 1) != 0 && *(_WORD *)(v22 + 224) )
    {
      if ( (xmmword_1400262E0 & 4) != 0 )
        WPP_SF_d(1026, 34, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, *(unsigned int *)(v22 + 220));
      goto LABEL_37;
    }
    SessionEntry = WinNatFindSessionEntry(
                     (int)qword_1400263D8 + 128,
                     *(_DWORD *)(a1 + 24),
                     (_DWORD)v24,
                     (_DWORD)v23,
                     v17,
                     1);
    p_Blink = SessionEntry + 8;
    if ( !SessionEntry )
      p_Blink = 0;
    if ( !p_Blink )
    {
      if ( v147 )
      {
LABEL_37:
        SlbNatAccountChain(&v148, 1);
LABEL_368:
        (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 40LL))(
          *(_QWORD *)(a1 + 8),
          *(_QWORD *)(a1 + 48),
          &v148);
        return;
      }
      p_Blink = SlbNatIpsCreateSessionForInternalDatagram(a1, v22, v145);
      if ( !p_Blink )
        return;
    }
  }
  v36 = v142;
  if ( *(_DWORD *)(a1 + 24) != 1
    && *(_DWORD *)(p_Blink + 8) != *(_DWORD *)(a1 + 28)
    && !(unsigned __int8)SlbNatIpsRefreshInternalNoRouteState(a1, v142, p_Blink) )
  {
    return;
  }
  v37 = *(_QWORD *)(a1 + 112);
  v38 = 1;
  v141 = 1;
  if ( v37 == *(_QWORD *)(p_Blink + 24) && v37 )
    goto LABEL_226;
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
  v40 = *(_QWORD *)(p_Blink + 24);
  if ( v40 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, __int128 *))(*(_QWORD *)(a1 + 16) + 112LL))(
      *(_QWORD *)(a1 + 8),
      v40,
      &v151);
    v41 = v152;
    *(_DWORD *)(a1 + 120) = DWORD1(v152);
  }
  else
  {
    v41 = 0;
    LODWORD(v152) = 0;
  }
  if ( *(_DWORD *)(p_Blink + 4) != dword_140026840 || !*(_QWORD *)(p_Blink + 24) || *(_DWORD *)(p_Blink + 12) != v41 )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
    if ( !(unsigned __int8)SlbNatIpsRefreshExternalNexthop(a1, v36, p_Blink) )
      return;
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
  }
  v42 = *(unsigned __int8 *)(p_Blink + 64);
  if ( (v42 & 1) == 0 )
    goto LABEL_102;
  v40 = (unsigned __int8)v42;
  LOBYTE(v40) = (unsigned __int8)v42 >> 4;
  if ( dword_1400264E8 <= 0 || (v42 & 0x30) != 0 )
  {
    LOBYTE(v39) = 0;
    v143 = 0;
  }
  else
  {
    v39 = 1;
    v143 = 1;
  }
  LOBYTE(v42) = (unsigned __int8)v42 >> 5;
  if ( (((unsigned __int8)v40 | (unsigned __int8)v42) & 1) == 0 && !(_BYTE)v39 )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
    if ( (byte_140026BED & 4) != 0 && *(_WORD *)a1 == 2 )
      SlbNatIpsLogIPv4Datagram(
        *(_DWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32),
        *(_QWORD *)(a1 + 40),
        0,
        0,
        *(_QWORD *)(a1 + 56),
        2,
        20);
    SlbNatAccountChain(&v148, 1);
    (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 40LL))(
      *(_QWORD *)(a1 + 8),
      *(_QWORD *)(a1 + 48),
      &v148);
    if ( *(_QWORD *)(a1 + 80) == p_Blink )
      *(_QWORD *)(a1 + 80) = 0;
    WinNatLibDereferenceSession(p_Blink - 8);
    return;
  }
  if ( (v42 & 1) != 0 )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
    if ( !(unsigned __int8)SlbNatIpsUpdateExternalHairpinNexthop(a1, p_Blink) )
    {
      SlbNatIpsDropDatagram(a1, *(_QWORD *)(a1 + 56), v36, 5);
      if ( *(_QWORD *)(a1 + 80) == p_Blink )
        *(_QWORD *)(a1 + 80) = 0;
      WinNatLibDereferenceSession(p_Blink - 8);
      return;
    }
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
  }
  if ( !v143 )
  {
LABEL_102:
    if ( (*(_BYTE *)(p_Blink + 64) & 0x11) == 1 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v42, v40);
  }
  v43 = *(_QWORD *)(p_Blink + 24);
  v44 = v142;
LABEL_186:
  if ( !v43 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v42, v40);
  if ( *(_QWORD *)(a1 + 112) != v43
    && !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)(a1 + 16) + 96LL))(
          *(_QWORD *)(a1 + 8),
          v43,
          v39) )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
    goto LABEL_192;
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
  if ( !v43 )
  {
LABEL_192:
    SlbNatIpsDropDatagram(a1, *(_QWORD *)(a1 + 56), v44, 7);
    if ( *(_QWORD *)(a1 + 80) == p_Blink )
      *(_QWORD *)(a1 + 80) = 0;
    v82 = p_Blink - 8;
    v83 = _InterlockedExchangeAdd64((volatile signed __int64 *)(p_Blink - 8), 0xFFFFFFFFFFFFFFFFuLL);
    v115 = v83 <= 1;
    v84 = v83 - 1;
    if ( !v115 )
      return;
    if ( !v84 )
      goto LABEL_196;
    goto LABEL_264;
  }
  v91 = *(_QWORD *)(a1 + 112);
  if ( v91 != v43 )
  {
    if ( *(_QWORD *)(a1 + 128) )
    {
      if ( !v91 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v81, v80);
      if ( (*(_BYTE *)(a1 + 2) & 2) != 0 )
      {
        SlbNatIpsClientPendPackets(a1, v80);
      }
      else
      {
        if ( (byte_140026BED & 8) != 0 && *(_WORD *)a1 == 2 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 112LL))(
            *(_QWORD *)(a1 + 8),
            *(_QWORD *)(a1 + 112),
            &v151);
          v92 = 1;
          if ( (*(_BYTE *)(a1 + 2) & 1) == 0 )
            v92 = *(_DWORD *)p_Blink;
          SlbNatIpsLogIPv4Datagram(
            *(_DWORD *)(a1 + 24),
            *(_DWORD *)(a1 + 32),
            *(_QWORD *)(a1 + 40),
            v92,
            v151,
            *(_QWORD *)(a1 + 128),
            0,
            0);
        }
        v93 = *(_QWORD **)(a1 + 128);
        v94 = *(_QWORD **)(a1 + 136);
        *((_QWORD *)&v148 + 1) = v93;
        v149 = v94;
        if ( gAccount && v93 )
        {
          do
          {
            _InterlockedIncrement64(&gNBLForward);
            v93 = (_QWORD *)*v93;
          }
          while ( v93 );
        }
        (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *, _QWORD, _QWORD))(*(_QWORD *)(a1 + 16) + 48LL))(
          *(_QWORD *)(a1 + 8),
          *(_QWORD *)(a1 + 48),
          &v148,
          0,
          *(_QWORD *)(a1 + 112));
        *(_QWORD *)(a1 + 128) = 0;
        *(_QWORD *)(a1 + 136) = a1 + 128;
      }
    }
    v80 = *(_QWORD *)(a1 + 112);
    if ( v80 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(a1 + 16) + 104LL))(*(_QWORD *)(a1 + 8));
    v81 = v143;
    v95 = *(_BYTE *)(a1 + 2) & 0xFD;
    LOBYTE(v81) = 2 * v143;
    *(_QWORD *)(a1 + 112) = v43;
    LOBYTE(v81) = v95 | v81;
    *(_BYTE *)(a1 + 2) = v81;
  }
  if ( ((*(_BYTE *)(a1 + 2) & 2) != 0) != v143 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v81, v80);
  v38 = v141;
LABEL_226:
  if ( (*(_BYTE *)(p_Blink + 64) & 0x10) != 0 && v38 )
  {
    v96 = *(_QWORD *)(a1 + 56);
    v145 = KeGetCurrentProcessorNumberEx(0);
    v98 = v22;
    v99 = v147;
    if ( v147 )
      v98 = v147;
    v100 = *(_BYTE *)(v98 + 16);
    if ( (*(_BYTE *)(p_Blink + 64) & 0x10) == 0 )
    {
LABEL_231:
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v98, v97);
      v99 = v147;
      goto LABEL_232;
    }
    while ( 1 )
    {
LABEL_232:
      if ( !(unsigned __int8)SlbNatLibTranslate((__int64)qword_1400263D8, p_Blink, 1u, 0, v22, v99, v96) )
      {
        v103 = 9;
        goto LABEL_245;
      }
      v96 = *(_QWORD *)v96;
      if ( !v96 )
        break;
      if ( v147 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v102, v101);
      v22 = *((_QWORD *)qword_1400263D8 + 169) + 232LL * v145;
      if ( **(_QWORD **)(v96 + 8) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v102, v101);
      if ( !WinNatParseNb(*(PNET_BUFFER *)(v96 + 8), (__int64 *)v22, 1, 5u) || !v22 )
      {
        v103 = 1;
        goto LABEL_245;
      }
      v99 = v147;
      if ( !*(_WORD *)(v22 + 224) )
        goto LABEL_231;
    }
    v103 = 0;
LABEL_245:
    if ( *(_QWORD *)(a1 + 80) == p_Blink )
      *(_QWORD *)(a1 + 80) = 0;
    v104 = *(_QWORD **)(a1 + 56);
    if ( v96 )
    {
      SlbNatIpsDropDatagram(a1, v104, v100, v103);
    }
    else
    {
      if ( v104 )
      {
        v105 = v145;
        v106 = 136LL * v145;
        do
        {
          v104 = (_QWORD *)*v104;
          v107 = 136 * v105;
          ++*(_QWORD *)((char *)qword_140026B68 + v106 + 88);
          if ( v100 == 6 )
          {
            ++*(_DWORD *)((char *)qword_140026B68 + v107 + 8);
          }
          else if ( v100 == 17 )
          {
            ++*(_DWORD *)((char *)qword_140026B68 + v107 + 32);
          }
          else
          {
            ++*(_DWORD *)((char *)qword_140026B68 + v107 + 56);
          }
          v108 = *(_BYTE *)(p_Blink + 64);
          if ( (v108 & 4) != 0 )
          {
            v109 = 136 * v105;
            if ( (v108 & 8) != 0 )
              ++*(_QWORD *)((char *)qword_140026B68 + v109 + 120);
            else
              ++*(_QWORD *)((char *)qword_140026B68 + v109 + 128);
          }
        }
        while ( v104 );
      }
      *(_QWORD *)(a1 + 64) = p_Blink;
      SlbNatIpsHandleIncomingUnicastDatagram(a1, v104);
      *(_QWORD *)(a1 + 64) = 0;
    }
    v82 = p_Blink - 8;
    v110 = _InterlockedExchangeAdd64((volatile signed __int64 *)(p_Blink - 8), 0xFFFFFFFFFFFFFFFFuLL);
    v115 = v110 <= 1;
    v111 = v110 - 1;
    if ( !v115 )
      return;
    if ( !v111 )
    {
LABEL_196:
      v85 = *(_QWORD *)(v82 + 80);
      if ( v85 )
        WinNatCleanupBinding(v85);
      v86 = *(void (__fastcall **)(__int64))(v82 + 48);
      if ( v86 )
        v86(p_Blink);
      v87 = HIDWORD(KeGetPcr()[1].LockArray);
      v88 = (__int64 *)(*(_QWORD *)(v82 + 288) + 8LL);
      if ( *(_BYTE *)(v82 + 256) )
        v88 = *(__int64 **)(v82 + 288);
      v89 = *v88;
      v90 = v89 + ((unsigned __int64)(unsigned int)(v87 + 1) << 7);
      if ( !*(_BYTE *)(v90 + 176) )
        PplpLazyInitializeLookasideList(v89, v90 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v90 + 64), (PVOID)v82);
      return;
    }
LABEL_264:
    __fastfail(0xEu);
  }
  v112 = v22;
  v113 = *(_QWORD *)(a1 + 56);
  if ( v147 )
    v112 = v147;
  v114 = *(unsigned __int8 *)(v112 + 150);
  if ( (unsigned __int8)v114 <= 1u )
    goto LABEL_351;
  if ( *(_DWORD *)(a1 + 120) >= *(_DWORD *)(*(_QWORD *)(v113 + 8) + 24LL) || (*(_BYTE *)(v112 + 212) & 4) == 0 )
    goto LABEL_275;
  if ( v142 == 6 )
  {
    v115 = *(_WORD *)(v113 + 320) <= 1u;
    goto LABEL_274;
  }
  if ( v142 == 17 )
  {
    v115 = *(_WORD *)(v113 + 280) <= 1u;
LABEL_274:
    if ( !v115 )
      goto LABEL_275;
LABEL_351:
    if ( (xmmword_1400262E0 & 4) != 0 )
      WPP_SF_dddd(
        *(_QWORD *)(v113 + 8),
        v112,
        v114,
        *(unsigned __int8 *)(v112 + 150),
        *(_DWORD *)(a1 + 120),
        *(_DWORD *)(*(_QWORD *)(v113 + 8) + 24LL),
        v151);
    SlbNatIpsSendICMPError(p_Blink, a1, v22);
    return;
  }
LABEL_275:
  v116 = *(_QWORD *)(a1 + 40);
  LODWORD(HashTable) = 0;
  if ( v116 )
  {
    if ( (BYTE8(xmmword_1400262E0) & 4) != 0 )
      WPP_SF_d(1282, 22, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, *(unsigned __int16 *)(v116 + 32));
    v117 = (unsigned __int16)(*(_WORD *)(v116 + 32) - 243) <= 1u;
  }
  else
  {
    v117 = 0;
  }
  v143 = v117;
  while ( 1 )
  {
    v144 = 0;
    v118 = v113;
    v119 = (_QWORD *)v113;
    v120 = v113;
    v113 = *(_QWORD *)v113;
    v52 = (*(_DWORD *)(v118 + 136) & 0x20000000) == 0;
    *v119 = 0;
    if ( v52 || (*(_BYTE *)(a1 + 2) & 2) != 0 )
    {
      v52 = (*(_BYTE *)(a1 + 2) & 2) == 0;
      v123 = (_DWORD *)v120;
      v144 = (_DWORD *)v120;
      if ( v52 )
      {
        v124 = *(_DWORD *)(v120 + 144);
        if ( (v124 & 0x18) != 0 && (v124 & 0x100) != 0 )
        {
          SlbNatFillPacketChecksum(v120, v22);
          v123 = v144;
        }
        v123[76] &= 0xFF000000;
        v144[44] &= 0xFFFF000F;
        *((_QWORD *)v144 + 18) = 0;
      }
      else
      {
        *(_QWORD *)(v120 + 272) = 0;
      }
      goto LABEL_301;
    }
    if ( !gAccount )
    {
      if ( v117 )
      {
        v121 = 14;
        goto LABEL_288;
      }
      goto LABEL_287;
    }
    if ( !v117 )
    {
      _InterlockedIncrement64(&gNBLClone);
LABEL_287:
      v121 = 0;
      goto LABEL_288;
    }
    _InterlockedIncrement64(&gNBLDeepClone);
    v121 = 14;
LABEL_288:
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64 (__fastcall *)(), bool, int, _DWORD, _DWORD **))(*(_QWORD *)(a1 + 16) + 56LL))(
      *(_QWORD *)(a1 + 8),
      *(_QWORD *)(a1 + 48),
      v120,
      SlbNatIpsClientNotifyEvent,
      v117,
      v121,
      0,
      &v144);
    if ( (*(_DWORD *)(v120 + 144) & 0x188) == 0x188 )
      SlbNatFillPacketChecksum((__int64)v144, v22);
    v122 = v144;
    if ( v144 )
      goto LABEL_302;
    if ( !gAccount )
      goto LABEL_341;
    _InterlockedIncrement64(&gNBLCloneFail);
LABEL_301:
    v122 = v144;
    if ( !v144 )
    {
LABEL_341:
      v134 = 8;
      LODWORD(HashTable) = 8;
LABEL_343:
      v131 = v142;
      SlbNatIpsDropDatagram(a1, v120, v142, v134);
      goto LABEL_331;
    }
LABEL_302:
    v125 = v141;
    *((_QWORD *)v122 + 26) = *(unsigned int *)(v120 + 208);
    *((_QWORD *)v144 + 22) = *(_QWORD *)(v120 + 176);
    if ( !(unsigned __int8)SlbNatLibTranslate((__int64)qword_1400263D8, p_Blink, v125, 0, v22, v147, (__int64)v144) )
    {
      if ( v144 != (_DWORD *)v120 )
      {
        **(_QWORD **)(a1 + 152) = v144;
        *(_QWORD *)(a1 + 152) = v144;
      }
      v134 = 9;
      v144 = 0;
      LODWORD(HashTable) = 9;
      goto LABEL_343;
    }
    v126 = v141;
    v127 = v142;
    **(_QWORD **)(a1 + 136) = v144;
    *(_QWORD *)(a1 + 136) = v144;
    v128 = v145;
    *(_BYTE *)(a1 + 2) ^= (v126 ^ *(_BYTE *)(a1 + 2)) & 1;
    v129 = 136 * v128;
    if ( (_BYTE)v126 )
    {
      ++*(_QWORD *)((char *)qword_140026B68 + v129 + 88);
      if ( (_BYTE)v127 == 6 )
      {
        ++*(_DWORD *)((char *)qword_140026B68 + v129 + 8);
      }
      else if ( (_BYTE)v127 == 17 )
      {
        ++*(_DWORD *)((char *)qword_140026B68 + v129 + 32);
      }
      else
      {
        ++*(_DWORD *)((char *)qword_140026B68 + v129 + 56);
      }
      v130 = *(_BYTE *)(p_Blink + 64);
      if ( (v130 & 4) != 0 )
      {
        if ( (v130 & 8) != 0 )
          ++*(_QWORD *)((char *)qword_140026B68 + v129 + 120);
        else
          ++*(_QWORD *)((char *)qword_140026B68 + v129 + 128);
      }
    }
    else
    {
      ++*(_QWORD *)((char *)qword_140026B68 + v129 + 96);
      if ( (_BYTE)v127 == 6 )
      {
        ++*(_DWORD *)((char *)qword_140026B68 + v129 + 12);
      }
      else if ( (_BYTE)v127 == 17 )
      {
        ++*(_DWORD *)((char *)qword_140026B68 + v129 + 36);
      }
      else
      {
        ++*(_DWORD *)((char *)qword_140026B68 + v129 + 60);
      }
    }
    if ( byte_140026B80 )
      SlbNatLibClampMssOnIpPkt(a1, p_Blink, v126, v22, *(_QWORD *)(*(_QWORD *)(a1 + 56) + 8LL));
    if ( !v144 )
    {
      v134 = (unsigned int)HashTable;
      goto LABEL_343;
    }
    if ( v144 != (_DWORD *)v120 )
    {
      if ( v143 )
      {
        **(_QWORD **)(a1 + 152) = v120;
        *(_QWORD *)(a1 + 152) = v120;
      }
      else
      {
        *((_QWORD *)&v148 + 1) = v120;
        v149 = 0;
        if ( gAccount && v118 )
        {
          do
          {
            _InterlockedIncrement64(&gNBLRelease);
            v118 = *(_QWORD *)v118;
          }
          while ( v118 );
        }
        (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 64LL))(*(_QWORD *)(a1 + 8), &v148);
      }
      if ( (*(_BYTE *)(a1 + 2) & 2) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v129, v127);
    }
    v131 = v142;
LABEL_331:
    if ( !v113 )
      goto LABEL_347;
    if ( v147 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v129, v127);
    v132 = SlbNatLibParseNBL((__int64)qword_1400263D8, v113, v145);
    v22 = v132;
    if ( !v132 )
      break;
    if ( !v144 )
    {
      v135 = (unsigned int)HashTable;
      goto LABEL_346;
    }
    v117 = v143;
    if ( !*(_WORD *)(v132 + 224) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v143, v133);
      v117 = v143;
    }
  }
  v135 = 1;
LABEL_346:
  SlbNatIpsDropDatagram(a1, v113, v131, v135);
LABEL_347:
  v136 = *(_QWORD *)(a1 + 80);
  if ( v136 != p_Blink )
  {
    if ( v136 )
      WinNatLibDereferenceSession(v136 - 8);
    *(_QWORD *)(a1 + 80) = p_Blink;
  }
}

```

## disassembly

```asm
0x1400020e0  push    rbp
0x1400020e2  push    rbx
0x1400020e3  push    rsi
0x1400020e4  push    rdi
0x1400020e5  push    r15
0x1400020e7  lea     rbp, [rsp-37h]
0x1400020ec  sub     rsp, 0F0h
0x1400020f3  mov     rax, cs:__security_cookie
0x1400020fa  xor     rax, rsp
0x1400020fd  mov     [rbp+57h+var_28], rax
0x140002101  xor     eax, eax
0x140002103  xorps   xmm1, xmm1
0x140002106  mov     byte ptr [rbp+57h+var_88], al
0x140002109  mov     rbx, rcx
0x14000210c  mov     rax, [rcx+28h]
0x140002110  xorps   xmm0, xmm0
0x140002113  xor     ecx, ecx; ProcNumber
0x140002115  mov     [rbp+57h+var_80], rax
0x140002119  movups  [rbp+57h+var_98], xmm0
0x14000211d  movups  [rbp+57h+var_78], xmm1
0x140002121  movups  [rbp+57h+var_68], xmm1
0x140002125  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000212c  nop     dword ptr [rax+rax+00h]
0x140002131  mov     rcx, cs:qword_1400263D8
0x140002138  mov     rsi, [rbx+38h]
0x14000213c  mov     r15d, eax
0x14000213f  imul    rdi, r15, 0E8h
0x140002146  mov     [rbp+57h+var_B0], r15d
0x14000214a  add     rdi, [rcx+548h]
0x140002151  mov     rcx, [rsi+8]
0x140002155  cmp     qword ptr [rcx], 0
0x140002159  jz      short loc_140002160
0x14000215b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140002160  mov     rcx, [rsi+8]; NetBuffer
0x140002164  mov     r9d, 5
0x14000216a  mov     [rsp+110h+arg_8], r12
0x140002172  mov     r8b, 1
0x140002175  mov     rdx, rdi
0x140002178  mov     [rsp+110h+arg_18], r14
0x140002180  call    WinNatParseNb
0x140002185  mov     rsi, [rbx+38h]
0x140002189  test    al, al
0x14000218b  jz      short loc_140002196
0x14000218d  test    rdi, rdi
0x140002190  jnz     loc_140002280
0x140002196  xor     ecx, ecx; ProcNumber
0x140002198  mov     rdi, rsi
0x14000219b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400021a2  nop     dword ptr [rax+rax+00h]
0x1400021a7  mov     r15d, eax
0x1400021aa  xor     r12d, r12d
0x1400021ad  xor     eax, eax
0x1400021af  xorps   xmm0, xmm0
0x1400021b2  cmp     cs:Microsoft_Windows_WinNatEnableBits, al
0x1400021b8  mov     r14d, 1
0x1400021be  movups  [rbp+57h+var_40], xmm0
0x1400021c2  mov     byte ptr [rbp+57h+var_30], al
0x1400021c5  jge     short loc_1400021F3
0x1400021c7  cmp     word ptr [rbx], 2
0x1400021cb  jnz     short loc_1400021F3
0x1400021cd  mov     r8, [rbx+28h]
0x1400021d1  xor     r9d, r9d
0x1400021d4  mov     edx, [rbx+20h]
0x1400021d7  mov     ecx, [rbx+18h]
0x1400021da  mov     dword ptr [rsp+110h+var_D8], r14d
0x1400021df  mov     dword ptr [rsp+110h+var_E0], r14d
0x1400021e4  mov     [rsp+110h+var_E8], rsi
0x1400021e9  mov     dword ptr [rsp+110h+var_F0], r12d
0x1400021ee  call    SlbNatIpsLogIPv4Datagram
0x1400021f3  mov     rax, [rsi]
0x1400021f6  test    rax, rax
0x1400021f9  jz      short loc_14000220B
0x1400021fb  nop     dword ptr [rax+rax+00h]
0x140002200  mov     rax, [rax]
0x140002203  inc     r14d
0x140002206  test    rax, rax
0x140002209  jnz     short loc_140002200
0x14000220b  cmp     cs:gAccount, r12d
0x140002212  mov     byte ptr [rbp+57h+var_40], r12b
0x140002216  mov     qword ptr [rbp+57h+var_40+8], rsi
0x14000221a  mov     [rbp+57h+var_30], r12
0x14000221e  jz      short loc_140002240
0x140002220  test    rdi, rdi
0x140002223  jz      short loc_140002240
0x140002225  nop     word ptr [rax+rax+00000000h]
0x140002230  lock inc cs:gNBLDrop
0x140002238  mov     rdi, [rdi]
0x14000223b  test    rdi, rdi
0x14000223e  jnz     short loc_140002230
0x140002240  mov     rax, [rbx+10h]
0x140002244  lea     r8, [rbp+57h+var_40]
0x140002248  mov     rdx, [rbx+30h]
0x14000224c  mov     rcx, [rbx+8]
0x140002250  mov     rax, [rax+20h]
0x140002254  call    _guard_dispatch_icall
0x140002259  mov     rcx, cs:qword_140026B68
0x140002260  imul    rdx, r15, 88h
0x140002267  mov     eax, r14d
0x14000226a  add     [rcx+rdx+68h], rax
0x14000226f  mov     rax, cs:qword_140026B68
0x140002276  add     [rdx+rax+40h], r14d
0x14000227b  jmp     loc_1400037F1
0x140002280  mov     byte ptr [rbp+57h+var_98], 0
0x140002284  mov     qword ptr [rbp+57h+var_98+8], rsi
0x140002288  mov     [rbp+57h+var_88], rsi
0x14000228c  test    byte ptr [rdi+0D4h], 1
0x140002293  movzx   r14d, byte ptr [rdi+10h]
0x140002298  mov     [rbp+57h+var_C0], 0
0x14000229c  jz      short loc_1400022C5
0x14000229e  mov     eax, [rdi+0DCh]
0x1400022a4  cmp     [rbx+0A0h], eax
0x1400022aa  setz    cl
0x1400022ad  cmp     word ptr [rdi+0E0h], 0
0x1400022b5  mov     [rbp+57h+var_C0], cl
0x1400022b8  jnz     short loc_1400022C2
0x1400022ba  mov     [rbx+0A0h], eax
0x1400022c0  jmp     short loc_1400022C5
0x1400022c2  mov     [rbp+57h+var_C0], cl
0x1400022c5  xor     r12d, r12d
0x1400022c8  test    byte ptr [rdi+0D4h], 1
0x1400022cf  jz      short loc_14000234E
0x1400022d1  mov     eax, [rdi+0DCh]
0x1400022d7  cmp     [rbx+0A0h], eax
0x1400022dd  jz      short loc_140002355
0x1400022df  mov     [rbx+0A0h], r12d
0x1400022e6  test    byte ptr cs:xmmword_1400262E0, 4
0x1400022ed  jz      short loc_14000230C
0x1400022ef  mov     r9d, [rdi+0DCh]
0x1400022f6  lea     r8, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids
0x1400022fd  mov     edx, 1Fh
0x140002302  mov     ecx, 402h
0x140002307  call    WPP_SF_d
0x14000230c  cmp     cs:gAccount, r12d
0x140002313  jz      short loc_140002330
0x140002315  mov     rax, qword ptr [rbp+57h+var_98+8]
0x140002319  test    rax, rax
0x14000231c  jz      short loc_140002330
0x14000231e  xchg    ax, ax
0x140002320  lock inc cs:gNBLReturn
0x140002328  mov     rax, [rax]
0x14000232b  test    rax, rax
0x14000232e  jnz     short loc_140002320
0x140002330  mov     rax, [rbx+10h]
0x140002334  lea     r8, [rbp+57h+var_98]
0x140002338  mov     rdx, [rbx+30h]
0x14000233c  mov     rcx, [rbx+8]
0x140002340  mov     rax, [rax+28h]
0x140002344  call    _guard_dispatch_icall
0x140002349  jmp     loc_1400037F1
0x14000234e  mov     [rbx+0A0h], r12d
0x140002355  movzx   eax, byte ptr [rdi+0D4h]
0x14000235c  and     al, 3
0x14000235e  mov     [rsp+110h+arg_10], r13
0x140002366  cmp     al, 1
0x140002368  jnz     short loc_140002371
0x14000236a  mov     [rbx+0A0h], r12d
0x140002371  mov     r13, 400000000020042h
0x14000237b  cmp     r14b, 3Ah ; ':'
0x14000237f  ja      loc_14000373F
0x140002385  bt      r13, r14
0x140002389  jnb     loc_14000373F
0x14000238f  test    byte ptr [rdi+0D4h], 1
0x140002396  jz      short loc_1400023A5
0x140002398  cmp     byte ptr cs:dword_140026B78+2, r12b
0x14000239f  jz      loc_14000373F
0x1400023a5  mov     [rbp+57h+var_BF], r14b
0x1400023a9  cmp     [rdi+0D5h], r12b
0x1400023b0  jz      short loc_140002424
0x1400023b2  mov     rcx, cs:qword_1400263D8
0x1400023b9  mov     r9d, r15d
0x1400023bc  mov     r8, rsi
0x1400023bf  mov     rdx, rdi
0x1400023c2  call    SlbNatLibParseICMPInnerPacket
0x1400023c7  mov     rsi, rax
0x1400023ca  test    rax, rax
0x1400023cd  jnz     short loc_140002401
0x1400023cf  test    byte ptr cs:xmmword_1400262E0, 4
0x1400023d6  jz      short loc_1400023EE
0x1400023d8  mov     edx, 20h ; ' '
0x1400023dd  lea     r8, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids
0x1400023e4  mov     ecx, 402h
0x1400023e9  call    WPP_SF_
0x1400023ee  mov     edx, 1
0x1400023f3  lea     rcx, [rbp+57h+var_98]
0x1400023f7  call    SlbNatAccountChain
0x1400023fc  jmp     loc_1400037D0
0x140002401  movzx   r14d, byte ptr [rsi+10h]
0x140002406  lea     r15, [rsi+98h]
0x14000240d  add     rax, 0B4h
0x140002413  mov     [rbp+57h+var_A0], rdi
0x140002417  mov     qword ptr [rbp+57h+var_40], rax
0x14000241b  lea     rdi, [rsi+0B4h]
0x140002422  jmp     short loc_14000243D
0x140002424  mov     rsi, rdi
0x140002427  mov     [rbp+57h+var_A0], r12
0x14000242b  lea     r15, [rdi+0B4h]
0x140002432  add     rdi, 98h
0x140002439  mov     qword ptr [rbp+57h+var_40], rdi
0x14000243d  mov     rax, [rbx+28h]
0x140002441  mov     r13d, 1
0x140002447  mov     [rbp+57h+var_BE], r12b
0x14000244b  test    rax, rax
0x14000244e  jz      loc_1400024F3
0x140002454  cmp     cs:dword_1400264E8, r12d
0x14000245b  jle     loc_1400024E9
0x140002461  mov     eax, [rax+18h]
0x140002464  test    al, 4
0x140002466  jnz     loc_1400024F3
0x14000246c  mov     rax, [rbx+50h]
0x140002470  test    rax, rax
0x140002473  jz      loc_140002840
0x140002479  movzx   ecx, [rbp+57h+var_C0]
0x14000247d  add     rax, 0B8h
0x140002483  mov     byte ptr [rsp+110h+var_E0], cl
0x140002487  xor     r9d, r9d
0x14000248a  mov     [rsp+110h+var_E8], rax
0x14000248f  mov     ecx, r13d
0x140002492  mov     r8, r15
0x140002495  mov     byte ptr [rsp+110h+var_F0], r14b
0x14000249a  mov     rdx, rdi
0x14000249d  call    WinNatIsMatchingSession
0x1400024a2  test    al, al
0x1400024a4  jz      loc_140002840
0x1400024aa  mov     rdi, [rbx+50h]
0x1400024ae  test    [rsi+0D4h], r13b
0x1400024b5  jz      short loc_1400024D6
0x1400024b7  test    byte ptr cs:xmmword_1400262E0, 4
0x1400024be  jz      short loc_1400024D6
0x1400024c0  mov     r9d, [rsi+0DCh]
0x1400024c7  mov     edx, 23h ; '#'
0x1400024cc  mov     [rsp+110h+var_F0], rdi
0x1400024d1  call    WPP_SF_dq
0x1400024d6  test    rdi, rdi
0x1400024d9  jnz     loc_140002D8C
0x1400024df  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400024e4  jmp     loc_140002D8C
0x1400024e9  cmp     [rax+28h], r12d
0x1400024ed  jnz     loc_14000246C
0x1400024f3  cmp     [rbx+40h], r12
0x1400024f7  jnz     loc_14000246C
0x1400024fd  mov     rax, [rbx+50h]
0x140002501  test    rax, rax
0x140002504  jz      short loc_140002573
0x140002506  movzx   ecx, [rbp+57h+var_C0]
0x14000250a  add     rax, 0A0h
0x140002510  mov     byte ptr [rsp+110h+var_E0], cl
0x140002514  movzx   r9d, r13b
0x140002518  mov     ecx, [rbx+18h]
0x14000251b  mov     r8, r15
0x14000251e  mov     [rsp+110h+var_E8], rax
0x140002523  mov     rdx, rdi
0x140002526  mov     byte ptr [rsp+110h+var_F0], r14b
0x14000252b  call    WinNatIsMatchingSession
0x140002530  test    al, al
0x140002532  jz      short loc_140002573
0x140002534  mov     rdi, [rbx+50h]
0x140002538  test    [rsi+0D4h], r13b
0x14000253f  jz      short loc_140002560
0x140002541  test    byte ptr cs:xmmword_1400262E0, 4
0x140002548  jz      short loc_140002560
0x14000254a  mov     r9d, [rsi+0DCh]
0x140002551  mov     edx, 21h ; '!'
0x140002556  mov     [rsp+110h+var_F0], rdi
0x14000255b  call    WPP_SF_dq
0x140002560  test    rdi, rdi
0x140002563  jnz     loc_140002611
0x140002569  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000256e  jmp     loc_140002611
0x140002573  test    [rsi+0D4h], r13b
0x14000257a  jz      short loc_1400025BD
0x14000257c  cmp     [rsi+0E0h], r12w
0x140002584  jz      short loc_1400025BD
0x140002586  test    byte ptr cs:xmmword_1400262E0, 4
0x14000258d  jz      short loc_1400025AC
0x14000258f  mov     r9d, [rsi+0DCh]
0x140002596  lea     r8, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids
0x14000259d  mov     edx, 22h ; '"'
0x1400025a2  mov     ecx, 402h
0x1400025a7  call    WPP_SF_d
0x1400025ac  mov     edx, r13d
0x1400025af  lea     rcx, [rbp+57h+var_98]
0x1400025b3  call    SlbNatAccountChain
0x1400025b8  jmp     loc_1400037D0
0x1400025bd  mov     rcx, cs:qword_1400263D8
0x1400025c4  mov     r9, r15
0x1400025c7  mov     edx, [rbx+18h]
0x1400025ca  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1400025ce  mov     byte ptr [rsp+110h+var_E8], r13b
0x1400025d3  mov     r8, rdi
0x1400025d6  mov     byte ptr [rsp+110h+var_F0], r14b
0x1400025db  call    WinNatFindSessionEntry
0x1400025e0  test    rax, rax
0x1400025e3  lea     rdi, [rax+8]
0x1400025e7  cmovz   rdi, r12
0x1400025eb  test    rdi, rdi
0x1400025ee  jnz     short loc_140002611
0x1400025f0  cmp     [rbp+57h+var_A0], r12
0x1400025f4  jnz     short loc_1400025AC
0x1400025f6  mov     r8d, [rbp+57h+var_B0]
0x1400025fa  mov     rdx, rsi
  ... truncated ...
```
