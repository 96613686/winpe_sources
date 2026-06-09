# NvmeNamespaceStorageQueryDeviceLedStatePropertyIoctl

- ea: `0x1401893d4`
- end: `0x14018a1ae`
- name: `NvmeNamespaceStorageQueryDeviceLedStatePropertyIoctl`
- size: `3546`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140187e98`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400b31c4`
- `0x14014b400`
- `0x14014b800`
- `0x1401893d4`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14018945f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14018975f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140189a22`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140189daa`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14018a01f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14018945f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14018975f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140189a22`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140189daa`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14018a01f`
- `ntoskrnl!IofCompleteRequest` at `0x140189cd4`
- `ntoskrnl!IofCompleteRequest` at `0x14018a175`
- `ntoskrnl!IofCompleteRequest` at `0x140189cd4`
- `ntoskrnl!IofCompleteRequest` at `0x14018a175`

## pseudocode

```c
__int64 __fastcall NvmeNamespaceStorageQueryDeviceLedStatePropertyIoctl(__int64 a1, __int64 a2)
{
  int v2; // ebx
  __int64 v4; // r14
  _DWORD *v5; // rsi
  bool v6; // zf
  unsigned int v7; // r12d
  unsigned __int64 v8; // rcx
  unsigned __int8 *v9; // rdx
  int v10; // eax
  __int64 v11; // rdx
  char v12; // r8
  unsigned int v13; // r13d
  unsigned __int8 v14; // r11
  char *v15; // rsi
  char v16; // r12
  _BYTE *v17; // r10
  unsigned int v18; // r15d
  unsigned __int64 v19; // r14
  __int64 v20; // r9
  int v21; // ecx
  int *v22; // rax
  __int64 *v23; // rdx
  char v24; // cl
  char v25; // r14
  char v26; // si
  _BYTE *v27; // rax
  char v28; // r9
  char *v29; // r9
  unsigned int v30; // eax
  int v31; // ecx
  unsigned __int64 v32; // rcx
  unsigned __int8 *v33; // rdx
  int v34; // eax
  int *v35; // rax
  __int64 v36; // rdx
  char v37; // r8
  int v38; // eax
  unsigned int v39; // r13d
  unsigned __int8 v40; // r11
  char *v41; // rsi
  char v42; // r12
  _BYTE *v43; // r10
  unsigned int v44; // r15d
  unsigned __int64 v45; // r14
  __int64 v46; // r9
  int v47; // ecx
  char v48; // cl
  char v49; // r14
  char v50; // r9
  char v51; // si
  _BYTE *v52; // rax
  char *v53; // r9
  unsigned int v54; // eax
  unsigned __int64 v55; // rcx
  __int64 v56; // rdx
  int *v57; // rax
  int v58; // ecx
  __int64 *v59; // rdx
  __int64 v60; // rdx
  char v61; // r8
  unsigned int v62; // r13d
  unsigned __int8 v63; // r11
  char *v64; // rsi
  char v65; // r15
  _BYTE *v66; // r10
  unsigned int v67; // r12d
  unsigned __int64 v68; // r14
  __int64 v69; // r9
  int v70; // ecx
  char v71; // cl
  char v72; // r14
  char v73; // si
  _BYTE *v74; // rax
  char v75; // r9
  char *v76; // r9
  unsigned int v77; // eax
  size_t v79; // r15
  int LedState; // eax
  __int64 v81; // rdx
  char v82; // r8
  unsigned __int8 v83; // si
  char *v84; // r11
  char v85; // r13
  _BYTE *v86; // r10
  unsigned int v87; // r15d
  unsigned __int64 v88; // r14
  __int64 v89; // r9
  int v90; // ecx
  char v91; // cl
  char v92; // r14
  char v93; // r11
  _BYTE *v94; // rax
  char v95; // r9
  char *v96; // r9
  unsigned int v97; // eax
  unsigned int v98; // r13d
  unsigned int v99; // r15d
  unsigned __int64 v100; // r14
  __int64 v101; // r9
  int v102; // ecx
  int v103; // [rsp+20h] [rbp-60h]
  char v104; // [rsp+60h] [rbp-20h]
  char v105; // [rsp+60h] [rbp-20h]
  char v106; // [rsp+60h] [rbp-20h]
  char v107; // [rsp+60h] [rbp-20h]
  char v108; // [rsp+60h] [rbp-20h]
  unsigned int v109; // [rsp+64h] [rbp-1Ch]
  __int128 v110; // [rsp+68h] [rbp-18h] BYREF

  LOBYTE(v2) = 0;
  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 128LL);
  if ( (*(_DWORD *)(*(_QWORD *)(v4 + 408) + 184LL) & 0x40000000) == 0 )
  {
    v6 = StorEtwLoggingEnabled == 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = -1073741637;
    if ( v6 )
      goto LABEL_290;
    v110 = 0;
    IoGetActivityIdIrp(a2, &v110);
    v33 = *(unsigned __int8 **)(a2 + 184);
    if ( *v33 != 14 )
    {
      v34 = *v33 - 15;
      if ( *v33 != 15 )
      {
LABEL_69:
        if ( v34 == 12 )
        {
          if ( v33[1] != 7 || *((_DWORD *)v33 + 2) )
          {
            if ( (byte_140177432 & 0x20) != 0 )
              McTemplateK0pd_EtwWriteTransfer(v32, EventPnpRequestComplete, &v110, a2, *(_DWORD *)(a2 + 48));
          }
          else if ( (byte_140177432 & 0x40) != 0 )
          {
            v35 = *(int **)(a2 + 56);
            if ( v35 )
              v2 = *v35;
            McTemplateK0pqd_EtwWriteTransfer(v32, (_DWORD)v33, (unsigned int)&v110, a2, v2, *(_DWORD *)(a2 + 48));
          }
        }
        goto LABEL_290;
      }
      if ( byte_140177431 >= 0 )
        goto LABEL_290;
      v36 = *((_QWORD *)v33 + 1);
      v37 = 1;
      v38 = *(unsigned __int8 *)(v36 + 2);
      if ( (_BYTE)v38 == 40 )
      {
        if ( *(_DWORD *)(v36 + 20) )
          goto LABEL_290;
        v98 = *(_DWORD *)(v36 + 56);
        if ( !v98 )
          goto LABEL_290;
        v40 = 0;
        v108 = 0;
        v41 = 0;
        v42 = 0;
        v43 = 0;
        v99 = 0;
        while ( 1 )
        {
          v32 = *(unsigned int *)(v36 + 4LL * v99 + 120);
          if ( (unsigned int)v32 >= 0x80 )
          {
            v100 = *(unsigned int *)(v36 + 16);
            if ( (unsigned int)v32 < (unsigned int)v100 )
            {
              v101 = (unsigned int)v32;
              v102 = *(_DWORD *)(v32 + v36) - 64;
              if ( v102 )
              {
                LODWORD(v32) = v102 - 1;
                if ( (_DWORD)v32 )
                {
                  if ( (_DWORD)v32 == 1 )
                  {
                    LODWORD(v32) = v101 + 40;
                    if ( v101 + 40 <= v100 )
                    {
                      if ( *(_DWORD *)(v101 + v36 + 12) )
                        v41 = (char *)(v101 + v36 + 32);
                      v43 = *(_BYTE **)(v101 + v36 + 24);
LABEL_286:
                      v40 = *(_BYTE *)(v101 + v36 + 9);
                      v42 = *(_BYTE *)(v101 + v36 + 8);
                      goto LABEL_104;
                    }
                  }
                }
                else
                {
                  LODWORD(v32) = v101 + 56;
                  if ( v101 + 56 <= v100 )
                  {
                    v108 = 1;
                    if ( *(_BYTE *)(v101 + v36 + 10) )
                      v41 = (char *)(v101 + v36 + 24);
                    v42 = *(_BYTE *)(v101 + v36 + 8);
                    v43 = *(_BYTE **)(v101 + v36 + 16);
                    v40 = *(_BYTE *)(v101 + v36 + 9);
                  }
                }
              }
              else
              {
                LODWORD(v32) = v101 + 40;
                if ( v101 + 40 <= v100 )
                {
                  if ( *(_BYTE *)(v101 + v36 + 10) )
                    v41 = (char *)(v101 + v36 + 24);
                  v43 = *(_BYTE **)(v101 + v36 + 16);
                  goto LABEL_286;
                }
              }
              if ( v108 )
                goto LABEL_104;
            }
          }
          if ( ++v99 >= v98 )
            goto LABEL_104;
        }
      }
      goto LABEL_106;
    }
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_290;
    v32 = *(unsigned int *)(a2 + 48);
    v103 = *(_DWORD *)(a2 + 48);
LABEL_289:
    McTemplateK0pd_EtwWriteTransfer(v32, EventNonReadWriteRequestComplete, &v110, a2, v103);
    goto LABEL_290;
  }
  v5 = *(_DWORD **)(a2 + 24);
  if ( !v5 )
  {
    v6 = StorEtwLoggingEnabled == 0;
    v7 = -1073741811;
    *(_DWORD *)(a2 + 48) = -1073741811;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    if ( v6 )
      goto LABEL_193;
    v110 = 0;
    IoGetActivityIdIrp(a2, &v110);
    v9 = *(unsigned __int8 **)(a2 + 184);
    if ( *v9 != 14 )
    {
      v10 = *v9 - 15;
      if ( *v9 == 15 )
      {
        if ( byte_140177431 >= 0 )
          goto LABEL_193;
        v11 = *((_QWORD *)v9 + 1);
        v12 = 1;
        if ( *(_BYTE *)(v11 + 2) == 40 )
        {
          if ( !*(_DWORD *)(v11 + 20) )
          {
            v13 = *(_DWORD *)(v11 + 56);
            if ( v13 )
            {
              v14 = 0;
              v104 = 0;
              v15 = 0;
              v16 = 0;
              v17 = 0;
              v18 = 0;
              while ( 1 )
              {
                v8 = *(unsigned int *)(v11 + 4LL * v18 + 120);
                if ( (unsigned int)v8 >= 0x80 )
                {
                  v19 = *(unsigned int *)(v11 + 16);
                  if ( (unsigned int)v8 < (unsigned int)v19 )
                  {
                    v20 = (unsigned int)v8;
                    v21 = *(_DWORD *)(v8 + v11) - 64;
                    if ( v21 )
                    {
                      LODWORD(v8) = v21 - 1;
                      if ( (_DWORD)v8 )
                      {
                        if ( (_DWORD)v8 == 1 )
                        {
                          LODWORD(v8) = v20 + 40;
                          if ( v20 + 40 <= v19 )
                          {
                            if ( *(_DWORD *)(v20 + v11 + 12) )
                              v15 = (char *)(v20 + v11 + 32);
                            v17 = *(_BYTE **)(v20 + v11 + 24);
                            goto LABEL_38;
                          }
                        }
                      }
                      else
                      {
                        LODWORD(v8) = v20 + 56;
                        if ( v20 + 56 <= v19 )
                        {
                          v104 = 1;
                          if ( *(_BYTE *)(v20 + v11 + 10) )
                            v15 = (char *)(v20 + v11 + 24);
                          v16 = *(_BYTE *)(v20 + v11 + 8);
                          v17 = *(_BYTE **)(v20 + v11 + 16);
                          v14 = *(_BYTE *)(v20 + v11 + 9);
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v8) = v20 + 40;
                      if ( v20 + 40 <= v19 )
                      {
                        if ( *(_BYTE *)(v20 + v11 + 10) )
                          v15 = (char *)(v20 + v11 + 24);
                        v17 = *(_BYTE **)(v20 + v11 + 16);
LABEL_38:
                        v14 = *(_BYTE *)(v20 + v11 + 9);
                        v16 = *(_BYTE *)(v20 + v11 + 8);
LABEL_39:
                        if ( v15 )
                        {
                          v24 = *v15;
                          goto LABEL_42;
                        }
                        goto LABEL_61;
                      }
                    }
                    if ( v104 )
                      goto LABEL_39;
                  }
                }
                if ( ++v18 >= v13 )
                  goto LABEL_39;
              }
            }
          }
          goto LABEL_193;
        }
        v24 = *(_BYTE *)(v11 + 72);
        v17 = *(_BYTE **)(v11 + 32);
        v14 = *(_BYTE *)(v11 + 11);
        v16 = *(_BYTE *)(v11 + 4);
        if ( *(_BYTE *)(v11 + 2) )
          goto LABEL_61;
LABEL_42:
        LOBYTE(v8) = v24 - 8;
        if ( (v8 & 0x5D) != 0 )
        {
LABEL_61:
          v7 = -1073741811;
          goto LABEL_193;
        }
        v25 = *(_BYTE *)(v11 + 3);
        if ( v25 == 1 || !v17 || !v14 )
          goto LABEL_59;
        LOBYTE(v11) = 0;
        v8 = (unsigned __int64)&v17[v14];
        v26 = 0;
        v27 = v17 + 8;
        v28 = 0;
        if ( (unsigned __int8)((*v17 & 0x7F) - 114) <= 1u )
        {
          if ( (unsigned __int64)v27 <= v8 )
          {
            v26 = v17[2];
            LOBYTE(v11) = v17[1] & 0xF;
            v28 = v17[3];
            goto LABEL_58;
          }
        }
        else if ( (unsigned __int64)v27 <= v8 )
        {
          v29 = v17 + 13;
          LOBYTE(v11) = v17[2] & 0xF;
          v30 = v14;
          if ( (unsigned int)(unsigned __int8)v17[7] + 8 <= v14 )
            v30 = (unsigned __int8)v17[7] + 8;
          v8 = (unsigned __int64)&v17[v30];
          if ( (unsigned __int64)v29 <= v8 )
            v26 = v17[12];
          if ( (unsigned __int64)(v17 + 14) > v8 )
            v28 = 0;
          else
            v28 = *v29;
LABEL_58:
          if ( v12 )
          {
LABEL_60:
            McTemplateK0pduuuuup_EtwWriteTransfer(
              v8,
              v11,
              (unsigned int)&v110,
              a2,
              *(_DWORD *)(a2 + 48),
              v25,
              v16,
              v11,
              v26,
              v28,
              a2);
            goto LABEL_61;
          }
LABEL_59:
          LOBYTE(v11) = 0;
          v26 = 0;
          v28 = 0;
          goto LABEL_60;
        }
        v12 = 0;
        goto LABEL_58;
      }
      goto LABEL_206;
    }
LABEL_62:
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_193;
    v23 = EventNonReadWriteRequestComplete;
    goto LABEL_26;
  }
  v31 = v5[1];
  if ( !v31 )
  {
    v79 = *(unsigned int *)(*(_QWORD *)(a2 + 184) + 8LL);
    if ( (unsigned int)v79 >= 0x10 )
    {
      v7 = 0;
      if ( (*(_DWORD *)(v4 + 152) & 0x40000LL) != 0
        || (LedState = NvmeAdapterQueryLedState(*(_QWORD *)(v4 + 8), *(_QWORD *)(v4 + 600) + 160LL),
            v7 = LedState,
            LedState >= 0) )
      {
        memset_0(v5, 0, v79);
        *v5 = 16;
        v5[1] = 16;
        *((_QWORD *)v5 + 1) = *(unsigned int *)(*(_QWORD *)(v4 + 600) + 160LL);
        *(_QWORD *)(a2 + 56) = 16;
LABEL_203:
        v6 = StorEtwLoggingEnabled == 0;
        *(_BYTE *)(a2 + 141) = -84;
        *(_DWORD *)(a2 + 48) = v7;
        if ( v6 )
          goto LABEL_193;
        v110 = 0;
        IoGetActivityIdIrp(a2, &v110);
        v9 = *(unsigned __int8 **)(a2 + 184);
        if ( *v9 == 14 )
          goto LABEL_62;
        v10 = *v9 - 15;
        if ( *v9 != 15 )
        {
LABEL_206:
          if ( v10 != 12 )
            goto LABEL_193;
          if ( v9[1] == 7 && !*((_DWORD *)v9 + 2) )
          {
            if ( (byte_140177432 & 0x40) != 0 )
            {
              v22 = *(int **)(a2 + 56);
              if ( v22 )
                v2 = *v22;
              McTemplateK0pqd_EtwWriteTransfer(v8, (_DWORD)v9, (unsigned int)&v110, a2, v2, *(_DWORD *)(a2 + 48));
            }
            goto LABEL_193;
          }
          if ( (byte_140177432 & 0x20) == 0 )
            goto LABEL_193;
          v23 = EventPnpRequestComplete;
LABEL_26:
          McTemplateK0pd_EtwWriteTransfer(v8, v23, &v110, a2, *(_DWORD *)(a2 + 48));
          goto LABEL_193;
        }
        if ( byte_140177431 >= 0 )
          goto LABEL_193;
        v81 = *((_QWORD *)v9 + 1);
        v82 = 1;
        if ( *(_BYTE *)(v81 + 2) == 40 )
        {
          if ( *(_DWORD *)(v81 + 20) )
            goto LABEL_193;
          v109 = *(_DWORD *)(v81 + 56);
          if ( !v109 )
            goto LABEL_193;
          v83 = 0;
          v107 = 0;
          v84 = 0;
          v85 = 0;
          v86 = 0;
          v87 = 0;
          while ( 1 )
          {
            v8 = *(unsigned int *)(v81 + 4LL * v87 + 120);
            if ( (unsigned int)v8 >= 0x80 )
            {
              v88 = *(unsigned int *)(v81 + 16);
              if ( (unsigned int)v8 < (unsigned int)v88 )
              {
                v89 = (unsigned int)v8;
                v90 = *(_DWORD *)(v81 + v8) - 64;
                if ( v90 )
                {
                  LODWORD(v8) = v90 - 1;
                  if ( (_DWORD)v8 )
                  {
                    if ( (_DWORD)v8 == 1 )
                    {
                      LODWORD(v8) = v89 + 40;
                      if ( v89 + 40 <= v88 )
                      {
                        if ( *(_DWORD *)(v81 + v89 + 12) )
                          v84 = (char *)(v89 + v81 + 32);
                        v86 = *(_BYTE **)(v81 + v89 + 24);
                        goto LABEL_235;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v8) = v89 + 56;
                    if ( v89 + 56 <= v88 )
                    {
                      v107 = 1;
                      if ( *(_BYTE *)(v81 + v89 + 10) )
                        v84 = (char *)(v89 + v81 + 24);
                      v85 = *(_BYTE *)(v81 + v89 + 8);
                      v86 = *(_BYTE **)(v81 + v89 + 16);
                      v83 = *(_BYTE *)(v81 + v89 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v8) = v89 + 40;
                  if ( v89 + 40 <= v88 )
                  {
                    if ( *(_BYTE *)(v81 + v89 + 10) )
                      v84 = (char *)(v89 + v81 + 24);
                    v86 = *(_BYTE **)(v81 + v89 + 16);
LABEL_235:
                    v83 = *(_BYTE *)(v81 + v89 + 9);
                    v85 = *(_BYTE *)(v81 + v89 + 8);
LABEL_236:
                    if ( v84 )
                    {
                      v91 = *v84;
                      goto LABEL_239;
                    }
                    goto LABEL_193;
                  }
                }
                if ( v107 )
                  goto LABEL_236;
              }
            }
            if ( ++v87 >= v109 )
              goto LABEL_236;
          }
        }
        v91 = *(_BYTE *)(v81 + 72);
        v86 = *(_BYTE **)(v81 + 32);
        v83 = *(_BYTE *)(v81 + 11);
        v85 = *(_BYTE *)(v81 + 4);
        if ( *(_BYTE *)(v81 + 2) )
          goto LABEL_193;
LABEL_239:
        LOBYTE(v8) = v91 - 8;
        if ( (v8 & 0x5D) != 0 )
        {
LABEL_193:
          IofCompleteRequest((PIRP)a2, 0);
          return v7;
        }
        v92 = *(_BYTE *)(v81 + 3);
        if ( v92 == 1 || !v86 || !v83 )
          goto LABEL_256;
        LOBYTE(v81) = 0;
        v8 = (unsigned __int64)&v86[v83];
        v93 = 0;
        v94 = v86 + 8;
        v95 = 0;
        if ( (unsigned __int8)((*v86 & 0x7F) - 114) <= 1u )
        {
          if ( (unsigned __int64)v94 <= v8 )
          {
            v93 = v86[2];
            LOBYTE(v81) = v86[1] & 0xF;
            v95 = v86[3];
            goto LABEL_255;
          }
        }
        else if ( (unsigned __int64)v94 <= v8 )
        {
          v96 = v86 + 13;
          LOBYTE(v81) = v86[2] & 0xF;
          v97 = v83;
          if ( (unsigned int)(unsigned __int8)v86[7] + 8 <= v83 )
            v97 = (unsigned __int8)v86[7] + 8;
          v8 = (unsigned __int64)&v86[v97];
          if ( (unsigned __int64)v96 <= v8 )
            v93 = v86[12];
          if ( (unsigned __int64)(v86 + 14) > v8 )
            v95 = 0;
          else
            v95 = *v96;
LABEL_255:
          if ( v82 )
          {
LABEL_257:
            McTemplateK0pduuuuup_EtwWriteTransfer(
              v8,
              v81,
              (unsigned int)&v110,
              a2,
              *(_DWORD *)(a2 + 48),
              v92,
              v85,
              v81,
              v93,
              v95,
              a2);
            goto LABEL_193;
          }
LABEL_256:
          LOBYTE(v81) = 0;
          v93 = 0;
          v95 = 0;
          goto LABEL_257;
        }
        v82 = 0;
        goto LABEL_255;
      }
      if ( LedState == -2147483643 )
        goto LABEL_203;
    }
    else
    {
      if ( (unsigned int)v79 >= 8 )
      {
        *v5 = 16;
        v7 = 0;
        v5[1] = 16;
        *(_QWORD *)(a2 + 56) = 8;
        goto LABEL_203;
      }
      v7 = -1073741789;
    }
    *(_QWORD *)(a2 + 56) = 0;
    goto LABEL_203;
  }
  *(_QWORD *)(a2 + 56) = 0;
  *(_BYTE *)(a2 + 141) = -84;
  if ( v31 == 1 )
  {
    v6 = StorEtwLoggingEnabled == 0;
    *(_DWORD *)(a2 + 48) = 0;
    if ( v6 )
      goto LABEL_192;
    v110 = 0;
    IoGetActivityIdIrp(a2, &v110);
    v56 = *(_QWORD *)(a2 + 184);
    if ( *(_BYTE *)v56 == 14 )
    {
      if ( (byte_140177432 & 8) == 0 )
        goto LABEL_192;
      v59 = EventNonReadWriteRequestComplete;
      goto LABEL_191;
    }
    if ( *(_BYTE *)v56 != 15 )
    {
      if ( *(_BYTE *)v56 != 27 )
        goto LABEL_192;
      if ( *(_BYTE *)(v56 + 1) == 7 && !*(_DWORD *)(v56 + 8) )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          v57 = *(int **)(a2 + 56);
          if ( v57 )
            v58 = *v57;
          else
            v58 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v58, v56, (unsigned int)&v110, a2, v58, *(_DWORD *)(a2 + 48));
        }
        goto LABEL_192;
      }
      if ( (byte_140177432 & 0x20) == 0 )
        goto LABEL_192;
      v59 = EventPnpRequestComplete;
LABEL_191:
      McTemplateK0pd_EtwWriteTransfer(v55, v59, &v110, a2, *(_DWORD *)(a2 + 48));
      goto LABEL_192;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_192;
    v60 = *(_QWORD *)(v56 + 8);
    v61 = 1;
    if ( *(_BYTE *)(v60 + 2) == 40 )
    {
      if ( *(_DWORD *)(v60 + 20) )
        goto LABEL_192;
      v62 = *(_DWORD *)(v60 + 56);
      if ( !v62 )
        goto LABEL_192;
      v63 = 0;
      v106 = 0;
      v64 = 0;
      v65 = 0;
      v66 = 0;
      v67 = 0;
      while ( 1 )
      {
        v55 = *(unsigned int *)(v60 + 4LL * v67 + 120);
        if ( (unsigned int)v55 >= 0x80 )
        {
          v68 = *(unsigned int *)(v60 + 16);
          if ( (unsigned int)v55 < (unsigned int)v68 )
          {
            v69 = (unsigned int)v55;
            v70 = *(_DWORD *)(v55 + v60) - 64;
            if ( v70 )
            {
              LODWORD(v55) = v70 - 1;
              if ( (_DWORD)v55 )
              {
                if ( (_DWORD)v55 == 1 )
                {
                  LODWORD(v55) = v69 + 40;
                  if ( v69 + 40 <= v68 )
                  {
                    if ( *(_DWORD *)(v69 + v60 + 12) )
                      v64 = (char *)(v69 + v60 + 32);
                    v66 = *(_BYTE **)(v69 + v60 + 24);
                    goto LABEL_166;
                  }
                }
              }
              else
              {
                LODWORD(v55) = v69 + 56;
                if ( v69 + 56 <= v68 )
                {
                  v106 = 1;
                  if ( *(_BYTE *)(v69 + v60 + 10) )
                    v64 = (char *)(v69 + v60 + 24);
                  v65 = *(_BYTE *)(v69 + v60 + 8);
                  v66 = *(_BYTE **)(v69 + v60 + 16);
                  v63 = *(_BYTE *)(v69 + v60 + 9);
                }
              }
            }
            else
            {
              LODWORD(v55) = v69 + 40;
              if ( v69 + 40 <= v68 )
              {
                if ( *(_BYTE *)(v69 + v60 + 10) )
                  v64 = (char *)(v69 + v60 + 24);
                v66 = *(_BYTE **)(v69 + v60 + 16);
LABEL_166:
                v63 = *(_BYTE *)(v69 + v60 + 9);
                v65 = *(_BYTE *)(v69 + v60 + 8);
LABEL_167:
                if ( v64 )
                {
                  v71 = *v64;
                  goto LABEL_170;
                }
                goto LABEL_192;
              }
            }
            if ( v106 )
              goto LABEL_167;
          }
        }
        if ( ++v67 >= v62 )
          goto LABEL_167;
      }
    }
    v71 = *(_BYTE *)(v60 + 72);
    v66 = *(_BYTE **)(v60 + 32);
    v63 = *(_BYTE *)(v60 + 11);
    v65 = *(_BYTE *)(v60 + 4);
    if ( *(_BYTE *)(v60 + 2) )
      goto LABEL_192;
LABEL_170:
    LOBYTE(v55) = v71 - 8;
    if ( (v55 & 0x5D) != 0 )
    {
LABEL_192:
      v7 = 0;
      goto LABEL_193;
    }
    v72 = *(_BYTE *)(v60 + 3);
    if ( v72 == 1 || !v66 || !v63 )
      goto LABEL_187;
    LOBYTE(v60) = 0;
    v55 = (unsigned __int64)&v66[v63];
    v73 = 0;
    v74 = v66 + 8;
    v75 = 0;
    if ( (unsigned __int8)((*v66 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v74 <= v55 )
      {
        v73 = v66[2];
        LOBYTE(v60) = v66[1] & 0xF;
        v75 = v66[3];
        goto LABEL_186;
      }
    }
    else if ( (unsigned __int64)v74 <= v55 )
    {
      v76 = v66 + 13;
      LOBYTE(v60) = v66[2] & 0xF;
      v77 = v63;
      if ( (unsigned int)(unsigned __int8)v66[7] + 8 <= v63 )
        v77 = (unsigned __int8)v66[7] + 8;
      v55 = (unsigned __int64)&v66[v77];
      if ( (unsigned __int64)v76 <= v55 )
        v73 = v66[12];
      if ( (unsigned __int64)(v66 + 14) > v55 )
        v75 = 0;
      else
        v75 = *v76;
LABEL_186:
      if ( v61 )
      {
LABEL_188:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v55,
          v60,
          (unsigned int)&v110,
          a2,
          *(_DWORD *)(a2 + 48),
          v72,
          v65,
          v60,
          v73,
          v75,
          a2);
        goto LABEL_192;
      }
LABEL_187:
      LOBYTE(v60) = 0;
      v73 = 0;
      v75 = 0;
      goto LABEL_188;
    }
    v61 = 0;
    goto LABEL_186;
  }
  v6 = StorEtwLoggingEnabled == 0;
  *(_DWORD *)(a2 + 48) = -1073741637;
  if ( v6 )
    goto LABEL_290;
  v110 = 0;
  IoGetActivityIdIrp(a2, &v110);
  v33 = *(unsigned __int8 **)(a2 + 184);
  if ( *v33 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_290;
    v103 = *(_DWORD *)(a2 + 48);
    goto LABEL_289;
  }
  v34 = *v33 - 15;
  if ( *v33 != 15 )
    goto LABEL_69;
  if ( byte_140177431 >= 0 )
    goto LABEL_290;
  v36 = *((_QWORD *)v33 + 1);
  v37 = 1;
  v38 = *(unsigned __int8 *)(v36 + 2);
  if ( (_BYTE)v38 == 40 )
  {
    if ( *(_DWORD *)(v36 + 20) )
      goto LABEL_290;
    v39 = *(_DWORD *)(v36 + 56);
    if ( !v39 )
      goto LABEL_290;
    v40 = 0;
    v105 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    while ( 1 )
    {
      v32 = *(unsigned int *)(v36 + 4LL * v44 + 120);
      if ( (unsigned int)v32 >= 0x80 )
      {
        v45 = *(unsigned int *)(v36 + 16);
        if ( (unsigned int)v32 < (unsigned int)v45 )
        {
          v46 = (unsigned int)v32;
          v47 = *(_DWORD *)(v36 + v32) - 64;
          if ( v47 )
          {
            LODWORD(v32) = v47 - 1;
            if ( (_DWORD)v32 )
            {
              if ( (_DWORD)v32 == 1 )
              {
                LODWORD(v32) = v46 + 40;
                if ( v46 + 40 <= v45 )
                {
                  if ( *(_DWORD *)(v36 + v46 + 12) )
                    v41 = (char *)(v46 + v36 + 32);
                  v43 = *(_BYTE **)(v36 + v46 + 24);
                  goto LABEL_103;
                }
              }
            }
            else
            {
              LODWORD(v32) = v46 + 56;
              if ( v46 + 56 <= v45 )
              {
                v105 = 1;
                if ( *(_BYTE *)(v36 + v46 + 10) )
                  v41 = (char *)(v46 + v36 + 24);
                v42 = *(_BYTE *)(v36 + v46 + 8);
                v43 = *(_BYTE **)(v36 + v46 + 16);
                v40 = *(_BYTE *)(v36 + v46 + 9);
              }
            }
          }
          else
          {
            LODWORD(v32) = v46 + 40;
            if ( v46 + 40 <= v45 )
            {
              if ( *(_BYTE *)(v36 + v46 + 10) )
                v41 = (char *)(v46 + v36 + 24);
              v43 = *(_BYTE **)(v36 + v46 + 16);
LABEL_103:
              v40 = *(_BYTE *)(v36 + v46 + 9);
              v42 = *(_BYTE *)(v36 + v46 + 8);
LABEL_104:
              if ( v41 )
              {
                v48 = *v41;
                goto LABEL_107;
              }
              goto LABEL_290;
            }
          }
          if ( v105 )
            goto LABEL_104;
        }
      }
      if ( ++v44 >= v39 )
        goto LABEL_104;
    }
  }
LABEL_106:
  v42 = *(_BYTE *)(v36 + 4);
  v40 = *(_BYTE *)(v36 + 11);
  v43 = *(_BYTE **)(v36 + 32);
  v48 = *(_BYTE *)(v36 + 72);
  if ( v38 )
    goto LABEL_290;
LABEL_107:
  LOBYTE(v32) = v48 - 8;
  if ( (v32 & 0x5D) == 0 )
  {
    v49 = *(_BYTE *)(v36 + 3);
    if ( v49 == 1 || !v43 || !v40 )
      goto LABEL_124;
    v50 = 0;
    v32 = (unsigned __int64)&v43[v40];
    v51 = 0;
    v52 = v43 + 8;
    LOBYTE(v36) = 0;
    if ( (unsigned __int8)((*v43 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v52 <= v32 )
      {
        v51 = v43[2];
        LOBYTE(v36) = v43[1] & 0xF;
        v50 = v43[3];
        goto LABEL_123;
      }
    }
    else if ( (unsigned __int64)v52 <= v32 )
    {
      v53 = v43 + 13;
      LOBYTE(v36) = v43[2] & 0xF;
      v54 = v40;
      if ( (unsigned int)(unsigned __int8)v43[7] + 8 <= v40 )
        v54 = (unsigned __int8)v43[7] + 8;
      v32 = (unsigned __int64)&v43[v54];
      if ( (unsigned __int64)v53 <= v32 )
        v51 = v43[12];
      if ( (unsigned __int64)(v43 + 14) > v32 )
        v50 = 0;
      else
        v50 = *v53;
LABEL_123:
      if ( v37 )
      {
LABEL_125:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v32,
          v36,
          (unsigned int)&v110,
          a2,
          *(_DWORD *)(a2 + 48),
          v49,
          v42,
          v36,
          v51,
          v50,
          a2);
        goto LABEL_290;
      }
LABEL_124:
      LOBYTE(v36) = 0;
      v51 = 0;
      v50 = 0;
      goto LABEL_125;
    }
    v37 = 0;
    goto LABEL_123;
  }
LABEL_290:
  IofCompleteRequest((PIRP)a2, 0);
  return 3221225659LL;
}

```

## disassembly

```asm
0x1401893d4  mov     [rsp-38h+arg_10], rbx
0x1401893d9  push    rbp
0x1401893da  push    rsi
0x1401893db  push    rdi
0x1401893dc  push    r12
0x1401893de  push    r13
0x1401893e0  push    r14
0x1401893e2  push    r15
0x1401893e4  mov     rbp, rsp
0x1401893e7  sub     rsp, 80h
0x1401893ee  mov     rax, cs:__security_cookie
0x1401893f5  xor     rax, rsp
0x1401893f8  mov     [rbp+var_8], rax
0x1401893fc  mov     rax, [rcx+10h]
0x140189400  xor     ebx, ebx
0x140189402  mov     rdi, rdx
0x140189405  mov     r14, [rax+80h]
0x14018940c  mov     rax, [r14+198h]
0x140189413  test    dword ptr [rax+0B8h], 40000000h
0x14018941d  jz      loc_140189FF3
0x140189423  mov     rsi, [rdx+18h]
0x140189427  test    rsi, rsi
0x14018942a  jnz     loc_14018971F
0x140189430  cmp     cs:StorEtwLoggingEnabled, bl
0x140189436  mov     r12d, 0C000000Dh
0x14018943c  mov     [rdx+30h], r12d
0x140189440  mov     [rdx+38h], rbx
0x140189444  mov     byte ptr [rdx+8Dh], 0ACh
0x14018944b  jz      loc_140189CCF
0x140189451  xorps   xmm0, xmm0
0x140189454  lea     rdx, [rbp+var_18]
0x140189458  mov     rcx, rdi
0x14018945b  movups  [rbp+var_18], xmm0
0x14018945f  call    cs:__imp_IoGetActivityIdIrp
0x140189466  nop     dword ptr [rax+rax+00h]
0x14018946b  mov     rdx, [rdi+0B8h]
0x140189472  movzx   eax, byte ptr [rdx]
0x140189475  sub     eax, 0Eh
0x140189478  jz      loc_140189706
0x14018947e  sub     eax, 1
0x140189481  jnz     loc_140189DCE
0x140189487  cmp     cs:byte_140177431, bl
0x14018948d  jge     loc_140189CCF
0x140189493  mov     rdx, [rdx+8]
0x140189497  lea     r8d, [rbx+1]
0x14018949b  movzx   eax, byte ptr [rdx+2]
0x14018949f  cmp     al, 28h ; '('
0x1401894a1  jnz     loc_140189606
0x1401894a7  cmp     [rdx+14h], ebx
0x1401894aa  jnz     loc_140189CCF
0x1401894b0  mov     r13d, [rdx+38h]
0x1401894b4  test    r13d, r13d
0x1401894b7  jz      loc_140189CCF
0x1401894bd  mov     r11b, bl
0x1401894c0  mov     [rbp+var_20], bl
0x1401894c3  mov     esi, ebx
0x1401894c5  mov     r12b, bl
0x1401894c8  mov     r10d, ebx
0x1401894cb  mov     r15d, ebx
0x1401894ce  mov     eax, r15d
0x1401894d1  mov     ecx, [rdx+rax*4+78h]
0x1401894d5  cmp     ecx, 80h
0x1401894db  jb      loc_1401895CE
0x1401894e1  mov     r14d, [rdx+10h]
0x1401894e5  cmp     ecx, r14d
0x1401894e8  jnb     loc_1401895CE
0x1401894ee  mov     r9d, ecx
0x1401894f1  mov     ecx, [rcx+rdx]
0x1401894f4  sub     ecx, 40h ; '@'
0x1401894f7  jz      loc_1401895C0
0x1401894fd  sub     ecx, r8d
0x140189500  jz      loc_140189594
0x140189506  cmp     ecx, r8d
0x140189509  jnz     loc_1401895C9
0x14018950f  lea     rcx, [r9+28h]
0x140189513  cmp     rcx, r14
0x140189516  ja      loc_1401895C9
0x14018951c  cmp     [r9+rdx+0Ch], ebx
0x140189521  jbe     short loc_14018952A
0x140189523  lea     rsi, [rdx+20h]
0x140189527  add     rsi, r9
0x14018952a  mov     r10, [r9+rdx+18h]
0x14018952f  jmp     loc_1401895EF
0x140189534  test    cs:byte_140177432, 40h
0x14018953b  jz      loc_140189CCF
0x140189541  mov     rax, [rdi+38h]
0x140189545  test    rax, rax
0x140189548  jz      short loc_14018954C
0x14018954a  mov     ebx, [rax]
0x14018954c  mov     eax, [rdi+30h]
0x14018954f  lea     r8, [rbp+var_18]
0x140189553  mov     [rsp+80h+var_58], eax
0x140189557  mov     r9, rdi
0x14018955a  mov     [rsp+80h+var_60], ebx
0x14018955e  call    McTemplateK0pqd_EtwWriteTransfer
0x140189563  jmp     loc_140189CCF
0x140189568  test    cs:byte_140177432, 20h
0x14018956f  jz      loc_140189CCF
0x140189575  lea     rdx, EventPnpRequestComplete
0x14018957c  mov     eax, [rdi+30h]
0x14018957f  lea     r8, [rbp+var_18]
0x140189583  mov     r9, rdi
0x140189586  mov     [rsp+80h+var_60], eax
0x14018958a  call    McTemplateK0pd_EtwWriteTransfer
0x14018958f  jmp     loc_140189CCF
0x140189594  lea     rcx, [r9+38h]
0x140189598  cmp     rcx, r14
0x14018959b  ja      short loc_1401895C9
0x14018959d  mov     [rbp+var_20], r8b
0x1401895a1  cmp     [r9+rdx+0Ah], bl
0x1401895a6  jbe     short loc_1401895AF
0x1401895a8  lea     rsi, [rdx+18h]
0x1401895ac  add     rsi, r9
0x1401895af  mov     r12b, [r9+rdx+8]
0x1401895b4  mov     r10, [r9+rdx+10h]
0x1401895b9  mov     r11b, [r9+rdx+9]
0x1401895be  jmp     short loc_1401895C9
0x1401895c0  lea     rcx, [r9+28h]
0x1401895c4  cmp     rcx, r14
0x1401895c7  jbe     short loc_1401895DC
0x1401895c9  cmp     [rbp+var_20], bl
0x1401895cc  jnz     short loc_1401895F9
0x1401895ce  add     r15d, r8d
0x1401895d1  cmp     r15d, r13d
0x1401895d4  jb      loc_1401894CE
0x1401895da  jmp     short loc_1401895F9
0x1401895dc  cmp     [r9+rdx+0Ah], bl
0x1401895e1  jbe     short loc_1401895EA
0x1401895e3  lea     rsi, [rdx+18h]
0x1401895e7  add     rsi, r9
0x1401895ea  mov     r10, [r9+rdx+10h]
0x1401895ef  mov     r11b, [r9+rdx+9]
0x1401895f4  mov     r12b, [r9+rdx+8]
0x1401895f9  test    rsi, rsi
0x1401895fc  jz      loc_1401896FB
0x140189602  mov     cl, [rsi]
0x140189604  jmp     short loc_14018961D
0x140189606  mov     cl, [rdx+48h]
0x140189609  mov     r10, [rdx+20h]
0x14018960d  mov     r11b, [rdx+0Bh]
0x140189611  mov     r12b, [rdx+4]
0x140189615  test    eax, eax
0x140189617  jnz     loc_1401896FB
0x14018961d  sub     cl, 8
0x140189620  test    cl, 5Dh
0x140189623  jnz     loc_1401896FB
0x140189629  mov     r14b, [rdx+3]
0x14018962d  cmp     r14b, r8b
0x140189630  jz      loc_1401896C3
0x140189636  test    r10, r10
0x140189639  jz      loc_1401896C3
0x14018963f  test    r11b, r11b
0x140189642  jz      short loc_1401896C3
0x140189644  mov     al, [r10]
0x140189647  mov     dl, bl
0x140189649  and     al, 7Fh
0x14018964b  movzx   ecx, r11b
0x14018964f  sub     al, 72h ; 'r'
0x140189651  add     rcx, r10
0x140189654  cmp     al, r8b
0x140189657  mov     sil, bl
0x14018965a  lea     rax, [r10+8]
0x14018965e  mov     r9b, bl
0x140189661  jbe     short loc_1401896A5
0x140189663  cmp     rax, rcx
0x140189666  ja      short loc_1401896BB
0x140189668  movzx   ecx, byte ptr [r10+7]
0x14018966d  lea     r9, [r10+0Dh]
0x140189671  mov     dl, [r10+2]
0x140189675  add     ecx, 8
0x140189678  and     dl, 0Fh
0x14018967b  movzx   eax, r11b
0x14018967f  cmp     ecx, eax
0x140189681  cmovbe  eax, ecx
0x140189684  mov     ecx, eax
0x140189686  add     rcx, r10
0x140189689  cmp     r9, rcx
0x14018968c  ja      short loc_140189692
0x14018968e  mov     sil, [r10+0Ch]
0x140189692  lea     rax, [r10+0Eh]
0x140189696  cmp     rax, rcx
0x140189699  ja      short loc_1401896A0
0x14018969b  mov     r9b, [r9]
0x14018969e  jmp     short loc_1401896BE
0x1401896a0  mov     r9b, bl
0x1401896a3  jmp     short loc_1401896BE
0x1401896a5  cmp     rax, rcx
0x1401896a8  ja      short loc_1401896BB
0x1401896aa  mov     dl, [r10+1]
0x1401896ae  mov     sil, [r10+2]
0x1401896b2  and     dl, 0Fh
0x1401896b5  mov     r9b, [r10+3]
0x1401896b9  jmp     short loc_1401896BE
0x1401896bb  mov     r8b, bl
0x1401896be  test    r8b, r8b
0x1401896c1  jnz     short loc_1401896CB
0x1401896c3  mov     dl, bl
0x1401896c5  mov     sil, bl
0x1401896c8  mov     r9b, bl
0x1401896cb  mov     eax, [rdi+30h]
0x1401896ce  lea     r8, [rbp+var_18]
0x1401896d2  mov     [rsp+80h+var_30], rdi
0x1401896d7  mov     [rsp+80h+var_38], r9b
0x1401896dc  mov     r9, rdi
0x1401896df  mov     [rsp+80h+var_40], sil
0x1401896e4  mov     [rsp+80h+var_48], dl
0x1401896e8  mov     [rsp+80h+var_50], r12b
0x1401896ed  mov     byte ptr [rsp+80h+var_58], r14b
0x1401896f2  mov     [rsp+80h+var_60], eax
0x1401896f6  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x1401896fb  mov     r12d, 0C000000Dh
0x140189701  jmp     loc_140189CCF
0x140189706  test    cs:byte_140177432, 8
0x14018970d  jz      loc_140189CCF
0x140189713  lea     rdx, EventNonReadWriteRequestComplete
0x14018971a  jmp     loc_14018957C
0x14018971f  mov     ecx, [rsi+4]
0x140189722  test    ecx, ecx
0x140189724  jz      loc_140189CE8
0x14018972a  mov     [rdx+38h], rbx
0x14018972e  mov     byte ptr [rdx+8Dh], 0ACh
0x140189735  cmp     ecx, 1
0x140189738  jz      loc_140189A05
0x14018973e  cmp     cs:StorEtwLoggingEnabled, bl
0x140189744  mov     dword ptr [rdx+30h], 0C00000BBh
0x14018974b  jz      loc_14018A170
0x140189751  xorps   xmm0, xmm0
0x140189754  lea     rdx, [rbp+var_18]
0x140189758  mov     rcx, rdi
0x14018975b  movups  [rbp+var_18], xmm0
0x14018975f  call    cs:__imp_IoGetActivityIdIrp
0x140189766  nop     dword ptr [rax+rax+00h]
0x14018976b  mov     rdx, [rdi+0B8h]
0x140189772  movzx   eax, byte ptr [rdx]
0x140189775  sub     eax, 0Eh
0x140189778  jz      loc_1401899EC
0x14018977e  sub     eax, 1
0x140189781  jz      short loc_1401897EB
0x140189783  cmp     eax, 0Ch
0x140189786  jnz     loc_14018A170
0x14018978c  cmp     byte ptr [rdx+1], 7
0x140189790  jnz     short loc_1401897CB
0x140189792  cmp     [rdx+8], ebx
0x140189795  jnz     short loc_1401897CB
0x140189797  test    cs:byte_140177432, 40h
0x14018979e  jz      loc_14018A170
0x1401897a4  mov     rax, [rdi+38h]
0x1401897a8  test    rax, rax
0x1401897ab  jz      short loc_1401897AF
0x1401897ad  mov     ebx, [rax]
0x1401897af  mov     eax, [rdi+30h]
0x1401897b2  lea     r8, [rbp+var_18]
0x1401897b6  mov     [rsp+80h+var_58], eax
0x1401897ba  mov     r9, rdi
0x1401897bd  mov     [rsp+80h+var_60], ebx
0x1401897c1  call    McTemplateK0pqd_EtwWriteTransfer
0x1401897c6  jmp     loc_14018A170
0x1401897cb  test    cs:byte_140177432, 20h
0x1401897d2  jz      loc_14018A170
0x1401897d8  mov     eax, [rdi+30h]
0x1401897db  lea     rdx, EventPnpRequestComplete
0x1401897e2  mov     [rsp+80h+var_60], eax
0x1401897e6  jmp     loc_14018A164
0x1401897eb  cmp     cs:byte_140177431, bl
0x1401897f1  jge     loc_14018A170
0x1401897f7  mov     rdx, [rdx+8]
0x1401897fb  mov     r8d, 1
0x140189801  movzx   eax, byte ptr [rdx+2]
0x140189805  cmp     al, 28h ; '('
0x140189807  jnz     loc_1401898F2
0x14018980d  cmp     [rdx+14h], ebx
0x140189810  jnz     loc_14018A170
0x140189816  mov     r13d, [rdx+38h]
0x14018981a  test    r13d, r13d
0x14018981d  jz      loc_14018A170
0x140189823  mov     r11b, bl
0x140189826  mov     [rbp+var_20], bl
0x140189829  mov     rsi, rbx
0x14018982c  mov     r12b, bl
0x14018982f  mov     r10, rbx
0x140189832  mov     r15d, ebx
0x140189835  mov     eax, r15d
0x140189838  mov     ecx, [rdx+rax*4+78h]
0x14018983c  cmp     ecx, 80h
0x140189842  jb      short loc_1401898BA
0x140189844  mov     r14d, [rdx+10h]
0x140189848  cmp     ecx, r14d
0x14018984b  jnb     short loc_1401898BA
0x14018984d  mov     r9d, ecx
0x140189850  mov     ecx, [rdx+rcx]
0x140189853  sub     ecx, 40h ; '@'
0x140189856  jz      short loc_1401898AC
0x140189858  sub     ecx, r8d
0x14018985b  jz      short loc_140189880
0x14018985d  cmp     ecx, r8d
0x140189860  jnz     short loc_1401898B5
0x140189862  lea     rcx, [r9+28h]
0x140189866  cmp     rcx, r14
0x140189869  ja      short loc_1401898B5
0x14018986b  cmp     [rdx+r9+0Ch], ebx
  ... truncated ...
```
