# JAmsi::JAmsiProcessor(IDispatch *,long,tagDISPPARAMS *,CSession *)

- ea: `0x180009020`
- end: `0x180009890`
- name: `?JAmsiProcessor@JAmsi@@QEAAJPEAUIDispatch@@JPEAUtagDISPPARAMS@@PEAVCSession@@@Z`
- size: `2160`
- prototype: `__int64 __fastcall(JAmsi *this, struct IDispatch *, unsigned int, struct tagDISPPARAMS *, struct CSession *)`
- caller_count: `4`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180004d80`
- `0x180007de0`
- `0x180008040`
- `0x180008cc0`

## callees

- `0x180009020`
- `0x1800098a0`
- `0x180009980`
- `0x1800174c4`
- `0x18002fd50`
- `0x180030230`
- `0x180035324`
- `0x1800363f8`
- `0x180045478`
- `0x180045484`
- `0x180045490`
- `0x1800454d0`
- `0x180076746`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x1800092c4`
- `msvcrt!_snwprintf_s` at `0x1800092c4`
- `msvcrt!wcscpy_s` at `0x1800097fa`
- `msvcrt!wcscpy_s` at `0x1800097fa`
- `msvcrt!wcsncat_s` at `0x1800093c6`
- `msvcrt!wcsncat_s` at `0x1800093c6`
- `msvcrt!wcscat_s` at `0x1800092f1`
- `msvcrt!wcscat_s` at `0x1800096ff`
- `msvcrt!wcscat_s` at `0x1800092f1`
- `msvcrt!wcscat_s` at `0x1800096ff`
- `msvcrt!wcsncpy_s` at `0x180009538`
- `msvcrt!wcsncpy_s` at `0x180009538`
- `OLEAUT32!__imp_SysFreeString` at `0x1800096e7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000975c`
- `OLEAUT32!__imp_SysFreeString` at `0x180009797`
- `OLEAUT32!__imp_SysFreeString` at `0x180009817`
- `OLEAUT32!__imp_SysFreeString` at `0x1800096e7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000975c`
- `OLEAUT32!__imp_SysFreeString` at `0x180009797`
- `OLEAUT32!__imp_SysFreeString` at `0x180009817`

## pseudocode

```c
__int64 __fastcall JAmsi::JAmsiProcessor(
        JAmsi *this,
        struct IDispatch *a2,
        unsigned int a3,
        struct tagDISPPARAMS *a4,
        struct CSession *a5)
{
  bool v5; // zf
  unsigned int v6; // r12d
  JAmsi *v7; // r8
  __int64 *v8; // rax
  unsigned int v9; // ebp
  wchar_t *v10; // r15
  unsigned __int16 *v11; // rsi
  unsigned __int16 *StringCopy; // rbx
  __int64 i; // rcx
  __int64 *v14; // rcx
  unsigned __int16 **v15; // r14
  __int64 v16; // rdi
  __int64 v17; // rax
  int v18; // edx
  __int64 v19; // rax
  unsigned __int64 cArgs; // r14
  unsigned int v21; // r13d
  __int64 v22; // rax
  unsigned __int64 v23; // rbp
  unsigned int v24; // ebp
  int v25; // r9d
  void **v26; // rax
  struct tagDISPPARAMS *v27; // r9
  unsigned int v28; // edi
  int v30; // r8d
  __int64 v31; // r10
  unsigned __int64 v32; // r12
  int j; // ebx
  JAmsi *v34; // rcx
  JAmsi *v35; // r13
  unsigned int v36; // edi
  __int64 v37; // rbx
  unsigned int v38; // ebp
  __int64 v39; // rcx
  unsigned int v40; // r10d
  unsigned int v41; // edx
  int v42; // r8d
  __int64 v43; // r10
  const wchar_t *v44; // r8
  unsigned int v45; // r10d
  unsigned __int64 v46; // r9
  unsigned int v47; // eax
  struct tagDISPPARAMS *v48; // rax
  __int64 v49; // r12
  struct tagDISPPARAMS *v50; // r13
  unsigned __int64 v51; // r11
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 k; // rbx
  void *v55; // rcx
  __int64 v56; // rcx
  int v57; // eax
  JAmsi *v58; // rcx
  __int64 v59; // rax
  int v60; // eax
  const wchar_t *v61; // r13
  __int64 v62; // rax
  JAmsi *v63; // rcx
  RollingBuffer *v64; // rcx
  const unsigned __int16 *Buffer; // rax
  unsigned __int16 *v66; // rbx
  unsigned __int64 v67; // rdx
  __int64 v68; // r12
  wchar_t *v69; // rax
  COleScript *v70; // rcx
  unsigned int v71; // [rsp+44h] [rbp-B4h] BYREF
  struct tagDISPPARAMS *v72; // [rsp+48h] [rbp-B0h]
  struct tagDISPPARAMS *v73; // [rsp+50h] [rbp-A8h]
  JAmsi *v74; // [rsp+58h] [rbp-A0h]
  __int64 v75; // [rsp+60h] [rbp-98h] BYREF
  rsize_t SizeInWords; // [rsp+68h] [rbp-90h]
  BSTR bstrString; // [rsp+70h] [rbp-88h] BYREF
  BSTR Source; // [rsp+78h] [rbp-80h] BYREF
  struct CSession *v79; // [rsp+80h] [rbp-78h]
  unsigned __int16 v80[12]; // [rsp+88h] [rbp-70h] BYREF

  v5 = *((_DWORD *)this + 1) == 1;
  v6 = a3;
  v71 = a3;
  v73 = a4;
  v7 = this;
  v74 = this;
  v79 = a5;
  v75 = 0;
  Source = 0;
  bstrString = 0;
  if ( !v5 || !a2 || !a4 || !a5 )
    return 0;
  v8 = (__int64 *)*((_QWORD *)this + 3);
  v9 = LODWORD(a2->lpVtbl) ^ v6;
  v10 = 0;
  v11 = 0;
  v72 = 0;
  StringCopy = 0;
  for ( i = *v8; ; i = *v14 )
  {
    if ( !i )
    {
      v15 = 0;
      goto LABEL_72;
    }
    if ( v9 == *(_DWORD *)(i + 24) )
      break;
    if ( v9 <= *(_DWORD *)(i + 24) )
      v14 = (__int64 *)(i + 8);
    else
      v14 = (__int64 *)(i + 16);
  }
  v15 = *(unsigned __int16 ***)(i + 32);
  if ( !v15 || (StringCopy = *v15, v11 = v15[1], !*v15) || !v11 )
  {
LABEL_72:
    if ( ((int (__fastcall *)(struct IDispatch *, _QWORD, _QWORD, __int64 *))a2->lpVtbl->GetTypeInfo)(a2, 0, 0, &v75) < 0 )
      return 0;
    v56 = v75;
    if ( !v75 )
      return 0;
    if ( StringCopy )
    {
      operator delete(StringCopy);
      v56 = v75;
      StringCopy = 0;
    }
    v16 = -1;
    v57 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v56 + 96LL))(
            v56,
            0xFFFFFFFFLL,
            &bstrString,
            0,
            0,
            0);
    if ( bstrString )
    {
      if ( v57 < 0 )
        goto LABEL_130;
      StringCopy = JAmsi::JAmsiGetStringCopy(v58, bstrString);
      SysFreeString(bstrString);
    }
    else if ( v57 < 0 )
    {
      goto LABEL_130;
    }
    if ( !StringCopy )
    {
LABEL_132:
      StringCopy = JAmsi::JAmsiGetStringCopy(v58, L"unkcls");
      goto LABEL_95;
    }
    v59 = -1;
    do
      ++v59;
    while ( StringCopy[v59] );
    if ( v59 )
    {
LABEL_95:
      if ( v11 )
      {
        operator delete(v11);
        v11 = 0;
      }
      v60 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v75 + 96LL))(
              v75,
              v6,
              &Source,
              0,
              0,
              0);
      v61 = Source;
      if ( Source )
      {
        if ( v60 < 0 )
          goto LABEL_108;
        v68 = -1;
        do
          ++v68;
        while ( Source[v68] );
        if ( (_DWORD)v68 )
        {
          SizeInWords = (unsigned int)(v68 + 1);
          v69 = (wchar_t *)operator new[](saturated_mul(SizeInWords, 2u));
          v11 = v69;
          if ( v69 )
          {
            if ( wcscpy_s(v69, SizeInWords, v61) )
            {
              operator delete[](v11);
              v11 = 0;
            }
            else
            {
              v11[(unsigned int)v68] = 0;
            }
          }
        }
        else
        {
          v11 = 0;
        }
        v6 = v71;
        SysFreeString(Source);
      }
      else if ( v60 < 0 )
      {
        goto LABEL_108;
      }
      if ( !v11 )
      {
LABEL_110:
        StringCchPrintfW(v80, 0xCu, L"_%08x", v6);
        v11 = JAmsi::JAmsiGetStringCopy(v63, v80);
        goto LABEL_103;
      }
      v62 = -1;
      do
        ++v62;
      while ( v11[v62] );
      if ( v62 )
      {
LABEL_103:
        if ( v15 )
        {
          *v15 = StringCopy;
          v15[1] = v11;
        }
        else
        {
          v26 = (void **)operator new(0x10u);
          cArgs = (unsigned __int64)v26;
          if ( v26 )
          {
            *v26 = StringCopy;
            v26[1] = v11;
            if ( !StringCopy || !v11 )
            {
              operator delete(StringCopy);
              operator delete(v11);
              operator delete(*(void **)cArgs);
              operator delete(*(void **)(cArgs + 8));
              operator delete((void *)cArgs);
              LODWORD(cArgs) = SizeInWords;
              goto LABEL_29;
            }
            HashMap::Insert(*((HashMap **)v74 + 3), v9, v26);
            v7 = v74;
LABEL_106:
            a4 = v73;
            goto LABEL_16;
          }
        }
        v7 = v74;
        goto LABEL_106;
      }
LABEL_108:
      if ( v11 )
        operator delete(v11);
      goto LABEL_110;
    }
LABEL_130:
    if ( StringCopy )
      operator delete(StringCopy);
    goto LABEL_132;
  }
  v16 = -1;
LABEL_16:
  v17 = -1;
  do
    v5 = StringCopy[++v17] == 0;
  while ( !v5 );
  v18 = 2 * v17;
  v19 = -1;
  LODWORD(SizeInWords) = v18;
  do
    v5 = v11[++v19] == 0;
  while ( !v5 );
  cArgs = *((unsigned int *)v7 + 4);
  v21 = 2 * v19;
  v22 = *((_QWORD *)v7 + 1);
  if ( a4->cArgs <= (unsigned int)cArgs )
    cArgs = a4->cArgs;
  v71 = v21;
  v23 = *(unsigned int *)(v22 + 4);
  if ( (unsigned __int64)(v18 + v21) + 12 >= v23 )
    goto LABEL_29;
  v24 = v23 - v21 - v18 - 12;
  if ( !(_DWORD)cArgs )
  {
    v73 = 0;
    v25 = 0;
    v72 = 0;
    goto LABEL_40;
  }
  if ( v24 < 2 * (unsigned __int64)(unsigned int)(12 * cArgs) )
  {
LABEL_29:
    v27 = 0;
    v28 = 0;
    goto LABEL_30;
  }
  v48 = (struct tagDISPPARAMS *)operator new[](saturated_mul((unsigned int)cArgs, 8u));
  v72 = v48;
  v27 = v48;
  if ( v48 )
  {
    memset_0(v48, 0, 8 * cArgs);
    v49 = 0;
    do
    {
      if ( !JAmsi::JAmsiVarParameterToString(
              (JAmsi *)(3 * v49),
              (const struct VAR *)&v73->rgvarg[v49],
              (unsigned __int16 **)&v72->rgvarg + v49) )
      {
        v27 = v72;
        goto LABEL_75;
      }
      v49 = (unsigned int)(v49 + 1);
    }
    while ( (unsigned int)v49 < (unsigned int)cArgs );
    v50 = v72;
    v73 = v72;
    v25 = 0;
    v51 = v24 / (unsigned int)cArgs;
    v31 = 0;
    do
    {
      v52 = -1;
      v53 = *((_QWORD *)&v50->rgvarg + v31);
      do
        v5 = *(_WORD *)(v53 + 2 * v52++ + 2) == 0;
      while ( !v5 );
      v30 = 2 * v52;
      if ( (unsigned __int64)(unsigned int)(2 * v52) + 4 > v51 )
      {
        v30 = v51 - 4;
        v67 = (unsigned __int64)(unsigned int)(v51 - 4) >> 1;
        *(_WORD *)(v53 + 2 * v67 - 4) = 34;
        *(_WORD *)(*((_QWORD *)&v50->rgvarg + v31) + 2 * v67 - 2) = 0;
      }
      v25 += v30;
      v31 = (unsigned int)(v31 + 1);
    }
    while ( (unsigned int)v31 < (unsigned int)cArgs );
    v21 = v71;
    v18 = SizeInWords;
LABEL_40:
    v32 = (unsigned __int64)(v25 + v18 + 16 + v21 + 4 * (_DWORD)cArgs) >> 1;
    v10 = (wchar_t *)operator new[](saturated_mul(v32, 2u));
    if ( !v10 )
      goto LABEL_85;
    *v10 = 0;
    if ( _snwprintf_s(v10, v32, 0xFFFFFFFFFFFFFFFFuLL, L"%s.%s(", StringCopy, v11) == -1 )
      goto LABEL_85;
    for ( j = cArgs - 1; j >= 0; --j )
    {
      v43 = -1;
      v44 = (const wchar_t *)*((_QWORD *)&v73->rgvarg + j);
      do
        ++v43;
      while ( v44[v43] );
      v45 = 2 * v43;
      v46 = v24 / (unsigned int)cArgs;
      v47 = v46 - 4;
      if ( (unsigned __int64)v45 + 4 <= v46 )
        v47 = v45;
      if ( wcsncat_s(v10, v32, v44, (unsigned __int64)v47 >> 1) || j > 0 && wcscat_s(v10, v32, L", ") )
        goto LABEL_85;
    }
    if ( wcscat_s(v10, v32, L");\r\n") )
      goto LABEL_85;
    do
      ++v16;
    while ( v10[v16] );
    v35 = v74;
    v36 = 2 * v16;
    if ( v36 )
    {
      v37 = *((_QWORD *)v74 + 1);
      v38 = *(_DWORD *)(v37 + 4);
      v39 = *(unsigned int *)(v37 + 16);
      if ( v36 <= v38 )
        v38 = v36;
      v40 = v38 + 4;
      if ( *(_DWORD *)v37 - (int)v39 <= v38 + 4 )
      {
        v41 = 0;
        *(_WORD *)(v39 + *(_QWORD *)(v37 + 8)) = -2;
        LODWORD(v39) = 0;
        *(_DWORD *)(v37 + 16) = 0;
        goto LABEL_52;
      }
      v41 = *(_DWORD *)(v37 + 20);
      if ( (unsigned int)v39 < v41 && v41 - (unsigned int)v39 <= v40 )
      {
LABEL_52:
        while ( v41 <= v40 + (unsigned int)v39 )
        {
          v42 = *(unsigned __int16 *)(v41 + *(_QWORD *)(v37 + 8));
          if ( (_WORD)v42 == 0xFFFE )
          {
            v41 = 0;
            break;
          }
          v41 += v42 + 2;
        }
        *(_DWORD *)(v37 + 20) = v41;
      }
      *(_WORD *)(*(unsigned int *)(v37 + 16) + *(_QWORD *)(v37 + 8)) = v38;
      wcsncpy_s(
        (wchar_t *)(*(_QWORD *)(v37 + 8) + 2LL + *(unsigned int *)(v37 + 16)),
        ((unsigned __int64)v40 - 2) >> 1,
        v10,
        (unsigned __int64)v38 >> 1);
      *(_DWORD *)(v37 + 16) += v38 + 2;
      v34 = (JAmsi *)*(unsigned int *)(v37 + 16);
      *(_WORD *)((char *)v34 + *(_QWORD *)(v37 + 8)) = -1;
    }
    if ( JAmsi::JAmsiIsScannerNeeded(v34, v11) )
    {
      v64 = (RollingBuffer *)*((_QWORD *)v35 + 1);
      v71 = 0;
      v28 = 0;
      Buffer = RollingBuffer::GetBuffer(v64, &v71);
      v66 = (unsigned __int16 *)Buffer;
      if ( Buffer )
      {
        if ( v71 )
        {
          v70 = (COleScript *)*((_QWORD *)v79 + 4);
          if ( v70 )
            v28 = COleScript::CheckDynamicCodeSafety(v70, Buffer);
        }
        operator delete(v66);
      }
      v27 = v72;
    }
    else
    {
LABEL_85:
      v27 = v72;
      v28 = 0;
    }
  }
  else
  {
LABEL_75:
    v28 = 0;
  }
LABEL_30:
  if ( v75 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    v27 = v72;
  }
  if ( v27 )
  {
    for ( k = 0; (unsigned int)k < (unsigned int)cArgs; k = (unsigned int)(k + 1) )
    {
      v55 = (void *)*((_QWORD *)&v27->rgvarg + k);
      if ( v55 )
      {
        operator delete(v55);
        v27 = v72;
      }
    }
    operator delete[](v27);
  }
  if ( v10 )
    operator delete[](v10);
  return v28;
}

```

## disassembly

```asm
0x180009020  push    rbx
0x180009022  push    rbp
0x180009023  push    rsi
0x180009024  push    rdi
0x180009025  push    r12
0x180009027  push    r13
0x180009029  push    r14
0x18000902b  push    r15
0x18000902d  sub     rsp, 0B8h
0x180009034  mov     rax, cs:__security_cookie
0x18000903b  xor     rax, rsp
0x18000903e  mov     [rsp+0F8h+var_58], rax
0x180009046  mov     rax, [rsp+0F8h+arg_20]
0x18000904e  xor     r11d, r11d
0x180009051  cmp     dword ptr [rcx+4], 1
0x180009055  mov     r12d, r8d
0x180009058  mov     [rsp+0F8h+var_B4], r8d
0x18000905d  mov     r10, rdx
0x180009060  mov     [rsp+0F8h+var_A8], r9
0x180009065  mov     r8, rcx
0x180009068  mov     [rsp+0F8h+var_A0], rcx
0x18000906d  mov     [rsp+0F8h+var_78], rax
0x180009075  mov     [rsp+0F8h+var_98], r11
0x18000907a  mov     [rsp+0F8h+Source], r11
0x18000907f  mov     [rsp+0F8h+bstrString], r11
0x180009084  jnz     loc_1800094C5
0x18000908a  test    rdx, rdx
0x18000908d  jz      loc_1800094C5
0x180009093  test    r9, r9
0x180009096  jz      loc_1800094C5
0x18000909c  test    rax, rax
0x18000909f  jz      loc_1800094C5
0x1800090a5  mov     rax, [rcx+18h]
0x1800090a9  mov     ebp, r12d
0x1800090ac  xor     ebp, [rdx]
0x1800090ae  mov     r15d, r11d
0x1800090b1  mov     [rsp+0F8h+var_B8], r11d
0x1800090b6  mov     esi, r11d
0x1800090b9  mov     [rsp+0F8h+var_B0], r11
0x1800090be  mov     ebx, r11d
0x1800090c1  mov     rcx, [rax]
0x1800090c4  test    rcx, rcx
0x1800090c7  jz      loc_1800094A1
0x1800090cd  cmp     ebp, [rcx+18h]
0x1800090d0  jz      short loc_1800090E3
0x1800090d2  jbe     short loc_1800090DD
0x1800090d4  add     rcx, 10h
0x1800090d8  mov     rcx, [rcx]
0x1800090db  jmp     short loc_1800090C4
0x1800090dd  add     rcx, 8
0x1800090e1  jmp     short loc_1800090D8
0x1800090e3  mov     r14, [rcx+20h]
0x1800090e7  test    r14, r14
0x1800090ea  jz      loc_1800094A4
0x1800090f0  mov     rbx, [r14]
0x1800090f3  mov     rsi, [r14+8]
0x1800090f7  test    rbx, rbx
0x1800090fa  jz      loc_1800094A4
0x180009100  test    rsi, rsi
0x180009103  jz      loc_1800094A4
0x180009109  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180009110  mov     rax, rdi
0x180009113  cmp     [rbx+rax*2+2], r15w
0x180009119  lea     rax, [rax+1]
0x18000911d  jnz     short loc_180009113
0x18000911f  lea     edx, [rax+rax]
0x180009122  mov     rax, rdi
0x180009125  mov     dword ptr [rsp+0F8h+SizeInWords], edx
0x180009129  nop     dword ptr [rax+00000000h]
0x180009130  cmp     [rsi+rax*2+2], r15w
0x180009136  lea     rax, [rax+1]
0x18000913a  jnz     short loc_180009130
0x18000913c  mov     r14d, [r8+10h]
0x180009140  lea     r13d, [rax+rax]
0x180009144  cmp     [r9+10h], r14d
0x180009148  lea     ecx, [rdx+r13]
0x18000914c  mov     rax, [r8+8]
0x180009150  cmovbe  r14d, [r9+10h]
0x180009155  add     rcx, 0Ch
0x180009159  mov     [rsp+0F8h+var_B4], r13d
0x18000915e  mov     ebp, [rax+4]
0x180009161  cmp     rcx, rbp
0x180009164  jnb     short loc_1800091E2
0x180009166  sub     ebp, r13d
0x180009169  sub     ebp, edx
0x18000916b  sub     ebp, 0Ch
0x18000916e  test    r14d, r14d
0x180009171  jnz     loc_1800093E3
0x180009177  mov     [rsp+0F8h+var_A8], r11
0x18000917c  mov     r9d, r11d
0x18000917f  mov     [rsp+0F8h+var_B0], r11
0x180009184  jmp     loc_18000926D
0x180009189  mov     ecx, 10h; Size
0x18000918e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009193  mov     r14, rax
0x180009196  test    rax, rax
0x180009199  jz      loc_18000964F
0x18000919f  mov     [rax], rbx
0x1800091a2  mov     [rax+8], rsi
0x1800091a6  test    rbx, rbx
0x1800091a9  jz      short loc_1800091B4
0x1800091ab  test    rsi, rsi
0x1800091ae  jnz     loc_180009875
0x1800091b4  mov     rcx, rbx; Block
0x1800091b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800091bc  mov     rcx, rsi; Block
0x1800091bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800091c4  mov     rcx, [r14]; Block
0x1800091c7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800091cc  mov     rcx, [r14+8]; Block
0x1800091d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800091d5  mov     rcx, r14; Block
0x1800091d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800091dd  mov     r14d, dword ptr [rsp+0F8h+SizeInWords]
0x1800091e2  mov     r9, r15
0x1800091e5  mov     edi, r9d
0x1800091e8  mov     rcx, [rsp+0F8h+var_98]
0x1800091ed  test    rcx, rcx
0x1800091f0  jnz     short loc_18000922E
0x1800091f2  test    r9, r9
0x1800091f5  jnz     loc_1800094D9
0x1800091fb  test    r15, r15
0x1800091fe  jz      short loc_180009208
0x180009200  mov     rcx, r15; Block
0x180009203  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180009208  mov     eax, edi
0x18000920a  mov     rcx, [rsp+0F8h+var_58]
0x180009212  xor     rcx, rsp; StackCookie
0x180009215  call    __security_check_cookie
0x18000921a  add     rsp, 0B8h
0x180009221  pop     r15
0x180009223  pop     r14
0x180009225  pop     r13
0x180009227  pop     r12
0x180009229  pop     rdi
0x18000922a  pop     rsi
0x18000922b  pop     rbp
0x18000922c  pop     rbx
0x18000922d  retn
0x18000922e  mov     rax, [rcx]
0x180009231  mov     rax, [rax+10h]
0x180009235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000923a  mov     r9, [rsp+0F8h+var_B0]
0x18000923f  jmp     short loc_1800091F2
0x180009241  lea     r8d, [rax+rax]
0x180009245  mov     eax, r8d
0x180009248  add     rax, 4
0x18000924c  cmp     rax, r11
0x18000924f  ja      loc_180009712
0x180009255  add     r9d, r8d
0x180009258  inc     r10d
0x18000925b  cmp     r10d, r14d
0x18000925e  jb      loc_180009479
0x180009264  mov     r13d, [rsp+0F8h+var_B4]
0x180009269  mov     edx, dword ptr [rsp+0F8h+SizeInWords]
0x18000926d  add     edx, 10h
0x180009270  lea     r12d, ds:0[r14*4]
0x180009278  add     r12d, r13d
0x18000927b  mov     eax, 2
0x180009280  add     r12d, edx
0x180009283  add     r12d, r9d
0x180009286  shr     r12, 1
0x180009289  mul     r12
0x18000928c  cmovb   rax, rdi
0x180009290  mov     rcx, rax; unsigned __int64
0x180009293  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009298  mov     r15, rax
0x18000929b  test    rax, rax
0x18000929e  jz      loc_180009561
0x1800092a4  xor     eax, eax
0x1800092a6  mov     [rsp+0F8h+var_D0], rsi
0x1800092ab  lea     r9, aSS_0; "%s.%s("
0x1800092b2  mov     [r15], ax
0x1800092b6  mov     r8, rdi; MaxCount
0x1800092b9  mov     [rsp+0F8h+var_D8], rbx
0x1800092be  mov     rdx, r12; BufferCount
0x1800092c1  mov     rcx, r15; Buffer
0x1800092c4  call    cs:__imp__snwprintf_s
0x1800092ca  cmp     eax, 0FFFFFFFFh
0x1800092cd  jz      loc_180009561
0x1800092d3  mov     r13, [rsp+0F8h+var_A8]
0x1800092d8  lea     ebx, [r14-1]
0x1800092dc  test    ebx, ebx
0x1800092de  jns     loc_180009386
0x1800092e4  lea     r8, Source; ");\r\n"
0x1800092eb  mov     rdx, r12; SizeInWords
0x1800092ee  mov     rcx, r15; Destination
0x1800092f1  call    cs:__imp_wcscat_s
0x1800092f7  test    eax, eax
0x1800092f9  jnz     loc_180009561
0x1800092ff  nop
0x180009300  inc     rdi
0x180009303  cmp     word ptr [r15+rdi*2], 0
0x180009309  jnz     short loc_180009300
0x18000930b  mov     r13, [rsp+0F8h+var_A0]
0x180009310  add     edi, edi
0x180009312  jz      loc_180009551
0x180009318  mov     rbx, [r13+8]
0x18000931c  mov     ebp, [rbx+4]
0x18000931f  cmp     edi, ebp
0x180009321  mov     ecx, [rbx+10h]
0x180009324  mov     eax, [rbx]
0x180009326  cmovbe  ebp, edi
0x180009329  sub     eax, ecx
0x18000932b  lea     r10d, [rbp+4]
0x18000932f  cmp     eax, r10d
0x180009332  jbe     loc_1800097D0
0x180009338  mov     edx, [rbx+14h]
0x18000933b  cmp     ecx, edx
0x18000933d  jnb     loc_18000950C
0x180009343  mov     eax, edx
0x180009345  sub     eax, ecx
0x180009347  cmp     eax, r10d
0x18000934a  ja      loc_18000950C
0x180009350  mov     r11d, 0FFFEh
0x180009356  lea     r9d, [r10+rcx]
0x18000935a  nop     word ptr [rax+rax+00h]
0x180009360  cmp     edx, r9d
0x180009363  ja      loc_180009509
0x180009369  mov     rax, [rbx+8]
0x18000936d  mov     ecx, edx
0x18000936f  movzx   r8d, word ptr [rcx+rax]
0x180009374  cmp     r8w, r11w
0x180009378  jz      loc_180009507
0x18000937e  add     edx, 2
0x180009381  add     edx, r8d
0x180009384  jmp     short loc_180009360
0x180009386  movsxd  rax, ebx
0x180009389  mov     r10, rdi
0x18000938c  mov     r8, [r13+rax*8+0]; Source
0x180009391  inc     r10
0x180009394  cmp     word ptr [r8+r10*2], 0
0x18000939a  jnz     short loc_180009391
0x18000939c  xor     edx, edx
0x18000939e  add     r10d, r10d
0x1800093a1  mov     eax, ebp
0x1800093a3  mov     ecx, r10d
0x1800093a6  div     r14d
0x1800093a9  add     rcx, 4
0x1800093ad  mov     rdx, r12; SizeInWords
0x1800093b0  mov     r9d, eax
0x1800093b3  add     eax, 0FFFFFFFCh
0x1800093b6  cmp     rcx, r9
0x1800093b9  mov     rcx, r15; Destination
0x1800093bc  cmovbe  eax, r10d
0x1800093c0  mov     r9d, eax
0x1800093c3  shr     r9, 1; MaxCount
0x1800093c6  call    cs:__imp_wcsncat_s
0x1800093cc  test    eax, eax
0x1800093ce  jnz     loc_180009561
0x1800093d4  test    ebx, ebx
0x1800093d6  jg      loc_1800096F2
0x1800093dc  dec     ebx
0x1800093de  jmp     loc_1800092DC
0x1800093e3  lea     ecx, [r14+r14*2]
0x1800093e7  mov     eax, ebp
0x1800093e9  shl     ecx, 2
0x1800093ec  add     rcx, rcx
0x1800093ef  cmp     rax, rcx
0x1800093f2  jb      loc_1800091E2
0x1800093f8  mov     r12d, r14d
0x1800093fb  mov     eax, 8
0x180009400  mul     r12
0x180009403  cmovb   rax, rdi
0x180009407  mov     rcx, rax; unsigned __int64
0x18000940a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000940f  mov     [rsp+0F8h+var_B0], rax
0x180009414  mov     r9, rax
0x180009417  test    rax, rax
0x18000941a  jz      loc_1800094D1
0x180009420  lea     r8, ds:0[r14*8]; Size
0x180009428  xor     edx, edx; Val
0x18000942a  mov     rcx, rax; void *
0x18000942d  call    memset_0
0x180009432  xor     r12d, r12d
0x180009435  mov     rcx, [rsp+0F8h+var_B0]
0x18000943a  mov     rax, [rsp+0F8h+var_A8]
0x18000943f  lea     r8, [rcx+r12*8]; unsigned __int16 **
0x180009443  mov     rax, [rax]
0x180009446  lea     rcx, [r12+r12*2]; this
0x18000944a  lea     rdx, [rax+rcx*8]; struct VAR *
0x18000944e  call    ?JAmsiVarParameterToString@JAmsi@@AEAA_NPEBVVAR@@PEAPEAG@Z; JAmsi::JAmsiVarParameterToString(VAR const *,ushort * *)
0x180009453  test    al, al
0x180009455  jz      short loc_1800094CC
0x180009457  inc     r12d
0x18000945a  cmp     r12d, r14d
0x18000945d  jb      short loc_180009435
0x18000945f  mov     r13, [rsp+0F8h+var_B0]
0x180009464  xor     edx, edx
0x180009466  mov     eax, ebp
0x180009468  mov     [rsp+0F8h+var_A8], r13
0x18000946d  div     r14d
0x180009470  xor     r9d, r9d
0x180009473  mov     r11d, eax
0x180009476  xor     r10d, r10d
0x180009479  lea     r15, ds:0[r10*8]
0x180009481  mov     rax, rdi
0x180009484  mov     rcx, [r15+r13]
0x180009488  nop     dword ptr [rax+rax+00000000h]
0x180009490  cmp     word ptr [rcx+rax*2+2], 0
  ... truncated ...
```
