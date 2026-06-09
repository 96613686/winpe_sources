# NvmeNamespacePowerIrp

- ea: `0x1401237e8`
- end: `0x140124157`
- name: `NvmeNamespacePowerIrp`
- size: `2415`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140097f10`

## callees

- `0x1400421f4`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1401237e8`
- `0x14013dc9c`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140123859`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140123b65`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140123e4a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140123859`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140123b65`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140123e4a`
- `ntoskrnl!IofCompleteRequest` at `0x140123b08`
- `ntoskrnl!IofCompleteRequest` at `0x140123e17`
- `ntoskrnl!IofCompleteRequest` at `0x1401240f9`
- `ntoskrnl!IofCompleteRequest` at `0x140123b08`
- `ntoskrnl!IofCompleteRequest` at `0x140123e17`
- `ntoskrnl!IofCompleteRequest` at `0x1401240f9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140124120`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140124120`

## pseudocode

```c
__int64 __fastcall NvmeNamespacePowerIrp(__int64 a1, __int64 a2)
{
  int v4; // eax
  bool v5; // zf
  unsigned __int64 v6; // rcx
  __int64 v7; // rdx
  int *v8; // rax
  int v9; // ecx
  __int64 *v10; // rdx
  __int64 v11; // rdx
  char v12; // r9
  unsigned int v13; // r12d
  unsigned __int8 v14; // r11
  char *v15; // rdi
  char v16; // r15
  _BYTE *v17; // r10
  __int64 v18; // r14
  char v19; // r13
  unsigned __int64 v20; // rsi
  __int64 v21; // r8
  int v22; // ecx
  char v23; // cl
  char v24; // si
  char v25; // di
  char v26; // r8
  _BYTE *v27; // rax
  char *v28; // r8
  unsigned int v29; // eax
  int v31; // ecx
  unsigned int v32; // r13d
  unsigned __int64 v33; // rcx
  __int64 v34; // rdx
  int *v35; // rax
  int v36; // ecx
  __int64 *v37; // rdx
  __int64 v38; // rdx
  char v39; // r9
  unsigned int v40; // r15d
  char *v41; // rdi
  unsigned __int8 v42; // r11
  char v43; // r12
  _BYTE *v44; // r10
  __int64 v45; // r14
  unsigned __int64 v46; // rsi
  __int64 v47; // r8
  int v48; // ecx
  char v49; // cl
  char v50; // si
  char v51; // di
  char v52; // r8
  _BYTE *v53; // rax
  char *v54; // r8
  unsigned int v55; // eax
  unsigned __int64 v56; // rcx
  __int64 v57; // rdx
  int *v58; // rax
  int v59; // ecx
  __int64 *v60; // rdx
  __int64 v61; // rdx
  char v62; // r9
  unsigned int v63; // r12d
  unsigned __int8 v64; // r11
  char *v65; // rdi
  char v66; // r15
  _BYTE *v67; // r10
  __int64 v68; // r14
  char v69; // r13
  unsigned __int64 v70; // rsi
  __int64 v71; // r8
  int v72; // ecx
  char v73; // cl
  char v74; // si
  char v75; // di
  char v76; // r8
  _BYTE *v77; // rax
  char *v78; // r8
  unsigned int v79; // eax
  char v80; // [rsp+60h] [rbp-9h]
  unsigned int v81; // [rsp+64h] [rbp-5h]
  __int128 v82; // [rsp+68h] [rbp-1h] BYREF
  __int128 v83; // [rsp+78h] [rbp+Fh] BYREF

  *(_QWORD *)&v83 = a1;
  v4 = NvmeNamespaceAcquireRemoveLock();
  v81 = v4;
  if ( v4 >= 0 )
  {
    v31 = *(unsigned __int8 *)(*(_QWORD *)(a2 + 184) + 1LL) - 2;
    if ( *(_BYTE *)(*(_QWORD *)(a2 + 184) + 1LL) == 2 )
    {
      v32 = NvmeNamespaceSetPowerIrp(a1, a2);
      goto LABEL_200;
    }
    *(_BYTE *)(a2 + 141) = -84;
    if ( v31 != 1 )
    {
      v5 = StorEtwLoggingEnabled == 0;
      v32 = -1073741637;
      *(_DWORD *)(a2 + 48) = -1073741637;
      if ( v5 )
        goto LABEL_133;
      v82 = 0;
      IoGetActivityIdIrp(a2, &v82);
      v34 = *(_QWORD *)(a2 + 184);
      if ( *(_BYTE *)v34 == 14 )
      {
        if ( (byte_140177432 & 8) == 0 )
          goto LABEL_133;
        v37 = EventNonReadWriteRequestComplete;
        goto LABEL_132;
      }
      if ( *(_BYTE *)v34 != 15 )
      {
        if ( *(_BYTE *)v34 != 27 )
          goto LABEL_133;
        if ( *(_BYTE *)(v34 + 1) == 7 && !*(_DWORD *)(v34 + 8) )
        {
          if ( (byte_140177432 & 0x40) != 0 )
          {
            v35 = *(int **)(a2 + 56);
            if ( v35 )
              v36 = *v35;
            else
              v36 = 0;
            McTemplateK0pqd_EtwWriteTransfer(v36, v34, (unsigned int)&v82, a2, v36, *(_DWORD *)(a2 + 48));
          }
          goto LABEL_133;
        }
        if ( (byte_140177432 & 0x20) == 0 )
          goto LABEL_133;
        v37 = EventPnpRequestComplete;
LABEL_132:
        McTemplateK0pd_EtwWriteTransfer(v33, v37, &v82, a2, *(_DWORD *)(a2 + 48));
        goto LABEL_133;
      }
      if ( byte_140177431 >= 0 )
        goto LABEL_133;
      v38 = *(_QWORD *)(v34 + 8);
      v39 = 1;
      if ( *(_BYTE *)(v38 + 2) == 40 )
      {
        if ( *(_DWORD *)(v38 + 20) )
          goto LABEL_133;
        v40 = *(_DWORD *)(v38 + 56);
        if ( !v40 )
          goto LABEL_133;
        v41 = 0;
        v42 = 0;
        v43 = 0;
        v80 = 0;
        v44 = 0;
        v45 = 0;
        while ( 1 )
        {
          v33 = *(unsigned int *)(v38 + 4 * v45 + 120);
          if ( (unsigned int)v33 >= 0x80 )
          {
            v46 = *(unsigned int *)(v38 + 16);
            if ( (unsigned int)v33 < (unsigned int)v46 )
            {
              v47 = (unsigned int)v33;
              v48 = *(_DWORD *)(v33 + v38) - 64;
              if ( v48 )
              {
                LODWORD(v33) = v48 - 1;
                if ( (_DWORD)v33 )
                {
                  if ( (_DWORD)v33 == 1 )
                  {
                    LODWORD(v33) = v47 + 40;
                    if ( v47 + 40 <= v46 )
                    {
                      if ( *(_DWORD *)(v47 + v38 + 12) )
                        v41 = (char *)(v47 + v38 + 32);
                      v44 = *(_BYTE **)(v47 + v38 + 24);
                      goto LABEL_107;
                    }
                  }
                }
                else
                {
                  LODWORD(v33) = v47 + 56;
                  if ( v47 + 56 <= v46 )
                  {
                    v80 = 1;
                    if ( *(_BYTE *)(v47 + v38 + 10) )
                      v41 = (char *)(v47 + v38 + 24);
                    v43 = *(_BYTE *)(v47 + v38 + 8);
                    v44 = *(_BYTE **)(v47 + v38 + 16);
                    v42 = *(_BYTE *)(v47 + v38 + 9);
                  }
                }
              }
              else
              {
                LODWORD(v33) = v47 + 40;
                if ( v47 + 40 <= v46 )
                {
                  if ( *(_BYTE *)(v47 + v38 + 10) )
                    v41 = (char *)(v47 + v38 + 24);
                  v44 = *(_BYTE **)(v47 + v38 + 16);
LABEL_107:
                  v42 = *(_BYTE *)(v47 + v38 + 9);
                  v43 = *(_BYTE *)(v47 + v38 + 8);
LABEL_108:
                  if ( v41 )
                  {
                    v49 = *v41;
                    goto LABEL_111;
                  }
                  goto LABEL_133;
                }
              }
              if ( v80 )
                goto LABEL_108;
            }
          }
          v45 = (unsigned int)(v45 + 1);
          if ( (unsigned int)v45 >= v40 )
            goto LABEL_108;
        }
      }
      v49 = *(_BYTE *)(v38 + 72);
      v44 = *(_BYTE **)(v38 + 32);
      v42 = *(_BYTE *)(v38 + 11);
      v43 = *(_BYTE *)(v38 + 4);
      if ( *(_BYTE *)(v38 + 2) )
        goto LABEL_133;
LABEL_111:
      LOBYTE(v33) = v49 - 8;
      if ( (v33 & 0x5D) == 0 )
      {
        v50 = *(_BYTE *)(v38 + 3);
        if ( v50 == 1 || !v44 || !v42 )
          goto LABEL_128;
        LOBYTE(v38) = 0;
        v51 = 0;
        v52 = 0;
        v33 = (unsigned __int64)&v44[v42];
        v53 = v44 + 8;
        if ( (unsigned __int8)((*v44 & 0x7F) - 114) <= 1u )
        {
          if ( (unsigned __int64)v53 <= v33 )
          {
            v51 = v44[2];
            LOBYTE(v38) = v44[1] & 0xF;
            v52 = v44[3];
            goto LABEL_127;
          }
        }
        else if ( (unsigned __int64)v53 <= v33 )
        {
          v54 = v44 + 13;
          LOBYTE(v38) = v44[2] & 0xF;
          v55 = v42;
          if ( (unsigned int)(unsigned __int8)v44[7] + 8 <= v42 )
            v55 = (unsigned __int8)v44[7] + 8;
          v33 = (unsigned __int64)&v44[v55];
          if ( (unsigned __int64)v54 <= v33 )
            v51 = v44[12];
          if ( (unsigned __int64)(v44 + 14) > v33 )
            v52 = 0;
          else
            v52 = *v54;
LABEL_127:
          if ( v39 )
          {
LABEL_129:
            McTemplateK0pduuuuup_EtwWriteTransfer(
              v33,
              v38,
              (unsigned int)&v82,
              a2,
              *(_DWORD *)(a2 + 48),
              v50,
              v43,
              v38,
              v51,
              v52,
              a2);
            goto LABEL_133;
          }
LABEL_128:
          LOBYTE(v38) = 0;
          v51 = 0;
          v52 = 0;
          goto LABEL_129;
        }
        v39 = 0;
        goto LABEL_127;
      }
LABEL_133:
      IofCompleteRequest((PIRP)a2, 0);
LABEL_200:
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v83 + 120));
      return v32;
    }
    v5 = StorEtwLoggingEnabled == 0;
    *(_DWORD *)(a2 + 48) = 0;
    if ( v5 )
      goto LABEL_198;
    v82 = 0;
    IoGetActivityIdIrp(a2, &v82);
    v57 = *(_QWORD *)(a2 + 184);
    if ( *(_BYTE *)v57 == 14 )
    {
      if ( (byte_140177432 & 8) == 0 )
        goto LABEL_198;
      v60 = EventNonReadWriteRequestComplete;
      goto LABEL_197;
    }
    if ( *(_BYTE *)v57 != 15 )
    {
      if ( *(_BYTE *)v57 != 27 )
        goto LABEL_198;
      if ( *(_BYTE *)(v57 + 1) == 7 && !*(_DWORD *)(v57 + 8) )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          v58 = *(int **)(a2 + 56);
          if ( v58 )
            v59 = *v58;
          else
            v59 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v59, v57, (unsigned int)&v82, a2, v59, *(_DWORD *)(a2 + 48));
        }
        goto LABEL_198;
      }
      if ( (byte_140177432 & 0x20) == 0 )
        goto LABEL_198;
      v60 = EventPnpRequestComplete;
LABEL_197:
      McTemplateK0pd_EtwWriteTransfer(v56, v60, &v82, a2, *(_DWORD *)(a2 + 48));
      goto LABEL_198;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_198;
    v61 = *(_QWORD *)(v57 + 8);
    v62 = 1;
    if ( *(_BYTE *)(v61 + 2) == 40 )
    {
      if ( *(_DWORD *)(v61 + 20) )
        goto LABEL_198;
      v63 = *(_DWORD *)(v61 + 56);
      if ( !v63 )
        goto LABEL_198;
      v64 = 0;
      v65 = 0;
      v66 = 0;
      v67 = 0;
      v68 = 0;
      v69 = 0;
      while ( 1 )
      {
        v56 = *(unsigned int *)(v61 + 4 * v68 + 120);
        if ( (unsigned int)v56 >= 0x80 )
        {
          v70 = *(unsigned int *)(v61 + 16);
          if ( (unsigned int)v56 < (unsigned int)v70 )
          {
            v71 = (unsigned int)v56;
            v72 = *(_DWORD *)(v56 + v61) - 64;
            if ( v72 )
            {
              LODWORD(v56) = v72 - 1;
              if ( (_DWORD)v56 )
              {
                if ( (_DWORD)v56 == 1 )
                {
                  LODWORD(v56) = v71 + 40;
                  if ( v71 + 40 <= v70 )
                  {
                    if ( *(_DWORD *)(v71 + v61 + 12) )
                      v65 = (char *)(v71 + v61 + 32);
                    v67 = *(_BYTE **)(v71 + v61 + 24);
                    goto LABEL_172;
                  }
                }
              }
              else
              {
                LODWORD(v56) = v71 + 56;
                if ( v71 + 56 <= v70 )
                {
                  v69 = 1;
                  if ( *(_BYTE *)(v71 + v61 + 10) )
                    v65 = (char *)(v71 + v61 + 24);
                  v66 = *(_BYTE *)(v71 + v61 + 8);
                  v67 = *(_BYTE **)(v71 + v61 + 16);
                  v64 = *(_BYTE *)(v71 + v61 + 9);
                }
              }
            }
            else
            {
              LODWORD(v56) = v71 + 40;
              if ( v71 + 40 <= v70 )
              {
                if ( *(_BYTE *)(v71 + v61 + 10) )
                  v65 = (char *)(v71 + v61 + 24);
                v67 = *(_BYTE **)(v71 + v61 + 16);
LABEL_172:
                v64 = *(_BYTE *)(v71 + v61 + 9);
                v66 = *(_BYTE *)(v71 + v61 + 8);
LABEL_173:
                if ( v65 )
                {
                  v73 = *v65;
                  goto LABEL_176;
                }
                goto LABEL_198;
              }
            }
            if ( v69 )
              goto LABEL_173;
          }
        }
        v68 = (unsigned int)(v68 + 1);
        if ( (unsigned int)v68 >= v63 )
          goto LABEL_173;
      }
    }
    v73 = *(_BYTE *)(v61 + 72);
    v67 = *(_BYTE **)(v61 + 32);
    v64 = *(_BYTE *)(v61 + 11);
    v66 = *(_BYTE *)(v61 + 4);
    if ( *(_BYTE *)(v61 + 2) )
      goto LABEL_198;
LABEL_176:
    LOBYTE(v56) = v73 - 8;
    if ( (v56 & 0x5D) != 0 )
    {
LABEL_198:
      IofCompleteRequest((PIRP)a2, 0);
      v32 = 0;
      goto LABEL_200;
    }
    v74 = *(_BYTE *)(v61 + 3);
    if ( v74 == 1 || !v67 || !v64 )
      goto LABEL_193;
    LOBYTE(v61) = 0;
    v75 = 0;
    v76 = 0;
    v56 = (unsigned __int64)&v67[v64];
    v77 = v67 + 8;
    if ( (unsigned __int8)((*v67 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v77 <= v56 )
      {
        v75 = v67[2];
        LOBYTE(v61) = v67[1] & 0xF;
        v76 = v67[3];
        goto LABEL_192;
      }
    }
    else if ( (unsigned __int64)v77 <= v56 )
    {
      v78 = v67 + 13;
      LOBYTE(v61) = v67[2] & 0xF;
      v79 = v64;
      if ( (unsigned int)(unsigned __int8)v67[7] + 8 <= v64 )
        v79 = (unsigned __int8)v67[7] + 8;
      v56 = (unsigned __int64)&v67[v79];
      if ( (unsigned __int64)v78 <= v56 )
        v75 = v67[12];
      if ( (unsigned __int64)(v67 + 14) > v56 )
        v76 = 0;
      else
        v76 = *v78;
LABEL_192:
      if ( v62 )
      {
LABEL_194:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v56,
          v61,
          (unsigned int)&v82,
          a2,
          *(_DWORD *)(a2 + 48),
          v74,
          v66,
          v61,
          v75,
          v76,
          a2);
        goto LABEL_198;
      }
LABEL_193:
      LOBYTE(v61) = 0;
      v75 = 0;
      v76 = 0;
      goto LABEL_194;
    }
    v62 = 0;
    goto LABEL_192;
  }
  v5 = StorEtwLoggingEnabled == 0;
  *(_QWORD *)(a2 + 56) = 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = v4;
  if ( v5 )
    goto LABEL_66;
  v83 = 0;
  IoGetActivityIdIrp(a2, &v83);
  v7 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v7 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_66;
    v10 = EventNonReadWriteRequestComplete;
    goto LABEL_65;
  }
  if ( *(_BYTE *)v7 != 15 )
  {
    if ( *(_BYTE *)v7 != 27 )
      goto LABEL_66;
    if ( *(_BYTE *)(v7 + 1) == 7 && !*(_DWORD *)(v7 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v8 = *(int **)(a2 + 56);
        if ( v8 )
          v9 = *v8;
        else
          v9 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v9, v7, (unsigned int)&v83, a2, v9, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_66;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_66;
    v10 = EventPnpRequestComplete;
LABEL_65:
    McTemplateK0pd_EtwWriteTransfer(v6, v10, &v83, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_66;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_66;
  v11 = *(_QWORD *)(v7 + 8);
  v12 = 1;
  if ( *(_BYTE *)(v11 + 2) == 40 )
  {
    if ( *(_DWORD *)(v11 + 20) )
      goto LABEL_66;
    v13 = *(_DWORD *)(v11 + 56);
    if ( !v13 )
      goto LABEL_66;
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    while ( 1 )
    {
      v6 = *(unsigned int *)(v11 + 4 * v18 + 120);
      if ( (unsigned int)v6 >= 0x80 )
      {
        v20 = *(unsigned int *)(v11 + 16);
        if ( (unsigned int)v6 < (unsigned int)v20 )
        {
          v21 = (unsigned int)v6;
          v22 = *(_DWORD *)(v6 + v11) - 64;
          if ( v22 )
          {
            LODWORD(v6) = v22 - 1;
            if ( (_DWORD)v6 )
            {
              if ( (_DWORD)v6 == 1 )
              {
                LODWORD(v6) = v21 + 40;
                if ( v21 + 40 <= v20 )
                {
                  if ( *(_DWORD *)(v21 + v11 + 12) )
                    v15 = (char *)(v21 + v11 + 32);
                  v17 = *(_BYTE **)(v21 + v11 + 24);
                  goto LABEL_40;
                }
              }
            }
            else
            {
              LODWORD(v6) = v21 + 56;
              if ( v21 + 56 <= v20 )
              {
                v19 = 1;
                if ( *(_BYTE *)(v21 + v11 + 10) )
                  v15 = (char *)(v21 + v11 + 24);
                v16 = *(_BYTE *)(v21 + v11 + 8);
                v17 = *(_BYTE **)(v21 + v11 + 16);
                v14 = *(_BYTE *)(v21 + v11 + 9);
              }
            }
          }
          else
          {
            LODWORD(v6) = v21 + 40;
            if ( v21 + 40 <= v20 )
            {
              if ( *(_BYTE *)(v21 + v11 + 10) )
                v15 = (char *)(v21 + v11 + 24);
              v17 = *(_BYTE **)(v21 + v11 + 16);
LABEL_40:
              v14 = *(_BYTE *)(v21 + v11 + 9);
              v16 = *(_BYTE *)(v21 + v11 + 8);
LABEL_41:
              if ( v15 )
              {
                v23 = *v15;
                goto LABEL_44;
              }
              goto LABEL_66;
            }
          }
          if ( v19 )
            goto LABEL_41;
        }
      }
      v18 = (unsigned int)(v18 + 1);
      if ( (unsigned int)v18 >= v13 )
        goto LABEL_41;
    }
  }
  v23 = *(_BYTE *)(v11 + 72);
  v17 = *(_BYTE **)(v11 + 32);
  v14 = *(_BYTE *)(v11 + 11);
  v16 = *(_BYTE *)(v11 + 4);
  if ( *(_BYTE *)(v11 + 2) )
    goto LABEL_66;
LABEL_44:
  LOBYTE(v6) = v23 - 8;
  if ( (v6 & 0x5D) == 0 )
  {
    v24 = *(_BYTE *)(v11 + 3);
    if ( v24 == 1 || !v17 || !v14 )
      goto LABEL_61;
    LOBYTE(v11) = 0;
    v25 = 0;
    v26 = 0;
    v6 = (unsigned __int64)&v17[v14];
    v27 = v17 + 8;
    if ( (unsigned __int8)((*v17 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v27 <= v6 )
      {
        v25 = v17[2];
        LOBYTE(v11) = v17[1] & 0xF;
        v26 = v17[3];
        goto LABEL_60;
      }
    }
    else if ( (unsigned __int64)v27 <= v6 )
    {
      v28 = v17 + 13;
      LOBYTE(v11) = v17[2] & 0xF;
      v29 = v14;
      if ( (unsigned int)(unsigned __int8)v17[7] + 8 <= v14 )
        v29 = (unsigned __int8)v17[7] + 8;
      v6 = (unsigned __int64)&v17[v29];
      if ( (unsigned __int64)v28 <= v6 )
        v25 = v17[12];
      if ( (unsigned __int64)(v17 + 14) > v6 )
        v26 = 0;
      else
        v26 = *v28;
LABEL_60:
      if ( v12 )
      {
LABEL_62:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v6,
          v11,
          (unsigned int)&v83,
          a2,
          *(_DWORD *)(a2 + 48),
          v24,
          v16,
          v11,
          v25,
          v26,
          a2);
        goto LABEL_66;
      }
LABEL_61:
      LOBYTE(v11) = 0;
      v25 = 0;
      v26 = 0;
      goto LABEL_62;
    }
    v12 = 0;
    goto LABEL_60;
  }
LABEL_66:
  IofCompleteRequest((PIRP)a2, 0);
  return v81;
}

```

## disassembly

```asm
0x1401237e8  mov     [rsp-8+arg_10], rbx
0x1401237ed  push    rbp
0x1401237ee  push    rsi
0x1401237ef  push    rdi
0x1401237f0  push    r12
0x1401237f2  push    r13
0x1401237f4  push    r14
0x1401237f6  push    r15
0x1401237f8  lea     rbp, [rsp-27h]
0x1401237fd  sub     rsp, 90h
0x140123804  mov     rax, cs:__security_cookie
0x14012380b  xor     rax, rsp
0x14012380e  mov     [rbp+57h+var_38], rax
0x140123812  mov     rbx, rdx
0x140123815  mov     qword ptr [rbp+57h+var_48], rcx
0x140123819  mov     r15, rcx
0x14012381c  call    NvmeNamespaceAcquireRemoveLock
0x140123821  mov     [rbp+57h+var_5C], eax
0x140123824  test    eax, eax
0x140123826  jns     loc_140123B1C
0x14012382c  cmp     cs:StorEtwLoggingEnabled, 0
0x140123833  mov     qword ptr [rbx+38h], 0
0x14012383b  mov     byte ptr [rbx+8Dh], 0ACh
0x140123842  mov     [rbx+30h], eax
0x140123845  jz      loc_140123B03
0x14012384b  xorps   xmm0, xmm0
0x14012384e  lea     rdx, [rbp+57h+var_48]
0x140123852  mov     rcx, rbx
0x140123855  movups  [rbp+57h+var_48], xmm0
0x140123859  call    cs:__imp_IoGetActivityIdIrp
0x140123860  nop     dword ptr [rax+rax+00h]
0x140123865  mov     rdx, [rbx+0B8h]
0x14012386c  movzx   eax, byte ptr [rdx]
0x14012386f  sub     eax, 0Eh
0x140123872  jz      loc_140123AE0
0x140123878  sub     eax, 1
0x14012387b  jz      short loc_1401238E3
0x14012387d  cmp     eax, 0Ch
0x140123880  jnz     loc_140123B03
0x140123886  cmp     byte ptr [rdx+1], 7
0x14012388a  jnz     short loc_1401238CA
0x14012388c  cmp     dword ptr [rdx+8], 0
0x140123890  jnz     short loc_1401238CA
0x140123892  test    cs:byte_140177432, 40h
0x140123899  jz      loc_140123B03
0x14012389f  mov     rax, [rbx+38h]
0x1401238a3  test    rax, rax
0x1401238a6  jz      short loc_1401238AC
0x1401238a8  mov     ecx, [rax]
0x1401238aa  jmp     short loc_1401238AE
0x1401238ac  xor     ecx, ecx
0x1401238ae  mov     eax, [rbx+30h]
0x1401238b1  lea     r8, [rbp+57h+var_48]
0x1401238b5  mov     [rsp+0C0h+var_98], eax
0x1401238b9  mov     r9, rbx
0x1401238bc  mov     [rsp+0C0h+var_A0], ecx
0x1401238c0  call    McTemplateK0pqd_EtwWriteTransfer
0x1401238c5  jmp     loc_140123B03
0x1401238ca  test    cs:byte_140177432, 20h
0x1401238d1  jz      loc_140123B03
0x1401238d7  lea     rdx, EventPnpRequestComplete
0x1401238de  jmp     loc_140123AF0
0x1401238e3  cmp     cs:byte_140177431, 0
0x1401238ea  jge     loc_140123B03
0x1401238f0  mov     rdx, [rdx+8]
0x1401238f4  mov     r9d, 1
0x1401238fa  movzx   eax, byte ptr [rdx+2]
0x1401238fe  cmp     al, 28h ; '('
0x140123900  jnz     loc_1401239E9
0x140123906  cmp     dword ptr [rdx+14h], 0
0x14012390a  jnz     loc_140123B03
0x140123910  mov     r12d, [rdx+38h]
0x140123914  test    r12d, r12d
0x140123917  jz      loc_140123B03
0x14012391d  xor     r11b, r11b
0x140123920  xor     edi, edi
0x140123922  xor     r15b, r15b
0x140123925  xor     r10d, r10d
0x140123928  xor     r14d, r14d
0x14012392b  xor     r13b, r13b
0x14012392e  mov     ecx, [rdx+r14*4+78h]
0x140123933  cmp     ecx, 80h
0x140123939  jb      short loc_1401239B0
0x14012393b  mov     esi, [rdx+10h]
0x14012393e  cmp     ecx, esi
0x140123940  jnb     short loc_1401239B0
0x140123942  mov     r8d, ecx
0x140123945  mov     ecx, [rcx+rdx]
0x140123948  sub     ecx, 40h ; '@'
0x14012394b  jz      short loc_1401239A2
0x14012394d  sub     ecx, r9d
0x140123950  jz      short loc_140123976
0x140123952  cmp     ecx, r9d
0x140123955  jnz     short loc_1401239AB
0x140123957  lea     rcx, [r8+28h]
0x14012395b  cmp     rcx, rsi
0x14012395e  ja      short loc_1401239AB
0x140123960  cmp     dword ptr [r8+rdx+0Ch], 0
0x140123966  jbe     short loc_14012396F
0x140123968  lea     rdi, [rdx+20h]
0x14012396c  add     rdi, r8
0x14012396f  mov     r10, [r8+rdx+18h]
0x140123974  jmp     short loc_1401239D2
0x140123976  lea     rcx, [r8+38h]
0x14012397a  cmp     rcx, rsi
0x14012397d  ja      short loc_1401239AB
0x14012397f  cmp     byte ptr [r8+rdx+0Ah], 0
0x140123985  mov     r13b, r9b
0x140123988  jbe     short loc_140123991
0x14012398a  lea     rdi, [rdx+18h]
0x14012398e  add     rdi, r8
0x140123991  mov     r15b, [r8+rdx+8]
0x140123996  mov     r10, [r8+rdx+10h]
0x14012399b  mov     r11b, [r8+rdx+9]
0x1401239a0  jmp     short loc_1401239AB
0x1401239a2  lea     rcx, [r8+28h]
0x1401239a6  cmp     rcx, rsi
0x1401239a9  jbe     short loc_1401239BE
0x1401239ab  test    r13b, r13b
0x1401239ae  jnz     short loc_1401239DC
0x1401239b0  add     r14d, r9d
0x1401239b3  cmp     r14d, r12d
0x1401239b6  jb      loc_14012392E
0x1401239bc  jmp     short loc_1401239DC
0x1401239be  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401239c4  jbe     short loc_1401239CD
0x1401239c6  lea     rdi, [rdx+18h]
0x1401239ca  add     rdi, r8
0x1401239cd  mov     r10, [r8+rdx+10h]
0x1401239d2  mov     r11b, [r8+rdx+9]
0x1401239d7  mov     r15b, [r8+rdx+8]
0x1401239dc  test    rdi, rdi
0x1401239df  jz      loc_140123B03
0x1401239e5  mov     cl, [rdi]
0x1401239e7  jmp     short loc_140123A00
0x1401239e9  mov     cl, [rdx+48h]
0x1401239ec  mov     r10, [rdx+20h]
0x1401239f0  mov     r11b, [rdx+0Bh]
0x1401239f4  mov     r15b, [rdx+4]
0x1401239f8  test    eax, eax
0x1401239fa  jnz     loc_140123B03
0x140123a00  sub     cl, 8
0x140123a03  test    cl, 5Dh
0x140123a06  jnz     loc_140123B03
0x140123a0c  mov     sil, [rdx+3]
0x140123a10  cmp     sil, r9b
0x140123a13  jz      loc_140123AA6
0x140123a19  test    r10, r10
0x140123a1c  jz      loc_140123AA6
0x140123a22  test    r11b, r11b
0x140123a25  jz      short loc_140123AA6
0x140123a27  mov     al, [r10]
0x140123a2a  xor     dl, dl
0x140123a2c  and     al, 7Fh
0x140123a2e  movzx   ecx, r11b
0x140123a32  sub     al, 72h ; 'r'
0x140123a34  xor     dil, dil
0x140123a37  xor     r8b, r8b
0x140123a3a  add     rcx, r10
0x140123a3d  cmp     al, r9b
0x140123a40  lea     rax, [r10+8]
0x140123a44  jbe     short loc_140123A88
0x140123a46  cmp     rax, rcx
0x140123a49  ja      short loc_140123A9E
0x140123a4b  movzx   ecx, byte ptr [r10+7]
0x140123a50  lea     r8, [r10+0Dh]
0x140123a54  mov     dl, [r10+2]
0x140123a58  add     ecx, 8
0x140123a5b  and     dl, 0Fh
0x140123a5e  movzx   eax, r11b
0x140123a62  cmp     ecx, eax
0x140123a64  cmovbe  eax, ecx
0x140123a67  mov     ecx, eax
0x140123a69  add     rcx, r10
0x140123a6c  cmp     r8, rcx
0x140123a6f  ja      short loc_140123A75
0x140123a71  mov     dil, [r10+0Ch]
0x140123a75  lea     rax, [r10+0Eh]
0x140123a79  cmp     rax, rcx
0x140123a7c  ja      short loc_140123A83
0x140123a7e  mov     r8b, [r8]
0x140123a81  jmp     short loc_140123AA1
0x140123a83  xor     r8b, r8b
0x140123a86  jmp     short loc_140123AA1
0x140123a88  cmp     rax, rcx
0x140123a8b  ja      short loc_140123A9E
0x140123a8d  mov     dl, [r10+1]
0x140123a91  mov     dil, [r10+2]
0x140123a95  and     dl, 0Fh
0x140123a98  mov     r8b, [r10+3]
0x140123a9c  jmp     short loc_140123AA1
0x140123a9e  xor     r9b, r9b
0x140123aa1  test    r9b, r9b
0x140123aa4  jnz     short loc_140123AAE
0x140123aa6  xor     dl, dl
0x140123aa8  xor     dil, dil
0x140123aab  xor     r8b, r8b
0x140123aae  mov     eax, [rbx+30h]
0x140123ab1  mov     r9, rbx
0x140123ab4  mov     [rsp+0C0h+var_70], rbx
0x140123ab9  mov     [rsp+0C0h+var_78], r8b
0x140123abe  lea     r8, [rbp+57h+var_48]
0x140123ac2  mov     [rsp+0C0h+var_80], dil
0x140123ac7  mov     [rsp+0C0h+var_88], dl
0x140123acb  mov     [rsp+0C0h+var_90], r15b
0x140123ad0  mov     byte ptr [rsp+0C0h+var_98], sil
0x140123ad5  mov     [rsp+0C0h+var_A0], eax
0x140123ad9  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x140123ade  jmp     short loc_140123B03
0x140123ae0  test    cs:byte_140177432, 8
0x140123ae7  jz      short loc_140123B03
0x140123ae9  lea     rdx, EventNonReadWriteRequestComplete
0x140123af0  mov     eax, [rbx+30h]
0x140123af3  lea     r8, [rbp+57h+var_48]
0x140123af7  mov     r9, rbx
0x140123afa  mov     [rsp+0C0h+var_A0], eax
0x140123afe  call    McTemplateK0pd_EtwWriteTransfer
0x140123b03  xor     edx, edx; PriorityBoost
0x140123b05  mov     rcx, rbx; Irp
0x140123b08  call    cs:__imp_IofCompleteRequest
0x140123b0f  nop     dword ptr [rax+rax+00h]
0x140123b14  mov     eax, [rbp+57h+var_5C]
0x140123b17  jmp     loc_14012412F
0x140123b1c  mov     rax, [rbx+0B8h]
0x140123b23  movzx   ecx, byte ptr [rax+1]
0x140123b27  sub     ecx, 2
0x140123b2a  jz      loc_14012410A
0x140123b30  mov     byte ptr [rbx+8Dh], 0ACh
0x140123b37  cmp     ecx, 1
0x140123b3a  jz      loc_140123E28
0x140123b40  cmp     cs:StorEtwLoggingEnabled, 0
0x140123b47  mov     r13d, 0C00000BBh
0x140123b4d  mov     [rbx+30h], r13d
0x140123b51  jz      loc_140123E12
0x140123b57  xorps   xmm0, xmm0
0x140123b5a  lea     rdx, [rbp+57h+var_58]
0x140123b5e  mov     rcx, rbx
0x140123b61  movups  [rbp+57h+var_58], xmm0
0x140123b65  call    cs:__imp_IoGetActivityIdIrp
0x140123b6c  nop     dword ptr [rax+rax+00h]
0x140123b71  mov     rdx, [rbx+0B8h]
0x140123b78  movzx   eax, byte ptr [rdx]
0x140123b7b  sub     eax, 0Eh
0x140123b7e  jz      loc_140123DEF
0x140123b84  sub     eax, 1
0x140123b87  jz      short loc_140123BEF
0x140123b89  cmp     eax, 0Ch
0x140123b8c  jnz     loc_140123E12
0x140123b92  cmp     byte ptr [rdx+1], 7
0x140123b96  jnz     short loc_140123BD6
0x140123b98  cmp     dword ptr [rdx+8], 0
0x140123b9c  jnz     short loc_140123BD6
0x140123b9e  test    cs:byte_140177432, 40h
0x140123ba5  jz      loc_140123E12
0x140123bab  mov     rax, [rbx+38h]
0x140123baf  test    rax, rax
0x140123bb2  jz      short loc_140123BB8
0x140123bb4  mov     ecx, [rax]
0x140123bb6  jmp     short loc_140123BBA
0x140123bb8  xor     ecx, ecx
0x140123bba  mov     eax, [rbx+30h]
0x140123bbd  lea     r8, [rbp+57h+var_58]
0x140123bc1  mov     [rsp+0C0h+var_98], eax
0x140123bc5  mov     r9, rbx
0x140123bc8  mov     [rsp+0C0h+var_A0], ecx
0x140123bcc  call    McTemplateK0pqd_EtwWriteTransfer
0x140123bd1  jmp     loc_140123E12
0x140123bd6  test    cs:byte_140177432, 20h
0x140123bdd  jz      loc_140123E12
0x140123be3  lea     rdx, EventPnpRequestComplete
0x140123bea  jmp     loc_140123DFF
0x140123bef  cmp     cs:byte_140177431, 0
0x140123bf6  jge     loc_140123E12
0x140123bfc  mov     rdx, [rdx+8]
0x140123c00  mov     r9d, 1
0x140123c06  movzx   eax, byte ptr [rdx+2]
0x140123c0a  cmp     al, 28h ; '('
0x140123c0c  jnz     loc_140123CF8
0x140123c12  cmp     dword ptr [rdx+14h], 0
0x140123c16  jnz     loc_140123E12
0x140123c1c  mov     r15d, [rdx+38h]
0x140123c20  test    r15d, r15d
0x140123c23  jz      loc_140123E12
0x140123c29  xor     edi, edi
0x140123c2b  xor     r11b, r11b
0x140123c2e  xor     r12b, r12b
0x140123c31  mov     [rbp+57h+var_60], dil
0x140123c35  xor     r10d, r10d
0x140123c38  xor     r14d, r14d
0x140123c3b  mov     ecx, [rdx+r14*4+78h]
0x140123c40  cmp     ecx, 80h
0x140123c46  jb      short loc_140123CBF
0x140123c48  mov     esi, [rdx+10h]
0x140123c4b  cmp     ecx, esi
0x140123c4d  jnb     short loc_140123CBF
0x140123c4f  mov     r8d, ecx
0x140123c52  mov     ecx, [rcx+rdx]
0x140123c55  sub     ecx, 40h ; '@'
0x140123c58  jz      short loc_140123CB0
0x140123c5a  sub     ecx, r9d
  ... truncated ...
```
