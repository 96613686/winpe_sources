# HUBDESC_InternalValidateEndpointDescriptor

- ea: `0x140036c84`
- end: `0x140037dda`
- name: `HUBDESC_InternalValidateEndpointDescriptor`
- size: `4438`
- prototype: `char __fastcall(char *, __int64, unsigned int *, int *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14003cce8`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x14000c578`
- `0x14001cf04`
- `0x14002d940`
- `0x140036c84`
- `0x140038e24`
- `0x14003bf54`
- `0x140045570`

## import_xrefs

- `ntoskrnl!RtlSetBit` at `0x140037da9`
- `ntoskrnl!RtlSetBit` at `0x140037da9`

## pseudocode

```c
char __fastcall HUBDESC_InternalValidateEndpointDescriptor(char *a1, __int64 a2, unsigned int *a3, int *a4, __int64 a5)
{
  int *v5; // rsi
  int v9; // r15d
  int v10; // ebp
  int v11; // r8d
  __int64 *v12; // rdx
  int v13; // r12d
  unsigned int v14; // ebp
  unsigned int v15; // ecx
  char v16; // r15
  int v18; // edx
  __int64 v19; // rdx
  unsigned __int16 v20; // r14
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // edx
  __int64 v25; // rdx
  int v26; // edx
  int v27; // edx
  int v28; // edx
  int v29; // edx
  int v30; // r9d
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // edx
  int v35; // r9d
  int v36; // edx
  unsigned __int64 v37; // rax
  __int64 v38; // rcx
  int v39; // ecx
  int v40; // ecx
  __int64 v41; // rcx
  int v42; // edx
  int v43; // edx
  int v44; // r9d
  __int64 v45; // rdx
  int v46; // edx
  int v47; // edx
  int v48; // edx
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  int v52; // edx
  int v53; // r9d
  unsigned __int64 v54; // rax
  __int64 v55; // rcx
  int v56; // eax
  __int64 v57; // [rsp+28h] [rbp-80h]
  int v58; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int8 v59; // [rsp+B0h] [rbp+8h]

  v5 = a4;
  v58 = 0;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    v5 = &v58;
  }
  v9 = *(_DWORD *)(a2 + 56);
  v10 = *(_DWORD *)(a2 + 72);
  *a3 = (unsigned __int8)*a1;
  HUBDESC_InternalValidateLastEndpoint(a2, v5, a5);
  v12 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
  if ( *v5 == 1 )
    goto LABEL_32;
  v13 = (_DWORD)a1 - v9;
  v14 = v10 - ((_DWORD)a1 - v9);
  if ( (unsigned __int8)*a1 >= 7u )
    goto LABEL_20;
  (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 81);
  if ( v14 < 7 )
  {
    v15 = *a3;
  }
  else
  {
    *a3 = 7;
    v15 = 7;
  }
  if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
    *v5 = 2;
  if ( v15 >= 7 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_DDDD(
        a5,
        (_DWORD)v12,
        5,
        33,
        (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
        *a1,
        v13,
        7,
        v15);
    }
    v12 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
LABEL_20:
    if ( (unsigned __int8)*a1 > 7u )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 3;
        WPP_RECORDER_SF_DDD(
          a5,
          (_DWORD)v12,
          v11,
          34,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *a1,
          v13,
          7);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a2 + 32))(*(_QWORD *)(a2 + 40), 80);
    }
    if ( *a3 > v14 )
    {
      if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v57) = (_DWORD)a1 - v9;
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_d(a5, (_DWORD)v12, 5, 35, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v57);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 83);
LABEL_32:
      v16 = 1;
      goto LABEL_33;
    }
    v16 = 1;
    if ( (*(_DWORD *)(a2 + 256) & 1) == 0 )
    {
      if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v57) = v13;
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_d(a5, (_DWORD)v12, 5, 36, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v57);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 85);
      goto LABEL_33;
    }
    v59 = a1[2];
    if ( (v59 & 0xF) == 0 )
    {
      if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v57) = v13;
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_d(a5, (_DWORD)v12, 5, 37, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v57);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 86);
    }
    if ( (a1[2] & 0x70) != 0 )
    {
      if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = 2;
        WPP_RECORDER_SF_dD(a5, v18, 5, 38, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v13, a1[2]);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 84);
    }
    if ( (a1[3] & 0xC0) != 0 )
    {
      if ( *(_BYTE *)(a2 + 15) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_dD(a5, (_DWORD)v12, 5, 39, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, a1[3], v13);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 82);
    }
    v19 = (unsigned __int8)a1[3];
    v20 = *((_WORD *)a1 + 2);
    if ( (a1[3] & 3) != 0 )
    {
      if ( (a1[3] & 3) != 1 )
      {
        if ( (a1[3] & 3) != 2 )
        {
          if ( (a1[3] & 3) == 3 )
          {
            v21 = *(_DWORD *)(a2 + 4);
            if ( v21 )
            {
              v22 = v21 - 1;
              if ( v22 )
              {
                v23 = v22 - 1;
                if ( v23 )
                {
                  if ( v23 != 1 || v20 <= 0x400u )
                    goto LABEL_271;
                  if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
                    *v5 = 2;
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v24) = 2;
                    WPP_RECORDER_SF_dD(
                      a5,
                      v24,
                      5,
                      56,
                      (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                      *((_WORD *)a1 + 2),
                      v13);
                  }
                  v25 = 110;
                }
                else
                {
                  if ( (v19 & 0xFFFFFFFC) != 0 )
                  {
                    if ( *(_BYTE *)(a2 + 15) )
                      *v5 = 2;
                    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v19) = 2;
                      WPP_RECORDER_SF_dD(
                        a5,
                        v19,
                        5,
                        52,
                        (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                        a1[3],
                        v13);
                    }
                    (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 108);
                  }
                  if ( (v20 & 0x7FFu) > 0x400 )
                  {
                    if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
                      *v5 = 2;
                    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v26) = 2;
                      WPP_RECORDER_SF_dD(
                        a5,
                        v26,
                        5,
                        53,
                        (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                        *((_WORD *)a1 + 2),
                        v13);
                    }
                    (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 110);
                  }
                  if ( v20 >= 0x2000u )
                  {
                    if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
                      *v5 = 2;
                    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v27) = 2;
                      WPP_RECORDER_SF_dD(
                        a5,
                        v27,
                        5,
                        54,
                        (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                        *((_WORD *)a1 + 2),
                        v13);
                    }
                    (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 110);
                  }
                  if ( (v20 & 0x1800) != 0x1800 )
                    goto LABEL_271;
                  if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
                    *v5 = 2;
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v28) = 2;
                    WPP_RECORDER_SF_dD(
                      a5,
                      v28,
                      5,
                      55,
                      (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                      *((_WORD *)a1 + 2),
                      v13);
                  }
                  v25 = 110;
                }
                goto LABEL_270;
              }
              if ( (v19 & 0xFFFFFFFC) != 0 )
              {
                if ( *(_BYTE *)(a2 + 15) )
                  *v5 = 2;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v19) = 2;
                  WPP_RECORDER_SF_dD(
                    a5,
                    v19,
                    5,
                    49,
                    (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                    a1[3],
                    v13);
                }
                (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 108);
              }
              if ( *((_WORD *)a1 + 2) > 0x40u )
              {
                *v5 = 2;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v19) = 2;
                  WPP_RECORDER_SF_dD(
                    a5,
                    v19,
                    5,
                    50,
                    (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                    *((_WORD *)a1 + 2),
                    v13);
                }
                (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 110);
              }
              if ( a1[6] )
                goto LABEL_271;
              if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
                *v5 = 2;
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_118;
              v30 = 51;
            }
            else
            {
              if ( (v19 & 0xFFFFFFFC) != 0 )
              {
                if ( *(_BYTE *)(a2 + 15) )
                  *v5 = 2;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v19) = 2;
                  WPP_RECORDER_SF_dD(
                    a5,
                    v19,
                    5,
                    45,
                    (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                    a1[3],
                    v13);
                }
                (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 108);
              }
              if ( *((_WORD *)a1 + 2) > 8u )
              {
                *v5 = 2;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v19) = 2;
                  WPP_RECORDER_SF_dD(
                    a5,
                    v19,
                    5,
                    46,
                    (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                    *((_WORD *)a1 + 2),
                    v13);
                }
                (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 110);
              }
              if ( !*((_WORD *)a1 + 2) )
              {
                *v5 = 2;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v19) = 2;
                  WPP_RECORDER_SF_dD(
                    a5,
                    v19,
                    5,
                    47,
                    (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                    *((_WORD *)a1 + 2),
                    v13);
                }
                (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 110);
              }
              if ( a1[6] )
                goto LABEL_271;
              if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
                *v5 = 2;
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_118;
              v30 = 48;
            }
            LOBYTE(v29) = 2;
            WPP_RECORDER_SF_dD(a5, v29, 5, v30, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, a1[6], v13);
LABEL_118:
            v25 = 109;
LABEL_270:
            (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), v25);
          }
LABEL_271:
          v36 = 512;
          goto LABEL_272;
        }
        if ( (v19 & 0xFFFFFFFC) != 0 )
        {
          if ( *(_BYTE *)(a2 + 15) )
            *v5 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v19) = 2;
            WPP_RECORDER_SF_dD(a5, v19, 5, 57, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, a1[3], v13);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 31);
        }
        v31 = *(_DWORD *)(a2 + 4);
        if ( !v31 )
        {
          *v5 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v57) = v13;
            LOBYTE(v19) = 2;
            WPP_RECORDER_SF_d(a5, v19, 5, 58, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v57);
          }
          v25 = 30;
          goto LABEL_270;
        }
        v32 = v31 - 1;
        if ( v32 )
        {
          v33 = v32 - 1;
          if ( v33 )
          {
            if ( v33 != 1 || *((_WORD *)a1 + 2) == 1024 )
              goto LABEL_271;
            if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
              *v5 = 2;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_154;
            v35 = 61;
          }
          else
          {
            v36 = 512;
            if ( *((_WORD *)a1 + 2) == 512 )
            {
LABEL_272:
              if ( _bittest64(*(const signed __int64 **)(a2 + 144), v59) )
              {
                if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
                  *v5 = 2;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v36) = 2;
                  WPP_RECORDER_SF_DDDD(
                    a5,
                    v36,
                    5,
                    72,
                    (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                    v59,
                    v13,
                    *(_BYTE *)(a2 + 80),
                    *(_BYTE *)(a2 + 81));
                }
                (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 102);
              }
              RtlSetBit((PRTL_BITMAP)(a2 + 136), v59);
              v56 = *(_DWORD *)(a2 + 256);
              ++*(_BYTE *)(a2 + 185);
              *(_QWORD *)(a2 + 192) = a1;
              *(_DWORD *)(a2 + 256) = v56 & 0xFFFFFFDB | 4;
LABEL_33:
              if ( !*v5 )
                return v16;
              goto LABEL_34;
            }
            if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
              *v5 = 2;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_154;
            v35 = 60;
          }
        }
        else
        {
          v37 = *((unsigned __int16 *)a1 + 2);
          LOWORD(v37) = v37 - 8;
          if ( (unsigned __int16)v37 <= 0x38u )
          {
            v38 = 0x100000001000101LL;
            if ( _bittest64(&v38, v37) )
              goto LABEL_271;
          }
          if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
            *v5 = 2;
          if ( !*((_WORD *)a1 + 2) )
            *v5 = 2;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_154;
          v35 = 59;
        }
        LOBYTE(v34) = 2;
        WPP_RECORDER_SF_dD(
          a5,
          v34,
          5,
          v35,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *((_WORD *)a1 + 2),
          v13);
LABEL_154:
        v25 = 32;
        goto LABEL_270;
      }
      if ( !*(_BYTE *)(a2 + 81) && v20 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v19) = 3;
          WPP_RECORDER_SF_dD(
            a5,
            v19,
            5,
            62,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            v13,
            *((_WORD *)a1 + 2));
        }
        (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 233);
      }
      v39 = *(_DWORD *)(a2 + 4);
      if ( !v39 )
      {
        *v5 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v57) = v13;
          LOBYTE(v19) = 2;
          WPP_RECORDER_SF_d(a5, v19, 5, 63, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v57);
        }
        v25 = 111;
        goto LABEL_270;
      }
      v40 = v39 - 1;
      if ( v40 )
      {
        v41 = (unsigned int)(v40 - 1);
        if ( (_DWORD)v41 )
        {
          if ( (_DWORD)v41 != 1 )
            goto LABEL_271;
          if ( *((_WORD *)a1 + 2) > 0x400u )
          {
            if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
              *v5 = 2;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v42) = 2;
              WPP_RECORDER_SF_dD(
                a5,
                v42,
                5,
                70,
                (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                *((_WORD *)a1 + 2),
                v13);
            }
            (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 113);
          }
          if ( (unsigned __int8)(a1[6] - 1) <= 0xFu )
            goto LABEL_271;
          if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
            *v5 = 2;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_192;
          v44 = 71;
        }
        else
        {
          if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline(v41, v19) )
            *(_DWORD *)(a2 + 256) &= ~0x10u;
          if ( (v20 & 0x7FFu) <= 0x400 )
          {
            if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline(1024, v45) && (v20 & 0x7FF) == 0 )
              *(_DWORD *)(a2 + 256) |= 0x10u;
          }
          else
          {
            if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
              *v5 = 2;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v46) = 2;
              WPP_RECORDER_SF_dD(
                a5,
                v46,
                5,
                66,
                (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                *((_WORD *)a1 + 2),
                v13);
            }
            (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 113);
          }
          if ( v20 >= 0x2000u )
          {
            if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
              *v5 = 2;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v47) = 2;
              WPP_RECORDER_SF_dD(
                a5,
                v47,
                5,
                67,
                (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                *((_WORD *)a1 + 2),
                v13);
            }
            (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 113);
          }
          if ( (v20 & 0x1800) == 0x1800 )
          {
            if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
              *v5 = 2;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v48) = 2;
              WPP_RECORDER_SF_dD(
                a5,
                v48,
                5,
                68,
                (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                *((_WORD *)a1 + 2),
                v13);
            }
            (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 113);
          }
          if ( (unsigned __int8)(a1[6] - 1) <= 0xFu )
            goto LABEL_271;
          if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
            *v5 = 2;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_192;
          v44 = 69;
        }
      }
      else
      {
        if ( *((_WORD *)a1 + 2) > 0x3FFu )
        {
          *v5 = 2;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v19) = 2;
            WPP_RECORDER_SF_dD(
              a5,
              v19,
              5,
              64,
              (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
              *((_WORD *)a1 + 2),
              v13);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 113);
        }
        if ( (unsigned __int8)(a1[6] - 1) <= 0xFu )
          goto LABEL_271;
        if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
          *v5 = 2;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_192;
        v44 = 65;
      }
      LOBYTE(v43) = 2;
      WPP_RECORDER_SF_dD(a5, v43, 5, v44, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, a1[6], v13);
LABEL_192:
      v25 = 112;
      goto LABEL_270;
    }
    if ( (v19 & 0xFFFFFFFC) != 0 )
    {
      if ( *(_BYTE *)(a2 + 15) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 2;
        WPP_RECORDER_SF_dD(a5, v19, 5, 40, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, a1[3], v13);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 67);
    }
    v49 = *(_DWORD *)(a2 + 4);
    if ( v49 )
    {
      v50 = v49 - 1;
      if ( !v50 )
      {
        v54 = *((unsigned __int16 *)a1 + 2);
        LOWORD(v54) = v54 - 8;
        if ( (unsigned __int16)v54 <= 0x38u )
        {
          v55 = 0x100000001000101LL;
          if ( _bittest64(&v55, v54) )
            goto LABEL_271;
        }
        if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
          *v5 = 2;
        if ( !*((_WORD *)a1 + 2) )
          *v5 = 2;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_269;
        v53 = 42;
        goto LABEL_268;
      }
      v51 = v50 - 1;
      if ( v51 )
      {
        v36 = 512;
        if ( v51 != 1 || *((_WORD *)a1 + 2) == 512 )
          goto LABEL_272;
        if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
          *v5 = 2;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_269;
        v53 = 44;
        goto LABEL_268;
      }
      if ( *((_WORD *)a1 + 2) == 64 )
        goto LABEL_271;
      if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v53 = 43;
LABEL_268:
        LOBYTE(v52) = 2;
        WPP_RECORDER_SF_dD(
          a5,
          v52,
          5,
          v53,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *((_WORD *)a1 + 2),
          v13);
      }
    }
    else
    {
      if ( *((_WORD *)a1 + 2) == 8 )
        goto LABEL_271;
      if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a2) )
        *v5 = 2;
      if ( (unsigned __int16)(*((_WORD *)a1 + 2) - 1) > 7u )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v53 = 41;
        goto LABEL_268;
      }
    }
LABEL_269:
    v25 = 68;
    goto LABEL_270;
  }
  v16 = 1;
  *v5 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_DDD(a5, (_DWORD)v12, v11, 32, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a1, v13, 7);
    goto LABEL_33;
  }
LABEL_34:
  v16 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_(a5, (_DWORD)v12, 5, 73, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v16;
}

```

## disassembly

```asm
0x140036c84  push    rbx
0x140036c86  push    rbp
0x140036c87  push    rsi
0x140036c88  push    rdi
0x140036c89  push    r12
0x140036c8b  push    r13
0x140036c8d  push    r14
0x140036c8f  push    r15
0x140036c91  sub     rsp, 68h
0x140036c95  xor     eax, eax
0x140036c97  mov     rsi, r9
0x140036c9a  mov     [rsp+0A8h+var_58], eax
0x140036c9e  mov     r14, r8
0x140036ca1  mov     rbx, rdx
0x140036ca4  mov     rdi, rcx
0x140036ca7  test    r9, r9
0x140036caa  jnz     short loc_140036CB3
0x140036cac  lea     rsi, [rsp+0A8h+var_58]
0x140036cb1  jmp     short loc_140036CBB
0x140036cb3  cmp     [rdx+30h], al
0x140036cb6  jz      short loc_140036CBB
0x140036cb8  mov     [r9], eax
0x140036cbb  movzx   eax, byte ptr [rcx]
0x140036cbe  mov     rcx, rbx
0x140036cc1  mov     r15d, [rdx+38h]
0x140036cc5  mov     ebp, [rdx+48h]
0x140036cc8  mov     rdx, rsi
0x140036ccb  mov     r13, [rsp+0A8h+arg_20]
0x140036cd3  mov     [r8], eax
0x140036cd6  mov     r8, r13
0x140036cd9  call    HUBDESC_InternalValidateLastEndpoint
0x140036cde  cmp     dword ptr [rsi], 1
0x140036ce1  lea     rdx, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036ce8  lea     rcx, WPP_RECORDER_INITIALIZED
0x140036cef  jz      loc_140036EB6
0x140036cf5  mov     r12d, edi
0x140036cf8  sub     r12d, r15d
0x140036cfb  mov     r15d, 7
0x140036d01  sub     ebp, r12d
0x140036d04  cmp     [rdi], r15b
0x140036d07  jnb     loc_140036DFD
0x140036d0d  mov     rax, [rbx+18h]
0x140036d11  lea     edx, [r15+4Ah]
0x140036d15  mov     rcx, [rbx+28h]
0x140036d19  call    _guard_dispatch_icall
0x140036d1e  cmp     ebp, r15d
0x140036d21  jb      short loc_140036D2B
0x140036d23  mov     [r14], r15d
0x140036d26  mov     ecx, r15d
0x140036d29  jmp     short loc_140036D2E
0x140036d2b  mov     ecx, [r14]
0x140036d2e  mov     eax, 200h
0x140036d33  cmp     [rbx], ax
0x140036d36  ja      short loc_140036D46
0x140036d38  xor     eax, eax
0x140036d3a  cmp     [rbx+0Ch], al
0x140036d3d  jnz     short loc_140036D48
0x140036d3f  cmp     [rbx+0Dh], al
0x140036d42  jz      short loc_140036D4E
0x140036d44  jmp     short loc_140036D48
0x140036d46  xor     eax, eax
0x140036d48  mov     dword ptr [rsi], 2
0x140036d4e  cmp     ecx, r15d
0x140036d51  jnb     short loc_140036DAA
0x140036d53  mov     r15d, 1
0x140036d59  mov     [rsi], r15d
0x140036d5c  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140036d63  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140036d6a  jz      loc_140036EC2
0x140036d70  movzx   eax, byte ptr [rdi]
0x140036d73  lea     r9d, [r15+1Fh]
0x140036d77  mov     [rsp+0A8h+var_70], 7
0x140036d7f  mov     dl, 2
0x140036d81  mov     [rsp+0A8h+var_78], r12d
0x140036d86  mov     rcx, r13
0x140036d89  mov     dword ptr [rsp+0A8h+var_80], eax
0x140036d8d  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036d94  mov     [rsp+0A8h+var_88], rax
0x140036d99  call    WPP_RECORDER_SF_DDD
0x140036d9e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140036da5  jmp     loc_140036EBC
0x140036daa  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140036db1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140036db8  jz      short loc_140036DEF
0x140036dba  movzx   eax, byte ptr [rdi]
0x140036dbd  mov     r9d, 21h ; '!'
0x140036dc3  mov     [rsp+0A8h+var_68], ecx
0x140036dc7  mov     dl, 2
0x140036dc9  mov     [rsp+0A8h+var_70], r15d
0x140036dce  mov     rcx, r13
0x140036dd1  mov     [rsp+0A8h+var_78], r12d
0x140036dd6  mov     dword ptr [rsp+0A8h+var_80], eax
0x140036dda  lea     r8d, [r9-1Ch]
0x140036dde  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036de5  mov     [rsp+0A8h+var_88], rax
0x140036dea  call    WPP_RECORDER_SF_DDDD
0x140036def  lea     rdx, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036df6  lea     rcx, WPP_RECORDER_INITIALIZED
0x140036dfd  movzx   eax, byte ptr [rdi]
0x140036e00  cmp     al, r15b
0x140036e03  jbe     short loc_140036E43
0x140036e05  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x140036e0c  jz      short loc_140036E31
0x140036e0e  mov     [rsp+0A8h+var_70], r15d
0x140036e13  mov     r9d, 22h ; '"'
0x140036e19  mov     [rsp+0A8h+var_78], r12d
0x140036e1e  mov     rcx, r13
0x140036e21  mov     dword ptr [rsp+0A8h+var_80], eax
0x140036e25  mov     [rsp+0A8h+var_88], rdx
0x140036e2a  mov     dl, 3
0x140036e2c  call    WPP_RECORDER_SF_DDD
0x140036e31  mov     rax, [rbx+20h]
0x140036e35  mov     edx, 50h ; 'P'
0x140036e3a  mov     rcx, [rbx+28h]
0x140036e3e  call    _guard_dispatch_icall
0x140036e43  cmp     [r14], ebp
0x140036e46  jbe     loc_140036F03
0x140036e4c  mov     eax, 200h
0x140036e51  cmp     [rbx], ax
0x140036e54  ja      short loc_140036E62
0x140036e56  xor     eax, eax
0x140036e58  cmp     [rbx+0Ch], al
0x140036e5b  jnz     short loc_140036E62
0x140036e5d  cmp     [rbx+0Dh], al
0x140036e60  jz      short loc_140036E68
0x140036e62  mov     dword ptr [rsi], 2
0x140036e68  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140036e6f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140036e76  jz      short loc_140036E9D
0x140036e78  mov     r9d, 23h ; '#'
0x140036e7e  mov     dword ptr [rsp+0A8h+var_80], r12d
0x140036e83  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036e8a  mov     dl, 2
0x140036e8c  mov     rcx, r13
0x140036e8f  mov     [rsp+0A8h+var_88], rax
0x140036e94  lea     r8d, [r9-1Eh]
0x140036e98  call    WPP_RECORDER_SF_d
0x140036e9d  mov     rax, [rbx+18h]
0x140036ea1  mov     edx, 53h ; 'S'
0x140036ea6  mov     rcx, [rbx+28h]
0x140036eaa  call    _guard_dispatch_icall
0x140036eaf  lea     rcx, WPP_RECORDER_INITIALIZED
0x140036eb6  mov     r15d, 1
0x140036ebc  xor     eax, eax
0x140036ebe  cmp     [rsi], eax
0x140036ec0  jz      short loc_140036EEE
0x140036ec2  mov     r15b, al
0x140036ec5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x140036ecc  jz      short loc_140036EEE
0x140036ece  mov     r9d, 49h ; 'I'
0x140036ed4  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036edb  mov     dl, 2
0x140036edd  mov     [rsp+0A8h+var_88], rax
0x140036ee2  mov     rcx, r13
0x140036ee5  lea     r8d, [r9-44h]
0x140036ee9  call    WPP_RECORDER_SF_
0x140036eee  mov     al, r15b
0x140036ef1  add     rsp, 68h
0x140036ef5  pop     r15
0x140036ef7  pop     r14
0x140036ef9  pop     r13
0x140036efb  pop     r12
0x140036efd  pop     rdi
0x140036efe  pop     rsi
0x140036eff  pop     rbp
0x140036f00  pop     rbx
0x140036f01  retn
0x140036f03  mov     eax, [rbx+100h]
0x140036f09  mov     r15d, 1
0x140036f0f  test    r15b, al
0x140036f12  jnz     short loc_140036F7C
0x140036f14  mov     eax, 200h
0x140036f19  cmp     [rbx], ax
0x140036f1c  ja      short loc_140036F2A
0x140036f1e  xor     eax, eax
0x140036f20  cmp     [rbx+0Ch], al
0x140036f23  jnz     short loc_140036F2A
0x140036f25  cmp     [rbx+0Dh], al
0x140036f28  jz      short loc_140036F30
0x140036f2a  mov     dword ptr [rsi], 2
0x140036f30  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140036f37  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140036f3e  jz      short loc_140036F65
0x140036f40  mov     r9d, 24h ; '$'
0x140036f46  mov     dword ptr [rsp+0A8h+var_80], r12d
0x140036f4b  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036f52  mov     dl, 2
0x140036f54  mov     rcx, r13
0x140036f57  mov     [rsp+0A8h+var_88], rax
0x140036f5c  lea     r8d, [r9-1Fh]
0x140036f60  call    WPP_RECORDER_SF_d
0x140036f65  mov     rax, [rbx+18h]
0x140036f69  mov     edx, 55h ; 'U'
0x140036f6e  mov     rcx, [rbx+28h]
0x140036f72  call    _guard_dispatch_icall
0x140036f77  jmp     loc_140036D9E
0x140036f7c  mov     al, [rdi+2]
0x140036f7f  mov     [rsp+0A8h+arg_0], al
0x140036f86  test    al, 0Fh
0x140036f88  jnz     short loc_140036FE9
0x140036f8a  mov     eax, 200h
0x140036f8f  cmp     [rbx], ax
0x140036f92  ja      short loc_140036F9A
0x140036f94  cmp     byte ptr [rbx+0Ch], 0
0x140036f98  jz      short loc_140036FA0
0x140036f9a  mov     dword ptr [rsi], 2
0x140036fa0  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140036fa7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140036fae  jz      short loc_140036FD5
0x140036fb0  mov     r9d, 25h ; '%'
0x140036fb6  mov     dword ptr [rsp+0A8h+var_80], r12d
0x140036fbb  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140036fc2  mov     dl, 2
0x140036fc4  mov     rcx, r13
0x140036fc7  mov     [rsp+0A8h+var_88], rax
0x140036fcc  lea     r8d, [r9-20h]
0x140036fd0  call    WPP_RECORDER_SF_d
0x140036fd5  mov     rax, [rbx+18h]
0x140036fd9  mov     edx, 56h ; 'V'
0x140036fde  mov     rcx, [rbx+28h]
0x140036fe2  call    _guard_dispatch_icall
0x140036fe7  jmp     short loc_140036FF0
0x140036fe9  lea     r14, WPP_RECORDER_INITIALIZED
0x140036ff0  test    byte ptr [rdi+2], 70h
0x140036ff4  jz      short loc_140037054
0x140036ff6  mov     rcx, rbx
0x140036ff9  call    HUBDESC_ShouldEnforceWin8ValidationMutable
0x140036ffe  xor     ebp, ebp
0x140037000  test    al, al
0x140037002  jz      short loc_14003700A
0x140037004  mov     dword ptr [rsi], 2
0x14003700a  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140037011  jz      short loc_140037040
0x140037013  movzx   eax, byte ptr [rdi+2]
0x140037017  mov     r9d, 26h ; '&'
0x14003701d  mov     [rsp+0A8h+var_78], eax
0x140037021  mov     dl, 2
0x140037023  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003702a  mov     dword ptr [rsp+0A8h+var_80], r12d
0x14003702f  mov     rcx, r13
0x140037032  mov     [rsp+0A8h+var_88], rax
0x140037037  lea     r8d, [r9-21h]
0x14003703b  call    WPP_RECORDER_SF_dD
0x140037040  mov     rax, [rbx+18h]
0x140037044  mov     edx, 54h ; 'T'
0x140037049  mov     rcx, [rbx+28h]
0x14003704d  call    _guard_dispatch_icall
0x140037052  jmp     short loc_140037056
0x140037054  xor     ebp, ebp
0x140037056  test    byte ptr [rdi+3], 0C0h
0x14003705a  jz      short loc_1400370B0
0x14003705c  cmp     [rbx+0Fh], bpl
0x140037060  jz      short loc_140037068
0x140037062  mov     dword ptr [rsi], 2
0x140037068  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14003706f  jz      short loc_14003709E
0x140037071  movzx   eax, byte ptr [rdi+3]
0x140037075  mov     r9d, 27h ; '''
0x14003707b  mov     [rsp+0A8h+var_78], r12d
0x140037080  mov     dl, 2
0x140037082  mov     dword ptr [rsp+0A8h+var_80], eax
0x140037086  mov     rcx, r13
0x140037089  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140037090  lea     r8d, [r9-22h]
0x140037094  mov     [rsp+0A8h+var_88], rax
0x140037099  call    WPP_RECORDER_SF_dD
0x14003709e  mov     rax, [rbx+18h]
0x1400370a2  mov     edx, 52h ; 'R'
0x1400370a7  mov     rcx, [rbx+28h]
0x1400370ab  call    _guard_dispatch_icall
0x1400370b0  movzx   edx, byte ptr [rdi+3]
0x1400370b4  movzx   r14d, word ptr [rdi+4]
0x1400370b9  mov     ecx, edx
0x1400370bb  and     ecx, 3
0x1400370be  jz      loc_140037B3C
0x1400370c4  sub     ecx, r15d
0x1400370c7  jz      loc_14003774D
0x1400370cd  sub     ecx, r15d
0x1400370d0  jz      loc_140037590
0x1400370d6  cmp     ecx, r15d
0x1400370d9  jnz     loc_140037D0C
0x1400370df  mov     ecx, [rbx+4]
0x1400370e2  test    ecx, ecx
0x1400370e4  jz      loc_14003743A
0x1400370ea  sub     ecx, r15d
0x1400370ed  jz      loc_140037317
0x1400370f3  sub     ecx, r15d
0x1400370f6  jz      short loc_140037169
0x1400370f8  cmp     ecx, r15d
0x1400370fb  jnz     loc_140037D0C
0x140037101  mov     ecx, 400h
0x140037106  cmp     r14w, cx
0x14003710a  jbe     loc_140037D0C
0x140037110  mov     rcx, rbx
0x140037113  call    HUBDESC_ShouldEnforceWin8ValidationMutable
0x140037118  test    al, al
0x14003711a  jz      short loc_140037122
0x14003711c  mov     dword ptr [rsi], 2
0x140037122  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140037129  cmp     cs:WPP_RECORDER_INITIALIZED, rax
  ... truncated ...
```
