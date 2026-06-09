# VsmmpWriteMemoryBlockByteRange

- ea: `0x14000d75c`
- end: `0x14000f21c`
- name: `VsmmpWriteMemoryBlockByteRange`
- size: `6848`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14000ad0c`
- `0x14001aa60`
- `0x1400295e0`

## callees

- `0x1400029c0`
- `0x1400064e8`
- `0x14000668c`
- `0x140006bf8`
- `0x140007200`
- `0x140007234`
- `0x1400085b0`
- `0x14000a4e0`
- `0x14000d75c`
- `0x140021650`
- `0x1400d51fc`
- `0x1400f2f50`
- `0x1400f8bc8`
- `0x1400f9cbc`
- `0x1400faa8c`
- `0x1400faef0`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x14000f1be`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000f1be`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000d9fd`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000d9fd`
- `ntoskrnl!RtlCompareMemoryUlong` at `0x14000e899`
- `ntoskrnl!RtlCompareMemoryUlong` at `0x14000e899`
- `ntoskrnl!RtlFindNextForwardRunClearEx` at `0x14000eaf1`
- `ntoskrnl!RtlFindNextForwardRunClearEx` at `0x14000eaf1`
- `ntoskrnl!RtlClearBitEx` at `0x14000e8ba`
- `ntoskrnl!RtlClearBitEx` at `0x14000e8ba`
- `ntoskrnl!RtlTestBitEx` at `0x14000e83a`
- `ntoskrnl!RtlTestBitEx` at `0x14000e83a`
- `ntoskrnl!IoFreeMdl` at `0x14000f1e9`
- `ntoskrnl!IoFreeMdl` at `0x14000f1e9`
- `ntoskrnl!KeStackAttachProcess` at `0x14000db62`
- `ntoskrnl!KeStackAttachProcess` at `0x14000db62`
- `ntoskrnl!MmUnlockPages` at `0x14000f1da`
- `ntoskrnl!MmUnlockPages` at `0x14000f1da`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x14000e5f7`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x14000e5f7`
- `ntoskrnl!RtlClearAllBitsEx` at `0x14000e60b`
- `ntoskrnl!RtlClearAllBitsEx` at `0x14000e60b`

## string_xrefs

- `0x14000d8b3`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000da72`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000dc0e`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000deb8`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000e057`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000e211`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000e3df`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000e6bf`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000e8f6`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000ec71`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000ef3d`: `VsmmpWriteMemoryBlockByteRange`

## pseudocode

```c
__int64 __fastcall VsmmpWriteMemoryBlockByteRange(
        __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned int a4,
        char *a5,
        unsigned __int64 a6,
        char a7,
        __int64 a8)
{
  __int128 v9; // xmm0
  __int64 v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  int v14; // eax
  signed int KnownZeroVaPages; // r14d
  __int64 *v16; // r9
  __int64 v17; // rdx
  int v18; // ecx
  __int64 v19; // rax
  unsigned __int64 v20; // rax
  char *v21; // rdx
  __int64 v22; // rdx
  int v23; // ecx
  __int64 v24; // rax
  char v25; // r14
  __int64 v26; // rdx
  int v27; // ecx
  __int64 v28; // rax
  int v29; // edi
  _DWORD *v30; // r9
  char v31; // r10
  unsigned __int64 v32; // r12
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // r13
  __int64 v35; // rdx
  int v36; // ecx
  __int64 v37; // rax
  unsigned __int64 v38; // r10
  int v39; // r9d
  __int64 v40; // rdx
  int v41; // ecx
  __int64 v42; // rax
  unsigned __int64 v43; // r10
  unsigned __int64 v44; // rcx
  unsigned __int64 v45; // r10
  __int64 v46; // rdx
  int v47; // ecx
  __int64 v48; // rax
  int v49; // r9d
  int v50; // r9d
  __int64 v51; // rdx
  int v52; // ecx
  __int64 v53; // rax
  unsigned __int64 v54; // r10
  int v55; // r14d
  unsigned __int64 v56; // rax
  __int64 v57; // rcx
  __int64 NextForwardRunClear; // rdx
  unsigned __int64 v59; // r8
  __int64 v60; // r9
  __int64 v61; // rdx
  int v62; // ecx
  __int64 v63; // rax
  int v64; // ecx
  unsigned __int64 i; // r14
  unsigned __int64 v66; // rax
  unsigned __int64 v67; // rax
  unsigned __int64 v68; // rdx
  unsigned __int64 v69; // rax
  unsigned __int64 v70; // r9
  SIZE_T v71; // rax
  unsigned __int64 v72; // r14
  unsigned __int64 v73; // rax
  int v74; // ecx
  unsigned __int64 v75; // rax
  __int64 v76; // rdx
  int v77; // ecx
  __int64 v78; // rax
  int v79; // r9d
  unsigned __int64 v80; // r14
  unsigned __int64 v81; // r13
  int v82; // eax
  int v83; // r9d
  int v84; // eax
  __int64 v85; // rdx
  int v86; // ecx
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 v90; // r9
  struct _MDL *v91; // rbx
  int v93; // [rsp+20h] [rbp-328h]
  int v94; // [rsp+50h] [rbp-2F8h] BYREF
  char v95; // [rsp+54h] [rbp-2F4h]
  int v96; // [rsp+58h] [rbp-2F0h] BYREF
  char v97; // [rsp+60h] [rbp-2E8h]
  unsigned __int64 v98; // [rsp+68h] [rbp-2E0h] BYREF
  unsigned __int64 v99; // [rsp+70h] [rbp-2D8h] BYREF
  int v100; // [rsp+78h] [rbp-2D0h]
  unsigned __int64 v101; // [rsp+80h] [rbp-2C8h] BYREF
  _DWORD *v102; // [rsp+88h] [rbp-2C0h] BYREF
  int v103; // [rsp+90h] [rbp-2B8h] BYREF
  int v104; // [rsp+94h] [rbp-2B4h]
  int v105; // [rsp+98h] [rbp-2B0h] BYREF
  unsigned __int64 v106; // [rsp+A0h] [rbp-2A8h]
  __int64 *v107; // [rsp+A8h] [rbp-2A0h]
  unsigned __int64 v108; // [rsp+B0h] [rbp-298h]
  __int64 v109; // [rsp+B8h] [rbp-290h]
  int v110; // [rsp+C0h] [rbp-288h] BYREF
  unsigned __int64 v111; // [rsp+C8h] [rbp-280h]
  unsigned __int64 v112; // [rsp+D0h] [rbp-278h]
  __int64 v113; // [rsp+D8h] [rbp-270h]
  unsigned __int64 v114; // [rsp+E0h] [rbp-268h] BYREF
  signed int v115; // [rsp+E8h] [rbp-260h]
  unsigned int v116; // [rsp+ECh] [rbp-25Ch] BYREF
  int v117; // [rsp+F0h] [rbp-258h] BYREF
  int v118; // [rsp+F4h] [rbp-254h] BYREF
  int v119; // [rsp+F8h] [rbp-250h] BYREF
  int v120; // [rsp+FCh] [rbp-24Ch] BYREF
  char *v121; // [rsp+100h] [rbp-248h] BYREF
  unsigned __int64 v122; // [rsp+108h] [rbp-240h] BYREF
  unsigned __int64 v123; // [rsp+110h] [rbp-238h]
  unsigned __int64 v124; // [rsp+118h] [rbp-230h] BYREF
  unsigned __int64 v125; // [rsp+120h] [rbp-228h]
  _DWORD *v126; // [rsp+128h] [rbp-220h]
  _QWORD v127[2]; // [rsp+130h] [rbp-218h] BYREF
  __int64 v128; // [rsp+140h] [rbp-208h]
  PMDL MemoryDescriptorList; // [rsp+148h] [rbp-200h] BYREF
  __int64 v130; // [rsp+150h] [rbp-1F8h]
  unsigned int v131; // [rsp+158h] [rbp-1F0h]
  __int128 v132; // [rsp+160h] [rbp-1E8h] BYREF
  __int128 v133; // [rsp+170h] [rbp-1D8h] BYREF
  __int128 v134; // [rsp+180h] [rbp-1C8h]
  __int64 v135; // [rsp+190h] [rbp-1B8h]
  __int64 v136; // [rsp+198h] [rbp-1B0h] BYREF
  __int128 v137; // [rsp+1A0h] [rbp-1A8h]
  struct _KAPC_STATE ApcState; // [rsp+1B0h] [rbp-198h] BYREF
  char v139[24]; // [rsp+1E0h] [rbp-168h] BYREF
  _BYTE v140[16]; // [rsp+200h] [rbp-148h] BYREF
  _BYTE v141[16]; // [rsp+210h] [rbp-138h] BYREF
  int *v142; // [rsp+220h] [rbp-128h]
  __int64 v143; // [rsp+228h] [rbp-120h]
  int *v144; // [rsp+230h] [rbp-118h]
  __int64 v145; // [rsp+238h] [rbp-110h]
  __int64 v146; // [rsp+240h] [rbp-108h]
  __int64 v147; // [rsp+248h] [rbp-100h]
  int *v148; // [rsp+250h] [rbp-F8h]
  __int64 v149; // [rsp+258h] [rbp-F0h]
  __int64 v150; // [rsp+260h] [rbp-E8h]
  int v151; // [rsp+268h] [rbp-E0h] BYREF
  int v152; // [rsp+26Ch] [rbp-DCh]
  unsigned __int64 *v153; // [rsp+270h] [rbp-D8h]
  __int64 v154; // [rsp+278h] [rbp-D0h]
  unsigned __int64 *v155; // [rsp+280h] [rbp-C8h]
  __int64 v156; // [rsp+288h] [rbp-C0h]
  unsigned __int64 *v157; // [rsp+290h] [rbp-B8h]
  __int64 v158; // [rsp+298h] [rbp-B0h]
  unsigned __int64 *v159; // [rsp+2A0h] [rbp-A8h]
  __int64 v160; // [rsp+2A8h] [rbp-A0h]
  unsigned __int64 *v161; // [rsp+2B0h] [rbp-98h]
  __int64 v162; // [rsp+2B8h] [rbp-90h]
  char v163[64]; // [rsp+2C0h] [rbp-88h] BYREF

  v111 = a3;
  v108 = a2;
  v109 = a1;
  v127[1] = a1;
  v101 = a2;
  v99 = a3;
  v96 = a4;
  v128 = a8;
  v9 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  v121 = 0;
  v103 = 0;
  v124 = 0;
  v132 = 0;
  v116 = 0;
  v133 = 0;
  v134 = 0;
  LODWORD(v135) = 0;
  v97 = 0;
  v113 = -1;
  MemoryDescriptorList = 0;
  v107 = (__int64 *)(a1 + 8);
  v10 = *(_QWORD *)(a1 + 8);
  *(double *)&v9 = VsmmHostAccessMinimumForMemoryBlock();
  v94 = v14;
  v137 = v9;
  v136 = v10;
  if ( a6 > 0xFFFFFFFF )
  {
    KnownZeroVaPages = -1073741637;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_113;
    tlgCreate1Sz_char(v140, "VsmmpWriteMemoryBlockByteRange");
    tlgCreate1Sz_char(v141, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    v94 = 2345;
    v142 = &v94;
    v143 = 4;
    v96 = -1073741637;
    v144 = &v96;
    v145 = 4;
    v17 = *v16;
    v146 = *v16 + 656;
    v147 = 16;
    v18 = *(unsigned __int16 *)(v17 + 120);
    v19 = *(_QWORD *)(v17 + 128);
    v148 = &v151;
    v149 = 2;
    v150 = v19;
    v151 = v18;
    v152 = 0;
    v20 = *(_QWORD *)(v17 + 648);
    v21 = byte_140055EE9;
LABEL_5:
    v98 = v20;
    v153 = &v98;
    v99 = a6;
    v155 = &v99;
    v93 = 11;
LABEL_6:
    v156 = 8;
LABEL_7:
    v154 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v21, 0, 0, v93, v139);
    goto LABEL_113;
  }
  v126 = (_DWORD *)(v12 + 20);
  if ( (*(_DWORD *)(v12 + 20) & 8) == 0 || PsGetCurrentProcess() == *(_QWORD *)(v10 + 10328) )
  {
    v121 = a5;
    v25 = a7;
    v95 = a7;
  }
  else
  {
    KnownZeroVaPages = VsmmpMapUserBufferToSystem(a5, a6, &MemoryDescriptorList, IoReadAccess, &v121);
    if ( KnownZeroVaPages < 0 )
    {
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_113;
      tlgCreate1Sz_char(v140, "VsmmpWriteMemoryBlockByteRange");
      tlgCreate1Sz_char(v141, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
      v94 = 2374;
      v142 = &v94;
      v143 = 4;
      v96 = KnownZeroVaPages;
      v144 = &v96;
      v145 = 4;
      v22 = *v107;
      v146 = *v107 + 656;
      v147 = 16;
      v23 = *(unsigned __int16 *)(v22 + 120);
      v24 = *(_QWORD *)(v22 + 128);
      v148 = &v151;
      v149 = 2;
      v150 = v24;
      v151 = v23;
      v152 = 0;
      v20 = *(_QWORD *)(v22 + 648);
      v21 = byte_140055F63;
      goto LABEL_5;
    }
    v25 = 0;
    v95 = 0;
    KeStackAttachProcess(*(PRKPROCESS *)(v10 + 10328), &ApcState);
    v97 = 1;
  }
  if ( ((a4 >> 2) & 3) != 0 )
  {
    if ( !MemoryDescriptorList && v25 )
    {
      KnownZeroVaPages = VsmmpMapUserBufferToSystem(a5, a6, &MemoryDescriptorList, IoReadAccess, &v121);
      if ( KnownZeroVaPages < 0 )
      {
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_113;
        tlgCreate1Sz_char(v140, "VsmmpWriteMemoryBlockByteRange");
        tlgCreate1Sz_char(v141, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
        v94 = 2415;
        v142 = &v94;
        v143 = 4;
        v96 = KnownZeroVaPages;
        v144 = &v96;
        v145 = 4;
        v26 = *v107;
        v146 = *v107 + 656;
        v147 = 16;
        v27 = *(unsigned __int16 *)(v26 + 120);
        v28 = *(_QWORD *)(v26 + 128);
        v148 = &v151;
        v149 = 2;
        v150 = v28;
        v151 = v27;
        v152 = 0;
        v20 = *(_QWORD *)(v26 + 648);
        v21 = &byte_140055C47;
        goto LABEL_5;
      }
      v95 = 0;
    }
    DWORD1(v133) = 0;
    DWORD1(v134) = 0;
    v135 = 0;
    LODWORD(v133) = VsmmCompressionFormatToVmCompress((a4 >> 2) & 3, v11);
    *((_QWORD *)&v133 + 1) = v121;
    LODWORD(v134) = a6;
    *((_QWORD *)&v134 + 1) = 0;
  }
  v102 = v126;
  v131 = a4;
  v105 = a4;
  v118 = a4;
  v119 = v94;
  LOBYTE(v11) = 1;
  v29 = VsmmpConvertMbpRwFlagsToMbpLockFlags(a4, v11, v13, v126);
  v110 = v29;
  v32 = v108;
  v114 = v108;
  v33 = v108 + v111;
  v98 = v108 + v111;
  v34 = v108 >> 12;
  v123 = v108 >> 12;
  while ( 1 )
  {
    if ( v32 >= v33 )
    {
      KnownZeroVaPages = 0;
      goto LABEL_113;
    }
    if ( (*v30 & 8) != 0 && (v31 & 0xC) != 0 )
    {
      KnownZeroVaPages = VmCompressParseNextRange(&v133, &v116, &v103);
      v115 = KnownZeroVaPages;
      if ( KnownZeroVaPages < 0 )
      {
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v140, "VsmmpWriteMemoryBlockByteRange");
          tlgCreate1Sz_char(v141, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
          v94 = 2473;
          v142 = &v94;
          v143 = 4;
          v96 = KnownZeroVaPages;
          v144 = &v96;
          v145 = 4;
          v35 = *v107;
          v146 = *v107 + 656;
          v147 = 16;
          v36 = *(unsigned __int16 *)(v35 + 120);
          v37 = *(_QWORD *)(v35 + 128);
          v148 = &v151;
          v149 = 2;
          v150 = v37;
          v151 = v36;
          v152 = 0;
          v98 = *(_QWORD *)(v35 + 648);
          v153 = &v98;
          v99 = v38;
          v155 = &v99;
          v101 = v111;
          v157 = &v101;
          v158 = 8;
          v102 = (_DWORD *)v32;
          v159 = (unsigned __int64 *)&v102;
          v160 = 8;
          v93 = 13;
          v21 = byte_140055CC1;
          goto LABEL_6;
        }
        goto LABEL_113;
      }
      if ( !v103 )
      {
        KnownZeroVaPages = -1073741811;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v140, "VsmmpWriteMemoryBlockByteRange");
          tlgCreate1Sz_char(v141, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
          v94 = 2490;
          v142 = &v94;
          v143 = 4;
          v96 = v39;
          v144 = &v96;
          v145 = 4;
          v40 = *v107;
          v146 = *v107 + 656;
          v147 = 16;
          v41 = *(unsigned __int16 *)(v40 + 120);
          v42 = *(_QWORD *)(v40 + 128);
          v148 = &v151;
          v149 = 2;
          v150 = v42;
          v151 = v41;
          v152 = 0;
          v98 = *(_QWORD *)(v40 + 648);
          v153 = &v98;
          v99 = v43;
          v155 = &v99;
          v101 = v111;
          v157 = &v101;
          v158 = 8;
          v102 = (_DWORD *)v32;
          v159 = (unsigned __int64 *)&v102;
          v160 = 8;
          v93 = 13;
          v21 = &byte_140055D67;
          goto LABEL_6;
        }
        goto LABEL_113;
      }
      v44 = v32 + v116;
      v45 = -1;
      if ( v44 >= v32 )
        v45 = v32 + v116;
      v112 = v45;
      KnownZeroVaPages = v44 < v32 ? 0xC0000095 : 0;
      if ( v44 < v32 )
      {
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v140, "VsmmpWriteMemoryBlockByteRange");
          tlgCreate1Sz_char(v141, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
          v94 = 2511;
          v142 = &v94;
          v143 = 4;
          v96 = KnownZeroVaPages;
          v144 = &v96;
          v145 = 4;
          v46 = *v107;
          v146 = *v107 + 656;
          v147 = 16;
          v47 = *(unsigned __int16 *)(v46 + 120);
          v48 = *(_QWORD *)(v46 + 128);
          v148 = &v151;
          v149 = 2;
          v150 = v48;
          v151 = v47;
          v152 = 0;
          v98 = *(_QWORD *)(v46 + 648);
          v153 = &v98;
          v99 = v108;
          v155 = &v99;
          v101 = v111;
          v157 = &v101;
          v158 = 8;
          v102 = (_DWORD *)v32;
          v159 = (unsigned __int64 *)&v102;
          v160 = 8;
          v110 = v49;
          v161 = (unsigned __int64 *)&v110;
          v162 = 4;
          v93 = 14;
          v21 = &byte_140055A3F;
          goto LABEL_6;
        }
        goto LABEL_113;
      }
      if ( v45 > v98 )
      {
        KnownZeroVaPages = -1073741811;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v140, "VsmmpWriteMemoryBlockByteRange");
          tlgCreate1Sz_char(v141, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
          v94 = 2526;
          v142 = &v94;
          v143 = 4;
          v96 = v50;
          v144 = &v96;
          v145 = 4;
          v51 = *v107;
          v146 = *v107 + 656;
          v147 = 16;
          v52 = *(unsigned __int16 *)(v51 + 120);
          v53 = *(_QWORD *)(v51 + 128);
          v148 = &v151;
          v149 = 2;
          v150 = v53;
          v151 = v52;
          v152 = 0;
          v98 = *(_QWORD *)(v51 + 648);
          v153 = &v98;
          v99 = v108;
          v155 = &v99;
          v101 = v111;
          v157 = &v101;
          v158 = 8;
          v102 = (_DWORD *)v32;
          v159 = (unsigned __int64 *)&v102;
          v160 = 8;
          v122 = v54;
          v161 = &v122;
          v162 = 8;
          v93 = 14;
          v21 = (char *)&dword_140055AFC;
          goto LABEL_6;
        }
        goto LABEL_113;
      }
    }
    else
    {
      v45 = v33;
      v112 = v33;
      v103 = 0;
    }
    v55 = v105 & 0xC;
    v100 = v55;
    v120 = v55;
LABEL_49:
    if ( v32 < v45 )
      break;
    v33 = v98;
    v30 = v126;
    v31 = v131;
  }
  v56 = v34 & 0x1FF;
  v57 = v45 - v32;
  if ( v45 - v32 >= (512 - v56) << 12 )
    v57 = (512 - v56) << 12;
  v106 = (v57 + 4095 + (v32 & 0xFFF)) >> 12;
  RtlInitializeBitMapEx(&v132, v163, v106);
  RtlClearAllBitsEx(&v132);
  if ( (*v126 & 8) == 0 || (a4 & 3) != 0 || v55 && v103 == 2 || (*v126 & 0x10000) != 0 )
  {
    v64 = v100;
    goto LABEL_73;
  }
  KnownZeroVaPages = VsmmQueryKnownZeroVaPages(*(PRKPROCESS *)(*v107 + 10328));
  if ( KnownZeroVaPages >= 0 )
  {
    v64 = v100;
    if ( !v100 )
    {
      for ( i = 0; ; ++i )
      {
        v125 = i;
        v66 = v106;
        if ( i >= v106 )
          break;
        if ( (unsigned __int8)RtlTestBitEx(&v132, i) )
        {
          v67 = (i + v34) << 12;
          v68 = v32;
          if ( v67 > v32 )
            v68 = (i + v34) << 12;
          v69 = v67 + 4096;
          v70 = v112;
          if ( v69 < v112 )
            v70 = v69;
          v122 = v70 - v68;
          v71 = RtlCompareMemoryUlong(&v121[v68 - v108], v70 - v68, 0);
          if ( v71 != v122 )
            RtlClearBitEx(&v132, i);
        }
      }
      v64 = v100;
LABEL_74:
      v72 = 0;
      v117 = v64;
      v104 = v64;
      while ( 1 )
      {
        v125 = v72;
        if ( v72 >= v66 )
        {
LABEL_109:
          v45 = v112;
          v55 = v100;
          if ( v113 != -1 )
          {
            VidPushLockRelease(*(_QWORD *)(v109 + 328) + 8 * v113, NextForwardRunClear, v59, v60);
            v113 = -1;
            v45 = v112;
          }
          goto LABEL_49;
        }
        NextForwardRunClear = RtlFindNextForwardRunClearEx(&v132, v72, &v124);
        v130 = NextForwardRunClear;
        if ( NextForwardRunClear )
        {
          v74 = v104;
          v73 = v124;
        }
        else
        {
          v73 = v106;
          v124 = v106;
          v74 = v117;
        }
        v122 = v73;
        v94 = v74;
        v104 = v74;
        if ( v73 > v72 && v74 )
        {
          v75 = (v34 + v73 - v72) << 12;
          if ( v112 < v75 )
            LODWORD(v75) = v112;
          v127[0] = (unsigned int)(v75 - v32);
          LODWORD(v114) = v75 - v32;
          KnownZeroVaPages = VmCompressUnpackExSkipBytes(&v133, LODWORD(v127[0]));
          v115 = KnownZeroVaPages;
          v73 = v122;
          v60 = v127[0];
          if ( KnownZeroVaPages < 0 )
          {
            if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
            {
              tlgCreate1Sz_char(v140, "VsmmpWriteMemoryBlockByteRange");
              tlgCreate1Sz_char(v141, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
              LODWORD(v114) = 2753;
              v142 = (int *)&v114;
              v143 = 4;
              v120 = KnownZeroVaPages;
              v144 = &v120;
              v145 = 4;
              v76 = *v107;
              v146 = *v107 + 656;
              v147 = 16;
              v77 = *(unsigned __int16 *)(v76 + 120);
              v78 = *(_QWORD *)(v76 + 128);
              v148 = &v151;
              v149 = 2;
              v150 = v78;
              v151 = v77;
              v152 = 0;
              v127[0] = *(_QWORD *)(v76 + 648);
              v153 = v127;
              v117 = v79;
              v155 = (unsigned __int64 *)&v117;
              v156 = 4;
              v93 = 11;
              v21 = byte_1400558FB;
              goto LABEL_7;
            }
            goto LABEL_113;
          }
          v72 = v125;
          NextForwardRunClear = v130;
        }
        v34 += v73 - v72;
        v123 = v34;
        v32 = v34 << 12;
        v59 = v108;
        v80 = v112;
        if ( v34 << 12 >= v108 )
        {
          if ( v32 > v112 )
            v32 = v112;
          v114 = v32;
        }
        else
        {
          v32 = v108;
          v114 = v108;
        }
        if ( !NextForwardRunClear )
          goto LABEL_109;
        if ( (a4 & 3) == 0 && v119 == 2 && v113 == -1 )
        {
          v113 = v34 >> 9;
          VidPushLockAcquireShared(*(_QWORD *)(v109 + 328) + 8 * (v34 >> 9));
          NextForwardRunClear = v130;
          v59 = v108;
        }
        v81 = (NextForwardRunClear + v34) << 12;
        if ( v80 < v81 )
          v81 = v80;
        v82 = v118 & 0x20;
        v83 = v81 - v32;
        v84 = v104
            ? VsmmMemoryBlockCopyByteRange(
                (unsigned int)&v136,
                v109,
                v32,
                v83,
                0,
                (__int64)&v133,
                v29,
                v82 != 0,
                v95,
                v128)
            : VsmmMemoryBlockCopyByteRange(
                (unsigned int)&v136,
                v109,
                v32,
                v83,
                (__int64)&v121[v32 - v59],
                0,
                v29,
                v82 != 0,
                v95,
                v128);
        KnownZeroVaPages = v84;
        if ( v84 < 0 )
          break;
        v32 = v81;
        v114 = v81;
        v34 = v81 >> 12;
        v123 = v34;
        v72 = v130 + v124;
        v66 = v106;
      }
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v140, "VsmmpWriteMemoryBlockByteRange");
        tlgCreate1Sz_char(v141, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
        v118 = 2857;
        v142 = &v118;
        v143 = 4;
        v119 = KnownZeroVaPages;
        v144 = &v119;
        v145 = 4;
        v85 = *v107;
        v146 = *v107 + 656;
        v147 = 16;
        v86 = *(unsigned __int16 *)(v85 + 120);
        v87 = *(_QWORD *)(v85 + 128);
        v148 = &v151;
        v149 = 2;
        v150 = v87;
        v151 = v86;
        v152 = 0;
        v127[0] = *(_QWORD *)(v85 + 648);
        v153 = v127;
        v98 = v108;
        v155 = &v98;
        v99 = v111;
        v157 = &v99;
        v158 = 8;
        v101 = v32;
        v159 = &v101;
        v160 = 8;
        v102 = (_DWORD *)v81;
        v161 = (unsigned __int64 *)&v102;
        v162 = 8;
        v93 = 14;
        v21 = (char *)&unk_140055980;
        goto LABEL_6;
      }
      goto LABEL_113;
    }
LABEL_73:
    v66 = v106;
    goto LABEL_74;
  }
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v140, "VsmmpWriteMemoryBlockByteRange");
    tlgCreate1Sz_char(v141, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    v105 = 2616;
    v142 = &v105;
    v143 = 4;
    v94 = KnownZeroVaPages;
    v144 = &v94;
    v145 = 4;
    v61 = *v107;
    v146 = *v107 + 656;
    v147 = 16;
    v62 = *(unsigned __int16 *)(v61 + 120);
    v63 = *(_QWORD *)(v61 + 128);
    v148 = &v151;
    v149 = 2;
    v150 = v63;
    v151 = v62;
    v152 = 0;
    v98 = *(_QWORD *)(v61 + 648);
    v153 = &v98;
    v99 = v34;
    v155 = &v99;
    v101 = v106;
    v157 = &v101;
    v158 = 8;
    v93 = 12;
    v21 = byte_140055BBD;
    goto LABEL_6;
  }
LABEL_113:
  VsmmMemoryBlockMbpRangeVaDestroy(&v136);
  if ( v113 != -1 )
    VidPushLockRelease(*(_QWORD *)(v109 + 328) + 8 * v113, v88, v89, v90);
  if ( v97 )
    KeUnstackDetachProcess(&ApcState);
  v91 = MemoryDescriptorList;
  if ( MemoryDescriptorList )
  {
    MmUnlockPages(MemoryDescriptorList);
    IoFreeMdl(v91);
  }
  return (unsigned int)KnownZeroVaPages;
}

```

## disassembly

```asm
0x14000d75c  push    rbx
0x14000d75e  push    rsi
0x14000d75f  push    rdi
0x14000d760  push    r12
0x14000d762  push    r13
0x14000d764  push    r14
0x14000d766  push    r15
0x14000d768  sub     rsp, 310h
0x14000d76f  mov     rax, cs:__security_cookie
0x14000d776  xor     rax, rsp
0x14000d779  mov     [rsp+348h+var_48], rax
0x14000d781  mov     ebx, r9d
0x14000d784  mov     [rsp+348h+var_280], r8
0x14000d78c  mov     [rsp+348h+var_298], rdx
0x14000d794  mov     [rsp+348h+var_290], rcx
0x14000d79c  mov     [rsp+348h+var_210], rcx
0x14000d7a4  mov     [rsp+348h+var_2C8], rdx
0x14000d7ac  mov     [rsp+348h+var_2D8], r8
0x14000d7b1  mov     [rsp+348h+var_2F0], ebx
0x14000d7b5  mov     r13, [rsp+348h+arg_20]
0x14000d7bd  mov     rax, [rsp+348h+arg_38]
0x14000d7c5  mov     [rsp+348h+var_208], rax
0x14000d7cd  xorps   xmm0, xmm0
0x14000d7d0  movups  xmmword ptr [rsp+348h+ApcState.ApcListHead.Flink], xmm0
0x14000d7d8  movups  xmmword ptr [rsp+348h+ApcState.ApcListHead.Flink+10h], xmm0
0x14000d7e0  movups  xmmword ptr [rsp+348h+ApcState.Process], xmm0
0x14000d7e8  xor     esi, esi
0x14000d7ea  mov     [rsp+348h+var_248], rsi
0x14000d7f2  mov     [rsp+348h+var_2B8], esi
0x14000d7f9  mov     [rsp+348h+var_230], rsi
0x14000d801  movups  [rsp+348h+var_1E8], xmm0
0x14000d809  mov     [rsp+348h+var_25C], esi
0x14000d810  xor     eax, eax
0x14000d812  movups  [rsp+348h+var_1D8], xmm0
0x14000d81a  movups  [rsp+348h+var_1C8], xmm0
0x14000d822  mov     dword ptr [rsp+348h+var_1B8], eax
0x14000d829  mov     [rsp+348h+var_2E8], sil
0x14000d82e  mov     [rsp+348h+var_270], 0FFFFFFFFFFFFFFFFh
0x14000d83a  mov     [rsp+348h+MemoryDescriptorList], rsi
0x14000d842  lea     r9, [rcx+8]
0x14000d846  mov     [rsp+348h+var_2A0], r9
0x14000d84e  mov     rdi, [r9]
0x14000d851  call    VsmmHostAccessMinimumForMemoryBlock
0x14000d856  mov     [rsp+348h+var_2F8], eax
0x14000d85a  movdqu  [rsp+348h+var_1A8], xmm0
0x14000d863  mov     [rsp+348h+var_1B0], rdi
0x14000d86b  mov     eax, 0FFFFFFFFh
0x14000d870  mov     r12, [rsp+348h+arg_28]
0x14000d878  cmp     r12, rax
0x14000d87b  jbe     loc_14000D9E7
0x14000d881  mov     r14d, 0C00000BBh
0x14000d887  mov     eax, cs:dword_140064110
0x14000d88d  lea     r15d, [rsi+2]
0x14000d891  cmp     eax, r15d
0x14000d894  jbe     loc_14000F17C
0x14000d89a  mov     edx, 100h
0x14000d89f  lea     rcx, dword_140064110
0x14000d8a6  call    _tlgKeywordOn
0x14000d8ab  test    al, al
0x14000d8ad  jz      loc_14000F17C
0x14000d8b3  lea     rdx, aVsmmpwritememo; "VsmmpWriteMemoryBlockByteRange"
0x14000d8ba  lea     rcx, [rsp+348h+var_148]
0x14000d8c2  call    _tlgCreate1Sz_char
0x14000d8c7  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000d8ce  lea     rcx, [rsp+348h+var_138]
0x14000d8d6  call    _tlgCreate1Sz_char
0x14000d8db  mov     [rsp+348h+var_2F8], 929h
0x14000d8e3  lea     rax, [rsp+348h+var_2F8]
0x14000d8e8  mov     [rsp+348h+var_128], rax
0x14000d8f0  mov     [rsp+348h+var_120], 4
0x14000d8fc  mov     [rsp+348h+var_2F0], r14d
0x14000d901  lea     rax, [rsp+348h+var_2F0]
0x14000d906  mov     [rsp+348h+var_118], rax
0x14000d90e  mov     [rsp+348h+var_110], 4
0x14000d91a  mov     rdx, [r9]
0x14000d91d  lea     rax, [rdx+290h]
0x14000d924  mov     [rsp+348h+var_108], rax
0x14000d92c  mov     [rsp+348h+var_100], 10h
0x14000d938  movzx   ecx, word ptr [rdx+78h]
0x14000d93c  mov     rax, [rdx+80h]
0x14000d943  lea     r8, [rsp+348h+var_E0]
0x14000d94b  mov     [rsp+348h+var_F8], r8
0x14000d953  mov     [rsp+348h+var_F0], r15
0x14000d95b  mov     [rsp+348h+var_E8], rax
0x14000d963  mov     [rsp+348h+var_E0], ecx
0x14000d96a  mov     [rsp+348h+var_DC], esi
0x14000d971  mov     rax, [rdx+288h]
0x14000d978  lea     rdx, byte_140055EE9
0x14000d97f  mov     [rsp+348h+var_2E0], rax
0x14000d984  lea     rax, [rsp+348h+var_2E0]
0x14000d989  mov     [rsp+348h+var_D8], rax
0x14000d991  lea     rax, [rsp+348h+var_168]
0x14000d999  lea     rcx, [rsp+348h+var_2D8]
0x14000d99e  mov     [rsp+348h+var_320], rax
0x14000d9a3  mov     [rsp+348h+var_2D8], r12
0x14000d9a8  mov     [rsp+348h+var_C8], rcx
0x14000d9b0  mov     dword ptr [rsp+348h+var_328], 0Bh
0x14000d9b8  mov     [rsp+348h+var_C0], 8
0x14000d9c4  xor     r9d, r9d
0x14000d9c7  xor     r8d, r8d
0x14000d9ca  mov     [rsp+348h+var_D0], 8
0x14000d9d6  lea     rcx, dword_140064110
0x14000d9dd  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d9e2  jmp     loc_14000F17C
0x14000d9e7  lea     rax, [rcx+14h]
0x14000d9eb  mov     [rsp+348h+var_220], rax
0x14000d9f3  mov     eax, [rax]
0x14000d9f5  test    al, 8
0x14000d9f7  jz      loc_14000DB75
0x14000d9fd  call    cs:__imp_PsGetCurrentProcess
0x14000da04  nop     dword ptr [rax+rax+00h]
0x14000da09  cmp     rax, [rdi+2858h]
0x14000da10  jz      loc_14000DB75
0x14000da16  lea     rax, [rsp+348h+var_248]
0x14000da1e  mov     [rsp+348h+var_328], rax
0x14000da23  xor     r9d, r9d
0x14000da26  lea     r8, [rsp+348h+MemoryDescriptorList]
0x14000da2e  mov     edx, r12d
0x14000da31  mov     rcx, r13
0x14000da34  call    VsmmpMapUserBufferToSystem
0x14000da39  mov     r14d, eax
0x14000da3c  test    eax, eax
0x14000da3e  jns     loc_14000DB4B
0x14000da44  mov     ecx, cs:dword_140064110
0x14000da4a  mov     r15d, 2
0x14000da50  cmp     ecx, r15d
0x14000da53  jbe     loc_14000F17C
0x14000da59  mov     edx, 100h
0x14000da5e  lea     rcx, dword_140064110
0x14000da65  call    _tlgKeywordOn
0x14000da6a  test    al, al
0x14000da6c  jz      loc_14000F17C
0x14000da72  lea     rdx, aVsmmpwritememo; "VsmmpWriteMemoryBlockByteRange"
0x14000da79  lea     rcx, [rsp+348h+var_148]
0x14000da81  call    _tlgCreate1Sz_char
0x14000da86  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000da8d  lea     rcx, [rsp+348h+var_138]
0x14000da95  call    _tlgCreate1Sz_char
0x14000da9a  mov     [rsp+348h+var_2F8], 946h
0x14000daa2  lea     rax, [rsp+348h+var_2F8]
0x14000daa7  mov     [rsp+348h+var_128], rax
0x14000daaf  mov     [rsp+348h+var_120], 4
0x14000dabb  mov     [rsp+348h+var_2F0], r14d
0x14000dac0  lea     rax, [rsp+348h+var_2F0]
0x14000dac5  mov     [rsp+348h+var_118], rax
0x14000dacd  mov     [rsp+348h+var_110], 4
0x14000dad9  mov     rcx, [rsp+348h+var_2A0]
0x14000dae1  mov     rdx, [rcx]
0x14000dae4  lea     rax, [rdx+290h]
0x14000daeb  mov     [rsp+348h+var_108], rax
0x14000daf3  mov     [rsp+348h+var_100], 10h
0x14000daff  movzx   ecx, word ptr [rdx+78h]
0x14000db03  mov     rax, [rdx+80h]
0x14000db0a  lea     r8, [rsp+348h+var_E0]
0x14000db12  mov     [rsp+348h+var_F8], r8
0x14000db1a  mov     [rsp+348h+var_F0], r15
0x14000db22  mov     [rsp+348h+var_E8], rax
0x14000db2a  mov     [rsp+348h+var_E0], ecx
0x14000db31  mov     [rsp+348h+var_DC], esi
0x14000db38  mov     rax, [rdx+288h]
0x14000db3f  lea     rdx, byte_140055F63
0x14000db46  jmp     loc_14000D97F
0x14000db4b  mov     r14b, sil
0x14000db4e  mov     [rsp+348h+var_2F4], sil
0x14000db53  lea     rdx, [rsp+348h+ApcState]; ApcState
0x14000db5b  mov     rcx, [rdi+2858h]; PROCESS
0x14000db62  call    cs:__imp_KeStackAttachProcess
0x14000db69  nop     dword ptr [rax+rax+00h]
0x14000db6e  mov     [rsp+348h+var_2E8], 1
0x14000db73  jmp     short loc_14000DB8A
0x14000db75  mov     [rsp+348h+var_248], r13
0x14000db7d  mov     r14b, [rsp+348h+arg_30]
0x14000db85  mov     [rsp+348h+var_2F4], r14b
0x14000db8a  mov     r15d, r12d
0x14000db8d  mov     edi, ebx
0x14000db8f  shr     edi, 2
0x14000db92  and     edi, 3
0x14000db95  jz      loc_14000DD30
0x14000db9b  cmp     [rsp+348h+MemoryDescriptorList], rsi
0x14000dba3  jnz     loc_14000DCEC
0x14000dba9  test    r14b, r14b
0x14000dbac  jz      loc_14000DCEC
0x14000dbb2  lea     rax, [rsp+348h+var_248]
0x14000dbba  mov     [rsp+348h+var_328], rax
0x14000dbbf  xor     r9d, r9d
0x14000dbc2  lea     r8, [rsp+348h+MemoryDescriptorList]
0x14000dbca  mov     edx, r12d
0x14000dbcd  mov     rcx, r13
0x14000dbd0  call    VsmmpMapUserBufferToSystem
0x14000dbd5  mov     r14d, eax
0x14000dbd8  test    eax, eax
0x14000dbda  jns     loc_14000DCE7
0x14000dbe0  mov     eax, cs:dword_140064110
0x14000dbe6  mov     r15d, 2
0x14000dbec  cmp     eax, r15d
0x14000dbef  jbe     loc_14000F17C
0x14000dbf5  mov     edx, 100h
0x14000dbfa  lea     rcx, dword_140064110
0x14000dc01  call    _tlgKeywordOn
0x14000dc06  test    al, al
0x14000dc08  jz      loc_14000F17C
0x14000dc0e  lea     rdx, aVsmmpwritememo; "VsmmpWriteMemoryBlockByteRange"
0x14000dc15  lea     rcx, [rsp+348h+var_148]
0x14000dc1d  call    _tlgCreate1Sz_char
0x14000dc22  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000dc29  lea     rcx, [rsp+348h+var_138]
0x14000dc31  call    _tlgCreate1Sz_char
0x14000dc36  mov     [rsp+348h+var_2F8], 96Fh
0x14000dc3e  lea     rax, [rsp+348h+var_2F8]
0x14000dc43  mov     [rsp+348h+var_128], rax
0x14000dc4b  mov     [rsp+348h+var_120], 4
0x14000dc57  mov     [rsp+348h+var_2F0], r14d
0x14000dc5c  lea     rax, [rsp+348h+var_2F0]
0x14000dc61  mov     [rsp+348h+var_118], rax
0x14000dc69  mov     [rsp+348h+var_110], 4
0x14000dc75  mov     rcx, [rsp+348h+var_2A0]
0x14000dc7d  mov     rdx, [rcx]
0x14000dc80  lea     rax, [rdx+290h]
0x14000dc87  mov     [rsp+348h+var_108], rax
0x14000dc8f  mov     [rsp+348h+var_100], 10h
0x14000dc9b  movzx   ecx, word ptr [rdx+78h]
0x14000dc9f  mov     rax, [rdx+80h]
0x14000dca6  lea     r8, [rsp+348h+var_E0]
0x14000dcae  mov     [rsp+348h+var_F8], r8
0x14000dcb6  mov     [rsp+348h+var_F0], r15
0x14000dcbe  mov     [rsp+348h+var_E8], rax
0x14000dcc6  mov     [rsp+348h+var_E0], ecx
0x14000dccd  mov     [rsp+348h+var_DC], esi
0x14000dcd4  mov     rax, [rdx+288h]
0x14000dcdb  lea     rdx, byte_140055C47
0x14000dce2  jmp     loc_14000D97F
0x14000dce7  mov     [rsp+348h+var_2F4], sil
0x14000dcec  mov     dword ptr [rsp+348h+var_1D8+4], esi
0x14000dcf3  mov     dword ptr [rsp+348h+var_1C8+4], esi
0x14000dcfa  mov     [rsp+348h+var_1B8], rsi
0x14000dd02  mov     ecx, edi
0x14000dd04  call    VsmmCompressionFormatToVmCompress
0x14000dd09  mov     dword ptr [rsp+348h+var_1D8], eax
0x14000dd10  mov     rax, [rsp+348h+var_248]
0x14000dd18  mov     qword ptr [rsp+348h+var_1D8+8], rax
0x14000dd20  mov     dword ptr [rsp+348h+var_1C8], r15d
0x14000dd28  mov     qword ptr [rsp+348h+var_1C8+8], rsi
0x14000dd30  mov     r9, [rsp+348h+var_220]
0x14000dd38  mov     [rsp+348h+var_2C0], r9
0x14000dd40  mov     r10d, ebx
0x14000dd43  mov     [rsp+348h+var_1F0], ebx
0x14000dd4a  mov     [rsp+348h+var_2B0], ebx
0x14000dd51  mov     [rsp+348h+var_254], ebx
0x14000dd58  mov     eax, [rsp+348h+var_2F8]
0x14000dd5c  mov     [rsp+348h+var_250], eax
0x14000dd63  mov     dl, 1
0x14000dd65  mov     ecx, ebx
0x14000dd67  call    VsmmpConvertMbpRwFlagsToMbpLockFlags
0x14000dd6c  mov     edi, eax
0x14000dd6e  mov     [rsp+348h+var_288], eax
0x14000dd75  mov     r8, [rsp+348h+var_298]
0x14000dd7d  mov     r12, r8
0x14000dd80  mov     [rsp+348h+var_268], r8
0x14000dd88  mov     rcx, [rsp+348h+var_280]
0x14000dd90  add     rcx, r8
0x14000dd93  mov     [rsp+348h+var_2E0], rcx
0x14000dd98  mov     r13, r8
0x14000dd9b  shr     r13, 0Ch
0x14000dd9f  mov     [rsp+348h+var_238], r13
0x14000dda7  mov     r15d, 2
0x14000ddad  cmp     r12, rcx
0x14000ddb0  jnb     loc_14000F179
0x14000ddb6  mov     eax, [r9]
0x14000ddb9  test    al, 8
0x14000ddbb  jz      loc_14000E571
0x14000ddc1  test    r10b, 0Ch
0x14000ddc5  jz      loc_14000E571
0x14000ddcb  lea     r8, [rsp+348h+var_2B8]
0x14000ddd3  lea     rdx, [rsp+348h+var_25C]
0x14000dddb  lea     rcx, [rsp+348h+var_1D8]
0x14000dde3  call    VmCompressParseNextRange
0x14000dde8  mov     r14d, eax
0x14000ddeb  mov     [rsp+348h+var_260], eax
0x14000ddf2  mov     r9d, [rsp+348h+var_25C]
0x14000ddfa  mov     edx, [rsp+348h+var_2B8]
0x14000de01  mov     r10, [rsp+348h+var_298]
0x14000de09  jmp     short loc_14000DE87
0x14000de0b  mov     r14d, eax
0x14000de0e  mov     [rsp+348h+var_260], eax
0x14000de15  xor     r9d, r9d
0x14000de18  mov     [rsp+348h+var_25C], r9d
0x14000de20  xor     edx, edx
0x14000de22  mov     [rsp+348h+var_2B8], edx
0x14000de29  xor     esi, esi
0x14000de2b  lea     r15d, [r9+2]
0x14000de2f  mov     r13, [rsp+348h+var_238]
0x14000de37  mov     r12, [rsp+348h+var_268]
0x14000de3f  mov     edi, [rsp+348h+var_288]
0x14000de46  mov     rax, [rsp+348h+var_2C0]
0x14000de4e  mov     [rsp+348h+var_220], rax
0x14000de56  mov     rax, [rsp+348h+var_210]
0x14000de5e  mov     [rsp+348h+var_290], rax
0x14000de66  mov     r10, [rsp+348h+var_2C8]
0x14000de6e  mov     [rsp+348h+var_298], r10
0x14000de76  mov     rax, [rsp+348h+var_2D8]
  ... truncated ...
```
