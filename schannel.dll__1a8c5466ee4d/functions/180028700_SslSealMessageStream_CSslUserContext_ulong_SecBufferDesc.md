# SslSealMessageStream(CSslUserContext *,ulong,_SecBufferDesc *)

- ea: `0x180028700`
- end: `0x180029087`
- name: `?SslSealMessageStream@@YAJPEAUCSslUserContext@@KPEAU_SecBufferDesc@@@Z`
- size: `2439`
- prototype: `__int64 __fastcall(struct CSslUserContext *, unsigned int, struct _SecBufferDesc *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180027740`

## callees

- `0x180021da8`
- `0x180021de8`
- `0x180021e64`
- `0x180028700`
- `0x180057c8c`
- `0x180057cb4`
- `0x18005c3a0`
- `0x18006bcf0`
- `0x180088a54`
- `0x180088a60`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028a64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028a64`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028b87`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028b87`
- `ncrypt!SslEncryptPacket` at `0x18002896f`
- `ncrypt!SslEncryptPacket` at `0x18008cf16`
- `ncrypt!SslEncryptPacket` at `0x18002896f`
- `ncrypt!SslEncryptPacket` at `0x18008cf16`

## string_xrefs

- `0x180028ff8`: `write counter`

## pseudocode

```c
__int64 __fastcall SslSealMessageStream(struct CSslUserContext *a1, int a2, struct _SecBufferDesc *a3)
{
  CCipherMill *v6; // r10
  unsigned int cBuffers; // r8d
  PSecBuffer pBuffers; // r9
  struct _SecBuffer *v10; // rdi
  struct _SecBuffer *v11; // rsi
  struct _SecBuffer *v12; // r15
  unsigned int i; // eax
  unsigned int BufferType; // ecx
  unsigned __int8 *pvBuffer; // r9
  __int64 cbBuffer; // rcx
  BOOL v17; // r14d
  unsigned int v18; // ebx
  unsigned int v19; // r8d
  unsigned int v20; // edx
  int v21; // edx
  struct CSslUserContext *v22; // r13
  int v23; // eax
  __int64 v24; // r11
  unsigned int v25; // r8d
  __int64 v26; // rax
  unsigned int KeyUpdateRecord; // eax
  unsigned int v28; // ebx
  unsigned int v29; // edx
  int v30; // ecx
  unsigned int v31; // edx
  unsigned int v32; // ecx
  unsigned int v33; // edx
  unsigned int v34; // ecx
  unsigned int v35; // eax
  unsigned int v36; // edx
  int v37; // eax
  unsigned int v38; // ecx
  void *v39; // r14
  unsigned int v40; // ecx
  char v41; // cl
  int v42; // r8d
  __int64 v43; // rdx
  __int64 v44; // r9
  unsigned int v45; // ecx
  char *v46; // rax
  char *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  unsigned int v50; // r13d
  __int64 v51; // r12
  __int64 v52; // rdx
  const wchar_t *v53; // r9
  _BYTE *v54; // r8
  CCipherMill *v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // [rsp+50h] [rbp-19h]
  unsigned __int8 *v58; // [rsp+58h] [rbp-11h]
  _BYTE *v59; // [rsp+60h] [rbp-9h]
  char *hMem; // [rsp+68h] [rbp-1h]
  __int128 v61; // [rsp+70h] [rbp+7h] BYREF
  __int128 v62; // [rsp+80h] [rbp+17h] BYREF
  int v64; // [rsp+E0h] [rbp+77h]
  unsigned int v65; // [rsp+E8h] [rbp+7Fh]

  v61 = 0;
  v62 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  cBuffers = a3->cBuffers;
  if ( !cBuffers )
    goto LABEL_5;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  for ( i = 0; i < cBuffers; ++i )
  {
    pBuffers = a3->pBuffers;
    BufferType = pBuffers[i].BufferType;
    if ( BufferType == 7 )
    {
LABEL_9:
      v10 = &pBuffers[i];
      continue;
    }
    v38 = BufferType - 1;
    if ( v38 )
    {
      v40 = v38 - 1;
      if ( v40 )
      {
        if ( v40 == 4 )
          v12 = &pBuffers[i];
      }
      else
      {
        if ( !v10 )
          goto LABEL_9;
        if ( !v12 )
          v12 = &pBuffers[i];
      }
    }
    else
    {
      v11 = &pBuffers[i];
      if ( !v10 )
        goto LABEL_9;
    }
  }
  if ( !v10 || !v11 )
  {
LABEL_5:
    if ( v6 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 5) != 0 )
      WPP_SF_dd(*((_QWORD *)v6 + 2), 14, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, 2148074248LL, -2146893048);
    return 2148074248LL;
  }
  pvBuffer = (unsigned __int8 *)v11->pvBuffer;
  cbBuffer = v10->cbBuffer;
  v58 = pvBuffer;
  v17 = pvBuffer != (unsigned __int8 *)v10->pvBuffer + cbBuffer;
  if ( v12 && v12->pvBuffer != &pvBuffer[v11->cbBuffer] )
    v17 = 1;
  v18 = v11->cbBuffer;
  v19 = v11->cbBuffer + cbBuffer;
  if ( v19 < (unsigned int)cbBuffer )
  {
    if ( v6 == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 5) == 0 )
      return 2148074333LL;
    v52 = 18;
    goto LABEL_155;
  }
  if ( v17 )
  {
    LODWORD(v61) = v11->cbBuffer + cbBuffer;
    if ( v12 )
    {
      v45 = v19 + v12->cbBuffer;
      if ( v45 < v19 )
      {
        if ( v6 == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 5) == 0 )
          return 2148074333LL;
        v52 = 20;
        goto LABEL_155;
      }
      v19 += v12->cbBuffer;
      LODWORD(v61) = v45;
    }
    v46 = (char *)LocalAlloc(0x40u, v19);
    hMem = v46;
    v47 = v46;
    if ( v46 )
    {
      *((_QWORD *)&v61 + 1) = v46;
      DWORD1(v61) = 0;
      v48 = v10->cbBuffer;
      v65 = v61 - v48;
      v18 = v11->cbBuffer;
      v58 = (unsigned __int8 *)&v47[v48];
      memcpy_0(&v47[v48], v11->pvBuffer, v11->cbBuffer);
      v6 = WPP_GLOBAL_Control;
      pvBuffer = v58;
      goto LABEL_22;
    }
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 5) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_12c1054e772130c368912b44a071a70c_Traceguids,
        2148074240LL,
        -2146893056);
    return 2148074240LL;
  }
  *((_QWORD *)&v61 + 1) = v10->pvBuffer;
  v20 = v10->cbBuffer + v11->cbBuffer;
  v65 = v18;
  *(_QWORD *)&v61 = v20;
  if ( !v12 )
    goto LABEL_21;
  if ( v20 + v12->cbBuffer < v20 )
  {
    if ( v6 == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 5) == 0 )
      return 2148074333LL;
    v52 = 19;
LABEL_155:
    WPP_SF_dd(*((_QWORD *)v6 + 2), v52, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, 2148074333LL, -2146892963);
    return 2148074333LL;
  }
  LODWORD(v61) = v20 + v12->cbBuffer;
  v65 = v18 + v12->cbBuffer;
LABEL_21:
  hMem = 0;
LABEL_22:
  v21 = 23;
  v64 = 23;
  if ( a2 == 0x40000000 )
  {
    v49 = *((_DWORD *)a1 + 6);
    if ( (v49 & 0x800A2AAA) != 0 && !v18 )
    {
      if ( v6 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)v6 + 2), 10, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
    }
    else if ( (v49 & 0x40051555) != 0 && v18 == 4 )
    {
      if ( !*pvBuffer && !pvBuffer[1] && !pvBuffer[2] && !pvBuffer[3] && (v49 & 0x1000) == 0 )
      {
        if ( v6 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)v6 + 2), 11, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
          v6 = WPP_GLOBAL_Control;
          pvBuffer = v58;
        }
        v21 = 22;
        goto LABEL_118;
      }
    }
    else if ( v18 == 2 && (unsigned __int8)(*pvBuffer - 1) <= 1u )
    {
      if ( v6 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
      {
        WPP_SF_dd(*((_QWORD *)v6 + 2), 12, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, *pvBuffer, pvBuffer[1]);
        pvBuffer = v58;
      }
      if ( IsValidAlert(pvBuffer[1]) )
      {
        v21 = 21;
LABEL_118:
        v64 = v21;
        goto LABEL_23;
      }
    }
    v28 = -2146893048;
    goto LABEL_76;
  }
LABEL_23:
  v22 = a1;
  v23 = *((_DWORD *)a1 + 6);
  if ( (v23 & 0xF0000) != 0 )
    v24 = *((_QWORD *)a1 + 13) | ((__int64)*((int *)a1 + 29) << 48);
  else
    v24 = *((_QWORD *)a1 + 13);
  v57 = v24;
  if ( (v23 & 0x30) == 0 && (v23 & 0xC0) == 0 )
  {
LABEL_27:
    v25 = v65;
    goto LABEL_28;
  }
  v50 = v10->cbBuffer;
  v51 = *((unsigned int *)a1 + 17);
  if ( v10->cbBuffer <= (unsigned int)(v51 + *((_DWORD *)a1 + 16)) )
  {
    if ( v6 == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 4) == 0 )
    {
      v22 = a1;
    }
    else
    {
      WPP_SF_(*((_QWORD *)v6 + 2), 31, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
      v6 = WPP_GLOBAL_Control;
      pvBuffer = v58;
      v21 = v64;
      v24 = v57;
      v22 = a1;
    }
    goto LABEL_27;
  }
  if ( v21 == 23 && v18 > 1 )
  {
    v54 = (char *)v10->pvBuffer + v51;
    *((_QWORD *)&v62 + 1) = *((_QWORD *)&v61 + 1);
    *(_QWORD *)&v62 = (unsigned int)v61;
    v59 = v54;
    *v54 = *(_BYTE *)v11->pvBuffer;
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control )
      goto LABEL_191;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
      v55 = WPP_GLOBAL_Control;
      v54 = v59;
      v24 = v57;
    }
    if ( v55 == (CCipherMill *)&WPP_GLOBAL_Control )
      goto LABEL_191;
    if ( (*((_BYTE *)v55 + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v55 + 2), 23, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, 1);
      v55 = WPP_GLOBAL_Control;
      v54 = v59;
      v24 = v57;
    }
    if ( v55 == (CCipherMill *)&WPP_GLOBAL_Control )
      goto LABEL_191;
    if ( (*((_BYTE *)v55 + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v55 + 2), 24, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, v50 - (unsigned int)v51);
      v55 = WPP_GLOBAL_Control;
      v54 = v59;
      v24 = v57;
    }
    if ( v55 == (CCipherMill *)&WPP_GLOBAL_Control )
      goto LABEL_191;
    if ( (*((_BYTE *)v55 + 28) & 4) != 0 )
    {
      WPP_SF_q(*((_QWORD *)v55 + 2), 25, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, v54);
      v55 = WPP_GLOBAL_Control;
      v54 = v59;
      v24 = v57;
    }
    if ( v55 == (CCipherMill *)&WPP_GLOBAL_Control )
      goto LABEL_191;
    if ( (*((_BYTE *)v55 + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v55 + 2), 26, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, DWORD1(v62));
      v55 = WPP_GLOBAL_Control;
      v54 = v59;
      v24 = v57;
    }
    if ( v55 == (CCipherMill *)&WPP_GLOBAL_Control )
      goto LABEL_191;
    if ( (*((_BYTE *)v55 + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v55 + 2), 27, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, (unsigned int)v62);
      v55 = WPP_GLOBAL_Control;
      v54 = v59;
      v24 = v57;
    }
    if ( v55 == (CCipherMill *)&WPP_GLOBAL_Control )
      goto LABEL_191;
    if ( (*((_BYTE *)v55 + 28) & 4) != 0 )
    {
      WPP_SF_q(*((_QWORD *)v55 + 2), 28, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, *((_QWORD *)&v62 + 1));
      v55 = WPP_GLOBAL_Control;
      v54 = v59;
      v24 = v57;
    }
    if ( v55 == (CCipherMill *)&WPP_GLOBAL_Control )
    {
LABEL_191:
      v22 = a1;
    }
    else
    {
      v22 = a1;
      if ( (*((_BYTE *)v55 + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v55 + 2), 29, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, *((unsigned int *)a1 + 26));
        v54 = v59;
        v24 = v57;
      }
    }
    KeyUpdateRecord = SslEncryptPacket(
                        *((_QWORD *)v22 + 11),
                        *((_QWORD *)v22 + 6),
                        v54,
                        1,
                        *((_QWORD *)&v62 + 1),
                        v62,
                        (char *)&v62 + 4,
                        v24,
                        23,
                        0);
    if ( KeyUpdateRecord )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v43 = 30;
        goto LABEL_204;
      }
LABEL_75:
      v28 = -2146893015;
LABEL_76:
      if ( v17 )
      {
        v39 = hMem;
        goto LABEL_78;
      }
      goto LABEL_67;
    }
    --v18;
    v24 = v57 + 1;
    pvBuffer = v58 + 1;
    v56 = DWORD1(v62);
    v25 = v65 - 1;
    ++*((_QWORD *)v22 + 13);
    *((_QWORD *)&v61 + 1) += v56;
    *(_QWORD *)&v61 = (unsigned int)(v61 - v56);
    v6 = WPP_GLOBAL_Control;
    v21 = v64;
    ++v57;
    ++v58;
    --v65;
  }
  else
  {
    pvBuffer = (unsigned __int8 *)v10->pvBuffer + v51;
    v25 = v61 - v51;
    v58 = pvBuffer;
    v65 = v61 - v51;
    if ( v18 )
    {
      memmove_0(pvBuffer, v11->pvBuffer, v18);
      v6 = WPP_GLOBAL_Control;
      pvBuffer = v58;
      v21 = v64;
      v24 = v57;
      v22 = a1;
      goto LABEL_27;
    }
    v22 = a1;
  }
LABEL_28:
  if ( (*((_DWORD *)v22 + 6) & 0x3000) != 0 )
  {
    v26 = v18++;
    pvBuffer[v26] = v21;
    v21 = 23;
    v6 = WPP_GLOBAL_Control;
    v64 = 23;
  }
  if ( v6 != (CCipherMill *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v6 + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)v6 + 2), 32, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
      v6 = WPP_GLOBAL_Control;
      pvBuffer = v58;
      v25 = v65;
      v21 = v64;
      v24 = v57;
    }
    if ( v6 != (CCipherMill *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v6 + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v6 + 2), 33, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, v18);
        v6 = WPP_GLOBAL_Control;
        pvBuffer = v58;
        v25 = v65;
        v21 = v64;
        v24 = v57;
      }
      if ( v6 != (CCipherMill *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v6 + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v6 + 2), 34, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, v25);
          v6 = WPP_GLOBAL_Control;
          pvBuffer = v58;
          v21 = v64;
          v24 = v57;
        }
        if ( v6 != (CCipherMill *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v6 + 28) & 4) != 0 )
          {
            WPP_SF_q(*((_QWORD *)v6 + 2), 35, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, pvBuffer);
            v6 = WPP_GLOBAL_Control;
            v21 = v64;
            v24 = v57;
          }
          if ( v6 != (CCipherMill *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v6 + 28) & 4) != 0 )
            {
              WPP_SF_d(*((_QWORD *)v6 + 2), 36, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, DWORD1(v61));
              v6 = WPP_GLOBAL_Control;
              v21 = v64;
              v24 = v57;
            }
            if ( v6 != (CCipherMill *)&WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v6 + 28) & 4) != 0 )
              {
                WPP_SF_d(*((_QWORD *)v6 + 2), 37, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, (unsigned int)v61);
                v6 = WPP_GLOBAL_Control;
                v21 = v64;
                v24 = v57;
              }
              if ( v6 != (CCipherMill *)&WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v6 + 28) & 4) != 0 )
                {
                  WPP_SF_q(
                    *((_QWORD *)v6 + 2),
                    38,
                    &WPP_12c1054e772130c368912b44a071a70c_Traceguids,
                    *((_QWORD *)&v61 + 1));
                  v6 = WPP_GLOBAL_Control;
                  v21 = v64;
                  v24 = v57;
                }
                if ( v6 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)v6 + 2),
                    39,
                    &WPP_12c1054e772130c368912b44a071a70c_Traceguids,
                    *((unsigned int *)v22 + 26));
                  v21 = v64;
                  v24 = v57;
                }
              }
            }
          }
        }
      }
    }
  }
  KeyUpdateRecord = SslEncryptPacket(
                      *((_QWORD *)a1 + 11),
                      *((_QWORD *)a1 + 6),
                      v58,
                      v18,
                      *((_QWORD *)&v61 + 1),
                      v61,
                      (char *)&v61 + 4,
                      v24,
                      v21,
                      0);
  v28 = KeyUpdateRecord;
  if ( KeyUpdateRecord )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v43 = 40;
      goto LABEL_204;
    }
    goto LABEL_75;
  }
  v29 = DWORD1(v61);
  v30 = *((_DWORD *)a1 + 6);
  if ( (v30 & 0xF0000) != 0 && DWORD1(v61) > *((unsigned __int16 *)a1 + 68) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_75;
    v43 = 41;
    v44 = 0;
LABEL_96:
    WPP_SF_d(*((_QWORD *)v6 + 2), v43, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, v44);
LABEL_91:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_75;
  }
  ++*((_QWORD *)a1 + 13);
  if ( (v30 & 0x3000) != 0 )
  {
    v41 = *((_BYTE *)a1 + 472);
    if ( v41 || *((_QWORD *)a1 + 13) >= (unsigned __int64)*((unsigned int *)a1 + 119) )
    {
      v42 = v61;
      if ( (unsigned int)v61 < v29 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_75;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
        goto LABEL_91;
      }
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v53 = L"peer request";
        if ( !v41 )
          v53 = L"write counter";
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, v53);
        v29 = DWORD1(v61);
        v42 = v61;
      }
      *((_QWORD *)&v62 + 1) = *((_QWORD *)&v61 + 1) + v29;
      *(_QWORD *)&v62 = v42 - v29;
      KeyUpdateRecord = CSslUserContext::GenerateKeyUpdateRecord(a1, (struct SPBuffer *)&v62);
      v28 = KeyUpdateRecord;
      if ( KeyUpdateRecord )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_75;
        v43 = 44;
LABEL_204:
        v44 = KeyUpdateRecord;
        goto LABEL_96;
      }
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
      v29 = DWORD1(v61);
      *((_BYTE *)a1 + 472) = 0;
    }
  }
  v31 = DWORD1(v62) + v29;
  v32 = v31;
  if ( v31 >= v10->cbBuffer )
    v32 = v10->cbBuffer;
  v33 = v31 - v32;
  v10->cbBuffer = v32;
  v34 = v11->cbBuffer;
  if ( v12 )
  {
    v35 = v33;
    if ( v33 >= v34 )
      v35 = v11->cbBuffer;
    v11->cbBuffer = v35;
    v36 = v33 - v35;
    if ( v36 >= v12->cbBuffer )
      v36 = v12->cbBuffer;
    v12->cbBuffer = v36;
  }
  else
  {
    if ( v33 >= v34 )
      v33 = v11->cbBuffer;
    v11->cbBuffer = v33;
  }
  if ( v17 )
  {
    v39 = hMem;
    memcpy_0(v10->pvBuffer, hMem, v10->cbBuffer);
    memcpy_0(v11->pvBuffer, &hMem[v10->cbBuffer], v11->cbBuffer);
    if ( v12 )
      memcpy_0(v12->pvBuffer, &hMem[v11->cbBuffer + v10->cbBuffer], v12->cbBuffer);
LABEL_78:
    LocalFree(v39);
  }
  v6 = WPP_GLOBAL_Control;
LABEL_67:
  if ( v6 != (CCipherMill *)&WPP_GLOBAL_Control )
  {
    if ( (v37 = *((_DWORD *)v6 + 7), (v37 & 1) != 0) && v28 || (v37 & 4) != 0 )
      WPP_SF_dd(*((_QWORD *)v6 + 2), 49, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, v28, v28);
  }
  return v28;
}

```

## disassembly

```asm
0x180028700  mov     [rsp-8+arg_0], rcx
0x180028705  push    rbp
0x180028706  push    rbx
0x180028707  push    r12
0x180028709  push    r13
0x18002870b  lea     rbp, [rsp-3Fh]
0x180028710  sub     rsp, 0A8h
0x180028717  xorps   xmm0, xmm0
0x18002871a  xorps   xmm1, xmm1
0x18002871d  movups  [rbp+57h+var_50], xmm0
0x180028721  mov     rbx, r8
0x180028724  mov     r12d, edx
0x180028727  movups  [rbp+57h+var_40], xmm1
0x18002872b  mov     r13, rcx
0x18002872e  mov     r10, cs:WPP_GLOBAL_Control
0x180028735  lea     r11, WPP_GLOBAL_Control
0x18002873c  cmp     r10, r11
0x18002873f  jz      short loc_18002874C
0x180028741  test    byte ptr [r10+1Ch], 20h
0x180028746  jnz     loc_180028D5B
0x18002874c  mov     r8d, [rbx+4]
0x180028750  mov     [rsp+0C0h+arg_8], rsi
0x180028758  mov     [rsp+0C0h+var_20], rdi
0x180028760  mov     [rsp+0C0h+var_30], r15
0x180028768  test    r8d, r8d
0x18002876b  jnz     short loc_180028780
0x18002876d  cmp     r10, r11
0x180028770  jnz     loc_180029054
0x180028776  mov     eax, 80090308h
0x18002877b  jmp     loc_180028A07
0x180028780  mov     r9, [rbx+8]
0x180028784  xor     edi, edi
0x180028786  xor     esi, esi
0x180028788  xor     r15d, r15d
0x18002878b  xor     eax, eax
0x18002878d  mov     edx, eax
0x18002878f  shl     rdx, 4
0x180028793  add     rdx, r9
0x180028796  mov     ecx, [rdx+4]
0x180028799  cmp     ecx, 7
0x18002879c  jnz     loc_180028A2D
0x1800287a2  mov     rdi, rdx
0x1800287a5  inc     eax
0x1800287a7  cmp     eax, r8d
0x1800287aa  jb      short loc_18002878D
0x1800287ac  test    rdi, rdi
0x1800287af  jz      short loc_18002876D
0x1800287b1  test    rsi, rsi
0x1800287b4  jz      short loc_18002876D
0x1800287b6  mov     r9, [rsi+8]
0x1800287ba  mov     r8d, 1
0x1800287c0  mov     rdx, [rdi+8]
0x1800287c4  mov     ecx, [rdi]
0x1800287c6  mov     [rsp+0C0h+var_28], r14
0x1800287ce  xor     r14d, r14d
0x1800287d1  mov     [rbp+57h+var_68], r9
0x1800287d5  lea     rax, [rdx+rcx]
0x1800287d9  cmp     r9, rax
0x1800287dc  setnz   r14b
0x1800287e0  test    r15, r15
0x1800287e3  jz      short loc_1800287F2
0x1800287e5  mov     eax, [rsi]
0x1800287e7  add     rax, r9
0x1800287ea  cmp     [r15+8], rax
0x1800287ee  cmovnz  r14d, r8d
0x1800287f2  mov     ebx, [rsi]
0x1800287f4  lea     r8d, [rbx+rcx]
0x1800287f8  cmp     r8d, ecx
0x1800287fb  jb      loc_180028A6F
0x180028801  test    r14d, r14d
0x180028804  jnz     loc_180028B61
0x18002880a  xor     r8d, r8d
0x18002880d  mov     qword ptr [rbp+57h+var_50+8], rdx
0x180028811  mov     dword ptr [rbp+57h+var_50+4], r8d
0x180028815  mov     edx, [rsi]
0x180028817  add     edx, [rdi]
0x180028819  mov     [rbp+57h+arg_18], ebx
0x18002881c  mov     dword ptr [rbp+57h+var_50], edx
0x18002881f  test    r15, r15
0x180028822  jz      short loc_18002883C
0x180028824  mov     ecx, [r15]
0x180028827  add     ecx, edx
0x180028829  cmp     ecx, edx
0x18002882b  jb      loc_180028CE5
0x180028831  mov     dword ptr [rbp+57h+var_50], ecx
0x180028834  mov     eax, [r15]
0x180028837  add     eax, ebx
0x180028839  mov     [rbp+57h+arg_18], eax
0x18002883c  mov     [rbp+57h+hMem], r8
0x180028840  mov     edx, 17h
0x180028845  mov     [rbp+57h+arg_10], edx
0x180028848  cmp     r12d, 40000000h
0x18002884f  jz      loc_180028C2C
0x180028855  mov     rax, [rbp+57h+arg_0]
0x180028859  mov     r13, [rbp+57h+arg_0]
0x18002885d  mov     rcx, [rax+68h]
0x180028861  mov     eax, [rax+18h]
0x180028864  test    eax, 0F0000h
0x180028869  jnz     loc_180028B4D
0x18002886f  mov     r11, rcx
0x180028872  mov     [rbp+57h+var_70], rcx
0x180028876  test    al, 30h
0x180028878  jnz     loc_180028C98
0x18002887e  test    al, 0C0h
0x180028880  jnz     loc_180028C98
0x180028886  lea     r12, WPP_GLOBAL_Control
0x18002888d  mov     r8d, [rbp+57h+arg_18]
0x180028891  test    dword ptr [r13+18h], 3000h
0x180028899  jz      short loc_1800288B2
0x18002889b  mov     eax, ebx
0x18002889d  inc     ebx
0x18002889f  mov     [rax+r9], dl
0x1800288a3  mov     edx, 17h
0x1800288a8  mov     r10, cs:WPP_GLOBAL_Control
0x1800288af  mov     [rbp+57h+arg_10], edx
0x1800288b2  cmp     r10, r12
0x1800288b5  jz      short loc_180028932
0x1800288b7  test    byte ptr [r10+1Ch], 4
0x1800288bc  jnz     loc_180028E64
0x1800288c2  cmp     r10, r12
0x1800288c5  jz      short loc_180028932
0x1800288c7  test    byte ptr [r10+1Ch], 4
0x1800288cc  jnz     loc_180028E94
0x1800288d2  cmp     r10, r12
0x1800288d5  jz      short loc_180028932
0x1800288d7  test    byte ptr [r10+1Ch], 4
0x1800288dc  jnz     loc_180028EC7
0x1800288e2  cmp     r10, r12
0x1800288e5  jz      short loc_180028932
0x1800288e7  test    byte ptr [r10+1Ch], 4
0x1800288ec  jnz     loc_180028EF6
0x1800288f2  cmp     r10, r12
0x1800288f5  jz      short loc_180028932
0x1800288f7  test    byte ptr [r10+1Ch], 4
0x1800288fc  jnz     loc_180028F1E
0x180028902  cmp     r10, r12
0x180028905  jz      short loc_180028932
0x180028907  test    byte ptr [r10+1Ch], 4
0x18002890c  jnz     loc_180028F4A
0x180028912  cmp     r10, r12
0x180028915  jz      short loc_180028932
0x180028917  test    byte ptr [r10+1Ch], 4
0x18002891c  jnz     loc_180028F76
0x180028922  cmp     r10, r12
0x180028925  jz      short loc_180028932
0x180028927  test    byte ptr [r10+1Ch], 4
0x18002892c  jnz     loc_180028FA2
0x180028932  mov     r8, [rbp+57h+var_68]
0x180028936  lea     rax, [rbp+57h+var_50+4]
0x18002893a  mov     [rsp+0C0h+var_78], 0
0x180028942  mov     r9d, ebx
0x180028945  mov     [rsp+0C0h+var_80], edx
0x180028949  mov     [rsp+0C0h+var_88], r11
0x18002894e  mov     [rsp+0C0h+var_90], rax
0x180028953  mov     eax, dword ptr [rbp+57h+var_50]
0x180028956  mov     [rsp+0C0h+var_98], eax
0x18002895a  mov     rax, qword ptr [rbp+57h+var_50+8]
0x18002895e  mov     [rsp+0C0h+var_A0], rax
0x180028963  mov     rax, [rbp+57h+arg_0]
0x180028967  mov     rdx, [rax+30h]
0x18002896b  mov     rcx, [rax+58h]
0x18002896f  call    cs:__imp_SslEncryptPacket
0x180028975  mov     ebx, eax
0x180028977  test    eax, eax
0x180028979  jnz     loc_180028A43
0x18002897f  mov     r13, [rbp+57h+arg_0]
0x180028983  mov     edx, dword ptr [rbp+57h+var_50+4]
0x180028986  mov     ecx, [r13+18h]
0x18002898a  test    ecx, 0F0000h
0x180028990  jnz     loc_180028B08
0x180028996  inc     qword ptr [r13+68h]
0x18002899a  test    ecx, 3000h
0x1800289a0  jnz     loc_180028AA2
0x1800289a6  add     edx, dword ptr [rbp+57h+var_40+4]
0x1800289a9  cmp     edx, [rdi]
0x1800289ab  mov     ecx, edx
0x1800289ad  cmovnb  ecx, [rdi]
0x1800289b0  sub     edx, ecx
0x1800289b2  mov     [rdi], ecx
0x1800289b4  mov     ecx, [rsi]
0x1800289b6  test    r15, r15
0x1800289b9  jz      loc_180028BD8
0x1800289bf  cmp     edx, ecx
0x1800289c1  mov     eax, edx
0x1800289c3  cmovnb  eax, ecx
0x1800289c6  mov     [rsi], eax
0x1800289c8  sub     edx, eax
0x1800289ca  cmp     edx, [r15]
0x1800289cd  cmovnb  edx, [r15]
0x1800289d1  mov     [r15], edx
0x1800289d4  test    r14d, r14d
0x1800289d7  jnz     loc_180028BE4
0x1800289dd  mov     r10, cs:WPP_GLOBAL_Control
0x1800289e4  cmp     r10, r12
0x1800289e7  jz      short loc_1800289FD
0x1800289e9  mov     eax, [r10+1Ch]
0x1800289ed  test    al, 1
0x1800289ef  jnz     loc_18002902B
0x1800289f5  test    al, 4
0x1800289f7  jnz     loc_180029033
0x1800289fd  mov     eax, ebx
0x1800289ff  mov     r14, [rsp+0C0h+var_28]
0x180028a07  mov     r15, [rsp+0C0h+var_30]
0x180028a0f  mov     rdi, [rsp+0C0h+var_20]
0x180028a17  mov     rsi, [rsp+0C0h+arg_8]
0x180028a1f  add     rsp, 0A8h
0x180028a26  pop     r13
0x180028a28  pop     r12
0x180028a2a  pop     rbx
0x180028a2b  pop     rbp
0x180028a2c  retn
0x180028a2d  sub     ecx, 1
0x180028a30  jnz     short loc_180028A7F
0x180028a32  mov     rsi, rdx
0x180028a35  test    rdi, rdi
0x180028a38  jz      loc_1800287A2
0x180028a3e  jmp     loc_1800287A5
0x180028a43  mov     r10, cs:WPP_GLOBAL_Control
0x180028a4a  cmp     r10, r12
0x180028a4d  jnz     loc_180028FC7
0x180028a53  mov     ebx, 80090329h
0x180028a58  test    r14d, r14d
0x180028a5b  jz      short loc_1800289E4
0x180028a5d  mov     r14, [rbp+57h+hMem]
0x180028a61  mov     rcx, r14; hMem
0x180028a64  call    cs:__imp_LocalFree
0x180028a6a  jmp     loc_1800289DD
0x180028a6f  cmp     r10, r11
0x180028a72  jnz     loc_180028DB3
0x180028a78  mov     eax, 8009035Dh
0x180028a7d  jmp     short loc_1800289FF
0x180028a7f  sub     ecx, 1
0x180028a82  jnz     loc_180028D83
0x180028a88  test    rdi, rdi
0x180028a8b  jz      loc_1800287A2
0x180028a91  test    r15, r15
0x180028a94  jnz     loc_1800287A5
0x180028a9a  mov     r15, rdx
0x180028a9d  jmp     loc_1800287A5
0x180028aa2  movzx   ecx, byte ptr [r13+1D8h]
0x180028aaa  test    cl, cl
0x180028aac  jnz     short loc_180028ABF
0x180028aae  mov     eax, [r13+1DCh]
0x180028ab5  cmp     [r13+68h], rax
0x180028ab9  jb      loc_1800289A6
0x180028abf  mov     r8d, dword ptr [rbp+57h+var_50]
0x180028ac3  cmp     r8d, edx
0x180028ac6  jnb     loc_180028FDC
0x180028acc  mov     r10, cs:WPP_GLOBAL_Control
0x180028ad3  cmp     r10, r12
0x180028ad6  jz      loc_180028A53
0x180028adc  test    byte ptr [r10+1Ch], 1
0x180028ae1  jz      loc_180028A53
0x180028ae7  mov     rcx, [r10+10h]
0x180028aeb  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x180028af2  mov     edx, 2Ah ; '*'
0x180028af7  call    WPP_SF_
0x180028afc  mov     r10, cs:WPP_GLOBAL_Control
0x180028b03  jmp     loc_180028A53
0x180028b08  movzx   eax, word ptr [r13+88h]
0x180028b10  cmp     edx, eax
0x180028b12  jbe     loc_180028996
0x180028b18  mov     r10, cs:WPP_GLOBAL_Control
0x180028b1f  cmp     r10, r12
0x180028b22  jz      loc_180028A53
0x180028b28  test    byte ptr [r10+1Ch], 1
0x180028b2d  jz      loc_180028A53
0x180028b33  mov     edx, 29h ; ')'
0x180028b38  xor     r9d, r9d
0x180028b3b  mov     rcx, [r10+10h]
0x180028b3f  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x180028b46  call    WPP_SF_d
0x180028b4b  jmp     short loc_180028AFC
0x180028b4d  movsxd  r11, dword ptr [r13+74h]
0x180028b51  shl     r11, 30h
0x180028b55  or      r11, rcx
0x180028b58  mov     [rbp+57h+var_70], r11
0x180028b5c  jmp     loc_180028876
0x180028b61  mov     dword ptr [rbp+57h+var_50], r8d
0x180028b65  test    r15, r15
0x180028b68  jz      short loc_180028B7F
0x180028b6a  mov     ecx, [r15]
0x180028b6d  add     ecx, r8d
0x180028b70  cmp     ecx, r8d
0x180028b73  jb      loc_180028CC7
0x180028b79  mov     r8d, ecx
0x180028b7c  mov     dword ptr [rbp+57h+var_50], ecx
0x180028b7f  mov     edx, r8d; uBytes
0x180028b82  mov     ecx, 40h ; '@'; uFlags
0x180028b87  call    cs:__imp_LocalAlloc
0x180028b8d  mov     [rbp+57h+hMem], rax
0x180028b91  mov     rcx, rax
0x180028b94  test    rax, rax
0x180028b97  jz      loc_180028DC8
0x180028b9d  mov     edx, dword ptr [rbp+57h+var_50]
0x180028ba0  mov     qword ptr [rbp+57h+var_50+8], rax
0x180028ba4  mov     dword ptr [rbp+57h+var_50+4], 0
0x180028bab  mov     eax, [rdi]
0x180028bad  mov     r8d, [rsi]; Size
0x180028bb0  sub     edx, eax
  ... truncated ...
```
