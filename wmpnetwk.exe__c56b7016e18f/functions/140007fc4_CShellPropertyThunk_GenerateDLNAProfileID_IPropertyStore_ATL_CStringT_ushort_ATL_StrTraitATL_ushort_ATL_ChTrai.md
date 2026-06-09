# CShellPropertyThunk::GenerateDLNAProfileID(IPropertyStore *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)

- ea: `0x140007fc4`
- end: `0x140008542`
- name: `?GenerateDLNAProfileID@CShellPropertyThunk@@SAXPEAUIPropertyStore@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@KAEAV34@2@Z`
- size: `1406`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x14000660c`
- `0x140010240`

## callees

- `0x140003750`
- `0x140007020`
- `0x140007fc4`
- `0x14000b3f0`
- `0x14000c780`
- `0x14000c920`
- `0x140014f90`
- `0x140015100`
- `0x140015230`
- `0x14001b560`
- `0x140022d30`
- `0x1400396dc`
- `0x14003d444`
- `0x140046c32`
- `0x140046d00`
- `0x140054534`
- `0x1400829fc`
- `0x14009ad10`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x140008345`
- `KERNEL32!CompareStringOrdinal` at `0x140008345`
- `KERNEL32!CompareStringW` at `0x140008222`
- `KERNEL32!CompareStringW` at `0x140008253`
- `KERNEL32!CompareStringW` at `0x140008281`
- `KERNEL32!CompareStringW` at `0x1400082b1`
- `KERNEL32!CompareStringW` at `0x1400084a4`
- `KERNEL32!CompareStringW` at `0x1400084cc`
- `KERNEL32!CompareStringW` at `0x140008222`
- `KERNEL32!CompareStringW` at `0x140008253`
- `KERNEL32!CompareStringW` at `0x140008281`
- `KERNEL32!CompareStringW` at `0x1400082b1`
- `KERNEL32!CompareStringW` at `0x1400084a4`
- `KERNEL32!CompareStringW` at `0x1400084cc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400083ed`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400083ed`
- `ole32!PropVariantClear` at `0x1400082cd`
- `ole32!PropVariantClear` at `0x1400084fd`
- `ole32!PropVariantClear` at `0x1400082cd`
- `ole32!PropVariantClear` at `0x1400084fd`

## pseudocode

```c
PVOID *__fastcall CShellPropertyThunk::GenerateDLNAProfileID(__int64 a1, __int64 *a2, int a3, __int64 *a4, __int64 *a5)
{
  char v6; // r14
  __int64 v9; // rdx
  __int64 *v10; // r13
  volatile signed __int32 *v11; // rcx
  volatile signed __int32 *v12; // rdi
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // rdx
  PCNZWCH v16; // rsi
  __int64 v17; // rdi
  unsigned __int64 v18; // r15
  unsigned __int64 v19; // r12
  int v20; // r14d
  PCNZWCH v21; // rax
  size_t v22; // r8
  WCHAR *v23; // rcx
  __int64 v24; // rax
  int v25; // r8d
  _WORD *v26; // rdi
  __int64 v27; // rdi
  PVOID *result; // rax
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  _QWORD *v31; // rax
  const wchar_t *v32; // rdx
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-20h] BYREF
  PCNZWCH *v34; // [rsp+40h] [rbp-10h]
  char v35; // [rsp+90h] [rbp+40h]
  PCNZWCH *v36; // [rsp+98h] [rbp+48h] BYREF
  int v37; // [rsp+A0h] [rbp+50h]

  v37 = a3;
  v36 = (PCNZWCH *)a2;
  v6 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, a1, *a2, a3);
  }
  v34 = 0;
  v35 = 0;
  *(_OWORD *)pvar = 0;
  ATL::CSimpleStringT<unsigned short,0>::Empty(a4);
  v9 = *a2;
  v10 = a5;
  v11 = (volatile signed __int32 *)(*a2 - 24);
  v12 = (volatile signed __int32 *)(*a5 - 24);
  if ( v11 != v12 )
  {
    if ( *((int *)v12 + 4) >= 0 && *(_QWORD *)v11 == *(_QWORD *)v12 )
    {
      v13 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v11);
      if ( _InterlockedDecrement(v12 + 4) <= 0 )
        (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12, v12);
      v14 = v13 + 24;
      v6 = v37;
      *v10 = v14;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(a5, v9, *(unsigned int *)(v9 - 16));
    }
  }
  if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)a1 + 40LL))(
         a1,
         &PKEY_DRM_IsProtected,
         pvar) < 0
    || LOWORD(pvar[1]) != 0xFFFF
    || LOWORD(pvar[0]) != 11
    || (v35 = 1, (v6 & 8) == 0) )
  {
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)a1 + 40LL))(
           a1,
           &PKEY_Media_DlnaProfileID,
           pvar) < 0 )
      goto LABEL_40;
    if ( LOWORD(pvar[0]) < 2u )
      goto LABEL_39;
    if ( LOWORD(pvar[0]) != 4127 || !LODWORD(pvar[1]) )
    {
      PropVariantClear(pvar);
      goto LABEL_39;
    }
    v16 = *v34;
    if ( *v34 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v16[v17] );
    }
    else
    {
      LODWORD(v17) = 0;
    }
    v18 = ((__int64)v16 - *a4) >> 1;
    v19 = *(unsigned int *)(*a4 - 16);
    v20 = v19 + v17;
    if ( (((*(_DWORD *)(*a4 - 12) - (v19 + v17)) | (1 - *(_DWORD *)(*a4 - 8))) & 0x80000000) != 0LL )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a4, (unsigned int)v20);
    v21 = (PCNZWCH)*a4;
    if ( v18 <= v19 )
      v16 = &v21[v18];
    v22 = 2LL * (int)v17;
    if ( v22 )
    {
      v23 = (WCHAR *)&v21[v19];
      if ( v23 )
      {
        if ( v16 )
        {
          memcpy_0(v23, v16, v22);
          goto LABEL_24;
        }
        memset_0(v23, 0, v22);
      }
      *(_DWORD *)_o__errno(v23, v15, v22) = 22;
      invalid_parameter_noinfo();
    }
LABEL_24:
    if ( v20 < 0 || v20 > *(_DWORD *)(*a4 - 12) )
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*a4 - 16) = v20;
    *(_WORD *)(*a4 + 2LL * v20) = 0;
    v24 = *a4;
    v25 = *(_DWORD *)(*a4 - 16);
    if ( v25 > 0 )
    {
      v26 = (_WORD *)*a4;
      if ( v24 )
      {
        while ( *v26 )
        {
          if ( *v26 == 44 )
          {
            if ( v26 )
            {
              v27 = ((__int64)v26 - v24) >> 1;
              if ( (_DWORD)v27 != -1 )
              {
                v30 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Right(
                                  a4,
                                  &a5,
                                  (unsigned int)(v25 - v27 - 1));
                ATL::CSimpleStringT<unsigned short,0>::operator=(v10, v30);
                ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&a5);
                v31 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                                  a4,
                                  &a5,
                                  (unsigned int)v27);
                ATL::CSimpleStringT<unsigned short,0>::operator=(a4, v31);
                ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&a5);
              }
            }
            break;
          }
          ++v26;
        }
      }
    }
    if ( (v37 & 8) == 0 )
      goto LABEL_38;
    if ( CompareStringW(0x7Fu, 1u, *v34, -1, L"MP3X", -1) == 2 )
    {
      ATL::CSimpleStringT<unsigned short,0>::Empty(a4);
      v32 = L"MP3";
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, *v34, -1, L"WMVSPLL_BASE", -1) != 2
        && CompareStringW(0x7Fu, 1u, *v34, -1, L"WMVSPML_BASE", -1) != 2 )
      {
LABEL_38:
        if ( CompareStringW(0x7Fu, 1u, *v36, -1, L"video/x-ms-wmv", -1) == 2
          && (CompareStringW(0x7Fu, 1u, (PCNZWCH)*a4, -1, L"VC1_ASF_AP_L1_WMA", -1) == 2
           || CompareStringW(0x7Fu, 1u, (PCNZWCH)*a4, -1, L"VC1_ASF_AP_L2_WMA", -1) == 2) )
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(v10, L"video/x-ms-asf");
        }
LABEL_39:
        if ( !v35 )
          goto LABEL_40;
        goto LABEL_46;
      }
      ATL::CSimpleStringT<unsigned short,0>::Empty(a4);
      v32 = L"WMVMED_BASE";
    }
    ATL::CSimpleStringT<unsigned short,0>::Append(a4, v32);
    goto LABEL_38;
  }
LABEL_46:
  if ( !*(_DWORD *)(*a4 - 16) && CompareStringOrdinal((LPCWCH)*a4, 0, L"WMDRM_", -1, 0) != 2 )
  {
    v29 = (_QWORD *)ATL::operator+(&v36, L"WMDRM_", a4);
    ATL::CSimpleStringT<unsigned short,0>::operator=(a4, v29);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v36);
  }
LABEL_40:
  PropVariantClear(pvar);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    return (PVOID *)WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), *v10);
  }
  return result;
}

```

## disassembly

```asm
0x140007fc4  mov     [rsp-38h+arg_18], rbx
0x140007fc9  mov     [rsp-38h+arg_10], r8d
0x140007fce  mov     [rsp-38h+arg_8], rdx
0x140007fd3  push    rbp
0x140007fd4  push    rsi
0x140007fd5  push    rdi
0x140007fd6  push    r12
0x140007fd8  push    r13
0x140007fda  push    r14
0x140007fdc  push    r15
0x140007fde  mov     rbp, rsp
0x140007fe1  sub     rsp, 50h
0x140007fe5  mov     rbx, r9
0x140007fe8  mov     r14d, r8d
0x140007feb  mov     rdi, rdx
0x140007fee  mov     rsi, rcx
0x140007ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ff8  lea     rax, WPP_GLOBAL_Control
0x140007fff  cmp     rcx, rax
0x140008002  jnz     loc_14000837F
0x140008008  xorps   xmm0, xmm0
0x14000800b  xor     eax, eax
0x14000800d  xor     r15d, r15d
0x140008010  mov     [rbp+var_10], rax
0x140008014  mov     rcx, rbx
0x140008017  mov     [rbp+arg_0], r15b
0x14000801b  movups  xmmword ptr [rbp+pvar], xmm0
0x14000801f  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140008024  mov     rdx, [rdi]
0x140008027  or      r12, 0FFFFFFFFFFFFFFFFh
0x14000802b  mov     r13, [rbp+arg_20]
0x14000802f  lea     rcx, [rdx-18h]
0x140008033  mov     rdi, [r13+0]
0x140008037  add     rdi, 0FFFFFFFFFFFFFFE8h
0x14000803b  cmp     rcx, rdi
0x14000803e  jz      short loc_14000808B
0x140008040  cmp     [rdi+10h], r15d
0x140008044  jl      loc_1400083CC
0x14000804a  mov     rax, [rdi]
0x14000804d  cmp     [rcx], rax
0x140008050  jnz     loc_1400083CC
0x140008056  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14000805b  mov     r14, rax
0x14000805e  mov     ecx, r12d
0x140008061  lock xadd [rdi+10h], ecx
0x140008066  add     ecx, r12d
0x140008069  test    ecx, ecx
0x14000806b  jg      short loc_14000807F
0x14000806d  mov     rcx, [rdi]
0x140008070  mov     rdx, rdi
0x140008073  mov     r8, [rcx]
0x140008076  mov     rax, [r8+8]
0x14000807a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000807f  lea     rax, [r14+18h]
0x140008083  mov     r14d, [rbp+arg_10]
0x140008087  mov     [r13+0], rax
0x14000808b  mov     rax, [rsi]
0x14000808e  lea     r8, [rbp+pvar]
0x140008092  lea     rdx, PKEY_DRM_IsProtected
0x140008099  mov     rcx, rsi
0x14000809c  mov     rax, [rax+28h]
0x1400080a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080a5  mov     edi, 2
0x1400080aa  lea     ecx, [rdi+9]
0x1400080ad  test    eax, eax
0x1400080af  jns     loc_140008308
0x1400080b5  mov     rax, [rsi]
0x1400080b8  lea     r8, [rbp+pvar]
0x1400080bc  lea     rdx, PKEY_Media_DlnaProfileID
0x1400080c3  mov     rcx, rsi
0x1400080c6  mov     rax, [rax+28h]
0x1400080ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080cf  test    eax, eax
0x1400080d1  js      loc_1400082C9
0x1400080d7  mov     rsi, rdi
0x1400080da  cmp     word ptr [rbp+pvar], si
0x1400080de  jb      loc_1400082BF
0x1400080e4  mov     eax, 101Fh
0x1400080e9  cmp     ax, word ptr [rbp+pvar]
0x1400080ed  jnz     loc_1400084F9
0x1400080f3  cmp     dword ptr [rbp+pvar+8], r15d
0x1400080f7  jz      loc_1400084F9
0x1400080fd  mov     rax, [rbp+var_10]
0x140008101  mov     rsi, [rax]
0x140008104  test    rsi, rsi
0x140008107  jz      loc_1400083C4
0x14000810d  mov     rdi, r12
0x140008110  inc     rdi
0x140008113  cmp     [rsi+rdi*2], r15w
0x140008118  jnz     short loc_140008110
0x14000811a  mov     rax, [rbx]
0x14000811d  mov     r15, rsi
0x140008120  sub     r15, rax
0x140008123  mov     ecx, 1
0x140008128  sar     r15, 1
0x14000812b  mov     r12d, [rax-10h]
0x14000812f  sub     ecx, [rax-8]
0x140008132  mov     eax, [rax-0Ch]
0x140008135  lea     r14d, [r12+rdi]
0x140008139  sub     eax, r14d
0x14000813c  or      ecx, eax
0x14000813e  jge     short loc_14000814B
0x140008140  mov     edx, r14d
0x140008143  mov     rcx, rbx
0x140008146  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14000814b  mov     rax, [rbx]
0x14000814e  cmp     r15, r12
0x140008151  jbe     loc_1400083DD
0x140008157  movsxd  r8, edi
0x14000815a  add     r8, r8; Size
0x14000815d  jz      loc_140008403
0x140008163  lea     rcx, [rax+r12*2]; void *
0x140008167  xor     r15d, r15d
0x14000816a  test    rcx, rcx
0x14000816d  jz      loc_1400083ED
0x140008173  test    rsi, rsi
0x140008176  jz      loc_1400083E6
0x14000817c  mov     rdx, rsi; Src
0x14000817f  call    memcpy_0
0x140008184  test    r14d, r14d
0x140008187  js      loc_1400084EE
0x14000818d  mov     rax, [rbx]
0x140008190  cmp     r14d, [rax-0Ch]
0x140008194  jg      loc_1400084EE
0x14000819a  mov     [rax-10h], r14d
0x14000819e  mov     rcx, [rbx]
0x1400081a1  movsxd  rdx, r14d
0x1400081a4  mov     [rcx+rdx*2], r15w
0x1400081a9  mov     rax, [rbx]
0x1400081ac  mov     r8d, [rax-10h]
0x1400081b0  test    r8d, r8d
0x1400081b3  jle     loc_1400083B1
0x1400081b9  mov     rdi, rax
0x1400081bc  test    rax, rax
0x1400081bf  jz      loc_1400083B1
0x1400081c5  cmp     [rdi], r15w
0x1400081c9  jz      loc_1400083B1
0x1400081cf  cmp     word ptr [rdi], 2Ch ; ','
0x1400081d3  jz      short loc_1400081DB
0x1400081d5  add     rdi, 2
0x1400081d9  jmp     short loc_1400081C5
0x1400081db  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400081df  test    rdi, rdi
0x1400081e2  jz      short loc_1400081F3
0x1400081e4  sub     rdi, rax
0x1400081e7  sar     rdi, 1
0x1400081ea  cmp     edi, r12d
0x1400081ed  jnz     loc_14000840B
0x1400081f3  test    byte ptr [rbp+arg_10], 8
0x1400081f7  mov     edi, 7Fh
0x1400081fc  jz      loc_1400083BA
0x140008202  mov     r8, [rbp+var_10]
0x140008206  lea     rax, aMp3x; "MP3X"
0x14000820d  mov     [rsp+50h+cchCount2], r12d; cchCount2
0x140008212  lea     edx, [rdi-7Eh]; dwCmpFlags
0x140008215  mov     r9d, r12d; cchCount1
0x140008218  mov     [rsp+50h+lpString2], rax; lpString2
0x14000821d  mov     ecx, edi; Locale
0x14000821f  mov     r8, [r8]; lpString1
0x140008222  call    cs:__imp_CompareStringW
0x140008228  lea     esi, [rdi-7Dh]
0x14000822b  cmp     eax, esi
0x14000822d  jz      loc_140008459
0x140008233  mov     r8, [rbp+var_10]
0x140008237  lea     rax, aWmvspllBase; "WMVSPLL_BASE"
0x14000823e  mov     [rsp+50h+cchCount2], r12d; cchCount2
0x140008243  lea     edx, [rdi-7Eh]; dwCmpFlags
0x140008246  mov     r9d, r12d; cchCount1
0x140008249  mov     [rsp+50h+lpString2], rax; lpString2
0x14000824e  mov     ecx, edi; Locale
0x140008250  mov     r8, [r8]; lpString1
0x140008253  call    cs:__imp_CompareStringW
0x140008259  cmp     eax, esi
0x14000825b  jz      loc_14000846A
0x140008261  mov     r8, [rbp+var_10]
0x140008265  lea     rax, aWmvspmlBase; "WMVSPML_BASE"
0x14000826c  mov     [rsp+50h+cchCount2], r12d; cchCount2
0x140008271  lea     edx, [rdi-7Eh]; dwCmpFlags
0x140008274  mov     r9d, r12d; cchCount1
0x140008277  mov     [rsp+50h+lpString2], rax; lpString2
0x14000827c  mov     ecx, edi; Locale
0x14000827e  mov     r8, [r8]; lpString1
0x140008281  call    cs:__imp_CompareStringW
0x140008287  cmp     eax, esi
0x140008289  jz      loc_14000846A
0x14000828f  mov     r8, [rbp+arg_8]
0x140008293  lea     rax, aVideoXMsWmv; "video/x-ms-wmv"
0x14000829a  mov     [rsp+50h+cchCount2], r12d; cchCount2
0x14000829f  mov     r9d, r12d; cchCount1
0x1400082a2  mov     edx, 1; dwCmpFlags
0x1400082a7  mov     [rsp+50h+lpString2], rax; lpString2
0x1400082ac  mov     ecx, edi; Locale
0x1400082ae  mov     r8, [r8]; lpString1
0x1400082b1  call    cs:__imp_CompareStringW
0x1400082b7  cmp     eax, esi
0x1400082b9  jz      loc_140008486
0x1400082bf  cmp     [rbp+arg_0], r15b
0x1400082c3  jnz     loc_140008508
0x1400082c9  lea     rcx, [rbp+pvar]; pvar
0x1400082cd  call    cs:__imp_PropVariantClear
0x1400082d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400082da  lea     rax, WPP_GLOBAL_Control
0x1400082e1  cmp     rcx, rax
0x1400082e4  jz      short loc_1400082F0
0x1400082e6  test    byte ptr [rcx+1Ch], 1
0x1400082ea  jnz     loc_140008512
0x1400082f0  mov     rbx, [rsp+50h+arg_18]
0x1400082f8  add     rsp, 50h
0x1400082fc  pop     r15
0x1400082fe  pop     r14
0x140008300  pop     r13
0x140008302  pop     r12
0x140008304  pop     rdi
0x140008305  pop     rsi
0x140008306  pop     rbp
0x140008307  retn
0x140008308  cmp     r12w, word ptr [rbp+pvar+8]
0x14000830d  jnz     loc_1400080B5
0x140008313  cmp     cx, word ptr [rbp+pvar]
0x140008317  jnz     loc_1400080B5
0x14000831d  mov     [rbp+arg_0], 1
0x140008321  test    r14b, 8
0x140008325  jz      loc_1400080B5
0x14000832b  mov     rcx, [rbx]; lpString1
0x14000832e  cmp     [rcx-10h], r15d
0x140008332  jnz     short loc_1400082C9
0x140008334  mov     r9d, r12d; cchCount2
0x140008337  mov     dword ptr [rsp+50h+lpString2], r15d; bIgnoreCase
0x14000833c  lea     r8, aWmdrm; "WMDRM_"
0x140008343  xor     edx, edx; cchCount1
0x140008345  call    cs:__imp_CompareStringOrdinal
0x14000834b  cmp     eax, edi
0x14000834d  jz      loc_1400082C9
0x140008353  mov     r8, rbx
0x140008356  lea     rdx, aWmdrm; "WMDRM_"
0x14000835d  lea     rcx, [rbp+arg_8]
0x140008361  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@PEBGAEBV10@@Z; ATL::operator+(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x140008366  mov     rdx, rax
0x140008369  mov     rcx, rbx
0x14000836c  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140008371  lea     rcx, [rbp+arg_8]
0x140008375  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14000837a  jmp     loc_1400082C9
0x14000837f  test    byte ptr [rcx+1Ch], 1
0x140008383  jz      loc_140008008
0x140008389  cmp     byte ptr [rcx+19h], 5
0x14000838d  jb      loc_140008008
0x140008393  mov     rax, [rdx]
0x140008396  mov     r9, rsi
0x140008399  mov     rcx, [rcx+10h]
0x14000839d  mov     [rsp+50h+cchCount2], r8d
0x1400083a2  mov     [rsp+50h+lpString2], rax
0x1400083a7  call    WPP_SF_qSD
0x1400083ac  jmp     loc_140008008
0x1400083b1  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400083b5  jmp     loc_1400081F3
0x1400083ba  mov     esi, 2
0x1400083bf  jmp     loc_14000828F
0x1400083c4  mov     edi, r15d
0x1400083c7  jmp     loc_14000811A
0x1400083cc  mov     r8d, [rdx-10h]
0x1400083d0  mov     rcx, r13
0x1400083d3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400083d8  jmp     loc_14000808B
0x1400083dd  lea     rsi, [rax+r15*2]
0x1400083e1  jmp     loc_140008157
0x1400083e6  xor     edx, edx; Val
0x1400083e8  call    memset_0
0x1400083ed  call    cs:__imp__o__errno
0x1400083f3  mov     dword ptr [rax], 16h
0x1400083f9  call    _invalid_parameter_noinfo
0x1400083fe  jmp     loc_140008184
0x140008403  xor     r15d, r15d
0x140008406  jmp     loc_140008184
0x14000840b  sub     r8d, edi
0x14000840e  lea     rdx, [rbp+arg_20]
0x140008412  dec     r8d
0x140008415  mov     rcx, rbx
0x140008418  call    ?Right@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Right(int)
0x14000841d  mov     rdx, rax
0x140008420  mov     rcx, r13
0x140008423  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140008428  lea     rcx, [rbp+arg_20]
0x14000842c  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140008431  mov     r8d, edi
0x140008434  lea     rdx, [rbp+arg_20]
0x140008438  mov     rcx, rbx
0x14000843b  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Left(int)
0x140008440  mov     rdx, rax
0x140008443  mov     rcx, rbx
0x140008446  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14000844b  lea     rcx, [rbp+arg_20]
0x14000844f  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140008454  jmp     loc_1400081F3
0x140008459  mov     rcx, rbx
0x14000845c  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140008461  lea     rdx, aMp3; "MP3"
0x140008468  jmp     short loc_140008479
0x14000846a  mov     rcx, rbx
0x14000846d  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
  ... truncated ...
```
