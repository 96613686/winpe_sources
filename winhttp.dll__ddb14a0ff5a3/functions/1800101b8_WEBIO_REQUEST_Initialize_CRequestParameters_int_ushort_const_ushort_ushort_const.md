# WEBIO_REQUEST::Initialize(CRequestParameters *,int,ushort const *,ushort,ushort const *)

- ea: `0x1800101b8`
- end: `0x180010a56`
- name: `?Initialize@WEBIO_REQUEST@@QEAAKPEAVCRequestParameters@@HPEBGG1@Z`
- size: `2206`
- prototype: `unsigned int __fastcall(WEBIO_REQUEST *__hidden this, struct CRequestParameters *, int, const unsigned __int16 *, unsigned __int16, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002daa4`

## callees

- `0x18000f318`
- `0x1800101b8`
- `0x180010a5c`
- `0x180010f50`
- `0x180019384`
- `0x1800193a0`
- `0x18001ce20`
- `0x18001cf34`
- `0x180032c78`
- `0x180041eb0`
- `0x18006aea0`
- `0x18009af18`
- `0x1800a1d10`
- `0x1800a3da8`
- `0x1800a3db4`
- `0x1800cdd7c`
- `0x1800de010`

## import_xrefs

- `webio!__imp_WebCreateHttpRequest` at `0x180010704`
- `webio!__imp_WebCreateHttpRequest` at `0x180010704`
- `webio!__imp_WebCreateUri` at `0x180010561`
- `webio!__imp_WebCreateUri` at `0x180010561`
- `webio!__imp_WebDeleteUri` at `0x1800107df`
- `webio!__imp_WebDeleteUri` at `0x1800107df`
- `webio!__imp_WebSetHttpRequestOption` at `0x1800108f3`
- `webio!__imp_WebSetHttpRequestOption` at `0x1800108f3`
- `webio!__imp_WebSetHttpRequestInformationRoutine` at `0x18001079f`
- `webio!__imp_WebSetHttpRequestInformationRoutine` at `0x18001079f`

## pseudocode

```c
__int64 __fastcall WEBIO_REQUEST::Initialize(
        WEBIO_REQUEST *this,
        struct CRequestParameters *a2,
        int a3,
        const unsigned __int16 *a4,
        unsigned __int16 a5,
        const unsigned __int16 *a6)
{
  __int64 v7; // rax
  __int64 *v8; // rdi
  const unsigned __int16 *v9; // r15
  __int64 *v11; // rax
  __int64 *v12; // r10
  unsigned int v13; // r11d
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  const wchar_t *v16; // rax
  unsigned int v17; // r12d
  unsigned __int64 v18; // r14
  unsigned __int64 v19; // r15
  __int64 v20; // rbx
  __int64 *v21; // r13
  __int64 *v22; // rax
  const unsigned __int16 *v23; // rdx
  __int64 v24; // rdx
  const unsigned __int16 *v25; // rax
  int v26; // r8d
  unsigned __int64 v27; // r9
  __int64 v28; // rdx
  const wchar_t *v29; // rax
  unsigned __int64 v30; // r9
  unsigned int v31; // r8d
  _WORD *v32; // r15
  __int16 v33; // ax
  __int64 v34; // r14
  int v35; // ebx
  int v36; // ecx
  __int64 v37; // rax
  const void *v38; // r9
  __int64 v39; // rcx
  _WORD *v40; // rax
  int v41; // edx
  unsigned __int64 v42; // r8
  int v43; // eax
  __int64 v44; // rcx
  __int64 **v45; // rbx
  unsigned __int64 v46; // rax
  unsigned __int64 v47; // r14
  __int64 v48; // rax
  const unsigned __int16 *v49; // rax
  unsigned __int64 v50; // r15
  __int64 *v51; // rax
  unsigned __int64 v52; // r10
  _QWORD *v53; // rbx
  unsigned int v54; // eax
  void *v55; // rax
  unsigned int v57; // eax
  unsigned int v58; // eax
  unsigned int v59; // eax
  unsigned int v60; // ebx
  int v61; // eax
  unsigned int v62; // ecx
  unsigned __int64 v63; // r10
  unsigned __int64 v64; // r10
  unsigned int appended; // eax
  __int64 v68; // [rsp+38h] [rbp-41h] BYREF
  _OWORD v69[2]; // [rsp+40h] [rbp-39h] BYREF
  __int64 *v70; // [rsp+60h] [rbp-19h] BYREF
  __int64 v71; // [rsp+68h] [rbp-11h]
  __int16 v72; // [rsp+82h] [rbp+9h] BYREF
  _WORD v73[2]; // [rsp+84h] [rbp+Bh] BYREF

  v7 = *((_QWORD *)a2 + 12);
  v8 = 0;
  v71 = 0;
  v68 = v7;
  v9 = a4;
  memset(v69, 0, sizeof(v69));
  v11 = (__int64 *)operator new[](0xFEu);
  v12 = 0;
  if ( !v11 )
  {
    v17 = 8;
    LODWORD(v20) = 8;
    goto LABEL_74;
  }
  v70 = v11;
  v13 = 127;
  HIDWORD(v71) = 127;
  v14 = 0x7FFFFFFF;
  *(_WORD *)v11 = 0;
  v15 = 0x7FFFFFFF;
  LODWORD(v71) = 1;
  v8 = v11;
  if ( a3 == 1 )
  {
    v49 = L"http://";
    do
    {
      if ( !*v49 )
        break;
      ++v49;
      --v15;
    }
    while ( v15 );
    v17 = 8;
    v18 = (0x7FFFFFFF - v15) & -(__int64)(v15 != 0);
    if ( v15 || (LODWORD(v20) = SafeStrHresultToWin32(-2147024809), v18 = (unsigned __int64)v12, !(_DWORD)v20) )
    {
      v50 = v18 + 1;
      if ( v18 < v18 + 1 )
      {
        if ( v50 <= v14 )
        {
          v20 = (unsigned int)v12;
          if ( v18 != -1 )
          {
            v21 = v12;
            if ( v50 > v13 )
            {
              v51 = (__int64 *)operator new[](saturated_mul(v50, 2u));
              LOWORD(v12) = 0;
              if ( !v51 )
              {
LABEL_102:
                LODWORD(v20) = 8;
                goto LABEL_18;
              }
              v21 = v8;
              v70 = v51;
              v8 = v51;
              HIDWORD(v71) = v18 + 1;
            }
            if ( !v18 )
            {
LABEL_16:
              LODWORD(v71) = v18 + 1;
              *((_WORD *)v8 + v18) = (_WORD)v12;
              if ( v21 )
              {
                operator delete(v21);
                LOWORD(v12) = 0;
              }
              goto LABEL_18;
            }
            v23 = L"http://";
LABEL_15:
            memcpy_0(v8, v23, 2 * v18);
            LOWORD(v12) = 0;
            goto LABEL_16;
          }
LABEL_88:
          operator delete(v8);
          LOWORD(v12) = 0;
          v8 = 0;
          v70 = 0;
          v71 = v20;
LABEL_18:
          v9 = a4;
          goto LABEL_19;
        }
LABEL_106:
        LODWORD(v20) = 13;
        goto LABEL_18;
      }
LABEL_104:
      LODWORD(v20) = 87;
      goto LABEL_18;
    }
  }
  else
  {
    v16 = L"https://";
    do
    {
      if ( !*v16 )
        break;
      ++v16;
      --v15;
    }
    while ( v15 );
    v17 = 8;
    v18 = (0x7FFFFFFF - v15) & -(__int64)(v15 != 0);
    if ( v15 || (LODWORD(v20) = SafeStrHresultToWin32(-2147024809), v18 = (unsigned __int64)v12, !(_DWORD)v20) )
    {
      v19 = v18 + 1;
      if ( v18 < v18 + 1 )
      {
        if ( v19 <= v14 )
        {
          v20 = (unsigned int)v12;
          if ( v18 != -1 )
          {
            v21 = v12;
            if ( v19 <= v13 )
            {
LABEL_13:
              if ( !v18 )
                goto LABEL_16;
              v23 = L"https://";
              goto LABEL_15;
            }
            v22 = (__int64 *)operator new[](saturated_mul(v19, 2u));
            LOWORD(v12) = 0;
            if ( v22 )
            {
              v21 = v8;
              v70 = v22;
              v8 = v22;
              HIDWORD(v71) = v18 + 1;
              goto LABEL_13;
            }
            goto LABEL_102;
          }
          goto LABEL_88;
        }
        goto LABEL_106;
      }
      goto LABEL_104;
    }
  }
LABEL_19:
  if ( (_DWORD)v20 )
    goto LABEL_74;
  if ( v9 )
  {
    v24 = 0x7FFFFFFF;
    v25 = v9;
    do
    {
      if ( *v25 == (_WORD)v12 )
        break;
      ++v25;
      --v24;
    }
    while ( v24 );
    v26 = v24 == 0 ? 0x80070057 : 0;
    v27 = (0x7FFFFFFF - v24) & -(__int64)(v24 != 0);
    if ( v24 )
      goto LABEL_25;
  }
  else
  {
    v26 = -2147024809;
  }
  LODWORD(v20) = SafeStrHresultToWin32(v26);
  v27 = v63;
  if ( (_DWORD)v20 )
    goto LABEL_74;
LABEL_25:
  LODWORD(v20) = CStringTemplate<unsigned short>::Append((__int64)&v70, v9, v27);
  if ( (_DWORD)v20 )
    goto LABEL_113;
  v28 = 0x7FFFFFFF;
  v29 = L":";
  do
  {
    if ( !*v29 )
      break;
    ++v29;
    --v28;
  }
  while ( v28 );
  if ( (v30 = (0x7FFFFFFF - v28) & -(__int64)(v28 != 0), !v28)
    && (LODWORD(v20) = SafeStrHresultToWin32(-2147024809), v30 = v64, (_DWORD)v20)
    || (LODWORD(v20) = CStringTemplate<unsigned short>::Append((__int64)&v70, L":", v30), (_DWORD)v20) )
  {
LABEL_113:
    v8 = v70;
    goto LABEL_74;
  }
  v31 = a5;
  v73[0] = 0;
  if ( !a5 )
  {
    v72 = 48;
    v61 = CStringTemplate<unsigned short>::Append((__int64)&v70, &v72, 1u);
    v8 = v70;
    LODWORD(v20) = v61;
    goto LABEL_42;
  }
  v32 = v73;
  do
  {
    --v32;
    v33 = v31 % 0xA;
    v31 /= 0xAu;
    *v32 = v33 + 48;
  }
  while ( v31 );
  v34 = v73 - v32;
  if ( (_DWORD)v34 )
  {
    v35 = v71;
    v36 = v71 - 1;
    if ( !(_DWORD)v71 )
      v36 = 0;
    if ( (unsigned __int64)(unsigned int)v34 + 1 <= (unsigned int)(HIDWORD(v71) - v36) )
      goto LABEL_38;
    v58 = v71 - 1;
    if ( !(_DWORD)v71 )
      v58 = 0;
    if ( (unsigned int)v34 + (unsigned __int64)v58 + 1 < (unsigned int)v34 )
    {
      LODWORD(v20) = 534;
    }
    else
    {
      v59 = v71 - 1;
      if ( (_DWORD)v71 )
      {
        v60 = v71 - 1;
      }
      else
      {
        v59 = 0;
        v60 = 0;
      }
      LODWORD(v20) = CStringTemplate<unsigned short>::SetString(&v70, v70, v60, (unsigned int)v34 + v59 + 1LL);
      if ( !(_DWORD)v20 )
      {
        v35 = v71;
LABEL_38:
        if ( v35 )
          v37 = (unsigned int)(v35 - 1);
        else
          v37 = 0;
        v8 = v70;
        memcpy_0((char *)v70 + 2 * v37, v32, 2LL * (unsigned int)v34);
        LODWORD(v71) = v34 + v35;
        *((_WORD *)v8 + (((_DWORD)v34 + v35 - 1) & (unsigned int)-((_DWORD)v34 + v35 != 0))) = 0;
        goto LABEL_41;
      }
    }
    v8 = v70;
    goto LABEL_42;
  }
  v8 = v70;
LABEL_41:
  LODWORD(v20) = 0;
LABEL_42:
  if ( (_DWORD)v20 )
    goto LABEL_74;
  if ( **((_WORD **)a2 + 14) != 47 )
  {
    appended = CStringTemplate<unsigned short>::AppendStrlen((__int64)&v70, L"/");
    v8 = v70;
    LODWORD(v20) = appended;
    if ( appended )
      goto LABEL_74;
  }
  v38 = (const void *)*((_QWORD *)a2 + 14);
  if ( !v38 )
  {
    v41 = -2147024809;
    goto LABEL_73;
  }
  v39 = 0x7FFFFFFF;
  v40 = (_WORD *)*((_QWORD *)a2 + 14);
  do
  {
    if ( !*v40 )
      break;
    ++v40;
    --v39;
  }
  while ( v39 );
  v41 = v39 == 0 ? 0x80070057 : 0;
  v42 = (0x7FFFFFFF - v39) & -(__int64)(v39 != 0);
  if ( !v39 )
  {
LABEL_73:
    LODWORD(v20) = SafeStrHresultToWin32(v41);
    v42 = v52;
    if ( (_DWORD)v20 )
      goto LABEL_74;
  }
  v43 = CStringTemplate<unsigned short>::Append((__int64)&v70, v38, v42);
  v8 = v70;
  LODWORD(v20) = v43;
  if ( !v43 )
  {
    LODWORD(v20) = WebCreateUri(v70, 1, v69);
    if ( !(_DWORD)v20 )
    {
      v45 = (__int64 **)((char *)this + 168);
      if ( v8 )
      {
        v46 = WxSizeHeapEx(v44, v8);
        if ( v46 != -1 && (v46 & 1) == 0 && v46 >= 2 )
        {
          v47 = (v46 - 2) >> 1;
          CWxString::_Release((WEBIO_REQUEST *)((char *)this + 168));
          *v45 = v8;
          *((_DWORD *)this + 45) = v47;
          if ( v8 != qword_1800E7D10 )
          {
            v48 = -1;
            *((_WORD *)v8 + (unsigned int)v47) = 0;
            do
              ++v48;
            while ( *((_WORD *)*v45 + v48) );
            *((_DWORD *)this + 44) = v48;
          }
        }
      }
      else
      {
        CWxString::Empty((WEBIO_REQUEST *)((char *)this + 168));
      }
      WORD4(v69[0]) = *((_WORD *)a2 + 44);
      WORD5(v69[0]) = *((_WORD *)a2 + 46);
      goto LABEL_77;
    }
  }
LABEL_74:
  if ( v8 )
    operator delete(v8);
  if ( (_DWORD)v20 )
  {
    v17 = v20;
    goto LABEL_83;
  }
LABEL_77:
  v53 = (_QWORD *)((char *)this + 184);
  v54 = WebCreateHttpRequest(*(_QWORD *)(*((_QWORD *)this + 96) + 560LL), 0, &v68, (char *)this + 184);
  if ( v54 )
    goto LABEL_100;
  v55 = operator new[](saturated_mul(*((unsigned int *)this + 32), 2u));
  *((_QWORD *)this + 102) = v55;
  if ( v55 )
  {
    *((_DWORD *)this + 206) = *((_DWORD *)this + 32);
    *(_QWORD *)((char *)this + 828) = 0;
    if ( !a6 || (v57 = CWxString::Set((WEBIO_REQUEST *)((char *)this + 936), a6), (v17 = WX_WIN32_FROM_HR(v57)) == 0) )
    {
      if ( !*((_DWORD *)this + 216) || (v54 = WebSetHttpRequestOption(*v53, 16397, (char *)this + 868, 16)) == 0 )
      {
        (**(void (__fastcall ***)(WEBIO_REQUEST *))this)(this);
        WxEtwGetActivityId((struct _GUID *)((char *)this + 844));
        v17 = WebSetHttpRequestInformationRoutine(*v53, 0x80000000LL, WEBIO_REQUEST::_OnInformation, this);
        if ( !v17 )
        {
          *((_DWORD *)this + 62) = 0;
          *((_QWORD *)this + 30) = this;
          *((_DWORD *)this + 172) = 0;
          *((_DWORD *)this + 118) = 0;
          *((_QWORD *)this + 58) = this;
          goto LABEL_83;
        }
        (*(void (__fastcall **)(WEBIO_REQUEST *))(*(_QWORD *)this + 8LL))(this);
        v62 = v17;
        goto LABEL_101;
      }
LABEL_100:
      v62 = v54;
LABEL_101:
      v17 = SET_WINHTTP_ERROR_FROM_WIN32(v62);
    }
  }
LABEL_83:
  if ( *(_QWORD *)&v69[0] )
    WebDeleteUri();
  return v17;
}

```

## disassembly

```asm
0x1800101b8  mov     [rsp-8+arg_10], rbx
0x1800101bd  push    rbp
0x1800101be  push    rsi
0x1800101bf  push    rdi
0x1800101c0  push    r12
0x1800101c2  push    r13
0x1800101c4  push    r14
0x1800101c6  push    r15
0x1800101c8  lea     rbp, [rsp-17h]
0x1800101cd  sub     rsp, 90h
0x1800101d4  mov     rax, cs:__security_cookie
0x1800101db  xor     rax, rsp
0x1800101de  mov     [rbp+47h+var_38], rax
0x1800101e2  mov     rax, [rbp+47h+arg_28]
0x1800101e6  mov     rsi, rcx
0x1800101e9  xor     ecx, ecx
0x1800101eb  mov     [rbp+47h+var_90], rax
0x1800101ef  mov     rax, [rdx+60h]
0x1800101f3  mov     edi, ecx
0x1800101f5  mov     [rbp+47h+var_58], rcx
0x1800101f9  xorps   xmm0, xmm0
0x1800101fc  xorps   xmm1, xmm1
0x1800101ff  mov     [rbp+47h+var_88], rax
0x180010203  mov     ecx, 0FEh; unsigned __int64
0x180010208  mov     [rbp+47h+var_A0], r9
0x18001020c  mov     r15, r9
0x18001020f  mov     [rbp+47h+var_98], rdx
0x180010213  mov     ebx, r8d
0x180010216  movdqu  [rbp+47h+var_80], xmm0
0x18001021b  movdqu  [rbp+47h+var_70], xmm1
0x180010220  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010225  xor     r10d, r10d
0x180010228  test    rax, rax
0x18001022b  jz      loc_1800108D0
0x180010231  mov     [rbp+47h+var_60], rax
0x180010235  lea     r11d, [r10+7Fh]
0x180010239  mov     dword ptr [rbp+47h+var_58+4], r11d
0x18001023d  mov     r9d, 7FFFFFFFh
0x180010243  mov     [rax], r10w
0x180010247  mov     edx, r9d
0x18001024a  mov     dword ptr [rbp+47h+var_58], 1
0x180010251  mov     rdi, rax
0x180010254  cmp     ebx, 1
0x180010257  jz      loc_1800105F3
0x18001025d  lea     rax, aHttps; "https://"
0x180010264  cmp     [rax], r10w
0x180010268  jz      short loc_180010274
0x18001026a  add     rax, 2
0x18001026e  sub     rdx, 1; unsigned __int64
0x180010272  jnz     short loc_180010264
0x180010274  mov     rax, rdx
0x180010277  mov     rcx, r9
0x18001027a  neg     rax
0x18001027d  mov     r12d, 8
0x180010283  mov     rax, rdx
0x180010286  sbb     r8d, r8d
0x180010289  sub     rcx, rdx
0x18001028c  not     r8d
0x18001028f  and     r8d, 80070057h
0x180010296  neg     rax
0x180010299  sbb     r14, r14
0x18001029c  and     r14, rcx
0x18001029f  test    rdx, rdx
0x1800102a2  jz      loc_1800109C5
0x1800102a8  lea     r15, [r14+1]
0x1800102ac  cmp     r14, r15
0x1800102af  jnb     loc_180010949
0x1800102b5  cmp     r15, r9
0x1800102b8  ja      loc_180010959
0x1800102be  mov     ebx, r10d
0x1800102c1  test    r15, r15
0x1800102c4  jz      loc_180010834
0x1800102ca  mov     eax, r11d
0x1800102cd  mov     r13, r10
0x1800102d0  cmp     r15, rax
0x1800102d3  jbe     short loc_18001030A
0x1800102d5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800102dc  mov     eax, 2
0x1800102e1  mul     r15
0x1800102e4  cmovb   rax, rcx
0x1800102e8  mov     rcx, rax; unsigned __int64
0x1800102eb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800102f0  xor     r10d, r10d
0x1800102f3  test    rax, rax
0x1800102f6  jz      loc_180010920
0x1800102fc  mov     r13, rdi
0x1800102ff  mov     [rbp+47h+var_60], rax
0x180010303  mov     rdi, rax
0x180010306  mov     dword ptr [rbp+47h+var_58+4], r15d
0x18001030a  test    r14, r14
0x18001030d  jz      short loc_180010325
0x18001030f  lea     rdx, aHttps; "https://"
0x180010316  lea     r8, [r14+r14]; Size
0x18001031a  mov     rcx, rdi; void *
0x18001031d  call    memcpy_0
0x180010322  xor     r10d, r10d
0x180010325  lea     eax, [r14+1]
0x180010329  mov     dword ptr [rbp+47h+var_58], eax
0x18001032c  mov     [rdi+r14*2], r10w
0x180010331  test    r13, r13
0x180010334  jnz     loc_180010910
0x18001033a  mov     r15, [rbp+47h+var_A0]
0x18001033e  test    ebx, ebx
0x180010340  jnz     loc_1800106D1
0x180010346  mov     r14d, 7FFFFFFFh
0x18001034c  test    r15, r15
0x18001034f  jz      loc_1800109F9
0x180010355  mov     edx, r14d
0x180010358  mov     rax, r15
0x18001035b  cmp     [rax], r10w
0x18001035f  jz      short loc_18001036B
0x180010361  add     rax, 2
0x180010365  sub     rdx, 1
0x180010369  jnz     short loc_18001035B
0x18001036b  mov     rax, rdx
0x18001036e  mov     r13d, 80070057h
0x180010374  neg     rax
0x180010377  mov     rcx, r14
0x18001037a  mov     rax, rdx
0x18001037d  sbb     r8d, r8d
0x180010380  sub     rcx, rdx
0x180010383  not     r8d
0x180010386  and     r8d, r13d
0x180010389  neg     rax
0x18001038c  sbb     r9, r9
0x18001038f  and     r9, rcx
0x180010392  test    rdx, rdx
0x180010395  jz      loc_18001098D
0x18001039b  mov     r8, r9
0x18001039e  lea     rcx, [rbp+47h+var_60]
0x1800103a2  mov     rdx, r15
0x1800103a5  call    ?Append@?$CStringTemplate@G@@QEAAKPEBG_K@Z; CStringTemplate<ushort>::Append(ushort const *,unsigned __int64)
0x1800103aa  xor     r10d, r10d
0x1800103ad  mov     ebx, eax
0x1800103af  test    eax, eax
0x1800103b1  jnz     loc_1800109BC
0x1800103b7  mov     rdx, r14
0x1800103ba  lea     rax, asc_1800E6F78; ":"
0x1800103c1  cmp     [rax], r10w
0x1800103c5  jz      short loc_1800103D1
0x1800103c7  add     rax, 2
0x1800103cb  sub     rdx, 1
0x1800103cf  jnz     short loc_1800103C1
0x1800103d1  mov     rax, rdx
0x1800103d4  mov     rcx, r14
0x1800103d7  neg     rax
0x1800103da  mov     rax, rdx
0x1800103dd  sbb     r8d, r8d
0x1800103e0  sub     rcx, rdx
0x1800103e3  not     r8d
0x1800103e6  and     r8d, r13d
0x1800103e9  neg     rax
0x1800103ec  sbb     r9, r9
0x1800103ef  and     r9, rcx
0x1800103f2  test    rdx, rdx
0x1800103f5  jz      loc_1800109A7
0x1800103fb  mov     r8, r9
0x1800103fe  lea     rdx, asc_1800E6F78; ":"
0x180010405  lea     rcx, [rbp+47h+var_60]
0x180010409  call    ?Append@?$CStringTemplate@G@@QEAAKPEBG_K@Z; CStringTemplate<ushort>::Append(ushort const *,unsigned __int64)
0x18001040e  xor     r10d, r10d
0x180010411  mov     ebx, eax
0x180010413  test    eax, eax
0x180010415  jnz     loc_1800109BC
0x18001041b  movzx   r8d, [rbp+47h+arg_20]
0x180010420  lea     r9d, [rax+30h]
0x180010424  mov     [rbp+47h+var_3C], r10w
0x180010429  test    r8d, r8d
0x18001042c  jz      loc_1800108AA
0x180010432  lea     r15, [rbp+47h+var_3C]
0x180010436  sub     r15, 2
0x18001043a  mov     eax, 0CCCCCCCDh
0x18001043f  mul     r8d
0x180010442  shr     edx, 3
0x180010445  mov     al, dl
0x180010447  shl     al, 2
0x18001044a  lea     ecx, [rax+rdx]
0x18001044d  add     cl, cl
0x18001044f  sub     r8b, cl
0x180010452  movsx   eax, r8b
0x180010456  mov     r8d, edx
0x180010459  add     ax, r9w
0x18001045d  mov     [r15], ax
0x180010461  test    edx, edx
0x180010463  jnz     short loc_180010436
0x180010465  lea     r14, [rbp+47h+var_3C]
0x180010469  sub     r14, r15
0x18001046c  sar     r14, 1
0x18001046f  test    r14d, r14d
0x180010472  jz      loc_180010928
0x180010478  mov     ebx, dword ptr [rbp+47h+var_58]
0x18001047b  lea     ecx, [rbx-1]
0x18001047e  test    ebx, ebx
0x180010480  jnz     short loc_180010485
0x180010482  mov     ecx, r10d
0x180010485  mov     eax, dword ptr [rbp+47h+var_58+4]
0x180010488  sub     eax, ecx
0x18001048a  mov     edi, r14d
0x18001048d  mov     ecx, eax
0x18001048f  lea     rax, [rdi+1]
0x180010493  cmp     rax, rcx
0x180010496  ja      loc_18001084D
0x18001049c  test    ebx, ebx
0x18001049e  jz      loc_1800106B5
0x1800104a4  lea     eax, [rbx-1]
0x1800104a7  lea     r8, [rdi+rdi]; Size
0x1800104ab  mov     rdx, r15; Src
0x1800104ae  mov     rdi, [rbp+47h+var_60]
0x1800104b2  lea     rcx, [rdi+rax*2]; void *
0x1800104b6  call    memcpy_0
0x1800104bb  add     ebx, r14d
0x1800104be  mov     dword ptr [rbp+47h+var_58], ebx
0x1800104c1  lea     ecx, [rbx-1]
0x1800104c4  neg     ebx
0x1800104c6  sbb     eax, eax
0x1800104c8  and     eax, ecx
0x1800104ca  xor     r10d, r10d
0x1800104cd  mov     [rdi+rax*2], r10w
0x1800104d2  mov     ebx, r10d
0x1800104d5  mov     r14d, 7FFFFFFFh
0x1800104db  test    ebx, ebx
0x1800104dd  jnz     loc_1800106D1
0x1800104e3  mov     r15, [rbp+47h+var_98]
0x1800104e7  mov     rax, [r15+70h]
0x1800104eb  cmp     word ptr [rax], 2Fh ; '/'
0x1800104ef  jnz     loc_180010A04
0x1800104f5  mov     r9, [r15+70h]
0x1800104f9  test    r9, r9
0x1800104fc  jz      loc_180010A2A
0x180010502  mov     rcx, r14
0x180010505  mov     rax, r9
0x180010508  cmp     [rax], r10w
0x18001050c  jz      short loc_180010518
0x18001050e  add     rax, 2
0x180010512  sub     rcx, 1
0x180010516  jnz     short loc_180010508
0x180010518  mov     rax, rcx
0x18001051b  neg     rax
0x18001051e  mov     rax, rcx
0x180010521  sbb     edx, edx
0x180010523  sub     r14, rcx
0x180010526  not     edx
0x180010528  and     edx, r13d
0x18001052b  neg     rax
0x18001052e  sbb     r8, r8
0x180010531  and     r8, r14
0x180010534  test    rcx, rcx
0x180010537  jz      loc_1800106BD
0x18001053d  mov     rdx, r9
0x180010540  lea     rcx, [rbp+47h+var_60]
0x180010544  call    ?Append@?$CStringTemplate@G@@QEAAKPEBG_K@Z; CStringTemplate<ushort>::Append(ushort const *,unsigned __int64)
0x180010549  mov     rdi, [rbp+47h+var_60]
0x18001054d  mov     ebx, eax
0x18001054f  test    eax, eax
0x180010551  jnz     loc_1800106D1
0x180010557  lea     r8, [rbp+47h+var_80]
0x18001055b  mov     rcx, rdi
0x18001055e  lea     edx, [rax+1]
0x180010561  call    cs:__imp_WebCreateUri
0x180010567  mov     ebx, eax
0x180010569  test    eax, eax
0x18001056b  jnz     loc_1800106D1
0x180010571  lea     rbx, [rsi+0A8h]
0x180010578  test    rdi, rdi
0x18001057b  jz      loc_180010A32
0x180010581  mov     rdx, rdi
0x180010584  call    WxSizeHeapEx
0x180010589  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001058d  cmp     rax, r13
0x180010590  jz      short loc_1800105DC
0x180010592  test    al, 1
0x180010594  jnz     short loc_1800105DC
0x180010596  cmp     rax, 2
0x18001059a  jb      short loc_1800105DC
0x18001059c  lea     r14, [rax-2]
0x1800105a0  shr     r14, 1
0x1800105a3  mov     rcx, rbx; this
0x1800105a6  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800105ab  lea     rax, qword_1800E7D10
0x1800105b2  mov     [rbx], rdi
0x1800105b5  mov     [rbx+0Ch], r14d
0x1800105b9  cmp     rdi, rax
0x1800105bc  jz      short loc_1800105DC
0x1800105be  mov     ecx, r14d
0x1800105c1  xor     r10d, r10d
0x1800105c4  mov     rax, r13
0x1800105c7  mov     [rdi+rcx*2], r10w
0x1800105cc  mov     rcx, [rbx]
0x1800105cf  inc     rax
0x1800105d2  cmp     [rcx+rax*2], r10w
0x1800105d7  jnz     short loc_1800105CF
0x1800105d9  mov     [rbx+8], eax
0x1800105dc  movzx   eax, word ptr [r15+58h]
0x1800105e1  mov     word ptr [rbp+47h+var_80+8], ax
0x1800105e5  movzx   eax, word ptr [r15+5Ch]
0x1800105ea  mov     word ptr [rbp+47h+var_80+0Ah], ax
0x1800105ee  jmp     loc_1800106E6
0x1800105f3  lea     rax, aHttp_1; "http://"
0x1800105fa  cmp     [rax], r10w
0x1800105fe  jz      short loc_18001060A
  ... truncated ...
```
