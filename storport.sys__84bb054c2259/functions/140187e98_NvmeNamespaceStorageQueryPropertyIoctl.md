# NvmeNamespaceStorageQueryPropertyIoctl

- ea: `0x140187e98`
- end: `0x140189014`
- name: `NvmeNamespaceStorageQueryPropertyIoctl`
- size: `4476`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1401c36a8`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1401355d0`
- `0x14014b400`
- `0x14018708c`
- `0x140187e98`
- `0x14018901c`
- `0x1401893d4`
- `0x14018a1b4`
- `0x1401aee0c`
- `0x1401b3da8`
- `0x1401b414c`
- `0x1401b4500`
- `0x1401b48a0`
- `0x1401b4c64`
- `0x1401c0a2c`
- `0x1401c140c`
- `0x1401c1d58`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140187f46`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140188363`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401884d5`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140188614`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140188753`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401888c6`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140188a3d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140188d2c`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140187f46`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140188363`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401884d5`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140188614`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140188753`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401888c6`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140188a3d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140188d2c`
- `ntoskrnl!IofCallDriver` at `0x140188303`
- `ntoskrnl!IofCallDriver` at `0x140188303`
- `ntoskrnl!IofCompleteRequest` at `0x14018886c`
- `ntoskrnl!IofCompleteRequest` at `0x140188cea`
- `ntoskrnl!IofCompleteRequest` at `0x140188fdb`
- `ntoskrnl!IofCompleteRequest` at `0x14018886c`
- `ntoskrnl!IofCompleteRequest` at `0x140188cea`
- `ntoskrnl!IofCompleteRequest` at `0x140188fdb`

## pseudocode

```c
__int64 __fastcall NvmeNamespaceStorageQueryPropertyIoctl(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v3; // rax
  char v4; // di
  int *v6; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  bool v11; // zf
  unsigned __int64 v12; // rcx
  unsigned __int8 *v13; // rdx
  int v14; // eax
  int *v15; // rax
  int v16; // ecx
  __int64 v17; // rdx
  int v18; // eax
  unsigned int v19; // r12d
  unsigned __int8 v20; // r11
  char *v21; // r10
  char v22; // r15
  _BYTE *v23; // r9
  __int64 v24; // r14
  char v25; // r13
  unsigned __int64 v26; // rsi
  __int64 v27; // r8
  int v28; // ecx
  char v29; // cl
  char v30; // si
  char v31; // r10
  char v32; // r8
  _BYTE *v33; // rax
  char *v34; // r8
  unsigned int v35; // eax
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  __int64 v41; // rcx
  __int64 v42; // rcx
  int v44; // ecx
  int v45; // ecx
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  int v50; // ecx
  unsigned int v51; // esi
  unsigned int v53; // r12d
  __int64 v54; // r14
  char v55; // r13
  unsigned __int64 v56; // rsi
  __int64 v57; // r8
  int v58; // ecx
  unsigned int v59; // r12d
  __int64 v60; // r14
  char v61; // r13
  unsigned __int64 v62; // rsi
  int v63; // ecx
  unsigned int v64; // r12d
  __int64 v65; // r14
  char v66; // r13
  unsigned __int64 v67; // rsi
  int v68; // ecx
  unsigned int v69; // r12d
  __int64 v70; // r14
  char v71; // r13
  unsigned __int64 v72; // rsi
  int v73; // ecx
  unsigned int v74; // eax
  unsigned __int64 v75; // rcx
  unsigned __int8 *v76; // rdx
  int v77; // eax
  __int64 v78; // rdx
  int v79; // eax
  unsigned int v80; // r13d
  _BYTE *v81; // r9
  unsigned __int8 v82; // r11
  char *v83; // r10
  char v84; // r12
  __int64 v85; // r15
  unsigned __int64 v86; // r14
  __int64 v87; // r8
  int v88; // ecx
  unsigned int StorageProtocolSpecificProperty; // eax
  int *v90; // rax
  int v91; // ecx
  __int64 *v92; // rdx
  unsigned int v93; // r13d
  __int64 v94; // r15
  unsigned __int64 v95; // r14
  __int64 v96; // r8
  int v97; // ecx
  char v98; // cl
  char v99; // r14
  char v100; // r10
  char v101; // r8
  _BYTE *v102; // rax
  char *v103; // r8
  unsigned int v104; // eax
  unsigned __int64 v105; // rcx
  __int64 v106; // rdx
  int *v107; // rax
  int v108; // ecx
  __int64 v109; // rdx
  unsigned int v110; // r12d
  unsigned __int8 v111; // r11
  char *v112; // r10
  char v113; // r15
  _BYTE *v114; // r9
  __int64 v115; // r14
  char v116; // r13
  unsigned __int64 v117; // rsi
  __int64 v118; // r8
  int v119; // ecx
  char v120; // cl
  char v121; // si
  char v122; // r10
  char v123; // r8
  _BYTE *v124; // rax
  char *v125; // r8
  unsigned int v126; // eax
  int v127; // [rsp+20h] [rbp-60h]
  char v128; // [rsp+60h] [rbp-20h]
  char v129; // [rsp+60h] [rbp-20h]
  unsigned int v130; // [rsp+64h] [rbp-1Ch]
  __int128 v131; // [rsp+68h] [rbp-18h] BYREF

  v3 = *(_QWORD *)(a2 + 184);
  v4 = 1;
  *a3 = 1;
  v6 = *(int **)(a2 + 24);
  if ( !v6 || *(_DWORD *)(v3 + 16) < 8u )
  {
    v11 = StorEtwLoggingEnabled == 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = -1073741811;
    if ( v11 )
      goto LABEL_369;
    v131 = 0;
    IoGetActivityIdIrp(a2, &v131);
    v106 = *(_QWORD *)(a2 + 184);
    if ( *(_BYTE *)v106 == 14 )
    {
      if ( (byte_140177432 & 8) != 0 )
        McTemplateK0pd_EtwWriteTransfer(
          *(unsigned int *)(a2 + 48),
          EventNonReadWriteRequestComplete,
          &v131,
          a2,
          *(_DWORD *)(a2 + 48));
      goto LABEL_369;
    }
    if ( *(_BYTE *)v106 != 15 )
    {
      if ( *(_BYTE *)v106 == 27 )
      {
        if ( *(_BYTE *)(v106 + 1) != 7 || *(_DWORD *)(v106 + 8) )
        {
          if ( (byte_140177432 & 0x20) != 0 )
            McTemplateK0pd_EtwWriteTransfer(v105, EventPnpRequestComplete, &v131, a2, *(_DWORD *)(a2 + 48));
        }
        else if ( (byte_140177432 & 0x40) != 0 )
        {
          v107 = *(int **)(a2 + 56);
          if ( v107 )
            v108 = *v107;
          else
            v108 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v108, v106, (unsigned int)&v131, a2, v108, *(_DWORD *)(a2 + 48));
        }
      }
      goto LABEL_369;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_369;
    v109 = *(_QWORD *)(v106 + 8);
    if ( *(_BYTE *)(v109 + 2) == 40 )
    {
      if ( *(_DWORD *)(v109 + 20) )
        goto LABEL_369;
      v110 = *(_DWORD *)(v109 + 56);
      if ( !v110 )
        goto LABEL_369;
      v111 = 0;
      v112 = 0;
      v113 = 0;
      v114 = 0;
      v115 = 0;
      v116 = 0;
      while ( 1 )
      {
        v105 = *(unsigned int *)(v109 + 4 * v115 + 120);
        if ( (unsigned int)v105 >= 0x80 )
        {
          v117 = *(unsigned int *)(v109 + 16);
          if ( (unsigned int)v105 < (unsigned int)v117 )
          {
            v118 = (unsigned int)v105;
            v119 = *(_DWORD *)(v105 + v109) - 64;
            if ( v119 )
            {
              LODWORD(v105) = v119 - 1;
              if ( (_DWORD)v105 )
              {
                if ( (_DWORD)v105 == 1 )
                {
                  LODWORD(v105) = v118 + 40;
                  if ( v118 + 40 <= v117 )
                  {
                    if ( *(_DWORD *)(v118 + v109 + 12) )
                      v112 = (char *)(v118 + v109 + 32);
                    v114 = *(_BYTE **)(v118 + v109 + 24);
                    goto LABEL_344;
                  }
                }
              }
              else
              {
                LODWORD(v105) = v118 + 56;
                if ( v118 + 56 <= v117 )
                {
                  v116 = 1;
                  if ( *(_BYTE *)(v118 + v109 + 10) )
                    v112 = (char *)(v118 + v109 + 24);
                  v113 = *(_BYTE *)(v118 + v109 + 8);
                  v114 = *(_BYTE **)(v118 + v109 + 16);
                  v111 = *(_BYTE *)(v118 + v109 + 9);
                }
              }
            }
            else
            {
              LODWORD(v105) = v118 + 40;
              if ( v118 + 40 <= v117 )
              {
                if ( *(_BYTE *)(v118 + v109 + 10) )
                  v112 = (char *)(v118 + v109 + 24);
                v114 = *(_BYTE **)(v118 + v109 + 16);
LABEL_344:
                v111 = *(_BYTE *)(v118 + v109 + 9);
                v113 = *(_BYTE *)(v118 + v109 + 8);
LABEL_345:
                if ( v112 )
                {
                  v120 = *v112;
                  goto LABEL_348;
                }
                goto LABEL_369;
              }
            }
            if ( v116 )
              goto LABEL_345;
          }
        }
        v115 = (unsigned int)(v115 + 1);
        if ( (unsigned int)v115 >= v110 )
          goto LABEL_345;
      }
    }
    v120 = *(_BYTE *)(v109 + 72);
    v114 = *(_BYTE **)(v109 + 32);
    v111 = *(_BYTE *)(v109 + 11);
    v113 = *(_BYTE *)(v109 + 4);
    if ( *(_BYTE *)(v109 + 2) )
      goto LABEL_369;
LABEL_348:
    LOBYTE(v105) = v120 - 8;
    if ( (v105 & 0x5D) != 0 )
    {
LABEL_369:
      IofCompleteRequest((PIRP)a2, 0);
      return 3221225485LL;
    }
    v121 = *(_BYTE *)(v109 + 3);
    if ( v121 == 1 || !v114 || !v111 )
      goto LABEL_365;
    LOBYTE(v109) = 0;
    v122 = 0;
    v123 = 0;
    v105 = (unsigned __int64)&v114[v111];
    v124 = v114 + 8;
    if ( (unsigned __int8)((*v114 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v124 <= v105 )
      {
        v122 = v114[2];
        LOBYTE(v109) = v114[1] & 0xF;
        v123 = v114[3];
        goto LABEL_364;
      }
    }
    else if ( (unsigned __int64)v124 <= v105 )
    {
      v125 = v114 + 13;
      LOBYTE(v109) = v114[2] & 0xF;
      v126 = v111;
      if ( (unsigned int)(unsigned __int8)v114[7] + 8 <= v111 )
        v126 = (unsigned __int8)v114[7] + 8;
      v105 = (unsigned __int64)&v114[v126];
      if ( (unsigned __int64)v125 <= v105 )
        v122 = v114[12];
      if ( (unsigned __int64)(v114 + 14) > v105 )
        v123 = 0;
      else
        v123 = *v125;
LABEL_364:
      if ( v4 )
      {
LABEL_366:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v105,
          v109,
          (unsigned int)&v131,
          a2,
          *(_DWORD *)(a2 + 48),
          v121,
          v113,
          v109,
          v122,
          v123,
          a2);
        goto LABEL_369;
      }
LABEL_365:
      LOBYTE(v109) = 0;
      v122 = 0;
      v123 = 0;
      goto LABEL_366;
    }
    v4 = 0;
    goto LABEL_364;
  }
  v9 = *(_QWORD *)(a1 + 16);
  v10 = *(_QWORD *)(v9 + 136) & 2LL;
  if ( (*(_QWORD *)(v9 + 136) & 2) != 0 && *(_DWORD *)(v9 + 568) != 2 )
  {
    v11 = StorEtwLoggingEnabled == 0;
    v130 = -1073741300;
    *(_DWORD *)(a2 + 48) = -1073741300;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    if ( v11 )
      goto LABEL_207;
    v131 = 0;
    IoGetActivityIdIrp(a2, &v131);
    v13 = *(unsigned __int8 **)(a2 + 184);
    if ( *v13 != 14 )
    {
      v14 = *v13 - 15;
      if ( *v13 != 15 )
        goto LABEL_8;
      if ( byte_140177431 >= 0 )
        goto LABEL_207;
      v17 = *((_QWORD *)v13 + 1);
      v18 = *(unsigned __int8 *)(v17 + 2);
      if ( (_BYTE)v18 == 40 )
      {
        if ( !*(_DWORD *)(v17 + 20) )
        {
          v19 = *(_DWORD *)(v17 + 56);
          if ( v19 )
          {
            v20 = 0;
            v21 = 0;
            v22 = 0;
            v23 = 0;
            v24 = 0;
            v25 = 0;
            while ( 1 )
            {
              v12 = *(unsigned int *)(v17 + 4 * v24 + 120);
              if ( (unsigned int)v12 >= 0x80 )
              {
                v26 = *(unsigned int *)(v17 + 16);
                if ( (unsigned int)v12 < (unsigned int)v26 )
                {
                  v27 = (unsigned int)v12;
                  v28 = *(_DWORD *)(v12 + v17) - 64;
                  if ( v28 )
                  {
                    LODWORD(v12) = v28 - 1;
                    if ( (_DWORD)v12 )
                    {
                      if ( (_DWORD)v12 == 1 )
                      {
                        LODWORD(v12) = v27 + 40;
                        if ( v27 + 40 <= v26 )
                          goto LABEL_29;
                      }
                    }
                    else
                    {
                      LODWORD(v12) = v27 + 56;
                      if ( v27 + 56 <= v26 )
                      {
                        v25 = 1;
                        if ( *(_BYTE *)(v27 + v17 + 10) )
                          v21 = (char *)(v27 + v17 + 24);
                        v22 = *(_BYTE *)(v27 + v17 + 8);
                        v23 = *(_BYTE **)(v27 + v17 + 16);
                        v20 = *(_BYTE *)(v27 + v17 + 9);
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v12) = v27 + 40;
                    if ( v27 + 40 <= v26 )
                      goto LABEL_40;
                  }
                  if ( v25 )
                    goto LABEL_44;
                }
              }
              v24 = (unsigned int)(v24 + 1);
              if ( (unsigned int)v24 >= v19 )
                goto LABEL_44;
            }
          }
        }
        goto LABEL_207;
      }
      goto LABEL_46;
    }
    goto LABEL_66;
  }
  v36 = *v6;
  if ( v36 <= 48 )
  {
    if ( v36 == 48 )
      return (unsigned int)NvmeNamespaceStorageQueryDeviceIoCapabilityPropertyIoctl(a1, a2);
    if ( !v36 )
      return (unsigned int)NvmeNamespaceStorageQueryDevicePropertyIoctl(a1, a2);
    v37 = v36 - 1;
    if ( !v37 )
      return (unsigned int)NvmeNamespaceStorageQueryAdapterPropertyIoctl(a1, a2);
    v38 = v37 - 1;
    if ( !v38 )
      return (unsigned int)NvmeNamespaceStorageQueryDeviceIdPropertyIoctl(a1, a2);
    v39 = v38 - 2;
    if ( !v39 )
      return (unsigned int)NvmeNamespaceStorageQueryDeviceWriteCachePropertyIoctl(a1, a2);
    v40 = v39 - 2;
    if ( !v40 )
      return (unsigned int)NvmeNamespaceStorageQueryAccessAlignmentPropertyIoctl(a1, a2);
    v41 = (unsigned int)(v40 - 1);
    if ( !(_DWORD)v41 )
      return (unsigned int)NvmeNamespaceStorageQueryDeviceSeekPenaltyPropertyIoctl(v41, a2);
    v42 = (unsigned int)(v41 - 1);
    if ( !(_DWORD)v42 )
      return (unsigned int)NvmeNamespaceStorageQueryDeviceTrimPropertyIoctl(a1, a2);
    if ( (_DWORD)v42 == 4 )
      return (unsigned int)NvmeNamespaceStorageQueryDevicePowerPropertyIoctl(v42, a2);
LABEL_95:
    ++*(_BYTE *)(a2 + 67);
    *(_QWORD *)(a2 + 184) += 72LL;
    return (unsigned int)IofCallDriver(*(PDEVICE_OBJECT *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 128LL) + 8LL), (PIRP)a2);
  }
  v44 = v36 - 49;
  if ( !v44 )
  {
LABEL_239:
    if ( *(_BYTE *)(v9 + 1728) != 1 )
      goto LABEL_95;
    StorageProtocolSpecificProperty = NvmeCommonGetStorageProtocolSpecificProperty(*(_QWORD *)(a1 + 8), a2, a3);
    v51 = StorageProtocolSpecificProperty;
    if ( StorageProtocolSpecificProperty == 259 )
    {
LABEL_209:
      *a3 = 0;
      return v51;
    }
    v11 = StorEtwLoggingEnabled == 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = StorageProtocolSpecificProperty;
    if ( v11 )
      goto LABEL_305;
    v131 = 0;
    IoGetActivityIdIrp(a2, &v131);
    v76 = *(unsigned __int8 **)(a2 + 184);
    if ( *v76 != 14 )
    {
      v77 = *v76 - 15;
      if ( *v76 == 15 )
      {
        if ( byte_140177431 >= 0 )
          goto LABEL_305;
        v78 = *((_QWORD *)v76 + 1);
        v79 = *(unsigned __int8 *)(v78 + 2);
        if ( (_BYTE)v79 == 40 )
        {
          if ( *(_DWORD *)(v78 + 20) )
            goto LABEL_305;
          v93 = *(_DWORD *)(v78 + 56);
          if ( !v93 )
            goto LABEL_305;
          v81 = 0;
          v82 = 0;
          v83 = 0;
          v129 = 0;
          v84 = 0;
          v94 = 0;
          while ( 1 )
          {
            v75 = *(unsigned int *)(v78 + 4 * v94 + 120);
            if ( (unsigned int)v75 >= 0x80 )
            {
              v95 = *(unsigned int *)(v78 + 16);
              if ( (unsigned int)v75 < (unsigned int)v95 )
              {
                v96 = (unsigned int)v75;
                v97 = *(_DWORD *)(v78 + v75) - 64;
                if ( v97 )
                {
                  LODWORD(v75) = v97 - 1;
                  if ( (_DWORD)v75 )
                  {
                    if ( (_DWORD)v75 == 1 )
                    {
                      LODWORD(v75) = v96 + 40;
                      if ( v96 + 40 <= v95 )
                      {
                        if ( *(_DWORD *)(v78 + v96 + 12) )
                          v83 = (char *)(v96 + v78 + 32);
                        v81 = *(_BYTE **)(v78 + v96 + 24);
LABEL_279:
                        v82 = *(_BYTE *)(v78 + v96 + 9);
                        v84 = *(_BYTE *)(v78 + v96 + 8);
                        goto LABEL_280;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v75) = v96 + 56;
                    if ( v96 + 56 <= v95 )
                    {
                      v129 = 1;
                      if ( *(_BYTE *)(v78 + v96 + 10) )
                        v83 = (char *)(v96 + v78 + 24);
                      v84 = *(_BYTE *)(v78 + v96 + 8);
                      v81 = *(_BYTE **)(v78 + v96 + 16);
                      v82 = *(_BYTE *)(v78 + v96 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v75) = v96 + 40;
                  if ( v96 + 40 <= v95 )
                  {
                    if ( *(_BYTE *)(v78 + v96 + 10) )
                      v83 = (char *)(v96 + v78 + 24);
                    v81 = *(_BYTE **)(v78 + v96 + 16);
                    goto LABEL_279;
                  }
                }
                if ( v129 )
                  goto LABEL_280;
              }
            }
            v94 = (unsigned int)(v94 + 1);
            if ( (unsigned int)v94 >= v93 )
              goto LABEL_280;
          }
        }
LABEL_282:
        v84 = *(_BYTE *)(v78 + 4);
        v82 = *(_BYTE *)(v78 + 11);
        v81 = *(_BYTE **)(v78 + 32);
        v98 = *(_BYTE *)(v78 + 72);
        if ( v79 )
          goto LABEL_305;
LABEL_283:
        LOBYTE(v75) = v98 - 8;
        if ( (v75 & 0x5D) != 0 )
        {
LABEL_305:
          IofCompleteRequest((PIRP)a2, 0);
          return v51;
        }
        v99 = *(_BYTE *)(v78 + 3);
        if ( v99 == 1 || !v81 || !v82 )
          goto LABEL_300;
        LOBYTE(v78) = 0;
        v100 = 0;
        v101 = 0;
        v75 = (unsigned __int64)&v81[v82];
        v102 = v81 + 8;
        if ( (unsigned __int8)((*v81 & 0x7F) - 114) <= 1u )
        {
          if ( (unsigned __int64)v102 <= v75 )
          {
            v100 = v81[2];
            LOBYTE(v78) = v81[1] & 0xF;
            v101 = v81[3];
            goto LABEL_299;
          }
        }
        else if ( (unsigned __int64)v102 <= v75 )
        {
          v103 = v81 + 13;
          LOBYTE(v78) = v81[2] & 0xF;
          v104 = v82;
          if ( (unsigned int)(unsigned __int8)v81[7] + 8 <= v82 )
            v104 = (unsigned __int8)v81[7] + 8;
          v75 = (unsigned __int64)&v81[v104];
          if ( (unsigned __int64)v103 <= v75 )
            v100 = v81[12];
          if ( (unsigned __int64)(v81 + 14) > v75 )
            v101 = 0;
          else
            v101 = *v103;
LABEL_299:
          if ( v4 )
          {
LABEL_301:
            McTemplateK0pduuuuup_EtwWriteTransfer(
              v75,
              v78,
              (unsigned int)&v131,
              a2,
              *(_DWORD *)(a2 + 48),
              v99,
              v84,
              v78,
              v100,
              v101,
              a2);
            goto LABEL_305;
          }
LABEL_300:
          LOBYTE(v78) = 0;
          v100 = 0;
          v101 = 0;
          goto LABEL_301;
        }
        v4 = 0;
        goto LABEL_299;
      }
      goto LABEL_244;
    }
LABEL_302:
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_305;
    v92 = EventNonReadWriteRequestComplete;
    goto LABEL_304;
  }
  v45 = v44 - 1;
  if ( !v45 )
    goto LABEL_180;
  v46 = v45 - 9;
  if ( !v46 )
  {
    if ( !v10 )
      return (unsigned int)NvmeNamespaceStorageQueryDeviceNumaPropertyIoctl(a1, a2);
    v11 = StorEtwLoggingEnabled == 0;
    v130 = -1073741637;
    *(_DWORD *)(a2 + 48) = -1073741637;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    if ( v11 )
      goto LABEL_207;
    v131 = 0;
    IoGetActivityIdIrp(a2, &v131);
    v13 = *(unsigned __int8 **)(a2 + 184);
    if ( *v13 != 14 )
    {
      v14 = *v13 - 15;
      if ( *v13 == 15 )
      {
        if ( byte_140177431 >= 0 )
          goto LABEL_207;
        v17 = *((_QWORD *)v13 + 1);
        v18 = *(unsigned __int8 *)(v17 + 2);
        if ( (_BYTE)v18 == 40 )
        {
          if ( *(_DWORD *)(v17 + 20) )
            goto LABEL_207;
          v64 = *(_DWORD *)(v17 + 56);
          if ( !v64 )
            goto LABEL_207;
          v20 = 0;
          v21 = 0;
          v22 = 0;
          v23 = 0;
          v65 = 0;
          v66 = 0;
          while ( 1 )
          {
            v12 = *(unsigned int *)(v17 + 4 * v65 + 120);
            if ( (unsigned int)v12 >= 0x80 )
            {
              v67 = *(unsigned int *)(v17 + 16);
              if ( (unsigned int)v12 < (unsigned int)v67 )
              {
                v57 = (unsigned int)v12;
                v68 = *(_DWORD *)(v17 + v12) - 64;
                if ( v68 )
                {
                  LODWORD(v12) = v68 - 1;
                  if ( (_DWORD)v12 )
                  {
                    if ( (_DWORD)v12 == 1 )
                    {
                      LODWORD(v12) = v57 + 40;
                      if ( v57 + 40 <= v67 )
                      {
LABEL_114:
                        if ( *(_DWORD *)(v17 + v57 + 12) )
                          v21 = (char *)(v57 + v17 + 32);
                        v23 = *(_BYTE **)(v17 + v57 + 24);
LABEL_128:
                        v20 = *(_BYTE *)(v17 + v57 + 9);
                        v22 = *(_BYTE *)(v17 + v57 + 8);
                        goto LABEL_44;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v12) = v57 + 56;
                    if ( v57 + 56 <= v67 )
                    {
                      v66 = 1;
                      if ( *(_BYTE *)(v17 + v57 + 10) )
                        v21 = (char *)(v57 + v17 + 24);
                      v22 = *(_BYTE *)(v17 + v57 + 8);
                      v23 = *(_BYTE **)(v17 + v57 + 16);
                      v20 = *(_BYTE *)(v17 + v57 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v12) = v57 + 40;
                  if ( v57 + 40 <= v67 )
                  {
LABEL_125:
                    if ( *(_BYTE *)(v17 + v57 + 10) )
                      v21 = (char *)(v57 + v17 + 24);
                    v23 = *(_BYTE **)(v17 + v57 + 16);
                    goto LABEL_128;
                  }
                }
                if ( v66 )
                  goto LABEL_44;
              }
            }
            v65 = (unsigned int)(v65 + 1);
            if ( (unsigned int)v65 >= v64 )
              goto LABEL_44;
          }
        }
        goto LABEL_46;
      }
      goto LABEL_8;
    }
    goto LABEL_66;
  }
  v47 = v46 - 3;
  if ( !v47 )
  {
    if ( !v10 )
      return (unsigned int)NvmeNamespaceStorageQueryDeviceEndurancePropertyIoctl(a1, a2);
    v11 = StorEtwLoggingEnabled == 0;
    v130 = -1073741637;
    *(_DWORD *)(a2 + 48) = -1073741637;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    if ( v11 )
      goto LABEL_207;
    v131 = 0;
    IoGetActivityIdIrp(a2, &v131);
    v13 = *(unsigned __int8 **)(a2 + 184);
    if ( *v13 != 14 )
    {
      v14 = *v13 - 15;
      if ( *v13 == 15 )
      {
        if ( byte_140177431 >= 0 )
          goto LABEL_207;
        v17 = *((_QWORD *)v13 + 1);
        v18 = *(unsigned __int8 *)(v17 + 2);
        if ( (_BYTE)v18 == 40 )
        {
          if ( *(_DWORD *)(v17 + 20) )
            goto LABEL_207;
          v59 = *(_DWORD *)(v17 + 56);
          if ( !v59 )
            goto LABEL_207;
          v20 = 0;
          v21 = 0;
          v22 = 0;
          v23 = 0;
          v60 = 0;
          v61 = 0;
          while ( 1 )
          {
            v12 = *(unsigned int *)(v17 + 4 * v60 + 120);
            if ( (unsigned int)v12 >= 0x80 )
            {
              v62 = *(unsigned int *)(v17 + 16);
              if ( (unsigned int)v12 < (unsigned int)v62 )
              {
                v57 = (unsigned int)v12;
                v63 = *(_DWORD *)(v17 + v12) - 64;
                if ( v63 )
                {
                  LODWORD(v12) = v63 - 1;
                  if ( (_DWORD)v12 )
                  {
                    if ( (_DWORD)v12 == 1 )
                    {
                      LODWORD(v12) = v57 + 40;
                      if ( v57 + 40 <= v62 )
                        goto LABEL_114;
                    }
                  }
                  else
                  {
                    LODWORD(v12) = v57 + 56;
                    if ( v57 + 56 <= v62 )
                    {
                      v61 = 1;
                      if ( *(_BYTE *)(v17 + v57 + 10) )
                        v21 = (char *)(v57 + v17 + 24);
                      v22 = *(_BYTE *)(v17 + v57 + 8);
                      v23 = *(_BYTE **)(v17 + v57 + 16);
                      v20 = *(_BYTE *)(v17 + v57 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v12) = v57 + 40;
                  if ( v57 + 40 <= v62 )
                    goto LABEL_125;
                }
                if ( v61 )
                  goto LABEL_44;
              }
            }
            v60 = (unsigned int)(v60 + 1);
            if ( (unsigned int)v60 >= v59 )
              goto LABEL_44;
          }
        }
        goto LABEL_46;
      }
      goto LABEL_8;
    }
LABEL_66:
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_207;
    v127 = *(_DWORD *)(a2 + 48);
LABEL_206:
    McTemplateK0pd_EtwWriteTransfer(v12, EventNonReadWriteRequestComplete, &v131, a2, v127);
    goto LABEL_207;
  }
  v48 = v47 - 1;
  if ( !v48 )
  {
    if ( !v10 )
      return (unsigned int)NvmeNamespaceStorageQueryDeviceLedStatePropertyIoctl(a1, a2);
    v11 = StorEtwLoggingEnabled == 0;
    v130 = -1073741637;
    *(_DWORD *)(a2 + 48) = -1073741637;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    if ( v11 )
      goto LABEL_207;
    v131 = 0;
    IoGetActivityIdIrp(a2, &v131);
    v13 = *(unsigned __int8 **)(a2 + 184);
    if ( *v13 != 14 )
    {
      v14 = *v13 - 15;
      if ( *v13 == 15 )
      {
        if ( byte_140177431 >= 0 )
          goto LABEL_207;
        v17 = *((_QWORD *)v13 + 1);
        v18 = *(unsigned __int8 *)(v17 + 2);
        if ( (_BYTE)v18 == 40 )
        {
          if ( *(_DWORD *)(v17 + 20) )
            goto LABEL_207;
          v53 = *(_DWORD *)(v17 + 56);
          if ( !v53 )
            goto LABEL_207;
          v20 = 0;
          v21 = 0;
          v22 = 0;
          v23 = 0;
          v54 = 0;
          v55 = 0;
          while ( 1 )
          {
            v12 = *(unsigned int *)(v17 + 4 * v54 + 120);
            if ( (unsigned int)v12 >= 0x80 )
            {
              v56 = *(unsigned int *)(v17 + 16);
              if ( (unsigned int)v12 < (unsigned int)v56 )
              {
                v57 = (unsigned int)v12;
                v58 = *(_DWORD *)(v17 + v12) - 64;
                if ( v58 )
                {
                  LODWORD(v12) = v58 - 1;
                  if ( (_DWORD)v12 )
                  {
                    if ( (_DWORD)v12 == 1 )
                    {
                      LODWORD(v12) = v57 + 40;
                      if ( v57 + 40 <= v56 )
                        goto LABEL_114;
                    }
                  }
                  else
                  {
                    LODWORD(v12) = v57 + 56;
                    if ( v57 + 56 <= v56 )
                    {
                      v55 = 1;
                      if ( *(_BYTE *)(v17 + v57 + 10) )
                        v21 = (char *)(v57 + v17 + 24);
                      v22 = *(_BYTE *)(v17 + v57 + 8);
                      v23 = *(_BYTE **)(v17 + v57 + 16);
                      v20 = *(_BYTE *)(v17 + v57 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v12) = v57 + 40;
                  if ( v57 + 40 <= v56 )
                    goto LABEL_125;
                }
                if ( v55 )
                  goto LABEL_44;
              }
            }
            v54 = (unsigned int)(v54 + 1);
            if ( (unsigned int)v54 >= v53 )
              goto LABEL_44;
          }
        }
        goto LABEL_46;
      }
LABEL_8:
      if ( v14 == 12 )
      {
        if ( v13[1] != 7 || *((_DWORD *)v13 + 2) )
        {
          if ( (byte_140177432 & 0x20) != 0 )
            McTemplateK0pd_EtwWriteTransfer(v12, EventPnpRequestComplete, &v131, a2, *(_DWORD *)(a2 + 48));
        }
        else if ( (byte_140177432 & 0x40) != 0 )
        {
          v15 = *(int **)(a2 + 56);
          if ( v15 )
            v16 = *v15;
          else
            v16 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v16, (_DWORD)v13, (unsigned int)&v131, a2, v16, *(_DWORD *)(a2 + 48));
        }
      }
      goto LABEL_207;
    }
    goto LABEL_66;
  }
  v49 = v48 - 3;
  if ( !v49 )
    return (unsigned int)NvmeNamespaceGetStorageStackPropertyIoctl(a1, a2);
  v50 = v49 - 1;
  if ( !v50 )
    goto LABEL_239;
  if ( v50 != 1 )
    goto LABEL_95;
LABEL_180:
  if ( !v10 )
  {
    v74 = NvmeCommonGetStorageProtocolSpecificProperty(*(_QWORD *)(a1 + 8), a2, a3);
    v51 = v74;
    if ( v74 == 259 )
      goto LABEL_209;
    v11 = StorEtwLoggingEnabled == 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = v74;
    if ( v11 )
      goto LABEL_305;
    v131 = 0;
    IoGetActivityIdIrp(a2, &v131);
    v76 = *(unsigned __int8 **)(a2 + 184);
    if ( *v76 != 14 )
    {
      v77 = *v76 - 15;
      if ( *v76 == 15 )
      {
        if ( byte_140177431 >= 0 )
          goto LABEL_305;
        v78 = *((_QWORD *)v76 + 1);
        v79 = *(unsigned __int8 *)(v78 + 2);
        if ( (_BYTE)v79 == 40 )
        {
          if ( *(_DWORD *)(v78 + 20) )
            goto LABEL_305;
          v80 = *(_DWORD *)(v78 + 56);
          if ( !v80 )
            goto LABEL_305;
          v81 = 0;
          v82 = 0;
          v83 = 0;
          v128 = 0;
          v84 = 0;
          v85 = 0;
          while ( 1 )
          {
            v75 = *(unsigned int *)(v78 + 4 * v85 + 120);
            if ( (unsigned int)v75 >= 0x80 )
            {
              v86 = *(unsigned int *)(v78 + 16);
              if ( (unsigned int)v75 < (unsigned int)v86 )
              {
                v87 = (unsigned int)v75;
                v88 = *(_DWORD *)(v75 + v78) - 64;
                if ( v88 )
                {
                  LODWORD(v75) = v88 - 1;
                  if ( (_DWORD)v75 )
                  {
                    if ( (_DWORD)v75 == 1 )
                    {
                      LODWORD(v75) = v87 + 40;
                      if ( v87 + 40 <= v86 )
                      {
                        if ( *(_DWORD *)(v87 + v78 + 12) )
                          v83 = (char *)(v87 + v78 + 32);
                        v81 = *(_BYTE **)(v87 + v78 + 24);
                        goto LABEL_238;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v75) = v87 + 56;
                    if ( v87 + 56 <= v86 )
                    {
                      v128 = 1;
                      if ( *(_BYTE *)(v87 + v78 + 10) )
                        v83 = (char *)(v87 + v78 + 24);
                      v84 = *(_BYTE *)(v87 + v78 + 8);
                      v81 = *(_BYTE **)(v87 + v78 + 16);
                      v82 = *(_BYTE *)(v87 + v78 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v75) = v87 + 40;
                  if ( v87 + 40 <= v86 )
                  {
                    if ( *(_BYTE *)(v87 + v78 + 10) )
                      v83 = (char *)(v87 + v78 + 24);
                    v81 = *(_BYTE **)(v87 + v78 + 16);
LABEL_238:
                    v82 = *(_BYTE *)(v87 + v78 + 9);
                    v84 = *(_BYTE *)(v87 + v78 + 8);
LABEL_280:
                    if ( v83 )
                    {
                      v98 = *v83;
                      goto LABEL_283;
                    }
                    goto LABEL_305;
                  }
                }
                if ( v128 )
                  goto LABEL_280;
              }
            }
            v85 = (unsigned int)(v85 + 1);
            if ( (unsigned int)v85 >= v80 )
              goto LABEL_280;
          }
        }
        goto LABEL_282;
      }
LABEL_244:
      if ( v77 != 12 )
        goto LABEL_305;
      if ( v76[1] == 7 && !*((_DWORD *)v76 + 2) )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          v90 = *(int **)(a2 + 56);
          if ( v90 )
            v91 = *v90;
          else
            v91 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v91, (_DWORD)v76, (unsigned int)&v131, a2, v91, *(_DWORD *)(a2 + 48));
        }
        goto LABEL_305;
      }
      if ( (byte_140177432 & 0x20) == 0 )
        goto LABEL_305;
      v92 = EventPnpRequestComplete;
LABEL_304:
      McTemplateK0pd_EtwWriteTransfer(v75, v92, &v131, a2, *(_DWORD *)(a2 + 48));
      goto LABEL_305;
    }
    goto LABEL_302;
  }
  v11 = StorEtwLoggingEnabled == 0;
  v130 = -1073741637;
  *(_DWORD *)(a2 + 48) = -1073741637;
  *(_QWORD *)(a2 + 56) = 0;
  *(_BYTE *)(a2 + 141) = -84;
  if ( v11 )
    goto LABEL_207;
  v131 = 0;
  IoGetActivityIdIrp(a2, &v131);
  v13 = *(unsigned __int8 **)(a2 + 184);
  if ( *v13 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_207;
    v12 = *(unsigned int *)(a2 + 48);
    v127 = *(_DWORD *)(a2 + 48);
    goto LABEL_206;
  }
  v14 = *v13 - 15;
  if ( *v13 != 15 )
    goto LABEL_8;
  if ( byte_140177431 >= 0 )
    goto LABEL_207;
  v17 = *((_QWORD *)v13 + 1);
  v18 = *(unsigned __int8 *)(v17 + 2);
  if ( (_BYTE)v18 == 40 )
  {
    if ( *(_DWORD *)(v17 + 20) )
      goto LABEL_207;
    v69 = *(_DWORD *)(v17 + 56);
    if ( !v69 )
      goto LABEL_207;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v70 = 0;
    v71 = 0;
    while ( 1 )
    {
      v12 = *(unsigned int *)(v17 + 4 * v70 + 120);
      if ( (unsigned int)v12 >= 0x80 )
      {
        v72 = *(unsigned int *)(v17 + 16);
        if ( (unsigned int)v12 < (unsigned int)v72 )
        {
          v27 = (unsigned int)v12;
          v73 = *(_DWORD *)(v12 + v17) - 64;
          if ( v73 )
          {
            LODWORD(v12) = v73 - 1;
            if ( (_DWORD)v12 )
            {
              if ( (_DWORD)v12 == 1 )
              {
                LODWORD(v12) = v27 + 40;
                if ( v27 + 40 <= v72 )
                {
LABEL_29:
                  if ( *(_DWORD *)(v27 + v17 + 12) )
                    v21 = (char *)(v27 + v17 + 32);
                  v23 = *(_BYTE **)(v27 + v17 + 24);
                  goto LABEL_43;
                }
              }
            }
            else
            {
              LODWORD(v12) = v27 + 56;
              if ( v27 + 56 <= v72 )
              {
                v71 = 1;
                if ( *(_BYTE *)(v27 + v17 + 10) )
                  v21 = (char *)(v27 + v17 + 24);
                v22 = *(_BYTE *)(v27 + v17 + 8);
                v23 = *(_BYTE **)(v27 + v17 + 16);
                v20 = *(_BYTE *)(v27 + v17 + 9);
              }
            }
          }
          else
          {
            LODWORD(v12) = v27 + 40;
            if ( v27 + 40 <= v72 )
            {
LABEL_40:
              if ( *(_BYTE *)(v27 + v17 + 10) )
                v21 = (char *)(v27 + v17 + 24);
              v23 = *(_BYTE **)(v27 + v17 + 16);
LABEL_43:
              v20 = *(_BYTE *)(v27 + v17 + 9);
              v22 = *(_BYTE *)(v27 + v17 + 8);
LABEL_44:
              if ( v21 )
              {
                v29 = *v21;
                goto LABEL_47;
              }
              goto LABEL_207;
            }
          }
          if ( v71 )
            goto LABEL_44;
        }
      }
      v70 = (unsigned int)(v70 + 1);
      if ( (unsigned int)v70 >= v69 )
        goto LABEL_44;
    }
  }
LABEL_46:
  v29 = *(_BYTE *)(v17 + 72);
  v23 = *(_BYTE **)(v17 + 32);
  v20 = *(_BYTE *)(v17 + 11);
  v22 = *(_BYTE *)(v17 + 4);
  if ( v18 )
    goto LABEL_207;
LABEL_47:
  LOBYTE(v12) = v29 - 8;
  if ( (v12 & 0x5D) == 0 )
  {
    v30 = *(_BYTE *)(v17 + 3);
    if ( v30 == 1 || !v23 || !v20 )
      goto LABEL_64;
    LOBYTE(v17) = 0;
    v31 = 0;
    v32 = 0;
    v12 = (unsigned __int64)&v23[v20];
    v33 = v23 + 8;
    if ( (unsigned __int8)((*v23 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v33 <= v12 )
      {
        v31 = v23[2];
        LOBYTE(v17) = v23[1] & 0xF;
        v32 = v23[3];
        goto LABEL_63;
      }
    }
    else if ( (unsigned __int64)v33 <= v12 )
    {
      v34 = v23 + 13;
      LOBYTE(v17) = v23[2] & 0xF;
      v35 = v20;
      if ( (unsigned int)(unsigned __int8)v23[7] + 8 <= v20 )
        v35 = (unsigned __int8)v23[7] + 8;
      v12 = (unsigned __int64)&v23[v35];
      if ( (unsigned __int64)v34 <= v12 )
        v31 = v23[12];
      if ( (unsigned __int64)(v23 + 14) > v12 )
        v32 = 0;
      else
        v32 = *v34;
LABEL_63:
      if ( v4 )
      {
LABEL_65:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v12,
          v17,
          (unsigned int)&v131,
          a2,
          *(_DWORD *)(a2 + 48),
          v30,
          v22,
          v17,
          v31,
          v32,
          a2);
        goto LABEL_207;
      }
LABEL_64:
      LOBYTE(v17) = 0;
      v31 = 0;
      v32 = 0;
      goto LABEL_65;
    }
    v4 = 0;
    goto LABEL_63;
  }
LABEL_207:
  IofCompleteRequest((PIRP)a2, 0);
  return v130;
}

```

## disassembly

```asm
0x140187e98  mov     [rsp-38h+arg_18], rbx
0x140187e9d  push    rbp
0x140187e9e  push    rsi
0x140187e9f  push    rdi
0x140187ea0  push    r12
0x140187ea2  push    r13
0x140187ea4  push    r14
0x140187ea6  push    r15
0x140187ea8  mov     rbp, rsp
0x140187eab  sub     rsp, 80h
0x140187eb2  mov     rax, cs:__security_cookie
0x140187eb9  xor     rax, rsp
0x140187ebc  mov     [rbp+var_8], rax
0x140187ec0  mov     rax, [rdx+0B8h]
0x140187ec7  mov     edi, 1
0x140187ecc  mov     [r8], dil
0x140187ecf  mov     r9, rcx
0x140187ed2  mov     rcx, [rdx+18h]
0x140187ed6  mov     r14, r8
0x140187ed9  mov     rbx, rdx
0x140187edc  test    rcx, rcx
0x140187edf  jz      loc_140188CFB
0x140187ee5  cmp     dword ptr [rax+10h], 8
0x140187ee9  jb      loc_140188CFB
0x140187eef  mov     r8, [r9+10h]
0x140187ef3  mov     rdx, [r8+88h]
0x140187efa  and     edx, 2
0x140187efd  jz      loc_1401881E9
0x140187f03  cmp     dword ptr [r8+238h], 2
0x140187f0b  jz      loc_1401881E9
0x140187f11  cmp     cs:StorEtwLoggingEnabled, 0
0x140187f18  mov     eax, 0C000020Ch
0x140187f1d  mov     [rbp+var_1C], eax
0x140187f20  mov     [rbx+30h], eax
0x140187f23  mov     qword ptr [rbx+38h], 0
0x140187f2b  mov     byte ptr [rbx+8Dh], 0ACh
0x140187f32  jz      loc_140188867
0x140187f38  xorps   xmm0, xmm0
0x140187f3b  lea     rdx, [rbp+var_18]
0x140187f3f  mov     rcx, rbx
0x140187f42  movups  [rbp+var_18], xmm0
0x140187f46  call    cs:__imp_IoGetActivityIdIrp
0x140187f4d  nop     dword ptr [rax+rax+00h]
0x140187f52  mov     rdx, [rbx+0B8h]
0x140187f59  movzx   eax, byte ptr [rdx]
0x140187f5c  sub     eax, 0Eh
0x140187f5f  jz      loc_1401881D0
0x140187f65  sub     eax, edi
0x140187f67  jz      short loc_140187FD6
0x140187f69  cmp     eax, 0Ch
0x140187f6c  jnz     loc_140188867
0x140187f72  cmp     byte ptr [rdx+1], 7
0x140187f76  jnz     short loc_140187FB6
0x140187f78  cmp     dword ptr [rdx+8], 0
0x140187f7c  jnz     short loc_140187FB6
0x140187f7e  test    cs:byte_140177432, 40h
0x140187f85  jz      loc_140188867
0x140187f8b  mov     rax, [rbx+38h]
0x140187f8f  test    rax, rax
0x140187f92  jz      short loc_140187F98
0x140187f94  mov     ecx, [rax]
0x140187f96  jmp     short loc_140187F9A
0x140187f98  xor     ecx, ecx
0x140187f9a  mov     eax, [rbx+30h]
0x140187f9d  lea     r8, [rbp+var_18]
0x140187fa1  mov     [rsp+80h+var_58], eax
0x140187fa5  mov     r9, rbx
0x140187fa8  mov     [rsp+80h+var_60], ecx
0x140187fac  call    McTemplateK0pqd_EtwWriteTransfer
0x140187fb1  jmp     loc_140188867
0x140187fb6  test    cs:byte_140177432, 20h
0x140187fbd  jz      loc_140188867
0x140187fc3  mov     eax, [rbx+30h]
0x140187fc6  lea     rdx, EventPnpRequestComplete
0x140187fcd  mov     [rsp+80h+var_60], eax
0x140187fd1  jmp     loc_14018885B
0x140187fd6  cmp     cs:byte_140177431, 0
0x140187fdd  jge     loc_140188867
0x140187fe3  mov     rdx, [rdx+8]
0x140187fe7  movzx   eax, byte ptr [rdx+2]
0x140187feb  cmp     al, 28h ; '('
0x140187fed  jnz     loc_1401880D6
0x140187ff3  cmp     dword ptr [rdx+14h], 0
0x140187ff7  jnz     loc_140188867
0x140187ffd  mov     r12d, [rdx+38h]
0x140188001  test    r12d, r12d
0x140188004  jz      loc_140188867
0x14018800a  xor     r11b, r11b
0x14018800d  xor     r10d, r10d
0x140188010  xor     r15b, r15b
0x140188013  xor     r9d, r9d
0x140188016  xor     r14d, r14d
0x140188019  xor     r13b, r13b
0x14018801c  mov     ecx, [rdx+r14*4+78h]
0x140188021  cmp     ecx, 80h
0x140188027  jb      short loc_14018809C
0x140188029  mov     esi, [rdx+10h]
0x14018802c  cmp     ecx, esi
0x14018802e  jnb     short loc_14018809C
0x140188030  mov     r8d, ecx
0x140188033  mov     ecx, [rcx+rdx]
0x140188036  sub     ecx, 40h ; '@'
0x140188039  jz      short loc_14018808E
0x14018803b  sub     ecx, edi
0x14018803d  jz      short loc_140188062
0x14018803f  cmp     ecx, edi
0x140188041  jnz     short loc_140188097
0x140188043  lea     rcx, [r8+28h]
0x140188047  cmp     rcx, rsi
0x14018804a  ja      short loc_140188097
0x14018804c  cmp     dword ptr [r8+rdx+0Ch], 0
0x140188052  jbe     short loc_14018805B
0x140188054  lea     r10, [rdx+20h]
0x140188058  add     r10, r8
0x14018805b  mov     r9, [r8+rdx+18h]
0x140188060  jmp     short loc_1401880BE
0x140188062  lea     rcx, [r8+38h]
0x140188066  cmp     rcx, rsi
0x140188069  ja      short loc_140188097
0x14018806b  cmp     byte ptr [r8+rdx+0Ah], 0
0x140188071  mov     r13b, dil
0x140188074  jbe     short loc_14018807D
0x140188076  lea     r10, [rdx+18h]
0x14018807a  add     r10, r8
0x14018807d  mov     r15b, [r8+rdx+8]
0x140188082  mov     r9, [r8+rdx+10h]
0x140188087  mov     r11b, [r8+rdx+9]
0x14018808c  jmp     short loc_140188097
0x14018808e  lea     rcx, [r8+28h]
0x140188092  cmp     rcx, rsi
0x140188095  jbe     short loc_1401880AA
0x140188097  test    r13b, r13b
0x14018809a  jnz     short loc_1401880C8
0x14018809c  add     r14d, edi
0x14018809f  cmp     r14d, r12d
0x1401880a2  jb      loc_14018801C
0x1401880a8  jmp     short loc_1401880C8
0x1401880aa  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401880b0  jbe     short loc_1401880B9
0x1401880b2  lea     r10, [rdx+18h]
0x1401880b6  add     r10, r8
0x1401880b9  mov     r9, [r8+rdx+10h]
0x1401880be  mov     r11b, [r8+rdx+9]
0x1401880c3  mov     r15b, [r8+rdx+8]
0x1401880c8  test    r10, r10
0x1401880cb  jz      loc_140188867
0x1401880d1  mov     cl, [r10]
0x1401880d4  jmp     short loc_1401880ED
0x1401880d6  mov     cl, [rdx+48h]
0x1401880d9  mov     r9, [rdx+20h]
0x1401880dd  mov     r11b, [rdx+0Bh]
0x1401880e1  mov     r15b, [rdx+4]
0x1401880e5  test    eax, eax
0x1401880e7  jnz     loc_140188867
0x1401880ed  sub     cl, 8
0x1401880f0  test    cl, 5Dh
0x1401880f3  jnz     loc_140188867
0x1401880f9  mov     sil, [rdx+3]
0x1401880fd  cmp     sil, dil
0x140188100  jz      loc_140188193
0x140188106  test    r9, r9
0x140188109  jz      loc_140188193
0x14018810f  test    r11b, r11b
0x140188112  jz      short loc_140188193
0x140188114  mov     al, [r9]
0x140188117  xor     dl, dl
0x140188119  and     al, 7Fh
0x14018811b  movzx   ecx, r11b
0x14018811f  sub     al, 72h ; 'r'
0x140188121  xor     r10b, r10b
0x140188124  xor     r8b, r8b
0x140188127  add     rcx, r9
0x14018812a  cmp     al, dil
0x14018812d  lea     rax, [r9+8]
0x140188131  jbe     short loc_140188175
0x140188133  cmp     rax, rcx
0x140188136  ja      short loc_14018818B
0x140188138  movzx   ecx, byte ptr [r9+7]
0x14018813d  lea     r8, [r9+0Dh]
0x140188141  mov     dl, [r9+2]
0x140188145  add     ecx, 8
0x140188148  and     dl, 0Fh
0x14018814b  movzx   eax, r11b
0x14018814f  cmp     ecx, eax
0x140188151  cmovbe  eax, ecx
0x140188154  mov     ecx, eax
0x140188156  add     rcx, r9
0x140188159  cmp     r8, rcx
0x14018815c  ja      short loc_140188162
0x14018815e  mov     r10b, [r9+0Ch]
0x140188162  lea     rax, [r9+0Eh]
0x140188166  cmp     rax, rcx
0x140188169  ja      short loc_140188170
0x14018816b  mov     r8b, [r8]
0x14018816e  jmp     short loc_14018818E
0x140188170  xor     r8b, r8b
0x140188173  jmp     short loc_14018818E
0x140188175  cmp     rax, rcx
0x140188178  ja      short loc_14018818B
0x14018817a  mov     dl, [r9+1]
0x14018817e  mov     r10b, [r9+2]
0x140188182  and     dl, 0Fh
0x140188185  mov     r8b, [r9+3]
0x140188189  jmp     short loc_14018818E
0x14018818b  xor     dil, dil
0x14018818e  test    dil, dil
0x140188191  jnz     short loc_14018819B
0x140188193  xor     dl, dl
0x140188195  xor     r10b, r10b
0x140188198  xor     r8b, r8b
0x14018819b  mov     eax, [rbx+30h]
0x14018819e  mov     r9, rbx
0x1401881a1  mov     [rsp+80h+var_30], rbx
0x1401881a6  mov     [rsp+80h+var_38], r8b
0x1401881ab  lea     r8, [rbp+var_18]
0x1401881af  mov     [rsp+80h+var_40], r10b
0x1401881b4  mov     [rsp+80h+var_48], dl
0x1401881b8  mov     [rsp+80h+var_50], r15b
0x1401881bd  mov     byte ptr [rsp+80h+var_58], sil
0x1401881c2  mov     [rsp+80h+var_60], eax
0x1401881c6  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x1401881cb  jmp     loc_140188867
0x1401881d0  test    cs:byte_140177432, 8
0x1401881d7  jz      loc_140188867
0x1401881dd  mov     eax, [rbx+30h]
0x1401881e0  mov     [rsp+80h+var_60], eax
0x1401881e4  jmp     loc_140188854
0x1401881e9  mov     ecx, [rcx]
0x1401881eb  cmp     ecx, 30h ; '0'
0x1401881ee  jg      loc_1401882A9
0x1401881f4  jz      loc_14018829C
0x1401881fa  test    ecx, ecx
0x1401881fc  jz      loc_14018828F
0x140188202  sub     ecx, edi
0x140188204  jz      short loc_14018827F
0x140188206  sub     ecx, edi
0x140188208  jz      short loc_14018826F
0x14018820a  sub     ecx, 2
0x14018820d  jz      short loc_14018825F
0x14018820f  sub     ecx, 2
0x140188212  jz      short loc_14018824F
0x140188214  sub     ecx, edi
0x140188216  jz      short loc_140188242
0x140188218  sub     ecx, edi
0x14018821a  jz      short loc_140188232
0x14018821c  cmp     ecx, 4
0x14018821f  jnz     loc_1401882E5
0x140188225  mov     rdx, rbx
0x140188228  call    NvmeNamespaceStorageQueryDevicePowerPropertyIoctl
0x14018822d  jmp     loc_14018830F
0x140188232  mov     rdx, rbx
0x140188235  mov     rcx, r9
0x140188238  call    NvmeNamespaceStorageQueryDeviceTrimPropertyIoctl
0x14018823d  jmp     loc_14018830F
0x140188242  mov     rdx, rbx
0x140188245  call    NvmeNamespaceStorageQueryDeviceSeekPenaltyPropertyIoctl
0x14018824a  jmp     loc_14018830F
0x14018824f  mov     rdx, rbx
0x140188252  mov     rcx, r9
0x140188255  call    NvmeNamespaceStorageQueryAccessAlignmentPropertyIoctl
0x14018825a  jmp     loc_14018830F
0x14018825f  mov     rdx, rbx
0x140188262  mov     rcx, r9
0x140188265  call    NvmeNamespaceStorageQueryDeviceWriteCachePropertyIoctl
0x14018826a  jmp     loc_14018830F
0x14018826f  mov     rdx, rbx
0x140188272  mov     rcx, r9
0x140188275  call    NvmeNamespaceStorageQueryDeviceIdPropertyIoctl
0x14018827a  jmp     loc_14018830F
0x14018827f  mov     rdx, rbx
0x140188282  mov     rcx, r9
0x140188285  call    NvmeNamespaceStorageQueryAdapterPropertyIoctl
0x14018828a  jmp     loc_14018830F
0x14018828f  mov     rdx, rbx
0x140188292  mov     rcx, r9
0x140188295  call    NvmeNamespaceStorageQueryDevicePropertyIoctl
0x14018829a  jmp     short loc_14018830F
0x14018829c  mov     rdx, rbx
0x14018829f  mov     rcx, r9
0x1401882a2  call    NvmeNamespaceStorageQueryDeviceIoCapabilityPropertyIoctl
0x1401882a7  jmp     short loc_14018830F
0x1401882a9  sub     ecx, 31h ; '1'
0x1401882ac  jz      loc_1401889EF
0x1401882b2  sub     ecx, edi
0x1401882b4  jz      loc_140188715
0x1401882ba  sub     ecx, 9
0x1401882bd  jz      loc_1401885D6
0x1401882c3  sub     ecx, 3
0x1401882c6  jz      loc_140188497
0x1401882cc  sub     ecx, edi
0x1401882ce  jz      short loc_140188325
0x1401882d0  sub     ecx, 3
0x1401882d3  jz      short loc_140188318
0x1401882d5  sub     ecx, edi
0x1401882d7  jz      loc_1401889EF
0x1401882dd  cmp     ecx, edi
0x1401882df  jz      loc_140188715
0x1401882e5  add     [rbx+43h], dil
0x1401882e9  mov     rdx, rbx; Irp
0x1401882ec  add     qword ptr [rbx+0B8h], 48h ; 'H'
  ... truncated ...
```
