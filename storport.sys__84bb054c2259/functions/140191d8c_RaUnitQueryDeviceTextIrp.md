# RaUnitQueryDeviceTextIrp

- ea: `0x140191d8c`
- end: `0x1401927f2`
- name: `RaUnitQueryDeviceTextIrp`
- size: `2662`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14004018c`

## callees

- `0x1400290b0`
- `0x140046bcc`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400cd1f4`
- `0x1400cd244`
- `0x14014b400`
- `0x140191d8c`
- `0x1401bd878`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140191e5d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140191ff4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401923ce`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140192506`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140191e5d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140191ff4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401923ce`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140192506`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192248`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192248`
- `ntoskrnl!IofCompleteRequest` at `0x140192222`
- `ntoskrnl!IofCompleteRequest` at `0x1401927b9`
- `ntoskrnl!IofCompleteRequest` at `0x140192222`
- `ntoskrnl!IofCompleteRequest` at `0x1401927b9`

## pseudocode

```c
__int64 __fastcall RaUnitQueryDeviceTextIrp(__int64 a1, __int64 a2)
{
  _DWORD *v2; // rax
  char v4; // r12
  _DWORD *v6; // r13
  unsigned int v7; // r15d
  wchar_t *Pool; // rax
  wchar_t *v9; // rsi
  char v10; // di
  bool v11; // zf
  unsigned __int64 v12; // rcx
  unsigned __int8 *v13; // rdx
  int v14; // eax
  int *v15; // rax
  int v16; // ecx
  __int64 *v17; // rdx
  __int64 v18; // rdx
  int v19; // eax
  unsigned int v20; // r15d
  _BYTE *v21; // r9
  __int64 v22; // r14
  char v23; // r13
  unsigned __int8 v24; // r10
  char *v25; // r11
  unsigned __int64 v26; // rsi
  __int64 v27; // r8
  int v28; // ecx
  char v29; // r8
  unsigned int v30; // r15d
  __int64 v31; // r14
  char v32; // r13
  unsigned __int64 v33; // rsi
  int v34; // ecx
  char v35; // cl
  char v36; // si
  char v37; // r11
  _BYTE *v38; // rax
  char *v39; // r8
  unsigned int v40; // eax
  int v42; // eax
  __int64 v43; // rax
  _BYTE *v44; // r9
  _BYTE *v45; // rax
  _BYTE *v46; // r9
  _QWORD *DeviceType; // rax
  unsigned int v48; // r15d
  __int64 v49; // r14
  char v50; // r13
  unsigned __int64 v51; // rsi
  int v52; // ecx
  unsigned __int64 v53; // rcx
  __int64 v54; // rdx
  int *v55; // rax
  int v56; // ecx
  __int64 v57; // rdx
  char v58; // di
  unsigned int v59; // r15d
  _BYTE *v60; // r9
  __int64 v61; // r14
  char v62; // r13
  unsigned __int8 v63; // r10
  char *v64; // r11
  unsigned __int64 v65; // rsi
  __int64 v66; // r8
  int v67; // ecx
  char v68; // cl
  char v69; // si
  char v70; // r11
  char v71; // r8
  _BYTE *v72; // rax
  char *v73; // r8
  unsigned int v74; // eax
  unsigned int v75; // [rsp+60h] [rbp-29h]
  __int128 v76; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v77[16]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v78[24]; // [rsp+88h] [rbp-1h] BYREF

  v2 = *(_DWORD **)(a1 + 24);
  v4 = 0;
  if ( *v2 == 1094997074 )
  {
    v6 = v2 + 90;
  }
  else
  {
    if ( *v2 != 1314275652 )
      goto LABEL_140;
    v6 = v2 + 44;
  }
  if ( !v6 )
  {
LABEL_140:
    v11 = StorEtwLoggingEnabled == 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = -1073741811;
    if ( v11 )
      goto LABEL_203;
    v76 = 0;
    IoGetActivityIdIrp(a2, &v76);
    v54 = *(_QWORD *)(a2 + 184);
    if ( *(_BYTE *)v54 == 14 )
    {
      if ( (byte_140177432 & 8) != 0 )
        McTemplateK0pd_EtwWriteTransfer(
          *(unsigned int *)(a2 + 48),
          EventNonReadWriteRequestComplete,
          &v76,
          a2,
          *(_DWORD *)(a2 + 48));
      goto LABEL_203;
    }
    if ( *(_BYTE *)v54 != 15 )
    {
      if ( *(_BYTE *)v54 == 27 )
      {
        if ( *(_BYTE *)(v54 + 1) != 7 || *(_DWORD *)(v54 + 8) )
        {
          if ( (byte_140177432 & 0x20) != 0 )
            McTemplateK0pd_EtwWriteTransfer(v53, EventPnpRequestComplete, &v76, a2, *(_DWORD *)(a2 + 48));
        }
        else if ( (byte_140177432 & 0x40) != 0 )
        {
          v55 = *(int **)(a2 + 56);
          if ( v55 )
            v56 = *v55;
          else
            v56 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v56, v54, (unsigned int)&v76, a2, v56, *(_DWORD *)(a2 + 48));
        }
      }
      goto LABEL_203;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_203;
    v57 = *(_QWORD *)(v54 + 8);
    v58 = 1;
    if ( *(_BYTE *)(v57 + 2) == 40 )
    {
      if ( *(_DWORD *)(v57 + 20) )
        goto LABEL_203;
      v59 = *(_DWORD *)(v57 + 56);
      if ( !v59 )
        goto LABEL_203;
      v60 = 0;
      v61 = 0;
      v62 = 0;
      v63 = 0;
      v64 = 0;
      while ( 1 )
      {
        v53 = *(unsigned int *)(v57 + 4 * v61 + 120);
        if ( (unsigned int)v53 >= 0x80 )
        {
          v65 = *(unsigned int *)(v57 + 16);
          if ( (unsigned int)v53 < (unsigned int)v65 )
          {
            v66 = (unsigned int)v53;
            v67 = *(_DWORD *)(v53 + v57) - 64;
            if ( v67 )
            {
              LODWORD(v53) = v67 - 1;
              if ( (_DWORD)v53 )
              {
                if ( (_DWORD)v53 == 1 )
                {
                  LODWORD(v53) = v66 + 40;
                  if ( v66 + 40 <= v65 )
                  {
                    if ( *(_DWORD *)(v66 + v57 + 12) )
                      v64 = (char *)(v66 + v57 + 32);
                    v60 = *(_BYTE **)(v66 + v57 + 24);
                    goto LABEL_178;
                  }
                }
              }
              else
              {
                LODWORD(v53) = v66 + 56;
                if ( v66 + 56 <= v65 )
                {
                  v62 = 1;
                  if ( *(_BYTE *)(v66 + v57 + 10) )
                    v64 = (char *)(v66 + v57 + 24);
                  v4 = *(_BYTE *)(v66 + v57 + 8);
                  v60 = *(_BYTE **)(v66 + v57 + 16);
                  v63 = *(_BYTE *)(v66 + v57 + 9);
                }
              }
            }
            else
            {
              LODWORD(v53) = v66 + 40;
              if ( v66 + 40 <= v65 )
              {
                if ( *(_BYTE *)(v66 + v57 + 10) )
                  v64 = (char *)(v66 + v57 + 24);
                v60 = *(_BYTE **)(v66 + v57 + 16);
LABEL_178:
                v63 = *(_BYTE *)(v66 + v57 + 9);
                v4 = *(_BYTE *)(v66 + v57 + 8);
LABEL_179:
                if ( v64 )
                {
                  v68 = *v64;
                  goto LABEL_182;
                }
                goto LABEL_203;
              }
            }
            if ( v62 )
              goto LABEL_179;
          }
        }
        v61 = (unsigned int)(v61 + 1);
        if ( (unsigned int)v61 >= v59 )
          goto LABEL_179;
      }
    }
    v68 = *(_BYTE *)(v57 + 72);
    v60 = *(_BYTE **)(v57 + 32);
    v63 = *(_BYTE *)(v57 + 11);
    v4 = *(_BYTE *)(v57 + 4);
    if ( *(_BYTE *)(v57 + 2) )
      goto LABEL_203;
LABEL_182:
    LOBYTE(v53) = v68 - 8;
    if ( (v53 & 0x5D) != 0 )
    {
LABEL_203:
      IofCompleteRequest((PIRP)a2, 0);
      return 3221225485LL;
    }
    v69 = *(_BYTE *)(v57 + 3);
    if ( v69 == 1 || !v60 || !v63 )
      goto LABEL_199;
    LOBYTE(v57) = 0;
    v70 = 0;
    v71 = 0;
    v53 = (unsigned __int64)&v60[v63];
    v72 = v60 + 8;
    if ( (unsigned __int8)((*v60 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v72 <= v53 )
      {
        v70 = v60[2];
        LOBYTE(v57) = v60[1] & 0xF;
        v71 = v60[3];
        goto LABEL_198;
      }
    }
    else if ( (unsigned __int64)v72 <= v53 )
    {
      v73 = v60 + 13;
      LOBYTE(v57) = v60[2] & 0xF;
      v74 = v63;
      if ( (unsigned int)(unsigned __int8)v60[7] + 8 <= v63 )
        v74 = (unsigned __int8)v60[7] + 8;
      v53 = (unsigned __int64)&v60[v74];
      if ( (unsigned __int64)v73 <= v53 )
        v70 = v60[12];
      if ( (unsigned __int64)(v60 + 14) > v53 )
        v71 = 0;
      else
        v71 = *v73;
LABEL_198:
      if ( v58 )
      {
LABEL_200:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v53,
          v57,
          (unsigned int)&v76,
          a2,
          *(_DWORD *)(a2 + 48),
          v69,
          v4,
          v57,
          v70,
          v71,
          a2);
        goto LABEL_203;
      }
LABEL_199:
      LOBYTE(v57) = 0;
      v70 = 0;
      v71 = 0;
      goto LABEL_200;
    }
    v58 = 0;
    goto LABEL_198;
  }
  v7 = *(_DWORD *)(*(_QWORD *)(a2 + 184) + 8LL);
  Pool = (wchar_t *)RaidAllocatePool(256, 512, 1414619474, *(_QWORD *)(a1 + 8));
  v9 = Pool;
  v10 = 1;
  if ( Pool )
  {
    if ( v7 )
    {
      if ( v7 != 1 )
      {
        ExFreePoolWithTag(Pool, 0x54516152u);
        v42 = -1073741637;
        v9 = 0;
LABEL_115:
        v11 = StorEtwLoggingEnabled == 0;
        v75 = v42;
        *(_QWORD *)(a2 + 56) = v9;
        *(_BYTE *)(a2 + 141) = -84;
        *(_DWORD *)(a2 + 48) = v42;
        if ( v11 )
          goto LABEL_95;
        v76 = 0;
        IoGetActivityIdIrp(a2, &v76);
        v13 = *(unsigned __int8 **)(a2 + 184);
        if ( *v13 == 14 )
        {
          if ( (byte_140177432 & 8) != 0 )
            McTemplateK0pd_EtwWriteTransfer(
              *(unsigned int *)(a2 + 48),
              EventNonReadWriteRequestComplete,
              &v76,
              a2,
              *(_DWORD *)(a2 + 48));
          goto LABEL_95;
        }
        v14 = *v13 - 15;
        if ( *v13 != 15 )
          goto LABEL_11;
        if ( byte_140177431 >= 0 )
          goto LABEL_95;
        v18 = *((_QWORD *)v13 + 1);
        v19 = *(unsigned __int8 *)(v18 + 2);
        if ( (_BYTE)v19 == 40 )
        {
          if ( *(_DWORD *)(v18 + 20) )
            goto LABEL_95;
          v48 = *(_DWORD *)(v18 + 56);
          if ( !v48 )
            goto LABEL_95;
          v21 = 0;
          v49 = 0;
          v50 = 0;
          v24 = 0;
          v25 = 0;
          while ( 1 )
          {
            v12 = *(unsigned int *)(v18 + 4 * v49 + 120);
            if ( (unsigned int)v12 >= 0x80 )
            {
              v51 = *(unsigned int *)(v18 + 16);
              if ( (unsigned int)v12 < (unsigned int)v51 )
              {
                v27 = (unsigned int)v12;
                v52 = *(_DWORD *)(v12 + v18) - 64;
                if ( v52 )
                {
                  LODWORD(v12) = v52 - 1;
                  if ( (_DWORD)v12 )
                  {
                    if ( (_DWORD)v12 == 1 )
                    {
                      LODWORD(v12) = v27 + 40;
                      if ( v27 + 40 <= v51 )
                      {
LABEL_32:
                        if ( *(_DWORD *)(v27 + v18 + 12) )
                          v25 = (char *)(v27 + v18 + 32);
                        v21 = *(_BYTE **)(v27 + v18 + 24);
                        goto LABEL_70;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v12) = v27 + 56;
                    if ( v27 + 56 <= v51 )
                    {
                      v50 = 1;
                      if ( *(_BYTE *)(v27 + v18 + 10) )
                        v25 = (char *)(v27 + v18 + 24);
                      v4 = *(_BYTE *)(v27 + v18 + 8);
                      v21 = *(_BYTE **)(v27 + v18 + 16);
                      v24 = *(_BYTE *)(v27 + v18 + 9);
                    }
                  }
                }
                else
                {
                  LODWORD(v12) = v27 + 40;
                  if ( v27 + 40 <= v51 )
                  {
LABEL_67:
                    if ( *(_BYTE *)(v27 + v18 + 10) )
                      v25 = (char *)(v27 + v18 + 24);
                    v21 = *(_BYTE **)(v27 + v18 + 16);
LABEL_70:
                    v24 = *(_BYTE *)(v27 + v18 + 9);
                    v4 = *(_BYTE *)(v27 + v18 + 8);
LABEL_71:
                    if ( v25 )
                    {
                      v35 = *v25;
                      goto LABEL_74;
                    }
                    goto LABEL_95;
                  }
                }
                if ( v50 )
                  goto LABEL_71;
              }
            }
            v49 = (unsigned int)(v49 + 1);
            if ( (unsigned int)v49 >= v48 )
              goto LABEL_71;
          }
        }
        goto LABEL_73;
      }
      RtlStringCchPrintfW(
        Pool,
        0x100u,
        L"Bus Number %d, Target Id %d, LUN %d",
        *(unsigned __int8 *)(a1 + 104),
        *(unsigned __int8 *)(a1 + 105),
        *(unsigned __int8 *)(a1 + 106));
LABEL_114:
      v42 = 0;
      goto LABEL_115;
    }
    if ( (*(_DWORD *)(a1 + 1952) & 1) != 0 )
    {
      RtlStringCchPrintfW(Pool, 0x100u, L"VM passthrough LUN device");
      goto LABEL_114;
    }
    StorGetIdentityVendorId(a1 + 112, v77);
    StorGetIdentityProductId(a1 + 112, v78);
    if ( (*(_DWORD *)(*((_QWORD *)v6 + 29) + 184LL) & 0x10) == 0 )
    {
      if ( (*(_DWORD *)(a1 + 1952) & 0x20) != 0 )
      {
        RtlStringCchPrintfW(v9, 0x100u, L"NVMe %hs %hs Device", v78, "ZNSDisk");
      }
      else
      {
        DeviceType = (_QWORD *)PortGetDeviceType(**(_BYTE **)(a1 + 112) & 0x1F);
        RtlStringCchPrintfW(v9, 0x100u, L"%hs %hs SCSI %hs Device", v77, v78, *DeviceType);
      }
      goto LABEL_114;
    }
    v43 = *(_QWORD *)(a1 + 160);
    if ( v43 )
    {
      v44 = (_BYTE *)(v43 + 8);
      v45 = (_BYTE *)(v43 + 25);
      if ( *v44 )
      {
LABEL_105:
        RtlStringCchPrintfW(v9, 0x100u, L"%hs %hs", v44, v45);
        goto LABEL_114;
      }
      v46 = v45;
    }
    else
    {
      v46 = *(_BYTE **)(a1 + 152);
      if ( !v46 )
      {
        v45 = v78;
        v44 = v77;
        goto LABEL_105;
      }
    }
    RtlStringCchPrintfW(v9, 0x100u, L"%hs", v46);
    goto LABEL_114;
  }
  *(_BYTE *)(a2 + 141) = -84;
  if ( v7 > 1 )
  {
    v11 = StorEtwLoggingEnabled == 0;
    v75 = -1073741637;
    *(_DWORD *)(a2 + 48) = -1073741637;
    if ( v11 )
      goto LABEL_95;
    v76 = 0;
    IoGetActivityIdIrp(a2, &v76);
    v13 = *(unsigned __int8 **)(a2 + 184);
    if ( *v13 != 14 )
    {
      v14 = *v13 - 15;
      if ( *v13 != 15 )
      {
LABEL_11:
        if ( v14 != 12 )
          goto LABEL_95;
        if ( v13[1] == 7 && !*((_DWORD *)v13 + 2) )
        {
          if ( (byte_140177432 & 0x40) != 0 )
          {
            v15 = *(int **)(a2 + 56);
            if ( v15 )
              v16 = *v15;
            else
              v16 = 0;
            McTemplateK0pqd_EtwWriteTransfer(v16, (_DWORD)v13, (unsigned int)&v76, a2, v16, *(_DWORD *)(a2 + 48));
          }
          goto LABEL_95;
        }
        if ( (byte_140177432 & 0x20) == 0 )
          goto LABEL_95;
        v17 = EventPnpRequestComplete;
LABEL_94:
        McTemplateK0pd_EtwWriteTransfer(v12, v17, &v76, a2, *(_DWORD *)(a2 + 48));
        goto LABEL_95;
      }
      if ( byte_140177431 >= 0 )
        goto LABEL_95;
      v18 = *((_QWORD *)v13 + 1);
      v19 = *(unsigned __int8 *)(v18 + 2);
      if ( (_BYTE)v19 == 40 )
      {
        if ( !*(_DWORD *)(v18 + 20) )
        {
          v20 = *(_DWORD *)(v18 + 56);
          if ( v20 )
          {
            v21 = 0;
            v22 = 0;
            v23 = 0;
            v24 = 0;
            v25 = 0;
            while ( 1 )
            {
              v12 = *(unsigned int *)(v18 + 4 * v22 + 120);
              if ( (unsigned int)v12 >= 0x80 )
              {
                v26 = *(unsigned int *)(v18 + 16);
                if ( (unsigned int)v12 < (unsigned int)v26 )
                {
                  v27 = (unsigned int)v12;
                  v28 = *(_DWORD *)(v12 + v18) - 64;
                  if ( v28 )
                  {
                    LODWORD(v12) = v28 - 1;
                    if ( (_DWORD)v12 )
                    {
                      if ( (_DWORD)v12 == 1 )
                      {
                        LODWORD(v12) = v27 + 40;
                        if ( v27 + 40 <= v26 )
                          goto LABEL_32;
                      }
                    }
                    else
                    {
                      LODWORD(v12) = v27 + 56;
                      if ( v27 + 56 <= v26 )
                      {
                        v23 = 1;
                        if ( *(_BYTE *)(v27 + v18 + 10) )
                          v25 = (char *)(v27 + v18 + 24);
                        v4 = *(_BYTE *)(v27 + v18 + 8);
                        v21 = *(_BYTE **)(v27 + v18 + 16);
                        v24 = *(_BYTE *)(v27 + v18 + 9);
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v12) = v27 + 40;
                    if ( v27 + 40 <= v26 )
                      goto LABEL_67;
                  }
                  if ( v23 )
                    goto LABEL_71;
                }
              }
              v22 = (unsigned int)(v22 + 1);
              if ( (unsigned int)v22 >= v20 )
                goto LABEL_71;
            }
          }
        }
        goto LABEL_95;
      }
      goto LABEL_73;
    }
LABEL_92:
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_95;
    v17 = EventNonReadWriteRequestComplete;
    goto LABEL_94;
  }
  v11 = StorEtwLoggingEnabled == 0;
  v75 = -1073741801;
  *(_DWORD *)(a2 + 48) = -1073741801;
  if ( v11 )
    goto LABEL_95;
  v76 = 0;
  IoGetActivityIdIrp(a2, &v76);
  v13 = *(unsigned __int8 **)(a2 + 184);
  if ( *v13 == 14 )
    goto LABEL_92;
  v14 = *v13 - 15;
  if ( *v13 != 15 )
    goto LABEL_11;
  if ( byte_140177431 >= 0 )
    goto LABEL_95;
  v18 = *((_QWORD *)v13 + 1);
  v19 = *(unsigned __int8 *)(v18 + 2);
  if ( (_BYTE)v19 == 40 )
  {
    if ( !*(_DWORD *)(v18 + 20) )
    {
      v30 = *(_DWORD *)(v18 + 56);
      if ( v30 )
      {
        v21 = 0;
        v31 = 0;
        v32 = 0;
        v24 = 0;
        v25 = 0;
        while ( 1 )
        {
          v12 = *(unsigned int *)(v18 + 4 * v31 + 120);
          if ( (unsigned int)v12 >= 0x80 )
          {
            v33 = *(unsigned int *)(v18 + 16);
            if ( (unsigned int)v12 < (unsigned int)v33 )
            {
              v27 = (unsigned int)v12;
              v34 = *(_DWORD *)(v12 + v18) - 64;
              if ( v34 )
              {
                LODWORD(v12) = v34 - 1;
                if ( (_DWORD)v12 )
                {
                  if ( (_DWORD)v12 == 1 )
                  {
                    LODWORD(v12) = v27 + 40;
                    if ( v27 + 40 <= v33 )
                      goto LABEL_32;
                  }
                }
                else
                {
                  LODWORD(v12) = v27 + 56;
                  if ( v27 + 56 <= v33 )
                  {
                    v32 = 1;
                    if ( *(_BYTE *)(v27 + v18 + 10) )
                      v25 = (char *)(v27 + v18 + 24);
                    v4 = *(_BYTE *)(v27 + v18 + 8);
                    v21 = *(_BYTE **)(v27 + v18 + 16);
                    v24 = *(_BYTE *)(v27 + v18 + 9);
                  }
                }
              }
              else
              {
                LODWORD(v12) = v27 + 40;
                if ( v27 + 40 <= v33 )
                  goto LABEL_67;
              }
              if ( v32 )
                goto LABEL_71;
            }
          }
          v31 = (unsigned int)(v31 + 1);
          if ( (unsigned int)v31 >= v30 )
            goto LABEL_71;
        }
      }
    }
    goto LABEL_95;
  }
LABEL_73:
  v35 = *(_BYTE *)(v18 + 72);
  v21 = *(_BYTE **)(v18 + 32);
  v24 = *(_BYTE *)(v18 + 11);
  v4 = *(_BYTE *)(v18 + 4);
  if ( v19 )
    goto LABEL_95;
LABEL_74:
  LOBYTE(v12) = v35 - 8;
  if ( (v12 & 0x5D) == 0 )
  {
    v36 = *(_BYTE *)(v18 + 3);
    if ( v36 == 1 || !v21 || !v24 )
      goto LABEL_90;
    LOBYTE(v18) = 0;
    v37 = 0;
    v29 = 0;
    v12 = (unsigned __int64)&v21[v24];
    v38 = v21 + 8;
    if ( (unsigned __int8)((*v21 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v38 <= v12 )
      {
        v37 = v21[2];
        LOBYTE(v18) = v21[1] & 0xF;
        v29 = v21[3];
        goto LABEL_89;
      }
    }
    else if ( (unsigned __int64)v38 <= v12 )
    {
      v39 = v21 + 13;
      LOBYTE(v18) = v21[2] & 0xF;
      v40 = v24;
      if ( (unsigned int)(unsigned __int8)v21[7] + 8 <= v24 )
        v40 = (unsigned __int8)v21[7] + 8;
      v12 = (unsigned __int64)&v21[v40];
      if ( (unsigned __int64)v39 <= v12 )
        v37 = v21[12];
      if ( (unsigned __int64)(v21 + 14) > v12 )
        v29 = 0;
      else
        v29 = *v39;
LABEL_89:
      if ( v10 )
      {
LABEL_91:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v12,
          v18,
          (unsigned int)&v76,
          a2,
          *(_DWORD *)(a2 + 48),
          v36,
          v4,
          v18,
          v37,
          v29,
          a2);
        goto LABEL_95;
      }
LABEL_90:
      LOBYTE(v18) = 0;
      v37 = 0;
      v29 = 0;
      goto LABEL_91;
    }
    v10 = 0;
    goto LABEL_89;
  }
LABEL_95:
  IofCompleteRequest((PIRP)a2, 0);
  return v75;
}

```

## disassembly

```asm
0x140191d8c  mov     [rsp-8+arg_10], rbx
0x140191d91  push    rbp
0x140191d92  push    rsi
0x140191d93  push    rdi
0x140191d94  push    r12
0x140191d96  push    r13
0x140191d98  push    r14
0x140191d9a  push    r15
0x140191d9c  lea     rbp, [rsp-27h]
0x140191da1  sub     rsp, 0B0h
0x140191da8  mov     rax, cs:__security_cookie
0x140191daf  xor     rax, rsp
0x140191db2  mov     [rbp+57h+var_40], rax
0x140191db6  mov     rax, [rcx+18h]
0x140191dba  mov     r14, rcx
0x140191dbd  xor     r12d, r12d
0x140191dc0  mov     rbx, rdx
0x140191dc3  mov     ecx, [rax]
0x140191dc5  cmp     ecx, 41445452h
0x140191dcb  jnz     short loc_140191DD6
0x140191dcd  lea     r13, [rax+168h]
0x140191dd4  jmp     short loc_140191DE9
0x140191dd6  cmp     ecx, 4E564144h
0x140191ddc  jnz     loc_1401924DD
0x140191de2  lea     r13, [rax+0B0h]
0x140191de9  test    r13, r13
0x140191dec  jz      loc_1401924DD
0x140191df2  mov     rax, [rdx+0B8h]
0x140191df9  mov     ecx, 100h
0x140191dfe  mov     r9, [r14+8]
0x140191e02  mov     edx, 200h
0x140191e07  mov     r8d, 54516152h
0x140191e0d  mov     r15d, [rax+8]
0x140191e11  call    RaidAllocatePool
0x140191e16  mov     rsi, rax
0x140191e19  mov     edi, 1
0x140191e1e  test    rax, rax
0x140191e21  jnz     loc_140192236
0x140191e27  mov     byte ptr [rbx+8Dh], 0ACh
0x140191e2e  cmp     r15d, edi
0x140191e31  jbe     loc_140191FCE
0x140191e37  cmp     cs:StorEtwLoggingEnabled, r12b
0x140191e3e  mov     eax, 0C00000BBh
0x140191e43  mov     [rbp+57h+var_80], eax
0x140191e46  mov     [rbx+30h], eax
0x140191e49  jz      loc_14019221D
0x140191e4f  xorps   xmm0, xmm0
0x140191e52  lea     rdx, [rbp+57h+var_78]
0x140191e56  mov     rcx, rbx
0x140191e59  movups  [rbp+57h+var_78], xmm0
0x140191e5d  call    cs:__imp_IoGetActivityIdIrp
0x140191e64  nop     dword ptr [rax+rax+00h]
0x140191e69  mov     rdx, [rbx+0B8h]
0x140191e70  movzx   eax, byte ptr [rdx]
0x140191e73  sub     eax, 0Eh
0x140191e76  jz      loc_1401921FA
0x140191e7c  sub     eax, edi
0x140191e7e  jz      short loc_140191EE7
0x140191e80  cmp     eax, 0Ch
0x140191e83  jnz     loc_14019221D
0x140191e89  cmp     byte ptr [rdx+1], 7
0x140191e8d  jnz     short loc_140191ECE
0x140191e8f  cmp     [rdx+8], r12d
0x140191e93  jnz     short loc_140191ECE
0x140191e95  test    cs:byte_140177432, 40h
0x140191e9c  jz      loc_14019221D
0x140191ea2  mov     rax, [rbx+38h]
0x140191ea6  test    rax, rax
0x140191ea9  jz      short loc_140191EAF
0x140191eab  mov     ecx, [rax]
0x140191ead  jmp     short loc_140191EB2
0x140191eaf  mov     ecx, r12d
0x140191eb2  mov     eax, [rbx+30h]
0x140191eb5  lea     r8, [rbp+57h+var_78]
0x140191eb9  mov     dword ptr [rsp+0E0h+var_B8], eax
0x140191ebd  mov     r9, rbx
0x140191ec0  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x140191ec4  call    McTemplateK0pqd_EtwWriteTransfer
0x140191ec9  jmp     loc_14019221D
0x140191ece  test    cs:byte_140177432, 20h
0x140191ed5  jz      loc_14019221D
0x140191edb  lea     rdx, EventPnpRequestComplete
0x140191ee2  jmp     loc_14019220A
0x140191ee7  cmp     cs:byte_140177431, r12b
0x140191eee  jge     loc_14019221D
0x140191ef4  mov     rdx, [rdx+8]
0x140191ef8  movzx   eax, byte ptr [rdx+2]
0x140191efc  cmp     al, 28h ; '('
0x140191efe  jnz     loc_140192104
0x140191f04  cmp     [rdx+14h], r12d
0x140191f08  jnz     loc_14019221D
0x140191f0e  mov     r15d, [rdx+38h]
0x140191f12  test    r15d, r15d
0x140191f15  jz      loc_14019221D
0x140191f1b  xor     r9d, r9d
0x140191f1e  xor     r14d, r14d
0x140191f21  xor     r13b, r13b
0x140191f24  mov     r10b, r12b
0x140191f27  mov     r11, r12
0x140191f2a  mov     ecx, [rdx+r14*4+78h]
0x140191f2f  cmp     ecx, 80h
0x140191f35  jb      short loc_140191FB5
0x140191f37  mov     esi, [rdx+10h]
0x140191f3a  cmp     ecx, esi
0x140191f3c  jnb     short loc_140191FB5
0x140191f3e  mov     r8d, ecx
0x140191f41  mov     ecx, [rcx+rdx]
0x140191f44  sub     ecx, 40h ; '@'
0x140191f47  jz      short loc_140191F9F
0x140191f49  sub     ecx, edi
0x140191f4b  jz      short loc_140191F73
0x140191f4d  cmp     ecx, edi
0x140191f4f  jnz     short loc_140191FAC
0x140191f51  lea     rcx, [r8+28h]
0x140191f55  cmp     rcx, rsi
0x140191f58  ja      short loc_140191FAC
0x140191f5a  cmp     dword ptr [r8+rdx+0Ch], 0
0x140191f60  jbe     short loc_140191F69
0x140191f62  lea     r11, [rdx+20h]
0x140191f66  add     r11, r8
0x140191f69  mov     r9, [r8+rdx+18h]
0x140191f6e  jmp     loc_1401920EC
0x140191f73  lea     rcx, [r8+38h]
0x140191f77  cmp     rcx, rsi
0x140191f7a  ja      short loc_140191FAC
0x140191f7c  cmp     byte ptr [r8+rdx+0Ah], 0
0x140191f82  mov     r13b, dil
0x140191f85  jbe     short loc_140191F8E
0x140191f87  lea     r11, [rdx+18h]
0x140191f8b  add     r11, r8
0x140191f8e  mov     r12b, [r8+rdx+8]
0x140191f93  mov     r9, [r8+rdx+10h]
0x140191f98  mov     r10b, [r8+rdx+9]
0x140191f9d  jmp     short loc_140191FAC
0x140191f9f  lea     rcx, [r8+28h]
0x140191fa3  cmp     rcx, rsi
0x140191fa6  jbe     loc_1401920D8
0x140191fac  test    r13b, r13b
0x140191faf  jnz     loc_1401920F6
0x140191fb5  add     r14d, edi
0x140191fb8  cmp     r14d, r15d
0x140191fbb  jb      loc_140191F2A
0x140191fc1  jmp     loc_1401920F6
0x140191fc6  xor     r8b, r8b
0x140191fc9  jmp     loc_1401921BB
0x140191fce  cmp     cs:StorEtwLoggingEnabled, r12b
0x140191fd5  mov     eax, 0C0000017h
0x140191fda  mov     [rbp+57h+var_80], eax
0x140191fdd  mov     [rbx+30h], eax
0x140191fe0  jz      loc_14019221D
0x140191fe6  xorps   xmm0, xmm0
0x140191fe9  lea     rdx, [rbp+57h+var_78]
0x140191fed  mov     rcx, rbx
0x140191ff0  movups  [rbp+57h+var_78], xmm0
0x140191ff4  call    cs:__imp_IoGetActivityIdIrp
0x140191ffb  nop     dword ptr [rax+rax+00h]
0x140192000  mov     rdx, [rbx+0B8h]
0x140192007  movzx   eax, byte ptr [rdx]
0x14019200a  sub     eax, 0Eh
0x14019200d  jz      loc_1401921FA
0x140192013  sub     eax, edi
0x140192015  jnz     loc_140191E80
0x14019201b  cmp     cs:byte_140177431, r12b
0x140192022  jge     loc_14019221D
0x140192028  mov     rdx, [rdx+8]
0x14019202c  movzx   eax, byte ptr [rdx+2]
0x140192030  cmp     al, 28h ; '('
0x140192032  jnz     loc_140192104
0x140192038  cmp     [rdx+14h], r12d
0x14019203c  jnz     loc_14019221D
0x140192042  mov     r15d, [rdx+38h]
0x140192046  test    r15d, r15d
0x140192049  jz      loc_14019221D
0x14019204f  xor     r9d, r9d
0x140192052  xor     r14d, r14d
0x140192055  xor     r13b, r13b
0x140192058  mov     r10b, r12b
0x14019205b  mov     r11, r12
0x14019205e  mov     ecx, [rdx+r14*4+78h]
0x140192063  cmp     ecx, 80h
0x140192069  jb      short loc_1401920CE
0x14019206b  mov     esi, [rdx+10h]
0x14019206e  cmp     ecx, esi
0x140192070  jnb     short loc_1401920CE
0x140192072  mov     r8d, ecx
0x140192075  mov     ecx, [rcx+rdx]
0x140192078  sub     ecx, 40h ; '@'
0x14019207b  jz      short loc_1401920C0
0x14019207d  sub     ecx, edi
0x14019207f  jz      short loc_140192094
0x140192081  cmp     ecx, edi
0x140192083  jnz     short loc_1401920C9
0x140192085  lea     rcx, [r8+28h]
0x140192089  cmp     rcx, rsi
0x14019208c  jbe     loc_140191F5A
0x140192092  jmp     short loc_1401920C9
0x140192094  lea     rcx, [r8+38h]
0x140192098  cmp     rcx, rsi
0x14019209b  ja      short loc_1401920C9
0x14019209d  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401920a3  mov     r13b, dil
0x1401920a6  jbe     short loc_1401920AF
0x1401920a8  lea     r11, [rdx+18h]
0x1401920ac  add     r11, r8
0x1401920af  mov     r12b, [r8+rdx+8]
0x1401920b4  mov     r9, [r8+rdx+10h]
0x1401920b9  mov     r10b, [r8+rdx+9]
0x1401920be  jmp     short loc_1401920C9
0x1401920c0  lea     rcx, [r8+28h]
0x1401920c4  cmp     rcx, rsi
0x1401920c7  jbe     short loc_1401920D8
0x1401920c9  test    r13b, r13b
0x1401920cc  jnz     short loc_1401920F6
0x1401920ce  add     r14d, edi
0x1401920d1  cmp     r14d, r15d
0x1401920d4  jb      short loc_14019205E
0x1401920d6  jmp     short loc_1401920F6
0x1401920d8  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401920de  jbe     short loc_1401920E7
0x1401920e0  lea     r11, [rdx+18h]
0x1401920e4  add     r11, r8
0x1401920e7  mov     r9, [r8+rdx+10h]
0x1401920ec  mov     r10b, [r8+rdx+9]
0x1401920f1  mov     r12b, [r8+rdx+8]
0x1401920f6  test    r11, r11
0x1401920f9  jz      loc_14019221D
0x1401920ff  mov     cl, [r11]
0x140192102  jmp     short loc_14019211B
0x140192104  mov     cl, [rdx+48h]
0x140192107  mov     r9, [rdx+20h]
0x14019210b  mov     r10b, [rdx+0Bh]
0x14019210f  mov     r12b, [rdx+4]
0x140192113  test    eax, eax
0x140192115  jnz     loc_14019221D
0x14019211b  sub     cl, 8
0x14019211e  test    cl, 5Dh
0x140192121  jnz     loc_14019221D
0x140192127  mov     sil, [rdx+3]
0x14019212b  cmp     sil, dil
0x14019212e  jz      loc_1401921C0
0x140192134  test    r9, r9
0x140192137  jz      loc_1401921C0
0x14019213d  test    r10b, r10b
0x140192140  jz      short loc_1401921C0
0x140192142  mov     al, [r9]
0x140192145  xor     dl, dl
0x140192147  and     al, 7Fh
0x140192149  movzx   ecx, r10b
0x14019214d  sub     al, 72h ; 'r'
0x14019214f  xor     r11b, r11b
0x140192152  xor     r8b, r8b
0x140192155  add     rcx, r9
0x140192158  cmp     al, dil
0x14019215b  lea     rax, [r9+8]
0x14019215f  jbe     short loc_1401921A2
0x140192161  cmp     rax, rcx
0x140192164  ja      short loc_1401921B8
0x140192166  movzx   ecx, byte ptr [r9+7]
0x14019216b  lea     r8, [r9+0Dh]
0x14019216f  mov     dl, [r9+2]
0x140192173  add     ecx, 8
0x140192176  and     dl, 0Fh
0x140192179  movzx   eax, r10b
0x14019217d  cmp     ecx, eax
0x14019217f  cmovbe  eax, ecx
0x140192182  mov     ecx, eax
0x140192184  add     rcx, r9
0x140192187  cmp     r8, rcx
0x14019218a  ja      short loc_140192190
0x14019218c  mov     r11b, [r9+0Ch]
0x140192190  lea     rax, [r9+0Eh]
0x140192194  cmp     rax, rcx
0x140192197  ja      loc_140191FC6
0x14019219d  mov     r8b, [r8]
0x1401921a0  jmp     short loc_1401921BB
0x1401921a2  cmp     rax, rcx
0x1401921a5  ja      short loc_1401921B8
0x1401921a7  mov     dl, [r9+1]
0x1401921ab  mov     r11b, [r9+2]
0x1401921af  and     dl, 0Fh
0x1401921b2  mov     r8b, [r9+3]
0x1401921b6  jmp     short loc_1401921BB
0x1401921b8  xor     dil, dil
0x1401921bb  test    dil, dil
0x1401921be  jnz     short loc_1401921C8
0x1401921c0  xor     dl, dl
0x1401921c2  xor     r11b, r11b
0x1401921c5  xor     r8b, r8b
0x1401921c8  mov     eax, [rbx+30h]
0x1401921cb  mov     r9, rbx
0x1401921ce  mov     [rsp+0E0h+var_90], rbx
0x1401921d3  mov     [rsp+0E0h+var_98], r8b
0x1401921d8  lea     r8, [rbp+57h+var_78]
0x1401921dc  mov     [rsp+0E0h+var_A0], r11b
0x1401921e1  mov     [rsp+0E0h+var_A8], dl
0x1401921e5  mov     [rsp+0E0h+var_B0], r12b
0x1401921ea  mov     byte ptr [rsp+0E0h+var_B8], sil
0x1401921ef  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1401921f3  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x1401921f8  jmp     short loc_14019221D
  ... truncated ...
```
