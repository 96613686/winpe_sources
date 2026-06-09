# RaDriverScsiIrp

- ea: `0x140015200`
- end: `0x1400172c9`
- name: `RaDriverScsiIrp`
- size: `8393`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400147f4`
- `0x140014bd4`
- `0x140014fd0`
- `0x140014fe4`
- `0x140015200`
- `0x1400172d0`
- `0x1400173f0`
- `0x140017544`
- `0x1400175d0`
- `0x140017ae8`
- `0x140017b80`
- `0x140033b18`
- `0x140063e4c`
- `0x1400693d8`
- `0x14006d1c0`
- `0x14006d298`
- `0x14006f610`
- `0x1400848c4`
- `0x140093dc0`
- `0x1400bdb38`
- `0x1400bf1c8`
- `0x1400c1a34`
- `0x1400c1dc8`
- `0x1400c2588`
- `0x14014b400`
- `0x14018e9a8`
- `0x1401971e4`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140015419`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140015522`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140015653`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140015772`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400158c4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140015af4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400166f0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400168bb`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140016ab1`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140016c64`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140016dad`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140015419`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140015522`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140015653`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140015772`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400158c4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140015af4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400166f0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400168bb`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140016ab1`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140016c64`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140016dad`
- `ntoskrnl!KeSetEvent` at `0x140015a4b`
- `ntoskrnl!KeSetEvent` at `0x140015b9f`
- `ntoskrnl!KeSetEvent` at `0x140015c66`
- `ntoskrnl!KeSetEvent` at `0x140015d89`
- `ntoskrnl!KeSetEvent` at `0x140016916`
- `ntoskrnl!KeSetEvent` at `0x14001698c`
- `ntoskrnl!KeSetEvent` at `0x140016cbf`
- `ntoskrnl!KeSetEvent` at `0x140015a4b`
- `ntoskrnl!KeSetEvent` at `0x140015b9f`
- `ntoskrnl!KeSetEvent` at `0x140015c66`
- `ntoskrnl!KeSetEvent` at `0x140015d89`
- `ntoskrnl!KeSetEvent` at `0x140016916`
- `ntoskrnl!KeSetEvent` at `0x14001698c`
- `ntoskrnl!KeSetEvent` at `0x140016cbf`
- `ntoskrnl!IofCompleteRequest` at `0x140015552`
- `ntoskrnl!IofCompleteRequest` at `0x140015683`
- `ntoskrnl!IofCompleteRequest` at `0x140015cf3`
- `ntoskrnl!IofCompleteRequest` at `0x140016e07`
- `ntoskrnl!IofCompleteRequest` at `0x140015552`
- `ntoskrnl!IofCompleteRequest` at `0x140015683`
- `ntoskrnl!IofCompleteRequest` at `0x140015cf3`
- `ntoskrnl!IofCompleteRequest` at `0x140016e07`

## pseudocode

```c
__int64 __fastcall RaDriverScsiIrp(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdi
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rbx
  int v9; // eax
  unsigned int v10; // r14d
  _DWORD *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r12
  __int64 v14; // r15
  int v15; // edx
  int v16; // r14d
  _BYTE *v17; // r14
  unsigned int v18; // r11d
  unsigned int v19; // r9d
  __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  int v22; // r10d
  __int64 v23; // r8
  unsigned __int64 v24; // rcx
  __int64 v25; // rcx
  char *v27; // rdx
  __int64 v28; // rcx
  char v29; // al
  unsigned int v30; // eax
  bool v31; // bl
  unsigned __int64 v32; // r8
  signed __int32 v33; // eax
  signed __int32 v34; // ett
  int v35; // r10d
  int v36; // edx
  char *v37; // rcx
  char v38; // al
  unsigned __int64 v39; // r8
  signed __int32 v40; // eax
  signed __int32 v41; // ett
  PDEVICE_OBJECT v42; // rcx
  unsigned __int8 *v43; // rax
  __int64 v44; // rdx
  int v45; // eax
  unsigned int v46; // edi
  char v47; // r15
  unsigned __int8 *v48; // r9
  unsigned __int8 v49; // r8
  unsigned int v50; // r11d
  __int64 v51; // rcx
  unsigned __int64 v52; // r10
  __int64 v53; // rbx
  int v54; // ecx
  unsigned __int64 v55; // r8
  signed __int32 v56; // eax
  signed __int32 v57; // ett
  unsigned int v58; // edi
  unsigned int v59; // r11d
  __int64 v60; // rcx
  unsigned __int64 v61; // r10
  int v62; // ecx
  __int64 v63; // rcx
  unsigned __int64 v64; // r8
  signed __int32 v65; // eax
  signed __int32 v66; // ett
  char v67; // al
  bool v68; // zf
  _DWORD *v69; // rax
  int *v70; // rax
  int v71; // ecx
  unsigned __int64 v72; // rcx
  char v73; // r11
  char v74; // r9
  char v75; // r10
  unsigned __int64 v76; // r8
  signed __int32 v77; // eax
  signed __int32 v78; // ett
  __int64 v79; // rdx
  unsigned __int64 v80; // rax
  char *v81; // r9
  unsigned int v82; // eax
  char v83; // al
  unsigned __int8 *v84; // r12
  _BYTE *v85; // rdx
  char v86; // r15
  unsigned __int8 v87; // r9
  unsigned __int64 v88; // rcx
  char v89; // bl
  char v90; // r8
  char v91; // r11
  char v92; // r10
  _BYTE *v93; // rax
  char *v94; // r10
  unsigned int v95; // eax
  char v96; // al
  unsigned __int8 *v97; // r9
  unsigned __int64 v98; // rcx
  _BYTE *v99; // rdx
  unsigned __int8 v100; // r9
  char v101; // r14
  char v102; // bl
  char v103; // r8
  char v104; // r11
  char v105; // r10
  _BYTE *v106; // rax
  char *v107; // r10
  unsigned int v108; // eax
  char v109; // al
  unsigned __int64 v110; // rcx
  _BYTE *v111; // rdx
  unsigned __int8 v112; // r10
  char v113; // r15
  char v114; // bl
  char v115; // r9
  char v116; // r11
  char v117; // r8
  _BYTE *v118; // rax
  char *v119; // r8
  unsigned int v120; // eax
  char v121; // al
  unsigned __int8 *v122; // r9
  char v123; // di
  unsigned __int8 v124; // r8
  unsigned __int64 v125; // rcx
  char v126; // r11
  __int64 v127; // rdx
  char v128; // r10
  char v129; // r9
  unsigned __int64 v130; // rax
  char *v131; // r9
  unsigned int v132; // eax
  char v133; // al
  unsigned __int64 v134; // rcx
  unsigned __int8 v135; // r9
  char v136; // r15
  char v137; // r11
  __int64 v138; // rdx
  char v139; // r10
  char v140; // r8
  unsigned __int64 v141; // rax
  char *v142; // r8
  unsigned int v143; // eax
  char v144; // al
  unsigned __int8 *v145; // r10
  unsigned __int8 *v146; // r9
  unsigned __int8 *v147; // r8
  int v148; // ecx
  int v149; // ecx
  int v150; // ecx
  int v151; // ecx
  int v152; // ecx
  unsigned int v153; // r11d
  __int64 v154; // rcx
  unsigned __int64 v155; // r10
  __int64 v156; // rbx
  int v157; // ecx
  int v158; // ecx
  unsigned int v159; // r11d
  __int64 v160; // rcx
  unsigned __int64 v161; // r10
  int v162; // ecx
  int v163; // ecx
  unsigned int v164; // r14d
  int v165; // ecx
  unsigned int v166; // r15d
  int v167; // ecx
  int v168; // ecx
  unsigned int v169; // r15d
  char *v170; // r8
  char v171; // al
  __int64 v172; // r8
  unsigned int v173; // edi
  unsigned int v174; // r11d
  __int64 v175; // rcx
  unsigned __int64 v176; // r10
  __int64 v177; // rbx
  int v178; // ecx
  unsigned int v179; // edi
  unsigned int v180; // r11d
  __int64 v181; // rcx
  unsigned __int64 v182; // r10
  __int64 v183; // rbx
  int v184; // ecx
  signed __int32 v185; // eax
  signed __int32 v186; // ett
  char v187; // al
  unsigned int v188; // edi
  unsigned int v189; // edi
  unsigned int v190; // r15d
  __int64 v191; // rcx
  unsigned __int64 v192; // r11
  __int64 v193; // rbx
  int v194; // ecx
  int v195; // edx
  __int64 v196; // rcx
  char *v197; // r8
  char v198; // al
  int *v199; // rax
  int v200; // ecx
  __int64 v201; // r8
  __int64 v202; // rcx
  unsigned __int64 v203; // r11
  __int64 v204; // rbx
  int v205; // ecx
  signed __int32 v206; // eax
  signed __int32 v207; // ett
  char v208; // al
  unsigned int v209; // r15d
  unsigned int v210; // r11d
  __int64 v211; // rcx
  unsigned __int64 v212; // r10
  __int64 v213; // rbx
  int v214; // ecx
  __int64 v215; // rcx
  char *v216; // rdx
  char v217; // al
  _DWORD *v218; // rax
  __int64 v219; // rcx
  unsigned __int64 v220; // r10
  __int64 v221; // r11
  int v222; // ecx
  unsigned __int64 v223; // r8
  __int64 v224; // r8
  char v225; // cl
  unsigned __int64 v226; // r8
  int v227; // [rsp+60h] [rbp-9h]
  unsigned int v228; // [rsp+60h] [rbp-9h]
  unsigned int v229; // [rsp+60h] [rbp-9h]
  __int128 v230; // [rsp+68h] [rbp-1h] BYREF
  __int128 v231; // [rsp+78h] [rbp+Fh] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_61bd6e0e791f31e2ffa75bd9431aea96_Traceguids, a1, a2);
  }
  *(_BYTE *)(a2 + 141) = -88;
  v5 = *(_QWORD *)(a1 + 64);
  v6 = *(_DWORD *)v5;
  if ( *(_DWORD *)v5 != 1431193940 )
  {
    if ( v6 == 1094997074 )
    {
      v10 = RaidAdapterScsiIrp(v5, a2);
      goto LABEL_42;
    }
    if ( v6 != 1314275652 )
    {
      if ( v6 == 1314278989 )
        v10 = NvmeNamespaceScsiIrp(v5, a2);
      else
        v10 = -1073741823;
      goto LABEL_42;
    }
    v68 = StorEtwLoggingEnabled == 0;
    v10 = -1073741823;
    *(_DWORD *)(a2 + 48) = -1073741823;
    *(_BYTE *)(a2 + 141) = -84;
    if ( v68 )
      goto LABEL_54;
    v230 = 0;
    IoGetActivityIdIrp(a2, &v230);
    v170 = *(char **)(a2 + 184);
    v171 = *v170;
    if ( *v170 == 15 )
    {
      if ( byte_140177431 >= 0 )
        goto LABEL_54;
      v172 = *((_QWORD *)v170 + 1);
      if ( *(_BYTE *)(v172 + 2) != 40 )
      {
        LODWORD(v88) = *(unsigned __int8 *)(v172 + 72);
        v85 = *(_BYTE **)(v172 + 32);
        v87 = *(_BYTE *)(v172 + 11);
        v86 = *(_BYTE *)(v172 + 4);
        if ( *(_BYTE *)(v172 + 2) )
          goto LABEL_54;
        goto LABEL_199;
      }
      if ( *(_DWORD *)(v172 + 20) )
        goto LABEL_54;
      v173 = *(_DWORD *)(v172 + 56);
      if ( !v173 )
        goto LABEL_54;
      v84 = 0;
      v87 = 0;
      v86 = 0;
      v85 = 0;
      v174 = 0;
      while ( 1 )
      {
        v175 = *(unsigned int *)(v172 + 4LL * v174 + 120);
        if ( (unsigned int)v175 >= 0x80 )
        {
          v176 = *(unsigned int *)(v172 + 16);
          if ( (unsigned int)v175 < (unsigned int)v176 )
          {
            v177 = (unsigned int)v175;
            v178 = *(_DWORD *)(v175 + v172);
            if ( v178 == 64 )
            {
              if ( v177 + 40 <= v176 )
              {
                if ( *(_BYTE *)(v177 + v172 + 10) )
LABEL_196:
                  v84 = (unsigned __int8 *)(v177 + v172 + 24);
LABEL_197:
                v85 = *(_BYTE **)(v177 + v172 + 16);
                v86 = *(_BYTE *)(v177 + v172 + 8);
                v87 = *(_BYTE *)(v177 + v172 + 9);
                goto LABEL_538;
              }
            }
            else
            {
              v148 = v178 - 65;
              if ( v148 )
              {
                if ( v148 == 1 && v177 + 40 <= v176 )
                {
                  if ( *(_DWORD *)(v177 + v172 + 12) )
                    v84 = (unsigned __int8 *)(v177 + v172 + 32);
                  v85 = *(_BYTE **)(v177 + v172 + 24);
                  v86 = *(_BYTE *)(v177 + v172 + 8);
                  v87 = *(_BYTE *)(v177 + v172 + 9);
LABEL_538:
                  if ( !v84 )
                    goto LABEL_54;
                  LODWORD(v88) = *v84;
LABEL_199:
                  LOBYTE(v88) = v88 - 8;
                  if ( (v88 & 0x5D) != 0 )
                    goto LABEL_54;
                  v89 = *(_BYTE *)(v172 + 3);
                  if ( v89 == 1 || !v85 || !v87 )
                    goto LABEL_414;
                  v90 = 0;
                  v91 = 0;
                  v92 = 0;
                  v88 = (unsigned __int64)&v85[v87];
                  v93 = v85 + 8;
                  if ( (unsigned __int8)((*v85 & 0x7F) - 114) <= 1u )
                  {
                    if ( (unsigned __int64)v93 <= v88 )
                    {
                      v91 = v85[2];
                      v90 = v85[1] & 0xF;
                      v92 = v85[3];
                      goto LABEL_211;
                    }
                  }
                  else if ( (unsigned __int64)v93 <= v88 )
                  {
                    v94 = v85 + 13;
                    v90 = v85[2] & 0xF;
                    v95 = v87;
                    if ( (unsigned int)(unsigned __int8)v85[7] + 8 <= v87 )
                      v95 = (unsigned __int8)v85[7] + 8;
                    v88 = (unsigned __int64)&v85[v95];
                    if ( (unsigned __int64)v94 <= v88 )
                      v91 = v85[12];
                    if ( (unsigned __int64)(v85 + 14) > v88 )
                      v92 = 0;
                    else
                      v92 = *v94;
LABEL_211:
                    v96 = 1;
LABEL_544:
                    if ( !v96 )
                    {
LABEL_414:
                      v92 = 0;
                      v91 = 0;
                      v90 = 0;
                    }
                    McTemplateK0pduuuuup_EtwWriteTransfer(
                      v88,
                      (_DWORD)v85,
                      (unsigned int)&v230,
                      a2,
                      *(_DWORD *)(a2 + 48),
                      v89,
                      v86,
                      v90,
                      v91,
                      v92,
                      a2);
                    goto LABEL_54;
                  }
                  v96 = 0;
                  goto LABEL_544;
                }
              }
              else if ( v177 + 56 <= v176 )
              {
                if ( *(_BYTE *)(v177 + v172 + 10) )
                  goto LABEL_196;
                goto LABEL_197;
              }
            }
          }
        }
        if ( ++v174 >= v173 )
          goto LABEL_538;
      }
    }
    if ( v171 != 14 )
    {
      if ( v171 != 27 )
        goto LABEL_54;
      if ( v170[1] == 7 && !*((_DWORD *)v170 + 2) )
      {
        if ( (byte_140177432 & 0x40) == 0 )
          goto LABEL_54;
        v13 = *(_QWORD *)(a2 + 56);
        if ( v13 )
          LODWORD(v13) = *(_DWORD *)v13;
        goto LABEL_614;
      }
LABEL_120:
      if ( (byte_140177432 & 0x20) != 0 )
        McTemplateK0pd_EtwWriteTransfer(v28, EventPnpRequestComplete, &v230, a2, *(_DWORD *)(a2 + 48));
      goto LABEL_54;
    }
    goto LABEL_100;
  }
  v7 = *(_QWORD *)(a2 + 184);
  v231 = 0;
  v8 = *(_QWORD *)(v7 + 8);
  if ( !v8 )
  {
    v13 = 0;
    *(_BYTE *)(a2 + 141) = -84;
    v68 = StorEtwLoggingEnabled == 0;
    v10 = -1073741811;
    *(_QWORD *)(a2 + 56) = 0;
    *(_DWORD *)(a2 + 48) = -1073741811;
    if ( v68 )
      goto LABEL_54;
    v230 = 0;
    IoGetActivityIdIrp(a2, &v230);
    v28 = *(_QWORD *)(a2 + 184);
    v29 = *(_BYTE *)v28;
    if ( *(_BYTE *)v28 == 15 )
    {
      if ( byte_140177431 >= 0 )
        goto LABEL_54;
      v44 = *(_QWORD *)(v28 + 8);
      if ( *(_BYTE *)(v44 + 2) != 40 )
      {
        LODWORD(v72) = *(unsigned __int8 *)(v44 + 72);
        v13 = *(_QWORD *)(v44 + 32);
        v49 = *(_BYTE *)(v44 + 11);
        v47 = *(_BYTE *)(v44 + 4);
        if ( *(_BYTE *)(v44 + 2) )
          goto LABEL_54;
        goto LABEL_215;
      }
      if ( *(_DWORD *)(v44 + 20) )
        goto LABEL_54;
      v179 = *(_DWORD *)(v44 + 56);
      if ( !v179 )
        goto LABEL_54;
      v47 = 0;
      v97 = 0;
      v49 = 0;
      v180 = 0;
      while ( 1 )
      {
        v181 = *(unsigned int *)(v44 + 4LL * v180 + 120);
        if ( (unsigned int)v181 >= 0x80 )
        {
          v182 = *(unsigned int *)(v44 + 16);
          if ( (unsigned int)v181 < (unsigned int)v182 )
          {
            v183 = (unsigned int)v181;
            v184 = *(_DWORD *)(v44 + v181);
            if ( v184 == 64 )
            {
              if ( v183 + 40 <= v182 )
              {
                if ( *(_BYTE *)(v44 + v183 + 10) )
LABEL_212:
                  v97 = (unsigned __int8 *)(v183 + v44 + 24);
LABEL_213:
                v13 = *(_QWORD *)(v44 + v183 + 16);
                v47 = *(_BYTE *)(v44 + v183 + 8);
                v49 = *(_BYTE *)(v44 + v183 + 9);
                goto LABEL_549;
              }
            }
            else
            {
              v149 = v184 - 65;
              if ( v149 )
              {
                if ( v149 == 1 && v183 + 40 <= v182 )
                {
                  if ( *(_DWORD *)(v44 + v183 + 12) )
                    v97 = (unsigned __int8 *)(v183 + v44 + 32);
                  v13 = *(_QWORD *)(v44 + v183 + 24);
                  v47 = *(_BYTE *)(v44 + v183 + 8);
                  v49 = *(_BYTE *)(v44 + v183 + 9);
LABEL_549:
                  if ( !v97 )
                    goto LABEL_54;
                  LODWORD(v72) = *v97;
LABEL_215:
                  LOBYTE(v72) = v72 - 8;
                  if ( (v72 & 0x5D) != 0 )
                    goto LABEL_54;
                  v73 = *(_BYTE *)(v44 + 3);
                  if ( v73 == 1 || !v13 )
                    goto LABEL_172;
                  goto LABEL_186;
                }
              }
              else if ( v183 + 56 <= v182 )
              {
                if ( *(_BYTE *)(v44 + v183 + 10) )
                  goto LABEL_212;
                goto LABEL_213;
              }
            }
          }
        }
        if ( ++v180 >= v179 )
          goto LABEL_549;
      }
    }
    if ( v29 != 14 )
    {
      if ( v29 != 27 )
        goto LABEL_54;
      if ( *(_BYTE *)(v28 + 1) != 7 )
        goto LABEL_120;
      v68 = *(_DWORD *)(v28 + 8) == 0;
      goto LABEL_147;
    }
    goto LABEL_100;
  }
  LOBYTE(a3) = 1;
  v9 = RaUnitAcquireRemoveLock(v5, a2, a3);
  v10 = v9;
  if ( v9 < 0 )
  {
    *(_BYTE *)(v8 + 3) = RaidNtStatusToSrbStatus((unsigned int)v9);
    v13 = 0;
    v68 = StorEtwLoggingEnabled == 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = v10;
    if ( v68 )
      goto LABEL_54;
    v230 = 0;
    IoGetActivityIdIrp(a2, &v230);
    v43 = *(unsigned __int8 **)(a2 + 184);
    v28 = *v43;
    if ( (_BYTE)v28 == 15 )
    {
      if ( byte_140177431 >= 0 )
        goto LABEL_54;
      v44 = *((_QWORD *)v43 + 1);
      v45 = *(unsigned __int8 *)(v44 + 2);
      if ( (_BYTE)v45 == 40 )
      {
        if ( *(_DWORD *)(v44 + 20) )
          goto LABEL_54;
        v46 = *(_DWORD *)(v44 + 56);
        if ( !v46 )
          goto LABEL_54;
        v47 = 0;
        v48 = 0;
        v49 = 0;
        v50 = 0;
        while ( 1 )
        {
          v51 = *(unsigned int *)(v44 + 4LL * v50 + 120);
          if ( (unsigned int)v51 >= 0x80 )
          {
            v52 = *(unsigned int *)(v44 + 16);
            if ( (unsigned int)v51 < (unsigned int)v52 )
            {
              v53 = (unsigned int)v51;
              v54 = *(_DWORD *)(v44 + v51);
              if ( v54 == 64 )
              {
                if ( v53 + 40 <= v52 )
                {
                  if ( *(_BYTE *)(v44 + v53 + 10) )
                    goto LABEL_97;
                  goto LABEL_98;
                }
              }
              else
              {
                v150 = v54 - 65;
                if ( v150 )
                {
                  if ( v150 == 1 && v53 + 40 <= v52 )
                  {
LABEL_279:
                    if ( *(_DWORD *)(v44 + v53 + 12) )
                      v48 = (unsigned __int8 *)(v53 + v44 + 32);
                    v13 = *(_QWORD *)(v44 + v53 + 24);
                    v47 = *(_BYTE *)(v44 + v53 + 8);
                    v49 = *(_BYTE *)(v44 + v53 + 9);
LABEL_320:
                    if ( !v48 )
                      goto LABEL_54;
                    LODWORD(v72) = *v48;
LABEL_169:
                    LOBYTE(v72) = v72 - 8;
                    if ( (v72 & 0x5D) != 0 )
                      goto LABEL_54;
                    v73 = *(_BYTE *)(v44 + 3);
                    if ( v73 == 1 || !v13 )
                    {
LABEL_172:
                      v74 = 0;
                      v75 = 0;
                      LOBYTE(v44) = 0;
                      goto LABEL_173;
                    }
LABEL_186:
                    if ( !v49 )
                      goto LABEL_172;
                    LOBYTE(v44) = 0;
                    v75 = 0;
                    v74 = 0;
                    v72 = v13 + v49;
                    v80 = v13 + 8;
                    if ( (unsigned __int8)((*(_BYTE *)v13 & 0x7F) - 114) <= 1u )
                    {
                      if ( v80 <= v72 )
                      {
                        LODWORD(v44) = *(unsigned __int8 *)(v13 + 1);
                        v75 = *(_BYTE *)(v13 + 2);
                        LOBYTE(v44) = v44 & 0xF;
                        v74 = *(_BYTE *)(v13 + 3);
                        goto LABEL_195;
                      }
                    }
                    else if ( v80 <= v72 )
                    {
                      v81 = (char *)(v13 + 13);
                      LODWORD(v44) = *(unsigned __int8 *)(v13 + 2);
                      LOBYTE(v44) = v44 & 0xF;
                      v82 = v49;
                      if ( (unsigned int)*(unsigned __int8 *)(v13 + 7) + 8 <= v49 )
                        v82 = *(unsigned __int8 *)(v13 + 7) + 8;
                      v72 = v13 + v82;
                      if ( (unsigned __int64)v81 <= v72 )
                        v75 = *(_BYTE *)(v13 + 12);
                      if ( v13 + 14 > v72 )
                        v74 = 0;
                      else
                        v74 = *v81;
LABEL_195:
                      v83 = 1;
LABEL_555:
                      if ( !v83 )
                        goto LABEL_172;
LABEL_173:
                      McTemplateK0pduuuuup_EtwWriteTransfer(
                        v72,
                        v44,
                        (unsigned int)&v230,
                        a2,
                        *(_DWORD *)(a2 + 48),
                        v73,
                        v47,
                        v44,
                        v75,
                        v74,
                        a2);
                      goto LABEL_54;
                    }
                    v83 = 0;
                    goto LABEL_555;
                  }
                }
                else if ( v53 + 56 <= v52 )
                {
LABEL_219:
                  if ( *(_BYTE *)(v44 + v53 + 10) )
LABEL_97:
                    v48 = (unsigned __int8 *)(v53 + v44 + 24);
LABEL_98:
                  v13 = *(_QWORD *)(v44 + v53 + 16);
                  v47 = *(_BYTE *)(v44 + v53 + 8);
                  v49 = *(_BYTE *)(v44 + v53 + 9);
                  goto LABEL_320;
                }
              }
            }
          }
          if ( ++v50 >= v46 )
            goto LABEL_320;
        }
      }
      goto LABEL_168;
    }
    goto LABEL_151;
  }
  v11 = *(_DWORD **)(v5 + 24);
  if ( *v11 == 1314275652 )
  {
    v12 = (__int64)v11 + 282;
  }
  else if ( *v11 == 1094997074 )
  {
    v12 = (__int64)v11 + 466;
  }
  else
  {
    v12 = 98;
  }
  v13 = 0;
  if ( *(_BYTE *)(v8 + 2) != 40 )
  {
    v15 = *(_DWORD *)(v8 + 12);
    v14 = 0;
    v227 = v15;
    v16 = *(unsigned __int8 *)(v8 + 2);
    goto LABEL_14;
  }
  if ( *(_BYTE *)v12 != 1 )
  {
    *(_BYTE *)(v8 + 3) = 6;
    *(_QWORD *)(a2 + 56) = 0;
    v55 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
    v56 = *(_DWORD *)(v55 + *(_QWORD *)(v5 + 40));
    while ( (v56 & 1) == 0 )
    {
      v57 = v56;
      v56 = _InterlockedCompareExchange((volatile signed __int32 *)(v55 + *(_QWORD *)(v5 + 40)), v56 - 2, v56);
      if ( v57 == v56 )
        goto LABEL_105;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 1032), 0xFFFFFFFF) == 1 )
      KeSetEvent((PRKEVENT)(v5 + 520), 0, 0);
LABEL_105:
    v68 = StorEtwLoggingEnabled == 0;
    v10 = -1073741637;
    *(_DWORD *)(a2 + 48) = -1073741637;
    *(_BYTE *)(a2 + 141) = -84;
    if ( v68 )
      goto LABEL_54;
    v230 = 0;
    IoGetActivityIdIrp(a2, &v230);
    v43 = *(unsigned __int8 **)(a2 + 184);
    v28 = *v43;
    if ( (_BYTE)v28 == 15 )
    {
      if ( byte_140177431 >= 0 )
        goto LABEL_54;
      v44 = *((_QWORD *)v43 + 1);
      v45 = *(unsigned __int8 *)(v44 + 2);
      if ( (_BYTE)v45 == 40 )
      {
        if ( *(_DWORD *)(v44 + 20) )
          goto LABEL_54;
        v58 = *(_DWORD *)(v44 + 56);
        if ( !v58 )
          goto LABEL_54;
        v47 = 0;
        v48 = 0;
        v49 = 0;
        v59 = 0;
        while ( 1 )
        {
          v60 = *(unsigned int *)(v44 + 4LL * v59 + 120);
          if ( (unsigned int)v60 >= 0x80 )
          {
            v61 = *(unsigned int *)(v44 + 16);
            if ( (unsigned int)v60 < (unsigned int)v61 )
            {
              v53 = (unsigned int)v60;
              v62 = *(_DWORD *)(v44 + v60);
              if ( v62 == 64 )
              {
                if ( v53 + 40 <= v61 )
                  goto LABEL_219;
              }
              else
              {
                v151 = v62 - 65;
                if ( v151 )
                {
                  if ( v151 == 1 && v53 + 40 <= v61 )
                    goto LABEL_279;
                }
                else if ( v53 + 56 <= v61 )
                {
                  goto LABEL_219;
                }
              }
            }
          }
          if ( ++v59 >= v58 )
            goto LABEL_320;
        }
      }
      goto LABEL_168;
    }
LABEL_151:
    if ( (_BYTE)v28 == 14 )
      goto LABEL_100;
    if ( (_BYTE)v28 != 27 )
      goto LABEL_54;
    if ( v43[1] != 7 )
      goto LABEL_120;
    v68 = *((_DWORD *)v43 + 2) == 0;
    goto LABEL_147;
  }
  if ( *(_DWORD *)(v8 + 8) != 1397899864
    || *(_DWORD *)(v8 + 48)
    || (v14 = v8, v15 = *(_DWORD *)(v8 + 24), v16 = *(_DWORD *)(v8 + 20), v227 = v15, *(_QWORD *)(v8 + 72)) )
  {
    *(_BYTE *)(v8 + 3) = 6;
    *(_QWORD *)(a2 + 56) = 0;
    v223 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
    v185 = *(_DWORD *)(v223 + *(_QWORD *)(v5 + 40));
    while ( (v185 & 1) == 0 )
    {
      v186 = v185;
      v185 = _InterlockedCompareExchange((volatile signed __int32 *)(v223 + *(_QWORD *)(v5 + 40)), v185 - 2, v185);
      if ( v186 == v185 )
        goto LABEL_427;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 1032), 0xFFFFFFFF) == 1 )
      KeSetEvent((PRKEVENT)(v5 + 520), 0, 0);
LABEL_427:
    v68 = StorEtwLoggingEnabled == 0;
    v10 = -1073741811;
    *(_DWORD *)(a2 + 48) = -1073741811;
    *(_BYTE *)(a2 + 141) = -84;
    if ( v68 )
      goto LABEL_54;
    v230 = 0;
    IoGetActivityIdIrp(a2, &v230);
    v27 = *(char **)(a2 + 184);
    v187 = *v27;
    if ( *v27 == 15 )
    {
      if ( byte_140177431 >= 0 )
        goto LABEL_54;
      v44 = *((_QWORD *)v27 + 1);
      v45 = *(unsigned __int8 *)(v44 + 2);
      if ( (_BYTE)v45 == 40 )
      {
        if ( *(_DWORD *)(v44 + 20) )
          goto LABEL_54;
        v188 = *(_DWORD *)(v44 + 56);
        if ( !v188 )
          goto LABEL_54;
        v47 = 0;
        v48 = 0;
        v49 = 0;
        v153 = 0;
        while ( 1 )
        {
          v154 = *(unsigned int *)(v44 + 4LL * v153 + 120);
          if ( (unsigned int)v154 >= 0x80 )
          {
            v155 = *(unsigned int *)(v44 + 16);
            if ( (unsigned int)v154 < (unsigned int)v155 )
            {
              v156 = (unsigned int)v154;
              v157 = *(_DWORD *)(v154 + v44);
              if ( v157 == 64 )
              {
                if ( v156 + 40 <= v155 )
                {
LABEL_287:
                  if ( *(_BYTE *)(v156 + v44 + 10) )
LABEL_184:
                    v48 = (unsigned __int8 *)(v156 + v44 + 24);
LABEL_185:
                  v13 = *(_QWORD *)(v156 + v44 + 16);
                  v47 = *(_BYTE *)(v156 + v44 + 8);
                  v49 = *(_BYTE *)(v156 + v44 + 9);
                  goto LABEL_320;
                }
              }
              else
              {
                v152 = v157 - 65;
                if ( v152 )
                {
                  if ( v152 == 1 && v156 + 40 <= v155 )
                  {
LABEL_282:
                    if ( *(_DWORD *)(v156 + v44 + 12) )
                      v48 = (unsigned __int8 *)(v156 + v44 + 32);
                    v13 = *(_QWORD *)(v156 + v44 + 24);
                    v47 = *(_BYTE *)(v156 + v44 + 8);
                    v49 = *(_BYTE *)(v156 + v44 + 9);
                    goto LABEL_320;
                  }
                }
                else if ( v156 + 56 <= v155 )
                {
LABEL_285:
                  if ( *(_BYTE *)(v156 + v44 + 10) )
                    goto LABEL_184;
                  goto LABEL_185;
                }
              }
            }
          }
          if ( ++v153 >= v188 )
            goto LABEL_320;
        }
      }
      goto LABEL_168;
    }
    if ( v187 == 14 )
      goto LABEL_100;
    if ( v187 != 27 )
      goto LABEL_54;
    if ( v27[1] != 7 )
      goto LABEL_120;
    v68 = *((_DWORD *)v27 + 2) == 0;
    goto LABEL_147;
  }
LABEL_14:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids, v5, a2, v16);
    v15 = v227;
  }
  if ( (v15 & 0x100000) != 0 )
  {
    if ( (unsigned __int8)RaidAdapterIsRegisteredForIdleDetection(*(_QWORD *)(v5 + 24))
      && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 24) + 5024LL) + 20LL) & 1) == 0
      || (v63 = *(_QWORD *)(v5 + 24), (*(_BYTE *)(v63 + 107) & 4) != 0)
      || *(_DWORD *)(v63 + 332) != 1 )
    {
      *(_BYTE *)(v8 + 3) = 36;
      *(_QWORD *)(a2 + 56) = 0;
      v64 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
      v65 = *(_DWORD *)(v64 + *(_QWORD *)(v5 + 40));
      while ( (v65 & 1) == 0 )
      {
        v66 = v65;
        v65 = _InterlockedCompareExchange((volatile signed __int32 *)(v64 + *(_QWORD *)(v5 + 40)), v65 - 2, v65);
        if ( v66 == v65 )
          goto LABEL_140;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 1032), 0xFFFFFFFF) == 1 )
        KeSetEvent((PRKEVENT)(v5 + 520), 0, 0);
LABEL_140:
      v68 = StorEtwLoggingEnabled == 0;
      v10 = -1073741823;
      *(_DWORD *)(a2 + 48) = -1073741823;
      *(_BYTE *)(a2 + 141) = -84;
      if ( v68 )
        goto LABEL_54;
      v230 = 0;
      IoGetActivityIdIrp(a2, &v230);
      v27 = *(char **)(a2 + 184);
      v67 = *v27;
      if ( *v27 != 15 )
      {
        if ( v67 != 14 )
        {
          if ( v67 != 27 )
            goto LABEL_54;
          if ( v27[1] != 7 )
            goto LABEL_120;
          v68 = *((_DWORD *)v27 + 2) == 0;
          goto LABEL_147;
        }
LABEL_100:
        if ( (byte_140177432 & 8) != 0 )
          McTemplateK0pd_EtwWriteTransfer(v28, EventNonReadWriteRequestComplete, &v230, a2, *(_DWORD *)(a2 + 48));
        goto LABEL_54;
      }
      if ( byte_140177431 >= 0 )
        goto LABEL_54;
      v44 = *((_QWORD *)v27 + 1);
      v45 = *(unsigned __int8 *)(v44 + 2);
      if ( (_BYTE)v45 == 40 )
      {
        if ( !*(_DWORD *)(v44 + 20) )
        {
          v189 = *(_DWORD *)(v44 + 56);
          if ( v189 )
          {
            v47 = 0;
            v48 = 0;
            v49 = 0;
            v159 = 0;
            while ( 1 )
            {
              v160 = *(unsigned int *)(v44 + 4LL * v159 + 120);
              if ( (unsigned int)v160 >= 0x80 )
              {
                v161 = *(unsigned int *)(v44 + 16);
                if ( (unsigned int)v160 < (unsigned int)v161 )
                {
                  v156 = (unsigned int)v160;
                  v162 = *(_DWORD *)(v160 + v44);
                  if ( v162 == 64 )
                  {
                    if ( v156 + 40 <= v161 )
                      goto LABEL_287;
                  }
                  else
                  {
                    v158 = v162 - 65;
                    if ( v158 )
                    {
                      if ( v158 == 1 && v156 + 40 <= v161 )
                        goto LABEL_282;
                    }
                    else if ( v156 + 56 <= v161 )
                    {
                      goto LABEL_285;
                    }
                  }
                }
              }
              if ( ++v159 >= v189 )
                goto LABEL_320;
            }
          }
        }
        goto LABEL_54;
      }
LABEL_168:
      LODWORD(v72) = *(unsigned __int8 *)(v44 + 72);
      v13 = *(_QWORD *)(v44 + 32);
      v49 = *(_BYTE *)(v44 + 11);
      v47 = *(_BYTE *)(v44 + 4);
      if ( v45 )
        goto LABEL_54;
      goto LABEL_169;
    }
  }
  switch ( v16 )
  {
    case 0:
      if ( *(_BYTE *)(v8 + 2) != 40 )
      {
        v17 = (_BYTE *)(v8 + 72);
        goto LABEL_31;
      }
      v17 = 0;
      if ( *(_BYTE *)(v14 + 2) == 40 && !*(_DWORD *)(v14 + 20) )
      {
        v18 = *(_DWORD *)(v14 + 56);
        if ( v18 )
        {
          v19 = 0;
          while ( 1 )
          {
            v20 = *(unsigned int *)(v14 + 4LL * v19 + 120);
            if ( (unsigned int)v20 < 0x80 )
              goto LABEL_28;
            v21 = *(unsigned int *)(v14 + 16);
            if ( (unsigned int)v20 >= (unsigned int)v21 )
              goto LABEL_28;
            v22 = *(_DWORD *)(v20 + v14);
            v23 = v20 + v14;
            if ( v22 == 64 )
              break;
            v35 = v22 - 65;
            if ( !v35 )
            {
              v24 = v20 + 56;
LABEL_27:
              if ( v24 <= v21 )
              {
                if ( *(_BYTE *)(v23 + 10) )
                  v17 = (_BYTE *)(v23 + 24);
                goto LABEL_31;
              }
              goto LABEL_28;
            }
            if ( v35 == 1 && v20 + 40 <= v21 )
            {
              if ( *(_DWORD *)(v23 + 12) )
                v17 = (_BYTE *)(v23 + 32);
              goto LABEL_31;
            }
LABEL_28:
            if ( ++v19 >= v18 )
              goto LABEL_31;
          }
          v24 = v20 + 40;
          goto LABEL_27;
        }
      }
LABEL_31:
      if ( !v17 )
        goto LABEL_35;
      if ( *v17 == 27 && (v17[4] & 1) == 0 && (unsigned __int8)RaUnitSwallowStopUnitCommand(v5) )
      {
        v68 = StorEtwLoggingEnabled == 0;
        *(_BYTE *)(v8 + 3) = 1;
        *(_QWORD *)(a2 + 56) = 0;
        *(_BYTE *)(a2 + 141) = -84;
        *(_DWORD *)(a2 + 48) = 0;
        if ( !v68 )
        {
          v230 = 0;
          IoGetActivityIdIrp(a2, &v230);
          v37 = *(char **)(a2 + 184);
          v38 = *v37;
          if ( *v37 != 15 )
          {
            if ( v38 == 14 )
            {
              if ( (byte_140177432 & 8) != 0 )
                McTemplateK0pd_EtwWriteTransfer(v37, EventNonReadWriteRequestComplete, &v230, a2, *(_DWORD *)(a2 + 48));
            }
            else if ( v38 == 27 )
            {
              if ( v37[1] != 7 || *((_DWORD *)v37 + 2) )
              {
                if ( (byte_140177432 & 0x20) != 0 )
                  McTemplateK0pd_EtwWriteTransfer(v37, EventPnpRequestComplete, &v230, a2, *(_DWORD *)(a2 + 48));
              }
              else if ( (byte_140177432 & 0x40) != 0 )
              {
                v70 = *(int **)(a2 + 56);
                if ( v70 )
                  v71 = *v70;
                else
                  v71 = 0;
                McTemplateK0pqd_EtwWriteTransfer(v71, v36, (unsigned int)&v230, a2, v71, *(_DWORD *)(a2 + 48));
              }
            }
            goto LABEL_75;
          }
          if ( byte_140177431 < 0 )
          {
            v224 = *((_QWORD *)v37 + 1);
            if ( *(_BYTE *)(v224 + 2) != 40 )
            {
              LODWORD(v98) = *(unsigned __int8 *)(v224 + 72);
              v99 = *(_BYTE **)(v224 + 32);
              v100 = *(_BYTE *)(v224 + 11);
              v101 = *(_BYTE *)(v224 + 4);
              if ( !*(_BYTE *)(v224 + 2) )
                goto LABEL_222;
              goto LABEL_75;
            }
            if ( *(_DWORD *)(v224 + 20) )
              goto LABEL_75;
            v190 = *(_DWORD *)(v224 + 56);
            if ( !v190 )
              goto LABEL_75;
            v99 = 0;
            v100 = 0;
            v145 = 0;
            v164 = 0;
            while ( 1 )
            {
              v191 = *(unsigned int *)(v224 + 4LL * v164 + 120);
              if ( (unsigned int)v191 >= 0x80 )
              {
                v192 = *(unsigned int *)(v224 + 16);
                if ( (unsigned int)v191 < (unsigned int)v192 )
                {
                  v193 = (unsigned int)v191;
                  v194 = *(_DWORD *)(v224 + v191);
                  if ( v194 == 64 )
                  {
                    if ( v193 + 40 <= v192 )
                    {
LABEL_289:
                      if ( *(_BYTE *)(v224 + v193 + 10) )
                        v145 = (unsigned __int8 *)(v193 + v224 + 24);
                      v101 = *(_BYTE *)(v224 + v193 + 8);
                      v99 = *(_BYTE **)(v224 + v193 + 16);
                      v100 = *(_BYTE *)(v224 + v193 + 9);
                      goto LABEL_361;
                    }
                  }
                  else
                  {
                    v163 = v194 - 65;
                    if ( v163 )
                    {
                      if ( v163 == 1 && v193 + 40 <= v192 )
                      {
                        if ( *(_DWORD *)(v224 + v193 + 12) )
                          v145 = (unsigned __int8 *)(v193 + v224 + 32);
                        v101 = *(_BYTE *)(v224 + v193 + 8);
                        v99 = *(_BYTE **)(v224 + v193 + 24);
                        v100 = *(_BYTE *)(v224 + v193 + 9);
LABEL_361:
                        if ( !v145 )
                          break;
                        LODWORD(v98) = *v145;
LABEL_222:
                        LOBYTE(v98) = v98 - 8;
                        if ( (v98 & 0x5D) != 0 )
                          break;
                        v102 = *(_BYTE *)(v224 + 3);
                        if ( v102 == 1 || !v99 || !v100 )
                          goto LABEL_455;
                        v103 = 0;
                        v104 = 0;
                        v105 = 0;
                        v98 = (unsigned __int64)&v99[v100];
                        v106 = v99 + 8;
                        if ( (unsigned __int8)((*v99 & 0x7F) - 114) <= 1u )
                        {
                          if ( (unsigned __int64)v106 <= v98 )
                          {
                            v104 = v99[2];
                            v103 = v99[1] & 0xF;
                            v105 = v99[3];
                            goto LABEL_234;
                          }
                        }
                        else if ( (unsigned __int64)v106 <= v98 )
                        {
                          v107 = v99 + 13;
                          v103 = v99[2] & 0xF;
                          v108 = v100;
                          if ( (unsigned int)(unsigned __int8)v99[7] + 8 <= v100 )
                            v108 = (unsigned __int8)v99[7] + 8;
                          v98 = (unsigned __int64)&v99[v108];
                          if ( (unsigned __int64)v107 <= v98 )
                            v104 = v99[12];
                          if ( (unsigned __int64)(v99 + 14) > v98 )
                            v105 = 0;
                          else
                            v105 = *v107;
LABEL_234:
                          v109 = 1;
LABEL_566:
                          if ( !v109 )
                          {
LABEL_455:
                            v105 = 0;
                            v104 = 0;
                            v103 = 0;
                          }
                          McTemplateK0pduuuuup_EtwWriteTransfer(
                            v98,
                            (_DWORD)v99,
                            (unsigned int)&v230,
                            a2,
                            *(_DWORD *)(a2 + 48),
                            v102,
                            v101,
                            v103,
                            v104,
                            v105,
                            a2);
                          break;
                        }
                        v109 = 0;
                        goto LABEL_566;
                      }
                    }
                    else if ( v193 + 56 <= v192 )
                    {
                      goto LABEL_289;
                    }
                  }
                }
              }
              if ( ++v164 >= v190 )
              {
                v101 = 0;
                goto LABEL_361;
              }
            }
          }
        }
LABEL_75:
        IofCompleteRequest((PIRP)a2, 0);
        v39 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
        v40 = *(_DWORD *)(v39 + *(_QWORD *)(v5 + 40));
        while ( (v40 & 1) == 0 )
        {
          v41 = v40;
          v40 = _InterlockedCompareExchange((volatile signed __int32 *)(v39 + *(_QWORD *)(v5 + 40)), v40 - 2, v40);
          if ( v41 == v40 )
            goto LABEL_78;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 1032), 0xFFFFFFFF) == 1 )
          KeSetEvent((PRKEVENT)(v5 + 520), 0, 0);
LABEL_78:
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          goto LABEL_79;
        }
        v79 = 16;
        goto LABEL_618;
      }
      v25 = *(_QWORD *)(v5 + 24);
      if ( (*(_DWORD *)(v25 + 128) & 4) == 0 && !*(_DWORD *)(v25 + 312) )
        goto LABEL_35;
      v225 = 0;
      if ( (v227 & 0x800) != 0 && (*(_DWORD *)(v5 + 512) & 0x40) != 0 )
      {
        if ( *v17 == 53 )
        {
LABEL_619:
          v225 = 1;
          goto LABEL_620;
        }
        if ( *v17 == 27 )
        {
          if ( (v17[4] & 1) != 0 )
            goto LABEL_622;
          goto LABEL_619;
        }
      }
LABEL_620:
      if ( *v17 != 27 || (v17[4] & 1) == 0 )
      {
LABEL_623:
        if ( !v225 )
        {
LABEL_35:
          if ( !DisableIEEE1667 || !v17 )
            goto LABEL_36;
          if ( *v17 == 0xA2 )
          {
            if ( v17[1] != 0xEE )
            {
LABEL_36:
              if ( StorEtwLoggingEnabled && (byte_140177431 & 0x1E) != 0 && ((*v17 - 8) & 0x5D) == 0 )
              {
                IoGetActivityIdIrp(a2, &v231);
                StorEtwIORequestDispatch(a2);
              }
              v10 = RaidUnitSubmitRequest(v5, a2);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_qqD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  19,
                  WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids,
                  v5,
                  a2,
                  v10);
              }
              goto LABEL_42;
            }
          }
          else if ( *v17 != 0xB5 || v17[1] != 0xEE )
          {
            goto LABEL_36;
          }
          *(_BYTE *)(v8 + 3) = 4;
          *(_QWORD *)(a2 + 56) = 0;
          v226 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
          v206 = *(_DWORD *)(v226 + *(_QWORD *)(v5 + 40));
          while ( (v206 & 1) == 0 )
          {
            v207 = v206;
            v206 = _InterlockedCompareExchange((volatile signed __int32 *)(v226 + *(_QWORD *)(v5 + 40)), v206 - 2, v206);
            if ( v207 == v206 )
              goto LABEL_484;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 1032), 0xFFFFFFFF) == 1 )
            KeSetEvent((PRKEVENT)(v5 + 520), 0, 0);
LABEL_484:
          v68 = StorEtwLoggingEnabled == 0;
          v10 = -1073741637;
          *(_DWORD *)(a2 + 48) = -1073741637;
          *(_BYTE *)(a2 + 141) = -84;
          if ( v68 )
            goto LABEL_54;
          v230 = 0;
          IoGetActivityIdIrp(a2, &v230);
          v27 = *(char **)(a2 + 184);
          v208 = *v27;
          if ( *v27 == 15 )
          {
            if ( byte_140177431 >= 0 )
              goto LABEL_54;
            v127 = *((_QWORD *)v27 + 1);
            if ( *(_BYTE *)(v127 + 2) != 40 )
            {
              LODWORD(v125) = *(unsigned __int8 *)(v127 + 72);
              v13 = *(_QWORD *)(v127 + 32);
              v124 = *(_BYTE *)(v127 + 11);
              v123 = *(_BYTE *)(v127 + 4);
              if ( !*(_BYTE *)(v127 + 2) )
                goto LABEL_252;
              goto LABEL_54;
            }
            if ( *(_DWORD *)(v127 + 20) )
              goto LABEL_54;
            v209 = *(_DWORD *)(v127 + 56);
            if ( !v209 )
              goto LABEL_54;
            v123 = 0;
            v122 = 0;
            v124 = 0;
            v210 = 0;
            while ( 1 )
            {
              v211 = *(unsigned int *)(v127 + 4LL * v210 + 120);
              if ( (unsigned int)v211 >= 0x80 )
              {
                v212 = *(unsigned int *)(v127 + 16);
                if ( (unsigned int)v211 < (unsigned int)v212 )
                {
                  v213 = (unsigned int)v211;
                  v214 = *(_DWORD *)(v211 + v127);
                  if ( v214 == 64 )
                  {
                    if ( v213 + 40 <= v212 )
                    {
                      if ( *(_BYTE *)(v213 + v127 + 10) )
LABEL_249:
                        v122 = (unsigned __int8 *)(v213 + v127 + 24);
LABEL_250:
                      v13 = *(_QWORD *)(v213 + v127 + 16);
                      v123 = *(_BYTE *)(v213 + v127 + 8);
                      v124 = *(_BYTE *)(v213 + v127 + 9);
                      goto LABEL_588;
                    }
                  }
                  else
                  {
                    v167 = v214 - 65;
                    if ( v167 )
                    {
                      if ( v167 == 1 && v213 + 40 <= v212 )
                      {
                        if ( *(_DWORD *)(v213 + v127 + 12) )
                          v122 = (unsigned __int8 *)(v213 + v127 + 32);
                        v13 = *(_QWORD *)(v213 + v127 + 24);
                        v123 = *(_BYTE *)(v213 + v127 + 8);
                        v124 = *(_BYTE *)(v213 + v127 + 9);
LABEL_588:
                        if ( !v122 )
                          goto LABEL_54;
                        LODWORD(v125) = *v122;
LABEL_252:
                        LOBYTE(v125) = v125 - 8;
                        if ( (v125 & 0x5D) != 0 )
                          goto LABEL_54;
                        v126 = *(_BYTE *)(v127 + 3);
                        if ( v126 == 1 || !v13 || !v124 )
                          goto LABEL_503;
                        LOBYTE(v127) = 0;
                        v128 = 0;
                        v129 = 0;
                        v125 = v13 + v124;
                        v130 = v13 + 8;
                        if ( (unsigned __int8)((*(_BYTE *)v13 & 0x7F) - 114) <= 1u )
                        {
                          if ( v130 <= v125 )
                          {
                            LODWORD(v127) = *(unsigned __int8 *)(v13 + 1);
                            v128 = *(_BYTE *)(v13 + 2);
                            LOBYTE(v127) = v127 & 0xF;
                            v129 = *(_BYTE *)(v13 + 3);
                            goto LABEL_264;
                          }
                        }
                        else if ( v130 <= v125 )
                        {
                          v131 = (char *)(v13 + 13);
                          LODWORD(v127) = *(unsigned __int8 *)(v13 + 2);
                          LOBYTE(v127) = v127 & 0xF;
                          v132 = v124;
                          if ( (unsigned int)*(unsigned __int8 *)(v13 + 7) + 8 <= v124 )
                            v132 = *(unsigned __int8 *)(v13 + 7) + 8;
                          v125 = v13 + v132;
                          if ( (unsigned __int64)v131 <= v125 )
                            v128 = *(_BYTE *)(v13 + 12);
                          if ( v13 + 14 > v125 )
                            v129 = 0;
                          else
                            v129 = *v131;
LABEL_264:
                          v133 = 1;
LABEL_594:
                          if ( !v133 )
                          {
LABEL_503:
                            v129 = 0;
                            v128 = 0;
                            LOBYTE(v127) = 0;
                          }
                          McTemplateK0pduuuuup_EtwWriteTransfer(
                            v125,
                            v127,
                            (unsigned int)&v230,
                            a2,
                            *(_DWORD *)(a2 + 48),
                            v126,
                            v123,
                            v127,
                            v128,
                            v129,
                            a2);
LABEL_54:
                          IofCompleteRequest((PIRP)a2, 0);
                          goto LABEL_42;
                        }
                        v133 = 0;
                        goto LABEL_594;
                      }
                    }
                    else if ( v213 + 56 <= v212 )
                    {
                      if ( *(_BYTE *)(v213 + v127 + 10) )
                        goto LABEL_249;
                      goto LABEL_250;
                    }
                  }
                }
              }
              if ( ++v210 >= v209 )
                goto LABEL_588;
            }
          }
          if ( v208 == 14 )
            goto LABEL_100;
          if ( v208 != 27 )
            goto LABEL_54;
          if ( v27[1] != 7 )
            goto LABEL_120;
          v68 = *((_DWORD *)v27 + 2) == 0;
LABEL_147:
          if ( v68 )
          {
            if ( (byte_140177432 & 0x40) == 0 )
              goto LABEL_54;
            v69 = *(_DWORD **)(a2 + 56);
            if ( v69 )
              LODWORD(v13) = *v69;
LABEL_614:
            McTemplateK0pqd_EtwWriteTransfer(v28, (_DWORD)v27, (unsigned int)&v230, a2, v13, *(_DWORD *)(a2 + 48));
            goto LABEL_54;
          }
          goto LABEL_120;
        }
LABEL_457:
        v68 = StorEtwLoggingEnabled == 0;
        *(_BYTE *)(v8 + 3) = 1;
        *(_QWORD *)(a2 + 56) = 0;
        *(_BYTE *)(a2 + 141) = -84;
        *(_DWORD *)(a2 + 48) = 0;
        if ( !v68 )
        {
          v230 = 0;
          IoGetActivityIdIrp(a2, &v230);
          v197 = *(char **)(a2 + 184);
          v198 = *v197;
          if ( *v197 != 15 )
          {
            if ( v198 == 14 )
            {
              if ( (byte_140177432 & 8) != 0 )
                McTemplateK0pd_EtwWriteTransfer(v196, EventNonReadWriteRequestComplete, &v230, a2, *(_DWORD *)(a2 + 48));
            }
            else if ( v198 == 27 )
            {
              if ( v197[1] == 7 && !*((_DWORD *)v197 + 2) )
              {
                if ( (byte_140177432 & 0x40) != 0 )
                {
                  v199 = *(int **)(a2 + 56);
                  if ( v199 )
                    v200 = *v199;
                  else
                    v200 = 0;
                  McTemplateK0pqd_EtwWriteTransfer(v200, v195, (unsigned int)&v230, a2, v200, *(_DWORD *)(a2 + 48));
                }
              }
              else if ( (byte_140177432 & 0x20) != 0 )
              {
                McTemplateK0pd_EtwWriteTransfer(v196, EventPnpRequestComplete, &v230, a2, *(_DWORD *)(a2 + 48));
              }
            }
            goto LABEL_174;
          }
          if ( byte_140177431 < 0 )
          {
            v201 = *((_QWORD *)v197 + 1);
            if ( *(_BYTE *)(v201 + 2) != 40 )
            {
              LODWORD(v110) = *(unsigned __int8 *)(v201 + 72);
              v111 = *(_BYTE **)(v201 + 32);
              v112 = *(_BYTE *)(v201 + 11);
              v113 = *(_BYTE *)(v201 + 4);
              if ( !*(_BYTE *)(v201 + 2) )
                goto LABEL_236;
              goto LABEL_174;
            }
            if ( *(_DWORD *)(v201 + 20) )
              goto LABEL_174;
            v228 = *(_DWORD *)(v201 + 56);
            if ( !v228 )
              goto LABEL_174;
            v111 = 0;
            v112 = 0;
            v146 = 0;
            v166 = 0;
            while ( 1 )
            {
              v202 = *(unsigned int *)(v201 + 4LL * v166 + 120);
              if ( (unsigned int)v202 >= 0x80 )
              {
                v203 = *(unsigned int *)(v201 + 16);
                if ( (unsigned int)v202 < (unsigned int)v203 )
                {
                  v204 = (unsigned int)v202;
                  v205 = *(_DWORD *)(v201 + v202);
                  if ( v205 == 64 )
                  {
                    if ( v204 + 40 <= v203 )
                    {
LABEL_292:
                      if ( *(_BYTE *)(v201 + v204 + 10) )
                        v146 = (unsigned __int8 *)(v204 + v201 + 24);
                      v113 = *(_BYTE *)(v201 + v204 + 8);
                      v111 = *(_BYTE **)(v201 + v204 + 16);
                      v112 = *(_BYTE *)(v201 + v204 + 9);
                      goto LABEL_372;
                    }
                  }
                  else
                  {
                    v165 = v205 - 65;
                    if ( v165 )
                    {
                      if ( v165 == 1 && v204 + 40 <= v203 )
                      {
                        if ( *(_DWORD *)(v201 + v204 + 12) )
                          v146 = (unsigned __int8 *)(v204 + v201 + 32);
                        v113 = *(_BYTE *)(v201 + v204 + 8);
                        v111 = *(_BYTE **)(v201 + v204 + 24);
                        v112 = *(_BYTE *)(v201 + v204 + 9);
LABEL_372:
                        if ( !v146 )
                          break;
                        LODWORD(v110) = *v146;
LABEL_236:
                        LOBYTE(v110) = v110 - 8;
                        if ( (v110 & 0x5D) != 0 )
                          break;
                        v114 = *(_BYTE *)(v201 + 3);
                        if ( v114 == 1 || !v111 || !v112 )
                          goto LABEL_480;
                        v115 = 0;
                        v116 = 0;
                        v117 = 0;
                        v110 = (unsigned __int64)&v111[v112];
                        v118 = v111 + 8;
                        if ( (unsigned __int8)((*v111 & 0x7F) - 114) <= 1u )
                        {
                          if ( (unsigned __int64)v118 <= v110 )
                          {
                            v116 = v111[2];
                            v115 = v111[1] & 0xF;
                            v117 = v111[3];
                            goto LABEL_248;
                          }
                        }
                        else if ( (unsigned __int64)v118 <= v110 )
                        {
                          v119 = v111 + 13;
                          v115 = v111[2] & 0xF;
                          v120 = v112;
                          if ( (unsigned int)(unsigned __int8)v111[7] + 8 <= v112 )
                            v120 = (unsigned __int8)v111[7] + 8;
                          v110 = (unsigned __int64)&v111[v120];
                          if ( (unsigned __int64)v119 <= v110 )
                            v116 = v111[12];
                          if ( (unsigned __int64)(v111 + 14) > v110 )
                            v117 = 0;
                          else
                            v117 = *v119;
LABEL_248:
                          v121 = 1;
LABEL_581:
                          if ( !v121 )
                          {
LABEL_480:
                            v117 = 0;
                            v116 = 0;
                            v115 = 0;
                          }
                          McTemplateK0pduuuuup_EtwWriteTransfer(
                            v110,
                            (_DWORD)v111,
                            (unsigned int)&v230,
                            a2,
                            *(_DWORD *)(a2 + 48),
                            v114,
                            v113,
                            v115,
                            v116,
                            v117,
                            a2);
                          break;
                        }
                        v121 = 0;
                        goto LABEL_581;
                      }
                    }
                    else if ( v204 + 56 <= v203 )
                    {
                      goto LABEL_292;
                    }
                  }
                }
              }
              if ( ++v166 >= v228 )
              {
                v113 = 0;
                goto LABEL_372;
              }
            }
          }
        }
LABEL_174:
        IofCompleteRequest((PIRP)a2, 0);
        v76 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
        v77 = *(_DWORD *)(v76 + *(_QWORD *)(v5 + 40));
        while ( (v77 & 1) == 0 )
        {
          v78 = v77;
          v77 = _InterlockedCompareExchange((volatile signed __int32 *)(v76 + *(_QWORD *)(v5 + 40)), v77 - 2, v77);
          if ( v78 == v77 )
            goto LABEL_177;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 1032), 0xFFFFFFFF) == 1 )
          KeSetEvent((PRKEVENT)(v5 + 520), 0, 0);
LABEL_177:
        if ( *v17 == 53 )
        {
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            goto LABEL_79;
          }
          v79 = 17;
        }
        else
        {
          if ( *v17 != 27 )
            goto LABEL_79;
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            goto LABEL_79;
          }
          v79 = 18;
        }
LABEL_618:
        WPP_SF_qq(v42->AttachedDevice, v79, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids, v5, a2);
LABEL_79:
        v10 = 0;
        goto LABEL_42;
      }
LABEL_622:
      if ( (*(_DWORD *)(v5 + 512) & 0x20) != 0 )
        goto LABEL_457;
      goto LABEL_623;
    case 10:
      v10 = StorUnitExecuteNvmeSrb(v5, a2);
      goto LABEL_42;
    case 7:
LABEL_57:
      v30 = RaidUnitSubmitRequest(v5, a2);
      v31 = 0;
LABEL_58:
      v10 = v30;
      goto LABEL_59;
    case 8:
      v30 = RaUnitFlushSrb(v5, a2);
      v31 = v30 != 259;
      goto LABEL_58;
  }
  v31 = 1;
  switch ( v16 )
  {
    case 1:
      v30 = RaUnitClaimDeviceSrb(v5, a2);
      goto LABEL_58;
    case 2:
    case 9:
      goto LABEL_57;
    case 4:
      v30 = RaUnitReleaseQueueSrb(v5, a2);
      goto LABEL_58;
    case 6:
      v30 = RaUnitReleaseDeviceSrb(v5, a2);
      goto LABEL_58;
    case 16:
    case 19:
    case 32:
      v30 = RaidUnitSubmitResetRequest(v5, a2);
      goto LABEL_58;
    case 18:
      v30 = RaUnitResetBusSrb(v5, a2);
      goto LABEL_58;
    case 21:
      v30 = RaUnitFlushQueueSrb(v5, a2);
      goto LABEL_58;
    case 23:
      v68 = StorEtwLoggingEnabled == 0;
      v10 = -1073741808;
      *(_DWORD *)(a2 + 48) = -1073741808;
      *(_BYTE *)(a2 + 141) = -84;
      if ( v68 )
        goto LABEL_513;
      v230 = 0;
      IoGetActivityIdIrp(a2, &v230);
      v216 = *(char **)(a2 + 184);
      v217 = *v216;
      if ( *v216 == 15 )
      {
        if ( byte_140177431 >= 0 )
          goto LABEL_513;
        v138 = *((_QWORD *)v216 + 1);
        if ( *(_BYTE *)(v138 + 2) != 40 )
        {
          LODWORD(v134) = *(unsigned __int8 *)(v138 + 72);
          v13 = *(_QWORD *)(v138 + 32);
          v135 = *(_BYTE *)(v138 + 11);
          v136 = *(_BYTE *)(v138 + 4);
          if ( *(_BYTE *)(v138 + 2) )
            goto LABEL_513;
          goto LABEL_266;
        }
        if ( !*(_DWORD *)(v138 + 20) )
        {
          v229 = *(_DWORD *)(v138 + 56);
          if ( v229 )
          {
            v135 = 0;
            v147 = 0;
            v169 = 0;
            while ( 1 )
            {
              v219 = *(unsigned int *)(v138 + 4LL * v169 + 120);
              if ( (unsigned int)v219 >= 0x80 )
              {
                v220 = *(unsigned int *)(v138 + 16);
                if ( (unsigned int)v219 < (unsigned int)v220 )
                {
                  v221 = (unsigned int)v219;
                  v222 = *(_DWORD *)(v219 + v138);
                  if ( v222 == 64 )
                  {
                    if ( v221 + 40 <= v220 )
                    {
LABEL_295:
                      if ( *(_BYTE *)(v221 + v138 + 10) )
                        v147 = (unsigned __int8 *)(v221 + v138 + 24);
                      v136 = *(_BYTE *)(v221 + v138 + 8);
                      v13 = *(_QWORD *)(v221 + v138 + 16);
                      v135 = *(_BYTE *)(v221 + v138 + 9);
                      goto LABEL_392;
                    }
                  }
                  else
                  {
                    v168 = v222 - 65;
                    if ( v168 )
                    {
                      if ( v168 == 1 && v221 + 40 <= v220 )
                      {
                        if ( *(_DWORD *)(v221 + v138 + 12) )
                          v147 = (unsigned __int8 *)(v221 + v138 + 32);
                        v136 = *(_BYTE *)(v221 + v138 + 8);
                        v13 = *(_QWORD *)(v221 + v138 + 24);
                        v135 = *(_BYTE *)(v221 + v138 + 9);
LABEL_392:
                        if ( !v147 )
                          break;
                        LODWORD(v134) = *v147;
LABEL_266:
                        LOBYTE(v134) = v134 - 8;
                        if ( (v134 & 0x5D) != 0 )
                          break;
                        v137 = *(_BYTE *)(v138 + 3);
                        if ( v137 == 1 || !v13 || !v135 )
                          goto LABEL_529;
                        LOBYTE(v138) = 0;
                        v139 = 0;
                        v140 = 0;
                        v134 = v13 + v135;
                        v141 = v13 + 8;
                        if ( (unsigned __int8)((*(_BYTE *)v13 & 0x7F) - 114) <= 1u )
                        {
                          if ( v141 <= v134 )
                          {
                            LODWORD(v138) = *(unsigned __int8 *)(v13 + 1);
                            v139 = *(_BYTE *)(v13 + 2);
                            LOBYTE(v138) = v138 & 0xF;
                            v140 = *(_BYTE *)(v13 + 3);
                            goto LABEL_278;
                          }
                        }
                        else if ( v141 <= v134 )
                        {
                          v142 = (char *)(v13 + 13);
                          LODWORD(v138) = *(unsigned __int8 *)(v13 + 2);
                          LOBYTE(v138) = v138 & 0xF;
                          v143 = v135;
                          if ( (unsigned int)*(unsigned __int8 *)(v13 + 7) + 8 <= v135 )
                            v143 = *(unsigned __int8 *)(v13 + 7) + 8;
                          v134 = v13 + v143;
                          if ( (unsigned __int64)v142 <= v134 )
                            v139 = *(_BYTE *)(v13 + 12);
                          if ( v13 + 14 > v134 )
                            v140 = 0;
                          else
                            v140 = *v142;
LABEL_278:
                          v144 = 1;
LABEL_607:
                          if ( !v144 )
                          {
LABEL_529:
                            v140 = 0;
                            v139 = 0;
                            LOBYTE(v138) = 0;
                          }
                          McTemplateK0pduuuuup_EtwWriteTransfer(
                            v134,
                            v138,
                            (unsigned int)&v230,
                            a2,
                            *(_DWORD *)(a2 + 48),
                            v137,
                            v136,
                            v138,
                            v139,
                            v140,
                            a2);
                          break;
                        }
                        v144 = 0;
                        goto LABEL_607;
                      }
                    }
                    else if ( v221 + 56 <= v220 )
                    {
                      goto LABEL_295;
                    }
                  }
                }
              }
              if ( ++v169 >= v229 )
              {
                v136 = 0;
                goto LABEL_392;
              }
            }
          }
        }
      }
      else if ( v217 == 14 )
      {
        if ( (byte_140177432 & 8) != 0 )
          McTemplateK0pd_EtwWriteTransfer(v215, EventNonReadWriteRequestComplete, &v230, a2, *(_DWORD *)(a2 + 48));
      }
      else if ( v217 == 27 )
      {
        if ( v216[1] == 7 && !*((_DWORD *)v216 + 2) )
        {
          if ( (byte_140177432 & 0x40) != 0 )
          {
            v218 = *(_DWORD **)(a2 + 56);
            if ( v218 )
              LODWORD(v13) = *v218;
            McTemplateK0pqd_EtwWriteTransfer(v215, (_DWORD)v216, (unsigned int)&v230, a2, v13, *(_DWORD *)(a2 + 48));
          }
        }
        else if ( (byte_140177432 & 0x20) != 0 )
        {
          McTemplateK0pd_EtwWriteTransfer(v215, EventPnpRequestComplete, &v230, a2, *(_DWORD *)(a2 + 48));
        }
      }
LABEL_513:
      IofCompleteRequest((PIRP)a2, 0);
      break;
    case 24:
      v30 = RaUnitLockQueueSrb(v5, a2);
      goto LABEL_58;
    case 25:
      v30 = RaUnitUnlockQueueSrb(v5, a2);
      goto LABEL_58;
    case 26:
      v30 = RaUnitQuiesceDeviceSrb(v5, a2);
      v31 = v30 != 259;
      goto LABEL_58;
    default:
      v30 = RaUnitUnknownSrb(v5, a2);
      goto LABEL_58;
  }
LABEL_59:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids, v5, a2, v10);
  }
  if ( v31 )
  {
    v32 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
    v33 = *(_DWORD *)(v32 + *(_QWORD *)(v5 + 40));
    while ( (v33 & 1) == 0 )
    {
      v34 = v33;
      v33 = _InterlockedCompareExchange((volatile signed __int32 *)(v32 + *(_QWORD *)(v5 + 40)), v33 - 2, v33);
      if ( v34 == v33 )
        goto LABEL_42;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 1032), 0xFFFFFFFF) == 1 )
      KeSetEvent((PRKEVENT)(v5 + 520), 0, 0);
  }
LABEL_42:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_61bd6e0e791f31e2ffa75bd9431aea96_Traceguids, a1, a2, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x140015200  push    rbp
0x140015202  push    rsi
0x140015203  push    r13
0x140015205  lea     rbp, [rsp-47h]
0x14001520a  sub     rsp, 0B0h
0x140015211  mov     rax, cs:__security_cookie
0x140015218  xor     rax, rsp
0x14001521b  mov     [rbp+57h+var_38], rax
0x14001521f  mov     [rsp+0C0h+var_18], rdi
0x140015227  mov     rsi, rdx
0x14001522a  mov     r13, rcx
0x14001522d  mov     rcx, cs:WPP_GLOBAL_Control
0x140015234  lea     rax, WPP_GLOBAL_Control
0x14001523b  cmp     rcx, rax
0x14001523e  jz      short loc_14001524B
0x140015240  mov     eax, [rcx+2Ch]
0x140015243  test    al, 8
0x140015245  jnz     loc_140016F0F
0x14001524b  mov     [rsp+0C0h+arg_10], rbx
0x140015253  mov     byte ptr [rsi+8Dh], 0A8h
0x14001525a  mov     rdi, [r13+40h]
0x14001525e  mov     [rsp+0C0h+var_20], r12
0x140015266  mov     [rsp+0C0h+var_28], r14
0x14001526e  mov     [rsp+0C0h+var_30], r15
0x140015276  mov     eax, [rdi]
0x140015278  cmp     eax, 554E4954h
0x14001527d  jnz     loc_140016F3B
0x140015283  mov     rax, [rsi+0B8h]
0x14001528a  xorps   xmm0, xmm0
0x14001528d  movups  [rbp+57h+var_48], xmm0
0x140015291  mov     rbx, [rax+8]
0x140015295  test    rbx, rbx
0x140015298  jz      loc_1400154F6
0x14001529e  mov     r8b, 1
0x1400152a1  mov     rdx, rsi
0x1400152a4  mov     rcx, rdi
0x1400152a7  call    RaUnitAcquireRemoveLock
0x1400152ac  mov     r14d, eax
0x1400152af  test    eax, eax
0x1400152b1  js      loc_14001573A
0x1400152b7  mov     rax, [rdi+18h]
0x1400152bb  mov     ecx, [rax]
0x1400152bd  cmp     ecx, 4E564144h
0x1400152c3  jz      loc_1400154D7
0x1400152c9  cmp     ecx, 41445452h
0x1400152cf  jnz     loc_140015BB0
0x1400152d5  lea     rcx, [rax+1D2h]
0x1400152dc  movzx   eax, byte ptr [rbx+2]
0x1400152e0  xor     r12d, r12d
0x1400152e3  cmp     al, 28h ; '('
0x1400152e5  jnz     loc_1400154C6
0x1400152eb  cmp     byte ptr [rcx], 1
0x1400152ee  jnz     loc_140015862
0x1400152f4  cmp     dword ptr [rbx+8], 53524258h
0x1400152fb  jnz     loc_140017023
0x140015301  cmp     [rbx+30h], r12d
0x140015305  jnz     loc_140017023
0x14001530b  mov     r15, rbx
0x14001530e  mov     edx, [rbx+18h]
0x140015311  mov     r14d, [rbx+14h]
0x140015315  mov     [rbp+57h+var_60], edx
0x140015318  cmp     [rbx+48h], r12
0x14001531c  jnz     loc_140017023
0x140015322  mov     rcx, cs:WPP_GLOBAL_Control
0x140015329  lea     rax, WPP_GLOBAL_Control
0x140015330  cmp     rcx, rax
0x140015333  jz      short loc_140015340
0x140015335  mov     eax, [rcx+2Ch]
0x140015338  test    al, 8
0x14001533a  jnz     loc_140017047
0x140015340  bt      edx, 14h
0x140015344  jb      loc_140015A5C
0x14001534a  test    r14d, r14d
0x14001534d  jnz     loc_140015563
0x140015353  cmp     byte ptr [rbx+2], 28h ; '('
0x140015357  jnz     short loc_1400153B6
0x140015359  cmp     byte ptr [r15+2], 28h ; '('
0x14001535e  mov     r14, r12
0x140015361  jnz     short loc_1400153BA
0x140015363  cmp     [r15+14h], r12d
0x140015367  jnz     short loc_1400153BA
0x140015369  mov     r11d, [r15+38h]
0x14001536d  test    r11d, r11d
0x140015370  jz      short loc_1400153BA
0x140015372  mov     r9d, r12d
0x140015375  mov     eax, r9d
0x140015378  mov     ecx, [r15+rax*4+78h]
0x14001537d  cmp     ecx, 80h
0x140015383  jb      short loc_1400153AC
0x140015385  mov     edx, [r15+10h]
0x140015389  cmp     ecx, edx
0x14001538b  jnb     short loc_1400153AC
0x14001538d  mov     r10d, [rcx+r15]
0x140015391  lea     r8, [rcx+r15]
0x140015395  cmp     r10d, 40h ; '@'
0x140015399  jnz     loc_1400155DA
0x14001539f  add     rcx, 28h ; '('
0x1400153a3  cmp     rcx, rdx
0x1400153a6  jbe     loc_1400154E3
0x1400153ac  inc     r9d
0x1400153af  cmp     r9d, r11d
0x1400153b2  jb      short loc_140015375
0x1400153b4  jmp     short loc_1400153BA
0x1400153b6  lea     r14, [rbx+48h]
0x1400153ba  test    r14, r14
0x1400153bd  jz      short loc_1400153E9
0x1400153bf  cmp     byte ptr [r14], 1Bh
0x1400153c3  jz      loc_14001560E
0x1400153c9  mov     rcx, [rdi+18h]
0x1400153cd  mov     eax, [rcx+80h]
0x1400153d3  test    al, 4
0x1400153d5  jnz     loc_1400170E4
0x1400153db  mov     eax, [rcx+138h]
0x1400153e1  test    eax, eax
0x1400153e3  jnz     loc_1400170E4
0x1400153e9  cmp     cs:DisableIEEE1667, r12b
0x1400153f0  jnz     loc_140017159
0x1400153f6  cmp     cs:StorEtwLoggingEnabled, r12b
0x1400153fd  jz      short loc_14001542D
0x1400153ff  test    cs:byte_140177431, 1Eh
0x140015406  jz      short loc_14001542D
0x140015408  movzx   eax, byte ptr [r14]
0x14001540c  sub     al, 8
0x14001540e  test    al, 5Dh
0x140015410  jnz     short loc_14001542D
0x140015412  lea     rdx, [rbp+57h+var_48]
0x140015416  mov     rcx, rsi
0x140015419  call    cs:__imp_IoGetActivityIdIrp
0x140015420  nop     dword ptr [rax+rax+00h]
0x140015425  mov     rcx, rsi
0x140015428  call    StorEtwIORequestDispatch
0x14001542d  mov     rdx, rsi
0x140015430  mov     rcx, rdi
0x140015433  call    RaidUnitSubmitRequest
0x140015438  mov     r14d, eax
0x14001543b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015442  lea     rax, WPP_GLOBAL_Control
0x140015449  cmp     rcx, rax
0x14001544c  jz      short loc_140015459
0x14001544e  mov     eax, [rcx+2Ch]
0x140015451  test    al, 8
0x140015453  jnz     loc_1400171D2
0x140015459  mov     rcx, cs:WPP_GLOBAL_Control
0x140015460  lea     rax, WPP_GLOBAL_Control
0x140015467  mov     r15, [rsp+0C0h+var_30]
0x14001546f  mov     r12, [rsp+0C0h+var_20]
0x140015477  mov     rdi, [rsp+0C0h+var_18]
0x14001547f  mov     rbx, [rsp+0C0h+arg_10]
0x140015487  cmp     rcx, rax
0x14001548a  jnz     short loc_140015495
0x14001548c  mov     eax, r14d
0x14001548f  jmp     loc_1400172A9
0x140015495  mov     eax, [rcx+2Ch]
0x140015498  test    al, 8
0x14001549a  jz      short loc_14001548C
0x14001549c  cmp     byte ptr [rcx+29h], 4
0x1400154a0  jb      short loc_14001548C
0x1400154a2  mov     rcx, [rcx+18h]
0x1400154a6  lea     r8, WPP_61bd6e0e791f31e2ffa75bd9431aea96_Traceguids
0x1400154ad  mov     edx, 13h
0x1400154b2  mov     [rsp+0C0h+var_98], r14d
0x1400154b7  mov     r9, r13
0x1400154ba  mov     [rsp+0C0h+var_A0], rsi
0x1400154bf  call    WPP_SF_qqD
0x1400154c4  jmp     short loc_14001548C
0x1400154c6  mov     edx, [rbx+0Ch]
0x1400154c9  mov     r15, r12
0x1400154cc  mov     [rbp+57h+var_60], edx
0x1400154cf  mov     r14d, eax
0x1400154d2  jmp     loc_140015322
0x1400154d7  lea     rcx, [rax+11Ah]
0x1400154de  jmp     loc_1400152DC
0x1400154e3  cmp     [r8+0Ah], r12b
0x1400154e7  jbe     loc_1400153BA
0x1400154ed  lea     r14, [r8+18h]
0x1400154f1  jmp     loc_1400153BA
0x1400154f6  xor     r12d, r12d
0x1400154f9  mov     byte ptr [rsi+8Dh], 0ACh
0x140015500  cmp     cs:StorEtwLoggingEnabled, r12b
0x140015507  mov     r14d, 0C000000Dh
0x14001550d  mov     [rsi+38h], r12
0x140015511  mov     [rsi+30h], r14d
0x140015515  jz      short loc_14001554D
0x140015517  lea     rdx, [rbp+57h+var_58]
0x14001551b  mov     rcx, rsi
0x14001551e  movups  [rbp+57h+var_58], xmm0
0x140015522  call    cs:__imp_IoGetActivityIdIrp
0x140015529  nop     dword ptr [rax+rax+00h]
0x14001552e  mov     rcx, [rsi+0B8h]
0x140015535  movzx   eax, byte ptr [rcx]
0x140015538  cmp     al, 0Fh
0x14001553a  jnz     loc_14001582E
0x140015540  cmp     cs:byte_140177431, r12b
0x140015547  jl      loc_140016FBA
0x14001554d  xor     edx, edx; PriorityBoost
0x14001554f  mov     rcx, rsi; Irp
0x140015552  call    cs:__imp_IofCompleteRequest
0x140015559  nop     dword ptr [rax+rax+00h]
0x14001555e  jmp     loc_140015459
0x140015563  cmp     r14d, 0Ah
0x140015567  jz      loc_140015A16
0x14001556d  cmp     r14d, 7
0x140015571  jnz     loc_1400156DC
0x140015577  mov     rdx, rsi; jumptable 0000000140015C06 cases 2,9
0x14001557a  mov     rcx, rdi
0x14001557d  call    RaidUnitSubmitRequest
0x140015582  xor     bl, bl
0x140015584  mov     r14d, eax
0x140015587  mov     rcx, cs:WPP_GLOBAL_Control
0x14001558e  lea     rax, WPP_GLOBAL_Control
0x140015595  cmp     rcx, rax
0x140015598  jnz     loc_1400156FE
0x14001559e  test    bl, bl
0x1400155a0  jz      loc_140015459
0x1400155a6  mov     eax, gs:1A4h
0x1400155ae  mov     r8d, eax
0x1400155b1  mov     rax, [rdi+28h]
0x1400155b5  shl     r8, 6
0x1400155b9  mov     eax, [r8+rax]
0x1400155bd  test    al, 1
0x1400155bf  jnz     loc_140015A29
0x1400155c5  mov     rcx, [rdi+28h]
0x1400155c9  lea     edx, [rax-2]
0x1400155cc  lock cmpxchg [r8+rcx], edx
0x1400155d2  jz      loc_140015459
0x1400155d8  jmp     short loc_1400155BD
0x1400155da  sub     r10d, 41h ; 'A'
0x1400155de  jz      loc_1400159CF
0x1400155e4  cmp     r10d, 1
0x1400155e8  jnz     loc_1400153AC
0x1400155ee  add     rcx, 28h ; '('
0x1400155f2  cmp     rcx, rdx
0x1400155f5  ja      loc_1400153AC
0x1400155fb  cmp     [r8+0Ch], r12d
0x1400155ff  jbe     loc_1400153BA
0x140015605  lea     r14, [r8+20h]
0x140015609  jmp     loc_1400153BA
0x14001560e  test    byte ptr [r14+4], 1
0x140015613  jnz     loc_1400153C9
0x140015619  mov     rcx, rdi
0x14001561c  call    RaUnitSwallowStopUnitCommand
0x140015621  test    al, al
0x140015623  jz      loc_1400153C9
0x140015629  cmp     cs:StorEtwLoggingEnabled, r12b
0x140015630  mov     byte ptr [rbx+3], 1
0x140015634  mov     [rsi+38h], r12
0x140015638  mov     byte ptr [rsi+8Dh], 0ACh
0x14001563f  mov     [rsi+30h], r12d
0x140015643  jz      short loc_14001567E
0x140015645  xorps   xmm0, xmm0
0x140015648  lea     rdx, [rbp+57h+var_58]
0x14001564c  mov     rcx, rsi
0x14001564f  movups  [rbp+57h+var_58], xmm0
0x140015653  call    cs:__imp_IoGetActivityIdIrp
0x14001565a  nop     dword ptr [rax+rax+00h]
0x14001565f  mov     rcx, [rsi+0B8h]
0x140015666  movzx   eax, byte ptr [rcx]
0x140015669  cmp     al, 0Fh
0x14001566b  jnz     loc_14001599F
0x140015671  cmp     cs:byte_140177431, r12b
0x140015678  jl      loc_14001707B
0x14001567e  xor     edx, edx; PriorityBoost
0x140015680  mov     rcx, rsi; Irp
0x140015683  call    cs:__imp_IofCompleteRequest
0x14001568a  nop     dword ptr [rax+rax+00h]
0x14001568f  mov     eax, gs:1A4h
0x140015697  mov     r8d, eax
0x14001569a  mov     rax, [rdi+28h]
0x14001569e  shl     r8, 6
0x1400156a2  mov     eax, [r8+rax]
0x1400156a6  test    al, 1
0x1400156a8  jnz     loc_140015B7D
0x1400156ae  mov     rcx, [rdi+28h]
0x1400156b2  lea     edx, [rax-2]
0x1400156b5  lock cmpxchg [r8+rcx], edx
0x1400156bb  jnz     short loc_1400156A6
0x1400156bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400156c4  lea     rax, WPP_GLOBAL_Control
0x1400156cb  cmp     rcx, rax
0x1400156ce  jnz     loc_1400170C5
0x1400156d4  mov     r14d, r12d
0x1400156d7  jmp     loc_140015459
0x1400156dc  cmp     r14d, 8
0x1400156e0  jnz     loc_140015BE5
0x1400156e6  mov     rdx, rsi
0x1400156e9  mov     rcx, rdi
0x1400156ec  call    RaUnitFlushSrb
0x1400156f1  cmp     eax, 103h
0x1400156f6  setnz   bl
0x1400156f9  jmp     loc_140015584
0x1400156fe  mov     eax, [rcx+2Ch]
0x140015701  test    al, 8
0x140015703  jz      loc_14001559E
0x140015709  cmp     byte ptr [rcx+29h], 4
0x14001570d  jb      loc_14001559E
0x140015713  mov     rcx, [rcx+18h]
0x140015717  lea     r8, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids
0x14001571e  mov     edx, 14h
0x140015723  mov     [rsp+0C0h+var_98], r14d
0x140015728  mov     r9, rdi
  ... truncated ...
```
