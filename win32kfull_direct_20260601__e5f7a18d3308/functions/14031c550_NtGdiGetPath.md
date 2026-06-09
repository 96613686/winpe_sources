# NtGdiGetPath

- ea: `0x14031c550`
- end: `0x14031c9c9`
- name: `NtGdiGetPath`
- size: `1145`
- prototype: `__int64 __fastcall(HDC)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x140039984`
- `0x14003a160`
- `0x14003d0e8`
- `0x14005b820`
- `0x140107e00`
- `0x1401fce54`
- `0x14020d334`
- `0x14031c478`
- `0x14031c550`

## import_xrefs

- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031c7ff`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031c849`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031c8bf`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031c90f`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031c7ff`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031c849`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031c8bf`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031c90f`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031c890`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031c890`
- `win32kbase!EngSetLastError` at `0x14031c65b`
- `win32kbase!EngSetLastError` at `0x14031c7ab`
- `win32kbase!EngSetLastError` at `0x14031c94e`
- `win32kbase!EngSetLastError` at `0x14031c969`
- `win32kbase!EngSetLastError` at `0x14031c990`
- `win32kbase!EngSetLastError` at `0x14031c65b`
- `win32kbase!EngSetLastError` at `0x14031c7ab`
- `win32kbase!EngSetLastError` at `0x14031c94e`
- `win32kbase!EngSetLastError` at `0x14031c969`
- `win32kbase!EngSetLastError` at `0x14031c990`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14031c5c6`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14031c5c6`
- `win32kbase!?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z` at `0x14031c6f6`
- `win32kbase!?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z` at `0x14031c70c`
- `win32kbase!?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z` at `0x14031c6f6`
- `win32kbase!?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z` at `0x14031c70c`
- `win32kbase!?bEnum@EPATHOBJ@@QEAAHPEAU_PATHDATA@@@Z` at `0x14031c76a`
- `win32kbase!?bEnum@EPATHOBJ@@QEAAHPEAU_PATHDATA@@@Z` at `0x14031c76a`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTFIX@@PEAU_POINTL@@_K@Z` at `0x14031c796`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTFIX@@PEAU_POINTL@@_K@Z` at `0x14031c796`
- `win32kbase!?cTotalPts@EPATHOBJ@@QEAAKXZ` at `0x14031c61d`
- `win32kbase!?cTotalPts@EPATHOBJ@@QEAAKXZ` at `0x14031c635`
- `win32kbase!?cTotalPts@EPATHOBJ@@QEAAKXZ` at `0x14031c61d`
- `win32kbase!?cTotalPts@EPATHOBJ@@QEAAKXZ` at `0x14031c635`
- `win32kbase!Win32FreePool` at `0x14031c93b`
- `win32kbase!Win32FreePool` at `0x14031c93b`

## pseudocode

```c
__int64 __fastcall NtGdiGetPath(HDC a1, struct _POINTL *a2, char *a3, unsigned int a4)
{
  __int64 v4; // rbx
  unsigned int v7; // edi
  __int64 v8; // r9
  char v9; // r12
  __int64 v10; // r8
  struct _POINTL *v11; // r13
  struct _POINTL *v12; // rax
  ULONG v13; // ecx
  char *v14; // r12
  char *v15; // rbx
  char flags; // dl
  ULONG v17; // ecx
  char v19; // [rsp+30h] [rbp-178h] BYREF
  char v20; // [rsp+31h] [rbp-177h] BYREF
  char v21[2]; // [rsp+32h] [rbp-176h] BYREF
  int v22; // [rsp+34h] [rbp-174h]
  char v23[8]; // [rsp+38h] [rbp-170h] BYREF
  const void **v24; // [rsp+40h] [rbp-168h] BYREF
  struct _POINTL *v25; // [rsp+48h] [rbp-160h] BYREF
  struct _PATHDATA v26; // [rsp+50h] [rbp-158h] BYREF
  __int64 v27; // [rsp+60h] [rbp-148h] BYREF
  struct _POINTL *v28; // [rsp+68h] [rbp-140h]
  char *v29; // [rsp+70h] [rbp-138h]
  void **v30; // [rsp+78h] [rbp-130h] BYREF
  char v31; // [rsp+80h] [rbp-128h]
  int v32; // [rsp+90h] [rbp-118h] BYREF
  __int64 v33; // [rsp+98h] [rbp-110h]
  DC *v34[14]; // [rsp+110h] [rbp-98h] BYREF

  v4 = a4;
  v7 = -1;
  v22 = -1;
  APIDCOBJ::APIDCOBJ((APIDCOBJ *)v34, a1);
  if ( !v34[0] || (int)v4 < 0 )
    goto LABEL_46;
  if ( !(unsigned int)DC::bInactive(v34[0]) )
  {
    v17 = 1003;
LABEL_47:
    EngSetLastError(v17);
    goto LABEL_48;
  }
  DC::QuickInitXform(v8, &v27, 1026);
  if ( !v27 )
  {
LABEL_46:
    v17 = 87;
    goto LABEL_47;
  }
  XEPATHOBJ::XEPATHOBJ((XEPATHOBJ *)&v32, *((struct HPATH__ **)v34[0] + 25));
  if ( v33 )
  {
    v9 = 0;
    if ( (unsigned int)Feature_Servicing_GdiUMAGetPath__private_IsEnabledDeviceUsageNoInline() )
    {
      v7 = EPATHOBJ::cTotalPts((EPATHOBJ *)&v32);
      if ( v7 > 0x7FFFFFFF )
      {
        v22 = -1;
        EngSetLastError(0x216u);
        v9 = 1;
      }
      v22 = v7;
    }
    else
    {
      v7 = EPATHOBJ::cTotalPts((EPATHOBJ *)&v32);
      v22 = v7;
    }
    if ( (_DWORD)v4 && !v9 )
    {
      if ( (int)v4 >= (int)v7 && (unsigned __int64)(int)v4 <= 0x1FFFFFFF )
      {
        v26 = 0;
        v19 = 0;
        v11 = 0;
        v28 = 0;
        v25 = 0;
        v24 = (const void **)&v25;
        wil::scope_exit__UMPDOBJ::BackPropagateLargeBitmapBits_::_2_::_lambda_1___(&v30, &v24, v10);
        v32 &= ~8u;
        *(_QWORD *)(v33 + 80) = *(_QWORD *)(v33 + 32);
        GreProbeForWriteToUntrustedVa(a2, 8LL * (int)v4, 4u);
        GreProbeForWriteToUntrustedVa(a3, (int)v4, 4u);
        if ( (unsigned int)Feature_Servicing_GdiUMAGetPath__private_IsEnabledDeviceUsageNoInline() )
        {
          v12 = (struct _POINTL *)PALLOCNOZ(8 * v7, 1886221383);
          v25 = v12;
          if ( !v12 )
          {
            v13 = 8;
LABEL_23:
            EngSetLastError(v13);
            v7 = -1;
            v22 = -1;
LABEL_35:
            if ( (unsigned int)Feature_Servicing_GdiUMAGetPath__private_IsEnabledDeviceUsageNoInline()
              && v25
              && (int)v7 > 0 )
            {
              GreProbeAndWriteToUntrustedVa(v11, 8LL * v7, v25, 8LL * v7, 1u);
            }
            if ( v31 && *v30 )
              Win32FreePool(*v30);
            goto LABEL_44;
          }
          v11 = a2;
          v28 = a2;
          a2 = v12;
        }
        v29 = a3;
        v14 = &a3[v4];
        while ( 1 )
        {
          LODWORD(v24) = EPATHOBJ::bEnum((EPATHOBJ *)&v32, &v26);
          if ( v26.count )
          {
            if ( !EXFORMOBJ::bXform((EXFORMOBJ *)&v27, v26.pptfx, a2, v26.count) )
            {
              v13 = 534;
              goto LABEL_23;
            }
            a2 += v26.count;
            v15 = &a3[v26.count];
            flags = v26.flags;
            if ( (v26.flags & 1) != 0 && a3 < v14 )
            {
              v23[0] = 6;
              GreProbeAndWriteToUntrustedVa(a3++, 1u, v23, 1u, 1u);
              flags = v26.flags;
            }
            v19 = (flags & 0x10) != 0 ? 4 : 2;
            if ( v15 <= v14 )
            {
              while ( a3 < v15 )
              {
                GreProbeAndWriteToUntrustedVa(a3++, 1u, &v19, 1u, 1u);
                flags = v26.flags;
              }
            }
            if ( (flags & 8) != 0 && a3 > v29 && a3 <= v14 )
            {
              v20 = 0;
              GreProbeAndReadFromUntrustedVa(&v20, 1u, a3 - 1, 1u, 1u);
              v21[0] = v20 | 1;
              GreProbeAndWriteToUntrustedVa(a3 - 1, 1u, v21, 1u, 1u);
            }
          }
          if ( !(_DWORD)v24 )
            goto LABEL_35;
        }
      }
      EngSetLastError(0x57u);
      v7 = -1;
      v22 = -1;
    }
  }
  else
  {
    EngSetLastError(0x57u);
  }
LABEL_44:
  XEPATHOBJ::~XEPATHOBJ((XEPATHOBJ *)&v32);
LABEL_48:
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)v34);
  return v7;
}

```

## disassembly

```asm
0x14031c550  mov     [rsp+arg_0], rbx
0x14031c555  mov     [rsp+arg_18], rsi
0x14031c55a  push    rdi
0x14031c55b  push    r12
0x14031c55d  push    r13
0x14031c55f  push    r14
0x14031c561  push    r15
0x14031c563  sub     rsp, 180h
0x14031c56a  mov     ebx, r9d
0x14031c56d  mov     r14, r8
0x14031c570  mov     r15, rdx
0x14031c573  or      r13d, 0FFFFFFFFh
0x14031c577  mov     edi, r13d
0x14031c57a  mov     [rsp+1A8h+var_174], r13d
0x14031c57f  mov     rdx, rcx; HDC
0x14031c582  lea     rcx, [rsp+1A8h+var_98]; this
0x14031c58a  call    ??0APIDCOBJ@@QEAA@PEAUHDC__@@@Z; APIDCOBJ::APIDCOBJ(HDC__ *)
0x14031c58f  mov     r9, [rsp+1A8h+var_98]
0x14031c597  test    r9, r9
0x14031c59a  jz      loc_14031C98B
0x14031c5a0  test    ebx, ebx
0x14031c5a2  js      loc_14031C98B
0x14031c5a8  mov     rcx, r9; this
0x14031c5ab  call    ?bInactive@DC@@QEBAHXZ; DC::bInactive(void)
0x14031c5b0  test    eax, eax
0x14031c5b2  jz      loc_14031C984
0x14031c5b8  mov     r8d, 402h
0x14031c5be  lea     rdx, [rsp+1A8h+var_148]
0x14031c5c3  mov     rcx, r9
0x14031c5c6  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x14031c5cd  nop     dword ptr [rax+rax+00h]
0x14031c5d2  cmp     [rsp+1A8h+var_148], 0
0x14031c5d8  jz      loc_14031C98B
0x14031c5de  mov     rdx, [rsp+1A8h+var_98]
0x14031c5e6  mov     rdx, [rdx+0C8h]; struct HPATH__ *
0x14031c5ed  lea     rcx, [rsp+1A8h+var_118]; this
0x14031c5f5  call    ??0XEPATHOBJ@@QEAA@PEAUHPATH__@@@Z; XEPATHOBJ::XEPATHOBJ(HPATH__ *)
0x14031c5fa  cmp     [rsp+1A8h+var_110], 0
0x14031c603  jz      loc_14031C964
0x14031c609  xor     r12b, r12b
0x14031c60c  call    Feature_Servicing_GdiUMAGetPath__private_IsEnabledDeviceUsageNoInline
0x14031c611  lea     rcx, [rsp+1A8h+var_118]
0x14031c619  test    eax, eax
0x14031c61b  jnz     short loc_14031C635
0x14031c61d  call    cs:__imp_?cTotalPts@EPATHOBJ@@QEAAKXZ; EPATHOBJ::cTotalPts(void)
0x14031c624  nop     dword ptr [rax+rax+00h]
0x14031c629  mov     edi, eax
0x14031c62b  mov     [rsp+1A8h+var_174], eax
0x14031c62f  lea     esi, [r13+2]
0x14031c633  jmp     short loc_14031C673
0x14031c635  call    cs:__imp_?cTotalPts@EPATHOBJ@@QEAAKXZ; EPATHOBJ::cTotalPts(void)
0x14031c63c  nop     dword ptr [rax+rax+00h]
0x14031c641  mov     edi, eax
0x14031c643  cmp     eax, 7FFFFFFFh
0x14031c648  ja      short loc_14031C651
0x14031c64a  mov     esi, 1
0x14031c64f  jmp     short loc_14031C66F
0x14031c651  mov     [rsp+1A8h+var_174], r13d
0x14031c656  mov     ecx, 216h; iError
0x14031c65b  call    cs:__imp_EngSetLastError
0x14031c662  nop     dword ptr [rax+rax+00h]
0x14031c667  mov     esi, 1
0x14031c66c  mov     r12b, sil
0x14031c66f  mov     [rsp+1A8h+var_174], edi
0x14031c673  test    ebx, ebx
0x14031c675  jz      loc_14031C975
0x14031c67b  test    r12b, r12b
0x14031c67e  jnz     loc_14031C975
0x14031c684  cmp     ebx, edi
0x14031c686  jl      loc_14031C949
0x14031c68c  movsxd  r12, ebx
0x14031c68f  cmp     r12, 1FFFFFFFh
0x14031c696  ja      loc_14031C949
0x14031c69c  xorps   xmm0, xmm0
0x14031c69f  movups  [rsp+1A8h+var_158], xmm0
0x14031c6a4  mov     [rsp+1A8h+var_178], 0
0x14031c6a9  xor     r13d, r13d
0x14031c6ac  mov     [rsp+1A8h+var_140], r13
0x14031c6b1  mov     [rsp+1A8h+var_160], r13
0x14031c6b6  lea     rax, [rsp+1A8h+var_160]
0x14031c6bb  mov     [rsp+1A8h+var_168], rax
0x14031c6c0  lea     rdx, [rsp+1A8h+var_168]
0x14031c6c5  lea     rcx, [rsp+1A8h+var_130]
0x14031c6ca  call    wil__scope_exit__UMPDOBJ__BackPropagateLargeBitmapBits____2____lambda_1___
0x14031c6cf  and     [rsp+1A8h+var_118], 0FFFFFFF7h
0x14031c6d7  mov     rcx, [rsp+1A8h+var_110]
0x14031c6df  mov     rax, [rcx+20h]
0x14031c6e3  mov     [rcx+50h], rax
0x14031c6e7  lea     rdx, ds:0[r12*8]
0x14031c6ef  lea     r8d, [r13+4]
0x14031c6f3  mov     rcx, r15
0x14031c6f6  call    cs:__imp_?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z; GreProbeForWriteToUntrustedVa(void *,unsigned __int64,unsigned __int64)
0x14031c6fd  nop     dword ptr [rax+rax+00h]
0x14031c702  lea     r8d, [r13+4]
0x14031c706  mov     rdx, r12
0x14031c709  mov     rcx, r14
0x14031c70c  call    cs:__imp_?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z; GreProbeForWriteToUntrustedVa(void *,unsigned __int64,unsigned __int64)
0x14031c713  nop     dword ptr [rax+rax+00h]
0x14031c718  call    Feature_Servicing_GdiUMAGetPath__private_IsEnabledDeviceUsageNoInline
0x14031c71d  test    eax, eax
0x14031c71f  jz      short loc_14031C754
0x14031c721  lea     ecx, ds:0[rdi*8]
0x14031c728  mov     edx, 706D7447h
0x14031c72d  call    PALLOCNOZ
0x14031c732  mov     [rsp+1A8h+var_160], rax
0x14031c737  test    rax, rax
0x14031c73a  jnz     short loc_14031C741
0x14031c73c  lea     ecx, [rax+8]
0x14031c73f  jmp     short loc_14031C7AB
0x14031c741  mov     r13, r15
0x14031c744  mov     [rsp+1A8h+var_140], r15
0x14031c749  mov     r15, rax
0x14031c74c  mov     [rsp+1A8h+arg_8], rax
0x14031c754  mov     [rsp+1A8h+var_138], r14
0x14031c759  lea     r12, [r14+rbx]
0x14031c75d  lea     rdx, [rsp+1A8h+var_158]
0x14031c762  lea     rcx, [rsp+1A8h+var_118]
0x14031c76a  call    cs:__imp_?bEnum@EPATHOBJ@@QEAAHPEAU_PATHDATA@@@Z; EPATHOBJ::bEnum(_PATHDATA *)
0x14031c771  nop     dword ptr [rax+rax+00h]
0x14031c776  mov     dword ptr [rsp+1A8h+var_168], eax
0x14031c77a  mov     ecx, dword ptr [rsp+1A8h+var_158+4]
0x14031c77e  test    ecx, ecx
0x14031c780  jz      loc_14031C8CB
0x14031c786  mov     r9d, ecx
0x14031c789  mov     r8, r15
0x14031c78c  mov     rdx, qword ptr [rsp+1A8h+var_158+8]
0x14031c791  lea     rcx, [rsp+1A8h+var_148]
0x14031c796  call    cs:__imp_?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTFIX@@PEAU_POINTL@@_K@Z; EXFORMOBJ::bXform(_POINTFIX const *,_POINTL *,unsigned __int64)
0x14031c79d  nop     dword ptr [rax+rax+00h]
0x14031c7a2  test    al, al
0x14031c7a4  jnz     short loc_14031C7C5
0x14031c7a6  mov     ecx, 216h; iError
0x14031c7ab  call    cs:__imp_EngSetLastError
0x14031c7b2  nop     dword ptr [rax+rax+00h]
0x14031c7b7  mov     edi, 0FFFFFFFFh
0x14031c7bc  mov     [rsp+1A8h+var_174], edi
0x14031c7c0  jmp     loc_14031C8D6
0x14031c7c5  mov     eax, dword ptr [rsp+1A8h+var_158+4]
0x14031c7c9  lea     r15, [r15+rax*8]
0x14031c7cd  mov     [rsp+1A8h+arg_8], r15
0x14031c7d5  lea     rbx, [rax+r14]
0x14031c7d9  mov     edx, dword ptr [rsp+1A8h+var_158]
0x14031c7dd  test    sil, dl
0x14031c7e0  jz      short loc_14031C81A
0x14031c7e2  cmp     r14, r12
0x14031c7e5  jnb     short loc_14031C81A
0x14031c7e7  mov     [rsp+1A8h+var_170], 6
0x14031c7ec  mov     [rsp+1A8h+var_188], rsi
0x14031c7f1  mov     r9, rsi
0x14031c7f4  lea     r8, [rsp+1A8h+var_170]
0x14031c7f9  mov     rdx, rsi
0x14031c7fc  mov     rcx, r14
0x14031c7ff  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14031c806  nop     dword ptr [rax+rax+00h]
0x14031c80b  add     r14, rsi
0x14031c80e  mov     [rsp+1A8h+arg_10], r14
0x14031c816  mov     edx, dword ptr [rsp+1A8h+var_158]
0x14031c81a  mov     eax, edx
0x14031c81c  and     al, 10h
0x14031c81e  neg     al
0x14031c820  sbb     cl, cl
0x14031c822  and     cl, 2
0x14031c825  add     cl, 2
0x14031c828  mov     [rsp+1A8h+var_178], cl
0x14031c82c  cmp     rbx, r12
0x14031c82f  ja      short loc_14031C866
0x14031c831  cmp     r14, rbx
0x14031c834  jnb     short loc_14031C866
0x14031c836  mov     [rsp+1A8h+var_188], rsi
0x14031c83b  mov     r9, rsi
0x14031c83e  lea     r8, [rsp+1A8h+var_178]
0x14031c843  mov     rdx, rsi
0x14031c846  mov     rcx, r14
0x14031c849  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14031c850  nop     dword ptr [rax+rax+00h]
0x14031c855  add     r14, rsi
0x14031c858  mov     [rsp+1A8h+arg_10], r14
0x14031c860  mov     edx, dword ptr [rsp+1A8h+var_158]
0x14031c864  jmp     short loc_14031C831
0x14031c866  test    dl, 8
0x14031c869  jz      short loc_14031C8CB
0x14031c86b  cmp     r14, [rsp+1A8h+var_138]
0x14031c870  jbe     short loc_14031C8CB
0x14031c872  cmp     r14, r12
0x14031c875  ja      short loc_14031C8CB
0x14031c877  mov     [rsp+1A8h+var_177], 0
0x14031c87c  mov     [rsp+1A8h+var_188], rsi
0x14031c881  mov     r9, rsi
0x14031c884  lea     r8, [r14-1]
0x14031c888  mov     rdx, rsi
0x14031c88b  lea     rcx, [rsp+1A8h+var_177]
0x14031c890  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14031c897  nop     dword ptr [rax+rax+00h]
0x14031c89c  mov     al, [rsp+1A8h+var_177]
0x14031c8a0  mov     [rsp+1A8h+var_176], al
0x14031c8a4  or      al, sil
0x14031c8a7  mov     [rsp+1A8h+var_176], al
0x14031c8ab  mov     [rsp+1A8h+var_188], rsi
0x14031c8b0  mov     r9, rsi
0x14031c8b3  lea     r8, [rsp+1A8h+var_176]
0x14031c8b8  mov     rdx, rsi
0x14031c8bb  lea     rcx, [r14-1]
0x14031c8bf  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14031c8c6  nop     dword ptr [rax+rax+00h]
0x14031c8cb  cmp     dword ptr [rsp+1A8h+var_168], 0
0x14031c8d0  jnz     loc_14031C75D
0x14031c8d6  jmp     short loc_14031C8E7
0x14031c8d8  or      edi, 0FFFFFFFFh
0x14031c8db  mov     [rsp+1A8h+var_174], edi
0x14031c8df  lea     esi, [rdi+2]
0x14031c8e2  mov     r13, [rsp+1A8h+var_140]
0x14031c8e7  call    Feature_Servicing_GdiUMAGetPath__private_IsEnabledDeviceUsageNoInline
0x14031c8ec  test    eax, eax
0x14031c8ee  jz      short loc_14031C924
0x14031c8f0  mov     r8, [rsp+1A8h+var_160]
0x14031c8f5  test    r8, r8
0x14031c8f8  jz      short loc_14031C924
0x14031c8fa  test    edi, edi
0x14031c8fc  jle     short loc_14031C924
0x14031c8fe  mov     edx, edi
0x14031c900  shl     rdx, 3
0x14031c904  mov     [rsp+1A8h+var_188], rsi
0x14031c909  mov     r9, rdx
0x14031c90c  mov     rcx, r13
0x14031c90f  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14031c916  nop     dword ptr [rax+rax+00h]
0x14031c91b  jmp     short loc_14031C924
0x14031c91d  or      edi, 0FFFFFFFFh
0x14031c920  mov     [rsp+1A8h+var_174], edi
0x14031c924  cmp     [rsp+1A8h+var_128], 0
0x14031c92c  jz      short loc_14031C975
0x14031c92e  mov     rax, [rsp+1A8h+var_130]
0x14031c933  mov     rcx, [rax]
0x14031c936  test    rcx, rcx
0x14031c939  jz      short loc_14031C975
0x14031c93b  call    cs:__imp_Win32FreePool
0x14031c942  nop     dword ptr [rax+rax+00h]
0x14031c947  jmp     short loc_14031C975
0x14031c949  mov     ecx, 57h ; 'W'; iError
0x14031c94e  call    cs:__imp_EngSetLastError
0x14031c955  nop     dword ptr [rax+rax+00h]
0x14031c95a  mov     edi, r13d
0x14031c95d  mov     [rsp+1A8h+var_174], r13d
0x14031c962  jmp     short loc_14031C975
0x14031c964  mov     ecx, 57h ; 'W'; iError
0x14031c969  call    cs:__imp_EngSetLastError
0x14031c970  nop     dword ptr [rax+rax+00h]
0x14031c975  lea     rcx, [rsp+1A8h+var_118]; this
0x14031c97d  call    ??1XEPATHOBJ@@QEAA@XZ; XEPATHOBJ::~XEPATHOBJ(void)
0x14031c982  jmp     short loc_14031C99C
0x14031c984  mov     ecx, 3EBh
0x14031c989  jmp     short loc_14031C990
0x14031c98b  mov     ecx, 57h ; 'W'; iError
0x14031c990  call    cs:__imp_EngSetLastError
0x14031c997  nop     dword ptr [rax+rax+00h]
0x14031c99c  lea     rcx, [rsp+1A8h+var_98]; this
0x14031c9a4  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x14031c9a9  mov     eax, edi
0x14031c9ab  lea     r11, [rsp+1A8h+var_28]
0x14031c9b3  mov     rbx, [r11+30h]
0x14031c9b7  mov     rsi, [r11+48h]
0x14031c9bb  mov     rsp, r11
0x14031c9be  pop     r15
0x14031c9c0  pop     r14
0x14031c9c2  pop     r13
0x14031c9c4  pop     r12
0x14031c9c6  pop     rdi
0x14031c9c7  retn
```
