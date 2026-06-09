# RaUnitQueryCapabilitiesIrp

- ea: `0x1401bcb90`
- end: `0x1401bd718`
- name: `RaUnitQueryCapabilitiesIrp`
- size: `2952`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004018c`

## callees

- `0x1400016cc`
- `0x140003df0`
- `0x140005c50`
- `0x140005c88`
- `0x1400290b0`
- `0x140048748`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400cbf18`
- `0x14014b400`
- `0x14014b800`
- `0x1401bcb90`
- `0x1401bd720`
- `0x1401bd878`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x1401bd0e3`
- `ntoskrnl!PoFxIdleComponent` at `0x1401bd0e3`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401bce9f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401bd143`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401bce9f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401bd143`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401bce05`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401bce05`
- `ntoskrnl!IofCompleteRequest` at `0x1401bced7`
- `ntoskrnl!IofCompleteRequest` at `0x1401bd17b`
- `ntoskrnl!IofCompleteRequest` at `0x1401bced7`
- `ntoskrnl!IofCompleteRequest` at `0x1401bd17b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401bcf78`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401bd0f6`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401bcf78`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401bd0f6`
- `ntoskrnl!PoFxActivateComponent` at `0x1401bcf62`
- `ntoskrnl!PoFxActivateComponent` at `0x1401bcf62`

## pseudocode

```c
__int64 __fastcall RaUnitQueryCapabilitiesIrp(__int64 a1, __int64 a2)
{
  __int64 v4; // r13
  char v5; // si
  int v6; // eax
  char v7; // bl
  __int64 v8; // r9
  __int64 v9; // r15
  _DWORD *Pool; // r12
  int v11; // r9d
  int v12; // r8d
  int v13; // r8d
  int v14; // edx
  int v15; // edx
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  int v19; // ecx
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  int v23; // ecx
  int v24; // edx
  char v25; // cl
  __int64 v26; // rcx
  __int64 v27; // r9
  __int64 v28; // r15
  bool v29; // zf
  unsigned __int64 v30; // rcx
  __int64 v31; // rdx
  volatile signed __int32 *v33; // rcx
  __int64 v34; // r8
  __int64 v35; // rcx
  int v36; // eax
  int v37; // ecx
  int v38; // eax
  int v39; // ecx
  int v40; // eax
  int v41; // ecx
  int v42; // eax
  int v43; // ecx
  int v44; // eax
  int v45; // ecx
  int v46; // eax
  int v47; // ecx
  int v48; // eax
  unsigned __int64 v49; // rcx
  __int64 v50; // rdx
  __int64 *v51; // rdx
  int *v52; // rax
  int v53; // ecx
  int *v54; // rax
  int v55; // ecx
  char v56; // cl
  _BYTE *v57; // r9
  unsigned __int8 v58; // r10
  char v59; // bl
  char v60; // r14
  __int64 v61; // rdx
  char v62; // r11
  char v63; // r8
  _BYTE *v64; // rax
  char *v65; // r8
  unsigned int v66; // eax
  char v67; // cl
  _BYTE *v68; // r9
  unsigned __int8 v69; // r10
  char v70; // bl
  char v71; // r14
  __int64 v72; // rdx
  char v73; // r11
  char v74; // r8
  _BYTE *v75; // rax
  char *v76; // r8
  unsigned int v77; // eax
  __int64 v78; // r8
  int v79; // ecx
  __int64 v80; // r15
  char v81; // r13
  char *v82; // r11
  __int64 v83; // r8
  int v84; // ecx
  __int64 v85; // r15
  char v86; // r13
  char *v87; // r11
  unsigned int v88; // r12d
  unsigned __int64 v89; // r14
  unsigned int v90; // r12d
  unsigned __int64 v91; // r14
  __int128 v92; // [rsp+60h] [rbp-39h] BYREF
  _OWORD v93[4]; // [rsp+70h] [rbp-29h] BYREF

  memset_0(v93, 0, sizeof(v93));
  v4 = *(_QWORD *)(a1 + 24);
  v5 = 1;
  if ( !v4 || (v6 = *(_DWORD *)(a1 + 56)) == 0 || (unsigned int)(v6 - 5) <= 1 )
  {
    v29 = StorEtwLoggingEnabled == 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = -1073741810;
    if ( v29 )
      goto LABEL_50;
    v92 = 0;
    IoGetActivityIdIrp(a2, &v92);
    v50 = *(_QWORD *)(a2 + 184);
    if ( *(_BYTE *)v50 == 14 )
    {
      if ( (byte_140177432 & 8) != 0 )
        McTemplateK0pd_EtwWriteTransfer(
          *(unsigned int *)(a2 + 48),
          EventNonReadWriteRequestComplete,
          &v92,
          a2,
          *(_DWORD *)(a2 + 48));
      goto LABEL_50;
    }
    if ( *(_BYTE *)v50 != 15 )
    {
      if ( *(_BYTE *)v50 == 27 )
      {
        if ( *(_BYTE *)(v50 + 1) == 7 && !*(_DWORD *)(v50 + 8) )
        {
          if ( (byte_140177432 & 0x40) != 0 )
          {
            v54 = *(int **)(a2 + 56);
            if ( v54 )
              v55 = *v54;
            else
              v55 = 0;
            McTemplateK0pqd_EtwWriteTransfer(v55, v50, (unsigned int)&v92, a2, v55, *(_DWORD *)(a2 + 48));
          }
        }
        else if ( (byte_140177432 & 0x20) != 0 )
        {
          McTemplateK0pd_EtwWriteTransfer(v49, EventPnpRequestComplete, &v92, a2, *(_DWORD *)(a2 + 48));
        }
      }
      goto LABEL_50;
    }
    if ( byte_140177431 >= 0 )
    {
LABEL_50:
      IofCompleteRequest((PIRP)a2, 0);
      return 3221225486LL;
    }
    v72 = *(_QWORD *)(v50 + 8);
    if ( *(_BYTE *)(v72 + 2) != 40 )
    {
      v67 = *(_BYTE *)(v72 + 72);
      v68 = *(_BYTE **)(v72 + 32);
      v69 = *(_BYTE *)(v72 + 11);
      v70 = *(_BYTE *)(v72 + 4);
      if ( !*(_BYTE *)(v72 + 2) )
        goto LABEL_88;
      goto LABEL_50;
    }
    if ( *(_DWORD *)(v72 + 20) )
      goto LABEL_50;
    v90 = *(_DWORD *)(v72 + 56);
    if ( !v90 )
      goto LABEL_50;
    v69 = 0;
    v87 = 0;
    v70 = 0;
    v68 = 0;
    v85 = 0;
    v86 = 0;
    while ( 1 )
    {
      v49 = *(unsigned int *)(v72 + 4 * v85 + 120);
      if ( (unsigned int)v49 >= 0x80 )
      {
        v91 = *(unsigned int *)(v72 + 16);
        if ( (unsigned int)v49 < (unsigned int)v91 )
        {
          v83 = *(unsigned int *)(v72 + 4 * v85 + 120);
          v84 = *(_DWORD *)(v49 + v72) - 64;
          if ( v84 )
          {
            LODWORD(v49) = v84 - 1;
            if ( (_DWORD)v49 )
            {
              if ( (_DWORD)v49 == 1 )
              {
                LODWORD(v49) = v83 + 40;
                if ( v83 + 40 <= v91 )
                {
                  if ( *(_DWORD *)(v83 + v72 + 12) )
                    v87 = (char *)(v83 + v72 + 32);
                  v68 = *(_BYTE **)(v83 + v72 + 24);
LABEL_137:
                  v69 = *(_BYTE *)(v83 + v72 + 9);
                  v70 = *(_BYTE *)(v83 + v72 + 8);
LABEL_126:
                  if ( !v87 )
                    goto LABEL_50;
                  v67 = *v87;
LABEL_88:
                  LOBYTE(v49) = v67 - 8;
                  if ( (v49 & 0x5D) != 0 )
                    goto LABEL_50;
                  v71 = *(_BYTE *)(v72 + 3);
                  if ( v71 == 1 || !v68 || !v69 )
                    goto LABEL_154;
                  LOBYTE(v72) = 0;
                  v73 = 0;
                  v74 = 0;
                  v49 = (unsigned __int64)&v68[v69];
                  v75 = v68 + 8;
                  if ( (unsigned __int8)((*v68 & 0x7F) - 114) <= 1u )
                  {
                    if ( (unsigned __int64)v75 <= v49 )
                    {
                      v73 = v68[2];
                      LOBYTE(v72) = v68[1] & 0xF;
                      v74 = v68[3];
                      goto LABEL_171;
                    }
                  }
                  else if ( (unsigned __int64)v75 <= v49 )
                  {
                    v76 = v68 + 13;
                    LOBYTE(v72) = v68[2] & 0xF;
                    v77 = v69;
                    if ( (unsigned int)(unsigned __int8)v68[7] + 8 <= v69 )
                      v77 = (unsigned __int8)v68[7] + 8;
                    v49 = (unsigned __int64)&v68[v77];
                    if ( (unsigned __int64)v76 <= v49 )
                      v73 = v68[12];
                    if ( (unsigned __int64)(v68 + 14) > v49 )
                      v74 = 0;
                    else
                      v74 = *v76;
LABEL_171:
                    if ( !v5 )
                    {
LABEL_154:
                      LOBYTE(v72) = 0;
                      v73 = 0;
                      v74 = 0;
                    }
                    McTemplateK0pduuuuup_EtwWriteTransfer(
                      v49,
                      v72,
                      (unsigned int)&v92,
                      a2,
                      *(_DWORD *)(a2 + 48),
                      v71,
                      v70,
                      v72,
                      v73,
                      v74,
                      a2);
                    goto LABEL_50;
                  }
                  v5 = 0;
                  goto LABEL_171;
                }
              }
            }
            else
            {
              LODWORD(v49) = v83 + 56;
              if ( v83 + 56 <= v91 )
              {
                v86 = 1;
                if ( *(_BYTE *)(v83 + v72 + 10) )
                  v87 = (char *)(v83 + v72 + 24);
                v70 = *(_BYTE *)(v83 + v72 + 8);
                v68 = *(_BYTE **)(v83 + v72 + 16);
                v69 = *(_BYTE *)(v83 + v72 + 9);
              }
            }
          }
          else
          {
            LODWORD(v49) = v83 + 40;
            if ( v83 + 40 <= v91 )
            {
              if ( *(_BYTE *)(v83 + v72 + 10) )
                v87 = (char *)(v83 + v72 + 24);
              v68 = *(_BYTE **)(v83 + v72 + 16);
              goto LABEL_137;
            }
          }
          if ( v86 )
            goto LABEL_126;
        }
      }
      v85 = (unsigned int)(v85 + 1);
      if ( (unsigned int)v85 >= v90 )
        goto LABEL_126;
    }
  }
  if ( *(_QWORD *)(v4 + 5024) )
  {
    RaidAdapterPoFxActivateComponent(*(_QWORD *)(a1 + 24), 0, 1);
    v7 = 2;
  }
  else
  {
    v7 = 0;
  }
  if ( (unsigned __int8)RaidUnitCheckAndAcquirePoFx(a1) )
  {
    if ( (*(_BYTE *)(v4 + 108) & 1) != 0 )
    {
      _InterlockedAdd64((volatile signed __int64 *)(a1 + 2168), 1u);
      if ( (*(_BYTE *)(v4 + 108) & 2) != 0 )
        _InterlockedAdd64((volatile signed __int64 *)(a1 + 2176), 1u);
    }
    v33 = *(volatile signed __int32 **)(a1 + 1872);
    if ( (v33[37] & 1) != 0 )
    {
      _InterlockedAdd(v33 + 36, 1u);
      v33 = *(volatile signed __int32 **)(a1 + 1872);
    }
    v34 = 5;
    v35 = *(_QWORD *)v33;
    if ( !*(_DWORD *)(a1 + 1036) )
      v34 = 1;
    PoFxActivateComponent(v35, 0, v34);
    v7 |= 1u;
    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864));
  }
  v8 = *(_QWORD *)(a1 + 8);
  v9 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL);
  *(_QWORD *)&v92 = 4 * (*(_DWORD *)(*(_QWORD *)(v4 + 592) + 184LL) & 4 | 2u);
  Pool = (_DWORD *)RaidAllocatePool(64, v92, 1918067026, v8);
  PortWdmGetDeviceCapabilities(*(PDEVICE_OBJECT *)(v4 + 8), v93);
  v11 = 256;
  *(_OWORD *)v9 = v93[0];
  *(_OWORD *)(v9 + 16) = v93[1];
  v12 = 128;
  *(_OWORD *)(v9 + 32) = v93[2];
  *(_OWORD *)(v9 + 48) = v93[3];
  *(_DWORD *)(v9 + 4) |= 0x100u;
  if ( (*(_DWORD *)(a1 + 1952) & 0x20) != 0 || *(_BYTE *)(PortGetDeviceType(**(_BYTE **)(a1 + 112) & 0x1F) + 24) )
    *(_DWORD *)(v9 + 4) |= v12;
  *(_DWORD *)(v9 + 8) = (unsigned __int8)BYTE1(*(_DWORD *)(a1 + 104));
  if ( Pool )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v4 + 592) + 184LL) & 4) != 0 )
    {
      v36 = Pool[1];
      *Pool = 1572865;
      v37 = v36 ^ (*(_DWORD *)(v9 + 4) ^ v36) & 1;
      Pool[1] = v37;
      v38 = v37 ^ (*(_DWORD *)(v9 + 4) ^ v37) & 2;
      Pool[1] = v38;
      v39 = v38 ^ (*(_DWORD *)(v9 + 4) ^ v38) & 4;
      Pool[1] = v39;
      v40 = v39 ^ (*(_DWORD *)(v9 + 4) ^ v39) & 8;
      Pool[1] = v40;
      v41 = v40 ^ (*(_DWORD *)(v9 + 4) ^ v40) & 0x10;
      Pool[1] = v41;
      v42 = v41 ^ (*(_DWORD *)(v9 + 4) ^ v41) & 0x20;
      Pool[1] = v42;
      v43 = v42 ^ (*(_DWORD *)(v9 + 4) ^ v42) & 0x40;
      Pool[1] = v43;
      v44 = v43 ^ v12 & (*(_DWORD *)(v9 + 4) ^ v43);
      Pool[1] = v44;
      v45 = v44 ^ v11 & (*(_DWORD *)(v9 + 4) ^ v44);
      Pool[1] = v45;
      v46 = v45 ^ (*(_DWORD *)(v9 + 4) ^ v45) & 0x200;
      Pool[1] = v46;
      v47 = v46 ^ ((unsigned __int16)v46 ^ (unsigned __int16)(*(_DWORD *)(v9 + 4) >> 7)) & 0x400;
      Pool[1] = v47;
      Pool[3] = *(_DWORD *)(v9 + 12);
      if ( v4 != -4800 && *(_BYTE *)(v4 + 4811) == 1 && *(_BYTE *)(v4 + 4810) == 6 )
        v48 = (*(unsigned __int8 *)(a1 + 104) << 16) | 0xFFFF;
      else
        v48 = *(_DWORD *)(v9 + 8);
      Pool[2] = v48;
      Pool[1] = v47 & 0xFFFFF7FF;
    }
    if ( (int)RaidPnPPassToMiniPort(*(_QWORD *)(a1 + 8), 9u, 0, (__int64)Pool, v92) >= 0 )
    {
      v13 = *(_DWORD *)(v9 + 4);
      v14 = Pool[1] ^ v13;
      if ( (*(_DWORD *)(*(_QWORD *)(v4 + 592) + 184LL) & 4) != 0 )
      {
        v15 = v13 ^ v14 & 1;
        *(_DWORD *)(v9 + 4) = v15;
        v16 = v15 ^ (Pool[1] ^ v15) & 2;
        *(_DWORD *)(v9 + 4) = v16;
        v17 = v16 ^ (Pool[1] ^ v16) & 4;
        *(_DWORD *)(v9 + 4) = v17;
        v18 = v17 ^ (Pool[1] ^ v17) & 8;
        *(_DWORD *)(v9 + 4) = v18;
        v19 = v18 ^ (Pool[1] ^ v18) & 0x10;
        *(_DWORD *)(v9 + 4) = v19;
        v20 = v19 ^ (Pool[1] ^ v19) & 0x20;
        *(_DWORD *)(v9 + 4) = v20;
        v21 = v20 ^ (Pool[1] ^ v20) & 0x40;
        *(_DWORD *)(v9 + 4) = v21;
        v22 = v21 ^ (Pool[1] ^ v21) & 0x80;
        *(_DWORD *)(v9 + 4) = v22;
        v23 = v22 ^ (Pool[1] ^ v22) & 0x100;
        *(_DWORD *)(v9 + 4) = v23;
        v24 = v23 ^ (Pool[1] ^ v23) & 0x200;
        *(_DWORD *)(v9 + 4) = v24;
        *(_DWORD *)(v9 + 4) = v24 ^ (v24 ^ (Pool[1] << 7)) & 0x20000;
        *(_DWORD *)(v9 + 12) = Pool[3];
        *(_DWORD *)(v9 + 8) = Pool[2];
        if ( (Pool[1] & 0x800) != 0 )
        {
          *(_DWORD *)(a1 + 1952) |= 0x10u;
          RaidUnitSetDefaultWriteCachePolicy(a1);
        }
      }
      else
      {
        *(_DWORD *)(v9 + 4) = v13 ^ v14 & 0x10;
      }
    }
    ExFreePoolWithTag(Pool, 0x72536152u);
  }
  if ( OverrideDeviceUniqueIDCapability )
    *(_DWORD *)(v9 + 4) &= ~0x40u;
  v25 = *(_BYTE *)(a1 + 506) ^ (*(_BYTE *)(a1 + 506) ^ ((unsigned __int8)(*(_DWORD *)(v9 + 4) >> 4) << 6)) & 0x40;
  *(_BYTE *)(a1 + 506) = v25;
  *(_BYTE *)(a1 + 506) = v25 & 0x7F | ((unsigned __int8)(*(_DWORD *)(v9 + 4) >> 9) << 7);
  if ( (unsigned int)RaUnitIsSMRDisabled(a1) )
    *(_DWORD *)(v9 + 4) |= 0x20000u;
  v28 = *(_QWORD *)(a1 + 24);
  if ( (v7 & 1) != 0 && (unsigned __int8)RaidUnitCheckAndAcquirePoFx(v26) )
  {
    PoFxIdleComponent(**(_QWORD **)(a1 + 1872), 0, 0);
    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864));
  }
  if ( (unsigned __int8)v7 >= 2u && *(_QWORD *)(v28 + 5024) )
    RaidAdapterPoFxIdleComponent(v28, 0, 0, v27);
  v29 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = 0;
  if ( v29 )
    goto LABEL_26;
  v92 = 0;
  IoGetActivityIdIrp(a2, &v92);
  v31 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v31 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_26;
    v51 = EventNonReadWriteRequestComplete;
    goto LABEL_53;
  }
  if ( *(_BYTE *)v31 != 15 )
  {
    if ( *(_BYTE *)v31 != 27 )
      goto LABEL_26;
    if ( *(_BYTE *)(v31 + 1) == 7 && !*(_DWORD *)(v31 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v52 = *(int **)(a2 + 56);
        if ( v52 )
          v53 = *v52;
        else
          v53 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v53, v31, (unsigned int)&v92, a2, v53, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_26;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_26;
    v51 = EventPnpRequestComplete;
LABEL_53:
    McTemplateK0pd_EtwWriteTransfer(v30, v51, &v92, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_26;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_26;
  v61 = *(_QWORD *)(v31 + 8);
  if ( *(_BYTE *)(v61 + 2) != 40 )
  {
    v56 = *(_BYTE *)(v61 + 72);
    v57 = *(_BYTE **)(v61 + 32);
    v58 = *(_BYTE *)(v61 + 11);
    v59 = *(_BYTE *)(v61 + 4);
    if ( !*(_BYTE *)(v61 + 2) )
      goto LABEL_75;
    goto LABEL_26;
  }
  if ( *(_DWORD *)(v61 + 20) )
    goto LABEL_26;
  v88 = *(_DWORD *)(v61 + 56);
  if ( !v88 )
    goto LABEL_26;
  v58 = 0;
  v82 = 0;
  v59 = 0;
  v57 = 0;
  v80 = 0;
  v81 = 0;
  while ( 1 )
  {
    v30 = *(unsigned int *)(v61 + 4 * v80 + 120);
    if ( (unsigned int)v30 >= 0x80 )
    {
      v89 = *(unsigned int *)(v61 + 16);
      if ( (unsigned int)v30 < (unsigned int)v89 )
        break;
    }
LABEL_105:
    v80 = (unsigned int)(v80 + 1);
    if ( (unsigned int)v80 >= v88 )
      goto LABEL_106;
  }
  v78 = *(unsigned int *)(v61 + 4 * v80 + 120);
  v79 = *(_DWORD *)(v61 + v30) - 64;
  if ( v79 )
  {
    LODWORD(v30) = v79 - 1;
    if ( (_DWORD)v30 )
    {
      if ( (_DWORD)v30 == 1 )
      {
        LODWORD(v30) = v78 + 40;
        if ( v78 + 40 <= v89 )
        {
          if ( *(_DWORD *)(v61 + v78 + 12) )
            v82 = (char *)(v78 + v61 + 32);
          v57 = *(_BYTE **)(v61 + v78 + 24);
          goto LABEL_117;
        }
      }
    }
    else
    {
      LODWORD(v30) = v78 + 56;
      if ( v78 + 56 <= v89 )
      {
        v81 = 1;
        if ( *(_BYTE *)(v61 + v78 + 10) )
          v82 = (char *)(v78 + v61 + 24);
        v59 = *(_BYTE *)(v61 + v78 + 8);
        v57 = *(_BYTE **)(v61 + v78 + 16);
        v58 = *(_BYTE *)(v61 + v78 + 9);
      }
    }
    goto LABEL_104;
  }
  LODWORD(v30) = v78 + 40;
  if ( v78 + 40 > v89 )
  {
LABEL_104:
    if ( v81 )
      goto LABEL_106;
    goto LABEL_105;
  }
  if ( *(_BYTE *)(v61 + v78 + 10) )
    v82 = (char *)(v78 + v61 + 24);
  v57 = *(_BYTE **)(v61 + v78 + 16);
LABEL_117:
  v58 = *(_BYTE *)(v61 + v78 + 9);
  v59 = *(_BYTE *)(v61 + v78 + 8);
LABEL_106:
  if ( !v82 )
    goto LABEL_26;
  v56 = *v82;
LABEL_75:
  LOBYTE(v30) = v56 - 8;
  if ( (v30 & 0x5D) != 0 )
    goto LABEL_26;
  v60 = *(_BYTE *)(v61 + 3);
  if ( v60 == 1 || !v57 || !v58 )
    goto LABEL_146;
  LOBYTE(v61) = 0;
  v62 = 0;
  v63 = 0;
  v30 = (unsigned __int64)&v57[v58];
  v64 = v57 + 8;
  if ( (unsigned __int8)((*v57 & 0x7F) - 114) <= 1u )
  {
    if ( (unsigned __int64)v64 <= v30 )
    {
      v62 = v57[2];
      LOBYTE(v61) = v57[1] & 0xF;
      v63 = v57[3];
      goto LABEL_163;
    }
    goto LABEL_162;
  }
  if ( (unsigned __int64)v64 > v30 )
  {
LABEL_162:
    v5 = 0;
    goto LABEL_163;
  }
  v65 = v57 + 13;
  LOBYTE(v61) = v57[2] & 0xF;
  v66 = v58;
  if ( (unsigned int)(unsigned __int8)v57[7] + 8 <= v58 )
    v66 = (unsigned __int8)v57[7] + 8;
  v30 = (unsigned __int64)&v57[v66];
  if ( (unsigned __int64)v65 <= v30 )
    v62 = v57[12];
  if ( (unsigned __int64)(v57 + 14) > v30 )
    v63 = 0;
  else
    v63 = *v65;
LABEL_163:
  if ( !v5 )
  {
LABEL_146:
    LOBYTE(v61) = 0;
    v62 = 0;
    v63 = 0;
  }
  McTemplateK0pduuuuup_EtwWriteTransfer(
    v30,
    v61,
    (unsigned int)&v92,
    a2,
    *(_DWORD *)(a2 + 48),
    v60,
    v59,
    v61,
    v62,
    v63,
    a2);
LABEL_26:
  IofCompleteRequest((PIRP)a2, 0);
  return 0;
}

```

## disassembly

```asm
0x1401bcb90  mov     [rsp-8+arg_10], rbx
0x1401bcb95  push    rbp
0x1401bcb96  push    rsi
0x1401bcb97  push    rdi
0x1401bcb98  push    r12
0x1401bcb9a  push    r13
0x1401bcb9c  push    r14
0x1401bcb9e  push    r15
0x1401bcba0  lea     rbp, [rsp-27h]
0x1401bcba5  sub     rsp, 0C0h
0x1401bcbac  mov     rax, cs:__security_cookie
0x1401bcbb3  xor     rax, rsp
0x1401bcbb6  mov     [rbp+57h+var_40], rax
0x1401bcbba  mov     rdi, rdx
0x1401bcbbd  mov     r14, rcx
0x1401bcbc0  mov     r12d, 40h ; '@'
0x1401bcbc6  lea     rcx, [rbp+57h+var_80]; void *
0x1401bcbca  mov     r8d, r12d; Size
0x1401bcbcd  xor     edx, edx; Val
0x1401bcbcf  call    memset_0
0x1401bcbd4  mov     r13, [r14+18h]
0x1401bcbd8  lea     esi, [r12-3Fh]
0x1401bcbdd  test    r13, r13
0x1401bcbe0  jz      loc_1401BD116
0x1401bcbe6  mov     eax, [r14+38h]
0x1401bcbea  test    eax, eax
0x1401bcbec  jz      loc_1401BD116
0x1401bcbf2  add     eax, 0FFFFFFFBh
0x1401bcbf5  cmp     eax, esi
0x1401bcbf7  jbe     loc_1401BD116
0x1401bcbfd  cmp     qword ptr [r13+13A0h], 0
0x1401bcc05  jnz     loc_1401BCF0D
0x1401bcc0b  xor     bl, bl
0x1401bcc0d  mov     rcx, r14
0x1401bcc10  call    RaidUnitCheckAndAcquirePoFx
0x1401bcc15  test    al, al
0x1401bcc17  jnz     loc_1401BCF21
0x1401bcc1d  mov     rax, [rdi+0B8h]
0x1401bcc24  mov     r8d, 72536152h
0x1401bcc2a  mov     r9, [r14+8]
0x1401bcc2e  mov     r15, [rax+8]
0x1401bcc32  mov     rax, [r13+250h]
0x1401bcc39  mov     ecx, [rax+0B8h]
0x1401bcc3f  and     ecx, 4
0x1401bcc42  or      ecx, 2
0x1401bcc45  shl     ecx, 2
0x1401bcc48  mov     eax, ecx
0x1401bcc4a  mov     edx, ecx
0x1401bcc4c  mov     rcx, r12
0x1401bcc4f  mov     qword ptr [rbp+57h+var_90], rax
0x1401bcc53  call    RaidAllocatePool
0x1401bcc58  mov     rcx, [r13+8]; DeviceObject
0x1401bcc5c  lea     rdx, [rbp+57h+var_80]; void *
0x1401bcc60  mov     r12, rax
0x1401bcc63  call    PortWdmGetDeviceCapabilities
0x1401bcc68  movaps  xmm0, [rbp+57h+var_80]
0x1401bcc6c  mov     r9d, 100h
0x1401bcc72  movups  xmmword ptr [r15], xmm0
0x1401bcc76  movaps  xmm1, [rbp+57h+var_70]
0x1401bcc7a  movups  xmmword ptr [r15+10h], xmm1
0x1401bcc7f  lea     r8d, [r9-80h]
0x1401bcc83  movaps  xmm0, [rbp+57h+var_60]
0x1401bcc87  movups  xmmword ptr [r15+20h], xmm0
0x1401bcc8c  movaps  xmm1, [rbp+57h+var_50]
0x1401bcc90  movups  xmmword ptr [r15+30h], xmm1
0x1401bcc95  or      [r15+4], r9d
0x1401bcc99  mov     eax, [r14+7A0h]
0x1401bcca0  test    al, 20h
0x1401bcca2  jz      loc_1401BCF89
0x1401bcca8  or      [r15+4], r8d
0x1401bccac  mov     eax, [r14+68h]
0x1401bccb0  shr     eax, 8
0x1401bccb3  movzx   eax, al
0x1401bccb6  mov     [r15+8], eax
0x1401bccba  test    r12, r12
0x1401bccbd  jz      loc_1401BCE11
0x1401bccc3  mov     rax, [r13+250h]
0x1401bccca  mov     ecx, [rax+0B8h]
0x1401bccd0  test    cl, 4
0x1401bccd3  jnz     loc_1401BCFC7
0x1401bccd9  mov     rax, qword ptr [rbp+57h+var_90]
0x1401bccdd  xor     r8d, r8d
0x1401bcce0  mov     rcx, [r14+8]
0x1401bcce4  mov     r9, r12
0x1401bcce7  mov     [rsp+0F0h+var_C8], 0
0x1401bccef  mov     [rsp+0F0h+var_D0], eax
0x1401bccf3  lea     edx, [r8+9]
0x1401bccf7  call    RaidPnPPassToMiniPort
0x1401bccfc  test    eax, eax
0x1401bccfe  js      loc_1401BCDFD
0x1401bcd04  mov     rax, [r13+250h]
0x1401bcd0b  mov     r8d, [r15+4]
0x1401bcd0f  mov     edx, r8d
0x1401bcd12  xor     edx, [r12+4]
0x1401bcd17  mov     ecx, [rax+0B8h]
0x1401bcd1d  test    cl, 4
0x1401bcd20  jz      loc_1401BD107
0x1401bcd26  and     edx, esi
0x1401bcd28  xor     edx, r8d
0x1401bcd2b  mov     [r15+4], edx
0x1401bcd2f  mov     eax, edx
0x1401bcd31  xor     eax, [r12+4]
0x1401bcd36  and     eax, 2
0x1401bcd39  xor     eax, edx
0x1401bcd3b  mov     [r15+4], eax
0x1401bcd3f  mov     ecx, eax
0x1401bcd41  xor     ecx, [r12+4]
0x1401bcd46  and     ecx, 4
0x1401bcd49  xor     ecx, eax
0x1401bcd4b  mov     [r15+4], ecx
0x1401bcd4f  mov     eax, ecx
0x1401bcd51  xor     eax, [r12+4]
0x1401bcd56  and     eax, 8
0x1401bcd59  xor     eax, ecx
0x1401bcd5b  mov     [r15+4], eax
0x1401bcd5f  mov     ecx, eax
0x1401bcd61  xor     ecx, [r12+4]
0x1401bcd66  and     ecx, 10h
0x1401bcd69  xor     ecx, eax
0x1401bcd6b  mov     [r15+4], ecx
0x1401bcd6f  mov     eax, ecx
0x1401bcd71  xor     eax, [r12+4]
0x1401bcd76  and     eax, 20h
0x1401bcd79  xor     eax, ecx
0x1401bcd7b  mov     [r15+4], eax
0x1401bcd7f  mov     ecx, eax
0x1401bcd81  xor     ecx, [r12+4]
0x1401bcd86  and     ecx, 40h
0x1401bcd89  xor     ecx, eax
0x1401bcd8b  mov     [r15+4], ecx
0x1401bcd8f  mov     eax, ecx
0x1401bcd91  xor     eax, [r12+4]
0x1401bcd96  and     eax, 80h
0x1401bcd9b  xor     eax, ecx
0x1401bcd9d  mov     [r15+4], eax
0x1401bcda1  mov     ecx, eax
0x1401bcda3  xor     ecx, [r12+4]
0x1401bcda8  and     ecx, 100h
0x1401bcdae  xor     ecx, eax
0x1401bcdb0  mov     [r15+4], ecx
0x1401bcdb4  mov     edx, ecx
0x1401bcdb6  xor     edx, [r12+4]
0x1401bcdbb  and     edx, 200h
0x1401bcdc1  xor     edx, ecx
0x1401bcdc3  mov     [r15+4], edx
0x1401bcdc7  mov     eax, [r12+4]
0x1401bcdcc  shl     eax, 7
0x1401bcdcf  xor     eax, edx
0x1401bcdd1  and     eax, 20000h
0x1401bcdd6  xor     eax, edx
0x1401bcdd8  mov     [r15+4], eax
0x1401bcddc  mov     eax, [r12+0Ch]
0x1401bcde1  mov     [r15+0Ch], eax
0x1401bcde5  mov     eax, [r12+8]
0x1401bcdea  mov     [r15+8], eax
0x1401bcdee  test    dword ptr [r12+4], 800h
0x1401bcdf7  jnz     loc_1401BD676
0x1401bcdfd  mov     edx, 72536152h; Tag
0x1401bce02  mov     rcx, r12; P
0x1401bce05  call    cs:__imp_ExFreePoolWithTag
0x1401bce0c  nop     dword ptr [rax+rax+00h]
0x1401bce11  cmp     cs:OverrideDeviceUniqueIDCapability, 0
0x1401bce18  jz      short loc_1401BCE1F
0x1401bce1a  and     dword ptr [r15+4], 0FFFFFFBFh
0x1401bce1f  mov     al, [r14+1FAh]
0x1401bce26  mov     ecx, [r15+4]
0x1401bce2a  shr     ecx, 4
0x1401bce2d  shl     cl, 6
0x1401bce30  xor     cl, al
0x1401bce32  and     cl, 40h
0x1401bce35  xor     cl, al
0x1401bce37  mov     [r14+1FAh], cl
0x1401bce3e  and     cl, 7Fh
0x1401bce41  mov     eax, [r15+4]
0x1401bce45  shr     eax, 9
0x1401bce48  shl     al, 7
0x1401bce4b  or      al, cl
0x1401bce4d  mov     rcx, r14
0x1401bce50  mov     [r14+1FAh], al
0x1401bce57  call    RaUnitIsSMRDisabled
0x1401bce5c  test    eax, eax
0x1401bce5e  jnz     loc_1401BD68B
0x1401bce64  mov     r15, [r14+18h]
0x1401bce68  test    sil, bl
0x1401bce6b  jnz     loc_1401BD0C7
0x1401bce71  cmp     bl, 2
0x1401bce74  jnb     loc_1401BCFA7
0x1401bce7a  cmp     cs:StorEtwLoggingEnabled, 0
0x1401bce81  mov     byte ptr [rdi+8Dh], 0ACh
0x1401bce88  mov     dword ptr [rdi+30h], 0
0x1401bce8f  jz      short loc_1401BCED2
0x1401bce91  xorps   xmm0, xmm0
0x1401bce94  lea     rdx, [rbp+57h+var_90]
0x1401bce98  mov     rcx, rdi
0x1401bce9b  movups  [rbp+57h+var_90], xmm0
0x1401bce9f  call    cs:__imp_IoGetActivityIdIrp
0x1401bcea6  nop     dword ptr [rax+rax+00h]
0x1401bceab  mov     rdx, [rdi+0B8h]
0x1401bceb2  movzx   eax, byte ptr [rdx]
0x1401bceb5  sub     eax, 0Eh
0x1401bceb8  jz      loc_1401BD191
0x1401bcebe  sub     eax, esi
0x1401bcec0  jnz     loc_1401BD1BD
0x1401bcec6  cmp     cs:byte_140177431, al
0x1401bcecc  jl      loc_1401BD696
0x1401bced2  xor     edx, edx; PriorityBoost
0x1401bced4  mov     rcx, rdi; Irp
0x1401bced7  call    cs:__imp_IofCompleteRequest
0x1401bcede  nop     dword ptr [rax+rax+00h]
0x1401bcee3  xor     eax, eax
0x1401bcee5  mov     rcx, [rbp+57h+var_40]
0x1401bcee9  xor     rcx, rsp; StackCookie
0x1401bceec  call    __security_check_cookie
0x1401bcef1  mov     rbx, [rsp+0F0h+arg_10]
0x1401bcef9  add     rsp, 0C0h
0x1401bcf00  pop     r15
0x1401bcf02  pop     r14
0x1401bcf04  pop     r13
0x1401bcf06  pop     r12
0x1401bcf08  pop     rdi
0x1401bcf09  pop     rsi
0x1401bcf0a  pop     rbp
0x1401bcf0b  retn
0x1401bcf0d  mov     r8d, esi
0x1401bcf10  xor     edx, edx
0x1401bcf12  mov     rcx, r13
0x1401bcf15  call    RaidAdapterPoFxActivateComponent
0x1401bcf1a  mov     bl, 2
0x1401bcf1c  jmp     loc_1401BCC0D
0x1401bcf21  test    [r13+6Ch], sil
0x1401bcf25  jnz     loc_1401BD1E2
0x1401bcf2b  mov     rcx, [r14+750h]
0x1401bcf32  mov     eax, [rcx+94h]
0x1401bcf38  test    sil, al
0x1401bcf3b  jz      short loc_1401BCF4B
0x1401bcf3d  lock add [rcx+90h], esi
0x1401bcf44  mov     rcx, [r14+750h]
0x1401bcf4b  cmp     dword ptr [r14+40Ch], 0
0x1401bcf53  mov     r8d, 5
0x1401bcf59  mov     rcx, [rcx]
0x1401bcf5c  cmovbe  r8d, esi
0x1401bcf60  xor     edx, edx
0x1401bcf62  call    cs:__imp_PoFxActivateComponent
0x1401bcf69  nop     dword ptr [rax+rax+00h]
0x1401bcf6e  mov     rcx, [r14+748h]; RunRefCacheAware
0x1401bcf75  or      bl, sil
0x1401bcf78  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401bcf7f  nop     dword ptr [rax+rax+00h]
0x1401bcf84  jmp     loc_1401BCC1D
0x1401bcf89  mov     rax, [r14+70h]
0x1401bcf8d  movzx   ecx, byte ptr [rax]
0x1401bcf90  and     ecx, 1Fh
0x1401bcf93  call    PortGetDeviceType
0x1401bcf98  cmp     byte ptr [rax+18h], 0
0x1401bcf9c  jz      loc_1401BCCAC
0x1401bcfa2  jmp     loc_1401BCCA8
0x1401bcfa7  cmp     qword ptr [r15+13A0h], 0
0x1401bcfaf  jz      loc_1401BCE7A
0x1401bcfb5  xor     r8d, r8d
0x1401bcfb8  xor     edx, edx
0x1401bcfba  mov     rcx, r15
0x1401bcfbd  call    RaidAdapterPoFxIdleComponent
0x1401bcfc2  jmp     loc_1401BCE7A
0x1401bcfc7  mov     eax, [r12+4]
0x1401bcfcc  lea     rdx, [r13+12C0h]
0x1401bcfd3  mov     ecx, eax
0x1401bcfd5  mov     dword ptr [r12], 180001h
0x1401bcfdd  xor     ecx, [r15+4]
0x1401bcfe1  and     ecx, esi
0x1401bcfe3  xor     ecx, eax
0x1401bcfe5  mov     [r12+4], ecx
0x1401bcfea  mov     eax, ecx
0x1401bcfec  xor     eax, [r15+4]
0x1401bcff0  and     eax, 2
0x1401bcff3  xor     eax, ecx
0x1401bcff5  mov     [r12+4], eax
0x1401bcffa  mov     ecx, eax
0x1401bcffc  xor     ecx, [r15+4]
0x1401bd000  and     ecx, 4
0x1401bd003  xor     ecx, eax
0x1401bd005  mov     [r12+4], ecx
0x1401bd00a  mov     eax, ecx
0x1401bd00c  xor     eax, [r15+4]
0x1401bd010  and     eax, 8
0x1401bd013  xor     eax, ecx
0x1401bd015  mov     [r12+4], eax
0x1401bd01a  mov     ecx, eax
0x1401bd01c  xor     ecx, [r15+4]
0x1401bd020  and     ecx, 10h
0x1401bd023  xor     ecx, eax
0x1401bd025  mov     [r12+4], ecx
0x1401bd02a  mov     eax, ecx
0x1401bd02c  xor     eax, [r15+4]
0x1401bd030  and     eax, 20h
0x1401bd033  xor     eax, ecx
0x1401bd035  mov     [r12+4], eax
0x1401bd03a  mov     ecx, eax
0x1401bd03c  xor     ecx, [r15+4]
0x1401bd040  and     ecx, 40h
0x1401bd043  xor     ecx, eax
  ... truncated ...
```
