# JAmsi::JAmsiProcessor(IDispatch *,long,tagDISPPARAMS *,CSession *)

- ea: `0x180007130`
- end: `0x1800079ae`
- name: `?JAmsiProcessor@JAmsi@@QEAAJPEAUIDispatch@@JPEAUtagDISPPARAMS@@PEAVCSession@@@Z`
- size: `2174`
- prototype: `__int64 __fastcall(JAmsi *this, struct IDispatch *, unsigned int, struct tagDISPPARAMS *, struct CSession *)`
- caller_count: `4`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180005e40`
- `0x1800060c0`
- `0x180006d80`
- `0x18001af30`

## callees

- `0x180007130`
- `0x1800079c0`
- `0x180007aa0`
- `0x1800118ac`
- `0x180012018`
- `0x180034940`
- `0x180034f88`
- `0x18003783c`
- `0x18004686c`
- `0x180046878`
- `0x180046884`
- `0x1800468c4`
- `0x180079436`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x1800073d5`
- `msvcrt!_snwprintf_s` at `0x1800073d5`
- `msvcrt!wcscpy_s` at `0x18000791d`
- `msvcrt!wcscpy_s` at `0x18000791d`
- `msvcrt!wcsncat_s` at `0x1800074e6`
- `msvcrt!wcsncat_s` at `0x1800074e6`
- `msvcrt!wcscat_s` at `0x180007408`
- `msvcrt!wcscat_s` at `0x180007825`
- `msvcrt!wcscat_s` at `0x180007408`
- `msvcrt!wcscat_s` at `0x180007825`
- `msvcrt!wcsncpy_s` at `0x180007658`
- `msvcrt!wcsncpy_s` at `0x180007658`
- `OLEAUT32!__imp_SysFreeString` at `0x180007807`
- `OLEAUT32!__imp_SysFreeString` at `0x18000788c`
- `OLEAUT32!__imp_SysFreeString` at `0x180007807`
- `OLEAUT32!__imp_SysFreeString` at `0x18000788c`

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
        goto LABEL_131;
      StringCopy = JAmsi::JAmsiGetStringCopy(v58, bstrString);
      SysFreeString(bstrString);
    }
    else if ( v57 < 0 )
    {
      goto LABEL_131;
    }
    if ( !StringCopy )
    {
LABEL_133:
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
LABEL_131:
    if ( StringCopy )
      operator delete(StringCopy);
    goto LABEL_133;
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
0x180007130  push    rbx
0x180007132  push    rbp
0x180007133  push    rsi
0x180007134  push    rdi
0x180007135  push    r12
0x180007137  push    r13
0x180007139  push    r14
0x18000713b  push    r15
0x18000713d  sub     rsp, 0B8h
0x180007144  mov     rax, cs:__security_cookie
0x18000714b  xor     rax, rsp
0x18000714e  mov     [rsp+0F8h+var_58], rax
0x180007156  mov     rax, [rsp+0F8h+arg_20]
0x18000715e  xor     r11d, r11d
0x180007161  cmp     dword ptr [rcx+4], 1
0x180007165  mov     r12d, r8d
0x180007168  mov     [rsp+0F8h+var_B4], r8d
0x18000716d  mov     r10, rdx
0x180007170  mov     [rsp+0F8h+var_A8], r9
0x180007175  mov     r8, rcx
0x180007178  mov     [rsp+0F8h+var_A0], rcx
0x18000717d  mov     [rsp+0F8h+var_78], rax
0x180007185  mov     [rsp+0F8h+var_98], r11
0x18000718a  mov     [rsp+0F8h+Source], r11
0x18000718f  mov     [rsp+0F8h+bstrString], r11
0x180007194  jnz     loc_1800075E5
0x18000719a  test    rdx, rdx
0x18000719d  jz      loc_1800075E5
0x1800071a3  test    r9, r9
0x1800071a6  jz      loc_1800075E5
0x1800071ac  test    rax, rax
0x1800071af  jz      loc_1800075E5
0x1800071b5  mov     rax, [rcx+18h]
0x1800071b9  mov     ebp, r12d
0x1800071bc  xor     ebp, [rdx]
0x1800071be  mov     r15d, r11d
0x1800071c1  mov     [rsp+0F8h+var_B8], r11d
0x1800071c6  mov     esi, r11d
0x1800071c9  mov     [rsp+0F8h+var_B0], r11
0x1800071ce  mov     ebx, r11d
0x1800071d1  mov     rcx, [rax]
0x1800071d4  test    rcx, rcx
0x1800071d7  jz      loc_1800075C1
0x1800071dd  cmp     ebp, [rcx+18h]
0x1800071e0  jz      short loc_1800071F3
0x1800071e2  jbe     short loc_1800071ED
0x1800071e4  add     rcx, 10h
0x1800071e8  mov     rcx, [rcx]
0x1800071eb  jmp     short loc_1800071D4
0x1800071ed  add     rcx, 8
0x1800071f1  jmp     short loc_1800071E8
0x1800071f3  mov     r14, [rcx+20h]
0x1800071f7  test    r14, r14
0x1800071fa  jz      loc_1800075C4
0x180007200  mov     rbx, [r14]
0x180007203  mov     rsi, [r14+8]
0x180007207  test    rbx, rbx
0x18000720a  jz      loc_1800075C4
0x180007210  test    rsi, rsi
0x180007213  jz      loc_1800075C4
0x180007219  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180007220  mov     rax, rdi
0x180007223  cmp     [rbx+rax*2+2], r15w
0x180007229  lea     rax, [rax+1]
0x18000722d  jnz     short loc_180007223
0x18000722f  lea     edx, [rax+rax]
0x180007232  mov     rax, rdi
0x180007235  mov     dword ptr [rsp+0F8h+SizeInWords], edx
0x180007239  nop     dword ptr [rax+00000000h]
0x180007240  cmp     [rsi+rax*2+2], r15w
0x180007246  lea     rax, [rax+1]
0x18000724a  jnz     short loc_180007240
0x18000724c  mov     r14d, [r8+10h]
0x180007250  lea     r13d, [rax+rax]
0x180007254  cmp     [r9+10h], r14d
0x180007258  lea     ecx, [rdx+r13]
0x18000725c  mov     rax, [r8+8]
0x180007260  cmovbe  r14d, [r9+10h]
0x180007265  add     rcx, 0Ch
0x180007269  mov     [rsp+0F8h+var_B4], r13d
0x18000726e  mov     ebp, [rax+4]
0x180007271  cmp     rcx, rbp
0x180007274  jnb     short loc_1800072F2
0x180007276  sub     ebp, r13d
0x180007279  sub     ebp, edx
0x18000727b  sub     ebp, 0Ch
0x18000727e  test    r14d, r14d
0x180007281  jnz     loc_180007509
0x180007287  mov     [rsp+0F8h+var_A8], r11
0x18000728c  mov     r9d, r11d
0x18000728f  mov     [rsp+0F8h+var_B0], r11
0x180007294  jmp     loc_18000737E
0x180007299  mov     ecx, 10h; Size
0x18000729e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800072a3  mov     r14, rax
0x1800072a6  test    rax, rax
0x1800072a9  jz      loc_18000776F
0x1800072af  mov     [rax], rbx
0x1800072b2  mov     [rax+8], rsi
0x1800072b6  test    rbx, rbx
0x1800072b9  jz      short loc_1800072C4
0x1800072bb  test    rsi, rsi
0x1800072be  jnz     loc_180007993
0x1800072c4  mov     rcx, rbx; Block
0x1800072c7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800072cc  mov     rcx, rsi; Block
0x1800072cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800072d4  mov     rcx, [r14]; Block
0x1800072d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800072dc  mov     rcx, [r14+8]; Block
0x1800072e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800072e5  mov     rcx, r14; Block
0x1800072e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800072ed  mov     r14d, dword ptr [rsp+0F8h+SizeInWords]
0x1800072f2  mov     r9, r15
0x1800072f5  mov     edi, r9d
0x1800072f8  mov     rcx, [rsp+0F8h+var_98]
0x1800072fd  test    rcx, rcx
0x180007300  jnz     short loc_18000733F
0x180007302  test    r9, r9
0x180007305  jnz     loc_1800075F9
0x18000730b  test    r15, r15
0x18000730e  jz      short loc_180007318
0x180007310  mov     rcx, r15; Block
0x180007313  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180007318  mov     eax, edi
0x18000731a  mov     rcx, [rsp+0F8h+var_58]
0x180007322  xor     rcx, rsp; StackCookie
0x180007325  call    __security_check_cookie
0x18000732a  add     rsp, 0B8h
0x180007331  pop     r15
0x180007333  pop     r14
0x180007335  pop     r13
0x180007337  pop     r12
0x180007339  pop     rdi
0x18000733a  pop     rsi
0x18000733b  pop     rbp
0x18000733c  pop     rbx
0x18000733d  retn
0x18000733f  mov     rax, [rcx]
0x180007342  mov     rax, [rax+10h]
0x180007346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000734b  mov     r9, [rsp+0F8h+var_B0]
0x180007350  jmp     short loc_180007302
0x180007352  lea     r8d, [rax+rax]
0x180007356  mov     eax, r8d
0x180007359  add     rax, 4
0x18000735d  cmp     rax, r11
0x180007360  ja      loc_18000783E
0x180007366  add     r9d, r8d
0x180007369  inc     r10d
0x18000736c  cmp     r10d, r14d
0x18000736f  jb      loc_18000759F
0x180007375  mov     r13d, [rsp+0F8h+var_B4]
0x18000737a  mov     edx, dword ptr [rsp+0F8h+SizeInWords]
0x18000737e  add     edx, 10h
0x180007381  lea     r12d, ds:0[r14*4]
0x180007389  add     r12d, r13d
0x18000738c  mov     eax, 2
0x180007391  add     r12d, edx
0x180007394  add     r12d, r9d
0x180007397  shr     r12, 1
0x18000739a  mul     r12
0x18000739d  cmovb   rax, rdi
0x1800073a1  mov     rcx, rax; unsigned __int64
0x1800073a4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800073a9  mov     r15, rax
0x1800073ac  test    rax, rax
0x1800073af  jz      loc_180007687
0x1800073b5  xor     eax, eax
0x1800073b7  mov     [rsp+0F8h+var_D0], rsi
0x1800073bc  lea     r9, aSS_0; "%s.%s("
0x1800073c3  mov     [r15], ax
0x1800073c7  mov     r8, rdi; MaxCount
0x1800073ca  mov     [rsp+0F8h+var_D8], rbx
0x1800073cf  mov     rdx, r12; BufferCount
0x1800073d2  mov     rcx, r15; Buffer
0x1800073d5  call    cs:__imp__snwprintf_s
0x1800073dc  nop     dword ptr [rax+rax+00h]
0x1800073e1  cmp     eax, 0FFFFFFFFh
0x1800073e4  jz      loc_180007687
0x1800073ea  mov     r13, [rsp+0F8h+var_A8]
0x1800073ef  lea     ebx, [r14-1]
0x1800073f3  test    ebx, ebx
0x1800073f5  jns     loc_1800074A6
0x1800073fb  lea     r8, Source; ");\r\n"
0x180007402  mov     rdx, r12; SizeInWords
0x180007405  mov     rcx, r15; Destination
0x180007408  call    cs:__imp_wcscat_s
0x18000740f  nop     dword ptr [rax+rax+00h]
0x180007414  test    eax, eax
0x180007416  jnz     loc_180007687
0x18000741c  nop     dword ptr [rax+00h]
0x180007420  inc     rdi
0x180007423  cmp     word ptr [r15+rdi*2], 0
0x180007429  jnz     short loc_180007420
0x18000742b  mov     r13, [rsp+0F8h+var_A0]
0x180007430  add     edi, edi
0x180007432  jz      loc_180007677
0x180007438  mov     rbx, [r13+8]
0x18000743c  mov     ebp, [rbx+4]
0x18000743f  cmp     edi, ebp
0x180007441  mov     ecx, [rbx+10h]
0x180007444  mov     eax, [rbx]
0x180007446  cmovbe  ebp, edi
0x180007449  sub     eax, ecx
0x18000744b  lea     r10d, [rbp+4]
0x18000744f  cmp     eax, r10d
0x180007452  jbe     loc_1800078F3
0x180007458  mov     edx, [rbx+14h]
0x18000745b  cmp     ecx, edx
0x18000745d  jnb     loc_18000762C
0x180007463  mov     eax, edx
0x180007465  sub     eax, ecx
0x180007467  cmp     eax, r10d
0x18000746a  ja      loc_18000762C
0x180007470  mov     r11d, 0FFFEh
0x180007476  lea     r9d, [r10+rcx]
0x18000747a  nop     word ptr [rax+rax+00h]
0x180007480  cmp     edx, r9d
0x180007483  ja      loc_180007629
0x180007489  mov     rax, [rbx+8]
0x18000748d  mov     ecx, edx
0x18000748f  movzx   r8d, word ptr [rcx+rax]
0x180007494  cmp     r8w, r11w
0x180007498  jz      loc_180007627
0x18000749e  add     edx, 2
0x1800074a1  add     edx, r8d
0x1800074a4  jmp     short loc_180007480
0x1800074a6  movsxd  rax, ebx
0x1800074a9  mov     r10, rdi
0x1800074ac  mov     r8, [r13+rax*8+0]; Source
0x1800074b1  inc     r10
0x1800074b4  cmp     word ptr [r8+r10*2], 0
0x1800074ba  jnz     short loc_1800074B1
0x1800074bc  xor     edx, edx
0x1800074be  add     r10d, r10d
0x1800074c1  mov     eax, ebp
0x1800074c3  mov     ecx, r10d
0x1800074c6  div     r14d
0x1800074c9  add     rcx, 4
0x1800074cd  mov     rdx, r12; SizeInWords
0x1800074d0  mov     r9d, eax
0x1800074d3  add     eax, 0FFFFFFFCh
0x1800074d6  cmp     rcx, r9
0x1800074d9  mov     rcx, r15; Destination
0x1800074dc  cmovbe  eax, r10d
0x1800074e0  mov     r9d, eax
0x1800074e3  shr     r9, 1; MaxCount
0x1800074e6  call    cs:__imp_wcsncat_s
0x1800074ed  nop     dword ptr [rax+rax+00h]
0x1800074f2  test    eax, eax
0x1800074f4  jnz     loc_180007687
0x1800074fa  test    ebx, ebx
0x1800074fc  jg      loc_180007818
0x180007502  dec     ebx
0x180007504  jmp     loc_1800073F3
0x180007509  lea     ecx, [r14+r14*2]
0x18000750d  mov     eax, ebp
0x18000750f  shl     ecx, 2
0x180007512  add     rcx, rcx
0x180007515  cmp     rax, rcx
0x180007518  jb      loc_1800072F2
0x18000751e  mov     r12d, r14d
0x180007521  mov     eax, 8
0x180007526  mul     r12
0x180007529  cmovb   rax, rdi
0x18000752d  mov     rcx, rax; unsigned __int64
0x180007530  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007535  mov     [rsp+0F8h+var_B0], rax
0x18000753a  mov     r9, rax
0x18000753d  test    rax, rax
0x180007540  jz      loc_1800075F1
0x180007546  lea     r8, ds:0[r14*8]; Size
0x18000754e  xor     edx, edx; Val
0x180007550  mov     rcx, rax; void *
0x180007553  call    memset_0
0x180007558  xor     r12d, r12d
0x18000755b  mov     rcx, [rsp+0F8h+var_B0]
0x180007560  mov     rax, [rsp+0F8h+var_A8]
0x180007565  lea     r8, [rcx+r12*8]; unsigned __int16 **
0x180007569  mov     rax, [rax]
0x18000756c  lea     rcx, [r12+r12*2]; this
0x180007570  lea     rdx, [rax+rcx*8]; struct VAR *
0x180007574  call    ?JAmsiVarParameterToString@JAmsi@@AEAA_NPEBVVAR@@PEAPEAG@Z; JAmsi::JAmsiVarParameterToString(VAR const *,ushort * *)
0x180007579  test    al, al
0x18000757b  jz      short loc_1800075EC
0x18000757d  inc     r12d
0x180007580  cmp     r12d, r14d
0x180007583  jb      short loc_18000755B
0x180007585  mov     r13, [rsp+0F8h+var_B0]
0x18000758a  xor     edx, edx
0x18000758c  mov     eax, ebp
0x18000758e  mov     [rsp+0F8h+var_A8], r13
0x180007593  div     r14d
0x180007596  xor     r9d, r9d
0x180007599  mov     r11d, eax
0x18000759c  xor     r10d, r10d
0x18000759f  lea     r15, ds:0[r10*8]
0x1800075a7  mov     rax, rdi
  ... truncated ...
```
