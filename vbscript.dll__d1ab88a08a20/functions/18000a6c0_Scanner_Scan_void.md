# Scanner::Scan(void)

- ea: `0x18000a6c0`
- end: `0x18000b318`
- name: `?Scan@Scanner@@QEAA?AW4tokens@@XZ`
- size: `3160`
- prototype: ``
- caller_count: `22`
- callee_count: `8`
- tags: ``

## callers

- `0x180007ee0`
- `0x180008b70`
- `0x180008ee0`
- `0x1800095c0`
- `0x18000b320`
- `0x18002dbf4`
- `0x18002dc3c`
- `0x18002dc68`
- `0x18002dea8`
- `0x18002e740`
- `0x18002f95c`
- `0x18002fdac`
- `0x180030050`
- `0x180030808`
- `0x1800344c8`
- `0x180050688`
- `0x18005e268`
- `0x18005e374`
- `0x18005e69c`
- `0x18005e8d0`
- `0x18005ea88`
- `0x18005fb58`

## callees

- `0x18000a6c0`
- `0x18000c2a0`
- `0x1800305f0`
- `0x1800319a0`
- `0x180042688`
- `0x180042738`
- `0x180042bc4`
- `0x180043b30`

## import_xrefs

- `msvcrt!realloc` at `0x18000acc0`
- `msvcrt!realloc` at `0x18000afcd`
- `msvcrt!realloc` at `0x18000acc0`
- `msvcrt!realloc` at `0x18000afcd`
- `msvcrt!malloc` at `0x18000ab9c`
- `msvcrt!malloc` at `0x18000aee7`
- `msvcrt!malloc` at `0x18000ab9c`
- `msvcrt!malloc` at `0x18000aee7`

## pseudocode

```c
__int64 __fastcall Scanner::Scan(__int64 a1)
{
  __int64 v1; // r8
  int v3; // ebp
  int v4; // edx
  const unsigned __int16 *v5; // r10
  __int64 v6; // rdx
  __int64 v7; // r9
  const unsigned __int16 *v8; // rsi
  char v9; // cl
  unsigned int v10; // r11d
  unsigned int v11; // edi
  _BYTE *v12; // rdx
  unsigned __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 result; // rax
  unsigned __int16 *v17; // rax
  __int64 v18; // rcx
  unsigned __int16 *v19; // r8
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rax
  _WORD *v23; // rcx
  _BYTE *v24; // rdx
  unsigned __int64 v25; // rdi
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  _WORD *v29; // rdx
  _WORD *v30; // rcx
  int i; // r8d
  int *v32; // rbp
  unsigned __int16 *v33; // rcx
  _QWORD *v34; // r9
  int v35; // esi
  struct Ident *v36; // rax
  unsigned int v37; // edx
  void *v38; // rcx
  int v39; // edi
  char *v40; // rax
  _WORD *v41; // rcx
  __int64 v42; // rdx
  _WORD *v43; // rcx
  __int64 v44; // rdx
  __int16 *v45; // rcx
  __int16 v46; // dx
  _DWORD *v47; // rax
  unsigned __int16 *v48; // r8
  __int16 v49; // r9
  unsigned __int16 v50; // cx
  unsigned __int16 *v51; // rdx
  __int64 v52; // r8
  _DWORD *v53; // rdx
  int v54; // r9d
  int v55; // r9d
  __int64 v56; // rax
  char *v57; // rax
  int v58; // eax
  unsigned int *v59; // rcx
  bool v60; // zf
  __int64 v61; // r8

  v1 = *(_DWORD *)(a1 + 80) & 0xFFFFFFFE;
  *(_DWORD *)(a1 + 80) = v1;
  v3 = 1024;
  while ( 1 )
  {
    while ( 1 )
    {
      v4 = *(_DWORD *)(a1 + 64);
      if ( (v4 & 0x10) != 0 && *(int *)(a1 + 68) <= (__int64)(*(_QWORD *)(a1 + 40) - *(_QWORD *)(a1 + 16)) >> 1 )
      {
        result = 184;
        **(_DWORD **)(a1 + 8) = 184;
        return result;
      }
      v5 = *(const unsigned __int16 **)(a1 + 40);
      v6 = v4 & 0xFFFFFFDF;
      *(_DWORD *)(a1 + 64) = v6;
      *(_QWORD *)(a1 + 32) = v5;
      v7 = *v5;
      v8 = v5 + 1;
      *(_QWORD *)(a1 + 40) = v5 + 1;
      if ( (unsigned __int16)v7 >= 0x80u )
      {
        v9 = 0;
        v10 = v7;
        v11 = v7;
LABEL_7:
        switch ( v9 )
        {
          case 1:
            v47 = *(_DWORD **)(a1 + 8);
            *(_QWORD *)(a1 + 40) = v5;
            *v47 = 184;
            return 184;
          case 3:
            return Scanner::ScanNumericConstant(a1, v10, 1);
          case 5:
            if ( v11 == 13 && *v8 == 10 )
              *(_QWORD *)(a1 + 40) = v5 + 2;
            if ( (v6 & 8) != 0 )
              goto LABEL_13;
            v12 = *(_BYTE **)(a1 + 368);
            v13 = *(_QWORD *)(a1 + 376);
            if ( (unsigned __int64)(v12 + 5) <= v13 )
              goto LABEL_11;
            v56 = *(_QWORD *)(a1 + 360);
            if ( v56 )
            {
              v3 = 2 * (v13 - v56);
              v57 = (char *)realloc(*(void **)(a1 + 360), v3);
            }
            else
            {
              v57 = (char *)malloc(0x400u);
            }
            if ( !v57 )
              goto LABEL_156;
            *(_QWORD *)(a1 + 368) += &v57[-*(_QWORD *)(a1 + 360)];
            v12 = *(_BYTE **)(a1 + 368);
            *(_QWORD *)(a1 + 360) = v57;
            *(_QWORD *)(a1 + 376) = &v57[v3];
LABEL_11:
            v14 = (__int64)(*(_QWORD *)(a1 + 40) - *(_QWORD *)(a1 + 24)) >> 1;
            if ( (v14 & 0xFFFFFF80) != 0 )
            {
              if ( (v14 & 0xFFFFC000) != 0 )
              {
                if ( (v14 & 0xFFE00000) != 0 )
                {
                  if ( (v14 & 0xF0000000) != 0 )
                  {
                    *v12 = ((int)v14 >> 28) & 0xF;
                    v12 = (_BYTE *)++*(_QWORD *)(a1 + 368);
                  }
                  *v12 = ((int)v14 >> 21) & 0x7F;
                  v12 = (_BYTE *)++*(_QWORD *)(a1 + 368);
                }
                *v12 = ((int)v14 >> 14) & 0x7F;
                v12 = (_BYTE *)++*(_QWORD *)(a1 + 368);
              }
              *v12 = ((int)v14 >> 7) & 0x7F;
              v12 = (_BYTE *)++*(_QWORD *)(a1 + 368);
            }
            *v12 = v14 | 0x80;
            v15 = *(_QWORD *)(a1 + 24);
            ++*(_QWORD *)(a1 + 368);
            ++*(_DWORD *)(a1 + 384);
            *(_QWORD *)(a1 + 48) = v15;
            *(_QWORD *)(a1 + 24) = *(_QWORD *)(a1 + 40);
LABEL_13:
            result = 183;
            **(_DWORD **)(a1 + 8) = 183;
            return result;
          case 7:
            result = 174;
            **(_DWORD **)(a1 + 8) = 174;
            return result;
          case 10:
            v58 = Scanner::ScanDateConstant(a1, v6, v1);
            v59 = *(unsigned int **)(a1 + 8);
            if ( v58 )
              return *v59;
            *v59 = 159;
            return 159;
          case 11:
            result = 179;
            **(_DWORD **)(a1 + 8) = 179;
            return result;
          case 12:
            goto LABEL_55;
          case 13:
            if ( (v6 & 2) != 0 )
            {
LABEL_55:
              *(_DWORD *)(a1 + 88) = 0;
              for ( i = 0; ; i = *(_DWORD *)(a1 + 88) )
              {
                v32 = (int *)(a1 + 84);
                while ( 1 )
                {
                  v33 = *(unsigned __int16 **)(a1 + 40);
                  v34 = (_QWORD *)(a1 + 96);
                  v35 = *v33;
                  *(_QWORD *)(a1 + 40) = v33 + 1;
                  if ( v35 == v11 )
                    break;
                  if ( !(_WORD)v35 || v35 == 13 || v35 == 10 )
                  {
                    v60 = (*(_BYTE *)(a1 + 64) & 8) == 0;
                    *(_QWORD *)(a1 + 40) = v33;
                    if ( v60 )
                      Scanner::Error((Scanner *)a1, 1033);
                    v37 = 180;
                    **(_DWORD **)(a1 + 8) = 180;
                    return v37;
                  }
                  if ( i >= *v32 )
                    Scanner::GrowBuf((Scanner *)a1);
                  *(_WORD *)(*(_QWORD *)(a1 + 96) + 2LL * (int)(*(_DWORD *)(a1 + 88))++) = v35;
                  i = *(_DWORD *)(a1 + 88);
                }
                if ( v33[1] != v11 )
                  break;
                *(_QWORD *)(a1 + 40) = v33 + 2;
                if ( i >= *v32 )
                {
                  Scanner::GrowBuf((Scanner *)a1);
                  v34 = (_QWORD *)(a1 + 96);
                }
                *(_WORD *)(*v34 + 2LL * (int)(*(_DWORD *)(a1 + 88))++) = v35;
              }
              if ( (*(_BYTE *)(a1 + 64) & 8) == 0 )
              {
                v36 = HashTbl::PidHashNameLen(*(HashTbl **)a1, *(const unsigned __int16 **)(a1 + 96), i, 1);
                v37 = 187;
                *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = v36;
                **(_DWORD **)(a1 + 8) = 187;
                return v37;
              }
              *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = 0;
              **(_DWORD **)(a1 + 8) = 187;
              return 187;
            }
            else
            {
              if ( (v6 & 8) != 0 )
                goto LABEL_96;
              result = 156;
              **(_DWORD **)(a1 + 8) = 156;
            }
            return result;
          case 15:
            if ( *v8 != 57 )
            {
              switch ( *v8 )
              {
                case '0':
                case '1':
                case '2':
                case '3':
                case '4':
                case '5':
                case '6':
                case '7':
                case '8':
                case 'H':
                case 'O':
                case 'h':
                case 'o':
                  break;
                default:
                  goto LABEL_51;
              }
            }
            if ( (unsigned int)Scanner::ScanNumericConstant(a1, v11, 0) )
              return **(unsigned int **)(a1 + 8);
LABEL_51:
            result = 160;
            **(_DWORD **)(a1 + 8) = 160;
            return result;
          case 16:
            result = 176;
            **(_DWORD **)(a1 + 8) = 176;
            return result;
          case 17:
            result = 151;
            **(_DWORD **)(a1 + 8) = 151;
            return result;
          case 18:
            result = 170;
            **(_DWORD **)(a1 + 8) = 170;
            return result;
          case 19:
            if ( (v6 & 1) == 0 )
              goto LABEL_76;
            v53 = *(_DWORD **)(a1 + 8);
            if ( *v53 != 183 || *v8 != 45 )
              goto LABEL_76;
            v54 = 1;
            if ( v5[2] == 45 )
            {
              do
                ++v54;
              while ( v8[v54] == 45 );
            }
            if ( v8[v54] == 62 )
            {
              v55 = v54 + 1;
              if ( v55 > 0 )
              {
                do
                {
                  --v55;
                  ++v8;
                }
                while ( v55 > 0 );
                *(_QWORD *)(a1 + 40) = v8;
              }
              *v53 = 116;
              return 116;
            }
            else
            {
LABEL_76:
              result = 171;
              **(_DWORD **)(a1 + 8) = 171;
            }
            return result;
          case 20:
            result = 172;
            **(_DWORD **)(a1 + 8) = 172;
            return result;
          case 21:
            if ( (v6 & 1) != 0 && *v8 == 47 )
            {
              *(_QWORD *)(a1 + 40) = v5 + 2;
              **(_DWORD **)(a1 + 8) = 116;
              return 116;
            }
            else
            {
              result = 173;
              **(_DWORD **)(a1 + 8) = 173;
            }
            return result;
          case 22:
            result = 175;
            **(_DWORD **)(a1 + 8) = 175;
            return result;
          case 23:
            result = 155;
            **(_DWORD **)(a1 + 8) = 155;
            return result;
          case 24:
            if ( !(unsigned int)Scanner::ScanNumericConstant(a1, v10, 0) )
              **(_DWORD **)(a1 + 8) = 178;
            return **(unsigned int **)(a1 + 8);
          case 25:
            **(_DWORD **)(a1 + 8) = 161;
            v41 = *(_WORD **)(a1 + 40);
            if ( *v41 == 61 )
            {
              *(_QWORD *)(a1 + 40) = v41 + 1;
              **(_DWORD **)(a1 + 8) = 162;
            }
            else if ( *v41 == 62 )
            {
              *(_QWORD *)(a1 + 40) = v41 + 1;
              **(_DWORD **)(a1 + 8) = 163;
            }
            goto LABEL_81;
          case 26:
            **(_DWORD **)(a1 + 8) = 164;
            v30 = *(_WORD **)(a1 + 40);
            if ( *v30 == 60 )
            {
              *(_QWORD *)(a1 + 40) = v30 + 1;
              **(_DWORD **)(a1 + 8) = 165;
            }
            else if ( *v30 == 62 )
            {
              *(_QWORD *)(a1 + 40) = v30 + 1;
              **(_DWORD **)(a1 + 8) = 166;
            }
            return **(unsigned int **)(a1 + 8);
          case 27:
            **(_DWORD **)(a1 + 8) = 167;
            v43 = *(_WORD **)(a1 + 40);
            if ( *v43 == 60 )
            {
              *(_QWORD *)(a1 + 40) = v43 + 1;
              **(_DWORD **)(a1 + 8) = 168;
            }
            else if ( *v43 == 61 )
            {
              *(_QWORD *)(a1 + 40) = v43 + 1;
              **(_DWORD **)(a1 + 8) = 169;
            }
            return **(unsigned int **)(a1 + 8);
          case 28:
            if ( (v6 & 4) == 0 )
              goto LABEL_172;
            result = 182;
            **(_DWORD **)(a1 + 8) = 182;
            return result;
          case 29:
            if ( (v6 & 8) == 0 )
            {
              v48 = (unsigned __int16 *)(v5 + 1);
              v49 = 93;
              while ( 1 )
              {
                v50 = *v48;
                *(_QWORD *)(a1 + 40) = v48 + 1;
                if ( v49 == v50 )
                  break;
                if ( !(unsigned int)FValidBracketIdCh(v50) )
                {
                  *(_QWORD *)(a1 + 40) = v52;
                  Scanner::Error((Scanner *)a1, 1007);
                }
                v48 = v51;
              }
              v61 = v48 - v8;
              if ( v61 <= 255 )
              {
                *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = HashTbl::PidHashNameLen(*(HashTbl **)a1, v8, v61, 0);
                **(_DWORD **)(a1 + 8) = 149;
                return **(unsigned int **)(a1 + 8);
              }
LABEL_155:
              Scanner::Error((Scanner *)a1, 1030);
            }
            v44 = 1;
            break;
          case 33:
LABEL_81:
            if ( (*(_BYTE *)(a1 + 64) & 1) != 0 )
            {
              v42 = *(_QWORD *)(a1 + 40);
              if ( *(_WORD *)(v42 + 2) == 45 && *(_WORD *)(v42 + 4) == 45 )
              {
                *(_QWORD *)(a1 + 40) = v42 + 6;
                **(_DWORD **)(a1 + 8) = 116;
              }
            }
            return **(unsigned int **)(a1 + 8);
          case 36:
            result = 158;
            **(_DWORD **)(a1 + 8) = 158;
            return result;
          case 37:
            result = 150;
            **(_DWORD **)(a1 + 8) = 150;
            return result;
          default:
LABEL_172:
            if ( (v6 & 8) == 0 )
            {
              *(_QWORD *)(a1 + 40) = v5;
              Scanner::Error((Scanner *)a1, 1032);
            }
            goto LABEL_138;
        }
LABEL_95:
        if ( (unsigned int)Scanner::ScanIdentifier(a1, v44, v1) != 116 )
          return **(unsigned int **)(a1 + 8);
        do
        {
LABEL_96:
          v45 = *(__int16 **)(a1 + 40);
          v46 = *v45;
          *(_QWORD *)(a1 + 40) = v45 + 1;
        }
        while ( v46 && v46 != 10 && v46 != 13 );
        *(_QWORD *)(a1 + 40) = v45;
        result = 181;
        **(_DWORD **)(a1 + 8) = 181;
        return result;
      }
      v9 = *((_BYTE *)&qword_180080C50[8] + v7);
      if ( v9 == 2 )
      {
        *(_QWORD *)(a1 + 40) = v5;
        if ( (v6 & 8) == 0 )
        {
          v17 = (unsigned __int16 *)v5;
          do
          {
            v18 = *v17;
            v19 = v17++;
            *(_QWORD *)(a1 + 40) = v17;
          }
          while ( (unsigned __int16)v18 < 0x80u && (*((_BYTE *)&qword_180080C10 + v18) & 1) != 0 );
          *(_QWORD *)(a1 + 40) = v19;
          v20 = v19 - v5;
          if ( v20 <= 255 )
          {
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = HashTbl::PidHashNameLen(*(HashTbl **)a1, v5, v20, 0);
            **(_DWORD **)(a1 + 8) = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 8LL);
            v21 = *(_QWORD *)(a1 + 8);
            if ( !*(_DWORD *)v21 || (*(_BYTE *)(*(_QWORD *)(v21 + 8) + 10LL) & 1) == 0 )
              *(_DWORD *)v21 = 149;
            return **(unsigned int **)(a1 + 8);
          }
          goto LABEL_155;
        }
        v44 = 0;
        goto LABEL_95;
      }
      if ( v9 != 4 )
        break;
      v1 = (unsigned int)v1 | 1;
      *(_DWORD *)(a1 + 80) = v1;
      *(_DWORD *)(a1 + 64) = v6 | 0x20;
    }
    v10 = v7;
    v11 = v7;
    if ( v9 != 31 )
      goto LABEL_7;
LABEL_25:
    v22 = *v8;
    v23 = v8 + 1;
    *(_QWORD *)(a1 + 40) = v8 + 1;
    if ( (_WORD)v22 != 13 )
      break;
    if ( *v23 == 10 )
    {
      v23 = v8 + 2;
      *(_QWORD *)(a1 + 40) = v8 + 2;
    }
LABEL_28:
    if ( (v6 & 8) == 0 )
    {
      v24 = *(_BYTE **)(a1 + 368);
      v25 = *(_QWORD *)(a1 + 376);
      if ( (unsigned __int64)(v24 + 5) > v25 )
      {
        v38 = *(void **)(a1 + 360);
        if ( v38 )
        {
          v39 = 2 * (v25 - (_DWORD)v38);
          v40 = (char *)realloc(v38, v39);
        }
        else
        {
          v39 = 1024;
          v40 = (char *)malloc(0x400u);
        }
        if ( !v40 )
LABEL_156:
          Scanner::Error((Scanner *)a1, 1001);
        *(_QWORD *)(a1 + 368) += &v40[-*(_QWORD *)(a1 + 360)];
        v24 = *(_BYTE **)(a1 + 368);
        *(_QWORD *)(a1 + 360) = v40;
        *(_QWORD *)(a1 + 376) = &v40[v39];
      }
      v26 = (__int64)(*(_QWORD *)(a1 + 40) - *(_QWORD *)(a1 + 24)) >> 1;
      if ( (v26 & 0xFFFFFF80) != 0 )
      {
        if ( (v26 & 0xFFFFC000) != 0 )
        {
          if ( (v26 & 0xFFE00000) != 0 )
          {
            if ( (v26 & 0xF0000000) != 0 )
            {
              *v24 = ((int)v26 >> 28) & 0xF;
              v24 = (_BYTE *)++*(_QWORD *)(a1 + 368);
            }
            *v24 = ((int)v26 >> 21) & 0x7F;
            v24 = (_BYTE *)++*(_QWORD *)(a1 + 368);
          }
          *v24 = ((int)v26 >> 14) & 0x7F;
          v24 = (_BYTE *)++*(_QWORD *)(a1 + 368);
        }
        *v24 = ((int)v26 >> 7) & 0x7F;
        v24 = (_BYTE *)++*(_QWORD *)(a1 + 368);
      }
      *v24 = v26 | 0x80;
      v27 = *(_QWORD *)(a1 + 24);
      ++*(_QWORD *)(a1 + 368);
      v23 = *(_WORD **)(a1 + 40);
      ++*(_DWORD *)(a1 + 384);
      *(_QWORD *)(a1 + 48) = v27;
      *(_QWORD *)(a1 + 24) = v23;
    }
    do
    {
      v28 = (unsigned __int16)*v23;
      v29 = v23++;
      *(_QWORD *)(a1 + 40) = v23;
    }
    while ( (unsigned __int16)v28 < 0x80u && *((_BYTE *)&qword_180080C50[8] + v28) == 4 );
    *(_DWORD *)(a1 + 80) &= ~1u;
    v1 = *(unsigned int *)(a1 + 80);
    *(_QWORD *)(a1 + 40) = v29;
  }
  if ( (_WORD)v22 == 10 )
    goto LABEL_28;
  if ( (unsigned __int16)v22 < 0x80u && *((_BYTE *)&qword_180080C50[8] + v22) == 4 )
  {
    ++v8;
    goto LABEL_25;
  }
  *(_QWORD *)(a1 + 40) = v8;
  if ( (v6 & 8) == 0 )
    Scanner::Error((Scanner *)a1, 1032);
LABEL_138:
  **(_DWORD **)(a1 + 8) = 180;
  return 180;
}

```

## disassembly

```asm
0x18000a6c0  mov     [rsp+arg_8], rbx
0x18000a6c5  mov     [rsp+arg_10], rbp
0x18000a6ca  push    rsi
0x18000a6cb  push    r12
0x18000a6cd  push    r13
0x18000a6cf  push    r14
0x18000a6d1  push    r15
0x18000a6d3  sub     rsp, 20h
0x18000a6d7  mov     r8d, [rcx+50h]
0x18000a6db  lea     r15, __ImageBase
0x18000a6e2  and     r8d, 0FFFFFFFEh
0x18000a6e6  mov     [rsp+48h+arg_0], rdi
0x18000a6eb  mov     [rcx+50h], r8d
0x18000a6ef  mov     rbx, rcx
0x18000a6f2  mov     r14d, 80h
0x18000a6f8  mov     ebp, 400h
0x18000a6fd  mov     r12d, 0Dh
0x18000a703  mov     r13d, 0Ah
0x18000a709  mov     edx, [rbx+40h]
0x18000a70c  test    dl, 10h
0x18000a70f  jnz     loc_18000AA42
0x18000a715  mov     r10, [rbx+28h]
0x18000a719  and     edx, 0FFFFFFDFh
0x18000a71c  mov     [rbx+40h], edx
0x18000a71f  mov     [rbx+20h], r10
0x18000a723  movzx   r9d, word ptr [r10]
0x18000a727  lea     rsi, [r10+2]
0x18000a72b  mov     [rbx+28h], rsi
0x18000a72f  cmp     r9w, r14w
0x18000a733  jnb     loc_18000AF96
0x18000a739  movzx   ecx, byte ptr [r9+r15+80C90h]
0x18000a742  cmp     cl, 2
0x18000a745  jz      loc_18000A7FA
0x18000a74b  cmp     cl, 4
0x18000a74e  jz      loc_18000A8AA
0x18000a754  mov     r11d, r9d
0x18000a757  mov     edi, r9d
0x18000a75a  cmp     cl, 1Fh
0x18000a75d  jz      loc_18000A8C0
0x18000a763  movzx   eax, cl
0x18000a766  dec     eax; switch 37 cases
0x18000a768  cmp     eax, 24h
0x18000a76b  ja      def_18000A77E; jumptable 000000018000A77E default case, cases 2,4,6,8,9,14,30-32,34,35
0x18000a771  cdqe
0x18000a773  mov     ecx, ds:(jpt_18000A77E - 180000000h)[r15+rax*4]
0x18000a77b  add     rcx, r15
0x18000a77e  jmp     rcx; switch jump
0x18000a784  cmp     edi, r12d; jumptable 000000018000A77E case 5
0x18000a787  jz      loc_18000A9D9
0x18000a78d  test    dl, 8
0x18000a790  jnz     short loc_18000A7E6
0x18000a792  mov     rdx, [rbx+170h]
0x18000a799  mov     rcx, [rbx+178h]
0x18000a7a0  lea     rax, [rdx+5]
0x18000a7a4  cmp     rax, rcx
0x18000a7a7  ja      loc_18000AED4
0x18000a7ad  mov     rcx, [rbx+28h]
0x18000a7b1  sub     rcx, [rbx+18h]
0x18000a7b5  sar     rcx, 1
0x18000a7b8  test    ecx, 0FFFFFF80h
0x18000a7be  jnz     loc_18000B146
0x18000a7c4  or      cl, r14b
0x18000a7c7  mov     [rdx], cl
0x18000a7c9  mov     rax, [rbx+18h]
0x18000a7cd  inc     qword ptr [rbx+170h]
0x18000a7d4  inc     dword ptr [rbx+180h]
0x18000a7da  mov     [rbx+30h], rax
0x18000a7de  mov     rax, [rbx+28h]
0x18000a7e2  mov     [rbx+18h], rax
0x18000a7e6  mov     rcx, [rbx+8]
0x18000a7ea  mov     eax, 0B7h
0x18000a7ef  mov     dword ptr [rcx], 0B7h
0x18000a7f5  jmp     loc_18000A878
0x18000a7fa  mov     [rbx+28h], r10
0x18000a7fe  test    dl, 8
0x18000a801  jnz     loc_18000AD25
0x18000a807  mov     rax, r10
0x18000a80a  nop     word ptr [rax+rax+00h]
0x18000a810  movzx   ecx, word ptr [rax]
0x18000a813  mov     r8, rax
0x18000a816  add     rax, 2
0x18000a81a  mov     [rbx+28h], rax
0x18000a81e  cmp     cx, r14w
0x18000a822  jb      short loc_18000A896
0x18000a824  mov     [rbx+28h], r8
0x18000a828  sub     r8, r10
0x18000a82b  sar     r8, 1; int
0x18000a82e  cmp     r8, 0FFh
0x18000a835  jg      loc_18000B12A
0x18000a83b  mov     rcx, [rbx]; this
0x18000a83e  xor     r9d, r9d; int
0x18000a841  mov     rdx, r10; unsigned __int16 *
0x18000a844  call    ?PidHashNameLen@HashTbl@@QEAAPEAUIdent@@PEBGJH@Z; HashTbl::PidHashNameLen(ushort const *,long,int)
0x18000a849  mov     rcx, [rbx+8]
0x18000a84d  mov     [rcx+8], rax
0x18000a851  mov     rdx, [rbx+8]
0x18000a855  mov     rax, [rdx+8]
0x18000a859  movzx   ecx, word ptr [rax+8]
0x18000a85d  mov     [rdx], ecx
0x18000a85f  mov     rcx, [rbx+8]
0x18000a863  cmp     dword ptr [rcx], 0
0x18000a866  jnz     loc_18000A965
0x18000a86c  mov     dword ptr [rcx], 95h
0x18000a872  mov     rax, [rbx+8]
0x18000a876  mov     eax, [rax]
0x18000a878  mov     rdi, [rsp+48h+arg_0]
0x18000a87d  mov     rbx, [rsp+48h+arg_8]
0x18000a882  mov     rbp, [rsp+48h+arg_10]
0x18000a887  add     rsp, 20h
0x18000a88b  pop     r15
0x18000a88d  pop     r14
0x18000a88f  pop     r13
0x18000a891  pop     r12
0x18000a893  pop     rsi
0x18000a894  retn
0x18000a896  test    byte ptr [rcx+r15+80C10h], 1
0x18000a89f  jnz     loc_18000A810
0x18000a8a5  jmp     loc_18000A824
0x18000a8aa  or      r8d, 1
0x18000a8ae  or      edx, 20h
0x18000a8b1  mov     [rbx+50h], r8d
0x18000a8b5  mov     [rbx+40h], edx
0x18000a8b8  jmp     loc_18000A709
0x18000a8c0  movzx   eax, word ptr [rsi]
0x18000a8c3  lea     rcx, [rsi+2]
0x18000a8c7  mov     [rbx+28h], rcx
0x18000a8cb  cmp     r12w, ax
0x18000a8cf  jnz     loc_18000B003
0x18000a8d5  cmp     [rcx], r13w
0x18000a8d9  jnz     short loc_18000A8E3
0x18000a8db  add     rcx, 2
0x18000a8df  mov     [rbx+28h], rcx
0x18000a8e3  test    dl, 8
0x18000a8e6  jnz     short loc_18000A93C
0x18000a8e8  mov     rdx, [rbx+170h]
0x18000a8ef  mov     rdi, [rbx+178h]
0x18000a8f6  lea     rax, [rdx+5]
0x18000a8fa  cmp     rax, rdi
0x18000a8fd  ja      loc_18000AB87
0x18000a903  mov     rcx, [rbx+28h]
0x18000a907  sub     rcx, [rbx+18h]
0x18000a90b  sar     rcx, 1
0x18000a90e  test    ecx, 0FFFFFF80h
0x18000a914  jnz     loc_18000B07D
0x18000a91a  or      cl, r14b
0x18000a91d  mov     [rdx], cl
0x18000a91f  mov     rax, [rbx+18h]
0x18000a923  inc     qword ptr [rbx+170h]
0x18000a92a  mov     rcx, [rbx+28h]
0x18000a92e  inc     dword ptr [rbx+180h]
0x18000a934  mov     [rbx+30h], rax
0x18000a938  mov     [rbx+18h], rcx
0x18000a93c  movzx   eax, word ptr [rcx]
0x18000a93f  mov     rdx, rcx
0x18000a942  add     rcx, 2
0x18000a946  mov     [rbx+28h], rcx
0x18000a94a  cmp     ax, r14w
0x18000a94e  jb      loc_18000B0F6
0x18000a954  and     dword ptr [rbx+50h], 0FFFFFFFEh
0x18000a958  mov     r8d, [rbx+50h]
0x18000a95c  mov     [rbx+28h], rdx
0x18000a960  jmp     loc_18000A709
0x18000a965  mov     rax, [rcx+8]
0x18000a969  test    byte ptr [rax+0Ah], 1
0x18000a96d  jnz     loc_18000A872
0x18000a973  jmp     loc_18000A86C
0x18000a978  mov     rcx, [rbx+8]; jumptable 000000018000A77E case 16
0x18000a97c  mov     eax, 0B0h
0x18000a981  mov     dword ptr [rcx], 0B0h
0x18000a987  jmp     loc_18000A878
0x18000a98c  mov     rcx, [rbx+8]; jumptable 000000018000A77E case 17
0x18000a990  mov     eax, 97h
0x18000a995  mov     dword ptr [rcx], 97h
0x18000a99b  jmp     loc_18000A878
0x18000a9a0  xor     r8d, r8d; jumptable 000000018000A77E case 24
0x18000a9a3  mov     edx, r11d
0x18000a9a6  mov     rcx, rbx
0x18000a9a9  call    ?ScanNumericConstant@Scanner@@AEAA?AW4tokens@@IH@Z; Scanner::ScanNumericConstant(uint,int)
0x18000a9ae  test    eax, eax
0x18000a9b0  jnz     loc_18000A872
0x18000a9b6  mov     rax, [rbx+8]
0x18000a9ba  mov     dword ptr [rax], 0B2h
0x18000a9c0  jmp     loc_18000A872
0x18000a9c5  mov     rcx, [rbx+8]; jumptable 000000018000A77E case 23
0x18000a9c9  mov     eax, 9Bh
0x18000a9ce  mov     dword ptr [rcx], 9Bh
0x18000a9d4  jmp     loc_18000A878
0x18000a9d9  cmp     [rsi], r13w
0x18000a9dd  jnz     loc_18000A78D
0x18000a9e3  lea     rax, [rsi+2]
0x18000a9e7  mov     [rbx+28h], rax
0x18000a9eb  jmp     loc_18000A78D
0x18000a9f0  mov     r8d, 1; jumptable 000000018000A77E case 3
0x18000a9f6  mov     edx, r11d
0x18000a9f9  mov     rcx, rbx
0x18000a9fc  call    ?ScanNumericConstant@Scanner@@AEAA?AW4tokens@@IH@Z; Scanner::ScanNumericConstant(uint,int)
0x18000aa01  jmp     loc_18000A878
0x18000aa06  mov     rax, [rbx+8]; jumptable 000000018000A77E case 26
0x18000aa0a  mov     dword ptr [rax], 0A4h
0x18000aa10  mov     rcx, [rbx+28h]
0x18000aa14  movzx   eax, word ptr [rcx]
0x18000aa17  cmp     ax, 3Ch ; '<'
0x18000aa1b  jz      loc_18000AF51
0x18000aa21  cmp     ax, 3Eh ; '>'
0x18000aa25  jnz     loc_18000A872
0x18000aa2b  lea     rax, [rcx+2]
0x18000aa2f  mov     [rbx+28h], rax
0x18000aa33  mov     rax, [rbx+8]
0x18000aa37  mov     dword ptr [rax], 0A6h
0x18000aa3d  jmp     loc_18000A872
0x18000aa42  mov     rcx, [rbx+28h]
0x18000aa46  sub     rcx, [rbx+10h]
0x18000aa4a  movsxd  rax, dword ptr [rbx+44h]
0x18000aa4e  sar     rcx, 1
0x18000aa51  cmp     rax, rcx
0x18000aa54  jg      loc_18000A715
0x18000aa5a  mov     rcx, [rbx+8]
0x18000aa5e  mov     eax, 0B8h
0x18000aa63  mov     dword ptr [rcx], 0B8h
0x18000aa69  jmp     loc_18000A878
0x18000aa6e  movzx   eax, word ptr [rsi]; jumptable 000000018000A77E case 15
0x18000aa71  cmp     eax, 39h ; '9'
0x18000aa74  jz      loc_18000AD0B; jumptable 000000018000B1D3 cases 48-56,72,79,104,111
0x18000aa7a  add     eax, 0FFFFFFD0h; switch 64 cases
0x18000aa7d  cmp     eax, 3Fh
0x18000aa80  jbe     loc_18000B1BF
0x18000aa86  mov     rcx, [rbx+8]; jumptable 000000018000B1D3 default case, cases 57-71,73-78,80-103,105-110
0x18000aa8a  mov     eax, 0A0h
0x18000aa8f  mov     dword ptr [rcx], 0A0h
0x18000aa95  jmp     loc_18000A878
0x18000aa9a  test    dl, 2; jumptable 000000018000A77E case 13
0x18000aa9d  jnz     short loc_18000AABC; jumptable 000000018000A77E case 12
0x18000aa9f  test    dl, 8
0x18000aaa2  jnz     loc_18000AD38
0x18000aaa8  mov     rcx, [rbx+8]
0x18000aaac  mov     eax, 9Ch
0x18000aab1  mov     dword ptr [rcx], 9Ch
0x18000aab7  jmp     loc_18000A878
0x18000aabc  xor     r15d, r15d; jumptable 000000018000A77E case 12
0x18000aabf  mov     [rbx+58h], r15d
0x18000aac3  mov     r8d, r15d; int
0x18000aac6  lea     rbp, [rbx+54h]
0x18000aaca  mov     rcx, [rbx+28h]
0x18000aace  lea     r9, [rbx+60h]
0x18000aad2  movzx   esi, word ptr [rcx]
0x18000aad5  lea     rdx, [rcx+2]
0x18000aad9  mov     [rbx+28h], rdx
0x18000aadd  cmp     esi, edi
0x18000aadf  jz      short loc_18000AB17
0x18000aae1  test    si, si
0x18000aae4  jz      loc_18000AFA3
0x18000aaea  cmp     esi, r12d
0x18000aaed  jz      loc_18000AFA3
0x18000aaf3  cmp     esi, r13d
0x18000aaf6  jz      loc_18000AFA3
0x18000aafc  cmp     r8d, [rbp+0]
0x18000ab00  jge     short loc_18000AB54
0x18000ab02  movsxd  rcx, dword ptr [rbx+58h]
0x18000ab06  mov     rax, [rbx+60h]
0x18000ab0a  mov     [rax+rcx*2], si
0x18000ab0e  inc     dword ptr [rbx+58h]
0x18000ab11  mov     r8d, [rbx+58h]
0x18000ab15  jmp     short loc_18000AACA
0x18000ab17  movzx   eax, word ptr [rdx]
0x18000ab1a  cmp     eax, edi
0x18000ab1c  jz      short loc_18000AB5E
0x18000ab1e  test    byte ptr [rbx+40h], 8
0x18000ab22  jnz     loc_18000AFE9
0x18000ab28  mov     rdx, [rbx+60h]; unsigned __int16 *
0x18000ab2c  mov     r9d, 1; int
0x18000ab32  mov     rcx, [rbx]; this
0x18000ab35  call    ?PidHashNameLen@HashTbl@@QEAAPEAUIdent@@PEBGJH@Z; HashTbl::PidHashNameLen(ushort const *,long,int)
0x18000ab3a  mov     rcx, [rbx+8]
0x18000ab3e  mov     edx, 0BBh
0x18000ab43  mov     [rcx+8], rax
0x18000ab47  mov     rax, [rbx+8]
0x18000ab4b  mov     [rax], edx
0x18000ab4d  mov     eax, edx
0x18000ab4f  jmp     loc_18000A878
0x18000ab54  mov     rcx, rbx; this
0x18000ab57  call    ?GrowBuf@Scanner@@AEAAXXZ; Scanner::GrowBuf(void)
0x18000ab5c  jmp     short loc_18000AB02
0x18000ab5e  lea     rax, [rdx+2]
0x18000ab62  mov     [rbx+28h], rax
0x18000ab66  cmp     r8d, [rbp+0]
0x18000ab6a  jge     loc_18000AEC3
0x18000ab70  movsxd  rcx, dword ptr [rbx+58h]
0x18000ab74  mov     rax, [r9]
0x18000ab77  mov     [rax+rcx*2], si
0x18000ab7b  inc     dword ptr [rbx+58h]
0x18000ab7e  mov     r8d, [rbx+58h]
0x18000ab82  jmp     loc_18000AAC6
0x18000ab87  mov     rcx, [rbx+168h]; Block
0x18000ab8e  test    rcx, rcx
0x18000ab91  jnz     loc_18000ACB9
0x18000ab97  mov     rcx, rbp; Size
0x18000ab9a  mov     edi, ebp
0x18000ab9c  call    cs:__imp_malloc
0x18000aba3  nop     dword ptr [rax+rax+00h]
0x18000aba8  mov     rcx, rax
  ... truncated ...
```
