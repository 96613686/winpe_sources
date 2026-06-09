# NvmeAdapterDeviceControlIrpFromNamespace

- ea: `0x14005df48`
- end: `0x14005ed63`
- name: `NvmeAdapterDeviceControlIrpFromNamespace`
- size: `3611`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1401b35f8`

## callees

- `0x140025144`
- `0x14004ac54`
- `0x14005df48`
- `0x14006d1c0`
- `0x14006d298`
- `0x14008479c`
- `0x1400848c4`
- `0x1400f8ed0`
- `0x1400f94ac`
- `0x1400f9ad8`
- `0x1400fd160`
- `0x1400fd580`
- `0x1400ff9c4`
- `0x14014b400`
- `0x14018761c`
- `0x14019eb48`
- `0x14019f1dc`
- `0x14019f908`
- `0x1401a9840`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14005dfb4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005e02d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005e3e7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005e6c5`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005ea00`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005dfb4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005e02d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005e3e7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005e6c5`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005ea00`
- `ntoskrnl!IofCompleteRequest` at `0x14005e2d5`
- `ntoskrnl!IofCompleteRequest` at `0x14005e68f`
- `ntoskrnl!IofCompleteRequest` at `0x14005e972`
- `ntoskrnl!IofCompleteRequest` at `0x14005ecad`
- `ntoskrnl!IofCompleteRequest` at `0x14005e2d5`
- `ntoskrnl!IofCompleteRequest` at `0x14005e68f`
- `ntoskrnl!IofCompleteRequest` at `0x14005e972`
- `ntoskrnl!IofCompleteRequest` at `0x14005ecad`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14005ed2d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14005ed2d`

## pseudocode

```c
__int64 __fastcall NvmeAdapterDeviceControlIrpFromNamespace(__int64 a1, __int64 a2, __int64 a3)
{
  char v3; // si
  int v7; // r15d
  __int64 v8; // rcx
  unsigned int v9; // edi
  bool v10; // zf
  unsigned __int64 v11; // rcx
  __int64 v12; // rdx
  int *v13; // rax
  int v14; // ecx
  __int64 *v15; // rdx
  __int64 v16; // rdx
  unsigned int v17; // r12d
  unsigned __int8 v18; // r10
  char *v19; // r11
  char v20; // r14
  _BYTE *v21; // r9
  __int64 v22; // r15
  char v23; // r13
  unsigned __int64 v24; // rdi
  __int64 v25; // r8
  int v26; // ecx
  char v27; // cl
  char v28; // di
  char v29; // r11
  char v30; // r8
  _BYTE *v31; // rax
  char *v32; // r8
  unsigned int v33; // eax
  unsigned int v35; // edi
  unsigned int v36; // edi
  unsigned int v37; // edi
  unsigned int v38; // edi
  unsigned int v39; // edi
  unsigned int v40; // edi
  unsigned int InfoIoctl; // eax
  unsigned int PropertyIoctl; // eax
  unsigned int v43; // edi
  int v44; // ecx
  unsigned __int64 v45; // rcx
  __int64 v46; // rdx
  int *v47; // rax
  int v48; // ecx
  __int64 *v49; // rdx
  __int64 v50; // rdx
  unsigned int v51; // r12d
  unsigned __int8 v52; // r10
  char *v53; // r11
  char v54; // r15
  _BYTE *v55; // r9
  __int64 v56; // r14
  char v57; // r13
  unsigned __int64 v58; // rdi
  __int64 v59; // r8
  int v60; // ecx
  char v61; // cl
  char v62; // di
  char v63; // r11
  char v64; // r8
  _BYTE *v65; // rax
  char *v66; // r8
  unsigned int v67; // eax
  unsigned __int64 v68; // rcx
  __int64 v69; // rdx
  int *v70; // rax
  int v71; // ecx
  __int64 *v72; // rdx
  __int64 v73; // rdx
  unsigned int v74; // r12d
  _BYTE *v75; // r9
  unsigned __int8 v76; // r10
  char *v77; // r11
  char v78; // r13
  __int64 v79; // r15
  unsigned __int64 v80; // r14
  __int64 v81; // r8
  int v82; // ecx
  char v83; // cl
  char v84; // r14
  char v85; // r11
  char v86; // r8
  _BYTE *v87; // rax
  char *v88; // r8
  unsigned int v89; // eax
  unsigned int v90; // edi
  unsigned int v91; // edi
  unsigned int v92; // edi
  unsigned int v93; // edi
  unsigned int v94; // edi
  unsigned __int64 v95; // rcx
  __int64 v96; // rdx
  int *v97; // rax
  int v98; // ecx
  __int64 *v99; // rdx
  __int64 v100; // rdx
  unsigned int v101; // r12d
  _BYTE *v102; // r9
  unsigned __int8 v103; // r11
  char *v104; // r10
  char v105; // r13
  __int64 v106; // r15
  unsigned __int64 v107; // r14
  __int64 v108; // r8
  int v109; // ecx
  char v110; // cl
  char v111; // r14
  char v112; // r10
  char v113; // r8
  _BYTE *v114; // rax
  char *v115; // r8
  unsigned int v116; // eax
  char v117; // [rsp+60h] [rbp-19h] BYREF
  char v118; // [rsp+61h] [rbp-18h]
  unsigned int v119; // [rsp+64h] [rbp-15h]
  __int128 v120; // [rsp+68h] [rbp-11h] BYREF
  __int128 v121; // [rsp+78h] [rbp-1h] BYREF
  __int128 v122; // [rsp+88h] [rbp+Fh] BYREF

  *(_QWORD *)&v121 = a1;
  v3 = 1;
  v122 = 0;
  v117 = 1;
  v7 = NvmeAdapterAcquireRemoveLock();
  v8 = *(_QWORD *)(a3 + 184);
  v119 = v7;
  v9 = *(_DWORD *)(v8 + 24);
  if ( StorEtwLoggingEnabled )
  {
    IoGetActivityIdIrp(a3, &v122);
    if ( (byte_140177432 & 2) != 0 )
      McTemplateK0pddd_EtwWriteTransfer(
        *(unsigned __int8 *)(*(_QWORD *)(a3 + 184) + 1LL),
        (unsigned int)EventIOCTL,
        (unsigned int)&v122,
        a3,
        **(_BYTE **)(a3 + 184),
        *(_BYTE *)(*(_QWORD *)(a3 + 184) + 1LL),
        v9);
  }
  if ( v7 >= 0 )
  {
    if ( v9 > 0x2DD3C0 )
    {
      v90 = v9 - 3005444;
      if ( !v90 )
      {
        InfoIoctl = NvmeAdapterFirmwareDownloadIoctl(a1, a2, a3, &v117);
        goto LABEL_294;
      }
      v91 = v90 - 4;
      if ( !v91 )
      {
        InfoIoctl = NvmeAdapterFirmwareActivateIoctl(a1, a2, a3, 0, &v117);
        goto LABEL_294;
      }
      v92 = v91 - 4;
      if ( v92 )
      {
        v93 = v92 - 4;
        if ( v93 )
        {
          v94 = v93 - 320496;
          if ( v94 && v94 != 56 )
            goto LABEL_224;
          PropertyIoctl = RaForwardIrp(*(_QWORD *)(a1 + 24), a3);
        }
        else
        {
          PropertyIoctl = NvmeAdapterBootPartitionActivateIoctl(a1, a3);
        }
      }
      else
      {
        PropertyIoctl = NvmeAdapterBootPartitionDownloadIoctl(a1, a3);
      }
      goto LABEL_81;
    }
    if ( v9 == 3003328 )
    {
      InfoIoctl = NvmeAdapterStorageProtocolCommandIoctl(a1, a2, a3, &v117);
      goto LABEL_294;
    }
    v35 = v9 - 266268;
    if ( v35 )
    {
      v36 = v35 - 2687964;
      if ( v36 )
      {
        v37 = v36 - 8;
        if ( !v37 )
        {
          InfoIoctl = NvmeAdapterStorageQueryProperty(a1, a3, &v117);
          goto LABEL_294;
        }
        v38 = v37 - 2048;
        if ( !v38 )
        {
          InfoIoctl = NvmeAdapterFirmwareGetInfoIoctl(a1, a2, a3, &v117);
          goto LABEL_294;
        }
        v39 = v38 - 20;
        if ( v39 )
        {
          v40 = v39 - 184;
          if ( v40 )
          {
            if ( v40 == 46388 )
            {
              InfoIoctl = NvmeAdapterSetTemperatureThresholdIoctl(a1, a3, &v117);
LABEL_294:
              v43 = InfoIoctl;
LABEL_295:
              if ( !v117 )
                return v43;
LABEL_296:
              ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v121 + 160));
              return v43;
            }
LABEL_224:
            v10 = StorEtwLoggingEnabled == 0;
            v43 = -1073741637;
            *(_DWORD *)(a3 + 48) = -1073741637;
            *(_BYTE *)(a3 + 141) = -84;
            if ( v10 )
              goto LABEL_288;
            v120 = 0;
            IoGetActivityIdIrp(a3, &v120);
            v96 = *(_QWORD *)(a3 + 184);
            if ( *(_BYTE *)v96 == 14 )
            {
              if ( (byte_140177432 & 8) == 0 )
                goto LABEL_288;
              v99 = EventNonReadWriteRequestComplete;
              goto LABEL_287;
            }
            if ( *(_BYTE *)v96 != 15 )
            {
              if ( *(_BYTE *)v96 != 27 )
                goto LABEL_288;
              if ( *(_BYTE *)(v96 + 1) == 7 && !*(_DWORD *)(v96 + 8) )
              {
                if ( (byte_140177432 & 0x40) != 0 )
                {
                  v97 = *(int **)(a3 + 56);
                  if ( v97 )
                    v98 = *v97;
                  else
                    v98 = 0;
                  McTemplateK0pqd_EtwWriteTransfer(v98, v96, (unsigned int)&v120, a3, v98, *(_DWORD *)(a3 + 48));
                }
                goto LABEL_288;
              }
              if ( (byte_140177432 & 0x20) == 0 )
                goto LABEL_288;
              v99 = EventPnpRequestComplete;
LABEL_287:
              McTemplateK0pd_EtwWriteTransfer(v95, v99, &v120, a3, *(_DWORD *)(a3 + 48));
              goto LABEL_288;
            }
            if ( byte_140177431 >= 0 )
              goto LABEL_288;
            v100 = *(_QWORD *)(v96 + 8);
            if ( *(_BYTE *)(v100 + 2) == 40 )
            {
              if ( *(_DWORD *)(v100 + 20) )
                goto LABEL_288;
              v101 = *(_DWORD *)(v100 + 56);
              if ( !v101 )
                goto LABEL_288;
              v102 = 0;
              v103 = 0;
              v104 = 0;
              v118 = 0;
              v105 = 0;
              v106 = 0;
              while ( 1 )
              {
                v95 = *(unsigned int *)(v100 + 4 * v106 + 120);
                if ( (unsigned int)v95 >= 0x80 )
                {
                  v107 = *(unsigned int *)(v100 + 16);
                  if ( (unsigned int)v95 < (unsigned int)v107 )
                  {
                    v108 = (unsigned int)v95;
                    v109 = *(_DWORD *)(v95 + v100) - 64;
                    if ( v109 )
                    {
                      LODWORD(v95) = v109 - 1;
                      if ( (_DWORD)v95 )
                      {
                        if ( (_DWORD)v95 == 1 )
                        {
                          LODWORD(v95) = v108 + 40;
                          if ( v108 + 40 <= v107 )
                          {
                            if ( *(_DWORD *)(v108 + v100 + 12) )
                              v104 = (char *)(v108 + v100 + 32);
                            v102 = *(_BYTE **)(v108 + v100 + 24);
                            goto LABEL_262;
                          }
                        }
                      }
                      else
                      {
                        LODWORD(v95) = v108 + 56;
                        if ( v108 + 56 <= v107 )
                        {
                          v10 = *(_BYTE *)(v108 + v100 + 10) == 0;
                          v118 = 1;
                          if ( !v10 )
                            v104 = (char *)(v108 + v100 + 24);
                          v105 = *(_BYTE *)(v108 + v100 + 8);
                          v102 = *(_BYTE **)(v108 + v100 + 16);
                          v103 = *(_BYTE *)(v108 + v100 + 9);
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v95) = v108 + 40;
                      if ( v108 + 40 <= v107 )
                      {
                        if ( *(_BYTE *)(v108 + v100 + 10) )
                          v104 = (char *)(v108 + v100 + 24);
                        v102 = *(_BYTE **)(v108 + v100 + 16);
LABEL_262:
                        v103 = *(_BYTE *)(v108 + v100 + 9);
                        v105 = *(_BYTE *)(v108 + v100 + 8);
LABEL_263:
                        if ( v104 )
                        {
                          v110 = *v104;
                          goto LABEL_266;
                        }
                        goto LABEL_288;
                      }
                    }
                    if ( v118 )
                      goto LABEL_263;
                  }
                }
                v106 = (unsigned int)(v106 + 1);
                if ( (unsigned int)v106 >= v101 )
                  goto LABEL_263;
              }
            }
            v110 = *(_BYTE *)(v100 + 72);
            v102 = *(_BYTE **)(v100 + 32);
            v103 = *(_BYTE *)(v100 + 11);
            v105 = *(_BYTE *)(v100 + 4);
            if ( *(_BYTE *)(v100 + 2) )
              goto LABEL_288;
LABEL_266:
            LOBYTE(v95) = v110 - 8;
            if ( (v95 & 0x5D) != 0 )
            {
LABEL_288:
              IofCompleteRequest((PIRP)a3, 0);
              goto LABEL_296;
            }
            v111 = *(_BYTE *)(v100 + 3);
            if ( v111 == 1 || !v102 || !v103 )
              goto LABEL_283;
            LOBYTE(v100) = 0;
            v112 = 0;
            v113 = 0;
            v95 = (unsigned __int64)&v102[v103];
            v114 = v102 + 8;
            if ( (unsigned __int8)((*v102 & 0x7F) - 114) <= 1u )
            {
              if ( (unsigned __int64)v114 <= v95 )
              {
                v112 = v102[2];
                LOBYTE(v100) = v102[1] & 0xF;
                v113 = v102[3];
                goto LABEL_282;
              }
            }
            else if ( (unsigned __int64)v114 <= v95 )
            {
              v115 = v102 + 13;
              LOBYTE(v100) = v102[2] & 0xF;
              v116 = v103;
              if ( (unsigned int)(unsigned __int8)v102[7] + 8 <= v103 )
                v116 = (unsigned __int8)v102[7] + 8;
              v95 = (unsigned __int64)&v102[v116];
              if ( (unsigned __int64)v115 <= v95 )
                v112 = v102[12];
              if ( (unsigned __int64)(v102 + 14) > v95 )
                v113 = 0;
              else
                v113 = *v115;
LABEL_282:
              if ( v3 )
              {
LABEL_284:
                McTemplateK0pduuuuup_EtwWriteTransfer(
                  v95,
                  v100,
                  (unsigned int)&v120,
                  a3,
                  *(_DWORD *)(a3 + 48),
                  v111,
                  v105,
                  v100,
                  v112,
                  v113,
                  a3);
                goto LABEL_288;
              }
LABEL_283:
              LOBYTE(v100) = 0;
              v112 = 0;
              v113 = 0;
              goto LABEL_284;
            }
            v3 = 0;
            goto LABEL_282;
          }
          PropertyIoctl = NvmeAdapterSetLedState(a1, a3);
        }
        else
        {
          PropertyIoctl = NvmeAdapterBootPartitionGetInfoIoctl(a1, a3);
        }
      }
      else
      {
        PropertyIoctl = NvmeAdapterStorageInternalQueryPropertyIoctl(a1, a3);
      }
LABEL_81:
      v43 = PropertyIoctl;
      goto LABEL_296;
    }
    v44 = *(_DWORD *)(*(_QWORD *)(a1 + 408) + 184LL) >> 30;
    *(_BYTE *)(a3 + 141) = -84;
    if ( (v44 & 1) != 0 )
    {
      v10 = StorEtwLoggingEnabled == 0;
      *(_DWORD *)(a3 + 48) = 0;
      if ( v10 )
        goto LABEL_151;
      v120 = 0;
      IoGetActivityIdIrp(a3, &v120);
      v46 = *(_QWORD *)(a3 + 184);
      if ( *(_BYTE *)v46 == 14 )
      {
        if ( (byte_140177432 & 8) == 0 )
          goto LABEL_151;
        v49 = EventNonReadWriteRequestComplete;
        goto LABEL_150;
      }
      if ( *(_BYTE *)v46 != 15 )
      {
        if ( *(_BYTE *)v46 != 27 )
          goto LABEL_151;
        if ( *(_BYTE *)(v46 + 1) == 7 && !*(_DWORD *)(v46 + 8) )
        {
          if ( (byte_140177432 & 0x40) != 0 )
          {
            v47 = *(int **)(a3 + 56);
            if ( v47 )
              v48 = *v47;
            else
              v48 = 0;
            McTemplateK0pqd_EtwWriteTransfer(v48, v46, (unsigned int)&v120, a3, v48, *(_DWORD *)(a3 + 48));
          }
          goto LABEL_151;
        }
        if ( (byte_140177432 & 0x20) == 0 )
          goto LABEL_151;
        v49 = EventPnpRequestComplete;
LABEL_150:
        McTemplateK0pd_EtwWriteTransfer(v45, v49, &v120, a3, *(_DWORD *)(a3 + 48));
        goto LABEL_151;
      }
      if ( byte_140177431 >= 0 )
        goto LABEL_151;
      v50 = *(_QWORD *)(v46 + 8);
      if ( *(_BYTE *)(v50 + 2) == 40 )
      {
        if ( *(_DWORD *)(v50 + 20) )
          goto LABEL_151;
        v51 = *(_DWORD *)(v50 + 56);
        if ( !v51 )
          goto LABEL_151;
        v52 = 0;
        v53 = 0;
        v54 = 0;
        v55 = 0;
        v56 = 0;
        v57 = 0;
        while ( 1 )
        {
          v45 = *(unsigned int *)(v50 + 4 * v56 + 120);
          if ( (unsigned int)v45 >= 0x80 )
          {
            v58 = *(unsigned int *)(v50 + 16);
            if ( (unsigned int)v45 < (unsigned int)v58 )
            {
              v59 = (unsigned int)v45;
              v60 = *(_DWORD *)(v45 + v50) - 64;
              if ( v60 )
              {
                LODWORD(v45) = v60 - 1;
                if ( (_DWORD)v45 )
                {
                  if ( (_DWORD)v45 == 1 )
                  {
                    LODWORD(v45) = v59 + 40;
                    if ( v59 + 40 <= v58 )
                    {
                      if ( *(_DWORD *)(v59 + v50 + 12) )
                        v53 = (char *)(v59 + v50 + 32);
                      v55 = *(_BYTE **)(v59 + v50 + 24);
                      goto LABEL_125;
                    }
                  }
                }
                else
                {
                  LODWORD(v45) = v59 + 56;
                  if ( v59 + 56 <= v58 )
                  {
                    v57 = 1;
                    if ( *(_BYTE *)(v59 + v50 + 10) )
                      v53 = (char *)(v59 + v50 + 24);
                    v54 = *(_BYTE *)(v59 + v50 + 8);
                    v55 = *(_BYTE **)(v59 + v50 + 16);
                    v52 = *(_BYTE *)(v59 + v50 + 9);
                  }
                }
              }
              else
              {
                LODWORD(v45) = v59 + 40;
                if ( v59 + 40 <= v58 )
                {
                  if ( *(_BYTE *)(v59 + v50 + 10) )
                    v53 = (char *)(v59 + v50 + 24);
                  v55 = *(_BYTE **)(v59 + v50 + 16);
LABEL_125:
                  v52 = *(_BYTE *)(v59 + v50 + 9);
                  v54 = *(_BYTE *)(v59 + v50 + 8);
LABEL_126:
                  if ( v53 )
                  {
                    v61 = *v53;
                    goto LABEL_129;
                  }
                  goto LABEL_151;
                }
              }
              if ( v57 )
                goto LABEL_126;
            }
          }
          v56 = (unsigned int)(v56 + 1);
          if ( (unsigned int)v56 >= v51 )
            goto LABEL_126;
        }
      }
      v61 = *(_BYTE *)(v50 + 72);
      v55 = *(_BYTE **)(v50 + 32);
      v52 = *(_BYTE *)(v50 + 11);
      v54 = *(_BYTE *)(v50 + 4);
      if ( *(_BYTE *)(v50 + 2) )
        goto LABEL_151;
LABEL_129:
      LOBYTE(v45) = v61 - 8;
      if ( (v45 & 0x5D) != 0 )
      {
LABEL_151:
        IofCompleteRequest((PIRP)a3, 0);
        v43 = 0;
        goto LABEL_295;
      }
      v62 = *(_BYTE *)(v50 + 3);
      if ( v62 == 1 || !v55 || !v52 )
        goto LABEL_146;
      LOBYTE(v50) = 0;
      v63 = 0;
      v64 = 0;
      v45 = (unsigned __int64)&v55[v52];
      v65 = v55 + 8;
      if ( (unsigned __int8)((*v55 & 0x7F) - 114) <= 1u )
      {
        if ( (unsigned __int64)v65 <= v45 )
        {
          v63 = v55[2];
          LOBYTE(v50) = v55[1] & 0xF;
          v64 = v55[3];
          goto LABEL_145;
        }
      }
      else if ( (unsigned __int64)v65 <= v45 )
      {
        v66 = v55 + 13;
        LOBYTE(v50) = v55[2] & 0xF;
        v67 = v52;
        if ( (unsigned int)(unsigned __int8)v55[7] + 8 <= v52 )
          v67 = (unsigned __int8)v55[7] + 8;
        v45 = (unsigned __int64)&v55[v67];
        if ( (unsigned __int64)v66 <= v45 )
          v63 = v55[12];
        if ( (unsigned __int64)(v55 + 14) > v45 )
          v64 = 0;
        else
          v64 = *v66;
LABEL_145:
        if ( v3 )
        {
LABEL_147:
          McTemplateK0pduuuuup_EtwWriteTransfer(
            v45,
            v50,
            (unsigned int)&v120,
            a3,
            *(_DWORD *)(a3 + 48),
            v62,
            v54,
            v50,
            v63,
            v64,
            a3);
          goto LABEL_151;
        }
LABEL_146:
        LOBYTE(v50) = 0;
        v63 = 0;
        v64 = 0;
        goto LABEL_147;
      }
      v3 = 0;
      goto LABEL_145;
    }
    v10 = StorEtwLoggingEnabled == 0;
    v43 = -1073741637;
    *(_DWORD *)(a3 + 48) = -1073741637;
    if ( v10 )
      goto LABEL_216;
    v120 = 0;
    IoGetActivityIdIrp(a3, &v120);
    v69 = *(_QWORD *)(a3 + 184);
    if ( *(_BYTE *)v69 == 14 )
    {
      if ( (byte_140177432 & 8) == 0 )
        goto LABEL_216;
      v72 = EventNonReadWriteRequestComplete;
      goto LABEL_215;
    }
    if ( *(_BYTE *)v69 != 15 )
    {
      if ( *(_BYTE *)v69 != 27 )
        goto LABEL_216;
      if ( *(_BYTE *)(v69 + 1) == 7 && !*(_DWORD *)(v69 + 8) )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          v70 = *(int **)(a3 + 56);
          if ( v70 )
            v71 = *v70;
          else
            v71 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v71, v69, (unsigned int)&v120, a3, v71, *(_DWORD *)(a3 + 48));
        }
        goto LABEL_216;
      }
      if ( (byte_140177432 & 0x20) == 0 )
        goto LABEL_216;
      v72 = EventPnpRequestComplete;
LABEL_215:
      McTemplateK0pd_EtwWriteTransfer(v68, v72, &v120, a3, *(_DWORD *)(a3 + 48));
      goto LABEL_216;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_216;
    v73 = *(_QWORD *)(v69 + 8);
    if ( *(_BYTE *)(v73 + 2) == 40 )
    {
      if ( *(_DWORD *)(v73 + 20) )
        goto LABEL_216;
      v74 = *(_DWORD *)(v73 + 56);
      if ( !v74 )
        goto LABEL_216;
      v75 = 0;
      v76 = 0;
      v77 = 0;
      v118 = 0;
      v78 = 0;
      v79 = 0;
      while ( 1 )
      {
        v68 = *(unsigned int *)(v73 + 4 * v79 + 120);
        if ( (unsigned int)v68 >= 0x80 )
        {
          v80 = *(unsigned int *)(v73 + 16);
          if ( (unsigned int)v68 < (unsigned int)v80 )
          {
            v81 = (unsigned int)v68;
            v82 = *(_DWORD *)(v68 + v73) - 64;
            if ( v82 )
            {
              LODWORD(v68) = v82 - 1;
              if ( (_DWORD)v68 )
              {
                if ( (_DWORD)v68 == 1 )
                {
                  LODWORD(v68) = v81 + 40;
                  if ( v81 + 40 <= v80 )
                  {
                    if ( *(_DWORD *)(v81 + v73 + 12) )
                      v77 = (char *)(v81 + v73 + 32);
                    v75 = *(_BYTE **)(v81 + v73 + 24);
                    goto LABEL_190;
                  }
                }
              }
              else
              {
                LODWORD(v68) = v81 + 56;
                if ( v81 + 56 <= v80 )
                {
                  v10 = *(_BYTE *)(v81 + v73 + 10) == 0;
                  v118 = 1;
                  if ( !v10 )
                    v77 = (char *)(v81 + v73 + 24);
                  v78 = *(_BYTE *)(v81 + v73 + 8);
                  v75 = *(_BYTE **)(v81 + v73 + 16);
                  v76 = *(_BYTE *)(v81 + v73 + 9);
                }
              }
            }
            else
            {
              LODWORD(v68) = v81 + 40;
              if ( v81 + 40 <= v80 )
              {
                if ( *(_BYTE *)(v81 + v73 + 10) )
                  v77 = (char *)(v81 + v73 + 24);
                v75 = *(_BYTE **)(v81 + v73 + 16);
LABEL_190:
                v76 = *(_BYTE *)(v81 + v73 + 9);
                v78 = *(_BYTE *)(v81 + v73 + 8);
LABEL_191:
                if ( v77 )
                {
                  v83 = *v77;
                  goto LABEL_194;
                }
                goto LABEL_216;
              }
            }
            if ( v118 )
              goto LABEL_191;
          }
        }
        v79 = (unsigned int)(v79 + 1);
        if ( (unsigned int)v79 >= v74 )
          goto LABEL_191;
      }
    }
    v83 = *(_BYTE *)(v73 + 72);
    v75 = *(_BYTE **)(v73 + 32);
    v76 = *(_BYTE *)(v73 + 11);
    v78 = *(_BYTE *)(v73 + 4);
    if ( *(_BYTE *)(v73 + 2) )
      goto LABEL_216;
LABEL_194:
    LOBYTE(v68) = v83 - 8;
    if ( (v68 & 0x5D) != 0 )
    {
LABEL_216:
      IofCompleteRequest((PIRP)a3, 0);
      goto LABEL_295;
    }
    v84 = *(_BYTE *)(v73 + 3);
    if ( v84 == 1 || !v75 || !v76 )
      goto LABEL_211;
    LOBYTE(v73) = 0;
    v85 = 0;
    v86 = 0;
    v68 = (unsigned __int64)&v75[v76];
    v87 = v75 + 8;
    if ( (unsigned __int8)((*v75 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v87 <= v68 )
      {
        v85 = v75[2];
        LOBYTE(v73) = v75[1] & 0xF;
        v86 = v75[3];
        goto LABEL_210;
      }
    }
    else if ( (unsigned __int64)v87 <= v68 )
    {
      v88 = v75 + 13;
      LOBYTE(v73) = v75[2] & 0xF;
      v89 = v76;
      if ( (unsigned int)(unsigned __int8)v75[7] + 8 <= v76 )
        v89 = (unsigned __int8)v75[7] + 8;
      v68 = (unsigned __int64)&v75[v89];
      if ( (unsigned __int64)v88 <= v68 )
        v85 = v75[12];
      if ( (unsigned __int64)(v75 + 14) > v68 )
        v86 = 0;
      else
        v86 = *v88;
LABEL_210:
      if ( v3 )
      {
LABEL_212:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v68,
          v73,
          (unsigned int)&v120,
          a3,
          *(_DWORD *)(a3 + 48),
          v84,
          v78,
          v73,
          v85,
          v86,
          a3);
        goto LABEL_216;
      }
LABEL_211:
      LOBYTE(v73) = 0;
      v85 = 0;
      v86 = 0;
      goto LABEL_212;
    }
    v3 = 0;
    goto LABEL_210;
  }
  v10 = StorEtwLoggingEnabled == 0;
  *(_QWORD *)(a3 + 56) = 0;
  *(_BYTE *)(a3 + 141) = -84;
  *(_DWORD *)(a3 + 48) = v7;
  if ( v10 )
    goto LABEL_69;
  v121 = 0;
  IoGetActivityIdIrp(a3, &v121);
  v12 = *(_QWORD *)(a3 + 184);
  if ( *(_BYTE *)v12 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_69;
    v15 = EventNonReadWriteRequestComplete;
    goto LABEL_68;
  }
  if ( *(_BYTE *)v12 != 15 )
  {
    if ( *(_BYTE *)v12 != 27 )
      goto LABEL_69;
    if ( *(_BYTE *)(v12 + 1) == 7 && !*(_DWORD *)(v12 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v13 = *(int **)(a3 + 56);
        if ( v13 )
          v14 = *v13;
        else
          v14 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v14, v12, (unsigned int)&v121, a3, v14, *(_DWORD *)(a3 + 48));
      }
      goto LABEL_69;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_69;
    v15 = EventPnpRequestComplete;
LABEL_68:
    McTemplateK0pd_EtwWriteTransfer(v11, v15, &v121, a3, *(_DWORD *)(a3 + 48));
    goto LABEL_69;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_69;
  v16 = *(_QWORD *)(v12 + 8);
  if ( *(_BYTE *)(v16 + 2) == 40 )
  {
    if ( *(_DWORD *)(v16 + 20) )
      goto LABEL_69;
    v17 = *(_DWORD *)(v16 + 56);
    if ( !v17 )
      goto LABEL_69;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    while ( 1 )
    {
      v11 = *(unsigned int *)(v16 + 4 * v22 + 120);
      if ( (unsigned int)v11 >= 0x80 )
      {
        v24 = *(unsigned int *)(v16 + 16);
        if ( (unsigned int)v11 < (unsigned int)v24 )
        {
          v25 = (unsigned int)v11;
          v26 = *(_DWORD *)(v11 + v16) - 64;
          if ( v26 )
          {
            LODWORD(v11) = v26 - 1;
            if ( (_DWORD)v11 )
            {
              if ( (_DWORD)v11 == 1 )
              {
                LODWORD(v11) = v25 + 40;
                if ( v25 + 40 <= v24 )
                {
                  if ( *(_DWORD *)(v25 + v16 + 12) )
                    v19 = (char *)(v25 + v16 + 32);
                  v21 = *(_BYTE **)(v25 + v16 + 24);
                  goto LABEL_43;
                }
              }
            }
            else
            {
              LODWORD(v11) = v25 + 56;
              if ( v25 + 56 <= v24 )
              {
                v23 = 1;
                if ( *(_BYTE *)(v25 + v16 + 10) )
                  v19 = (char *)(v25 + v16 + 24);
                v20 = *(_BYTE *)(v25 + v16 + 8);
                v21 = *(_BYTE **)(v25 + v16 + 16);
                v18 = *(_BYTE *)(v25 + v16 + 9);
              }
            }
          }
          else
          {
            LODWORD(v11) = v25 + 40;
            if ( v25 + 40 <= v24 )
            {
              if ( *(_BYTE *)(v25 + v16 + 10) )
                v19 = (char *)(v25 + v16 + 24);
              v21 = *(_BYTE **)(v25 + v16 + 16);
LABEL_43:
              v18 = *(_BYTE *)(v25 + v16 + 9);
              v20 = *(_BYTE *)(v25 + v16 + 8);
LABEL_44:
              if ( v19 )
              {
                v27 = *v19;
                goto LABEL_47;
              }
              goto LABEL_69;
            }
          }
          if ( v23 )
            goto LABEL_44;
        }
      }
      v22 = (unsigned int)(v22 + 1);
      if ( (unsigned int)v22 >= v17 )
        goto LABEL_44;
    }
  }
  v27 = *(_BYTE *)(v16 + 72);
  v21 = *(_BYTE **)(v16 + 32);
  v18 = *(_BYTE *)(v16 + 11);
  v20 = *(_BYTE *)(v16 + 4);
  if ( *(_BYTE *)(v16 + 2) )
    goto LABEL_69;
LABEL_47:
  LOBYTE(v11) = v27 - 8;
  if ( (v11 & 0x5D) == 0 )
  {
    v28 = *(_BYTE *)(v16 + 3);
    if ( v28 == 1 || !v21 || !v18 )
      goto LABEL_64;
    LOBYTE(v16) = 0;
    v29 = 0;
    v30 = 0;
    v11 = (unsigned __int64)&v21[v18];
    v31 = v21 + 8;
    if ( (unsigned __int8)((*v21 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v31 <= v11 )
      {
        v29 = v21[2];
        LOBYTE(v16) = v21[1] & 0xF;
        v30 = v21[3];
        goto LABEL_63;
      }
    }
    else if ( (unsigned __int64)v31 <= v11 )
    {
      v32 = v21 + 13;
      LOBYTE(v16) = v21[2] & 0xF;
      v33 = v18;
      if ( (unsigned int)(unsigned __int8)v21[7] + 8 <= v18 )
        v33 = (unsigned __int8)v21[7] + 8;
      v11 = (unsigned __int64)&v21[v33];
      if ( (unsigned __int64)v32 <= v11 )
        v29 = v21[12];
      if ( (unsigned __int64)(v21 + 14) > v11 )
        v30 = 0;
      else
        v30 = *v32;
LABEL_63:
      if ( v3 )
      {
LABEL_65:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v11,
          v16,
          (unsigned int)&v121,
          a3,
          *(_DWORD *)(a3 + 48),
          v28,
          v20,
          v16,
          v29,
          v30,
          a3);
        goto LABEL_69;
      }
LABEL_64:
      LOBYTE(v16) = 0;
      v29 = 0;
      v30 = 0;
      goto LABEL_65;
    }
    v3 = 0;
    goto LABEL_63;
  }
LABEL_69:
  IofCompleteRequest((PIRP)a3, 0);
  return v119;
}

```

## disassembly

```asm
0x14005df48  mov     [rsp-8+arg_18], rbx
0x14005df4d  push    rbp
0x14005df4e  push    rsi
0x14005df4f  push    rdi
0x14005df50  push    r12
0x14005df52  push    r13
0x14005df54  push    r14
0x14005df56  push    r15
0x14005df58  lea     rbp, [rsp-27h]
0x14005df5d  sub     rsp, 0A0h
0x14005df64  mov     rax, cs:__security_cookie
0x14005df6b  xor     rax, rsp
0x14005df6e  mov     [rbp+57h+var_38], rax
0x14005df72  xorps   xmm0, xmm0
0x14005df75  mov     qword ptr [rbp+57h+var_58], rcx
0x14005df79  mov     esi, 1
0x14005df7e  mov     rbx, r8
0x14005df81  movups  [rbp+57h+var_48], xmm0
0x14005df85  mov     [rbp+57h+var_70], sil
0x14005df89  mov     r14, rdx
0x14005df8c  mov     r13, rcx
0x14005df8f  call    NvmeAdapterAcquireRemoveLock
0x14005df94  cmp     cs:StorEtwLoggingEnabled, 0
0x14005df9b  mov     r15d, eax
0x14005df9e  mov     rcx, [rbx+0B8h]
0x14005dfa5  mov     [rbp+57h+var_6C], eax
0x14005dfa8  mov     edi, [rcx+18h]
0x14005dfab  jz      short loc_14005DFF6
0x14005dfad  lea     rdx, [rbp+57h+var_48]
0x14005dfb1  mov     rcx, rbx
0x14005dfb4  call    cs:__imp_IoGetActivityIdIrp
0x14005dfbb  nop     dword ptr [rax+rax+00h]
0x14005dfc0  test    cs:byte_140177432, 2
0x14005dfc7  jz      short loc_14005DFF6
0x14005dfc9  mov     rax, [rbx+0B8h]
0x14005dfd0  lea     r8, [rbp+57h+var_48]
0x14005dfd4  mov     [rsp+0D0h+var_A0], edi
0x14005dfd8  mov     r9, rbx
0x14005dfdb  movzx   edx, byte ptr [rax]
0x14005dfde  movzx   ecx, byte ptr [rax+1]
0x14005dfe2  mov     [rsp+0D0h+var_A8], ecx
0x14005dfe6  mov     dword ptr [rsp+0D0h+var_B0], edx
0x14005dfea  lea     rdx, EventIOCTL
0x14005dff1  call    McTemplateK0pddd_EtwWriteTransfer
0x14005dff6  test    r15d, r15d
0x14005dff9  jns     loc_14005E2E9
0x14005dfff  cmp     cs:StorEtwLoggingEnabled, 0
0x14005e006  mov     qword ptr [rbx+38h], 0
0x14005e00e  mov     byte ptr [rbx+8Dh], 0ACh
0x14005e015  mov     [rbx+30h], r15d
0x14005e019  jz      loc_14005E2D0
0x14005e01f  xorps   xmm0, xmm0
0x14005e022  lea     rdx, [rbp+57h+var_58]
0x14005e026  mov     rcx, rbx
0x14005e029  movups  [rbp+57h+var_58], xmm0
0x14005e02d  call    cs:__imp_IoGetActivityIdIrp
0x14005e034  nop     dword ptr [rax+rax+00h]
0x14005e039  mov     rdx, [rbx+0B8h]
0x14005e040  movzx   eax, byte ptr [rdx]
0x14005e043  sub     eax, 0Eh
0x14005e046  jz      loc_14005E2AD
0x14005e04c  sub     eax, esi
0x14005e04e  jz      short loc_14005E0B6
0x14005e050  cmp     eax, 0Ch
0x14005e053  jnz     loc_14005E2D0
0x14005e059  cmp     byte ptr [rdx+1], 7
0x14005e05d  jnz     short loc_14005E09D
0x14005e05f  cmp     dword ptr [rdx+8], 0
0x14005e063  jnz     short loc_14005E09D
0x14005e065  test    cs:byte_140177432, 40h
0x14005e06c  jz      loc_14005E2D0
0x14005e072  mov     rax, [rbx+38h]
0x14005e076  test    rax, rax
0x14005e079  jz      short loc_14005E07F
0x14005e07b  mov     ecx, [rax]
0x14005e07d  jmp     short loc_14005E081
0x14005e07f  xor     ecx, ecx
0x14005e081  mov     eax, [rbx+30h]
0x14005e084  lea     r8, [rbp+57h+var_58]
0x14005e088  mov     [rsp+0D0h+var_A8], eax
0x14005e08c  mov     r9, rbx
0x14005e08f  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x14005e093  call    McTemplateK0pqd_EtwWriteTransfer
0x14005e098  jmp     loc_14005E2D0
0x14005e09d  test    cs:byte_140177432, 20h
0x14005e0a4  jz      loc_14005E2D0
0x14005e0aa  lea     rdx, EventPnpRequestComplete
0x14005e0b1  jmp     loc_14005E2BD
0x14005e0b6  cmp     cs:byte_140177431, 0
0x14005e0bd  jge     loc_14005E2D0
0x14005e0c3  mov     rdx, [rdx+8]
0x14005e0c7  movzx   eax, byte ptr [rdx+2]
0x14005e0cb  cmp     al, 28h ; '('
0x14005e0cd  jnz     loc_14005E1B6
0x14005e0d3  cmp     dword ptr [rdx+14h], 0
0x14005e0d7  jnz     loc_14005E2D0
0x14005e0dd  mov     r12d, [rdx+38h]
0x14005e0e1  test    r12d, r12d
0x14005e0e4  jz      loc_14005E2D0
0x14005e0ea  xor     r10b, r10b
0x14005e0ed  xor     r11d, r11d
0x14005e0f0  xor     r14b, r14b
0x14005e0f3  xor     r9d, r9d
0x14005e0f6  xor     r15d, r15d
0x14005e0f9  xor     r13b, r13b
0x14005e0fc  mov     ecx, [rdx+r15*4+78h]
0x14005e101  cmp     ecx, 80h
0x14005e107  jb      short loc_14005E17C
0x14005e109  mov     edi, [rdx+10h]
0x14005e10c  cmp     ecx, edi
0x14005e10e  jnb     short loc_14005E17C
0x14005e110  mov     r8d, ecx
0x14005e113  mov     ecx, [rcx+rdx]
0x14005e116  sub     ecx, 40h ; '@'
0x14005e119  jz      short loc_14005E16E
0x14005e11b  sub     ecx, esi
0x14005e11d  jz      short loc_14005E142
0x14005e11f  cmp     ecx, esi
0x14005e121  jnz     short loc_14005E177
0x14005e123  lea     rcx, [r8+28h]
0x14005e127  cmp     rcx, rdi
0x14005e12a  ja      short loc_14005E177
0x14005e12c  cmp     dword ptr [r8+rdx+0Ch], 0
0x14005e132  jbe     short loc_14005E13B
0x14005e134  lea     r11, [rdx+20h]
0x14005e138  add     r11, r8
0x14005e13b  mov     r9, [r8+rdx+18h]
0x14005e140  jmp     short loc_14005E19E
0x14005e142  lea     rcx, [r8+38h]
0x14005e146  cmp     rcx, rdi
0x14005e149  ja      short loc_14005E177
0x14005e14b  cmp     byte ptr [r8+rdx+0Ah], 0
0x14005e151  mov     r13b, sil
0x14005e154  jbe     short loc_14005E15D
0x14005e156  lea     r11, [rdx+18h]
0x14005e15a  add     r11, r8
0x14005e15d  mov     r14b, [r8+rdx+8]
0x14005e162  mov     r9, [r8+rdx+10h]
0x14005e167  mov     r10b, [r8+rdx+9]
0x14005e16c  jmp     short loc_14005E177
0x14005e16e  lea     rcx, [r8+28h]
0x14005e172  cmp     rcx, rdi
0x14005e175  jbe     short loc_14005E18A
0x14005e177  test    r13b, r13b
0x14005e17a  jnz     short loc_14005E1A8
0x14005e17c  add     r15d, esi
0x14005e17f  cmp     r15d, r12d
0x14005e182  jb      loc_14005E0FC
0x14005e188  jmp     short loc_14005E1A8
0x14005e18a  cmp     byte ptr [r8+rdx+0Ah], 0
0x14005e190  jbe     short loc_14005E199
0x14005e192  lea     r11, [rdx+18h]
0x14005e196  add     r11, r8
0x14005e199  mov     r9, [r8+rdx+10h]
0x14005e19e  mov     r10b, [r8+rdx+9]
0x14005e1a3  mov     r14b, [r8+rdx+8]
0x14005e1a8  test    r11, r11
0x14005e1ab  jz      loc_14005E2D0
0x14005e1b1  mov     cl, [r11]
0x14005e1b4  jmp     short loc_14005E1CD
0x14005e1b6  mov     cl, [rdx+48h]
0x14005e1b9  mov     r9, [rdx+20h]
0x14005e1bd  mov     r10b, [rdx+0Bh]
0x14005e1c1  mov     r14b, [rdx+4]
0x14005e1c5  test    eax, eax
0x14005e1c7  jnz     loc_14005E2D0
0x14005e1cd  sub     cl, 8
0x14005e1d0  test    cl, 5Dh
0x14005e1d3  jnz     loc_14005E2D0
0x14005e1d9  mov     dil, [rdx+3]
0x14005e1dd  cmp     dil, sil
0x14005e1e0  jz      loc_14005E273
0x14005e1e6  test    r9, r9
0x14005e1e9  jz      loc_14005E273
0x14005e1ef  test    r10b, r10b
0x14005e1f2  jz      short loc_14005E273
0x14005e1f4  mov     al, [r9]
0x14005e1f7  xor     dl, dl
0x14005e1f9  and     al, 7Fh
0x14005e1fb  movzx   ecx, r10b
0x14005e1ff  sub     al, 72h ; 'r'
0x14005e201  xor     r11b, r11b
0x14005e204  xor     r8b, r8b
0x14005e207  add     rcx, r9
0x14005e20a  cmp     al, sil
0x14005e20d  lea     rax, [r9+8]
0x14005e211  jbe     short loc_14005E255
0x14005e213  cmp     rax, rcx
0x14005e216  ja      short loc_14005E26B
0x14005e218  movzx   ecx, byte ptr [r9+7]
0x14005e21d  lea     r8, [r9+0Dh]
0x14005e221  mov     dl, [r9+2]
0x14005e225  add     ecx, 8
0x14005e228  and     dl, 0Fh
0x14005e22b  movzx   eax, r10b
0x14005e22f  cmp     ecx, eax
0x14005e231  cmovbe  eax, ecx
0x14005e234  mov     ecx, eax
0x14005e236  add     rcx, r9
0x14005e239  cmp     r8, rcx
0x14005e23c  ja      short loc_14005E242
0x14005e23e  mov     r11b, [r9+0Ch]
0x14005e242  lea     rax, [r9+0Eh]
0x14005e246  cmp     rax, rcx
0x14005e249  ja      short loc_14005E250
0x14005e24b  mov     r8b, [r8]
0x14005e24e  jmp     short loc_14005E26E
0x14005e250  xor     r8b, r8b
0x14005e253  jmp     short loc_14005E26E
0x14005e255  cmp     rax, rcx
0x14005e258  ja      short loc_14005E26B
0x14005e25a  mov     dl, [r9+1]
0x14005e25e  mov     r11b, [r9+2]
0x14005e262  and     dl, 0Fh
0x14005e265  mov     r8b, [r9+3]
0x14005e269  jmp     short loc_14005E26E
0x14005e26b  xor     sil, sil
0x14005e26e  test    sil, sil
0x14005e271  jnz     short loc_14005E27B
0x14005e273  xor     dl, dl
0x14005e275  xor     r11b, r11b
0x14005e278  xor     r8b, r8b
0x14005e27b  mov     eax, [rbx+30h]
0x14005e27e  mov     r9, rbx
0x14005e281  mov     [rsp+0D0h+var_80], rbx
0x14005e286  mov     [rsp+0D0h+var_88], r8b
0x14005e28b  lea     r8, [rbp+57h+var_58]
0x14005e28f  mov     [rsp+0D0h+var_90], r11b
0x14005e294  mov     [rsp+0D0h+var_98], dl
0x14005e298  mov     byte ptr [rsp+0D0h+var_A0], r14b
0x14005e29d  mov     byte ptr [rsp+0D0h+var_A8], dil
0x14005e2a2  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14005e2a6  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x14005e2ab  jmp     short loc_14005E2D0
0x14005e2ad  test    cs:byte_140177432, 8
0x14005e2b4  jz      short loc_14005E2D0
0x14005e2b6  lea     rdx, EventNonReadWriteRequestComplete
0x14005e2bd  mov     eax, [rbx+30h]
0x14005e2c0  lea     r8, [rbp+57h+var_58]
0x14005e2c4  mov     r9, rbx
0x14005e2c7  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14005e2cb  call    McTemplateK0pd_EtwWriteTransfer
0x14005e2d0  xor     edx, edx; PriorityBoost
0x14005e2d2  mov     rcx, rbx; Irp
0x14005e2d5  call    cs:__imp_IofCompleteRequest
0x14005e2dc  nop     dword ptr [rax+rax+00h]
0x14005e2e1  mov     eax, [rbp+57h+var_6C]
0x14005e2e4  jmp     loc_14005ED3B
0x14005e2e9  mov     eax, 2DD3C0h
0x14005e2ee  cmp     edi, eax
0x14005e2f0  ja      loc_14005E99A
0x14005e2f6  jz      loc_14005E983
0x14005e2fc  sub     edi, 4101Ch
0x14005e302  jz      loc_14005E3A5
0x14005e308  sub     edi, 2903DCh
0x14005e30e  jz      loc_14005E398
0x14005e314  sub     edi, 8
0x14005e317  jz      short loc_14005E384
0x14005e319  sub     edi, 800h
0x14005e31f  jz      short loc_14005E36D
0x14005e321  sub     edi, 14h
0x14005e324  jz      short loc_14005E360
0x14005e326  sub     edi, 0B8h
0x14005e32c  jz      short loc_14005E34E
0x14005e32e  cmp     edi, 0B534h
0x14005e334  jnz     loc_14005E9D6
0x14005e33a  lea     r8, [rbp+57h+var_70]
0x14005e33e  mov     rdx, rbx
0x14005e341  mov     rcx, r13
0x14005e344  call    NvmeAdapterSetTemperatureThresholdIoctl
0x14005e349  jmp     loc_14005ED1A
0x14005e34e  mov     rdx, rbx
0x14005e351  mov     rcx, r13
0x14005e354  call    NvmeAdapterSetLedState
0x14005e359  mov     edi, eax
0x14005e35b  jmp     loc_14005ED22
0x14005e360  mov     rdx, rbx
0x14005e363  mov     rcx, r13
0x14005e366  call    NvmeAdapterBootPartitionGetInfoIoctl
0x14005e36b  jmp     short loc_14005E359
0x14005e36d  lea     r9, [rbp+57h+var_70]
0x14005e371  mov     r8, rbx
0x14005e374  mov     rdx, r14
0x14005e377  mov     rcx, r13
0x14005e37a  call    NvmeAdapterFirmwareGetInfoIoctl
0x14005e37f  jmp     loc_14005ED1A
0x14005e384  lea     r8, [rbp+57h+var_70]
0x14005e388  mov     rdx, rbx
0x14005e38b  mov     rcx, r13
0x14005e38e  call    NvmeAdapterStorageQueryProperty
0x14005e393  jmp     loc_14005ED1A
0x14005e398  mov     rdx, rbx
0x14005e39b  mov     rcx, r13
0x14005e39e  call    NvmeAdapterStorageInternalQueryPropertyIoctl
0x14005e3a3  jmp     short loc_14005E359
0x14005e3a5  mov     rax, [r13+198h]
0x14005e3ac  mov     ecx, [rax+0B8h]
0x14005e3b2  shr     ecx, 1Eh
0x14005e3b5  mov     byte ptr [rbx+8Dh], 0ACh
0x14005e3bc  test    sil, cl
  ... truncated ...
```
