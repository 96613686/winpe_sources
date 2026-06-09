# NvmeNamespaceStorageSetPropertyIoctl

- ea: `0x1401b5070`
- end: `0x1401b5cd9`
- name: `NvmeNamespaceStorageSetPropertyIoctl`
- size: `3177`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1401c36a8`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x140135700`
- `0x14014b400`
- `0x1401b5070`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b511e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b541f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b5592`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b56e9`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b59f1`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b511e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b541f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b5592`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b56e9`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401b59f1`
- `ntoskrnl!IofCallDriver` at `0x1401b59af`
- `ntoskrnl!IofCallDriver` at `0x1401b59af`
- `ntoskrnl!IofCompleteRequest` at `0x1401b5538`
- `ntoskrnl!IofCompleteRequest` at `0x1401b597d`
- `ntoskrnl!IofCompleteRequest` at `0x1401b5ca0`
- `ntoskrnl!IofCompleteRequest` at `0x1401b5538`
- `ntoskrnl!IofCompleteRequest` at `0x1401b597d`
- `ntoskrnl!IofCompleteRequest` at `0x1401b5ca0`

## pseudocode

```c
NTSTATUS __fastcall NvmeNamespaceStorageSetPropertyIoctl(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v3; // rax
  char v4; // di
  _DWORD *v6; // rcx
  __int64 v9; // rdx
  bool v10; // zf
  unsigned __int64 v11; // rcx
  unsigned __int8 *v12; // rdx
  int v13; // eax
  int *v14; // rax
  int v15; // ecx
  __int64 v16; // rdx
  int v17; // eax
  unsigned int v18; // r12d
  unsigned __int8 v19; // r11
  char *v20; // r10
  char v21; // r15
  _BYTE *v22; // r9
  __int64 v23; // r14
  char v24; // r13
  unsigned __int64 v25; // rsi
  __int64 v26; // r8
  int v27; // ecx
  char v28; // cl
  char v29; // si
  char v30; // r10
  char v31; // r8
  _BYTE *v32; // rax
  char *v33; // r8
  unsigned int v34; // eax
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  unsigned int v38; // r12d
  __int64 v39; // r14
  char v40; // r13
  unsigned __int64 v41; // rsi
  int v42; // ecx
  NTSTATUS result; // eax
  int v44; // eax
  int v45; // eax
  unsigned int v46; // r12d
  unsigned __int8 v47; // r11
  char *v48; // r10
  _BYTE *v49; // r9
  __int64 v50; // r14
  char v51; // r13
  unsigned __int64 v52; // rsi
  __int64 v53; // r8
  int v54; // ecx
  int *v55; // rax
  __int64 *v56; // rdx
  unsigned int v57; // r12d
  __int64 v58; // r14
  char v59; // r13
  unsigned __int64 v60; // rsi
  int v61; // ecx
  char v62; // cl
  _BYTE *v63; // rax
  char *v64; // r8
  unsigned int v65; // eax
  unsigned __int64 v66; // rcx
  __int64 v67; // rdx
  int *v68; // rax
  int v69; // ecx
  __int64 v70; // rdx
  unsigned int v71; // r12d
  unsigned __int8 v72; // r11
  char *v73; // r10
  char v74; // r15
  _BYTE *v75; // r9
  __int64 v76; // r14
  char v77; // r13
  unsigned __int64 v78; // rsi
  __int64 v79; // r8
  int v80; // ecx
  char v81; // cl
  char v82; // si
  char v83; // r10
  char v84; // r8
  _BYTE *v85; // rax
  char *v86; // r8
  unsigned int v87; // eax
  int v88; // [rsp+60h] [rbp-20h]
  __int128 v89; // [rsp+68h] [rbp-18h] BYREF

  v3 = *(_QWORD *)(a2 + 184);
  v4 = 1;
  *a3 = 1;
  v6 = *(_DWORD **)(a2 + 24);
  if ( !v6 || *(_DWORD *)(v3 + 16) < 8u )
  {
    v10 = StorEtwLoggingEnabled == 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = -1073741811;
    if ( v10 )
      goto LABEL_254;
    v89 = 0;
    IoGetActivityIdIrp(a2, &v89);
    v67 = *(_QWORD *)(a2 + 184);
    if ( *(_BYTE *)v67 == 14 )
    {
      if ( (byte_140177432 & 8) != 0 )
        McTemplateK0pd_EtwWriteTransfer(
          *(unsigned int *)(a2 + 48),
          EventNonReadWriteRequestComplete,
          &v89,
          a2,
          *(_DWORD *)(a2 + 48));
      goto LABEL_254;
    }
    if ( *(_BYTE *)v67 != 15 )
    {
      if ( *(_BYTE *)v67 == 27 )
      {
        if ( *(_BYTE *)(v67 + 1) != 7 || *(_DWORD *)(v67 + 8) )
        {
          if ( (byte_140177432 & 0x20) != 0 )
            McTemplateK0pd_EtwWriteTransfer(v66, EventPnpRequestComplete, &v89, a2, *(_DWORD *)(a2 + 48));
        }
        else if ( (byte_140177432 & 0x40) != 0 )
        {
          v68 = *(int **)(a2 + 56);
          if ( v68 )
            v69 = *v68;
          else
            v69 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v69, v67, (unsigned int)&v89, a2, v69, *(_DWORD *)(a2 + 48));
        }
      }
      goto LABEL_254;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_254;
    v70 = *(_QWORD *)(v67 + 8);
    if ( *(_BYTE *)(v70 + 2) == 40 )
    {
      if ( *(_DWORD *)(v70 + 20) )
        goto LABEL_254;
      v71 = *(_DWORD *)(v70 + 56);
      if ( !v71 )
        goto LABEL_254;
      v72 = 0;
      v73 = 0;
      v74 = 0;
      v75 = 0;
      v76 = 0;
      v77 = 0;
      while ( 1 )
      {
        v66 = *(unsigned int *)(v70 + 4 * v76 + 120);
        if ( (unsigned int)v66 >= 0x80 )
        {
          v78 = *(unsigned int *)(v70 + 16);
          if ( (unsigned int)v66 < (unsigned int)v78 )
          {
            v79 = (unsigned int)v66;
            v80 = *(_DWORD *)(v66 + v70) - 64;
            if ( v80 )
            {
              LODWORD(v66) = v80 - 1;
              if ( (_DWORD)v66 )
              {
                if ( (_DWORD)v66 == 1 )
                {
                  LODWORD(v66) = v79 + 40;
                  if ( v79 + 40 <= v78 )
                  {
                    if ( *(_DWORD *)(v79 + v70 + 12) )
                      v73 = (char *)(v79 + v70 + 32);
                    v75 = *(_BYTE **)(v79 + v70 + 24);
                    goto LABEL_229;
                  }
                }
              }
              else
              {
                LODWORD(v66) = v79 + 56;
                if ( v79 + 56 <= v78 )
                {
                  v77 = 1;
                  if ( *(_BYTE *)(v79 + v70 + 10) )
                    v73 = (char *)(v79 + v70 + 24);
                  v74 = *(_BYTE *)(v79 + v70 + 8);
                  v75 = *(_BYTE **)(v79 + v70 + 16);
                  v72 = *(_BYTE *)(v79 + v70 + 9);
                }
              }
            }
            else
            {
              LODWORD(v66) = v79 + 40;
              if ( v79 + 40 <= v78 )
              {
                if ( *(_BYTE *)(v79 + v70 + 10) )
                  v73 = (char *)(v79 + v70 + 24);
                v75 = *(_BYTE **)(v79 + v70 + 16);
LABEL_229:
                v72 = *(_BYTE *)(v79 + v70 + 9);
                v74 = *(_BYTE *)(v79 + v70 + 8);
LABEL_230:
                if ( v73 )
                {
                  v81 = *v73;
                  goto LABEL_233;
                }
                goto LABEL_254;
              }
            }
            if ( v77 )
              goto LABEL_230;
          }
        }
        v76 = (unsigned int)(v76 + 1);
        if ( (unsigned int)v76 >= v71 )
          goto LABEL_230;
      }
    }
    v81 = *(_BYTE *)(v70 + 72);
    v75 = *(_BYTE **)(v70 + 32);
    v72 = *(_BYTE *)(v70 + 11);
    v74 = *(_BYTE *)(v70 + 4);
    if ( *(_BYTE *)(v70 + 2) )
      goto LABEL_254;
LABEL_233:
    LOBYTE(v66) = v81 - 8;
    if ( (v66 & 0x5D) != 0 )
    {
LABEL_254:
      IofCompleteRequest((PIRP)a2, 0);
      return -1073741811;
    }
    v82 = *(_BYTE *)(v70 + 3);
    if ( v82 == 1 || !v75 || !v72 )
      goto LABEL_250;
    LOBYTE(v70) = 0;
    v83 = 0;
    v84 = 0;
    v66 = (unsigned __int64)&v75[v72];
    v85 = v75 + 8;
    if ( (unsigned __int8)((*v75 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v85 <= v66 )
      {
        v83 = v75[2];
        LOBYTE(v70) = v75[1] & 0xF;
        v84 = v75[3];
        goto LABEL_249;
      }
    }
    else if ( (unsigned __int64)v85 <= v66 )
    {
      v86 = v75 + 13;
      LOBYTE(v70) = v75[2] & 0xF;
      v87 = v72;
      if ( (unsigned int)(unsigned __int8)v75[7] + 8 <= v72 )
        v87 = (unsigned __int8)v75[7] + 8;
      v66 = (unsigned __int64)&v75[v87];
      if ( (unsigned __int64)v86 <= v66 )
        v83 = v75[12];
      if ( (unsigned __int64)(v75 + 14) > v66 )
        v84 = 0;
      else
        v84 = *v86;
LABEL_249:
      if ( v4 )
      {
LABEL_251:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v66,
          v70,
          (unsigned int)&v89,
          a2,
          *(_DWORD *)(a2 + 48),
          v82,
          v74,
          v70,
          v83,
          v84,
          a2);
        goto LABEL_254;
      }
LABEL_250:
      LOBYTE(v70) = 0;
      v83 = 0;
      v84 = 0;
      goto LABEL_251;
    }
    v4 = 0;
    goto LABEL_249;
  }
  v9 = *(_QWORD *)(a1 + 16);
  if ( (*(_QWORD *)(v9 + 136) & 2) != 0 && *(_DWORD *)(v9 + 568) != 2 )
  {
    v10 = StorEtwLoggingEnabled == 0;
    v88 = -1073741300;
    *(_DWORD *)(a2 + 48) = -1073741300;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    if ( v10 )
      goto LABEL_189;
    v89 = 0;
    IoGetActivityIdIrp(a2, &v89);
    v12 = *(unsigned __int8 **)(a2 + 184);
    if ( *v12 == 14 )
    {
      if ( (byte_140177432 & 8) != 0 )
        McTemplateK0pd_EtwWriteTransfer(v11, EventNonReadWriteRequestComplete, &v89, a2, *(_DWORD *)(a2 + 48));
      goto LABEL_189;
    }
    v13 = *v12 - 15;
    if ( *v12 != 15 )
    {
LABEL_8:
      if ( v13 != 12 )
        goto LABEL_189;
      if ( v12[1] != 7 || *((_DWORD *)v12 + 2) )
      {
        if ( (byte_140177432 & 0x20) != 0 )
          McTemplateK0pd_EtwWriteTransfer(v11, EventPnpRequestComplete, &v89, a2, *(_DWORD *)(a2 + 48));
        goto LABEL_189;
      }
      if ( (byte_140177432 & 0x40) == 0 )
        goto LABEL_189;
      v14 = *(int **)(a2 + 56);
      if ( v14 )
        v15 = *v14;
      else
        v15 = 0;
LABEL_137:
      McTemplateK0pqd_EtwWriteTransfer(v15, (_DWORD)v12, (unsigned int)&v89, a2, v15, *(_DWORD *)(a2 + 48));
      goto LABEL_189;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_189;
    v16 = *((_QWORD *)v12 + 1);
    v17 = *(unsigned __int8 *)(v16 + 2);
    if ( (_BYTE)v17 == 40 )
    {
      if ( !*(_DWORD *)(v16 + 20) )
      {
        v18 = *(_DWORD *)(v16 + 56);
        if ( v18 )
        {
          v19 = 0;
          v20 = 0;
          v21 = 0;
          v22 = 0;
          v23 = 0;
          v24 = 0;
          while ( 1 )
          {
            v11 = *(unsigned int *)(v16 + 4 * v23 + 120);
            if ( (unsigned int)v11 >= 0x80 )
            {
              v25 = *(unsigned int *)(v16 + 16);
              if ( (unsigned int)v11 < (unsigned int)v25 )
              {
                v26 = (unsigned int)v11;
                v27 = *(_DWORD *)(v11 + v16) - 64;
                if ( v27 )
                {
                  LODWORD(v11) = v27 - 1;
                  if ( (_DWORD)v11 )
                  {
                    if ( (_DWORD)v11 == 1 )
                    {
                      LODWORD(v11) = v26 + 40;
                      if ( v26 + 40 <= v25 )
                        goto LABEL_28;
                    }
                  }
                  else
                  {
                    LODWORD(v11) = v26 + 56;
                    if ( v26 + 56 <= v25 )
                    {
                      v24 = 1;
                      if ( *(_BYTE *)(v26 + v16 + 10) )
                        v20 = (char *)(v26 + v16 + 24);
                      v21 = *(_BYTE *)(v26 + v16 + 8);
                      v22 = *(_BYTE **)(v26 + v16 + 16);
                      v19 = *(_BYTE *)(v26 + v16 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v11) = v26 + 40;
                  if ( v26 + 40 <= v25 )
                    goto LABEL_39;
                }
                if ( v24 )
                  goto LABEL_43;
              }
            }
            v23 = (unsigned int)(v23 + 1);
            if ( (unsigned int)v23 >= v18 )
              goto LABEL_43;
          }
        }
      }
      goto LABEL_189;
    }
    goto LABEL_45;
  }
  v35 = *v6 - 49;
  if ( !v35 )
    goto LABEL_125;
  v36 = v35 - 1;
  if ( !v36 )
    goto LABEL_71;
  v37 = v36 - 17;
  if ( !v37 )
  {
LABEL_125:
    if ( *(_BYTE *)(v9 + 1728) == 1 )
    {
      result = NvmeCommonSetStorageProtocolSpecificProperty(*(_QWORD *)(a1 + 8), a2, a3);
      v88 = result;
      if ( result == 259 )
        goto LABEL_99;
      v10 = StorEtwLoggingEnabled == 0;
      *(_BYTE *)(a2 + 141) = -84;
      *(_DWORD *)(a2 + 48) = result;
      if ( v10 )
        goto LABEL_189;
      v89 = 0;
      IoGetActivityIdIrp(a2, &v89);
      v12 = *(unsigned __int8 **)(a2 + 184);
      if ( *v12 != 14 )
      {
        v44 = *v12 - 15;
        if ( *v12 == 15 )
        {
          if ( byte_140177431 >= 0 )
            goto LABEL_189;
          v16 = *((_QWORD *)v12 + 1);
          v45 = *(unsigned __int8 *)(v16 + 2);
          if ( (_BYTE)v45 == 40 )
          {
            if ( *(_DWORD *)(v16 + 20) )
              goto LABEL_189;
            v57 = *(_DWORD *)(v16 + 56);
            if ( !v57 )
              goto LABEL_189;
            v47 = 0;
            v48 = 0;
            v21 = 0;
            v49 = 0;
            v58 = 0;
            v59 = 0;
            while ( 1 )
            {
              v11 = *(unsigned int *)(v16 + 4 * v58 + 120);
              if ( (unsigned int)v11 >= 0x80 )
              {
                v60 = *(unsigned int *)(v16 + 16);
                if ( (unsigned int)v11 < (unsigned int)v60 )
                {
                  v53 = (unsigned int)v11;
                  v61 = *(_DWORD *)(v16 + v11) - 64;
                  if ( v61 )
                  {
                    LODWORD(v11) = v61 - 1;
                    if ( (_DWORD)v11 )
                    {
                      if ( (_DWORD)v11 == 1 )
                      {
                        LODWORD(v11) = v53 + 40;
                        if ( v53 + 40 <= v60 )
                        {
LABEL_114:
                          if ( *(_DWORD *)(v16 + v53 + 12) )
                            v48 = (char *)(v53 + v16 + 32);
                          v49 = *(_BYTE **)(v16 + v53 + 24);
LABEL_163:
                          v47 = *(_BYTE *)(v16 + v53 + 9);
                          v21 = *(_BYTE *)(v16 + v53 + 8);
LABEL_164:
                          if ( !v48 )
                            goto LABEL_189;
                          v62 = *v48;
LABEL_167:
                          LOBYTE(v11) = v62 - 8;
                          if ( (v11 & 0x5D) != 0 )
                            goto LABEL_189;
                          v29 = *(_BYTE *)(v16 + 3);
                          if ( v29 == 1 || !v49 || !v47 )
                            goto LABEL_184;
                          LOBYTE(v16) = 0;
                          v30 = 0;
                          v31 = 0;
                          v11 = (unsigned __int64)&v49[v47];
                          v63 = v49 + 8;
                          if ( (unsigned __int8)((*v49 & 0x7F) - 114) <= 1u )
                          {
                            if ( (unsigned __int64)v63 <= v11 )
                            {
                              v30 = v49[2];
                              LOBYTE(v16) = v49[1] & 0xF;
                              v31 = v49[3];
                              goto LABEL_183;
                            }
                          }
                          else if ( (unsigned __int64)v63 <= v11 )
                          {
                            v64 = v49 + 13;
                            LOBYTE(v16) = v49[2] & 0xF;
                            v65 = v47;
                            if ( (unsigned int)(unsigned __int8)v49[7] + 8 <= v47 )
                              v65 = (unsigned __int8)v49[7] + 8;
                            v11 = (unsigned __int64)&v49[v65];
                            if ( (unsigned __int64)v64 <= v11 )
                              v30 = v49[12];
                            if ( (unsigned __int64)(v49 + 14) > v11 )
                              v31 = 0;
                            else
                              v31 = *v64;
LABEL_183:
                            if ( !v4 )
                            {
LABEL_184:
                              LOBYTE(v16) = 0;
                              v30 = 0;
                              v31 = 0;
                            }
LABEL_185:
                            McTemplateK0pduuuuup_EtwWriteTransfer(
                              v11,
                              v16,
                              (unsigned int)&v89,
                              a2,
                              *(_DWORD *)(a2 + 48),
                              v29,
                              v21,
                              v16,
                              v30,
                              v31,
                              a2);
                            goto LABEL_189;
                          }
                          v4 = 0;
                          goto LABEL_183;
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v11) = v53 + 56;
                      if ( v53 + 56 <= v60 )
                      {
                        v59 = 1;
                        if ( *(_BYTE *)(v16 + v53 + 10) )
                          v48 = (char *)(v53 + v16 + 24);
                        v21 = *(_BYTE *)(v16 + v53 + 8);
                        v49 = *(_BYTE **)(v16 + v53 + 16);
                        v47 = *(_BYTE *)(v16 + v53 + 9);
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v11) = v53 + 40;
                    if ( v53 + 40 <= v60 )
                    {
LABEL_160:
                      if ( *(_BYTE *)(v16 + v53 + 10) )
                        v48 = (char *)(v53 + v16 + 24);
                      v49 = *(_BYTE **)(v16 + v53 + 16);
                      goto LABEL_163;
                    }
                  }
                  if ( v59 )
                    goto LABEL_164;
                }
              }
              v58 = (unsigned int)(v58 + 1);
              if ( (unsigned int)v58 >= v57 )
                goto LABEL_164;
            }
          }
LABEL_166:
          v21 = *(_BYTE *)(v16 + 4);
          v47 = *(_BYTE *)(v16 + 11);
          v49 = *(_BYTE **)(v16 + 32);
          v62 = *(_BYTE *)(v16 + 72);
          if ( v45 )
            goto LABEL_189;
          goto LABEL_167;
        }
        goto LABEL_130;
      }
LABEL_186:
      if ( (byte_140177432 & 8) == 0 )
        goto LABEL_189;
      v56 = EventNonReadWriteRequestComplete;
      goto LABEL_188;
    }
LABEL_190:
    ++*(_BYTE *)(a2 + 67);
    *(_QWORD *)(a2 + 184) += 72LL;
    return IofCallDriver(*(PDEVICE_OBJECT *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 128LL) + 8LL), (PIRP)a2);
  }
  if ( v37 != 1 )
    goto LABEL_190;
LABEL_71:
  if ( (*(_QWORD *)(v9 + 136) & 2LL) == 0 )
  {
    result = NvmeCommonSetStorageProtocolSpecificProperty(*(_QWORD *)(a1 + 8), a2, a3);
    v88 = result;
    if ( result == 259 )
    {
LABEL_99:
      *a3 = 0;
      return result;
    }
    v10 = StorEtwLoggingEnabled == 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = result;
    if ( v10 )
      goto LABEL_189;
    v89 = 0;
    IoGetActivityIdIrp(a2, &v89);
    v12 = *(unsigned __int8 **)(a2 + 184);
    if ( *v12 != 14 )
    {
      v44 = *v12 - 15;
      if ( *v12 == 15 )
      {
        if ( byte_140177431 >= 0 )
          goto LABEL_189;
        v16 = *((_QWORD *)v12 + 1);
        v45 = *(unsigned __int8 *)(v16 + 2);
        if ( (_BYTE)v45 == 40 )
        {
          if ( *(_DWORD *)(v16 + 20) )
            goto LABEL_189;
          v46 = *(_DWORD *)(v16 + 56);
          if ( !v46 )
            goto LABEL_189;
          v47 = 0;
          v48 = 0;
          v21 = 0;
          v49 = 0;
          v50 = 0;
          v51 = 0;
          while ( 1 )
          {
            v11 = *(unsigned int *)(v16 + 4 * v50 + 120);
            if ( (unsigned int)v11 >= 0x80 )
            {
              v52 = *(unsigned int *)(v16 + 16);
              if ( (unsigned int)v11 < (unsigned int)v52 )
              {
                v53 = (unsigned int)v11;
                v54 = *(_DWORD *)(v16 + v11) - 64;
                if ( v54 )
                {
                  LODWORD(v11) = v54 - 1;
                  if ( (_DWORD)v11 )
                  {
                    if ( (_DWORD)v11 == 1 )
                    {
                      LODWORD(v11) = v53 + 40;
                      if ( v53 + 40 <= v52 )
                        goto LABEL_114;
                    }
                  }
                  else
                  {
                    LODWORD(v11) = v53 + 56;
                    if ( v53 + 56 <= v52 )
                    {
                      v51 = 1;
                      if ( *(_BYTE *)(v16 + v53 + 10) )
                        v48 = (char *)(v53 + v16 + 24);
                      v21 = *(_BYTE *)(v16 + v53 + 8);
                      v49 = *(_BYTE **)(v16 + v53 + 16);
                      v47 = *(_BYTE *)(v16 + v53 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v11) = v53 + 40;
                  if ( v53 + 40 <= v52 )
                    goto LABEL_160;
                }
                if ( v51 )
                  goto LABEL_164;
              }
            }
            v50 = (unsigned int)(v50 + 1);
            if ( (unsigned int)v50 >= v46 )
              goto LABEL_164;
          }
        }
        goto LABEL_166;
      }
LABEL_130:
      if ( v44 != 12 )
        goto LABEL_189;
      if ( v12[1] == 7 && !*((_DWORD *)v12 + 2) )
      {
        if ( (byte_140177432 & 0x40) == 0 )
          goto LABEL_189;
        v55 = *(int **)(a2 + 56);
        if ( v55 )
          v15 = *v55;
        else
          v15 = 0;
        goto LABEL_137;
      }
      if ( (byte_140177432 & 0x20) == 0 )
        goto LABEL_189;
      v56 = EventPnpRequestComplete;
LABEL_188:
      McTemplateK0pd_EtwWriteTransfer(v11, v56, &v89, a2, *(_DWORD *)(a2 + 48));
      goto LABEL_189;
    }
    goto LABEL_186;
  }
  v10 = StorEtwLoggingEnabled == 0;
  v88 = -1073741637;
  *(_DWORD *)(a2 + 48) = -1073741637;
  *(_QWORD *)(a2 + 56) = 0;
  *(_BYTE *)(a2 + 141) = -84;
  if ( v10 )
    goto LABEL_189;
  v89 = 0;
  IoGetActivityIdIrp(a2, &v89);
  v12 = *(unsigned __int8 **)(a2 + 184);
  if ( *v12 == 14 )
  {
    if ( (byte_140177432 & 8) != 0 )
      McTemplateK0pd_EtwWriteTransfer(
        *(unsigned int *)(a2 + 48),
        EventNonReadWriteRequestComplete,
        &v89,
        a2,
        *(_DWORD *)(a2 + 48));
    goto LABEL_189;
  }
  v13 = *v12 - 15;
  if ( *v12 != 15 )
    goto LABEL_8;
  if ( byte_140177431 >= 0 )
    goto LABEL_189;
  v16 = *((_QWORD *)v12 + 1);
  v17 = *(unsigned __int8 *)(v16 + 2);
  if ( (_BYTE)v17 == 40 )
  {
    if ( *(_DWORD *)(v16 + 20) )
      goto LABEL_189;
    v38 = *(_DWORD *)(v16 + 56);
    if ( !v38 )
      goto LABEL_189;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v39 = 0;
    v40 = 0;
    while ( 1 )
    {
      v11 = *(unsigned int *)(v16 + 4 * v39 + 120);
      if ( (unsigned int)v11 >= 0x80 )
      {
        v41 = *(unsigned int *)(v16 + 16);
        if ( (unsigned int)v11 < (unsigned int)v41 )
        {
          v26 = (unsigned int)v11;
          v42 = *(_DWORD *)(v11 + v16) - 64;
          if ( v42 )
          {
            LODWORD(v11) = v42 - 1;
            if ( (_DWORD)v11 )
            {
              if ( (_DWORD)v11 == 1 )
              {
                LODWORD(v11) = v26 + 40;
                if ( v26 + 40 <= v41 )
                {
LABEL_28:
                  if ( *(_DWORD *)(v26 + v16 + 12) )
                    v20 = (char *)(v26 + v16 + 32);
                  v22 = *(_BYTE **)(v26 + v16 + 24);
                  goto LABEL_42;
                }
              }
            }
            else
            {
              LODWORD(v11) = v26 + 56;
              if ( v26 + 56 <= v41 )
              {
                v40 = 1;
                if ( *(_BYTE *)(v26 + v16 + 10) )
                  v20 = (char *)(v26 + v16 + 24);
                v21 = *(_BYTE *)(v26 + v16 + 8);
                v22 = *(_BYTE **)(v26 + v16 + 16);
                v19 = *(_BYTE *)(v26 + v16 + 9);
              }
            }
          }
          else
          {
            LODWORD(v11) = v26 + 40;
            if ( v26 + 40 <= v41 )
            {
LABEL_39:
              if ( *(_BYTE *)(v26 + v16 + 10) )
                v20 = (char *)(v26 + v16 + 24);
              v22 = *(_BYTE **)(v26 + v16 + 16);
LABEL_42:
              v19 = *(_BYTE *)(v26 + v16 + 9);
              v21 = *(_BYTE *)(v26 + v16 + 8);
LABEL_43:
              if ( v20 )
              {
                v28 = *v20;
                goto LABEL_46;
              }
              goto LABEL_189;
            }
          }
          if ( v40 )
            goto LABEL_43;
        }
      }
      v39 = (unsigned int)(v39 + 1);
      if ( (unsigned int)v39 >= v38 )
        goto LABEL_43;
    }
  }
LABEL_45:
  v21 = *(_BYTE *)(v16 + 4);
  v19 = *(_BYTE *)(v16 + 11);
  v22 = *(_BYTE **)(v16 + 32);
  v28 = *(_BYTE *)(v16 + 72);
  if ( v17 )
    goto LABEL_189;
LABEL_46:
  LOBYTE(v11) = v28 - 8;
  if ( (v11 & 0x5D) == 0 )
  {
    v29 = *(_BYTE *)(v16 + 3);
    if ( v29 == 1 || !v22 || !v19 )
      goto LABEL_63;
    LOBYTE(v16) = 0;
    v30 = 0;
    v31 = 0;
    v11 = (unsigned __int64)&v22[v19];
    v32 = v22 + 8;
    if ( (unsigned __int8)((*v22 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v32 <= v11 )
      {
        v30 = v22[2];
        LOBYTE(v16) = v22[1] & 0xF;
        v31 = v22[3];
        goto LABEL_62;
      }
    }
    else if ( (unsigned __int64)v32 <= v11 )
    {
      v33 = v22 + 13;
      LOBYTE(v16) = v22[2] & 0xF;
      v34 = v19;
      if ( (unsigned int)(unsigned __int8)v22[7] + 8 <= v19 )
        v34 = (unsigned __int8)v22[7] + 8;
      v11 = (unsigned __int64)&v22[v34];
      if ( (unsigned __int64)v33 <= v11 )
        v30 = v22[12];
      if ( (unsigned __int64)(v22 + 14) > v11 )
        v31 = 0;
      else
        v31 = *v33;
LABEL_62:
      if ( v4 )
        goto LABEL_185;
LABEL_63:
      LOBYTE(v16) = 0;
      v30 = 0;
      v31 = 0;
      goto LABEL_185;
    }
    v4 = 0;
    goto LABEL_62;
  }
LABEL_189:
  IofCompleteRequest((PIRP)a2, 0);
  return v88;
}

```

## disassembly

```asm
0x1401b5070  mov     [rsp-38h+arg_18], rbx
0x1401b5075  push    rbp
0x1401b5076  push    rsi
0x1401b5077  push    rdi
0x1401b5078  push    r12
0x1401b507a  push    r13
0x1401b507c  push    r14
0x1401b507e  push    r15
0x1401b5080  mov     rbp, rsp
0x1401b5083  sub     rsp, 80h
0x1401b508a  mov     rax, cs:__security_cookie
0x1401b5091  xor     rax, rsp
0x1401b5094  mov     [rbp+var_8], rax
0x1401b5098  mov     rax, [rdx+0B8h]
0x1401b509f  mov     edi, 1
0x1401b50a4  mov     [r8], dil
0x1401b50a7  mov     r9, rcx
0x1401b50aa  mov     rcx, [rdx+18h]
0x1401b50ae  mov     rsi, r8
0x1401b50b1  mov     rbx, rdx
0x1401b50b4  test    rcx, rcx
0x1401b50b7  jz      loc_1401B59C0
0x1401b50bd  cmp     dword ptr [rax+10h], 8
0x1401b50c1  jb      loc_1401B59C0
0x1401b50c7  mov     rdx, [r9+10h]
0x1401b50cb  mov     r8, [rdx+88h]
0x1401b50d2  and     r8d, 2
0x1401b50d6  jz      loc_1401B53C1
0x1401b50dc  cmp     dword ptr [rdx+238h], 2
0x1401b50e3  jz      loc_1401B53C1
0x1401b50e9  cmp     cs:StorEtwLoggingEnabled, 0
0x1401b50f0  mov     eax, 0C000020Ch
0x1401b50f5  mov     [rbp+var_20], eax
0x1401b50f8  mov     [rbx+30h], eax
0x1401b50fb  mov     qword ptr [rbx+38h], 0
0x1401b5103  mov     byte ptr [rbx+8Dh], 0ACh
0x1401b510a  jz      loc_1401B5533
0x1401b5110  xorps   xmm0, xmm0
0x1401b5113  lea     rdx, [rbp+var_18]
0x1401b5117  mov     rcx, rbx
0x1401b511a  movups  [rbp+var_18], xmm0
0x1401b511e  call    cs:__imp_IoGetActivityIdIrp
0x1401b5125  nop     dword ptr [rax+rax+00h]
0x1401b512a  mov     rdx, [rbx+0B8h]
0x1401b5131  movzx   eax, byte ptr [rdx]
0x1401b5134  sub     eax, 0Eh
0x1401b5137  jz      loc_1401B53A8
0x1401b513d  sub     eax, edi
0x1401b513f  jz      short loc_1401B51AE
0x1401b5141  cmp     eax, 0Ch
0x1401b5144  jnz     loc_1401B5533
0x1401b514a  cmp     byte ptr [rdx+1], 7
0x1401b514e  jnz     short loc_1401B518E
0x1401b5150  cmp     dword ptr [rdx+8], 0
0x1401b5154  jnz     short loc_1401B518E
0x1401b5156  test    cs:byte_140177432, 40h
0x1401b515d  jz      loc_1401B5533
0x1401b5163  mov     rax, [rbx+38h]
0x1401b5167  test    rax, rax
0x1401b516a  jz      short loc_1401B5170
0x1401b516c  mov     ecx, [rax]
0x1401b516e  jmp     short loc_1401B5172
0x1401b5170  xor     ecx, ecx
0x1401b5172  mov     eax, [rbx+30h]
0x1401b5175  lea     r8, [rbp+var_18]
0x1401b5179  mov     [rsp+80h+var_58], eax
0x1401b517d  mov     r9, rbx
0x1401b5180  mov     [rsp+80h+var_60], ecx
0x1401b5184  call    McTemplateK0pqd_EtwWriteTransfer
0x1401b5189  jmp     loc_1401B5533
0x1401b518e  test    cs:byte_140177432, 20h
0x1401b5195  jz      loc_1401B5533
0x1401b519b  mov     eax, [rbx+30h]
0x1401b519e  lea     rdx, EventPnpRequestComplete
0x1401b51a5  mov     [rsp+80h+var_60], eax
0x1401b51a9  jmp     loc_1401B5527
0x1401b51ae  cmp     cs:byte_140177431, 0
0x1401b51b5  jge     loc_1401B5533
0x1401b51bb  mov     rdx, [rdx+8]
0x1401b51bf  movzx   eax, byte ptr [rdx+2]
0x1401b51c3  cmp     al, 28h ; '('
0x1401b51c5  jnz     loc_1401B52AE
0x1401b51cb  cmp     dword ptr [rdx+14h], 0
0x1401b51cf  jnz     loc_1401B5533
0x1401b51d5  mov     r12d, [rdx+38h]
0x1401b51d9  test    r12d, r12d
0x1401b51dc  jz      loc_1401B5533
0x1401b51e2  xor     r11b, r11b
0x1401b51e5  xor     r10d, r10d
0x1401b51e8  xor     r15b, r15b
0x1401b51eb  xor     r9d, r9d
0x1401b51ee  xor     r14d, r14d
0x1401b51f1  xor     r13b, r13b
0x1401b51f4  mov     ecx, [rdx+r14*4+78h]
0x1401b51f9  cmp     ecx, 80h
0x1401b51ff  jb      short loc_1401B5274
0x1401b5201  mov     esi, [rdx+10h]
0x1401b5204  cmp     ecx, esi
0x1401b5206  jnb     short loc_1401B5274
0x1401b5208  mov     r8d, ecx
0x1401b520b  mov     ecx, [rcx+rdx]
0x1401b520e  sub     ecx, 40h ; '@'
0x1401b5211  jz      short loc_1401B5266
0x1401b5213  sub     ecx, edi
0x1401b5215  jz      short loc_1401B523A
0x1401b5217  cmp     ecx, edi
0x1401b5219  jnz     short loc_1401B526F
0x1401b521b  lea     rcx, [r8+28h]
0x1401b521f  cmp     rcx, rsi
0x1401b5222  ja      short loc_1401B526F
0x1401b5224  cmp     dword ptr [r8+rdx+0Ch], 0
0x1401b522a  jbe     short loc_1401B5233
0x1401b522c  lea     r10, [rdx+20h]
0x1401b5230  add     r10, r8
0x1401b5233  mov     r9, [r8+rdx+18h]
0x1401b5238  jmp     short loc_1401B5296
0x1401b523a  lea     rcx, [r8+38h]
0x1401b523e  cmp     rcx, rsi
0x1401b5241  ja      short loc_1401B526F
0x1401b5243  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401b5249  mov     r13b, dil
0x1401b524c  jbe     short loc_1401B5255
0x1401b524e  lea     r10, [rdx+18h]
0x1401b5252  add     r10, r8
0x1401b5255  mov     r15b, [r8+rdx+8]
0x1401b525a  mov     r9, [r8+rdx+10h]
0x1401b525f  mov     r11b, [r8+rdx+9]
0x1401b5264  jmp     short loc_1401B526F
0x1401b5266  lea     rcx, [r8+28h]
0x1401b526a  cmp     rcx, rsi
0x1401b526d  jbe     short loc_1401B5282
0x1401b526f  test    r13b, r13b
0x1401b5272  jnz     short loc_1401B52A0
0x1401b5274  add     r14d, edi
0x1401b5277  cmp     r14d, r12d
0x1401b527a  jb      loc_1401B51F4
0x1401b5280  jmp     short loc_1401B52A0
0x1401b5282  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401b5288  jbe     short loc_1401B5291
0x1401b528a  lea     r10, [rdx+18h]
0x1401b528e  add     r10, r8
0x1401b5291  mov     r9, [r8+rdx+10h]
0x1401b5296  mov     r11b, [r8+rdx+9]
0x1401b529b  mov     r15b, [r8+rdx+8]
0x1401b52a0  test    r10, r10
0x1401b52a3  jz      loc_1401B5533
0x1401b52a9  mov     cl, [r10]
0x1401b52ac  jmp     short loc_1401B52C5
0x1401b52ae  mov     r15b, [rdx+4]
0x1401b52b2  mov     r11b, [rdx+0Bh]
0x1401b52b6  mov     r9, [rdx+20h]
0x1401b52ba  mov     cl, [rdx+48h]
0x1401b52bd  test    eax, eax
0x1401b52bf  jnz     loc_1401B5533
0x1401b52c5  sub     cl, 8
0x1401b52c8  test    cl, 5Dh
0x1401b52cb  jnz     loc_1401B5533
0x1401b52d1  mov     sil, [rdx+3]
0x1401b52d5  cmp     sil, dil
0x1401b52d8  jz      loc_1401B536B
0x1401b52de  test    r9, r9
0x1401b52e1  jz      loc_1401B536B
0x1401b52e7  test    r11b, r11b
0x1401b52ea  jz      short loc_1401B536B
0x1401b52ec  mov     al, [r9]
0x1401b52ef  xor     dl, dl
0x1401b52f1  and     al, 7Fh
0x1401b52f3  movzx   ecx, r11b
0x1401b52f7  sub     al, 72h ; 'r'
0x1401b52f9  xor     r10b, r10b
0x1401b52fc  xor     r8b, r8b
0x1401b52ff  add     rcx, r9
0x1401b5302  cmp     al, dil
0x1401b5305  lea     rax, [r9+8]
0x1401b5309  jbe     short loc_1401B534D
0x1401b530b  cmp     rax, rcx
0x1401b530e  ja      short loc_1401B5363
0x1401b5310  movzx   ecx, byte ptr [r9+7]
0x1401b5315  lea     r8, [r9+0Dh]
0x1401b5319  mov     dl, [r9+2]
0x1401b531d  add     ecx, 8
0x1401b5320  and     dl, 0Fh
0x1401b5323  movzx   eax, r11b
0x1401b5327  cmp     ecx, eax
0x1401b5329  cmovbe  eax, ecx
0x1401b532c  mov     ecx, eax
0x1401b532e  add     rcx, r9
0x1401b5331  cmp     r8, rcx
0x1401b5334  ja      short loc_1401B533A
0x1401b5336  mov     r10b, [r9+0Ch]
0x1401b533a  lea     rax, [r9+0Eh]
0x1401b533e  cmp     rax, rcx
0x1401b5341  ja      short loc_1401B5348
0x1401b5343  mov     r8b, [r8]
0x1401b5346  jmp     short loc_1401B5366
0x1401b5348  xor     r8b, r8b
0x1401b534b  jmp     short loc_1401B5366
0x1401b534d  cmp     rax, rcx
0x1401b5350  ja      short loc_1401B5363
0x1401b5352  mov     dl, [r9+1]
0x1401b5356  mov     r10b, [r9+2]
0x1401b535a  and     dl, 0Fh
0x1401b535d  mov     r8b, [r9+3]
0x1401b5361  jmp     short loc_1401B5366
0x1401b5363  xor     dil, dil
0x1401b5366  test    dil, dil
0x1401b5369  jnz     short loc_1401B5373
0x1401b536b  xor     dl, dl
0x1401b536d  xor     r10b, r10b
0x1401b5370  xor     r8b, r8b
0x1401b5373  mov     eax, [rbx+30h]
0x1401b5376  mov     r9, rbx
0x1401b5379  mov     [rsp+80h+var_30], rbx
0x1401b537e  mov     [rsp+80h+var_38], r8b
0x1401b5383  lea     r8, [rbp+var_18]
0x1401b5387  mov     [rsp+80h+var_40], r10b
0x1401b538c  mov     [rsp+80h+var_48], dl
0x1401b5390  mov     [rsp+80h+var_50], r15b
0x1401b5395  mov     byte ptr [rsp+80h+var_58], sil
0x1401b539a  mov     [rsp+80h+var_60], eax
0x1401b539e  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x1401b53a3  jmp     loc_1401B5533
0x1401b53a8  test    cs:byte_140177432, 8
0x1401b53af  jz      loc_1401B5533
0x1401b53b5  mov     eax, [rbx+30h]
0x1401b53b8  mov     [rsp+80h+var_60], eax
0x1401b53bc  jmp     loc_1401B5520
0x1401b53c1  mov     ecx, [rcx]
0x1401b53c3  sub     ecx, 31h ; '1'
0x1401b53c6  jz      loc_1401B569A
0x1401b53cc  sub     ecx, edi
0x1401b53ce  jz      short loc_1401B53E1
0x1401b53d0  sub     ecx, 11h
0x1401b53d3  jz      loc_1401B569A
0x1401b53d9  cmp     ecx, edi
0x1401b53db  jnz     loc_1401B5991
0x1401b53e1  test    r8, r8
0x1401b53e4  jz      loc_1401B554C
0x1401b53ea  cmp     cs:StorEtwLoggingEnabled, 0
0x1401b53f1  mov     eax, 0C00000BBh
0x1401b53f6  mov     [rbp+var_20], eax
0x1401b53f9  mov     [rbx+30h], eax
0x1401b53fc  mov     qword ptr [rbx+38h], 0
0x1401b5404  mov     byte ptr [rbx+8Dh], 0ACh
0x1401b540b  jz      loc_1401B5533
0x1401b5411  xorps   xmm0, xmm0
0x1401b5414  lea     rdx, [rbp+var_18]
0x1401b5418  mov     rcx, rbx
0x1401b541b  movups  [rbp+var_18], xmm0
0x1401b541f  call    cs:__imp_IoGetActivityIdIrp
0x1401b5426  nop     dword ptr [rax+rax+00h]
0x1401b542b  mov     rdx, [rbx+0B8h]
0x1401b5432  movzx   eax, byte ptr [rdx]
0x1401b5435  sub     eax, 0Eh
0x1401b5438  jz      loc_1401B5510
0x1401b543e  sub     eax, edi
0x1401b5440  jnz     loc_1401B5141
0x1401b5446  cmp     cs:byte_140177431, al
0x1401b544c  jge     loc_1401B5533
0x1401b5452  mov     rdx, [rdx+8]
0x1401b5456  movzx   eax, byte ptr [rdx+2]
0x1401b545a  cmp     al, 28h ; '('
0x1401b545c  jnz     loc_1401B52AE
0x1401b5462  cmp     dword ptr [rdx+14h], 0
0x1401b5466  jnz     loc_1401B5533
0x1401b546c  mov     r12d, [rdx+38h]
0x1401b5470  test    r12d, r12d
0x1401b5473  jz      loc_1401B5533
0x1401b5479  xor     r11b, r11b
0x1401b547c  xor     r10d, r10d
0x1401b547f  xor     r15b, r15b
0x1401b5482  xor     r9d, r9d
0x1401b5485  xor     r14d, r14d
0x1401b5488  xor     r13b, r13b
0x1401b548b  mov     ecx, [rdx+r14*4+78h]
0x1401b5490  cmp     ecx, 80h
0x1401b5496  jb      short loc_1401B5503
0x1401b5498  mov     esi, [rdx+10h]
0x1401b549b  cmp     ecx, esi
0x1401b549d  jnb     short loc_1401B5503
0x1401b549f  mov     r8d, ecx
0x1401b54a2  mov     ecx, [rcx+rdx]
0x1401b54a5  sub     ecx, 40h ; '@'
0x1401b54a8  jz      short loc_1401B54ED
0x1401b54aa  sub     ecx, edi
0x1401b54ac  jz      short loc_1401B54C1
0x1401b54ae  cmp     ecx, edi
0x1401b54b0  jnz     short loc_1401B54FA
0x1401b54b2  lea     rcx, [r8+28h]
0x1401b54b6  cmp     rcx, rsi
0x1401b54b9  jbe     loc_1401B5224
0x1401b54bf  jmp     short loc_1401B54FA
0x1401b54c1  lea     rcx, [r8+38h]
0x1401b54c5  cmp     rcx, rsi
0x1401b54c8  ja      short loc_1401B54FA
0x1401b54ca  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401b54d0  mov     r13b, dil
0x1401b54d3  jbe     short loc_1401B54DC
0x1401b54d5  lea     r10, [rdx+18h]
0x1401b54d9  add     r10, r8
  ... truncated ...
```
