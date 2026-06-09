# SlbNatIpsHandleIncomingUnicastDatagram

- ea: `0x1400020e0`
- end: `0x14000381c`
- name: `SlbNatIpsHandleIncomingUnicastDatagram`
- size: `5948`
- prototype: ``
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
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rsi
  int v7; // r15d
  __int64 v8; // rdi
  _QWORD *v9; // rcx
  char v10; // al
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  _QWORD *v15; // rsi
  _QWORD *v16; // rdi
  __int64 v17; // r15
  unsigned int v18; // r14d
  _QWORD *v19; // rax
  __int64 v20; // rdx
  unsigned __int64 v21; // r14
  int v22; // eax
  _QWORD *v23; // rax
  __int64 v24; // r13
  __int64 v25; // rax
  __int64 v26; // rsi
  _WORD *v27; // r15
  _WORD *v28; // rdi
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 p_Blink; // rdi
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 SessionEntry; // rax
  unsigned __int8 v42; // r15
  __int64 v43; // rax
  unsigned __int8 v44; // cl
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rdx
  int v48; // ecx
  __int64 v49; // rcx
  __int64 v50; // r14
  unsigned __int8 v51; // r15
  char *v52; // r13
  KIRQL v53; // al
  unsigned int LockArray_high; // ecx
  __int64 v55; // rax
  __int64 v56; // rcx
  volatile signed __int32 *v57; // r13
  _WORD *v58; // rdx
  bool v59; // zf
  volatile signed __int64 *v60; // r13
  __int64 v61; // r8
  int v62; // edi
  int v63; // eax
  _WORD *v64; // rdx
  bool v65; // zf
  unsigned int v66; // eax
  int v67; // edi
  int v68; // eax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY NextEntryHashTable; // rdi
  _QWORD *v70; // rax
  _QWORD *v71; // rax
  _DWORD *v72; // r13
  __int16 v73; // ax
  bool v74; // di
  _BYTE *v75; // r13
  PRTL_DYNAMIC_HASH_TABLE_ENTRY SessionForExternalPacket; // rax
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 v80; // r9
  bool v81; // r13
  __int64 v82; // rcx
  unsigned __int8 v83; // al
  int v84; // eax
  __int128 v85; // xmm0
  _QWORD *v86; // rax
  __int64 v87; // rax
  int v88; // eax
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // r8
  __int64 v92; // r9
  __int64 v93; // rbx
  signed __int64 v94; // rax
  signed __int64 v95; // rax
  __int64 v96; // rcx
  void (__fastcall *v97)(__int64); // rax
  int v98; // eax
  __int64 *v99; // rcx
  __int64 v100; // rcx
  __int64 v101; // rdi
  __int64 v102; // rax
  int v103; // r9d
  _QWORD *v104; // rcx
  _QWORD *v105; // rax
  char v106; // al
  __int64 v107; // r14
  __int64 v108; // rdx
  __int64 v109; // r8
  __int64 v110; // r9
  __int64 v111; // rcx
  __int64 v112; // rax
  unsigned __int8 v113; // r15
  __int64 v114; // rdx
  __int64 v115; // rcx
  __int64 v116; // r8
  __int64 v117; // r9
  unsigned int v118; // eax
  _QWORD *v119; // rdx
  __int64 v120; // r8
  __int64 v121; // r9
  __int64 v122; // rcx
  char v123; // al
  __int64 v124; // rcx
  signed __int64 v125; // rax
  signed __int64 v126; // rax
  __int64 v127; // rdx
  __int64 *v128; // r13
  __int64 v129; // r8
  bool v130; // cc
  __int64 v131; // r14
  bool v132; // cl
  __int64 **v133; // r15
  _QWORD *v134; // rax
  __int64 *v135; // r14
  int v136; // edx
  __int64 *v137; // rcx
  __int64 *v138; // rcx
  int v139; // eax
  __int64 v140; // r8
  __int64 v141; // r9
  __int64 v142; // r8
  __int64 v143; // rdx
  __int64 v144; // rax
  __int64 v145; // rcx
  char v146; // al
  unsigned __int8 v147; // r15
  __int64 v148; // rax
  __int64 v149; // rdx
  __int64 v150; // r8
  __int64 v151; // r9
  unsigned int v152; // eax
  __int64 v153; // r9
  __int64 v154; // rcx
  BOOL v155; // edx
  int v156; // eax
  _QWORD *v157; // rax
  _DWORD *v158; // [rsp+30h] [rbp-89h]
  unsigned __int8 v159; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int8 v160; // [rsp+51h] [rbp-68h]
  unsigned __int8 v161; // [rsp+52h] [rbp-67h]
  __int64 *v162; // [rsp+58h] [rbp-61h] BYREF
  ULONG v163; // [rsp+60h] [rbp-59h]
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+68h] [rbp-51h]
  __int64 v165; // [rsp+70h] [rbp-49h]
  __int128 v166; // [rsp+78h] [rbp-41h] BYREF
  _QWORD *v167; // [rsp+88h] [rbp-31h]
  __int64 v168; // [rsp+90h] [rbp-29h]
  __int128 v169; // [rsp+98h] [rbp-21h] BYREF
  __int128 v170; // [rsp+A8h] [rbp-11h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B8h] [rbp-1h] BYREF
  __int128 v172; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v173; // [rsp+E0h] [rbp+27h]

  LOBYTE(v167) = 0;
  v168 = *(_QWORD *)(a1 + 40);
  v166 = 0;
  v169 = 0;
  v170 = 0;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v6 = *(_QWORD *)(a1 + 56);
  v7 = CurrentProcessorNumber;
  v163 = CurrentProcessorNumber;
  v8 = *((_QWORD *)qword_1400263D8 + 169) + 232LL * CurrentProcessorNumber;
  v9 = *(_QWORD **)(v6 + 8);
  if ( *v9 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v9, v3, v4, v5);
  v10 = WinNatParseNb(*(PNET_BUFFER *)(v6 + 8));
  v15 = *(_QWORD **)(a1 + 56);
  if ( !v10 || !v8 )
  {
    v16 = *(_QWORD **)(a1 + 56);
    v17 = KeGetCurrentProcessorNumberEx(0);
    v18 = 1;
    v172 = 0;
    LOBYTE(v173) = 0;
    if ( Microsoft_Windows_WinNatEnableBits < 0 && *(_WORD *)a1 == 2 )
      SlbNatIpsLogIPv4Datagram(
        *(_DWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32),
        *(_QWORD *)(a1 + 40),
        0,
        0,
        (__int64)v15,
        1,
        1);
    v19 = (_QWORD *)*v15;
    if ( *v15 )
    {
      do
      {
        v19 = (_QWORD *)*v19;
        ++v18;
      }
      while ( v19 );
    }
    LOBYTE(v172) = 0;
    *((_QWORD *)&v172 + 1) = v15;
    v173 = 0;
    if ( gAccount && v15 )
    {
      do
      {
        _InterlockedIncrement64(&gNBLDrop);
        v16 = (_QWORD *)*v16;
      }
      while ( v16 );
    }
    (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 32LL))(
      *(_QWORD *)(a1 + 8),
      *(_QWORD *)(a1 + 48),
      &v172);
    v20 = 136 * v17;
    *(_QWORD *)((char *)qword_140026B68 + v20 + 104) += v18;
    *(_DWORD *)((char *)qword_140026B68 + v20 + 64) += v18;
    return;
  }
  LOBYTE(v166) = 0;
  *((_QWORD *)&v166 + 1) = v15;
  v167 = v15;
  v59 = (*(_BYTE *)(v8 + 212) & 1) == 0;
  v21 = *(unsigned __int8 *)(v8 + 16);
  v159 = 0;
  if ( !v59 )
  {
    v22 = *(_DWORD *)(v8 + 220);
    LOBYTE(v12) = *(_DWORD *)(a1 + 160) == v22;
    v59 = *(_WORD *)(v8 + 224) == 0;
    v159 = v12;
    if ( v59 )
      *(_DWORD *)(a1 + 160) = v22;
    else
      v159 = v12;
  }
  if ( (*(_BYTE *)(v8 + 212) & 1) != 0 )
  {
    if ( *(_DWORD *)(a1 + 160) != *(_DWORD *)(v8 + 220) )
    {
      *(_DWORD *)(a1 + 160) = 0;
      if ( (xmmword_1400262E0 & 4) != 0 )
        WPP_SF_d(1026, 31, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, *(unsigned int *)(v8 + 220));
      if ( gAccount )
      {
        v23 = (_QWORD *)*((_QWORD *)&v166 + 1);
        if ( *((_QWORD *)&v166 + 1) )
        {
          do
          {
            _InterlockedIncrement64(&gNBLReturn);
            v23 = (_QWORD *)*v23;
          }
          while ( v23 );
        }
      }
      (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 40LL))(
        *(_QWORD *)(a1 + 8),
        *(_QWORD *)(a1 + 48),
        &v166);
      return;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 160) = 0;
  }
  if ( (*(_BYTE *)(v8 + 212) & 3) == 1 )
    *(_DWORD *)(a1 + 160) = 0;
  v24 = 0x400000000020042LL;
  if ( (unsigned __int8)v21 > 0x3Au
    || !_bittest64(&v24, v21)
    || (*(_BYTE *)(v8 + 212) & 1) != 0 && !BYTE2(dword_140026B78) )
  {
    if ( *(_QWORD *)(a1 + 64) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v12, v11, v13, v14);
    if ( (byte_140026BED & 4) != 0 && *(_WORD *)a1 == 2 )
    {
      v155 = (unsigned __int8)v21 > 0x3Au || !_bittest64(&v24, v21);
      v156 = 19;
      if ( !v155 )
        v156 = 2;
      SlbNatIpsLogIPv4Datagram(
        *(_DWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32),
        *(_QWORD *)(a1 + 40),
        0,
        0,
        *(_QWORD *)(a1 + 56),
        2,
        v156);
    }
    if ( gAccount )
    {
      v157 = (_QWORD *)*((_QWORD *)&v166 + 1);
      if ( *((_QWORD *)&v166 + 1) )
      {
        do
        {
          _InterlockedIncrement64(&gNBLReturn);
          v157 = (_QWORD *)*v157;
        }
        while ( v157 );
      }
    }
    goto LABEL_368;
  }
  v160 = v21;
  if ( *(_BYTE *)(v8 + 213) )
  {
    v25 = SlbNatLibParseICMPInnerPacket((__int64)qword_1400263D8, v8, (__int64)v15, v7);
    v26 = v25;
    if ( !v25 )
    {
      if ( (xmmword_1400262E0 & 4) != 0 )
        WPP_SF_(1026, 32, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids);
      goto LABEL_37;
    }
    LOBYTE(v21) = *(_BYTE *)(v25 + 16);
    v27 = (_WORD *)(v25 + 152);
    v165 = v8;
    *(_QWORD *)&v172 = v25 + 180;
    v28 = (_WORD *)(v25 + 180);
  }
  else
  {
    v26 = v8;
    v165 = 0;
    v27 = (_WORD *)(v8 + 180);
    v28 = (_WORD *)(v8 + 152);
    *(_QWORD *)&v172 = v28;
  }
  v29 = *(_QWORD *)(a1 + 40);
  v161 = 0;
  if ( v29 )
  {
    if ( dword_1400264E8 <= 0 )
    {
      if ( *(_DWORD *)(v29 + 40) )
        goto LABEL_43;
    }
    else if ( (*(_DWORD *)(v29 + 24) & 4) == 0 )
    {
LABEL_43:
      v30 = *(_QWORD *)(a1 + 80);
      if ( v30 && (unsigned __int8)WinNatIsMatchingSession(1, (_DWORD)v28, (_DWORD)v27, 0, v21, v30 + 184, v159) )
      {
        p_Blink = *(_QWORD *)(a1 + 80);
        if ( (*(_BYTE *)(v26 + 212) & 1) != 0 && (xmmword_1400262E0 & 4) != 0 )
          WPP_SF_dq(v32, 35, v33, *(unsigned int *)(v26 + 220), *(_QWORD *)(a1 + 80));
        if ( !p_Blink )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v32, v31, v33, v34);
LABEL_175:
        v87 = *(_QWORD *)(a1 + 112);
        v44 = 0;
        v159 = 0;
        if ( v87 == *(_QWORD *)(p_Blink + 32) && v87 )
          goto LABEL_226;
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
        v47 = *(_QWORD *)(p_Blink + 32);
        if ( v47 )
        {
          (*(void (__fastcall **)(_QWORD, __int64, __int128 *))(*(_QWORD *)(a1 + 16) + 112LL))(
            *(_QWORD *)(a1 + 8),
            v47,
            &v169);
          *(_DWORD *)(a1 + 120) = DWORD1(v170);
          v88 = v170;
        }
        else
        {
          v88 = 0;
          LODWORD(v170) = 0;
        }
        if ( *(_QWORD *)(p_Blink + 32) && *(_DWORD *)(p_Blink + 16) == v88 )
        {
          v51 = v160;
        }
        else
        {
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
          v51 = v160;
          if ( !(unsigned __int8)SlbNatIpsRefreshInternalNexthop(a1, v160, p_Blink) )
            return;
          KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
        }
        v50 = *(_QWORD *)(p_Blink + 32);
        goto LABEL_186;
      }
      if ( v165 && (*(_BYTE *)(v26 + 212) & 1) == 0 )
      {
        v162 = (__int64 *)qword_1400263D8;
        v52 = (char *)qword_1400263D8 + 192;
        v53 = KfRaiseIrql(2u);
        LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
        v159 = v53;
        v55 = LockArray_high;
        v56 = LockArray_high & *((_DWORD *)v52 + 2);
        v168 = v55;
        v57 = (volatile signed __int32 *)&v52[64 * v56 + 64];
        memset(&LockHandle, 0, sizeof(LockHandle));
        _InterlockedIncrement(v57);
        if ( !KeTestSpinLock((PKSPIN_LOCK)v162 + 24) )
        {
          _InterlockedDecrement(v57);
          KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v162 + 24, &LockHandle);
          _InterlockedIncrement(v57);
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        }
        v58 = v28 + 2;
        v59 = *v28 == 2;
        memset(&LockHandle, 0, sizeof(LockHandle));
        v60 = 0;
        if ( !v59 )
          v58 = v28 + 4;
        v61 = 4;
        if ( !v59 )
          v61 = 16;
        v62 = RtlComputeToeplitzHash(v162 + 67, v58, v61, 0);
        v63 = RtlComputeToeplitzHash(v162 + 67, v172 + 2, 2, 0);
        v64 = v27 + 2;
        v65 = *v27 == 2;
        LODWORD(HashTable) = v62 ^ v63;
        if ( !v65 )
          v64 = v27 + 4;
        v66 = 4;
        if ( !v65 )
          v66 = 16;
        v67 = (unsigned int)HashTable ^ RtlComputeToeplitzHash(v162 + 67, v64, v66, 0);
        v68 = RtlComputeToeplitzHash(v162 + 67, v27 + 1, 2, 0);
        HashTable = (PRTL_DYNAMIC_HASH_TABLE)v162[65];
        LockHandle.LockQueue = 0;
        NextEntryHashTable = RtlLookupEntryHashTable(
                               HashTable,
                               v67 ^ v68 | 0x80000000,
                               (PRTL_DYNAMIC_HASH_TABLE_CONTEXT)&LockHandle);
        if ( NextEntryHashTable )
        {
          while ( !(unsigned __int8)WinNatIsMatchingSession(
                                      1,
                                      v172,
                                      (_DWORD)v27,
                                      0,
                                      v21,
                                      (__int64)NextEntryHashTable,
                                      0) )
          {
            v60 = 0;
            NextEntryHashTable = RtlGetNextEntryHashTable(HashTable, (PRTL_DYNAMIC_HASH_TABLE_CONTEXT)&LockHandle);
            if ( !NextEntryHashTable )
              goto LABEL_124;
          }
          v60 = (volatile signed __int64 *)&NextEntryHashTable[-8];
          if ( NextEntryHashTable != (PRTL_DYNAMIC_HASH_TABLE_ENTRY)192 && _InterlockedIncrement64(v60) <= 1 )
            __fastfail(0xEu);
        }
LABEL_124:
        _InterlockedDecrement((volatile signed __int32 *)&v162[8 * ((unsigned int)v168 & (_DWORD)v162[25]) + 32]);
        KeLowerIrql(v159);
        if ( !v60 || (p_Blink = (__int64)(v60 + 1), v60 == (volatile signed __int64 *)-8LL) )
        {
          if ( gAccount )
          {
            v70 = (_QWORD *)*((_QWORD *)&v166 + 1);
            if ( *((_QWORD *)&v166 + 1) )
            {
              do
              {
                _InterlockedIncrement64(&gNBLReturn);
                v70 = (_QWORD *)*v70;
              }
              while ( v70 );
            }
          }
          goto LABEL_368;
        }
        goto LABEL_175;
      }
      v159 = 0;
      if ( (*(_BYTE *)(v26 + 212) & 1) != 0 && *(_WORD *)(v26 + 224) )
      {
        if ( (xmmword_1400262E0 & 4) != 0 )
          WPP_SF_d(1026, 36, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, *(unsigned int *)(v26 + 220));
        if ( gAccount )
        {
          v71 = (_QWORD *)*((_QWORD *)&v166 + 1);
          if ( *((_QWORD *)&v166 + 1) )
          {
            do
            {
              _InterlockedIncrement64(&gNBLReturn);
              v71 = (_QWORD *)*v71;
            }
            while ( v71 );
          }
        }
        goto LABEL_368;
      }
      v72 = 0;
      v162 = 0;
      if ( v168 )
      {
        v72 = (_DWORD *)(v168 + 36);
        v162 = (__int64 *)(v168 + 36);
      }
      if ( (_BYTE)v21 != *(_BYTE *)(a1 + 104) )
        goto LABEL_146;
      v73 = *v27;
      if ( *v27 != *(_WORD *)(a1 + 88) )
        goto LABEL_146;
      if ( v73 == 2 )
      {
        if ( v27[1] != *(_WORD *)(a1 + 90) )
          goto LABEL_146;
        v82 = 0;
        while ( 1 )
        {
          v83 = *((_BYTE *)v27 + v82++ + 4);
          if ( v83 != *((_BYTE *)v27 + v82 + 3) )
            break;
          if ( v82 == 4 )
          {
            v84 = 0;
            goto LABEL_160;
          }
        }
        v84 = v83 < *((_BYTE *)v27 + v82 + 3) ? -1 : 1;
LABEL_160:
        if ( v84 )
          goto LABEL_146;
      }
      else if ( v73 != 23 || v27[1] != *(_WORD *)(a1 + 90) || memcmp(v27 + 4, v27 + 4, 0x10u) )
      {
LABEL_146:
        v74 = dword_1400264E8 > 0;
        v158 = v72;
        v75 = (_BYTE *)v172;
        LODWORD(HashTable) = *(_DWORD *)(a1 + 32);
        v168 = (__int64)qword_1400263D8;
        SessionForExternalPacket = WinNatGetSessionForExternalPacket(
                                     (__int64)qword_1400263D8,
                                     (_BYTE *)v172,
                                     v27,
                                     0,
                                     v21,
                                     &v159,
                                     v158,
                                     (int)HashTable);
        if ( v74 && !SessionForExternalPacket )
        {
          v172 = *(_OWORD *)v27;
          DWORD1(v172) = 0;
          SessionForExternalPacket = WinNatGetSessionForExternalPacket(
                                       v168,
                                       v75,
                                       &v172,
                                       (__int64)v27,
                                       v21,
                                       &v159,
                                       v162,
                                       (int)HashTable);
        }
        p_Blink = (__int64)&SessionForExternalPacket->Linkage.Blink;
        if ( !SessionForExternalPacket )
          p_Blink = 0;
        v81 = p_Blink == 0;
        if ( p_Blink )
        {
          if ( (*(_BYTE *)(p_Blink + 64) & 2) == 0 )
          {
            if ( v165 )
              MicrosoftTelemetryAssertTriggeredNoArgsKM(v78, v77, v79, v80);
            SlbNatIpsCheckHairpinning(p_Blink, 0, a1, v26);
          }
          goto LABEL_175;
        }
        if ( v159 )
        {
          SlbNatIpsDropDatagram(a1, *(_QWORD *)(a1 + 56), v160, 6);
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
        if ( v81 )
        {
          v85 = *(_OWORD *)v27;
          *(_BYTE *)(a1 + 104) = v21;
          *(_OWORD *)(a1 + 88) = v85;
        }
        if ( gAccount )
        {
          v86 = (_QWORD *)*((_QWORD *)&v166 + 1);
          if ( *((_QWORD *)&v166 + 1) )
          {
            do
            {
              _InterlockedIncrement64(&gNBLReturn);
              v86 = (_QWORD *)*v86;
            }
            while ( v86 );
          }
        }
        goto LABEL_368;
      }
      v81 = 0;
      goto LABEL_162;
    }
  }
  if ( *(_QWORD *)(a1 + 64) )
    goto LABEL_43;
  v36 = *(_QWORD *)(a1 + 80);
  if ( v36
    && (unsigned __int8)WinNatIsMatchingSession(*(_DWORD *)(a1 + 24), (_DWORD)v28, (_DWORD)v27, 1, v21, v36 + 160, v159) )
  {
    p_Blink = *(_QWORD *)(a1 + 80);
    if ( (*(_BYTE *)(v26 + 212) & 1) != 0 && (xmmword_1400262E0 & 4) != 0 )
      WPP_SF_dq(v38, 33, v39, *(unsigned int *)(v26 + 220), *(_QWORD *)(a1 + 80));
    if ( !p_Blink )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v38, v37, v39, v40);
  }
  else
  {
    if ( (*(_BYTE *)(v26 + 212) & 1) != 0 && *(_WORD *)(v26 + 224) )
    {
      if ( (xmmword_1400262E0 & 4) != 0 )
        WPP_SF_d(1026, 34, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, *(unsigned int *)(v26 + 220));
      goto LABEL_37;
    }
    SessionEntry = WinNatFindSessionEntry(
                     (int)qword_1400263D8 + 128,
                     *(_DWORD *)(a1 + 24),
                     (_DWORD)v28,
                     (_DWORD)v27,
                     v21,
                     1);
    p_Blink = SessionEntry + 8;
    if ( !SessionEntry )
      p_Blink = 0;
    if ( !p_Blink )
    {
      if ( v165 )
      {
LABEL_37:
        SlbNatAccountChain(&v166, 1);
LABEL_368:
        (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 40LL))(
          *(_QWORD *)(a1 + 8),
          *(_QWORD *)(a1 + 48),
          &v166);
        return;
      }
      p_Blink = SlbNatIpsCreateSessionForInternalDatagram(a1, v26, v163);
      if ( !p_Blink )
        return;
    }
  }
  v42 = v160;
  if ( *(_DWORD *)(a1 + 24) != 1
    && *(_DWORD *)(p_Blink + 8) != *(_DWORD *)(a1 + 28)
    && !(unsigned __int8)SlbNatIpsRefreshInternalNoRouteState(a1, v160, p_Blink) )
  {
    return;
  }
  v43 = *(_QWORD *)(a1 + 112);
  v44 = 1;
  v159 = 1;
  if ( v43 == *(_QWORD *)(p_Blink + 24) && v43 )
    goto LABEL_226;
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
  v47 = *(_QWORD *)(p_Blink + 24);
  if ( v47 )
  {
    (*(void (__fastcall **)(_QWORD, __int64, __int128 *))(*(_QWORD *)(a1 + 16) + 112LL))(
      *(_QWORD *)(a1 + 8),
      v47,
      &v169);
    v48 = v170;
    *(_DWORD *)(a1 + 120) = DWORD1(v170);
  }
  else
  {
    v48 = 0;
    LODWORD(v170) = 0;
  }
  if ( *(_DWORD *)(p_Blink + 4) != dword_140026840 || !*(_QWORD *)(p_Blink + 24) || *(_DWORD *)(p_Blink + 12) != v48 )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
    if ( !(unsigned __int8)SlbNatIpsRefreshExternalNexthop(a1, v42, p_Blink) )
      return;
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
  }
  v49 = *(unsigned __int8 *)(p_Blink + 64);
  if ( (v49 & 1) == 0 )
    goto LABEL_102;
  v47 = (unsigned __int8)v49;
  LOBYTE(v47) = (unsigned __int8)v49 >> 4;
  if ( dword_1400264E8 <= 0 || (v49 & 0x30) != 0 )
  {
    LOBYTE(v45) = 0;
    v161 = 0;
  }
  else
  {
    v45 = 1;
    v161 = 1;
  }
  LOBYTE(v49) = (unsigned __int8)v49 >> 5;
  if ( (((unsigned __int8)v47 | (unsigned __int8)v49) & 1) == 0 && !(_BYTE)v45 )
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
    SlbNatAccountChain(&v166, 1);
    (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 40LL))(
      *(_QWORD *)(a1 + 8),
      *(_QWORD *)(a1 + 48),
      &v166);
    if ( *(_QWORD *)(a1 + 80) == p_Blink )
      *(_QWORD *)(a1 + 80) = 0;
    WinNatLibDereferenceSession(p_Blink - 8);
    return;
  }
  if ( (v49 & 1) != 0 )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
    if ( !(unsigned __int8)SlbNatIpsUpdateExternalHairpinNexthop(a1, p_Blink) )
    {
      SlbNatIpsDropDatagram(a1, *(_QWORD *)(a1 + 56), v42, 5);
      if ( *(_QWORD *)(a1 + 80) == p_Blink )
        *(_QWORD *)(a1 + 80) = 0;
      WinNatLibDereferenceSession(p_Blink - 8);
      return;
    }
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
  }
  if ( !v161 )
  {
LABEL_102:
    if ( (*(_BYTE *)(p_Blink + 64) & 0x11) == 1 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v49, v47, v45, v46);
  }
  v50 = *(_QWORD *)(p_Blink + 24);
  v51 = v160;
LABEL_186:
  if ( !v50 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v49, v47, v45, v46);
  if ( *(_QWORD *)(a1 + 112) != v50
    && !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)(a1 + 16) + 96LL))(
          *(_QWORD *)(a1 + 8),
          v50,
          v45) )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
    goto LABEL_192;
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(p_Blink + 232));
  if ( !v50 )
  {
LABEL_192:
    SlbNatIpsDropDatagram(a1, *(_QWORD *)(a1 + 56), v51, 7);
    if ( *(_QWORD *)(a1 + 80) == p_Blink )
      *(_QWORD *)(a1 + 80) = 0;
    v93 = p_Blink - 8;
    v94 = _InterlockedExchangeAdd64((volatile signed __int64 *)(p_Blink - 8), 0xFFFFFFFFFFFFFFFFuLL);
    v130 = v94 <= 1;
    v95 = v94 - 1;
    if ( !v130 )
      return;
    if ( !v95 )
      goto LABEL_196;
    goto LABEL_264;
  }
  v102 = *(_QWORD *)(a1 + 112);
  if ( v102 != v50 )
  {
    if ( *(_QWORD *)(a1 + 128) )
    {
      if ( !v102 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v90, v89, v91, v92);
      if ( (*(_BYTE *)(a1 + 2) & 2) != 0 )
      {
        SlbNatIpsClientPendPackets(a1);
      }
      else
      {
        if ( (byte_140026BED & 8) != 0 && *(_WORD *)a1 == 2 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 112LL))(
            *(_QWORD *)(a1 + 8),
            *(_QWORD *)(a1 + 112),
            &v169);
          v103 = 1;
          if ( (*(_BYTE *)(a1 + 2) & 1) == 0 )
            v103 = *(_DWORD *)p_Blink;
          SlbNatIpsLogIPv4Datagram(
            *(_DWORD *)(a1 + 24),
            *(_DWORD *)(a1 + 32),
            *(_QWORD *)(a1 + 40),
            v103,
            v169,
            *(_QWORD *)(a1 + 128),
            0,
            0);
        }
        v104 = *(_QWORD **)(a1 + 128);
        v105 = *(_QWORD **)(a1 + 136);
        *((_QWORD *)&v166 + 1) = v104;
        v167 = v105;
        if ( gAccount && v104 )
        {
          do
          {
            _InterlockedIncrement64(&gNBLForward);
            v104 = (_QWORD *)*v104;
          }
          while ( v104 );
        }
        (*(void (__fastcall **)(_QWORD, _QWORD, __int128 *, _QWORD, _QWORD))(*(_QWORD *)(a1 + 16) + 48LL))(
          *(_QWORD *)(a1 + 8),
          *(_QWORD *)(a1 + 48),
          &v166,
          0,
          *(_QWORD *)(a1 + 112));
        *(_QWORD *)(a1 + 128) = 0;
        *(_QWORD *)(a1 + 136) = a1 + 128;
      }
    }
    v89 = *(_QWORD *)(a1 + 112);
    if ( v89 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(a1 + 16) + 104LL))(*(_QWORD *)(a1 + 8));
    v90 = v161;
    v106 = *(_BYTE *)(a1 + 2) & 0xFD;
    LOBYTE(v90) = 2 * v161;
    *(_QWORD *)(a1 + 112) = v50;
    LOBYTE(v90) = v106 | v90;
    *(_BYTE *)(a1 + 2) = v90;
  }
  if ( ((*(_BYTE *)(a1 + 2) & 2) != 0) != v161 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v90, v89, v91, v92);
  v44 = v159;
LABEL_226:
  if ( (*(_BYTE *)(p_Blink + 64) & 0x10) != 0 && v44 )
  {
    v107 = *(_QWORD *)(a1 + 56);
    v163 = KeGetCurrentProcessorNumberEx(0);
    v111 = v26;
    v112 = v165;
    if ( v165 )
      v111 = v165;
    v113 = *(_BYTE *)(v111 + 16);
    if ( (*(_BYTE *)(p_Blink + 64) & 0x10) == 0 )
    {
LABEL_231:
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v111, v108, v109, v110);
      v112 = v165;
      goto LABEL_232;
    }
    while ( 1 )
    {
LABEL_232:
      LOBYTE(v109) = 1;
      if ( !(unsigned __int8)SlbNatLibTranslate((__int64)qword_1400263D8, p_Blink, v109, 0, v26, v112, v107) )
      {
        v118 = 9;
        goto LABEL_245;
      }
      v107 = *(_QWORD *)v107;
      if ( !v107 )
        break;
      if ( v165 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v115, v114, v116, v117);
      v26 = *((_QWORD *)qword_1400263D8 + 169) + 232LL * v163;
      if ( **(_QWORD **)(v107 + 8) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v115, v114, v116, v117);
      if ( !(unsigned __int8)WinNatParseNb(*(PNET_BUFFER *)(v107 + 8)) || !v26 )
      {
        v118 = 1;
        goto LABEL_245;
      }
      v112 = v165;
      if ( !*(_WORD *)(v26 + 224) )
        goto LABEL_231;
    }
    v118 = 0;
LABEL_245:
    if ( *(_QWORD *)(a1 + 80) == p_Blink )
      *(_QWORD *)(a1 + 80) = 0;
    v119 = *(_QWORD **)(a1 + 56);
    if ( v107 )
    {
      SlbNatIpsDropDatagram(a1, v119, v113, v118);
    }
    else
    {
      if ( v119 )
      {
        v120 = v163;
        v121 = 136LL * v163;
        do
        {
          v119 = (_QWORD *)*v119;
          v122 = 136 * v120;
          ++*(_QWORD *)((char *)qword_140026B68 + v121 + 88);
          if ( v113 == 6 )
          {
            ++*(_DWORD *)((char *)qword_140026B68 + v122 + 8);
          }
          else if ( v113 == 17 )
          {
            ++*(_DWORD *)((char *)qword_140026B68 + v122 + 32);
          }
          else
          {
            ++*(_DWORD *)((char *)qword_140026B68 + v122 + 56);
          }
          v123 = *(_BYTE *)(p_Blink + 64);
          if ( (v123 & 4) != 0 )
          {
            v124 = 136 * v120;
            if ( (v123 & 8) != 0 )
              ++*(_QWORD *)((char *)qword_140026B68 + v124 + 120);
            else
              ++*(_QWORD *)((char *)qword_140026B68 + v124 + 128);
          }
        }
        while ( v119 );
      }
      *(_QWORD *)(a1 + 64) = p_Blink;
      SlbNatIpsHandleIncomingUnicastDatagram(a1);
      *(_QWORD *)(a1 + 64) = 0;
    }
    v93 = p_Blink - 8;
    v125 = _InterlockedExchangeAdd64((volatile signed __int64 *)(p_Blink - 8), 0xFFFFFFFFFFFFFFFFuLL);
    v130 = v125 <= 1;
    v126 = v125 - 1;
    if ( !v130 )
      return;
    if ( !v126 )
    {
LABEL_196:
      v96 = *(_QWORD *)(v93 + 80);
      if ( v96 )
        WinNatCleanupBinding(v96);
      v97 = *(void (__fastcall **)(__int64))(v93 + 48);
      if ( v97 )
        v97(p_Blink);
      v98 = HIDWORD(KeGetPcr()[1].LockArray);
      v99 = (__int64 *)(*(_QWORD *)(v93 + 288) + 8LL);
      if ( *(_BYTE *)(v93 + 256) )
        v99 = *(__int64 **)(v93 + 288);
      v100 = *v99;
      v101 = v100 + ((unsigned __int64)(unsigned int)(v98 + 1) << 7);
      if ( !*(_BYTE *)(v101 + 176) )
        PplpLazyInitializeLookasideList(v100, v101 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v101 + 64), (PVOID)v93);
      return;
    }
LABEL_264:
    __fastfail(0xEu);
  }
  v127 = v26;
  v128 = *(__int64 **)(a1 + 56);
  if ( v165 )
    v127 = v165;
  v129 = *(unsigned __int8 *)(v127 + 150);
  if ( (unsigned __int8)v129 <= 1u )
    goto LABEL_351;
  if ( *(_DWORD *)(a1 + 120) >= *(_DWORD *)(v128[1] + 24) || (*(_BYTE *)(v127 + 212) & 4) == 0 )
    goto LABEL_275;
  if ( v160 == 6 )
  {
    v130 = *((_WORD *)v128 + 160) <= 1u;
    goto LABEL_274;
  }
  if ( v160 == 17 )
  {
    v130 = *((_WORD *)v128 + 140) <= 1u;
LABEL_274:
    if ( !v130 )
      goto LABEL_275;
LABEL_351:
    if ( (xmmword_1400262E0 & 4) != 0 )
      WPP_SF_dddd(
        v128[1],
        v127,
        v129,
        *(unsigned __int8 *)(v127 + 150),
        *(_DWORD *)(a1 + 120),
        *(_DWORD *)(v128[1] + 24),
        v169);
    SlbNatIpsSendICMPError(p_Blink, a1, v26);
    return;
  }
LABEL_275:
  v131 = *(_QWORD *)(a1 + 40);
  LODWORD(HashTable) = 0;
  if ( v131 )
  {
    if ( (BYTE8(xmmword_1400262E0) & 4) != 0 )
      WPP_SF_d(1282, 22, WPP_2017c49255f13d724299eee942b0d5fe_Traceguids, *(unsigned __int16 *)(v131 + 32));
    v132 = (unsigned __int16)(*(_WORD *)(v131 + 32) - 243) <= 1u;
  }
  else
  {
    v132 = 0;
  }
  v161 = v132;
  while ( 1 )
  {
    v162 = 0;
    v133 = (__int64 **)v128;
    v134 = v128;
    v135 = v128;
    v128 = (__int64 *)*v128;
    v59 = ((_DWORD)v133[17] & 0x20000000) == 0;
    *v134 = 0;
    if ( v59 || (*(_BYTE *)(a1 + 2) & 2) != 0 )
    {
      v59 = (*(_BYTE *)(a1 + 2) & 2) == 0;
      v138 = v135;
      v162 = v135;
      if ( v59 )
      {
        v139 = *((_DWORD *)v135 + 36);
        if ( (v139 & 0x18) != 0 && (v139 & 0x100) != 0 )
        {
          SlbNatFillPacketChecksum(v135, v26);
          v138 = v162;
        }
        *((_DWORD *)v138 + 76) &= 0xFF000000;
        *((_DWORD *)v162 + 44) &= 0xFFFF000F;
        v162[18] = 0;
      }
      else
      {
        v135[34] = 0;
      }
      goto LABEL_301;
    }
    if ( !gAccount )
    {
      if ( v132 )
      {
        v136 = 14;
        goto LABEL_288;
      }
      goto LABEL_287;
    }
    if ( !v132 )
    {
      _InterlockedIncrement64(&gNBLClone);
LABEL_287:
      v136 = 0;
      goto LABEL_288;
    }
    _InterlockedIncrement64(&gNBLDeepClone);
    v136 = 14;
LABEL_288:
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *, __int64 (__fastcall *)(), bool, int, _DWORD, __int64 **))(*(_QWORD *)(a1 + 16) + 56LL))(
      *(_QWORD *)(a1 + 8),
      *(_QWORD *)(a1 + 48),
      v135,
      SlbNatIpsClientNotifyEvent,
      v132,
      v136,
      0,
      &v162);
    if ( (v135[18] & 0x188) == 0x188 )
      SlbNatFillPacketChecksum(v162, v26);
    v137 = v162;
    if ( v162 )
      goto LABEL_302;
    if ( !gAccount )
      goto LABEL_341;
    _InterlockedIncrement64(&gNBLCloneFail);
LABEL_301:
    v137 = v162;
    if ( !v162 )
    {
LABEL_341:
      v152 = 8;
      LODWORD(HashTable) = 8;
LABEL_343:
      v147 = v160;
      SlbNatIpsDropDatagram(a1, v135, v160, v152);
      goto LABEL_331;
    }
LABEL_302:
    v140 = v159;
    v137[26] = *((unsigned int *)v135 + 52);
    v162[22] = v135[22];
    if ( !(unsigned __int8)SlbNatLibTranslate((__int64)qword_1400263D8, p_Blink, v140, 0, v26, v165, (__int64)v162) )
    {
      if ( v162 != v135 )
      {
        **(_QWORD **)(a1 + 152) = v162;
        *(_QWORD *)(a1 + 152) = v162;
      }
      v152 = 9;
      v162 = 0;
      LODWORD(HashTable) = 9;
      goto LABEL_343;
    }
    v142 = v159;
    v143 = v160;
    **(_QWORD **)(a1 + 136) = v162;
    *(_QWORD *)(a1 + 136) = v162;
    v144 = v163;
    *(_BYTE *)(a1 + 2) ^= (v142 ^ *(_BYTE *)(a1 + 2)) & 1;
    v145 = 136 * v144;
    if ( (_BYTE)v142 )
    {
      ++*(_QWORD *)((char *)qword_140026B68 + v145 + 88);
      if ( (_BYTE)v143 == 6 )
      {
        ++*(_DWORD *)((char *)qword_140026B68 + v145 + 8);
      }
      else if ( (_BYTE)v143 == 17 )
      {
        ++*(_DWORD *)((char *)qword_140026B68 + v145 + 32);
      }
      else
      {
        ++*(_DWORD *)((char *)qword_140026B68 + v145 + 56);
      }
      v146 = *(_BYTE *)(p_Blink + 64);
      if ( (v146 & 4) != 0 )
      {
        if ( (v146 & 8) != 0 )
          ++*(_QWORD *)((char *)qword_140026B68 + v145 + 120);
        else
          ++*(_QWORD *)((char *)qword_140026B68 + v145 + 128);
      }
    }
    else
    {
      ++*(_QWORD *)((char *)qword_140026B68 + v145 + 96);
      if ( (_BYTE)v143 == 6 )
      {
        ++*(_DWORD *)((char *)qword_140026B68 + v145 + 12);
      }
      else if ( (_BYTE)v143 == 17 )
      {
        ++*(_DWORD *)((char *)qword_140026B68 + v145 + 36);
      }
      else
      {
        ++*(_DWORD *)((char *)qword_140026B68 + v145 + 60);
      }
    }
    if ( byte_140026B80 )
      SlbNatLibClampMssOnIpPkt(a1, p_Blink, v142, v26, *(_QWORD *)(*(_QWORD *)(a1 + 56) + 8LL));
    if ( !v162 )
    {
      v152 = (unsigned int)HashTable;
      goto LABEL_343;
    }
    if ( v162 != v135 )
    {
      if ( v161 )
      {
        **(_QWORD **)(a1 + 152) = v135;
        *(_QWORD *)(a1 + 152) = v135;
      }
      else
      {
        *((_QWORD *)&v166 + 1) = v135;
        v167 = 0;
        if ( gAccount && v133 )
        {
          do
          {
            _InterlockedIncrement64(&gNBLRelease);
            v133 = (__int64 **)*v133;
          }
          while ( v133 );
        }
        (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)(a1 + 16) + 64LL))(*(_QWORD *)(a1 + 8), &v166);
      }
      if ( (*(_BYTE *)(a1 + 2) & 2) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v145, v143, v142, v141);
    }
    v147 = v160;
LABEL_331:
    if ( !v128 )
      goto LABEL_347;
    if ( v165 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v145, v143, v142, v141);
    v148 = SlbNatLibParseNBL(qword_1400263D8, v128, v163);
    v26 = v148;
    if ( !v148 )
      break;
    if ( !v162 )
    {
      v153 = (unsigned int)HashTable;
      goto LABEL_346;
    }
    v132 = v161;
    if ( !*(_WORD *)(v148 + 224) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v161, v149, v150, v151);
      v132 = v161;
    }
  }
  v153 = 1;
LABEL_346:
  SlbNatIpsDropDatagram(a1, v128, v147, v153);
LABEL_347:
  v154 = *(_QWORD *)(a1 + 80);
  if ( v154 != p_Blink )
  {
    if ( v154 )
      WinNatLibDereferenceSession(v154 - 8);
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
