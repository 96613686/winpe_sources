# RaUnitTelemetryIdIoctl

- ea: `0x14005a554`
- end: `0x14005b0fe`
- name: `RaUnitTelemetryIdIoctl`
- size: `2986`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140036290`

## callees

- `0x140046c60`
- `0x140054800`
- `0x14005a554`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14005a5d0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005a8b9`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005ab21`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005ae0e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005a5d0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005a8b9`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005ab21`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14005ae0e`
- `ntoskrnl!IofCompleteRequest` at `0x14005a9e2`
- `ntoskrnl!IofCompleteRequest` at `0x14005adcb`
- `ntoskrnl!IofCompleteRequest` at `0x14005b0c5`
- `ntoskrnl!IofCompleteRequest` at `0x14005a9e2`
- `ntoskrnl!IofCompleteRequest` at `0x14005adcb`
- `ntoskrnl!IofCompleteRequest` at `0x14005b0c5`

## pseudocode

```c
__int64 __fastcall RaUnitTelemetryIdIoctl(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  int v5; // ebx
  bool v6; // zf
  unsigned __int64 v7; // rcx
  unsigned __int8 *v8; // rdx
  int v9; // eax
  int *v10; // rax
  __int64 v11; // rdx
  char v12; // si
  int v13; // eax
  unsigned int v14; // r13d
  unsigned __int8 v15; // r10
  char *v16; // r11
  char v17; // r12
  _BYTE *v18; // r9
  unsigned int v19; // r15d
  unsigned __int64 v20; // r14
  __int64 v21; // r8
  int v22; // ecx
  char v23; // cl
  char v24; // r14
  char v25; // r8
  char v26; // r11
  _BYTE *v27; // rax
  char *v28; // r8
  unsigned int v29; // eax
  unsigned int v30; // r13d
  unsigned int v31; // r15d
  unsigned __int64 v32; // r14
  int v33; // ecx
  __int64 v35; // rcx
  int v36; // ebx
  char v37; // si
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rcx
  unsigned __int64 v41; // rcx
  __int64 v42; // rdx
  int *v43; // rax
  __int64 *v44; // rdx
  __int64 v45; // rdx
  unsigned int v46; // r13d
  unsigned __int8 v47; // r10
  char *v48; // r11
  char v49; // r15
  _BYTE *v50; // r9
  unsigned int v51; // r12d
  unsigned __int64 v52; // r14
  __int64 v53; // r8
  int v54; // ecx
  char v55; // cl
  char v56; // r14
  char v57; // r11
  _BYTE *v58; // rax
  char v59; // r8
  char *v60; // r8
  unsigned int v61; // eax
  int v62; // ebx
  unsigned __int64 v63; // rcx
  __int64 v64; // rdx
  int *v65; // rax
  __int64 v66; // rdx
  char v67; // si
  unsigned int v68; // r13d
  unsigned __int8 v69; // r10
  char *v70; // r11
  char v71; // r12
  _BYTE *v72; // r9
  unsigned int v73; // r15d
  unsigned __int64 v74; // r14
  __int64 v75; // r8
  int v76; // ecx
  char v77; // cl
  char v78; // r14
  char v79; // r11
  _BYTE *v80; // rax
  char v81; // r8
  char *v82; // r8
  unsigned int v83; // eax
  ULONG v84; // [rsp+20h] [rbp-E0h]
  char v85; // [rsp+60h] [rbp-A0h] BYREF
  char v86; // [rsp+61h] [rbp-9Fh] BYREF
  char v87; // [rsp+62h] [rbp-9Eh] BYREF
  unsigned int v88; // [rsp+64h] [rbp-9Ch] BYREF
  __int128 v89; // [rsp+68h] [rbp-98h] BYREF
  __int64 v90[16]; // [rsp+80h] [rbp-80h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  if ( *(_DWORD *)(v2 + 16) >= 0x28u )
  {
    if ( *(_DWORD *)(v2 + 8) < 0x28u )
    {
      LOBYTE(v5) = 0;
      *(_BYTE *)(a2 + 141) = -84;
      v6 = StorEtwLoggingEnabled == 0;
      *(_QWORD *)(a2 + 56) = 0;
      v88 = -1073741789;
      *(_DWORD *)(a2 + 48) = -1073741789;
      if ( v6 )
        goto LABEL_91;
      v89 = 0;
      IoGetActivityIdIrp(a2, &v89);
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
                McTemplateK0pd_EtwWriteTransfer(v7, EventPnpRequestComplete, &v89, a2, *(_DWORD *)(a2 + 48));
            }
            else if ( (byte_140177432 & 0x40) != 0 )
            {
              v10 = *(int **)(a2 + 56);
              if ( v10 )
                v5 = *v10;
              McTemplateK0pqd_EtwWriteTransfer(v7, (_DWORD)v8, (unsigned int)&v89, a2, v5, *(_DWORD *)(a2 + 48));
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
          v85 = 0;
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
                      v85 = 1;
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
                if ( v85 )
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
      v84 = *(_DWORD *)(a2 + 48);
LABEL_90:
      McTemplateK0pd_EtwWriteTransfer(v7, EventNonReadWriteRequestComplete, &v89, a2, v84);
      goto LABEL_91;
    }
    v35 = *(_QWORD *)(a2 + 24);
    if ( *(_DWORD *)v35 == 40 && *(_DWORD *)(v35 + 4) == 40 )
    {
      LOBYTE(v36) = 0;
      *(_OWORD *)(a1 + 2104) = *(_OWORD *)(v35 + 8);
      *(_DWORD *)v35 = 40;
      *(_DWORD *)(v35 + 4) = 40;
      v37 = 1;
      *(_OWORD *)(v35 + 24) = *(_OWORD *)(*(_QWORD *)(a1 + 24) + 5128LL);
      *(_QWORD *)(a2 + 56) = 40;
      if ( (unsigned int)dword_140176178 > 5 && (unsigned __int8)tlgKeywordOn(v35, 0x400000000000LL) )
      {
        v40 = *(_QWORD *)(v38 + 24);
        v90[5] = 16;
        v90[6] = v39;
        v90[7] = 16;
        v90[4] = v40 + 5128;
        v88 = *(_DWORD *)(v40 + 56);
        v90[8] = (__int64)&v88;
        v85 = *(_BYTE *)(v38 + 104);
        v90[10] = (__int64)&v85;
        v86 = *(_BYTE *)(v38 + 105);
        v90[12] = (__int64)&v86;
        v87 = *(_BYTE *)(v38 + 106);
        v90[14] = (__int64)&v87;
        v90[9] = 4;
        v90[11] = 1;
        v90[13] = 1;
        v90[15] = 1;
        tlgWriteTransfer_EtwWriteTransfer(v40, (int)&dword_1401646E4, v38, v39, 8u, (__int64)v90);
      }
      v6 = StorEtwLoggingEnabled == 0;
      *(_BYTE *)(a2 + 141) = -84;
      *(_DWORD *)(a2 + 48) = 0;
      if ( v6 )
        goto LABEL_160;
      v89 = 0;
      IoGetActivityIdIrp(a2, &v89);
      v42 = *(_QWORD *)(a2 + 184);
      if ( *(_BYTE *)v42 == 14 )
      {
        if ( (byte_140177432 & 8) == 0 )
          goto LABEL_160;
        v44 = EventNonReadWriteRequestComplete;
        goto LABEL_159;
      }
      if ( *(_BYTE *)v42 != 15 )
      {
        if ( *(_BYTE *)v42 != 27 )
          goto LABEL_160;
        if ( *(_BYTE *)(v42 + 1) == 7 && !*(_DWORD *)(v42 + 8) )
        {
          if ( (byte_140177432 & 0x40) != 0 )
          {
            v43 = *(int **)(a2 + 56);
            if ( v43 )
              v36 = *v43;
            McTemplateK0pqd_EtwWriteTransfer(v41, v42, (unsigned int)&v89, a2, v36, *(_DWORD *)(a2 + 48));
          }
          goto LABEL_160;
        }
        if ( (byte_140177432 & 0x20) == 0 )
          goto LABEL_160;
        v44 = EventPnpRequestComplete;
LABEL_159:
        McTemplateK0pd_EtwWriteTransfer(v41, v44, &v89, a2, *(_DWORD *)(a2 + 48));
        goto LABEL_160;
      }
      if ( byte_140177431 >= 0 )
        goto LABEL_160;
      v45 = *(_QWORD *)(v42 + 8);
      if ( *(_BYTE *)(v45 + 2) == 40 )
      {
        if ( *(_DWORD *)(v45 + 20) )
          goto LABEL_160;
        v46 = *(_DWORD *)(v45 + 56);
        if ( !v46 )
          goto LABEL_160;
        v47 = 0;
        v85 = 0;
        v48 = 0;
        v49 = 0;
        v50 = 0;
        v51 = 0;
        while ( 1 )
        {
          v41 = *(unsigned int *)(v45 + 4LL * v51 + 120);
          if ( (unsigned int)v41 >= 0x80 )
          {
            v52 = *(unsigned int *)(v45 + 16);
            if ( (unsigned int)v41 < (unsigned int)v52 )
            {
              v53 = (unsigned int)v41;
              v54 = *(_DWORD *)(v41 + v45) - 64;
              if ( v54 )
              {
                LODWORD(v41) = v54 - 1;
                if ( (_DWORD)v41 )
                {
                  if ( (_DWORD)v41 == 1 )
                  {
                    LODWORD(v41) = v53 + 40;
                    if ( v53 + 40 <= v52 )
                    {
                      if ( *(_DWORD *)(v53 + v45 + 12) )
                        v48 = (char *)(v53 + v45 + 32);
                      v50 = *(_BYTE **)(v53 + v45 + 24);
                      goto LABEL_134;
                    }
                  }
                }
                else
                {
                  LODWORD(v41) = v53 + 56;
                  if ( v53 + 56 <= v52 )
                  {
                    v85 = 1;
                    if ( *(_BYTE *)(v53 + v45 + 10) )
                      v48 = (char *)(v53 + v45 + 24);
                    v49 = *(_BYTE *)(v53 + v45 + 8);
                    v50 = *(_BYTE **)(v53 + v45 + 16);
                    v47 = *(_BYTE *)(v53 + v45 + 9);
                  }
                }
              }
              else
              {
                LODWORD(v41) = v53 + 40;
                if ( v53 + 40 <= v52 )
                {
                  if ( *(_BYTE *)(v53 + v45 + 10) )
                    v48 = (char *)(v53 + v45 + 24);
                  v50 = *(_BYTE **)(v53 + v45 + 16);
LABEL_134:
                  v47 = *(_BYTE *)(v53 + v45 + 9);
                  v49 = *(_BYTE *)(v53 + v45 + 8);
LABEL_135:
                  if ( v48 )
                  {
                    v55 = *v48;
                    goto LABEL_138;
                  }
                  goto LABEL_160;
                }
              }
              if ( v85 )
                goto LABEL_135;
            }
          }
          if ( ++v51 >= v46 )
            goto LABEL_135;
        }
      }
      v55 = *(_BYTE *)(v45 + 72);
      v50 = *(_BYTE **)(v45 + 32);
      v47 = *(_BYTE *)(v45 + 11);
      v49 = *(_BYTE *)(v45 + 4);
      if ( *(_BYTE *)(v45 + 2) )
        goto LABEL_160;
LABEL_138:
      LOBYTE(v41) = v55 - 8;
      if ( (v41 & 0x5D) != 0 )
      {
LABEL_160:
        IofCompleteRequest((PIRP)a2, 0);
        return 0;
      }
      v56 = *(_BYTE *)(v45 + 3);
      if ( v56 == 1 || !v50 || !v47 )
        goto LABEL_155;
      LOBYTE(v45) = 0;
      v41 = (unsigned __int64)&v50[v47];
      v57 = 0;
      v58 = v50 + 8;
      v59 = 0;
      if ( (unsigned __int8)((*v50 & 0x7F) - 114) <= 1u )
      {
        if ( (unsigned __int64)v58 <= v41 )
        {
          v57 = v50[2];
          LOBYTE(v45) = v50[1] & 0xF;
          v59 = v50[3];
          goto LABEL_154;
        }
      }
      else if ( (unsigned __int64)v58 <= v41 )
      {
        v60 = v50 + 13;
        LOBYTE(v45) = v50[2] & 0xF;
        v61 = v47;
        if ( (unsigned int)(unsigned __int8)v50[7] + 8 <= v47 )
          v61 = (unsigned __int8)v50[7] + 8;
        v41 = (unsigned __int64)&v50[v61];
        if ( (unsigned __int64)v60 <= v41 )
          v57 = v50[12];
        if ( (unsigned __int64)(v50 + 14) > v41 )
          v59 = 0;
        else
          v59 = *v60;
LABEL_154:
        if ( v37 )
        {
LABEL_156:
          McTemplateK0pduuuuup_EtwWriteTransfer(
            v41,
            v45,
            (unsigned int)&v89,
            a2,
            *(_DWORD *)(a2 + 48),
            v56,
            v49,
            v45,
            v57,
            v59,
            a2);
          goto LABEL_160;
        }
LABEL_155:
        LOBYTE(v45) = 0;
        v57 = 0;
        v59 = 0;
        goto LABEL_156;
      }
      v37 = 0;
      goto LABEL_154;
    }
    LOBYTE(v62) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    v6 = StorEtwLoggingEnabled == 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_DWORD *)(a2 + 48) = -1073741811;
    if ( v6 )
      goto LABEL_223;
    v89 = 0;
    IoGetActivityIdIrp(a2, &v89);
    v64 = *(_QWORD *)(a2 + 184);
    if ( *(_BYTE *)v64 == 14 )
    {
      if ( (byte_140177432 & 8) != 0 )
        McTemplateK0pd_EtwWriteTransfer(
          *(unsigned int *)(a2 + 48),
          EventNonReadWriteRequestComplete,
          &v89,
          a2,
          *(_DWORD *)(a2 + 48));
      goto LABEL_223;
    }
    if ( *(_BYTE *)v64 != 15 )
    {
      if ( *(_BYTE *)v64 == 27 )
      {
        if ( *(_BYTE *)(v64 + 1) != 7 || *(_DWORD *)(v64 + 8) )
        {
          if ( (byte_140177432 & 0x20) != 0 )
            McTemplateK0pd_EtwWriteTransfer(v63, EventPnpRequestComplete, &v89, a2, *(_DWORD *)(a2 + 48));
        }
        else if ( (byte_140177432 & 0x40) != 0 )
        {
          v65 = *(int **)(a2 + 56);
          if ( v65 )
            v62 = *v65;
          McTemplateK0pqd_EtwWriteTransfer(v63, v64, (unsigned int)&v89, a2, v62, *(_DWORD *)(a2 + 48));
        }
      }
      goto LABEL_223;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_223;
    v66 = *(_QWORD *)(v64 + 8);
    v67 = 1;
    if ( *(_BYTE *)(v66 + 2) == 40 )
    {
      if ( *(_DWORD *)(v66 + 20) )
        goto LABEL_223;
      v68 = *(_DWORD *)(v66 + 56);
      if ( !v68 )
        goto LABEL_223;
      v69 = 0;
      v85 = 0;
      v70 = 0;
      v71 = 0;
      v72 = 0;
      v73 = 0;
      while ( 1 )
      {
        v63 = *(unsigned int *)(v66 + 4LL * v73 + 120);
        if ( (unsigned int)v63 >= 0x80 )
        {
          v74 = *(unsigned int *)(v66 + 16);
          if ( (unsigned int)v63 < (unsigned int)v74 )
          {
            v75 = (unsigned int)v63;
            v76 = *(_DWORD *)(v63 + v66) - 64;
            if ( v76 )
            {
              LODWORD(v63) = v76 - 1;
              if ( (_DWORD)v63 )
              {
                if ( (_DWORD)v63 == 1 )
                {
                  LODWORD(v63) = v75 + 40;
                  if ( v75 + 40 <= v74 )
                  {
                    if ( *(_DWORD *)(v75 + v66 + 12) )
                      v70 = (char *)(v75 + v66 + 32);
                    v72 = *(_BYTE **)(v75 + v66 + 24);
                    goto LABEL_198;
                  }
                }
              }
              else
              {
                LODWORD(v63) = v75 + 56;
                if ( v75 + 56 <= v74 )
                {
                  v85 = 1;
                  if ( *(_BYTE *)(v75 + v66 + 10) )
                    v70 = (char *)(v75 + v66 + 24);
                  v71 = *(_BYTE *)(v75 + v66 + 8);
                  v72 = *(_BYTE **)(v75 + v66 + 16);
                  v69 = *(_BYTE *)(v75 + v66 + 9);
                }
              }
            }
            else
            {
              LODWORD(v63) = v75 + 40;
              if ( v75 + 40 <= v74 )
              {
                if ( *(_BYTE *)(v75 + v66 + 10) )
                  v70 = (char *)(v75 + v66 + 24);
                v72 = *(_BYTE **)(v75 + v66 + 16);
LABEL_198:
                v69 = *(_BYTE *)(v75 + v66 + 9);
                v71 = *(_BYTE *)(v75 + v66 + 8);
LABEL_199:
                if ( v70 )
                {
                  v77 = *v70;
                  goto LABEL_202;
                }
                goto LABEL_223;
              }
            }
            if ( v85 )
              goto LABEL_199;
          }
        }
        if ( ++v73 >= v68 )
          goto LABEL_199;
      }
    }
    v77 = *(_BYTE *)(v66 + 72);
    v72 = *(_BYTE **)(v66 + 32);
    v69 = *(_BYTE *)(v66 + 11);
    v71 = *(_BYTE *)(v66 + 4);
    if ( *(_BYTE *)(v66 + 2) )
      goto LABEL_223;
LABEL_202:
    LOBYTE(v63) = v77 - 8;
    if ( (v63 & 0x5D) != 0 )
    {
LABEL_223:
      IofCompleteRequest((PIRP)a2, 0);
      return 3221225485LL;
    }
    v78 = *(_BYTE *)(v66 + 3);
    if ( v78 == 1 || !v72 || !v69 )
      goto LABEL_219;
    LOBYTE(v66) = 0;
    v63 = (unsigned __int64)&v72[v69];
    v79 = 0;
    v80 = v72 + 8;
    v81 = 0;
    if ( (unsigned __int8)((*v72 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v80 <= v63 )
      {
        v79 = v72[2];
        LOBYTE(v66) = v72[1] & 0xF;
        v81 = v72[3];
        goto LABEL_218;
      }
    }
    else if ( (unsigned __int64)v80 <= v63 )
    {
      v82 = v72 + 13;
      LOBYTE(v66) = v72[2] & 0xF;
      v83 = v69;
      if ( (unsigned int)(unsigned __int8)v72[7] + 8 <= v69 )
        v83 = (unsigned __int8)v72[7] + 8;
      v63 = (unsigned __int64)&v72[v83];
      if ( (unsigned __int64)v82 <= v63 )
        v79 = v72[12];
      if ( (unsigned __int64)(v72 + 14) > v63 )
        v81 = 0;
      else
        v81 = *v82;
LABEL_218:
      if ( v67 )
      {
LABEL_220:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v63,
          v66,
          (unsigned int)&v89,
          a2,
          *(_DWORD *)(a2 + 48),
          v78,
          v71,
          v66,
          v79,
          v81,
          a2);
        goto LABEL_223;
      }
LABEL_219:
      LOBYTE(v66) = 0;
      v79 = 0;
      v81 = 0;
      goto LABEL_220;
    }
    v67 = 0;
    goto LABEL_218;
  }
  LOBYTE(v5) = 0;
  *(_BYTE *)(a2 + 141) = -84;
  v6 = StorEtwLoggingEnabled == 0;
  *(_QWORD *)(a2 + 56) = 0;
  v88 = -1073741820;
  *(_DWORD *)(a2 + 48) = -1073741820;
  if ( v6 )
    goto LABEL_91;
  v89 = 0;
  IoGetActivityIdIrp(a2, &v89);
  v8 = *(unsigned __int8 **)(a2 + 184);
  if ( *v8 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_91;
    v84 = *(_DWORD *)(a2 + 48);
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
        v85 = 0;
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
                    v85 = 1;
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
              if ( v85 )
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
          (unsigned int)&v89,
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
  return v88;
}

```

## disassembly

```asm
0x14005a554  mov     [rsp-8+arg_10], rbx
0x14005a559  push    rbp
0x14005a55a  push    rsi
0x14005a55b  push    rdi
0x14005a55c  push    r12
0x14005a55e  push    r13
0x14005a560  push    r14
0x14005a562  push    r15
0x14005a564  lea     rbp, [rsp-10h]
0x14005a569  sub     rsp, 110h
0x14005a570  mov     rax, cs:__security_cookie
0x14005a577  xor     rax, rsp
0x14005a57a  mov     [rbp+40h+var_40], rax
0x14005a57e  mov     rax, [rdx+0B8h]
0x14005a585  mov     r14d, 28h ; '('
0x14005a58b  mov     rdi, rdx
0x14005a58e  mov     r8, rcx
0x14005a591  cmp     [rax+10h], r14d
0x14005a595  jnb     loc_14005A87A
0x14005a59b  xor     ebx, ebx
0x14005a59d  mov     byte ptr [rdx+8Dh], 0ACh
0x14005a5a4  cmp     cs:StorEtwLoggingEnabled, bl
0x14005a5aa  mov     eax, 0C0000004h
0x14005a5af  mov     [rdx+38h], rbx
0x14005a5b3  mov     [rsp+140h+var_DC], eax
0x14005a5b7  mov     [rdx+30h], eax
0x14005a5ba  jz      loc_14005A9DD
0x14005a5c0  xorps   xmm0, xmm0
0x14005a5c3  lea     rdx, [rsp+140h+var_D8]
0x14005a5c8  mov     rcx, rdi
0x14005a5cb  movups  [rsp+140h+var_D8], xmm0
0x14005a5d0  call    cs:__imp_IoGetActivityIdIrp
0x14005a5d7  nop     dword ptr [rax+rax+00h]
0x14005a5dc  mov     rdx, [rdi+0B8h]
0x14005a5e3  movzx   eax, byte ptr [rdx]
0x14005a5e6  sub     eax, 0Eh
0x14005a5e9  jz      loc_14005A861
0x14005a5ef  sub     eax, 1
0x14005a5f2  jz      short loc_14005A65D
0x14005a5f4  cmp     eax, 0Ch
0x14005a5f7  jnz     loc_14005A9DD
0x14005a5fd  cmp     byte ptr [rdx+1], 7
0x14005a601  jnz     short loc_14005A63D
0x14005a603  cmp     [rdx+8], ebx
0x14005a606  jnz     short loc_14005A63D
0x14005a608  test    cs:byte_140177432, 40h
0x14005a60f  jz      loc_14005A9DD
0x14005a615  mov     rax, [rdi+38h]
0x14005a619  test    rax, rax
0x14005a61c  jz      short loc_14005A620
0x14005a61e  mov     ebx, [rax]
0x14005a620  mov     eax, [rdi+30h]
0x14005a623  lea     r8, [rsp+140h+var_D8]
0x14005a628  mov     dword ptr [rsp+140h+var_118], eax
0x14005a62c  mov     r9, rdi
0x14005a62f  mov     [rsp+140h+var_120], ebx
0x14005a633  call    McTemplateK0pqd_EtwWriteTransfer
0x14005a638  jmp     loc_14005A9DD
0x14005a63d  test    cs:byte_140177432, 20h
0x14005a644  jz      loc_14005A9DD
0x14005a64a  mov     eax, [rdi+30h]
0x14005a64d  lea     rdx, EventPnpRequestComplete
0x14005a654  mov     [rsp+140h+var_120], eax
0x14005a658  jmp     loc_14005A9D0
0x14005a65d  cmp     cs:byte_140177431, bl
0x14005a663  jge     loc_14005A9DD
0x14005a669  mov     rdx, [rdx+8]
0x14005a66d  mov     esi, 1
0x14005a672  movzx   eax, byte ptr [rdx+2]
0x14005a676  cmp     al, r14b
0x14005a679  jnz     loc_14005A766
0x14005a67f  cmp     [rdx+14h], ebx
0x14005a682  jnz     loc_14005A9DD
0x14005a688  mov     r13d, [rdx+38h]
0x14005a68c  test    r13d, r13d
0x14005a68f  jz      loc_14005A9DD
0x14005a695  mov     r10b, bl
0x14005a698  mov     [rsp+140h+var_E0], bl
0x14005a69c  mov     r11, rbx
0x14005a69f  mov     r12b, bl
0x14005a6a2  mov     r9, rbx
0x14005a6a5  mov     r15d, ebx
0x14005a6a8  mov     eax, r15d
0x14005a6ab  mov     ecx, [rdx+rax*4+78h]
0x14005a6af  cmp     ecx, 80h
0x14005a6b5  jb      short loc_14005A72D
0x14005a6b7  mov     r14d, [rdx+10h]
0x14005a6bb  cmp     ecx, r14d
0x14005a6be  jnb     short loc_14005A72D
0x14005a6c0  mov     r8d, ecx
0x14005a6c3  mov     ecx, [rcx+rdx]
0x14005a6c6  sub     ecx, 40h ; '@'
0x14005a6c9  jz      short loc_14005A71E
0x14005a6cb  sub     ecx, esi
0x14005a6cd  jz      short loc_14005A6F1
0x14005a6cf  cmp     ecx, esi
0x14005a6d1  jnz     short loc_14005A727
0x14005a6d3  lea     rcx, [r8+28h]
0x14005a6d7  cmp     rcx, r14
0x14005a6da  ja      short loc_14005A727
0x14005a6dc  cmp     [r8+rdx+0Ch], ebx
0x14005a6e1  jbe     short loc_14005A6EA
0x14005a6e3  lea     r11, [rdx+20h]
0x14005a6e7  add     r11, r8
0x14005a6ea  mov     r9, [r8+rdx+18h]
0x14005a6ef  jmp     short loc_14005A74E
0x14005a6f1  lea     rcx, [r8+38h]
0x14005a6f5  cmp     rcx, r14
0x14005a6f8  ja      short loc_14005A727
0x14005a6fa  mov     [rsp+140h+var_E0], sil
0x14005a6ff  cmp     [r8+rdx+0Ah], bl
0x14005a704  jbe     short loc_14005A70D
0x14005a706  lea     r11, [rdx+18h]
0x14005a70a  add     r11, r8
0x14005a70d  mov     r12b, [r8+rdx+8]
0x14005a712  mov     r9, [r8+rdx+10h]
0x14005a717  mov     r10b, [r8+rdx+9]
0x14005a71c  jmp     short loc_14005A727
0x14005a71e  lea     rcx, [r8+28h]
0x14005a722  cmp     rcx, r14
0x14005a725  jbe     short loc_14005A73B
0x14005a727  cmp     [rsp+140h+var_E0], bl
0x14005a72b  jnz     short loc_14005A758
0x14005a72d  add     r15d, esi
0x14005a730  cmp     r15d, r13d
0x14005a733  jb      loc_14005A6A8
0x14005a739  jmp     short loc_14005A758
0x14005a73b  cmp     [r8+rdx+0Ah], bl
0x14005a740  jbe     short loc_14005A749
0x14005a742  lea     r11, [rdx+18h]
0x14005a746  add     r11, r8
0x14005a749  mov     r9, [r8+rdx+10h]
0x14005a74e  mov     r10b, [r8+rdx+9]
0x14005a753  mov     r12b, [r8+rdx+8]
0x14005a758  test    r11, r11
0x14005a75b  jz      loc_14005A9DD
0x14005a761  mov     cl, [r11]
0x14005a764  jmp     short loc_14005A77D
0x14005a766  mov     r12b, [rdx+4]
0x14005a76a  mov     r10b, [rdx+0Bh]
0x14005a76e  mov     r9, [rdx+20h]
0x14005a772  mov     cl, [rdx+48h]
0x14005a775  test    eax, eax
0x14005a777  jnz     loc_14005A9DD
0x14005a77d  sub     cl, 8
0x14005a780  test    cl, 5Dh
0x14005a783  jnz     loc_14005A9DD
0x14005a789  mov     r14b, [rdx+3]
0x14005a78d  cmp     r14b, sil
0x14005a790  jz      loc_14005A823
0x14005a796  test    r9, r9
0x14005a799  jz      loc_14005A823
0x14005a79f  test    r10b, r10b
0x14005a7a2  jz      short loc_14005A823
0x14005a7a4  mov     al, [r9]
0x14005a7a7  mov     r8b, bl
0x14005a7aa  and     al, 7Fh
0x14005a7ac  movzx   ecx, r10b
0x14005a7b0  sub     al, 72h ; 'r'
0x14005a7b2  add     rcx, r9
0x14005a7b5  cmp     al, sil
0x14005a7b8  mov     r11b, bl
0x14005a7bb  lea     rax, [r9+8]
0x14005a7bf  mov     dl, bl
0x14005a7c1  jbe     short loc_14005A805
0x14005a7c3  cmp     rax, rcx
0x14005a7c6  ja      short loc_14005A81B
0x14005a7c8  movzx   ecx, byte ptr [r9+7]
0x14005a7cd  lea     r8, [r9+0Dh]
0x14005a7d1  mov     dl, [r9+2]
0x14005a7d5  add     ecx, 8
0x14005a7d8  and     dl, 0Fh
0x14005a7db  movzx   eax, r10b
0x14005a7df  cmp     ecx, eax
0x14005a7e1  cmovbe  eax, ecx
0x14005a7e4  mov     ecx, eax
0x14005a7e6  add     rcx, r9
0x14005a7e9  cmp     r8, rcx
0x14005a7ec  ja      short loc_14005A7F2
0x14005a7ee  mov     r11b, [r9+0Ch]
0x14005a7f2  lea     rax, [r9+0Eh]
0x14005a7f6  cmp     rax, rcx
0x14005a7f9  ja      short loc_14005A800
0x14005a7fb  mov     r8b, [r8]
0x14005a7fe  jmp     short loc_14005A81E
0x14005a800  mov     r8b, bl
0x14005a803  jmp     short loc_14005A81E
0x14005a805  cmp     rax, rcx
0x14005a808  ja      short loc_14005A81B
0x14005a80a  mov     dl, [r9+1]
0x14005a80e  mov     r11b, [r9+2]
0x14005a812  and     dl, 0Fh
0x14005a815  mov     r8b, [r9+3]
0x14005a819  jmp     short loc_14005A81E
0x14005a81b  mov     sil, bl
0x14005a81e  test    sil, sil
0x14005a821  jnz     short loc_14005A82B
0x14005a823  mov     dl, bl
0x14005a825  mov     r11b, bl
0x14005a828  mov     r8b, bl
0x14005a82b  mov     eax, [rdi+30h]
0x14005a82e  mov     r9, rdi
0x14005a831  mov     [rsp+140h+var_F0], rdi
0x14005a836  mov     [rsp+140h+var_F8], r8b
0x14005a83b  lea     r8, [rsp+140h+var_D8]
0x14005a840  mov     [rsp+140h+var_100], r11b
0x14005a845  mov     [rsp+140h+var_108], dl
0x14005a849  mov     [rsp+140h+var_110], r12b
0x14005a84e  mov     byte ptr [rsp+140h+var_118], r14b
0x14005a853  mov     [rsp+140h+var_120], eax
0x14005a857  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x14005a85c  jmp     loc_14005A9DD
0x14005a861  test    cs:byte_140177432, 8
0x14005a868  jz      loc_14005A9DD
0x14005a86e  mov     eax, [rdi+30h]
0x14005a871  mov     [rsp+140h+var_120], eax
0x14005a875  jmp     loc_14005A9C9
0x14005a87a  cmp     [rax+8], r14d
0x14005a87e  jnb     loc_14005A9F7
0x14005a884  xor     ebx, ebx
0x14005a886  mov     byte ptr [rdx+8Dh], 0ACh
0x14005a88d  cmp     cs:StorEtwLoggingEnabled, bl
0x14005a893  mov     eax, 0C0000023h
0x14005a898  mov     [rdx+38h], rbx
0x14005a89c  mov     [rsp+140h+var_DC], eax
0x14005a8a0  mov     [rdx+30h], eax
0x14005a8a3  jz      loc_14005A9DD
0x14005a8a9  xorps   xmm0, xmm0
0x14005a8ac  lea     rdx, [rsp+140h+var_D8]
0x14005a8b1  mov     rcx, rdi
0x14005a8b4  movups  [rsp+140h+var_D8], xmm0
0x14005a8b9  call    cs:__imp_IoGetActivityIdIrp
0x14005a8c0  nop     dword ptr [rax+rax+00h]
0x14005a8c5  mov     rdx, [rdi+0B8h]
0x14005a8cc  movzx   eax, byte ptr [rdx]
0x14005a8cf  sub     eax, 0Eh
0x14005a8d2  jz      loc_14005A9B9
0x14005a8d8  sub     eax, 1
0x14005a8db  jnz     loc_14005A5F4
0x14005a8e1  cmp     cs:byte_140177431, bl
0x14005a8e7  jge     loc_14005A9DD
0x14005a8ed  mov     rdx, [rdx+8]
0x14005a8f1  lea     esi, [rbx+1]
0x14005a8f4  movzx   eax, byte ptr [rdx+2]
0x14005a8f8  cmp     al, r14b
0x14005a8fb  jnz     loc_14005A766
0x14005a901  cmp     [rdx+14h], ebx
0x14005a904  jnz     loc_14005A9DD
0x14005a90a  mov     r13d, [rdx+38h]
0x14005a90e  test    r13d, r13d
0x14005a911  jz      loc_14005A9DD
0x14005a917  mov     r10b, bl
0x14005a91a  mov     [rsp+140h+var_E0], bl
0x14005a91e  mov     r11d, ebx
0x14005a921  mov     r12b, bl
0x14005a924  mov     r9d, ebx
0x14005a927  mov     r15d, ebx
0x14005a92a  mov     eax, r15d
0x14005a92d  mov     ecx, [rdx+rax*4+78h]
0x14005a931  cmp     ecx, 80h
0x14005a937  jb      short loc_14005A9A8
0x14005a939  mov     r14d, [rdx+10h]
0x14005a93d  cmp     ecx, r14d
0x14005a940  jnb     short loc_14005A9A8
0x14005a942  mov     r8d, ecx
0x14005a945  mov     ecx, [rcx+rdx]
0x14005a948  sub     ecx, 40h ; '@'
0x14005a94b  jz      short loc_14005A991
0x14005a94d  sub     ecx, esi
0x14005a94f  jz      short loc_14005A964
0x14005a951  cmp     ecx, esi
0x14005a953  jnz     short loc_14005A99E
0x14005a955  lea     rcx, [r8+28h]
0x14005a959  cmp     rcx, r14
0x14005a95c  jbe     loc_14005A6DC
0x14005a962  jmp     short loc_14005A99E
0x14005a964  lea     rcx, [r8+38h]
0x14005a968  cmp     rcx, r14
0x14005a96b  ja      short loc_14005A99E
0x14005a96d  mov     [rsp+140h+var_E0], sil
0x14005a972  cmp     [r8+rdx+0Ah], bl
0x14005a977  jbe     short loc_14005A980
0x14005a979  lea     r11, [rdx+18h]
0x14005a97d  add     r11, r8
0x14005a980  mov     r12b, [r8+rdx+8]
0x14005a985  mov     r9, [r8+rdx+10h]
0x14005a98a  mov     r10b, [r8+rdx+9]
0x14005a98f  jmp     short loc_14005A99E
0x14005a991  lea     rcx, [r8+28h]
0x14005a995  cmp     rcx, r14
0x14005a998  jbe     loc_14005A73B
0x14005a99e  cmp     [rsp+140h+var_E0], bl
0x14005a9a2  jnz     loc_14005A758
0x14005a9a8  add     r15d, esi
0x14005a9ab  cmp     r15d, r13d
0x14005a9ae  jb      loc_14005A92A
0x14005a9b4  jmp     loc_14005A758
0x14005a9b9  test    cs:byte_140177432, 8
0x14005a9c0  jz      short loc_14005A9DD
0x14005a9c2  mov     edx, [rdi+30h]
  ... truncated ...
```
