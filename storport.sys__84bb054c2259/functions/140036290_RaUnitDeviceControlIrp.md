# RaUnitDeviceControlIrp

- ea: `0x140036290`
- end: `0x1400377e3`
- name: `RaUnitDeviceControlIrp`
- size: `5459`
- prototype: ``
- caller_count: `1`
- callee_count: `72`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140034cd0`

## callees

- `0x14000129c`
- `0x140004db0`
- `0x1400172d0`
- `0x14002a778`
- `0x140036290`
- `0x1400377f0`
- `0x140037850`
- `0x1400378a8`
- `0x140046d10`
- `0x140047ab4`
- `0x14004acac`
- `0x14005a554`
- `0x140064200`
- `0x14006d1c0`
- `0x14006d298`
- `0x14006f610`
- `0x14006fb64`
- `0x14008479c`
- `0x1400848c4`
- `0x14008ee48`
- `0x140093e14`
- `0x140098968`
- `0x1400ac00c`
- `0x1400ac53c`
- `0x1400acb2c`
- `0x1400ad090`
- `0x1400ad658`
- `0x1400adbac`
- `0x1400ae144`
- `0x1400ae628`
- `0x1400aead4`
- `0x1400aeff0`
- `0x1400af5c4`
- `0x1400afb58`
- `0x1400b00e4`
- `0x1400bcc30`
- `0x1400bd0c4`
- `0x1400bf988`
- `0x1400bfdb8`
- `0x1400c0160`
- `0x1400c0510`
- `0x1400c08c0`
- `0x1400c0c60`
- `0x1400c1000`
- `0x1400c263c`
- `0x1400c3670`
- `0x1400c3a10`
- `0x1400c441c`
- `0x1400c4ac8`
- `0x1400c6450`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14003642e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400364b8`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003665e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140036f7b`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140037000`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003707f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140037172`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003642e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400364b8`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003665e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140036f7b`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140037000`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003707f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140037172`
- `ntoskrnl!KeSetEvent` at `0x140036842`
- `ntoskrnl!KeSetEvent` at `0x140036842`
- `ntoskrnl!IofCallDriver` at `0x140150819`
- `ntoskrnl!IofCallDriver` at `0x140150819`
- `ntoskrnl!IofCompleteRequest` at `0x140036468`
- `ntoskrnl!IofCompleteRequest` at `0x140036698`
- `ntoskrnl!IofCompleteRequest` at `0x140036468`
- `ntoskrnl!IofCompleteRequest` at `0x140036698`

## pseudocode

```c
__int64 __fastcall RaUnitDeviceControlIrp(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  char v4; // r12
  unsigned int v7; // r15d
  char v8; // r14
  int v9; // eax
  unsigned int inserted; // esi
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int SystemFeatureSupportIoctl; // eax
  __int64 v15; // rcx
  unsigned int v16; // eax
  bool v17; // zf
  unsigned __int64 v18; // rcx
  unsigned __int8 *v19; // rdx
  int v20; // eax
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  unsigned __int64 v24; // r8
  signed __int32 v25; // eax
  signed __int32 v26; // ett
  unsigned __int64 v27; // rcx
  unsigned __int8 *v28; // rdx
  int v29; // eax
  __int64 *v30; // rdx
  __int64 v31; // r8
  int *v32; // rax
  int v33; // ecx
  __int64 *v34; // rdx
  int *v35; // rax
  int v36; // ecx
  char v37; // cl
  _BYTE *v38; // r9
  unsigned __int8 v39; // r10
  char v40; // di
  char v41; // r15
  __int64 v42; // rdx
  char v43; // r11
  char v44; // r8
  _BYTE *v45; // rax
  char *v46; // r8
  unsigned int v47; // eax
  char v48; // cl
  _BYTE *v49; // r9
  unsigned __int8 v50; // r10
  char v51; // di
  unsigned __int64 v52; // rcx
  char v53; // si
  __int64 v54; // rdx
  char v55; // r11
  char v56; // r8
  _BYTE *v57; // rax
  char *v58; // r8
  unsigned int v59; // eax
  char v60; // cl
  _BYTE *v61; // r9
  unsigned __int8 v62; // r10
  char v63; // r12
  char v64; // r15
  __int64 v65; // rdx
  char v66; // r11
  char v67; // r8
  _BYTE *v68; // rax
  char *v69; // r8
  unsigned int v70; // eax
  char v71; // al
  char v72; // cl
  _BYTE *v73; // r9
  unsigned __int8 v74; // r11
  char v75; // r12
  char v76; // r15
  __int64 v77; // rdx
  char v78; // r10
  char v79; // r8
  _BYTE *v80; // rax
  char *v81; // r8
  unsigned int v82; // eax
  char v83; // al
  __int64 v84; // r8
  int v85; // ecx
  __int64 v86; // r12
  unsigned __int64 v87; // r15
  char *v88; // r11
  __int64 v89; // r8
  int v90; // ecx
  __int64 v91; // r12
  unsigned __int64 v92; // r15
  __int64 v93; // r8
  int v94; // ecx
  __int64 v95; // r15
  char v96; // r13
  char *v97; // r11
  int v98; // ecx
  __int64 v99; // r12
  __int64 v100; // r8
  int v101; // ecx
  __int64 v102; // r12
  char *v103; // r11
  __int64 v104; // r8
  int v105; // ecx
  __int64 v106; // r12
  char *v107; // r10
  int v108; // eax
  unsigned int v109; // r13d
  unsigned int v110; // r13d
  __int64 v111; // rdx
  __int64 *v112; // rdx
  int *v113; // rax
  int v114; // ecx
  unsigned int v115; // r12d
  unsigned __int64 v116; // rsi
  unsigned int v117; // r13d
  unsigned __int64 v118; // r15
  unsigned int v119; // r13d
  unsigned __int64 v120; // r15
  unsigned int v121; // r13d
  unsigned __int64 v122; // r15
  __int64 v123; // rcx
  char v124; // [rsp+60h] [rbp-9h]
  char v125; // [rsp+60h] [rbp-9h]
  char v126; // [rsp+60h] [rbp-9h]
  char v127; // [rsp+60h] [rbp-9h]
  char v128; // [rsp+60h] [rbp-9h]
  char v129; // [rsp+61h] [rbp-8h]
  char v130; // [rsp+61h] [rbp-8h]
  _BYTE v131[2]; // [rsp+62h] [rbp-7h] BYREF
  unsigned int v132; // [rsp+64h] [rbp-5h]
  __int128 v133; // [rsp+68h] [rbp-1h] BYREF
  __int128 v134; // [rsp+78h] [rbp+Fh] BYREF

  v3 = *(_QWORD *)(a2 + 184);
  v4 = 0;
  v131[0] = 0;
  v134 = 0;
  v7 = *(_DWORD *)(v3 + 24);
  v132 = v7;
  if ( v7 == 2955532 )
  {
    if ( *(_BYTE *)(a2 + 64) )
    {
      v17 = StorEtwLoggingEnabled == 0;
      inserted = -1073741808;
      *(_DWORD *)(a2 + 48) = -1073741808;
      *(_BYTE *)(a2 + 141) = -84;
      if ( v17 )
        goto LABEL_28;
      v133 = 0;
      IoGetActivityIdIrp(a2, &v133);
      v19 = *(unsigned __int8 **)(a2 + 184);
      if ( *v19 == 14 )
        goto LABEL_62;
      v20 = *v19 - 15;
      if ( *v19 == 15 )
      {
        if ( byte_140177431 >= 0 )
          goto LABEL_28;
        v42 = *((_QWORD *)v19 + 1);
        v8 = 1;
        v108 = *(unsigned __int8 *)(v42 + 2);
        if ( (_BYTE)v108 == 40 )
        {
          if ( *(_DWORD *)(v42 + 20) )
            goto LABEL_28;
          v109 = *(_DWORD *)(v42 + 56);
          if ( !v109 )
            goto LABEL_28;
          v40 = 0;
          v39 = 0;
          v88 = 0;
          v124 = 0;
          v38 = 0;
          v86 = 0;
          while ( 1 )
          {
            v18 = *(unsigned int *)(v42 + 4 * v86 + 120);
            if ( (unsigned int)v18 >= 0x80 )
            {
              v87 = *(unsigned int *)(v42 + 16);
              if ( (unsigned int)v18 < (unsigned int)v87 )
              {
                v84 = *(unsigned int *)(v42 + 4 * v86 + 120);
                v85 = *(_DWORD *)(v18 + v42) - 64;
                if ( v85 )
                {
                  LODWORD(v18) = v85 - 1;
                  if ( (_DWORD)v18 )
                  {
                    if ( (_DWORD)v18 == 1 )
                    {
                      LODWORD(v18) = v84 + 40;
                      if ( v84 + 40 <= v87 )
                      {
LABEL_165:
                        if ( *(_DWORD *)(v84 + v42 + 12) )
                          v88 = (char *)(v84 + v42 + 32);
                        v38 = *(_BYTE **)(v84 + v42 + 24);
LABEL_112:
                        v39 = *(_BYTE *)(v84 + v42 + 9);
                        v40 = *(_BYTE *)(v84 + v42 + 8);
                        goto LABEL_222;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v18) = v84 + 56;
                    if ( v84 + 56 <= v87 )
                    {
                      v124 = 1;
                      if ( *(_BYTE *)(v84 + v42 + 10) )
                        v88 = (char *)(v84 + v42 + 24);
                      v40 = *(_BYTE *)(v84 + v42 + 8);
                      v38 = *(_BYTE **)(v84 + v42 + 16);
                      v39 = *(_BYTE *)(v84 + v42 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v18) = v84 + 40;
                  if ( v84 + 40 <= v87 )
                  {
LABEL_172:
                    if ( *(_BYTE *)(v84 + v42 + 10) )
                      v88 = (char *)(v84 + v42 + 24);
                    v38 = *(_BYTE **)(v84 + v42 + 16);
                    goto LABEL_112;
                  }
                }
                if ( v124 )
                  goto LABEL_222;
              }
            }
            v86 = (unsigned int)(v86 + 1);
            if ( (unsigned int)v86 >= v109 )
              goto LABEL_222;
          }
        }
LABEL_98:
        v37 = *(_BYTE *)(v42 + 72);
        v38 = *(_BYTE **)(v42 + 32);
        v39 = *(_BYTE *)(v42 + 11);
        v40 = *(_BYTE *)(v42 + 4);
        if ( !v108 )
          goto LABEL_99;
        goto LABEL_28;
      }
    }
    else
    {
      v8 = 1;
      if ( *(_DWORD *)(v3 + 8) )
      {
        v17 = StorEtwLoggingEnabled == 0;
        **(_BYTE **)(a2 + 24) = (*(_BYTE *)(a1 + 504) & 4) == 0;
        *(_QWORD *)(a2 + 56) = 1;
        *(_BYTE *)(a2 + 141) = -84;
        *(_DWORD *)(a2 + 48) = 0;
        if ( v17 )
          goto LABEL_296;
        v133 = 0;
        IoGetActivityIdIrp(a2, &v133);
        v111 = *(_QWORD *)(a2 + 184);
        switch ( *(_BYTE *)v111 )
        {
          case 0xE:
            if ( (byte_140177432 & 8) == 0 )
              goto LABEL_296;
            v112 = EventNonReadWriteRequestComplete;
            break;
          case 0xF:
            if ( byte_140177431 >= 0 )
              goto LABEL_296;
            v54 = *(_QWORD *)(v111 + 8);
            if ( *(_BYTE *)(v54 + 2) != 40 )
            {
              v48 = *(_BYTE *)(v54 + 72);
              v49 = *(_BYTE **)(v54 + 32);
              v50 = *(_BYTE *)(v54 + 11);
              v51 = *(_BYTE *)(v54 + 4);
              if ( !*(_BYTE *)(v54 + 2) )
                goto LABEL_114;
              goto LABEL_296;
            }
            if ( *(_DWORD *)(v54 + 20) )
              goto LABEL_296;
            v115 = *(_DWORD *)(v54 + 56);
            if ( !v115 )
              goto LABEL_296;
            v50 = 0;
            v97 = 0;
            v51 = 0;
            v49 = 0;
            v95 = 0;
            v96 = 0;
            while ( 1 )
            {
              v52 = *(unsigned int *)(v54 + 4 * v95 + 120);
              if ( (unsigned int)v52 >= 0x80 )
              {
                v116 = *(unsigned int *)(v54 + 16);
                if ( (unsigned int)v52 < (unsigned int)v116 )
                {
                  v93 = *(unsigned int *)(v54 + 4 * v95 + 120);
                  v94 = *(_DWORD *)(v54 + v52) - 64;
                  if ( v94 )
                  {
                    LODWORD(v52) = v94 - 1;
                    if ( (_DWORD)v52 )
                    {
                      if ( (_DWORD)v52 == 1 )
                      {
                        LODWORD(v52) = v93 + 40;
                        if ( v93 + 40 <= v116 )
                        {
                          if ( *(_DWORD *)(v54 + v93 + 12) )
                            v97 = (char *)(v93 + v54 + 32);
                          v49 = *(_BYTE **)(v54 + v93 + 24);
LABEL_213:
                          v50 = *(_BYTE *)(v54 + v93 + 9);
                          v51 = *(_BYTE *)(v54 + v93 + 8);
LABEL_202:
                          if ( !v97 )
                            goto LABEL_296;
                          v48 = *v97;
LABEL_114:
                          LOBYTE(v52) = v48 - 8;
                          if ( (v52 & 0x5D) != 0 )
                            goto LABEL_296;
                          v53 = *(_BYTE *)(v54 + 3);
                          if ( v53 == 1 || !v49 || !v50 )
                            goto LABEL_324;
                          LOBYTE(v54) = 0;
                          v55 = 0;
                          v56 = 0;
                          v52 = (unsigned __int64)&v49[v50];
                          v57 = v49 + 8;
                          if ( (unsigned __int8)((*v49 & 0x7F) - 114) <= 1u )
                          {
                            if ( (unsigned __int64)v57 <= v52 )
                            {
                              v55 = v49[2];
                              LOBYTE(v54) = v49[1] & 0xF;
                              v56 = v49[3];
                              goto LABEL_352;
                            }
                          }
                          else if ( (unsigned __int64)v57 <= v52 )
                          {
                            v58 = v49 + 13;
                            LOBYTE(v54) = v49[2] & 0xF;
                            v59 = v50;
                            if ( (unsigned int)(unsigned __int8)v49[7] + 8 <= v50 )
                              v59 = (unsigned __int8)v49[7] + 8;
                            v52 = (unsigned __int64)&v49[v59];
                            if ( (unsigned __int64)v58 <= v52 )
                              v55 = v49[12];
                            if ( (unsigned __int64)(v49 + 14) > v52 )
                              v56 = 0;
                            else
                              v56 = *v58;
LABEL_352:
                            if ( !v8 )
                            {
LABEL_324:
                              LOBYTE(v54) = 0;
                              v55 = 0;
                              v56 = 0;
                            }
                            McTemplateK0pduuuuup_EtwWriteTransfer(
                              v52,
                              v54,
                              (unsigned int)&v133,
                              a2,
                              *(_DWORD *)(a2 + 48),
                              v53,
                              v51,
                              v54,
                              v55,
                              v56,
                              a2);
                            goto LABEL_296;
                          }
                          v8 = 0;
                          goto LABEL_352;
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v52) = v93 + 56;
                      if ( v93 + 56 <= v116 )
                      {
                        v96 = 1;
                        if ( *(_BYTE *)(v54 + v93 + 10) )
                          v97 = (char *)(v93 + v54 + 24);
                        v51 = *(_BYTE *)(v54 + v93 + 8);
                        v49 = *(_BYTE **)(v54 + v93 + 16);
                        v50 = *(_BYTE *)(v54 + v93 + 9);
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v52) = v93 + 40;
                    if ( v93 + 40 <= v116 )
                    {
                      if ( *(_BYTE *)(v54 + v93 + 10) )
                        v97 = (char *)(v93 + v54 + 24);
                      v49 = *(_BYTE **)(v54 + v93 + 16);
                      goto LABEL_213;
                    }
                  }
                  if ( v96 )
                    goto LABEL_202;
                }
              }
              v95 = (unsigned int)(v95 + 1);
              if ( (unsigned int)v95 >= v115 )
                goto LABEL_202;
            }
          case 0x1B:
            if ( *(_BYTE *)(v111 + 1) == 7 && !*(_DWORD *)(v111 + 8) )
            {
              if ( (byte_140177432 & 0x40) != 0 )
              {
                v113 = *(int **)(a2 + 56);
                if ( v113 )
                  v114 = *v113;
                else
                  v114 = 0;
                McTemplateK0pqd_EtwWriteTransfer(v114, v111, (unsigned int)&v133, a2, v114, *(_DWORD *)(a2 + 48));
              }
              goto LABEL_296;
            }
            if ( (byte_140177432 & 0x20) == 0 )
            {
LABEL_296:
              inserted = 0;
              goto LABEL_28;
            }
            v112 = EventPnpRequestComplete;
            break;
          default:
            goto LABEL_296;
        }
        McTemplateK0pd_EtwWriteTransfer(v52, v112, &v133, a2, *(_DWORD *)(a2 + 48));
        goto LABEL_296;
      }
      v17 = StorEtwLoggingEnabled == 0;
      inserted = -1073741789;
      *(_DWORD *)(a2 + 48) = -1073741789;
      *(_QWORD *)(a2 + 56) = 0;
      *(_BYTE *)(a2 + 141) = -84;
      if ( v17 )
        goto LABEL_28;
      v133 = 0;
      IoGetActivityIdIrp(a2, &v133);
      v19 = *(unsigned __int8 **)(a2 + 184);
      if ( *v19 == 14 )
        goto LABEL_62;
      v20 = *v19 - 15;
      if ( *v19 == 15 )
      {
        if ( byte_140177431 >= 0 )
          goto LABEL_28;
        v42 = *((_QWORD *)v19 + 1);
        v108 = *(unsigned __int8 *)(v42 + 2);
        if ( (_BYTE)v108 == 40 )
        {
          if ( *(_DWORD *)(v42 + 20) )
            goto LABEL_28;
          v110 = *(_DWORD *)(v42 + 56);
          if ( !v110 )
            goto LABEL_28;
          v40 = 0;
          v39 = 0;
          v88 = 0;
          v125 = 0;
          v38 = 0;
          v91 = 0;
          while ( 1 )
          {
            v18 = *(unsigned int *)(v42 + 4 * v91 + 120);
            if ( (unsigned int)v18 >= 0x80 )
            {
              v92 = *(unsigned int *)(v42 + 16);
              if ( (unsigned int)v18 < (unsigned int)v92 )
              {
                v89 = *(unsigned int *)(v42 + 4 * v91 + 120);
                v90 = *(_DWORD *)(v42 + v18) - 64;
                if ( v90 )
                {
                  LODWORD(v18) = v90 - 1;
                  if ( (_DWORD)v18 )
                  {
                    if ( (_DWORD)v18 == 1 )
                    {
                      LODWORD(v18) = v89 + 40;
                      if ( v89 + 40 <= v92 )
                      {
                        if ( *(_DWORD *)(v42 + v89 + 12) )
                          v88 = (char *)(v89 + v42 + 32);
                        v38 = *(_BYTE **)(v42 + v89 + 24);
                        goto LABEL_193;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v18) = v89 + 56;
                    if ( v89 + 56 <= v92 )
                    {
                      v125 = 1;
                      if ( *(_BYTE *)(v42 + v89 + 10) )
                        v88 = (char *)(v89 + v42 + 24);
                      v40 = *(_BYTE *)(v42 + v89 + 8);
                      v38 = *(_BYTE **)(v42 + v89 + 16);
                      v39 = *(_BYTE *)(v42 + v89 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v18) = v89 + 40;
                  if ( v89 + 40 <= v92 )
                  {
                    if ( *(_BYTE *)(v42 + v89 + 10) )
                      v88 = (char *)(v89 + v42 + 24);
                    v38 = *(_BYTE **)(v42 + v89 + 16);
LABEL_193:
                    v39 = *(_BYTE *)(v42 + v89 + 9);
                    v40 = *(_BYTE *)(v42 + v89 + 8);
LABEL_222:
                    if ( !v88 )
                      goto LABEL_28;
                    v37 = *v88;
LABEL_99:
                    LOBYTE(v18) = v37 - 8;
                    if ( (v18 & 0x5D) != 0 )
                      goto LABEL_28;
                    v41 = *(_BYTE *)(v42 + 3);
                    if ( v41 == 1 || !v38 || !v39 )
                      goto LABEL_126;
                    LOBYTE(v42) = 0;
                    v43 = 0;
                    v44 = 0;
                    v18 = (unsigned __int64)&v38[v39];
                    v45 = v38 + 8;
                    if ( (unsigned __int8)((*v38 & 0x7F) - 114) <= 1u )
                    {
                      if ( (unsigned __int64)v45 <= v18 )
                      {
                        v43 = v38[2];
                        LOBYTE(v42) = v38[1] & 0xF;
                        v44 = v38[3];
                        goto LABEL_361;
                      }
                    }
                    else if ( (unsigned __int64)v45 <= v18 )
                    {
                      v46 = v38 + 13;
                      LOBYTE(v42) = v38[2] & 0xF;
                      v47 = v39;
                      if ( (unsigned int)(unsigned __int8)v38[7] + 8 <= v39 )
                        v47 = (unsigned __int8)v38[7] + 8;
                      v18 = (unsigned __int64)&v38[v47];
                      if ( (unsigned __int64)v46 <= v18 )
                        v43 = v38[12];
                      if ( (unsigned __int64)(v38 + 14) > v18 )
                        v44 = 0;
                      else
                        v44 = *v46;
LABEL_361:
                      if ( !v8 )
                      {
LABEL_126:
                        LOBYTE(v42) = 0;
                        v43 = 0;
                        v44 = 0;
                      }
                      McTemplateK0pduuuuup_EtwWriteTransfer(
                        v18,
                        v42,
                        (unsigned int)&v133,
                        a2,
                        *(_DWORD *)(a2 + 48),
                        v41,
                        v40,
                        v42,
                        v43,
                        v44,
                        a2);
                      goto LABEL_28;
                    }
                    v8 = 0;
                    goto LABEL_361;
                  }
                }
                if ( v125 )
                  goto LABEL_222;
              }
            }
            v91 = (unsigned int)(v91 + 1);
            if ( (unsigned int)v91 >= v110 )
              goto LABEL_222;
          }
        }
        goto LABEL_98;
      }
    }
LABEL_77:
    if ( v20 != 12 )
      goto LABEL_28;
    if ( v19[1] == 7 && !*((_DWORD *)v19 + 2) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v32 = *(int **)(a2 + 56);
        if ( v32 )
          v33 = *v32;
        else
          v33 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v33, (_DWORD)v19, (unsigned int)&v133, a2, v33, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_28;
    }
    if ( (byte_140177432 & 0x20) == 0 )
    {
LABEL_28:
      IofCompleteRequest((PIRP)a2, 0);
      return inserted;
    }
    v30 = EventPnpRequestComplete;
LABEL_64:
    McTemplateK0pd_EtwWriteTransfer(v18, v30, &v133, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_28;
  }
  v8 = 1;
  if ( StorEtwLoggingEnabled )
  {
    IoGetActivityIdIrp(a2, &v134);
    if ( v7 == 315396
      || (v22 = v7 - 315412, (unsigned int)v22 <= 0x34) && (v23 = 0x11000011000001LL, _bittest64(&v23, v22)) )
    {
      if ( (byte_140177433 & 1) != 0 )
        McTemplateK0pddd_EtwWriteTransfer(
          *(unsigned __int8 *)(*(_QWORD *)(a2 + 184) + 1LL),
          (unsigned int)EventPassThrough,
          (unsigned int)&v134,
          a2,
          **(_BYTE **)(a2 + 184),
          *(_BYTE *)(*(_QWORD *)(a2 + 184) + 1LL),
          v7);
    }
    else if ( (byte_140177432 & 2) != 0 )
    {
      McTemplateK0pddd_EtwWriteTransfer(
        *(unsigned __int8 *)(*(_QWORD *)(a2 + 184) + 1LL),
        (unsigned int)EventIOCTL,
        (unsigned int)&v134,
        a2,
        **(_BYTE **)(a2 + 184),
        *(_BYTE *)(*(_QWORD *)(a2 + 184) + 1LL),
        v7);
    }
  }
  LOBYTE(a3) = 1;
  v9 = RaUnitAcquireRemoveLock(a1, a2, a3);
  inserted = v9;
  if ( v9 < 0 )
  {
    v17 = StorEtwLoggingEnabled == 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = v9;
    if ( v17 )
      goto LABEL_28;
    v133 = 0;
    IoGetActivityIdIrp(a2, &v133);
    v19 = *(unsigned __int8 **)(a2 + 184);
    if ( *v19 != 14 )
    {
      v20 = *v19 - 15;
      if ( *v19 == 15 )
      {
        if ( byte_140177431 >= 0 )
          goto LABEL_28;
        v42 = *((_QWORD *)v19 + 1);
        v108 = *(unsigned __int8 *)(v42 + 2);
        if ( (_BYTE)v108 == 40 )
        {
          if ( !*(_DWORD *)(v42 + 20) )
          {
            v119 = *(_DWORD *)(v42 + 56);
            if ( v119 )
            {
              v40 = 0;
              v39 = 0;
              v88 = 0;
              v126 = 0;
              v38 = 0;
              v99 = 0;
              while ( 1 )
              {
                v18 = *(unsigned int *)(v42 + 4 * v99 + 120);
                if ( (unsigned int)v18 >= 0x80 )
                {
                  v120 = *(unsigned int *)(v42 + 16);
                  if ( (unsigned int)v18 < (unsigned int)v120 )
                  {
                    v84 = *(unsigned int *)(v42 + 4 * v99 + 120);
                    v98 = *(_DWORD *)(v18 + v42) - 64;
                    if ( v98 )
                    {
                      LODWORD(v18) = v98 - 1;
                      if ( (_DWORD)v18 )
                      {
                        if ( (_DWORD)v18 == 1 )
                        {
                          LODWORD(v18) = v84 + 40;
                          if ( v84 + 40 <= v120 )
                            goto LABEL_165;
                        }
                      }
                      else
                      {
                        LODWORD(v18) = v84 + 56;
                        if ( v84 + 56 <= v120 )
                        {
                          v126 = 1;
                          if ( *(_BYTE *)(v84 + v42 + 10) )
                            v88 = (char *)(v84 + v42 + 24);
                          v40 = *(_BYTE *)(v84 + v42 + 8);
                          v38 = *(_BYTE **)(v84 + v42 + 16);
                          v39 = *(_BYTE *)(v84 + v42 + 9);
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v18) = v84 + 40;
                      if ( v84 + 40 <= v120 )
                        goto LABEL_172;
                    }
                    if ( v126 )
                      goto LABEL_222;
                  }
                }
                v99 = (unsigned int)(v99 + 1);
                if ( (unsigned int)v99 >= v119 )
                  goto LABEL_222;
              }
            }
          }
          goto LABEL_28;
        }
        goto LABEL_98;
      }
      goto LABEL_77;
    }
LABEL_62:
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_28;
    v30 = EventNonReadWriteRequestComplete;
    goto LABEL_64;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids, a1, a2, v7);
  }
  if ( !DisableExtensionDriver )
  {
    if ( EnableExtensionCalls )
    {
      _InterlockedAdd(&ExtRefCount, 1u);
      inserted = ((__int64 (__fastcall *)(__int64 *, __int64, __int64))ExtUnitIoctlReplace)(&qword_1401761E8, a1, a2);
      _InterlockedDecrement(&ExtRefCount);
      if ( inserted != -1073741822 )
        goto LABEL_30;
    }
  }
  ExtensionUnitIoctlPre(v11, a1, a2);
  if ( v7 > 0x2D2830 )
  {
    if ( v7 > 0x2DD684 )
    {
      if ( v7 <= 0x2DDF94 )
      {
        switch ( v7 )
        {
          case 0x2DDF94u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaidUnitStorageTcgAssignLockingObject(a1, (PIRP)a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DDC04u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaUnitHwFirmwareDownloadIoctl(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DDC08u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaUnitHwFirmwareActivateIoctl(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DDC0Cu:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaUnitHwBootPartitionDownloadIoctl(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DDC10u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaUnitHwBootPartitionActivateIoctl(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DDC9Cu:
            SystemFeatureSupportIoctl = RaUnitAttributeManagement(a1, a2);
            goto LABEL_20;
          case 0x2DDF84u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaidUnitStorageTcgActivateLocking(a1, (PIRP)a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DDF88u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaidUnitStorageTcgRevertConfig(a1, (PIRP)a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DDF8Cu:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaidUnitStorageTcgSetSpAuthorityKey(a1, (PIRP)a2);
              goto LABEL_20;
            }
            goto LABEL_573;
        }
      }
      else
      {
        switch ( v7 )
        {
          case 0x2DDF98u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaidUnitStorageTcgDeassignLockingObject(a1, (PIRP)a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DDF9Cu:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaidUnitStorageTcgSetLockingObjectAuthKey(a1, (PIRP)a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DDFA0u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaidUnitStorageTcgEraseLockingObject(a1, (PIRP)a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DDFA4u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaidUnitStorageTcgSetLockingObject(a1, (PIRP)a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DDFACu:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaidUnitStorageTcgSetLockingObjectMetadata(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DDFB0u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaidUnitStorageTcgResetState(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DE814u:
            SystemFeatureSupportIoctl = RaUnitSetQOSIoctl(a1, a2);
            goto LABEL_20;
        }
      }
      goto LABEL_57;
    }
    if ( v7 != 3004036 )
    {
      if ( v7 > 0x2D93F4 )
      {
        switch ( v7 )
        {
          case 0x2D93FCu:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaUnitStorageSetPropertyIoctl(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2D9404u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaUnitStorageDataSetManagementIoctl(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DD040u:
            SystemFeatureSupportIoctl = RaidUnitTestDeviceQueue(a1, a2);
            goto LABEL_20;
          case 0x2DD044u:
            SystemFeatureSupportIoctl = RaUnitStorageNotificationConfigureIoctl(a1, a2);
            goto LABEL_20;
          case 0x2DD04Cu:
            SystemFeatureSupportIoctl = RaUnitSetPciLinkBandwidthIoctl(a1, a2);
            goto LABEL_20;
          case 0x2DD200u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaUnitSetTemperatureThresholdIoctl(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2DD3C0u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaUnitProtocolCommandIoctl(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
        }
      }
      else
      {
        switch ( v7 )
        {
          case 0x2D93F4u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaUnitStorageInternalSetPropertyIoctl(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2D4C1Cu:
            SystemFeatureSupportIoctl = StorageGetSystemFeatureSupportIoctl((PIRP)a2);
            goto LABEL_20;
          case 0x2D5000u:
            SystemFeatureSupportIoctl = RaidAdapterStorageResetBusIoctl(*(_QWORD *)(a1 + 24), a2);
            goto LABEL_20;
          case 0x2D5014u:
            SystemFeatureSupportIoctl = RaUnitStorageBreakReservationIoctl(a1, a2);
            goto LABEL_20;
          case 0x2D5020u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaidAdapterStorageDeviceResetIoctl(*(_QWORD *)(a1 + 24), a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2D5048u:
            SystemFeatureSupportIoctl = RaUnitStorageNotificationGetInfoIoctl(a1, a2);
            goto LABEL_20;
          case 0x2D5644u:
            SystemFeatureSupportIoctl = RaUnitStorageDumpNotification(a1, a2);
            goto LABEL_20;
          case 0x2D5F90u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaidUnitStorageTcgEnumerateLockingObjects(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          case 0x2D5FA8u:
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaidUnitStorageTcgGetLockingObjectMetadata(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
        }
      }
      goto LABEL_57;
    }
    goto LABEL_531;
  }
  if ( v7 == 2959408 )
    goto LABEL_397;
  if ( v7 <= 0x2D1C00 )
  {
    if ( v7 == 2956288 )
    {
      if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
        || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
      {
        SystemFeatureSupportIoctl = RaUnitHwFirmwareGetInfoIoctl((_QWORD *)a1, a2);
        goto LABEL_20;
      }
      goto LABEL_573;
    }
    if ( v7 <= 0x4D044 )
    {
      if ( v7 != 315460 )
      {
        switch ( v7 )
        {
          case 0x41018u:
            SystemFeatureSupportIoctl = RaUnitScsiGetAddressIoctl(a1, a2);
            goto LABEL_20;
          case 0x41020u:
            SystemFeatureSupportIoctl = RaUnitScsiGetDumpPointersIoctl(a1, a2);
            goto LABEL_20;
          case 0x41024u:
            SystemFeatureSupportIoctl = RaUnitScsiFreeDumpPointersIoctl(a1, a2);
            goto LABEL_20;
        }
        if ( v7 != 315396 )
        {
          if ( v7 == 315400 )
          {
            if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
              || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
            {
              SystemFeatureSupportIoctl = RaUnitScsiMiniportIoctl(a1, a2);
              goto LABEL_20;
            }
            goto LABEL_573;
          }
          if ( v7 != 315412 )
          {
            if ( v7 == 315436 )
            {
              if ( (unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
                && (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) == 0 )
              {
                goto LABEL_573;
              }
              v31 = 0;
            }
            else
            {
              if ( v7 != 315440 )
                goto LABEL_57;
              if ( (unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
                && (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) == 0 )
              {
                goto LABEL_573;
              }
              LOBYTE(v31) = 1;
            }
            SystemFeatureSupportIoctl = RaUnitAtaPassThroughIoctl(a1, a2, v31);
            goto LABEL_20;
          }
        }
      }
    }
    else if ( v7 != 315464 )
    {
      switch ( v7 )
      {
        case 0x2D08C0u:
          SystemFeatureSupportIoctl = RaUnitStorageManageBypassIOIoctl(a1, a2);
          goto LABEL_20;
        case 0x2D11D0u:
          SystemFeatureSupportIoctl = RaUnitStorageDataCollectionIoctl(a1, a2);
          goto LABEL_20;
        case 0x2D11D4u:
          SystemFeatureSupportIoctl = RaUnitStorageGetInternalDataIoctl(a1, a2);
          goto LABEL_20;
        case 0x2D13F8u:
          if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
            || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
          {
            SystemFeatureSupportIoctl = RaUnitStorageInternalQueryPropertyIoctl(a1, a2, v131);
            goto LABEL_20;
          }
          goto LABEL_573;
        case 0x2D1400u:
          if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
            || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
          {
            SystemFeatureSupportIoctl = RaUnitStorageQueryPropertyIoctl(a1, a2, v12, v13);
LABEL_20:
            inserted = SystemFeatureSupportIoctl;
            goto LABEL_21;
          }
LABEL_573:
          inserted = RaInsertDFxQueue(*(_QWORD *)(a1 + 8), a2);
          if ( !inserted )
            inserted = 259;
          goto LABEL_21;
        case 0x2D164Bu:
          SystemFeatureSupportIoctl = RaUnitStorageGetDumpInfoIoctl(a1, a2);
          goto LABEL_20;
      }
      if ( v7 != 2954880 )
        goto LABEL_57;
LABEL_531:
      if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
        || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
      {
        v123 = *(_QWORD *)(a1 + 24);
        ++*(_BYTE *)(a2 + 67);
        *(_QWORD *)(a2 + 184) += 72LL;
        SystemFeatureSupportIoctl = IofCallDriver(*(PDEVICE_OBJECT *)(v123 + 8), (PIRP)a2);
        goto LABEL_20;
      }
      goto LABEL_573;
    }
    if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
      || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
    {
      SystemFeatureSupportIoctl = RaUnitScsiPassThroughIoctl(a1, a2);
      goto LABEL_20;
    }
    goto LABEL_573;
  }
  if ( v7 <= 0x2D1CCC )
  {
    switch ( v7 )
    {
      case 0x2D1CCCu:
        SystemFeatureSupportIoctl = RaidUnitSetLedState(a1, a2);
        goto LABEL_20;
      case 0x2D1C14u:
        if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
          || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
        {
          SystemFeatureSupportIoctl = RaUnitHwBootPartitionGetInfoIoctl(a1, a2);
          goto LABEL_20;
        }
        goto LABEL_573;
      case 0x2D1C80u:
        SystemFeatureSupportIoctl = RaUnitStorageEnableIdlePower(a1, a2);
        goto LABEL_20;
      case 0x2D1C84u:
        SystemFeatureSupportIoctl = RaUnitStorageGetIdlePowerUpReason(a1, a2);
        goto LABEL_20;
      case 0x2D1C88u:
        if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
          || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
        {
          SystemFeatureSupportIoctl = RaUnitStoragePowerActive(a1, a2);
          goto LABEL_20;
        }
        goto LABEL_573;
      case 0x2D1C8Cu:
        SystemFeatureSupportIoctl = RaUnitStoragePowerIdle(a1, a2);
        goto LABEL_20;
      case 0x2D1C94u:
        if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
          || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
        {
          SystemFeatureSupportIoctl = RaUnitPowerCapIoctl(a1, a2);
          goto LABEL_20;
        }
        goto LABEL_573;
      case 0x2D1CA0u:
        SystemFeatureSupportIoctl = RaUnitStorageDiagnosticIoctl(a1, a2);
        goto LABEL_20;
      case 0x2D1CC8u:
        if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
          || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
        {
          SystemFeatureSupportIoctl = RaUnitSmartDataIoctl(a1, a2);
          goto LABEL_20;
        }
        goto LABEL_573;
    }
    goto LABEL_57;
  }
  switch ( v7 )
  {
    case 0x2D1D00u:
    case 0x2D1D04u:
      v17 = StorEtwLoggingEnabled == 0;
      inserted = -1073741637;
      *(_DWORD *)(a2 + 48) = -1073741637;
      *(_BYTE *)(a2 + 141) = -84;
      if ( v17 )
        goto LABEL_61;
      v133 = 0;
      IoGetActivityIdIrp(a2, &v133);
      v28 = *(unsigned __int8 **)(a2 + 184);
      if ( *v28 != 14 )
      {
        v29 = *v28 - 15;
        if ( *v28 == 15 )
        {
          if ( byte_140177431 >= 0 )
            goto LABEL_61;
          v65 = *((_QWORD *)v28 + 1);
          if ( *(_BYTE *)(v65 + 2) != 40 )
          {
            v60 = *(_BYTE *)(v65 + 72);
            v61 = *(_BYTE **)(v65 + 32);
            v62 = *(_BYTE *)(v65 + 11);
            v63 = *(_BYTE *)(v65 + 4);
            if ( *(_BYTE *)(v65 + 2) )
              goto LABEL_61;
            goto LABEL_129;
          }
          if ( *(_DWORD *)(v65 + 20) )
            goto LABEL_61;
          v117 = *(_DWORD *)(v65 + 56);
          if ( !v117 )
            goto LABEL_61;
          v62 = 0;
          v103 = 0;
          v127 = 0;
          v61 = 0;
          v129 = 0;
          v102 = 0;
          while ( 1 )
          {
            v27 = *(unsigned int *)(v65 + 4 * v102 + 120);
            if ( (unsigned int)v27 >= 0x80 )
            {
              v118 = *(unsigned int *)(v65 + 16);
              if ( (unsigned int)v27 < (unsigned int)v118 )
              {
                v100 = *(unsigned int *)(v65 + 4 * v102 + 120);
                v101 = *(_DWORD *)(v27 + v65) - 64;
                if ( v101 )
                {
                  LODWORD(v27) = v101 - 1;
                  if ( (_DWORD)v27 )
                  {
                    if ( (_DWORD)v27 == 1 )
                    {
                      LODWORD(v27) = v100 + 40;
                      if ( v100 + 40 <= v118 )
                      {
                        if ( *(_DWORD *)(v100 + v65 + 12) )
                          v103 = (char *)(v100 + v65 + 32);
                        v61 = *(_BYTE **)(v100 + v65 + 24);
                        goto LABEL_247;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v27) = v100 + 56;
                    if ( v100 + 56 <= v118 )
                    {
                      v129 = 1;
                      if ( *(_BYTE *)(v100 + v65 + 10) )
                        v103 = (char *)(v100 + v65 + 24);
                      v61 = *(_BYTE **)(v100 + v65 + 16);
                      v62 = *(_BYTE *)(v100 + v65 + 9);
                      v127 = *(_BYTE *)(v100 + v65 + 8);
                    }
                  }
                }
                else
                {
                  LODWORD(v27) = v100 + 40;
                  if ( v100 + 40 <= v118 )
                  {
                    if ( *(_BYTE *)(v100 + v65 + 10) )
                      v103 = (char *)(v100 + v65 + 24);
                    v61 = *(_BYTE **)(v100 + v65 + 16);
LABEL_247:
                    v63 = *(_BYTE *)(v100 + v65 + 8);
                    v62 = *(_BYTE *)(v100 + v65 + 9);
LABEL_237:
                    if ( !v103 )
                      goto LABEL_61;
                    v60 = *v103;
LABEL_129:
                    LOBYTE(v27) = v60 - 8;
                    if ( (v27 & 0x5D) != 0 )
                      goto LABEL_61;
                    v64 = *(_BYTE *)(v65 + 3);
                    if ( v64 == 1 || !v61 || !v62 )
                      goto LABEL_334;
                    LOBYTE(v65) = 0;
                    v66 = 0;
                    v67 = 0;
                    v27 = (unsigned __int64)&v61[v62];
                    v68 = v61 + 8;
                    if ( (unsigned __int8)((*v61 & 0x7F) - 114) <= 1u )
                    {
                      if ( (unsigned __int64)v68 <= v27 )
                      {
                        v66 = v61[2];
                        LOBYTE(v65) = v61[1] & 0xF;
                        v67 = v61[3];
                        goto LABEL_141;
                      }
                    }
                    else if ( (unsigned __int64)v68 <= v27 )
                    {
                      v69 = v61 + 13;
                      LOBYTE(v65) = v61[2] & 0xF;
                      v70 = v62;
                      if ( (unsigned int)(unsigned __int8)v61[7] + 8 <= v62 )
                        v70 = (unsigned __int8)v61[7] + 8;
                      v27 = (unsigned __int64)&v61[v70];
                      if ( (unsigned __int64)v69 <= v27 )
                        v66 = v61[12];
                      if ( (unsigned __int64)(v61 + 14) > v27 )
                        v67 = 0;
                      else
                        v67 = *v69;
LABEL_141:
                      v71 = 1;
LABEL_394:
                      if ( !v71 )
                      {
LABEL_334:
                        LOBYTE(v65) = 0;
                        v66 = 0;
                        v67 = 0;
                      }
                      McTemplateK0pduuuuup_EtwWriteTransfer(
                        v27,
                        v65,
                        (unsigned int)&v133,
                        a2,
                        *(_DWORD *)(a2 + 48),
                        v64,
                        v63,
                        v65,
                        v66,
                        v67,
                        a2);
                      goto LABEL_61;
                    }
                    v71 = 0;
                    goto LABEL_394;
                  }
                }
                if ( v129 )
                  goto LABEL_236;
              }
            }
            v102 = (unsigned int)(v102 + 1);
            if ( (unsigned int)v102 >= v117 )
            {
LABEL_236:
              v63 = v127;
              goto LABEL_237;
            }
          }
        }
        goto LABEL_88;
      }
LABEL_85:
      if ( (byte_140177432 & 8) == 0 )
        goto LABEL_61;
      v34 = EventNonReadWriteRequestComplete;
      goto LABEL_87;
    case 0x2D1F80u:
      if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
        || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
      {
        SystemFeatureSupportIoctl = RaidUnitStorageTcgQueryCapability(a1, a2);
        goto LABEL_20;
      }
      goto LABEL_573;
    case 0x2D280Cu:
      SystemFeatureSupportIoctl = RaUnitTelemetryIdIoctl(a1, a2);
      goto LABEL_20;
    case 0x2D2810u:
      SystemFeatureSupportIoctl = RaUnitGetQOSIoctl(a1, a2);
      goto LABEL_20;
    case 0x2D2828u:
    case 0x2D282Cu:
LABEL_397:
      if ( !(unsigned __int8)RaIsDeviceDFxPoweredDown(*(_QWORD *)(a1 + 8))
        || (*(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) & 1) != 0 )
      {
        SystemFeatureSupportIoctl = RaUnitStreamsIoctl(a1, a2);
        goto LABEL_20;
      }
      goto LABEL_573;
  }
LABEL_57:
  v17 = StorEtwLoggingEnabled == 0;
  inserted = -1073741808;
  *(_DWORD *)(a2 + 48) = -1073741808;
  *(_BYTE *)(a2 + 141) = -84;
  if ( v17 )
    goto LABEL_61;
  v133 = 0;
  IoGetActivityIdIrp(a2, &v133);
  v28 = *(unsigned __int8 **)(a2 + 184);
  if ( *v28 == 14 )
    goto LABEL_85;
  v29 = *v28 - 15;
  if ( *v28 != 15 )
  {
LABEL_88:
    if ( v29 != 12 )
      goto LABEL_61;
    if ( v28[1] == 7 && !*((_DWORD *)v28 + 2) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v35 = *(int **)(a2 + 56);
        if ( v35 )
          v36 = *v35;
        else
          v36 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v36, (_DWORD)v28, (unsigned int)&v133, a2, v36, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_61;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_61;
    v34 = EventPnpRequestComplete;
LABEL_87:
    McTemplateK0pd_EtwWriteTransfer(v27, v34, &v133, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_61;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_61;
  v77 = *((_QWORD *)v28 + 1);
  if ( *(_BYTE *)(v77 + 2) != 40 )
  {
    v72 = *(_BYTE *)(v77 + 72);
    v73 = *(_BYTE **)(v77 + 32);
    v74 = *(_BYTE *)(v77 + 11);
    v75 = *(_BYTE *)(v77 + 4);
    if ( !*(_BYTE *)(v77 + 2) )
      goto LABEL_143;
    goto LABEL_61;
  }
  if ( *(_DWORD *)(v77 + 20) )
    goto LABEL_61;
  v121 = *(_DWORD *)(v77 + 56);
  if ( !v121 )
    goto LABEL_61;
  v74 = 0;
  v107 = 0;
  v128 = 0;
  v73 = 0;
  v130 = 0;
  v106 = 0;
  while ( 1 )
  {
    v27 = *(unsigned int *)(v77 + 4 * v106 + 120);
    if ( (unsigned int)v27 >= 0x80 )
    {
      v122 = *(unsigned int *)(v77 + 16);
      if ( (unsigned int)v27 < (unsigned int)v122 )
        break;
    }
LABEL_256:
    v106 = (unsigned int)(v106 + 1);
    if ( (unsigned int)v106 >= v121 )
    {
LABEL_257:
      v75 = v128;
      goto LABEL_258;
    }
  }
  v104 = *(unsigned int *)(v77 + 4 * v106 + 120);
  v105 = *(_DWORD *)(v27 + v77) - 64;
  if ( v105 )
  {
    LODWORD(v27) = v105 - 1;
    if ( (_DWORD)v27 )
    {
      if ( (_DWORD)v27 == 1 )
      {
        LODWORD(v27) = v104 + 40;
        if ( v104 + 40 <= v122 )
        {
          if ( *(_DWORD *)(v104 + v77 + 12) )
            v107 = (char *)(v104 + v77 + 32);
          v73 = *(_BYTE **)(v104 + v77 + 24);
          goto LABEL_268;
        }
      }
    }
    else
    {
      LODWORD(v27) = v104 + 56;
      if ( v104 + 56 <= v122 )
      {
        v130 = 1;
        if ( *(_BYTE *)(v104 + v77 + 10) )
          v107 = (char *)(v104 + v77 + 24);
        v73 = *(_BYTE **)(v104 + v77 + 16);
        v74 = *(_BYTE *)(v104 + v77 + 9);
        v128 = *(_BYTE *)(v104 + v77 + 8);
      }
    }
    goto LABEL_255;
  }
  LODWORD(v27) = v104 + 40;
  if ( v104 + 40 > v122 )
  {
LABEL_255:
    if ( v130 )
      goto LABEL_257;
    goto LABEL_256;
  }
  if ( *(_BYTE *)(v104 + v77 + 10) )
    v107 = (char *)(v104 + v77 + 24);
  v73 = *(_BYTE **)(v104 + v77 + 16);
LABEL_268:
  v75 = *(_BYTE *)(v104 + v77 + 8);
  v74 = *(_BYTE *)(v104 + v77 + 9);
LABEL_258:
  if ( !v107 )
    goto LABEL_61;
  v72 = *v107;
LABEL_143:
  LOBYTE(v27) = v72 - 8;
  if ( (v27 & 0x5D) != 0 )
    goto LABEL_61;
  v76 = *(_BYTE *)(v77 + 3);
  if ( v76 == 1 || !v73 || !v74 )
    goto LABEL_336;
  LOBYTE(v77) = 0;
  v78 = 0;
  v79 = 0;
  v27 = (unsigned __int64)&v73[v74];
  v80 = v73 + 8;
  if ( (unsigned __int8)((*v73 & 0x7F) - 114) <= 1u )
  {
    if ( (unsigned __int64)v80 <= v27 )
    {
      v78 = v73[2];
      LOBYTE(v77) = v73[1] & 0xF;
      v79 = v73[3];
      goto LABEL_155;
    }
    goto LABEL_404;
  }
  if ( (unsigned __int64)v80 > v27 )
  {
LABEL_404:
    v83 = 0;
    goto LABEL_405;
  }
  v81 = v73 + 13;
  LOBYTE(v77) = v73[2] & 0xF;
  v82 = v74;
  if ( (unsigned int)(unsigned __int8)v73[7] + 8 <= v74 )
    v82 = (unsigned __int8)v73[7] + 8;
  v27 = (unsigned __int64)&v73[v82];
  if ( (unsigned __int64)v81 <= v27 )
    v78 = v73[12];
  if ( (unsigned __int64)(v73 + 14) > v27 )
    v79 = 0;
  else
    v79 = *v81;
LABEL_155:
  v83 = 1;
LABEL_405:
  if ( !v83 )
  {
LABEL_336:
    LOBYTE(v77) = 0;
    v78 = 0;
    v79 = 0;
  }
  McTemplateK0pduuuuup_EtwWriteTransfer(
    v27,
    v77,
    (unsigned int)&v133,
    a2,
    *(_DWORD *)(a2 + 48),
    v76,
    v75,
    v77,
    v78,
    v79,
    a2);
LABEL_61:
  IofCompleteRequest((PIRP)a2, 0);
  v7 = v132;
LABEL_21:
  v16 = ExtensionUnitIoctlPost(v15, a1, a2);
  v4 = v131[0];
  if ( v16 != -1073741822 )
    inserted = v16;
LABEL_30:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqDD(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids,
      a1,
      a2,
      v7,
      inserted);
  }
  if ( !v4 )
  {
    v24 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
    v25 = *(_DWORD *)(v24 + *(_QWORD *)(a1 + 40));
    while ( (v25 & 1) == 0 )
    {
      v26 = v25;
      v25 = _InterlockedCompareExchange((volatile signed __int32 *)(v24 + *(_QWORD *)(a1 + 40)), v25 - 2, v25);
      if ( v26 == v25 )
        return inserted;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 1032), 0xFFFFFFFF) == 1 )
      KeSetEvent((PRKEVENT)(a1 + 520), 0, 0);
  }
  return inserted;
}

```

## disassembly

```asm
0x140036290  mov     [rsp-8+arg_10], rbx
0x140036295  push    rbp
0x140036296  push    rsi
0x140036297  push    rdi
0x140036298  push    r12
0x14003629a  push    r13
0x14003629c  push    r14
0x14003629e  push    r15
0x1400362a0  lea     rbp, [rsp-27h]
0x1400362a5  sub     rsp, 90h
0x1400362ac  mov     rax, cs:__security_cookie
0x1400362b3  xor     rax, rsp
0x1400362b6  mov     [rbp+57h+var_38], rax
0x1400362ba  mov     rax, [rdx+0B8h]
0x1400362c1  xor     r12b, r12b
0x1400362c4  xorps   xmm0, xmm0
0x1400362c7  mov     [rbp+57h+var_5E], r12b
0x1400362cb  movups  [rbp+57h+var_48], xmm0
0x1400362cf  mov     rbx, rdx
0x1400362d2  mov     rdi, rcx
0x1400362d5  mov     r15d, [rax+18h]
0x1400362d9  mov     [rbp+57h+var_5C], r15d
0x1400362dd  cmp     r15d, 2D190Ch
0x1400362e4  jz      loc_1400373D6
0x1400362ea  cmp     cs:StorEtwLoggingEnabled, r12b
0x1400362f1  mov     r14d, 1
0x1400362f7  jnz     loc_1400364B1
0x1400362fd  mov     r8b, r14b
0x140036300  mov     rdx, rbx
0x140036303  mov     rcx, rdi
0x140036306  call    RaUnitAcquireRemoveLock
0x14003630b  mov     esi, eax
0x14003630d  test    eax, eax
0x14003630f  js      loc_140036405
0x140036315  mov     rcx, cs:WPP_GLOBAL_Control
0x14003631c  lea     rax, WPP_GLOBAL_Control
0x140036323  mov     r13d, 4
0x140036329  cmp     rcx, rax
0x14003632c  jnz     loc_14003659A
0x140036332  cmp     cs:DisableExtensionDriver, r12b
0x140036339  jnz     short loc_140036349
0x14003633b  mov     al, cs:EnableExtensionCalls
0x140036341  test    al, al
0x140036343  jnz     loc_140037499
0x140036349  mov     r8, rbx
0x14003634c  mov     rdx, rdi
0x14003634f  call    ExtensionUnitIoctlPre
0x140036354  mov     eax, 2D2830h
0x140036359  cmp     r15d, eax
0x14003635c  ja      loc_1400365D6
0x140036362  jz      loc_140037656
0x140036368  mov     eax, 2D1C00h
0x14003636d  cmp     r15d, eax
0x140036370  ja      loc_140150312
0x140036376  jz      loc_1400375FF
0x14003637c  mov     eax, 4D044h
0x140036381  cmp     r15d, eax
0x140036384  jbe     loc_1400366DF
0x14003638a  mov     eax, r15d
0x14003638d  sub     eax, 4D048h
0x140036392  jz      loc_1400375D8
0x140036398  sub     eax, 283878h
0x14003639d  jz      loc_1400375C8
0x1400363a3  sub     eax, 910h
0x1400363a8  jz      loc_1400375B8
0x1400363ae  sub     eax, r13d
0x1400363b1  jz      loc_1400375A8
0x1400363b7  sub     eax, 224h
0x1400363bc  jz      loc_140037581
0x1400363c2  sub     eax, 8
0x1400363c5  jnz     loc_140037552
0x1400363cb  mov     rcx, [rdi+8]
0x1400363cf  call    RaIsDeviceDFxPoweredDown
0x1400363d4  test    al, al
0x1400363d6  jnz     loc_14003756B
0x1400363dc  mov     rdx, rbx
0x1400363df  mov     rcx, rdi
0x1400363e2  call    RaUnitStorageQueryPropertyIoctl
0x1400363e7  mov     esi, eax
0x1400363e9  mov     r8, rbx
0x1400363ec  mov     rdx, rdi
0x1400363ef  call    ExtensionUnitIoctlPost
0x1400363f4  mov     r12b, [rbp+57h+var_5E]
0x1400363f8  cmp     eax, 0C0000002h
0x1400363fd  cmovnz  esi, eax
0x140036400  jmp     loc_140036489
0x140036405  cmp     cs:StorEtwLoggingEnabled, r12b
0x14003640c  mov     qword ptr [rbx+38h], 0
0x140036414  mov     byte ptr [rbx+8Dh], 0ACh
0x14003641b  mov     [rbx+30h], eax
0x14003641e  jz      short loc_140036463
0x140036420  xorps   xmm0, xmm0
0x140036423  lea     rdx, [rbp+57h+var_58]
0x140036427  mov     rcx, rbx
0x14003642a  movups  [rbp+57h+var_58], xmm0
0x14003642e  call    cs:__imp_IoGetActivityIdIrp
0x140036435  nop     dword ptr [rax+rax+00h]
0x14003643a  mov     rdx, [rbx+0B8h]
0x140036441  movzx   eax, byte ptr [rdx]
0x140036444  sub     eax, 0Eh
0x140036447  jz      loc_1400366B3
0x14003644d  sub     eax, r14d
0x140036450  jnz     loc_14003675B
0x140036456  cmp     cs:byte_140177431, r12b
0x14003645d  jl      loc_14003745D
0x140036463  xor     edx, edx; PriorityBoost
0x140036465  mov     rcx, rbx; Irp
0x140036468  call    cs:__imp_IofCompleteRequest
0x14003646f  nop     dword ptr [rax+rax+00h]
0x140036474  jmp     short loc_1400364A9
0x140036476  lock dec cs:ExtRefCount
0x14003647d  cmp     esi, 0C0000002h
0x140036483  jz      loc_140036349
0x140036489  mov     rcx, cs:WPP_GLOBAL_Control
0x140036490  lea     rax, WPP_GLOBAL_Control
0x140036497  cmp     rcx, rax
0x14003649a  jnz     loc_140036525
0x1400364a0  test    r12b, r12b
0x1400364a3  jz      loc_140036565
0x1400364a9  mov     eax, esi
0x1400364ab  jmp     loc_1400377BC
0x1400364b1  lea     rdx, [rbp+57h+var_48]
0x1400364b5  mov     rcx, rbx
0x1400364b8  call    cs:__imp_IoGetActivityIdIrp
0x1400364bf  nop     dword ptr [rax+rax+00h]
0x1400364c4  cmp     r15d, 4D004h
0x1400364cb  jz      loc_140037429
0x1400364d1  lea     eax, [r15-4D014h]
0x1400364d8  cmp     eax, 34h ; '4'
0x1400364db  ja      short loc_1400364F1
0x1400364dd  mov     rcx, 11000011000001h
0x1400364e7  bt      rcx, rax
0x1400364eb  jb      loc_140037429
0x1400364f1  test    cs:byte_140177432, 2
0x1400364f8  jz      loc_1400362FD
0x1400364fe  mov     rax, [rbx+0B8h]
0x140036505  mov     [rsp+0C0h+var_90], r15d
0x14003650a  movzx   edx, byte ptr [rax]
0x14003650d  movzx   ecx, byte ptr [rax+1]
0x140036511  mov     [rsp+0C0h+var_98], ecx
0x140036515  mov     dword ptr [rsp+0C0h+var_A0], edx
0x140036519  lea     rdx, EventIOCTL
0x140036520  jmp     loc_14015028E
0x140036525  mov     eax, [rcx+2Ch]
0x140036528  test    al, 10h
0x14003652a  jz      loc_1400364A0
0x140036530  cmp     [rcx+29h], r13b
0x140036534  jb      loc_1400364A0
0x14003653a  mov     rcx, [rcx+18h]
0x14003653e  lea     r8, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids
0x140036545  mov     [rsp+0C0h+var_90], esi
0x140036549  mov     edx, 1Ah
0x14003654e  mov     [rsp+0C0h+var_98], r15d
0x140036553  mov     r9, rdi
0x140036556  mov     [rsp+0C0h+var_A0], rbx
0x14003655b  call    WPP_SF_qqDD
0x140036560  jmp     loc_1400364A0
0x140036565  mov     eax, gs:1A4h
0x14003656d  mov     r8d, eax
0x140036570  mov     rax, [rdi+28h]
0x140036574  shl     r8, 6
0x140036578  mov     eax, [r8+rax]
0x14003657c  test    r14b, al
0x14003657f  jnz     loc_140036822
0x140036585  mov     rcx, [rdi+28h]
0x140036589  lea     edx, [rax-2]
0x14003658c  lock cmpxchg [r8+rcx], edx
0x140036592  jz      loc_1400364A9
0x140036598  jmp     short loc_14003657C
0x14003659a  mov     eax, [rcx+2Ch]
0x14003659d  test    al, 10h
0x14003659f  jz      loc_140036332
0x1400365a5  cmp     [rcx+29h], r13b
0x1400365a9  jb      loc_140036332
0x1400365af  mov     rcx, [rcx+18h]
0x1400365b3  lea     r8, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids
0x1400365ba  mov     edx, 19h
0x1400365bf  mov     [rsp+0C0h+var_98], r15d
0x1400365c4  mov     r9, rdi
0x1400365c7  mov     [rsp+0C0h+var_A0], rbx
0x1400365cc  call    WPP_SF_qqD
0x1400365d1  jmp     loc_140036332
0x1400365d6  mov     eax, 2DD684h
0x1400365db  cmp     r15d, eax
0x1400365de  jbe     loc_14015053E
0x1400365e4  mov     eax, 2DDF94h
0x1400365e9  cmp     r15d, eax
0x1400365ec  jbe     loc_14015082B
0x1400365f2  mov     eax, r15d
0x1400365f5  sub     eax, 2DDF98h
0x1400365fa  jz      loc_140037795
0x140036600  sub     eax, r13d
0x140036603  jz      loc_14003776E
0x140036609  sub     eax, r13d
0x14003660c  jz      loc_140037747
0x140036612  sub     eax, r13d
0x140036615  jz      loc_140037720
0x14003661b  sub     eax, 8
0x14003661e  jz      loc_1400376F9
0x140036624  sub     eax, r13d
0x140036627  jz      loc_1400376D2
0x14003662d  cmp     eax, 864h
0x140036632  jz      loc_1400376C2
0x140036638  cmp     cs:StorEtwLoggingEnabled, r12b
0x14003663f  mov     esi, 0C0000010h
0x140036644  mov     [rbx+30h], esi
0x140036647  mov     byte ptr [rbx+8Dh], 0ACh
0x14003664e  jz      short loc_140036693
0x140036650  xorps   xmm0, xmm0
0x140036653  lea     rdx, [rbp+57h+var_58]
0x140036657  mov     rcx, rbx
0x14003665a  movups  [rbp+57h+var_58], xmm0
0x14003665e  call    cs:__imp_IoGetActivityIdIrp
0x140036665  nop     dword ptr [rax+rax+00h]
0x14003666a  mov     rdx, [rbx+0B8h]
0x140036671  movzx   eax, byte ptr [rdx]
0x140036674  sub     eax, 0Eh
0x140036677  jz      loc_1400367AA
0x14003667d  sub     eax, r14d
0x140036680  jnz     loc_1400367D6
0x140036686  cmp     cs:byte_140177431, r12b
0x14003668d  jl      loc_14003767D
0x140036693  xor     edx, edx; PriorityBoost
0x140036695  mov     rcx, rbx; Irp
0x140036698  call    cs:__imp_IofCompleteRequest
0x14003669f  nop     dword ptr [rax+rax+00h]
0x1400366a4  mov     r15d, [rbp+57h+var_5C]
0x1400366a8  mov     r13d, 4
0x1400366ae  jmp     loc_1400363E9
0x1400366b3  test    cs:byte_140177432, 8
0x1400366ba  jz      loc_140036463
0x1400366c0  lea     rdx, EventNonReadWriteRequestComplete
0x1400366c7  mov     eax, [rbx+30h]
0x1400366ca  lea     r8, [rbp+57h+var_58]
0x1400366ce  mov     r9, rbx
0x1400366d1  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1400366d5  call    McTemplateK0pd_EtwWriteTransfer
0x1400366da  jmp     loc_140036463
0x1400366df  jz      loc_1400375D8
0x1400366e5  mov     eax, r15d
0x1400366e8  sub     eax, 41018h
0x1400366ed  jz      loc_140037542
0x1400366f3  sub     eax, 8
0x1400366f6  jz      loc_140037532
0x1400366fc  sub     eax, r13d
0x1400366ff  jz      loc_140037522
0x140036705  sub     eax, 0BFE0h
0x14003670a  jz      loc_1400375D8
0x140036710  sub     eax, r13d
0x140036713  jz      loc_1400374FB
0x140036719  sub     eax, 0Ch
0x14003671c  jz      loc_1400375D8
0x140036722  sub     eax, 18h
0x140036725  jz      loc_1400374D4
0x14003672b  cmp     eax, r13d
0x14003672e  jnz     loc_140036638
0x140036734  mov     rcx, [rdi+8]
0x140036738  call    RaIsDeviceDFxPoweredDown
0x14003673d  test    al, al
0x14003673f  jz      loc_1401502A0
0x140036745  mov     rax, [rbx+0B8h]
0x14003674c  test    [rax+3], r14b
0x140036750  jnz     loc_1401502A0
0x140036756  jmp     loc_140150A54
0x14003675b  cmp     eax, 0Ch
0x14003675e  jnz     loc_140036463
0x140036764  cmp     byte ptr [rdx+1], 7
0x140036768  jz      short loc_140036783
0x14003676a  test    cs:byte_140177432, 20h
0x140036771  jz      loc_140036463
0x140036777  lea     rdx, EventPnpRequestComplete
0x14003677e  jmp     loc_1400366C7
0x140036783  cmp     dword ptr [rdx+8], 0
0x140036787  jnz     short loc_14003676A
0x140036789  test    cs:byte_140177432, 40h
0x140036790  jz      loc_140036463
0x140036796  mov     rax, [rbx+38h]
0x14003679a  test    rax, rax
0x14003679d  jz      loc_140150250
0x1400367a3  mov     ecx, [rax]
0x1400367a5  jmp     loc_140150252
0x1400367aa  test    cs:byte_140177432, 8
0x1400367b1  jz      loc_140036693
0x1400367b7  lea     rdx, EventNonReadWriteRequestComplete
0x1400367be  mov     eax, [rbx+30h]
0x1400367c1  lea     r8, [rbp+57h+var_58]
0x1400367c5  mov     r9, rbx
0x1400367c8  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1400367cc  call    McTemplateK0pd_EtwWriteTransfer
0x1400367d1  jmp     loc_140036693
0x1400367d6  cmp     eax, 0Ch
0x1400367d9  jnz     loc_140036693
0x1400367df  cmp     byte ptr [rdx+1], 7
0x1400367e3  jnz     short loc_1400367EB
0x1400367e5  cmp     dword ptr [rdx+8], 0
0x1400367e9  jz      short loc_140036801
0x1400367eb  test    cs:byte_140177432, 20h
0x1400367f2  jz      loc_140036693
0x1400367f8  lea     rdx, EventPnpRequestComplete
0x1400367ff  jmp     short loc_1400367BE
  ... truncated ...
```
