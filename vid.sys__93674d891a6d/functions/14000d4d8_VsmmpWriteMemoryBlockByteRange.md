# VsmmpWriteMemoryBlockByteRange

- ea: `0x14000d4d8`
- end: `0x14000ef9a`
- name: `VsmmpWriteMemoryBlockByteRange`
- size: `6850`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, unsigned __int64, unsigned int, __int64, unsigned __int64, char, __int64)`
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14000aae0`
- `0x14001d140`
- `0x140029790`

## callees

- `0x1400029c0`
- `0x140006458`
- `0x1400065fc`
- `0x140006b68`
- `0x140007170`
- `0x1400071a4`
- `0x14000a010`
- `0x14000d4d8`
- `0x14000efa0`
- `0x140021c60`
- `0x1400d7c2c`
- `0x1400f51b8`
- `0x1400fb38c`
- `0x1400fc52c`
- `0x1400fd300`
- `0x1400fd760`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x14000ef3c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14000ef3c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000d77c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000d77c`
- `ntoskrnl!RtlCompareMemoryUlong` at `0x14000e618`
- `ntoskrnl!RtlCompareMemoryUlong` at `0x14000e618`
- `ntoskrnl!RtlFindNextForwardRunClearEx` at `0x14000e870`
- `ntoskrnl!RtlFindNextForwardRunClearEx` at `0x14000e870`
- `ntoskrnl!RtlClearBitEx` at `0x14000e639`
- `ntoskrnl!RtlClearBitEx` at `0x14000e639`
- `ntoskrnl!RtlTestBitEx` at `0x14000e5b9`
- `ntoskrnl!RtlTestBitEx` at `0x14000e5b9`
- `ntoskrnl!IoFreeMdl` at `0x14000ef67`
- `ntoskrnl!IoFreeMdl` at `0x14000ef67`
- `ntoskrnl!KeStackAttachProcess` at `0x14000d8e1`
- `ntoskrnl!KeStackAttachProcess` at `0x14000d8e1`
- `ntoskrnl!MmUnlockPages` at `0x14000ef58`
- `ntoskrnl!MmUnlockPages` at `0x14000ef58`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x14000e376`
- `ntoskrnl!RtlInitializeBitMapEx` at `0x14000e376`
- `ntoskrnl!RtlClearAllBitsEx` at `0x14000e38a`
- `ntoskrnl!RtlClearAllBitsEx` at `0x14000e38a`

## string_xrefs

- `0x14000d62f`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000d7f1`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000d98d`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000dc37`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000ddd6`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000df90`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000e15e`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000e43e`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000e675`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000e9f0`: `VsmmpWriteMemoryBlockByteRange`
- `0x14000ecbb`: `VsmmpWriteMemoryBlockByteRange`

## pseudocode

```c
__int64 __fastcall VsmmpWriteMemoryBlockByteRange(
        __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned int a4,
        __int64 a5,
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
  __int64 v58; // rdx
  int v59; // ecx
  __int64 v60; // rax
  int v61; // ecx
  unsigned __int64 i; // r14
  unsigned __int64 v63; // rax
  unsigned __int64 v64; // rax
  unsigned __int64 v65; // rdx
  unsigned __int64 v66; // rax
  unsigned __int64 v67; // r9
  SIZE_T v68; // rax
  unsigned __int64 v69; // r14
  __int64 NextForwardRunClear; // rdx
  unsigned __int64 v71; // rax
  int v72; // ecx
  unsigned __int64 v73; // rax
  __int64 v74; // rdx
  int v75; // ecx
  __int64 v76; // rax
  int v77; // r9d
  unsigned __int64 v78; // r8
  unsigned __int64 v79; // r14
  unsigned __int64 v80; // r13
  int v81; // eax
  int v82; // r9d
  int v83; // eax
  __int64 v84; // rdx
  int v85; // ecx
  __int64 v86; // rax
  struct _MDL *v87; // rbx
  int v89; // [rsp+20h] [rbp-328h]
  int v90; // [rsp+50h] [rbp-2F8h] BYREF
  char v91; // [rsp+54h] [rbp-2F4h]
  int v92; // [rsp+58h] [rbp-2F0h] BYREF
  char v93; // [rsp+60h] [rbp-2E8h]
  unsigned __int64 v94; // [rsp+68h] [rbp-2E0h] BYREF
  unsigned __int64 v95; // [rsp+70h] [rbp-2D8h] BYREF
  int v96; // [rsp+78h] [rbp-2D0h]
  unsigned __int64 v97; // [rsp+80h] [rbp-2C8h] BYREF
  _DWORD *v98; // [rsp+88h] [rbp-2C0h] BYREF
  int v99; // [rsp+90h] [rbp-2B8h] BYREF
  int v100; // [rsp+94h] [rbp-2B4h]
  int v101; // [rsp+98h] [rbp-2B0h] BYREF
  unsigned __int64 v102; // [rsp+A0h] [rbp-2A8h]
  __int64 *v103; // [rsp+A8h] [rbp-2A0h]
  unsigned __int64 v104; // [rsp+B0h] [rbp-298h]
  __int64 v105; // [rsp+B8h] [rbp-290h]
  int v106; // [rsp+C0h] [rbp-288h] BYREF
  unsigned __int64 v107; // [rsp+C8h] [rbp-280h]
  unsigned __int64 v108; // [rsp+D0h] [rbp-278h]
  __int64 v109; // [rsp+D8h] [rbp-270h]
  unsigned __int64 v110; // [rsp+E0h] [rbp-268h] BYREF
  signed int v111; // [rsp+E8h] [rbp-260h]
  unsigned int v112; // [rsp+ECh] [rbp-25Ch] BYREF
  int v113; // [rsp+F0h] [rbp-258h] BYREF
  int v114; // [rsp+F4h] [rbp-254h] BYREF
  int v115; // [rsp+F8h] [rbp-250h] BYREF
  int v116; // [rsp+FCh] [rbp-24Ch] BYREF
  __int64 v117; // [rsp+100h] [rbp-248h] BYREF
  unsigned __int64 v118; // [rsp+108h] [rbp-240h] BYREF
  unsigned __int64 v119; // [rsp+110h] [rbp-238h]
  unsigned __int64 v120; // [rsp+118h] [rbp-230h] BYREF
  unsigned __int64 v121; // [rsp+120h] [rbp-228h]
  _DWORD *v122; // [rsp+128h] [rbp-220h]
  _QWORD v123[2]; // [rsp+130h] [rbp-218h] BYREF
  __int64 v124; // [rsp+140h] [rbp-208h]
  PMDL MemoryDescriptorList; // [rsp+148h] [rbp-200h] BYREF
  __int64 v126; // [rsp+150h] [rbp-1F8h]
  unsigned int v127; // [rsp+158h] [rbp-1F0h]
  __int128 v128; // [rsp+160h] [rbp-1E8h] BYREF
  __int128 v129; // [rsp+170h] [rbp-1D8h] BYREF
  __int128 v130; // [rsp+180h] [rbp-1C8h]
  __int64 v131; // [rsp+190h] [rbp-1B8h]
  __int64 v132; // [rsp+198h] [rbp-1B0h] BYREF
  __int128 v133; // [rsp+1A0h] [rbp-1A8h]
  struct _KAPC_STATE ApcState; // [rsp+1B0h] [rbp-198h] BYREF
  char v135[24]; // [rsp+1E0h] [rbp-168h] BYREF
  _BYTE v136[16]; // [rsp+200h] [rbp-148h] BYREF
  _BYTE v137[16]; // [rsp+210h] [rbp-138h] BYREF
  int *v138; // [rsp+220h] [rbp-128h]
  __int64 v139; // [rsp+228h] [rbp-120h]
  int *v140; // [rsp+230h] [rbp-118h]
  __int64 v141; // [rsp+238h] [rbp-110h]
  __int64 v142; // [rsp+240h] [rbp-108h]
  __int64 v143; // [rsp+248h] [rbp-100h]
  int *v144; // [rsp+250h] [rbp-F8h]
  __int64 v145; // [rsp+258h] [rbp-F0h]
  __int64 v146; // [rsp+260h] [rbp-E8h]
  int v147; // [rsp+268h] [rbp-E0h] BYREF
  int v148; // [rsp+26Ch] [rbp-DCh]
  unsigned __int64 *v149; // [rsp+270h] [rbp-D8h]
  __int64 v150; // [rsp+278h] [rbp-D0h]
  unsigned __int64 *v151; // [rsp+280h] [rbp-C8h]
  __int64 v152; // [rsp+288h] [rbp-C0h]
  unsigned __int64 *v153; // [rsp+290h] [rbp-B8h]
  __int64 v154; // [rsp+298h] [rbp-B0h]
  unsigned __int64 *v155; // [rsp+2A0h] [rbp-A8h]
  __int64 v156; // [rsp+2A8h] [rbp-A0h]
  unsigned __int64 *v157; // [rsp+2B0h] [rbp-98h]
  __int64 v158; // [rsp+2B8h] [rbp-90h]
  char v159[64]; // [rsp+2C0h] [rbp-88h] BYREF

  v107 = a3;
  v104 = a2;
  v105 = a1;
  v123[1] = a1;
  v97 = a2;
  v95 = a3;
  v92 = a4;
  v124 = a8;
  v9 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  v117 = 0;
  v99 = 0;
  v120 = 0;
  v128 = 0;
  v112 = 0;
  v129 = 0;
  v130 = 0;
  LODWORD(v131) = 0;
  v93 = 0;
  v109 = -1;
  MemoryDescriptorList = 0;
  v103 = (__int64 *)(a1 + 8);
  v10 = *(_QWORD *)(a1 + 8);
  *(double *)&v9 = VsmmHostAccessMinimumForMemoryBlock();
  v90 = v14;
  v133 = v9;
  v132 = v10;
  if ( a6 > 0xFFFFFFFF )
  {
    KnownZeroVaPages = -1073741637;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_113;
    tlgCreate1Sz_char(v136, "VsmmpWriteMemoryBlockByteRange");
    tlgCreate1Sz_char(v137, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    v90 = 2345;
    v138 = &v90;
    v139 = 4;
    v92 = -1073741637;
    v140 = &v92;
    v141 = 4;
    v17 = *v16;
    v142 = *v16 + 656;
    v143 = 16;
    v18 = *(unsigned __int16 *)(v17 + 120);
    v19 = *(_QWORD *)(v17 + 128);
    v144 = &v147;
    v145 = 2;
    v146 = v19;
    v147 = v18;
    v148 = 0;
    v20 = *(_QWORD *)(v17 + 648);
    v21 = byte_14005658B;
LABEL_5:
    v94 = v20;
    v149 = &v94;
    v95 = a6;
    v151 = &v95;
    v89 = 11;
LABEL_6:
    v152 = 8;
LABEL_7:
    v150 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v21, 0, 0, v89, v135);
    goto LABEL_113;
  }
  v122 = (_DWORD *)(v12 + 264);
  if ( (*(_DWORD *)(v12 + 264) & 8) == 0 || PsGetCurrentProcess() == *(_QWORD *)(v10 + 10328) )
  {
    v117 = a5;
    v25 = a7;
    v91 = a7;
  }
  else
  {
    KnownZeroVaPages = VsmmpMapUserBufferToSystem(a5, (unsigned int)a6, &MemoryDescriptorList, 0, &v117);
    if ( KnownZeroVaPages < 0 )
    {
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_113;
      tlgCreate1Sz_char(v136, "VsmmpWriteMemoryBlockByteRange");
      tlgCreate1Sz_char(v137, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
      v90 = 2374;
      v138 = &v90;
      v139 = 4;
      v92 = KnownZeroVaPages;
      v140 = &v92;
      v141 = 4;
      v22 = *v103;
      v142 = *v103 + 656;
      v143 = 16;
      v23 = *(unsigned __int16 *)(v22 + 120);
      v24 = *(_QWORD *)(v22 + 128);
      v144 = &v147;
      v145 = 2;
      v146 = v24;
      v147 = v23;
      v148 = 0;
      v20 = *(_QWORD *)(v22 + 648);
      v21 = byte_140056605;
      goto LABEL_5;
    }
    v25 = 0;
    v91 = 0;
    KeStackAttachProcess(*(PRKPROCESS *)(v10 + 10328), &ApcState);
    v93 = 1;
  }
  if ( ((a4 >> 2) & 3) != 0 )
  {
    if ( !MemoryDescriptorList && v25 )
    {
      KnownZeroVaPages = VsmmpMapUserBufferToSystem(a5, (unsigned int)a6, &MemoryDescriptorList, 0, &v117);
      if ( KnownZeroVaPages < 0 )
      {
        if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          goto LABEL_113;
        tlgCreate1Sz_char(v136, "VsmmpWriteMemoryBlockByteRange");
        tlgCreate1Sz_char(v137, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
        v90 = 2415;
        v138 = &v90;
        v139 = 4;
        v92 = KnownZeroVaPages;
        v140 = &v92;
        v141 = 4;
        v26 = *v103;
        v142 = *v103 + 656;
        v143 = 16;
        v27 = *(unsigned __int16 *)(v26 + 120);
        v28 = *(_QWORD *)(v26 + 128);
        v144 = &v147;
        v145 = 2;
        v146 = v28;
        v147 = v27;
        v148 = 0;
        v20 = *(_QWORD *)(v26 + 648);
        v21 = byte_1400562E9;
        goto LABEL_5;
      }
      v91 = 0;
    }
    DWORD1(v129) = 0;
    DWORD1(v130) = 0;
    v131 = 0;
    LODWORD(v129) = VsmmCompressionFormatToVmCompress((a4 >> 2) & 3);
    *((_QWORD *)&v129 + 1) = v117;
    LODWORD(v130) = a6;
    *((_QWORD *)&v130 + 1) = 0;
  }
  v98 = v122;
  v127 = a4;
  v101 = a4;
  v114 = a4;
  v115 = v90;
  LOBYTE(v11) = 1;
  v29 = VsmmpConvertMbpRwFlagsToMbpLockFlags(a4, v11, v13, v122);
  v106 = v29;
  v32 = v104;
  v110 = v104;
  v33 = v104 + v107;
  v94 = v104 + v107;
  v34 = v104 >> 12;
  v119 = v104 >> 12;
  while ( 1 )
  {
    if ( v32 >= v33 )
    {
      KnownZeroVaPages = 0;
      goto LABEL_113;
    }
    if ( (*v30 & 8) != 0 && (v31 & 0xC) != 0 )
    {
      KnownZeroVaPages = VmCompressParseNextRange(&v129, &v112, &v99);
      v111 = KnownZeroVaPages;
      if ( KnownZeroVaPages < 0 )
      {
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v136, "VsmmpWriteMemoryBlockByteRange");
          tlgCreate1Sz_char(v137, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
          v90 = 2473;
          v138 = &v90;
          v139 = 4;
          v92 = KnownZeroVaPages;
          v140 = &v92;
          v141 = 4;
          v35 = *v103;
          v142 = *v103 + 656;
          v143 = 16;
          v36 = *(unsigned __int16 *)(v35 + 120);
          v37 = *(_QWORD *)(v35 + 128);
          v144 = &v147;
          v145 = 2;
          v146 = v37;
          v147 = v36;
          v148 = 0;
          v94 = *(_QWORD *)(v35 + 648);
          v149 = &v94;
          v95 = v38;
          v151 = &v95;
          v97 = v107;
          v153 = &v97;
          v154 = 8;
          v98 = (_DWORD *)v32;
          v155 = (unsigned __int64 *)&v98;
          v156 = 8;
          v89 = 13;
          v21 = byte_140056363;
          goto LABEL_6;
        }
        goto LABEL_113;
      }
      if ( !v99 )
      {
        KnownZeroVaPages = -1073741811;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v136, "VsmmpWriteMemoryBlockByteRange");
          tlgCreate1Sz_char(v137, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
          v90 = 2490;
          v138 = &v90;
          v139 = 4;
          v92 = v39;
          v140 = &v92;
          v141 = 4;
          v40 = *v103;
          v142 = *v103 + 656;
          v143 = 16;
          v41 = *(unsigned __int16 *)(v40 + 120);
          v42 = *(_QWORD *)(v40 + 128);
          v144 = &v147;
          v145 = 2;
          v146 = v42;
          v147 = v41;
          v148 = 0;
          v94 = *(_QWORD *)(v40 + 648);
          v149 = &v94;
          v95 = v43;
          v151 = &v95;
          v97 = v107;
          v153 = &v97;
          v154 = 8;
          v98 = (_DWORD *)v32;
          v155 = (unsigned __int64 *)&v98;
          v156 = 8;
          v89 = 13;
          v21 = byte_140056409;
          goto LABEL_6;
        }
        goto LABEL_113;
      }
      v44 = v32 + v112;
      v45 = -1;
      if ( v44 >= v32 )
        v45 = v32 + v112;
      v108 = v45;
      KnownZeroVaPages = v44 < v32 ? 0xC0000095 : 0;
      if ( v44 < v32 )
      {
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v136, "VsmmpWriteMemoryBlockByteRange");
          tlgCreate1Sz_char(v137, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
          v90 = 2511;
          v138 = &v90;
          v139 = 4;
          v92 = KnownZeroVaPages;
          v140 = &v92;
          v141 = 4;
          v46 = *v103;
          v142 = *v103 + 656;
          v143 = 16;
          v47 = *(unsigned __int16 *)(v46 + 120);
          v48 = *(_QWORD *)(v46 + 128);
          v144 = &v147;
          v145 = 2;
          v146 = v48;
          v147 = v47;
          v148 = 0;
          v94 = *(_QWORD *)(v46 + 648);
          v149 = &v94;
          v95 = v104;
          v151 = &v95;
          v97 = v107;
          v153 = &v97;
          v154 = 8;
          v98 = (_DWORD *)v32;
          v155 = (unsigned __int64 *)&v98;
          v156 = 8;
          v106 = v49;
          v157 = (unsigned __int64 *)&v106;
          v158 = 4;
          v89 = 14;
          v21 = byte_1400560E1;
          goto LABEL_6;
        }
        goto LABEL_113;
      }
      if ( v45 > v94 )
      {
        KnownZeroVaPages = -1073741811;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v136, "VsmmpWriteMemoryBlockByteRange");
          tlgCreate1Sz_char(v137, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
          v90 = 2526;
          v138 = &v90;
          v139 = 4;
          v92 = v50;
          v140 = &v92;
          v141 = 4;
          v51 = *v103;
          v142 = *v103 + 656;
          v143 = 16;
          v52 = *(unsigned __int16 *)(v51 + 120);
          v53 = *(_QWORD *)(v51 + 128);
          v144 = &v147;
          v145 = 2;
          v146 = v53;
          v147 = v52;
          v148 = 0;
          v94 = *(_QWORD *)(v51 + 648);
          v149 = &v94;
          v95 = v104;
          v151 = &v95;
          v97 = v107;
          v153 = &v97;
          v154 = 8;
          v98 = (_DWORD *)v32;
          v155 = (unsigned __int64 *)&v98;
          v156 = 8;
          v118 = v54;
          v157 = &v118;
          v158 = 8;
          v89 = 14;
          v21 = (char *)&word_14005619E;
          goto LABEL_6;
        }
        goto LABEL_113;
      }
    }
    else
    {
      v45 = v33;
      v108 = v33;
      v99 = 0;
    }
    v55 = v101 & 0xC;
    v96 = v55;
    v116 = v55;
LABEL_49:
    if ( v32 < v45 )
      break;
    v33 = v94;
    v30 = v122;
    v31 = v127;
  }
  v56 = v34 & 0x1FF;
  v57 = v45 - v32;
  if ( v45 - v32 >= (512 - v56) << 12 )
    v57 = (512 - v56) << 12;
  v102 = (v57 + 4095 + (v32 & 0xFFF)) >> 12;
  RtlInitializeBitMapEx(&v128, v159, v102);
  RtlClearAllBitsEx(&v128);
  if ( (*v122 & 8) == 0 || (a4 & 3) != 0 || v55 && v99 == 2 || (*v122 & 0x10000) != 0 )
  {
    v61 = v96;
    goto LABEL_73;
  }
  KnownZeroVaPages = VsmmQueryKnownZeroVaPages(*(PRKPROCESS *)(*v103 + 10328));
  if ( KnownZeroVaPages >= 0 )
  {
    v61 = v96;
    if ( !v96 )
    {
      for ( i = 0; ; ++i )
      {
        v121 = i;
        v63 = v102;
        if ( i >= v102 )
          break;
        if ( (unsigned __int8)RtlTestBitEx(&v128, i) )
        {
          v64 = (i + v34) << 12;
          v65 = v32;
          if ( v64 > v32 )
            v65 = (i + v34) << 12;
          v66 = v64 + 4096;
          v67 = v108;
          if ( v66 < v108 )
            v67 = v66;
          v118 = v67 - v65;
          v68 = RtlCompareMemoryUlong((PVOID)(v65 + v117 - v104), v67 - v65, 0);
          if ( v68 != v118 )
            RtlClearBitEx(&v128, i);
        }
      }
      v61 = v96;
LABEL_74:
      v69 = 0;
      v113 = v61;
      v100 = v61;
      while ( 1 )
      {
        v121 = v69;
        if ( v69 >= v63 )
        {
LABEL_109:
          v45 = v108;
          v55 = v96;
          if ( v109 != -1 )
          {
            VidPushLockRelease(*(_QWORD *)(v105 + 400) + 8 * v109);
            v109 = -1;
            v45 = v108;
          }
          goto LABEL_49;
        }
        NextForwardRunClear = RtlFindNextForwardRunClearEx(&v128, v69, &v120);
        v126 = NextForwardRunClear;
        if ( NextForwardRunClear )
        {
          v72 = v100;
          v71 = v120;
        }
        else
        {
          v71 = v102;
          v120 = v102;
          v72 = v113;
        }
        v118 = v71;
        v90 = v72;
        v100 = v72;
        if ( v71 > v69 && v72 )
        {
          v73 = (v34 + v71 - v69) << 12;
          if ( v108 < v73 )
            LODWORD(v73) = v108;
          v123[0] = (unsigned int)(v73 - v32);
          LODWORD(v110) = v73 - v32;
          KnownZeroVaPages = VmCompressUnpackExSkipBytes(&v129, LODWORD(v123[0]));
          v111 = KnownZeroVaPages;
          v71 = v118;
          if ( KnownZeroVaPages < 0 )
          {
            if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
            {
              tlgCreate1Sz_char(v136, "VsmmpWriteMemoryBlockByteRange");
              tlgCreate1Sz_char(v137, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
              LODWORD(v110) = 2753;
              v138 = (int *)&v110;
              v139 = 4;
              v116 = KnownZeroVaPages;
              v140 = &v116;
              v141 = 4;
              v74 = *v103;
              v142 = *v103 + 656;
              v143 = 16;
              v75 = *(unsigned __int16 *)(v74 + 120);
              v76 = *(_QWORD *)(v74 + 128);
              v144 = &v147;
              v145 = 2;
              v146 = v76;
              v147 = v75;
              v148 = 0;
              v123[0] = *(_QWORD *)(v74 + 648);
              v149 = v123;
              v113 = v77;
              v151 = (unsigned __int64 *)&v113;
              v152 = 4;
              v89 = 11;
              v21 = byte_140055F9D;
              goto LABEL_7;
            }
            goto LABEL_113;
          }
          v69 = v121;
          NextForwardRunClear = v126;
        }
        v34 += v71 - v69;
        v119 = v34;
        v32 = v34 << 12;
        v78 = v104;
        v79 = v108;
        if ( v34 << 12 >= v104 )
        {
          if ( v32 > v108 )
            v32 = v108;
          v110 = v32;
        }
        else
        {
          v32 = v104;
          v110 = v104;
        }
        if ( !NextForwardRunClear )
          goto LABEL_109;
        if ( (a4 & 3) == 0 && !v115 && v109 == -1 )
        {
          v109 = v34 >> 9;
          VidPushLockAcquireShared(*(_QWORD *)(v105 + 400) + 8 * (v34 >> 9), NextForwardRunClear);
          NextForwardRunClear = v126;
          v78 = v104;
        }
        v80 = (NextForwardRunClear + v34) << 12;
        if ( v79 < v80 )
          v80 = v79;
        v81 = v114 & 0x20;
        v82 = v80 - v32;
        v83 = v100
            ? VsmmMemoryBlockCopyByteRange(
                (unsigned int)&v132,
                v105,
                v32,
                v82,
                0,
                (__int64)&v129,
                v29,
                v81 != 0,
                v91,
                v124)
            : VsmmMemoryBlockCopyByteRange(
                (unsigned int)&v132,
                v105,
                v32,
                v82,
                v32 + v117 - v78,
                0,
                v29,
                v81 != 0,
                v91,
                v124);
        KnownZeroVaPages = v83;
        if ( v83 < 0 )
          break;
        v32 = v80;
        v110 = v80;
        v34 = v80 >> 12;
        v119 = v34;
        v69 = v126 + v120;
        v63 = v102;
      }
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v136, "VsmmpWriteMemoryBlockByteRange");
        tlgCreate1Sz_char(v137, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
        v114 = 2857;
        v138 = &v114;
        v139 = 4;
        v115 = KnownZeroVaPages;
        v140 = &v115;
        v141 = 4;
        v84 = *v103;
        v142 = *v103 + 656;
        v143 = 16;
        v85 = *(unsigned __int16 *)(v84 + 120);
        v86 = *(_QWORD *)(v84 + 128);
        v144 = &v147;
        v145 = 2;
        v146 = v86;
        v147 = v85;
        v148 = 0;
        v123[0] = *(_QWORD *)(v84 + 648);
        v149 = v123;
        v94 = v104;
        v151 = &v94;
        v95 = v107;
        v153 = &v95;
        v154 = 8;
        v97 = v32;
        v155 = &v97;
        v156 = 8;
        v98 = (_DWORD *)v80;
        v157 = (unsigned __int64 *)&v98;
        v158 = 8;
        v89 = 14;
        v21 = (char *)word_140056022;
        goto LABEL_6;
      }
      goto LABEL_113;
    }
LABEL_73:
    v63 = v102;
    goto LABEL_74;
  }
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v136, "VsmmpWriteMemoryBlockByteRange");
    tlgCreate1Sz_char(v137, "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c");
    v101 = 2616;
    v138 = &v101;
    v139 = 4;
    v90 = KnownZeroVaPages;
    v140 = &v90;
    v141 = 4;
    v58 = *v103;
    v142 = *v103 + 656;
    v143 = 16;
    v59 = *(unsigned __int16 *)(v58 + 120);
    v60 = *(_QWORD *)(v58 + 128);
    v144 = &v147;
    v145 = 2;
    v146 = v60;
    v147 = v59;
    v148 = 0;
    v94 = *(_QWORD *)(v58 + 648);
    v149 = &v94;
    v95 = v34;
    v151 = &v95;
    v97 = v102;
    v153 = &v97;
    v154 = 8;
    v89 = 12;
    v21 = &byte_14005625F;
    goto LABEL_6;
  }
LABEL_113:
  VsmmMemoryBlockMbpRangeVaDestroy(&v132);
  if ( v109 != -1 )
    VidPushLockRelease(*(_QWORD *)(v105 + 400) + 8 * v109);
  if ( v93 )
    KeUnstackDetachProcess(&ApcState);
  v87 = MemoryDescriptorList;
  if ( MemoryDescriptorList )
  {
    MmUnlockPages(MemoryDescriptorList);
    IoFreeMdl(v87);
  }
  return (unsigned int)KnownZeroVaPages;
}

```

## disassembly

```asm
0x14000d4d8  push    rbx
0x14000d4da  push    rsi
0x14000d4db  push    rdi
0x14000d4dc  push    r12
0x14000d4de  push    r13
0x14000d4e0  push    r14
0x14000d4e2  push    r15
0x14000d4e4  sub     rsp, 310h
0x14000d4eb  mov     rax, cs:__security_cookie
0x14000d4f2  xor     rax, rsp
0x14000d4f5  mov     [rsp+348h+var_48], rax
0x14000d4fd  mov     ebx, r9d
0x14000d500  mov     [rsp+348h+var_280], r8
0x14000d508  mov     [rsp+348h+var_298], rdx
0x14000d510  mov     [rsp+348h+var_290], rcx
0x14000d518  mov     [rsp+348h+var_210], rcx
0x14000d520  mov     [rsp+348h+var_2C8], rdx
0x14000d528  mov     [rsp+348h+var_2D8], r8
0x14000d52d  mov     [rsp+348h+var_2F0], ebx
0x14000d531  mov     r13, [rsp+348h+arg_20]
0x14000d539  mov     rax, [rsp+348h+arg_38]
0x14000d541  mov     [rsp+348h+var_208], rax
0x14000d549  xorps   xmm0, xmm0
0x14000d54c  movups  xmmword ptr [rsp+348h+ApcState.ApcListHead.Flink], xmm0
0x14000d554  movups  xmmword ptr [rsp+348h+ApcState.ApcListHead.Flink+10h], xmm0
0x14000d55c  movups  xmmword ptr [rsp+348h+ApcState.Process], xmm0
0x14000d564  xor     esi, esi
0x14000d566  mov     [rsp+348h+var_248], rsi
0x14000d56e  mov     [rsp+348h+var_2B8], esi
0x14000d575  mov     [rsp+348h+var_230], rsi
0x14000d57d  movups  [rsp+348h+var_1E8], xmm0
0x14000d585  mov     [rsp+348h+var_25C], esi
0x14000d58c  xor     eax, eax
0x14000d58e  movups  [rsp+348h+var_1D8], xmm0
0x14000d596  movups  [rsp+348h+var_1C8], xmm0
0x14000d59e  mov     dword ptr [rsp+348h+var_1B8], eax
0x14000d5a5  mov     [rsp+348h+var_2E8], sil
0x14000d5aa  mov     [rsp+348h+var_270], 0FFFFFFFFFFFFFFFFh
0x14000d5b6  mov     [rsp+348h+MemoryDescriptorList], rsi
0x14000d5be  lea     r9, [rcx+8]
0x14000d5c2  mov     [rsp+348h+var_2A0], r9
0x14000d5ca  mov     rdi, [r9]
0x14000d5cd  call    VsmmHostAccessMinimumForMemoryBlock
0x14000d5d2  mov     [rsp+348h+var_2F8], eax
0x14000d5d6  movdqu  [rsp+348h+var_1A8], xmm0
0x14000d5df  mov     [rsp+348h+var_1B0], rdi
0x14000d5e7  mov     eax, 0FFFFFFFFh
0x14000d5ec  mov     r12, [rsp+348h+arg_28]
0x14000d5f4  cmp     r12, rax
0x14000d5f7  jbe     loc_14000D763
0x14000d5fd  mov     r14d, 0C00000BBh
0x14000d603  mov     eax, cs:dword_140065110
0x14000d609  lea     r15d, [rsi+2]
0x14000d60d  cmp     eax, r15d
0x14000d610  jbe     loc_14000EEFA
0x14000d616  mov     edx, 100h
0x14000d61b  lea     rcx, dword_140065110
0x14000d622  call    _tlgKeywordOn
0x14000d627  test    al, al
0x14000d629  jz      loc_14000EEFA
0x14000d62f  lea     rdx, aVsmmpwritememo; "VsmmpWriteMemoryBlockByteRange"
0x14000d636  lea     rcx, [rsp+348h+var_148]
0x14000d63e  call    _tlgCreate1Sz_char
0x14000d643  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000d64a  lea     rcx, [rsp+348h+var_138]
0x14000d652  call    _tlgCreate1Sz_char
0x14000d657  mov     [rsp+348h+var_2F8], 929h
0x14000d65f  lea     rax, [rsp+348h+var_2F8]
0x14000d664  mov     [rsp+348h+var_128], rax
0x14000d66c  mov     [rsp+348h+var_120], 4
0x14000d678  mov     [rsp+348h+var_2F0], r14d
0x14000d67d  lea     rax, [rsp+348h+var_2F0]
0x14000d682  mov     [rsp+348h+var_118], rax
0x14000d68a  mov     [rsp+348h+var_110], 4
0x14000d696  mov     rdx, [r9]
0x14000d699  lea     rax, [rdx+290h]
0x14000d6a0  mov     [rsp+348h+var_108], rax
0x14000d6a8  mov     [rsp+348h+var_100], 10h
0x14000d6b4  movzx   ecx, word ptr [rdx+78h]
0x14000d6b8  mov     rax, [rdx+80h]
0x14000d6bf  lea     r8, [rsp+348h+var_E0]
0x14000d6c7  mov     [rsp+348h+var_F8], r8
0x14000d6cf  mov     [rsp+348h+var_F0], r15
0x14000d6d7  mov     [rsp+348h+var_E8], rax
0x14000d6df  mov     [rsp+348h+var_E0], ecx
0x14000d6e6  mov     [rsp+348h+var_DC], esi
0x14000d6ed  mov     rax, [rdx+288h]
0x14000d6f4  lea     rdx, byte_14005658B
0x14000d6fb  mov     [rsp+348h+var_2E0], rax
0x14000d700  lea     rax, [rsp+348h+var_2E0]
0x14000d705  mov     [rsp+348h+var_D8], rax
0x14000d70d  lea     rax, [rsp+348h+var_168]
0x14000d715  lea     rcx, [rsp+348h+var_2D8]
0x14000d71a  mov     [rsp+348h+var_320], rax
0x14000d71f  mov     [rsp+348h+var_2D8], r12
0x14000d724  mov     [rsp+348h+var_C8], rcx
0x14000d72c  mov     dword ptr [rsp+348h+var_328], 0Bh
0x14000d734  mov     [rsp+348h+var_C0], 8
0x14000d740  xor     r9d, r9d
0x14000d743  xor     r8d, r8d
0x14000d746  mov     [rsp+348h+var_D0], 8
0x14000d752  lea     rcx, dword_140065110
0x14000d759  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d75e  jmp     loc_14000EEFA
0x14000d763  lea     rax, [rcx+108h]
0x14000d76a  mov     [rsp+348h+var_220], rax
0x14000d772  mov     eax, [rax]
0x14000d774  test    al, 8
0x14000d776  jz      loc_14000D8F4
0x14000d77c  call    cs:__imp_PsGetCurrentProcess
0x14000d783  nop     dword ptr [rax+rax+00h]
0x14000d788  cmp     rax, [rdi+2858h]
0x14000d78f  jz      loc_14000D8F4
0x14000d795  lea     rax, [rsp+348h+var_248]
0x14000d79d  mov     [rsp+348h+var_328], rax
0x14000d7a2  xor     r9d, r9d
0x14000d7a5  lea     r8, [rsp+348h+MemoryDescriptorList]
0x14000d7ad  mov     edx, r12d
0x14000d7b0  mov     rcx, r13
0x14000d7b3  call    VsmmpMapUserBufferToSystem
0x14000d7b8  mov     r14d, eax
0x14000d7bb  test    eax, eax
0x14000d7bd  jns     loc_14000D8CA
0x14000d7c3  mov     ecx, cs:dword_140065110
0x14000d7c9  mov     r15d, 2
0x14000d7cf  cmp     ecx, r15d
0x14000d7d2  jbe     loc_14000EEFA
0x14000d7d8  mov     edx, 100h
0x14000d7dd  lea     rcx, dword_140065110
0x14000d7e4  call    _tlgKeywordOn
0x14000d7e9  test    al, al
0x14000d7eb  jz      loc_14000EEFA
0x14000d7f1  lea     rdx, aVsmmpwritememo; "VsmmpWriteMemoryBlockByteRange"
0x14000d7f8  lea     rcx, [rsp+348h+var_148]
0x14000d800  call    _tlgCreate1Sz_char
0x14000d805  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000d80c  lea     rcx, [rsp+348h+var_138]
0x14000d814  call    _tlgCreate1Sz_char
0x14000d819  mov     [rsp+348h+var_2F8], 946h
0x14000d821  lea     rax, [rsp+348h+var_2F8]
0x14000d826  mov     [rsp+348h+var_128], rax
0x14000d82e  mov     [rsp+348h+var_120], 4
0x14000d83a  mov     [rsp+348h+var_2F0], r14d
0x14000d83f  lea     rax, [rsp+348h+var_2F0]
0x14000d844  mov     [rsp+348h+var_118], rax
0x14000d84c  mov     [rsp+348h+var_110], 4
0x14000d858  mov     rcx, [rsp+348h+var_2A0]
0x14000d860  mov     rdx, [rcx]
0x14000d863  lea     rax, [rdx+290h]
0x14000d86a  mov     [rsp+348h+var_108], rax
0x14000d872  mov     [rsp+348h+var_100], 10h
0x14000d87e  movzx   ecx, word ptr [rdx+78h]
0x14000d882  mov     rax, [rdx+80h]
0x14000d889  lea     r8, [rsp+348h+var_E0]
0x14000d891  mov     [rsp+348h+var_F8], r8
0x14000d899  mov     [rsp+348h+var_F0], r15
0x14000d8a1  mov     [rsp+348h+var_E8], rax
0x14000d8a9  mov     [rsp+348h+var_E0], ecx
0x14000d8b0  mov     [rsp+348h+var_DC], esi
0x14000d8b7  mov     rax, [rdx+288h]
0x14000d8be  lea     rdx, byte_140056605
0x14000d8c5  jmp     loc_14000D6FB
0x14000d8ca  mov     r14b, sil
0x14000d8cd  mov     [rsp+348h+var_2F4], sil
0x14000d8d2  lea     rdx, [rsp+348h+ApcState]; ApcState
0x14000d8da  mov     rcx, [rdi+2858h]; PROCESS
0x14000d8e1  call    cs:__imp_KeStackAttachProcess
0x14000d8e8  nop     dword ptr [rax+rax+00h]
0x14000d8ed  mov     [rsp+348h+var_2E8], 1
0x14000d8f2  jmp     short loc_14000D909
0x14000d8f4  mov     [rsp+348h+var_248], r13
0x14000d8fc  mov     r14b, [rsp+348h+arg_30]
0x14000d904  mov     [rsp+348h+var_2F4], r14b
0x14000d909  mov     r15d, r12d
0x14000d90c  mov     edi, ebx
0x14000d90e  shr     edi, 2
0x14000d911  and     edi, 3
0x14000d914  jz      loc_14000DAAF
0x14000d91a  cmp     [rsp+348h+MemoryDescriptorList], rsi
0x14000d922  jnz     loc_14000DA6B
0x14000d928  test    r14b, r14b
0x14000d92b  jz      loc_14000DA6B
0x14000d931  lea     rax, [rsp+348h+var_248]
0x14000d939  mov     [rsp+348h+var_328], rax
0x14000d93e  xor     r9d, r9d
0x14000d941  lea     r8, [rsp+348h+MemoryDescriptorList]
0x14000d949  mov     edx, r12d
0x14000d94c  mov     rcx, r13
0x14000d94f  call    VsmmpMapUserBufferToSystem
0x14000d954  mov     r14d, eax
0x14000d957  test    eax, eax
0x14000d959  jns     loc_14000DA66
0x14000d95f  mov     eax, cs:dword_140065110
0x14000d965  mov     r15d, 2
0x14000d96b  cmp     eax, r15d
0x14000d96e  jbe     loc_14000EEFA
0x14000d974  mov     edx, 100h
0x14000d979  lea     rcx, dword_140065110
0x14000d980  call    _tlgKeywordOn
0x14000d985  test    al, al
0x14000d987  jz      loc_14000EEFA
0x14000d98d  lea     rdx, aVsmmpwritememo; "VsmmpWriteMemoryBlockByteRange"
0x14000d994  lea     rcx, [rsp+348h+var_148]
0x14000d99c  call    _tlgCreate1Sz_char
0x14000d9a1  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x14000d9a8  lea     rcx, [rsp+348h+var_138]
0x14000d9b0  call    _tlgCreate1Sz_char
0x14000d9b5  mov     [rsp+348h+var_2F8], 96Fh
0x14000d9bd  lea     rax, [rsp+348h+var_2F8]
0x14000d9c2  mov     [rsp+348h+var_128], rax
0x14000d9ca  mov     [rsp+348h+var_120], 4
0x14000d9d6  mov     [rsp+348h+var_2F0], r14d
0x14000d9db  lea     rax, [rsp+348h+var_2F0]
0x14000d9e0  mov     [rsp+348h+var_118], rax
0x14000d9e8  mov     [rsp+348h+var_110], 4
0x14000d9f4  mov     rcx, [rsp+348h+var_2A0]
0x14000d9fc  mov     rdx, [rcx]
0x14000d9ff  lea     rax, [rdx+290h]
0x14000da06  mov     [rsp+348h+var_108], rax
0x14000da0e  mov     [rsp+348h+var_100], 10h
0x14000da1a  movzx   ecx, word ptr [rdx+78h]
0x14000da1e  mov     rax, [rdx+80h]
0x14000da25  lea     r8, [rsp+348h+var_E0]
0x14000da2d  mov     [rsp+348h+var_F8], r8
0x14000da35  mov     [rsp+348h+var_F0], r15
0x14000da3d  mov     [rsp+348h+var_E8], rax
0x14000da45  mov     [rsp+348h+var_E0], ecx
0x14000da4c  mov     [rsp+348h+var_DC], esi
0x14000da53  mov     rax, [rdx+288h]
0x14000da5a  lea     rdx, byte_1400562E9
0x14000da61  jmp     loc_14000D6FB
0x14000da66  mov     [rsp+348h+var_2F4], sil
0x14000da6b  mov     dword ptr [rsp+348h+var_1D8+4], esi
0x14000da72  mov     dword ptr [rsp+348h+var_1C8+4], esi
0x14000da79  mov     [rsp+348h+var_1B8], rsi
0x14000da81  mov     ecx, edi
0x14000da83  call    VsmmCompressionFormatToVmCompress
0x14000da88  mov     dword ptr [rsp+348h+var_1D8], eax
0x14000da8f  mov     rax, [rsp+348h+var_248]
0x14000da97  mov     qword ptr [rsp+348h+var_1D8+8], rax
0x14000da9f  mov     dword ptr [rsp+348h+var_1C8], r15d
0x14000daa7  mov     qword ptr [rsp+348h+var_1C8+8], rsi
0x14000daaf  mov     r9, [rsp+348h+var_220]
0x14000dab7  mov     [rsp+348h+var_2C0], r9
0x14000dabf  mov     r10d, ebx
0x14000dac2  mov     [rsp+348h+var_1F0], ebx
0x14000dac9  mov     [rsp+348h+var_2B0], ebx
0x14000dad0  mov     [rsp+348h+var_254], ebx
0x14000dad7  mov     eax, [rsp+348h+var_2F8]
0x14000dadb  mov     [rsp+348h+var_250], eax
0x14000dae2  mov     dl, 1
0x14000dae4  mov     ecx, ebx
0x14000dae6  call    VsmmpConvertMbpRwFlagsToMbpLockFlags
0x14000daeb  mov     edi, eax
0x14000daed  mov     [rsp+348h+var_288], eax
0x14000daf4  mov     r8, [rsp+348h+var_298]
0x14000dafc  mov     r12, r8
0x14000daff  mov     [rsp+348h+var_268], r8
0x14000db07  mov     rcx, [rsp+348h+var_280]
0x14000db0f  add     rcx, r8
0x14000db12  mov     [rsp+348h+var_2E0], rcx
0x14000db17  mov     r13, r8
0x14000db1a  shr     r13, 0Ch
0x14000db1e  mov     [rsp+348h+var_238], r13
0x14000db26  mov     r15d, 2
0x14000db2c  cmp     r12, rcx
0x14000db2f  jnb     loc_14000EEF7
0x14000db35  mov     eax, [r9]
0x14000db38  test    al, 8
0x14000db3a  jz      loc_14000E2F0
0x14000db40  test    r10b, 0Ch
0x14000db44  jz      loc_14000E2F0
0x14000db4a  lea     r8, [rsp+348h+var_2B8]
0x14000db52  lea     rdx, [rsp+348h+var_25C]
0x14000db5a  lea     rcx, [rsp+348h+var_1D8]
0x14000db62  call    VmCompressParseNextRange
0x14000db67  mov     r14d, eax
0x14000db6a  mov     [rsp+348h+var_260], eax
0x14000db71  mov     r9d, [rsp+348h+var_25C]
0x14000db79  mov     edx, [rsp+348h+var_2B8]
0x14000db80  mov     r10, [rsp+348h+var_298]
0x14000db88  jmp     short loc_14000DC06
0x14000db8a  mov     r14d, eax
0x14000db8d  mov     [rsp+348h+var_260], eax
0x14000db94  xor     r9d, r9d
0x14000db97  mov     [rsp+348h+var_25C], r9d
0x14000db9f  xor     edx, edx
0x14000dba1  mov     [rsp+348h+var_2B8], edx
0x14000dba8  xor     esi, esi
0x14000dbaa  lea     r15d, [r9+2]
0x14000dbae  mov     r13, [rsp+348h+var_238]
0x14000dbb6  mov     r12, [rsp+348h+var_268]
0x14000dbbe  mov     edi, [rsp+348h+var_288]
0x14000dbc5  mov     rax, [rsp+348h+var_2C0]
0x14000dbcd  mov     [rsp+348h+var_220], rax
0x14000dbd5  mov     rax, [rsp+348h+var_210]
0x14000dbdd  mov     [rsp+348h+var_290], rax
0x14000dbe5  mov     r10, [rsp+348h+var_2C8]
0x14000dbed  mov     [rsp+348h+var_298], r10
0x14000dbf5  mov     rax, [rsp+348h+var_2D8]
  ... truncated ...
```
