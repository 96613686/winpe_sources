# VidPartitionIoctlSetup

- ea: `0x14008d084`
- end: `0x14008fc23`
- name: `VidPartitionIoctlSetup`
- size: `11167`
- prototype: `__int64 __fastcall(__int64, unsigned int *, int)`
- caller_count: `1`
- callee_count: `58`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140035698`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x14001362c`
- `0x1400143dc`
- `0x14001444c`
- `0x140021650`
- `0x1400217a0`
- `0x140021800`
- `0x140021d40`
- `0x14002304c`
- `0x14002311c`
- `0x14002f524`
- `0x140034554`
- `0x140034914`
- `0x140035218`
- `0x1400737bc`
- `0x14007410c`
- `0x140074398`
- `0x140074988`
- `0x140074fbc`
- `0x140075460`
- `0x140075da8`
- `0x140075fb0`
- `0x14007930c`
- `0x14008a284`
- `0x14008d084`
- `0x14008fcec`
- `0x140090030`
- `0x140090c48`
- `0x140093448`
- `0x140098628`
- `0x140098864`
- `0x140099e18`
- `0x14009b9fc`
- `0x14009eb70`
- `0x1400a1fcc`
- `0x1400a21fc`
- `0x1400a3500`
- `0x1400a5058`
- `0x1400a50cc`
- `0x1400a5b8c`
- `0x1400a70d0`
- `0x1400ad19c`
- `0x1400aeedc`
- `0x1400b1a24`
- `0x1400cc7b0`
- `0x1400e33ec`
- `0x1400f57e8`
- `0x1400f6994`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x14008f783`
- `ntoskrnl!EtwEventEnabled` at `0x14008f783`
- `ntoskrnl!HalPrivateDispatchTable` at `0x14008d992`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008f891`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008f891`
- `ntoskrnl!ExAllocatePool2` at `0x14008f5e0`
- `ntoskrnl!ExAllocatePool2` at `0x14008f5e0`
- `winhvr!WinHvInitializePartition` at `0x14008ed5c`
- `winhvr!WinHvInitializePartition` at `0x14008ed5c`
- `winhvr!WinHvCreatePartitionEx` at `0x14008e6e1`
- `winhvr!WinHvCreatePartitionEx` at `0x14008e6e1`
- `winhvr!WinHvIsOverlayMapLocationRequired` at `0x14008eab5`
- `winhvr!WinHvIsOverlayMapLocationRequired` at `0x14008eab5`
- `winhvr!WinHvSetPartitionProperty` at `0x14008ea70`
- `winhvr!WinHvSetPartitionProperty` at `0x14008eb02`
- `winhvr!WinHvSetPartitionProperty` at `0x14008ec54`
- `winhvr!WinHvSetPartitionProperty` at `0x14008ee69`
- `winhvr!WinHvSetPartitionProperty` at `0x14008ef58`
- `winhvr!WinHvSetPartitionProperty` at `0x14008f0ec`
- `winhvr!WinHvSetPartitionProperty` at `0x14008f19d`
- `winhvr!WinHvSetPartitionProperty` at `0x14008f259`
- `winhvr!WinHvSetPartitionProperty` at `0x14008f494`
- `winhvr!WinHvSetPartitionProperty` at `0x14008ea70`
- `winhvr!WinHvSetPartitionProperty` at `0x14008eb02`
- `winhvr!WinHvSetPartitionProperty` at `0x14008ec54`
- `winhvr!WinHvSetPartitionProperty` at `0x14008ee69`
- `winhvr!WinHvSetPartitionProperty` at `0x14008ef58`
- `winhvr!WinHvSetPartitionProperty` at `0x14008f0ec`
- `winhvr!WinHvSetPartitionProperty` at `0x14008f19d`
- `winhvr!WinHvSetPartitionProperty` at `0x14008f259`
- `winhvr!WinHvSetPartitionProperty` at `0x14008f494`
- `winhvr!WinHvDeletePartition` at `0x14008f8f4`
- `winhvr!WinHvDeletePartition` at `0x14008f8f4`
- `winhvr!WinHvGetPartitionProperty` at `0x14008ef05`
- `winhvr!WinHvGetPartitionProperty` at `0x14008f02c`
- `winhvr!WinHvGetPartitionProperty` at `0x14008ef05`
- `winhvr!WinHvGetPartitionProperty` at `0x14008f02c`
- `winhvr!WinHvSetPartitionPropertyEx` at `0x14008e813`
- `winhvr!WinHvSetPartitionPropertyEx` at `0x14008e813`

## string_xrefs

- `0x14008d765`: `ForceDeferredCommit`

## pseudocode

```c
__int64 __fastcall VidPartitionIoctlSetup(__int64 a1, unsigned int *a2, int a3)
{
  PVOID v3; // rbx
  unsigned __int64 v4; // r15
  char v5; // di
  char v6; // si
  char v7; // r14
  __int64 v10; // rdx
  __int64 v11; // xmm7_8
  __int128 v12; // xmm6
  __int64 v13; // rcx
  unsigned int v14; // eax
  _DWORD *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdi
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rsi
  __int64 v32; // rcx
  unsigned __int64 v33; // rdx
  __int64 v34; // rcx
  unsigned __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  unsigned __int64 v40; // rax
  unsigned int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // r8
  unsigned __int64 v48; // rdx
  __int64 v49; // r9
  unsigned __int64 v50; // rcx
  int v51; // ecx
  __int64 v52; // r8
  int v53; // ecx
  __int16 v54; // dx
  __int64 v55; // rcx
  unsigned int v56; // r8d
  __int64 v57; // r8
  __int64 v58; // rcx
  __int64 v59; // r9
  __int64 v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rax
  unsigned int v63; // r9d
  unsigned int v64; // ecx
  int v65; // r9d
  __int64 v66; // r8
  __int64 v67; // rdx
  __int64 v68; // r10
  unsigned __int8 v69; // r11
  __int64 v70; // rax
  _QWORD *v71; // rbx
  __int64 v72; // r9
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rax
  unsigned __int64 v78; // rcx
  int UINT32WithDefault; // eax
  unsigned __int64 v80; // r14
  unsigned int v81; // ecx
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // rsi
  unsigned int v85; // eax
  __int64 v86; // r8
  __int64 v87; // r9
  __int128 v88; // xmm0
  unsigned int v89; // r8d
  __int64 j; // rdx
  __int64 v91; // rcx
  unsigned int v92; // r9d
  unsigned __int8 v93; // r8
  __int64 v94; // r10
  __int64 v95; // rdx
  char *v96; // r14
  unsigned int v97; // eax
  __int64 v98; // rsi
  char v99; // r9
  char *v100; // rdx
  unsigned __int64 v101; // rax
  __int64 v102; // rcx
  bool v103; // zf
  __int64 v104; // rdx
  __int64 v105; // rcx
  __int64 v106; // rcx
  __int64 v107; // rcx
  __int64 v108; // rax
  unsigned __int64 v109; // rbx
  __int64 v110; // r14
  __int64 v111; // rbx
  int v112; // ebx
  __int64 v113; // rax
  __int64 v114; // rdx
  int i; // ecx
  __int64 v116; // rax
  __int64 v117; // rcx
  int v118; // eax
  __int64 Pool2; // rax
  unsigned int v120; // ebx
  __int64 v121; // rax
  int v122; // eax
  void *v123; // rcx
  int v124; // r9d
  unsigned __int64 v125; // r14
  unsigned __int64 v126; // rcx
  __int64 v127; // r8
  int v128; // eax
  int v130; // [rsp+28h] [rbp-E0h]
  char v131; // [rsp+58h] [rbp-B0h]
  __int64 v132; // [rsp+78h] [rbp-90h] BYREF
  PVOID v133; // [rsp+80h] [rbp-88h] BYREF
  int v134; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v135; // [rsp+90h] [rbp-78h] BYREF
  char v136; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 v137; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v138; // [rsp+A8h] [rbp-60h]
  __int128 v139; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 v140; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v141; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v142; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v143; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v144; // [rsp+F8h] [rbp-10h]
  unsigned __int64 v145; // [rsp+100h] [rbp-8h] BYREF
  __int128 v146; // [rsp+108h] [rbp+0h] BYREF
  _QWORD v147[2]; // [rsp+118h] [rbp+10h] BYREF
  __int128 v148; // [rsp+128h] [rbp+20h]
  __int128 v149; // [rsp+138h] [rbp+30h] BYREF
  _OWORD v150[2]; // [rsp+148h] [rbp+40h] BYREF
  __int64 v151; // [rsp+168h] [rbp+60h]
  _QWORD v152[17]; // [rsp+178h] [rbp+70h] BYREF
  _DWORD v153[2]; // [rsp+200h] [rbp+F8h] BYREF
  __int128 *v154; // [rsp+208h] [rbp+100h]
  __int64 v155; // [rsp+210h] [rbp+108h]
  char *v156; // [rsp+218h] [rbp+110h]
  __int64 v157; // [rsp+220h] [rbp+118h]
  unsigned int *v158; // [rsp+228h] [rbp+120h]
  __int64 v159; // [rsp+230h] [rbp+128h]
  unsigned __int64 *v160; // [rsp+238h] [rbp+130h]
  __int64 v161; // [rsp+240h] [rbp+138h]
  PVOID *v162; // [rsp+248h] [rbp+140h]
  __int64 v163; // [rsp+250h] [rbp+148h]
  unsigned int *v164; // [rsp+258h] [rbp+150h]
  __int64 v165; // [rsp+260h] [rbp+158h]
  __int128 *v166; // [rsp+268h] [rbp+160h]
  __int64 v167; // [rsp+270h] [rbp+168h]
  _DWORD v168[128]; // [rsp+278h] [rbp+170h] BYREF

  v3 = VidDeviceExtension;
  v4 = 0;
  *(_QWORD *)&v142 = 0;
  memset(v150, 0, sizeof(v150));
  v151 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v140 = 0;
  v145 = 0;
  v143 = 0;
  v133 = VidDeviceExtension;
  v134 = a3;
  VidObjectLockAcquireExclusive(a1);
  VidObjectLockAcquireExclusive(a1 + 3736);
  VidRegistryOpenParametersKey(&v142);
  v11 = *(_QWORD *)(a1 + 32);
  v12 = *(_OWORD *)(a1 + 16);
  v138 = v142;
  if ( *(_DWORD *)(a1 + 48) )
  {
    if ( (a2[8] & 0x800LL) == 0 || !*(_BYTE *)(a1 + 8657) )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1777);
    }
    goto LABEL_82;
  }
  *(_QWORD *)(a1 + 40) = 0;
  if ( (*((_QWORD *)a2 + 4) & 0xFE00000000000000uLL) != 0 )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1791);
    goto LABEL_82;
  }
  v13 = *(_QWORD *)(a1 + 16);
  v14 = a2[10];
  if ( (v13 & 0x8000) != 0 )
  {
    if ( v14 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1800);
      goto LABEL_82;
    }
  }
  else if ( v14 - 1 > 0x7FF )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1810);
    goto LABEL_82;
  }
  if ( *a2 - 1536 > 0xF900 )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1823);
    goto LABEL_82;
  }
  v15 = a2 + 16956;
  if ( (*(_QWORD *)(a1 + 16) & 0x8000LL) == 0 && (*v15 & 0x30) == 0 )
  {
    v13 |= 0x10uLL;
    *(_QWORD *)(a1 + 16) = v13;
  }
  if ( *((char *)a2 + 32) < 0 )
  {
    v13 &= ~0x10uLL;
    *(_QWORD *)(a1 + 16) = v13;
  }
  v16 = *((_QWORD *)a2 + 4);
  if ( (v16 & 0x40000000) != 0 )
  {
    if ( (*v15 & 0x30) != 0 || ((v16 & 0x100000000LL) == 0 || *a2 != 1541) && (int)*a2 < 1543 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1851);
      goto LABEL_82;
    }
    v13 |= 0x20uLL;
    *(_QWORD *)(a1 + 16) = v13;
  }
  if ( _bittest64((const signed __int64 *)a2 + 4, 0x31u) )
  {
    if ( (v13 & 0x20) == 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1861);
      goto LABEL_82;
    }
    *(_QWORD *)(a1 + 32) |= 0x4000uLL;
  }
  v17 = 0;
  if ( _bittest64((const signed __int64 *)a2 + 4, 0x37u) )
    *(_QWORD *)(a1 + 32) |= 0x10000uLL;
  if ( (v13 & 0x30) != 0 )
    v18 = v13 | 8;
  else
    v18 = v13 | 0x40;
  *(_QWORD *)(a1 + 16) = v18;
  v19 = *((_QWORD *)a2 + 4);
  *(_QWORD *)&v139 = *((_QWORD *)&v143 + 1);
  if ( (v18 & 0x8000) != 0 )
  {
    if ( (v19 & 0xFFBED7C9FFFEFF9FuLL) != 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1891);
LABEL_81:
      v5 = 0;
      v7 = 0;
      goto LABEL_82;
    }
    if ( *((_OWORD *)a2 + 4236) != v143 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1904);
      goto LABEL_81;
    }
    if ( (a2[12] & 0x180) != 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1914);
      goto LABEL_81;
    }
    *(_QWORD *)(a1 + 16) = v18 | 0x200;
    v20 = (*((_QWORD *)a2 + 4) & 0x200000000LL | 0x10000000uLL) >> 20;
    v21 = *((_DWORD *)VidDeviceExtension + 162);
    if ( (v21 & 0x20) != 0 )
      v17 = 1;
    v19 = *((_QWORD *)a2 + 4);
    v4 = ((unsigned __int64)*((unsigned int *)VidDeviceExtension + 162) >> 5) & 1 | 2;
    if ( (v21 & 0x20) == 0 )
      v4 = ((unsigned __int64)*((unsigned int *)VidDeviceExtension + 162) >> 5) & 1;
    *(_QWORD *)&v142 = v4;
    if ( (v19 & 0x200000000000LL) != 0 )
      v20 |= 0x1000000u;
    v22 = v20 | 0x800;
    v17 |= 0x3FFEuLL;
    if ( (v19 & 0x10000) != 0 )
      v22 = v20;
  }
  else
  {
    if ( (v19 & 0x200000000000LL) != 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1972);
      goto LABEL_81;
    }
    v22 = 0;
    *(_QWORD *)&v142 = 0;
  }
  if ( (v19 & 8) != 0 )
  {
    if ( !(unsigned int)VidCurrentProcessIsTrusted(a1) )
    {
      LODWORD(v4) = -1073741790;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1989);
LABEL_80:
      v3 = v133;
      goto LABEL_81;
    }
    *(_QWORD *)(a1 + 40) |= 6uLL;
  }
  if ( (a2[8] & 0x10) != 0 )
    *(_QWORD *)(a1 + 40) |= 2uLL;
  v23 = *((_QWORD *)a2 + 4);
  if ( (v23 & 0x100000000LL) != 0 )
    v22 |= 0x1000uLL;
  v24 = v22 | 1;
  if ( (v23 & 0x20) == 0 )
    v24 = v22;
  v25 = v24 | 0x4000;
  if ( (v23 & 0x800000000LL) == 0 )
    v25 = v24;
  if ( (v23 & 0x40) != 0 )
  {
    v25 |= 2uLL;
    *(_QWORD *)(a1 + 16) |= 0x100uLL;
  }
  v26 = *((_QWORD *)a2 + 4);
  v27 = v25 | 0x8000;
  v28 = 0x1000000000000LL;
  if ( (v26 & 0x1000000000LL) == 0 )
    v27 = v25;
  v29 = v27 | 0x8000000;
  if ( (v26 & 0x1000000000000LL) == 0 )
    v29 = v27;
  v30 = v29 | 0x10000;
  if ( (v26 & 0x2000000000LL) == 0 )
    v30 = v29;
  if ( (v26 & 0x4000000000LL) != 0 )
    v30 |= 0x20000uLL;
  v31 = v30 | 0x40000;
  if ( (v26 & 0x8000000000LL) == 0 )
    v31 = v30;
  if ( (v26 & 0x40000000000LL) != 0 && (v26 & 0x80000000000LL) != 0 )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2065);
LABEL_79:
    v6 = 0;
    goto LABEL_80;
  }
  if ( (v26 & 0x400000000000LL) != 0 && (v26 & 0x80000000000LL) == 0 )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2073);
    goto LABEL_79;
  }
  if ( (v26 & 0x40000000000LL) != 0 )
  {
    v31 |= 0x200000uLL;
  }
  else if ( (v26 & 0x80000000000LL) != 0 )
  {
    v31 |= 0x400000uLL;
    if ( (v26 & 0x400000000000LL) != 0 )
      v31 |= 0x2000000uLL;
  }
  v32 = *(_QWORD *)(a1 + 16);
  v135 = v31;
  if ( (v26 & 0x4000000000000LL) != 0 )
  {
    if ( (v32 & 0x20) == 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2109);
      goto LABEL_79;
    }
    v31 |= 0x80000000uLL;
    v135 = v31;
  }
  if ( (v32 & 0x8000) != 0 || (v26 & 0x100000000000LL) != 0 )
  {
    v31 |= 0x800000uLL;
    v135 = v31;
  }
  if ( (a2[8] & 0x100LL) != 0 )
  {
    *(_QWORD *)(a1 + 16) = v32 | 0x200;
    v33 = ((unsigned __int64)a2[12] >> 2)
        & 0x3FFFFFFFFFFFFE00LL
        ^ (*(_QWORD *)(a1 + 24)
         ^ ((unsigned __int64)a2[12] >> 2)
         & 0x3FFFFFFFFFFFFE00LL)
        & 0xFFFFFFFFFFFFE1FFuLL;
    *(_QWORD *)(a1 + 24) = v33;
    *(_QWORD *)(a1 + 24) = ((unsigned __int64)a2[12] >> 2)
                         & 0x3FFFFFFFFFFFE000LL
                         ^ (v33
                          ^ ((unsigned __int64)a2[12] >> 2)
                          & 0x3FFFFFFFFFFFE000LL)
                         & 0xFFFFFFFFFFFE1FFFuLL;
    if ( v138 )
    {
      HIDWORD(v132) = 0;
      if ( (int)VidRegistryQueryUINT32(v138, L"ForceDeferredCommit", (char *)&v132 + 4) >= 0 && HIDWORD(v132) )
        *(_QWORD *)(a1 + 24) |= 2uLL;
      if ( (int)VidRegistryQueryUINT32(v138, L"ForcePinBackingPages", (char *)&v132 + 4) >= 0 && HIDWORD(v132) )
        *(_QWORD *)(a1 + 24) |= 1uLL;
      if ( (int)VidRegistryQueryUINT32(v138, L"FaultClusterSizeShift", (char *)&v132 + 4) >= 0 && HIDWORD(v132) < 0x10 )
        *(_QWORD *)(a1 + 24) = ((unsigned __int64)HIDWORD(v132) << 9)
                             ^ (*(_QWORD *)(a1 + 24)
                              ^ ((unsigned __int64)HIDWORD(v132) << 9))
                             & 0xFFFFFFFFFFFFE1FFuLL;
      if ( (int)VidRegistryQueryUINT32(v138, L"DirectMapFaultClusterSizeShift", (char *)&v132 + 4) >= 0
        && HIDWORD(v132) < 0x10 )
      {
        *(_QWORD *)(a1 + 24) = ((unsigned __int64)HIDWORD(v132) << 13)
                             ^ (*(_QWORD *)(a1 + 24)
                              ^ ((unsigned __int64)HIDWORD(v132) << 13))
                             & 0xFFFFFFFFFFFE1FFFuLL;
      }
    }
  }
  if ( (a2[8] & 0x40000) != 0 )
    *(_QWORD *)(a1 + 24) |= 2uLL;
  if ( (a2[8] & 0x400000) != 0 )
    *(_QWORD *)(a1 + 24) |= 1uLL;
  v34 = *(_QWORD *)(a1 + 16);
  if ( (a2[8] & 0x200LL) != 0 )
  {
    v31 |= 4uLL;
    v34 |= 0x400uLL;
    v135 = v31;
    *(_QWORD *)(a1 + 16) = v34;
  }
  v35 = *((_QWORD *)a2 + 4);
  if ( (v35 & 0x38000000) != 0 )
  {
    if ( (v34 & 0x400) == 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2228);
      goto LABEL_79;
    }
    v34 &= ~0x800uLL;
    v36 = v34 | (v35 >> 16) & 0x800;
    *(_QWORD *)(a1 + 16) = v36;
    *(_QWORD *)(a1 + 16) = v36 & 0xFFFFFFFFFFFFEFFFuLL | HIWORD(a2[8]) & 0x1000;
  }
  v37 = *((_QWORD *)a2 + 4);
  if ( (v37 & 0x400) != 0 )
  {
    v31 |= 0x20uLL;
    v135 = v31;
  }
  if ( (v37 & 0x1000) != 0 )
    *(_QWORD *)(a1 + 24) |= 4uLL;
  if ( (a2[8] & 0x2000LL) != 0 )
    *(_QWORD *)(a1 + 24) |= 8uLL;
  if ( (a2[8] & 0x4000LL) != 0 )
  {
    v38 = *(_QWORD *)(a1 + 24);
    if ( (v38 & 2) == 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2261);
      goto LABEL_79;
    }
    *(_QWORD *)(a1 + 24) = v38 | 0x10;
  }
  if ( (a2[8] & 0x8000LL) != 0 )
    *(_QWORD *)(a1 + 24) |= 0x40uLL;
  if ( (a2[8] & 0x20000) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x100LL) != 0 || (int)*a2 < 1538 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2281);
      goto LABEL_79;
    }
    *(_QWORD *)(a1 + 24) |= 0x80uLL;
  }
  if ( _bittest64((const signed __int64 *)a2 + 4, 0x33u) )
    *(_QWORD *)(a1 + 24) |= 0x20000uLL;
  if ( _bittest64((const signed __int64 *)a2 + 4, 0x2Fu) )
  {
    if ( !HalPrivateDispatchTable[90](v34, 0x20000, 1024) && (unsigned __int8)VidpIsOsClientVersion() )
    {
      LODWORD(v4) = -1073741637;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2307);
      goto LABEL_79;
    }
    v31 |= 0x4000000uLL;
    *(_QWORD *)(a1 + 40) |= 0x10uLL;
    v135 = v31;
  }
  v39 = *(_QWORD *)(a1 + 24);
  if ( (v39 & 1) != 0 )
  {
    v39 &= 0xFFFFFFFFFFFFFFE7uLL;
    *(_QWORD *)(a1 + 24) = v39;
  }
  if ( (v39 & 0x80u) != 0LL && ((v39 & 0xC) != 0 || (v39 & 0x10) != 0) && (int)*a2 >= 1540 )
  {
    v39 |= 0x20uLL;
    *(_QWORD *)(a1 + 24) = v39;
  }
  if ( (v39 & 2) != 0 && (v39 & 0x18) != 0 )
    *(_QWORD *)(a1 + 24) = v39 | 0x100;
  if ( (a2[8] & 0x100000) != 0 )
  {
    if ( (int)*a2 < 1538 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2383);
      goto LABEL_79;
    }
    v40 = ((unsigned __int64)*((unsigned int *)VidDeviceExtension + 162) << 8)
        ^ (*(_QWORD *)(a1 + 16)
         ^ ((unsigned __int64)*((unsigned int *)VidDeviceExtension + 162) << 8))
        & 0xFFFFFFFFFFFFDFFFuLL;
    *(_QWORD *)(a1 + 16) = v40;
    if ( (v40 & 0x2000) != 0 )
    {
      v31 |= 0x80uLL;
      v135 = v31;
      *(_QWORD *)&v142 = v4 | 1;
    }
  }
  if ( a2[11] )
  {
    if ( (*((_DWORD *)VidDeviceExtension + 162) & 0x20) == 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2419);
      goto LABEL_79;
    }
    v41 = a2[11];
    if ( v41 >= 0x10 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2428);
      goto LABEL_79;
    }
    *(_DWORD *)(a1 + 3224) = v41;
  }
  if ( (*((_DWORD *)VidDeviceExtension + 162) & 0x20) != 0 || (*(_DWORD *)(a1 + 16) & 0x8000LL) != 0 )
  {
    v31 |= 0x80000uLL;
    v135 = v31;
  }
  v42 = (a2[12] >> 7) & 3;
  HIDWORD(v132) = 0;
  LODWORD(v4) = VidPartitionpPageSizeUnitGet(a1, v42, 0, (char *)&v132 + 4);
  if ( (v4 & 0x80000000) != 0LL )
  {
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2460);
    goto LABEL_79;
  }
  v44 = v138;
  *(_QWORD *)(a1 + 32) = SHIDWORD(v132) ^ (*(_QWORD *)(a1 + 32) ^ SHIDWORD(v132)) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v44 )
  {
    HIDWORD(v132) = 0;
    if ( (int)VidRegistryQueryUINT32(v44, L"PageBackingSize", (char *)&v132 + 4) >= 0 && HIDWORD(v132) < 3 )
      *(_QWORD *)(a1 + 32) = HIDWORD(v132) ^ (*(_QWORD *)(a1 + 32) ^ HIDWORD(v132)) & 0xFFFFFFFFFFFFFFFCuLL;
    v44 = v138;
  }
  if ( (a2[8] & 0x80000) != 0
    || v44
    && (HIDWORD(v132) = 0, (int)VidRegistryQueryUINT32(v44, L"ForcePageBackingSizeRequired", (char *)&v132 + 4) >= 0)
    && HIDWORD(v132) )
  {
    *(_QWORD *)(a1 + 32) |= 4uLL;
  }
  LOBYTE(v43) = 1;
  v45 = (a2[12] >> 9) & 3;
  HIDWORD(v132) = 0;
  LODWORD(v4) = VidPartitionpPageSizeUnitGet(a1, v45, v43, (char *)&v132 + 4);
  if ( (v4 & 0x80000000) != 0LL )
  {
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2514);
    goto LABEL_79;
  }
  v46 = v138;
  *(_QWORD *)(a1 + 32) = (8LL * SHIDWORD(v132))
                       ^ (*(_QWORD *)(a1 + 32)
                        ^ (8LL * SHIDWORD(v132)))
                       & 0xFFFFFFFFFFFFFFE7uLL;
  if ( v46 )
  {
    HIDWORD(v132) = 0;
    if ( (int)VidRegistryQueryUINT32(v46, L"PageMappingSize", (char *)&v132 + 4) >= 0 && HIDWORD(v132) < 3 )
      *(_QWORD *)(a1 + 32) = (8LL * HIDWORD(v132))
                           ^ (*(_QWORD *)(a1 + 32)
                            ^ (8LL * HIDWORD(v132)))
                           & 0xFFFFFFFFFFFFFFE7uLL;
  }
  v47 = *(_QWORD *)(a1 + 16);
  if ( (v47 & 0x200) == 0 )
  {
    v50 = *(_QWORD *)(a1 + 32);
LABEL_204:
    v49 = v47;
    goto LABEL_205;
  }
  v48 = *(_QWORD *)(a1 + 32);
  v49 = *(_QWORD *)(a1 + 16);
  if ( (v48 & 3) > 1 )
  {
    v48 = v48 & 0xFFFFFFFFFFFFFFFCuLL | 1;
    *(_QWORD *)(a1 + 32) = v48;
  }
  if ( (v48 & 0x18) <= 8 )
  {
    v49 = v47;
    LOBYTE(v50) = v48;
  }
  else
  {
    v50 = v48 & 0xFFFFFFFFFFFFFFE7uLL | 8;
    *(_QWORD *)(a1 + 32) = v50;
  }
  if ( (v50 & 3) != 1 )
    goto LABEL_204;
  if ( (*(_QWORD *)(a1 + 24) & 0x1E00LL) != 0x1200 )
    *(_QWORD *)(a1 + 24) = *(_QWORD *)(a1 + 24) & 0xFFFFFFFFFFFFE1FFuLL | 0x1200;
LABEL_205:
  v51 = v50 & 0x18;
  if ( v51 )
  {
    if ( v51 != 16 )
      goto LABEL_210;
    v31 |= 0x10uLL;
  }
  else
  {
    v31 |= 8uLL;
  }
  v135 = v31;
LABEL_210:
  if ( (a2[8] & 0x200000) != 0 )
  {
    if ( (v49 & 0x200) == 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2586);
      goto LABEL_79;
    }
    v49 |= 0x4000uLL;
    *(_QWORD *)(a1 + 16) = v49;
  }
  *(_QWORD *)(a1 + 11952) = 0;
  v52 = a2[16956];
  v53 = a2[16956] & 0xF;
  if ( (unsigned int)(v53 - 2) > 2 && *((_QWORD *)a2 + 8479) )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2599);
    goto LABEL_79;
  }
  if ( (v52 & 0xC0) != 0 )
  {
    if ( v53 != 2 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2609);
      goto LABEL_79;
    }
    if ( (a2[16956] & 0xC0) == 0x80 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2619);
      goto LABEL_79;
    }
    goto LABEL_224;
  }
  if ( v53 || (v52 & 0x30) != 0 )
  {
LABEL_224:
    if ( (*(_BYTE *)(a1 + 40) & 6) != 0 || (v49 & 0x200) != 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2632);
      goto LABEL_79;
    }
    if ( (v52 & 0xF) != 0 )
    {
      switch ( a2[16956] & 0xF )
      {
        case 1u:
          v54 = v140 & 0xFFE0 | 1;
          break;
        case 2u:
          v54 = v140 & 0xFFE0 | 2;
          break;
        case 3u:
          v54 = v140 & 0xFFE0 | 3;
          break;
        default:
          LODWORD(v4) = -1073741811;
          VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2671);
          goto LABEL_79;
      }
      *(_QWORD *)(a1 + 32) = (32 * v52) ^ (*(_QWORD *)(a1 + 32) ^ (32 * v52)) & 0xFFFFFFFFFFFFFE1FuLL;
      v55 = *((_QWORD *)a2 + 8479);
      *(_QWORD *)(a1 + 11952) = v55;
      LODWORD(v52) = a2[16956];
      v140 = (2 * (v52 & 0xFFC0)) & 0x180 ^ (v54 & 0xE7F | (unsigned __int64)(v55 << 12));
    }
  }
  v56 = ((unsigned int)v52 >> 4) & 3;
  v10 = *(_QWORD *)(a1 + 32) & 0xFFFFFFFFFFFFCFFFuLL | ((unsigned __int64)v56 << 12);
  *(_QWORD *)(a1 + 32) = v10;
  if ( v56 )
  {
    LODWORD(v4) = -1073741811;
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2725);
    goto LABEL_79;
  }
  if ( _bittest64((const signed __int64 *)a2 + 4, 0x34u) )
  {
    if ( (v49 & 0x200) != 0 || (v10 & 0x1E0) != 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2735);
      goto LABEL_79;
    }
    v31 |= 0x100000000uLL;
    v10 |= 0x8000uLL;
    v135 = v31;
    *(_QWORD *)(a1 + 32) = v10;
  }
  if ( (*((_QWORD *)a2 + 4) & 0x400000000LL) != 0 )
  {
    v10 |= 0x400uLL;
    *(_QWORD *)(a1 + 32) = v10;
  }
  v57 = *((_QWORD *)a2 + 4);
  if ( (v57 & 0x40000000000000LL) != 0 )
  {
    v31 |= 0x400000000uLL;
    v135 = v31;
  }
  if ( (v49 & 0x8000) == 0 )
  {
    v58 = v31 | 0x200;
    if ( (v49 & 0x10) != 0 )
      v58 = v31;
    v59 = v49 & 0x20;
    v60 = v58 | 0x400;
    if ( v59 )
      v60 = v58;
    v10 &= 0x4000u;
    v61 = v60 | 0x40000000;
    if ( !v10 )
      v61 = v60;
    if ( (v57 & 0x10000) != 0 )
    {
      v62 = v61 | 0x10000000;
      if ( !v59 )
        v62 = v61;
    }
    else
    {
      v62 = v61 | 0x800;
    }
    v135 = v62;
  }
  if ( (v57 & 0x20000000000000LL) != 0 )
  {
    LODWORD(v4) = -1073741637;
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2813);
    goto LABEL_79;
  }
  v63 = a2[10];
  if ( v63 )
  {
    v64 = 0;
    v10 = a2[12] & 0x7F;
    while ( *((unsigned __int8 *)a2 + v64 + 184) < (unsigned int)v10 )
    {
      if ( ++v64 >= v63 )
        goto LABEL_265;
    }
    LODWORD(v4) = -1073741811;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(&v152[4], "VidPartitionIoctlSetup");
      tlgCreate1Sz_char(&v152[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
      v134 = v65;
      v152[8] = (char *)&v132 + 4;
      HIDWORD(v132) = 2828;
      v152[10] = &v134;
      v136 = *((_BYTE *)a2 + v66 + 184);
      v152[9] = 4;
      v152[12] = &v136;
      v152[11] = 4;
      v152[13] = 1;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_14004776A, 0, 0, 7, v152);
    }
    goto LABEL_79;
  }
LABEL_265:
  LOBYTE(v10) = a2[12] & 0x7F;
  if ( !(unsigned __int8)VsmmNumaArePartitionSettingsValid(
                           (_DWORD)v133,
                           v10,
                           (int)a2 + 52,
                           (int)a2 + 116,
                           (*(_DWORD *)(a1 + 16) & 0x8000LL) != 0) )
  {
    LODWORD(v4) = -1070137329;
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2845);
    goto LABEL_79;
  }
  memmove((void *)(a1 + 2041), a2 + 13, a2[12] & 0x7F);
  memmove((void *)(a1 + 2105), a2 + 29, a2[12] & 0x7F);
  if ( *((_QWORD *)a2 + 8547) )
  {
    LODWORD(v4) = VidResourcePartitionPartitionSetup(a1);
    if ( (v4 & 0x80000000) != 0LL )
    {
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2876);
      goto LABEL_79;
    }
  }
  LODWORD(v4) = VsmmMemPartSetupPartition(a1, *((_QWORD *)a2 + 8548));
  if ( (v4 & 0x80000000) != 0LL )
  {
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2892);
    goto LABEL_79;
  }
  LOBYTE(v67) = a2[12] & 0x7F;
  LODWORD(v4) = VsmmPartitionSetup(a1, v67);
  if ( (v4 & 0x80000000) != 0LL )
  {
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2901);
    goto LABEL_79;
  }
  v68 = 0;
  v69 = 0;
  v70 = *(_QWORD *)(a1 + 1528);
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 16) & 0xFFFFFFFFFFFFFF7FuLL | ((unsigned __int64)(a2[8] & 2) << 6);
  *(_QWORD *)(v70 + 376) = *(unsigned __int8 *)(a1 + 2041);
  if ( (a2[12] & 0x7F) != 0 )
  {
    v71 = v133;
    do
    {
      v72 = v69++;
      v73 = 2LL * (unsigned int)v72;
      v74 = *(_QWORD *)(v71[33] + 8LL * *(unsigned __int8 *)(v72 + a1 + 2105));
      *(_OWORD *)(a1 + 8 * v73 + 2176) = 0;
      *(_WORD *)(a1 + 8 * v73 + 2184) = *(_WORD *)(*(_QWORD *)(v74 + 16) + 8LL);
      *(_QWORD *)(a1 + 16 * (v72 + 136)) = **(_QWORD **)(v74 + 16);
      v68 |= 1LL << *(_BYTE *)(v72 + a1 + 2105);
    }
    while ( v69 < (a2[12] & 0x7F) );
    v28 = 0x1000000000000LL;
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 1528) + 912LL) = v68;
  v75 = *((_QWORD *)a2 + 4);
  if ( (v75 & 0x800) != 0 )
  {
    VsmmMemTrackerDisable(a1);
    v76 = *((_QWORD *)a2 + 4) >> 41;
    LOBYTE(v76) = (*((_QWORD *)a2 + 4) & 0x20000000000LL) != 0;
    LODWORD(v4) = VsmmPhuPartitionRestore(a1, v76);
    if ( (v4 & 0x80000000) != 0LL )
    {
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2957);
      goto LABEL_79;
    }
  }
  else
  {
    if ( (v75 & 0x20000000000LL) != 0 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 2966);
      goto LABEL_79;
    }
    *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 32) & 0xFFFFFFFFFFFBFFFFuLL
                         | ((*(_QWORD *)(a1 + 32) & 0xB1E0LL) != 0 ? 0x40000 : 0);
  }
  v77 = *(_QWORD *)(a1 + 8648);
  if ( v77 && *(_BYTE *)(v77 + 1176) )
  {
    v78 = (8LL * *(_QWORD *)(v77 + 1168))
        ^ (*(_QWORD *)(a1 + 32)
         ^ (8LL * *(_QWORD *)(v77 + 1168)))
        & 0xFFFFFFFFFFFFFDFFuLL;
  }
  else
  {
    UINT32WithDefault = 0;
    if ( v138 )
      UINT32WithDefault = VidRegistryQueryUINT32WithDefault(v138, L"ForceSmallGpaMappings", 0);
    v78 = (UINT32WithDefault != 0 ? 0x200 : 0) | *(_QWORD *)(a1 + 32) & 0xFFFFFFFFFFFFFDFFuLL;
  }
  *(_QWORD *)(a1 + 32) = v78;
  v80 = v135;
  if ( (v78 & 0x200) != 0 )
  {
    v80 = v135 & 0xFFFFFFFFFFFFFFE7uLL | 8;
    v135 = v80;
  }
  if ( v17 )
  {
    v80 |= 0x100000u;
    v135 = v80;
    *(_QWORD *)(a1 + 32) = v78 | 0x800;
  }
  if ( (*(_DWORD *)(a1 + 16) & 0x8000LL) == 0 && (*((_DWORD *)VidDeviceExtension + 162) & 0x800) != 0 )
  {
    v80 |= 0x20000000u;
    v135 = v80;
  }
  VidNumaSetGroupAffinity(a1, 0, v150);
  v81 = *(unsigned __int8 *)(a1 + 2105);
  v82 = *(_QWORD *)(a1 + 16);
  v83 = v81 | 0x80000000;
  v137 = 0;
  v141 = 0;
  if ( (v82 & 0x80u) != 0LL )
    v83 = v81;
  if ( *(_DWORD *)(a1 + 8632) == 2 && *(_DWORD *)(a1 + 8636) == 2 )
  {
    v84 = *(_QWORD *)(a1 + 8648);
    if ( *(_BYTE *)(v84 + 1176) )
    {
      v85 = *a2;
      v147[0] = v80;
      v147[1] = v85;
      v148 = 0;
      v149 = 0;
      VsmmPhuStoreCreationPropertiesSerialize(a2 + 2, v147, v83);
      LODWORD(v149) = a2[10];
      VsmmPhuStoreHvPartitionMakeInvariantFlags(a1 + 16, a1 + 40, (char *)&v149 + 8);
      LODWORD(v4) = VsmmPhuStoreHvPartitionRestore(a1, v84 + 1128, v147);
      if ( (v4 & 0x80000000) != 0LL )
      {
        VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3103);
        goto LABEL_79;
      }
      v6 = 1;
      LODWORD(v4) = VidPartitionpPrivilegesUpdate(a1, &v137, &v141);
      if ( (v4 & 0x80000000) != 0LL )
      {
        VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3119);
        goto LABEL_309;
      }
LABEL_372:
      *(_QWORD *)(a1 + 672) = v80;
      *(_DWORD *)(a1 + 680) = *a2;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qiddd(WPP_GLOBAL_Control->AttachedDevice, a2[12] & 0x7F, v86, a1, *(_QWORD *)(a1 + 648), a2[10]);
      }
      v104 = *(_QWORD *)(a1 + 16);
      if ( (v104 & 0x8000) == 0 && (*(_DWORD *)(a1 + 32) & 0x1E0LL) == 0 )
        *(_QWORD *)(a1 + 16) = (v137 >> 50) & 0x3FFC ^ (v104 ^ (v137 >> 50) & 0x3FFC) & 0xFFFFFFFFFFFFFFFBuLL;
      if ( (((*(_DWORD *)(a1 + 32) & 0x1E0) - 64LL) & 0xFFFFFFFFFFFFFFDFuLL) == 0 && !*(_BYTE *)(a1 + 8760) )
      {
        if ( *((_QWORD *)a2 + 8480) )
        {
          LODWORD(v4) = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
          if ( (v4 & 0x80000000) != 0LL )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3461);
            goto LABEL_348;
          }
        }
      }
      LODWORD(v4) = VidPdcNotifyPartitionCreation(a1);
      if ( (v4 & 0x80000000) != 0LL )
      {
        VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3473);
        goto LABEL_348;
      }
      if ( (*(_DWORD *)(a1 + 16) & 0x8010LL) == 0 && (int)*a2 >= 1536 )
      {
        v105 = *(_QWORD *)(a1 + 648);
        v135 = 0;
        LODWORD(v4) = WinHvGetPartitionProperty(v105, 327681, &v135);
        if ( (v4 & 0x80000000) != 0LL )
        {
          VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3491);
          goto LABEL_348;
        }
        if ( *(_BYTE *)(a1 + 8760) )
        {
          if ( (v135 & 0xF) != 0 )
          {
            LODWORD(v4) = -1070268335;
            if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
              goto LABEL_348;
            tlgCreate1Sz_char(&v152[4], "VidPartitionIoctlSetup");
            tlgCreate1Sz_char(&v152[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
            v134 = 3517;
            v152[8] = &v134;
            v100 = (char *)&dword_1400475BC;
            v152[10] = (char *)&v132 + 4;
            v101 = v135;
LABEL_335:
            *(_QWORD *)&v139 = v101;
            goto LABEL_336;
          }
        }
        else
        {
          v106 = *(_QWORD *)(a1 + 648);
          v135 &= 0xFFFFFFFFFFFFFFF0uLL;
          LODWORD(v4) = WinHvSetPartitionProperty(v106);
          if ( (v4 & 0x80000000) != 0LL )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3506);
            goto LABEL_348;
          }
        }
      }
      LODWORD(v4) = WinHvGetPartitionProperty(*(_QWORD *)(a1 + 648), 393236, &v145);
      if ( (v4 & 0x80000000) != 0LL )
      {
        VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3529);
        goto LABEL_348;
      }
      if ( v145 > 0x34 )
      {
        LODWORD(v4) = -1070268406;
        VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3538);
        goto LABEL_348;
      }
      v107 = *(_QWORD *)(a1 + 32);
      v108 = (1LL << ((unsigned __int8)v145 - 12)) - 1;
      *(_QWORD *)(a1 + 10456) = v108;
      if ( (v107 & 0x4000) != 0 )
        *(_QWORD *)(a1 + 10464) = v108;
      v109 = *(_QWORD *)(a1 + 16);
      if ( (v109 & 0x8000) != 0 )
      {
        *(_DWORD *)(a1 + 10652) = (v107 & 0x18) != 0;
        LODWORD(v4) = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
        if ( (v4 & 0x80000000) != 0LL )
        {
          VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3592);
          goto LABEL_348;
        }
        v109 = *(_QWORD *)(a1 + 16);
      }
      v110 = v143;
      if ( (v109 & 0x200) == 0 && (*((_QWORD *)a2 + 8472) != (_QWORD)v143 || *((_QWORD *)a2 + 8473) != (_QWORD)v139) )
      {
        LODWORD(v4) = -1073741811;
        VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3609);
        goto LABEL_348;
      }
      if ( (v109 & 0x400) != 0 && !*(_BYTE *)(a1 + 8762) )
      {
        v111 = (v109 >> 11) & 3;
        LODWORD(v4) = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
        if ( (v4 & 0x80000000) != 0LL )
        {
          if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
            goto LABEL_348;
          tlgCreate1Sz_char(&v152[4], "VidPartitionIoctlSetup");
          tlgCreate1Sz_char(&v152[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
          v134 = 3635;
          v152[8] = &v134;
          v100 = byte_14004755D;
          *(_QWORD *)&v139 = (unsigned int)v111;
          v152[10] = (char *)&v132 + 4;
LABEL_336:
          v152[12] = &v139;
          v130 = 7;
LABEL_337:
          v152[13] = 8;
          goto LABEL_338;
        }
      }
      if ( (a2[8] & 0x20000000) != 0 && !*(_BYTE *)(a1 + 8762) )
      {
        v112 = 0;
        while ( 1 )
        {
          LODWORD(v4) = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
          if ( (v4 & 0x80000000) != 0LL )
            break;
          if ( (unsigned int)++v112 >= 4 )
            goto LABEL_422;
        }
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_348;
        tlgCreate1Sz_char(&v152[4], "VidPartitionIoctlSetup");
        tlgCreate1Sz_char(&v152[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
        v134 = 3663;
        v152[8] = &v134;
        v100 = byte_140047515;
        LODWORD(v137) = v112;
        v152[10] = (char *)&v132 + 4;
        v152[12] = &v137;
        v130 = 7;
        v152[13] = 4;
LABEL_338:
        v152[9] = 4;
        HIDWORD(v132) = v4;
        v152[11] = 4;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v100, 0, 0, v130, v152);
        goto LABEL_348;
      }
LABEL_422:
      v113 = *(_QWORD *)(a1 + 32);
      if ( (v113 & 0x31E0) == 0 )
      {
        v114 = *(_QWORD *)(a1 + 16);
        if ( (v114 & 0x210) == 0 && (v113 & 0x8000) == 0 && !_bittest64((const signed __int64 *)a2 + 4, 0x38u) )
        {
          for ( i = 0; i < 2; ++i )
          {
            v116 = (unsigned int)i;
            v114 |= v116 + 1;
          }
          *(_QWORD *)(a1 + 16) = v114;
        }
      }
      LODWORD(v4) = VsmmProcessHostingProcessNamePopulate(a1, a2 + 16962);
      if ( (v4 & 0x80000000) != 0LL )
      {
        VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3697);
        goto LABEL_348;
      }
      v117 = *(_QWORD *)(a1 + 16);
      if ( (v117 & 0x200) != 0 )
      {
        if ( *((_QWORD *)a2 + 8472) != v110 || *((_QWORD *)a2 + 8473) != (_QWORD)v139 )
        {
          v139 = *((_OWORD *)a2 + 4236);
          LODWORD(v4) = VsmmCloneTemplateApply(a1, &v139);
          if ( (v4 & 0x80000000) != 0LL )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3731);
            goto LABEL_348;
          }
          v7 = 1;
LABEL_444:
          LODWORD(v4) = VsmmProcessVpThreadHostingSetup(a1);
          if ( (v4 & 0x80000000) != 0LL )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3746);
            goto LABEL_446;
          }
          if ( v17 )
          {
            LODWORD(v4) = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
            if ( (v4 & 0x80000000) != 0LL )
            {
              if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
              {
                tlgCreate1Sz_char(&v152[4], "VidPartitionIoctlSetup");
                tlgCreate1Sz_char(&v152[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
                LODWORD(v137) = 3763;
                v152[8] = &v137;
                v152[9] = 4;
                v152[10] = &v134;
                v134 = v4;
                v152[12] = &v139;
                v152[11] = 4;
                *(_QWORD *)&v139 = v17;
                v152[13] = 8;
                tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_1400474B3, 0, 0, 7, v152);
              }
              goto LABEL_446;
            }
          }
          LODWORD(v4) = VidThreadPoolThreadAdd(a1 + 3488);
          if ( (v4 & 0x80000000) != 0LL )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3781);
            goto LABEL_446;
          }
          v118 = *(_DWORD *)(a1 + 16);
          *(_BYTE *)(a1 + 3728) = 1;
          if ( (v118 & 0x8000) == 0 )
          {
            VsmmHvMemPreDepositForVps(a1, a2[10]);
            Pool2 = ExAllocatePool2(64, 2512LL * a2[10], 1917084758);
            *(_QWORD *)(a1 + 3208) = Pool2;
            if ( !Pool2 )
            {
              LODWORD(v4) = -1073741670;
              VidTraceErrorStatusInternal0(
                "VidPartitionIoctlSetup",
                "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
                3802);
              goto LABEL_446;
            }
            v120 = 0;
            if ( a2[10] )
            {
              while ( 1 )
              {
                LODWORD(v4) = VidVpCreate(a1, v120, a2 + 46);
                if ( (v4 & 0x80000000) != 0LL )
                  break;
                if ( ++v120 >= a2[10] )
                  goto LABEL_461;
              }
              VidTraceErrorStatusInternal0(
                "VidPartitionIoctlSetup",
                "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
                3820);
              goto LABEL_446;
            }
          }
LABEL_461:
          v121 = *(_QWORD *)(a1 + 32) & 0x1E0LL;
          switch ( v121 )
          {
            case ' ':
              if ( v6 )
              {
                *(_BYTE *)(a1 + 8848) = 1;
              }
              else
              {
                LODWORD(v4) = VsmmSvcPartitionSetup(a1);
                if ( (v4 & 0x80000000) != 0LL )
                {
                  VidTraceErrorStatusInternal0(
                    "VidPartitionIoctlSetup",
                    "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
                    3837);
                  goto LABEL_446;
                }
              }
              goto LABEL_467;
            case '@':
              LODWORD(v4) = VidSnpPartitionInitialize(a1);
              if ( (v4 & 0x80000000) != 0LL )
              {
                VidTraceErrorStatusInternal0(
                  "VidPartitionIoctlSetup",
                  "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
                  3865);
                goto LABEL_446;
              }
              if ( !_bittest64((const signed __int64 *)a2 + 2, 0x34u) )
                *(_QWORD *)(a1 + 32) |= 0x20000uLL;
              break;
            case '`':
              break;
            default:
LABEL_467:
              LODWORD(v4) = VsmmVsmPartitionHypervisorSetup(a1);
              if ( (v4 & 0x80000000) == 0LL )
              {
                if ( VID_TRACE_ETW_GUID_Context
                  && EtwEventEnabled(VID_TRACE_ETW_GUID_Context, &MSVML_VID_PARTITION_INFORMATION) )
                {
                  VidTraceStr1Int1Routine(&MSVML_VID_PARTITION_INFORMATION);
                }
                v3 = v133;
                LODWORD(v4) = VidPartitionTableInsertById(v133, a1);
                if ( (v4 & 0x80000000) == 0LL )
                {
                  v6 = 1;
                  v10 = 1;
                  v5 = 1;
                  *(_DWORD *)(a1 + 48) = 1;
                  goto LABEL_82;
                }
                VidTraceErrorStatusInternal0(
                  "VidPartitionIoctlSetup",
                  "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
                  3909);
LABEL_447:
                v6 = 1;
                v5 = 0;
                goto LABEL_82;
              }
              VidTraceErrorStatusInternal0(
                "VidPartitionIoctlSetup",
                "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
                3887);
LABEL_446:
              v3 = v133;
              goto LABEL_447;
          }
          LODWORD(v4) = VsmmHwIsoPartitionSetup(a1);
          if ( (v4 & 0x80000000) != 0LL )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3879);
            goto LABEL_446;
          }
          goto LABEL_467;
        }
        if ( (v117 & 0x8000) == 0 )
        {
          LODWORD(v4) = VsmmProcessMemoryHostingSetup(a1);
          if ( (v4 & 0x80000000) != 0LL )
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSetup",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              3719);
            goto LABEL_348;
          }
        }
      }
      v7 = 0;
      goto LABEL_444;
    }
  }
  v87 = *a2;
  v144 = -1;
  LODWORD(v4) = WinHvCreatePartitionEx(v80, v142, v83, v87, a2 + 2, &v140);
  if ( (v4 & 0x80000000) != 0LL )
  {
    VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3153);
    goto LABEL_79;
  }
  v88 = *(_OWORD *)(a1 + 656);
  *(_QWORD *)(a1 + 648) = v144;
  v142 = v88;
  v6 = 1;
  VidTraceRoutineGuidWithUint64(&VID_EVT_HV_PARTITION_ID);
  if ( (*(_DWORD *)(a1 + 32) & 0x8000LL) != 0 )
  {
    memset(v168, 0, sizeof(v168));
    memset(v152, 0, 0x80u);
    v89 = a2[10];
    for ( j = 0; (unsigned int)j < v89; ++*((_WORD *)v152 + v91) )
    {
      v91 = *((unsigned __int8 *)a2 + j + 184);
      j = (unsigned int)(j + 1);
    }
    v92 = a2[12] & 0x7F;
    if ( v92 )
    {
      v93 = 0;
      v94 = *((_QWORD *)v133 + 33);
      do
      {
        v95 = v93++;
        v168[2 * v95] = *(_DWORD *)(*(_QWORD *)(v94 + 8LL * *((unsigned __int8 *)a2 + v95 + 116)) + 416LL);
        LOWORD(v168[2 * v95 + 1]) = *((_WORD *)v152 + v95);
      }
      while ( v93 < v92 );
    }
    LODWORD(v4) = WinHvSetPartitionPropertyEx(*(_QWORD *)(a1 + 648), 589828, 0, v168, 8 * (a2[12] & 0x7F));
    if ( (v4 & 0x80000000) != 0LL )
    {
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(&v152[4], "VidPartitionIoctlSetup");
        tlgCreate1Sz_char(&v152[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
        v134 = 3203;
        v152[8] = &v134;
        v152[9] = 4;
        v152[10] = (char *)&v132 + 4;
        HIDWORD(v132) = v4;
        v152[12] = &v139;
        v152[11] = 4;
        *(_QWORD *)&v139 = 589828;
        v152[13] = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &byte_14004769F, 0, 0, 7, v152);
      }
      goto LABEL_309;
    }
  }
  if ( !a2[17098] )
  {
LABEL_342:
    if ( (v80 & 0x100000) != 0 && (unsigned __int8)WinHvIsOverlayMapLocationRequired() )
    {
      LODWORD(v4) = VidHvMemAllocatePagesForOverlay(a1, 2, a1 + 10888);
      if ( (v4 & 0x80000000) != 0LL )
      {
        VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3299);
        goto LABEL_348;
      }
      LODWORD(v4) = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
      if ( (v4 & 0x80000000) != 0LL )
      {
        VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3310);
        goto LABEL_348;
      }
    }
    if ( (*(_DWORD *)(a1 + 24) & 0x40000) != 0 )
    {
      LODWORD(v4) = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
      if ( (v4 & 0x80000000) != 0LL )
      {
        VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3324);
        goto LABEL_348;
      }
    }
    v102 = *(_QWORD *)(a1 + 16);
    if ( (v102 & 0x8000) == 0 )
    {
      v103 = (a2[8] & 1) == 0;
      v137 = 0x3000000000LL;
      if ( !v103 )
      {
        if ( (*(_BYTE *)(a1 + 40) & 4) != 0 )
        {
          LODWORD(v4) = -1073741811;
          VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3355);
          goto LABEL_348;
        }
        v137 = 0x83000000000LL;
      }
      if ( (v102 & 0x10) == 0 && (int)*a2 >= 1536 )
      {
        v141 = 0x1000000000000LL;
        if ( (v102 & 0x20) == 0 )
        {
          if ( (*(_DWORD *)(a1 + 32) & 0x1E0LL) == 0 )
            v28 = 0x3000000000000LL;
          v141 = v28;
        }
      }
      LODWORD(v4) = VidPartitionpPrivilegesUpdate(a1, &v137, &v141);
      if ( (v4 & 0x80000000) != 0LL )
      {
        VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3400);
        goto LABEL_348;
      }
    }
    LODWORD(v4) = WinHvInitializePartition(*(_QWORD *)(a1 + 648));
    if ( (v4 & 0x80000000) != 0LL )
    {
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3412);
      goto LABEL_348;
    }
    v6 = 0;
    goto LABEL_372;
  }
  v96 = (char *)a2 + a2[17099];
  v97 = 0;
  HIDWORD(v132) = 0;
  while ( 1 )
  {
    if ( (*(_DWORD *)(a1 + 32) & 0x8000LL) != 0 && *(_DWORD *)&v96[16 * v97] == 589828 )
    {
      LODWORD(v4) = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSetup", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 3249);
      goto LABEL_348;
    }
    v98 = 2LL * v97;
    v99 = 0;
    if ( *(_DWORD *)&v96[16 * v97] == 589831
      || *(_DWORD *)&v96[16 * v97] == 589833
      || *(_DWORD *)&v96[16 * v97] == 589838 )
    {
      v99 = 1;
    }
    if ( !v99 )
      break;
    LODWORD(v4) = VidPartitionpSetPropertyWithPayload(
                    a1,
                    (_DWORD)a2,
                    v134,
                    *(_DWORD *)&v96[16 * v97],
                    *(_QWORD *)&v96[16 * v97 + 8]);
    if ( (v4 & 0x80000000) != 0LL )
    {
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(&v152[4], "VidPartitionIoctlSetup");
        tlgCreate1Sz_char(&v152[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
        v134 = 3266;
        v152[8] = &v134;
        v100 = byte_140047705;
        v152[10] = (char *)&v132 + 4;
        v101 = *(int *)&v96[8 * v98];
        goto LABEL_335;
      }
      goto LABEL_348;
    }
LABEL_340:
    v97 = HIDWORD(v132) + 1;
    HIDWORD(v132) = v97;
    if ( v97 >= a2[17098] )
    {
      v80 = v135;
      goto LABEL_342;
    }
  }
  LODWORD(v4) = WinHvSetPartitionProperty(*(_QWORD *)(a1 + 648));
  if ( (v4 & 0x80000000) == 0LL )
    goto LABEL_340;
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(&v152[4], "VidPartitionIoctlSetup");
    tlgCreate1Sz_char(&v152[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
    v134 = 3281;
    v152[8] = &v134;
    v100 = (char *)word_140047612;
    v152[15] = 8;
    v152[10] = (char *)&v132 + 4;
    *(_QWORD *)&v139 = *(int *)&v96[8 * v98];
    v152[12] = &v139;
    *(_QWORD *)&v143 = *(_QWORD *)&v96[8 * v98 + 8];
    v152[14] = &v143;
    v130 = 8;
    goto LABEL_337;
  }
LABEL_348:
  v6 = 1;
LABEL_309:
  v5 = 0;
  v3 = v133;
  v7 = 0;
LABEL_82:
  if ( v138 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1848))(WdfDriverGlobals, v138);
  if ( (v4 & 0x80000000) != 0LL && !*(_DWORD *)(a1 + 48) )
  {
    *(_DWORD *)(a1 + 48) = 2;
    if ( v6 )
    {
      if ( v5 )
        VidPartitionTableRemoveById(v3, a1);
      while ( 1 )
      {
        v122 = *(_DWORD *)(a1 + 3200);
        if ( !v122 )
          break;
        LOBYTE(v10) = 1;
        VidVpDelete(*(_QWORD *)(a1 + 3208) + 2512LL * (unsigned int)(v122 - 1), v10);
      }
      v123 = *(void **)(a1 + 3208);
      if ( v123 )
      {
        ExFreePoolWithTag(v123, 0x72446456u);
        *(_QWORD *)(a1 + 3208) = 0;
      }
      if ( *(_BYTE *)(a1 + 3728) )
      {
        VidThreadPoolThreadRemove(a1 + 3488, 0);
        *(_BYTE *)(a1 + 3728) = 0;
      }
      if ( v7 )
        VsmmClonePartitionTeardown(a1);
      VidHypercallDoorbellFree(a1);
      VsmmProcessTeardown(a1);
      VsmmPhuHvPartitionTeardown(a1);
      if ( *(_QWORD *)(a1 + 648) != -1 )
      {
        WinHvDeletePartition();
        *(_QWORD *)(a1 + 648) = -1;
      }
    }
    VsmmPhuPartitionTeardown(a1);
    VsmmPartitionSetupUndo(a1);
    VsmmMemPartTeardownPartition(a1);
    *(_OWORD *)(a1 + 16) = v12;
    *(_QWORD *)(a1 + 32) = v11;
  }
  VidNumaRevertGroupAffinity(v150);
  if ( (*(_DWORD *)(a1 + 16) & 0x200LL) != 0 )
  {
    v125 = *(_QWORD *)(a1 + 24);
    v126 = v125 >> 9;
    v131 = *(_BYTE *)(a1 + 32) & 3;
    LOBYTE(v124) = *(_BYTE *)(a1 + 24) & 1;
    LOBYTE(v126) = (v125 & 4) != 0;
    v146 = *(_OWORD *)(a1 + 656);
    VidTraceGuidString_7Uint8_3Uint64(
      v126,
      (unsigned int)&v146,
      a1 + 120,
      v124,
      (v125 & 2) != 0,
      (v125 & 0x40) != 0,
      v126,
      (v125 & 8) != 0,
      (v125 & 0x10) != 0,
      (unsigned __int8)v125 >> 7,
      v131,
      1LL << ((v125 >> 9) & 0xF),
      1LL << ((v125 >> 13) & 0xF));
    *(_QWORD *)(*(_QWORD *)(a1 + 1528) + 2256LL) = *(_QWORD *)(a1 + 24);
  }
  VidObjectLockRelease(a1 + 3736);
  VidObjectLockRelease(a1);
  if ( (v4 & 0x80000000) != 0LL
    && (unsigned int)dword_140064110 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(&v152[4], "VidPartitionIoctlSetup");
    tlgCreate1Sz_char(&v152[6], "onecore\\vm\\vid\\sys\\driver\\vidpartition.c");
    LODWORD(v137) = 4066;
    v152[13] = (unsigned int)(v127 + 16);
    v152[8] = &v137;
    v159 = v152[13];
    v152[10] = &v134;
    v165 = v152[13];
    v152[12] = a1 + 656;
    v152[14] = v153;
    v152[16] = *(_QWORD *)(a1 + 128);
    v153[0] = *(unsigned __int16 *)(a1 + 120);
    *(_QWORD *)&v146 = *(_QWORD *)(a1 + 648);
    v154 = &v146;
    HIDWORD(v132) = *a2;
    v156 = (char *)&v132 + 4;
    v158 = a2 + 2;
    v128 = a2[12] & 0x7F;
    v152[9] = 4;
    LODWORD(v135) = v128;
    v160 = &v135;
    LODWORD(v133) = a2[10];
    v162 = &v133;
    v164 = a2 + 16944;
    *(_QWORD *)&v139 = *((_QWORD *)a2 + 4);
    v166 = &v139;
    v134 = v4;
    v152[11] = 4;
    v152[15] = 2;
    v153[1] = v127;
    v155 = 8;
    v157 = 4;
    v161 = 4;
    v163 = 4;
    v167 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_1400473DA, v127, 0, v127 + 16, v152);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14008d084  mov     rax, rsp
0x14008d087  mov     [rax+20h], rbx
0x14008d08b  push    rbp
0x14008d08c  push    rsi
0x14008d08d  push    rdi
0x14008d08e  push    r12
0x14008d090  push    r13
0x14008d092  push    r14
0x14008d094  push    r15
0x14008d096  lea     rbp, [rax-3D8h]
0x14008d09d  sub     rsp, 4A0h
0x14008d0a4  movaps  xmmword ptr [rax-48h], xmm6
0x14008d0a8  movaps  xmmword ptr [rax-58h], xmm7
0x14008d0ac  mov     rax, cs:__security_cookie
0x14008d0b3  xor     rax, rsp
0x14008d0b6  mov     [rbp+3D0h+var_60], rax
0x14008d0bd  mov     rbx, cs:VidDeviceExtension
0x14008d0c4  xor     r15d, r15d
0x14008d0c7  xorps   xmm0, xmm0
0x14008d0ca  mov     qword ptr [rbp+3D0h+var_400], r15
0x14008d0ce  xor     eax, eax
0x14008d0d0  mov     byte ptr [rsp+4D0h+var_460], r15b
0x14008d0d5  movups  [rbp+3D0h+var_390], xmm0
0x14008d0d9  mov     [rbp+3D0h+var_370], rax
0x14008d0dd  mov     dil, r15b
0x14008d0e0  movups  [rbp+3D0h+var_380], xmm0
0x14008d0e4  mov     sil, r15b
0x14008d0e7  mov     byte ptr [rsp+4D0h+var_460+1], r15b
0x14008d0ec  mov     r14b, r15b
0x14008d0ef  mov     byte ptr [rsp+4D0h+var_460+2], r15b
0x14008d0f4  mov     [rbp+3D0h+var_410], r15
0x14008d0f8  mov     r12, rdx
0x14008d0fb  mov     [rbp+3D0h+var_3D8], r15
0x14008d0ff  mov     r13, rcx
0x14008d102  movups  [rbp+3D0h+var_3F0], xmm0
0x14008d106  mov     [rsp+4D0h+var_458], rbx
0x14008d10b  mov     [rbp+3D0h+var_450], r8d
0x14008d10f  call    VidObjectLockAcquireExclusive
0x14008d114  lea     rcx, [r13+0E98h]
0x14008d11b  call    VidObjectLockAcquireExclusive
0x14008d120  lea     rcx, [rbp+3D0h+var_400]
0x14008d124  call    VidRegistryOpenParametersKey
0x14008d129  lea     r10, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008d130  mov     rax, qword ptr [rbp+3D0h+var_400]
0x14008d134  lea     r11, aVidpartitionio_11; "VidPartitionIoctlSetup"
0x14008d13b  movsd   xmm7, qword ptr [r13+20h]
0x14008d141  movups  xmm6, xmmword ptr [r13+10h]
0x14008d146  mov     [rbp+3D0h+var_430], rax
0x14008d14a  cmp     [r13+30h], r15d
0x14008d14e  jz      short loc_14008D188
0x14008d150  mov     eax, [r12+20h]
0x14008d155  bt      rax, 0Bh
0x14008d15a  jnb     short loc_14008D169
0x14008d15c  cmp     [r13+21D1h], r15b
0x14008d163  jnz     loc_14008D5C8
0x14008d169  mov     r9d, 0C000000Dh
0x14008d16f  mov     r15d, r9d
0x14008d172  mov     r8d, 6F1h
0x14008d178  mov     rdx, r10
0x14008d17b  mov     rcx, r11
0x14008d17e  call    VidTraceErrorStatusInternal0
0x14008d183  jmp     loc_14008D5C8
0x14008d188  mov     rcx, 0FE00000000000000h
0x14008d192  mov     [r13+28h], r15
0x14008d196  test    [r12+20h], rcx
0x14008d19b  jz      short loc_14008D1BC
0x14008d19d  mov     r9d, 0C000000Dh
0x14008d1a3  mov     r15d, r9d
0x14008d1a6  mov     r8d, 6FFh
0x14008d1ac  mov     rdx, r10
0x14008d1af  mov     rcx, r11
0x14008d1b2  call    VidTraceErrorStatusInternal0
0x14008d1b7  jmp     loc_14008D5C8
0x14008d1bc  mov     rcx, [r13+10h]
0x14008d1c0  mov     eax, [r12+28h]
0x14008d1c5  mov     rdx, rcx
0x14008d1c8  and     edx, 8000h
0x14008d1ce  jz      short loc_14008D1F3
0x14008d1d0  test    eax, eax
0x14008d1d2  jz      short loc_14008D200
0x14008d1d4  mov     r9d, 0C000000Dh
0x14008d1da  mov     r15d, r9d
0x14008d1dd  mov     r8d, 708h
0x14008d1e3  mov     rdx, r10
0x14008d1e6  mov     rcx, r11
0x14008d1e9  call    VidTraceErrorStatusInternal0
0x14008d1ee  jmp     loc_14008D5C8
0x14008d1f3  dec     eax
0x14008d1f5  cmp     eax, 7FFh
0x14008d1fa  ja      loc_14008F83E
0x14008d200  mov     eax, [r12]
0x14008d204  sub     eax, 600h
0x14008d209  cmp     eax, 0F900h
0x14008d20e  ja      loc_14008F81F
0x14008d214  test    rdx, rdx
0x14008d217  mov     r9b, 30h ; '0'
0x14008d21a  lea     rdx, [r12+108F0h]
0x14008d222  jnz     short loc_14008D233
0x14008d224  mov     eax, [rdx]
0x14008d226  test    r9b, al
0x14008d229  jnz     short loc_14008D233
0x14008d22b  or      rcx, 10h
0x14008d22f  mov     [r13+10h], rcx
0x14008d233  mov     al, [r12+20h]
0x14008d238  test    al, al
0x14008d23a  jns     short loc_14008D244
0x14008d23c  and     rcx, 0FFFFFFFFFFFFFFEFh
0x14008d240  mov     [r13+10h], rcx
0x14008d244  mov     r8, [r12+20h]
0x14008d249  bt      r8, 1Eh
0x14008d24e  jnb     short loc_14008D27A
0x14008d250  mov     eax, [rdx]
0x14008d252  test    r9b, al
0x14008d255  jnz     short loc_14008D2A7
0x14008d257  bt      r8, 20h ; ' '
0x14008d25c  jnb     short loc_14008D268
0x14008d25e  cmp     dword ptr [r12], 605h
0x14008d266  jz      short loc_14008D272
0x14008d268  cmp     dword ptr [r12], 607h
0x14008d270  jl      short loc_14008D2A7
0x14008d272  or      rcx, 20h
0x14008d276  mov     [r13+10h], rcx
0x14008d27a  bt      qword ptr [r12+20h], 31h ; '1'
0x14008d281  jnb     short loc_14008D2CC
0x14008d283  test    cl, 20h
0x14008d286  jnz     short loc_14008D2C6
0x14008d288  mov     r9d, 0C000000Dh
0x14008d28e  mov     r15d, r9d
0x14008d291  mov     r8d, 745h
0x14008d297  mov     rdx, r10
0x14008d29a  mov     rcx, r11
0x14008d29d  call    VidTraceErrorStatusInternal0
0x14008d2a2  jmp     loc_14008D5C8
0x14008d2a7  mov     r9d, 0C000000Dh
0x14008d2ad  mov     r15d, r9d
0x14008d2b0  mov     r8d, 73Bh
0x14008d2b6  mov     rdx, r10
0x14008d2b9  mov     rcx, r11
0x14008d2bc  call    VidTraceErrorStatusInternal0
0x14008d2c1  jmp     loc_14008D5C8
0x14008d2c6  bts     qword ptr [r13+20h], 0Eh
0x14008d2cc  bt      qword ptr [r12+20h], 37h ; '7'
0x14008d2d3  mov     rdi, r15
0x14008d2d6  jnb     short loc_14008D2DE
0x14008d2d8  bts     qword ptr [r13+20h], 10h
0x14008d2de  test    r9b, cl
0x14008d2e1  jnz     short loc_14008D2E9
0x14008d2e3  or      rcx, 40h
0x14008d2e7  jmp     short loc_14008D2ED
0x14008d2e9  or      rcx, 8
0x14008d2ed  mov     [r13+10h], rcx
0x14008d2f1  mov     r14d, 800h
0x14008d2f7  mov     r9, qword ptr [rbp+3D0h+var_3F0+8]
0x14008d2fb  mov     rdx, qword ptr [rbp+3D0h+var_3F0]
0x14008d2ff  mov     r8, [r12+20h]
0x14008d304  mov     qword ptr [rbp+3D0h+var_420], r9
0x14008d308  mov     qword ptr [rbp+3D0h+var_3F0], rdx
0x14008d30c  bt      rcx, 0Fh
0x14008d311  jnb     loc_14008D43F
0x14008d317  mov     rax, 0FFBED7C9FFFEFF9Fh
0x14008d321  test    rax, r8
0x14008d324  jz      short loc_14008D345
0x14008d326  mov     r9d, 0C000000Dh
0x14008d32c  mov     r15d, r9d
0x14008d32f  mov     r8d, 763h
0x14008d335  mov     rdx, r10
0x14008d338  mov     rcx, r11
0x14008d33b  call    VidTraceErrorStatusInternal0
0x14008d340  jmp     loc_14008D5C2
0x14008d345  cmp     [r12+108C0h], rdx
0x14008d34d  jnz     loc_14008D420
0x14008d353  cmp     [r12+108C8h], r9
0x14008d35b  jnz     loc_14008D420
0x14008d361  test    dword ptr [r12+30h], 180h
0x14008d36a  jz      short loc_14008D38B
0x14008d36c  mov     r9d, 0C000000Dh
0x14008d372  mov     r15d, r9d
0x14008d375  mov     r8d, 77Ah
0x14008d37b  mov     rdx, r10
0x14008d37e  mov     rcx, r11
0x14008d381  call    VidTraceErrorStatusInternal0
0x14008d386  jmp     loc_14008D5C2
0x14008d38b  bts     rcx, 9
0x14008d390  mov     r8d, 1
0x14008d396  mov     [r13+10h], rcx
0x14008d39a  mov     rax, 200000000h
0x14008d3a4  mov     rdx, [r12+20h]
0x14008d3a9  and     rdx, rax
0x14008d3ac  mov     rax, cs:VidDeviceExtension
0x14008d3b3  bts     rdx, 1Ch
0x14008d3b8  shr     rdx, 14h
0x14008d3bc  mov     ecx, [rax+288h]
0x14008d3c2  mov     rax, cs:VidDeviceExtension
0x14008d3c9  shr     rcx, 5
0x14008d3cd  and     rcx, r8
0x14008d3d0  mov     r15, rcx
0x14008d3d3  mov     eax, [rax+288h]
0x14008d3d9  bt      eax, 5
0x14008d3dd  cmovb   rdi, r8
0x14008d3e1  mov     r8, [r12+20h]
0x14008d3e6  or      r15, 2
0x14008d3ea  bt      eax, 5
0x14008d3ee  cmovnb  r15, rcx
0x14008d3f2  bt      r8, 2Dh ; '-'
0x14008d3f7  mov     qword ptr [rbp+3D0h+var_400], r15
0x14008d3fb  jnb     short loc_14008D402
0x14008d3fd  bts     rdx, 18h
0x14008d402  mov     rax, r8
0x14008d405  mov     rbx, rdx
0x14008d408  or      rbx, r14
0x14008d40b  and     eax, 10000h
0x14008d410  or      rdi, 3FFEh
0x14008d417  test    rax, rax
0x14008d41a  cmovnz  rbx, rdx
0x14008d41e  jmp     short loc_14008D46C
0x14008d420  mov     r9d, 0C000000Dh
0x14008d426  mov     r15d, r9d
0x14008d429  mov     r8d, 770h
0x14008d42f  mov     rdx, r10
0x14008d432  mov     rcx, r11
0x14008d435  call    VidTraceErrorStatusInternal0
0x14008d43a  jmp     loc_14008D5C2
0x14008d43f  bt      r8, 2Dh ; '-'
0x14008d444  jnb     short loc_14008D465
0x14008d446  mov     r9d, 0C000000Dh
0x14008d44c  mov     r15d, r9d
0x14008d44f  mov     r8d, 7B4h
0x14008d455  mov     rdx, r10
0x14008d458  mov     rcx, r11
0x14008d45b  call    VidTraceErrorStatusInternal0
0x14008d460  jmp     loc_14008D5C2
0x14008d465  mov     rbx, r15
0x14008d468  mov     qword ptr [rbp+3D0h+var_400], r15
0x14008d46c  test    r8b, 8
0x14008d470  jz      short loc_14008D4B8
0x14008d472  mov     rcx, r13
0x14008d475  call    VidCurrentProcessIsTrusted
0x14008d47a  test    eax, eax
0x14008d47c  jnz     short loc_14008D4A5
0x14008d47e  mov     r15d, 0C0000022h
0x14008d484  mov     r9d, r15d
0x14008d487  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008d48e  mov     r8d, 7C5h
0x14008d494  lea     rcx, aVidpartitionio_11; "VidPartitionIoctlSetup"
0x14008d49b  call    VidTraceErrorStatusInternal0
0x14008d4a0  jmp     loc_14008D5BD
0x14008d4a5  or      qword ptr [r13+28h], 6
0x14008d4aa  lea     r10, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008d4b1  lea     r11, aVidpartitionio_11; "VidPartitionIoctlSetup"
0x14008d4b8  test    byte ptr [r12+20h], 10h
0x14008d4be  jz      short loc_14008D4C5
0x14008d4c0  or      qword ptr [r13+28h], 2
0x14008d4c5  mov     rdx, [r12+20h]
0x14008d4ca  bt      rdx, 20h ; ' '
0x14008d4cf  jnb     short loc_14008D4D6
0x14008d4d1  bts     rbx, 0Ch
0x14008d4d6  mov     r8, 800000000h
0x14008d4e0  mov     rcx, rbx
0x14008d4e3  or      rcx, 1
0x14008d4e7  mov     rax, rdx
0x14008d4ea  test    dl, 20h
0x14008d4ed  cmovz   rcx, rbx
0x14008d4f1  and     rax, r8
0x14008d4f4  mov     r8, rcx
0x14008d4f7  bts     r8, 0Eh
0x14008d4fc  test    rax, rax
0x14008d4ff  cmovz   r8, rcx
0x14008d503  test    dl, 40h
0x14008d506  jz      short loc_14008D512
0x14008d508  or      r8, 2
0x14008d50c  bts     qword ptr [r13+10h], 8
0x14008d512  mov     r9, [r12+20h]
0x14008d517  mov     rdx, r8
0x14008d51a  bts     rdx, 0Fh
0x14008d51f  mov     rbx, 1000000000000h
0x14008d529  bt      r9, 24h ; '$'
0x14008d52e  mov     rax, r9
0x14008d531  cmovnb  rdx, r8
0x14008d535  mov     rcx, rdx
0x14008d538  bts     rcx, 1Bh
0x14008d53d  test    rbx, r9
0x14008d540  cmovz   rcx, rdx
0x14008d544  mov     rdx, 2000000000h
0x14008d54e  and     rax, rdx
0x14008d551  mov     rdx, rcx
0x14008d554  bts     rdx, 10h
0x14008d559  test    rax, rax
0x14008d55c  cmovz   rdx, rcx
0x14008d560  bt      r9, 26h ; '&'
0x14008d565  jnb     short loc_14008D56C
0x14008d567  bts     rdx, 11h
0x14008d56c  mov     rsi, rdx
0x14008d56f  mov     rax, 40000000000h
0x14008d579  bts     rsi, 12h
0x14008d57e  mov     rcx, r9
0x14008d581  bt      r9, 27h ; '''
0x14008d586  cmovnb  rsi, rdx
0x14008d58a  and     rcx, rax
0x14008d58d  jz      loc_14008D62E
0x14008d593  bt      r9, 2Bh ; '+'
  ... truncated ...
```
