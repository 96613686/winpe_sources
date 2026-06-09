# FixReparsePointPath

- ea: `0x1800156f8`
- end: `0x180015f75`
- name: `FixReparsePointPath`
- size: `2173`
- prototype: `__int64 __fastcall(unsigned int *, _DWORD *, int *, const wchar_t *, STRSAFE_PCNZWCH, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x180016118`

## callees

- `0x18000144c`
- `0x180001458`
- `0x18000f670`
- `0x180014bc4`
- `0x1800151f0`
- `0x180015668`
- `0x1800156f8`
- `0x180016088`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180015f28`
- `ntdll!RtlFreeHeap` at `0x180015f46`
- `ntdll!RtlFreeHeap` at `0x180015f28`
- `ntdll!RtlFreeHeap` at `0x180015f46`

## string_xrefs

- `0x18001595d`: `FixReparsePointPath: Skipping the current symbolic link; it's relative.`
- `0x180015996`: `FixReparsePointPath: Reparse points with ReparseTag [0x%x] cannot be updated.`
- `0x180015cfb`: `Updates required for link; Old SubstName = [%s], Old PrintName = [%s]`

## pseudocode

```c
__int64 __fastcall FixReparsePointPath(
        unsigned int *a1,
        _DWORD *a2,
        int *a3,
        const wchar_t *a4,
        STRSAFE_PCNZWCH a5,
        _DWORD *a6)
{
  const wchar_t *v9; // r14
  const wchar_t *v10; // r12
  int v11; // ebx
  signed int LastErrorValue; // edx
  bool v13; // sf
  bool v14; // sf
  int v15; // edi
  wchar_t *v16; // r13
  _WORD *v17; // rcx
  _WORD *v18; // rdx
  _WORD *v19; // r9
  _WORD *v20; // r11
  __int16 v21; // ax
  int v22; // eax
  __int64 v23; // r15
  unsigned __int16 v24; // r8
  unsigned __int16 v25; // r9
  __int64 v26; // r12
  __int64 v27; // rcx
  const wchar_t *v28; // rdi
  size_t v29; // r8
  const wchar_t *v30; // rcx
  const wchar_t *v31; // rdx
  wchar_t v32; // cx
  int v33; // r12d
  unsigned __int16 v34; // di
  const wchar_t *v35; // r15
  size_t v36; // r8
  const wchar_t *v37; // rdx
  const wchar_t *v38; // rcx
  wchar_t v39; // cx
  int v40; // eax
  unsigned int v41; // ebx
  wchar_t *v42; // rdi
  unsigned int v43; // r14d
  HRESULT v44; // r11d
  int v45; // r11d
  wchar_t *v46; // rcx
  unsigned __int16 v47; // [rsp+30h] [rbp-D0h]
  int v48; // [rsp+34h] [rbp-CCh]
  int v49; // [rsp+38h] [rbp-C8h]
  unsigned int v50; // [rsp+3Ch] [rbp-C4h]
  unsigned int v51; // [rsp+3Ch] [rbp-C4h]
  unsigned __int16 v52; // [rsp+40h] [rbp-C0h]
  unsigned int MaxCount; // [rsp+48h] [rbp-B8h]
  __int16 v54; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v55; // [rsp+54h] [rbp-ACh]
  unsigned __int16 v56; // [rsp+58h] [rbp-A8h]
  _WORD *v57; // [rsp+60h] [rbp-A0h]
  _WORD *v58; // [rsp+68h] [rbp-98h]
  _WORD *v59; // [rsp+70h] [rbp-90h]
  _WORD *v60; // [rsp+78h] [rbp-88h]
  wchar_t *pszSrc; // [rsp+80h] [rbp-80h]
  unsigned int v62; // [rsp+88h] [rbp-78h]
  unsigned int *v63; // [rsp+90h] [rbp-70h]
  wchar_t *P; // [rsp+A0h] [rbp-60h]
  _BYTE v66[5]; // [rsp+BAh] [rbp-46h] BYREF
  char v67; // [rsp+BFh] [rbp-41h]
  wchar_t v68[8]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t String2[8]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t v70[8]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t v71[12]; // [rsp+F0h] [rbp-10h] BYREF

  *(_DWORD *)&v66[1] = *(_DWORD *)((char *)L":\\" + 1);
  wcscpy(String2, L"\\??\\");
  v67 = HIBYTE(asc_18001E768[3]);
  wcscpy(v68, L"\\\\?\\");
  v66[0] = 58;
  if ( !a1 || !a2 || !*a2 || !a3 || !*a3 || a4 && !*a4 || !a5 || !*a5 )
    return 2147942487LL;
  if ( (unsigned int)*a3 <= 0x18 )
    return 2147942522LL;
  P = 0;
  v9 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a4 && (pszSrc = 0, v10 = 0, P = BuildPath(a4, &::pszSrc), (v9 = P) == 0)
    || (v11 = 0, pszSrc = BuildPath(a5, &::pszSrc), (v10 = pszSrc) == 0) )
  {
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    v13 = LastErrorValue < 0;
    if ( LastErrorValue > 0 )
      v13 = 1;
    if ( !v13 )
    {
      v11 = -2147467259;
      goto LABEL_92;
    }
    v11 = NtCurrentTeb()->LastErrorValue;
    v14 = v11 < 0;
    if ( v11 > 0 )
    {
      v11 = (unsigned __int16)v11 | 0x80070000;
      v14 = v11 < 0;
    }
    if ( v14 )
      goto LABEL_92;
  }
  v57 = 0;
  v15 = 0;
  v58 = 0;
  v16 = 0;
  v59 = 0;
  v60 = 0;
  v63 = 0;
  if ( !v9 || !v10 || wcsicmp_0(v9, v10) )
  {
    if ( *a1 == -1610612733 )
    {
      v17 = a1 + 2;
      v18 = (_WORD *)a1 + 5;
      v57 = a1 + 2;
      v19 = a1 + 3;
      v58 = (_WORD *)a1 + 5;
      v20 = (_WORD *)a1 + 7;
      v59 = a1 + 3;
      v16 = (wchar_t *)(a1 + 4);
      v60 = (_WORD *)a1 + 7;
      v63 = a1 + 4;
      v21 = *((_WORD *)a1 + 2) - 10;
    }
    else
    {
      if ( *a1 != -1610612724 )
      {
        LibLog(
          &g_WdsNativeLibLog,
          50331648,
          L"FixReparsePointPath: Reparse points with ReparseTag [0x%x] cannot be updated.",
          *a1);
        v54 = 0;
        goto LABEL_36;
      }
      if ( (a1[4] & 1) != 0 )
      {
        LibLog(&g_WdsNativeLibLog, 50331648, L"FixReparsePointPath: Skipping the current symbolic link; it's relative.");
        v17 = 0;
        v21 = 0;
        v18 = 0;
        v19 = 0;
        v20 = 0;
        v15 = 1;
      }
      else
      {
        v17 = a1 + 2;
        v18 = (_WORD *)a1 + 5;
        v57 = a1 + 2;
        v19 = a1 + 3;
        v58 = (_WORD *)a1 + 5;
        v20 = (_WORD *)a1 + 7;
        v59 = a1 + 3;
        v16 = (wchar_t *)(a1 + 5);
        v60 = (_WORD *)a1 + 7;
        v63 = a1 + 5;
        v21 = *((_WORD *)a1 + 2) - 16;
      }
    }
    v54 = v21;
    goto LABEL_37;
  }
  v54 = 0;
LABEL_36:
  v17 = 0;
  v15 = 1;
  v20 = 0;
  v19 = 0;
  v18 = 0;
LABEL_37:
  if ( v15 )
    goto LABEL_92;
  v47 = *v20 >> 1;
  v22 = *a3;
  v23 = -1;
  v24 = *v17 >> 1;
  v49 = 0;
  v48 = 0;
  v25 = *v19 >> 1;
  v50 = v22 - 24;
  v55 = v24;
  v26 = v24;
  v52 = *v18 >> 1;
  v56 = v25;
  if ( v9 )
  {
    v27 = -1;
    do
      ++v27;
    while ( v9[v27] );
  }
  else
  {
    LODWORD(v27) = 3;
  }
  MaxCount = v27;
  v62 = v27 + 4;
  if ( *v18 >> 1 < (unsigned int)(v27 + 4) )
    goto LABEL_53;
  v28 = &v16[v24];
  if ( !wcsnicmp_0(v28, String2, 4u) )
  {
    if ( v9 )
    {
      v29 = MaxCount;
      v30 = v28 + 4;
      v31 = v9;
      goto LABEL_51;
    }
    v32 = v16[v26 + 4];
    if ( (unsigned __int16)(v32 - 65) <= 0x19u || (unsigned __int16)(v32 - 97) <= 0x19u )
    {
      v30 = v28 + 5;
      v29 = 2;
      v31 = (const wchar_t *)v66;
LABEL_51:
      if ( !wcsnicmp_0(v30, v31, v29) )
      {
        LODWORD(v27) = MaxCount;
        v33 = 1;
        v25 = v56;
        v49 = 1;
        goto LABEL_54;
      }
    }
  }
  LODWORD(v27) = MaxCount;
  v25 = v56;
LABEL_53:
  v33 = 0;
LABEL_54:
  v34 = v47;
  if ( v47 )
  {
    if ( v47 < (unsigned int)v27 )
    {
LABEL_75:
      v34 = v47;
      goto LABEL_76;
    }
    wcscpy(v71, L"globaloot");
    v35 = &v16[v25];
    wcscpy(v70, L"volume{");
    if ( v9 )
    {
      v36 = (unsigned int)v27;
      v37 = v9;
      v38 = &v16[v25];
    }
    else
    {
      if ( (unsigned __int16)(*v35 - 65) > 0x19u && (unsigned __int16)(*v35 - 97) > 0x19u )
        goto LABEL_59;
      v38 = v35 + 1;
      v36 = 2;
      v37 = (const wchar_t *)v66;
    }
    if ( !wcsnicmp_0(v38, v37, v36) )
    {
      v48 = 1;
      goto LABEL_65;
    }
LABEL_59:
    if ( v47 >= v62 && !wcsnicmp_0(v35, v68, 4u) && wcsnicmp_0(v35 + 4, v71, 0xAu) && wcsnicmp_0(v35 + 4, v70, 7u) )
    {
      if ( !v9 )
        goto LABEL_66;
      if ( !wcsnicmp_0(v35 + 4, v9, MaxCount) )
      {
LABEL_69:
        v34 = v47;
        v40 = 1;
        v23 = -1;
        goto LABEL_77;
      }
    }
LABEL_65:
    if ( v9 )
    {
LABEL_74:
      v23 = -1;
      goto LABEL_75;
    }
LABEL_66:
    v39 = v16[v56 + 4];
    if ( ((unsigned __int16)(v39 - 65) <= 0x19u || (unsigned __int16)(v39 - 97) <= 0x19u)
      && !wcsnicmp_0(v35 + 5, (const wchar_t *)v66, 2u) )
    {
      goto LABEL_69;
    }
    goto LABEL_74;
  }
LABEL_76:
  v40 = v48;
LABEL_77:
  if ( v33 || v40 )
  {
    do
      ++v23;
    while ( pszSrc[v23] );
    *(_QWORD *)v70 = v23;
    v11 = StrSubstring(&v16[v55]);
    if ( v11 >= 0 )
    {
      if ( !v34 || (v11 = StrSubstring(&v16[v56]), v11 >= 0) )
      {
        v41 = v50 >> 1;
        v42 = v16;
        v43 = 0;
        LibLog(
          &g_WdsNativeLibLog,
          0x4000000,
          L"Updates required for link; Old SubstName = [%s], Old PrintName = [%s]",
          0,
          L"<not present>");
        if ( !v49 )
        {
LABEL_87:
          v11 = StringCchCopyW(v42, v41, (STRSAFE_LPCWSTR)(2LL * v43));
          if ( v11 >= 0 )
          {
            *v57 = 0;
            v46 = &v42[v52 - v43];
            *v58 = 2 * (v46 - v16);
            *v59 = 2 * (((char *)(v46 + 1) - (char *)v63) >> 1);
            *v60 = 0;
            *((_WORD *)a1 + 2) += 2 * (((char *)(v46 + 1) - (char *)v63) >> 1) - v54;
            *a2 = *((unsigned __int16 *)a1 + 2) + 8;
            if ( a6 )
              *a6 = 1;
          }
          goto LABEL_92;
        }
        v44 = StringCchCopyNW(v16, v41, String2, 4u);
        if ( v44 < 0 )
        {
          v11 = v44;
        }
        else
        {
          v51 = v41 - 4;
          v11 = StringCchCopyW(v16 + 4, v41 - 4, pszSrc);
          if ( v11 >= 0 )
          {
            v41 = v51 - *(_DWORD *)v70;
            v43 = ((v45 >> 31) & 0xFFFFFFFC) + MaxCount + 4;
            v42 = &v16[*(unsigned int *)v70 + 4];
            goto LABEL_87;
          }
        }
      }
    }
  }
LABEL_92:
  if ( pszSrc )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pszSrc);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800156f8  push    rbp
0x1800156fa  push    rbx
0x1800156fb  push    rsi
0x1800156fc  push    rdi
0x1800156fd  push    r12
0x1800156ff  push    r13
0x180015701  push    r14
0x180015703  push    r15
0x180015705  lea     rbp, [rsp-18h]
0x18001570a  sub     rsp, 118h
0x180015711  mov     rax, cs:__security_cookie
0x180015718  xor     rax, rsp
0x18001571b  mov     [rbp+50h+var_48], rax
0x18001571f  movzx   eax, word ptr cs:asc_18001E748+8; ""
0x180015726  mov     rsi, rcx
0x180015729  movsd   xmm0, qword ptr cs:asc_18001E748; "\\??\\"
0x180015731  xor     r10d, r10d
0x180015734  mov     rcx, [rbp+50h+arg_28]
0x18001573b  mov     r15, r8
0x18001573e  mov     rdi, [rbp+50h+arg_20]
0x180015745  mov     [rbp+50h+var_78], ax
0x180015749  movzx   eax, word ptr cs:asc_18001E758+8; ""
0x180015750  mov     [rbp+50h+var_88], ax
0x180015754  mov     eax, 3Fh ; '?'
0x180015759  mov     [rbp+50h+var_98], ax
0x18001575d  mov     eax, dword ptr cs:asc_18001E768+3; "尀"
0x180015763  mov     dword ptr [rbp+50h+var_96+1], eax
0x180015766  mov     al, byte ptr cs:asc_18001E768+7; ""
0x18001576c  movsd   qword ptr [rbp+50h+String2], xmm0
0x180015771  movsd   xmm0, qword ptr cs:asc_18001E758; "\\\\?\\"
0x180015779  mov     [rbp+50h+var_91], al
0x18001577c  mov     [rbp+50h+var_A8], rdx
0x180015780  mov     [rbp+50h+var_A0], rcx
0x180015784  movsd   qword ptr [rbp+50h+var_90], xmm0
0x180015789  mov     [rbp+50h+var_96], 3Ah ; ':'
0x18001578d  test    rsi, rsi
0x180015790  jz      loc_180015F50
0x180015796  test    rdx, rdx
0x180015799  jz      loc_180015F50
0x18001579f  cmp     [rdx], r10d
0x1800157a2  jz      loc_180015F50
0x1800157a8  test    r8, r8
0x1800157ab  jz      loc_180015F50
0x1800157b1  cmp     [r8], r10d
0x1800157b4  jz      loc_180015F50
0x1800157ba  test    r9, r9
0x1800157bd  jz      short loc_1800157C9
0x1800157bf  cmp     r10w, [r9]
0x1800157c3  jz      loc_180015F50
0x1800157c9  test    rdi, rdi
0x1800157cc  jz      loc_180015F50
0x1800157d2  cmp     r10w, [rdi]
0x1800157d6  jz      loc_180015F50
0x1800157dc  cmp     dword ptr [r8], 18h
0x1800157e0  ja      short loc_1800157EC
0x1800157e2  mov     eax, 8007007Ah
0x1800157e7  jmp     loc_180015F55
0x1800157ec  mov     [rbp+50h+P], r10
0x1800157f0  mov     r14, r10
0x1800157f3  test    rcx, rcx
0x1800157f6  jz      short loc_1800157FB
0x1800157f8  mov     [rcx], r10d
0x1800157fb  test    r9, r9
0x1800157fe  jz      short loc_180015825
0x180015800  lea     rdx, pszSrc; STRSAFE_PCNZWCH
0x180015807  mov     [rbp+50h+pszSrc], r10
0x18001580b  mov     rcx, r9; pszSrc
0x18001580e  mov     r12, r10
0x180015811  call    BuildPath
0x180015816  xor     r10d, r10d
0x180015819  mov     [rbp+50h+P], rax
0x18001581d  mov     r14, rax
0x180015820  test    rax, rax
0x180015823  jz      short loc_180015846
0x180015825  lea     rdx, pszSrc; STRSAFE_PCNZWCH
0x18001582c  mov     rcx, rdi; pszSrc
0x18001582f  mov     ebx, r10d
0x180015832  call    BuildPath
0x180015837  xor     r10d, r10d
0x18001583a  mov     [rbp+50h+pszSrc], rax
0x18001583e  mov     r12, rax
0x180015841  test    rax, rax
0x180015844  jnz     short loc_180015881
0x180015846  mov     rcx, gs:30h
0x18001584f  mov     edx, [rcx+68h]
0x180015852  mov     ecx, 80070000h
0x180015857  test    edx, edx
0x180015859  jle     short loc_180015862
0x18001585b  movzx   edx, dx
0x18001585e  or      edx, ecx
0x180015860  test    edx, edx
0x180015862  jns     short loc_1800158CB
0x180015864  mov     rax, gs:30h
0x18001586d  mov     ebx, [rax+68h]
0x180015870  test    ebx, ebx
0x180015872  jle     short loc_18001587B
0x180015874  movzx   ebx, bx
0x180015877  or      ebx, ecx
0x180015879  test    ebx, ebx
0x18001587b  js      loc_180015F0D
0x180015881  mov     [rsp+150h+var_F0], r10
0x180015886  mov     edi, r10d
0x180015889  mov     [rsp+150h+var_E8], r10
0x18001588e  mov     r13, r10
0x180015891  mov     [rsp+150h+var_E0], r10
0x180015896  mov     r8d, 0Ah
0x18001589c  mov     [rsp+150h+var_D8], r10
0x1800158a1  mov     [rbp+50h+var_C0], r10
0x1800158a5  test    r14, r14
0x1800158a8  jz      short loc_1800158DB
0x1800158aa  test    r12, r12
0x1800158ad  jz      short loc_1800158DB
0x1800158af  mov     rdx, r12; String2
0x1800158b2  mov     rcx, r14; String1
0x1800158b5  call    _wcsicmp_0
0x1800158ba  xor     r10d, r10d
0x1800158bd  test    eax, eax
0x1800158bf  jnz     short loc_1800158D5
0x1800158c1  mov     [rsp+150h+var_100], r10d
0x1800158c6  jmp     loc_1800159B7
0x1800158cb  mov     ebx, 80004005h
0x1800158d0  jmp     loc_180015F0D
0x1800158d5  mov     r8d, 0Ah
0x1800158db  cmp     dword ptr [rsi], 0A0000003h
0x1800158e1  jnz     short loc_180015919
0x1800158e3  movzx   eax, word ptr [rsi+4]
0x1800158e7  lea     rcx, [rsi+8]
0x1800158eb  lea     rdx, [rsi+0Ah]
0x1800158ef  mov     [rsp+150h+var_F0], rcx
0x1800158f4  lea     r9, [rsi+0Ch]
0x1800158f8  mov     [rsp+150h+var_E8], rdx
0x1800158fd  lea     r11, [rsi+0Eh]
0x180015901  mov     [rsp+150h+var_E0], r9
0x180015906  lea     r13, [rsi+10h]
0x18001590a  mov     [rsp+150h+var_D8], r11
0x18001590f  mov     [rbp+50h+var_C0], r13
0x180015913  sub     ax, r8w
0x180015917  jmp     short loc_18001598C
0x180015919  cmp     dword ptr [rsi], 0A000000Ch
0x18001591f  jnz     short loc_180015993
0x180015921  test    byte ptr [rsi+10h], 1
0x180015925  jnz     short loc_18001595D
0x180015927  movzx   eax, word ptr [rsi+4]
0x18001592b  lea     rcx, [rsi+8]
0x18001592f  lea     rdx, [rsi+0Ah]
0x180015933  mov     [rsp+150h+var_F0], rcx
0x180015938  lea     r9, [rsi+0Ch]
0x18001593c  mov     [rsp+150h+var_E8], rdx
0x180015941  lea     r11, [rsi+0Eh]
0x180015945  mov     [rsp+150h+var_E0], r9
0x18001594a  lea     r13, [rsi+14h]
0x18001594e  mov     [rsp+150h+var_D8], r11
0x180015953  mov     [rbp+50h+var_C0], r13
0x180015957  sub     ax, 10h
0x18001595b  jmp     short loc_18001598C
0x18001595d  lea     r8, aFixreparsepoin_0; "FixReparsePointPath: Skipping the curre"...
0x180015964  mov     edx, 3000000h
0x180015969  lea     rcx, g_WdsNativeLibLog
0x180015970  call    LibLog
0x180015975  mov     rcx, r13
0x180015978  xor     r10d, r10d
0x18001597b  mov     eax, r10d
0x18001597e  mov     rdx, rcx
0x180015981  mov     r9, rcx
0x180015984  mov     r11, rcx
0x180015987  mov     edi, 1
0x18001598c  mov     word ptr [rsp+150h+var_100], ax
0x180015991  jmp     short loc_1800159C8
0x180015993  mov     r9d, [rsi]
0x180015996  lea     r8, aFixreparsepoin_1; "FixReparsePointPath: Reparse points wit"...
0x18001599d  mov     edx, 3000000h
0x1800159a2  lea     rcx, g_WdsNativeLibLog
0x1800159a9  call    LibLog
0x1800159ae  xor     r10d, r10d
0x1800159b1  mov     word ptr [rsp+150h+var_100], r10w
0x1800159b7  mov     rcx, r13
0x1800159ba  mov     edi, 1
0x1800159bf  mov     r11, rcx
0x1800159c2  mov     r9, rcx
0x1800159c5  mov     rdx, rcx
0x1800159c8  test    edi, edi
0x1800159ca  jnz     loc_180015F0D
0x1800159d0  movzx   eax, word ptr [r11]
0x1800159d4  movzx   r8d, word ptr [rcx]
0x1800159d8  movzx   r9d, word ptr [r9]
0x1800159dc  shr     ax, 1
0x1800159df  mov     [rsp+150h+var_120], ax
0x1800159e4  mov     eax, [r15]
0x1800159e7  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800159eb  sub     eax, 18h
0x1800159ee  shr     r8w, 1
0x1800159f2  mov     [rsp+150h+var_118], r10d
0x1800159f7  mov     [rsp+150h+var_11C], r10d
0x1800159fc  movzx   r10d, word ptr [rdx]
0x180015a00  shr     r10w, 1
0x180015a04  shr     r9w, 1
0x180015a08  mov     [rsp+150h+var_114], eax
0x180015a0c  xor     eax, eax
0x180015a0e  mov     [rsp+150h+var_FC], r8w
0x180015a14  movzx   r12d, r8w
0x180015a18  mov     [rsp+150h+var_110], r10w
0x180015a1e  mov     [rsp+150h+var_F8], r9w
0x180015a24  test    r14, r14
0x180015a27  jz      short loc_180015A38
0x180015a29  mov     rcx, r15
0x180015a2c  inc     rcx
0x180015a2f  cmp     [r14+rcx*2], ax
0x180015a34  jnz     short loc_180015A2C
0x180015a36  jmp     short loc_180015A3D
0x180015a38  mov     ecx, 3
0x180015a3d  lea     edx, [rcx+4]
0x180015a40  movzx   eax, r10w
0x180015a44  mov     [rsp+150h+MaxCount], rcx
0x180015a49  mov     dword ptr [rbp+50h+var_C8], edx
0x180015a4c  cmp     eax, edx
0x180015a4e  jb      loc_180015AE5
0x180015a54  movzx   eax, r8w
0x180015a58  lea     rdx, [rbp+50h+String2]; String2
0x180015a5c  mov     r8d, 4; MaxCount
0x180015a62  lea     rdi, ds:0[rax*2]
0x180015a6a  add     rdi, r13
0x180015a6d  mov     rcx, rdi; String1
0x180015a70  call    _wcsnicmp_0
0x180015a75  xor     r10d, r10d
0x180015a78  test    eax, eax
0x180015a7a  jnz     short loc_180015A8F
0x180015a7c  test    r14, r14
0x180015a7f  jz      short loc_180015A9C
0x180015a81  mov     r8d, dword ptr [rsp+150h+MaxCount]
0x180015a86  lea     rcx, [rdi+8]
0x180015a8a  mov     rdx, r14
0x180015a8d  jmp     short loc_180015AC3
0x180015a8f  mov     rcx, [rsp+150h+MaxCount]
0x180015a94  movzx   r9d, [rsp+150h+var_F8]
0x180015a9a  jmp     short loc_180015AE8
0x180015a9c  movzx   ecx, word ptr [r13+r12*2+8]
0x180015aa2  lea     eax, [rcx-41h]
0x180015aa5  cmp     ax, 19h
0x180015aa9  jbe     short loc_180015AB5
0x180015aab  sub     cx, 61h ; 'a'
0x180015aaf  cmp     cx, 19h
0x180015ab3  ja      short loc_180015A8F
0x180015ab5  lea     rcx, [rdi+0Ah]; String1
0x180015ab9  mov     r8d, 2; MaxCount
0x180015abf  lea     rdx, [rbp+50h+var_96]; String2
0x180015ac3  call    _wcsnicmp_0
0x180015ac8  xor     r10d, r10d
0x180015acb  test    eax, eax
0x180015acd  jnz     short loc_180015A8F
0x180015acf  mov     rcx, [rsp+150h+MaxCount]
0x180015ad4  lea     r12d, [r10+1]
0x180015ad8  movzx   r9d, [rsp+150h+var_F8]
0x180015ade  mov     [rsp+150h+var_118], r12d
0x180015ae3  jmp     short loc_180015AED
0x180015ae5  xor     r10d, r10d
0x180015ae8  mov     r12d, [rsp+150h+var_118]
0x180015aed  movzx   edi, [rsp+150h+var_120]
0x180015af2  cmp     r10w, di
0x180015af6  jz      loc_180015C5E
0x180015afc  cmp     edi, ecx
0x180015afe  jb      loc_180015C59
0x180015b04  movups  xmm0, xmmword ptr cs:aGlobalroot; "globalroot"
0x180015b0b  movzx   eax, r9w
0x180015b0f  movsd   xmm1, qword ptr cs:aGlobalroot+0Eh; "oot"
0x180015b17  movups  xmmword ptr [rbp+50h+var_60], xmm0
0x180015b1b  movups  xmm0, xmmword ptr cs:aVolume; "volume{"
0x180015b22  lea     r15, ds:0[rax*2]
0x180015b2a  add     r15, r13
0x180015b2d  movsd   qword ptr [rbp+50h+var_60+0Eh], xmm1
0x180015b32  movdqu  xmmword ptr [rbp+50h+var_70], xmm0
0x180015b37  test    r14, r14
0x180015b3a  jz      loc_180015C1A
0x180015b40  mov     r8d, ecx; MaxCount
0x180015b43  mov     rdx, r14; String2
0x180015b46  mov     rcx, r15; String1
0x180015b49  call    _wcsnicmp_0
0x180015b4e  xor     r10d, r10d
0x180015b51  test    eax, eax
0x180015b53  jz      loc_180015C48
0x180015b59  cmp     edi, dword ptr [rbp+50h+var_C8]
0x180015b5c  jb      short loc_180015BC5
0x180015b5e  mov     r8d, 4; MaxCount
0x180015b64  lea     rdx, [rbp+50h+var_90]; String2
0x180015b68  mov     rcx, r15; String1
0x180015b6b  call    _wcsnicmp_0
0x180015b70  xor     r10d, r10d
0x180015b73  test    eax, eax
0x180015b75  jnz     short loc_180015BC5
0x180015b77  lea     rdi, [r15+8]
0x180015b7b  mov     rcx, rdi; String1
0x180015b7e  lea     r8d, [r10+0Ah]; MaxCount
0x180015b82  lea     rdx, [rbp+50h+var_60]; String2
0x180015b86  call    _wcsnicmp_0
0x180015b8b  xor     r10d, r10d
0x180015b8e  test    eax, eax
0x180015b90  jz      short loc_180015BC5
0x180015b92  lea     r8d, [r10+7]; MaxCount
0x180015b96  mov     rcx, rdi; String1
0x180015b99  lea     rdx, [rbp+50h+var_70]; String2
0x180015b9d  call    _wcsnicmp_0
  ... truncated ...
```
