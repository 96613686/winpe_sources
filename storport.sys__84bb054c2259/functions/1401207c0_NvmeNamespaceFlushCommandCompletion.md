# NvmeNamespaceFlushCommandCompletion

- ea: `0x1401207c0`
- end: `0x1401211fe`
- name: `NvmeNamespaceFlushCommandCompletion`
- size: `2622`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400daa90`
- `0x1401207c0`
- `0x14014b400`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140120b0d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140120e49`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140120b0d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140120e49`
- `ntoskrnl!KeReleaseSpinLock` at `0x140121199`
- `ntoskrnl!KeReleaseSpinLock` at `0x140121199`
- `ntoskrnl!IofCompleteRequest` at `0x140120db8`
- `ntoskrnl!IofCompleteRequest` at `0x1401210f3`
- `ntoskrnl!IofCompleteRequest` at `0x140120db8`
- `ntoskrnl!IofCompleteRequest` at `0x1401210f3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140120e18`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401211a9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140120e18`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401211a9`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1401211d1`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1401211d1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140121123`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140121123`

## pseudocode

```c
void __fastcall NvmeNamespaceFlushCommandCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // edx
  unsigned int v5; // edx
  int v6; // ecx
  int v7; // ebx
  unsigned int v8; // edx
  bool v9; // zf
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  bool v13; // zf
  int v14; // ecx
  unsigned int v15; // edx
  bool v16; // zf
  __int64 v17; // rsi
  unsigned __int64 v18; // rcx
  __int64 v19; // rdx
  int *v20; // rax
  int v21; // ecx
  __int64 *v22; // rdx
  _BYTE *v23; // rdx
  unsigned int v24; // r15d
  unsigned __int8 v25; // r11
  char *v26; // rdi
  char v27; // r13
  _BYTE *v28; // r9
  __int64 v29; // r14
  char v30; // r12
  unsigned __int64 v31; // r10
  __int64 v32; // r8
  int v33; // ecx
  char v34; // cl
  char v35; // di
  char v36; // r8
  char v37; // r10
  _BYTE *v38; // rax
  unsigned int v39; // eax
  char v40; // al
  char *v41; // r14
  _QWORD **v42; // r13
  _QWORD *v43; // rax
  _QWORD *v44; // rcx
  _QWORD *v45; // rsi
  unsigned __int64 v46; // rcx
  __int64 v47; // rdx
  int *v48; // rax
  int v49; // ecx
  __int64 *v50; // rdx
  _BYTE *v51; // rdx
  unsigned int v52; // r15d
  unsigned __int8 v53; // r11
  char *v54; // rdi
  _BYTE *v55; // r9
  __int64 v56; // r14
  char v57; // r12
  unsigned __int64 v58; // r10
  __int64 v59; // r8
  int v60; // ecx
  char v61; // r14
  char v62; // cl
  char v63; // di
  char v64; // r8
  char v65; // r10
  _BYTE *v66; // rax
  unsigned int v67; // eax
  char v68; // al
  KIRQL v69; // r8
  _QWORD **v70; // rdx
  _QWORD *v71; // rcx
  _QWORD *v72; // rax
  _QWORD *v73; // rax
  __int64 v74; // rbx
  char v75; // [rsp+60h] [rbp-19h]
  char *Context; // [rsp+68h] [rbp-11h]
  __int128 v77; // [rsp+70h] [rbp-9h] BYREF

  if ( !a3 )
  {
    v7 = -1073740757;
    goto LABEL_99;
  }
  *(_WORD *)(*(_QWORD *)a2 + 4260LL) = *(_WORD *)(a3 + 14);
  v4 = *(unsigned __int16 *)(*(_QWORD *)a2 + 4260LL);
  if ( ((v4 >> 9) & 7) == 0 )
  {
    v15 = v4 >> 1;
    if ( (unsigned __int8)v15 > 0x80u )
    {
      if ( (unsigned __int8)v15 == 129 )
        goto LABEL_26;
      v12 = (unsigned __int8)v15 - 130;
      if ( (unsigned __int8)v15 == 130 )
      {
        v7 = -1073741661;
        goto LABEL_99;
      }
      goto LABEL_73;
    }
    if ( (unsigned __int8)v15 == 128 )
      goto LABEL_26;
    if ( (unsigned __int8)v15 > 0xEu )
    {
      if ( (unsigned __int8)v15 <= 0x16u )
      {
        if ( (unsigned __int8)v15 == 22
          || (unsigned __int8)v15 == 15
          || (unsigned __int8)v15 == 16
          || (unsigned __int8)v15 == 17
          || (unsigned __int8)v15 == 18
          || (unsigned __int8)v15 == 19 )
        {
          goto LABEL_26;
        }
        v6 = (unsigned __int8)v15 - 20;
        if ( (unsigned __int8)v15 != 20 )
          goto LABEL_84;
LABEL_45:
        v7 = -1073741436;
        goto LABEL_99;
      }
      if ( (unsigned __int8)v15 == 24 )
        goto LABEL_26;
      if ( (unsigned __int8)v15 == 25 || (unsigned __int8)v15 == 26 )
      {
        v7 = -1073741643;
        goto LABEL_99;
      }
      if ( (unsigned __int8)v15 != 27 )
      {
        if ( (unsigned __int8)v15 == 28 )
          goto LABEL_11;
        v16 = (unsigned __int8)v15 == 30;
        goto LABEL_92;
      }
    }
    else
    {
      if ( (unsigned __int8)v15 == 14 )
        goto LABEL_26;
      if ( (unsigned __int8)v15 > 7u )
      {
        if ( (unsigned __int8)v15 != 8 && (unsigned __int8)v15 != 9 && (unsigned __int8)v15 != 10 )
        {
          if ( (unsigned __int8)v15 == 11 )
            goto LABEL_26;
          v12 = (unsigned __int8)v15 - 12;
          if ( (unsigned __int8)v15 == 12 )
          {
            v7 = -1073740758;
            goto LABEL_99;
          }
          goto LABEL_73;
        }
      }
      else if ( (unsigned __int8)v15 != 7 )
      {
        if ( !(_BYTE)v15 )
        {
          v7 = 0;
          goto LABEL_99;
        }
        if ( (unsigned __int8)v15 == 1 || (unsigned __int8)v15 == 2 )
          goto LABEL_26;
        if ( (unsigned __int8)v15 == 3 || (unsigned __int8)v15 == 4 )
          goto LABEL_11;
        v14 = (unsigned __int8)v15 - 5;
        v13 = (unsigned __int8)v15 == 5;
LABEL_43:
        if ( !v13 && v14 != 1 )
          goto LABEL_11;
        goto LABEL_45;
      }
    }
    v7 = -1073741248;
    goto LABEL_99;
  }
  if ( ((v4 >> 9) & 7) == 1 )
  {
    v8 = v4 >> 1;
    if ( (unsigned __int8)v8 > 0x80u )
    {
      if ( (unsigned __int8)v8 == 129 )
        goto LABEL_26;
      v12 = (unsigned __int8)v8 - 130;
      if ( (unsigned __int8)v8 != 130 )
        goto LABEL_73;
    }
    else
    {
      if ( (unsigned __int8)v8 == 128 )
        goto LABEL_26;
      if ( (unsigned __int8)v8 <= 0x11u )
      {
        if ( (unsigned __int8)v8 != 17 )
        {
          if ( (unsigned __int8)v8 <= 9u )
          {
            if ( (unsigned __int8)v8 == 9
              || !(_BYTE)v8
              || (unsigned __int8)v8 == 1
              || (unsigned __int8)v8 == 2
              || (unsigned __int8)v8 == 3 )
            {
              goto LABEL_26;
            }
            v10 = (unsigned __int8)v8 - 5;
            v9 = (unsigned __int8)v8 == 5;
LABEL_23:
            if ( v9 )
              goto LABEL_26;
            v11 = v10 - 1;
            if ( !v11 )
              goto LABEL_26;
            v12 = v11 - 1;
            if ( !v12 )
              goto LABEL_26;
LABEL_73:
            v16 = v12 == 1;
LABEL_92:
            if ( !v16 )
              goto LABEL_11;
LABEL_26:
            v7 = -1073741808;
            goto LABEL_99;
          }
          if ( (unsigned __int8)v8 == 10 )
            goto LABEL_26;
          if ( (unsigned __int8)v8 != 11 )
          {
            if ( (unsigned __int8)v8 == 12
              || (unsigned __int8)v8 == 13
              || (unsigned __int8)v8 == 14
              || (unsigned __int8)v8 == 15 )
            {
              goto LABEL_26;
            }
            if ( (unsigned __int8)v8 != 16 )
              goto LABEL_11;
          }
        }
        v7 = -2147483210;
        goto LABEL_99;
      }
      if ( (unsigned __int8)v8 <= 0x1Au )
      {
        switch ( (unsigned __int8)v8 )
        {
          case 0x1Au:
          case 0x12u:
          case 0x13u:
            goto LABEL_45;
          case 0x14u:
            v7 = -1073741800;
            goto LABEL_99;
          case 0x15u:
            goto LABEL_11;
          case 0x16u:
            goto LABEL_45;
        }
        v14 = (unsigned __int8)v8 - 24;
        v13 = (unsigned __int8)v8 == 24;
        goto LABEL_43;
      }
      if ( (unsigned __int8)v8 == 27 )
      {
        v7 = -1073741637;
        goto LABEL_99;
      }
      if ( (unsigned __int8)v8 == 28 )
        goto LABEL_26;
      if ( (unsigned __int8)v8 != 30 )
      {
        v10 = (unsigned __int8)v8 - 31;
        v9 = (unsigned __int8)v8 == 31;
        goto LABEL_23;
      }
    }
LABEL_85:
    v7 = -1073741790;
    goto LABEL_99;
  }
  if ( ((v4 >> 9) & 7) != 2 )
    goto LABEL_11;
  v5 = v4 >> 1;
  switch ( (unsigned __int8)v5 )
  {
    case 0x80u:
      goto LABEL_11;
    case 0x81u:
      goto LABEL_11;
    case 0x82u:
      goto LABEL_11;
    case 0x83u:
      goto LABEL_11;
    case 0x84u:
      goto LABEL_11;
  }
  v6 = (unsigned __int8)v5 - 133;
  if ( (unsigned __int8)v5 == 133 )
    goto LABEL_11;
LABEL_84:
  if ( v6 == 1 )
    goto LABEL_85;
LABEL_11:
  v7 = -1073741435;
LABEL_99:
  v17 = *(_QWORD *)(*(_QWORD *)a2 + 4184LL);
  Context = *(char **)(*(_QWORD *)a2 + 4216LL);
  StorpTelemetryCollectNvmeNonIoCmdPerfData(
    *(_QWORD *)(a2 + 96),
    *(_QWORD *)a2 + 4096,
    (_DWORD)Context,
    v7,
    *(_DWORD *)(a2 + 80));
  *(_DWORD *)(v17 + 48) = v7;
  *(_QWORD *)(v17 + 56) = 0;
  memset_0(*(void **)a2, 0, 0x10B0u);
  *(_DWORD *)(a2 + 64) &= ~1u;
  v9 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(v17 + 141) = -84;
  *(_DWORD *)(v17 + 48) = v7;
  if ( v9 )
    goto LABEL_164;
  v77 = 0;
  IoGetActivityIdIrp(v17, &v77);
  v19 = *(_QWORD *)(v17 + 184);
  if ( *(_BYTE *)v19 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_164;
    v22 = EventNonReadWriteRequestComplete;
    goto LABEL_163;
  }
  if ( *(_BYTE *)v19 != 15 )
  {
    if ( *(_BYTE *)v19 != 27 )
      goto LABEL_164;
    if ( *(_BYTE *)(v19 + 1) == 7 && !*(_DWORD *)(v19 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v20 = *(int **)(v17 + 56);
        if ( v20 )
          v21 = *v20;
        else
          v21 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v21, v19, (unsigned int)&v77, v17, v21, *(_DWORD *)(v17 + 48));
      }
      goto LABEL_164;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_164;
    v22 = EventPnpRequestComplete;
LABEL_163:
    McTemplateK0pd_EtwWriteTransfer(v18, v22, &v77, v17, *(_DWORD *)(v17 + 48));
    goto LABEL_164;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_164;
  v23 = *(_BYTE **)(v19 + 8);
  if ( v23[2] == 40 )
  {
    if ( *((_DWORD *)v23 + 5) )
      goto LABEL_164;
    v24 = *((_DWORD *)v23 + 14);
    if ( !v24 )
      goto LABEL_164;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    while ( 1 )
    {
      v18 = *(unsigned int *)&v23[4 * v29 + 120];
      if ( (unsigned int)v18 >= 0x80 )
      {
        v31 = *((unsigned int *)v23 + 4);
        if ( (unsigned int)v18 < (unsigned int)v31 )
        {
          v32 = (unsigned int)v18;
          v33 = *(_DWORD *)&v23[v18] - 64;
          if ( v33 )
          {
            LODWORD(v18) = v33 - 1;
            if ( (_DWORD)v18 )
            {
              if ( (_DWORD)v18 == 1 )
              {
                LODWORD(v18) = v32 + 40;
                if ( v32 + 40 <= v31 )
                {
                  if ( *(_DWORD *)&v23[v32 + 12] )
                    v26 = &v23[v32 + 32];
                  v28 = *(_BYTE **)&v23[v32 + 24];
                  goto LABEL_137;
                }
              }
            }
            else
            {
              LODWORD(v18) = v32 + 56;
              if ( v32 + 56 <= v31 )
              {
                v30 = 1;
                if ( v23[v32 + 10] )
                  v26 = &v23[v32 + 24];
                v27 = v23[v32 + 8];
                v28 = *(_BYTE **)&v23[v32 + 16];
                v25 = v23[v32 + 9];
              }
            }
          }
          else
          {
            LODWORD(v18) = v32 + 40;
            if ( v32 + 40 <= v31 )
            {
              if ( v23[v32 + 10] )
                v26 = &v23[v32 + 24];
              v28 = *(_BYTE **)&v23[v32 + 16];
LABEL_137:
              v25 = v23[v32 + 9];
              v27 = v23[v32 + 8];
LABEL_138:
              if ( v26 )
              {
                v34 = *v26;
                goto LABEL_141;
              }
              goto LABEL_164;
            }
          }
          if ( v30 )
            goto LABEL_138;
        }
      }
      v29 = (unsigned int)(v29 + 1);
      if ( (unsigned int)v29 >= v24 )
        goto LABEL_138;
    }
  }
  v34 = v23[72];
  v28 = (_BYTE *)*((_QWORD *)v23 + 4);
  v25 = v23[11];
  v27 = v23[4];
  if ( v23[2] )
    goto LABEL_164;
LABEL_141:
  LOBYTE(v18) = v34 - 8;
  if ( (v18 & 0x5D) == 0 )
  {
    v35 = v23[3];
    if ( v35 == 1 || !v28 || !v25 )
      goto LABEL_159;
    v36 = 0;
    v37 = 0;
    LOBYTE(v23) = 0;
    v18 = (unsigned __int64)&v28[v25];
    v38 = v28 + 8;
    if ( (unsigned __int8)((*v28 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v38 <= v18 )
      {
        v37 = v28[2];
        v36 = v28[1] & 0xF;
        LOBYTE(v23) = v28[3];
LABEL_156:
        v40 = 1;
        goto LABEL_158;
      }
    }
    else if ( (unsigned __int64)v38 <= v18 )
    {
      v23 = v28 + 13;
      v36 = v28[2] & 0xF;
      v39 = v25;
      if ( (unsigned int)(unsigned __int8)v28[7] + 8 <= v25 )
        v39 = (unsigned __int8)v28[7] + 8;
      v18 = (unsigned __int64)&v28[v39];
      if ( (unsigned __int64)v23 <= v18 )
        v37 = v28[12];
      if ( (unsigned __int64)(v28 + 14) > v18 )
        LOBYTE(v23) = 0;
      else
        LOBYTE(v23) = *v23;
      goto LABEL_156;
    }
    v40 = 0;
LABEL_158:
    if ( v40 )
    {
LABEL_160:
      McTemplateK0pduuuuup_EtwWriteTransfer(
        v18,
        (_DWORD)v23,
        (unsigned int)&v77,
        v17,
        *(_DWORD *)(v17 + 48),
        v35,
        v27,
        v36,
        v37,
        (char)v23,
        v17);
      goto LABEL_164;
    }
LABEL_159:
    v36 = 0;
    v37 = 0;
    LOBYTE(v23) = 0;
    goto LABEL_160;
  }
LABEL_164:
  IofCompleteRequest((PIRP)v17, 1);
  v41 = Context;
  v42 = (_QWORD **)(Context + 576);
  while ( 1 )
  {
    v43 = *v42;
    if ( *v42 == v42 )
      break;
    if ( (_QWORD **)v43[1] != v42 || (v44 = (_QWORD *)*v43, *(_QWORD **)(*v43 + 8LL) != v43) )
LABEL_241:
      __fastfail(3u);
    *v42 = v44;
    v45 = v43 - 21;
    v44[1] = v42;
    v43[1] = v43;
    *v43 = v43;
    *((_DWORD *)v45 + 12) = v7;
    v45[7] = 0;
    ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)v41 + 15));
    v9 = StorEtwLoggingEnabled == 0;
    *((_BYTE *)v45 + 141) = -84;
    *((_DWORD *)v45 + 12) = v7;
    if ( !v9 )
    {
      v77 = 0;
      IoGetActivityIdIrp(v45, &v77);
      v47 = v45[23];
      switch ( *(_BYTE *)v47 )
      {
        case 0xE:
          if ( (byte_140177432 & 8) != 0 )
          {
            v50 = EventNonReadWriteRequestComplete;
LABEL_181:
            McTemplateK0pd_EtwWriteTransfer(v46, v50, &v77, v45, *((_DWORD *)v45 + 12));
          }
          break;
        case 0xF:
          if ( byte_140177431 >= 0 )
            break;
          v51 = *(_BYTE **)(v47 + 8);
          if ( v51[2] != 40 )
          {
            v62 = v51[72];
            v55 = (_BYTE *)*((_QWORD *)v51 + 4);
            v53 = v51[11];
            v61 = v51[4];
            if ( v51[2] )
              goto LABEL_231;
LABEL_211:
            LOBYTE(v46) = v62 - 8;
            if ( (v46 & 0x5D) != 0 )
              goto LABEL_231;
            v63 = v51[3];
            if ( v63 == 1 || !v55 || !v53 )
              goto LABEL_229;
            v64 = 0;
            v65 = 0;
            LOBYTE(v51) = 0;
            v46 = (unsigned __int64)&v55[v53];
            v66 = v55 + 8;
            if ( (unsigned __int8)((*v55 & 0x7F) - 114) <= 1u )
            {
              if ( (unsigned __int64)v66 <= v46 )
              {
                v65 = v55[2];
                v64 = v55[1] & 0xF;
                LOBYTE(v51) = v55[3];
                goto LABEL_226;
              }
            }
            else if ( (unsigned __int64)v66 <= v46 )
            {
              v51 = v55 + 13;
              v64 = v55[2] & 0xF;
              v67 = v53;
              if ( (unsigned int)(unsigned __int8)v55[7] + 8 <= v53 )
                v67 = (unsigned __int8)v55[7] + 8;
              v46 = (unsigned __int64)&v55[v67];
              if ( (unsigned __int64)v51 <= v46 )
                v65 = v55[12];
              if ( (unsigned __int64)(v55 + 14) > v46 )
                LOBYTE(v51) = 0;
              else
                LOBYTE(v51) = *v51;
LABEL_226:
              v68 = 1;
LABEL_228:
              if ( !v68 )
              {
LABEL_229:
                v64 = 0;
                v65 = 0;
                LOBYTE(v51) = 0;
              }
              McTemplateK0pduuuuup_EtwWriteTransfer(
                v46,
                (_DWORD)v51,
                (unsigned int)&v77,
                (_DWORD)v45,
                *((_DWORD *)v45 + 12),
                v63,
                v61,
                v64,
                v65,
                (char)v51,
                (char)v45);
LABEL_231:
              v41 = Context;
              break;
            }
            v68 = 0;
            goto LABEL_228;
          }
          if ( !*((_DWORD *)v51 + 5) )
          {
            v52 = *((_DWORD *)v51 + 14);
            if ( v52 )
            {
              v53 = 0;
              v54 = 0;
              v75 = 0;
              v55 = 0;
              v56 = 0;
              v57 = 0;
              do
              {
                v46 = *(unsigned int *)&v51[4 * v56 + 120];
                if ( (unsigned int)v46 >= 0x80 )
                {
                  v58 = *((unsigned int *)v51 + 4);
                  if ( (unsigned int)v46 < (unsigned int)v58 )
                  {
                    v59 = (unsigned int)v46;
                    v60 = *(_DWORD *)&v51[v46] - 64;
                    if ( v60 )
                    {
                      LODWORD(v46) = v60 - 1;
                      if ( (_DWORD)v46 )
                      {
                        if ( (_DWORD)v46 == 1 )
                        {
                          LODWORD(v46) = v59 + 40;
                          if ( v59 + 40 <= v58 )
                          {
                            if ( *(_DWORD *)&v51[v59 + 12] )
                              v54 = &v51[v59 + 32];
                            v55 = *(_BYTE **)&v51[v59 + 24];
LABEL_196:
                            v61 = v51[v59 + 8];
                            v53 = v51[v59 + 9];
                            goto LABEL_205;
                          }
                        }
                      }
                      else
                      {
                        LODWORD(v46) = v59 + 56;
                        if ( v59 + 56 <= v58 )
                        {
                          v57 = 1;
                          if ( v51[v59 + 10] )
                            v54 = &v51[v59 + 24];
                          v55 = *(_BYTE **)&v51[v59 + 16];
                          v53 = v51[v59 + 9];
                          v75 = v51[v59 + 8];
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v46) = v59 + 40;
                      if ( v59 + 40 <= v58 )
                      {
                        if ( v51[v59 + 10] )
                          v54 = &v51[v59 + 24];
                        v55 = *(_BYTE **)&v51[v59 + 16];
                        goto LABEL_196;
                      }
                    }
                    if ( v57 )
                      break;
                  }
                }
                v56 = (unsigned int)(v56 + 1);
              }
              while ( (unsigned int)v56 < v52 );
              v61 = v75;
LABEL_205:
              if ( v54 )
              {
                v62 = *v54;
                goto LABEL_211;
              }
              goto LABEL_231;
            }
          }
          break;
        case 0x1B:
          if ( *(_BYTE *)(v47 + 1) != 7 || *(_DWORD *)(v47 + 8) )
          {
            if ( (byte_140177432 & 0x20) == 0 )
              break;
            v50 = EventPnpRequestComplete;
            goto LABEL_181;
          }
          if ( (byte_140177432 & 0x40) != 0 )
          {
            v48 = (int *)v45[7];
            if ( v48 )
              v49 = *v48;
            else
              v49 = 0;
            McTemplateK0pqd_EtwWriteTransfer(v49, v47, (unsigned int)&v77, (_DWORD)v45, v49, *((_DWORD *)v45 + 12));
          }
          break;
        default:
          break;
      }
    }
    IofCompleteRequest((PIRP)v45, 1);
  }
  v69 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v41 + 70);
  v70 = (_QWORD **)(v41 + 600);
  while ( 1 )
  {
    v71 = *v70;
    if ( *v70 == v70 )
      break;
    if ( (_QWORD **)v71[1] != v70 )
      goto LABEL_241;
    v72 = (_QWORD *)*v71;
    if ( *(_QWORD **)(*v71 + 8LL) != v71 )
      goto LABEL_241;
    *v70 = v72;
    v72[1] = v70;
    v73 = (_QWORD *)*((_QWORD *)v41 + 73);
    if ( (_QWORD **)*v73 != v42 )
      goto LABEL_241;
    *v71 = v42;
    v71[1] = v73;
    *v73 = v71;
    *((_QWORD *)Context + 73) = v71;
  }
  v74 = *((_QWORD *)v41 + 74);
  *((_QWORD *)v41 + 71) = v74;
  *((_QWORD *)v41 + 74) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)v41 + 70, v69);
  ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)v41 + 15));
  if ( v74 )
    IoQueueWorkItemEx(*((PIO_WORKITEM *)v41 + 69), NvmeNamespaceFlushWorker, DelayedWorkQueue, v41);
}

```

## disassembly

```asm
0x1401207c0  push    rbp
0x1401207c2  push    rbx
0x1401207c3  push    rsi
0x1401207c4  push    rdi
0x1401207c5  push    r12
0x1401207c7  push    r13
0x1401207c9  push    r14
0x1401207cb  push    r15
0x1401207cd  lea     rbp, [rsp-1Fh]
0x1401207d2  sub     rsp, 98h
0x1401207d9  mov     rax, cs:__security_cookie
0x1401207e0  xor     rax, rsp
0x1401207e3  mov     [rbp+57h+var_50], rax
0x1401207e7  mov     rdi, rdx
0x1401207ea  mov     r9d, 80h
0x1401207f0  test    r8, r8
0x1401207f3  jz      loc_140120A95
0x1401207f9  mov     rcx, [rdx]
0x1401207fc  movzx   eax, word ptr [r8+0Eh]
0x140120801  mov     [rcx+10A4h], ax
0x140120808  mov     rax, [rdx]
0x14012080b  movzx   edx, word ptr [rax+10A4h]
0x140120812  mov     ecx, edx
0x140120814  shr     ecx, 9
0x140120817  and     ecx, 7
0x14012081a  jz      loc_14012095C
0x140120820  sub     ecx, 1
0x140120823  jz      short loc_14012085B
0x140120825  sub     ecx, 1
0x140120828  jnz     short loc_140120851
0x14012082a  shr     edx, 1
0x14012082c  movzx   ecx, dl
0x14012082f  sub     ecx, r9d
0x140120832  jz      short loc_140120851
0x140120834  sub     ecx, 1
0x140120837  jz      short loc_140120851
0x140120839  sub     ecx, 1
0x14012083c  jz      short loc_140120851
0x14012083e  sub     ecx, 1
0x140120841  jz      short loc_140120851
0x140120843  sub     ecx, 1
0x140120846  jz      short loc_140120851
0x140120848  sub     ecx, 1
0x14012084b  jnz     loc_140120A33
0x140120851  mov     ebx, 0C0000185h
0x140120856  jmp     loc_140120A9A
0x14012085b  shr     edx, 1
0x14012085d  movzx   ecx, dl
0x140120860  cmp     ecx, r9d
0x140120863  ja      loc_140120945
0x140120869  jz      short loc_14012089F
0x14012086b  cmp     ecx, 11h
0x14012086e  ja      short loc_1401208D6
0x140120870  jz      short loc_1401208CC
0x140120872  cmp     ecx, 9
0x140120875  ja      short loc_1401208A9
0x140120877  jz      short loc_14012089F
0x140120879  test    dl, dl
0x14012087b  jz      short loc_14012089F
0x14012087d  sub     ecx, 1
0x140120880  jz      short loc_14012089F
0x140120882  sub     ecx, 1
0x140120885  jz      short loc_14012089F
0x140120887  sub     ecx, 1
0x14012088a  jz      short loc_14012089F
0x14012088c  sub     ecx, 2
0x14012088f  jz      short loc_14012089F
0x140120891  sub     ecx, 1
0x140120894  jz      short loc_14012089F
0x140120896  sub     ecx, 1
0x140120899  jnz     loc_1401209D6
0x14012089f  mov     ebx, 0C0000010h
0x1401208a4  jmp     loc_140120A9A
0x1401208a9  sub     ecx, 0Ah
0x1401208ac  jz      short loc_14012089F
0x1401208ae  sub     ecx, 1
0x1401208b1  jz      short loc_1401208CC
0x1401208b3  sub     ecx, 1
0x1401208b6  jz      short loc_14012089F
0x1401208b8  sub     ecx, 1
0x1401208bb  jz      short loc_14012089F
0x1401208bd  sub     ecx, 1
0x1401208c0  jz      short loc_14012089F
0x1401208c2  sub     ecx, 1
0x1401208c5  jz      short loc_14012089F
0x1401208c7  cmp     ecx, 1
0x1401208ca  jnz     short loc_140120851
0x1401208cc  mov     ebx, 800001B6h
0x1401208d1  jmp     loc_140120A9A
0x1401208d6  cmp     ecx, 1Ah
0x1401208d9  ja      short loc_14012091C
0x1401208db  jz      short loc_140120908
0x1401208dd  sub     ecx, 12h
0x1401208e0  jz      short loc_140120908
0x1401208e2  sub     ecx, 1
0x1401208e5  jz      short loc_140120908
0x1401208e7  sub     ecx, 1
0x1401208ea  jz      short loc_140120912
0x1401208ec  sub     ecx, 1
0x1401208ef  jz      loc_140120851
0x1401208f5  sub     ecx, 1
0x1401208f8  jz      short loc_140120908
0x1401208fa  sub     ecx, 2
0x1401208fd  jz      short loc_140120908
0x1401208ff  cmp     ecx, 1
0x140120902  jnz     loc_140120851
0x140120908  mov     ebx, 0C0000184h
0x14012090d  jmp     loc_140120A9A
0x140120912  mov     ebx, 0C0000018h
0x140120917  jmp     loc_140120A9A
0x14012091c  sub     ecx, 1Bh
0x14012091f  jz      short loc_14012093B
0x140120921  sub     ecx, 1
0x140120924  jz      loc_14012089F
0x14012092a  sub     ecx, 2
0x14012092d  jz      loc_140120A3C
0x140120933  sub     ecx, 1
0x140120936  jmp     loc_14012088F
0x14012093b  mov     ebx, 0C00000BBh
0x140120940  jmp     loc_140120A9A
0x140120945  sub     ecx, 81h
0x14012094b  jz      loc_14012089F
0x140120951  sub     ecx, 1
0x140120954  jz      loc_140120A3C
0x14012095a  jmp     short loc_1401209D6
0x14012095c  shr     edx, 1
0x14012095e  movzx   ecx, dl
0x140120961  cmp     ecx, r9d
0x140120964  ja      loc_140120A79
0x14012096a  jz      loc_14012089F
0x140120970  cmp     ecx, 0Eh
0x140120973  ja      short loc_1401209F2
0x140120975  jz      loc_14012089F
0x14012097b  cmp     ecx, 7
0x14012097e  ja      short loc_1401209B9
0x140120980  jz      short loc_1401209E8
0x140120982  test    dl, dl
0x140120984  jz      short loc_1401209B2
0x140120986  sub     ecx, 1
0x140120989  jz      loc_14012089F
0x14012098f  sub     ecx, 1
0x140120992  jz      loc_14012089F
0x140120998  sub     ecx, 1
0x14012099b  jz      loc_140120851
0x1401209a1  sub     ecx, 1
0x1401209a4  jz      loc_140120851
0x1401209aa  sub     ecx, 1
0x1401209ad  jmp     loc_1401208FD
0x1401209b2  xor     ebx, ebx
0x1401209b4  jmp     loc_140120A9A
0x1401209b9  sub     ecx, 8
0x1401209bc  jz      short loc_1401209E8
0x1401209be  sub     ecx, 1
0x1401209c1  jz      short loc_1401209E8
0x1401209c3  sub     ecx, 1
0x1401209c6  jz      short loc_1401209E8
0x1401209c8  sub     ecx, 1
0x1401209cb  jz      loc_14012089F
0x1401209d1  sub     ecx, 1
0x1401209d4  jz      short loc_1401209DE
0x1401209d6  cmp     ecx, 1
0x1401209d9  jmp     loc_140120A67
0x1401209de  mov     ebx, 0C000042Ah
0x1401209e3  jmp     loc_140120A9A
0x1401209e8  mov     ebx, 0C0000240h
0x1401209ed  jmp     loc_140120A9A
0x1401209f2  cmp     ecx, 16h
0x1401209f5  ja      short loc_140120A43
0x1401209f7  jz      loc_14012089F
0x1401209fd  sub     ecx, 0Fh
0x140120a00  jz      loc_14012089F
0x140120a06  sub     ecx, 1
0x140120a09  jz      loc_14012089F
0x140120a0f  sub     ecx, 1
0x140120a12  jz      loc_14012089F
0x140120a18  sub     ecx, 1
0x140120a1b  jz      loc_14012089F
0x140120a21  sub     ecx, 1
0x140120a24  jz      loc_14012089F
0x140120a2a  sub     ecx, 1
0x140120a2d  jz      loc_140120908
0x140120a33  cmp     ecx, 1
0x140120a36  jnz     loc_140120851
0x140120a3c  mov     ebx, 0C0000022h
0x140120a41  jmp     short loc_140120A9A
0x140120a43  sub     ecx, 18h
0x140120a46  jz      loc_14012089F
0x140120a4c  sub     ecx, 1
0x140120a4f  jz      short loc_140120A72
0x140120a51  sub     ecx, 1
0x140120a54  jz      short loc_140120A72
0x140120a56  sub     ecx, 1
0x140120a59  jz      short loc_1401209E8
0x140120a5b  sub     ecx, 1
0x140120a5e  jz      loc_140120851
0x140120a64  cmp     ecx, 2
0x140120a67  jz      loc_14012089F
0x140120a6d  jmp     loc_140120851
0x140120a72  mov     ebx, 0C00000B5h
0x140120a77  jmp     short loc_140120A9A
0x140120a79  sub     ecx, 81h
0x140120a7f  jz      loc_14012089F
0x140120a85  sub     ecx, 1
0x140120a88  jnz     loc_1401209D6
0x140120a8e  mov     ebx, 0C00000A3h
0x140120a93  jmp     short loc_140120A9A
0x140120a95  mov     ebx, 0C000042Bh
0x140120a9a  mov     rdx, [rdi]
0x140120a9d  mov     r9d, ebx
0x140120aa0  mov     eax, [rdi+50h]
0x140120aa3  mov     rcx, [rdi+60h]
0x140120aa7  mov     [rsp+0D0h+var_B0], eax
0x140120aab  mov     r8, [rdx+1078h]
0x140120ab2  mov     rsi, [rdx+1058h]
0x140120ab9  add     rdx, 1000h
0x140120ac0  mov     [rbp+57h+Context], r8
0x140120ac4  call    StorpTelemetryCollectNvmeNonIoCmdPerfData
0x140120ac9  mov     [rsi+30h], ebx
0x140120acc  xor     edx, edx; Val
0x140120ace  mov     qword ptr [rsi+38h], 0
0x140120ad6  mov     r8d, 10B0h; Size
0x140120adc  mov     rcx, [rdi]; void *
0x140120adf  call    memset_0
0x140120ae4  and     dword ptr [rdi+40h], 0FFFFFFFEh
0x140120ae8  cmp     cs:StorEtwLoggingEnabled, 0
0x140120aef  mov     byte ptr [rsi+8Dh], 0ACh
0x140120af6  mov     [rsi+30h], ebx
0x140120af9  jz      loc_140120DB3
0x140120aff  xorps   xmm0, xmm0
0x140120b02  lea     rdx, [rbp+57h+var_60]
0x140120b06  mov     rcx, rsi
0x140120b09  movups  [rbp+57h+var_60], xmm0
0x140120b0d  call    cs:__imp_IoGetActivityIdIrp
0x140120b14  nop     dword ptr [rax+rax+00h]
0x140120b19  mov     rdx, [rsi+0B8h]
0x140120b20  movzx   eax, byte ptr [rdx]
0x140120b23  sub     eax, 0Eh
0x140120b26  jz      loc_140120D90
0x140120b2c  sub     eax, 1
0x140120b2f  jz      short loc_140120B97
0x140120b31  cmp     eax, 0Ch
0x140120b34  jnz     loc_140120DB3
0x140120b3a  cmp     byte ptr [rdx+1], 7
0x140120b3e  jnz     short loc_140120B7E
0x140120b40  cmp     dword ptr [rdx+8], 0
0x140120b44  jnz     short loc_140120B7E
0x140120b46  test    cs:byte_140177432, 40h
0x140120b4d  jz      loc_140120DB3
0x140120b53  mov     rax, [rsi+38h]
0x140120b57  test    rax, rax
0x140120b5a  jz      short loc_140120B60
0x140120b5c  mov     ecx, [rax]
0x140120b5e  jmp     short loc_140120B62
0x140120b60  xor     ecx, ecx
0x140120b62  mov     eax, [rsi+30h]
0x140120b65  lea     r8, [rbp+57h+var_60]
0x140120b69  mov     [rsp+0D0h+var_A8], eax
0x140120b6d  mov     r9, rsi
0x140120b70  mov     [rsp+0D0h+var_B0], ecx
0x140120b74  call    McTemplateK0pqd_EtwWriteTransfer
0x140120b79  jmp     loc_140120DB3
0x140120b7e  test    cs:byte_140177432, 20h
0x140120b85  jz      loc_140120DB3
0x140120b8b  lea     rdx, EventPnpRequestComplete
0x140120b92  jmp     loc_140120DA0
0x140120b97  cmp     cs:byte_140177431, 0
0x140120b9e  jge     loc_140120DB3
0x140120ba4  mov     rdx, [rdx+8]
0x140120ba8  movzx   eax, byte ptr [rdx+2]
0x140120bac  cmp     al, 28h ; '('
0x140120bae  jnz     loc_140120C99
0x140120bb4  cmp     dword ptr [rdx+14h], 0
0x140120bb8  jnz     loc_140120DB3
0x140120bbe  mov     r15d, [rdx+38h]
0x140120bc2  test    r15d, r15d
0x140120bc5  jz      loc_140120DB3
0x140120bcb  xor     r11b, r11b
0x140120bce  xor     edi, edi
0x140120bd0  xor     r13b, r13b
0x140120bd3  xor     r9d, r9d
0x140120bd6  xor     r14d, r14d
0x140120bd9  xor     r12b, r12b
0x140120bdc  mov     ecx, [rdx+r14*4+78h]
0x140120be1  cmp     ecx, 80h
0x140120be7  jb      short loc_140120C60
0x140120be9  mov     r10d, [rdx+10h]
0x140120bed  cmp     ecx, r10d
0x140120bf0  jnb     short loc_140120C60
0x140120bf2  mov     r8d, ecx
0x140120bf5  mov     ecx, [rcx+rdx]
0x140120bf8  sub     ecx, 40h ; '@'
0x140120bfb  jz      short loc_140120C52
0x140120bfd  sub     ecx, 1
0x140120c00  jz      short loc_140120C26
0x140120c02  cmp     ecx, 1
0x140120c05  jnz     short loc_140120C5B
0x140120c07  lea     rcx, [r8+28h]
0x140120c0b  cmp     rcx, r10
0x140120c0e  ja      short loc_140120C5B
0x140120c10  cmp     dword ptr [r8+rdx+0Ch], 0
  ... truncated ...
```
