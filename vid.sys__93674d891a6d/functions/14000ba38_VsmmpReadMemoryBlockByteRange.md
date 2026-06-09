# VsmmpReadMemoryBlockByteRange

- ea: `0x14000ba38`
- end: `0x14000d4d2`
- name: `VsmmpReadMemoryBlockByteRange`
- size: `6810`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, unsigned __int64, unsigned int, __int64, unsigned __int64, char, __int64, __int64 *)`
- caller_count: `3`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000aae0`
- `0x14001c0a8`
- `0x140029790`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x140007170`
- `0x1400071a4`
- `0x14000a010`
- `0x14000ba38`
- `0x14000efa0`
- `0x14001c040`
- `0x1400218b8`
- `0x14002195c`
- `0x140021c60`
- `0x140021d20`
- `0x1400309d0`
- `0x140033b00`
- `0x140079f4c`
- `0x1400d7310`
- `0x1400d7c2c`
- `0x1400f51b8`
- `0x1400fb38c`
- `0x1400fc52c`
- `0x1400fd300`
- `0x1400fd760`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x14000d474`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000d474`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000bea4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000bea4`
- `ntoskrnl!RtlFindNextForwardRunClearEx` at `0x14000c717`
- `ntoskrnl!RtlFindNextForwardRunClearEx` at `0x14000c717`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d459`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000d459`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000c0e8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14000c0e8`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000bb4f`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000bb4f`
- `ntoskrnl!IoFreeMdl` at `0x14000d49f`
- `ntoskrnl!IoFreeMdl` at `0x14000d49f`
- `ntoskrnl!KeStackAttachProcess` at `0x14000c08f`
- `ntoskrnl!KeStackAttachProcess` at `0x14000c08f`
- `ntoskrnl!MmUnlockPages` at `0x14000d490`
- `ntoskrnl!MmUnlockPages` at `0x14000d490`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x14000c4cc`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x14000c4cc`
- `ntoskrnl!RtlClearAllBitsEx` at `0x14000c4e0`
- `ntoskrnl!RtlClearAllBitsEx` at `0x14000c4e0`

## string_xrefs

- `0x14000bbde`: `VsmmpReadMemoryBlockByteRange`
- `0x14000bd40`: `VsmmpReadMemoryBlockByteRange`
- `0x14000bf1d`: `VsmmpReadMemoryBlockByteRange`
- `0x14000c136`: `VsmmpReadMemoryBlockByteRange`
- `0x14000c2c1`: `VsmmpReadMemoryBlockByteRange`
- `0x14000c57e`: `VsmmpReadMemoryBlockByteRange`
- `0x14000c7ce`: `VsmmpReadMemoryBlockByteRange`
- `0x14000ca11`: `VsmmpReadMemoryBlockByteRange`
- `0x14000cd1f`: `VsmmpReadMemoryBlockByteRange`
- `0x14000cfc7`: `VsmmpReadMemoryBlockByteRange`
- `0x14000d273`: `VsmmpReadMemoryBlockByteRange`

## pseudocode

```c
__int64 __fastcall VsmmpReadMemoryBlockByteRange(
        unsigned __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned __int64 a6,
        char a7,
        __int64 a8,
        __int64 *a9)
{
  unsigned __int64 v10; // r13
  __int64 v11; // r14
  char v12; // r15
  unsigned __int64 v13; // rdi
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
  __int64 v27; // r9
  unsigned __int64 v28; // r15
  __int64 v29; // rdi
  __int64 v30; // rdx
  int v31; // ecx
  __int64 v32; // rax
  char *v33; // rdx
  __int64 v34; // rcx
  struct _KPROCESS *v35; // rcx
  unsigned int v36; // edi
  PVOID v37; // r15
  __int64 v38; // rdx
  int v39; // ecx
  __int64 v40; // rax
  char *v41; // rdx
  __int64 v42; // rdx
  int v43; // ecx
  __int64 v44; // rax
  int v45; // edi
  unsigned __int64 v46; // r12
  unsigned __int64 v47; // rcx
  __int64 v48; // r13
  void *v49; // r9
  __int64 v50; // rax
  unsigned __int64 v51; // rcx
  int v52; // ecx
  __int64 v53; // rdx
  int v54; // ecx
  __int64 v55; // rax
  char *v56; // rdx
  unsigned __int64 i; // r14
  __int64 v58; // rdx
  __int64 NextForwardRunClear; // r10
  unsigned __int64 v60; // r9
  __int64 v61; // rdx
  int v62; // ecx
  __int64 v63; // rax
  unsigned __int64 v64; // r9
  __int64 v65; // r12
  unsigned __int64 v66; // rcx
  void *v67; // r8
  unsigned __int64 v68; // r13
  int v69; // r9d
  __int64 v70; // rdx
  int v71; // ecx
  __int64 v72; // rax
  int v73; // r14d
  int v74; // eax
  int v75; // r9d
  int v76; // eax
  int v77; // r8d
  __int64 v78; // rdx
  int v79; // ecx
  __int64 v80; // rax
  __int64 v81; // rdx
  int v82; // ecx
  __int64 v83; // rax
  unsigned __int64 v84; // r11
  __int64 v85; // rdx
  struct _MDL *v86; // rbx
  int v88; // [rsp+20h] [rbp-308h]
  int v89; // [rsp+20h] [rbp-308h]
  int v90; // [rsp+20h] [rbp-308h]
  int v91; // [rsp+20h] [rbp-308h]
  int v92; // [rsp+50h] [rbp-2D8h] BYREF
  unsigned int v93; // [rsp+54h] [rbp-2D4h] BYREF
  char v94; // [rsp+58h] [rbp-2D0h]
  char v95; // [rsp+59h] [rbp-2CFh]
  unsigned __int64 v96; // [rsp+60h] [rbp-2C8h]
  __int64 v97; // [rsp+68h] [rbp-2C0h] BYREF
  char v98; // [rsp+70h] [rbp-2B8h]
  int v99; // [rsp+78h] [rbp-2B0h] BYREF
  unsigned __int64 v100; // [rsp+80h] [rbp-2A8h]
  __int64 v101; // [rsp+88h] [rbp-2A0h]
  __int64 v102; // [rsp+90h] [rbp-298h] BYREF
  int v103; // [rsp+98h] [rbp-290h] BYREF
  unsigned __int64 v104; // [rsp+A0h] [rbp-288h] BYREF
  unsigned __int64 v105; // [rsp+A8h] [rbp-280h]
  unsigned __int64 v106; // [rsp+B0h] [rbp-278h] BYREF
  unsigned __int64 v107; // [rsp+B8h] [rbp-270h]
  unsigned __int64 v108; // [rsp+C0h] [rbp-268h] BYREF
  unsigned __int64 v109; // [rsp+C8h] [rbp-260h] BYREF
  unsigned __int64 v110; // [rsp+D0h] [rbp-258h] BYREF
  __int64 v111; // [rsp+D8h] [rbp-250h] BYREF
  void *v112; // [rsp+E0h] [rbp-248h]
  __int64 v113; // [rsp+E8h] [rbp-240h]
  __int64 v114; // [rsp+F0h] [rbp-238h]
  unsigned __int64 v115; // [rsp+F8h] [rbp-230h] BYREF
  __int64 v116; // [rsp+100h] [rbp-228h] BYREF
  unsigned __int64 v117; // [rsp+108h] [rbp-220h] BYREF
  __int64 v118; // [rsp+110h] [rbp-218h] BYREF
  unsigned __int64 v119; // [rsp+118h] [rbp-210h] BYREF
  PMDL MemoryDescriptorList; // [rsp+120h] [rbp-208h] BYREF
  int v121; // [rsp+128h] [rbp-200h]
  PVOID Entry; // [rsp+130h] [rbp-1F8h]
  __int128 v123; // [rsp+138h] [rbp-1F0h] BYREF
  __int128 v124; // [rsp+148h] [rbp-1E0h]
  __int128 v125; // [rsp+158h] [rbp-1D0h] BYREF
  __int64 *v126; // [rsp+168h] [rbp-1C0h]
  unsigned __int64 v127; // [rsp+170h] [rbp-1B8h] BYREF
  __int128 v128; // [rsp+178h] [rbp-1B0h]
  struct _KAPC_STATE ApcState; // [rsp+188h] [rbp-1A0h] BYREF
  _BYTE v130[24]; // [rsp+1C0h] [rbp-168h] BYREF
  _BYTE v131[16]; // [rsp+1E0h] [rbp-148h] BYREF
  _BYTE v132[16]; // [rsp+1F0h] [rbp-138h] BYREF
  int *v133; // [rsp+200h] [rbp-128h]
  __int64 v134; // [rsp+208h] [rbp-120h]
  int *v135; // [rsp+210h] [rbp-118h]
  __int64 v136; // [rsp+218h] [rbp-110h]
  __int64 v137; // [rsp+220h] [rbp-108h]
  __int64 v138; // [rsp+228h] [rbp-100h]
  int *v139; // [rsp+230h] [rbp-F8h]
  __int64 v140; // [rsp+238h] [rbp-F0h]
  __int64 v141; // [rsp+240h] [rbp-E8h]
  int v142; // [rsp+248h] [rbp-E0h] BYREF
  int v143; // [rsp+24Ch] [rbp-DCh]
  __int64 *v144; // [rsp+250h] [rbp-D8h]
  __int64 v145; // [rsp+258h] [rbp-D0h]
  __int64 *v146; // [rsp+260h] [rbp-C8h]
  __int64 v147; // [rsp+268h] [rbp-C0h]
  __int64 *v148; // [rsp+270h] [rbp-B8h]
  __int64 v149; // [rsp+278h] [rbp-B0h]
  unsigned __int64 *v150; // [rsp+280h] [rbp-A8h]
  __int64 v151; // [rsp+288h] [rbp-A0h]
  unsigned __int64 *v152; // [rsp+290h] [rbp-98h]
  __int64 v153; // [rsp+298h] [rbp-90h]
  char v154[64]; // [rsp+2A0h] [rbp-88h] BYREF

  v113 = a3;
  v105 = a2;
  v10 = a1;
  v96 = a1;
  v119 = a1;
  v108 = a2;
  v109 = a3;
  v99 = a4;
  v11 = a5;
  v97 = a5;
  v102 = a8;
  v126 = a9;
  memset(&ApcState, 0, sizeof(ApcState));
  v93 = 0;
  v125 = 0;
  v123 = 0;
  v124 = 0;
  v117 = 0;
  *a9 = 0;
  v95 = 0;
  v12 = 0;
  Entry = 0;
  v114 = -1;
  MemoryDescriptorList = 0;
  v13 = *(_QWORD *)(a1 + 8);
  v100 = v13;
  v110 = v13;
  v103 = VsmmHostAccessMinimumForMemoryBlock();
  v14 = *(_QWORD *)(*((_QWORD *)VidDeviceExtension + 33) + 8LL * (unsigned __int8)KeGetCurrentNodeNumber());
  v101 = v14;
  v111 = v14;
  v128 = 0;
  v127 = v13;
  v16 = a4 & 0xC;
  v92 = v16;
  if ( (a4 & 4) != 0 )
  {
    KnownZeroVaPages = -1073741637;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_115;
    tlgCreate1Sz_char(v131, "VsmmpReadMemoryBlockByteRange");
    tlgCreate1Sz_char(v132, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    v93 = 1405;
    v133 = (int *)&v93;
    v134 = 4;
    v92 = v18;
    v135 = &v92;
    v136 = 4;
    v19 = *(_QWORD *)(v10 + 8);
    v137 = v19 + 656;
    v138 = 16;
    v20 = *(unsigned __int16 *)(v19 + 120);
    v21 = *(_QWORD *)(v19 + 128);
    v139 = &v142;
    v140 = 2;
    v141 = v21;
    v142 = v20;
    v143 = 0;
    v97 = *(_QWORD *)(v19 + 648);
    v144 = &v97;
    v88 = 10;
    v22 = byte_140056E03;
    goto LABEL_5;
  }
  if ( a6 > 0xFFFFFFFF )
  {
    KnownZeroVaPages = -1073741637;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_115;
    tlgCreate1Sz_char(v131, "VsmmpReadMemoryBlockByteRange");
    tlgCreate1Sz_char(v132, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    v93 = 1421;
    v133 = (int *)&v93;
    v134 = 4;
    v92 = v23;
    v135 = &v92;
    v136 = 4;
    v24 = *(_QWORD *)(v10 + 8);
    v137 = v24 + 656;
    v138 = 16;
    v25 = *(unsigned __int16 *)(v24 + 120);
    v26 = *(_QWORD *)(v24 + 128);
    v139 = &v142;
    v140 = 2;
    v141 = v26;
    v142 = v25;
    v143 = 0;
    v97 = *(_QWORD *)(v24 + 648);
    v144 = &v97;
    v102 = a6;
    v146 = &v102;
    v147 = 8;
    v88 = 11;
    v22 = &byte_140056C27;
LABEL_5:
    v145 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v22, 0, 0, v88, v130);
    goto LABEL_115;
  }
  v27 = a5;
  v116 = a5;
  v94 = 0;
  if ( (*(_DWORD *)(v10 + 264) & 8) == 0 )
    goto LABEL_26;
  v28 = v13 + 10408;
  VidLockAcquireShared(v13 + 10408);
  if ( *(_QWORD *)(v13 + 10416) && (a4 & 3) == 0 )
    goto LABEL_15;
  v29 = *(_QWORD *)(v13 + 10328);
  if ( PsGetCurrentProcess() != v29 )
  {
    v13 = v100;
LABEL_15:
    KnownZeroVaPages = VsmmpMapUserBufferToSystem(a5, (unsigned int)a6, &MemoryDescriptorList, 1, &v116);
    if ( KnownZeroVaPages < 0 )
    {
      v12 = 1;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_114;
      tlgCreate1Sz_char(v131, "VsmmpReadMemoryBlockByteRange");
      tlgCreate1Sz_char(v132, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
      v93 = 1456;
      v133 = (int *)&v93;
      v134 = 4;
      v92 = KnownZeroVaPages;
      v135 = &v92;
      v136 = 4;
      v30 = *(_QWORD *)(v10 + 8);
      v137 = v30 + 656;
      v138 = 16;
      v31 = *(unsigned __int16 *)(v30 + 120);
      v32 = *(_QWORD *)(v30 + 128);
      v139 = &v142;
      v140 = 2;
      v141 = v32;
      v142 = v31;
      v143 = 0;
      v97 = *(_QWORD *)(v30 + 648);
      v144 = &v97;
      v102 = a6;
      v146 = &v102;
      v89 = 11;
      v33 = byte_140056CA1;
LABEL_19:
      v147 = 8;
      v145 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v33, 0, 0, v89, v130);
      goto LABEL_114;
    }
    a7 = 0;
    v34 = *(_QWORD *)(v13 + 10416);
    if ( !v34 || (a4 & 3) != 0 )
    {
      v35 = *(struct _KPROCESS **)(v13 + 10328);
    }
    else
    {
      v94 = 1;
      v35 = *(struct _KPROCESS **)(v34 + 88);
    }
    KeStackAttachProcess(v35, &ApcState);
    v95 = 1;
    v11 = v97;
  }
  VidLockRelease(v28);
  v27 = v116;
  v16 = v92;
  v14 = v101;
LABEL_26:
  if ( v16 )
  {
    v36 = (a4 >> 2) & 3;
    v37 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v14 + 96LL * (v36 - 1) + 224));
    Entry = v37;
    if ( !v37 )
    {
      KnownZeroVaPages = -1073741670;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_32;
      tlgCreate1Sz_char(v131, "VsmmpReadMemoryBlockByteRange");
      tlgCreate1Sz_char(v132, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
      v93 = 1502;
      v133 = (int *)&v93;
      v134 = 4;
      v92 = -1073741670;
      v135 = &v92;
      v136 = 4;
      v38 = *(_QWORD *)(v10 + 8);
      v137 = v38 + 656;
      v138 = 16;
      v39 = *(unsigned __int16 *)(v38 + 120);
      v40 = *(_QWORD *)(v38 + 128);
      v139 = &v142;
      v140 = 2;
      v141 = v40;
      v142 = v39;
      v143 = 0;
      v97 = *(_QWORD *)(v38 + 648);
      v144 = &v97;
      v90 = 10;
      v41 = byte_140056D1B;
LABEL_31:
      v145 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v41, 0, 0, v90, v130);
LABEL_32:
      v12 = 0;
      goto LABEL_114;
    }
    if ( !MemoryDescriptorList && a7 )
    {
      KnownZeroVaPages = VsmmpMapUserBufferToSystem(v11, (unsigned int)a6, &MemoryDescriptorList, 1, &v116);
      if ( KnownZeroVaPages < 0 )
      {
        if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          goto LABEL_32;
        tlgCreate1Sz_char(v131, "VsmmpReadMemoryBlockByteRange");
        tlgCreate1Sz_char(v132, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
        v93 = 1520;
        v133 = (int *)&v93;
        v134 = 4;
        v92 = KnownZeroVaPages;
        v135 = &v92;
        v136 = 4;
        v42 = *(_QWORD *)(v10 + 8);
        v137 = v42 + 656;
        v138 = 16;
        v43 = *(unsigned __int16 *)(v42 + 120);
        v44 = *(_QWORD *)(v42 + 128);
        v139 = &v142;
        v140 = 2;
        v141 = v44;
        v142 = v43;
        v143 = 0;
        v97 = *(_QWORD *)(v42 + 648);
        v144 = &v97;
        v102 = a6;
        v146 = &v102;
        v147 = 8;
        v90 = 11;
        v41 = byte_140056D89;
        goto LABEL_31;
      }
      a7 = 0;
    }
    DWORD1(v124) = 0;
    LODWORD(v123) = VsmmCompressionFormatToVmCompress(v36);
    DWORD1(v123) = 3;
    v27 = v116;
    *((_QWORD *)&v123 + 1) = v116;
    LODWORD(v124) = a6;
    *((_QWORD *)&v124 + 1) = v37;
  }
  v12 = 0;
  v98 = 0;
  v45 = VsmmpConvertMbpRwFlagsToMbpLockFlags(a4, 0, v15, v27);
  v46 = v105;
  v107 = v105;
  v47 = v105 + v113;
  v106 = v105 + v113;
  v48 = v105 >> 12;
  v112 = v49;
LABEL_42:
  if ( v46 >= v47 )
  {
    if ( v92 )
    {
      KnownZeroVaPages = VmCompressPackExComplete(&v123, &v93);
      if ( KnownZeroVaPages < 0 )
      {
        if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          goto LABEL_113;
        tlgCreate1Sz_char(v131, "VsmmpReadMemoryBlockByteRange");
        tlgCreate1Sz_char(v132, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
        v103 = 1899;
        v133 = &v103;
        v134 = 4;
        v99 = KnownZeroVaPages;
        v135 = &v99;
        v136 = 4;
        v10 = v96;
        v81 = *(_QWORD *)(v96 + 8);
        v137 = v81 + 656;
        v138 = 16;
        v82 = *(unsigned __int16 *)(v81 + 120);
        v83 = *(_QWORD *)(v81 + 128);
        v139 = &v142;
        v140 = 2;
        v141 = v83;
        v142 = v82;
        v143 = 0;
        v111 = *(_QWORD *)(v81 + 648);
        v144 = &v111;
        v110 = v84;
        v146 = (__int64 *)&v110;
        v104 = v113;
        v148 = (__int64 *)&v104;
        v149 = 8;
        v89 = 12;
        v33 = byte_1400568F5;
        goto LABEL_19;
      }
      v85 = v93;
    }
    else
    {
      v85 = v113;
    }
    *v126 = v85;
    KnownZeroVaPages = 0;
    goto LABEL_113;
  }
  v50 = v48 & 0x1FF;
  v51 = v47 - v46;
  if ( v51 >= (512 - v50) << 12 )
    v51 = (512 - v50) << 12;
  v115 = (v51 + 4095 + (v46 & 0xFFF)) >> 12;
  RtlInitializeBitMapEx(&v125, v154, v115);
  RtlClearAllBitsEx(&v125);
  v52 = *(_DWORD *)(v96 + 264);
  if ( (v52 & 8) != 0 && (a4 & 3) == 0 && !v94 && (v52 & 0x10000) == 0 )
  {
    KnownZeroVaPages = VsmmQueryKnownZeroVaPages(*(PRKPROCESS *)(v100 + 10328));
    if ( KnownZeroVaPages < 0 )
    {
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v131, "VsmmpReadMemoryBlockByteRange");
        tlgCreate1Sz_char(v132, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
        v93 = 1614;
        v133 = (int *)&v93;
        v134 = 4;
        v92 = KnownZeroVaPages;
        v135 = &v92;
        v136 = 4;
        v53 = *(_QWORD *)(v96 + 8);
        v137 = v53 + 656;
        v138 = 16;
        v54 = *(unsigned __int16 *)(v53 + 120);
        v55 = *(_QWORD *)(v53 + 128);
        v139 = &v142;
        v140 = 2;
        v141 = v55;
        v142 = v54;
        v143 = 0;
        v97 = *(_QWORD *)(v53 + 648);
        v144 = &v97;
        v102 = v48;
        v146 = &v102;
        v119 = v115;
        v148 = (__int64 *)&v119;
        v91 = 12;
        v56 = byte_140056981;
LABEL_53:
        v149 = 8;
        v147 = 8;
        v145 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v56, 0, 0, v91, v130);
      }
      goto LABEL_113;
    }
  }
  for ( i = 0; ; i = v118 + v117 )
  {
    v97 = i;
    if ( i >= v115 )
      goto LABEL_103;
    NextForwardRunClear = RtlFindNextForwardRunClearEx(&v125, i, &v117);
    v118 = NextForwardRunClear;
    if ( !NextForwardRunClear )
      v117 = v115;
    if ( v117 > i )
    {
      v60 = (v48 + v117 - i) << 12;
      if ( v106 < v60 )
        v60 = v106;
      v104 = v60;
      if ( v92 )
      {
        KnownZeroVaPages = VmCompressPackExAddConstantRun(&v123, v58, (unsigned int)(v60 - v46));
        v121 = KnownZeroVaPages;
        if ( KnownZeroVaPages < 0 )
        {
          if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          {
            tlgCreate1Sz_char(v131, "VsmmpReadMemoryBlockByteRange");
            tlgCreate1Sz_char(v132, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
            v93 = 1675;
            v133 = (int *)&v93;
            v134 = 4;
            v92 = KnownZeroVaPages;
            v135 = &v92;
            v136 = 4;
            v10 = v96;
            v61 = *(_QWORD *)(v96 + 8);
            v137 = v61 + 656;
            v138 = 16;
            v62 = *(unsigned __int16 *)(v61 + 120);
            v63 = *(_QWORD *)(v61 + 128);
            v139 = &v142;
            v140 = 2;
            v141 = v63;
            v142 = v62;
            v143 = 0;
            v97 = *(_QWORD *)(v61 + 648);
            v144 = &v97;
            v145 = 8;
            v102 = v105;
            v146 = &v102;
            v147 = 8;
            v118 = v113;
            v148 = &v118;
            v149 = 8;
            v115 = v46;
            v150 = &v115;
            v151 = 8;
            v106 = v64;
            v152 = &v106;
            v153 = 8;
            tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, byte_140056A0B, 0, 0, 14, v130);
          }
          else
          {
            v10 = v96;
          }
          v13 = v100;
          v65 = v101;
          goto LABEL_116;
        }
        i = v97;
      }
      else
      {
        if ( a7 )
          RtlSetUserMemory(v112);
        else
          RtlSetVolatileMemory(v112, 0, v60 - v46);
        NextForwardRunClear = v118;
      }
    }
    v48 += v117 - i;
    v66 = v48;
    v46 = v48 << 12;
    if ( v48 << 12 >= v105 )
    {
      if ( v46 > v106 )
        v46 = v106;
      v107 = v46;
    }
    else
    {
      v46 = v105;
      v107 = v105;
    }
    v67 = (void *)(v46 + v116 - v105);
    v112 = v67;
    if ( !NextForwardRunClear )
    {
LABEL_103:
      v47 = v106;
      if ( v114 != -1 )
      {
        VidPushLockRelease(*(_QWORD *)(v96 + 400) + 8 * v114);
        v114 = -1;
        v47 = v106;
      }
      goto LABEL_42;
    }
    v68 = (NextForwardRunClear + v48) << 12;
    if ( v106 < v68 )
      v68 = v106;
    if ( v94 )
      break;
    if ( (a4 & 3) != 0 || v103 )
    {
      v73 = v96;
    }
    else
    {
      v73 = v96;
      if ( v114 == -1 )
      {
        v114 = v66 >> 9;
        VidPushLockAcquireShared(*(_QWORD *)(v96 + 400) + 8 * (v66 >> 9), v106);
        v67 = v112;
      }
    }
    v74 = a4 & 0x20;
    v107 = v68 - v46;
    v75 = v68 - v46;
    if ( v92 )
      v76 = VsmmMemoryBlockCopyByteRange((unsigned int)&v127, v73, v46, v75, 0, (__int64)&v123, v45, v74 != 0, a7, v102);
    else
      v76 = VsmmMemoryBlockCopyByteRange((unsigned int)&v127, v73, v46, v75, (__int64)v67, 0, v45, v74 != 0, a7, v102);
    KnownZeroVaPages = v76;
    if ( v76 < 0 )
    {
      v13 = v100;
      if ( !(unsigned __int8)VsmmReadWriteFailureExpected(v100, a4, (unsigned int)v76)
        && (unsigned int)dword_140065110 > 2
        && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v131, "VsmmpReadMemoryBlockByteRange");
        tlgCreate1Sz_char(v132, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
        v103 = 1853;
        v133 = &v103;
        v134 = 4;
        v99 = v77;
        v135 = &v99;
        v136 = 4;
        v78 = *(_QWORD *)(v96 + 8);
        v137 = v78 + 656;
        v138 = 16;
        v79 = *(unsigned __int16 *)(v78 + 120);
        v80 = *(_QWORD *)(v78 + 128);
        v139 = &v142;
        v140 = 2;
        v141 = v80;
        v142 = v79;
        v143 = 0;
        v111 = *(_QWORD *)(v78 + 648);
        v144 = &v111;
        v145 = 8;
        v110 = v105;
        v146 = (__int64 *)&v110;
        v147 = 8;
        v104 = v113;
        v148 = (__int64 *)&v104;
        v149 = 8;
        v109 = v46;
        v150 = &v109;
        v151 = 8;
        v108 = v68;
        v152 = &v108;
        v153 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, byte_140056841, 0, 0, 14, v130);
      }
      v10 = v96;
      goto LABEL_115;
    }
LABEL_102:
    v112 = (char *)v112 + v107;
    v46 = v68;
    v107 = v68;
    v48 = v68 >> 12;
  }
  v107 = v68 - v46;
  v69 = v46 + v116 - v105;
  if ( v92 )
    v69 = 0;
  KnownZeroVaPages = VsmmpReadCloneTemplateByteRange(
                       v96,
                       v46,
                       (int)v68 - (int)v46,
                       v69,
                       (unsigned __int64)&v123 & -(__int64)(v92 != 0),
                       a7);
  if ( KnownZeroVaPages >= 0 )
    goto LABEL_102;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v131, "VsmmpReadMemoryBlockByteRange");
    tlgCreate1Sz_char(v132, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    v99 = 1779;
    v133 = &v99;
    v134 = 4;
    v93 = KnownZeroVaPages;
    v135 = (int *)&v93;
    v136 = 4;
    v70 = *(_QWORD *)(v96 + 8);
    v137 = v70 + 656;
    v138 = 16;
    v71 = *(unsigned __int16 *)(v70 + 120);
    v72 = *(_QWORD *)(v70 + 128);
    v139 = &v142;
    v140 = 2;
    v141 = v72;
    v142 = v71;
    v143 = 0;
    v111 = *(_QWORD *)(v70 + 648);
    v144 = &v111;
    v110 = v105;
    v146 = (__int64 *)&v110;
    v104 = v113;
    v148 = (__int64 *)&v104;
    v109 = v46;
    v150 = &v109;
    v151 = 8;
    v108 = v68;
    v152 = &v108;
    v153 = 8;
    v91 = 14;
    v56 = byte_140056B73;
    goto LABEL_53;
  }
LABEL_113:
  v10 = v96;
LABEL_114:
  v13 = v100;
LABEL_115:
  v65 = v101;
LABEL_116:
  VsmmMemoryBlockMbpRangeVaDestroy(&v127);
  if ( v114 != -1 )
    VidPushLockRelease(*(_QWORD *)(v10 + 400) + 8 * v114);
  if ( v12 )
    VidLockRelease(v13 + 10408);
  if ( Entry )
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v65 + 96LL * (((a4 >> 2) & 3) - 1) + 224), Entry);
  if ( v95 )
    KeUnstackDetachProcess(&ApcState);
  v86 = MemoryDescriptorList;
  if ( MemoryDescriptorList )
  {
    MmUnlockPages(MemoryDescriptorList);
    IoFreeMdl(v86);
  }
  return (unsigned int)KnownZeroVaPages;
}

```

## disassembly

```asm
0x14000ba38  push    rbx
0x14000ba3a  push    rsi
0x14000ba3b  push    rdi
0x14000ba3c  push    r12
0x14000ba3e  push    r13
0x14000ba40  push    r14
0x14000ba42  push    r15
0x14000ba44  sub     rsp, 2F0h
0x14000ba4b  mov     rax, cs:__security_cookie
0x14000ba52  xor     rax, rsp
0x14000ba55  mov     [rsp+328h+var_48], rax
0x14000ba5d  mov     ebx, r9d
0x14000ba60  mov     rax, r8
0x14000ba63  mov     [rsp+328h+var_240], rax
0x14000ba6b  mov     [rsp+328h+var_280], rdx
0x14000ba73  mov     r13, rcx
0x14000ba76  mov     [rsp+328h+var_2C8], rcx
0x14000ba7b  mov     [rsp+328h+var_210], rcx
0x14000ba83  mov     [rsp+328h+var_268], rdx
0x14000ba8b  mov     [rsp+328h+var_260], rax
0x14000ba93  mov     [rsp+328h+var_2B0], ebx
0x14000ba97  mov     r14, [rsp+328h+arg_20]
0x14000ba9f  mov     [rsp+328h+var_2C0], r14
0x14000baa4  mov     rax, [rsp+328h+arg_38]
0x14000baac  mov     [rsp+328h+var_298], rax
0x14000bab4  mov     rax, [rsp+328h+arg_40]
0x14000babc  mov     [rsp+328h+var_1C0], rax
0x14000bac4  xorps   xmm0, xmm0
0x14000bac7  movups  xmmword ptr [rsp+328h+ApcState.ApcListHead.Flink], xmm0
0x14000bacf  movups  xmmword ptr [rsp+328h+ApcState.ApcListHead.Flink+10h], xmm0
0x14000bad7  movups  xmmword ptr [rsp+328h+ApcState.Process], xmm0
0x14000badf  xor     esi, esi
0x14000bae1  mov     [rsp+328h+var_2D4], esi
0x14000bae5  movups  [rsp+328h+var_1D0], xmm0
0x14000baed  xorps   xmm1, xmm1
0x14000baf0  movups  [rsp+328h+var_1F0], xmm1
0x14000baf8  movups  [rsp+328h+var_1E0], xmm1
0x14000bb00  mov     [rsp+328h+var_220], rsi
0x14000bb08  mov     [rax], rsi
0x14000bb0b  mov     [rsp+328h+var_2CF], sil
0x14000bb10  mov     r15b, sil
0x14000bb13  mov     [rsp+328h+Entry], rsi
0x14000bb1b  mov     [rsp+328h+var_238], 0FFFFFFFFFFFFFFFFh
0x14000bb27  mov     [rsp+328h+MemoryDescriptorList], rsi
0x14000bb2f  mov     rdi, [rcx+8]
0x14000bb33  mov     [rsp+328h+var_2A8], rdi
0x14000bb3b  mov     [rsp+328h+var_258], rdi
0x14000bb43  call    VsmmHostAccessMinimumForMemoryBlock
0x14000bb48  mov     [rsp+328h+var_290], eax
0x14000bb4f  call    cs:__imp_KeGetCurrentNodeNumber
0x14000bb56  nop     dword ptr [rax+rax+00h]
0x14000bb5b  movzx   edx, al
0x14000bb5e  mov     rax, cs:VidDeviceExtension
0x14000bb65  mov     rcx, [rax+108h]
0x14000bb6c  mov     rdx, [rcx+rdx*8]
0x14000bb70  mov     [rsp+328h+var_2A0], rdx
0x14000bb78  mov     [rsp+328h+var_250], rdx
0x14000bb80  xorps   xmm0, xmm0
0x14000bb83  movdqu  [rsp+328h+var_1B0], xmm0
0x14000bb8c  mov     [rsp+328h+var_1B8], rdi
0x14000bb94  mov     r10d, ebx
0x14000bb97  and     r10d, 0Ch
0x14000bb9b  mov     [rsp+328h+var_2D8], r10d
0x14000bba0  test    r10d, 0FFFFFFF7h
0x14000bba7  jz      loc_14000BCF9
0x14000bbad  mov     r8d, 0C00000BBh
0x14000bbb3  mov     r14d, r8d
0x14000bbb6  mov     eax, cs:dword_140065110
0x14000bbbc  cmp     eax, 2
0x14000bbbf  jbe     loc_14000D3EE
0x14000bbc5  mov     edx, 100h
0x14000bbca  lea     rcx, dword_140065110
0x14000bbd1  call    _tlgKeywordOn
0x14000bbd6  test    al, al
0x14000bbd8  jz      loc_14000D3EE
0x14000bbde  lea     rdx, aVsmmpreadmemor; "VsmmpReadMemoryBlockByteRange"
0x14000bbe5  lea     rcx, [rsp+328h+var_148]
0x14000bbed  call    _tlgCreate1Sz_char
0x14000bbf2  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000bbf9  lea     rcx, [rsp+328h+var_138]
0x14000bc01  call    _tlgCreate1Sz_char
0x14000bc06  mov     [rsp+328h+var_2D4], 57Dh
0x14000bc0e  lea     rax, [rsp+328h+var_2D4]
0x14000bc13  mov     [rsp+328h+var_128], rax
0x14000bc1b  mov     [rsp+328h+var_120], 4
0x14000bc27  mov     [rsp+328h+var_2D8], r8d
0x14000bc2c  lea     rcx, [rsp+328h+var_2D8]
0x14000bc31  mov     [rsp+328h+var_118], rcx
0x14000bc39  mov     [rsp+328h+var_110], 4
0x14000bc45  mov     rdx, [r13+8]
0x14000bc49  lea     rax, [rdx+290h]
0x14000bc50  mov     [rsp+328h+var_108], rax
0x14000bc58  mov     [rsp+328h+var_100], 10h
0x14000bc64  movzx   ecx, word ptr [rdx+78h]
0x14000bc68  mov     rax, [rdx+80h]
0x14000bc6f  lea     r8, [rsp+328h+var_E0]
0x14000bc77  mov     [rsp+328h+var_F8], r8
0x14000bc7f  mov     [rsp+328h+var_F0], 2
0x14000bc8b  mov     [rsp+328h+var_E8], rax
0x14000bc93  mov     [rsp+328h+var_E0], ecx
0x14000bc9a  mov     [rsp+328h+var_DC], esi
0x14000bca1  mov     rax, [rdx+288h]
0x14000bca8  mov     [rsp+328h+var_2C0], rax
0x14000bcad  lea     rax, [rsp+328h+var_2C0]
0x14000bcb2  mov     [rsp+328h+var_D8], rax
0x14000bcba  lea     rax, [rsp+328h+var_168]
0x14000bcc2  mov     [rsp+328h+var_300], rax
0x14000bcc7  mov     dword ptr [rsp+328h+var_308], 0Ah
0x14000bccf  lea     rdx, byte_140056E03
0x14000bcd6  xor     r9d, r9d
0x14000bcd9  xor     r8d, r8d
0x14000bcdc  mov     [rsp+328h+var_D0], 8
0x14000bce8  lea     rcx, dword_140065110
0x14000bcef  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000bcf4  jmp     loc_14000D3EE
0x14000bcf9  mov     eax, 0FFFFFFFFh
0x14000bcfe  mov     r12, [rsp+328h+arg_28]
0x14000bd06  cmp     r12, rax
0x14000bd09  jbe     loc_14000BE61
0x14000bd0f  mov     r8d, 0C00000BBh
0x14000bd15  mov     r14d, r8d
0x14000bd18  mov     eax, cs:dword_140065110
0x14000bd1e  cmp     eax, 2
0x14000bd21  jbe     loc_14000D3EE
0x14000bd27  mov     edx, 100h
0x14000bd2c  lea     rcx, dword_140065110
0x14000bd33  call    _tlgKeywordOn
0x14000bd38  test    al, al
0x14000bd3a  jz      loc_14000D3EE
0x14000bd40  lea     rdx, aVsmmpreadmemor; "VsmmpReadMemoryBlockByteRange"
0x14000bd47  lea     rcx, [rsp+328h+var_148]
0x14000bd4f  call    _tlgCreate1Sz_char
0x14000bd54  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000bd5b  lea     rcx, [rsp+328h+var_138]
0x14000bd63  call    _tlgCreate1Sz_char
0x14000bd68  mov     [rsp+328h+var_2D4], 58Dh
0x14000bd70  lea     rax, [rsp+328h+var_2D4]
0x14000bd75  mov     [rsp+328h+var_128], rax
0x14000bd7d  mov     [rsp+328h+var_120], 4
0x14000bd89  mov     [rsp+328h+var_2D8], r8d
0x14000bd8e  lea     rcx, [rsp+328h+var_2D8]
0x14000bd93  mov     [rsp+328h+var_118], rcx
0x14000bd9b  mov     [rsp+328h+var_110], 4
0x14000bda7  mov     rdx, [r13+8]
0x14000bdab  lea     rax, [rdx+290h]
0x14000bdb2  mov     [rsp+328h+var_108], rax
0x14000bdba  mov     [rsp+328h+var_100], 10h
0x14000bdc6  movzx   ecx, word ptr [rdx+78h]
0x14000bdca  mov     rax, [rdx+80h]
0x14000bdd1  lea     r8, [rsp+328h+var_E0]
0x14000bdd9  mov     [rsp+328h+var_F8], r8
0x14000bde1  mov     [rsp+328h+var_F0], 2
0x14000bded  mov     [rsp+328h+var_E8], rax
0x14000bdf5  mov     [rsp+328h+var_E0], ecx
0x14000bdfc  mov     [rsp+328h+var_DC], esi
0x14000be03  mov     rax, [rdx+288h]
0x14000be0a  mov     [rsp+328h+var_2C0], rax
0x14000be0f  lea     rax, [rsp+328h+var_2C0]
0x14000be14  mov     [rsp+328h+var_D8], rax
0x14000be1c  mov     [rsp+328h+var_298], r12
0x14000be24  lea     rcx, [rsp+328h+var_298]
0x14000be2c  mov     [rsp+328h+var_C8], rcx
0x14000be34  mov     [rsp+328h+var_C0], 8
0x14000be40  lea     rax, [rsp+328h+var_168]
0x14000be48  mov     [rsp+328h+var_300], rax
0x14000be4d  mov     dword ptr [rsp+328h+var_308], 0Bh
0x14000be55  lea     rdx, byte_140056C27
0x14000be5c  jmp     loc_14000BCD6
0x14000be61  mov     r9, r14
0x14000be64  mov     [rsp+328h+var_228], r14
0x14000be6c  mov     [rsp+328h+var_2D0], sil
0x14000be71  mov     eax, [r13+108h]
0x14000be78  test    al, 8
0x14000be7a  jz      loc_14000C0C2
0x14000be80  lea     r15, [rdi+28A8h]
0x14000be87  mov     rcx, r15
0x14000be8a  call    VidLockAcquireShared
0x14000be8f  cmp     [rdi+28B0h], rsi
0x14000be96  jz      short loc_14000BE9D
0x14000be98  test    bl, 3
0x14000be9b  jz      short loc_14000BEC1
0x14000be9d  mov     rdi, [rdi+2858h]
0x14000bea4  call    cs:__imp_PsGetCurrentProcess
0x14000beab  nop     dword ptr [rax+rax+00h]
0x14000beb0  cmp     rax, rdi
0x14000beb3  jz      loc_14000C0A5
0x14000beb9  mov     rdi, [rsp+328h+var_2A8]
0x14000bec1  mov     edx, r12d
0x14000bec4  lea     rax, [rsp+328h+var_228]
0x14000becc  mov     [rsp+328h+var_308], rax
0x14000bed1  mov     r9d, 1
0x14000bed7  lea     r8, [rsp+328h+MemoryDescriptorList]
0x14000bedf  mov     rcx, r14
0x14000bee2  call    VsmmpMapUserBufferToSystem
0x14000bee7  mov     r14d, eax
0x14000beea  test    eax, eax
0x14000beec  jns     loc_14000C05C
0x14000bef2  mov     r15b, 1
0x14000bef5  mov     ecx, cs:dword_140065110
0x14000befb  cmp     ecx, 2
0x14000befe  jbe     loc_14000D3E6
0x14000bf04  mov     edx, 100h
0x14000bf09  lea     rcx, dword_140065110
0x14000bf10  call    _tlgKeywordOn
0x14000bf15  test    al, al
0x14000bf17  jz      loc_14000D3E6
0x14000bf1d  lea     rdx, aVsmmpreadmemor; "VsmmpReadMemoryBlockByteRange"
0x14000bf24  lea     rcx, [rsp+328h+var_148]
0x14000bf2c  call    _tlgCreate1Sz_char
0x14000bf31  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000bf38  lea     rcx, [rsp+328h+var_138]
0x14000bf40  call    _tlgCreate1Sz_char
0x14000bf45  mov     [rsp+328h+var_2D4], 5B0h
0x14000bf4d  lea     rax, [rsp+328h+var_2D4]
0x14000bf52  mov     [rsp+328h+var_128], rax
0x14000bf5a  mov     [rsp+328h+var_120], 4
0x14000bf66  mov     [rsp+328h+var_2D8], r14d
0x14000bf6b  lea     rcx, [rsp+328h+var_2D8]
0x14000bf70  mov     [rsp+328h+var_118], rcx
0x14000bf78  mov     [rsp+328h+var_110], 4
0x14000bf84  mov     rdx, [r13+8]
0x14000bf88  lea     rax, [rdx+290h]
0x14000bf8f  mov     [rsp+328h+var_108], rax
0x14000bf97  mov     [rsp+328h+var_100], 10h
0x14000bfa3  movzx   ecx, word ptr [rdx+78h]
0x14000bfa7  mov     rax, [rdx+80h]
0x14000bfae  lea     r8, [rsp+328h+var_E0]
0x14000bfb6  mov     [rsp+328h+var_F8], r8
0x14000bfbe  mov     [rsp+328h+var_F0], 2
0x14000bfca  mov     [rsp+328h+var_E8], rax
0x14000bfd2  mov     [rsp+328h+var_E0], ecx
0x14000bfd9  mov     [rsp+328h+var_DC], esi
0x14000bfe0  mov     rax, [rdx+288h]
0x14000bfe7  mov     [rsp+328h+var_2C0], rax
0x14000bfec  lea     rax, [rsp+328h+var_2C0]
0x14000bff1  mov     [rsp+328h+var_D8], rax
0x14000bff9  mov     [rsp+328h+var_298], r12
0x14000c001  lea     rax, [rsp+328h+var_298]
0x14000c009  mov     [rsp+328h+var_C8], rax
0x14000c011  lea     rax, [rsp+328h+var_168]
0x14000c019  mov     [rsp+328h+var_300], rax
0x14000c01e  mov     dword ptr [rsp+328h+var_308], 0Bh
0x14000c026  lea     rdx, byte_140056CA1
0x14000c02d  xor     r9d, r9d
0x14000c030  xor     r8d, r8d
0x14000c033  mov     [rsp+328h+var_C0], 8
0x14000c03f  mov     [rsp+328h+var_D0], 8
0x14000c04b  lea     rcx, dword_140065110
0x14000c052  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000c057  jmp     loc_14000D3E6
0x14000c05c  mov     [rsp+328h+arg_30], sil
0x14000c064  mov     rcx, [rdi+28B0h]
0x14000c06b  test    rcx, rcx
0x14000c06e  jz      short loc_14000C080
0x14000c070  test    bl, 3
0x14000c073  jnz     short loc_14000C080
0x14000c075  mov     [rsp+328h+var_2D0], 1
0x14000c07a  mov     rcx, [rcx+58h]
0x14000c07e  jmp     short loc_14000C087
0x14000c080  mov     rcx, [rdi+2858h]; PROCESS
0x14000c087  lea     rdx, [rsp+328h+ApcState]; ApcState
0x14000c08f  call    cs:__imp_KeStackAttachProcess
0x14000c096  nop     dword ptr [rax+rax+00h]
0x14000c09b  mov     [rsp+328h+var_2CF], 1
0x14000c0a0  mov     r14, [rsp+328h+var_2C0]
0x14000c0a5  mov     rcx, r15
0x14000c0a8  call    VidLockRelease
0x14000c0ad  mov     r9, [rsp+328h+var_228]
0x14000c0b5  mov     r10d, [rsp+328h+var_2D8]
0x14000c0ba  mov     rdx, [rsp+328h+var_2A0]
0x14000c0c2  test    r10d, r10d
0x14000c0c5  jz      loc_14000C42A
0x14000c0cb  mov     edi, ebx
0x14000c0cd  shr     edi, 2
0x14000c0d0  and     edi, 3
0x14000c0d3  lea     eax, [rdi-1]
0x14000c0d6  lea     rcx, [rax+rax*2]
0x14000c0da  shl     rcx, 5
0x14000c0de  add     rcx, 0E0h
0x14000c0e5  add     rcx, rdx; Lookaside
0x14000c0e8  call    cs:__imp_ExAllocateFromLookasideListEx
0x14000c0ef  nop     dword ptr [rax+rax+00h]
0x14000c0f4  mov     r15, rax
0x14000c0f7  mov     [rsp+328h+Entry], rax
0x14000c0ff  test    rax, rax
0x14000c102  jnz     loc_14000C254
0x14000c108  mov     r14d, 0C000009Ah
0x14000c10e  mov     ecx, cs:dword_140065110
0x14000c114  cmp     ecx, 2
0x14000c117  jbe     loc_14000C24C
0x14000c11d  mov     edx, 100h
0x14000c122  lea     rcx, dword_140065110
0x14000c129  call    _tlgKeywordOn
0x14000c12e  test    al, al
0x14000c130  jz      loc_14000C24C
0x14000c136  lea     rdx, aVsmmpreadmemor; "VsmmpReadMemoryBlockByteRange"
0x14000c13d  lea     rcx, [rsp+328h+var_148]
0x14000c145  call    _tlgCreate1Sz_char
0x14000c14a  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000c151  lea     rcx, [rsp+328h+var_138]
  ... truncated ...
```
