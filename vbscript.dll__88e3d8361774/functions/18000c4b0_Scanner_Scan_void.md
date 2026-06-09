# Scanner::Scan(void)

- ea: `0x18000c4b0`
- end: `0x18000d0ec`
- name: `?Scan@Scanner@@QEAA?AW4tokens@@XZ`
- size: `3132`
- prototype: ``
- caller_count: `22`
- callee_count: `8`
- tags: ``

## callers

- `0x180009da0`
- `0x18000aa20`
- `0x18000ad80`
- `0x18000b430`
- `0x18000d100`
- `0x1800286f4`
- `0x18002873c`
- `0x180028768`
- `0x1800289a8`
- `0x180029220`
- `0x18002a3d0`
- `0x18002a810`
- `0x18002aaa0`
- `0x18002be54`
- `0x18002f674`
- `0x18004ef20`
- `0x18005c6c4`
- `0x18005c7cc`
- `0x18005cae0`
- `0x18005cd14`
- `0x18005cecc`
- `0x18005df6c`

## callees

- `0x18000c4b0`
- `0x18000e050`
- `0x18002bcc0`
- `0x18002cea0`
- `0x180040fc8`
- `0x18004106c`
- `0x180041780`
- `0x1800424cc`

## import_xrefs

- `msvcrt!realloc` at `0x18000caaa`
- `msvcrt!realloc` at `0x18000cdab`
- `msvcrt!realloc` at `0x18000caaa`
- `msvcrt!realloc` at `0x18000cdab`
- `msvcrt!malloc` at `0x18000c98c`
- `msvcrt!malloc` at `0x18000cccb`
- `msvcrt!malloc` at `0x18000c98c`
- `msvcrt!malloc` at `0x18000cccb`

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
      v9 = *((_BYTE *)&qword_18007DC10[8] + v7);
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
          while ( (unsigned __int16)v18 < 0x80u && (*((_BYTE *)&qword_18007DBD0 + v18) & 1) != 0 );
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
    while ( (unsigned __int16)v28 < 0x80u && *((_BYTE *)&qword_18007DC10[8] + v28) == 4 );
    *(_DWORD *)(a1 + 80) &= ~1u;
    v1 = *(unsigned int *)(a1 + 80);
    *(_QWORD *)(a1 + 40) = v29;
  }
  if ( (_WORD)v22 == 10 )
    goto LABEL_28;
  if ( (unsigned __int16)v22 < 0x80u && *((_BYTE *)&qword_18007DC10[8] + v22) == 4 )
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
0x18000c4b0  mov     [rsp+arg_8], rbx
0x18000c4b5  mov     [rsp+arg_10], rbp
0x18000c4ba  push    rsi
0x18000c4bb  push    r12
0x18000c4bd  push    r13
0x18000c4bf  push    r14
0x18000c4c1  push    r15
0x18000c4c3  sub     rsp, 20h
0x18000c4c7  mov     r8d, [rcx+50h]
0x18000c4cb  lea     r15, __ImageBase
0x18000c4d2  and     r8d, 0FFFFFFFEh
0x18000c4d6  mov     [rsp+48h+arg_0], rdi
0x18000c4db  mov     [rcx+50h], r8d
0x18000c4df  mov     rbx, rcx
0x18000c4e2  mov     r14d, 80h
0x18000c4e8  mov     ebp, 400h
0x18000c4ed  mov     r12d, 0Dh
0x18000c4f3  mov     r13d, 0Ah
0x18000c4f9  mov     edx, [rbx+40h]
0x18000c4fc  test    dl, 10h
0x18000c4ff  jnz     loc_18000C832
0x18000c505  mov     r10, [rbx+28h]
0x18000c509  and     edx, 0FFFFFFDFh
0x18000c50c  mov     [rbx+40h], edx
0x18000c50f  mov     [rbx+20h], r10
0x18000c513  movzx   r9d, word ptr [r10]
0x18000c517  lea     rsi, [r10+2]
0x18000c51b  mov     [rbx+28h], rsi
0x18000c51f  cmp     r9w, r14w
0x18000c523  jnb     loc_18000CD74
0x18000c529  movzx   ecx, byte ptr [r9+r15+7DC50h]
0x18000c532  cmp     cl, 2
0x18000c535  jz      loc_18000C5E6
0x18000c53b  cmp     cl, 4
0x18000c53e  jz      loc_18000C699
0x18000c544  mov     r11d, r9d
0x18000c547  mov     edi, r9d
0x18000c54a  cmp     cl, 1Fh
0x18000c54d  jz      loc_18000C6B0
0x18000c553  movzx   eax, cl
0x18000c556  dec     eax; switch 37 cases
0x18000c558  cmp     eax, 24h
0x18000c55b  ja      def_18000C56E; jumptable 000000018000C56E default case, cases 2,4,6,8,9,14,30-32,34,35
0x18000c561  cdqe
0x18000c563  mov     ecx, ds:(jpt_18000C56E - 180000000h)[r15+rax*4]
0x18000c56b  add     rcx, r15
0x18000c56e  jmp     rcx; switch jump
0x18000c570  cmp     edi, r12d; jumptable 000000018000C56E case 5
0x18000c573  jz      loc_18000C7C9
0x18000c579  test    dl, 8
0x18000c57c  jnz     short loc_18000C5D2
0x18000c57e  mov     rdx, [rbx+170h]
0x18000c585  mov     rcx, [rbx+178h]
0x18000c58c  lea     rax, [rdx+5]
0x18000c590  cmp     rax, rcx
0x18000c593  ja      loc_18000CCB8
0x18000c599  mov     rcx, [rbx+28h]
0x18000c59d  sub     rcx, [rbx+18h]
0x18000c5a1  sar     rcx, 1
0x18000c5a4  test    ecx, 0FFFFFF80h
0x18000c5aa  jnz     loc_18000CF1E
0x18000c5b0  or      cl, r14b
0x18000c5b3  mov     [rdx], cl
0x18000c5b5  mov     rax, [rbx+18h]
0x18000c5b9  inc     qword ptr [rbx+170h]
0x18000c5c0  inc     dword ptr [rbx+180h]
0x18000c5c6  mov     [rbx+30h], rax
0x18000c5ca  mov     rax, [rbx+28h]
0x18000c5ce  mov     [rbx+18h], rax
0x18000c5d2  mov     rcx, [rbx+8]
0x18000c5d6  mov     eax, 0B7h
0x18000c5db  mov     dword ptr [rcx], 0B7h
0x18000c5e1  jmp     loc_18000C668
0x18000c5e6  mov     [rbx+28h], r10
0x18000c5ea  test    dl, 8
0x18000c5ed  jnz     loc_18000CB09
0x18000c5f3  mov     rax, r10
0x18000c5f6  nop     word ptr [rax+rax+00000000h]
0x18000c600  movzx   ecx, word ptr [rax]
0x18000c603  mov     r8, rax
0x18000c606  add     rax, 2
0x18000c60a  mov     [rbx+28h], rax
0x18000c60e  cmp     cx, r14w
0x18000c612  jb      short loc_18000C685
0x18000c614  mov     [rbx+28h], r8
0x18000c618  sub     r8, r10
0x18000c61b  sar     r8, 1; int
0x18000c61e  cmp     r8, 0FFh
0x18000c625  jg      loc_18000CF02
0x18000c62b  mov     rcx, [rbx]; this
0x18000c62e  xor     r9d, r9d; int
0x18000c631  mov     rdx, r10; unsigned __int16 *
0x18000c634  call    ?PidHashNameLen@HashTbl@@QEAAPEAUIdent@@PEBGJH@Z; HashTbl::PidHashNameLen(ushort const *,long,int)
0x18000c639  mov     rcx, [rbx+8]
0x18000c63d  mov     [rcx+8], rax
0x18000c641  mov     rdx, [rbx+8]
0x18000c645  mov     rax, [rdx+8]
0x18000c649  movzx   ecx, word ptr [rax+8]
0x18000c64d  mov     [rdx], ecx
0x18000c64f  mov     rcx, [rbx+8]
0x18000c653  cmp     dword ptr [rcx], 0
0x18000c656  jnz     loc_18000C755
0x18000c65c  mov     dword ptr [rcx], 95h
0x18000c662  mov     rax, [rbx+8]
0x18000c666  mov     eax, [rax]
0x18000c668  mov     rdi, [rsp+48h+arg_0]
0x18000c66d  mov     rbx, [rsp+48h+arg_8]
0x18000c672  mov     rbp, [rsp+48h+arg_10]
0x18000c677  add     rsp, 20h
0x18000c67b  pop     r15
0x18000c67d  pop     r14
0x18000c67f  pop     r13
0x18000c681  pop     r12
0x18000c683  pop     rsi
0x18000c684  retn
0x18000c685  test    byte ptr [rcx+r15+7DBD0h], 1
0x18000c68e  jnz     loc_18000C600
0x18000c694  jmp     loc_18000C614
0x18000c699  or      r8d, 1
0x18000c69d  or      edx, 20h
0x18000c6a0  mov     [rbx+50h], r8d
0x18000c6a4  mov     [rbx+40h], edx
0x18000c6a7  jmp     loc_18000C4F9
0x18000c6b0  movzx   eax, word ptr [rsi]
0x18000c6b3  lea     rcx, [rsi+2]
0x18000c6b7  mov     [rbx+28h], rcx
0x18000c6bb  cmp     r12w, ax
0x18000c6bf  jnz     loc_18000CDDB
0x18000c6c5  cmp     [rcx], r13w
0x18000c6c9  jnz     short loc_18000C6D3
0x18000c6cb  add     rcx, 2
0x18000c6cf  mov     [rbx+28h], rcx
0x18000c6d3  test    dl, 8
0x18000c6d6  jnz     short loc_18000C72C
0x18000c6d8  mov     rdx, [rbx+170h]
0x18000c6df  mov     rdi, [rbx+178h]
0x18000c6e6  lea     rax, [rdx+5]
0x18000c6ea  cmp     rax, rdi
0x18000c6ed  ja      loc_18000C977
0x18000c6f3  mov     rcx, [rbx+28h]
0x18000c6f7  sub     rcx, [rbx+18h]
0x18000c6fb  sar     rcx, 1
0x18000c6fe  test    ecx, 0FFFFFF80h
0x18000c704  jnz     loc_18000CE55
0x18000c70a  or      cl, r14b
0x18000c70d  mov     [rdx], cl
0x18000c70f  mov     rax, [rbx+18h]
0x18000c713  inc     qword ptr [rbx+170h]
0x18000c71a  mov     rcx, [rbx+28h]
0x18000c71e  inc     dword ptr [rbx+180h]
0x18000c724  mov     [rbx+30h], rax
0x18000c728  mov     [rbx+18h], rcx
0x18000c72c  movzx   eax, word ptr [rcx]
0x18000c72f  mov     rdx, rcx
0x18000c732  add     rcx, 2
0x18000c736  mov     [rbx+28h], rcx
0x18000c73a  cmp     ax, r14w
0x18000c73e  jb      loc_18000CECE
0x18000c744  and     dword ptr [rbx+50h], 0FFFFFFFEh
0x18000c748  mov     r8d, [rbx+50h]
0x18000c74c  mov     [rbx+28h], rdx
0x18000c750  jmp     loc_18000C4F9
0x18000c755  mov     rax, [rcx+8]
0x18000c759  test    byte ptr [rax+0Ah], 1
0x18000c75d  jnz     loc_18000C662
0x18000c763  jmp     loc_18000C65C
0x18000c768  mov     rcx, [rbx+8]; jumptable 000000018000C56E case 16
0x18000c76c  mov     eax, 0B0h
0x18000c771  mov     dword ptr [rcx], 0B0h
0x18000c777  jmp     loc_18000C668
0x18000c77c  mov     rcx, [rbx+8]; jumptable 000000018000C56E case 17
0x18000c780  mov     eax, 97h
0x18000c785  mov     dword ptr [rcx], 97h
0x18000c78b  jmp     loc_18000C668
0x18000c790  xor     r8d, r8d; jumptable 000000018000C56E case 24
0x18000c793  mov     edx, r11d
0x18000c796  mov     rcx, rbx
0x18000c799  call    ?ScanNumericConstant@Scanner@@AEAA?AW4tokens@@IH@Z; Scanner::ScanNumericConstant(uint,int)
0x18000c79e  test    eax, eax
0x18000c7a0  jnz     loc_18000C662
0x18000c7a6  mov     rax, [rbx+8]
0x18000c7aa  mov     dword ptr [rax], 0B2h
0x18000c7b0  jmp     loc_18000C662
0x18000c7b5  mov     rcx, [rbx+8]; jumptable 000000018000C56E case 23
0x18000c7b9  mov     eax, 9Bh
0x18000c7be  mov     dword ptr [rcx], 9Bh
0x18000c7c4  jmp     loc_18000C668
0x18000c7c9  cmp     [rsi], r13w
0x18000c7cd  jnz     loc_18000C579
0x18000c7d3  lea     rax, [rsi+2]
0x18000c7d7  mov     [rbx+28h], rax
0x18000c7db  jmp     loc_18000C579
0x18000c7e0  mov     r8d, 1; jumptable 000000018000C56E case 3
0x18000c7e6  mov     edx, r11d
0x18000c7e9  mov     rcx, rbx
0x18000c7ec  call    ?ScanNumericConstant@Scanner@@AEAA?AW4tokens@@IH@Z; Scanner::ScanNumericConstant(uint,int)
0x18000c7f1  jmp     loc_18000C668
0x18000c7f6  mov     rax, [rbx+8]; jumptable 000000018000C56E case 26
0x18000c7fa  mov     dword ptr [rax], 0A4h
0x18000c800  mov     rcx, [rbx+28h]
0x18000c804  movzx   eax, word ptr [rcx]
0x18000c807  cmp     ax, 3Ch ; '<'
0x18000c80b  jz      loc_18000CD2F
0x18000c811  cmp     ax, 3Eh ; '>'
0x18000c815  jnz     loc_18000C662
0x18000c81b  lea     rax, [rcx+2]
0x18000c81f  mov     [rbx+28h], rax
0x18000c823  mov     rax, [rbx+8]
0x18000c827  mov     dword ptr [rax], 0A6h
0x18000c82d  jmp     loc_18000C662
0x18000c832  mov     rcx, [rbx+28h]
0x18000c836  sub     rcx, [rbx+10h]
0x18000c83a  movsxd  rax, dword ptr [rbx+44h]
0x18000c83e  sar     rcx, 1
0x18000c841  cmp     rax, rcx
0x18000c844  jg      loc_18000C505
0x18000c84a  mov     rcx, [rbx+8]
0x18000c84e  mov     eax, 0B8h
0x18000c853  mov     dword ptr [rcx], 0B8h
0x18000c859  jmp     loc_18000C668
0x18000c85e  movzx   eax, word ptr [rsi]; jumptable 000000018000C56E case 15
0x18000c861  cmp     eax, 39h ; '9'
0x18000c864  jz      loc_18000CAEF; jumptable 000000018000CFAB cases 48-56,72,79,104,111
0x18000c86a  add     eax, 0FFFFFFD0h; switch 64 cases
0x18000c86d  cmp     eax, 3Fh
0x18000c870  jbe     loc_18000CF97
0x18000c876  mov     rcx, [rbx+8]; jumptable 000000018000CFAB default case, cases 57-71,73-78,80-103,105-110
0x18000c87a  mov     eax, 0A0h
0x18000c87f  mov     dword ptr [rcx], 0A0h
0x18000c885  jmp     loc_18000C668
0x18000c88a  test    dl, 2; jumptable 000000018000C56E case 13
0x18000c88d  jnz     short loc_18000C8AC; jumptable 000000018000C56E case 12
0x18000c88f  test    dl, 8
0x18000c892  jnz     loc_18000CB1C
0x18000c898  mov     rcx, [rbx+8]
0x18000c89c  mov     eax, 9Ch
0x18000c8a1  mov     dword ptr [rcx], 9Ch
0x18000c8a7  jmp     loc_18000C668
0x18000c8ac  xor     r15d, r15d; jumptable 000000018000C56E case 12
0x18000c8af  mov     [rbx+58h], r15d
0x18000c8b3  mov     r8d, r15d; int
0x18000c8b6  lea     rbp, [rbx+54h]
0x18000c8ba  mov     rcx, [rbx+28h]
0x18000c8be  lea     r9, [rbx+60h]
0x18000c8c2  movzx   esi, word ptr [rcx]
0x18000c8c5  lea     rdx, [rcx+2]
0x18000c8c9  mov     [rbx+28h], rdx
0x18000c8cd  cmp     esi, edi
0x18000c8cf  jz      short loc_18000C907
0x18000c8d1  test    si, si
0x18000c8d4  jz      loc_18000CD81
0x18000c8da  cmp     esi, r12d
0x18000c8dd  jz      loc_18000CD81
0x18000c8e3  cmp     esi, r13d
0x18000c8e6  jz      loc_18000CD81
0x18000c8ec  cmp     r8d, [rbp+0]
0x18000c8f0  jge     short loc_18000C944
0x18000c8f2  movsxd  rcx, dword ptr [rbx+58h]
0x18000c8f6  mov     rax, [rbx+60h]
0x18000c8fa  mov     [rax+rcx*2], si
0x18000c8fe  inc     dword ptr [rbx+58h]
0x18000c901  mov     r8d, [rbx+58h]
0x18000c905  jmp     short loc_18000C8BA
0x18000c907  movzx   eax, word ptr [rdx]
0x18000c90a  cmp     eax, edi
0x18000c90c  jz      short loc_18000C94E
0x18000c90e  test    byte ptr [rbx+40h], 8
0x18000c912  jnz     loc_18000CDC1
0x18000c918  mov     rdx, [rbx+60h]; unsigned __int16 *
0x18000c91c  mov     r9d, 1; int
0x18000c922  mov     rcx, [rbx]; this
0x18000c925  call    ?PidHashNameLen@HashTbl@@QEAAPEAUIdent@@PEBGJH@Z; HashTbl::PidHashNameLen(ushort const *,long,int)
0x18000c92a  mov     rcx, [rbx+8]
0x18000c92e  mov     edx, 0BBh
0x18000c933  mov     [rcx+8], rax
0x18000c937  mov     rax, [rbx+8]
0x18000c93b  mov     [rax], edx
0x18000c93d  mov     eax, edx
0x18000c93f  jmp     loc_18000C668
0x18000c944  mov     rcx, rbx; this
0x18000c947  call    ?GrowBuf@Scanner@@AEAAXXZ; Scanner::GrowBuf(void)
0x18000c94c  jmp     short loc_18000C8F2
0x18000c94e  lea     rax, [rdx+2]
0x18000c952  mov     [rbx+28h], rax
0x18000c956  cmp     r8d, [rbp+0]
0x18000c95a  jge     loc_18000CCA7
0x18000c960  movsxd  rcx, dword ptr [rbx+58h]
0x18000c964  mov     rax, [r9]
0x18000c967  mov     [rax+rcx*2], si
0x18000c96b  inc     dword ptr [rbx+58h]
0x18000c96e  mov     r8d, [rbx+58h]
0x18000c972  jmp     loc_18000C8B6
0x18000c977  mov     rcx, [rbx+168h]; Block
0x18000c97e  test    rcx, rcx
0x18000c981  jnz     loc_18000CAA3
0x18000c987  mov     rcx, rbp; Size
0x18000c98a  mov     edi, ebp
0x18000c98c  call    cs:__imp_malloc
0x18000c992  mov     rcx, rax
0x18000c995  test    rax, rax
  ... truncated ...
```
