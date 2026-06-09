# RaidCompleteWmiIrp

- ea: `0x14004bda0`
- end: `0x14004c672`
- name: `RaidCompleteWmiIrp`
- size: `2258`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1401be9b4`

## callees

- `0x14004bda0`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14004be32`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14004c116`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14004c3f4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14004c50c`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14004be32`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14004c116`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14004c3f4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14004c50c`
- `ntoskrnl!IofCallDriver` at `0x14004c63e`
- `ntoskrnl!IofCallDriver` at `0x14004c63e`
- `ntoskrnl!IofCompleteRequest` at `0x14004c0dd`
- `ntoskrnl!IofCompleteRequest` at `0x14004c3c1`
- `ntoskrnl!IofCompleteRequest` at `0x14004c0dd`
- `ntoskrnl!IofCompleteRequest` at `0x14004c3c1`

## pseudocode

```c
NTSTATUS __fastcall RaidCompleteWmiIrp(__int64 a1, __int64 a2)
{
  PDEVICE_OBJECT *v2; // rcx
  int v4; // eax
  int v5; // ebx
  bool v6; // zf
  unsigned __int64 v7; // rcx
  __int64 v8; // rdx
  int *v9; // rax
  __int64 *v10; // rdx
  __int64 v11; // rdx
  char v12; // r8
  unsigned int v13; // r12d
  unsigned __int8 v14; // r11
  char *v15; // rsi
  char v16; // r13
  _BYTE *v17; // r10
  unsigned int v18; // r15d
  unsigned __int64 v19; // r14
  __int64 v20; // r9
  int v21; // ecx
  char v22; // cl
  char v23; // r14
  char v24; // si
  _BYTE *v25; // rax
  char v26; // r9
  char *v27; // r9
  unsigned int v28; // eax
  unsigned __int64 v30; // rcx
  unsigned __int8 *v31; // rdx
  int v32; // eax
  int *v33; // rax
  __int64 *v34; // rdx
  __int64 v35; // rdx
  char v36; // r8
  int v37; // eax
  unsigned int v38; // r12d
  unsigned __int8 v39; // r11
  char *v40; // rsi
  char v41; // r13
  _BYTE *v42; // r10
  unsigned int v43; // r15d
  unsigned __int64 v44; // r14
  __int64 v45; // r9
  int v46; // ecx
  char v47; // cl
  char v48; // r14
  char v49; // si
  _BYTE *v50; // rax
  char v51; // r9
  char *v52; // r9
  unsigned int v53; // eax
  unsigned int v54; // r12d
  unsigned int v55; // r15d
  unsigned __int64 v56; // r14
  int v57; // ecx
  unsigned int v58; // r12d
  unsigned int v59; // r15d
  unsigned __int64 v60; // r14
  int v61; // ecx
  __int64 v62; // rax
  char v63; // [rsp+60h] [rbp-20h]
  char v64; // [rsp+60h] [rbp-20h]
  char v65; // [rsp+60h] [rbp-20h]
  char v66; // [rsp+60h] [rbp-20h]
  int v67; // [rsp+64h] [rbp-1Ch]
  __int128 v68; // [rsp+68h] [rbp-18h] BYREF

  v2 = *(PDEVICE_OBJECT **)(a1 + 64);
  v4 = *(_DWORD *)v2;
  if ( *(_DWORD *)v2 == 1094997074 || v4 == 1314275652 )
  {
    v62 = *(_QWORD *)(a2 + 184);
    *(_OWORD *)(v62 - 72) = *(_OWORD *)v62;
    *(_OWORD *)(v62 - 56) = *(_OWORD *)(v62 + 16);
    *(_OWORD *)(v62 - 40) = *(_OWORD *)(v62 + 32);
    *(_QWORD *)(v62 - 24) = *(_QWORD *)(v62 + 48);
    *(_BYTE *)(v62 - 69) = 0;
    return IofCallDriver(v2[3], (PIRP)a2);
  }
  LOBYTE(v5) = 0;
  *(_BYTE *)(a2 + 141) = -84;
  switch ( v4 )
  {
    case 1314278989:
      v6 = StorEtwLoggingEnabled == 0;
      v67 = *(_DWORD *)(a2 + 48);
      *(_DWORD *)(a2 + 48) = v67;
      if ( v6 )
        goto LABEL_133;
      v68 = 0;
      IoGetActivityIdIrp(a2, &v68);
      v31 = *(unsigned __int8 **)(a2 + 184);
      if ( *v31 != 14 )
      {
        v32 = *v31 - 15;
        if ( *v31 != 15 )
          goto LABEL_73;
        if ( byte_140177431 >= 0 )
          goto LABEL_133;
        v35 = *((_QWORD *)v31 + 1);
        v36 = 1;
        v37 = *(unsigned __int8 *)(v35 + 2);
        if ( (_BYTE)v37 == 40 )
        {
          if ( *(_DWORD *)(v35 + 20) )
            goto LABEL_133;
          v58 = *(_DWORD *)(v35 + 56);
          if ( !v58 )
            goto LABEL_133;
          v39 = 0;
          v66 = 0;
          v40 = 0;
          v41 = 0;
          v42 = 0;
          v59 = 0;
          while ( 1 )
          {
            v30 = *(unsigned int *)(v35 + 4LL * v59 + 120);
            if ( (unsigned int)v30 >= 0x80 )
            {
              v60 = *(unsigned int *)(v35 + 16);
              if ( (unsigned int)v30 < (unsigned int)v60 )
              {
                v45 = (unsigned int)v30;
                v61 = *(_DWORD *)(v30 + v35) - 64;
                if ( v61 )
                {
                  LODWORD(v30) = v61 - 1;
                  if ( (_DWORD)v30 )
                  {
                    if ( (_DWORD)v30 == 1 )
                    {
                      LODWORD(v30) = v45 + 40;
                      if ( v45 + 40 <= v60 )
                      {
LABEL_93:
                        if ( *(_DWORD *)(v45 + v35 + 12) )
                          v40 = (char *)(v45 + v35 + 32);
                        v42 = *(_BYTE **)(v45 + v35 + 24);
                        goto LABEL_107;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v30) = v45 + 56;
                    if ( v45 + 56 <= v60 )
                    {
                      v66 = 1;
                      if ( *(_BYTE *)(v45 + v35 + 10) )
                        v40 = (char *)(v45 + v35 + 24);
                      v41 = *(_BYTE *)(v45 + v35 + 8);
                      v42 = *(_BYTE **)(v45 + v35 + 16);
                      v39 = *(_BYTE *)(v45 + v35 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v30) = v45 + 40;
                  if ( v45 + 40 <= v60 )
                  {
LABEL_104:
                    if ( *(_BYTE *)(v45 + v35 + 10) )
                      v40 = (char *)(v45 + v35 + 24);
                    v42 = *(_BYTE **)(v45 + v35 + 16);
LABEL_107:
                    v39 = *(_BYTE *)(v45 + v35 + 9);
                    v41 = *(_BYTE *)(v45 + v35 + 8);
LABEL_108:
                    if ( v40 )
                    {
                      v47 = *v40;
                      goto LABEL_111;
                    }
                    goto LABEL_133;
                  }
                }
                if ( v66 )
                  goto LABEL_108;
              }
            }
            if ( ++v59 >= v58 )
              goto LABEL_108;
          }
        }
        goto LABEL_110;
      }
      goto LABEL_130;
    case 1396916560:
      v6 = StorEtwLoggingEnabled == 0;
      v67 = *(_DWORD *)(a2 + 48);
      *(_DWORD *)(a2 + 48) = v67;
      if ( v6 )
        goto LABEL_133;
      v68 = 0;
      IoGetActivityIdIrp(a2, &v68);
      v31 = *(unsigned __int8 **)(a2 + 184);
      if ( *v31 != 14 )
      {
        v32 = *v31 - 15;
        if ( *v31 != 15 )
          goto LABEL_73;
        if ( byte_140177431 >= 0 )
          goto LABEL_133;
        v35 = *((_QWORD *)v31 + 1);
        v36 = 1;
        v37 = *(unsigned __int8 *)(v35 + 2);
        if ( (_BYTE)v37 == 40 )
        {
          if ( !*(_DWORD *)(v35 + 20) )
          {
            v54 = *(_DWORD *)(v35 + 56);
            if ( v54 )
            {
              v39 = 0;
              v65 = 0;
              v40 = 0;
              v41 = 0;
              v42 = 0;
              v55 = 0;
              while ( 1 )
              {
                v30 = *(unsigned int *)(v35 + 4LL * v55 + 120);
                if ( (unsigned int)v30 >= 0x80 )
                {
                  v56 = *(unsigned int *)(v35 + 16);
                  if ( (unsigned int)v30 < (unsigned int)v56 )
                  {
                    v45 = (unsigned int)v30;
                    v57 = *(_DWORD *)(v30 + v35) - 64;
                    if ( v57 )
                    {
                      LODWORD(v30) = v57 - 1;
                      if ( (_DWORD)v30 )
                      {
                        if ( (_DWORD)v30 == 1 )
                        {
                          LODWORD(v30) = v45 + 40;
                          if ( v45 + 40 <= v56 )
                            goto LABEL_93;
                        }
                      }
                      else
                      {
                        LODWORD(v30) = v45 + 56;
                        if ( v45 + 56 <= v56 )
                        {
                          v65 = 1;
                          if ( *(_BYTE *)(v45 + v35 + 10) )
                            v40 = (char *)(v45 + v35 + 24);
                          v41 = *(_BYTE *)(v45 + v35 + 8);
                          v42 = *(_BYTE **)(v45 + v35 + 16);
                          v39 = *(_BYTE *)(v45 + v35 + 9);
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v30) = v45 + 40;
                      if ( v45 + 40 <= v56 )
                        goto LABEL_104;
                    }
                    if ( v65 )
                      goto LABEL_108;
                  }
                }
                if ( ++v55 >= v54 )
                  goto LABEL_108;
              }
            }
          }
          goto LABEL_133;
        }
        goto LABEL_110;
      }
LABEL_130:
      if ( (byte_140177432 & 8) == 0 )
        goto LABEL_133;
      v34 = EventNonReadWriteRequestComplete;
      goto LABEL_132;
    case 1431193940:
      v6 = StorEtwLoggingEnabled == 0;
      v67 = *(_DWORD *)(a2 + 48);
      *(_DWORD *)(a2 + 48) = v67;
      if ( v6 )
        goto LABEL_133;
      v68 = 0;
      IoGetActivityIdIrp(a2, &v68);
      v31 = *(unsigned __int8 **)(a2 + 184);
      if ( *v31 != 14 )
      {
        v32 = *v31 - 15;
        if ( *v31 != 15 )
        {
LABEL_73:
          if ( v32 != 12 )
            goto LABEL_133;
          if ( v31[1] == 7 && !*((_DWORD *)v31 + 2) )
          {
            if ( (byte_140177432 & 0x40) != 0 )
            {
              v33 = *(int **)(a2 + 56);
              if ( v33 )
                v5 = *v33;
              McTemplateK0pqd_EtwWriteTransfer(v30, (_DWORD)v31, (unsigned int)&v68, a2, v5, *(_DWORD *)(a2 + 48));
            }
            goto LABEL_133;
          }
          if ( (byte_140177432 & 0x20) == 0 )
            goto LABEL_133;
          v34 = EventPnpRequestComplete;
LABEL_132:
          McTemplateK0pd_EtwWriteTransfer(v30, v34, &v68, a2, *(_DWORD *)(a2 + 48));
          goto LABEL_133;
        }
        if ( byte_140177431 >= 0 )
          goto LABEL_133;
        v35 = *((_QWORD *)v31 + 1);
        v36 = 1;
        v37 = *(unsigned __int8 *)(v35 + 2);
        if ( (_BYTE)v37 == 40 )
        {
          if ( !*(_DWORD *)(v35 + 20) )
          {
            v38 = *(_DWORD *)(v35 + 56);
            if ( v38 )
            {
              v39 = 0;
              v64 = 0;
              v40 = 0;
              v41 = 0;
              v42 = 0;
              v43 = 0;
              while ( 1 )
              {
                v30 = *(unsigned int *)(v35 + 4LL * v43 + 120);
                if ( (unsigned int)v30 >= 0x80 )
                {
                  v44 = *(unsigned int *)(v35 + 16);
                  if ( (unsigned int)v30 < (unsigned int)v44 )
                  {
                    v45 = (unsigned int)v30;
                    v46 = *(_DWORD *)(v30 + v35) - 64;
                    if ( v46 )
                    {
                      LODWORD(v30) = v46 - 1;
                      if ( (_DWORD)v30 )
                      {
                        if ( (_DWORD)v30 == 1 )
                        {
                          LODWORD(v30) = v45 + 40;
                          if ( v45 + 40 <= v44 )
                            goto LABEL_93;
                        }
                      }
                      else
                      {
                        LODWORD(v30) = v45 + 56;
                        if ( v45 + 56 <= v44 )
                        {
                          v64 = 1;
                          if ( *(_BYTE *)(v45 + v35 + 10) )
                            v40 = (char *)(v45 + v35 + 24);
                          v41 = *(_BYTE *)(v45 + v35 + 8);
                          v42 = *(_BYTE **)(v45 + v35 + 16);
                          v39 = *(_BYTE *)(v45 + v35 + 9);
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v30) = v45 + 40;
                      if ( v45 + 40 <= v44 )
                        goto LABEL_104;
                    }
                    if ( v64 )
                      goto LABEL_108;
                  }
                }
                if ( ++v43 >= v38 )
                  goto LABEL_108;
              }
            }
          }
          goto LABEL_133;
        }
LABEL_110:
        v47 = *(_BYTE *)(v35 + 72);
        v42 = *(_BYTE **)(v35 + 32);
        v39 = *(_BYTE *)(v35 + 11);
        v41 = *(_BYTE *)(v35 + 4);
        if ( v37 )
          goto LABEL_133;
LABEL_111:
        LOBYTE(v30) = v47 - 8;
        if ( (v30 & 0x5D) != 0 )
        {
LABEL_133:
          IofCompleteRequest((PIRP)a2, 0);
          return v67;
        }
        v48 = *(_BYTE *)(v35 + 3);
        if ( v48 == 1 || !v42 || !v39 )
          goto LABEL_128;
        LOBYTE(v35) = 0;
        v30 = (unsigned __int64)&v42[v39];
        v49 = 0;
        v50 = v42 + 8;
        v51 = 0;
        if ( (unsigned __int8)((*v42 & 0x7F) - 114) <= 1u )
        {
          if ( (unsigned __int64)v50 <= v30 )
          {
            v49 = v42[2];
            LOBYTE(v35) = v42[1] & 0xF;
            v51 = v42[3];
            goto LABEL_127;
          }
        }
        else if ( (unsigned __int64)v50 <= v30 )
        {
          v52 = v42 + 13;
          LOBYTE(v35) = v42[2] & 0xF;
          v53 = v39;
          if ( (unsigned int)(unsigned __int8)v42[7] + 8 <= v39 )
            v53 = (unsigned __int8)v42[7] + 8;
          v30 = (unsigned __int64)&v42[v53];
          if ( (unsigned __int64)v52 <= v30 )
            v49 = v42[12];
          if ( (unsigned __int64)(v42 + 14) > v30 )
            v51 = 0;
          else
            v51 = *v52;
LABEL_127:
          if ( v36 )
          {
LABEL_129:
            McTemplateK0pduuuuup_EtwWriteTransfer(
              v30,
              v35,
              (unsigned int)&v68,
              a2,
              *(_DWORD *)(a2 + 48),
              v48,
              v41,
              v35,
              v49,
              v51,
              a2);
            goto LABEL_133;
          }
LABEL_128:
          LOBYTE(v35) = 0;
          v49 = 0;
          v51 = 0;
          goto LABEL_129;
        }
        v36 = 0;
        goto LABEL_127;
      }
      goto LABEL_130;
  }
  v6 = StorEtwLoggingEnabled == 0;
  *(_DWORD *)(a2 + 48) = -1073741811;
  if ( v6 )
    goto LABEL_69;
  v68 = 0;
  IoGetActivityIdIrp(a2, &v68);
  v8 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v8 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_69;
    v10 = EventNonReadWriteRequestComplete;
    goto LABEL_68;
  }
  if ( *(_BYTE *)v8 != 15 )
  {
    if ( *(_BYTE *)v8 != 27 )
      goto LABEL_69;
    if ( *(_BYTE *)(v8 + 1) == 7 && !*(_DWORD *)(v8 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v9 = *(int **)(a2 + 56);
        if ( v9 )
          v5 = *v9;
        McTemplateK0pqd_EtwWriteTransfer(v7, v8, (unsigned int)&v68, a2, v5, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_69;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_69;
    v10 = EventPnpRequestComplete;
LABEL_68:
    McTemplateK0pd_EtwWriteTransfer(v7, v10, &v68, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_69;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_69;
  v11 = *(_QWORD *)(v8 + 8);
  v12 = 1;
  if ( *(_BYTE *)(v11 + 2) == 40 )
  {
    if ( *(_DWORD *)(v11 + 20) )
      goto LABEL_69;
    v13 = *(_DWORD *)(v11 + 56);
    if ( !v13 )
      goto LABEL_69;
    v14 = 0;
    v63 = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    while ( 1 )
    {
      v7 = *(unsigned int *)(v11 + 4LL * v18 + 120);
      if ( (unsigned int)v7 >= 0x80 )
      {
        v19 = *(unsigned int *)(v11 + 16);
        if ( (unsigned int)v7 < (unsigned int)v19 )
        {
          v20 = (unsigned int)v7;
          v21 = *(_DWORD *)(v11 + v7) - 64;
          if ( v21 )
          {
            LODWORD(v7) = v21 - 1;
            if ( (_DWORD)v7 )
            {
              if ( (_DWORD)v7 == 1 )
              {
                LODWORD(v7) = v20 + 40;
                if ( v20 + 40 <= v19 )
                {
                  if ( *(_DWORD *)(v11 + v20 + 12) )
                    v15 = (char *)(v20 + v11 + 32);
                  v17 = *(_BYTE **)(v11 + v20 + 24);
                  goto LABEL_43;
                }
              }
            }
            else
            {
              LODWORD(v7) = v20 + 56;
              if ( v20 + 56 <= v19 )
              {
                v63 = 1;
                if ( *(_BYTE *)(v11 + v20 + 10) )
                  v15 = (char *)(v20 + v11 + 24);
                v16 = *(_BYTE *)(v11 + v20 + 8);
                v17 = *(_BYTE **)(v11 + v20 + 16);
                v14 = *(_BYTE *)(v11 + v20 + 9);
              }
            }
          }
          else
          {
            LODWORD(v7) = v20 + 40;
            if ( v20 + 40 <= v19 )
            {
              if ( *(_BYTE *)(v11 + v20 + 10) )
                v15 = (char *)(v20 + v11 + 24);
              v17 = *(_BYTE **)(v11 + v20 + 16);
LABEL_43:
              v14 = *(_BYTE *)(v11 + v20 + 9);
              v16 = *(_BYTE *)(v11 + v20 + 8);
LABEL_44:
              if ( v15 )
              {
                v22 = *v15;
                goto LABEL_47;
              }
              goto LABEL_69;
            }
          }
          if ( v63 )
            goto LABEL_44;
        }
      }
      if ( ++v18 >= v13 )
        goto LABEL_44;
    }
  }
  v22 = *(_BYTE *)(v11 + 72);
  v17 = *(_BYTE **)(v11 + 32);
  v14 = *(_BYTE *)(v11 + 11);
  v16 = *(_BYTE *)(v11 + 4);
  if ( *(_BYTE *)(v11 + 2) )
    goto LABEL_69;
LABEL_47:
  LOBYTE(v7) = v22 - 8;
  if ( (v7 & 0x5D) == 0 )
  {
    v23 = *(_BYTE *)(v11 + 3);
    if ( v23 == 1 || !v17 || !v14 )
      goto LABEL_64;
    LOBYTE(v11) = 0;
    v7 = (unsigned __int64)&v17[v14];
    v24 = 0;
    v25 = v17 + 8;
    v26 = 0;
    if ( (unsigned __int8)((*v17 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v25 <= v7 )
      {
        v24 = v17[2];
        LOBYTE(v11) = v17[1] & 0xF;
        v26 = v17[3];
        goto LABEL_63;
      }
    }
    else if ( (unsigned __int64)v25 <= v7 )
    {
      v27 = v17 + 13;
      LOBYTE(v11) = v17[2] & 0xF;
      v28 = v14;
      if ( (unsigned int)(unsigned __int8)v17[7] + 8 <= v14 )
        v28 = (unsigned __int8)v17[7] + 8;
      v7 = (unsigned __int64)&v17[v28];
      if ( (unsigned __int64)v27 <= v7 )
        v24 = v17[12];
      if ( (unsigned __int64)(v17 + 14) > v7 )
        v26 = 0;
      else
        v26 = *v27;
LABEL_63:
      if ( v12 )
      {
LABEL_65:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v7,
          v11,
          (unsigned int)&v68,
          a2,
          *(_DWORD *)(a2 + 48),
          v23,
          v16,
          v11,
          v24,
          v26,
          a2);
        goto LABEL_69;
      }
LABEL_64:
      LOBYTE(v11) = 0;
      v24 = 0;
      v26 = 0;
      goto LABEL_65;
    }
    v12 = 0;
    goto LABEL_63;
  }
LABEL_69:
  IofCompleteRequest((PIRP)a2, 0);
  return -1073741811;
}

```

## disassembly

```asm
0x14004bda0  mov     [rsp-38h+arg_10], rbx
0x14004bda5  push    rbp
0x14004bda6  push    rsi
0x14004bda7  push    rdi
0x14004bda8  push    r12
0x14004bdaa  push    r13
0x14004bdac  push    r14
0x14004bdae  push    r15
0x14004bdb0  mov     rbp, rsp
0x14004bdb3  sub     rsp, 80h
0x14004bdba  mov     rax, cs:__security_cookie
0x14004bdc1  xor     rax, rsp
0x14004bdc4  mov     [rbp+var_8], rax
0x14004bdc8  mov     rcx, [rcx+40h]
0x14004bdcc  mov     rdi, rdx
0x14004bdcf  mov     eax, [rcx]
0x14004bdd1  cmp     eax, 41445452h
0x14004bdd6  jz      loc_14004C60D
0x14004bddc  cmp     eax, 4E564144h
0x14004bde1  jz      loc_14004C60D
0x14004bde7  xor     ebx, ebx
0x14004bde9  mov     byte ptr [rdx+8Dh], 0ACh
0x14004bdf0  cmp     eax, 4E564E4Dh
0x14004bdf5  jz      loc_14004C4E9
0x14004bdfb  cmp     eax, 53434150h
0x14004be00  jz      loc_14004C3D5
0x14004be06  cmp     eax, 554E4954h
0x14004be0b  jz      loc_14004C0F3
0x14004be11  cmp     cs:StorEtwLoggingEnabled, bl
0x14004be17  mov     dword ptr [rdx+30h], 0C000000Dh
0x14004be1e  jz      loc_14004C0D8
0x14004be24  xorps   xmm0, xmm0
0x14004be27  lea     rdx, [rbp+var_18]
0x14004be2b  mov     rcx, rdi
0x14004be2e  movups  [rbp+var_18], xmm0
0x14004be32  call    cs:__imp_IoGetActivityIdIrp
0x14004be39  nop     dword ptr [rax+rax+00h]
0x14004be3e  mov     rdx, [rdi+0B8h]
0x14004be45  movzx   eax, byte ptr [rdx]
0x14004be48  sub     eax, 0Eh
0x14004be4b  jz      loc_14004C0B5
0x14004be51  sub     eax, 1
0x14004be54  jz      short loc_14004BEB7
0x14004be56  cmp     eax, 0Ch
0x14004be59  jnz     loc_14004C0D8
0x14004be5f  cmp     byte ptr [rdx+1], 7
0x14004be63  jnz     short loc_14004BE9E
0x14004be65  cmp     [rdx+8], ebx
0x14004be68  jnz     short loc_14004BE9E
0x14004be6a  test    cs:byte_140177432, 40h
0x14004be71  jz      loc_14004C0D8
0x14004be77  mov     rax, [rdi+38h]
0x14004be7b  test    rax, rax
0x14004be7e  jz      short loc_14004BE82
0x14004be80  mov     ebx, [rax]
0x14004be82  mov     eax, [rdi+30h]
0x14004be85  lea     r8, [rbp+var_18]
0x14004be89  mov     [rsp+80h+var_58], eax
0x14004be8d  mov     r9, rdi
0x14004be90  mov     [rsp+80h+var_60], ebx
0x14004be94  call    McTemplateK0pqd_EtwWriteTransfer
0x14004be99  jmp     loc_14004C0D8
0x14004be9e  test    cs:byte_140177432, 20h
0x14004bea5  jz      loc_14004C0D8
0x14004beab  lea     rdx, EventPnpRequestComplete
0x14004beb2  jmp     loc_14004C0C5
0x14004beb7  cmp     cs:byte_140177431, bl
0x14004bebd  jge     loc_14004C0D8
0x14004bec3  mov     rdx, [rdx+8]
0x14004bec7  mov     r8d, 1
0x14004becd  movzx   eax, byte ptr [rdx+2]
0x14004bed1  cmp     al, 28h ; '('
0x14004bed3  jnz     loc_14004BFBE
0x14004bed9  cmp     [rdx+14h], ebx
0x14004bedc  jnz     loc_14004C0D8
0x14004bee2  mov     r12d, [rdx+38h]
0x14004bee6  test    r12d, r12d
0x14004bee9  jz      loc_14004C0D8
0x14004beef  mov     r11b, bl
0x14004bef2  mov     [rbp+var_20], bl
0x14004bef5  mov     rsi, rbx
0x14004bef8  mov     r13b, bl
0x14004befb  mov     r10, rbx
0x14004befe  mov     r15d, ebx
0x14004bf01  mov     eax, r15d
0x14004bf04  mov     ecx, [rdx+rax*4+78h]
0x14004bf08  cmp     ecx, 80h
0x14004bf0e  jb      short loc_14004BF86
0x14004bf10  mov     r14d, [rdx+10h]
0x14004bf14  cmp     ecx, r14d
0x14004bf17  jnb     short loc_14004BF86
0x14004bf19  mov     r9d, ecx
0x14004bf1c  mov     ecx, [rdx+rcx]
0x14004bf1f  sub     ecx, 40h ; '@'
0x14004bf22  jz      short loc_14004BF78
0x14004bf24  sub     ecx, r8d
0x14004bf27  jz      short loc_14004BF4C
0x14004bf29  cmp     ecx, r8d
0x14004bf2c  jnz     short loc_14004BF81
0x14004bf2e  lea     rcx, [r9+28h]
0x14004bf32  cmp     rcx, r14
0x14004bf35  ja      short loc_14004BF81
0x14004bf37  cmp     [rdx+r9+0Ch], ebx
0x14004bf3c  jbe     short loc_14004BF45
0x14004bf3e  lea     rsi, [rdx+20h]
0x14004bf42  add     rsi, r9
0x14004bf45  mov     r10, [rdx+r9+18h]
0x14004bf4a  jmp     short loc_14004BFA7
0x14004bf4c  lea     rcx, [r9+38h]
0x14004bf50  cmp     rcx, r14
0x14004bf53  ja      short loc_14004BF81
0x14004bf55  mov     [rbp+var_20], r8b
0x14004bf59  cmp     [rdx+r9+0Ah], bl
0x14004bf5e  jbe     short loc_14004BF67
0x14004bf60  lea     rsi, [rdx+18h]
0x14004bf64  add     rsi, r9
0x14004bf67  mov     r13b, [rdx+r9+8]
0x14004bf6c  mov     r10, [rdx+r9+10h]
0x14004bf71  mov     r11b, [rdx+r9+9]
0x14004bf76  jmp     short loc_14004BF81
0x14004bf78  lea     rcx, [r9+28h]
0x14004bf7c  cmp     rcx, r14
0x14004bf7f  jbe     short loc_14004BF94
0x14004bf81  cmp     [rbp+var_20], bl
0x14004bf84  jnz     short loc_14004BFB1
0x14004bf86  add     r15d, r8d
0x14004bf89  cmp     r15d, r12d
0x14004bf8c  jb      loc_14004BF01
0x14004bf92  jmp     short loc_14004BFB1
0x14004bf94  cmp     [rdx+r9+0Ah], bl
0x14004bf99  jbe     short loc_14004BFA2
0x14004bf9b  lea     rsi, [rdx+18h]
0x14004bf9f  add     rsi, r9
0x14004bfa2  mov     r10, [rdx+r9+10h]
0x14004bfa7  mov     r11b, [rdx+r9+9]
0x14004bfac  mov     r13b, [rdx+r9+8]
0x14004bfb1  test    rsi, rsi
0x14004bfb4  jz      loc_14004C0D8
0x14004bfba  mov     cl, [rsi]
0x14004bfbc  jmp     short loc_14004BFD5
0x14004bfbe  mov     cl, [rdx+48h]
0x14004bfc1  mov     r10, [rdx+20h]
0x14004bfc5  mov     r11b, [rdx+0Bh]
0x14004bfc9  mov     r13b, [rdx+4]
0x14004bfcd  test    eax, eax
0x14004bfcf  jnz     loc_14004C0D8
0x14004bfd5  sub     cl, 8
0x14004bfd8  test    cl, 5Dh
0x14004bfdb  jnz     loc_14004C0D8
0x14004bfe1  mov     r14b, [rdx+3]
0x14004bfe5  cmp     r14b, r8b
0x14004bfe8  jz      loc_14004C07B
0x14004bfee  test    r10, r10
0x14004bff1  jz      loc_14004C07B
0x14004bff7  test    r11b, r11b
0x14004bffa  jz      short loc_14004C07B
0x14004bffc  mov     al, [r10]
0x14004bfff  mov     dl, bl
0x14004c001  and     al, 7Fh
0x14004c003  movzx   ecx, r11b
0x14004c007  sub     al, 72h ; 'r'
0x14004c009  add     rcx, r10
0x14004c00c  cmp     al, r8b
0x14004c00f  mov     sil, bl
0x14004c012  lea     rax, [r10+8]
0x14004c016  mov     r9b, bl
0x14004c019  jbe     short loc_14004C05D
0x14004c01b  cmp     rax, rcx
0x14004c01e  ja      short loc_14004C073
0x14004c020  movzx   ecx, byte ptr [r10+7]
0x14004c025  lea     r9, [r10+0Dh]
0x14004c029  mov     dl, [r10+2]
0x14004c02d  add     ecx, 8
0x14004c030  and     dl, 0Fh
0x14004c033  movzx   eax, r11b
0x14004c037  cmp     ecx, eax
0x14004c039  cmovbe  eax, ecx
0x14004c03c  mov     ecx, eax
0x14004c03e  add     rcx, r10
0x14004c041  cmp     r9, rcx
0x14004c044  ja      short loc_14004C04A
0x14004c046  mov     sil, [r10+0Ch]
0x14004c04a  lea     rax, [r10+0Eh]
0x14004c04e  cmp     rax, rcx
0x14004c051  ja      short loc_14004C058
0x14004c053  mov     r9b, [r9]
0x14004c056  jmp     short loc_14004C076
0x14004c058  mov     r9b, bl
0x14004c05b  jmp     short loc_14004C076
0x14004c05d  cmp     rax, rcx
0x14004c060  ja      short loc_14004C073
0x14004c062  mov     dl, [r10+1]
0x14004c066  mov     sil, [r10+2]
0x14004c06a  and     dl, 0Fh
0x14004c06d  mov     r9b, [r10+3]
0x14004c071  jmp     short loc_14004C076
0x14004c073  mov     r8b, bl
0x14004c076  test    r8b, r8b
0x14004c079  jnz     short loc_14004C083
0x14004c07b  mov     dl, bl
0x14004c07d  mov     sil, bl
0x14004c080  mov     r9b, bl
0x14004c083  mov     eax, [rdi+30h]
0x14004c086  lea     r8, [rbp+var_18]
0x14004c08a  mov     [rsp+80h+var_30], rdi
0x14004c08f  mov     [rsp+80h+var_38], r9b
0x14004c094  mov     r9, rdi
0x14004c097  mov     [rsp+80h+var_40], sil
0x14004c09c  mov     [rsp+80h+var_48], dl
0x14004c0a0  mov     [rsp+80h+var_50], r13b
0x14004c0a5  mov     byte ptr [rsp+80h+var_58], r14b
0x14004c0aa  mov     [rsp+80h+var_60], eax
0x14004c0ae  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x14004c0b3  jmp     short loc_14004C0D8
0x14004c0b5  test    cs:byte_140177432, 8
0x14004c0bc  jz      short loc_14004C0D8
0x14004c0be  lea     rdx, EventNonReadWriteRequestComplete
0x14004c0c5  mov     eax, [rdi+30h]
0x14004c0c8  lea     r8, [rbp+var_18]
0x14004c0cc  mov     r9, rdi
0x14004c0cf  mov     [rsp+80h+var_60], eax
0x14004c0d3  call    McTemplateK0pd_EtwWriteTransfer
0x14004c0d8  xor     edx, edx; PriorityBoost
0x14004c0da  mov     rcx, rdi; Irp
0x14004c0dd  call    cs:__imp_IofCompleteRequest
0x14004c0e4  nop     dword ptr [rax+rax+00h]
0x14004c0e9  mov     eax, 0C000000Dh
0x14004c0ee  jmp     loc_14004C64A
0x14004c0f3  cmp     cs:StorEtwLoggingEnabled, bl
0x14004c0f9  mov     eax, [rdx+30h]
0x14004c0fc  mov     [rbp+var_1C], eax
0x14004c0ff  mov     [rdx+30h], eax
0x14004c102  jz      loc_14004C3BC
0x14004c108  xorps   xmm0, xmm0
0x14004c10b  lea     rdx, [rbp+var_18]
0x14004c10f  mov     rcx, rdi
0x14004c112  movups  [rbp+var_18], xmm0
0x14004c116  call    cs:__imp_IoGetActivityIdIrp
0x14004c11d  nop     dword ptr [rax+rax+00h]
0x14004c122  mov     rdx, [rdi+0B8h]
0x14004c129  movzx   eax, byte ptr [rdx]
0x14004c12c  sub     eax, 0Eh
0x14004c12f  jz      loc_14004C399
0x14004c135  sub     eax, 1
0x14004c138  jz      short loc_14004C19B
0x14004c13a  cmp     eax, 0Ch
0x14004c13d  jnz     loc_14004C3BC
0x14004c143  cmp     byte ptr [rdx+1], 7
0x14004c147  jnz     short loc_14004C182
0x14004c149  cmp     [rdx+8], ebx
0x14004c14c  jnz     short loc_14004C182
0x14004c14e  test    cs:byte_140177432, 40h
0x14004c155  jz      loc_14004C3BC
0x14004c15b  mov     rax, [rdi+38h]
0x14004c15f  test    rax, rax
0x14004c162  jz      short loc_14004C166
0x14004c164  mov     ebx, [rax]
0x14004c166  mov     eax, [rdi+30h]
0x14004c169  lea     r8, [rbp+var_18]
0x14004c16d  mov     [rsp+80h+var_58], eax
0x14004c171  mov     r9, rdi
0x14004c174  mov     [rsp+80h+var_60], ebx
0x14004c178  call    McTemplateK0pqd_EtwWriteTransfer
0x14004c17d  jmp     loc_14004C3BC
0x14004c182  test    cs:byte_140177432, 20h
0x14004c189  jz      loc_14004C3BC
0x14004c18f  lea     rdx, EventPnpRequestComplete
0x14004c196  jmp     loc_14004C3A9
0x14004c19b  cmp     cs:byte_140177431, bl
0x14004c1a1  jge     loc_14004C3BC
0x14004c1a7  mov     rdx, [rdx+8]
0x14004c1ab  mov     r8d, 1
0x14004c1b1  movzx   eax, byte ptr [rdx+2]
0x14004c1b5  cmp     al, 28h ; '('
0x14004c1b7  jnz     loc_14004C2A2
0x14004c1bd  cmp     [rdx+14h], ebx
0x14004c1c0  jnz     loc_14004C3BC
0x14004c1c6  mov     r12d, [rdx+38h]
0x14004c1ca  test    r12d, r12d
0x14004c1cd  jz      loc_14004C3BC
0x14004c1d3  mov     r11b, bl
0x14004c1d6  mov     [rbp+var_20], bl
0x14004c1d9  mov     rsi, rbx
0x14004c1dc  mov     r13b, bl
0x14004c1df  mov     r10, rbx
0x14004c1e2  mov     r15d, ebx
0x14004c1e5  mov     eax, r15d
0x14004c1e8  mov     ecx, [rdx+rax*4+78h]
0x14004c1ec  cmp     ecx, 80h
0x14004c1f2  jb      short loc_14004C26A
0x14004c1f4  mov     r14d, [rdx+10h]
0x14004c1f8  cmp     ecx, r14d
0x14004c1fb  jnb     short loc_14004C26A
0x14004c1fd  mov     r9d, ecx
0x14004c200  mov     ecx, [rcx+rdx]
0x14004c203  sub     ecx, 40h ; '@'
0x14004c206  jz      short loc_14004C25C
0x14004c208  sub     ecx, r8d
0x14004c20b  jz      short loc_14004C230
0x14004c20d  cmp     ecx, r8d
  ... truncated ...
```
