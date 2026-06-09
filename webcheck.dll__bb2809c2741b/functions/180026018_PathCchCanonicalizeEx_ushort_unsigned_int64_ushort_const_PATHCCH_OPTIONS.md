# PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)

- ea: `0x180026018`
- end: `0x18002667d`
- name: `?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z`
- size: `1637`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, enum PATHCCH_OPTIONS)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path`

## callers

- `0x180027384`

## callees

- `0x180003950`
- `0x180010928`
- `0x180024c68`
- `0x180025960`
- `0x180025ee4`
- `0x180026018`
- `0x180026684`
- `0x180026c8c`
- `0x180026ce4`
- `0x180027608`
- `0x18002a010`

## import_xrefs

- `msvcrt!iswalpha` at `0x18002617a`
- `msvcrt!iswalpha` at `0x1800261f9`
- `msvcrt!iswalpha` at `0x18002617a`
- `msvcrt!iswalpha` at `0x1800261f9`
- `msvcrt!wcspbrk` at `0x18002627c`
- `msvcrt!wcspbrk` at `0x18002627c`

## pseudocode

```c
__int64 __fastcall PathCchCanonicalizeEx(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int16 *a3,
        enum PATHCCH_OPTIONS a4)
{
  __int64 result; // rax
  int v7; // esi
  __int64 v8; // r12
  enum PATHCCH_OPTIONS v9; // ebx
  char v10; // cl
  __int64 (__fastcall *v11)(); // rax
  wchar_t *v12; // rdx
  const unsigned __int16 *v13; // r14
  bool v14; // bl
  const unsigned __int16 *v15; // r8
  int v16; // eax
  bool v17; // cf
  unsigned __int16 *v18; // rbx
  char v19; // r13
  __int64 v20; // r11
  bool v21; // r13
  wint_t v22; // cx
  __int16 v23; // r11
  wint_t v24; // cx
  int v25; // eax
  unsigned __int64 i; // r15
  wchar_t *v27; // rax
  wchar_t *v28; // r13
  BOOL v29; // eax
  BOOL IsRoot; // eax
  int v31; // eax
  __int64 (__fastcall *v32)(); // r13
  const unsigned __int16 *j; // rbx
  char v34; // al
  char v35; // al
  unsigned __int16 v36; // ax
  unsigned __int16 *v37; // rbx
  int v38; // eax
  unsigned __int16 *v39; // rbx
  unsigned __int16 *v40; // rcx
  unsigned __int16 *v41; // rax
  __int64 v42; // rax
  unsigned __int16 *v43; // rbx
  unsigned __int16 *v44; // r8
  unsigned __int16 *v45; // rcx
  unsigned __int64 v46; // rdx
  unsigned int v47; // [rsp+38h] [rbp-39h]
  unsigned __int16 *v48; // [rsp+48h] [rbp-29h] BYREF
  unsigned __int64 v49; // [rsp+50h] [rbp-21h] BYREF
  __int64 (__fastcall *v50)(); // [rsp+58h] [rbp-19h]
  __int64 v51; // [rsp+60h] [rbp-11h]
  const unsigned __int16 *v52; // [rsp+68h] [rbp-9h]
  enum PATHCCH_OPTIONS v53; // [rsp+70h] [rbp-1h] BYREF
  __int32 v54; // [rsp+78h] [rbp+7h]
  int v55; // [rsp+7Ch] [rbp+Bh]
  int IsUnc2; // [rsp+80h] [rbp+Fh]
  wchar_t *Control; // [rsp+88h] [rbp+17h]
  enum PATHCCH_OPTIONS v58; // [rsp+E0h] [rbp+6Fh]
  char v59; // [rsp+F0h] [rbp+7Fh]

  v53 = PATHCCH_NONE;
  result = StringCchCopyW(a1, 0x104u, (unsigned __int16 *)&Default);
  v7 = result;
  if ( (int)result < 0 )
    return result;
  if ( !AreOptionsValidAndOptInLongPathAwareProcess(&v53) )
    return 2147942487LL;
  v8 = 260;
  v9 = v53 & 0xFFFFFFF8;
  v49 = 260;
  v58 = v53 & 0xFFFFFFF8;
  v48 = 0;
  v54 = v53 & 0x10;
  if ( (v53 & 0x40) != 0 )
  {
    v10 = 1;
    v11 = IsBackOrForwardSlash;
  }
  else
  {
    v10 = 0;
    v11 = IsBackslash;
  }
  v59 = v10;
  v50 = v11;
  v12 = L"\\/";
  v52 = 0;
  if ( !v10 )
    v12 = (wchar_t *)L"\\";
  Control = v12;
  IsUnc2 = PathIsUnc2(a3);
  if ( !IsUnc2 )
  {
    v18 = a1;
    v51 = 0;
    v48 = a1;
    v13 = a3;
    v21 = IsExtendedLengthDosDevicePath(a3);
    if ( v21 )
    {
      v22 = a3[4];
      v52 = a3 + 4;
      if ( iswalpha(v22) && a3[5] == 58 )
        v13 = a3 + 4;
      else
        v21 = 0;
      if ( !v21 )
        goto LABEL_19;
    }
    else
    {
      v24 = *a3;
      v52 = a3;
      if ( !iswalpha(v24) || a3[1] != 58 )
      {
LABEL_19:
        v19 = v58;
        goto LABEL_20;
      }
    }
    v19 = v58;
    if ( MayNeedExtendedLengthPrefix(v58) )
    {
      v51 = 4;
      v25 = StringCchCopyExW(a1, 0x104u, L"\\\\?\\", &v48, &v49, 0);
      v8 = v49;
      v7 = v25;
      v18 = v48;
      v20 = 4;
      goto LABEL_21;
    }
LABEL_20:
    v20 = v51;
    goto LABEL_21;
  }
  v13 = v52;
  v14 = MayNeedExtendedLengthPrefix(v9);
  v15 = L"\\\\?\\UNC\\";
  if ( !v14 )
    v15 = L"\\\\";
  v16 = StringCchCopyExW(a1, 0x104u, v15, &v48, &v49, 0);
  v8 = v49;
  v17 = v14;
  v18 = v48;
  v7 = v16;
  v19 = v58;
  v20 = v17 ? 6 : 0;
  v51 = (unsigned int)v20;
LABEL_21:
  v55 = v19 & 5;
  if ( v55 == 5 && v20 )
  {
    v8 = 260;
    v49 = 260;
    v18 = a1;
    v51 = 0;
    v48 = a1;
    v13 = a3;
    v7 = StringCchCopyW(a1, 0x104u, (unsigned __int16 *)&Default);
  }
  else
  {
    v23 = 0;
  }
LABEL_29:
  for ( i = -1; ; i = -1 )
  {
    if ( v7 < 0 || *v13 == v23 )
      goto LABEL_83;
    v27 = wcspbrk(v13, Control);
    v23 = 0;
    v28 = v27;
    if ( v27 )
    {
      i = v27 - v13;
    }
    else
    {
      do
        ++i;
      while ( v13[i] );
    }
    if ( i > 0x100 && !v54 || i >= 0x8000 )
      break;
    if ( i != 1 )
    {
      if ( i != 2 )
      {
        if ( i )
        {
LABEL_66:
          v7 = StringCchCopyNExW(v18, v8, v13, i, &v48, &v49, v47);
          v23 = 0;
        }
        else
        {
          v31 = StringCchCopyNExW(v18, v8, L"\\", 1u, &v48, &v49, v47);
          v23 = 0;
          ++v13;
          v7 = v31;
          if ( v13 > v52 )
          {
            v32 = v50;
            if ( v59 )
            {
              for ( j = v13 + 1; ; ++j )
              {
                v34 = ((__int64 (__fastcall *)(_QWORD))v32)(*v13);
                v23 = 0;
                if ( !v34 )
                  break;
                v13 = j;
              }
            }
LABEL_68:
            if ( v7 == -2147024774 && i == 1 && (v35 = ((__int64 (__fastcall *)(_QWORD))v32)(*v13), v23 = 0, v35) )
            {
              v36 = v13[1];
              if ( !v36 || v36 == 46 && !v13[2] )
              {
                v8 = v49;
                v7 = 0;
                v18 = v48;
                i = -1;
                goto LABEL_84;
              }
              v8 = v49;
              if ( v49 == 1 && v36 == 46 && v13[2] == 46 )
              {
                v37 = v48;
                v8 = 0;
                v49 = 0;
                v7 = 0;
                *v48 = 0;
                v18 = v37 + 1;
                v48 = v18;
LABEL_80:
                v13 += i;
                goto LABEL_29;
              }
            }
            else
            {
              v8 = v49;
            }
            v18 = v48;
            goto LABEL_80;
          }
        }
        v32 = v50;
        goto LABEL_68;
      }
      if ( *v13 != 46 || v13[1] != 46 )
        goto LABEL_66;
      if ( v18 > a1 )
      {
        IsRoot = PathCchIsRoot(a1);
        v23 = 0;
        if ( !IsRoot )
        {
          --v18;
          while ( a1 < v18 )
          {
            if ( *--v18 == 92 )
            {
              v48 = v18;
              if ( v18 )
              {
                v8 = 260 - (v18 - a1);
                goto LABEL_56;
              }
              break;
            }
          }
          v18 = a1;
          v8 = 260;
          v48 = a1;
LABEL_56:
          v49 = v8;
          v7 = StringCchCopyW(v18, v8, (unsigned __int16 *)&Default);
          goto LABEL_57;
        }
      }
      if ( !v28 )
      {
LABEL_57:
        v13 += 2;
        goto LABEL_29;
      }
      v13 = v28 + 1;
      goto LABEL_29;
    }
    if ( *v13 != 46 )
      goto LABEL_66;
    if ( v27 )
    {
      v13 = v27 + 1;
      goto LABEL_29;
    }
    ++v13;
    if ( v18 > a1 )
    {
      v29 = PathCchIsRoot(a1);
      v23 = 0;
      if ( !v29 )
      {
        --v18;
        ++v8;
        v48 = v18;
        v49 = v8;
        v7 = StringCchCopyW(v18, v8, (unsigned __int16 *)&Default);
      }
    }
  }
  v7 = -2147024690;
  i = -1;
LABEL_83:
  v32 = v50;
LABEL_84:
  if ( (v58 & 0x20) != 0 && v18 > a1 && !((unsigned __int8 (__fastcall *)(_QWORD))v32)(*(v18 - 1)) )
  {
    v38 = StringCchCopyNExW(v18, v8, L"\\", 1u, &v48, &v49, v47);
    v18 = v48;
    v7 = v38;
  }
  if ( v7 >= 0 )
  {
    if ( (v58 & 0x18) == 0 )
    {
      if ( v18 > a1 )
      {
        v39 = v18 - 1;
        v40 = v39;
        v41 = v39;
        while ( *v39 == 46 )
        {
          if ( v40 == a1 )
          {
            *v39 = 0;
            break;
          }
          v40 = v41 - 1;
          if ( *(v41 - 1) == 42 )
            break;
          *v39 = 0;
          --v41;
          v39 = v40;
        }
      }
      v42 = -1;
      do
        ++v42;
      while ( a1[v42] );
      v43 = &a1[v42];
      if ( v43 >= a1 + 7 && StrIsEqualCaseInsensitive(v43 - 7, L"::$DATA", 7) )
        *(v43 - 7) = 0;
    }
    if ( v51 && v55 == 5 )
    {
      do
        ++i;
      while ( a1[v51 + i] );
      if ( i < 0x104 )
      {
        if ( IsUnc2 )
        {
          v44 = a1 + 8;
          v45 = a1 + 2;
          v46 = 258;
        }
        else
        {
          v44 = a1 + 4;
          v46 = 260;
          v45 = a1;
        }
        StringCchCopyW(v45, v46, v44);
      }
    }
    if ( !*a1 )
      *(_DWORD *)a1 = 92;
    if ( a1[1] == 58 && !a1[2] )
      *((_DWORD *)a1 + 1) = 92;
    return 0;
  }
  else
  {
    StringCchCopyW(a1, 0x104u, (unsigned __int16 *)&Default);
    if ( v7 == -2147024774 && (v58 & 1) == 0 )
      return (unsigned int)-2147024690;
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x180026018  mov     rax, rsp
0x18002601b  mov     [rax+8], rbx
0x18002601f  mov     [rax+20h], r9d
0x180026023  mov     [rax+10h], rdx
0x180026027  push    rbp
0x180026028  push    rsi
0x180026029  push    rdi
0x18002602a  push    r12
0x18002602c  push    r13
0x18002602e  push    r14
0x180026030  push    r15
0x180026032  lea     rbp, [rax-5Fh]
0x180026036  sub     rsp, 90h
0x18002603d  mov     r15, r8
0x180026040  mov     r14d, 104h
0x180026046  xor     r13d, r13d
0x180026049  lea     r8, Default; unsigned __int16 *
0x180026050  mov     edx, r14d; unsigned __int64
0x180026053  mov     [rbp+57h+var_58], r13d
0x180026057  mov     rdi, rcx
0x18002605a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002605f  mov     esi, eax
0x180026061  test    eax, eax
0x180026063  js      loc_180026662
0x180026069  lea     rcx, [rbp+57h+var_58]; enum PATHCCH_OPTIONS *
0x18002606d  call    ?AreOptionsValidAndOptInLongPathAwareProcess@@YA_NAEAW4PATHCCH_OPTIONS@@@Z; AreOptionsValidAndOptInLongPathAwareProcess(PATHCCH_OPTIONS &)
0x180026072  test    al, al
0x180026074  jnz     short loc_180026080
0x180026076  mov     eax, 80070057h
0x18002607b  jmp     loc_180026662
0x180026080  mov     ebx, [rbp+57h+var_58]
0x180026083  mov     r12, r14
0x180026086  and     ebx, 0FFFFFFF8h
0x180026089  mov     [rbp+57h+var_78], r14
0x18002608d  mov     eax, ebx
0x18002608f  mov     [rbp+57h+arg_8], ebx
0x180026092  and     eax, 11h
0x180026095  mov     [rbp+57h+var_80], r13
0x180026099  mov     [rbp+57h+var_50], eax
0x18002609c  test    bl, 40h
0x18002609f  jz      short loc_1800260AC
0x1800260a1  mov     cl, 1
0x1800260a3  lea     rax, IsBackOrForwardSlash
0x1800260aa  jmp     short loc_1800260B6
0x1800260ac  mov     cl, r13b
0x1800260af  lea     rax, IsBackslash
0x1800260b6  test    cl, cl
0x1800260b8  mov     [rbp+57h+arg_18], cl
0x1800260bb  lea     r8, asc_18002E888; "\\"
0x1800260c2  mov     [rbp+57h+var_70], rax
0x1800260c6  lea     rdx, asc_18002E88C; "\\/"
0x1800260cd  mov     [rbp+57h+var_60], r13
0x1800260d1  cmovz   rdx, r8
0x1800260d5  mov     rcx, r15; unsigned __int16 *
0x1800260d8  mov     [rbp+57h+Control], rdx
0x1800260dc  mov     r8, rax
0x1800260df  lea     rdx, [rbp+57h+var_60]
0x1800260e3  call    PathIsUnc2
0x1800260e8  mov     [rbp+57h+var_48], eax
0x1800260eb  test    eax, eax
0x1800260ed  jz      short loc_18002614E
0x1800260ef  mov     r14, [rbp+57h+var_60]
0x1800260f3  mov     ecx, ebx; enum PATHCCH_OPTIONS
0x1800260f5  mov     [rbp+57h+var_60], r14
0x1800260f9  call    ?MayNeedExtendedLengthPrefix@@YA_NW4PATHCCH_OPTIONS@@@Z; MayNeedExtendedLengthPrefix(PATHCCH_OPTIONS)
0x1800260fe  mov     bl, al
0x180026100  mov     [rsp+28h], r13d; unsigned int
0x180026105  lea     rax, asc_18002EB44; "\\\\"
0x18002610c  test    bl, bl
0x18002610e  lea     r8, aUnc; "\\\\?\\UNC\\"
0x180026115  mov     rdx, r12; unsigned __int64
0x180026118  cmovz   r8, rax; unsigned __int16 *
0x18002611c  lea     r9, [rbp+57h+var_80]; unsigned __int16 **
0x180026120  lea     rax, [rbp+57h+var_78]
0x180026124  mov     rcx, rdi; pszDest
0x180026127  mov     [rsp+0C0h+var_A0], rax; unsigned __int64 *
0x18002612c  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180026131  mov     r12, [rbp+57h+var_78]
0x180026135  neg     bl
0x180026137  mov     rbx, [rbp+57h+var_80]
0x18002613b  mov     esi, eax
0x18002613d  mov     r13d, [rbp+57h+arg_8]
0x180026141  sbb     r11, r11
0x180026144  and     r11d, 6
0x180026148  mov     [rbp+57h+var_68], r11
0x18002614c  jmp     short loc_1800261A4
0x18002614e  mov     rbx, rdi
0x180026151  mov     [rbp+57h+var_68], r13
0x180026155  mov     rcx, r15; unsigned __int16 *
0x180026158  mov     [rbp+57h+var_80], rbx
0x18002615c  mov     r14, r15
0x18002615f  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180026164  mov     r13b, al
0x180026167  test    al, al
0x180026169  jz      loc_1800261F1
0x18002616f  lea     rax, [r15+8]
0x180026173  movzx   ecx, word ptr [rax]; C
0x180026176  mov     [rbp+57h+var_60], rax
0x18002617a  call    cs:__imp_iswalpha
0x180026180  xor     ecx, ecx
0x180026182  test    eax, eax
0x180026184  jz      short loc_180026194
0x180026186  cmp     word ptr [r15+0Ah], 3Ah ; ':'
0x18002618c  jnz     short loc_180026194
0x18002618e  lea     r14, [r15+8]
0x180026192  jmp     short loc_180026197
0x180026194  mov     r13b, cl
0x180026197  test    r13b, r13b
0x18002619a  jnz     short loc_18002620B
0x18002619c  mov     r13d, [rbp+57h+arg_8]
0x1800261a0  mov     r11, [rbp+57h+var_68]
0x1800261a4  mov     eax, r13d
0x1800261a7  and     eax, 5
0x1800261aa  mov     [rbp+57h+var_4C], eax
0x1800261ad  cmp     eax, 5
0x1800261b0  jnz     loc_18002625C
0x1800261b6  test    r11, r11
0x1800261b9  jz      loc_18002625C
0x1800261bf  mov     ecx, 104h
0x1800261c4  lea     r8, Default; unsigned __int16 *
0x1800261cb  mov     r12d, ecx
0x1800261ce  mov     [rbp+57h+var_78], rcx
0x1800261d2  mov     edx, ecx; unsigned __int64
0x1800261d4  xor     r11d, r11d
0x1800261d7  mov     rbx, rdi
0x1800261da  mov     [rbp+57h+var_68], r11
0x1800261de  mov     rcx, rdi; unsigned __int16 *
0x1800261e1  mov     [rbp+57h+var_80], rbx
0x1800261e5  mov     r14, r15
0x1800261e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800261ed  mov     esi, eax
0x1800261ef  jmp     short loc_18002625F
0x1800261f1  movzx   ecx, word ptr [r15]; C
0x1800261f5  mov     [rbp+57h+var_60], r15
0x1800261f9  call    cs:__imp_iswalpha
0x1800261ff  test    eax, eax
0x180026201  jz      short loc_18002619C
0x180026203  cmp     word ptr [r15+2], 3Ah ; ':'
0x180026209  jnz     short loc_18002619C
0x18002620b  mov     r13d, [rbp+57h+arg_8]
0x18002620f  mov     ecx, r13d; enum PATHCCH_OPTIONS
0x180026212  call    ?MayNeedExtendedLengthPrefix@@YA_NW4PATHCCH_OPTIONS@@@Z; MayNeedExtendedLengthPrefix(PATHCCH_OPTIONS)
0x180026217  xor     ecx, ecx
0x180026219  test    al, al
0x18002621b  jz      short loc_1800261A0
0x18002621d  lea     eax, [rcx+4]
0x180026220  mov     [rsp+28h], ecx; unsigned int
0x180026224  mov     [rbp+57h+var_68], rax
0x180026228  lea     r9, [rbp+57h+var_80]; unsigned __int16 **
0x18002622c  lea     rax, [rbp+57h+var_78]
0x180026230  mov     rdx, r12; unsigned __int64
0x180026233  lea     r8, asc_18002EBF8; "\\\\?\\"
0x18002623a  mov     [rsp+0C0h+var_A0], rax; unsigned __int64 *
0x18002623f  mov     rcx, rdi; pszDest
0x180026242  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180026247  mov     r12, [rbp+57h+var_78]
0x18002624b  mov     esi, eax
0x18002624d  mov     rbx, [rbp+57h+var_80]
0x180026251  mov     r11d, 4
0x180026257  jmp     loc_1800261A4
0x18002625c  xor     r11d, r11d
0x18002625f  or      r15, 0FFFFFFFFFFFFFFFFh
0x180026263  test    esi, esi
0x180026265  js      loc_1800264FC
0x18002626b  cmp     [r14], r11w
0x18002626f  jz      loc_1800264FC
0x180026275  mov     rdx, [rbp+57h+Control]; Control
0x180026279  mov     rcx, r14; String
0x18002627c  call    cs:__imp_wcspbrk
0x180026282  xor     r11d, r11d
0x180026285  mov     r13, rax
0x180026288  test    rax, rax
0x18002628b  jz      short loc_180026298
0x18002628d  mov     r15, rax
0x180026290  sub     r15, r14
0x180026293  sar     r15, 1
0x180026296  jmp     short loc_1800262A2
0x180026298  inc     r15
0x18002629b  cmp     [r14+r15*2], r11w
0x1800262a0  jnz     short loc_180026298
0x1800262a2  cmp     r15, 100h
0x1800262a9  jbe     short loc_1800262B5
0x1800262ab  cmp     [rbp+57h+var_50], r11d
0x1800262af  jz      loc_1800264F3
0x1800262b5  cmp     r15, 8000h
0x1800262bc  jnb     loc_1800264F3
0x1800262c2  cmp     r15, 1
0x1800262c6  jnz     short loc_180026330
0x1800262c8  cmp     word ptr [r14], 2Eh ; '.'
0x1800262cd  jnz     loc_18002643A
0x1800262d3  test    r13, r13
0x1800262d6  jz      short loc_1800262DE
0x1800262d8  lea     r14, [rax+2]
0x1800262dc  jmp     short loc_18002625F
0x1800262de  add     r14, 2
0x1800262e2  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800262e9  cmp     rbx, rdi
0x1800262ec  jbe     loc_180026263
0x1800262f2  mov     rcx, rdi; pszPath
0x1800262f5  call    PathCchIsRoot
0x1800262fa  xor     r11d, r11d
0x1800262fd  test    eax, eax
0x1800262ff  jnz     loc_180026263
0x180026305  sub     rbx, 2
0x180026309  lea     r8, Default; unsigned __int16 *
0x180026310  inc     r12
0x180026313  mov     [rbp+57h+var_80], rbx
0x180026317  mov     rdx, r12; unsigned __int64
0x18002631a  mov     [rbp+57h+var_78], r12
0x18002631e  mov     rcx, rbx; unsigned __int16 *
0x180026321  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026326  mov     esi, eax
0x180026328  or      r15, r15
0x18002632b  jmp     loc_180026263
0x180026330  cmp     r15, 2
0x180026334  jnz     loc_1800263D4
0x18002633a  cmp     word ptr [r14], 2Eh ; '.'
0x18002633f  jnz     loc_18002643A
0x180026345  cmp     word ptr [r14+2], 2Eh ; '.'
0x18002634b  jnz     loc_18002643A
0x180026351  cmp     rbx, rdi
0x180026354  jbe     short loc_1800263C6
0x180026356  mov     rcx, rdi; pszPath
0x180026359  call    PathCchIsRoot
0x18002635e  xor     r11d, r11d
0x180026361  test    eax, eax
0x180026363  jnz     short loc_1800263C6
0x180026365  add     rbx, 0FFFFFFFFFFFFFFFEh
0x180026369  lea     eax, [r15+5Ah]
0x18002636d  cmp     rdi, rbx
0x180026370  jnb     short loc_180026398
0x180026372  sub     rbx, 2
0x180026376  cmp     [rbx], ax
0x180026379  jnz     short loc_18002636D
0x18002637b  mov     [rbp+57h+var_80], rbx
0x18002637f  test    rbx, rbx
0x180026382  jz      short loc_180026398
0x180026384  mov     rax, rbx
0x180026387  mov     r12d, 104h
0x18002638d  sub     rax, rdi
0x180026390  sar     rax, 1
0x180026393  sub     r12, rax
0x180026396  jmp     short loc_1800263A5
0x180026398  mov     rbx, rdi
0x18002639b  mov     r12d, 104h
0x1800263a1  mov     [rbp+57h+var_80], rbx
0x1800263a5  lea     r8, Default; unsigned __int16 *
0x1800263ac  mov     [rbp+57h+var_78], r12
0x1800263b0  mov     rdx, r12; unsigned __int64
0x1800263b3  mov     rcx, rbx; unsigned __int16 *
0x1800263b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800263bb  mov     esi, eax
0x1800263bd  add     r14, 4
0x1800263c1  jmp     loc_18002625F
0x1800263c6  test    r13, r13
0x1800263c9  jz      short loc_1800263BD
0x1800263cb  lea     r14, [r13+2]
0x1800263cf  jmp     loc_18002625F
0x1800263d4  test    r15, r15
0x1800263d7  jnz     short loc_18002643A
0x1800263d9  lea     rax, [rbp+57h+var_78]
0x1800263dd  mov     rdx, r12; unsigned __int64
0x1800263e0  mov     [rsp+28h], rax; unsigned __int64 *
0x1800263e5  lea     r9d, [r15+1]; unsigned __int64
0x1800263e9  lea     rax, [rbp+57h+var_80]
0x1800263ed  mov     rcx, rbx; unsigned __int16 *
0x1800263f0  lea     r8, asc_18002E888; "\\"
0x1800263f7  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 **
0x1800263fc  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180026401  xor     r11d, r11d
0x180026404  add     r14, 2
0x180026408  mov     esi, eax
0x18002640a  cmp     r14, [rbp+57h+var_60]
0x18002640e  jbe     short loc_180026462
0x180026410  mov     r13, [rbp+57h+var_70]
0x180026414  cmp     [rbp+57h+arg_18], r11b
0x180026418  jz      short loc_180026466
0x18002641a  lea     rbx, [r14+2]
0x18002641e  movzx   ecx, word ptr [r14]
0x180026422  mov     rax, r13
0x180026425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002642a  xor     r11d, r11d
0x18002642d  test    al, al
0x18002642f  jz      short loc_180026466
0x180026431  mov     r14, rbx
0x180026434  add     rbx, 2
0x180026438  jmp     short loc_18002641E
0x18002643a  lea     rax, [rbp+57h+var_78]
0x18002643e  mov     r9, r15; unsigned __int64
0x180026441  mov     [rsp+28h], rax; unsigned __int64 *
0x180026446  mov     r8, r14; unsigned __int16 *
0x180026449  lea     rax, [rbp+57h+var_80]
0x18002644d  mov     rdx, r12; unsigned __int64
0x180026450  mov     rcx, rbx; unsigned __int16 *
0x180026453  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 **
0x180026458  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18002645d  mov     esi, eax
0x18002645f  xor     r11d, r11d
0x180026462  mov     r13, [rbp+57h+var_70]
0x180026466  cmp     esi, 8007007Ah
  ... truncated ...
```
