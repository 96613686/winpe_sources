# WfpAlepReauthorizeOutboundConnection

- ea: `0x1400ca040`
- end: `0x1400cb7a5`
- name: `WfpAlepReauthorizeOutboundConnection`
- size: `5989`
- prototype: `__int64 __fastcall(__int64, __int16, unsigned __int16 *, __int64, int, __int64, _OWORD *, __int16, char, _DWORD **, __int128 *, __int16, __int64, __int64, __int64, unsigned __int8, __int64, int, int, __int64, int, int, int, __int64, __int64, __int64, __int64, _DWORD *, _DWORD *, _DWORD *, bool *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400c8170`

## callees

- `0x14001215c`
- `0x140012f00`
- `0x1400143c0`
- `0x140014480`
- `0x140014974`
- `0x1400162f0`
- `0x140016470`
- `0x1400611c0`
- `0x14009f27c`
- `0x1400ad6a0`
- `0x1400ca040`
- `0x1401163cc`
- `0x140141b90`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400ca343`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400cb6d3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400cb713`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400ca343`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400cb6d3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400cb713`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400ca28c`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400ca28c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400cab5f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400cab5f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400cac0a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400cac0a`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400ca0fd`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400ca0fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cac29`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb2fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb62c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cac29`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb2fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cb62c`
- `ntoskrnl!ExAllocatePool2` at `0x1400ca9b5`
- `ntoskrnl!ExAllocatePool2` at `0x1400ca9b5`
- `NETIO!FeReleaseCompletionHandle` at `0x1400cb60d`
- `NETIO!FeReleaseCompletionHandle` at `0x1400cb60d`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x1400ca453`
- `NETIO!FeAcquireGenericCompletionHandle` at `0x1400ca453`
- `NETIO!FeAcquireCompletionHandle` at `0x1400ca442`
- `NETIO!FeAcquireCompletionHandle` at `0x1400ca442`
- `NETIO!KfdAleAcquireEndpointContextFromFlow` at `0x1400ca1f5`
- `NETIO!KfdAleAcquireEndpointContextFromFlow` at `0x1400ca1f5`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400cb684`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400cb684`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x1400cb651`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x1400cb651`

## string_xrefs

- `0x1400caa8e`: `WfpAleQueryPeerTokenInformation`
- `0x1400caaf1`: `StringCchCopyA`
- `0x1400cab33`: `WfpStringCchCopyA`

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
  __int64 v44; // r8
  __int64 v45; // r9
  char *v46; // rbx
  _DWORD *v47; // rax
  _QWORD *v48; // rbx
  __int64 v49; // r8
  __int64 v50; // rax
  __int64 v51; // rcx
  int v52; // r9d
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rax
  __int64 v56; // r13
  size_t v57; // r8
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rax
  bool v61; // zf
  __int64 v62; // rax
  __int128 v63; // xmm6
  __int128 v64; // xmm7
  __int128 v65; // xmm8
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // r13
  size_t v69; // r8
  __int64 v70; // rdx
  __int64 v71; // rax
  __int64 v72; // rdx
  int v73; // eax
  int v74; // r13d
  __int64 *v75; // rcx
  __int64 v76; // rax
  __int16 v77; // cx
  bool v78; // al
  int v79; // r9d
  PKSPIN_LOCK v80; // rsi
  __int64 v81; // rax
  int v82; // r9d
  __int64 v83; // r13
  __int64 v84; // rbx
  _BYTE *v85; // rsi
  __int64 v86; // rax
  const char *v87; // rdx
  _BYTE *v88; // rcx
  char v89; // si
  _BYTE *v90; // rax
  PKSPIN_LOCK v91; // rbx
  KSPIN_LOCK v92; // rax
  unsigned int v93; // r8d
  __int64 v94; // r9
  unsigned int v95; // ecx
  __int64 v96; // rax
  int v97; // edx
  void *v98; // rbx
  int v99; // ecx
  __int64 v100; // r8
  __int64 v101; // rax
  __int64 v102; // rax
  int v103; // edx
  int v104; // edx
  int v105; // ecx
  int v106; // edx
  int v107; // ecx
  __int16 v108; // r10
  __int16 v109; // cx
  _DWORD **v110; // rsi
  PKSPIN_LOCK v111; // rbx
  int v112; // r13d
  int v113; // r9d
  int v114; // ecx
  __int64 v115; // rbx
  __int64 v116; // rdx
  int v117; // r8d
  __int64 v118; // rdx
  unsigned int v119; // eax
  int v120; // ecx
  int v121; // eax
  __int64 v122; // rcx
  __int64 v123; // rax
  __int64 v124; // rcx
  __int64 v125; // r13
  __int64 v126; // rbx
  _DWORD *v127; // rsi
  int v128; // r9d
  int v129; // r8d
  __int64 v130; // rax
  __int64 v131; // rcx
  __int64 *v132; // r13
  __int64 v133; // rcx
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rcx
  __int64 v137; // rcx
  __int64 v138; // rax
  int v139; // r9d
  char v140; // dl
  __int128 v141; // xmm0
  __int64 v142; // rcx
  __int128 v143; // xmm1
  __int128 v144; // xmm2
  __int64 *v145; // r8
  int v146; // r8d
  __int128 *v147; // rcx
  __int128 v148; // xmm0
  char v149; // al
  int v150; // r8d
  unsigned __int128 v151; // rax
  __int64 v152; // rax
  __int64 v153; // r8
  PVOID *v154; // rsi
  __int64 v155; // r8
  __int64 v156; // r9
  char *v157; // rsi
  __int64 v158; // r8
  __int64 v159; // r9
  char *v160; // rdi
  __int16 v162; // [rsp+68h] [rbp-A0h]
  char v163; // [rsp+6Ah] [rbp-9Eh]
  int v164; // [rsp+6Ch] [rbp-9Ch]
  int v165; // [rsp+70h] [rbp-98h]
  __int64 Size; // [rsp+78h] [rbp-90h] BYREF
  size_t Size_8[2]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v168; // [rsp+90h] [rbp-78h] BYREF
  __int64 v169; // [rsp+98h] [rbp-70h]
  int v170; // [rsp+A0h] [rbp-68h]
  BOOL v171; // [rsp+A4h] [rbp-64h]
  PKSPIN_LOCK SpinLock; // [rsp+A8h] [rbp-60h]
  __int64 v173; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v174; // [rsp+B8h] [rbp-50h]
  __int64 v175; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v176; // [rsp+C8h] [rbp-40h]
  __int64 v177; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v178; // [rsp+D8h] [rbp-30h]
  __int64 v179; // [rsp+E0h] [rbp-28h]
  __int64 v180; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v181; // [rsp+F0h] [rbp-18h]
  __int64 v182; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v183; // [rsp+100h] [rbp-8h]
  __int64 v184; // [rsp+108h] [rbp+0h] BYREF
  __int64 v185; // [rsp+110h] [rbp+8h]
  __int64 v186; // [rsp+118h] [rbp+10h] BYREF
  __int64 v187; // [rsp+120h] [rbp+18h]
  __int128 v188; // [rsp+128h] [rbp+20h] BYREF
  __int128 v189; // [rsp+138h] [rbp+30h] BYREF
  __int64 v190; // [rsp+148h] [rbp+40h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+150h] [rbp+48h] BYREF
  PVOID Entry; // [rsp+1D8h] [rbp+D0h] BYREF
  __int16 v193; // [rsp+1E0h] [rbp+D8h]
  __int16 v194; // [rsp+1F0h] [rbp+E8h]

  v194 = a4;
  v193 = a2;
  v31 = 0;
  v33 = 0;
  Entry = 0;
  LODWORD(v181) = 0;
  v35 = 0;
  LODWORD(v176) = 0;
  LODWORD(v187) = 0;
  LODWORD(v183) = 0;
  LODWORD(v185) = 0;
  LODWORD(v169) = 0;
  v180 = 0;
  v175 = 0;
  v186 = 0;
  v182 = 0;
  v184 = 0;
  v168 = 0;
  v162 = 0;
  v190 = 0;
  v173 = 0;
  Size = 0;
  v174 = 0;
  v177 = 0;
  *(_OWORD *)Size_8 = 0;
  v188 = 0;
  v189 = 0;
  if ( dword_140224310 )
  {
    v36 = KeQueryInterruptTimePrecise(&v177);
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
    v42 = KfdAleAcquireEndpointContextFromFlow(*(_QWORD *)(v38 + 504), &WPP_GLOBAL_Control);
    v174 = v42;
    v35 = v42;
    if ( v42 )
      v38 = *(_QWORD *)(v42 + 448);
  }
  if ( (*(_DWORD *)(a1 + 52) & 0x2000) == 0
    || (*(_DWORD *)(a1 + 52) & 0x10000) != 0
    || (*(_DWORD *)(a1 + 48) & 0x1000000) != 0
    || (v165 = 1, !v38) )
  {
    v165 = 0;
  }
  if ( (*(_DWORD *)(a1 + 52) & 0x10000) == 0 || (*(_DWORD *)(a1 + 48) & 0x1000000) != 0 || !v35 || (v164 = 1, !v38) )
    v164 = 0;
  if ( KeGetCurrentIrql() < 2u )
  {
    LOBYTE(v162) = WfpRaiseIrqlToDispatchLevel();
    HIBYTE(v162) = 1;
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
    v47 = v31 + 156;
    *((_QWORD *)v31 + 79) = v31 + 156;
    *((_QWORD *)v31 + 78) = v31 + 156;
    LODWORD(v47) = HIDWORD(KeGetPcr()[1].LockArray);
    v48 = (_QWORD *)*((_QWORD *)gPerProcessorContext + 9 * (_QWORD)v47 + 5);
    memset(v48, 0, 0x158u);
    v50 = a17;
    v48[9] = v36;
    if ( v50 && FeAcquireCompletionHandle(v50, &v173) )
      v173 = FeAcquireGenericCompletionHandle();
    v51 = *(_QWORD *)(a1 + 480);
    v52 = v164;
    LOWORD(v188) = v193;
    DWORD1(v188) = *a3;
    *((_QWORD *)&v188 + 1) = v33;
    v181 = *(_QWORD *)(v51 + 16);
    LODWORD(v180) = *(unsigned __int16 *)(v51 + 10);
    *(_DWORD *)&v33[16 * a3[1]] = 12;
    *(_QWORD *)&v33[16 * a3[1] + 8] = &v180;
    if ( v164 )
    {
      v49 = v174;
      v176 = *(_QWORD *)(v174 + 488) + 224LL;
      LODWORD(v175) = *(_DWORD *)(*(_QWORD *)(v174 + 488) + 72LL);
      v53 = *(_QWORD *)(v174 + 488);
      v54 = *(_QWORD *)(v53 + 280);
      v55 = *(_QWORD *)(v53 + 144);
      Size = v54;
      if ( !v55 )
      {
LABEL_57:
        v58 = *(_QWORD *)(v49 + 728);
        if ( v58 )
          v169 = v58 + 104;
        else
          v169 = 0;
        v59 = *(_QWORD *)(v49 + 728);
        v60 = -1;
        if ( v59 )
        {
          do
            v61 = *(_WORD *)(v59 + 2 * v60++ + 106) == 0;
          while ( !v61 );
          LODWORD(v168) = 2 * v60 + 2;
        }
        else
        {
          LODWORD(v168) = 0;
        }
        v62 = *(_QWORD *)(v49 + 488);
        v63 = *(_OWORD *)(v62 + 160);
        v163 = *(_BYTE *)(v62 + 152);
        v64 = *(_OWORD *)(v62 + 192);
        v177 = *(_QWORD *)(v62 + 176);
        v65 = *(_OWORD *)(v62 + 208);
        goto LABEL_75;
      }
      v56 = *(_QWORD *)(*(_QWORD *)(v55 + 8) + 32LL);
      LODWORD(Entry) = (unsigned __int16)(*(_WORD *)(v56 + 8) + 2);
      LODWORD(Size_8[0]) = (_DWORD)Entry + 8;
      v39 = WfpPoolAllocNonPaged((unsigned int)((_DWORD)Entry + 8), 1668376129, &Size_8[1]);
      if ( !v39 )
      {
        memset((void *)Size_8[1], 0, LODWORD(Size_8[0]));
        v57 = (unsigned __int16)Entry;
        *(_QWORD *)Size_8[1] = *(_QWORD *)v56;
        memmove((void *)(Size_8[1] + 8), *(const void **)(v56 + 16), v57);
        v49 = v174;
        v52 = v164;
        goto LABEL_57;
      }
LABEL_59:
      LOBYTE(v38) = 1;
      goto LABEL_242;
    }
    v66 = *(_QWORD *)(a1 + 488);
    v176 = v66 + 224;
    LODWORD(v175) = *(_DWORD *)(v66 + 72);
    v67 = *(_QWORD *)(v66 + 144);
    Size = *(_QWORD *)(v66 + 280);
    if ( v67 )
    {
      v68 = *(_QWORD *)(*(_QWORD *)(v67 + 8) + 32LL);
      LODWORD(Entry) = (unsigned __int16)(*(_WORD *)(v68 + 8) + 2);
      LODWORD(Size_8[0]) = (_DWORD)Entry + 8;
      v39 = WfpPoolAllocNonPaged((unsigned int)((_DWORD)Entry + 8), 1668376129, &Size_8[1]);
      if ( v39 )
        goto LABEL_59;
      memset((void *)Size_8[1], 0, LODWORD(Size_8[0]));
      v69 = (unsigned __int16)Entry;
      *(_QWORD *)Size_8[1] = *(_QWORD *)v68;
      memmove((void *)(Size_8[1] + 8), *(const void **)(v68 + 16), v69);
      v66 = *(_QWORD *)(a1 + 488);
      v52 = 0;
    }
    v70 = *(_QWORD *)(a1 + 728);
    v71 = -1;
    if ( v70 )
    {
      v72 = v70 + 104;
      v169 = v72;
      do
        v61 = *(_WORD *)(v72 + 2 * v71++ + 2) == 0;
      while ( !v61 );
      v73 = 2 * v71 + 2;
    }
    else
    {
      v73 = 0;
      v169 = 0;
    }
    LODWORD(v168) = v73;
    v63 = *(_OWORD *)(v66 + 160);
    v163 = *(_BYTE *)(v66 + 152);
    v64 = *(_OWORD *)(v66 + 192);
    v177 = *(_QWORD *)(v66 + 176);
    v65 = *(_OWORD *)(v66 + 208);
LABEL_75:
    v74 = v165;
    v75 = gAleNullSid;
    if ( Size )
      v75 = (__int64 *)Size;
    *(_DWORD *)&v33[16 * a3[39]] = 12;
    *(_QWORD *)&v33[16 * a3[39] + 8] = &v168;
    *(_DWORD *)&v33[16 * a3[2]] = 16;
    *(_QWORD *)&v33[16 * a3[2] + 8] = &v175;
    *(_DWORD *)&v33[16 * a3[37]] = 13;
    *(_QWORD *)&v33[16 * a3[37] + 8] = v75;
    *(_DWORD *)&v33[16 * a3[41]] = 16;
    *(_QWORD *)&v33[16 * a3[41] + 8] = &v175;
    *(_DWORD *)&v33[16 * a3[38]] = 12;
    *(_QWORD *)&v33[16 * a3[38] + 8] = Size_8;
    *(_OWORD *)&v33[16 * a3[3]] = *a7;
    if ( v165 || v52 )
    {
      v61 = *(_WORD *)(v38 + 72) == 23;
      v171 = *a31;
      if ( v61 )
        v78 = !*(_WORD *)(v38 + 80)
           && !*(_WORD *)(v38 + 82)
           && !*(_WORD *)(v38 + 84)
           && !*(_WORD *)(v38 + 86)
           && !*(_WORD *)(v38 + 88)
           && !*(_WORD *)(v38 + 90)
           && !*(_WORD *)(v38 + 92)
           && *(_WORD *)(v38 + 94) == 256;
      else
        v78 = *(_BYTE *)(v38 + 76) == 127;
      v79 = (int)a11;
      *a31 = v78;
      v39 = WfpAlepAuthOutboundFlowSwizzleDestinationInformation((_DWORD)a3, v38, v49, v79, (__int64)v33);
      LOBYTE(v38) = 1;
      if ( v39 )
        goto LABEL_242;
    }
    else
    {
      v76 = 2LL * a3[7];
      v171 = 0;
      v77 = __ROR2__(a12, 8);
      *(_OWORD *)&v33[8 * v76] = *a11;
      *(_DWORD *)&v33[16 * a3[8]] = 2;
      *(_WORD *)&v33[16 * a3[8] + 8] = v77;
    }
    v80 = SpinLock;
    v81 = 2LL * a3[6];
    v82 = a5;
    v170 = 0;
    *(_DWORD *)&v33[8 * v81] = 1;
    v33[16 * a3[6] + 8] = v82;
    if ( v80[32] )
    {
      *(_DWORD *)&v33[16 * a3[33]] = 12;
      *(_QWORD *)&v33[16 * a3[33] + 8] = *(_QWORD *)(v80[32] + 64);
      v170 = *(unsigned __int8 *)(v80[32] + 2);
    }
    v61 = v80[31] == 0;
    LOBYTE(Entry) = 1;
    if ( !v61 )
    {
      v179 = 0;
      memset(&LockHandle, 0, sizeof(LockHandle));
      v83 = 0;
      v178 = 0;
      if ( gAleDebugEnabled )
      {
        v84 = 32;
        Size = ExAllocatePool2(64, 32, 1281715265);
        v85 = (_BYTE *)Size;
        if ( Size )
          goto LABEL_106;
        v83 = -1073741801;
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
          if ( !v83 )
          {
            v86 = 2147483646;
            LOBYTE(Entry) = 1;
            v87 = "WfpAleQueryPeerTokenInformation";
            v88 = v85;
            do
            {
              if ( !v86 )
                break;
              if ( !*v87 )
                break;
              *v88++ = *v87++;
              --v86;
              --v84;
            }
            while ( v84 );
            v89 = 122;
            if ( v84 )
              v89 = 0;
            v90 = v88 - 1;
            if ( v84 )
              v90 = v88;
            *v90 = 0;
            if ( !v84 )
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
                  v89);
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
                  v89);
              }
            }
            v85 = (_BYTE *)Size;
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
        v85 = 0;
        LOBYTE(Entry) = 1;
      }
      v91 = SpinLock;
      KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
      while ( *((_DWORD *)v91 + 2) )
        ;
      v61 = gAleDebugEnabled == 1;
      v91[2] = (KSPIN_LOCK)KeGetCurrentThread();
      if ( v61 && !v83 )
        v91[3] = (KSPIN_LOCK)v85;
      v92 = v91[31];
      v80 = v91;
      v93 = *(_DWORD *)v92;
      if ( *(_DWORD *)v92 )
      {
        v94 = *(_QWORD *)(v92 + 8);
        v95 = 0;
        do
        {
          v96 = 32LL * v95;
          v97 = *(_DWORD *)(v96 + v94 + 8);
          if ( v97 )
          {
            if ( v97 == 1 )
              v178 = *(_QWORD *)(v96 + v94 + 24);
          }
          else
          {
            v179 = *(_QWORD *)(v96 + v94 + 24);
          }
          ++v95;
        }
        while ( v95 < v93 );
      }
      v61 = gAleDebugEnabled == 1;
      v98 = 0;
      v80[2] = 0;
      if ( v61 )
      {
        v98 = (void *)v80[3];
        v80[3] = 0;
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( gAleDebugEnabled == 1 && v98 )
        ExFreePoolWithTag(v98, 0);
      if ( v178 )
      {
        v183 = v178 + 224;
        LODWORD(v182) = *(_DWORD *)(v178 + 72);
        *(_DWORD *)&v33[16 * a3[9]] = 16;
        *(_QWORD *)&v33[16 * a3[9] + 8] = &v182;
      }
      v82 = a5;
      v74 = v165;
      if ( v179 )
      {
        v185 = v179 + 224;
        LODWORD(v184) = *(_DWORD *)(v179 + 72);
        *(_DWORD *)&v33[16 * a3[10]] = 16;
        *(_QWORD *)&v33[16 * a3[10] + 8] = &v184;
      }
    }
    v99 = 0;
    v100 = a15;
    v61 = a15 == 0;
    *(_DWORD *)&v33[16 * a3[16]] = 3;
    v101 = v100;
    if ( v61 )
      v101 = a1;
    if ( v101 != -168 )
    {
      LOBYTE(Entry) = 1;
      if ( v100 )
      {
        v102 = v100 + 168;
      }
      else
      {
        v102 = a1 + 168;
        LOBYTE(Entry) = 1;
      }
      v99 = 2 * (*(_DWORD *)(v102 + 32) & 1);
      if ( (*(_DWORD *)(v102 + 32) & 0x800) != 0 )
        v99 |= 0x10000u;
    }
    v103 = v99 | 1;
    if ( !*a31 )
      v103 = v99;
    v104 = v103 | 4;
    v105 = v104 | 0x10;
    if ( (*(_DWORD *)(a1 + 48) & 0x10) == 0 )
      v105 = v104;
    v106 = v105 | 0x4000;
    if ( !v170 )
      v106 = v105;
    if ( (*((_DWORD *)v80 + 13) & 0x2000) != 0 )
      v106 |= 0x100000u;
    v107 = v106 | 0x200000;
    if ( (*((_DWORD *)v80 + 13) & 0x10000) == 0 )
      v107 = v106;
    *(_DWORD *)&v33[16 * a3[16] + 8] = v107;
    if ( v74 || v164 )
      *(_DWORD *)&v33[16 * a3[16] + 8] |= 0x2000000u;
    v108 = v194;
    if ( v194 == 2 )
    {
      if ( v82 != 1 )
      {
LABEL_170:
        v109 = __ROR2__(a8, 8);
        *(_DWORD *)&v33[16 * a3[5]] = 2;
        *(_WORD *)&v33[16 * a3[5] + 8] = v109;
        *(_DWORD *)&v33[16 * a3[34]] = 0;
        goto LABEL_171;
      }
    }
    else if ( v194 != 23 || v82 != 58 )
    {
      goto LABEL_170;
    }
    v118 = a13;
    *(_DWORD *)&v33[16 * a3[5]] = 2;
    *(_WORD *)&v33[16 * a3[5] + 8] = *(unsigned __int8 *)(v118 + 4);
    *(_DWORD *)&v33[16 * a3[8]] = 2;
    *(_WORD *)&v33[16 * a3[8] + 8] = *(unsigned __int8 *)(v118 + 5);
    *(_DWORD *)&v33[16 * a3[34]] = 2;
    *(_WORD *)&v33[16 * a3[34] + 8] = *(unsigned __int8 *)(v100 + 570);
    v119 = *(unsigned __int8 *)(v118 + 4);
    if ( v108 == 2 )
    {
      if ( (unsigned __int8)v119 <= 0x12u )
      {
        v120 = 418049;
        if ( _bittest(&v120, v119) )
        {
          *v31 |= 0x8000000u;
          v31[50] = *(_DWORD *)v118;
        }
      }
    }
    else if ( (unsigned __int8)(v119 + 0x80) <= 1u )
    {
      *v31 |= 0x8000000u;
      v31[50] = *(_DWORD *)v118;
    }
LABEL_171:
    v110 = a10;
    v111 = SpinLock;
    v112 = a23;
    v113 = a25;
    *(_DWORD *)&v33[16 * a3[4]] = 1;
    v33[16 * a3[4] + 8] = a9;
    *(_DWORD *)&v33[16 * a3[12]] = 4;
    *(_QWORD *)&v33[16 * a3[12] + 8] = v110 + 2;
    *(_DWORD *)&v33[16 * a3[13]] = 3;
    *(_DWORD *)&v33[16 * a3[13] + 8] = v110[6][3];
    *(_DWORD *)&v33[16 * a3[14]] = 3;
    *(_DWORD *)&v33[16 * a3[14] + 8] = v110[6][4];
    *(_DWORD *)&v33[16 * a3[19]] = 3;
    *(_DWORD *)&v33[16 * a3[19] + 8] = *((_DWORD *)v110 + 2);
    v114 = *((_DWORD *)v111 + 83);
    v115 = a20;
    v116 = a20;
    v117 = a20;
    if ( v112 )
      v116 = 0;
    *a29 = v114;
    if ( v112 != 1 )
      v117 = 0;
    AlepFillEdgeInterfaceRelatedFields(v114, (_DWORD)a3, v117, v113, v116, a6, a24, a21, a21, v114, a22, (__int64)v33);
    if ( *(_DWORD *)&v33[16 * a3[31]] )
      *a30 = *(_DWORD *)&v33[16 * a3[31] + 8];
    if ( v115 )
    {
      *(_DWORD *)&v33[16 * a3[35]] = 4;
      *(_QWORD *)&v33[16 * a3[35] + 8] = v115 + 80;
    }
    else
    {
      *(_DWORD *)&v33[16 * a3[35]] = 0;
    }
    *(_DWORD *)&v33[16 * a3[40]] = 3;
    *(_DWORD *)&v33[16 * a3[40] + 8] = **v110;
    if ( *(_DWORD *)(a1 + 680) == 1 )
      v31[1] |= 0x80000u;
    *v31 |= 0x80u;
    *((_QWORD *)v31 + 1) = &v189;
    *v31 |= 0x20u;
    *((_QWORD *)v31 + 8) = *(_QWORD *)(*(_QWORD *)(a1 + 480) + 32LL);
    *v31 |= 0x800u;
    v121 = a18;
    v31[20] = **v110;
    *v31 |= 4u;
    v31[10] = v121;
    *v31 |= 0x400u;
    v31[11] = a19;
    v122 = *(_QWORD *)(a1 + 480);
    v187 = *(_QWORD *)(v122 + 16);
    LODWORD(v186) = *(unsigned __int16 *)(v122 + 10);
    *v31 |= 8u;
    *((_QWORD *)v31 + 6) = &v186;
    *v31 |= 0x10u;
    v123 = a14;
    *((_QWORD *)v31 + 7) = *(_QWORD *)(*(_QWORD *)(a1 + 488) + 64LL);
    *v31 |= 2u;
    v124 = a27;
    *((_QWORD *)v31 + 4) = v123;
    *v31 |= 0x4000u;
    *((_QWORD *)v31 + 13) = v173;
    *v31 |= 0x40000u;
    v31[35] = v112;
    if ( v124 )
    {
      *v31 |= 0x20000000u;
      *((_QWORD *)v31 + 26) = v124 + 72;
      if ( *(_DWORD *)(v124 + 464) )
      {
        *v31 |= 0x10000000u;
        v31[51] = *(_DWORD *)(v124 + 464);
      }
      *v31 |= 0x40000000u;
      *((_QWORD *)v31 + 27) = v124;
    }
    v125 = a15;
    v126 = a26;
    if ( a15 )
    {
      *(_QWORD *)&v189 = a15;
    }
    else
    {
      *(_QWORD *)&v189 = a1;
      if ( a26 )
      {
        v137 = *(_QWORD *)(a1 + 544);
        if ( v137 )
          *(_QWORD *)(v126 + 48) = WfpAleQueryOrInsertEndpointHandle(v137);
        else
          *(_QWORD *)(a26 + 48) = 0;
        BYTE8(v189) = 0;
LABEL_197:
        *v31 |= 0x8000u;
        *((_QWORD *)v31 + 14) = *(_QWORD *)v126;
        if ( *(_QWORD *)(v126 + 48) )
        {
          *v31 |= 0x4000000u;
          *((_QWORD *)v31 + 24) = *(_QWORD *)(v126 + 48);
        }
        if ( *(_DWORD *)(v126 + 8) )
        {
          *v31 |= 0x20000u;
          v31[30] = *(_DWORD *)(v126 + 8);
        }
        if ( *(_QWORD *)(v126 + 16) )
        {
          *v31 |= 0x10000u;
          *((_QWORD *)v31 + 16) = *(_QWORD *)(v126 + 16);
          v31[34] = *(_DWORD *)(v126 + 24);
        }
        if ( *(_QWORD *)(v126 + 32) )
        {
          *v31 |= 0x800000u;
          *((_QWORD *)v31 + 18) = *(_QWORD *)(v126 + 32);
          v31[38] = *(_DWORD *)(v126 + 40);
        }
LABEL_205:
        if ( *(_DWORD *)(a1 + 40) == 6 && (*(_DWORD *)(a1 + 48) & 0x10) == 0 )
          *((_QWORD *)v31 + 63) = *(_QWORD *)(a1 + 352);
        v127 = a28;
        v128 = a16;
        v129 = a25;
        *((_BYTE *)v31 + 592) = v163;
        v130 = v177;
        *(_OWORD *)(v31 + 150) = v63;
        *((_QWORD *)v31 + 77) = v130;
        *(_OWORD *)(v31 + 162) = v64;
        *(_OWORD *)(v31 + 166) = v65;
        v39 = WfpAleClassify((unsigned int)&v188, (_DWORD)v31, v129, v128, 0, (__int64)v127);
        if ( v39 )
          goto LABEL_241;
        if ( *v127 != 4097 && (v165 || v164) )
        {
          if ( v171 )
            *(_DWORD *)&v33[16 * a3[16] + 8] |= 1u;
          *(_DWORD *)&v33[16 * a3[16] + 8] &= ~0x2000000u;
          if ( Size_8[1] )
          {
            ExFreePoolWithTag((PVOID)Size_8[1], 0);
            Size_8[1] = 0;
            LODWORD(Size_8[0]) = 0;
          }
          v131 = *(_QWORD *)(a1 + 488);
          v176 = v131 + 224;
          LODWORD(v175) = *(_DWORD *)(v131 + 72);
          v132 = *(__int64 **)(v131 + 280);
          v133 = *(_QWORD *)(v131 + 144);
          if ( v133 )
          {
            v39 = WfpAleMarshalFqbnValue(*(_QWORD *)(*(_QWORD *)(v133 + 8) + 32LL), Size_8);
            if ( v39 )
              goto LABEL_241;
          }
          v134 = *(_QWORD *)(a1 + 728);
          if ( v134 )
          {
            v135 = v134 + 104;
            v136 = -1;
            v169 = v135;
            do
              v61 = *(_WORD *)(v135 + 2 * v136++ + 2) == 0;
            while ( !v61 );
            LODWORD(v134) = 2 * v136 + 2;
          }
          else
          {
            v169 = 0;
          }
          LODWORD(v168) = v134;
          v138 = *(_QWORD *)(a1 + 488);
          v139 = a16;
          v140 = *(_BYTE *)(v138 + 152);
          v141 = *(_OWORD *)(v138 + 160);
          v142 = *(_QWORD *)(v138 + 176);
          v143 = *(_OWORD *)(v138 + 192);
          v144 = *(_OWORD *)(v138 + 208);
          *(_DWORD *)&v33[16 * a3[2]] = 16;
          *(_QWORD *)&v33[16 * a3[2] + 8] = &v175;
          v145 = gAleNullSid;
          if ( v132 )
            v145 = v132;
          *(_DWORD *)&v33[16 * a3[37]] = 13;
          *(_QWORD *)&v33[16 * a3[37] + 8] = v145;
          *(_DWORD *)&v33[16 * a3[39]] = 12;
          *(_QWORD *)&v33[16 * a3[39] + 8] = &v168;
          *(_DWORD *)&v33[16 * a3[38]] = 12;
          *(_QWORD *)&v33[16 * a3[38] + 8] = Size_8;
          v146 = a25;
          *((_BYTE *)v31 + 592) = v140;
          *(_OWORD *)(v31 + 150) = v141;
          *((_QWORD *)v31 + 77) = v142;
          v147 = a11;
          *(_OWORD *)(v31 + 162) = v143;
          *(_OWORD *)(v31 + 166) = v144;
          v148 = *v147;
          LOWORD(v147) = __ROR2__(a12, 8);
          *(_OWORD *)&v33[16 * a3[7]] = v148;
          *(_DWORD *)&v33[16 * a3[8]] = 2;
          *(_WORD *)&v33[16 * a3[8] + 8] = (_WORD)v147;
          v39 = WfpAleClassify((unsigned int)&v188, (_DWORD)v31, v146, v139, 0, (__int64)v127);
          if ( v39 )
            goto LABEL_241;
          v125 = a15;
        }
        if ( *(_DWORD *)(a1 + 40) != 6 || (*(_DWORD *)(a1 + 48) & 0x10) != 0 )
        {
          v149 = *(_BYTE *)(v125 + 492);
          LOBYTE(v38) = (_BYTE)Entry;
          if ( v149 == 1 )
          {
            v40 = HIBYTE(v162);
            v41 = v162;
            if ( v31[84] != 3 )
              goto LABEL_243;
            v150 = v31[86];
            goto LABEL_237;
          }
          if ( (v149 & 2) != 0 )
          {
            v40 = HIBYTE(v162);
            v41 = v162;
            if ( v31[88] != 3 )
              goto LABEL_243;
            v150 = v31[90];
LABEL_237:
            v151 = MEMORY[0xFFFFF78000000008] * (unsigned __int128)0x346DC5D63886594BuLL;
            *(_DWORD *)(v125 + 532) = v150;
            _InterlockedExchange64((volatile __int64 *)(v125 + 544), *((_QWORD *)&v151 + 1) >> 11);
            goto LABEL_243;
          }
LABEL_242:
          v41 = v162;
          v40 = HIBYTE(v162);
          goto LABEL_243;
        }
LABEL_241:
        LOBYTE(v38) = (_BYTE)Entry;
        goto LABEL_242;
      }
    }
    BYTE8(v189) = 0;
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
    v46 = (char *)gIncomingValuesLookasideList
        + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v46[176] )
      PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v46 + 64, v44, v45);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v46 + 64), Entry);
  }
  v40 = HIBYTE(v162);
  LOBYTE(v38) = 0;
  v41 = v162;
  v31 = 0;
  if ( HIBYTE(v162) )
    WfpLowerIrqlFromDispatchLevel((unsigned __int8)v162);
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
  v152 = WfpAlepAuthTelemetry(a17, 0, 0, a4);
  if ( v173 )
  {
    v152 = FeReleaseCompletionHandle();
    v173 = 0;
  }
  if ( Size_8[1] )
  {
    ExFreePoolWithTag((PVOID)Size_8[1], 0);
    Size_8[1] = 0;
    LODWORD(Size_8[0]) = 0;
  }
  if ( v174 )
    v152 = KfdAleReleaseFlowHandleForFlow(v174);
  if ( (_BYTE)v38 )
  {
    LODWORD(v152) = HIDWORD(KeGetPcr()[1].LockArray);
    v154 = (PVOID *)((char *)gPerProcessorContext + 72 * v152);
    KfdReleaseTerminatingFilters(v31 + 156, 9 * v152, v153);
    if ( v33 == v154[3] )
    {
      *((_BYTE *)v154 + 32) = 0;
    }
    else
    {
      v157 = (char *)gMetadataLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v157[176] )
        PplpLazyInitializeLookasideList(gMetadataLookasideList, v157 + 64, v155, v156);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v157 + 64), v31);
      v160 = (char *)gIncomingValuesLookasideList
           + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
      if ( !v160[176] )
        PplpLazyInitializeLookasideList(gIncomingValuesLookasideList, v160 + 64, v158, v159);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v160 + 64), v33);
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
0x1400ca040  mov     rax, rsp
0x1400ca043  mov     [rax+20h], r9w
0x1400ca048  mov     [rax+10h], dx
0x1400ca04c  push    rbp
0x1400ca04d  push    rbx
0x1400ca04e  push    r13
0x1400ca050  lea     rbp, [rax-0C8h]
0x1400ca057  sub     rsp, 1B0h
0x1400ca05e  mov     [rax+18h], rsi
0x1400ca062  xorps   xmm0, xmm0
0x1400ca065  mov     [rax-20h], rdi
0x1400ca069  mov     rdx, 0FFFFF78000000008h
0x1400ca073  mov     [rax-28h], r12
0x1400ca077  xor     edi, edi
0x1400ca079  mov     [rax-30h], r14
0x1400ca07d  mov     r12, r8
0x1400ca080  mov     [rax-38h], r15
0x1400ca084  xor     r14d, r14d
0x1400ca087  xor     eax, eax
0x1400ca089  mov     [rbp+0C0h+Entry], r14
0x1400ca090  mov     qword ptr [rbp+0C0h+var_DC], rax
0x1400ca094  mov     r15, rcx
0x1400ca097  xor     ecx, ecx
0x1400ca099  mov     qword ptr [rbp+0C0h+var_104], rax
0x1400ca09d  mov     qword ptr [rbp+0C0h+var_AC], rax
0x1400ca0a1  mov     qword ptr [rbp+0C0h+var_CC], rax
0x1400ca0a5  mov     qword ptr [rbp+0C0h+var_BC], rax
0x1400ca0a9  mov     qword ptr [rbp+0C0h+var_134], rax
0x1400ca0ad  mov     [rbp-20h], rax
0x1400ca0b1  mov     [rbp-48h], rax
0x1400ca0b5  mov     [rbp+10h], rax
0x1400ca0b9  mov     [rbp-10h], rax
0x1400ca0bd  mov     [rbp+0], rax
0x1400ca0c1  mov     [rbp-78h], rax
0x1400ca0c5  mov     byte ptr [rsp+1C0h+var_160], al
0x1400ca0c9  mov     byte ptr [rsp+1C0h+var_160+1], al
0x1400ca0cd  mov     [rbp+0C0h+var_80], rax
0x1400ca0d1  mov     [rbp+0C0h+var_118], rax
0x1400ca0d5  mov     eax, cs:dword_140224310
0x1400ca0db  mov     [rsp+1C0h+Size], rdi
0x1400ca0e0  mov     [rbp+0C0h+var_110], rcx
0x1400ca0e4  mov     [rbp+0C0h+var_F8], rcx
0x1400ca0e8  movups  xmmword ptr [rsp+1C0h+Size+8], xmm0
0x1400ca0ed  movups  [rbp+0C0h+var_A0], xmm0
0x1400ca0f1  movups  [rbp+0C0h+var_90], xmm0
0x1400ca0f5  test    eax, eax
0x1400ca0f7  jz      short loc_1400CA110
0x1400ca0f9  lea     rcx, [rbp+0C0h+var_F8]
0x1400ca0fd  call    cs:__imp_KeQueryInterruptTimePrecise
0x1400ca104  nop     dword ptr [rax+rax+00h]
0x1400ca109  mov     r13, rax
0x1400ca10c  mov     ecx, edi
0x1400ca10e  jmp     short loc_1400CA113
0x1400ca110  mov     r13, [rdx]
0x1400ca113  cmp     dword ptr [r15+28h], 6
0x1400ca118  jnz     short loc_1400CA12C
0x1400ca11a  mov     eax, [r15+30h]
0x1400ca11e  test    al, 10h
0x1400ca120  jnz     short loc_1400CA12C
0x1400ca122  mov     eax, [r15+30h]
0x1400ca126  mov     [rbp+0C0h+SpinLock], r15
0x1400ca12a  jmp     short loc_1400CA13A
0x1400ca12c  mov     rbx, [rbp+0C0h+arg_70]
0x1400ca133  mov     [rbp+0C0h+SpinLock], rbx
0x1400ca137  mov     eax, [rbx+30h]
0x1400ca13a  mov     rdx, [rbp+0C0h+arg_F0]
0x1400ca141  shr     eax, 18h
0x1400ca144  and     al, 1
0x1400ca146  mov     [rdx], al
0x1400ca148  lea     rdx, WPP_GLOBAL_Control
0x1400ca14f  mov     eax, [r15+34h]
0x1400ca153  bt      eax, 10h
0x1400ca157  jnb     loc_1400CA216
0x1400ca15d  mov     eax, [r15+34h]
0x1400ca161  bt      eax, 0Dh
0x1400ca165  jnb     short loc_1400CA175
0x1400ca167  mov     eax, [r15+30h]
0x1400ca16b  bt      eax, 18h
0x1400ca16f  jb      loc_1400CA216
0x1400ca175  mov     rsi, [r15+1C0h]
0x1400ca17c  test    rsi, rsi
0x1400ca17f  jnz     short loc_1400CA1E0
0x1400ca181  mov     rax, [rbp+0C0h+arg_D8]
0x1400ca188  mov     dword ptr [rax], 1001h
0x1400ca18e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca195  mov     rbx, 0FFFFFFFFC0000022h
0x1400ca19c  cmp     rcx, rdx
0x1400ca19f  jz      short loc_1400CA1D0
0x1400ca1a1  cmp     byte ptr [rcx+29h], 2
0x1400ca1a5  jb      short loc_1400CA1D0
0x1400ca1a7  test    dword ptr [rcx+2Ch], 1000h
0x1400ca1ae  jz      short loc_1400CA1D0
0x1400ca1b0  mov     rcx, [rcx+18h]
0x1400ca1b4  lea     r9, aWfpalepreautho; "WfpAlepReauthorizeOutboundConnection"
0x1400ca1bb  mov     edx, 0Ah
0x1400ca1c0  mov     dword ptr [rsp+1C0h+var_1A0], ebx
0x1400ca1c4  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400ca1cb  call    WPP_SF_sd
0x1400ca1d0  xor     r15b, r15b
0x1400ca1d3  xor     r12b, r12b
0x1400ca1d6  jmp     loc_1400CB5E9
0x1400ca1e0  mov     rax, [rsi+30h]
0x1400ca1e4  test    rax, rax
0x1400ca1e7  jz      short loc_1400CA1EE
0x1400ca1e9  mov     rsi, rax
0x1400ca1ec  jmp     short loc_1400CA1E0
0x1400ca1ee  mov     rcx, [rsi+1F8h]
0x1400ca1f5  call    cs:__imp_KfdAleAcquireEndpointContextFromFlow
0x1400ca1fc  nop     dword ptr [rax+rax+00h]
0x1400ca201  mov     [rbp+0C0h+var_110], rax
0x1400ca205  mov     rcx, rax
0x1400ca208  test    rax, rax
0x1400ca20b  jz      short loc_1400CA233
0x1400ca20d  mov     rsi, [rax+1C0h]
0x1400ca214  jmp     short loc_1400CA233
0x1400ca216  mov     eax, [r15+34h]
0x1400ca21a  xor     esi, esi
0x1400ca21c  bt      eax, 0Dh
0x1400ca220  jnb     short loc_1400CA233
0x1400ca222  mov     eax, [r15+34h]
0x1400ca226  bt      eax, 10h
0x1400ca22a  jb      short loc_1400CA233
0x1400ca22c  mov     rsi, [r15+1C0h]
0x1400ca233  mov     eax, [r15+34h]
0x1400ca237  bt      eax, 0Dh
0x1400ca23b  jnb     short loc_1400CA25E
0x1400ca23d  mov     eax, [r15+34h]
0x1400ca241  bt      eax, 10h
0x1400ca245  jb      short loc_1400CA25E
0x1400ca247  mov     eax, [r15+30h]
0x1400ca24b  bt      eax, 18h
0x1400ca24f  jb      short loc_1400CA25E
0x1400ca251  mov     dword ptr [rsp+1C0h+var_158], 1
0x1400ca259  test    rsi, rsi
0x1400ca25c  jnz     short loc_1400CA262
0x1400ca25e  mov     dword ptr [rsp+1C0h+var_158], edi
0x1400ca262  mov     eax, [r15+34h]
0x1400ca266  bt      eax, 10h
0x1400ca26a  jnb     short loc_1400CA288
0x1400ca26c  mov     eax, [r15+30h]
0x1400ca270  bt      eax, 18h
0x1400ca274  jb      short loc_1400CA288
0x1400ca276  test    rcx, rcx
0x1400ca279  jz      short loc_1400CA288
0x1400ca27b  mov     dword ptr [rsp+64h], 1
0x1400ca283  test    rsi, rsi
0x1400ca286  jnz     short loc_1400CA28C
0x1400ca288  mov     [rsp+64h], edi
0x1400ca28c  call    cs:__imp_KeGetCurrentIrql
0x1400ca293  nop     dword ptr [rax+rax+00h]
0x1400ca298  cmp     al, 2
0x1400ca29a  jnb     short loc_1400CA2AA
0x1400ca29c  call    WfpRaiseIrqlToDispatchLevel
0x1400ca2a1  mov     byte ptr [rsp+1C0h+var_160], al
0x1400ca2a5  mov     byte ptr [rsp+1C0h+var_160+1], 1
0x1400ca2aa  mov     ecx, gs:1A4h
0x1400ca2b2  lea     r8, [rcx+rcx*8]
0x1400ca2b6  mov     rcx, cs:gPerProcessorContext
0x1400ca2bd  cmp     [rcx+r8*8+20h], dil
0x1400ca2c2  jnz     short loc_1400CA2D9
0x1400ca2c4  mov     r14, [rcx+r8*8+18h]
0x1400ca2c9  mov     rdi, [rcx+r8*8+10h]
0x1400ca2ce  mov     byte ptr [rcx+r8*8+20h], 1
0x1400ca2d4  jmp     loc_1400CA3D5
0x1400ca2d9  mov     rcx, cs:gIncomingValuesLookasideList
0x1400ca2e0  lea     rdx, [rbp+0C0h+Entry]
0x1400ca2e7  call    WfpAllocateFromPerProcessorLookasideList
0x1400ca2ec  test    rax, rax
0x1400ca2ef  jnz     short loc_1400CA34F
0x1400ca2f1  mov     rcx, cs:gMetadataLookasideList
0x1400ca2f8  lea     rdx, [rsp+1C0h+Size]
0x1400ca2fd  call    WfpAllocateFromPerProcessorLookasideList
0x1400ca302  test    rax, rax
0x1400ca305  jz      loc_1400CA3C9
0x1400ca30b  mov     eax, gs:1A4h
0x1400ca313  mov     rcx, cs:gIncomingValuesLookasideList
0x1400ca31a  lea     ebx, [rax+1]
0x1400ca31d  shl     rbx, 7
0x1400ca321  add     rbx, rcx
0x1400ca324  movzx   eax, byte ptr [rbx+0B0h]
0x1400ca32b  test    al, al
0x1400ca32d  jnz     short loc_1400CA338
0x1400ca32f  lea     rdx, [rbx+40h]
0x1400ca333  call    PplpLazyInitializeLookasideList
0x1400ca338  mov     rdx, [rbp+0C0h+Entry]; Entry
0x1400ca33f  lea     rcx, [rbx+40h]; Lookaside
0x1400ca343  call    cs:__imp_ExFreeToLookasideListEx
0x1400ca34a  nop     dword ptr [rax+rax+00h]
0x1400ca34f  movzx   r15d, byte ptr [rsp+1C0h+var_160+1]
0x1400ca355  xor     sil, sil
0x1400ca358  movzx   r12d, byte ptr [rsp+1C0h+var_160]
0x1400ca35e  mov     rdi, r14
0x1400ca361  test    r15b, r15b
0x1400ca364  jz      short loc_1400CA36F
0x1400ca366  movzx   ecx, r12b
0x1400ca36a  call    WfpLowerIrqlFromDispatchLevel
0x1400ca36f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca376  lea     r13, WPP_GLOBAL_Control
0x1400ca37d  mov     rbx, 0FFFFFFFFC000009Ah
0x1400ca384  cmp     rcx, r13
0x1400ca387  jz      loc_1400CB5F0
0x1400ca38d  cmp     byte ptr [rcx+29h], 2
0x1400ca391  jb      loc_1400CB5F0
0x1400ca397  test    dword ptr [rcx+2Ch], 1000h
0x1400ca39e  jz      loc_1400CB5F0
0x1400ca3a4  mov     rcx, [rcx+18h]
0x1400ca3a8  lea     r9, aWfpalepreautho; "WfpAlepReauthorizeOutboundConnection"
0x1400ca3af  mov     edx, 0Ah
0x1400ca3b4  mov     dword ptr [rsp+1C0h+var_1A0], ebx
0x1400ca3b8  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400ca3bf  call    WPP_SF_sd
0x1400ca3c4  jmp     loc_1400CB5F0
0x1400ca3c9  mov     r14, [rbp+0C0h+Entry]
0x1400ca3d0  mov     rdi, [rsp+1C0h+Size]
0x1400ca3d5  xor     edx, edx; Val
0x1400ca3d7  mov     r8d, 2A0h; Size
0x1400ca3dd  mov     rcx, r14; void *
0x1400ca3e0  call    memset
0x1400ca3e5  xor     edx, edx; Val
0x1400ca3e7  mov     r8d, 2A8h; Size
0x1400ca3ed  mov     rcx, rdi; void *
0x1400ca3f0  call    memset
0x1400ca3f5  lea     rax, [rdi+270h]
0x1400ca3fc  mov     r8d, 158h; Size
0x1400ca402  mov     [rax+8], rax
0x1400ca406  mov     [rax], rax
0x1400ca409  mov     eax, gs:1A4h
0x1400ca411  lea     rdx, [rax+rax*8]
0x1400ca415  mov     rax, cs:gPerProcessorContext
0x1400ca41c  mov     rbx, [rax+rdx*8+28h]
0x1400ca421  xor     edx, edx; Val
0x1400ca423  mov     rcx, rbx; void *
0x1400ca426  call    memset
0x1400ca42b  mov     rax, [rbp+0C0h+arg_80]
0x1400ca432  mov     [rbx+48h], r13
0x1400ca436  test    rax, rax
0x1400ca439  jz      short loc_1400CA463
0x1400ca43b  lea     rdx, [rbp+0C0h+var_118]
0x1400ca43f  mov     rcx, rax
0x1400ca442  call    cs:__imp_FeAcquireCompletionHandle
0x1400ca449  nop     dword ptr [rax+rax+00h]
0x1400ca44e  test    rax, rax
0x1400ca451  jz      short loc_1400CA463
0x1400ca453  call    cs:__imp_FeAcquireGenericCompletionHandle
0x1400ca45a  nop     dword ptr [rax+rax+00h]
0x1400ca45f  mov     [rbp+0C0h+var_118], rax
0x1400ca463  mov     rcx, [r15+1E0h]
0x1400ca46a  movzx   eax, [rbp+0C0h+arg_8]
0x1400ca471  mov     r9d, [rsp+64h]
0x1400ca476  mov     word ptr [rbp+0C0h+var_A0], ax
0x1400ca47a  movzx   eax, word ptr [r12]
0x1400ca47f  mov     dword ptr [rbp+0C0h+var_A0+4], eax
0x1400ca482  mov     qword ptr [rbp+0C0h+var_A0+8], r14
0x1400ca486  mov     rax, [rcx+10h]
0x1400ca48a  mov     qword ptr [rbp+0C0h+var_DC+4], rax
0x1400ca48e  movzx   eax, word ptr [rcx+0Ah]
0x1400ca492  lea     rcx, [rbp+0C0h+var_E0]
0x1400ca496  mov     [rbp+0C0h+var_E0], eax
0x1400ca499  movzx   eax, word ptr [r12+2]
0x1400ca49f  add     rax, rax
0x1400ca4a2  movaps  [rsp+1C0h+var_48+8], xmm6
0x1400ca4aa  movaps  [rsp+1C0h+var_58+8], xmm7
0x1400ca4b2  movaps  xmmword ptr [rsp+160h], xmm8
0x1400ca4bb  mov     dword ptr [r14+rax*8], 0Ch
0x1400ca4c3  movzx   eax, word ptr [r12+2]
0x1400ca4c9  add     rax, rax
0x1400ca4cc  mov     [r14+rax*8+8], rcx
0x1400ca4d1  test    r9d, r9d
0x1400ca4d4  jz      loc_1400CA627
0x1400ca4da  mov     r8, [rbp+0C0h+var_110]
0x1400ca4de  mov     rax, [r8+1E8h]
0x1400ca4e5  add     rax, 0E0h
0x1400ca4eb  mov     qword ptr [rbp+0C0h+var_104+4], rax
0x1400ca4ef  mov     rax, [r8+1E8h]
0x1400ca4f6  mov     ecx, [rax+48h]
0x1400ca4f9  mov     [rbp+0C0h+var_108], ecx
0x1400ca4fc  mov     rax, [r8+1E8h]
0x1400ca503  mov     rdx, [rax+118h]
0x1400ca50a  mov     rax, [rax+90h]
0x1400ca511  mov     [rsp+1C0h+Size], rdx
0x1400ca516  test    rax, rax
0x1400ca519  jz      short loc_1400CA591
0x1400ca51b  mov     rax, [rax+8]
0x1400ca51f  lea     r8, [rbp+0C0h+P]
0x1400ca523  mov     edx, 63716641h
0x1400ca528  mov     r13, [rax+20h]
0x1400ca52c  movzx   eax, word ptr [r13+8]
0x1400ca531  add     ax, 2
0x1400ca535  movzx   eax, ax
0x1400ca538  mov     dword ptr [rbp+0C0h+Entry], eax
0x1400ca53e  add     eax, 8
0x1400ca541  mov     ecx, eax
0x1400ca543  mov     dword ptr [rsp+1C0h+Size+8], eax
0x1400ca547  call    WfpPoolAllocNonPaged
0x1400ca54c  mov     rbx, rax
0x1400ca54f  test    rax, rax
0x1400ca552  jnz     short loc_1400CA5A7
0x1400ca554  mov     r8d, dword ptr [rsp+1C0h+Size+8]; Size
0x1400ca559  xor     edx, edx; Val
0x1400ca55b  mov     rcx, [rbp+0C0h+P]; void *
  ... truncated ...
```
