# NvmeNamespaceDataSetManagementIoctl

- ea: `0x1401acda4`
- end: `0x1401ad74a`
- name: `NvmeNamespaceDataSetManagementIoctl`
- size: `2470`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1401c36a8`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x14011e3b8`
- `0x14011e8e0`
- `0x14014b400`
- `0x1401acda4`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1401ace5c`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401ad16f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401ad45b`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401ace5c`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401ad16f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401ad45b`
- `ntoskrnl!IofCompleteRequest` at `0x1401ad10b`
- `ntoskrnl!IofCompleteRequest` at `0x1401ad41e`
- `ntoskrnl!IofCompleteRequest` at `0x1401ad711`
- `ntoskrnl!IofCompleteRequest` at `0x1401ad10b`
- `ntoskrnl!IofCompleteRequest` at `0x1401ad41e`
- `ntoskrnl!IofCompleteRequest` at `0x1401ad711`

## pseudocode

```c
__int64 __fastcall NvmeNamespaceDataSetManagementIoctl(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rdx
  unsigned __int64 v5; // rcx
  __int64 v6; // r10
  __int64 v7; // r9
  bool v8; // zf
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  int *v11; // rax
  int v12; // ecx
  __int64 *v13; // rdx
  __int64 v14; // rdx
  char v15; // r9
  unsigned int v16; // r15d
  unsigned __int8 v17; // r11
  char *v18; // rdi
  char v19; // r12
  _BYTE *v20; // r10
  __int64 v21; // r14
  char v22; // r13
  unsigned __int64 v23; // rsi
  __int64 v24; // r8
  int v25; // ecx
  char v26; // cl
  char v27; // si
  char v28; // di
  char v29; // r8
  _BYTE *v30; // rax
  char *v31; // r8
  unsigned int v32; // eax
  int v34; // eax
  unsigned __int64 v35; // rcx
  __int64 v36; // rdx
  int *v37; // rax
  int v38; // ecx
  __int64 *v39; // rdx
  __int64 v40; // rdx
  char v41; // r9
  unsigned int v42; // r15d
  unsigned __int8 v43; // r11
  char *v44; // rdi
  char v45; // r12
  _BYTE *v46; // r10
  __int64 v47; // r14
  char v48; // r13
  unsigned __int64 v49; // rsi
  __int64 v50; // r8
  int v51; // ecx
  char v52; // cl
  char v53; // si
  char v54; // di
  char v55; // r8
  _BYTE *v56; // rax
  char *v57; // r8
  unsigned int v58; // eax
  unsigned __int64 v59; // rcx
  __int64 v60; // rdx
  int *v61; // rax
  int v62; // ecx
  __int64 v63; // rdx
  char v64; // r9
  unsigned int v65; // r15d
  unsigned __int8 v66; // r11
  char *v67; // rdi
  char v68; // r12
  _BYTE *v69; // r10
  __int64 v70; // r14
  char v71; // r13
  unsigned __int64 v72; // rsi
  __int64 v73; // r8
  int v74; // ecx
  char v75; // cl
  char v76; // si
  char v77; // di
  char v78; // r8
  _BYTE *v79; // rax
  char *v80; // r8
  unsigned int v81; // eax
  unsigned int v82; // [rsp+60h] [rbp-20h]
  __int128 v83; // [rsp+68h] [rbp-18h] BYREF

  v4 = *(_DWORD **)(a2 + 24);
  if ( !v4
    || (v5 = *(unsigned int *)(*(_QWORD *)(a2 + 184) + 16LL), (unsigned int)v5 < 0x1C)
    || (v6 = (unsigned int)v4[4], v5 < v6 + (unsigned __int64)(unsigned int)v4[3])
    || (v7 = (unsigned int)v4[6], v5 < v7 + (unsigned __int64)(unsigned int)v4[5])
    || v5 < v7 + v6 + 28 )
  {
    v8 = StorEtwLoggingEnabled == 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = -1073741811;
    if ( v8 )
      goto LABEL_205;
    v83 = 0;
    IoGetActivityIdIrp(a2, &v83);
    v60 = *(_QWORD *)(a2 + 184);
    if ( *(_BYTE *)v60 == 14 )
    {
      if ( (byte_140177432 & 8) != 0 )
        McTemplateK0pd_EtwWriteTransfer(
          *(unsigned int *)(a2 + 48),
          EventNonReadWriteRequestComplete,
          &v83,
          a2,
          *(_DWORD *)(a2 + 48));
      goto LABEL_205;
    }
    if ( *(_BYTE *)v60 != 15 )
    {
      if ( *(_BYTE *)v60 == 27 )
      {
        if ( *(_BYTE *)(v60 + 1) != 7 || *(_DWORD *)(v60 + 8) )
        {
          if ( (byte_140177432 & 0x20) != 0 )
            McTemplateK0pd_EtwWriteTransfer(v59, EventPnpRequestComplete, &v83, a2, *(_DWORD *)(a2 + 48));
        }
        else if ( (byte_140177432 & 0x40) != 0 )
        {
          v61 = *(int **)(a2 + 56);
          if ( v61 )
            v62 = *v61;
          else
            v62 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v62, v60, (unsigned int)&v83, a2, v62, *(_DWORD *)(a2 + 48));
        }
      }
      goto LABEL_205;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_205;
    v63 = *(_QWORD *)(v60 + 8);
    v64 = 1;
    if ( *(_BYTE *)(v63 + 2) == 40 )
    {
      if ( *(_DWORD *)(v63 + 20) )
        goto LABEL_205;
      v65 = *(_DWORD *)(v63 + 56);
      if ( !v65 )
        goto LABEL_205;
      v66 = 0;
      v67 = 0;
      v68 = 0;
      v69 = 0;
      v70 = 0;
      v71 = 0;
      while ( 1 )
      {
        v59 = *(unsigned int *)(v63 + 4 * v70 + 120);
        if ( (unsigned int)v59 >= 0x80 )
        {
          v72 = *(unsigned int *)(v63 + 16);
          if ( (unsigned int)v59 < (unsigned int)v72 )
          {
            v73 = (unsigned int)v59;
            v74 = *(_DWORD *)(v59 + v63) - 64;
            if ( v74 )
            {
              LODWORD(v59) = v74 - 1;
              if ( (_DWORD)v59 )
              {
                if ( (_DWORD)v59 == 1 )
                {
                  LODWORD(v59) = v73 + 40;
                  if ( v73 + 40 <= v72 )
                  {
                    if ( *(_DWORD *)(v73 + v63 + 12) )
                      v67 = (char *)(v73 + v63 + 32);
                    v69 = *(_BYTE **)(v73 + v63 + 24);
                    goto LABEL_180;
                  }
                }
              }
              else
              {
                LODWORD(v59) = v73 + 56;
                if ( v73 + 56 <= v72 )
                {
                  v71 = 1;
                  if ( *(_BYTE *)(v73 + v63 + 10) )
                    v67 = (char *)(v73 + v63 + 24);
                  v68 = *(_BYTE *)(v73 + v63 + 8);
                  v69 = *(_BYTE **)(v73 + v63 + 16);
                  v66 = *(_BYTE *)(v73 + v63 + 9);
                }
              }
            }
            else
            {
              LODWORD(v59) = v73 + 40;
              if ( v73 + 40 <= v72 )
              {
                if ( *(_BYTE *)(v73 + v63 + 10) )
                  v67 = (char *)(v73 + v63 + 24);
                v69 = *(_BYTE **)(v73 + v63 + 16);
LABEL_180:
                v66 = *(_BYTE *)(v73 + v63 + 9);
                v68 = *(_BYTE *)(v73 + v63 + 8);
LABEL_181:
                if ( v67 )
                {
                  v75 = *v67;
                  goto LABEL_184;
                }
                goto LABEL_205;
              }
            }
            if ( v71 )
              goto LABEL_181;
          }
        }
        v70 = (unsigned int)(v70 + 1);
        if ( (unsigned int)v70 >= v65 )
          goto LABEL_181;
      }
    }
    v75 = *(_BYTE *)(v63 + 72);
    v69 = *(_BYTE **)(v63 + 32);
    v66 = *(_BYTE *)(v63 + 11);
    v68 = *(_BYTE *)(v63 + 4);
    if ( *(_BYTE *)(v63 + 2) )
      goto LABEL_205;
LABEL_184:
    LOBYTE(v59) = v75 - 8;
    if ( (v59 & 0x5D) != 0 )
    {
LABEL_205:
      IofCompleteRequest((PIRP)a2, 0);
      return 3221225485LL;
    }
    v76 = *(_BYTE *)(v63 + 3);
    if ( v76 == 1 || !v69 || !v66 )
      goto LABEL_201;
    LOBYTE(v63) = 0;
    v77 = 0;
    v78 = 0;
    v59 = (unsigned __int64)&v69[v66];
    v79 = v69 + 8;
    if ( (unsigned __int8)((*v69 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v79 <= v59 )
      {
        v77 = v69[2];
        LOBYTE(v63) = v69[1] & 0xF;
        v78 = v69[3];
        goto LABEL_200;
      }
    }
    else if ( (unsigned __int64)v79 <= v59 )
    {
      v80 = v69 + 13;
      LOBYTE(v63) = v69[2] & 0xF;
      v81 = v66;
      if ( (unsigned int)(unsigned __int8)v69[7] + 8 <= v66 )
        v81 = (unsigned __int8)v69[7] + 8;
      v59 = (unsigned __int64)&v69[v81];
      if ( (unsigned __int64)v80 <= v59 )
        v77 = v69[12];
      if ( (unsigned __int64)(v69 + 14) > v59 )
        v78 = 0;
      else
        v78 = *v80;
LABEL_200:
      if ( v64 )
      {
LABEL_202:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v59,
          v63,
          (unsigned int)&v83,
          a2,
          *(_DWORD *)(a2 + 48),
          v76,
          v68,
          v63,
          v77,
          v78,
          a2);
        goto LABEL_205;
      }
LABEL_201:
      LOBYTE(v63) = 0;
      v77 = 0;
      v78 = 0;
      goto LABEL_202;
    }
    v64 = 0;
    goto LABEL_200;
  }
  if ( (*(_BYTE *)(a1 + 112) & 4) == 0 )
  {
    if ( v4[1] == 1 )
    {
      v34 = NvmeNamespaceDsmDeallocate(a1);
    }
    else if ( v4[1] == 25 )
    {
      v34 = NvmeNamespaceDsmWriteZeroes(a1);
    }
    else
    {
      v34 = -1073741637;
    }
    v8 = StorEtwLoggingEnabled == 0;
    v82 = v34;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = v34;
    if ( v8 )
      goto LABEL_141;
    v83 = 0;
    IoGetActivityIdIrp(a2, &v83);
    v36 = *(_QWORD *)(a2 + 184);
    if ( *(_BYTE *)v36 == 14 )
    {
      if ( (byte_140177432 & 8) == 0 )
        goto LABEL_141;
      v39 = EventNonReadWriteRequestComplete;
      goto LABEL_140;
    }
    if ( *(_BYTE *)v36 != 15 )
    {
      if ( *(_BYTE *)v36 != 27 )
        goto LABEL_141;
      if ( *(_BYTE *)(v36 + 1) == 7 && !*(_DWORD *)(v36 + 8) )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          v37 = *(int **)(a2 + 56);
          if ( v37 )
            v38 = *v37;
          else
            v38 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v38, v36, (unsigned int)&v83, a2, v38, *(_DWORD *)(a2 + 48));
        }
        goto LABEL_141;
      }
      if ( (byte_140177432 & 0x20) == 0 )
        goto LABEL_141;
      v39 = EventPnpRequestComplete;
LABEL_140:
      McTemplateK0pd_EtwWriteTransfer(v35, v39, &v83, a2, *(_DWORD *)(a2 + 48));
      goto LABEL_141;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_141;
    v40 = *(_QWORD *)(v36 + 8);
    v41 = 1;
    if ( *(_BYTE *)(v40 + 2) == 40 )
    {
      if ( *(_DWORD *)(v40 + 20) )
        goto LABEL_141;
      v42 = *(_DWORD *)(v40 + 56);
      if ( !v42 )
        goto LABEL_141;
      v43 = 0;
      v44 = 0;
      v45 = 0;
      v46 = 0;
      v47 = 0;
      v48 = 0;
      while ( 1 )
      {
        v35 = *(unsigned int *)(v40 + 4 * v47 + 120);
        if ( (unsigned int)v35 >= 0x80 )
        {
          v49 = *(unsigned int *)(v40 + 16);
          if ( (unsigned int)v35 < (unsigned int)v49 )
          {
            v50 = (unsigned int)v35;
            v51 = *(_DWORD *)(v35 + v40) - 64;
            if ( v51 )
            {
              LODWORD(v35) = v51 - 1;
              if ( (_DWORD)v35 )
              {
                if ( (_DWORD)v35 == 1 )
                {
                  LODWORD(v35) = v50 + 40;
                  if ( v50 + 40 <= v49 )
                  {
                    if ( *(_DWORD *)(v50 + v40 + 12) )
                      v44 = (char *)(v50 + v40 + 32);
                    v46 = *(_BYTE **)(v50 + v40 + 24);
                    goto LABEL_115;
                  }
                }
              }
              else
              {
                LODWORD(v35) = v50 + 56;
                if ( v50 + 56 <= v49 )
                {
                  v48 = 1;
                  if ( *(_BYTE *)(v50 + v40 + 10) )
                    v44 = (char *)(v50 + v40 + 24);
                  v45 = *(_BYTE *)(v50 + v40 + 8);
                  v46 = *(_BYTE **)(v50 + v40 + 16);
                  v43 = *(_BYTE *)(v50 + v40 + 9);
                }
              }
            }
            else
            {
              LODWORD(v35) = v50 + 40;
              if ( v50 + 40 <= v49 )
              {
                if ( *(_BYTE *)(v50 + v40 + 10) )
                  v44 = (char *)(v50 + v40 + 24);
                v46 = *(_BYTE **)(v50 + v40 + 16);
LABEL_115:
                v43 = *(_BYTE *)(v50 + v40 + 9);
                v45 = *(_BYTE *)(v50 + v40 + 8);
LABEL_116:
                if ( v44 )
                {
                  v52 = *v44;
                  goto LABEL_119;
                }
                goto LABEL_141;
              }
            }
            if ( v48 )
              goto LABEL_116;
          }
        }
        v47 = (unsigned int)(v47 + 1);
        if ( (unsigned int)v47 >= v42 )
          goto LABEL_116;
      }
    }
    v52 = *(_BYTE *)(v40 + 72);
    v46 = *(_BYTE **)(v40 + 32);
    v43 = *(_BYTE *)(v40 + 11);
    v45 = *(_BYTE *)(v40 + 4);
    if ( *(_BYTE *)(v40 + 2) )
      goto LABEL_141;
LABEL_119:
    LOBYTE(v35) = v52 - 8;
    if ( (v35 & 0x5D) != 0 )
    {
LABEL_141:
      IofCompleteRequest((PIRP)a2, 0);
      return v82;
    }
    v53 = *(_BYTE *)(v40 + 3);
    if ( v53 == 1 || !v46 || !v43 )
      goto LABEL_136;
    LOBYTE(v40) = 0;
    v54 = 0;
    v55 = 0;
    v35 = (unsigned __int64)&v46[v43];
    v56 = v46 + 8;
    if ( (unsigned __int8)((*v46 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v56 <= v35 )
      {
        v54 = v46[2];
        LOBYTE(v40) = v46[1] & 0xF;
        v55 = v46[3];
        goto LABEL_135;
      }
    }
    else if ( (unsigned __int64)v56 <= v35 )
    {
      v57 = v46 + 13;
      LOBYTE(v40) = v46[2] & 0xF;
      v58 = v43;
      if ( (unsigned int)(unsigned __int8)v46[7] + 8 <= v43 )
        v58 = (unsigned __int8)v46[7] + 8;
      v35 = (unsigned __int64)&v46[v58];
      if ( (unsigned __int64)v57 <= v35 )
        v54 = v46[12];
      if ( (unsigned __int64)(v46 + 14) > v35 )
        v55 = 0;
      else
        v55 = *v57;
LABEL_135:
      if ( v41 )
      {
LABEL_137:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v35,
          v40,
          (unsigned int)&v83,
          a2,
          *(_DWORD *)(a2 + 48),
          v53,
          v45,
          v40,
          v54,
          v55,
          a2);
        goto LABEL_141;
      }
LABEL_136:
      LOBYTE(v40) = 0;
      v54 = 0;
      v55 = 0;
      goto LABEL_137;
    }
    v41 = 0;
    goto LABEL_135;
  }
  v8 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = -1073741637;
  if ( v8 )
    goto LABEL_71;
  v83 = 0;
  IoGetActivityIdIrp(a2, &v83);
  v10 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v10 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_71;
    v13 = EventNonReadWriteRequestComplete;
    goto LABEL_70;
  }
  if ( *(_BYTE *)v10 != 15 )
  {
    if ( *(_BYTE *)v10 != 27 )
      goto LABEL_71;
    if ( *(_BYTE *)(v10 + 1) == 7 && !*(_DWORD *)(v10 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v11 = *(int **)(a2 + 56);
        if ( v11 )
          v12 = *v11;
        else
          v12 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v12, v10, (unsigned int)&v83, a2, v12, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_71;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_71;
    v13 = EventPnpRequestComplete;
LABEL_70:
    McTemplateK0pd_EtwWriteTransfer(v9, v13, &v83, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_71;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_71;
  v14 = *(_QWORD *)(v10 + 8);
  v15 = 1;
  if ( *(_BYTE *)(v14 + 2) == 40 )
  {
    if ( *(_DWORD *)(v14 + 20) )
      goto LABEL_71;
    v16 = *(_DWORD *)(v14 + 56);
    if ( !v16 )
      goto LABEL_71;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    while ( 1 )
    {
      v9 = *(unsigned int *)(v14 + 4 * v21 + 120);
      if ( (unsigned int)v9 >= 0x80 )
      {
        v23 = *(unsigned int *)(v14 + 16);
        if ( (unsigned int)v9 < (unsigned int)v23 )
        {
          v24 = (unsigned int)v9;
          v25 = *(_DWORD *)(v9 + v14) - 64;
          if ( v25 )
          {
            LODWORD(v9) = v25 - 1;
            if ( (_DWORD)v9 )
            {
              if ( (_DWORD)v9 == 1 )
              {
                LODWORD(v9) = v24 + 40;
                if ( v24 + 40 <= v23 )
                {
                  if ( *(_DWORD *)(v24 + v14 + 12) )
                    v18 = (char *)(v24 + v14 + 32);
                  v20 = *(_BYTE **)(v24 + v14 + 24);
                  goto LABEL_45;
                }
              }
            }
            else
            {
              LODWORD(v9) = v24 + 56;
              if ( v24 + 56 <= v23 )
              {
                v22 = 1;
                if ( *(_BYTE *)(v24 + v14 + 10) )
                  v18 = (char *)(v24 + v14 + 24);
                v19 = *(_BYTE *)(v24 + v14 + 8);
                v20 = *(_BYTE **)(v24 + v14 + 16);
                v17 = *(_BYTE *)(v24 + v14 + 9);
              }
            }
          }
          else
          {
            LODWORD(v9) = v24 + 40;
            if ( v24 + 40 <= v23 )
            {
              if ( *(_BYTE *)(v24 + v14 + 10) )
                v18 = (char *)(v24 + v14 + 24);
              v20 = *(_BYTE **)(v24 + v14 + 16);
LABEL_45:
              v17 = *(_BYTE *)(v24 + v14 + 9);
              v19 = *(_BYTE *)(v24 + v14 + 8);
LABEL_46:
              if ( v18 )
              {
                v26 = *v18;
                goto LABEL_49;
              }
              goto LABEL_71;
            }
          }
          if ( v22 )
            goto LABEL_46;
        }
      }
      v21 = (unsigned int)(v21 + 1);
      if ( (unsigned int)v21 >= v16 )
        goto LABEL_46;
    }
  }
  v26 = *(_BYTE *)(v14 + 72);
  v20 = *(_BYTE **)(v14 + 32);
  v17 = *(_BYTE *)(v14 + 11);
  v19 = *(_BYTE *)(v14 + 4);
  if ( *(_BYTE *)(v14 + 2) )
    goto LABEL_71;
LABEL_49:
  LOBYTE(v9) = v26 - 8;
  if ( (v9 & 0x5D) == 0 )
  {
    v27 = *(_BYTE *)(v14 + 3);
    if ( v27 == 1 || !v20 || !v17 )
      goto LABEL_66;
    LOBYTE(v14) = 0;
    v28 = 0;
    v29 = 0;
    v9 = (unsigned __int64)&v20[v17];
    v30 = v20 + 8;
    if ( (unsigned __int8)((*v20 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v30 <= v9 )
      {
        v28 = v20[2];
        LOBYTE(v14) = v20[1] & 0xF;
        v29 = v20[3];
        goto LABEL_65;
      }
    }
    else if ( (unsigned __int64)v30 <= v9 )
    {
      v31 = v20 + 13;
      LOBYTE(v14) = v20[2] & 0xF;
      v32 = v17;
      if ( (unsigned int)(unsigned __int8)v20[7] + 8 <= v17 )
        v32 = (unsigned __int8)v20[7] + 8;
      v9 = (unsigned __int64)&v20[v32];
      if ( (unsigned __int64)v31 <= v9 )
        v28 = v20[12];
      if ( (unsigned __int64)(v20 + 14) > v9 )
        v29 = 0;
      else
        v29 = *v31;
LABEL_65:
      if ( v15 )
      {
LABEL_67:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v9,
          v14,
          (unsigned int)&v83,
          a2,
          *(_DWORD *)(a2 + 48),
          v27,
          v19,
          v14,
          v28,
          v29,
          a2);
        goto LABEL_71;
      }
LABEL_66:
      LOBYTE(v14) = 0;
      v28 = 0;
      v29 = 0;
      goto LABEL_67;
    }
    v15 = 0;
    goto LABEL_65;
  }
LABEL_71:
  IofCompleteRequest((PIRP)a2, 0);
  return 3221225659LL;
}

```

## disassembly

```asm
0x1401acda4  mov     [rsp-38h+arg_10], rbx
0x1401acda9  push    rbp
0x1401acdaa  push    rsi
0x1401acdab  push    rdi
0x1401acdac  push    r12
0x1401acdae  push    r13
0x1401acdb0  push    r14
0x1401acdb2  push    r15
0x1401acdb4  mov     rbp, rsp
0x1401acdb7  sub     rsp, 80h
0x1401acdbe  mov     rax, cs:__security_cookie
0x1401acdc5  xor     rax, rsp
0x1401acdc8  mov     [rbp+var_8], rax
0x1401acdcc  mov     rbx, rdx
0x1401acdcf  mov     r8, rcx
0x1401acdd2  mov     rdx, [rdx+18h]
0x1401acdd6  test    rdx, rdx
0x1401acdd9  jz      loc_1401AD432
0x1401acddf  mov     rax, [rbx+0B8h]
0x1401acde6  mov     ecx, [rax+10h]
0x1401acde9  cmp     ecx, 1Ch
0x1401acdec  jb      loc_1401AD432
0x1401acdf2  mov     r10d, [rdx+10h]
0x1401acdf6  mov     eax, [rdx+0Ch]
0x1401acdf9  add     rax, r10
0x1401acdfc  cmp     rcx, rax
0x1401acdff  jb      loc_1401AD432
0x1401ace05  mov     r9d, [rdx+18h]
0x1401ace09  mov     eax, [rdx+14h]
0x1401ace0c  add     rax, r9
0x1401ace0f  cmp     rcx, rax
0x1401ace12  jb      loc_1401AD432
0x1401ace18  lea     rax, [r10+1Ch]
0x1401ace1c  add     rax, r9
0x1401ace1f  cmp     rcx, rax
0x1401ace22  jb      loc_1401AD432
0x1401ace28  test    byte ptr [r8+70h], 4
0x1401ace2d  jz      loc_1401AD121
0x1401ace33  cmp     cs:StorEtwLoggingEnabled, 0
0x1401ace3a  mov     byte ptr [rbx+8Dh], 0ACh
0x1401ace41  mov     dword ptr [rbx+30h], 0C00000BBh
0x1401ace48  jz      loc_1401AD106
0x1401ace4e  xorps   xmm0, xmm0
0x1401ace51  lea     rdx, [rbp+var_18]
0x1401ace55  mov     rcx, rbx
0x1401ace58  movups  [rbp+var_18], xmm0
0x1401ace5c  call    cs:__imp_IoGetActivityIdIrp
0x1401ace63  nop     dword ptr [rax+rax+00h]
0x1401ace68  mov     rdx, [rbx+0B8h]
0x1401ace6f  movzx   eax, byte ptr [rdx]
0x1401ace72  sub     eax, 0Eh
0x1401ace75  jz      loc_1401AD0E3
0x1401ace7b  sub     eax, 1
0x1401ace7e  jz      short loc_1401ACEE6
0x1401ace80  cmp     eax, 0Ch
0x1401ace83  jnz     loc_1401AD106
0x1401ace89  cmp     byte ptr [rdx+1], 7
0x1401ace8d  jnz     short loc_1401ACECD
0x1401ace8f  cmp     dword ptr [rdx+8], 0
0x1401ace93  jnz     short loc_1401ACECD
0x1401ace95  test    cs:byte_140177432, 40h
0x1401ace9c  jz      loc_1401AD106
0x1401acea2  mov     rax, [rbx+38h]
0x1401acea6  test    rax, rax
0x1401acea9  jz      short loc_1401ACEAF
0x1401aceab  mov     ecx, [rax]
0x1401acead  jmp     short loc_1401ACEB1
0x1401aceaf  xor     ecx, ecx
0x1401aceb1  mov     eax, [rbx+30h]
0x1401aceb4  lea     r8, [rbp+var_18]
0x1401aceb8  mov     [rsp+80h+var_58], eax
0x1401acebc  mov     r9, rbx
0x1401acebf  mov     [rsp+80h+var_60], ecx
0x1401acec3  call    McTemplateK0pqd_EtwWriteTransfer
0x1401acec8  jmp     loc_1401AD106
0x1401acecd  test    cs:byte_140177432, 20h
0x1401aced4  jz      loc_1401AD106
0x1401aceda  lea     rdx, EventPnpRequestComplete
0x1401acee1  jmp     loc_1401AD0F3
0x1401acee6  cmp     cs:byte_140177431, 0
0x1401aceed  jge     loc_1401AD106
0x1401acef3  mov     rdx, [rdx+8]
0x1401acef7  mov     r9d, 1
0x1401acefd  movzx   eax, byte ptr [rdx+2]
0x1401acf01  cmp     al, 28h ; '('
0x1401acf03  jnz     loc_1401ACFEC
0x1401acf09  cmp     dword ptr [rdx+14h], 0
0x1401acf0d  jnz     loc_1401AD106
0x1401acf13  mov     r15d, [rdx+38h]
0x1401acf17  test    r15d, r15d
0x1401acf1a  jz      loc_1401AD106
0x1401acf20  xor     r11b, r11b
0x1401acf23  xor     edi, edi
0x1401acf25  xor     r12b, r12b
0x1401acf28  xor     r10d, r10d
0x1401acf2b  xor     r14d, r14d
0x1401acf2e  xor     r13b, r13b
0x1401acf31  mov     ecx, [rdx+r14*4+78h]
0x1401acf36  cmp     ecx, 80h
0x1401acf3c  jb      short loc_1401ACFB3
0x1401acf3e  mov     esi, [rdx+10h]
0x1401acf41  cmp     ecx, esi
0x1401acf43  jnb     short loc_1401ACFB3
0x1401acf45  mov     r8d, ecx
0x1401acf48  mov     ecx, [rcx+rdx]
0x1401acf4b  sub     ecx, 40h ; '@'
0x1401acf4e  jz      short loc_1401ACFA5
0x1401acf50  sub     ecx, r9d
0x1401acf53  jz      short loc_1401ACF79
0x1401acf55  cmp     ecx, r9d
0x1401acf58  jnz     short loc_1401ACFAE
0x1401acf5a  lea     rcx, [r8+28h]
0x1401acf5e  cmp     rcx, rsi
0x1401acf61  ja      short loc_1401ACFAE
0x1401acf63  cmp     dword ptr [r8+rdx+0Ch], 0
0x1401acf69  jbe     short loc_1401ACF72
0x1401acf6b  lea     rdi, [rdx+20h]
0x1401acf6f  add     rdi, r8
0x1401acf72  mov     r10, [r8+rdx+18h]
0x1401acf77  jmp     short loc_1401ACFD5
0x1401acf79  lea     rcx, [r8+38h]
0x1401acf7d  cmp     rcx, rsi
0x1401acf80  ja      short loc_1401ACFAE
0x1401acf82  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401acf88  mov     r13b, r9b
0x1401acf8b  jbe     short loc_1401ACF94
0x1401acf8d  lea     rdi, [rdx+18h]
0x1401acf91  add     rdi, r8
0x1401acf94  mov     r12b, [r8+rdx+8]
0x1401acf99  mov     r10, [r8+rdx+10h]
0x1401acf9e  mov     r11b, [r8+rdx+9]
0x1401acfa3  jmp     short loc_1401ACFAE
0x1401acfa5  lea     rcx, [r8+28h]
0x1401acfa9  cmp     rcx, rsi
0x1401acfac  jbe     short loc_1401ACFC1
0x1401acfae  test    r13b, r13b
0x1401acfb1  jnz     short loc_1401ACFDF
0x1401acfb3  add     r14d, r9d
0x1401acfb6  cmp     r14d, r15d
0x1401acfb9  jb      loc_1401ACF31
0x1401acfbf  jmp     short loc_1401ACFDF
0x1401acfc1  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401acfc7  jbe     short loc_1401ACFD0
0x1401acfc9  lea     rdi, [rdx+18h]
0x1401acfcd  add     rdi, r8
0x1401acfd0  mov     r10, [r8+rdx+10h]
0x1401acfd5  mov     r11b, [r8+rdx+9]
0x1401acfda  mov     r12b, [r8+rdx+8]
0x1401acfdf  test    rdi, rdi
0x1401acfe2  jz      loc_1401AD106
0x1401acfe8  mov     cl, [rdi]
0x1401acfea  jmp     short loc_1401AD003
0x1401acfec  mov     cl, [rdx+48h]
0x1401acfef  mov     r10, [rdx+20h]
0x1401acff3  mov     r11b, [rdx+0Bh]
0x1401acff7  mov     r12b, [rdx+4]
0x1401acffb  test    eax, eax
0x1401acffd  jnz     loc_1401AD106
0x1401ad003  sub     cl, 8
0x1401ad006  test    cl, 5Dh
0x1401ad009  jnz     loc_1401AD106
0x1401ad00f  mov     sil, [rdx+3]
0x1401ad013  cmp     sil, r9b
0x1401ad016  jz      loc_1401AD0A9
0x1401ad01c  test    r10, r10
0x1401ad01f  jz      loc_1401AD0A9
0x1401ad025  test    r11b, r11b
0x1401ad028  jz      short loc_1401AD0A9
0x1401ad02a  mov     al, [r10]
0x1401ad02d  xor     dl, dl
0x1401ad02f  and     al, 7Fh
0x1401ad031  movzx   ecx, r11b
0x1401ad035  sub     al, 72h ; 'r'
0x1401ad037  xor     dil, dil
0x1401ad03a  xor     r8b, r8b
0x1401ad03d  add     rcx, r10
0x1401ad040  cmp     al, r9b
0x1401ad043  lea     rax, [r10+8]
0x1401ad047  jbe     short loc_1401AD08B
0x1401ad049  cmp     rax, rcx
0x1401ad04c  ja      short loc_1401AD0A1
0x1401ad04e  movzx   ecx, byte ptr [r10+7]
0x1401ad053  lea     r8, [r10+0Dh]
0x1401ad057  mov     dl, [r10+2]
0x1401ad05b  add     ecx, 8
0x1401ad05e  and     dl, 0Fh
0x1401ad061  movzx   eax, r11b
0x1401ad065  cmp     ecx, eax
0x1401ad067  cmovbe  eax, ecx
0x1401ad06a  mov     ecx, eax
0x1401ad06c  add     rcx, r10
0x1401ad06f  cmp     r8, rcx
0x1401ad072  ja      short loc_1401AD078
0x1401ad074  mov     dil, [r10+0Ch]
0x1401ad078  lea     rax, [r10+0Eh]
0x1401ad07c  cmp     rax, rcx
0x1401ad07f  ja      short loc_1401AD086
0x1401ad081  mov     r8b, [r8]
0x1401ad084  jmp     short loc_1401AD0A4
0x1401ad086  xor     r8b, r8b
0x1401ad089  jmp     short loc_1401AD0A4
0x1401ad08b  cmp     rax, rcx
0x1401ad08e  ja      short loc_1401AD0A1
0x1401ad090  mov     dl, [r10+1]
0x1401ad094  mov     dil, [r10+2]
0x1401ad098  and     dl, 0Fh
0x1401ad09b  mov     r8b, [r10+3]
0x1401ad09f  jmp     short loc_1401AD0A4
0x1401ad0a1  xor     r9b, r9b
0x1401ad0a4  test    r9b, r9b
0x1401ad0a7  jnz     short loc_1401AD0B1
0x1401ad0a9  xor     dl, dl
0x1401ad0ab  xor     dil, dil
0x1401ad0ae  xor     r8b, r8b
0x1401ad0b1  mov     eax, [rbx+30h]
0x1401ad0b4  mov     r9, rbx
0x1401ad0b7  mov     [rsp+80h+var_30], rbx
0x1401ad0bc  mov     [rsp+80h+var_38], r8b
0x1401ad0c1  lea     r8, [rbp+var_18]
0x1401ad0c5  mov     [rsp+80h+var_40], dil
0x1401ad0ca  mov     [rsp+80h+var_48], dl
0x1401ad0ce  mov     [rsp+80h+var_50], r12b
0x1401ad0d3  mov     byte ptr [rsp+80h+var_58], sil
0x1401ad0d8  mov     [rsp+80h+var_60], eax
0x1401ad0dc  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x1401ad0e1  jmp     short loc_1401AD106
0x1401ad0e3  test    cs:byte_140177432, 8
0x1401ad0ea  jz      short loc_1401AD106
0x1401ad0ec  lea     rdx, EventNonReadWriteRequestComplete
0x1401ad0f3  mov     eax, [rbx+30h]
0x1401ad0f6  lea     r8, [rbp+var_18]
0x1401ad0fa  mov     r9, rbx
0x1401ad0fd  mov     [rsp+80h+var_60], eax
0x1401ad101  call    McTemplateK0pd_EtwWriteTransfer
0x1401ad106  xor     edx, edx; PriorityBoost
0x1401ad108  mov     rcx, rbx; Irp
0x1401ad10b  call    cs:__imp_IofCompleteRequest
0x1401ad112  nop     dword ptr [rax+rax+00h]
0x1401ad117  mov     eax, 0C00000BBh
0x1401ad11c  jmp     loc_1401AD722
0x1401ad121  mov     ecx, [rdx+4]
0x1401ad124  sub     ecx, 1
0x1401ad127  jz      short loc_1401AD13F
0x1401ad129  cmp     ecx, 18h
0x1401ad12c  jz      short loc_1401AD135
0x1401ad12e  mov     eax, 0C00000BBh
0x1401ad133  jmp     short loc_1401AD147
0x1401ad135  mov     rcx, r8
0x1401ad138  call    NvmeNamespaceDsmWriteZeroes
0x1401ad13d  jmp     short loc_1401AD147
0x1401ad13f  mov     rcx, r8
0x1401ad142  call    NvmeNamespaceDsmDeallocate
0x1401ad147  cmp     cs:StorEtwLoggingEnabled, 0
0x1401ad14e  mov     [rbp+var_20], eax
0x1401ad151  mov     byte ptr [rbx+8Dh], 0ACh
0x1401ad158  mov     [rbx+30h], eax
0x1401ad15b  jz      loc_1401AD419
0x1401ad161  xorps   xmm0, xmm0
0x1401ad164  lea     rdx, [rbp+var_18]
0x1401ad168  mov     rcx, rbx
0x1401ad16b  movups  [rbp+var_18], xmm0
0x1401ad16f  call    cs:__imp_IoGetActivityIdIrp
0x1401ad176  nop     dword ptr [rax+rax+00h]
0x1401ad17b  mov     rdx, [rbx+0B8h]
0x1401ad182  movzx   eax, byte ptr [rdx]
0x1401ad185  sub     eax, 0Eh
0x1401ad188  jz      loc_1401AD3F6
0x1401ad18e  sub     eax, 1
0x1401ad191  jz      short loc_1401AD1F9
0x1401ad193  cmp     eax, 0Ch
0x1401ad196  jnz     loc_1401AD419
0x1401ad19c  cmp     byte ptr [rdx+1], 7
0x1401ad1a0  jnz     short loc_1401AD1E0
0x1401ad1a2  cmp     dword ptr [rdx+8], 0
0x1401ad1a6  jnz     short loc_1401AD1E0
0x1401ad1a8  test    cs:byte_140177432, 40h
0x1401ad1af  jz      loc_1401AD419
0x1401ad1b5  mov     rax, [rbx+38h]
0x1401ad1b9  test    rax, rax
0x1401ad1bc  jz      short loc_1401AD1C2
0x1401ad1be  mov     ecx, [rax]
0x1401ad1c0  jmp     short loc_1401AD1C4
0x1401ad1c2  xor     ecx, ecx
0x1401ad1c4  mov     eax, [rbx+30h]
0x1401ad1c7  lea     r8, [rbp+var_18]
0x1401ad1cb  mov     [rsp+80h+var_58], eax
0x1401ad1cf  mov     r9, rbx
0x1401ad1d2  mov     [rsp+80h+var_60], ecx
0x1401ad1d6  call    McTemplateK0pqd_EtwWriteTransfer
0x1401ad1db  jmp     loc_1401AD419
0x1401ad1e0  test    cs:byte_140177432, 20h
0x1401ad1e7  jz      loc_1401AD419
0x1401ad1ed  lea     rdx, EventPnpRequestComplete
0x1401ad1f4  jmp     loc_1401AD406
0x1401ad1f9  cmp     cs:byte_140177431, 0
0x1401ad200  jge     loc_1401AD419
0x1401ad206  mov     rdx, [rdx+8]
0x1401ad20a  mov     r9d, 1
0x1401ad210  movzx   eax, byte ptr [rdx+2]
0x1401ad214  cmp     al, 28h ; '('
  ... truncated ...
```
