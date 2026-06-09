# VsmmpReadMemoryBlockByteRange

- ea: `0x14000bc64`
- end: `0x14000d756`
- name: `VsmmpReadMemoryBlockByteRange`
- size: `6898`
- prototype: ``
- caller_count: `3`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000ad0c`
- `0x1400199c4`
- `0x1400295e0`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x140007200`
- `0x140007234`
- `0x1400085b0`
- `0x14000a4e0`
- `0x14000bc64`
- `0x14001995c`
- `0x1400212a8`
- `0x14002134c`
- `0x140021650`
- `0x140021710`
- `0x1400307d0`
- `0x140033900`
- `0x140079070`
- `0x1400d496c`
- `0x1400d51fc`
- `0x1400f2f50`
- `0x1400f8bc8`
- `0x1400f9cbc`
- `0x1400faa8c`
- `0x1400faef0`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x14000d6f8`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000d6f8`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000c0d2`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000c0d2`
- `ntoskrnl!RtlFindNextForwardRunClearEx` at `0x14000c931`
- `ntoskrnl!RtlFindNextForwardRunClearEx` at `0x14000c931`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d6dd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d6dd`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000c2fe`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000c2fe`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000bd7b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000bd7b`
- `ntoskrnl!IoFreeMdl` at `0x14000d723`
- `ntoskrnl!IoFreeMdl` at `0x14000d723`
- `ntoskrnl!KeStackAttachProcess` at `0x14000c29e`
- `ntoskrnl!KeStackAttachProcess` at `0x14000c29e`
- `ntoskrnl!MmUnlockPages` at `0x14000d714`
- `ntoskrnl!MmUnlockPages` at `0x14000d714`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x14000c6f2`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x14000c6f2`
- `ntoskrnl!RtlClearAllBitsEx` at `0x14000c706`
- `ntoskrnl!RtlClearAllBitsEx` at `0x14000c706`

## string_xrefs

- `0x14000be0e`: `VsmmpReadMemoryBlockByteRange`
- `0x14000bf72`: `VsmmpReadMemoryBlockByteRange`
- `0x14000c14e`: `VsmmpReadMemoryBlockByteRange`
- `0x14000c350`: `VsmmpReadMemoryBlockByteRange`
- `0x14000c4de`: `VsmmpReadMemoryBlockByteRange`
- `0x14000c7a3`: `VsmmpReadMemoryBlockByteRange`
- `0x14000c9f0`: `VsmmpReadMemoryBlockByteRange`
- `0x14000cc34`: `VsmmpReadMemoryBlockByteRange`
- `0x14000cf5f`: `VsmmpReadMemoryBlockByteRange`
- `0x14000d223`: `VsmmpReadMemoryBlockByteRange`
- `0x14000d4e8`: `VsmmpReadMemoryBlockByteRange`

## pseudocode

```c
__int64 __fastcall VsmmpReadMemoryBlockByteRange(
        unsigned __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned int a4,
        char *a5,
        unsigned __int64 a6,
        char a7,
        __int64 a8,
        char **a9)
{
  unsigned __int64 v10; // rdi
  void *v11; // r14
  char v12; // r12
  unsigned __int64 v13; // r15
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // r10d
  int KnownZeroVaPages; // r14d
  int v18; // r8d
  __int64 v19; // rdx
  int v20; // ecx
  __int64 v21; // rax
  char *v22; // rdx
  int v23; // r8d
  __int64 v24; // rdx
  int v25; // ecx
  __int64 v26; // rax
  void *v27; // r9
  __int64 v28; // rdi
  __int64 v29; // rdx
  int v30; // ecx
  __int64 v31; // rax
  __int64 v32; // rcx
  struct _KPROCESS *v33; // rcx
  unsigned int v34; // edi
  __int64 v35; // rdx
  PVOID v36; // r15
  __int64 v37; // rdx
  int v38; // ecx
  __int64 v39; // rax
  char *v40; // rdx
  __int64 v41; // rdx
  int v42; // ecx
  __int64 v43; // rax
  int v44; // edi
  unsigned __int64 v45; // r13
  char *v46; // rcx
  unsigned __int64 v47; // r14
  void *v48; // r9
  unsigned __int64 v49; // rax
  unsigned __int64 v50; // rcx
  char *v51; // r8
  unsigned __int64 v52; // r9
  int v53; // ecx
  __int64 v54; // rdx
  int v55; // ecx
  __int64 v56; // rax
  char *i; // rax
  __int64 v58; // rdx
  __int64 NextForwardRunClear; // r11
  char *v60; // r10
  unsigned __int64 v61; // r9
  __int64 v62; // rdx
  int v63; // ecx
  __int64 v64; // rax
  char *v65; // r9
  unsigned __int64 v66; // rdi
  __int64 v67; // r15
  SIZE_T v68; // r8
  unsigned __int64 v69; // rcx
  unsigned __int64 v70; // r14
  int v71; // r9d
  __int64 v72; // rdx
  int v73; // ecx
  __int64 v74; // rax
  int v75; // eax
  int v76; // r9d
  int v77; // eax
  int v78; // r8d
  __int64 v79; // rdx
  int v80; // ecx
  __int64 v81; // rax
  __int64 v82; // rdx
  int v83; // ecx
  __int64 v84; // rax
  unsigned __int64 v85; // r10
  char *v86; // rdx
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // r9
  struct _MDL *v90; // rbx
  int v92; // [rsp+20h] [rbp-308h]
  int v93; // [rsp+20h] [rbp-308h]
  int v94; // [rsp+50h] [rbp-2D8h] BYREF
  unsigned int v95; // [rsp+54h] [rbp-2D4h] BYREF
  char v96; // [rsp+58h] [rbp-2D0h]
  char v97; // [rsp+59h] [rbp-2CFh]
  __int64 v98; // [rsp+60h] [rbp-2C8h] BYREF
  unsigned __int64 v99; // [rsp+68h] [rbp-2C0h]
  unsigned __int64 v100; // [rsp+70h] [rbp-2B8h]
  char v101; // [rsp+78h] [rbp-2B0h]
  int v102; // [rsp+80h] [rbp-2A8h] BYREF
  __int64 v103; // [rsp+88h] [rbp-2A0h]
  unsigned __int64 v104; // [rsp+90h] [rbp-298h] BYREF
  int v105; // [rsp+98h] [rbp-290h] BYREF
  unsigned __int64 v106; // [rsp+A0h] [rbp-288h]
  char *v107; // [rsp+A8h] [rbp-280h] BYREF
  char *v108; // [rsp+B0h] [rbp-278h] BYREF
  char *v109; // [rsp+B8h] [rbp-270h] BYREF
  unsigned __int64 v110; // [rsp+C0h] [rbp-268h]
  char *v111; // [rsp+C8h] [rbp-260h] BYREF
  unsigned __int64 v112; // [rsp+D0h] [rbp-258h] BYREF
  unsigned __int64 v113; // [rsp+D8h] [rbp-250h] BYREF
  unsigned __int64 v114; // [rsp+E0h] [rbp-248h] BYREF
  __int64 v115; // [rsp+E8h] [rbp-240h] BYREF
  __int64 v116; // [rsp+F0h] [rbp-238h]
  unsigned __int64 v117; // [rsp+F8h] [rbp-230h] BYREF
  void *v118; // [rsp+100h] [rbp-228h]
  char *v119; // [rsp+108h] [rbp-220h]
  unsigned __int64 v120; // [rsp+110h] [rbp-218h] BYREF
  char *v121; // [rsp+118h] [rbp-210h] BYREF
  PMDL MemoryDescriptorList; // [rsp+120h] [rbp-208h] BYREF
  unsigned __int64 v123; // [rsp+128h] [rbp-200h]
  int v124; // [rsp+130h] [rbp-1F8h]
  PVOID Entry; // [rsp+138h] [rbp-1F0h]
  __int128 v126; // [rsp+140h] [rbp-1E8h] BYREF
  __int128 v127; // [rsp+150h] [rbp-1D8h]
  __int128 v128; // [rsp+160h] [rbp-1C8h] BYREF
  char **v129; // [rsp+170h] [rbp-1B8h]
  unsigned __int64 v130; // [rsp+178h] [rbp-1B0h] BYREF
  __int128 v131; // [rsp+180h] [rbp-1A8h]
  struct _KAPC_STATE ApcState; // [rsp+190h] [rbp-198h] BYREF
  _BYTE v133[24]; // [rsp+1C0h] [rbp-168h] BYREF
  _BYTE v134[16]; // [rsp+1E0h] [rbp-148h] BYREF
  _BYTE v135[16]; // [rsp+1F0h] [rbp-138h] BYREF
  int *v136; // [rsp+200h] [rbp-128h]
  __int64 v137; // [rsp+208h] [rbp-120h]
  int *v138; // [rsp+210h] [rbp-118h]
  __int64 v139; // [rsp+218h] [rbp-110h]
  __int64 v140; // [rsp+220h] [rbp-108h]
  __int64 v141; // [rsp+228h] [rbp-100h]
  int *v142; // [rsp+230h] [rbp-F8h]
  __int64 v143; // [rsp+238h] [rbp-F0h]
  __int64 v144; // [rsp+240h] [rbp-E8h]
  int v145; // [rsp+248h] [rbp-E0h] BYREF
  int v146; // [rsp+24Ch] [rbp-DCh]
  __int64 *v147; // [rsp+250h] [rbp-D8h]
  __int64 v148; // [rsp+258h] [rbp-D0h]
  void **v149; // [rsp+260h] [rbp-C8h]
  __int64 v150; // [rsp+268h] [rbp-C0h]
  void **v151; // [rsp+270h] [rbp-B8h]
  __int64 v152; // [rsp+278h] [rbp-B0h]
  unsigned __int64 *v153; // [rsp+280h] [rbp-A8h]
  __int64 v154; // [rsp+288h] [rbp-A0h]
  unsigned __int64 *v155; // [rsp+290h] [rbp-98h]
  __int64 v156; // [rsp+298h] [rbp-90h]
  char v157[64]; // [rsp+2A0h] [rbp-88h] BYREF

  v119 = (char *)a3;
  v110 = a2;
  v10 = a1;
  v99 = a1;
  v104 = a1;
  v112 = a2;
  v113 = a3;
  v102 = a4;
  v11 = a5;
  v107 = a5;
  v98 = a8;
  v129 = a9;
  memset(&ApcState, 0, sizeof(ApcState));
  v95 = 0;
  v128 = 0;
  v126 = 0;
  v127 = 0;
  v120 = 0;
  *a9 = 0;
  v97 = 0;
  v12 = 0;
  Entry = 0;
  v116 = -1;
  MemoryDescriptorList = 0;
  v13 = *(_QWORD *)(a1 + 8);
  v100 = v13;
  v114 = v13;
  v105 = VsmmHostAccessMinimumForMemoryBlock();
  v14 = *(_QWORD *)(*((_QWORD *)VidDeviceExtension + 33) + 8LL * (unsigned __int8)KeGetCurrentNodeNumber());
  v103 = v14;
  v115 = v14;
  v131 = 0;
  v130 = v13;
  v16 = a4 & 0xC;
  v94 = v16;
  if ( (a4 & 4) != 0 )
  {
    KnownZeroVaPages = -1073741637;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_109;
    tlgCreate1Sz_char(v134, "VsmmpReadMemoryBlockByteRange");
    tlgCreate1Sz_char(v135, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    v95 = 1405;
    v136 = (int *)&v95;
    v137 = 4;
    v94 = v18;
    v138 = &v94;
    v139 = 4;
    v19 = *(_QWORD *)(v10 + 8);
    v140 = v19 + 656;
    v141 = 16;
    v20 = *(unsigned __int16 *)(v19 + 120);
    v21 = *(_QWORD *)(v19 + 128);
    v142 = &v145;
    v143 = 2;
    v144 = v21;
    v145 = v20;
    v146 = 0;
    v98 = *(_QWORD *)(v19 + 648);
    v147 = &v98;
    v92 = 10;
    v22 = byte_140056761;
    goto LABEL_5;
  }
  if ( a6 > 0xFFFFFFFF )
  {
    KnownZeroVaPages = -1073741637;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_109;
    tlgCreate1Sz_char(v134, "VsmmpReadMemoryBlockByteRange");
    tlgCreate1Sz_char(v135, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    v95 = 1421;
    v136 = (int *)&v95;
    v137 = 4;
    v94 = v23;
    v138 = &v94;
    v139 = 4;
    v24 = *(_QWORD *)(v10 + 8);
    v140 = v24 + 656;
    v141 = 16;
    v25 = *(unsigned __int16 *)(v24 + 120);
    v26 = *(_QWORD *)(v24 + 128);
    v142 = &v145;
    v143 = 2;
    v144 = v26;
    v145 = v25;
    v146 = 0;
    v98 = *(_QWORD *)(v24 + 648);
    v147 = &v98;
    v104 = a6;
    v149 = (void **)&v104;
    v150 = 8;
    v92 = 11;
    v22 = byte_140056585;
    goto LABEL_5;
  }
  v27 = a5;
  v121 = a5;
  v96 = 0;
  if ( (*(_DWORD *)(v10 + 20) & 8) != 0 )
  {
    VidLockAcquireShared(v13 + 10408, v14, v15);
    if ( !*(_QWORD *)(v13 + 10416) || (a4 & 3) != 0 )
    {
      v28 = *(_QWORD *)(v13 + 10328);
      if ( PsGetCurrentProcess() == v28 )
      {
LABEL_24:
        VidLockRelease(v13 + 10408);
        v27 = v121;
        v16 = v94;
        v14 = v103;
        goto LABEL_25;
      }
      v10 = v99;
    }
    KnownZeroVaPages = VsmmpMapUserBufferToSystem(a5, a6, &MemoryDescriptorList, IoWriteAccess, &v121);
    if ( KnownZeroVaPages < 0 )
    {
      v12 = 1;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_109;
      tlgCreate1Sz_char(v134, "VsmmpReadMemoryBlockByteRange");
      tlgCreate1Sz_char(v135, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
      v95 = 1456;
      v136 = (int *)&v95;
      v137 = 4;
      v94 = KnownZeroVaPages;
      v138 = &v94;
      v139 = 4;
      v29 = *(_QWORD *)(v10 + 8);
      v140 = v29 + 656;
      v141 = 16;
      v30 = *(unsigned __int16 *)(v29 + 120);
      v31 = *(_QWORD *)(v29 + 128);
      v142 = &v145;
      v143 = 2;
      v144 = v31;
      v145 = v30;
      v146 = 0;
      v98 = *(_QWORD *)(v29 + 648);
      v147 = &v98;
      v104 = a6;
      v149 = (void **)&v104;
      v150 = 8;
      v92 = 11;
      v22 = &byte_1400565FF;
      goto LABEL_5;
    }
    a7 = 0;
    v32 = *(_QWORD *)(v13 + 10416);
    if ( !v32 || (a4 & 3) != 0 )
    {
      v33 = *(struct _KPROCESS **)(v13 + 10328);
    }
    else
    {
      v96 = 1;
      v33 = *(struct _KPROCESS **)(v32 + 88);
    }
    KeStackAttachProcess(v33, &ApcState);
    v97 = 1;
    v11 = v107;
    goto LABEL_24;
  }
LABEL_25:
  if ( v16 )
  {
    v34 = (a4 >> 2) & 3;
    v36 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v14 + 96LL * (v34 - 1) + 224));
    Entry = v36;
    if ( !v36 )
    {
      KnownZeroVaPages = -1073741670;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_31;
      tlgCreate1Sz_char(v134, "VsmmpReadMemoryBlockByteRange");
      tlgCreate1Sz_char(v135, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
      v95 = 1502;
      v136 = (int *)&v95;
      v137 = 4;
      v94 = -1073741670;
      v138 = &v94;
      v139 = 4;
      v37 = *(_QWORD *)(v99 + 8);
      v140 = v37 + 656;
      v141 = 16;
      v38 = *(unsigned __int16 *)(v37 + 120);
      v39 = *(_QWORD *)(v37 + 128);
      v142 = &v145;
      v143 = 2;
      v144 = v39;
      v145 = v38;
      v146 = 0;
      v98 = *(_QWORD *)(v37 + 648);
      v147 = &v98;
      v93 = 10;
      v40 = byte_140056679;
LABEL_30:
      v148 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v40, 0, 0, v93, v133);
LABEL_31:
      v12 = 0;
      goto LABEL_109;
    }
    if ( !MemoryDescriptorList && a7 )
    {
      KnownZeroVaPages = VsmmpMapUserBufferToSystem(v11, a6, &MemoryDescriptorList, IoWriteAccess, &v121);
      if ( KnownZeroVaPages < 0 )
      {
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_31;
        tlgCreate1Sz_char(v134, "VsmmpReadMemoryBlockByteRange");
        tlgCreate1Sz_char(v135, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
        v95 = 1520;
        v136 = (int *)&v95;
        v137 = 4;
        v94 = KnownZeroVaPages;
        v138 = &v94;
        v139 = 4;
        v41 = *(_QWORD *)(v99 + 8);
        v140 = v41 + 656;
        v141 = 16;
        v42 = *(unsigned __int16 *)(v41 + 120);
        v43 = *(_QWORD *)(v41 + 128);
        v142 = &v145;
        v143 = 2;
        v144 = v43;
        v145 = v42;
        v146 = 0;
        v98 = *(_QWORD *)(v41 + 648);
        v147 = &v98;
        v104 = a6;
        v149 = (void **)&v104;
        v150 = 8;
        v93 = 11;
        v40 = &byte_1400566E7;
        goto LABEL_30;
      }
      a7 = 0;
    }
    DWORD1(v127) = 0;
    LODWORD(v126) = VsmmCompressionFormatToVmCompress(v34, v35);
    DWORD1(v126) = 3;
    v27 = v121;
    *((_QWORD *)&v126 + 1) = v121;
    LODWORD(v127) = a6;
    *((_QWORD *)&v127 + 1) = v36;
  }
  v12 = 0;
  v101 = 0;
  v44 = VsmmpConvertMbpRwFlagsToMbpLockFlags(a4, 0, v15, v27);
  v45 = v110;
  v123 = v110;
  v46 = &v119[v110];
  v111 = &v119[v110];
  v47 = v110 >> 12;
  v106 = v110 >> 12;
  v118 = v48;
LABEL_41:
  if ( v45 < (unsigned __int64)v46 )
  {
    v49 = v47 & 0x1FF;
    v50 = (unsigned __int64)&v46[-v45];
    if ( v50 >= (512 - v49) << 12 )
      v50 = (512 - v49) << 12;
    v117 = (v50 + 4095 + (v45 & 0xFFF)) >> 12;
    RtlInitializeBitMapEx(&v128, v157, v117);
    RtlClearAllBitsEx(&v128);
    v53 = *(_DWORD *)(v99 + 20);
    if ( (v53 & 8) != 0 && (a4 & 3) == 0 && !v96 && (v53 & 0x10000) == 0 )
    {
      KnownZeroVaPages = VsmmQueryKnownZeroVaPages(*(PRKPROCESS *)(v100 + 10328));
      if ( KnownZeroVaPages < 0 )
      {
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_109;
        tlgCreate1Sz_char(v134, "VsmmpReadMemoryBlockByteRange");
        tlgCreate1Sz_char(v135, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
        v95 = 1614;
        v136 = (int *)&v95;
        v137 = 4;
        v94 = KnownZeroVaPages;
        v138 = &v94;
        v139 = 4;
        v54 = *(_QWORD *)(v99 + 8);
        v140 = v54 + 656;
        v141 = 16;
        v55 = *(unsigned __int16 *)(v54 + 120);
        v56 = *(_QWORD *)(v54 + 128);
        v142 = &v145;
        v143 = 2;
        v144 = v56;
        v145 = v55;
        v146 = 0;
        v98 = *(_QWORD *)(v54 + 648);
        v147 = &v98;
        v104 = v106;
        v149 = (void **)&v104;
        v150 = 8;
        v107 = (char *)v117;
        v151 = (void **)&v107;
        v152 = 8;
        v92 = 12;
        v22 = &byte_1400562DF;
        goto LABEL_5;
      }
      v47 = v106;
    }
    for ( i = 0; ; i = &v107[v120] )
    {
      v108 = i;
      if ( (unsigned __int64)i >= v117 )
        goto LABEL_99;
      NextForwardRunClear = RtlFindNextForwardRunClearEx(&v128, i, &v120);
      v107 = (char *)NextForwardRunClear;
      if ( !NextForwardRunClear )
        v120 = v117;
      v52 = v120;
      v60 = v108;
      if ( v120 > (unsigned __int64)v108 )
      {
        v61 = (v47 + v120 - (_QWORD)v108) << 12;
        if ( (unsigned __int64)v111 < v61 )
          v61 = (unsigned __int64)v111;
        v109 = (char *)v61;
        if ( v94 )
        {
          KnownZeroVaPages = VmCompressPackExAddConstantRun(&v126, v58, (unsigned int)(v61 - v45));
          v124 = KnownZeroVaPages;
          if ( KnownZeroVaPages < 0 )
          {
            if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
            {
              tlgCreate1Sz_char(v134, "VsmmpReadMemoryBlockByteRange");
              tlgCreate1Sz_char(v135, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
              v95 = 1675;
              v136 = (int *)&v95;
              v137 = 4;
              v94 = KnownZeroVaPages;
              v138 = &v94;
              v139 = 4;
              v62 = *(_QWORD *)(v99 + 8);
              v140 = v62 + 656;
              v141 = 16;
              v63 = *(unsigned __int16 *)(v62 + 120);
              v64 = *(_QWORD *)(v62 + 128);
              v142 = &v145;
              v143 = 2;
              v144 = v64;
              v145 = v63;
              v146 = 0;
              v98 = *(_QWORD *)(v62 + 648);
              v147 = &v98;
              v148 = 8;
              v107 = (char *)v110;
              v149 = (void **)&v107;
              v150 = 8;
              v108 = v119;
              v151 = (void **)&v108;
              v152 = 8;
              v117 = v45;
              v153 = &v117;
              v154 = 8;
              v111 = v65;
              v155 = (unsigned __int64 *)&v111;
              v156 = 8;
              tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140056369, 0, 0, 14, v133);
            }
            v66 = v100;
            v67 = v103;
            goto LABEL_111;
          }
          v47 = v106;
        }
        else
        {
          v68 = v61 - v45;
          if ( a7 )
            RtlSetUserMemory(v118, 0, v68);
          else
            RtlSetVolatileMemory(v118, 0, v68);
          v60 = v108;
          NextForwardRunClear = (__int64)v107;
        }
      }
      v47 += v120 - (_QWORD)v60;
      v106 = v47;
      v69 = v47;
      v45 = v47 << 12;
      if ( v47 << 12 >= v110 )
      {
        if ( v45 > (unsigned __int64)v111 )
          v45 = (unsigned __int64)v111;
        v123 = v45;
      }
      else
      {
        v45 = v110;
        v123 = v110;
      }
      v51 = &v121[v45 - v110];
      v118 = v51;
      if ( !NextForwardRunClear )
      {
LABEL_99:
        v46 = v111;
        if ( v116 != -1 )
        {
          VidPushLockRelease(*(_QWORD *)(v99 + 328) + 8 * v116, v116, v51, v52);
          v116 = -1;
          v46 = v111;
        }
        goto LABEL_41;
      }
      v70 = (NextForwardRunClear + v47) << 12;
      if ( (unsigned __int64)v111 < v70 )
        v70 = (unsigned __int64)v111;
      v106 = v70;
      if ( v96 )
      {
        v108 = (char *)(v70 - v45);
        v71 = v45 + (_DWORD)v121 - v110;
        if ( v94 )
          v71 = 0;
        KnownZeroVaPages = VsmmpReadCloneTemplateByteRange(
                             v99,
                             v45,
                             (int)v70 - (int)v45,
                             v71,
                             (unsigned __int64)&v126 & -(__int64)(v94 != 0),
                             a7);
        if ( KnownZeroVaPages < 0 )
        {
          if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          {
            tlgCreate1Sz_char(v134, "VsmmpReadMemoryBlockByteRange");
            tlgCreate1Sz_char(v135, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
            v102 = 1779;
            v136 = &v102;
            v137 = 4;
            v95 = KnownZeroVaPages;
            v138 = (int *)&v95;
            v139 = 4;
            v72 = *(_QWORD *)(v99 + 8);
            v140 = v72 + 656;
            v141 = 16;
            v73 = *(unsigned __int16 *)(v72 + 120);
            v74 = *(_QWORD *)(v72 + 128);
            v142 = &v145;
            v143 = 2;
            v144 = v74;
            v145 = v73;
            v146 = 0;
            v115 = *(_QWORD *)(v72 + 648);
            v147 = &v115;
            v114 = v110;
            v149 = (void **)&v114;
            v150 = 8;
            v109 = v119;
            v151 = (void **)&v109;
            v152 = 8;
            v113 = v45;
            v153 = &v113;
            v154 = 8;
            v112 = v106;
            v155 = &v112;
            v156 = 8;
            v92 = 14;
            v22 = byte_1400564D1;
            goto LABEL_5;
          }
          goto LABEL_109;
        }
      }
      else
      {
        if ( (a4 & 3) == 0 && v105 == 2 && v116 == -1 )
        {
          v116 = v69 >> 9;
          VidPushLockAcquireShared(*(_QWORD *)(v99 + 328) + 8 * (v69 >> 9));
          v51 = (char *)v118;
        }
        v75 = a4 & 0x20;
        v108 = (char *)(v70 - v45);
        v76 = v70 - v45;
        if ( v94 )
          v77 = VsmmMemoryBlockCopyByteRange(
                  (unsigned int)&v130,
                  v99,
                  v45,
                  v76,
                  0,
                  (__int64)&v126,
                  v44,
                  v75 != 0,
                  a7,
                  v98);
        else
          v77 = VsmmMemoryBlockCopyByteRange(
                  (unsigned int)&v130,
                  v99,
                  v45,
                  v76,
                  (__int64)v51,
                  0,
                  v44,
                  v75 != 0,
                  a7,
                  v98);
        KnownZeroVaPages = v77;
        if ( v77 < 0 )
        {
          v66 = v100;
          if ( !(unsigned __int8)VsmmReadWriteFailureExpected(v100, a4, (unsigned int)v77)
            && (unsigned int)dword_140064110 > 2
            && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          {
            tlgCreate1Sz_char(v134, "VsmmpReadMemoryBlockByteRange");
            tlgCreate1Sz_char(v135, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
            v105 = 1853;
            v136 = &v105;
            v137 = 4;
            v102 = v78;
            v138 = &v102;
            v139 = 4;
            v79 = *(_QWORD *)(v99 + 8);
            v140 = v79 + 656;
            v141 = 16;
            v80 = *(unsigned __int16 *)(v79 + 120);
            v81 = *(_QWORD *)(v79 + 128);
            v142 = &v145;
            v143 = 2;
            v144 = v81;
            v145 = v80;
            v146 = 0;
            v115 = *(_QWORD *)(v79 + 648);
            v147 = &v115;
            v148 = 8;
            v114 = v110;
            v149 = (void **)&v114;
            v150 = 8;
            v109 = v119;
            v151 = (void **)&v109;
            v152 = 8;
            v113 = v45;
            v153 = &v113;
            v154 = 8;
            v112 = v106;
            v155 = &v112;
            v156 = 8;
            tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &byte_14005619F, 0, 0, 14, v133);
          }
          goto LABEL_110;
        }
      }
      v118 = (char *)v118 + (_QWORD)v108;
      v45 = v106;
      v123 = v106;
      v47 = v106 >> 12;
      v106 >>= 12;
    }
  }
  if ( !v94 )
  {
    v86 = v119;
    goto LABEL_108;
  }
  KnownZeroVaPages = VmCompressPackExComplete(&v126, &v95);
  if ( KnownZeroVaPages >= 0 )
  {
    v86 = (char *)v95;
LABEL_108:
    *v129 = v86;
    KnownZeroVaPages = 0;
    goto LABEL_109;
  }
  if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    goto LABEL_109;
  tlgCreate1Sz_char(v134, "VsmmpReadMemoryBlockByteRange");
  tlgCreate1Sz_char(v135, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
  v105 = 1899;
  v136 = &v105;
  v137 = 4;
  v102 = KnownZeroVaPages;
  v138 = &v102;
  v139 = 4;
  v82 = *(_QWORD *)(v99 + 8);
  v140 = v82 + 656;
  v141 = 16;
  v83 = *(unsigned __int16 *)(v82 + 120);
  v84 = *(_QWORD *)(v82 + 128);
  v142 = &v145;
  v143 = 2;
  v144 = v84;
  v145 = v83;
  v146 = 0;
  v115 = *(_QWORD *)(v82 + 648);
  v147 = &v115;
  v114 = v85;
  v149 = (void **)&v114;
  v150 = 8;
  v109 = v119;
  v151 = (void **)&v109;
  v152 = 8;
  v92 = 12;
  v22 = byte_140056253;
LABEL_5:
  v148 = 8;
  tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v22, 0, 0, v92, v133);
LABEL_109:
  v66 = v100;
LABEL_110:
  v67 = v103;
LABEL_111:
  VsmmMemoryBlockMbpRangeVaDestroy(&v130);
  if ( v116 != -1 )
    VidPushLockRelease(*(_QWORD *)(v99 + 328) + 8 * v116, v87, v88, v89);
  if ( v12 )
    VidLockRelease(v66 + 10408);
  if ( Entry )
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v67 + 96LL * (((a4 >> 2) & 3) - 1) + 224), Entry);
  if ( v97 )
    KeUnstackDetachProcess(&ApcState);
  v90 = MemoryDescriptorList;
  if ( MemoryDescriptorList )
  {
    MmUnlockPages(MemoryDescriptorList);
    IoFreeMdl(v90);
  }
  return (unsigned int)KnownZeroVaPages;
}

```

## disassembly

```asm
0x14000bc64  push    rbx
0x14000bc66  push    rsi
0x14000bc67  push    rdi
0x14000bc68  push    r12
0x14000bc6a  push    r13
0x14000bc6c  push    r14
0x14000bc6e  push    r15
0x14000bc70  sub     rsp, 2F0h
0x14000bc77  mov     rax, cs:__security_cookie
0x14000bc7e  xor     rax, rsp
0x14000bc81  mov     [rsp+328h+var_48], rax
0x14000bc89  mov     ebx, r9d
0x14000bc8c  mov     rax, r8
0x14000bc8f  mov     [rsp+328h+var_220], rax
0x14000bc97  mov     [rsp+328h+var_268], rdx
0x14000bc9f  mov     rdi, rcx
0x14000bca2  mov     [rsp+328h+var_2C0], rcx
0x14000bca7  mov     [rsp+328h+var_298], rcx
0x14000bcaf  mov     [rsp+328h+var_258], rdx
0x14000bcb7  mov     [rsp+328h+var_250], rax
0x14000bcbf  mov     [rsp+328h+var_2A8], ebx
0x14000bcc6  mov     r14, [rsp+328h+arg_20]
0x14000bcce  mov     [rsp+328h+var_280], r14
0x14000bcd6  mov     rax, [rsp+328h+arg_38]
0x14000bcde  mov     [rsp+328h+var_2C8], rax
0x14000bce3  mov     rax, [rsp+328h+arg_40]
0x14000bceb  mov     [rsp+328h+var_1B8], rax
0x14000bcf3  xorps   xmm0, xmm0
0x14000bcf6  movups  xmmword ptr [rsp+328h+ApcState.ApcListHead.Flink], xmm0
0x14000bcfe  movups  xmmword ptr [rsp+328h+ApcState.ApcListHead.Flink+10h], xmm0
0x14000bd06  movups  xmmword ptr [rsp+328h+ApcState.Process], xmm0
0x14000bd0e  xor     esi, esi
0x14000bd10  mov     [rsp+328h+var_2D4], esi
0x14000bd14  movups  [rsp+328h+var_1C8], xmm0
0x14000bd1c  xorps   xmm1, xmm1
0x14000bd1f  movups  [rsp+328h+var_1E8], xmm1
0x14000bd27  movups  [rsp+328h+var_1D8], xmm1
0x14000bd2f  mov     [rsp+328h+var_218], rsi
0x14000bd37  mov     [rax], rsi
0x14000bd3a  mov     [rsp+328h+var_2CF], sil
0x14000bd3f  mov     r12b, sil
0x14000bd42  mov     [rsp+328h+Entry], rsi
0x14000bd4a  mov     [rsp+328h+var_238], 0FFFFFFFFFFFFFFFFh
0x14000bd56  mov     [rsp+328h+MemoryDescriptorList], rsi
0x14000bd5e  mov     r15, [rcx+8]
0x14000bd62  mov     [rsp+328h+var_2B8], r15
0x14000bd67  mov     [rsp+328h+var_248], r15
0x14000bd6f  call    VsmmHostAccessMinimumForMemoryBlock
0x14000bd74  mov     [rsp+328h+var_290], eax
0x14000bd7b  call    cs:__imp_KeGetCurrentNodeNumber
0x14000bd82  nop     dword ptr [rax+rax+00h]
0x14000bd87  movzx   edx, al
0x14000bd8a  mov     rax, cs:VidDeviceExtension
0x14000bd91  mov     rcx, [rax+108h]
0x14000bd98  mov     rdx, [rcx+rdx*8]
0x14000bd9c  mov     [rsp+328h+var_2A0], rdx
0x14000bda4  mov     [rsp+328h+var_240], rdx
0x14000bdac  xorps   xmm0, xmm0
0x14000bdaf  movdqu  [rsp+328h+var_1A8], xmm0
0x14000bdb8  mov     [rsp+328h+var_1B0], r15
0x14000bdc0  mov     r10d, ebx
0x14000bdc3  and     r10d, 0Ch
0x14000bdc7  mov     [rsp+328h+var_2D8], r10d
0x14000bdcc  test    r10d, 0FFFFFFF7h
0x14000bdd3  jz      loc_14000BF25
0x14000bdd9  mov     r8d, 0C00000BBh
0x14000bddf  mov     r14d, r8d
0x14000bde2  mov     eax, cs:dword_140064110
0x14000bde8  lea     r15d, [rsi+2]
0x14000bdec  cmp     eax, r15d
0x14000bdef  jbe     loc_14000D668
0x14000bdf5  mov     edx, 100h
0x14000bdfa  lea     rcx, dword_140064110
0x14000be01  call    _tlgKeywordOn
0x14000be06  test    al, al
0x14000be08  jz      loc_14000D668
0x14000be0e  lea     rdx, aVsmmpreadmemor; "VsmmpReadMemoryBlockByteRange"
0x14000be15  lea     rcx, [rsp+328h+var_148]
0x14000be1d  call    _tlgCreate1Sz_char
0x14000be22  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000be29  lea     rcx, [rsp+328h+var_138]
0x14000be31  call    _tlgCreate1Sz_char
0x14000be36  mov     [rsp+328h+var_2D4], 57Dh
0x14000be3e  lea     rax, [rsp+328h+var_2D4]
0x14000be43  mov     [rsp+328h+var_128], rax
0x14000be4b  mov     [rsp+328h+var_120], 4
0x14000be57  mov     [rsp+328h+var_2D8], r8d
0x14000be5c  lea     rcx, [rsp+328h+var_2D8]
0x14000be61  mov     [rsp+328h+var_118], rcx
0x14000be69  mov     [rsp+328h+var_110], 4
0x14000be75  mov     rdx, [rdi+8]
0x14000be79  lea     rax, [rdx+290h]
0x14000be80  mov     [rsp+328h+var_108], rax
0x14000be88  mov     [rsp+328h+var_100], 10h
0x14000be94  movzx   ecx, word ptr [rdx+78h]
0x14000be98  mov     rax, [rdx+80h]
0x14000be9f  lea     r8, [rsp+328h+var_E0]
0x14000bea7  mov     [rsp+328h+var_F8], r8
0x14000beaf  mov     [rsp+328h+var_F0], r15
0x14000beb7  mov     [rsp+328h+var_E8], rax
0x14000bebf  mov     [rsp+328h+var_E0], ecx
0x14000bec6  mov     [rsp+328h+var_DC], esi
0x14000becd  mov     rax, [rdx+288h]
0x14000bed4  mov     [rsp+328h+var_2C8], rax
0x14000bed9  lea     rax, [rsp+328h+var_2C8]
0x14000bede  mov     [rsp+328h+var_D8], rax
0x14000bee6  lea     rax, [rsp+328h+var_168]
0x14000beee  mov     [rsp+328h+var_300], rax
0x14000bef3  mov     dword ptr [rsp+328h+var_308], 0Ah
0x14000befb  lea     rdx, byte_140056761
0x14000bf02  xor     r9d, r9d
0x14000bf05  xor     r8d, r8d
0x14000bf08  mov     [rsp+328h+var_D0], 8
0x14000bf14  lea     rcx, dword_140064110
0x14000bf1b  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000bf20  jmp     loc_14000D668
0x14000bf25  mov     eax, 0FFFFFFFFh
0x14000bf2a  mov     r13, [rsp+328h+arg_28]
0x14000bf32  cmp     r13, rax
0x14000bf35  jbe     loc_14000C08F
0x14000bf3b  mov     r8d, 0C00000BBh
0x14000bf41  mov     r14d, r8d
0x14000bf44  mov     eax, cs:dword_140064110
0x14000bf4a  mov     r15d, 2
0x14000bf50  cmp     eax, r15d
0x14000bf53  jbe     loc_14000D668
0x14000bf59  mov     edx, 100h
0x14000bf5e  lea     rcx, dword_140064110
0x14000bf65  call    _tlgKeywordOn
0x14000bf6a  test    al, al
0x14000bf6c  jz      loc_14000D668
0x14000bf72  lea     rdx, aVsmmpreadmemor; "VsmmpReadMemoryBlockByteRange"
0x14000bf79  lea     rcx, [rsp+328h+var_148]
0x14000bf81  call    _tlgCreate1Sz_char
0x14000bf86  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000bf8d  lea     rcx, [rsp+328h+var_138]
0x14000bf95  call    _tlgCreate1Sz_char
0x14000bf9a  mov     [rsp+328h+var_2D4], 58Dh
0x14000bfa2  lea     rax, [rsp+328h+var_2D4]
0x14000bfa7  mov     [rsp+328h+var_128], rax
0x14000bfaf  mov     [rsp+328h+var_120], 4
0x14000bfbb  mov     [rsp+328h+var_2D8], r8d
0x14000bfc0  lea     rcx, [rsp+328h+var_2D8]
0x14000bfc5  mov     [rsp+328h+var_118], rcx
0x14000bfcd  mov     [rsp+328h+var_110], 4
0x14000bfd9  mov     rdx, [rdi+8]
0x14000bfdd  lea     rax, [rdx+290h]
0x14000bfe4  mov     [rsp+328h+var_108], rax
0x14000bfec  mov     [rsp+328h+var_100], 10h
0x14000bff8  movzx   ecx, word ptr [rdx+78h]
0x14000bffc  mov     rax, [rdx+80h]
0x14000c003  lea     r8, [rsp+328h+var_E0]
0x14000c00b  mov     [rsp+328h+var_F8], r8
0x14000c013  mov     [rsp+328h+var_F0], r15
0x14000c01b  mov     [rsp+328h+var_E8], rax
0x14000c023  mov     [rsp+328h+var_E0], ecx
0x14000c02a  mov     [rsp+328h+var_DC], esi
0x14000c031  mov     rax, [rdx+288h]
0x14000c038  mov     [rsp+328h+var_2C8], rax
0x14000c03d  lea     rax, [rsp+328h+var_2C8]
0x14000c042  mov     [rsp+328h+var_D8], rax
0x14000c04a  mov     [rsp+328h+var_298], r13
0x14000c052  lea     rcx, [rsp+328h+var_298]
0x14000c05a  mov     [rsp+328h+var_C8], rcx
0x14000c062  mov     [rsp+328h+var_C0], 8
0x14000c06e  lea     rax, [rsp+328h+var_168]
0x14000c076  mov     [rsp+328h+var_300], rax
0x14000c07b  mov     dword ptr [rsp+328h+var_308], 0Bh
0x14000c083  lea     rdx, byte_140056585
0x14000c08a  jmp     loc_14000BF02
0x14000c08f  mov     r9, r14
0x14000c092  mov     [rsp+328h+var_210], r14
0x14000c09a  mov     [rsp+328h+var_2D0], sil
0x14000c09f  mov     eax, [rdi+14h]
0x14000c0a2  mov     r12d, 8
0x14000c0a8  test    r12b, al
0x14000c0ab  jz      loc_14000C2D8
0x14000c0b1  lea     rcx, [r15+28A8h]
0x14000c0b8  call    VidLockAcquireShared
0x14000c0bd  cmp     [r15+28B0h], rsi
0x14000c0c4  jz      short loc_14000C0CB
0x14000c0c6  test    bl, 3
0x14000c0c9  jz      short loc_14000C0EC
0x14000c0cb  mov     rdi, [r15+2858h]
0x14000c0d2  call    cs:__imp_PsGetCurrentProcess
0x14000c0d9  nop     dword ptr [rax+rax+00h]
0x14000c0de  cmp     rax, rdi
0x14000c0e1  jz      loc_14000C2B7
0x14000c0e7  mov     rdi, [rsp+328h+var_2C0]
0x14000c0ec  mov     edx, r13d
0x14000c0ef  lea     rax, [rsp+328h+var_210]
0x14000c0f7  mov     [rsp+328h+var_308], rax
0x14000c0fc  mov     r9d, 1
0x14000c102  lea     r8, [rsp+328h+MemoryDescriptorList]
0x14000c10a  mov     rcx, r14
0x14000c10d  call    VsmmpMapUserBufferToSystem
0x14000c112  mov     r14d, eax
0x14000c115  test    eax, eax
0x14000c117  jns     loc_14000C26B
0x14000c11d  mov     r12b, 1
0x14000c120  mov     ecx, cs:dword_140064110
0x14000c126  mov     r15d, 2
0x14000c12c  cmp     ecx, r15d
0x14000c12f  jbe     loc_14000D668
0x14000c135  mov     edx, 100h
0x14000c13a  lea     rcx, dword_140064110
0x14000c141  call    _tlgKeywordOn
0x14000c146  test    al, al
0x14000c148  jz      loc_14000D668
0x14000c14e  lea     rdx, aVsmmpreadmemor; "VsmmpReadMemoryBlockByteRange"
0x14000c155  lea     rcx, [rsp+328h+var_148]
0x14000c15d  call    _tlgCreate1Sz_char
0x14000c162  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000c169  lea     rcx, [rsp+328h+var_138]
0x14000c171  call    _tlgCreate1Sz_char
0x14000c176  mov     [rsp+328h+var_2D4], 5B0h
0x14000c17e  lea     rax, [rsp+328h+var_2D4]
0x14000c183  mov     [rsp+328h+var_128], rax
0x14000c18b  mov     [rsp+328h+var_120], 4
0x14000c197  mov     [rsp+328h+var_2D8], r14d
0x14000c19c  lea     rcx, [rsp+328h+var_2D8]
0x14000c1a1  mov     [rsp+328h+var_118], rcx
0x14000c1a9  mov     [rsp+328h+var_110], 4
0x14000c1b5  mov     rdx, [rdi+8]
0x14000c1b9  lea     rax, [rdx+290h]
0x14000c1c0  mov     [rsp+328h+var_108], rax
0x14000c1c8  mov     [rsp+328h+var_100], 10h
0x14000c1d4  movzx   ecx, word ptr [rdx+78h]
0x14000c1d8  mov     rax, [rdx+80h]
0x14000c1df  lea     r8, [rsp+328h+var_E0]
0x14000c1e7  mov     [rsp+328h+var_F8], r8
0x14000c1ef  mov     [rsp+328h+var_F0], r15
0x14000c1f7  mov     [rsp+328h+var_E8], rax
0x14000c1ff  mov     [rsp+328h+var_E0], ecx
0x14000c206  mov     [rsp+328h+var_DC], esi
0x14000c20d  mov     rax, [rdx+288h]
0x14000c214  mov     [rsp+328h+var_2C8], rax
0x14000c219  lea     rax, [rsp+328h+var_2C8]
0x14000c21e  mov     [rsp+328h+var_D8], rax
0x14000c226  mov     [rsp+328h+var_298], r13
0x14000c22e  lea     rax, [rsp+328h+var_298]
0x14000c236  mov     [rsp+328h+var_C8], rax
0x14000c23e  mov     [rsp+328h+var_C0], 8
0x14000c24a  lea     rax, [rsp+328h+var_168]
0x14000c252  mov     [rsp+328h+var_300], rax
0x14000c257  mov     dword ptr [rsp+328h+var_308], 0Bh
0x14000c25f  lea     rdx, byte_1400565FF
0x14000c266  jmp     loc_14000BF02
0x14000c26b  mov     [rsp+328h+arg_30], sil
0x14000c273  mov     rcx, [r15+28B0h]
0x14000c27a  test    rcx, rcx
0x14000c27d  jz      short loc_14000C28F
0x14000c27f  test    bl, 3
0x14000c282  jnz     short loc_14000C28F
0x14000c284  mov     [rsp+328h+var_2D0], 1
0x14000c289  mov     rcx, [rcx+58h]
0x14000c28d  jmp     short loc_14000C296
0x14000c28f  mov     rcx, [r15+2858h]; PROCESS
0x14000c296  lea     rdx, [rsp+328h+ApcState]; ApcState
0x14000c29e  call    cs:__imp_KeStackAttachProcess
0x14000c2a5  nop     dword ptr [rax+rax+00h]
0x14000c2aa  mov     [rsp+328h+var_2CF], 1
0x14000c2af  mov     r14, [rsp+328h+var_280]
0x14000c2b7  lea     rcx, [r15+28A8h]
0x14000c2be  call    VidLockRelease
0x14000c2c3  mov     r9, [rsp+328h+var_210]
0x14000c2cb  mov     r10d, [rsp+328h+var_2D8]
0x14000c2d0  mov     rdx, [rsp+328h+var_2A0]
0x14000c2d8  test    r10d, r10d
0x14000c2db  jz      loc_14000C644
0x14000c2e1  mov     edi, ebx
0x14000c2e3  shr     edi, 2
0x14000c2e6  and     edi, 3
0x14000c2e9  lea     eax, [rdi-1]
0x14000c2ec  lea     rcx, [rax+rax*2]
0x14000c2f0  shl     rcx, 5
0x14000c2f4  add     rcx, 0E0h
0x14000c2fb  add     rcx, rdx; Lookaside
0x14000c2fe  call    cs:__imp_ExAllocateFromLookasideListEx
0x14000c305  nop     dword ptr [rax+rax+00h]
0x14000c30a  mov     r15, rax
0x14000c30d  mov     [rsp+328h+Entry], rax
0x14000c315  test    rax, rax
0x14000c318  jnz     loc_14000C46B
0x14000c31e  mov     r14d, 0C000009Ah
0x14000c324  mov     ecx, cs:dword_140064110
0x14000c32a  lea     r15d, [rax+2]
0x14000c32e  cmp     ecx, r15d
0x14000c331  jbe     loc_14000C463
0x14000c337  mov     edx, 100h
0x14000c33c  lea     rcx, dword_140064110
0x14000c343  call    _tlgKeywordOn
0x14000c348  test    al, al
0x14000c34a  jz      loc_14000C463
0x14000c350  lea     rdx, aVsmmpreadmemor; "VsmmpReadMemoryBlockByteRange"
0x14000c357  lea     rcx, [rsp+328h+var_148]
0x14000c35f  call    _tlgCreate1Sz_char
0x14000c364  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000c36b  lea     rcx, [rsp+328h+var_138]
0x14000c373  call    _tlgCreate1Sz_char
  ... truncated ...
```
