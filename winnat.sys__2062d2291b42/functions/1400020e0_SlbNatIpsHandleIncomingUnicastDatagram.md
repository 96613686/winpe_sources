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
- `0x140012538`
- `0x1400157b4`
- `0x140015ad8`
- `0x140015d7c`
- `0x140015ecc`
- `0x140019edc`
- `0x14001d930`
- `0x14001f320`
- `0x14001f4b0`
- `0x14001f560`
- `0x14002e008`
- `0x14002e040`
- `0x14002e304`
- `0x14002e36c`

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
  __int64 v4; // r8
  __int64 v5; // rsi
  ULONG v6; // r15d
  __int64 v7; // rdi
  _QWORD *v8; // rcx
  char v9; // al
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  _QWORD *v13; // rsi
  _QWORD *v14; // rdi
  __int64 v15; // r15
  unsigned int v16; // r14d
  _QWORD *v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // r14
  int v20; // eax
  _QWORD *v21; // rax
  __int64 v22; // r13
  __int64 v23; // rax
  __int64 v24; // rsi
  _WORD *v25; // r15
  _WORD *v26; // rdi
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 p_Blink; // rdi
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 SessionEntry; // rax
  unsigned __int8 v38; // r15
  __int64 v39; // rax
  unsigned __int8 v40; // cl
  __int64 v41; // r8
  __int64 v42; // rdx
  int v43; // ecx
  __int64 v44; // rcx
  __int64 v45; // r14
  unsigned __int8 v46; // r15
  char *v47; // r13
  KIRQL v48; // al
  unsigned int LockArray_high; // ecx
  __int64 v50; // rax
  __int64 v51; // rcx
  volatile signed __int32 *v52; // r13
  _WORD *v53; // rdx
  bool v54; // zf
  volatile signed __int64 *v55; // r13
  __int64 v56; // r8
  int v57; // edi
  int v58; // eax
  _WORD *v59; // rdx
  bool v60; // zf
  unsigned int v61; // eax
  int v62; // edi
  int v63; // eax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY NextEntryHashTable; // rdi
  _QWORD *v65; // rax
  _QWORD *v66; // rax
  _DWORD *v67; // r13
  __int16 v68; // ax
  bool v69; // di
  _BYTE *v70; // r13
  PRTL_DYNAMIC_HASH_TABLE_ENTRY SessionForExternalPacket; // rax
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  bool v75; // r13
  __int64 v76; // rcx
  unsigned __int8 v77; // al
  int v78; // eax
  __int128 v79; // xmm0
  _QWORD *v80; // rax
  __int64 v81; // rax
  int v82; // eax
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  __int64 v86; // rbx
  signed __int64 v87; // rax
  signed __int64 v88; // rax
  void (__fastcall *v89)(__int64); // rax
  int v90; // eax
  __int64 *v91; // rcx
  __int64 v92; // rcx
  __int64 v93; // rdi
  __int64 v94; // rax
  int v95; // r9d
  _QWORD *v96; // rcx
  _QWORD *v97; // rax
  char v98; // al
  __int64 v99; // r14
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // rcx
  __int64 v103; // rax
  unsigned __int8 v104; // r15
  __int64 v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // r8
  unsigned int v108; // eax
  _QWORD *v109; // rdx
  __int64 v110; // r8
  __int64 v111; // r9
  __int64 v112; // rcx
  char v113; // al
  __int64 v114; // rcx
  signed __int64 v115; // rax
  signed __int64 v116; // rax
  __int64 v117; // rdx
  __int64 *v118; // r13
  __int64 v119; // r8
  bool v120; // cc
  __int64 v121; // r14
  bool v122; // cl
  __int64 **v123; // r15
  _QWORD *v124; // rax
  __int64 *v125; // r14
  int v126; // edx
  __int64 *v127; // rcx
  __int64 *v128; // rcx
  int v129; // eax
  int v130; // r8d
  __int64 v131; // r8
  __int64 v132; // rdx
  __int64 v133; // rax
  __int64 v134; // rcx
  char v135; // al
  unsigned __int8 v136; // r15
  __int64 v137; // rax
  __int64 v138; // rdx
  __int64 v139; // r8
  unsigned int v140; // eax
  __int64 v141; // r9
  __int64 v142; // rcx
  BOOL v143; // edx
  int v144; // eax
  _QWORD *v145; // rax
  _DWORD *v146; // [rsp+30h] [rbp-89h]
  unsigned __int8 v147; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int8 v148; // [rsp+51h] [rbp-68h]
  unsigned __int8 v149; // [rsp+52h] [rbp-67h]
  __int64 *v150; // [rsp+58h] [rbp-61h] BYREF
  ULONG v151; // [rsp+60h] [rbp-59h]
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+68h] [rbp-51h]
  __int64 v153; // [rsp+70h] [rbp-49h]
  __int128 v154; // [rsp+78h] [rbp-41h] BYREF
  _QWORD *v155; // [rsp+88h] [rbp-31h]
  __int64 v156; // [rsp+90h] [rbp-29h]
  __int128 v157; // [rsp+98h] [rbp-21h] BYREF
  __int128 v158; // [rsp+A8h] [rbp-11h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B8h] [rbp-1h] BYREF
  __int128 v160; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v161; // [rsp+E0h] [rbp+27h]

  LOBYTE(v155) = 0;
  v156 = *(_QWORD *)(a1 + 40);
  v154 = 0;
  v157 = 0;
  v158 = 0;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v5 = *(_QWORD *)(a1 + 56);
  v6 = CurrentProcessorNumber;
  v151 = CurrentProcessorNumber;
  v7 = *((_QWORD *)qword_1400273D8 + 169) + 232LL * CurrentProcessorNumber;
  v8 = *(_QWORD **)(v5 + 8);
  if ( *v8 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v8, v3, v4);
  v9 = WinNatParseNb(*(PNET_BUFFER *)(v5 + 8));
  v13 = *(_QWORD **)(a1 + 56);
  if ( !v9 || !v7 )
  {
    v14 = *(_QWORD **)(a1 + 56);
    v15 = KeGetCurrentProcessorNumberEx(0);
    v16 = 1;
    v160 = 0;
    LOBYTE(v161) = 0;
    if ( Microsoft_Windows_WinNatEnableBits < 0 && *(_WORD *)a1 == 2 )
      SlbNatIpsLogIPv4Datagram(
        *(_DWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32),
        *(_QWORD *)(a1 + 40),
        0,
        0,
        (__int64)v13,
        1,
        1);
    v17 = (_QWORD *)*v13;
    if ( *v13 )
    {
      do
      {
        v17 = (_QWORD *)*v17;
        ++v16;
      }
      while ( v17 );
    }
    LOBYTE(v160) = 0;
    *((_QWORD *)&v160 + 1) = v13;
    v161 = 0;
    if ( gAccount && v13 )
    {
      do
      {
        _InterlockedIncrement64(&gNBLDrop);
        v14 = (_QWORD *)*v14;
      }
      while ( v14 );
    }
    (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 32LL))(
      *(_QWORD *)(a1 + 8),
      *(_QWORD *)(a1 + 48),
      &v160);
    v18 = 136 * v15;
    *(_QWORD *)((char *)qword_140027B68 + v18 + 104) += v16;
    *(_DWORD *)((char *)qword_140027B68 + v18 + 64) += v16;
    return;
  }
  LOBYTE(v154) = 0;
  *((_QWORD *)&v154 + 1) = v13;
  v155 = v13;
  v54 = (*(_BYTE *)(v7 + 212) & 1) == 0;
  v19 = *(unsigned __int8 *)(v7 + 16);
  v147 = 0;
  if ( !v54 )
  {
    v20 = *(_DWORD *)(v7 + 220);
    LOBYTE(v11) = *(_DWORD *)(a1 + 160) == v20;
    v54 = *(_WORD *)(v7 + 224) == 0;
    v147 = v11;
    if ( v54 )
      *(_DWORD *)(a1 + 160) = v20;
    else
      v147 = v11;
  }
  if ( (*(_BYTE *)(v7 + 212) & 1) != 0 )
  {
    if ( *(_DWORD *)(a1 + 160) != *(_DWORD *)(v7 + 220) )
    {
      *(_DWORD *)(a1 + 160) = 0;
      if ( (xmmword_1400272E0 & 4) != 0 )
        WPP_SF_d(1026, 31, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, *(unsigned int *)(v7 + 220));
      if ( gAccount )
      {
        v21 = (_QWORD *)*((_QWORD *)&v154 + 1);
        if ( *((_QWORD *)&v154 + 1) )
        {
          do
          {
            _InterlockedIncrement64(&gNBLReturn);
            v21 = (_QWORD *)*v21;
          }
          while ( v21 );
        }
      }
      (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 40LL))(
        *(_QWORD *)(a1 + 8),
        *(_QWORD *)(a1 + 48),
        &v154);
      return;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 160) = 0;
  }
  if ( (*(_BYTE *)(v7 + 212) & 3) == 1 )
    *(_DWORD *)(a1 + 160) = 0;
  v22 = 0x400000000020042LL;
  if ( (unsigned __int8)v19 > 0x3Au
    || !_bittest64(&v22, v19)
    || (*(_BYTE *)(v7 + 212) & 1) != 0 && !BYTE2(dword_140027B78) )
  {
    if ( *(_QWORD *)(a1 + 64) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v11, v10, v12);
    if ( (byte_140027BED & 4) != 0 && *(_WORD *)a1 == 2 )
    {
      v143 = (unsigned __int8)v19 > 0x3Au || !_bittest64(&v22, v19);
      v144 = 19;
      if ( !v143 )
        v144 = 2;
      SlbNatIpsLogIPv4Datagram(
        *(_DWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32),
        *(_QWORD *)(a1 + 40),
        0,
        0,
        *(_QWORD *)(a1 + 56),
        2,
        v144);
    }
    if ( gAccount )
    {
      v145 = (_QWORD *)*((_QWORD *)&v154 + 1);
      if ( *((_QWORD *)&v154 + 1) )
      {
        do
        {
          _InterlockedIncrement64(&gNBLReturn);
          v145 = (_QWORD *)*v145;
        }
        while ( v145 );
      }
    }
    goto LABEL_368;
  }
  v148 = v19;
  if ( *(_BYTE *)(v7 + 213) )
  {
    v23 = SlbNatLibParseICMPInnerPacket(qword_1400273D8, v7, v13, v6);
    v24 = v23;
    if ( !v23 )
    {
      if ( (xmmword_1400272E0 & 4) != 0 )
        WPP_SF_(1026, 32, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids);
      goto LABEL_37;
    }
    LOBYTE(v19) = *(_BYTE *)(v23 + 16);
    v25 = (_WORD *)(v23 + 152);
    v153 = v7;
    *(_QWORD *)&v160 = v23 + 180;
    v26 = (_WORD *)(v23 + 180);
  }
  else
  {
    v24 = v7;
    v153 = 0;
    v25 = (_WORD *)(v7 + 180);
    v26 = (_WORD *)(v7 + 152);
    *(_QWORD *)&v160 = v26;
  }
  v27 = *(_QWORD *)(a1 + 40);
  v149 = 0;
  if ( v27 )
  {
    if ( dword_1400274E8 <= 0 )
    {
      if ( *(_DWORD *)(v27 + 40) )
        goto LABEL_43;
    }
    else if ( (*(_DWORD *)(v27 + 24) & 4) == 0 )
    {
LABEL_43:
      v28 = *(_QWORD *)(a1 + 80);
      if ( v28 && (unsigned __int8)WinNatIsMatchingSession(1, (_DWORD)v26, (_DWORD)v25, 0, v19, v28 + 184, v147) )
      {
        p_Blink = *(_QWORD *)(a1 + 80);
        if ( (*(_BYTE *)(v24 + 212) & 1) != 0 && (xmmword_1400272E0 & 4) != 0 )
          WPP_SF_dq(v30, 35, v31, *(unsigned int *)(v24 + 220), *(_QWORD *)(a1 + 80));
        if ( !p_Blink )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v30, v29, v31);
LABEL_175:
        v81 = *(_QWORD *)(a1 + 112);
        v40 = 0;
        v147 = 0;
        if ( v81 == *(_QWORD *)(p_Blink + 32) && v81 )
          goto LABEL_226;
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
        v42 = *(_QWORD *)(p_Blink + 32);
        if ( v42 )
        {
          (*(void (__fastcall **)(_QWORD, __int64, __int128 *))(*(_QWORD *)(a1 + 16) + 112LL))(
            *(_QWORD *)(a1 + 8),
            v42,
            &v157);
          *(_DWORD *)(a1 + 120) = DWORD1(v158);
          v82 = v158;
        }
        else
        {
          v82 = 0;
          LODWORD(v158) = 0;
        }
        if ( *(_QWORD *)(p_Blink + 32) && *(_DWORD *)(p_Blink + 16) == v82 )
        {
          v46 = v148;
        }
        else
        {
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
          v46 = v148;
          if ( !(unsigned __int8)SlbNatIpsRefreshInternalNexthop(a1, v148, p_Blink) )
            return;
          KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
        }
        v45 = *(_QWORD *)(p_Blink + 32);
        goto LABEL_186;
      }
      if ( v153 && (*(_BYTE *)(v24 + 212) & 1) == 0 )
      {
        v150 = (__int64 *)qword_1400273D8;
        v47 = (char *)qword_1400273D8 + 192;
        v48 = KfRaiseIrql(2u);
        LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
        v147 = v48;
        v50 = LockArray_high;
        v51 = LockArray_high & *((_DWORD *)v47 + 2);
        v156 = v50;
        v52 = (volatile signed __int32 *)&v47[64 * v51 + 64];
        memset(&LockHandle, 0, sizeof(LockHandle));
        _InterlockedIncrement(v52);
        if ( !KeTestSpinLock((PKSPIN_LOCK)v150 + 24) )
        {
          _InterlockedDecrement(v52);
          KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v150 + 24, &LockHandle);
          _InterlockedIncrement(v52);
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        }
        v53 = v26 + 2;
        v54 = *v26 == 2;
        memset(&LockHandle, 0, sizeof(LockHandle));
        v55 = 0;
        if ( !v54 )
          v53 = v26 + 4;
        v56 = 4;
        if ( !v54 )
          v56 = 16;
        v57 = RtlComputeToeplitzHash(v150 + 67, v53, v56, 0);
        v58 = RtlComputeToeplitzHash(v150 + 67, v160 + 2, 2, 0);
        v59 = v25 + 2;
        v60 = *v25 == 2;
        LODWORD(HashTable) = v57 ^ v58;
        if ( !v60 )
          v59 = v25 + 4;
        v61 = 4;
        if ( !v60 )
          v61 = 16;
        v62 = (unsigned int)HashTable ^ RtlComputeToeplitzHash(v150 + 67, v59, v61, 0);
        v63 = RtlComputeToeplitzHash(v150 + 67, v25 + 1, 2, 0);
        HashTable = (PRTL_DYNAMIC_HASH_TABLE)v150[65];
        LockHandle.LockQueue = 0;
        NextEntryHashTable = RtlLookupEntryHashTable(
                               HashTable,
                               v62 ^ v63 | 0x80000000,
                               (PRTL_DYNAMIC_HASH_TABLE_CONTEXT)&LockHandle);
        if ( NextEntryHashTable )
        {
          while ( !(unsigned __int8)WinNatIsMatchingSession(
                                      1,
                                      v160,
                                      (_DWORD)v25,
                                      0,
                                      v19,
                                      (__int64)NextEntryHashTable,
                                      0) )
          {
            v55 = 0;
            NextEntryHashTable = RtlGetNextEntryHashTable(HashTable, (PRTL_DYNAMIC_HASH_TABLE_CONTEXT)&LockHandle);
            if ( !NextEntryHashTable )
              goto LABEL_124;
          }
          v55 = (volatile signed __int64 *)&NextEntryHashTable[-8];
          if ( NextEntryHashTable != (PRTL_DYNAMIC_HASH_TABLE_ENTRY)192 && _InterlockedIncrement64(v55) <= 1 )
            __fastfail(0xEu);
        }
LABEL_124:
        _InterlockedDecrement((volatile signed __int32 *)&v150[8 * ((unsigned int)v156 & (_DWORD)v150[25]) + 32]);
        KeLowerIrql(v147);
        if ( !v55 || (p_Blink = (__int64)(v55 + 1), v55 == (volatile signed __int64 *)-8LL) )
        {
          if ( gAccount )
          {
            v65 = (_QWORD *)*((_QWORD *)&v154 + 1);
            if ( *((_QWORD *)&v154 + 1) )
            {
              do
              {
                _InterlockedIncrement64(&gNBLReturn);
                v65 = (_QWORD *)*v65;
              }
              while ( v65 );
            }
          }
          goto LABEL_368;
        }
        goto LABEL_175;
      }
      v147 = 0;
      if ( (*(_BYTE *)(v24 + 212) & 1) != 0 && *(_WORD *)(v24 + 224) )
      {
        if ( (xmmword_1400272E0 & 4) != 0 )
          WPP_SF_d(1026, 36, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, *(unsigned int *)(v24 + 220));
        if ( gAccount )
        {
          v66 = (_QWORD *)*((_QWORD *)&v154 + 1);
          if ( *((_QWORD *)&v154 + 1) )
          {
            do
            {
              _InterlockedIncrement64(&gNBLReturn);
              v66 = (_QWORD *)*v66;
            }
            while ( v66 );
          }
        }
        goto LABEL_368;
      }
      v67 = 0;
      v150 = 0;
      if ( v156 )
      {
        v67 = (_DWORD *)(v156 + 36);
        v150 = (__int64 *)(v156 + 36);
      }
      if ( (_BYTE)v19 != *(_BYTE *)(a1 + 104) )
        goto LABEL_146;
      v68 = *v25;
      if ( *v25 != *(_WORD *)(a1 + 88) )
        goto LABEL_146;
      if ( v68 == 2 )
      {
        if ( v25[1] != *(_WORD *)(a1 + 90) )
          goto LABEL_146;
        v76 = 0;
        while ( 1 )
        {
          v77 = *((_BYTE *)v25 + v76++ + 4);
          if ( v77 != *((_BYTE *)v25 + v76 + 3) )
            break;
          if ( v76 == 4 )
          {
            v78 = 0;
            goto LABEL_160;
          }
        }
        v78 = v77 < *((_BYTE *)v25 + v76 + 3) ? -1 : 1;
LABEL_160:
        if ( v78 )
          goto LABEL_146;
      }
      else if ( v68 != 23 || v25[1] != *(_WORD *)(a1 + 90) || memcmp(v25 + 4, v25 + 4, 0x10u) )
      {
LABEL_146:
        v69 = dword_1400274E8 > 0;
        v146 = v67;
        v70 = (_BYTE *)v160;
        LODWORD(HashTable) = *(_DWORD *)(a1 + 32);
        v156 = (__int64)qword_1400273D8;
        SessionForExternalPacket = WinNatGetSessionForExternalPacket(
                                     (__int64)qword_1400273D8,
                                     (_BYTE *)v160,
                                     v25,
                                     0,
                                     v19,
                                     &v147,
                                     v146,
                                     (int)HashTable);
        if ( v69 && !SessionForExternalPacket )
        {
          v160 = *(_OWORD *)v25;
          DWORD1(v160) = 0;
          SessionForExternalPacket = WinNatGetSessionForExternalPacket(
                                       v156,
                                       v70,
                                       &v160,
                                       (__int64)v25,
                                       v19,
                                       &v147,
                                       v150,
                                       (int)HashTable);
        }
        p_Blink = (__int64)&SessionForExternalPacket->Linkage.Blink;
        if ( !SessionForExternalPacket )
          p_Blink = 0;
        v75 = p_Blink == 0;
        if ( p_Blink )
        {
          if ( (*(_BYTE *)(p_Blink + 64) & 2) == 0 )
          {
            if ( v153 )
              MicrosoftTelemetryAssertTriggeredNoArgsKM(v73, v72, v74);
            SlbNatIpsCheckHairpinning(p_Blink, 0, a1, v24);
          }
          goto LABEL_175;
        }
        if ( v147 )
        {
          SlbNatIpsDropDatagram(a1, *(_QWORD *)(a1 + 56), v148, 6);
          return;
        }
LABEL_162:
        if ( (byte_140027BED & 4) != 0 && *(_WORD *)a1 == 2 )
          SlbNatIpsLogIPv4Datagram(
            *(_DWORD *)(a1 + 24),
            *(_DWORD *)(a1 + 32),
            *(_QWORD *)(a1 + 40),
            0,
            0,
            *(_QWORD *)(a1 + 56),
            2,
            21);
        if ( v75 )
        {
          v79 = *(_OWORD *)v25;
          *(_BYTE *)(a1 + 104) = v19;
          *(_OWORD *)(a1 + 88) = v79;
        }
        if ( gAccount )
        {
          v80 = (_QWORD *)*((_QWORD *)&v154 + 1);
          if ( *((_QWORD *)&v154 + 1) )
          {
            do
            {
              _InterlockedIncrement64(&gNBLReturn);
              v80 = (_QWORD *)*v80;
            }
            while ( v80 );
          }
        }
        goto LABEL_368;
      }
      v75 = 0;
      goto LABEL_162;
    }
  }
  if ( *(_QWORD *)(a1 + 64) )
    goto LABEL_43;
  v33 = *(_QWORD *)(a1 + 80);
  if ( v33
    && (unsigned __int8)WinNatIsMatchingSession(*(_DWORD *)(a1 + 24), (_DWORD)v26, (_DWORD)v25, 1, v19, v33 + 160, v147) )
  {
    p_Blink = *(_QWORD *)(a1 + 80);
    if ( (*(_BYTE *)(v24 + 212) & 1) != 0 && (xmmword_1400272E0 & 4) != 0 )
      WPP_SF_dq(v35, 33, v36, *(unsigned int *)(v24 + 220), *(_QWORD *)(a1 + 80));
    if ( !p_Blink )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v35, v34, v36);
  }
  else
  {
    if ( (*(_BYTE *)(v24 + 212) & 1) != 0 && *(_WORD *)(v24 + 224) )
    {
      if ( (xmmword_1400272E0 & 4) != 0 )
        WPP_SF_d(1026, 34, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, *(unsigned int *)(v24 + 220));
      goto LABEL_37;
    }
    SessionEntry = WinNatFindSessionEntry(
                     (int)qword_1400273D8 + 128,
                     *(_DWORD *)(a1 + 24),
                     (_DWORD)v26,
                     (_DWORD)v25,
                     v19,
                     1);
    p_Blink = SessionEntry + 8;
    if ( !SessionEntry )
      p_Blink = 0;
    if ( !p_Blink )
    {
      if ( v153 )
      {
LABEL_37:
        SlbNatAccountChain(&v154, 1);
LABEL_368:
        (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 40LL))(
          *(_QWORD *)(a1 + 8),
          *(_QWORD *)(a1 + 48),
          &v154);
        return;
      }
      p_Blink = SlbNatIpsCreateSessionForInternalDatagram(a1, v24, v151);
      if ( !p_Blink )
        return;
    }
  }
  v38 = v148;
  if ( *(_DWORD *)(a1 + 24) != 1
    && *(_DWORD *)(p_Blink + 8) != *(_DWORD *)(a1 + 28)
    && !(unsigned __int8)SlbNatIpsRefreshInternalNoRouteState(a1, v148, p_Blink) )
  {
    return;
  }
  v39 = *(_QWORD *)(a1 + 112);
  v40 = 1;
  v147 = 1;
  if ( v39 == *(_QWORD *)(p_Blink + 24) && v39 )
    goto LABEL_226;
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
  v42 = *(_QWORD *)(p_Blink + 24);
  if ( v42 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, __int128 *))(*(_QWORD *)(a1 + 16) + 112LL))(
      *(_QWORD *)(a1 + 8),
      v42,
      &v157);
    v43 = v158;
    *(_DWORD *)(a1 + 120) = DWORD1(v158);
  }
  else
  {
    v43 = 0;
    LODWORD(v158) = 0;
  }
  if ( *(_DWORD *)(p_Blink + 4) != dword_140027840 || !*(_QWORD *)(p_Blink + 24) || *(_DWORD *)(p_Blink + 12) != v43 )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
    if ( !(unsigned __int8)SlbNatIpsRefreshExternalNexthop(a1, v38, p_Blink) )
      return;
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
  }
  v44 = *(unsigned __int8 *)(p_Blink + 64);
  if ( (v44 & 1) == 0 )
    goto LABEL_102;
  v42 = (unsigned __int8)v44;
  LOBYTE(v42) = (unsigned __int8)v44 >> 4;
  if ( dword_1400274E8 <= 0 || (v44 & 0x30) != 0 )
  {
    LOBYTE(v41) = 0;
    v149 = 0;
  }
  else
  {
    v41 = 1;
    v149 = 1;
  }
  LOBYTE(v44) = (unsigned __int8)v44 >> 5;
  if ( (((unsigned __int8)v42 | (unsigned __int8)v44) & 1) == 0 && !(_BYTE)v41 )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
    if ( (byte_140027BED & 4) != 0 && *(_WORD *)a1 == 2 )
      SlbNatIpsLogIPv4Datagram(
        *(_DWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32),
        *(_QWORD *)(a1 + 40),
        0,
        0,
        *(_QWORD *)(a1 + 56),
        2,
        20);
    SlbNatAccountChain(&v154, 1);
    (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 40LL))(
      *(_QWORD *)(a1 + 8),
      *(_QWORD *)(a1 + 48),
      &v154);
    if ( *(_QWORD *)(a1 + 80) == p_Blink )
      *(_QWORD *)(a1 + 80) = 0;
    WinNatLibDereferenceSession(p_Blink - 8);
    return;
  }
  if ( (v44 & 1) != 0 )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
    if ( !(unsigned __int8)SlbNatIpsUpdateExternalHairpinNexthop(a1, p_Blink) )
    {
      SlbNatIpsDropDatagram(a1, *(_QWORD *)(a1 + 56), v38, 5);
      if ( *(_QWORD *)(a1 + 80) == p_Blink )
        *(_QWORD *)(a1 + 80) = 0;
      WinNatLibDereferenceSession(p_Blink - 8);
      return;
    }
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
  }
  if ( !v149 )
  {
LABEL_102:
    if ( (*(_BYTE *)(p_Blink + 64) & 0x11) == 1 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v44, v42, v41);
  }
  v45 = *(_QWORD *)(p_Blink + 24);
  v46 = v148;
LABEL_186:
  if ( !v45 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v44, v42, v41);
  if ( *(_QWORD *)(a1 + 112) != v45
    && !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)(a1 + 16) + 96LL))(
          *(_QWORD *)(a1 + 8),
          v45,
          v41) )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
    goto LABEL_192;
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
  if ( !v45 )
  {
LABEL_192:
    SlbNatIpsDropDatagram(a1, *(_QWORD *)(a1 + 56), v46, 7);
    if ( *(_QWORD *)(a1 + 80) == p_Blink )
      *(_QWORD *)(a1 + 80) = 0;
    v86 = p_Blink - 8;
    v87 = _InterlockedExchangeAdd64((volatile signed __int64 *)(p_Blink - 8), 0xFFFFFFFFFFFFFFFFuLL);
    v120 = v87 <= 1;
    v88 = v87 - 1;
    if ( !v120 )
      return;
    if ( !v88 )
      goto LABEL_196;
    goto LABEL_264;
  }
  v94 = *(_QWORD *)(a1 + 112);
  if ( v94 != v45 )
  {
    if ( *(_QWORD *)(a1 + 128) )
    {
      if ( !v94 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v84, v83, v85);
      if ( (*(_BYTE *)(a1 + 2) & 2) != 0 )
      {
        SlbNatIpsClientPendPackets(a1);
      }
      else
      {
        if ( (byte_140027BED & 8) != 0 && *(_WORD *)a1 == 2 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 112LL))(
            *(_QWORD *)(a1 + 8),
            *(_QWORD *)(a1 + 112),
            &v157);
          v95 = 1;
          if ( (*(_BYTE *)(a1 + 2) & 1) == 0 )
            v95 = *(_DWORD *)p_Blink;
          SlbNatIpsLogIPv4Datagram(
            *(_DWORD *)(a1 + 24),
            *(_DWORD *)(a1 + 32),
            *(_QWORD *)(a1 + 40),
            v95,
            v157,
            *(_QWORD *)(a1 + 128),
            0,
            0);
        }
        v96 = *(_QWORD **)(a1 + 128);
        v97 = *(_QWORD **)(a1 + 136);
        *((_QWORD *)&v154 + 1) = v96;
        v155 = v97;
        if ( gAccount && v96 )
        {
          do
          {
            _InterlockedIncrement64(&gNBLForward);
            v96 = (_QWORD *)*v96;
          }
          while ( v96 );
        }
        (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *, _QWORD, _QWORD))(*(_QWORD *)(a1 + 16) + 48LL))(
          *(_QWORD *)(a1 + 8),
          *(_QWORD *)(a1 + 48),
          &v154,
          0,
          *(_QWORD *)(a1 + 112));
        *(_QWORD *)(a1 + 128) = 0;
        *(_QWORD *)(a1 + 136) = a1 + 128;
      }
    }
    v83 = *(_QWORD *)(a1 + 112);
    if ( v83 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(a1 + 16) + 104LL))(*(_QWORD *)(a1 + 8));
    v84 = v149;
    v98 = *(_BYTE *)(a1 + 2) & 0xFD;
    LOBYTE(v84) = 2 * v149;
    *(_QWORD *)(a1 + 112) = v45;
    LOBYTE(v84) = v98 | v84;
    *(_BYTE *)(a1 + 2) = v84;
  }
  if ( ((*(_BYTE *)(a1 + 2) & 2) != 0) != v149 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v84, v83, v85);
  v40 = v147;
LABEL_226:
  if ( (*(_BYTE *)(p_Blink + 64) & 0x10) != 0 && v40 )
  {
    v99 = *(_QWORD *)(a1 + 56);
    v151 = KeGetCurrentProcessorNumberEx(0);
    v102 = v24;
    v103 = v153;
    if ( v153 )
      v102 = v153;
    v104 = *(_BYTE *)(v102 + 16);
    if ( (*(_BYTE *)(p_Blink + 64) & 0x10) == 0 )
    {
LABEL_231:
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v102, v100, v101);
      v103 = v153;
      goto LABEL_232;
    }
    while ( 1 )
    {
LABEL_232:
      LOBYTE(v101) = 1;
      if ( !(unsigned __int8)SlbNatLibTranslate((_DWORD)qword_1400273D8, p_Blink, v101, 0, v24, v103, v99) )
      {
        v108 = 9;
        goto LABEL_245;
      }
      v99 = *(_QWORD *)v99;
      if ( !v99 )
        break;
      if ( v153 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v106, v105, v107);
      v24 = *((_QWORD *)qword_1400273D8 + 169) + 232LL * v151;
      if ( **(_QWORD **)(v99 + 8) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v106, v105, v107);
      if ( !(unsigned __int8)WinNatParseNb(*(PNET_BUFFER *)(v99 + 8)) || !v24 )
      {
        v108 = 1;
        goto LABEL_245;
      }
      v103 = v153;
      if ( !*(_WORD *)(v24 + 224) )
        goto LABEL_231;
    }
    v108 = 0;
LABEL_245:
    if ( *(_QWORD *)(a1 + 80) == p_Blink )
      *(_QWORD *)(a1 + 80) = 0;
    v109 = *(_QWORD **)(a1 + 56);
    if ( v99 )
    {
      SlbNatIpsDropDatagram(a1, v109, v104, v108);
    }
    else
    {
      if ( v109 )
      {
        v110 = v151;
        v111 = 136LL * v151;
        do
        {
          v109 = (_QWORD *)*v109;
          v112 = 136 * v110;
          ++*(_QWORD *)((char *)qword_140027B68 + v111 + 88);
          if ( v104 == 6 )
          {
            ++*(_DWORD *)((char *)qword_140027B68 + v112 + 8);
          }
          else if ( v104 == 17 )
          {
            ++*(_DWORD *)((char *)qword_140027B68 + v112 + 32);
          }
          else
          {
            ++*(_DWORD *)((char *)qword_140027B68 + v112 + 56);
          }
          v113 = *(_BYTE *)(p_Blink + 64);
          if ( (v113 & 4) != 0 )
          {
            v114 = 136 * v110;
            if ( (v113 & 8) != 0 )
              ++*(_QWORD *)((char *)qword_140027B68 + v114 + 120);
            else
              ++*(_QWORD *)((char *)qword_140027B68 + v114 + 128);
          }
        }
        while ( v109 );
      }
      *(_QWORD *)(a1 + 64) = p_Blink;
      SlbNatIpsHandleIncomingUnicastDatagram(a1);
      *(_QWORD *)(a1 + 64) = 0;
    }
    v86 = p_Blink - 8;
    v115 = _InterlockedExchangeAdd64((volatile signed __int64 *)(p_Blink - 8), 0xFFFFFFFFFFFFFFFFuLL);
    v120 = v115 <= 1;
    v116 = v115 - 1;
    if ( !v120 )
      return;
    if ( !v116 )
    {
LABEL_196:
      if ( *(_QWORD *)(v86 + 80) )
        WinNatCleanupBinding();
      v89 = *(void (__fastcall **)(__int64))(v86 + 48);
      if ( v89 )
        v89(p_Blink);
      v90 = HIDWORD(KeGetPcr()[1].LockArray);
      v91 = (__int64 *)(*(_QWORD *)(v86 + 288) + 8LL);
      if ( *(_BYTE *)(v86 + 256) )
        v91 = *(__int64 **)(v86 + 288);
      v92 = *v91;
      v93 = v92 + ((unsigned __int64)(unsigned int)(v90 + 1) << 7);
      if ( !*(_BYTE *)(v93 + 176) )
        PplpLazyInitializeLookasideList(v92, v93 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v93 + 64), (PVOID)v86);
      return;
    }
LABEL_264:
    __fastfail(0xEu);
  }
  v117 = v24;
  v118 = *(__int64 **)(a1 + 56);
  if ( v153 )
    v117 = v153;
  v119 = *(unsigned __int8 *)(v117 + 150);
  if ( (unsigned __int8)v119 <= 1u )
    goto LABEL_351;
  if ( *(_DWORD *)(a1 + 120) >= *(_DWORD *)(v118[1] + 24) || (*(_BYTE *)(v117 + 212) & 4) == 0 )
    goto LABEL_275;
  if ( v148 == 6 )
  {
    v120 = *((_WORD *)v118 + 160) <= 1u;
    goto LABEL_274;
  }
  if ( v148 == 17 )
  {
    v120 = *((_WORD *)v118 + 140) <= 1u;
LABEL_274:
    if ( !v120 )
      goto LABEL_275;
LABEL_351:
    if ( (xmmword_1400272E0 & 4) != 0 )
      WPP_SF_dddd(
        v118[1],
        v117,
        v119,
        *(unsigned __int8 *)(v117 + 150),
        *(_DWORD *)(a1 + 120),
        *(_DWORD *)(v118[1] + 24),
        v157);
    SlbNatIpsSendICMPError(p_Blink, a1, v24);
    return;
  }
LABEL_275:
  v121 = *(_QWORD *)(a1 + 40);
  LODWORD(HashTable) = 0;
  if ( v121 )
  {
    if ( (BYTE8(xmmword_1400272E0) & 4) != 0 )
      WPP_SF_d(1282, 22, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, *(unsigned __int16 *)(v121 + 32));
    v122 = (unsigned __int16)(*(_WORD *)(v121 + 32) - 243) <= 1u;
  }
  else
  {
    v122 = 0;
  }
  v149 = v122;
  while ( 1 )
  {
    v150 = 0;
    v123 = (__int64 **)v118;
    v124 = v118;
    v125 = v118;
    v118 = (__int64 *)*v118;
    v54 = ((_DWORD)v123[17] & 0x20000000) == 0;
    *v124 = 0;
    if ( v54 || (*(_BYTE *)(a1 + 2) & 2) != 0 )
    {
      v54 = (*(_BYTE *)(a1 + 2) & 2) == 0;
      v128 = v125;
      v150 = v125;
      if ( v54 )
      {
        v129 = *((_DWORD *)v125 + 36);
        if ( (v129 & 0x18) != 0 && (v129 & 0x100) != 0 )
        {
          SlbNatFillPacketChecksum(v125, v24);
          v128 = v150;
        }
        *((_DWORD *)v128 + 76) &= 0xFF000000;
        *((_DWORD *)v150 + 44) &= 0xFFFF000F;
        v150[18] = 0;
      }
      else
      {
        v125[34] = 0;
      }
      goto LABEL_301;
    }
    if ( !gAccount )
    {
      if ( v122 )
      {
        v126 = 14;
        goto LABEL_288;
      }
      goto LABEL_287;
    }
    if ( !v122 )
    {
      _InterlockedIncrement64(&gNBLClone);
LABEL_287:
      v126 = 0;
      goto LABEL_288;
    }
    _InterlockedIncrement64(&gNBLDeepClone);
    v126 = 14;
LABEL_288:
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *, __int64 (__fastcall *)(), bool, int, _DWORD, __int64 **))(*(_QWORD *)(a1 + 16) + 56LL))(
      *(_QWORD *)(a1 + 8),
      *(_QWORD *)(a1 + 48),
      v125,
      SlbNatIpsClientNotifyEvent,
      v122,
      v126,
      0,
      &v150);
    if ( (v125[18] & 0x188) == 0x188 )
      SlbNatFillPacketChecksum(v150, v24);
    v127 = v150;
    if ( v150 )
      goto LABEL_302;
    if ( !gAccount )
      goto LABEL_341;
    _InterlockedIncrement64(&gNBLCloneFail);
LABEL_301:
    v127 = v150;
    if ( !v150 )
    {
LABEL_341:
      v140 = 8;
      LODWORD(HashTable) = 8;
LABEL_343:
      v136 = v148;
      SlbNatIpsDropDatagram(a1, v125, v148, v140);
      goto LABEL_331;
    }
LABEL_302:
    v130 = v147;
    v127[26] = *((unsigned int *)v125 + 52);
    v150[22] = v125[22];
    if ( !(unsigned __int8)SlbNatLibTranslate((_DWORD)qword_1400273D8, p_Blink, v130, 0, v24, v153, (__int64)v150) )
    {
      if ( v150 != v125 )
      {
        **(_QWORD **)(a1 + 152) = v150;
        *(_QWORD *)(a1 + 152) = v150;
      }
      v140 = 9;
      v150 = 0;
      LODWORD(HashTable) = 9;
      goto LABEL_343;
    }
    v131 = v147;
    v132 = v148;
    **(_QWORD **)(a1 + 136) = v150;
    *(_QWORD *)(a1 + 136) = v150;
    v133 = v151;
    *(_BYTE *)(a1 + 2) ^= (v131 ^ *(_BYTE *)(a1 + 2)) & 1;
    v134 = 136 * v133;
    if ( (_BYTE)v131 )
    {
      ++*(_QWORD *)((char *)qword_140027B68 + v134 + 88);
      if ( (_BYTE)v132 == 6 )
      {
        ++*(_DWORD *)((char *)qword_140027B68 + v134 + 8);
      }
      else if ( (_BYTE)v132 == 17 )
      {
        ++*(_DWORD *)((char *)qword_140027B68 + v134 + 32);
      }
      else
      {
        ++*(_DWORD *)((char *)qword_140027B68 + v134 + 56);
      }
      v135 = *(_BYTE *)(p_Blink + 64);
      if ( (v135 & 4) != 0 )
      {
        if ( (v135 & 8) != 0 )
          ++*(_QWORD *)((char *)qword_140027B68 + v134 + 120);
        else
          ++*(_QWORD *)((char *)qword_140027B68 + v134 + 128);
      }
    }
    else
    {
      ++*(_QWORD *)((char *)qword_140027B68 + v134 + 96);
      if ( (_BYTE)v132 == 6 )
      {
        ++*(_DWORD *)((char *)qword_140027B68 + v134 + 12);
      }
      else if ( (_BYTE)v132 == 17 )
      {
        ++*(_DWORD *)((char *)qword_140027B68 + v134 + 36);
      }
      else
      {
        ++*(_DWORD *)((char *)qword_140027B68 + v134 + 60);
      }
    }
    if ( byte_140027B80 )
      SlbNatLibClampMssOnIpPkt(a1, p_Blink, v131, v24, *(_QWORD *)(*(_QWORD *)(a1 + 56) + 8LL));
    if ( !v150 )
    {
      v140 = (unsigned int)HashTable;
      goto LABEL_343;
    }
    if ( v150 != v125 )
    {
      if ( v149 )
      {
        **(_QWORD **)(a1 + 152) = v125;
        *(_QWORD *)(a1 + 152) = v125;
      }
      else
      {
        *((_QWORD *)&v154 + 1) = v125;
        v155 = 0;
        if ( gAccount && v123 )
        {
          do
          {
            _InterlockedIncrement64(&gNBLRelease);
            v123 = (__int64 **)*v123;
          }
          while ( v123 );
        }
        (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 64LL))(*(_QWORD *)(a1 + 8), &v154);
      }
      if ( (*(_BYTE *)(a1 + 2) & 2) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v134, v132, v131);
    }
    v136 = v148;
LABEL_331:
    if ( !v118 )
      goto LABEL_347;
    if ( v153 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v134, v132, v131);
    v137 = SlbNatLibParseNBL(qword_1400273D8, v118, v151);
    v24 = v137;
    if ( !v137 )
      break;
    if ( !v150 )
    {
      v141 = (unsigned int)HashTable;
      goto LABEL_346;
    }
    v122 = v149;
    if ( !*(_WORD *)(v137 + 224) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v149, v138, v139);
      v122 = v149;
    }
  }
  v141 = 1;
LABEL_346:
  SlbNatIpsDropDatagram(a1, v118, v136, v141);
LABEL_347:
  v142 = *(_QWORD *)(a1 + 80);
  if ( v142 != p_Blink )
  {
    if ( v142 )
      WinNatLibDereferenceSession(v142 - 8);
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
0x140002131  mov     rcx, cs:qword_1400273D8
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
0x140002259  mov     rcx, cs:qword_140027B68
0x140002260  imul    rdx, r15, 88h
0x140002267  mov     eax, r14d
0x14000226a  add     [rcx+rdx+68h], rax
0x14000226f  mov     rax, cs:qword_140027B68
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
0x1400022e6  test    byte ptr cs:xmmword_1400272E0, 4
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
0x140002398  cmp     byte ptr cs:dword_140027B78+2, r12b
0x14000239f  jz      loc_14000373F
0x1400023a5  mov     [rbp+57h+var_BF], r14b
0x1400023a9  cmp     [rdi+0D5h], r12b
0x1400023b0  jz      short loc_140002424
0x1400023b2  mov     rcx, cs:qword_1400273D8
0x1400023b9  mov     r9d, r15d
0x1400023bc  mov     r8, rsi
0x1400023bf  mov     rdx, rdi
0x1400023c2  call    SlbNatLibParseICMPInnerPacket
0x1400023c7  mov     rsi, rax
0x1400023ca  test    rax, rax
0x1400023cd  jnz     short loc_140002401
0x1400023cf  test    byte ptr cs:xmmword_1400272E0, 4
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
0x140002454  cmp     cs:dword_1400274E8, r12d
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
0x1400024b7  test    byte ptr cs:xmmword_1400272E0, 4
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
0x140002541  test    byte ptr cs:xmmword_1400272E0, 4
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
0x140002586  test    byte ptr cs:xmmword_1400272E0, 4
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
0x1400025bd  mov     rcx, cs:qword_1400273D8
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
