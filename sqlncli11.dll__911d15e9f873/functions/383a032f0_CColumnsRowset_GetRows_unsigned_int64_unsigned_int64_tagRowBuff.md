# CColumnsRowset::GetRows(unsigned __int64,unsigned __int64 *,tagRowBuff *)

- ea: `0x383a032f0`
- end: `0x383a0442a`
- name: `?GetRows@CColumnsRowset@@MEAAJ_KPEA_KPEAUtagRowBuff@@@Z`
- size: `4410`
- prototype: `__int64 __fastcall(CColumnsRowset *__hidden this, unsigned __int64, unsigned __int64 *, struct tagRowBuff *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x3838427d0`
- `0x3838434c0`
- `0x38387c640`
- `0x38391aed0`
- `0x38391afe0`
- `0x383937270`
- `0x383a032f0`

## import_xrefs

- `MSVCR100!memmove` at `0x383a0359c`
- `MSVCR100!memmove` at `0x383a0359c`
- `MSVCR100!wcschr` at `0x383a0365c`
- `MSVCR100!wcschr` at `0x383a0365c`

## pseudocode

```c
__int64 __fastcall CColumnsRowset::GetRows(
        CColumnsRowset *this,
        unsigned __int64 a2,
        unsigned __int64 *a3,
        struct tagRowBuff *a4)
{
  __int64 v6; // r11
  __int64 v8; // rax
  BOOL v9; // r10d
  __int64 v10; // r13
  __int64 v11; // rax
  __int64 v12; // r14
  __int64 v13; // rdx
  _WORD *v14; // rcx
  unsigned int v15; // esi
  __int64 v16; // r9
  __int64 v17; // r8
  __int16 v18; // ax
  unsigned __int64 v20; // rax
  CColumnsRowset *v21; // rbx
  __int64 v22; // r12
  __int64 v23; // r15
  unsigned __int8 v24; // al
  __int64 v25; // r8
  __int64 v26; // r10
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  const wchar_t *v32; // rdi
  __int64 v33; // rbx
  int v34; // esi
  __int64 v35; // rbp
  wchar_t *v36; // rax
  __int64 v37; // rax
  const void *v38; // rdx
  __int64 v39; // r8
  _WORD *v40; // r11
  __int64 v41; // r10
  int v42; // esi
  int v43; // esi
  const void *v44; // rax
  __int64 v45; // r14
  struct tagRowBuff *v46; // r9
  unsigned __int64 v47; // r12
  _QWORD *v48; // rbp
  char *v49; // rdi
  _DWORD *v50; // r14
  _QWORD *v51; // rsi
  _WORD *v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r8
  char *v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rax
  __int16 v58; // ax
  unsigned __int64 v59; // rax
  int v60; // eax
  unsigned __int64 v61; // rax
  __int64 v62; // rax
  char *v63; // rcx
  _BYTE *v64; // rdx
  __int64 v65; // rbx
  char *v66; // r11
  __int64 v67; // rcx
  size_t v68; // rbx
  char *v69; // rcx
  int v70; // eax
  __int16 v71; // ax
  int v72; // eax
  int v73; // eax
  bool v74; // zf
  int v75; // ebx
  __int64 v76; // rax
  __int64 v77; // rax
  char *v78; // rcx
  char *v79; // rcx
  char *v80; // rcx
  char *v81; // rcx
  char *v82; // rcx
  __int64 v85; // [rsp+40h] [rbp-218h]
  __int64 v86; // [rsp+48h] [rbp-210h]
  _WORD *v87; // [rsp+50h] [rbp-208h]
  const void *v88; // [rsp+58h] [rbp-200h]
  unsigned int v89; // [rsp+60h] [rbp-1F8h]
  const void *v90; // [rsp+68h] [rbp-1F0h]
  __int64 v91; // [rsp+70h] [rbp-1E8h]
  _BYTE *v92; // [rsp+78h] [rbp-1E0h]
  _BOOL8 v93; // [rsp+80h] [rbp-1D8h]
  __int64 v94; // [rsp+88h] [rbp-1D0h]
  __int64 v95; // [rsp+90h] [rbp-1C8h]
  __int64 v96; // [rsp+98h] [rbp-1C0h]
  unsigned __int64 v97; // [rsp+A0h] [rbp-1B8h]
  unsigned __int64 v98; // [rsp+A8h] [rbp-1B0h]
  __int64 v99; // [rsp+B0h] [rbp-1A8h]
  _QWORD v100[4]; // [rsp+B8h] [rbp-1A0h]
  _QWORD v101[5]; // [rsp+D8h] [rbp-180h]
  _BYTE Src[272]; // [rsp+100h] [rbp-158h] BYREF

  v6 = *((_QWORD *)this + 66);
  v8 = *((_QWORD *)this + 79);
  v9 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 528) + 200LL) + 344LL) + 40LL) + 880LL) == 80;
  if ( !v8 || *((_QWORD *)this + 104) > v8 )
  {
    *a3 = 0;
    return 265926;
  }
  v88 = 0;
  v10 = 0;
  v87 = 0;
  v92 = 0;
  v90 = 0;
  v86 = 0;
  v94 = 0;
  v85 = 0;
  if ( !*(_QWORD *)(v6 + 424) )
  {
    v11 = *(_QWORD *)(v6 + 704);
    if ( v11 )
      *(_QWORD *)(v6 + 424) = *(_QWORD *)(v11 + 1944);
  }
  v12 = *(_QWORD *)(v6 + 424);
  v96 = v12;
  if ( !v12 || (*(_WORD *)(v6 + 584) & 0x2000) != 0 )
  {
    v12 = v6 + 320;
    v96 = v6 + 320;
  }
  v13 = 129;
  v14 = Src;
  v15 = 0;
  v89 = 0;
  v16 = *(_QWORD *)(*((_QWORD *)this + 66) + 528LL) + 754LL - (_QWORD)Src;
  v17 = 0;
  while ( v13 != -2147483517 )
  {
    v18 = *(_WORD *)((char *)v14 + v16);
    if ( !v18 )
      break;
    *v14++ = v18;
    ++v17;
    if ( !--v13 )
    {
      v15 = -2147024774;
      --v14;
      --v17;
      v89 = -2147024774;
      break;
    }
  }
  *v14 = 0;
  if ( (v15 & 0x80000000) == 0 )
  {
    v20 = *((_QWORD *)this + 79) - *((_QWORD *)this + 104) + 1LL;
    v99 = (2 * v17) >> 1;
    if ( a2 >= v20 )
      a2 = v20;
    *a3 = a2;
    v21 = this;
    v98 = a2;
    v95 = *((_QWORD *)this + 104);
    v22 = v95;
    v23 = *((_QWORD *)this + 108) + 304 * v95;
    if ( *((_DWORD *)this + 221) )
      v23 -= 304;
    v97 = 0;
    v93 = v9;
    if ( !a2 )
      return v15;
    while ( 1 )
    {
      if ( !*(_QWORD *)(v23 + 104) )
      {
        v24 = *(_BYTE *)(v23 + 122);
        if ( v24 )
        {
          v25 = *((_QWORD *)v21 + 109);
          if ( v25 )
            memmove((void *)(v23 + 72), (const void *)(*(_QWORD *)(v25 + 32) + 40LL * v24), 0x28u);
        }
      }
      v26 = *(_QWORD *)(v23 + 104);
      v27 = *(_QWORD *)(v23 + 96);
      v28 = *(_QWORD *)(v23 + 88);
      v29 = *(_QWORD *)(v23 + 80);
      v30 = *(_QWORD *)(v23 + 72);
      v91 = v26;
      if ( v26 )
      {
        v31 = *((_QWORD *)v21 + 115);
        v32 = (const wchar_t *)(v31 + v26);
        if ( v27 || v28 || v29 || v30 )
        {
          v44 = (const void *)(v31 + v27);
          v41 = -1;
          v90 = v44;
          do
            ++v41;
          while ( *((_WORD *)v44 + v41) );
          v85 = v41;
          v45 = -1;
          v92 = (_BYTE *)(v31 + v28);
          do
            ++v45;
          while ( *(_WORD *)(v31 + v28 + 2 * v45) );
          v40 = (_WORD *)(v31 + v29);
          v94 = v45;
          v39 = -1;
          v87 = v40;
          do
            ++v39;
          while ( v40[v39] );
          v86 = v39;
          v10 = -1;
          v88 = (const void *)(v31 + v30);
          do
            ++v10;
          while ( *(_WORD *)(v31 + v30 + 2 * v10) );
          v38 = (const void *)(v31 + v30);
          v12 = v96;
          goto LABEL_65;
        }
        v90 = 0;
        v85 = 0;
        v92 = 0;
        v94 = 0;
        v87 = 0;
        v86 = 0;
        v88 = 0;
        v10 = 0;
        v33 = -1;
        do
          ++v33;
        while ( v32[v33] );
        v34 = 0;
        v35 = 0;
        while ( 1 )
        {
          v100[v35] = v32;
          if ( *v32 == 46 )
          {
            v101[v35] = 0;
          }
          else
          {
            v36 = wcschr(v32, 0x2Eu);
            if ( v36 )
            {
              v37 = v36 - v32;
              v101[v35] = v37;
            }
            else
            {
              v37 = v33;
              v101[v35] = v33;
            }
            v33 -= v37;
            v32 += v37;
          }
          if ( !v33 )
            break;
          ++v34;
          ++v35;
          ++v32;
          --v33;
          if ( v34 >= 4 )
          {
            v21 = this;
            v38 = 0;
            v39 = 0;
            v40 = 0;
            v41 = 0;
            goto LABEL_65;
          }
        }
        v38 = (const void *)v100[v35];
        v10 = v101[v35];
        v88 = v38;
        v42 = v34 - 1;
        if ( !v42 )
          goto LABEL_51;
        v43 = v42 - 1;
        if ( !v43 )
          goto LABEL_49;
        if ( v43 == 1 )
        {
          if ( v101[0] )
          {
            v85 = v101[0];
            v90 = (const void *)v100[0];
          }
LABEL_49:
          if ( v100[v35 + 2] )
          {
            v94 = v100[v35 + 2];
            v92 = (_BYTE *)*(&v98 + v35);
          }
LABEL_51:
          v21 = this;
          v41 = v85;
          if ( v100[v35 + 3] )
          {
            v40 = (_WORD *)v100[v35 - 1];
            v39 = v100[v35 + 3];
            v86 = v39;
            v87 = v40;
          }
          else
          {
            v39 = 0;
            v40 = 0;
          }
          goto LABEL_65;
        }
        v39 = 0;
        v21 = this;
        v41 = 0;
        v40 = 0;
      }
      else
      {
        v39 = v86;
        v41 = v85;
        v38 = v88;
        v40 = v87;
      }
LABEL_65:
      v46 = a4;
      *((_QWORD *)a4 + 16) = v22;
      *((_DWORD *)a4 + 8) = 1;
      *((_DWORD *)a4 + 30) = 0;
      *((_QWORD *)a4 + 14) = 8;
      v47 = 1;
      v48 = (_QWORD *)(*(_QWORD *)(v12 + 16) + 304LL);
      if ( *(_WORD *)(v12 + 2) )
      {
        v89 = 0;
        while ( 1 )
        {
          v49 = (char *)v46 + v48[23];
          v50 = (_DWORD *)((char *)v46 + v48[25]);
          v51 = (_QWORD *)((char *)v46 + v48[24]);
          switch ( *(_DWORD *)(*((_QWORD *)v21 + 105) + 4 * v47) )
          {
            case 1:
              if ( ((1 << *(_DWORD *)(v23 + 168)) & 0xD) == 0 )
              {
                *v51 = 0;
                *(_WORD *)v49 = 0;
                *v50 = 3;
                goto LABEL_227;
              }
              v52 = (_WORD *)(*(_QWORD *)(v23 + 32) + *((_QWORD *)v21 + 115));
              v53 = -1;
              do
                ++v53;
              while ( v52[v53] );
              goto LABEL_71;
            case 2:
              if ( ((1 << *(_DWORD *)(v23 + 168)) & 0x43) == 0 )
                goto LABEL_75;
              *(_DWORD *)v49 = *(_DWORD *)(v23 + 152);
              *((_DWORD *)v49 + 1) = *(_DWORD *)(v23 + 156);
              *((_DWORD *)v49 + 2) = *(_DWORD *)(v23 + 160);
              *((_DWORD *)v49 + 3) = *(_DWORD *)(v23 + 164);
              *v51 = 16;
              *v50 = 0;
              goto LABEL_227;
            case 3:
              if ( ((1 << *(_DWORD *)(v23 + 168)) & 0x32) == 0 )
                goto LABEL_75;
              *(_DWORD *)v49 = *(_DWORD *)(v23 + 176);
              *v51 = 4;
              *v50 = 0;
              goto LABEL_227;
            case 4:
              v56 = *(_QWORD *)(v23 + 32);
              if ( !v56 )
                goto LABEL_82;
              v52 = (_WORD *)(v56 + *((_QWORD *)v21 + 115));
              v53 = -1;
              do
                ++v53;
              while ( v52[v53] );
              goto LABEL_71;
            case 5:
              v57 = v95;
              if ( *((_DWORD *)v21 + 221) )
                v57 = v95 - 1;
              *(_QWORD *)v49 = v57;
              *v51 = 8;
              *v50 = 0;
              goto LABEL_227;
            case 6:
              if ( *(_DWORD *)(v23 + 136) != 144 || (*(_WORD *)(v23 + 132) & 0x1000) != 0 )
              {
                v58 = *(_WORD *)(v23 + 136);
                if ( v93 )
                {
                  if ( v58 == 141 )
                  {
                    v58 = 130;
                  }
                  else if ( v58 == 132 )
                  {
                    v58 = 128;
                  }
                }
              }
              else
              {
                v58 = 12;
              }
              goto LABEL_94;
            case 7:
              goto LABEL_75;
            case 8:
              if ( !(unsigned int)FIsVarMaxType((struct BaseMetaInfo *)v23) )
              {
                if ( *(_DWORD *)(v23 + 112) == 25 && *(_QWORD *)(v23 + 144) == 0xFFFF )
                {
                  v59 = -1;
LABEL_111:
                  *(_QWORD *)v49 = v59;
                  goto LABEL_112;
                }
                v60 = *(_DWORD *)(v23 + 136);
                if ( v60 == 129 )
                {
                  v61 = *(_QWORD *)(v23 + 144);
                }
                else
                {
                  v74 = v60 == 130;
                  v59 = *(_QWORD *)(v23 + 144);
                  if ( !v74 )
                    goto LABEL_111;
                  v61 = v59 >> 1;
                }
                v59 = v61 - 1;
                goto LABEL_111;
              }
              *(_QWORD *)v49 = -1;
              if ( !v93 )
                goto LABEL_112;
              if ( *(_DWORD *)(v23 + 112) != 26 )
              {
                if ( *(_DWORD *)(v23 + 112) == 27 )
                  goto LABEL_101;
                if ( *(_DWORD *)(v23 + 112) != 28 )
                {
                  if ( *(_DWORD *)(v23 + 112) != 29 )
                    goto LABEL_112;
LABEL_101:
                  *(_QWORD *)v49 = 0x3FFFFFFF;
                  goto LABEL_112;
                }
              }
              *(_QWORD *)v49 = 0x7FFFFFFF;
LABEL_112:
              v46 = a4;
              *v51 = 8;
              *v50 = 0;
LABEL_227:
              v12 = v96;
              v39 = v86;
              v41 = v85;
              v38 = v88;
              v40 = v87;
              ++v47;
              v48 += 38;
              if ( v47 > *(unsigned __int16 *)(v96 + 2) )
                goto LABEL_228;
              break;
            case 9:
              LOBYTE(v58) = *(_BYTE *)(v23 + 140);
              if ( (_BYTE)v58 == 0xFF )
                goto LABEL_75;
              if ( *(_DWORD *)(v23 + 112) == 16 )
                v58 = *(unsigned __int8 *)(v23 + 120);
              else
LABEL_117:
                v58 = (unsigned __int8)v58;
LABEL_94:
              *(_WORD *)v49 = v58;
              *v51 = 2;
              *v50 = 0;
              goto LABEL_227;
            case 0xA:
              LOBYTE(v58) = *(_BYTE *)(v23 + 141);
              if ( (_BYTE)v58 != 0xFF )
                goto LABEL_117;
              goto LABEL_75;
            case 0xB:
              *(_DWORD *)v49 = *(_DWORD *)(v23 + 116);
              *v51 = 4;
              *v50 = 0;
              goto LABEL_227;
            case 0xC:
              if ( v91 )
              {
                v62 = v94;
                v63 = (char *)v46 + v48[23];
                if ( v94 )
                {
                  v64 = v92;
                }
                else
                {
                  v62 = v99;
                  v64 = Src;
                }
                v65 = 2 * v62;
                *v51 = 2 * v62;
                memcpy(v63, v64, 2 * v62);
                v46 = a4;
                v66 = &v49[v65];
                v21 = this;
                *(_WORD *)v66 = 0;
                *v50 = 0;
              }
              else
              {
                *(_QWORD *)v49 = 0;
                *v51 = 0;
                *v50 = 3;
              }
              goto LABEL_227;
            case 0xD:
              v67 = *(_QWORD *)(v23 + 40);
              if ( !v67 )
                goto LABEL_82;
              v52 = (_WORD *)(v67 + *((_QWORD *)v21 + 115));
              v53 = -1;
              do
                ++v53;
              while ( v52[v53] );
LABEL_71:
              v54 = 2 * v53;
              v55 = (char *)v46 + v48[23];
              *v51 = v54;
              memcpy(v55, v52, v54 + 2);
              v46 = a4;
              *v50 = 0;
              goto LABEL_227;
            case 0xE:
              if ( !v91 || !v39 )
                goto LABEL_82;
              v68 = 2 * v39;
              v38 = v40;
              goto LABEL_132;
            case 0xF:
              if ( !v91 || !v10 )
                goto LABEL_82;
              v68 = 2 * v10;
              goto LABEL_132;
            case 0x10:
              v70 = *(_DWORD *)(v23 + 48);
              if ( v70 || *(_BYTE *)(v23 + 52) )
              {
                *(_DWORD *)v49 = v70 & 0xFFFFF;
                *v51 = 4;
                *v50 = 0;
              }
              else
              {
                *(_QWORD *)v49 = 0;
                *v51 = 0;
                *v50 = 3;
              }
              goto LABEL_227;
            case 0x11:
              v71 = *(_WORD *)(v23 + 130);
              if ( (v71 & 0x400) == 0 || v93 )
              {
                *(_DWORD *)v49 = (~(_BYTE)v71 & 0x20 | 0x10u) >> 4;
                *v51 = 4;
                *v50 = 0;
              }
              else
              {
                *(_DWORD *)v49 = 2;
                *v51 = 4;
                *v50 = 0;
              }
              goto LABEL_227;
            case 0x12:
              v72 = *(_DWORD *)(v23 + 112);
              if ( v72 == 17 )
              {
                *v51 = 4;
                *v50 = 0;
                v73 = 0;
                if ( *(_QWORD *)(v23 + 8) == 8 )
                  v73 = 3;
                *(_DWORD *)v49 = v73;
              }
              else if ( v72 == 31 )
              {
                *v51 = 4;
                *v50 = 0;
                *(_DWORD *)v49 = 0;
              }
              else
              {
                if ( (unsigned int)(v72 - 32) > 2 )
                  goto LABEL_75;
                *v51 = 4;
                *v50 = 0;
                *(_DWORD *)v49 = *(unsigned __int8 *)(v23 + 121);
              }
              goto LABEL_227;
            case 0x13:
              v74 = (*(_BYTE *)(v23 + 130) & 0x10) == 0;
              goto LABEL_156;
            case 0x14:
              v74 = (*(_BYTE *)(v23 + 130) & 2) == 0;
              goto LABEL_156;
            case 0x15:
              switch ( *(_DWORD *)(v23 + 112) )
              {
                case 1:
                case 2:
                case 4:
                case 5:
                case 0x11:
                case 0x1A:
                case 0x1B:
                case 0x1C:
                case 0x1F:
                case 0x20:
                case 0x21:
                case 0x22:
                  *(_DWORD *)v49 = 4;
                  *v51 = 4;
                  *v50 = 0;
                  break;
                case 3:
                case 6:
                  *(_DWORD *)v49 = 2;
                  *v51 = 4;
                  *v50 = 0;
                  break;
                case 9:
                case 0x1D:
                  *(_DWORD *)v49 = 1;
                  *v51 = 4;
                  *v50 = 0;
                  break;
                default:
                  *(_DWORD *)v49 = 3;
                  *v51 = 4;
                  *v50 = 0;
                  break;
              }
              goto LABEL_227;
            case 0x16:
              v75 = *(_DWORD *)(v23 + 136);
              if ( v75 == 129 || v75 == 130 || v75 == 128 || (unsigned int)FIsVarMaxType((struct BaseMetaInfo *)v23) )
              {
                v74 = (unsigned int)FIsVarMaxType((struct BaseMetaInfo *)v23) == 0;
                v77 = 0;
                if ( v74 )
                  v77 = *(_QWORD *)(v23 + 8);
                *(_QWORD *)v49 = v77;
                if ( v93 )
                {
                  switch ( *(_DWORD *)(v23 + 112) )
                  {
                    case 0x1A:
                      goto LABEL_182;
                    case 0x1B:
                      goto LABEL_181;
                    case 0x1C:
LABEL_182:
                      *(_QWORD *)v49 = 0x7FFFFFFF;
                      break;
                    case 0x1D:
LABEL_181:
                      *(_QWORD *)v49 = 2147483646;
                      break;
                  }
                }
                v21 = this;
                v46 = a4;
                *v50 = 0;
                *v51 = 8;
                goto LABEL_227;
              }
              v46 = a4;
              v74 = v75 == 132;
              v21 = this;
              if ( v74 )
              {
                v76 = *(_QWORD *)(v23 + 8);
                if ( v76 == 0xFFFF )
                  v76 = -1;
                *(_QWORD *)v49 = v76;
                *v50 = 0;
                *v51 = 8;
              }
              else
              {
LABEL_75:
                *v51 = 0;
                *v50 = 3;
              }
              goto LABEL_227;
            case 0x17:
              v74 = (*(_DWORD *)(v23 + 116) & 0x8000) == 0;
LABEL_156:
              if ( v74 )
                *(_WORD *)v49 = 0;
              else
                *(_WORD *)v49 = -1;
              *v51 = 2;
              *v50 = 0;
              goto LABEL_227;
            case 0x18:
              if ( *(_DWORD *)(v23 + 48) || *(_BYTE *)(v23 + 52) )
              {
                *(_DWORD *)v49 = DWCompFlagsFromTDSCollation((struct tagTDSCOLLATION *)(v23 + 48));
                *v51 = 4;
                *v50 = 0;
              }
              else
              {
                *(_QWORD *)v49 = 0;
                *v51 = 0;
                *v50 = 3;
              }
              goto LABEL_227;
            case 0x19:
              if ( *(_DWORD *)(v23 + 48) || *(_BYTE *)(v23 + 52) )
              {
                *(_DWORD *)v49 = *(unsigned __int8 *)(v23 + 52);
                *v51 = 4;
                *v50 = 0;
              }
              else
              {
                *(_QWORD *)v49 = 0;
                *v51 = 0;
                *v50 = 3;
              }
              goto LABEL_227;
            case 0x1A:
              *(_DWORD *)v49 = *(unsigned __int8 *)(v23 + 122);
              *v51 = 4;
              *v50 = 0;
              goto LABEL_227;
            case 0x1B:
              if ( *(_DWORD *)(v23 + 48) || *(_BYTE *)(v23 + 52) )
              {
                *(_DWORD *)v49 = *(_DWORD *)(v23 + 48);
                v49[4] = *(_BYTE *)(v23 + 52);
                *v51 = 5;
                *v50 = 0;
              }
              else
              {
                *(_QWORD *)v49 = 0;
                *v51 = 0;
                *v50 = 3;
              }
              goto LABEL_227;
            case 0x1C:
              if ( v91 && v41 )
              {
                v38 = v90;
                v68 = 2 * v41;
LABEL_132:
                v69 = (char *)v46 + v48[23];
                *v51 = v68;
                memcpy(v69, v38, v68);
                v46 = a4;
                *(_WORD *)&v49[v68] = 0;
                v21 = this;
                *v50 = 0;
              }
              else
              {
LABEL_82:
                *(_WORD *)v49 = 0;
                *v51 = 0;
                *v50 = 3;
              }
              goto LABEL_227;
            case 0x1D:
              if ( *(_QWORD *)(v23 + 232) && *(_DWORD *)(v23 + 112) == 29 )
                goto LABEL_200;
              goto LABEL_202;
            case 0x1E:
              if ( *(_QWORD *)(v23 + 248)
                && *(_DWORD *)(v23 + 112) == 29
                && !*(_WORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v21 + 66) + 528LL) + 200LL)
                                                     + 344LL)
                                         + 40LL)
                             + 880LL) )
              {
                goto LABEL_206;
              }
              goto LABEL_202;
            case 0x1F:
              if ( *(_DWORD *)(v23 + 136) != 141
                || !*(_QWORD *)(v23 + 264)
                || *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v21 + 66) + 528LL) + 200LL)
                                                    + 344LL)
                                        + 40LL)
                            + 880LL) )
              {
                goto LABEL_202;
              }
              v80 = (char *)v46 + v48[23];
              *v51 = *(unsigned __int16 *)(v23 + 256);
              *v50 = 0;
              memcpy(
                v80,
                (const void *)(*(_QWORD *)(v23 + 264) + *((_QWORD *)v21 + 115)),
                *(unsigned __int16 *)(v23 + 256));
              v46 = a4;
              goto LABEL_227;
            case 0x20:
              if ( *(_DWORD *)(v23 + 136) != 132 || !*(_QWORD *)(v23 + 232) )
                goto LABEL_202;
LABEL_200:
              if ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v21 + 66) + 528LL) + 200LL)
                                                    + 344LL)
                                        + 40LL)
                            + 880LL) )
              {
LABEL_202:
                *v51 = 0;
                *v50 = 3;
                *(_QWORD *)v49 = 0;
              }
              else
              {
                v78 = (char *)v46 + v48[23];
                *v51 = *(unsigned __int16 *)(v23 + 224);
                *v50 = 0;
                memcpy(
                  v78,
                  (const void *)(*(_QWORD *)(v23 + 232) + *((_QWORD *)v21 + 115)),
                  *(unsigned __int16 *)(v23 + 224));
                v46 = a4;
              }
              goto LABEL_227;
            case 0x21:
              if ( *(_DWORD *)(v23 + 136) != 132
                || !*(_QWORD *)(v23 + 248)
                || *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v21 + 66) + 528LL) + 200LL)
                                                    + 344LL)
                                        + 40LL)
                            + 880LL) )
              {
                goto LABEL_202;
              }
LABEL_206:
              v79 = (char *)v46 + v48[23];
              *v51 = *(unsigned __int16 *)(v23 + 240);
              *v50 = 0;
              memcpy(
                v79,
                (const void *)(*(_QWORD *)(v23 + 248) + *((_QWORD *)v21 + 115)),
                *(unsigned __int16 *)(v23 + 240));
              v46 = a4;
              goto LABEL_227;
            case 0x22:
              if ( *(_DWORD *)(v23 + 136) != 132
                || !*(_QWORD *)(v23 + 280)
                || *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v21 + 66) + 528LL) + 200LL)
                                                    + 344LL)
                                        + 40LL)
                            + 880LL) )
              {
                goto LABEL_202;
              }
              v81 = (char *)v46 + v48[23];
              *v51 = *(unsigned __int16 *)(v23 + 272);
              *v50 = 0;
              memcpy(
                v81,
                (const void *)(*(_QWORD *)(v23 + 280) + *((_QWORD *)v21 + 115)),
                *(unsigned __int16 *)(v23 + 272));
              v46 = a4;
              goto LABEL_227;
            case 0x23:
              if ( *(_DWORD *)(v23 + 136) == 132
                && *(_QWORD *)(v23 + 296)
                && !*(_WORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v21 + 66) + 528LL) + 200LL)
                                                     + 344LL)
                                         + 40LL)
                             + 880LL) )
              {
                v82 = (char *)v46 + v48[23];
                *v51 = *(unsigned __int16 *)(v23 + 288);
                *v50 = 0;
                memcpy(
                  v82,
                  (const void *)(*(_QWORD *)(v23 + 296) + *((_QWORD *)v21 + 115)),
                  *(unsigned __int16 *)(v23 + 288));
                v46 = a4;
              }
              else
              {
                *v51 = 0;
                *v50 = 3;
                *(_QWORD *)v49 = 0;
              }
              goto LABEL_227;
            default:
              if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
                bidTraceW(off_383B43340[0], 1606697, off_383B49128[0], 2147942487LL);
              return 2147942487LL;
          }
        }
      }
LABEL_228:
      v22 = v95 + 1;
      v23 += 304;
      ++v95;
      ++v97;
      a4 = (struct tagRowBuff *)((char *)v46 + *(unsigned int *)(v12 + 32));
      if ( v97 >= v98 )
        return v89;
    }
  }
  if ( (bidGblFlags & 2) != 0 )
    bidTraceHR(off_383B43340[0], 779273, v15);
  return v15;
}

```

## disassembly

```asm
0x383a032f0  push    rbx
0x383a032f2  push    rbp
0x383a032f3  push    rdi
0x383a032f4  push    r15
0x383a032f6  sub     rsp, 238h
0x383a032fd  mov     rax, cs:__security_cookie
0x383a03304  xor     rax, rsp
0x383a03307  mov     [rsp+258h+var_48], rax
0x383a0330f  mov     rdi, rcx
0x383a03312  mov     rbx, r8
0x383a03315  mov     [rsp+258h+var_220], rcx
0x383a0331a  mov     r11, [rdi+210h]
0x383a03321  xor     ecx, ecx
0x383a03323  mov     [rsp+258h+var_228], r9
0x383a03328  mov     rax, [r11+210h]
0x383a0332f  mov     rbp, rdx
0x383a03332  mov     r15d, ecx
0x383a03335  mov     r10, [rax+0C8h]
0x383a0333c  mov     rax, [r10+158h]
0x383a03343  mov     r10d, ecx
0x383a03346  mov     r8, [rax+28h]
0x383a0334a  mov     rax, [rdi+278h]
0x383a03351  cmp     word ptr [r8+370h], 50h ; 'P'
0x383a0335a  setz    r10b
0x383a0335e  test    rax, rax
0x383a03361  jz      loc_383A04420
0x383a03367  cmp     [rdi+340h], rax
0x383a0336e  jg      loc_383A04420
0x383a03374  mov     [rsp+258h+arg_8], rsi
0x383a0337c  mov     [rsp+258h+var_30], r13
0x383a03384  mov     [rsp+258h+var_200], rcx
0x383a03389  mov     [rsp+258h+var_38], r14
0x383a03391  mov     r13d, ecx
0x383a03394  mov     [rsp+258h+var_208], rcx
0x383a03399  mov     [rsp+258h+var_1E0], rcx
0x383a0339e  mov     [rsp+258h+var_1F0], rcx
0x383a033a3  mov     [rsp+258h+var_210], rcx
0x383a033a8  mov     [rsp+258h+var_1D0], rcx
0x383a033b0  mov     [rsp+258h+var_218], rcx
0x383a033b5  cmp     [r11+1A8h], rcx
0x383a033bc  jnz     short loc_383A033D8
0x383a033be  mov     rax, [r11+2C0h]
0x383a033c5  test    rax, rax
0x383a033c8  jz      short loc_383A033D8
0x383a033ca  mov     rax, [rax+798h]
0x383a033d1  mov     [r11+1A8h], rax
0x383a033d8  mov     r14, [r11+1A8h]
0x383a033df  mov     [rsp+258h+var_1C0], r14
0x383a033e7  test    r14, r14
0x383a033ea  jz      short loc_383A033FB
0x383a033ec  mov     eax, 2000h
0x383a033f1  test    [r11+248h], ax
0x383a033f9  jz      short loc_383A0340A
0x383a033fb  lea     r14, [r11+140h]
0x383a03402  mov     [rsp+258h+var_1C0], r14
0x383a0340a  mov     rax, [rdi+210h]
0x383a03411  xor     r11d, r11d
0x383a03414  mov     edx, 81h
0x383a03419  mov     r9, [rax+210h]
0x383a03420  lea     rax, [rsp+258h+Src]
0x383a03428  lea     rcx, [rsp+258h+Src]
0x383a03430  add     r9, 2F2h
0x383a03437  mov     esi, r11d
0x383a0343a  mov     [rsp+258h+var_1F8], r11d
0x383a0343f  sub     r9, rax
0x383a03442  mov     r8d, r11d
0x383a03445  nop     word ptr [rax+rax+00000000h]
0x383a03450  lea     rax, [rdx+7FFFFF7Dh]
0x383a03457  test    rax, rax
0x383a0345a  jz      short loc_383A03477
0x383a0345c  movzx   eax, word ptr [rcx+r9]
0x383a03461  test    ax, ax
0x383a03464  jz      short loc_383A03477
0x383a03466  mov     [rcx], ax
0x383a03469  add     rcx, 2
0x383a0346d  inc     r8
0x383a03470  dec     rdx
0x383a03473  jnz     short loc_383A03450
0x383a03475  jmp     short loc_383A0347C
0x383a03477  test    rdx, rdx
0x383a0347a  jnz     short loc_383A0348C
0x383a0347c  mov     esi, 8007007Ah
0x383a03481  sub     rcx, 2
0x383a03485  dec     r8
0x383a03488  mov     [rsp+258h+var_1F8], esi
0x383a0348c  lea     rax, [rsp+258h+Src]
0x383a03494  mov     [rcx], r11w
0x383a03498  lea     rax, [rax+r8*2]
0x383a0349c  test    esi, esi
0x383a0349e  jns     short loc_383A034A8
0x383a034a0  cmp     esi, 8007007Ah
0x383a034a6  jnz     short loc_383A034AB
0x383a034a8  mov     r15, rax
0x383a034ab  test    esi, esi
0x383a034ad  jns     short loc_383A034D3
0x383a034af  test    byte ptr cs:_bidGblFlags, 2
0x383a034b6  jz      short loc_383A034CC
0x383a034b8  mov     rcx, cs:off_383B43340; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a034bf  mov     r8d, esi
0x383a034c2  mov     edx, 0BE409h
0x383a034c7  call    _bidTraceHR
0x383a034cc  mov     eax, esi
0x383a034ce  jmp     loc_383A043E1
0x383a034d3  lea     rax, [rsp+258h+Src]
0x383a034db  mov     [rsp+258h+var_28], r12
0x383a034e3  sub     r15, rax
0x383a034e6  mov     rax, [rdi+278h]
0x383a034ed  sub     rax, [rdi+340h]
0x383a034f4  sar     r15, 1
0x383a034f7  inc     rax
0x383a034fa  mov     [rsp+258h+var_1A8], r15
0x383a03502  cmp     rbp, rax
0x383a03505  cmovnb  rbp, rax
0x383a03509  mov     [rbx], rbp
0x383a0350c  mov     rbx, rdi
0x383a0350f  mov     [rsp+258h+var_1B0], rbp
0x383a03517  mov     r12, [rbx+340h]
0x383a0351e  mov     r15, r12
0x383a03521  mov     [rsp+258h+var_1C8], r12
0x383a03529  imul    r15, 130h
0x383a03530  add     r15, [rbx+360h]
0x383a03537  cmp     [rbx+374h], r11d
0x383a0353e  jz      short loc_383A03547
0x383a03540  sub     r15, 130h
0x383a03547  movsxd  rax, r10d
0x383a0354a  mov     [rsp+258h+var_1B8], r11
0x383a03552  mov     [rsp+258h+var_1D8], rax
0x383a0355a  test    rbp, rbp
0x383a0355d  jz      loc_383A0441C
0x383a03563  or      rbp, 0FFFFFFFFFFFFFFFFh
0x383a03567  cmp     qword ptr [r15+68h], 0
0x383a0356c  ja      short loc_383A035A5
0x383a0356e  movzx   eax, byte ptr [r15+7Ah]
0x383a03573  test    al, al
0x383a03575  jz      short loc_383A035A5
0x383a03577  mov     r8, [rbx+368h]
0x383a0357e  test    r8, r8
0x383a03581  jz      short loc_383A035A5
0x383a03583  movzx   eax, al
0x383a03586  lea     ecx, [rax+rax*4]
0x383a03589  mov     rax, [r8+20h]
0x383a0358d  lea     r8d, [rbp+29h]; Size
0x383a03591  movsxd  rdx, ecx
0x383a03594  lea     rcx, [r15+48h]; void *
0x383a03598  lea     rdx, [rax+rdx*8]; Src
0x383a0359c  call    cs:__imp_memmove
0x383a035a2  xor     r11d, r11d
0x383a035a5  mov     r10, [r15+68h]
0x383a035a9  mov     rax, [r15+60h]
0x383a035ad  mov     rcx, [r15+58h]
0x383a035b1  mov     r8, [r15+50h]
0x383a035b5  mov     r9, [r15+48h]
0x383a035b9  mov     [rsp+258h+var_1E8], r10
0x383a035be  test    r10, r10
0x383a035c1  jz      loc_383A03804
0x383a035c7  mov     rdx, [rbx+398h]
0x383a035ce  lea     rdi, [rdx+r10]
0x383a035d2  test    rax, rax
0x383a035d5  jnz     loc_383A0375C
0x383a035db  test    rcx, rcx
0x383a035de  jnz     loc_383A0375C
0x383a035e4  test    r8, r8
0x383a035e7  jnz     loc_383A0375C
0x383a035ed  test    r9, r9
0x383a035f0  jnz     loc_383A0375C
0x383a035f6  mov     [rsp+258h+var_1F0], r11
0x383a035fb  mov     [rsp+258h+var_218], r11
0x383a03600  mov     [rsp+258h+var_1E0], r11
0x383a03605  mov     [rsp+258h+var_1D0], r11
0x383a0360d  mov     [rsp+258h+var_208], r11
0x383a03612  mov     [rsp+258h+var_210], r11
0x383a03617  mov     [rsp+258h+var_200], r11
0x383a0361c  mov     r13, r11
0x383a0361f  mov     rbx, rbp
0x383a03622  inc     rbx
0x383a03625  cmp     word ptr [rdi+rbx*2], 0
0x383a0362a  jnz     short loc_383A03622
0x383a0362c  mov     esi, r11d
0x383a0362f  mov     rbp, r11
0x383a03632  mov     eax, 2Eh ; '.'
0x383a03637  nop     word ptr [rax+rax+00000000h]
0x383a03640  mov     [rsp+rbp*8+258h+var_1A0], rdi
0x383a03648  cmp     ax, [rdi]
0x383a0364b  jnz     short loc_383A03657
0x383a0364d  mov     [rsp+rbp*8+258h+var_180], r11
0x383a03655  jmp     short loc_383A03690
0x383a03657  mov     edx, eax; Ch
0x383a03659  mov     rcx, rdi; Str
0x383a0365c  call    cs:__imp_wcschr
0x383a03662  test    rax, rax
0x383a03665  jz      short loc_383A03677
0x383a03667  sub     rax, rdi
0x383a0366a  sar     rax, 1
0x383a0366d  mov     [rsp+rbp*8+258h+var_180], rax
0x383a03675  jmp     short loc_383A03682
0x383a03677  mov     rax, rbx
0x383a0367a  mov     [rsp+rbp*8+258h+var_180], rbx
0x383a03682  sub     rbx, rax
0x383a03685  xor     r11d, r11d
0x383a03688  lea     rdi, [rdi+rax*2]
0x383a0368c  lea     eax, [r11+2Eh]
0x383a03690  test    rbx, rbx
0x383a03693  jz      short loc_383A036BC
0x383a03695  inc     esi
0x383a03697  inc     rbp
0x383a0369a  add     rdi, 2
0x383a0369e  dec     rbx
0x383a036a1  cmp     esi, 4
0x383a036a4  jl      short loc_383A03640
0x383a036a6  mov     rbx, [rsp+258h+var_220]
0x383a036ab  mov     rdx, r13
0x383a036ae  mov     r8, r13
0x383a036b1  mov     r11, rdx
0x383a036b4  mov     r10, r13
0x383a036b7  jmp     loc_383A03818
0x383a036bc  cmp     esi, 4
0x383a036bf  jge     short loc_383A036A6
0x383a036c1  mov     rdx, [rsp+rbp*8+258h+var_1A0]
0x383a036c9  mov     r13, [rsp+rbp*8+258h+var_180]
0x383a036d1  mov     [rsp+258h+var_200], rdx
0x383a036d6  dec     esi
0x383a036d8  jz      short loc_383A03727
0x383a036da  dec     esi
0x383a036dc  jz      short loc_383A03705
0x383a036de  dec     esi
0x383a036e0  jnz     loc_383A037E8
0x383a036e6  mov     rax, [rsp+258h+var_180]
0x383a036ee  test    rax, rax
0x383a036f1  jz      short loc_383A03705
0x383a036f3  mov     rcx, [rsp+258h+var_1A0]
0x383a036fb  mov     [rsp+258h+var_218], rax
0x383a03700  mov     [rsp+258h+var_1F0], rcx
0x383a03705  mov     rax, [rsp+rbp*8+258h+var_190]
0x383a0370d  test    rax, rax
0x383a03710  jz      short loc_383A03727
0x383a03712  mov     rsi, [rsp+rbp*8+258h+var_1B0]
0x383a0371a  mov     [rsp+258h+var_1D0], rax
0x383a03722  mov     [rsp+258h+var_1E0], rsi
0x383a03727  mov     rax, [rsp+rbp*8+258h+var_188]
0x383a0372f  mov     rbx, [rsp+258h+var_220]
0x383a03734  mov     r10, [rsp+258h+var_218]
0x383a03739  test    rax, rax
0x383a0373c  jz      loc_383A037FA
0x383a03742  mov     r11, [rsp+rbp*8+258h+var_1A8]
0x383a0374a  mov     r8, rax
0x383a0374d  mov     [rsp+258h+var_210], rax
0x383a03752  mov     [rsp+258h+var_208], r11
0x383a03757  jmp     loc_383A03818
0x383a0375c  add     rax, rdx
0x383a0375f  mov     r10, rbp
0x383a03762  mov     [rsp+258h+var_1F0], rax
0x383a03767  nop     word ptr [rax+rax+00000000h]
0x383a03770  inc     r10
0x383a03773  cmp     word ptr [rax+r10*2], 0
0x383a03779  jnz     short loc_383A03770
0x383a0377b  lea     rsi, [rdx+rcx]
0x383a0377f  mov     [rsp+258h+var_218], r10
0x383a03784  mov     r14, rbp
0x383a03787  mov     [rsp+258h+var_1E0], rsi
0x383a0378c  nop     dword ptr [rax+00h]
0x383a03790  inc     r14
0x383a03793  cmp     word ptr [rsi+r14*2], 0
0x383a03799  jnz     short loc_383A03790
0x383a0379b  lea     r11, [rdx+r8]
0x383a0379f  mov     [rsp+258h+var_1D0], r14
0x383a037a7  mov     r8, rbp
0x383a037aa  mov     [rsp+258h+var_208], r11
0x383a037af  nop
0x383a037b0  inc     r8
0x383a037b3  cmp     word ptr [r11+r8*2], 0
0x383a037b9  jnz     short loc_383A037B0
0x383a037bb  lea     r14, [rdx+r9]
0x383a037bf  mov     [rsp+258h+var_210], r8
0x383a037c4  mov     r13, rbp
0x383a037c7  mov     [rsp+258h+var_200], r14
0x383a037cc  nop     dword ptr [rax+00h]
0x383a037d0  inc     r13
0x383a037d3  cmp     word ptr [r14+r13*2], 0
0x383a037d9  jnz     short loc_383A037D0
0x383a037db  mov     rdx, r14
0x383a037de  mov     r14, [rsp+258h+var_1C0]
0x383a037e6  jmp     short loc_383A03818
0x383a037e8  mov     r8, [rsp+258h+var_210]
0x383a037ed  mov     rbx, [rsp+258h+var_220]
0x383a037f2  mov     r10, r8
0x383a037f5  mov     r11, r8
0x383a037f8  jmp     short loc_383A03818
0x383a037fa  mov     r8, [rsp+258h+var_210]
0x383a037ff  mov     r11, r8
0x383a03802  jmp     short loc_383A03818
0x383a03804  mov     r8, [rsp+258h+var_210]
0x383a03809  mov     r10, [rsp+258h+var_218]
0x383a0380e  mov     rdx, [rsp+258h+var_200]
0x383a03813  mov     r11, [rsp+258h+var_208]
0x383a03818  mov     r9, [rsp+258h+var_228]
0x383a0381d  mov     ecx, 1
0x383a03822  xor     eax, eax
0x383a03824  mov     [r9+80h], r12
0x383a0382b  mov     [r9+20h], ecx
0x383a0382f  mov     [r9+78h], eax
  ... truncated ...
```
