# WfpAlepReauthorizeOutboundConnection

- ea: `0x1400c08f0`
- end: `0x1400c2055`
- name: `WfpAlepReauthorizeOutboundConnection`
- size: `5989`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400bea20`

## callees

- `0x1400515e8`
- `0x140052390`
- `0x140053850`
- `0x140053910`
- `0x140053e04`
- `0x140055780`
- `0x140055820`
- `0x14008a370`
- `0x1400ac790`
- `0x1400c08f0`
- `0x1400e5208`
- `0x14010c6cc`
- `0x14013c8f0`
- `0x1401bf640`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c0bf3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c1f83`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c1fc3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c0bf3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c1f83`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400c1fc3`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c0b3c`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c0b3c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400c140f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400c140f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400c14ba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400c14ba`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400c09ad`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400c09ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c14d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c1baa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c1edc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c14d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c1baa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c1edc`
- `ntoskrnl!ExAllocatePool2` at `0x1400c1265`
- `ntoskrnl!ExAllocatePool2` at `0x1400c1265`
- `NETIO!FeReleaseCompletionHandle` at `0x1400c1ebd`
- `NETIO!FeReleaseCompletionHandle` at `0x1400c1ebd`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x1400c0d03`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x1400c0d03`
- `NETIO!FeAcquireCompletionHandle` at `0x1400c0cf2`
- `NETIO!FeAcquireCompletionHandle` at `0x1400c0cf2`
- `NETIO!KfdAleAcquireEndpointContextFromFlow` at `0x1400c0aa5`
- `NETIO!KfdAleAcquireEndpointContextFromFlow` at `0x1400c0aa5`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400c1f34`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400c1f34`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x1400c1f01`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x1400c1f01`

## string_xrefs

- `0x1400c133e`: `WfpAleQueryPeerTokenInformation`
- `0x1400c13e3`: `WfpStringCchCopyA`
- `0x1400c13a1`: `StringCchCopyA`

## pseudocode

```c
__int64 __fastcall WfpAlepReauthorizeOutboundConnection(
        __int64 a1,
        __int16 a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5,
        __int64 a6,
        _OWORD *a7,
        __int16 a8,
        char a9,
        _DWORD **a10,
        __int128 *a11,
        __int16 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        unsigned __int8 a16,
        __int64 a17,
        int a18,
        int a19,
        __int64 a20,
        int a21,
        int a22,
        int a23,
        __int64 a24,
        __int64 a25,
        __int64 a26,
        __int64 a27,
        _DWORD *a28,
        _DWORD *a29,
        _DWORD *a30,
        bool *a31)
{
  _DWORD *v31; // rdi
  char *v33; // r14
  __int64 v35; // rcx
  __int64 v36; // r13
  int v37; // eax
  __int64 v38; // rsi
  __int64 v39; // rbx
  char v40; // r15
  unsigned __int8 v41; // r12
  __int64 v42; // rax
  __int64 v43; // rcx
  char *v44; // rbx
  _DWORD *v45; // rax
  _QWORD *v46; // rbx
  __int64 v47; // r8
  __int64 v48; // rax
  __int64 v49; // rcx
  int v50; // r9d
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 v53; // rax
  __int64 v54; // r13
  size_t v55; // r8
  __int64 v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rax
  bool v59; // zf
  __int64 v60; // rax
  __int128 v61; // xmm6
  __int128 v62; // xmm7
  __int128 v63; // xmm8
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // r13
  size_t v67; // r8
  __int64 v68; // rdx
  __int64 v69; // rax
  __int64 v70; // rdx
  int v71; // eax
  int v72; // r13d
  __int64 *v73; // rcx
  __int64 v74; // rax
  __int16 v75; // cx
  bool v76; // al
  int v77; // r9d
  PKSPIN_LOCK v78; // rsi
  __int64 v79; // rax
  int v80; // r9d
  __int64 v81; // r13
  __int64 v82; // rbx
  _BYTE *v83; // rsi
  __int64 v84; // rax
  const char *v85; // rdx
  _BYTE *v86; // rcx
  char v87; // si
  _BYTE *v88; // rax
  PKSPIN_LOCK v89; // rbx
  KSPIN_LOCK v90; // rax
  unsigned int v91; // r8d
  __int64 v92; // r9
  unsigned int v93; // ecx
  __int64 v94; // rax
  int v95; // edx
  void *v96; // rbx
  int v97; // ecx
  __int64 v98; // r8
  __int64 v99; // rax
  __int64 v100; // rax
  int v101; // edx
  int v102; // edx
  int v103; // ecx
  int v104; // edx
  int v105; // ecx
  __int16 v106; // r10
  __int16 v107; // cx
  _DWORD **v108; // rsi
  PKSPIN_LOCK v109; // rbx
  int v110; // r13d
  int v111; // r9d
  int v112; // ecx
  __int64 v113; // rbx
  __int64 v114; // rdx
  int v115; // r8d
  __int64 v116; // rdx
  unsigned int v117; // eax
  int v118; // ecx
  int v119; // eax
  __int64 v120; // rcx
  __int64 v121; // rax
  __int64 v122; // rcx
  __int64 v123; // r13
  __int64 v124; // rbx
  _DWORD *v125; // rsi
  int v126; // r9d
  int v127; // r8d
  __int64 v128; // rax
  __int64 v129; // rcx
  __int64 *v130; // r13
  __int64 v131; // rcx
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 v134; // rcx
  __int64 v135; // rax
  int v136; // r9d
  char v137; // dl
  __int128 v138; // xmm0
  __int64 v139; // rcx
  __int128 v140; // xmm1
  __int128 v141; // xmm2
  __int64 *v142; // r8
  int v143; // r8d
  __int128 *v144; // rcx
  __int128 v145; // xmm0
  char v146; // al
  int v147; // r8d
  unsigned __int128 v148; // rax
  __int64 v149; // rax
  __int64 v150; // rdx
  PVOID *v151; // rsi
  char *v152; // rsi
  char *v153; // rdi
  __int16 v155; // [rsp+68h] [rbp-A0h]
  char v156; // [rsp+6Ah] [rbp-9Eh]
  int v157; // [rsp+6Ch] [rbp-9Ch]
  int v158; // [rsp+70h] [rbp-98h]
  __int64 Size; // [rsp+78h] [rbp-90h] BYREF
  size_t Size_8[2]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v161; // [rsp+90h] [rbp-78h] BYREF
  __int64 v162; // [rsp+98h] [rbp-70h]
  int v163; // [rsp+A0h] [rbp-68h]
  BOOL v164; // [rsp+A4h] [rbp-64h]
  PKSPIN_LOCK SpinLock; // [rsp+A8h] [rbp-60h]
  __int64 v166; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v167; // [rsp+B8h] [rbp-50h]
  __int64 v168; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v169; // [rsp+C8h] [rbp-40h]
  __int64 v170; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v171; // [rsp+D8h] [rbp-30h]
  __int64 v172; // [rsp+E0h] [rbp-28h]
  __int64 v173; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v174; // [rsp+F0h] [rbp-18h]
  __int64 v175; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v176; // [rsp+100h] [rbp-8h]
  __int64 v177; // [rsp+108h] [rbp+0h] BYREF
  __int64 v178; // [rsp+110h] [rbp+8h]
  __int64 v179; // [rsp+118h] [rbp+10h] BYREF
  __int64 v180; // [rsp+120h] [rbp+18h]
  __int128 v181; // [rsp+128h] [rbp+20h] BYREF
  __int128 v182; // [rsp+138h] [rbp+30h] BYREF
  __int64 v183; // [rsp+148h] [rbp+40h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+150h] [rbp+48h] BYREF
  PVOID Entry; // [rsp+1D8h] [rbp+D0h] BYREF
  __int16 v186; // [rsp+1E0h] [rbp+D8h]
  __int16 v187; // [rsp+1F0h] [rbp+E8h]

  v187 = a4;
  v186 = a2;
  v31 = 0;
  v33 = 0;
  Entry = 0;
  LODWORD(v174) = 0;
  v35 = 0;
  LODWORD(v169) = 0;
  LODWORD(v180) = 0;
  LODWORD(v176) = 0;
  LODWORD(v178) = 0;
  LODWORD(v162) = 0;
  v173 = 0;
  v168 = 0;
  v179 = 0;
  v175 = 0;
  v177 = 0;
  v161 = 0;
  v155 = 0;
  v183 = 0;
  v166 = 0;
  Size = 0;
  v167 = 0;
  v170 = 0;
  *(_OWORD *)Size_8 = 0;
  v181 = 0;
  v182 = 0;
  if ( dword_140220310 )
  {
    v36 = KeQueryInterruptTimePrecise(&v170, 0xFFFFF78000000008uLL);
    v35 = 0;
  }
  else
  {
    v36 = MEMORY[0xFFFFF78000000008];
  }
  if ( *(_DWORD *)(a1 + 40) != 6 || (*(_DWORD *)(a1 + 48) & 0x10) != 0 )
  {
    SpinLock = (PKSPIN_LOCK)a15;
    v37 = *(_DWORD *)(a15 + 48);
  }
  else
  {
    v37 = *(_DWORD *)(a1 + 48);
    SpinLock = (PKSPIN_LOCK)a1;
  }
  *a31 = HIBYTE(v37) & 1;
  if ( (*(_DWORD *)(a1 + 52) & 0x10000) == 0
    || (*(_DWORD *)(a1 + 52) & 0x2000) != 0 && (*(_DWORD *)(a1 + 48) & 0x1000000) != 0 )
  {
    v38 = 0;
    if ( (*(_DWORD *)(a1 + 52) & 0x2000) != 0 && (*(_DWORD *)(a1 + 52) & 0x10000) == 0 )
      v38 = *(_QWORD *)(a1 + 448);
  }
  else
  {
    v38 = *(_QWORD *)(a1 + 448);
    if ( !v38 )
    {
      *a28 = 4097;
      v39 = -1073741790;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpAlepReauthorizeOutboundConnection",
          34);
      }
      v40 = 0;
      v41 = 0;
      goto LABEL_243;
    }
    while ( *(_QWORD *)(v38 + 48) )
      v38 = *(_QWORD *)(v38 + 48);
    v42 = KfdAleAcquireEndpointContextFromFlow(*(_QWORD *)(v38 + 504));
    v167 = v42;
    v35 = v42;
    if ( v42 )
      v38 = *(_QWORD *)(v42 + 448);
  }
  if ( (*(_DWORD *)(a1 + 52) & 0x2000) == 0
    || (*(_DWORD *)(a1 + 52) & 0x10000) != 0
    || (*(_DWORD *)(a1 + 48) & 0x1000000) != 0
    || (v158 = 1, !v38) )
  {
    v158 = 0;
  }
  if ( (*(_DWORD *)(a1 + 52) & 0x10000) == 0 || (*(_DWORD *)(a1 + 48) & 0x1000000) != 0 || !v35 || (v157 = 1, !v38) )
    v157 = 0;
  if ( KeGetCurrentIrql() < 2u )
  {
    LOBYTE(v155) = WfpRaiseIrqlToDispatchLevel();
    HIBYTE(v155) = 1;
  }
  LODWORD(v43) = HIDWORD(KeGetPcr()[1].LockArray);
  if ( !*((_BYTE *)gPerProcessorContext + 72 * v43 + 32) )
  {
    v33 = (char *)*((_QWORD *)gPerProcessorContext + 9 * v43 + 3);
    v31 = (_DWORD *)*((_QWORD *)gPerProcessorContext + 9 * v43 + 2);
    *((_BYTE *)gPerProcessorContext + 72 * v43 + 32) = 1;
LABEL_50:
    memset(v33, 0, 0x2A0u);
    memset(v31, 0, 0x2A8u);
    v45 = v31 + 156;
    *((_QWORD *)v31 + 79) = v31 + 156;
    *((_QWORD *)v31 + 78) = v31 + 156;
    LODWORD(v45) = HIDWORD(KeGetPcr()[1].LockArray);
    v46 = (_QWORD *)*((_QWORD *)gPerProcessorContext + 9 * (_QWORD)v45 + 5);
    memset(v46, 0, 0x158u);
    v48 = a17;
    v46[9] = v36;
    if ( v48 && FeAcquireCompletionHandle(v48, &v166) )
      v166 = FeAcquireGenericCompletionHandle();
    v49 = *(_QWORD *)(a1 + 480);
    v50 = v157;
    LOWORD(v181) = v186;
    DWORD1(v181) = *a3;
    *((_QWORD *)&v181 + 1) = v33;
    v174 = *(_QWORD *)(v49 + 16);
    LODWORD(v173) = *(unsigned __int16 *)(v49 + 10);
    *(_DWORD *)&v33[16 * a3[1]] = 12;
    *(_QWORD *)&v33[16 * a3[1] + 8] = &v173;
    if ( v157 )
    {
      v47 = v167;
      v169 = *(_QWORD *)(v167 + 488) + 224LL;
      LODWORD(v168) = *(_DWORD *)(*(_QWORD *)(v167 + 488) + 72LL);
      v51 = *(_QWORD *)(v167 + 488);
      v52 = *(_QWORD *)(v51 + 280);
      v53 = *(_QWORD *)(v51 + 144);
      Size = v52;
      if ( !v53 )
      {
LABEL_57:
        v56 = *(_QWORD *)(v47 + 728);
        if ( v56 )
          v162 = v56 + 104;
        else
          v162 = 0;
        v57 = *(_QWORD *)(v47 + 728);
        v58 = -1;
        if ( v57 )
        {
          do
            v59 = *(_WORD *)(v57 + 2 * v58++ + 106) == 0;
          while ( !v59 );
          LODWORD(v161) = 2 * v58 + 2;
        }
        else
        {
          LODWORD(v161) = 0;
        }
        v60 = *(_QWORD *)(v47 + 488);
        v61 = *(_OWORD *)(v60 + 160);
        v156 = *(_BYTE *)(v60 + 152);
        v62 = *(_OWORD *)(v60 + 192);
        v170 = *(_QWORD *)(v60 + 176);
        v63 = *(_OWORD *)(v60 + 208);
        goto LABEL_75;
      }
      v54 = *(_QWORD *)(*(_QWORD *)(v53 + 8) + 32LL);
      LODWORD(Entry) = (unsigned __int16)(*(_WORD *)(v54 + 8) + 2);
      LODWORD(Size_8[0]) = (_DWORD)Entry + 8;
      v39 = WfpPoolAllocNonPaged((unsigned int)((_DWORD)Entry + 8), 1668376129, &Size_8[1]);
      if ( !v39 )
      {
        memset((void *)Size_8[1], 0, LODWORD(Size_8[0]));
        v55 = (unsigned __int16)Entry;
        *(_QWORD *)Size_8[1] = *(_QWORD *)v54;
        memmove((void *)(Size_8[1] + 8), *(const void **)(v54 + 16), v55);
        v47 = v167;
        v50 = v157;
        goto LABEL_57;
      }
LABEL_59:
      LOBYTE(v38) = 1;
      goto LABEL_242;
    }
    v64 = *(_QWORD *)(a1 + 488);
    v169 = v64 + 224;
    LODWORD(v168) = *(_DWORD *)(v64 + 72);
    v65 = *(_QWORD *)(v64 + 144);
    Size = *(_QWORD *)(v64 + 280);
    if ( v65 )
    {
      v66 = *(_QWORD *)(*(_QWORD *)(v65 + 8) + 32LL);
      LODWORD(Entry) = (unsigned __int16)(*(_WORD *)(v66 + 8) + 2);
      LODWORD(Size_8[0]) = (_DWORD)Entry + 8;
      v39 = WfpPoolAllocNonPaged((unsigned int)((_DWORD)Entry + 8), 1668376129, &Size_8[1]);
      if ( v39 )
        goto LABEL_59;
      memset((void *)Size_8[1], 0, LODWORD(Size_8[0]));
      v67 = (unsigned __int16)Entry;
      *(_QWORD *)Size_8[1] = *(_QWORD *)v66;
      memmove((void *)(Size_8[1] + 8), *(const void **)(v66 + 16), v67);
      v64 = *(_QWORD *)(a1 + 488);
      v50 = 0;
    }
    v68 = *(_QWORD *)(a1 + 728);
    v69 = -1;
    if ( v68 )
    {
      v70 = v68 + 104;
      v162 = v70;
      do
        v59 = *(_WORD *)(v70 + 2 * v69++ + 2) == 0;
      while ( !v59 );
      v71 = 2 * v69 + 2;
    }
    else
    {
      v71 = 0;
      v162 = 0;
    }
    LODWORD(v161) = v71;
    v61 = *(_OWORD *)(v64 + 160);
    v156 = *(_BYTE *)(v64 + 152);
    v62 = *(_OWORD *)(v64 + 192);
    v170 = *(_QWORD *)(v64 + 176);
    v63 = *(_OWORD *)(v64 + 208);
LABEL_75:
    v72 = v158;
    v73 = gAleNullSid;
    if ( Size )
      v73 = (__int64 *)Size;
    *(_DWORD *)&v33[16 * a3[39]] = 12;
    *(_QWORD *)&v33[16 * a3[39] + 8] = &v161;
    *(_DWORD *)&v33[16 * a3[2]] = 16;
    *(_QWORD *)&v33[16 * a3[2] + 8] = &v168;
    *(_DWORD *)&v33[16 * a3[37]] = 13;
    *(_QWORD *)&v33[16 * a3[37] + 8] = v73;
    *(_DWORD *)&v33[16 * a3[41]] = 16;
    *(_QWORD *)&v33[16 * a3[41] + 8] = &v168;
    *(_DWORD *)&v33[16 * a3[38]] = 12;
    *(_QWORD *)&v33[16 * a3[38] + 8] = Size_8;
    *(_OWORD *)&v33[16 * a3[3]] = *a7;
    if ( v158 || v50 )
    {
      v59 = *(_WORD *)(v38 + 72) == 23;
      v164 = *a31;
      if ( v59 )
        v76 = !*(_WORD *)(v38 + 80)
           && !*(_WORD *)(v38 + 82)
           && !*(_WORD *)(v38 + 84)
           && !*(_WORD *)(v38 + 86)
           && !*(_WORD *)(v38 + 88)
           && !*(_WORD *)(v38 + 90)
           && !*(_WORD *)(v38 + 92)
           && *(_WORD *)(v38 + 94) == 256;
      else
        v76 = *(_BYTE *)(v38 + 76) == 127;
      v77 = (int)a11;
      *a31 = v76;
      v39 = WfpAlepAuthOutboundFlowSwizzleDestinationInformation((_DWORD)a3, v38, v47, v77, (__int64)v33);
      LOBYTE(v38) = 1;
      if ( v39 )
        goto LABEL_242;
    }
    else
    {
      v74 = 2LL * a3[7];
      v164 = 0;
      v75 = __ROR2__(a12, 8);
      *(_OWORD *)&v33[8 * v74] = *a11;
      *(_DWORD *)&v33[16 * a3[8]] = 2;
      *(_WORD *)&v33[16 * a3[8] + 8] = v75;
    }
    v78 = SpinLock;
    v79 = 2LL * a3[6];
    v80 = a5;
    v163 = 0;
    *(_DWORD *)&v33[8 * v79] = 1;
    v33[16 * a3[6] + 8] = v80;
    if ( v78[32] )
    {
      *(_DWORD *)&v33[16 * a3[33]] = 12;
      *(_QWORD *)&v33[16 * a3[33] + 8] = *(_QWORD *)(v78[32] + 64);
      v163 = *(unsigned __int8 *)(v78[32] + 2);
    }
    v59 = v78[31] == 0;
    LOBYTE(Entry) = 1;
    if ( !v59 )
    {
      v172 = 0;
      memset(&LockHandle, 0, sizeof(LockHandle));
      v81 = 0;
      v171 = 0;
      if ( gAleDebugEnabled )
      {
        v82 = 32;
        Size = ExAllocatePool2(64, 32, 1281715265);
        v83 = (_BYTE *)Size;
        if ( Size )
          goto LABEL_106;
        v81 = -1073741801;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"ExAllocatePool2",
            23);
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0 )
        {
LABEL_106:
          LOBYTE(Entry) = 1;
          if ( !v81 )
          {
            v84 = 2147483646;
            LOBYTE(Entry) = 1;
            v85 = "WfpAleQueryPeerTokenInformation";
            v86 = v83;
            do
            {
              if ( !v84 )
                break;
              if ( !*v85 )
                break;
              *v86++ = *v85++;
              --v84;
              --v82;
            }
            while ( v82 );
            v87 = 122;
            if ( v82 )
              v87 = 0;
            v88 = v86 - 1;
            if ( v82 )
              v88 = v86;
            *v88 = 0;
            if ( !v82 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
              {
                WPP_SF_sd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  13,
                  (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                  (unsigned int)"StringCchCopyA",
                  v87);
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
              {
                WPP_SF_sd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  15,
                  (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                  (unsigned int)"WfpStringCchCopyA",
                  v87);
              }
            }
            v83 = (_BYTE *)Size;
          }
        }
        else
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"WfpPoolAllocNonPaged",
            23);
          LOBYTE(Entry) = 1;
        }
      }
      else
      {
        v83 = 0;
        LOBYTE(Entry) = 1;
      }
      v89 = SpinLock;
      KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
      while ( *((_DWORD *)v89 + 2) )
        ;
      v59 = gAleDebugEnabled == 1;
      v89[2] = (KSPIN_LOCK)KeGetCurrentThread();
      if ( v59 && !v81 )
        v89[3] = (KSPIN_LOCK)v83;
      v90 = v89[31];
      v78 = v89;
      v91 = *(_DWORD *)v90;
      if ( *(_DWORD *)v90 )
      {
        v92 = *(_QWORD *)(v90 + 8);
        v93 = 0;
        do
        {
          v94 = 32LL * v93;
          v95 = *(_DWORD *)(v94 + v92 + 8);
          if ( v95 )
          {
            if ( v95 == 1 )
              v171 = *(_QWORD *)(v94 + v92 + 24);
          }
          else
          {
            v172 = *(_QWORD *)(v94 + v92 + 24);
          }
          ++v93;
        }
        while ( v93 < v91 );
      }
      v59 = gAleDebugEnabled == 1;
      v96 = 0;
      v78[2] = 0;
      if ( v59 )
      {
        v96 = (void *)v78[3];
        v78[3] = 0;
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( gAleDebugEnabled == 1 && v96 )
        ExFreePoolWithTag(v96, 0);
      if ( v171 )
      {
        v176 = v171 + 224;
        LODWORD(v175) = *(_DWORD *)(v171 + 72);
        *(_DWORD *)&v33[16 * a3[9]] = 16;
        *(_QWORD *)&v33[16 * a3[9] + 8] = &v175;
      }
      v80 = a5;
      v72 = v158;
      if ( v172 )
      {
        v178 = v172 + 224;
        LODWORD(v177) = *(_DWORD *)(v172 + 72);
        *(_DWORD *)&v33[16 * a3[10]] = 16;
        *(_QWORD *)&v33[16 * a3[10] + 8] = &v177;
      }
    }
    v97 = 0;
    v98 = a15;
    v59 = a15 == 0;
    *(_DWORD *)&v33[16 * a3[16]] = 3;
    v99 = v98;
    if ( v59 )
      v99 = a1;
    if ( v99 != -168 )
    {
      LOBYTE(Entry) = 1;
      if ( v98 )
      {
        v100 = v98 + 168;
      }
      else
      {
        v100 = a1 + 168;
        LOBYTE(Entry) = 1;
      }
      v97 = 2 * (*(_DWORD *)(v100 + 32) & 1);
      if ( (*(_DWORD *)(v100 + 32) & 0x800) != 0 )
        v97 |= 0x10000u;
    }
    v101 = v97 | 1;
    if ( !*a31 )
      v101 = v97;
    v102 = v101 | 4;
    v103 = v102 | 0x10;
    if ( (*(_DWORD *)(a1 + 48) & 0x10) == 0 )
      v103 = v102;
    v104 = v103 | 0x4000;
    if ( !v163 )
      v104 = v103;
    if ( (*((_DWORD *)v78 + 13) & 0x2000) != 0 )
      v104 |= 0x100000u;
    v105 = v104 | 0x200000;
    if ( (*((_DWORD *)v78 + 13) & 0x10000) == 0 )
      v105 = v104;
    *(_DWORD *)&v33[16 * a3[16] + 8] = v105;
    if ( v72 || v157 )
      *(_DWORD *)&v33[16 * a3[16] + 8] |= 0x2000000u;
    v106 = v187;
    if ( v187 == 2 )
    {
      if ( v80 != 1 )
      {
LABEL_170:
        v107 = __ROR2__(a8, 8);
        *(_DWORD *)&v33[16 * a3[5]] = 2;
        *(_WORD *)&v33[16 * a3[5] + 8] = v107;
        *(_DWORD *)&v33[16 * a3[34]] = 0;
        goto LABEL_171;
      }
    }
    else if ( v187 != 23 || v80 != 58 )
    {
      goto LABEL_170;
    }
    v116 = a13;
    *(_DWORD *)&v33[16 * a3[5]] = 2;
    *(_WORD *)&v33[16 * a3[5] + 8] = *(unsigned __int8 *)(v116 + 4);
    *(_DWORD *)&v33[16 * a3[8]] = 2;
    *(_WORD *)&v33[16 * a3[8] + 8] = *(unsigned __int8 *)(v116 + 5);
    *(_DWORD *)&v33[16 * a3[34]] = 2;
    *(_WORD *)&v33[16 * a3[34] + 8] = *(unsigned __int8 *)(v98 + 570);
    v117 = *(unsigned __int8 *)(v116 + 4);
    if ( v106 == 2 )
    {
      if ( (unsigned __int8)v117 <= 0x12u )
      {
        v118 = 418049;
        if ( _bittest(&v118, v117) )
        {
          *v31 |= 0x8000000u;
          v31[50] = *(_DWORD *)v116;
        }
      }
    }
    else if ( (unsigned __int8)(v117 + 0x80) <= 1u )
    {
      *v31 |= 0x8000000u;
      v31[50] = *(_DWORD *)v116;
    }
LABEL_171:
    v108 = a10;
    v109 = SpinLock;
    v110 = a23;
    v111 = a25;
    *(_DWORD *)&v33[16 * a3[4]] = 1;
    v33[16 * a3[4] + 8] = a9;
    *(_DWORD *)&v33[16 * a3[12]] = 4;
    *(_QWORD *)&v33[16 * a3[12] + 8] = v108 + 2;
    *(_DWORD *)&v33[16 * a3[13]] = 3;
    *(_DWORD *)&v33[16 * a3[13] + 8] = v108[6][3];
    *(_DWORD *)&v33[16 * a3[14]] = 3;
    *(_DWORD *)&v33[16 * a3[14] + 8] = v108[6][4];
    *(_DWORD *)&v33[16 * a3[19]] = 3;
    *(_DWORD *)&v33[16 * a3[19] + 8] = *((_DWORD *)v108 + 2);
    v112 = *((_DWORD *)v109 + 83);
    v113 = a20;
    v114 = a20;
    v115 = a20;
    if ( v110 )
      v114 = 0;
    *a29 = v112;
    if ( v110 != 1 )
      v115 = 0;
    AlepFillEdgeInterfaceRelatedFields(v112, (_DWORD)a3, v115, v111, v114, a6, a24, a21, a21, v112, a22, (__int64)v33);
    if ( *(_DWORD *)&v33[16 * a3[31]] )
      *a30 = *(_DWORD *)&v33[16 * a3[31] + 8];
    if ( v113 )
    {
      *(_DWORD *)&v33[16 * a3[35]] = 4;
      *(_QWORD *)&v33[16 * a3[35] + 8] = v113 + 80;
    }
    else
    {
      *(_DWORD *)&v33[16 * a3[35]] = 0;
    }
    *(_DWORD *)&v33[16 * a3[40]] = 3;
    *(_DWORD *)&v33[16 * a3[40] + 8] = **v108;
    if ( *(_DWORD *)(a1 + 680) == 1 )
      v31[1] |= 0x80000u;
    *v31 |= 0x80u;
    *((_QWORD *)v31 + 1) = &v182;
    *v31 |= 0x20u;
    *((_QWORD *)v31 + 8) = *(_QWORD *)(*(_QWORD *)(a1 + 480) + 32LL);
    *v31 |= 0x800u;
    v119 = a18;
    v31[20] = **v108;
    *v31 |= 4u;
    v31[10] = v119;
    *v31 |= 0x400u;
    v31[11] = a19;
    v120 = *(_QWORD *)(a1 + 480);
    v180 = *(_QWORD *)(v120 + 16);
    LODWORD(v179) = *(unsigned __int16 *)(v120 + 10);
    *v31 |= 8u;
    *((_QWORD *)v31 + 6) = &v179;
    *v31 |= 0x10u;
    v121 = a14;
    *((_QWORD *)v31 + 7) = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 64LL);
    *v31 |= 2u;
    v122 = a27;
    *((_QWORD *)v31 + 4) = v121;
    *v31 |= 0x4000u;
    *((_QWORD *)v31 + 13) = v166;
    *v31 |= 0x40000u;
    v31[35] = v110;
    if ( v122 )
    {
      *v31 |= 0x20000000u;
      *((_QWORD *)v31 + 26) = v122 + 72;
      if ( *(_DWORD *)(v122 + 464) )
      {
        *v31 |= 0x10000000u;
        v31[51] = *(_DWORD *)(v122 + 464);
      }
      *v31 |= 0x40000000u;
      *((_QWORD *)v31 + 27) = v122;
    }
    v123 = a15;
    v124 = a26;
    if ( a15 )
    {
      *(_QWORD *)&v182 = a15;
    }
    else
    {
      *(_QWORD *)&v182 = a1;
      if ( a26 )
      {
        if ( *(_QWORD *)(a1 + 544) )
          *(_QWORD *)(v124 + 48) = WfpAleQueryOrInsertEndpointHandle();
        else
          *(_QWORD *)(a26 + 48) = 0;
        BYTE8(v182) = 0;
LABEL_197:
        *v31 |= 0x8000u;
        *((_QWORD *)v31 + 14) = *(_QWORD *)v124;
        if ( *(_QWORD *)(v124 + 48) )
        {
          *v31 |= 0x4000000u;
          *((_QWORD *)v31 + 24) = *(_QWORD *)(v124 + 48);
        }
        if ( *(_DWORD *)(v124 + 8) )
        {
          *v31 |= 0x20000u;
          v31[30] = *(_DWORD *)(v124 + 8);
        }
        if ( *(_QWORD *)(v124 + 16) )
        {
          *v31 |= 0x10000u;
          *((_QWORD *)v31 + 16) = *(_QWORD *)(v124 + 16);
          v31[34] = *(_DWORD *)(v124 + 24);
        }
        if ( *(_QWORD *)(v124 + 32) )
        {
          *v31 |= 0x800000u;
          *((_QWORD *)v31 + 18) = *(_QWORD *)(v124 + 32);
          v31[38] = *(_DWORD *)(v124 + 40);
        }
LABEL_205:
        if ( *(_DWORD *)(a1 + 40) == 6 && (*(_DWORD *)(a1 + 48) & 0x10) == 0 )
          *((_QWORD *)v31 + 63) = *(_QWORD *)(a1 + 352);
        v125 = a28;
        v126 = a16;
        v127 = a25;
        *((_BYTE *)v31 + 592) = v156;
        v128 = v170;
        *(_OWORD *)(v31 + 150) = v61;
        *((_QWORD *)v31 + 77) = v128;
        *(_OWORD *)(v31 + 162) = v62;
        *(_OWORD *)(v31 + 166) = v63;
        v39 = WfpAleClassify((unsigned int)&v181, (_DWORD)v31, v127, v126, 0, (__int64)v125);
        if ( v39 )
          goto LABEL_241;
        if ( *v125 != 4097 && (v158 || v157) )
        {
          if ( v164 )
            *(_DWORD *)&v33[16 * a3[16] + 8] |= 1u;
          *(_DWORD *)&v33[16 * a3[16] + 8] &= ~0x2000000u;
          if ( Size_8[1] )
          {
            ExFreePoolWithTag((PVOID)Size_8[1], 0);
            Size_8[1] = 0;
            LODWORD(Size_8[0]) = 0;
          }
          v129 = *(_QWORD *)(a1 + 488);
          v169 = v129 + 224;
          LODWORD(v168) = *(_DWORD *)(v129 + 72);
          v130 = *(__int64 **)(v129 + 280);
          v131 = *(_QWORD *)(v129 + 144);
          if ( v131 )
          {
            v39 = WfpAleMarshalFqbnValue(*(_QWORD *)(*(_QWORD *)(v131 + 8) + 32LL), Size_8);
            if ( v39 )
              goto LABEL_241;
          }
          v132 = *(_QWORD *)(a1 + 728);
          if ( v132 )
          {
            v133 = v132 + 104;
            v134 = -1;
            v162 = v133;
            do
              v59 = *(_WORD *)(v133 + 2 * v134++ + 2) == 0;
            while ( !v59 );
            LODWORD(v132) = 2 * v134 + 2;
          }
          else
          {
            v162 = 0;
          }
          LODWORD(v161) = v132;
          v135 = *(_QWORD *)(a1 + 488);
          v136 = a16;
          v137 = *(_BYTE *)(v135 + 152);
          v138 = *(_OWORD *)(v135 + 160);
          v139 = *(_QWORD *)(v135 + 176);
          v140 = *(_OWORD *)(v135 + 192);
          v141 = *(_OWORD *)(v135 + 208);
          *(_DWORD *)&v33[16 * a3[2]] = 16;
          *(_QWORD *)&v33[16 * a3[2] + 8] = &v168;
          v142 = gAleNullSid;
          if ( v130 )
            v142 = v130;
          *(_DWORD *)&v33[16 * a3[37]] = 13;
          *(_QWORD *)&v33[16 * a3[37] + 8] = v142;
          *(_DWORD *)&v33[16 * a3[39]] = 12;
          *(_QWORD *)&v33[16 * a3[39] + 8] = &v161;
          *(_DWORD *)&v33[16 * a3[38]] = 12;
          *(_QWORD *)&v33[16 * a3[38] + 8] = Size_8;
          v143 = a25;
          *((_BYTE *)v31 + 592) = v137;
          *(_OWORD *)(v31 + 150) = v138;
          *((_QWORD *)v31 + 77) = v139;
          v144 = a11;
          *(_OWORD *)(v31 + 162) = v140;
          *(_OWORD *)(v31 + 166) = v141;
          v145 = *v144;
          LOWORD(v144) = __ROR2__(a12, 8);
          *(_OWORD *)&v33[16 * a3[7]] = v145;
          *(_DWORD *)&v33[16 * a3[8]] = 2;
          *(_WORD *)&v33[16 * a3[8] + 8] = (_WORD)v144;
          v39 = WfpAleClassify((unsigned int)&v181, (_DWORD)v31, v143, v136, 0, (__int64)v125);
          if ( v39 )
            goto LABEL_241;
          v123 = a15;
        }
        if ( *(_DWORD *)(a1 + 40) != 6 || (*(_DWORD *)(a1 + 48) & 0x10) != 0 )
        {
          v146 = *(_BYTE *)(v123 + 492);
          LOBYTE(v38) = (_BYTE)Entry;
          if ( v146 == 1 )
          {
            v40 = HIBYTE(v155);
            v41 = v155;
            if ( v31[84] != 3 )
              goto LABEL_243;
            v147 = v31[86];
            goto LABEL_237;
          }
          if ( (v146 & 2) != 0 )
          {
            v40 = HIBYTE(v155);
            v41 = v155;
            if ( v31[88] != 3 )
              goto LABEL_243;
            v147 = v31[90];
LABEL_237:
            v148 = MEMORY[0xFFFFF78000000008] * (unsigned __int128)0x346DC5D63886594BuLL;
            *(_DWORD *)(v123 + 532) = v147;
            _InterlockedExchange64((volatile __int64 *)(v123 + 544), *((_QWORD *)&v148 + 1) >> 11);
            goto LABEL_243;
          }
LABEL_242:
          v41 = v155;
          v40 = HIBYTE(v155);
          goto LABEL_243;
        }
LABEL_241:
        LOBYTE(v38) = (_BYTE)Entry;
        goto LABEL_242;
      }
    }
    BYTE8(v182) = 0;
    if ( !a26 )
      goto LABEL_205;
    goto LABEL_197;
  }
  if ( !WfpAllocateFromPerProcessorLookasideList(gIncomingValuesLookasideList, &Entry) )
  {
    if ( !WfpAllocateFromPerProcessorLookasideList(gMetadataLookasideList, &Size) )
    {
      v33 = (char *)Entry;
      v31 = (_DWORD *)Size;
      goto LABEL_50;
    }
    v44 = (char *)gIncomingValuesLookasideList
        + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v44[176] )
      PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v44 + 64);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v44 + 64), Entry);
  }
  v40 = HIBYTE(v155);
  LOBYTE(v38) = 0;
  v41 = v155;
  v31 = 0;
  if ( HIBYTE(v155) )
    WfpLowerIrqlFromDispatchLevel((unsigned __int8)v155);
  v39 = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAlepReauthorizeOutboundConnection",
      154);
  }
LABEL_243:
  LOBYTE(a4) = 5;
  v149 = WfpAlepAuthTelemetry(a17, 0, 0, a4);
  if ( v166 )
  {
    v149 = FeReleaseCompletionHandle(v166, v150);
    v166 = 0;
  }
  if ( Size_8[1] )
  {
    ExFreePoolWithTag((PVOID)Size_8[1], 0);
    Size_8[1] = 0;
    LODWORD(Size_8[0]) = 0;
  }
  if ( v167 )
    v149 = KfdAleReleaseFlowHandleForFlow(v167);
  if ( (_BYTE)v38 )
  {
    LODWORD(v149) = HIDWORD(KeGetPcr()[1].LockArray);
    v151 = (PVOID *)((char *)gPerProcessorContext + 72 * v149);
    KfdReleaseTerminatingFilters(v31 + 156);
    if ( v33 == v151[3] )
    {
      *((_BYTE *)v151 + 32) = 0;
    }
    else
    {
      v152 = (char *)gMetadataLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v152[176] )
        PplpLazyInitializeLookasideList(gMetadataLookasideList, v152 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v152 + 64), v31);
      v153 = (char *)gIncomingValuesLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v153[176] )
        PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v153 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v153 + 64), v33);
    }
    if ( v40 )
      WfpLowerIrqlFromDispatchLevel(v41);
  }
  if ( v39
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"WfpAlepReauthorizeOutboundConnection",
      v39);
  }
  return v39;
}

```

## disassembly

```asm
0x1400c08f0  mov     rax, rsp
0x1400c08f3  mov     [rax+20h], r9w
0x1400c08f8  mov     [rax+10h], dx
0x1400c08fc  push    rbp
0x1400c08fd  push    rbx
0x1400c08fe  push    r13
0x1400c0900  lea     rbp, [rax-0C8h]
0x1400c0907  sub     rsp, 1B0h
0x1400c090e  mov     [rax+18h], rsi
0x1400c0912  xorps   xmm0, xmm0
0x1400c0915  mov     [rax-20h], rdi
0x1400c0919  mov     rdx, 0FFFFF78000000008h
0x1400c0923  mov     [rax-28h], r12
0x1400c0927  xor     edi, edi
0x1400c0929  mov     [rax-30h], r14
0x1400c092d  mov     r12, r8
0x1400c0930  mov     [rax-38h], r15
0x1400c0934  xor     r14d, r14d
0x1400c0937  xor     eax, eax
0x1400c0939  mov     [rbp+0C0h+Entry], r14
0x1400c0940  mov     qword ptr [rbp+0C0h+var_DC], rax
0x1400c0944  mov     r15, rcx
0x1400c0947  xor     ecx, ecx
0x1400c0949  mov     qword ptr [rbp+0C0h+var_104], rax
0x1400c094d  mov     qword ptr [rbp+0C0h+var_AC], rax
0x1400c0951  mov     qword ptr [rbp+0C0h+var_CC], rax
0x1400c0955  mov     qword ptr [rbp+0C0h+var_BC], rax
0x1400c0959  mov     qword ptr [rbp+0C0h+var_134], rax
0x1400c095d  mov     [rbp-20h], rax
0x1400c0961  mov     [rbp-48h], rax
0x1400c0965  mov     [rbp+10h], rax
0x1400c0969  mov     [rbp-10h], rax
0x1400c096d  mov     [rbp+0], rax
0x1400c0971  mov     [rbp-78h], rax
0x1400c0975  mov     byte ptr [rsp+1C0h+var_160], al
0x1400c0979  mov     byte ptr [rsp+1C0h+var_160+1], al
0x1400c097d  mov     [rbp+0C0h+var_80], rax
0x1400c0981  mov     [rbp+0C0h+var_118], rax
0x1400c0985  mov     eax, cs:dword_140220310
0x1400c098b  mov     [rsp+1C0h+Size], rdi
0x1400c0990  mov     [rbp+0C0h+var_110], rcx
0x1400c0994  mov     [rbp+0C0h+var_F8], rcx
0x1400c0998  movups  xmmword ptr [rsp+1C0h+Size+8], xmm0
0x1400c099d  movups  [rbp+0C0h+var_A0], xmm0
0x1400c09a1  movups  [rbp+0C0h+var_90], xmm0
0x1400c09a5  test    eax, eax
0x1400c09a7  jz      short loc_1400C09C0
0x1400c09a9  lea     rcx, [rbp+0C0h+var_F8]
0x1400c09ad  call    cs:__imp_KeQueryInterruptTimePrecise
0x1400c09b4  nop     dword ptr [rax+rax+00h]
0x1400c09b9  mov     r13, rax
0x1400c09bc  mov     ecx, edi
0x1400c09be  jmp     short loc_1400C09C3
0x1400c09c0  mov     r13, [rdx]
0x1400c09c3  cmp     dword ptr [r15+28h], 6
0x1400c09c8  jnz     short loc_1400C09DC
0x1400c09ca  mov     eax, [r15+30h]
0x1400c09ce  test    al, 10h
0x1400c09d0  jnz     short loc_1400C09DC
0x1400c09d2  mov     eax, [r15+30h]
0x1400c09d6  mov     [rbp+0C0h+SpinLock], r15
0x1400c09da  jmp     short loc_1400C09EA
0x1400c09dc  mov     rbx, [rbp+0C0h+arg_70]
0x1400c09e3  mov     [rbp+0C0h+SpinLock], rbx
0x1400c09e7  mov     eax, [rbx+30h]
0x1400c09ea  mov     rdx, [rbp+0C0h+arg_F0]
0x1400c09f1  shr     eax, 18h
0x1400c09f4  and     al, 1
0x1400c09f6  mov     [rdx], al
0x1400c09f8  lea     rdx, WPP_GLOBAL_Control
0x1400c09ff  mov     eax, [r15+34h]
0x1400c0a03  bt      eax, 10h
0x1400c0a07  jnb     loc_1400C0AC6
0x1400c0a0d  mov     eax, [r15+34h]
0x1400c0a11  bt      eax, 0Dh
0x1400c0a15  jnb     short loc_1400C0A25
0x1400c0a17  mov     eax, [r15+30h]
0x1400c0a1b  bt      eax, 18h
0x1400c0a1f  jb      loc_1400C0AC6
0x1400c0a25  mov     rsi, [r15+1C0h]
0x1400c0a2c  test    rsi, rsi
0x1400c0a2f  jnz     short loc_1400C0A90
0x1400c0a31  mov     rax, [rbp+0C0h+arg_D8]
0x1400c0a38  mov     dword ptr [rax], 1001h
0x1400c0a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0a45  mov     rbx, 0FFFFFFFFC0000022h
0x1400c0a4c  cmp     rcx, rdx
0x1400c0a4f  jz      short loc_1400C0A80
0x1400c0a51  cmp     byte ptr [rcx+29h], 2
0x1400c0a55  jb      short loc_1400C0A80
0x1400c0a57  test    dword ptr [rcx+2Ch], 1000h
0x1400c0a5e  jz      short loc_1400C0A80
0x1400c0a60  mov     rcx, [rcx+18h]
0x1400c0a64  lea     r9, aWfpalepreautho; "WfpAlepReauthorizeOutboundConnection"
0x1400c0a6b  mov     edx, 0Ah
0x1400c0a70  mov     dword ptr [rsp+1C0h+var_1A0], ebx
0x1400c0a74  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400c0a7b  call    WPP_SF_sd
0x1400c0a80  xor     r15b, r15b
0x1400c0a83  xor     r12b, r12b
0x1400c0a86  jmp     loc_1400C1E99
0x1400c0a90  mov     rax, [rsi+30h]
0x1400c0a94  test    rax, rax
0x1400c0a97  jz      short loc_1400C0A9E
0x1400c0a99  mov     rsi, rax
0x1400c0a9c  jmp     short loc_1400C0A90
0x1400c0a9e  mov     rcx, [rsi+1F8h]
0x1400c0aa5  call    cs:__imp_KfdAleAcquireEndpointContextFromFlow
0x1400c0aac  nop     dword ptr [rax+rax+00h]
0x1400c0ab1  mov     [rbp+0C0h+var_110], rax
0x1400c0ab5  mov     rcx, rax
0x1400c0ab8  test    rax, rax
0x1400c0abb  jz      short loc_1400C0AE3
0x1400c0abd  mov     rsi, [rax+1C0h]
0x1400c0ac4  jmp     short loc_1400C0AE3
0x1400c0ac6  mov     eax, [r15+34h]
0x1400c0aca  xor     esi, esi
0x1400c0acc  bt      eax, 0Dh
0x1400c0ad0  jnb     short loc_1400C0AE3
0x1400c0ad2  mov     eax, [r15+34h]
0x1400c0ad6  bt      eax, 10h
0x1400c0ada  jb      short loc_1400C0AE3
0x1400c0adc  mov     rsi, [r15+1C0h]
0x1400c0ae3  mov     eax, [r15+34h]
0x1400c0ae7  bt      eax, 0Dh
0x1400c0aeb  jnb     short loc_1400C0B0E
0x1400c0aed  mov     eax, [r15+34h]
0x1400c0af1  bt      eax, 10h
0x1400c0af5  jb      short loc_1400C0B0E
0x1400c0af7  mov     eax, [r15+30h]
0x1400c0afb  bt      eax, 18h
0x1400c0aff  jb      short loc_1400C0B0E
0x1400c0b01  mov     dword ptr [rsp+1C0h+var_158], 1
0x1400c0b09  test    rsi, rsi
0x1400c0b0c  jnz     short loc_1400C0B12
0x1400c0b0e  mov     dword ptr [rsp+1C0h+var_158], edi
0x1400c0b12  mov     eax, [r15+34h]
0x1400c0b16  bt      eax, 10h
0x1400c0b1a  jnb     short loc_1400C0B38
0x1400c0b1c  mov     eax, [r15+30h]
0x1400c0b20  bt      eax, 18h
0x1400c0b24  jb      short loc_1400C0B38
0x1400c0b26  test    rcx, rcx
0x1400c0b29  jz      short loc_1400C0B38
0x1400c0b2b  mov     dword ptr [rsp+64h], 1
0x1400c0b33  test    rsi, rsi
0x1400c0b36  jnz     short loc_1400C0B3C
0x1400c0b38  mov     [rsp+64h], edi
0x1400c0b3c  call    cs:__imp_KeGetCurrentIrql
0x1400c0b43  nop     dword ptr [rax+rax+00h]
0x1400c0b48  cmp     al, 2
0x1400c0b4a  jnb     short loc_1400C0B5A
0x1400c0b4c  call    WfpRaiseIrqlToDispatchLevel
0x1400c0b51  mov     byte ptr [rsp+1C0h+var_160], al
0x1400c0b55  mov     byte ptr [rsp+1C0h+var_160+1], 1
0x1400c0b5a  mov     ecx, gs:1A4h
0x1400c0b62  lea     r8, [rcx+rcx*8]
0x1400c0b66  mov     rcx, cs:gPerProcessorContext
0x1400c0b6d  cmp     [rcx+r8*8+20h], dil
0x1400c0b72  jnz     short loc_1400C0B89
0x1400c0b74  mov     r14, [rcx+r8*8+18h]
0x1400c0b79  mov     rdi, [rcx+r8*8+10h]
0x1400c0b7e  mov     byte ptr [rcx+r8*8+20h], 1
0x1400c0b84  jmp     loc_1400C0C85
0x1400c0b89  mov     rcx, cs:gIncomingValuesLookasideList
0x1400c0b90  lea     rdx, [rbp+0C0h+Entry]
0x1400c0b97  call    WfpAllocateFromPerProcessorLookasideList
0x1400c0b9c  test    rax, rax
0x1400c0b9f  jnz     short loc_1400C0BFF
0x1400c0ba1  mov     rcx, cs:gMetadataLookasideList
0x1400c0ba8  lea     rdx, [rsp+1C0h+Size]
0x1400c0bad  call    WfpAllocateFromPerProcessorLookasideList
0x1400c0bb2  test    rax, rax
0x1400c0bb5  jz      loc_1400C0C79
0x1400c0bbb  mov     eax, gs:1A4h
0x1400c0bc3  mov     rcx, cs:gIncomingValuesLookasideList
0x1400c0bca  lea     ebx, [rax+1]
0x1400c0bcd  shl     rbx, 7
0x1400c0bd1  add     rbx, rcx
0x1400c0bd4  movzx   eax, byte ptr [rbx+0B0h]
0x1400c0bdb  test    al, al
0x1400c0bdd  jnz     short loc_1400C0BE8
0x1400c0bdf  lea     rdx, [rbx+40h]
0x1400c0be3  call    PplpLazyInitializeLookasideList
0x1400c0be8  mov     rdx, [rbp+0C0h+Entry]; Entry
0x1400c0bef  lea     rcx, [rbx+40h]; Lookaside
0x1400c0bf3  call    cs:__imp_ExFreeToLookasideListEx
0x1400c0bfa  nop     dword ptr [rax+rax+00h]
0x1400c0bff  movzx   r15d, byte ptr [rsp+1C0h+var_160+1]
0x1400c0c05  xor     sil, sil
0x1400c0c08  movzx   r12d, byte ptr [rsp+1C0h+var_160]
0x1400c0c0e  mov     rdi, r14
0x1400c0c11  test    r15b, r15b
0x1400c0c14  jz      short loc_1400C0C1F
0x1400c0c16  movzx   ecx, r12b
0x1400c0c1a  call    WfpLowerIrqlFromDispatchLevel
0x1400c0c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0c26  lea     r13, WPP_GLOBAL_Control
0x1400c0c2d  mov     rbx, 0FFFFFFFFC000009Ah
0x1400c0c34  cmp     rcx, r13
0x1400c0c37  jz      loc_1400C1EA0
0x1400c0c3d  cmp     byte ptr [rcx+29h], 2
0x1400c0c41  jb      loc_1400C1EA0
0x1400c0c47  test    dword ptr [rcx+2Ch], 1000h
0x1400c0c4e  jz      loc_1400C1EA0
0x1400c0c54  mov     rcx, [rcx+18h]
0x1400c0c58  lea     r9, aWfpalepreautho; "WfpAlepReauthorizeOutboundConnection"
0x1400c0c5f  mov     edx, 0Ah
0x1400c0c64  mov     dword ptr [rsp+1C0h+var_1A0], ebx
0x1400c0c68  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400c0c6f  call    WPP_SF_sd
0x1400c0c74  jmp     loc_1400C1EA0
0x1400c0c79  mov     r14, [rbp+0C0h+Entry]
0x1400c0c80  mov     rdi, [rsp+1C0h+Size]
0x1400c0c85  xor     edx, edx; Val
0x1400c0c87  mov     r8d, 2A0h; Size
0x1400c0c8d  mov     rcx, r14; void *
0x1400c0c90  call    memset
0x1400c0c95  xor     edx, edx; Val
0x1400c0c97  mov     r8d, 2A8h; Size
0x1400c0c9d  mov     rcx, rdi; void *
0x1400c0ca0  call    memset
0x1400c0ca5  lea     rax, [rdi+270h]
0x1400c0cac  mov     r8d, 158h; Size
0x1400c0cb2  mov     [rax+8], rax
0x1400c0cb6  mov     [rax], rax
0x1400c0cb9  mov     eax, gs:1A4h
0x1400c0cc1  lea     rdx, [rax+rax*8]
0x1400c0cc5  mov     rax, cs:gPerProcessorContext
0x1400c0ccc  mov     rbx, [rax+rdx*8+28h]
0x1400c0cd1  xor     edx, edx; Val
0x1400c0cd3  mov     rcx, rbx; void *
0x1400c0cd6  call    memset
0x1400c0cdb  mov     rax, [rbp+0C0h+arg_80]
0x1400c0ce2  mov     [rbx+48h], r13
0x1400c0ce6  test    rax, rax
0x1400c0ce9  jz      short loc_1400C0D13
0x1400c0ceb  lea     rdx, [rbp+0C0h+var_118]
0x1400c0cef  mov     rcx, rax
0x1400c0cf2  call    cs:__imp_FeAcquireCompletionHandle
0x1400c0cf9  nop     dword ptr [rax+rax+00h]
0x1400c0cfe  test    rax, rax
0x1400c0d01  jz      short loc_1400C0D13
0x1400c0d03  call    cs:__imp_FeAcquireGenericCompletionHandle
0x1400c0d0a  nop     dword ptr [rax+rax+00h]
0x1400c0d0f  mov     [rbp+0C0h+var_118], rax
0x1400c0d13  mov     rcx, [r15+1E0h]
0x1400c0d1a  movzx   eax, [rbp+0C0h+arg_8]
0x1400c0d21  mov     r9d, [rsp+64h]
0x1400c0d26  mov     word ptr [rbp+0C0h+var_A0], ax
0x1400c0d2a  movzx   eax, word ptr [r12]
0x1400c0d2f  mov     dword ptr [rbp+0C0h+var_A0+4], eax
0x1400c0d32  mov     qword ptr [rbp+0C0h+var_A0+8], r14
0x1400c0d36  mov     rax, [rcx+10h]
0x1400c0d3a  mov     qword ptr [rbp+0C0h+var_DC+4], rax
0x1400c0d3e  movzx   eax, word ptr [rcx+0Ah]
0x1400c0d42  lea     rcx, [rbp+0C0h+var_E0]
0x1400c0d46  mov     [rbp+0C0h+var_E0], eax
0x1400c0d49  movzx   eax, word ptr [r12+2]
0x1400c0d4f  add     rax, rax
0x1400c0d52  movaps  [rsp+1C0h+var_48+8], xmm6
0x1400c0d5a  movaps  [rsp+1C0h+var_58+8], xmm7
0x1400c0d62  movaps  xmmword ptr [rsp+160h], xmm8
0x1400c0d6b  mov     dword ptr [r14+rax*8], 0Ch
0x1400c0d73  movzx   eax, word ptr [r12+2]
0x1400c0d79  add     rax, rax
0x1400c0d7c  mov     [r14+rax*8+8], rcx
0x1400c0d81  test    r9d, r9d
0x1400c0d84  jz      loc_1400C0ED7
0x1400c0d8a  mov     r8, [rbp+0C0h+var_110]
0x1400c0d8e  mov     rax, [r8+1E8h]
0x1400c0d95  add     rax, 0E0h
0x1400c0d9b  mov     qword ptr [rbp+0C0h+var_104+4], rax
0x1400c0d9f  mov     rax, [r8+1E8h]
0x1400c0da6  mov     ecx, [rax+48h]
0x1400c0da9  mov     [rbp+0C0h+var_108], ecx
0x1400c0dac  mov     rax, [r8+1E8h]
0x1400c0db3  mov     rdx, [rax+118h]
0x1400c0dba  mov     rax, [rax+90h]
0x1400c0dc1  mov     [rsp+1C0h+Size], rdx
0x1400c0dc6  test    rax, rax
0x1400c0dc9  jz      short loc_1400C0E41
0x1400c0dcb  mov     rax, [rax+8]
0x1400c0dcf  lea     r8, [rbp+0C0h+P]
0x1400c0dd3  mov     edx, 63716641h
0x1400c0dd8  mov     r13, [rax+20h]
0x1400c0ddc  movzx   eax, word ptr [r13+8]
0x1400c0de1  add     ax, 2
0x1400c0de5  movzx   eax, ax
0x1400c0de8  mov     dword ptr [rbp+0C0h+Entry], eax
0x1400c0dee  add     eax, 8
0x1400c0df1  mov     ecx, eax
0x1400c0df3  mov     dword ptr [rsp+1C0h+Size+8], eax
0x1400c0df7  call    WfpPoolAllocNonPaged
0x1400c0dfc  mov     rbx, rax
0x1400c0dff  test    rax, rax
0x1400c0e02  jnz     short loc_1400C0E57
0x1400c0e04  mov     r8d, dword ptr [rsp+1C0h+Size+8]; Size
0x1400c0e09  xor     edx, edx; Val
0x1400c0e0b  mov     rcx, [rbp+0C0h+P]; void *
  ... truncated ...
```
