# NvmeNamespaceTelemetryIdIoctl

- ea: `0x14012a564`
- end: `0x14012b1fc`
- name: `NvmeNamespaceTelemetryIdIoctl`
- size: `3224`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1401c36a8`

## callees

- `0x140046c60`
- `0x140054800`
- `0x14006d1c0`
- `0x14006d298`
- `0x14007d330`
- `0x1400848c4`
- `0x14012a564`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14012abf1`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14012abf1`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14012a5e2`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14012a8c7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14012ac24`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14012af0c`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14012a5e2`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14012a8c7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14012ac24`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14012af0c`
- `ntoskrnl!IofCompleteRequest` at `0x14012a9ef`
- `ntoskrnl!IofCompleteRequest` at `0x14012aecd`
- `ntoskrnl!IofCompleteRequest` at `0x14012b1c3`
- `ntoskrnl!IofCompleteRequest` at `0x14012a9ef`
- `ntoskrnl!IofCompleteRequest` at `0x14012aecd`
- `ntoskrnl!IofCompleteRequest` at `0x14012b1c3`
- `ntoskrnl!RtlStringFromGUID` at `0x14012ab08`
- `ntoskrnl!RtlStringFromGUID` at `0x14012ab08`

## string_xrefs

- `0x14012abb5`: `Optimal write size`
- `0x14012ab9d`: `Optimal write granularity`
- `0x14012ab89`: `Optimal write alignment`

## pseudocode

```c
__int64 __fastcall NvmeNamespaceTelemetryIdIoctl(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  int v5; // esi
  bool v6; // zf
  unsigned __int64 v7; // rcx
  unsigned __int8 *v8; // rdx
  int v9; // eax
  int *v10; // rax
  __int64 v11; // rdx
  char v12; // bl
  int v13; // eax
  unsigned int v14; // r13d
  unsigned __int8 v15; // r10
  char *v16; // r11
  char v17; // di
  _BYTE *v18; // r9
  unsigned int v19; // r12d
  unsigned __int64 v20; // r15
  __int64 v21; // r8
  int v22; // ecx
  char v23; // cl
  char v24; // r15
  char v25; // r8
  char v26; // r11
  _BYTE *v27; // rax
  char *v28; // r8
  unsigned int v29; // eax
  unsigned int v30; // r13d
  unsigned int v31; // r12d
  unsigned __int64 v32; // r15
  int v33; // ecx
  __int64 v35; // rax
  __int64 v36; // r8
  int v37; // esi
  const GUID *v38; // rbx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // rax
  int v42; // ecx
  wchar_t *Buffer; // rdi
  char v44; // bl
  unsigned __int64 v45; // rcx
  __int64 v46; // rdx
  int *v47; // rax
  __int64 *v48; // rdx
  __int64 v49; // rdx
  unsigned int v50; // r13d
  unsigned __int8 v51; // r10
  char *v52; // r11
  char v53; // di
  _BYTE *v54; // r9
  unsigned int v55; // r12d
  unsigned __int64 v56; // r15
  __int64 v57; // r8
  int v58; // ecx
  char v59; // cl
  char v60; // r15
  char v61; // r11
  _BYTE *v62; // rax
  char v63; // r8
  char *v64; // r8
  unsigned int v65; // eax
  int v66; // esi
  unsigned __int64 v67; // rcx
  __int64 v68; // rdx
  int *v69; // rax
  __int64 v70; // rdx
  char v71; // bl
  unsigned int v72; // r13d
  unsigned __int8 v73; // r10
  char *v74; // r11
  char v75; // di
  _BYTE *v76; // r9
  unsigned int v77; // r12d
  unsigned __int64 v78; // r15
  __int64 v79; // r8
  int v80; // ecx
  char v81; // cl
  char v82; // r15
  char v83; // r11
  _BYTE *v84; // rax
  char v85; // r8
  char *v86; // r8
  unsigned int v87; // eax
  int v88; // [rsp+20h] [rbp-100h]
  char v89; // [rsp+A0h] [rbp-80h]
  char v90; // [rsp+A0h] [rbp-80h]
  char v91; // [rsp+A0h] [rbp-80h]
  char v92; // [rsp+A0h] [rbp-80h]
  unsigned int v93; // [rsp+A4h] [rbp-7Ch] BYREF
  int v94; // [rsp+A8h] [rbp-78h] BYREF
  int v95; // [rsp+ACh] [rbp-74h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+B0h] [rbp-70h] BYREF
  __int128 v97; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v98[16]; // [rsp+D0h] [rbp-50h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  GuidString = 0;
  if ( *(_DWORD *)(v2 + 16) >= 0x28u )
  {
    if ( *(_DWORD *)(v2 + 8) < 0x28u )
    {
      LOBYTE(v5) = 0;
      *(_BYTE *)(a2 + 141) = -84;
      v6 = StorEtwLoggingEnabled == 0;
      *(_QWORD *)(a2 + 56) = 0;
      v93 = -1073741789;
      *(_DWORD *)(a2 + 48) = -1073741789;
      if ( v6 )
        goto LABEL_91;
      v97 = 0;
      IoGetActivityIdIrp(a2, &v97);
      v8 = *(unsigned __int8 **)(a2 + 184);
      if ( *v8 != 14 )
      {
        v9 = *v8 - 15;
        if ( *v8 != 15 )
        {
LABEL_5:
          if ( v9 == 12 )
          {
            if ( v8[1] != 7 || *((_DWORD *)v8 + 2) )
            {
              if ( (byte_140177432 & 0x20) != 0 )
                McTemplateK0pd_EtwWriteTransfer(v7, EventPnpRequestComplete, &v97, a2, *(_DWORD *)(a2 + 48));
            }
            else if ( (byte_140177432 & 0x40) != 0 )
            {
              v10 = *(int **)(a2 + 56);
              if ( v10 )
                v5 = *v10;
              McTemplateK0pqd_EtwWriteTransfer(v7, (_DWORD)v8, (unsigned int)&v97, a2, v5, *(_DWORD *)(a2 + 48));
            }
          }
          goto LABEL_91;
        }
        if ( byte_140177431 >= 0 )
          goto LABEL_91;
        v11 = *((_QWORD *)v8 + 1);
        v12 = 1;
        v13 = *(unsigned __int8 *)(v11 + 2);
        if ( (_BYTE)v13 == 40 )
        {
          if ( *(_DWORD *)(v11 + 20) )
            goto LABEL_91;
          v30 = *(_DWORD *)(v11 + 56);
          if ( !v30 )
            goto LABEL_91;
          v15 = 0;
          v90 = 0;
          v16 = 0;
          v17 = 0;
          v18 = 0;
          v31 = 0;
          while ( 1 )
          {
            v7 = *(unsigned int *)(v11 + 4LL * v31 + 120);
            if ( (unsigned int)v7 >= 0x80 )
            {
              v32 = *(unsigned int *)(v11 + 16);
              if ( (unsigned int)v7 < (unsigned int)v32 )
              {
                v21 = (unsigned int)v7;
                v33 = *(_DWORD *)(v7 + v11) - 64;
                if ( v33 )
                {
                  LODWORD(v7) = v33 - 1;
                  if ( (_DWORD)v7 )
                  {
                    if ( (_DWORD)v7 == 1 )
                    {
                      LODWORD(v7) = v21 + 40;
                      if ( v21 + 40 <= v32 )
                      {
LABEL_25:
                        if ( *(_DWORD *)(v21 + v11 + 12) )
                          v16 = (char *)(v21 + v11 + 32);
                        v18 = *(_BYTE **)(v21 + v11 + 24);
                        goto LABEL_39;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v7) = v21 + 56;
                    if ( v21 + 56 <= v32 )
                    {
                      v90 = 1;
                      if ( *(_BYTE *)(v21 + v11 + 10) )
                        v16 = (char *)(v21 + v11 + 24);
                      v17 = *(_BYTE *)(v21 + v11 + 8);
                      v18 = *(_BYTE **)(v21 + v11 + 16);
                      v15 = *(_BYTE *)(v21 + v11 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v7) = v21 + 40;
                  if ( v21 + 40 <= v32 )
                  {
LABEL_36:
                    if ( *(_BYTE *)(v21 + v11 + 10) )
                      v16 = (char *)(v21 + v11 + 24);
                    v18 = *(_BYTE **)(v21 + v11 + 16);
LABEL_39:
                    v15 = *(_BYTE *)(v21 + v11 + 9);
                    v17 = *(_BYTE *)(v21 + v11 + 8);
LABEL_40:
                    if ( v16 )
                    {
                      v23 = *v16;
                      goto LABEL_43;
                    }
                    goto LABEL_91;
                  }
                }
                if ( v90 )
                  goto LABEL_40;
              }
            }
            if ( ++v31 >= v30 )
              goto LABEL_40;
          }
        }
        goto LABEL_42;
      }
      if ( (byte_140177432 & 8) == 0 )
        goto LABEL_91;
      v7 = *(unsigned int *)(a2 + 48);
      v88 = *(_DWORD *)(a2 + 48);
LABEL_90:
      McTemplateK0pd_EtwWriteTransfer(v7, EventNonReadWriteRequestComplete, &v97, a2, v88);
      goto LABEL_91;
    }
    v35 = *(_QWORD *)(a2 + 24);
    if ( *(_DWORD *)v35 == 40 && *(_DWORD *)(v35 + 4) == 40 )
    {
      v36 = *(_QWORD *)(a1 + 16);
      LOBYTE(v37) = 0;
      v38 = (const GUID *)(a1 + 160);
      *(_OWORD *)(a1 + 160) = *(_OWORD *)(v35 + 8);
      *(_OWORD *)(v35 + 24) = *(_OWORD *)(*(_QWORD *)(v36 + 128) + 1048LL);
      *(_QWORD *)(a2 + 56) = 40;
      if ( (unsigned int)dword_140176178 > 5 && (unsigned __int8)tlgKeywordOn(a1, 0x400000000000LL) )
      {
        *(_QWORD *)&v97 = 0x1000000;
        v98[4] = (__int64)&v97;
        v93 = *(_DWORD *)(a1 + 56);
        v98[10] = (__int64)&v93;
        v41 = *(_QWORD *)(v39 + 128);
        v98[5] = 8;
        v98[6] = v40;
        v98[7] = 16;
        v98[8] = (__int64)v38;
        v98[9] = 16;
        v98[11] = 4;
        v42 = *(_DWORD *)(v41 + 56);
        v98[12] = (__int64)&v94;
        v95 = *(unsigned __int16 *)(v39 + 4);
        v98[14] = (__int64)&v95;
        v94 = v42;
        v98[13] = 4;
        v98[15] = 4;
        tlgWriteTransfer_EtwWriteTransfer(v42, (int)&dword_1401694AC, v39, v40, 8u, (__int64)v98);
      }
      RtlStringFromGUID(v38, &GuidString);
      Buffer = (wchar_t *)&word_140155F3C;
      if ( GuidString.Buffer )
        Buffer = GuidString.Buffer;
      v44 = 1;
      StorEtwNvmeNamespaceEvent(
        a1,
        1,
        4,
        (unsigned int)L"NVMe namespace identification",
        (__int64)Buffer,
        *(_DWORD *)(a1 + 68),
        (__int64)L"Optimal IO boundary",
        *(_DWORD *)(a1 + 428),
        (__int64)L"Optimal write size",
        *(_DWORD *)(a1 + 72),
        (__int64)L"Optimal write granularity",
        *(_DWORD *)(a1 + 76),
        (__int64)L"Optimal write alignment",
        *(_DWORD *)(a1 + 80),
        (__int64)L"Deallocate granularity in blocks",
        *(_DWORD *)(a1 + 84),
        (__int64)L"Deallocate alignment in blocks",
        *(_DWORD *)(a1 + 88),
        (__int64)L"Logical block size",
        *(_DWORD *)(a1 + 64));
      RtlFreeUnicodeString(&GuidString);
      v6 = StorEtwLoggingEnabled == 0;
      *(_BYTE *)(a2 + 141) = -84;
      *(_DWORD *)(a2 + 48) = 0;
      if ( v6 )
        goto LABEL_162;
      v97 = 0;
      IoGetActivityIdIrp(a2, &v97);
      v46 = *(_QWORD *)(a2 + 184);
      if ( *(_BYTE *)v46 == 14 )
      {
        if ( (byte_140177432 & 8) == 0 )
          goto LABEL_162;
        v48 = EventNonReadWriteRequestComplete;
        goto LABEL_161;
      }
      if ( *(_BYTE *)v46 != 15 )
      {
        if ( *(_BYTE *)v46 != 27 )
          goto LABEL_162;
        if ( *(_BYTE *)(v46 + 1) == 7 && !*(_DWORD *)(v46 + 8) )
        {
          if ( (byte_140177432 & 0x40) != 0 )
          {
            v47 = *(int **)(a2 + 56);
            if ( v47 )
              v37 = *v47;
            McTemplateK0pqd_EtwWriteTransfer(v45, v46, (unsigned int)&v97, a2, v37, *(_DWORD *)(a2 + 48));
          }
          goto LABEL_162;
        }
        if ( (byte_140177432 & 0x20) == 0 )
          goto LABEL_162;
        v48 = EventPnpRequestComplete;
LABEL_161:
        McTemplateK0pd_EtwWriteTransfer(v45, v48, &v97, a2, *(_DWORD *)(a2 + 48));
        goto LABEL_162;
      }
      if ( byte_140177431 >= 0 )
        goto LABEL_162;
      v49 = *(_QWORD *)(v46 + 8);
      if ( *(_BYTE *)(v49 + 2) == 40 )
      {
        if ( *(_DWORD *)(v49 + 20) )
          goto LABEL_162;
        v50 = *(_DWORD *)(v49 + 56);
        if ( !v50 )
          goto LABEL_162;
        v51 = 0;
        v91 = 0;
        v52 = 0;
        v53 = 0;
        v54 = 0;
        v55 = 0;
        while ( 1 )
        {
          v45 = *(unsigned int *)(v49 + 4LL * v55 + 120);
          if ( (unsigned int)v45 >= 0x80 )
          {
            v56 = *(unsigned int *)(v49 + 16);
            if ( (unsigned int)v45 < (unsigned int)v56 )
            {
              v57 = (unsigned int)v45;
              v58 = *(_DWORD *)(v45 + v49) - 64;
              if ( v58 )
              {
                LODWORD(v45) = v58 - 1;
                if ( (_DWORD)v45 )
                {
                  if ( (_DWORD)v45 == 1 )
                  {
                    LODWORD(v45) = v57 + 40;
                    if ( v57 + 40 <= v56 )
                    {
                      if ( *(_DWORD *)(v57 + v49 + 12) )
                        v52 = (char *)(v57 + v49 + 32);
                      v54 = *(_BYTE **)(v57 + v49 + 24);
                      goto LABEL_136;
                    }
                  }
                }
                else
                {
                  LODWORD(v45) = v57 + 56;
                  if ( v57 + 56 <= v56 )
                  {
                    v91 = 1;
                    if ( *(_BYTE *)(v57 + v49 + 10) )
                      v52 = (char *)(v57 + v49 + 24);
                    v53 = *(_BYTE *)(v57 + v49 + 8);
                    v54 = *(_BYTE **)(v57 + v49 + 16);
                    v51 = *(_BYTE *)(v57 + v49 + 9);
                  }
                }
              }
              else
              {
                LODWORD(v45) = v57 + 40;
                if ( v57 + 40 <= v56 )
                {
                  if ( *(_BYTE *)(v57 + v49 + 10) )
                    v52 = (char *)(v57 + v49 + 24);
                  v54 = *(_BYTE **)(v57 + v49 + 16);
LABEL_136:
                  v51 = *(_BYTE *)(v57 + v49 + 9);
                  v53 = *(_BYTE *)(v57 + v49 + 8);
LABEL_137:
                  if ( v52 )
                  {
                    v59 = *v52;
                    goto LABEL_140;
                  }
                  goto LABEL_162;
                }
              }
              if ( v91 )
                goto LABEL_137;
            }
          }
          if ( ++v55 >= v50 )
            goto LABEL_137;
        }
      }
      v59 = *(_BYTE *)(v49 + 72);
      v54 = *(_BYTE **)(v49 + 32);
      v51 = *(_BYTE *)(v49 + 11);
      v53 = *(_BYTE *)(v49 + 4);
      if ( *(_BYTE *)(v49 + 2) )
        goto LABEL_162;
LABEL_140:
      LOBYTE(v45) = v59 - 8;
      if ( (v45 & 0x5D) != 0 )
      {
LABEL_162:
        IofCompleteRequest((PIRP)a2, 0);
        return 0;
      }
      v60 = *(_BYTE *)(v49 + 3);
      if ( v60 == 1 || !v54 || !v51 )
        goto LABEL_157;
      LOBYTE(v49) = 0;
      v45 = (unsigned __int64)&v54[v51];
      v61 = 0;
      v62 = v54 + 8;
      v63 = 0;
      if ( (unsigned __int8)((*v54 & 0x7F) - 114) <= 1u )
      {
        if ( (unsigned __int64)v62 <= v45 )
        {
          v61 = v54[2];
          LOBYTE(v49) = v54[1] & 0xF;
          v63 = v54[3];
          goto LABEL_156;
        }
      }
      else if ( (unsigned __int64)v62 <= v45 )
      {
        v64 = v54 + 13;
        LOBYTE(v49) = v54[2] & 0xF;
        v65 = v51;
        if ( (unsigned int)(unsigned __int8)v54[7] + 8 <= v51 )
          v65 = (unsigned __int8)v54[7] + 8;
        v45 = (unsigned __int64)&v54[v65];
        if ( (unsigned __int64)v64 <= v45 )
          v61 = v54[12];
        if ( (unsigned __int64)(v54 + 14) > v45 )
          v63 = 0;
        else
          v63 = *v64;
LABEL_156:
        if ( v44 )
        {
LABEL_158:
          McTemplateK0pduuuuup_EtwWriteTransfer(
            v45,
            v49,
            (unsigned int)&v97,
            a2,
            *(_DWORD *)(a2 + 48),
            v60,
            v53,
            v49,
            v61,
            v63,
            a2);
          goto LABEL_162;
        }
LABEL_157:
        LOBYTE(v49) = 0;
        v61 = 0;
        v63 = 0;
        goto LABEL_158;
      }
      v44 = 0;
      goto LABEL_156;
    }
    LOBYTE(v66) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    v6 = StorEtwLoggingEnabled == 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_DWORD *)(a2 + 48) = -1073741811;
    if ( v6 )
      goto LABEL_225;
    v97 = 0;
    IoGetActivityIdIrp(a2, &v97);
    v68 = *(_QWORD *)(a2 + 184);
    if ( *(_BYTE *)v68 == 14 )
    {
      if ( (byte_140177432 & 8) != 0 )
        McTemplateK0pd_EtwWriteTransfer(
          *(unsigned int *)(a2 + 48),
          EventNonReadWriteRequestComplete,
          &v97,
          a2,
          *(_DWORD *)(a2 + 48));
      goto LABEL_225;
    }
    if ( *(_BYTE *)v68 != 15 )
    {
      if ( *(_BYTE *)v68 == 27 )
      {
        if ( *(_BYTE *)(v68 + 1) != 7 || *(_DWORD *)(v68 + 8) )
        {
          if ( (byte_140177432 & 0x20) != 0 )
            McTemplateK0pd_EtwWriteTransfer(v67, EventPnpRequestComplete, &v97, a2, *(_DWORD *)(a2 + 48));
        }
        else if ( (byte_140177432 & 0x40) != 0 )
        {
          v69 = *(int **)(a2 + 56);
          if ( v69 )
            v66 = *v69;
          McTemplateK0pqd_EtwWriteTransfer(v67, v68, (unsigned int)&v97, a2, v66, *(_DWORD *)(a2 + 48));
        }
      }
      goto LABEL_225;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_225;
    v70 = *(_QWORD *)(v68 + 8);
    v71 = 1;
    if ( *(_BYTE *)(v70 + 2) == 40 )
    {
      if ( *(_DWORD *)(v70 + 20) )
        goto LABEL_225;
      v72 = *(_DWORD *)(v70 + 56);
      if ( !v72 )
        goto LABEL_225;
      v73 = 0;
      v92 = 0;
      v74 = 0;
      v75 = 0;
      v76 = 0;
      v77 = 0;
      while ( 1 )
      {
        v67 = *(unsigned int *)(v70 + 4LL * v77 + 120);
        if ( (unsigned int)v67 >= 0x80 )
        {
          v78 = *(unsigned int *)(v70 + 16);
          if ( (unsigned int)v67 < (unsigned int)v78 )
          {
            v79 = (unsigned int)v67;
            v80 = *(_DWORD *)(v70 + v67) - 64;
            if ( v80 )
            {
              LODWORD(v67) = v80 - 1;
              if ( (_DWORD)v67 )
              {
                if ( (_DWORD)v67 == 1 )
                {
                  LODWORD(v67) = v79 + 40;
                  if ( v79 + 40 <= v78 )
                  {
                    if ( *(_DWORD *)(v70 + v79 + 12) )
                      v74 = (char *)(v79 + v70 + 32);
                    v76 = *(_BYTE **)(v70 + v79 + 24);
                    goto LABEL_200;
                  }
                }
              }
              else
              {
                LODWORD(v67) = v79 + 56;
                if ( v79 + 56 <= v78 )
                {
                  v92 = 1;
                  if ( *(_BYTE *)(v70 + v79 + 10) )
                    v74 = (char *)(v79 + v70 + 24);
                  v75 = *(_BYTE *)(v70 + v79 + 8);
                  v76 = *(_BYTE **)(v70 + v79 + 16);
                  v73 = *(_BYTE *)(v70 + v79 + 9);
                }
              }
            }
            else
            {
              LODWORD(v67) = v79 + 40;
              if ( v79 + 40 <= v78 )
              {
                if ( *(_BYTE *)(v70 + v79 + 10) )
                  v74 = (char *)(v79 + v70 + 24);
                v76 = *(_BYTE **)(v70 + v79 + 16);
LABEL_200:
                v73 = *(_BYTE *)(v70 + v79 + 9);
                v75 = *(_BYTE *)(v70 + v79 + 8);
LABEL_201:
                if ( v74 )
                {
                  v81 = *v74;
                  goto LABEL_204;
                }
                goto LABEL_225;
              }
            }
            if ( v92 )
              goto LABEL_201;
          }
        }
        if ( ++v77 >= v72 )
          goto LABEL_201;
      }
    }
    v81 = *(_BYTE *)(v70 + 72);
    v76 = *(_BYTE **)(v70 + 32);
    v73 = *(_BYTE *)(v70 + 11);
    v75 = *(_BYTE *)(v70 + 4);
    if ( *(_BYTE *)(v70 + 2) )
      goto LABEL_225;
LABEL_204:
    LOBYTE(v67) = v81 - 8;
    if ( (v67 & 0x5D) != 0 )
    {
LABEL_225:
      IofCompleteRequest((PIRP)a2, 0);
      return 3221225485LL;
    }
    v82 = *(_BYTE *)(v70 + 3);
    if ( v82 == 1 || !v76 || !v73 )
      goto LABEL_221;
    LOBYTE(v70) = 0;
    v67 = (unsigned __int64)&v76[v73];
    v83 = 0;
    v84 = v76 + 8;
    v85 = 0;
    if ( (unsigned __int8)((*v76 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v84 <= v67 )
      {
        v83 = v76[2];
        LOBYTE(v70) = v76[1] & 0xF;
        v85 = v76[3];
        goto LABEL_220;
      }
    }
    else if ( (unsigned __int64)v84 <= v67 )
    {
      v86 = v76 + 13;
      LOBYTE(v70) = v76[2] & 0xF;
      v87 = v73;
      if ( (unsigned int)(unsigned __int8)v76[7] + 8 <= v73 )
        v87 = (unsigned __int8)v76[7] + 8;
      v67 = (unsigned __int64)&v76[v87];
      if ( (unsigned __int64)v86 <= v67 )
        v83 = v76[12];
      if ( (unsigned __int64)(v76 + 14) > v67 )
        v85 = 0;
      else
        v85 = *v86;
LABEL_220:
      if ( v71 )
      {
LABEL_222:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v67,
          v70,
          (unsigned int)&v97,
          a2,
          *(_DWORD *)(a2 + 48),
          v82,
          v75,
          v70,
          v83,
          v85,
          a2);
        goto LABEL_225;
      }
LABEL_221:
      LOBYTE(v70) = 0;
      v83 = 0;
      v85 = 0;
      goto LABEL_222;
    }
    v71 = 0;
    goto LABEL_220;
  }
  LOBYTE(v5) = 0;
  *(_BYTE *)(a2 + 141) = -84;
  v6 = StorEtwLoggingEnabled == 0;
  *(_QWORD *)(a2 + 56) = 0;
  v93 = -1073741820;
  *(_DWORD *)(a2 + 48) = -1073741820;
  if ( v6 )
    goto LABEL_91;
  v97 = 0;
  IoGetActivityIdIrp(a2, &v97);
  v8 = *(unsigned __int8 **)(a2 + 184);
  if ( *v8 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_91;
    v88 = *(_DWORD *)(a2 + 48);
    goto LABEL_90;
  }
  v9 = *v8 - 15;
  if ( *v8 != 15 )
    goto LABEL_5;
  if ( byte_140177431 >= 0 )
    goto LABEL_91;
  v11 = *((_QWORD *)v8 + 1);
  v12 = 1;
  v13 = *(unsigned __int8 *)(v11 + 2);
  if ( (_BYTE)v13 == 40 )
  {
    if ( !*(_DWORD *)(v11 + 20) )
    {
      v14 = *(_DWORD *)(v11 + 56);
      if ( v14 )
      {
        v15 = 0;
        v89 = 0;
        v16 = 0;
        v17 = 0;
        v18 = 0;
        v19 = 0;
        while ( 1 )
        {
          v7 = *(unsigned int *)(v11 + 4LL * v19 + 120);
          if ( (unsigned int)v7 >= 0x80 )
          {
            v20 = *(unsigned int *)(v11 + 16);
            if ( (unsigned int)v7 < (unsigned int)v20 )
            {
              v21 = (unsigned int)v7;
              v22 = *(_DWORD *)(v7 + v11) - 64;
              if ( v22 )
              {
                LODWORD(v7) = v22 - 1;
                if ( (_DWORD)v7 )
                {
                  if ( (_DWORD)v7 == 1 )
                  {
                    LODWORD(v7) = v21 + 40;
                    if ( v21 + 40 <= v20 )
                      goto LABEL_25;
                  }
                }
                else
                {
                  LODWORD(v7) = v21 + 56;
                  if ( v21 + 56 <= v20 )
                  {
                    v89 = 1;
                    if ( *(_BYTE *)(v21 + v11 + 10) )
                      v16 = (char *)(v21 + v11 + 24);
                    v17 = *(_BYTE *)(v21 + v11 + 8);
                    v18 = *(_BYTE **)(v21 + v11 + 16);
                    v15 = *(_BYTE *)(v21 + v11 + 9);
                  }
                }
              }
              else
              {
                LODWORD(v7) = v21 + 40;
                if ( v21 + 40 <= v20 )
                  goto LABEL_36;
              }
              if ( v89 )
                goto LABEL_40;
            }
          }
          if ( ++v19 >= v14 )
            goto LABEL_40;
        }
      }
    }
    goto LABEL_91;
  }
LABEL_42:
  v17 = *(_BYTE *)(v11 + 4);
  v15 = *(_BYTE *)(v11 + 11);
  v18 = *(_BYTE **)(v11 + 32);
  v23 = *(_BYTE *)(v11 + 72);
  if ( v13 )
    goto LABEL_91;
LABEL_43:
  LOBYTE(v7) = v23 - 8;
  if ( (v7 & 0x5D) == 0 )
  {
    v24 = *(_BYTE *)(v11 + 3);
    if ( v24 == 1 || !v18 || !v15 )
      goto LABEL_60;
    v25 = 0;
    v7 = (unsigned __int64)&v18[v15];
    v26 = 0;
    v27 = v18 + 8;
    LOBYTE(v11) = 0;
    if ( (unsigned __int8)((*v18 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v27 <= v7 )
      {
        v26 = v18[2];
        LOBYTE(v11) = v18[1] & 0xF;
        v25 = v18[3];
        goto LABEL_59;
      }
    }
    else if ( (unsigned __int64)v27 <= v7 )
    {
      v28 = v18 + 13;
      LOBYTE(v11) = v18[2] & 0xF;
      v29 = v15;
      if ( (unsigned int)(unsigned __int8)v18[7] + 8 <= v15 )
        v29 = (unsigned __int8)v18[7] + 8;
      v7 = (unsigned __int64)&v18[v29];
      if ( (unsigned __int64)v28 <= v7 )
        v26 = v18[12];
      if ( (unsigned __int64)(v18 + 14) > v7 )
        v25 = 0;
      else
        v25 = *v28;
LABEL_59:
      if ( v12 )
      {
LABEL_61:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v7,
          v11,
          (unsigned int)&v97,
          a2,
          *(_DWORD *)(a2 + 48),
          v24,
          v17,
          v11,
          v26,
          v25,
          a2);
        goto LABEL_91;
      }
LABEL_60:
      LOBYTE(v11) = 0;
      v26 = 0;
      v25 = 0;
      goto LABEL_61;
    }
    v12 = 0;
    goto LABEL_59;
  }
LABEL_91:
  IofCompleteRequest((PIRP)a2, 0);
  return v93;
}

```

## disassembly

```asm
0x14012a564  mov     [rsp-8+arg_10], rbx
0x14012a569  push    rbp
0x14012a56a  push    rsi
0x14012a56b  push    rdi
0x14012a56c  push    r12
0x14012a56e  push    r13
0x14012a570  push    r14
0x14012a572  push    r15
0x14012a574  lea     rbp, [rsp-40h]
0x14012a579  sub     rsp, 160h
0x14012a580  mov     rax, cs:__security_cookie
0x14012a587  xor     rax, rsp
0x14012a58a  mov     [rbp+70h+var_40], rax
0x14012a58e  mov     rax, [rdx+0B8h]
0x14012a595  xorps   xmm0, xmm0
0x14012a598  mov     r12d, 28h ; '('
0x14012a59e  mov     r14, rdx
0x14012a5a1  movups  xmmword ptr [rbp+70h+GuidString.Length], xmm0
0x14012a5a5  mov     r15, rcx
0x14012a5a8  cmp     [rax+10h], r12d
0x14012a5ac  jnb     loc_14012A88D
0x14012a5b2  xor     esi, esi
0x14012a5b4  mov     byte ptr [rdx+8Dh], 0ACh
0x14012a5bb  cmp     cs:StorEtwLoggingEnabled, sil
0x14012a5c2  mov     eax, 0C0000004h
0x14012a5c7  mov     [rdx+38h], rsi
0x14012a5cb  mov     [rbp+70h+var_EC], eax
0x14012a5ce  mov     [rdx+30h], eax
0x14012a5d1  jz      loc_14012A9EA
0x14012a5d7  lea     rdx, [rbp+70h+var_D0]
0x14012a5db  mov     rcx, r14
0x14012a5de  movups  [rbp+70h+var_D0], xmm0
0x14012a5e2  call    cs:__imp_IoGetActivityIdIrp
0x14012a5e9  nop     dword ptr [rax+rax+00h]
0x14012a5ee  mov     rdx, [r14+0B8h]
0x14012a5f5  movzx   eax, byte ptr [rdx]
0x14012a5f8  sub     eax, 0Eh
0x14012a5fb  jz      loc_14012A873
0x14012a601  sub     eax, 1
0x14012a604  jz      short loc_14012A670
0x14012a606  cmp     eax, 0Ch
0x14012a609  jnz     loc_14012A9EA
0x14012a60f  cmp     byte ptr [rdx+1], 7
0x14012a613  jnz     short loc_14012A64F
0x14012a615  cmp     [rdx+8], esi
0x14012a618  jnz     short loc_14012A64F
0x14012a61a  test    cs:byte_140177432, 40h
0x14012a621  jz      loc_14012A9EA
0x14012a627  mov     rax, [r14+38h]
0x14012a62b  test    rax, rax
0x14012a62e  jz      short loc_14012A632
0x14012a630  mov     esi, [rax]
0x14012a632  mov     eax, [r14+30h]
0x14012a636  lea     r8, [rbp+70h+var_D0]
0x14012a63a  mov     dword ptr [rsp+190h+var_168], eax
0x14012a63e  mov     r9, r14
0x14012a641  mov     [rsp+190h+var_170], esi
0x14012a645  call    McTemplateK0pqd_EtwWriteTransfer
0x14012a64a  jmp     loc_14012A9EA
0x14012a64f  test    cs:byte_140177432, 20h
0x14012a656  jz      loc_14012A9EA
0x14012a65c  mov     eax, [r14+30h]
0x14012a660  lea     rdx, EventPnpRequestComplete
0x14012a667  mov     [rsp+190h+var_170], eax
0x14012a66b  jmp     loc_14012A9DE
0x14012a670  cmp     cs:byte_140177431, sil
0x14012a677  jge     loc_14012A9EA
0x14012a67d  mov     rdx, [rdx+8]
0x14012a681  mov     ebx, 1
0x14012a686  movzx   eax, byte ptr [rdx+2]
0x14012a68a  cmp     al, r12b
0x14012a68d  jnz     loc_14012A778
0x14012a693  cmp     [rdx+14h], esi
0x14012a696  jnz     loc_14012A9EA
0x14012a69c  mov     r13d, [rdx+38h]
0x14012a6a0  test    r13d, r13d
0x14012a6a3  jz      loc_14012A9EA
0x14012a6a9  mov     r10b, sil
0x14012a6ac  mov     [rbp+70h+var_F0], sil
0x14012a6b0  mov     r11, rsi
0x14012a6b3  mov     dil, sil
0x14012a6b6  mov     r9, rsi
0x14012a6b9  mov     r12d, esi
0x14012a6bc  mov     eax, r12d
0x14012a6bf  mov     ecx, [rdx+rax*4+78h]
0x14012a6c3  cmp     ecx, 80h
0x14012a6c9  jb      short loc_14012A73F
0x14012a6cb  mov     r15d, [rdx+10h]
0x14012a6cf  cmp     ecx, r15d
0x14012a6d2  jnb     short loc_14012A73F
0x14012a6d4  mov     r8d, ecx
0x14012a6d7  mov     ecx, [rcx+rdx]
0x14012a6da  sub     ecx, 40h ; '@'
0x14012a6dd  jz      short loc_14012A730
0x14012a6df  sub     ecx, ebx
0x14012a6e1  jz      short loc_14012A705
0x14012a6e3  cmp     ecx, ebx
0x14012a6e5  jnz     short loc_14012A739
0x14012a6e7  lea     rcx, [r8+28h]
0x14012a6eb  cmp     rcx, r15
0x14012a6ee  ja      short loc_14012A739
0x14012a6f0  cmp     [r8+rdx+0Ch], esi
0x14012a6f5  jbe     short loc_14012A6FE
0x14012a6f7  lea     r11, [rdx+20h]
0x14012a6fb  add     r11, r8
0x14012a6fe  mov     r9, [r8+rdx+18h]
0x14012a703  jmp     short loc_14012A760
0x14012a705  lea     rcx, [r8+38h]
0x14012a709  cmp     rcx, r15
0x14012a70c  ja      short loc_14012A739
0x14012a70e  mov     [rbp+70h+var_F0], bl
0x14012a711  cmp     [r8+rdx+0Ah], sil
0x14012a716  jbe     short loc_14012A71F
0x14012a718  lea     r11, [rdx+18h]
0x14012a71c  add     r11, r8
0x14012a71f  mov     dil, [r8+rdx+8]
0x14012a724  mov     r9, [r8+rdx+10h]
0x14012a729  mov     r10b, [r8+rdx+9]
0x14012a72e  jmp     short loc_14012A739
0x14012a730  lea     rcx, [r8+28h]
0x14012a734  cmp     rcx, r15
0x14012a737  jbe     short loc_14012A74D
0x14012a739  cmp     [rbp+70h+var_F0], sil
0x14012a73d  jnz     short loc_14012A76A
0x14012a73f  add     r12d, ebx
0x14012a742  cmp     r12d, r13d
0x14012a745  jb      loc_14012A6BC
0x14012a74b  jmp     short loc_14012A76A
0x14012a74d  cmp     [r8+rdx+0Ah], sil
0x14012a752  jbe     short loc_14012A75B
0x14012a754  lea     r11, [rdx+18h]
0x14012a758  add     r11, r8
0x14012a75b  mov     r9, [r8+rdx+10h]
0x14012a760  mov     r10b, [r8+rdx+9]
0x14012a765  mov     dil, [r8+rdx+8]
0x14012a76a  test    r11, r11
0x14012a76d  jz      loc_14012A9EA
0x14012a773  mov     cl, [r11]
0x14012a776  jmp     short loc_14012A78F
0x14012a778  mov     dil, [rdx+4]
0x14012a77c  mov     r10b, [rdx+0Bh]
0x14012a780  mov     r9, [rdx+20h]
0x14012a784  mov     cl, [rdx+48h]
0x14012a787  test    eax, eax
0x14012a789  jnz     loc_14012A9EA
0x14012a78f  sub     cl, 8
0x14012a792  test    cl, 5Dh
0x14012a795  jnz     loc_14012A9EA
0x14012a79b  mov     r15b, [rdx+3]
0x14012a79f  cmp     r15b, bl
0x14012a7a2  jz      loc_14012A834
0x14012a7a8  test    r9, r9
0x14012a7ab  jz      loc_14012A834
0x14012a7b1  test    r10b, r10b
0x14012a7b4  jz      short loc_14012A834
0x14012a7b6  mov     al, [r9]
0x14012a7b9  mov     r8b, sil
0x14012a7bc  and     al, 7Fh
0x14012a7be  movzx   ecx, r10b
0x14012a7c2  sub     al, 72h ; 'r'
0x14012a7c4  add     rcx, r9
0x14012a7c7  cmp     al, bl
0x14012a7c9  mov     r11b, sil
0x14012a7cc  lea     rax, [r9+8]
0x14012a7d0  mov     dl, sil
0x14012a7d3  jbe     short loc_14012A817
0x14012a7d5  cmp     rax, rcx
0x14012a7d8  ja      short loc_14012A82D
0x14012a7da  movzx   ecx, byte ptr [r9+7]
0x14012a7df  lea     r8, [r9+0Dh]
0x14012a7e3  mov     dl, [r9+2]
0x14012a7e7  add     ecx, 8
0x14012a7ea  and     dl, 0Fh
0x14012a7ed  movzx   eax, r10b
0x14012a7f1  cmp     ecx, eax
0x14012a7f3  cmovbe  eax, ecx
0x14012a7f6  mov     ecx, eax
0x14012a7f8  add     rcx, r9
0x14012a7fb  cmp     r8, rcx
0x14012a7fe  ja      short loc_14012A804
0x14012a800  mov     r11b, [r9+0Ch]
0x14012a804  lea     rax, [r9+0Eh]
0x14012a808  cmp     rax, rcx
0x14012a80b  ja      short loc_14012A812
0x14012a80d  mov     r8b, [r8]
0x14012a810  jmp     short loc_14012A830
0x14012a812  mov     r8b, sil
0x14012a815  jmp     short loc_14012A830
0x14012a817  cmp     rax, rcx
0x14012a81a  ja      short loc_14012A82D
0x14012a81c  mov     dl, [r9+1]
0x14012a820  mov     r11b, [r9+2]
0x14012a824  and     dl, 0Fh
0x14012a827  mov     r8b, [r9+3]
0x14012a82b  jmp     short loc_14012A830
0x14012a82d  mov     bl, sil
0x14012a830  test    bl, bl
0x14012a832  jnz     short loc_14012A83D
0x14012a834  mov     dl, sil
0x14012a837  mov     r11b, sil
0x14012a83a  mov     r8b, sil
0x14012a83d  mov     eax, [r14+30h]
0x14012a841  mov     r9, r14
0x14012a844  mov     [rsp+190h+var_140], r14
0x14012a849  mov     byte ptr [rsp+190h+var_148], r8b
0x14012a84e  lea     r8, [rbp+70h+var_D0]
0x14012a852  mov     byte ptr [rsp+190h+var_150], r11b
0x14012a857  mov     byte ptr [rsp+190h+var_158], dl
0x14012a85b  mov     byte ptr [rsp+190h+var_160], dil
0x14012a860  mov     byte ptr [rsp+190h+var_168], r15b
0x14012a865  mov     [rsp+190h+var_170], eax
0x14012a869  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x14012a86e  jmp     loc_14012A9EA
0x14012a873  test    cs:byte_140177432, 8
0x14012a87a  jz      loc_14012A9EA
0x14012a880  mov     eax, [r14+30h]
0x14012a884  mov     [rsp+190h+var_170], eax
0x14012a888  jmp     loc_14012A9D7
0x14012a88d  cmp     [rax+8], r12d
0x14012a891  jnb     loc_14012AA03
0x14012a897  xor     esi, esi
0x14012a899  mov     byte ptr [rdx+8Dh], 0ACh
0x14012a8a0  cmp     cs:StorEtwLoggingEnabled, sil
0x14012a8a7  mov     eax, 0C0000023h
0x14012a8ac  mov     [rdx+38h], rsi
0x14012a8b0  mov     [rbp+70h+var_EC], eax
0x14012a8b3  mov     [rdx+30h], eax
0x14012a8b6  jz      loc_14012A9EA
0x14012a8bc  lea     rdx, [rbp+70h+var_D0]
0x14012a8c0  mov     rcx, r14
0x14012a8c3  movups  [rbp+70h+var_D0], xmm0
0x14012a8c7  call    cs:__imp_IoGetActivityIdIrp
0x14012a8ce  nop     dword ptr [rax+rax+00h]
0x14012a8d3  mov     rdx, [r14+0B8h]
0x14012a8da  movzx   eax, byte ptr [rdx]
0x14012a8dd  sub     eax, 0Eh
0x14012a8e0  jz      loc_14012A9C6
0x14012a8e6  sub     eax, 1
0x14012a8e9  jnz     loc_14012A606
0x14012a8ef  cmp     cs:byte_140177431, sil
0x14012a8f6  jge     loc_14012A9EA
0x14012a8fc  mov     rdx, [rdx+8]
0x14012a900  lea     ebx, [rsi+1]
0x14012a903  movzx   eax, byte ptr [rdx+2]
0x14012a907  cmp     al, r12b
0x14012a90a  jnz     loc_14012A778
0x14012a910  cmp     [rdx+14h], esi
0x14012a913  jnz     loc_14012A9EA
0x14012a919  mov     r13d, [rdx+38h]
0x14012a91d  test    r13d, r13d
0x14012a920  jz      loc_14012A9EA
0x14012a926  mov     r10b, sil
0x14012a929  mov     [rbp+70h+var_F0], sil
0x14012a92d  mov     r11d, esi
0x14012a930  mov     dil, sil
0x14012a933  mov     r9d, esi
0x14012a936  mov     r12d, esi
0x14012a939  mov     eax, r12d
0x14012a93c  mov     ecx, [rdx+rax*4+78h]
0x14012a940  cmp     ecx, 80h
0x14012a946  jb      short loc_14012A9B5
0x14012a948  mov     r15d, [rdx+10h]
0x14012a94c  cmp     ecx, r15d
0x14012a94f  jnb     short loc_14012A9B5
0x14012a951  mov     r8d, ecx
0x14012a954  mov     ecx, [rcx+rdx]
0x14012a957  sub     ecx, 40h ; '@'
0x14012a95a  jz      short loc_14012A99E
0x14012a95c  sub     ecx, ebx
0x14012a95e  jz      short loc_14012A973
0x14012a960  cmp     ecx, ebx
0x14012a962  jnz     short loc_14012A9AB
0x14012a964  lea     rcx, [r8+28h]
0x14012a968  cmp     rcx, r15
0x14012a96b  jbe     loc_14012A6F0
0x14012a971  jmp     short loc_14012A9AB
0x14012a973  lea     rcx, [r8+38h]
0x14012a977  cmp     rcx, r15
0x14012a97a  ja      short loc_14012A9AB
0x14012a97c  mov     [rbp+70h+var_F0], bl
0x14012a97f  cmp     [r8+rdx+0Ah], sil
0x14012a984  jbe     short loc_14012A98D
0x14012a986  lea     r11, [rdx+18h]
0x14012a98a  add     r11, r8
0x14012a98d  mov     dil, [r8+rdx+8]
0x14012a992  mov     r9, [r8+rdx+10h]
0x14012a997  mov     r10b, [r8+rdx+9]
0x14012a99c  jmp     short loc_14012A9AB
0x14012a99e  lea     rcx, [r8+28h]
0x14012a9a2  cmp     rcx, r15
0x14012a9a5  jbe     loc_14012A74D
0x14012a9ab  cmp     [rbp+70h+var_F0], sil
0x14012a9af  jnz     loc_14012A76A
0x14012a9b5  add     r12d, ebx
0x14012a9b8  cmp     r12d, r13d
0x14012a9bb  jb      loc_14012A939
0x14012a9c1  jmp     loc_14012A76A
0x14012a9c6  test    cs:byte_140177432, 8
0x14012a9cd  jz      short loc_14012A9EA
0x14012a9cf  mov     ecx, [r14+30h]
  ... truncated ...
```
