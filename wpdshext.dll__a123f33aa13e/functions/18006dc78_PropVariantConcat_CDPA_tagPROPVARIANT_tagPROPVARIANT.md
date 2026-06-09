# PropVariantConcat(CDPA<tagPROPVARIANT> *,tagPROPVARIANT *)

- ea: `0x18006dc78`
- end: `0x18006e1c5`
- name: `?PropVariantConcat@@YAJPEAV?$CDPA@UtagPROPVARIANT@@@@PEAUtagPROPVARIANT@@@Z`
- size: `1357`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18004b92c`

## callees

- `0x180004110`
- `0x180019d90`
- `0x18001d6b0`
- `0x18002e9f0`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18006dc78`
- `0x180075530`

## import_xrefs

- `ole32!PropVariantCopy` at `0x18006e124`
- `ole32!PropVariantCopy` at `0x18006e124`
- `ole32!CoTaskMemAlloc` at `0x18006dead`
- `ole32!CoTaskMemAlloc` at `0x18006dfd1`
- `ole32!CoTaskMemAlloc` at `0x18006dead`
- `ole32!CoTaskMemAlloc` at `0x18006dfd1`
- `ole32!PropVariantClear` at `0x18006dd08`
- `ole32!PropVariantClear` at `0x18006e164`
- `ole32!PropVariantClear` at `0x18006dd08`
- `ole32!PropVariantClear` at `0x18006e164`

## pseudocode

```c
__int64 __fastcall PropVariantConcat(int **a1, PROPVARIANT *a2)
{
  LARGE_INTEGER *Ptr; // rax
  LARGE_INTEGER *v5; // rbx
  int LowPart_low; // edi
  int v7; // ebx
  HRESULT v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int k; // r14d
  int *v12; // rcx
  int v13; // eax
  const unsigned __int16 **v14; // rax
  const unsigned __int16 **v15; // rbx
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  void *v19; // rax
  int v20; // ebx
  int *v21; // rcx
  int v22; // eax
  __int64 v23; // rax
  int v24; // ebx
  int *v25; // rcx
  int v26; // eax
  __int64 v27; // rax
  int v28; // ecx
  int v29; // edx
  int *v30; // rax
  OLECHAR *QuadPart; // rcx
  int v32; // ebx
  int *v33; // rcx
  int v34; // eax
  __int64 v35; // r14
  __int64 v36; // rax
  int v37; // ebx
  double j; // xmm0_8
  int *v39; // rcx
  int v40; // eax
  __int64 v41; // rax
  int v42; // ebx
  float i; // xmm0_4
  int *v44; // rcx
  int v45; // eax
  __int64 v46; // rax
  PROPVARIANT pvarSrc; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v49[2080]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(v49, 0, sizeof(v49));
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  if ( !a1 || !a2 )
    goto LABEL_94;
  if ( !*a1 || **a1 <= 0 )
  {
    v7 = -2147024809;
    goto LABEL_95;
  }
  PropVariantClear(a2);
  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  Ptr = (LARGE_INTEGER *)IsolationAwareDPA_GetPtr(*a1, 0);
  v5 = Ptr;
  if ( !Ptr )
  {
LABEL_94:
    v7 = -2147467261;
    goto LABEL_95;
  }
  LowPart_low = LOWORD(Ptr->LowPart);
  switch ( LowPart_low )
  {
    case 4:
      pvarSrc.vt = 4;
      v42 = 1;
      for ( i = *(float *)&Ptr[1].LowPart; ; i = pvarSrc.fltVal + *(float *)(v46 + 8) )
      {
        v44 = *a1;
        pvarSrc.fltVal = i;
        v45 = v44 ? *v44 : 0;
        if ( v42 >= v45 )
          break;
        v46 = IsolationAwareDPA_GetPtr(v44, v42);
        if ( !v46 || *(_WORD *)v46 != 4 )
        {
LABEL_33:
          v7 = -2147467259;
          goto LABEL_95;
        }
        ++v42;
      }
      goto LABEL_89;
    case 5:
      pvarSrc.vt = 5;
      v37 = 1;
      for ( j = *(double *)&Ptr[1].QuadPart; ; j = pvarSrc.dblVal + *(double *)(v41 + 8) )
      {
        v39 = *a1;
        pvarSrc.dblVal = j;
        v40 = v39 ? *v39 : 0;
        if ( v37 >= v40 )
          break;
        v41 = IsolationAwareDPA_GetPtr(v39, v37);
        if ( !v41 || *(_WORD *)v41 != (_WORD)LowPart_low )
          goto LABEL_33;
        ++v37;
      }
      goto LABEL_89;
    case 7:
      if ( *a1 )
        v28 = **a1;
      else
        v28 = 0;
      pvarSrc.bstrblobVal.pData = (BYTE *)CoTaskMemAlloc(8LL * v28);
      if ( !pvarSrc.bstrblobVal.pData )
      {
LABEL_35:
        v7 = -2147024882;
        goto LABEL_95;
      }
      if ( *a1 )
        v29 = **a1;
      else
        v29 = 0;
      memset_0(pvarSrc.bstrblobVal.pData, 0, 8LL * v29);
      pvarSrc.vt = 4103;
      v30 = *a1;
      if ( *a1 )
        LODWORD(v30) = *v30;
      pvarSrc.lVal = (int)v30;
      QuadPart = (OLECHAR *)v5[1].QuadPart;
      v32 = 1;
      *pvarSrc.cabstr.pElems = QuadPart;
      while ( 1 )
      {
        v33 = *a1;
        v34 = *a1 ? *v33 : 0;
        if ( v32 >= v34 )
          goto LABEL_89;
        v35 = v32;
        v36 = IsolationAwareDPA_GetPtr(v33, v32);
        if ( !v36 || *(_WORD *)v36 != (_WORD)LowPart_low )
          goto LABEL_33;
        ++v32;
        *(_QWORD *)&pvarSrc.bstrblobVal.pData[8 * v35] = *(_QWORD *)(v36 + 8);
      }
    case 19:
      pvarSrc.vt = 19;
      v24 = 1;
      pvarSrc.lVal = Ptr[1].LowPart;
      while ( 1 )
      {
        v25 = *a1;
        v26 = *a1 ? *v25 : 0;
        if ( v24 >= v26 )
          goto LABEL_89;
        v27 = IsolationAwareDPA_GetPtr(v25, v24);
        if ( !v27 || *(_WORD *)v27 != (_WORD)LowPart_low )
          goto LABEL_33;
        pvarSrc.lVal += *(_DWORD *)(v27 + 8);
        ++v24;
      }
    case 21:
      pvarSrc.vt = 21;
      v20 = 1;
      pvarSrc.hVal = Ptr[1];
      while ( 1 )
      {
        v21 = *a1;
        v22 = *a1 ? *v21 : 0;
        if ( v20 >= v22 )
          goto LABEL_89;
        v23 = IsolationAwareDPA_GetPtr(v21, v20);
        if ( !v23 || *(_WORD *)v23 != (_WORD)LowPart_low )
          goto LABEL_33;
        pvarSrc.hVal.QuadPart += *(_QWORD *)(v23 + 8);
        ++v20;
      }
  }
  if ( LowPart_low != 31 )
  {
    v7 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids,
        LOWORD(Ptr->LowPart));
    goto LABEL_95;
  }
  v8 = StringCchCopyW(v49, 0x820u, (const unsigned __int16 *)Ptr[1].QuadPart);
  v7 = v8;
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_95;
    v10 = 36;
    goto LABEL_19;
  }
  for ( k = 1; ; ++k )
  {
    v12 = *a1;
    v13 = *a1 ? *v12 : 0;
    if ( k >= v13 )
      break;
    v14 = (const unsigned __int16 **)IsolationAwareDPA_GetPtr(v12, k);
    v15 = v14;
    if ( !v14 || *(_WORD *)v14 != (_WORD)LowPart_low )
      goto LABEL_33;
    StringCchCatW(v49, 0x820u, L"; ");
    v16 = StringCchCatW(v49, 0x820u, v15[1]);
    v7 = v16;
    if ( v16 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v18 = 37;
LABEL_32:
        WPP_SF_d(v17[2], v18, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, (unsigned int)v16);
        goto LABEL_95;
      }
      goto LABEL_95;
    }
  }
  v19 = CoTaskMemAlloc(0x1040u);
  pvarSrc.hVal.QuadPart = (LONGLONG)v19;
  if ( !v19 )
    goto LABEL_35;
  memset_0(v19, 0, 0x1040u);
  pvarSrc.vt = LowPart_low;
  v16 = StringCchCopyW(pvarSrc.bstrVal, 0x820u, v49);
  v7 = v16;
  if ( v16 >= 0 )
  {
LABEL_89:
    v8 = PropVariantCopy(a2, &pvarSrc);
    v7 = v8;
    if ( v8 >= 0 )
      goto LABEL_95;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_95;
    v10 = 40;
LABEL_19:
    WPP_SF_d(v9[2], v10, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, (unsigned int)v8);
    goto LABEL_95;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v18 = 38;
    goto LABEL_32;
  }
LABEL_95:
  PropVariantClear(&pvarSrc);
  if ( v7 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids,
      (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006dc78  mov     [rsp-8+arg_10], rbx
0x18006dc7d  mov     [rsp-8+arg_18], rsi
0x18006dc82  push    rbp
0x18006dc83  push    rdi
0x18006dc84  push    r12
0x18006dc86  push    r14
0x18006dc88  push    r15
0x18006dc8a  lea     rbp, [rsp-0FA0h]
0x18006dc92  mov     eax, 10A0h
0x18006dc97  call    _alloca_probe
0x18006dc9c  sub     rsp, rax
0x18006dc9f  mov     rax, cs:__security_cookie
0x18006dca6  xor     rax, rsp
0x18006dca9  mov     [rbp+0FC0h+var_30], rax
0x18006dcb0  mov     r15, rdx
0x18006dcb3  mov     rsi, rcx
0x18006dcb6  xor     edx, edx; Val
0x18006dcb8  lea     rcx, [rsp+10C0h+var_1070]; void *
0x18006dcbd  mov     r8d, 1040h; Size
0x18006dcc3  call    memset_0
0x18006dcc8  xor     eax, eax
0x18006dcca  lea     r14, WPP_GLOBAL_Control
0x18006dcd1  mov     qword ptr [rsp+10C0h+pvarSrc+10h], rax
0x18006dcd6  xorps   xmm0, xmm0
0x18006dcd9  movups  xmmword ptr [rsp+10C0h+pvarSrc], xmm0
0x18006dcde  test    rsi, rsi
0x18006dce1  jz      loc_18006E153
0x18006dce7  test    r15, r15
0x18006dcea  jz      loc_18006E153
0x18006dcf0  mov     rax, [rsi]
0x18006dcf3  test    rax, rax
0x18006dcf6  jz      loc_18006E14C
0x18006dcfc  cmp     dword ptr [rax], 0
0x18006dcff  jle     loc_18006E14C
0x18006dd05  mov     rcx, r15; pvar
0x18006dd08  call    cs:__imp_PropVariantClear
0x18006dd0e  xorps   xmm0, xmm0
0x18006dd11  xor     eax, eax
0x18006dd13  movups  xmmword ptr [r15], xmm0
0x18006dd17  mov     [r15+10h], rax
0x18006dd1b  xor     edx, edx
0x18006dd1d  mov     rcx, [rsi]
0x18006dd20  call    IsolationAwareDPA_GetPtr
0x18006dd25  mov     rbx, rax
0x18006dd28  test    rax, rax
0x18006dd2b  jz      loc_18006E153
0x18006dd31  movzx   edi, word ptr [rax]
0x18006dd34  mov     ecx, edi
0x18006dd36  mov     r9d, edi
0x18006dd39  sub     ecx, 4
0x18006dd3c  jz      loc_18006E0C5
0x18006dd42  sub     ecx, 1
0x18006dd45  jz      loc_18006E071
0x18006dd4b  sub     ecx, 2
0x18006dd4e  jz      loc_18006DFBC
0x18006dd54  sub     ecx, 0Ch
0x18006dd57  jz      loc_18006DF70
0x18006dd5d  sub     ecx, 2
0x18006dd60  jz      loc_18006DF20
0x18006dd66  cmp     ecx, 0Ah
0x18006dd69  jz      short loc_18006DDA8
0x18006dd6b  mov     ebx, 80070057h
0x18006dd70  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dd77  cmp     rcx, r14
0x18006dd7a  jz      loc_18006E158
0x18006dd80  test    byte ptr [rcx+1Ch], 2
0x18006dd84  jz      loc_18006E158
0x18006dd8a  mov     rcx, [rcx+10h]
0x18006dd8e  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x18006dd95  mov     edx, 27h ; '''
0x18006dd9a  mov     [rsp+10C0h+var_10A0], ebx
0x18006dd9e  call    WPP_SF_dd
0x18006dda3  jmp     loc_18006E158
0x18006dda8  mov     r8, [rax+8]; unsigned __int16 *
0x18006ddac  lea     rcx, [rsp+10C0h+var_1070]; unsigned __int16 *
0x18006ddb1  mov     r12d, 820h
0x18006ddb7  mov     edx, r12d; unsigned __int64
0x18006ddba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006ddbf  mov     ebx, eax
0x18006ddc1  test    eax, eax
0x18006ddc3  jns     short loc_18006DDFC
0x18006ddc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ddcc  cmp     rcx, r14
0x18006ddcf  jz      loc_18006E158
0x18006ddd5  test    byte ptr [rcx+1Ch], 2
0x18006ddd9  jz      loc_18006E158
0x18006dddf  mov     edx, 24h ; '$'
0x18006dde4  mov     rcx, [rcx+10h]
0x18006dde8  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x18006ddef  mov     r9d, eax
0x18006ddf2  call    WPP_SF_d
0x18006ddf7  jmp     loc_18006E158
0x18006ddfc  mov     r14d, 1
0x18006de02  mov     rcx, [rsi]
0x18006de05  test    rcx, rcx
0x18006de08  jz      short loc_18006DE0E
0x18006de0a  mov     eax, [rcx]
0x18006de0c  jmp     short loc_18006DE10
0x18006de0e  xor     eax, eax
0x18006de10  cmp     r14d, eax
0x18006de13  jge     loc_18006DEA6
0x18006de19  movsxd  rdx, r14d
0x18006de1c  call    IsolationAwareDPA_GetPtr
0x18006de21  mov     rbx, rax
0x18006de24  test    rax, rax
0x18006de27  jz      short loc_18006DE9C
0x18006de29  cmp     [rax], di
0x18006de2c  jnz     short loc_18006DE9C
0x18006de2e  lea     r8, asc_1800824C0; "; "
0x18006de35  mov     rdx, r12; unsigned __int64
0x18006de38  lea     rcx, [rsp+10C0h+var_1070]; unsigned __int16 *
0x18006de3d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006de42  mov     r8, [rbx+8]; unsigned __int16 *
0x18006de46  lea     rcx, [rsp+10C0h+var_1070]; unsigned __int16 *
0x18006de4b  mov     rdx, r12; unsigned __int64
0x18006de4e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006de53  mov     ebx, eax
0x18006de55  test    eax, eax
0x18006de57  js      short loc_18006DE5E
0x18006de59  inc     r14d
0x18006de5c  jmp     short loc_18006DE02
0x18006de5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006de65  lea     rdi, WPP_GLOBAL_Control
0x18006de6c  cmp     rcx, rdi
0x18006de6f  jz      loc_18006E15F
0x18006de75  test    byte ptr [rcx+1Ch], 2
0x18006de79  jz      loc_18006E15F
0x18006de7f  mov     edx, 25h ; '%'
0x18006de84  mov     rcx, [rcx+10h]
0x18006de88  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x18006de8f  mov     r9d, eax
0x18006de92  call    WPP_SF_d
0x18006de97  jmp     loc_18006E15F
0x18006de9c  mov     ebx, 80004005h
0x18006dea1  jmp     loc_18006E158
0x18006dea6  mov     ebx, 1040h
0x18006deab  mov     ecx, ebx; cb
0x18006dead  call    cs:__imp_CoTaskMemAlloc
0x18006deb3  mov     qword ptr [rsp+10C0h+pvarSrc+8], rax
0x18006deb8  test    rax, rax
0x18006debb  jnz     short loc_18006DEC7
0x18006debd  mov     ebx, 8007000Eh
0x18006dec2  jmp     loc_18006E158
0x18006dec7  mov     r8, rbx; Size
0x18006deca  xor     edx, edx; Val
0x18006decc  mov     rcx, rax; void *
0x18006decf  call    memset_0
0x18006ded4  mov     rcx, qword ptr [rsp+10C0h+pvarSrc+8]; unsigned __int16 *
0x18006ded9  lea     r8, [rsp+10C0h+var_1070]; unsigned __int16 *
0x18006dede  mov     rdx, r12; unsigned __int64
0x18006dee1  mov     word ptr [rsp+10C0h+pvarSrc], di
0x18006dee6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006deeb  mov     ebx, eax
0x18006deed  test    eax, eax
0x18006deef  jns     loc_18006E115
0x18006def5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006defc  lea     rdi, WPP_GLOBAL_Control
0x18006df03  cmp     rcx, rdi
0x18006df06  jz      loc_18006E15F
0x18006df0c  test    byte ptr [rcx+1Ch], 2
0x18006df10  jz      loc_18006E15F
0x18006df16  mov     edx, 26h ; '&'
0x18006df1b  jmp     loc_18006DE84
0x18006df20  mov     word ptr [rsp+10C0h+pvarSrc], di
0x18006df25  mov     ebx, 1
0x18006df2a  mov     rax, [rax+8]
0x18006df2e  mov     qword ptr [rsp+10C0h+pvarSrc+8], rax
0x18006df33  mov     rcx, [rsi]
0x18006df36  test    rcx, rcx
0x18006df39  jz      short loc_18006DF3F
0x18006df3b  mov     eax, [rcx]
0x18006df3d  jmp     short loc_18006DF41
0x18006df3f  xor     eax, eax
0x18006df41  cmp     ebx, eax
0x18006df43  jge     loc_18006E11C
0x18006df49  movsxd  rdx, ebx
0x18006df4c  call    IsolationAwareDPA_GetPtr
0x18006df51  test    rax, rax
0x18006df54  jz      loc_18006DE9C
0x18006df5a  cmp     [rax], di
0x18006df5d  jnz     loc_18006DE9C
0x18006df63  mov     rax, [rax+8]
0x18006df67  add     qword ptr [rsp+10C0h+pvarSrc+8], rax
0x18006df6c  inc     ebx
0x18006df6e  jmp     short loc_18006DF33
0x18006df70  mov     word ptr [rsp+10C0h+pvarSrc], di
0x18006df75  mov     ebx, 1
0x18006df7a  mov     eax, [rax+8]
0x18006df7d  mov     dword ptr [rsp+10C0h+pvarSrc+8], eax
0x18006df81  mov     rcx, [rsi]
0x18006df84  test    rcx, rcx
0x18006df87  jz      short loc_18006DF8D
0x18006df89  mov     eax, [rcx]
0x18006df8b  jmp     short loc_18006DF8F
0x18006df8d  xor     eax, eax
0x18006df8f  cmp     ebx, eax
0x18006df91  jge     loc_18006E11C
0x18006df97  movsxd  rdx, ebx
0x18006df9a  call    IsolationAwareDPA_GetPtr
0x18006df9f  test    rax, rax
0x18006dfa2  jz      loc_18006DE9C
0x18006dfa8  cmp     [rax], di
0x18006dfab  jnz     loc_18006DE9C
0x18006dfb1  mov     eax, [rax+8]
0x18006dfb4  add     dword ptr [rsp+10C0h+pvarSrc+8], eax
0x18006dfb8  inc     ebx
0x18006dfba  jmp     short loc_18006DF81
0x18006dfbc  mov     rax, [rsi]
0x18006dfbf  test    rax, rax
0x18006dfc2  jz      short loc_18006DFC8
0x18006dfc4  mov     ecx, [rax]
0x18006dfc6  jmp     short loc_18006DFCA
0x18006dfc8  xor     ecx, ecx
0x18006dfca  movsxd  rcx, ecx
0x18006dfcd  shl     rcx, 3; cb
0x18006dfd1  call    cs:__imp_CoTaskMemAlloc
0x18006dfd7  mov     qword ptr [rsp+10C0h+pvarSrc+10h], rax
0x18006dfdc  mov     rcx, rax; void *
0x18006dfdf  test    rax, rax
0x18006dfe2  jz      loc_18006DEBD
0x18006dfe8  mov     rax, [rsi]
0x18006dfeb  test    rax, rax
0x18006dfee  jz      short loc_18006DFF4
0x18006dff0  mov     edx, [rax]
0x18006dff2  jmp     short loc_18006DFF6
0x18006dff4  xor     edx, edx
0x18006dff6  movsxd  r8, edx
0x18006dff9  xor     edx, edx; Val
0x18006dffb  shl     r8, 3; Size
0x18006dfff  call    memset_0
0x18006e004  mov     eax, 1007h
0x18006e009  mov     word ptr [rsp+10C0h+pvarSrc], ax
0x18006e00e  mov     rax, [rsi]
0x18006e011  test    rax, rax
0x18006e014  jz      short loc_18006E018
0x18006e016  mov     eax, [rax]
0x18006e018  mov     dword ptr [rsp+10C0h+pvarSrc+8], eax
0x18006e01c  mov     rcx, [rbx+8]
0x18006e020  mov     ebx, 1
0x18006e025  mov     rax, qword ptr [rsp+10C0h+pvarSrc+10h]
0x18006e02a  mov     [rax], rcx
0x18006e02d  mov     rcx, [rsi]
0x18006e030  test    rcx, rcx
0x18006e033  jz      short loc_18006E039
0x18006e035  mov     eax, [rcx]
0x18006e037  jmp     short loc_18006E03B
0x18006e039  xor     eax, eax
0x18006e03b  cmp     ebx, eax
0x18006e03d  jge     loc_18006E115
0x18006e043  movsxd  r14, ebx
0x18006e046  mov     rdx, r14
0x18006e049  call    IsolationAwareDPA_GetPtr
0x18006e04e  test    rax, rax
0x18006e051  jz      loc_18006DE9C
0x18006e057  cmp     [rax], di
0x18006e05a  jnz     loc_18006DE9C
0x18006e060  mov     rcx, [rax+8]
0x18006e064  inc     ebx
0x18006e066  mov     rax, qword ptr [rsp+10C0h+pvarSrc+10h]
0x18006e06b  mov     [rax+r14*8], rcx
0x18006e06f  jmp     short loc_18006E02D
0x18006e071  mov     word ptr [rsp+10C0h+pvarSrc], di
0x18006e076  mov     ebx, 1
0x18006e07b  movsd   xmm0, qword ptr [rax+8]
0x18006e080  mov     rcx, [rsi]
0x18006e083  movsd   qword ptr [rsp+10C0h+pvarSrc+8], xmm0
0x18006e089  test    rcx, rcx
0x18006e08c  jz      short loc_18006E092
0x18006e08e  mov     eax, [rcx]
0x18006e090  jmp     short loc_18006E094
0x18006e092  xor     eax, eax
0x18006e094  cmp     ebx, eax
0x18006e096  jge     loc_18006E11C
0x18006e09c  movsxd  rdx, ebx
0x18006e09f  call    IsolationAwareDPA_GetPtr
0x18006e0a4  test    rax, rax
0x18006e0a7  jz      loc_18006DE9C
0x18006e0ad  cmp     [rax], di
0x18006e0b0  jnz     loc_18006DE9C
0x18006e0b6  movsd   xmm0, qword ptr [rsp+10C0h+pvarSrc+8]
0x18006e0bc  inc     ebx
0x18006e0be  addsd   xmm0, qword ptr [rax+8]
0x18006e0c3  jmp     short loc_18006E080
0x18006e0c5  mov     word ptr [rsp+10C0h+pvarSrc], di
0x18006e0ca  mov     ebx, 1
0x18006e0cf  movss   xmm0, dword ptr [rax+8]
0x18006e0d4  mov     rcx, [rsi]
0x18006e0d7  movss   dword ptr [rsp+10C0h+pvarSrc+8], xmm0
0x18006e0dd  test    rcx, rcx
0x18006e0e0  jz      short loc_18006E0E6
0x18006e0e2  mov     eax, [rcx]
0x18006e0e4  jmp     short loc_18006E0E8
0x18006e0e6  xor     eax, eax
0x18006e0e8  cmp     ebx, eax
0x18006e0ea  jge     short loc_18006E11C
0x18006e0ec  movsxd  rdx, ebx
0x18006e0ef  call    IsolationAwareDPA_GetPtr
0x18006e0f4  test    rax, rax
0x18006e0f7  jz      loc_18006DE9C
0x18006e0fd  cmp     [rax], di
  ... truncated ...
```
