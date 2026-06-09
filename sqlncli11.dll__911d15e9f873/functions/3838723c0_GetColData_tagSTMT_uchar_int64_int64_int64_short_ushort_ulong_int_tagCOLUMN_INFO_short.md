# GetColData(tagSTMT *,uchar *,__int64,__int64 *,__int64 *,short,ushort,ulong,int,tagCOLUMN_INFO *,short)

- ea: `0x3838723c0`
- end: `0x3838724ad`
- name: `?GetColData@@YAFPEAUtagSTMT@@PEAE_JPEA_J3FGKHPEAUtagCOLUMN_INFO@@F@Z`
- size: `237`
- prototype: `__int16 __usercall@<ax>(struct tagSTMT *@<rcx>, unsigned __int8 *@<rdx>, __int64@<r8>, __int64 *@<r9>, __int64 *, __int16, unsigned __int16, unsigned int, int, struct tagCOLUMN_INFO *, __int16)`
- caller_count: `6`
- callee_count: `17`
- tags: ``

## callers

- `0x3838727a0`
- `0x38395ee50`
- `0x383960e00`
- `0x383961460`
- `0x383965820`
- `0x383974c60`

## callees

- `0x3838427d0`
- `0x3838434c0`
- `0x3838455b0`
- `0x3838457b0`
- `0x3838723c0`
- `0x3838724c0`
- `0x383872fe0`
- `0x38389a4e0`
- `0x3838b96d0`
- `0x38391aed0`
- `0x38391afe0`
- `0x3839609c0`
- `0x383960b30`
- `0x383961cd0`
- `0x383964b80`
- `0x38398b610`
- `0x383acdff0`

## import_xrefs

- `MSVCR100!memmove` at `0x3838cf3a2`
- `MSVCR100!memmove` at `0x3838cf3a2`
- `KERNEL32!IsDBCSLeadByteEx` at `0x3838cf5f6`
- `KERNEL32!IsDBCSLeadByteEx` at `0x3838cf5f6`

## pseudocode

```c
__int64 __fastcall GetColData(
        struct tagSTMT *a1,
        unsigned __int8 *a2,
        size_t a3,
        __int64 *a4,
        __int64 *a5,
        __int16 a6,
        unsigned __int16 a7,
        unsigned int a8,
        int a9,
        struct tagCOLUMN_INFO *a10)
{
  __int64 v11; // r15
  BATCHCTX *v12; // rcx
  unsigned __int16 v14; // r12
  struct tagCOLUMN_INFO *ColInfoByOrdinal; // rax
  unsigned __int16 v16; // dx
  struct tagCOLUMN_INFO *v17; // rcx
  bool v18; // zf
  __int16 v19; // r14
  __int16 v20; // si
  BATCHCTX *v21; // r15
  unsigned __int16 v22; // r8
  size_t v23; // rdi
  unsigned int DataLen; // eax
  int v25; // ecx
  struct tagCOLUMN_INFO *v26; // rdx
  unsigned __int64 v27; // r15
  size_t v28; // rbx
  struct tagDBC *v29; // rbx
  unsigned int v30; // edi
  unsigned __int64 v31; // r9
  unsigned int Data; // eax
  unsigned __int64 v33; // rax
  unsigned __int8 *v34; // rbx
  unsigned __int8 *v35; // rbx
  _QWORD *v36; // r8
  int v37; // eax
  __int16 v38; // bx
  char v40; // cl
  unsigned int VariantBaseTypeInfo; // eax
  __int64 v42; // rdx
  __int16 v43; // ax
  __int64 v44; // rax
  char *v45; // rax
  size_t v46; // r8
  unsigned __int64 v47; // rax
  unsigned int v48; // eax
  unsigned __int64 v49; // rdi
  unsigned __int64 v50; // rcx
  char v51; // al
  unsigned __int64 v52; // rax
  BOOL v53; // eax
  const unsigned __int8 *v54; // rdx
  int v55; // ecx
  int v56; // eax
  __int16 v57; // ax
  __int16 v58; // bx
  __int64 v59; // rdx
  size_t v60; // rcx
  int v61; // ecx
  int v62; // eax
  __int16 v63; // ax
  __int64 v64; // rdx
  size_t v65; // r12
  size_t v66; // r8
  unsigned int v67; // r9d
  struct tagCOLUMN_INFO *v68; // rsi
  __int64 v69; // rax
  unsigned __int64 v70; // rax
  unsigned __int64 v71; // kr10_8
  unsigned __int64 v72; // rcx
  unsigned __int16 v73; // di
  struct tagDBC *v74; // rdi
  unsigned __int16 v75; // di
  int v76; // eax
  __int64 v77; // rdx
  int v78; // [rsp+38h] [rbp-D0h]
  int v79; // [rsp+38h] [rbp-D0h]
  int v80; // [rsp+40h] [rbp-C8h]
  int v81; // [rsp+40h] [rbp-C8h]
  int *v82; // [rsp+60h] [rbp-A8h]
  int v83; // [rsp+78h] [rbp-90h]
  unsigned __int8 v84; // [rsp+7Ch] [rbp-8Ch] BYREF
  struct tagCOLUMN_INFO *v85; // [rsp+80h] [rbp-88h]
  unsigned __int16 v86[4]; // [rsp+88h] [rbp-80h]
  size_t Size; // [rsp+90h] [rbp-78h]
  struct tagDBC *v88; // [rsp+98h] [rbp-70h]
  unsigned __int16 v89; // [rsp+A0h] [rbp-68h]
  void *v90; // [rsp+A8h] [rbp-60h]
  BATCHCTX *v91; // [rsp+B0h] [rbp-58h]
  unsigned __int64 v92; // [rsp+B8h] [rbp-50h] BYREF
  __int64 *v93; // [rsp+C0h] [rbp-48h]
  unsigned __int64 v94; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int64 v95; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int64 v96; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int8 *v97; // [rsp+E0h] [rbp-28h] BYREF
  int v98; // [rsp+E8h] [rbp-20h] BYREF
  int v99; // [rsp+ECh] [rbp-1Ch]
  signed __int64 v100; // [rsp+F0h] [rbp-18h]
  int v101; // [rsp+F8h] [rbp-10h] BYREF
  int v102; // [rsp+FCh] [rbp-Ch]
  unsigned __int64 v103; // [rsp+100h] [rbp-8h]
  unsigned __int64 v104; // [rsp+108h] [rbp+0h] BYREF
  struct tagCOLUMN_INFO *v105; // [rsp+110h] [rbp+8h]
  unsigned __int8 *v106; // [rsp+118h] [rbp+10h] BYREF
  struct BaseMetaInfo *v107; // [rsp+120h] [rbp+18h]
  unsigned __int8 *v108; // [rsp+128h] [rbp+20h] BYREF
  unsigned __int64 v109; // [rsp+130h] [rbp+28h] BYREF
  _BYTE Src[2496]; // [rsp+138h] [rbp+30h] BYREF

  v11 = *((_QWORD *)a1 + 14);
  v12 = (BATCHCTX *)*((_QWORD *)a1 + 139);
  v90 = a2;
  v97 = a2;
  v91 = v12;
  LODWORD(v12) = *(_DWORD *)(v11 + 9024);
  v93 = a4;
  v100 = a3;
  *(_DWORD *)v86 = a7;
  v105 = a10;
  v102 = (int)v12;
  v14 = 0;
  v88 = (struct tagDBC *)v11;
  Size = a3;
  v96 = 0;
  v92 = 0;
  v103 = 0;
  v94 = 0;
  v98 = 0;
  v99 = 0;
  if ( a10 )
  {
    v89 = a7;
    v16 = 1;
    v17 = a10;
    *(_DWORD *)v86 = 1;
  }
  else
  {
    ColInfoByOrdinal = IRDTag::GetColInfoByOrdinal((struct tagSTMT *)((char *)a1 + 56), a7);
    v16 = v86[0];
    v17 = ColInfoByOrdinal;
  }
  v18 = *((_WORD *)v17 + 8) == 13;
  v85 = v17;
  if ( v18 )
  {
    VariantBaseTypeInfo = GetVariantBaseTypeInfo(a1, v16, a8, v17);
    v25 = VariantBaseTypeInfo;
    v83 = VariantBaseTypeInfo;
    if ( VariantBaseTypeInfo )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v42 = 1607689;
        goto LABEL_58;
      }
LABEL_59:
      v21 = v91;
      goto LABEL_38;
    }
    v17 = v85;
  }
  v19 = a6;
  v20 = *((_WORD *)v17 + 54);
  if ( a6 == 99 )
  {
    v43 = *((_WORD *)v17 + 8);
    if ( (*(_BYTE *)(v11 + 10112) & 0x24) != 0 )
      v19 = word_383911D96[v43];
    else
      v19 = word_383911DD6[v43];
    v17 = v85;
  }
  if ( v19 && (*((_DWORD *)a1 + 372) & 0x40000) == 0 )
  {
    v21 = v91;
    v22 = v86[0];
    if ( v86[0] == *((_WORD *)v91 + 72) )
    {
      v44 = *((_QWORD *)a1 + 26);
      v90 = &a2[v44];
      v97 = &a2[v44];
      v100 -= v44;
      v23 = v100;
      Size = v100;
    }
    else
    {
      v23 = Size;
      *((_QWORD *)a1 + 285) = 0;
      *((_QWORD *)a1 + 27) = 0;
      *((_QWORD *)a1 + 26) = 0;
    }
    v107 = (struct tagCOLUMN_INFO *)((char *)v17 + 64);
    DataLen = BATCHCTX::GetDataLen(v21, a1, v22, (struct tagCOLUMN_INFO *)((char *)v17 + 64), a8, &v92, &v101);
    v25 = DataLen;
    v83 = DataLen;
    if ( DataLen )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        bidTraceHR(off_383B43208[0], 1654793, DataLen);
LABEL_68:
        v25 = v83;
      }
LABEL_38:
      v30 = a8;
LABEL_39:
      v36 = v93;
      goto LABEL_40;
    }
    if ( v101 )
    {
      if ( a5 )
      {
        v30 = a8;
        *a5 = -1;
        goto LABEL_39;
      }
      v29 = v88;
      v14 = -25413;
      v94 = v103;
      v83 = -2147467259;
      goto LABEL_211;
    }
    v26 = v85;
    v27 = v92;
    v18 = *((_WORD *)v85 + 8) == 13;
    v103 = v92;
    if ( v18 && v19 == -2 )
    {
      if ( !v100 )
      {
        v29 = v88;
        v14 = -25126;
        v94 = v92;
LABEL_211:
        v68 = v85;
        goto LABEL_212;
      }
    }
    else if ( v19 == -8 )
    {
      v23 &= ~1uLL;
      Size = v23;
      if ( v23 )
      {
        v23 -= 2LL;
        Size = v23;
      }
      else
      {
        v14 = -25126;
      }
    }
    else if ( v19 == 1 )
    {
      if ( v23 )
        Size = --v23;
      else
        v14 = -25126;
      v28 = *((_QWORD *)a1 + 285);
      if ( v28 )
      {
        if ( v23 < v28 )
          v28 = v23;
        if ( v28 )
        {
          memcpy(v90, (char *)a1 + 2288, v28);
          v45 = (char *)v90;
          *((_QWORD *)a1 + 285) -= v28;
          v46 = *((_QWORD *)a1 + 285);
          Size -= v28;
          *((_QWORD *)a1 + 26) += v28;
          v90 = &v45[v28];
          v97 = (unsigned __int8 *)&v45[v28];
          if ( v46 )
            memmove((char *)a1 + 2288, (char *)a1 + v28 + 2288, v46);
          v26 = v85;
          v23 = Size;
        }
        if ( !v23 )
        {
          v99 = 1;
          v14 = -25126;
          goto LABEL_33;
        }
      }
    }
    if ( *((_DWORD *)a1 + 376) )
    {
      v40 = *((_BYTE *)v26 + 64);
      if ( (v40 & 0x30) == 0x20 || v40 == -15 )
        *((_DWORD *)a1 + 376) = 0;
    }
    if ( !v27 )
    {
      if ( (v20 == -8 || v20 == 1) && (v19 == 9 || v19 == 10 || v19 == 11 || v19 == 0x4000 || v19 == 16385) )
        v14 = -25411;
      v35 = (unsigned __int8 *)v90;
LABEL_31:
      if ( v19 == -8 )
      {
        if ( v100 > 1 )
          *(_WORD *)v35 = 0;
LABEL_35:
        if ( !v14 )
        {
          if ( !v27 )
          {
            v25 = v83;
            v21 = v91;
            v94 = *((_QWORD *)a1 + 26);
            goto LABEL_38;
          }
          v14 = -25126;
        }
LABEL_188:
        v29 = v88;
LABEL_189:
        if ( !v99 )
        {
          v94 = v103;
          goto LABEL_211;
        }
        if ( v103 != -1 )
        {
          switch ( v19 )
          {
            case 1:
              if ( v20 == 1 )
              {
                v94 = v27 + *((_QWORD *)a1 + 26) + *((_QWORD *)a1 + 285);
                goto LABEL_211;
              }
              if ( v20 != -8 )
              {
                v18 = v20 == -2;
                v68 = v85;
                if ( !v18 )
                  goto LABEL_212;
                v69 = 2;
LABEL_198:
                v71 = v69;
                v70 = v103 * v69;
                v72 = -1;
                if ( is_mul_ok(v103, v71) )
                  v72 = v70;
                v94 = v72;
                goto LABEL_212;
              }
              break;
            case -8:
              if ( v20 != 1 )
              {
                v18 = v20 == -2;
                v68 = v85;
                if ( !v18 )
                  goto LABEL_212;
                v69 = 4;
                goto LABEL_198;
              }
              break;
            case -2:
              v18 = v20 == 2;
              v68 = v85;
              if ( v18 )
              {
                v94 = 19;
              }
              else if ( *((_WORD *)v85 + 8) == 15 )
              {
                v94 = v27 + *((_QWORD *)a1 + 26) - *((_QWORD *)a1 + 27) + 2LL;
              }
LABEL_212:
              if ( v105 )
              {
                if ( *((_DWORD *)v29 + 2530) && v98 )
                {
                  if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                    bidTraceW(off_383B43208[0], 2197513, off_383B49120[0], 2146);
                  v73 = v89;
                  PostSQLErrorEx(a1, 0x9DE3u, 0, *((_QWORD *)a1 + 93), v89);
                }
                else
                {
                  v73 = v89;
                }
                if ( v14 == 0x9DDD )
                {
                  v25 = v83;
                }
                else
                {
                  if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                    bidTraceW(off_383B43208[0], 2202633, off_383B49120[0], 2151);
                  PostSQLErrorEx(a1, v14, 0, *((_QWORD *)a1 + 93), v73);
                  if ( v14 == 0x9DDA || v14 == 0x9E0D )
                  {
                    v25 = 265937;
                    v83 = 265937;
                  }
                  else
                  {
                    v25 = -2147467259;
                    v83 = -2147467259;
                  }
                }
              }
              else
              {
                v74 = v88;
                if ( *((_DWORD *)v88 + 2530) && v98 )
                {
                  if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                    bidTraceW(off_383B43208[0], 2210825, off_383B49120[0], 2159);
                  PostSQLErrorEx(a1, 0x9DE3u, 0, *((_QWORD *)a1 + 29) + 1LL, v86[0]);
                }
                if ( !*((_QWORD *)v74 + 1006) || *((_WORD *)v68 + 8) != 13 || v19 != -2 || v100 || v14 != 0x9DDA )
                {
                  if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                    bidTraceW(off_383B43208[0], 2225161, off_383B49120[0], 2173);
                  v75 = v86[0];
                  PostSQLErrorEx(a1, v14, 0, *((_QWORD *)a1 + 29) + 1LL, v86[0]);
                  if ( v14 == 0x9DDA || v14 == 0x9DDD || v14 == 0x9E0D || v14 == 0x9DE3 )
                  {
                    v25 = 265937;
                    v83 = 265937;
                  }
                  else
                  {
                    v25 = -2147467259;
                    v83 = -2147467259;
                  }
                  goto LABEL_251;
                }
                v25 = 0;
                v83 = 0;
              }
              v75 = v86[0];
LABEL_251:
              v21 = v91;
              if ( !a9 || !*((_QWORD *)v91 + 14) && !*((_QWORD *)v91 + 15) )
                goto LABEL_38;
              if ( (unsigned int)BATCHCTX::FlushData(v91, a1, v75, v107, a8) )
              {
                if ( !v105 )
                  *((_DWORD *)a1 + 372) |= 0x40000u;
                v25 = -2147467259;
                goto LABEL_38;
              }
              goto LABEL_68;
            default:
              goto LABEL_211;
          }
        }
        v94 = -1;
        goto LABEL_211;
      }
      if ( v19 != 1 )
        goto LABEL_35;
LABEL_33:
      if ( v100 )
        *(_BYTE *)v90 = 0;
      goto LABEL_35;
    }
    v29 = v88;
    v99 = FIsConversionNeeded(v88, v26, v19, *((_DWORD *)v26 + 24));
    if ( !v99 )
    {
      if ( v19 == 1 || v19 == -8 || v19 == -2 )
      {
        if ( v20 != 1 && v20 != -8 && v20 != -2 && v23 < v27 )
        {
          v14 = -25412;
          v94 = v103;
          goto LABEL_211;
        }
        v27 = v23;
      }
      v30 = a8;
      v31 = v27;
      v21 = v91;
      Data = BATCHCTX::FetchData(v91, a1, &v97, v31, 1, a8, &v96, &v92);
      v25 = Data;
      v83 = Data;
      if ( Data )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          bidTraceHR(off_383B43208[0], 1809417, Data);
          v25 = v83;
        }
        goto LABEL_39;
      }
      v33 = v96;
      v34 = v97;
      v27 = v92;
      *((_QWORD *)a1 + 26) += v96;
      v35 = &v34[v33];
      v90 = v35;
      if ( v27 != -1 )
        v27 -= v33;
      goto LABEL_31;
    }
    v35 = (unsigned __int8 *)v90;
    while ( 1 )
    {
      v95 = 0;
      v47 = EstimateBytesToRead(a1, v85, v19, v23, v27);
      v21 = v91;
      v30 = a8;
      v108 = (unsigned __int8 *)a1 + 2288;
      v96 = 0;
      v48 = BATCHCTX::FetchData(v91, a1, &v108, v47, 1, a8, &v96, &v92);
      v25 = v48;
      v83 = v48;
      if ( v48 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          bidTraceHR(off_383B43208[0], 1846281, v48);
          v25 = v83;
        }
        goto LABEL_39;
      }
      v49 = v96;
      if ( !v96 && (*((_WORD *)v85 + 8) != 15 || v19 != -2) )
      {
        v27 = v92;
        goto LABEL_31;
      }
      if ( v20 != 1 && v20 != -8 || v19 != 1 && v19 != -8 )
      {
        v27 = v92;
        v50 = v92;
        if ( *((_QWORD *)a1 + 237) )
        {
          if ( v19 == 1 )
          {
            v19 = 98;
          }
          else if ( v19 == -8 )
          {
            v19 = 97;
          }
        }
        if ( v92 == -1
          || ((v51 = *((_BYTE *)v85 + 64), v51 == -15) || (v51 & 0xB1) == 0xA1 && *((_QWORD *)v85 + 9) == 0xFFFF)
          && v92 > 0x7FFFFFFF )
        {
          v50 = v96;
        }
        v14 = OdbcDataFromSqlData(v88, a1, v85, (char *)a1 + 2288, v96, v50, v35, v19, Size, &v94, &v95, (int)v82);
        if ( v14 == 0x9CDA )
        {
          v29 = v88;
          v67 = *((_DWORD *)v88 + 2250);
          if ( v67 == -1 )
            v67 = 120000;
          BATCHCTX::Cancel(v91, a1, 0, v67);
          *((_DWORD *)a1 + 502) = 0;
          v83 = -2147467259;
          goto LABEL_189;
        }
        if ( v19 != 1 && v19 != -8 && v19 != -2 && v27 > v49 )
        {
          if ( !v14 )
            v14 = -25126;
          a9 = 1;
          goto LABEL_188;
        }
        v52 = v95;
        goto LABEL_171;
      }
      v27 = v92;
      if ( v20 != 1 || v96 == v92 )
        goto LABEL_139;
      v53 = IsDBCSLeadByteEx(*((_DWORD *)v88 + 2256), *((_BYTE *)a1 + v96 + 2287));
      v54 = (const unsigned __int8 *)a1 + 2288;
      if ( !v53 )
        goto LABEL_140;
      if ( (unsigned int)IsDBCSCharAligned(*((_DWORD *)v88 + 2256), v54, v49) )
      {
LABEL_139:
        v54 = (const unsigned __int8 *)a1 + 2288;
      }
      else
      {
        v84 = 0;
        v106 = &v84;
        v104 = 0;
        VariantBaseTypeInfo = BATCHCTX::FetchData(v91, a1, &v106, 1u, 1, a8, &v104, &v109);
        v25 = VariantBaseTypeInfo;
        v83 = VariantBaseTypeInfo;
        if ( VariantBaseTypeInfo )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_59;
          v42 = 1901577;
LABEL_58:
          bidTraceHR(off_383B43208[0], v42, VariantBaseTypeInfo);
          v25 = v83;
          goto LABEL_59;
        }
        v54 = (const unsigned __int8 *)a1 + 2288;
        if ( v104 )
        {
          v54[v49++] = v84;
          v96 = v49;
        }
      }
LABEL_140:
      v95 = v49;
      v55 = 0;
      v56 = 0;
      if ( (_DWORD)v49 )
      {
        v55 = *((_DWORD *)v88 + 2256);
        if ( (*((_BYTE *)v88 + 10112) & 2) != 0 || v20 <= -8 || v19 == -8 )
          v56 = *((_DWORD *)v88 + 2514);
        else
          v56 = *((_DWORD *)v88 + 2256);
      }
      v82 = &v98;
      LOWORD(v80) = v19;
      LOWORD(v78) = v20;
      v57 = TranslateParam(v88, a1, v54, v35, &v95, Size, v78, v80, v55, v56, 1);
      v58 = v57;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( !v57 && (bidGblFlags & 0x40) == 0 )
        {
          v49 = v96;
          v27 = v92;
          v35 = v97;
          goto LABEL_156;
        }
        v59 = 1704961;
        if ( v57 )
          v59 = 1704993;
        bidTraceW(off_383B43220, v59, off_383B494E8[0], (unsigned int)v57);
        v49 = v96;
        v27 = v92;
        v90 = v97;
      }
      if ( v58 == -1 )
      {
        v83 = -2147467259;
        goto LABEL_188;
      }
      v18 = v58 == 1;
      v35 = (unsigned __int8 *)v90;
      if ( v18 )
      {
        v14 = -25126;
        v83 = 265937;
      }
LABEL_156:
      v52 = v95;
      v60 = Size;
      if ( v95 > Size )
      {
        v95 = v49;
        v61 = 0;
        v62 = 0;
        if ( (_DWORD)v49 )
        {
          v61 = *((_DWORD *)v88 + 2256);
          if ( (*((_BYTE *)v88 + 10112) & 2) != 0 || v20 <= -8 || v19 == -8 )
            v62 = *((_DWORD *)v88 + 2514);
          else
            v62 = *((_DWORD *)v88 + 2256);
        }
        LODWORD(v82) = 0;
        LOWORD(v81) = v19;
        LOWORD(v79) = v20;
        v63 = TranslateParam(v88, a1, (char *)a1 + 2288, Src, &v95, 2488, v79, v81, v61, v62, 1);
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( v63 || (bidGblFlags & 0x40) != 0 )
          {
            v64 = 1704961;
            if ( v63 )
              v64 = 1704993;
            bidTraceW(off_383B43220, v64, off_383B494E8[0], (unsigned int)v63);
          }
          v35 = v97;
          v27 = v92;
          v49 = v96;
        }
        v65 = Size;
        memcpy(v35, Src, Size);
        v66 = v95 - v65;
        *((_QWORD *)a1 + 285) = v95 - v65;
        memcpy((char *)a1 + 2288, &Src[v65], v66);
        v52 = v65;
        v95 = v65;
        v14 = -25126;
LABEL_171:
        v60 = Size;
      }
      v35 += v52;
      v90 = v35;
      v97 = v35;
      Size = v60 - v52;
      if ( v27 != -1 )
      {
        v27 -= v49;
        v92 = v27;
      }
      v23 = Size;
      *((_QWORD *)a1 + 26) += v52;
      if ( !v23 || !v27 )
        goto LABEL_31;
    }
  }
  v21 = v91;
  v30 = a8;
  v25 = BATCHCTX::FlushData(v91, a1, v86[0], (struct tagCOLUMN_INFO *)((char *)v17 + 64), a8);
  if ( !v25 )
  {
    v76 = *((_DWORD *)a1 + 372);
    if ( (v76 & 0x40000) != 0 )
    {
      v25 = 265937;
      *((_DWORD *)a1 + 372) = v76 & 0xFFFBFFFF;
    }
  }
  v36 = 0;
LABEL_40:
  v37 = *((_DWORD *)v88 + 2256);
  if ( v37 != v102 )
    v37 = v102;
  *((_DWORD *)v88 + 2256) = v37;
  if ( !v25 )
    goto LABEL_43;
  if ( v25 >= 0 )
  {
    if ( v25 == 265937 )
    {
      v38 = 1;
      goto LABEL_44;
    }
LABEL_43:
    v38 = 0;
LABEL_44:
    if ( (v38 & 0xFFFE) != 0 || !v36 || v101 )
      goto LABEL_50;
    if ( v94 != -1 )
    {
      if ( v94 <= 0x7FFFFFFFFFFFFFFFLL )
      {
        *v36 = v94;
LABEL_50:
        *((_QWORD *)a1 + 26) = 0;
        *((_QWORD *)v21 + 17) = 0;
        goto LABEL_51;
      }
      *v36 = -1;
    }
    *v36 = -4;
    goto LABEL_50;
  }
  if ( v25 != -2147023436 )
  {
    v38 = -1;
    goto LABEL_44;
  }
  v38 = 2;
  if ( v30 != 1000 )
  {
    *((_QWORD *)a1 + 26) = 0;
    *((_QWORD *)v21 + 17) = 0;
    v38 = -1;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B49120[0] )
        bidTraceW(off_383B43208[0], 2266121, off_383B49120[0], 2213);
    }
  }
LABEL_51:
  if ( (bidGblFlags & 2) != 0 && (v38 || (bidGblFlags & 0x40) != 0) )
  {
    v77 = 2287617;
    if ( v38 )
      v77 = 2287649;
    bidTraceW(off_383B43208[0], v77, off_383B494E8[0], (unsigned int)v38);
  }
  return (unsigned __int16)v38;
}

```

## disassembly

```asm
0x3838723c0  mov     r11, rsp
0x3838723c3  push    rbp
0x3838723c4  push    rbx
0x3838723c5  lea     rbp, [r11-0A48h]
0x3838723cc  sub     rsp, 0B38h
0x3838723d3  mov     rax, cs:__security_cookie
0x3838723da  xor     rax, rsp
0x3838723dd  mov     [rbp+0A40h+var_50], rax
0x3838723e4  mov     rbx, [rbp+0A40h+arg_20]
0x3838723eb  mov     [r11-20h], rdi
0x3838723ef  mov     [r11-28h], r12
0x3838723f3  mov     rax, r8
0x3838723f6  mov     r8, [rbp+0A40h+arg_48]
0x3838723fd  mov     [r11-30h], r13
0x383872401  mov     r13, rcx
0x383872404  mov     [r11-40h], r15
0x383872408  mov     r15, [rcx+70h]
0x38387240c  mov     rcx, [rcx+458h]
0x383872413  mov     rdi, rdx
0x383872416  mov     [rbp+0A40h+var_AA0], rdx
0x38387241a  mov     [rbp+0A40h+var_A68], rdx
0x38387241e  movzx   edx, [rbp+0A40h+arg_30]; unsigned __int16
0x383872425  mov     [rbp+0A40h+var_A98], rcx
0x383872429  mov     ecx, [r15+2340h]
0x383872430  mov     [rbp+0A40h+var_A88], r9
0x383872434  xor     r9d, r9d
0x383872437  mov     [rbp+0A40h+var_A58], rax
0x38387243b  mov     dword ptr [rbp+0A40h+var_AC0], edx
0x38387243e  mov     [rbp+0A40h+var_A38], r8
0x383872442  mov     [rbp+0A40h+var_A4C], ecx
0x383872445  movzx   r12d, r9w
0x383872449  mov     [rbp+0A40h+var_AB0], r15
0x38387244d  mov     [rbp+0A40h+Size], rax
0x383872451  mov     [rbp+0A40h+var_A70], r9
0x383872455  mov     [rbp+0A40h+var_A90], r9
0x383872459  mov     [rbp+0A40h+var_A48], r9
0x38387245d  mov     [rbp+0A40h+var_A80], r9
0x383872461  mov     [rbp+0A40h+var_A60], r9d
0x383872465  mov     [rbp+0A40h+var_A5C], r9d
0x383872469  test    r8, r8
0x38387246c  jnz     short loc_38387247F
0x38387246e  lea     rcx, [r13+38h]; this
0x383872472  call    ?GetColInfoByOrdinal@IRDTag@@QEAAPEAUtagCOLUMN_INFO@@G@Z; IRDTag::GetColInfoByOrdinal(ushort)
0x383872477  mov     edx, dword ptr [rbp+0A40h+var_AC0]
0x38387247a  mov     rcx, rax
0x38387247d  jmp     short loc_38387248E
0x38387247f  mov     [rbp+0A40h+var_AA8], dx
0x383872483  mov     edx, 1; unsigned __int16
0x383872488  mov     rcx, r8
0x38387248b  mov     dword ptr [rbp+0A40h+var_AC0], edx
0x38387248e  cmp     word ptr [rcx+10h], 0Dh
0x383872493  mov     [rsp+0B30h], rsi
0x38387249b  mov     [rsp+0B40h+var_AC8], rcx
0x3838724a0  mov     [rsp+0B40h+var_30], r14
0x3838724a8  jmp     loc_383873080
0x383873065  cmp     r14w, 0FFF8h
0x38387306a  jz      loc_3838731C7
0x383873070  cmp     r14w, 0FFFEh
0x383873075  jnz     loc_3838731D4
0x38387307b  jmp     loc_3838731C7
0x383873080  jz      loc_3838CF176
0x383873086  movzx   r14d, [rbp+0A40h+arg_28]
0x38387308e  movzx   esi, word ptr [rcx+6Ch]
0x383873092  cmp     r14w, 63h ; 'c'
0x383873097  jz      loc_3838CF1C6
0x38387309d  test    r14w, r14w
0x3838730a1  jz      loc_3838CFDD3
0x3838730a7  test    dword ptr [r13+5D0h], 40000h
0x3838730b2  jnz     loc_3838CFDD3
0x3838730b8  mov     r15, [rbp+0A40h+var_A98]
0x3838730bc  mov     r8d, dword ptr [rbp+0A40h+var_AC0]; unsigned __int16
0x3838730c0  cmp     r8w, [r15+90h]
0x3838730c8  jz      loc_3838CF1FD
0x3838730ce  mov     rdi, [rbp+0A40h+Size]
0x3838730d2  xor     eax, eax
0x3838730d4  mov     [r13+8E8h], rax
0x3838730db  mov     [r13+0D8h], rax
0x3838730e2  mov     [r13+0D0h], rax
0x3838730e9  jmp     short $+2
0x3838730eb  add     rcx, 40h ; '@'
0x3838730ef  lea     rax, [rbp+0A40h+var_A50]
0x3838730f3  mov     rdx, r13; void *
0x3838730f6  mov     [rsp+0B40h+var_B10], rax; int *
0x3838730fb  lea     rax, [rbp+0A40h+var_A90]
0x3838730ff  mov     [rbp+0A40h+var_A28], rcx
0x383873103  mov     [rsp+0B40h+var_B18], rax; unsigned __int64 *
0x383873108  mov     eax, [rbp+0A40h+arg_38]
0x38387310e  mov     r9, rcx; struct BaseMetaInfo *
0x383873111  mov     rcx, r15; this
0x383873114  mov     [rsp+0B40h+var_B20], eax; unsigned int
0x383873118  call    ?GetDataLen@BATCHCTX@@QEAAJPEAXGPEAUBaseMetaInfo@@KPEA_KPEAH@Z; BATCHCTX::GetDataLen(void *,ushort,BaseMetaInfo *,ulong,unsigned __int64 *,int *)
0x38387311d  mov     ecx, eax
0x38387311f  mov     dword ptr [rsp+0B40h+var_AD0], eax
0x383873123  test    eax, eax
0x383873125  jnz     loc_3838CF226
0x38387312b  cmp     [rbp+0A40h+var_A50], 0
0x38387312f  mov     eax, 9DDAh
0x383873134  jnz     loc_3838CF250
0x38387313a  mov     rdx, [rsp+0B40h+var_AC8]; struct tagCOLUMN_INFO *
0x38387313f  mov     r15, [rbp+0A40h+var_A90]
0x383873143  cmp     word ptr [rdx+10h], 0Dh
0x383873148  mov     [rbp+0A40h+var_A48], r15
0x38387314c  jz      loc_3838CF289
0x383873152  cmp     r14w, 0FFF8h
0x383873157  jz      loc_3838CF2B3
0x38387315d  cmp     r14w, 1
0x383873162  jnz     short loc_383873186
0x383873164  test    rdi, rdi
0x383873167  jz      loc_3838CF33C
0x38387316d  dec     rdi
0x383873170  mov     [rbp+0A40h+Size], rdi
0x383873174  jmp     short $+2
0x383873176  mov     rbx, [r13+8E8h]
0x38387317d  test    rbx, rbx
0x383873180  jnz     loc_3838CF345
0x383873186  cmp     dword ptr [r13+5E0h], 0
0x38387318e  jnz     loc_383873365
0x383873194  test    r15, r15
0x383873197  jz      loc_3838CF2D8
0x38387319d  mov     rbx, [rbp+0A40h+var_AB0]
0x3838731a1  mov     r9d, [rdx+60h]; unsigned int
0x3838731a5  movzx   r8d, r14w; __int16
0x3838731a9  mov     rcx, rbx; struct tagDBC *
0x3838731ac  call    ?FIsConversionNeeded@@YAHPEAUtagDBC@@PEAUtagCOLUMN_INFO@@FK@Z; FIsConversionNeeded(tagDBC *,tagCOLUMN_INFO *,short,ulong)
0x3838731b1  mov     [rbp+0A40h+var_A5C], eax
0x3838731b4  test    eax, eax
0x3838731b6  jnz     loc_3838CF429
0x3838731bc  cmp     r14w, 1
0x3838731c1  jnz     loc_383873065
0x3838731c7  cmp     si, 1
0x3838731cb  jnz     loc_3838CF3CF
0x3838731d1  mov     r15, rdi
0x3838731d4  mov     edi, [rbp+0A40h+arg_38]
0x3838731da  lea     rax, [rbp+0A40h+var_A90]
0x3838731de  mov     r9, r15; unsigned __int64
0x3838731e1  mov     r15, [rbp+0A40h+var_A98]
0x3838731e5  mov     [rsp+0B40h+var_B08], rax; unsigned __int64 *
0x3838731ea  lea     rax, [rbp+0A40h+var_A70]
0x3838731ee  mov     [rsp+0B40h+var_B10], rax; unsigned __int64 *
0x3838731f3  lea     r8, [rbp+0A40h+var_A68]; unsigned __int8 **
0x3838731f7  mov     rdx, r13; void *
0x3838731fa  mov     rcx, r15; this
0x3838731fd  mov     dword ptr [rsp+0B40h+var_B18], edi; unsigned int
0x383873201  mov     [rsp+0B40h+var_B20], 1; int
0x383873209  call    ?FetchData@BATCHCTX@@QEAAJPEAXPEAPEAE_KHKPEA_K3@Z; BATCHCTX::FetchData(void *,uchar * *,unsigned __int64,int,ulong,unsigned __int64 *,unsigned __int64 *)
0x38387320e  mov     ecx, eax
0x383873210  mov     dword ptr [rsp+0B40h+var_AD0], eax
0x383873214  test    eax, eax
0x383873216  jnz     loc_3838CF3FF
0x38387321c  mov     rax, [rbp+0A40h+var_A70]
0x383873220  mov     rbx, [rbp+0A40h+var_A68]
0x383873224  mov     r15, [rbp+0A40h+var_A90]
0x383873228  add     [r13+0D0h], rax
0x38387322f  add     rbx, rax
0x383873232  mov     [rbp+0A40h+var_AA0], rbx
0x383873236  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x38387323a  jz      short loc_383873241
0x38387323c  sub     r15, rax
0x38387323f  jmp     short $+2
0x383873241  cmp     r14w, 0FFF8h
0x383873246  jz      loc_3838CF31E
0x38387324c  cmp     r14w, 1
0x383873251  jnz     short loc_383873261
0x383873253  cmp     [rbp+0A40h+var_A58], 0
0x383873258  jz      short loc_383873261
0x38387325a  mov     rax, [rbp+0A40h+var_AA0]
0x38387325e  mov     byte ptr [rax], 0
0x383873261  test    r12w, r12w
0x383873265  jnz     loc_3838CFA1D
0x38387326b  test    r15, r15
0x38387326e  jnz     loc_3838CFA0D
0x383873274  mov     rax, [r13+0D0h]
0x38387327b  mov     ecx, dword ptr [rsp+0B40h+var_AD0]
0x38387327f  mov     r15, [rbp+0A40h+var_A98]
0x383873283  mov     [rbp+0A40h+var_A80], rax
0x383873287  jmp     short $+2
0x383873289  mov     edi, [rbp+0A40h+arg_38]
0x38387328f  xor     r10d, r10d
0x383873292  or      r11, 0FFFFFFFFFFFFFFFFh
0x383873296  mov     r8, [rbp+0A40h+var_A88]
0x38387329a  mov     rdx, [rbp+0A40h+var_AB0]
0x38387329e  mov     r9d, [rbp+0A40h+var_A4C]
0x3838732a2  mov     r14, [rsp+0B40h+var_30]
0x3838732aa  mov     eax, [rdx+2340h]
0x3838732b0  mov     r12, [rsp+0B40h+var_20]
0x3838732b8  mov     rsi, [rsp+0B30h]
0x3838732c0  cmp     eax, r9d
0x3838732c3  cmovnz  eax, r9d
0x3838732c7  mov     [rdx+2340h], eax
0x3838732cd  test    ecx, ecx
0x3838732cf  jnz     loc_3838CFE27
0x3838732d5  movzx   ebx, r10w
0x3838732d9  jmp     short $+2
0x3838732db  mov     eax, 0FFFEh
0x3838732e0  test    ax, bx
0x3838732e3  jnz     short loc_383873316
0x3838732e5  test    r8, r8
0x3838732e8  jz      short loc_383873316
0x3838732ea  cmp     [rbp+0A40h+var_A50], 0
0x3838732ee  jnz     short loc_383873316
0x3838732f0  mov     rax, [rbp+0A40h+var_A80]
0x3838732f4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x3838732f8  jz      loc_3838CFEB8
0x3838732fe  mov     rcx, 7FFFFFFFFFFFFFFFh
0x383873308  cmp     rax, rcx
0x38387330b  ja      loc_3838CFEB5
0x383873311  mov     [r8], rax
0x383873314  jmp     short $+2
0x383873316  mov     [r13+0D0h], r10
0x38387331d  mov     [r15+88h], r10
0x383873324  test    byte ptr cs:_bidGblFlags, 2
0x38387332b  mov     r15, [rsp+0B40h+var_38]
0x383873333  mov     r13, [rsp+0B40h+var_28]
0x38387333b  mov     rdi, [rsp+0B40h+var_18]
0x383873343  jnz     loc_3838CFEC4
0x383873349  movzx   eax, bx
0x38387334c  mov     rcx, [rbp+0A40h+var_50]
0x383873353  xor     rcx, rsp; StackCookie
0x383873356  call    __security_check_cookie
0x38387335b  add     rsp, 0B38h
0x383873362  pop     rbx
0x383873363  pop     rbp
0x383873364  retn
0x383873365  movzx   ecx, byte ptr [rdx+40h]
0x383873369  movzx   eax, cl
0x38387336c  and     al, 30h
0x38387336e  cmp     al, 20h ; ' '
0x383873370  jnz     loc_3838CF2CA
0x383873376  mov     dword ptr [r13+5E0h], 0
0x383873381  jmp     loc_383873194
0x3838cf176  mov     r8d, [rbp+0A40h+arg_38]; unsigned int
0x3838cf17d  mov     r9, rcx; struct tagCOLUMN_INFO *
0x3838cf180  mov     rcx, r13; struct tagSTMT *
0x3838cf183  call    ?GetVariantBaseTypeInfo@@YAJPEAUtagSTMT@@GKPEAUtagCOLUMN_INFO@@@Z; GetVariantBaseTypeInfo(tagSTMT *,ushort,ulong,tagCOLUMN_INFO *)
0x3838cf188  mov     ecx, eax
0x3838cf18a  mov     dword ptr [rsp+0B40h+var_AD0], eax
0x3838cf18e  test    eax, eax
0x3838cf190  jz      short loc_3838CF1BC
0x3838cf192  test    byte ptr cs:_bidGblFlags, 2
0x3838cf199  jz      short loc_3838CF1B3
0x3838cf19b  mov     edx, 188809h
0x3838cf1a0  mov     rcx, cs:off_383B43208; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838cf1a7  mov     r8d, eax
0x3838cf1aa  call    _bidTraceHR
0x3838cf1af  mov     ecx, dword ptr [rsp+0B40h+var_AD0]
0x3838cf1b3  mov     r15, [rbp+0A40h+var_A98]
0x3838cf1b7  jmp     loc_383873289
0x3838cf1bc  mov     rcx, [rsp+0B40h+var_AC8]
0x3838cf1c1  jmp     loc_383873086
0x3838cf1c6  test    byte ptr [r15+2780h], 24h
0x3838cf1ce  movzx   eax, word ptr [rcx+10h]
0x3838cf1d2  lea     rcx, cs:383800000h
0x3838cf1d9  movsx   rax, ax
0x3838cf1dd  jz      short loc_3838CF1EA
0x3838cf1df  movzx   r14d, ds:rva word_383911D96[rcx+rax*2]
0x3838cf1e8  jmp     short loc_3838CF1F3
0x3838cf1ea  movzx   r14d, ds:rva word_383911DD6[rcx+rax*2]
0x3838cf1f3  mov     rcx, [rsp+0B40h+var_AC8]
0x3838cf1f8  jmp     loc_38387309D
0x3838cf1fd  mov     rax, [r13+0D0h]
0x3838cf204  mov     rdx, [rbp+0A40h+var_A58]
0x3838cf208  add     rdi, rax
0x3838cf20b  sub     rdx, rax
0x3838cf20e  mov     [rbp+0A40h+var_AA0], rdi
0x3838cf212  mov     [rbp+0A40h+var_A68], rdi
0x3838cf216  mov     [rbp+0A40h+var_A58], rdx
0x3838cf21a  mov     rdi, rdx
0x3838cf21d  mov     [rbp+0A40h+Size], rdx
0x3838cf221  jmp     loc_3838730EB
0x3838cf226  test    byte ptr cs:_bidGblFlags, 2
0x3838cf22d  jz      loc_383873289
0x3838cf233  mov     rcx, cs:off_383B43208; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3838cf23a  mov     r8d, eax
0x3838cf23d  mov     edx, 194009h
0x3838cf242  call    _bidTraceHR
0x3838cf247  mov     ecx, dword ptr [rsp+0B40h+var_AD0]
0x3838cf24b  jmp     loc_383873289
0x3838cf250  test    rbx, rbx
0x3838cf253  jnz     short loc_3838CF274
0x3838cf255  mov     rax, [rbp+0A40h+var_A48]
0x3838cf259  mov     rbx, [rbp+0A40h+var_AB0]
0x3838cf25d  mov     r12d, 9CBBh
0x3838cf263  mov     [rbp+0A40h+var_A80], rax
0x3838cf267  mov     dword ptr [rsp+0B40h+var_AD0], 80004005h
0x3838cf26f  jmp     loc_3838CFB00
0x3838cf274  mov     edi, [rbp+0A40h+arg_38]
0x3838cf27a  or      r11, 0FFFFFFFFFFFFFFFFh
0x3838cf27e  xor     r10d, r10d
0x3838cf281  mov     [rbx], r11
0x3838cf284  jmp     loc_383873296
0x3838cf289  cmp     r14w, 0FFFEh
0x3838cf28e  jnz     loc_383873152
0x3838cf294  cmp     [rbp+0A40h+var_A58], 0
0x3838cf299  jnz     loc_383873186
0x3838cf29f  mov     rbx, [rbp+0A40h+var_AB0]
0x3838cf2a3  movzx   r12d, ax
0x3838cf2a7  mov     rax, r15
0x3838cf2aa  mov     [rbp+0A40h+var_A80], rax
0x3838cf2ae  jmp     loc_3838CFB00
0x3838cf2b3  and     rdi, 0FFFFFFFFFFFFFFFEh
  ... truncated ...
```
