# CMDEProfileCollection::FindHighestProfileInGroup(ATL::CRBMultiMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<MDEProfile const *>> const *,MDEProfile const *,_WMCResElementParams const *,int,int,MDEProfile const * *)

- ea: `0x140003940`
- end: `0x140003f3e`
- name: `?FindHighestProfileInGroup@CMDEProfileCollection@@QEAAJPEBV?$CRBMultiMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBUMDEProfile@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEBUMDEProfile@@@2@@ATL@@PEBUMDEProfile@@PEBU_WMCResElementParams@@HHPEAPEBU4@@Z`
- size: `1534`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004fe0`

## callees

- `0x140003940`
- `0x140003f50`
- `0x14005480c`
- `0x14009aab8`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x140003bd8`
- `KERNEL32!CompareStringOrdinal` at `0x140003bd8`
- `KERNEL32!CompareStringW` at `0x140003a0a`
- `KERNEL32!CompareStringW` at `0x140003a8b`
- `KERNEL32!CompareStringW` at `0x140003b66`
- `KERNEL32!CompareStringW` at `0x140003a0a`
- `KERNEL32!CompareStringW` at `0x140003a8b`
- `KERNEL32!CompareStringW` at `0x140003b66`

## pseudocode

```c
__int64 __fastcall CMDEProfileCollection::FindHighestProfileInGroup(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 *a7)
{
  PVOID *v9; // r10
  int v12; // ebx
  _QWORD *v13; // rdi
  const WCHAR *v14; // rsi
  __int64 v15; // rbx
  int v16; // eax
  int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rbx
  _QWORD *v20; // rcx
  __int64 v21; // r10
  unsigned __int64 v22; // r15
  _QWORD *v23; // rcx
  _QWORD *v24; // rbx
  _QWORD *v25; // rsi
  __int64 v26; // rbx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rcx
  unsigned int *v30; // rax
  unsigned __int64 v31; // rcx
  bool v32; // cf
  int v33; // eax
  int v34; // ecx
  unsigned int v35; // eax
  _QWORD *v36; // rax
  unsigned int v38; // eax
  bool v39; // cf
  bool v40; // zf
  unsigned int v41; // r8d
  unsigned int v42; // eax
  bool v43; // cf
  __int64 v44; // rax
  unsigned int v45; // [rsp+40h] [rbp-58h]
  unsigned int v46; // [rsp+44h] [rbp-54h]
  unsigned int v47; // [rsp+48h] [rbp-50h]
  __int64 v48; // [rsp+50h] [rbp-48h]
  unsigned __int64 v49; // [rsp+58h] [rbp-40h]
  unsigned int v50; // [rsp+A0h] [rbp+8h]
  BOOL v52; // [rsp+C0h] [rbp+28h]
  unsigned int v53; // [rsp+D0h] [rbp+38h]

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v12 = a6;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_qqllq(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, a3, a2, a3, a5, a6, a7);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v12 = a6;
  }
  v52 = !a5 && !v12;
  if ( !a7 )
    goto LABEL_15;
  *a7 = 0;
  v13 = 0;
  v14 = *(const WCHAR **)(a3 + 48);
  v15 = *a2;
  while ( v15 != a2[5] )
  {
    if ( v13 )
      goto LABEL_16;
    v16 = CompareStringW(0x7Fu, 1u, v14, -1, *(PCNZWCH *)v15, -1) - 1;
    if ( v16 )
    {
      if ( v16 == 2 )
        v15 = *(_QWORD *)(v15 + 32);
      else
        v13 = (_QWORD *)v15;
    }
    else
    {
      v15 = *(_QWORD *)(v15 + 24);
    }
  }
  if ( !v13 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_15:
    v17 = -2147467259;
    goto LABEL_58;
  }
  while ( 1 )
  {
LABEL_16:
    v18 = a2[5];
    v19 = v13[3];
    if ( v19 == v18 )
    {
      v19 = v13[5];
      v20 = v13;
      while ( v19 != v18 )
      {
        if ( v20 != *(_QWORD **)(v19 + 24) )
          goto LABEL_20;
        v20 = (_QWORD *)v19;
        v19 = *(_QWORD *)(v19 + 40);
      }
LABEL_19:
      v19 = 0;
      goto LABEL_20;
    }
    if ( !v19 )
      goto LABEL_19;
    while ( *(_QWORD *)(v19 + 32) != v18 )
      v19 = *(_QWORD *)(v19 + 32);
LABEL_20:
    if ( !v19 || CompareStringW(0x7Fu, 1u, v14, -1, *(PCNZWCH *)v19, -1) != 2 )
      break;
    v13 = (_QWORD *)v19;
  }
  v21 = 0;
  v48 = 0;
  v46 = 0;
  v22 = 0;
  v49 = -1;
  v45 = 0;
  v47 = 0;
  v53 = -1;
  v50 = -1;
  if ( a4 )
  {
    if ( a5 || v52 )
    {
      v49 = *(unsigned int *)(a4 + 72) * (unsigned __int64)*(unsigned int *)(a4 + 76);
    }
    else
    {
      v50 = *(_DWORD *)(a4 + 80);
      v53 = *(_DWORD *)(a4 + 88);
    }
  }
  while ( v13 )
  {
    v23 = (_QWORD *)a2[5];
    v24 = (_QWORD *)v13[4];
    if ( v24 == v23 )
    {
      v24 = (_QWORD *)v13[5];
      v36 = v13;
      while ( v24 != v23 )
      {
        if ( v36 != (_QWORD *)v24[4] )
          goto LABEL_30;
        v36 = v24;
        v24 = (_QWORD *)v24[5];
      }
    }
    else if ( v24 )
    {
      while ( (_QWORD *)v24[3] != v23 )
        v24 = (_QWORD *)v24[3];
      goto LABEL_30;
    }
    v24 = 0;
LABEL_30:
    v25 = v13;
    if ( v24 && CompareStringW(0x7Fu, 1u, (PCNZWCH)*v24, -1, *(PCNZWCH *)(a3 + 48), -1) == 2 )
      v13 = v24;
    else
      v13 = 0;
    v26 = v25[1];
    if ( !v26 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      v17 = -2147418113;
      goto LABEL_58;
    }
    v21 = v48;
    if ( *(_DWORD *)(v26 + 56) == *(_DWORD *)(a3 + 56)
      && *(_DWORD *)(v26 + 76) == *(_DWORD *)(a3 + 76)
      && *(_DWORD *)(v26 + 184) == *(_DWORD *)(a3 + 184) )
    {
      if ( !a4
        || (v27 = CompareStringOrdinal(*(LPCWCH *)(v26 + 32), 9, L"audio/L16", 9, 1),
            v28 = IsMDEProfileSuitableForResElement(
                    (const struct MDEProfile *)v26,
                    (const struct _WMCResElementParams *)a4,
                    a5,
                    a6,
                    v27 == 2,
                    0),
            v21 = v48,
            v28) )
      {
        if ( a5 )
        {
          v29 = *(unsigned int *)(v26 + 104);
          v30 = (unsigned int *)(v26 + 108);
LABEL_42:
          v31 = *v30 * v29;
          v32 = v31 < v22;
          if ( v31 > v22 )
          {
            if ( v22 >= v49 )
            {
              v32 = v31 < v22;
              goto LABEL_43;
            }
          }
          else
          {
LABEL_43:
            if ( !v32 || v31 < v49 )
            {
LABEL_45:
              v21 = v48;
              if ( v52 && v31 == v22 )
              {
                v33 = *(_DWORD *)(v26 + 96);
                v34 = *(_DWORD *)(v26 + 128);
                if ( v33 == -1 )
                {
                  v35 = *(_DWORD *)(v26 + 128);
                }
                else
                {
                  v35 = 8 * v33;
                  if ( v34 != -1 )
                    v35 += v34;
                }
                if ( v35 > v46 )
                {
                  v46 = v35;
                  v21 = v26;
                  v48 = v26;
                }
              }
              continue;
            }
          }
          v22 = v31;
          v46 = 0;
          v48 = v26;
          goto LABEL_45;
        }
        if ( v52 )
        {
          v29 = *(unsigned int *)(v26 + 120);
          v30 = (unsigned int *)(v26 + 124);
          goto LABEL_42;
        }
        v21 = v48;
        if ( !a6 )
          continue;
        v38 = *(_DWORD *)(v26 + 88);
        v39 = v38 < v47;
        v40 = v38 == v47;
        if ( v38 > v47 )
        {
          if ( v47 < v50 )
            goto LABEL_86;
          v39 = v38 < v47;
          v40 = v38 == v47;
        }
        if ( v39 )
        {
          if ( v38 < v50 )
            continue;
LABEL_86:
          v41 = 0;
          v47 = *(_DWORD *)(v26 + 88);
          v45 = 0;
          v48 = v26;
          goto LABEL_79;
        }
        if ( !v40 )
          continue;
        v41 = v45;
LABEL_79:
        v42 = *(_DWORD *)(v26 + 100);
        v43 = v42 < v41;
        if ( v42 > v41 )
        {
          if ( v41 < v53 )
            goto LABEL_84;
          v43 = v42 < v41;
        }
        v21 = v48;
        if ( v43 && v42 >= v53 )
        {
LABEL_84:
          v45 = *(_DWORD *)(v26 + 100);
          v21 = v26;
          v48 = v26;
          continue;
        }
      }
    }
  }
  *a7 = v21;
  v40 = v21 == 0;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  v17 = -2147467259;
  if ( !v40 )
    v17 = 0;
LABEL_58:
  if ( v9 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v9 + 28) & 2) != 0
    && *((unsigned __int8 *)v9 + 25) >= ((v17 >> 31) & 0xFFFFFFFD) + 5 )
  {
    if ( a7 )
      v44 = *a7;
    else
      v44 = 0;
    WPP_SF_dq(v9[2], 64, &WPP_12d29b41b149367017654092f21a41cc_Traceguids, (unsigned int)v17, v44);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140003940  mov     rax, rsp
0x140003943  mov     [rax+20h], r9
0x140003947  mov     [rax+8], rcx
0x14000394b  push    rbx
0x14000394c  push    r13
0x14000394e  sub     rsp, 88h
0x140003955  mov     [rax+10h], rbp
0x140003959  mov     rbp, r8
0x14000395c  mov     [rax-28h], r12
0x140003960  mov     [rax-30h], r14
0x140003964  mov     r14, rdx
0x140003967  mov     r10, cs:WPP_GLOBAL_Control
0x14000396e  lea     r11, WPP_GLOBAL_Control
0x140003975  mov     r13, [rsp+98h+arg_30]
0x14000397d  mov     r12d, [rsp+98h+arg_20]
0x140003985  cmp     r10, r11
0x140003988  jz      short loc_140003995
0x14000398a  test    byte ptr [r10+1Ch], 2
0x14000398f  jnz     loc_140003E5E
0x140003995  mov     ebx, [rsp+98h+arg_28]
0x14000399c  test    r12d, r12d
0x14000399f  jnz     short loc_1400039A9
0x1400039a1  test    ebx, ebx
0x1400039a3  jz      loc_140003D9B
0x1400039a9  mov     [rsp+98h+arg_20], 0
0x1400039b4  mov     [rsp+98h+var_18], rsi
0x1400039bc  mov     [rsp+98h+var_20], rdi
0x1400039c1  mov     [rsp+98h+var_38], r15
0x1400039c6  test    r13, r13
0x1400039c9  jz      short loc_140003A32
0x1400039cb  mov     qword ptr [r13+0], 0
0x1400039d3  xor     edi, edi
0x1400039d5  mov     rsi, [rbp+30h]
0x1400039d9  mov     rbx, [r14]
0x1400039dc  cmp     rbx, [r14+28h]
0x1400039e0  jz      short loc_140003A1F
0x1400039e2  test    rdi, rdi
0x1400039e5  jnz     short loc_140003A40
0x1400039e7  mov     rax, [rbx]
0x1400039ea  mov     r9d, 0FFFFFFFFh; cchCount1
0x1400039f0  mov     [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x1400039f8  mov     r8, rsi; lpString1
0x1400039fb  mov     edx, 1; dwCmpFlags
0x140003a00  mov     [rsp+98h+lpString2], rax; lpString2
0x140003a05  mov     ecx, 7Fh; Locale
0x140003a0a  call    cs:__imp_CompareStringW
0x140003a10  sub     eax, 1
0x140003a13  jnz     loc_140003EA7
0x140003a19  mov     rbx, [rbx+18h]
0x140003a1d  jmp     short loc_1400039DC
0x140003a1f  test    rdi, rdi
0x140003a22  jnz     short loc_140003A40
0x140003a24  mov     r10, cs:WPP_GLOBAL_Control
0x140003a2b  lea     r11, WPP_GLOBAL_Control
0x140003a32  mov     ebx, 80004005h
0x140003a37  jmp     loc_140003CDF
0x140003a40  mov     rax, [r14+28h]
0x140003a44  mov     rbx, [rdi+18h]
0x140003a48  cmp     rbx, rax
0x140003a4b  jnz     loc_140003D36
0x140003a51  mov     rbx, [rdi+28h]
0x140003a55  mov     rcx, rdi
0x140003a58  cmp     rbx, rax
0x140003a5b  jnz     loc_140003D20
0x140003a61  xor     ebx, ebx
0x140003a63  test    rbx, rbx
0x140003a66  jz      short loc_140003A9A
0x140003a68  mov     rax, [rbx]
0x140003a6b  mov     r9d, 0FFFFFFFFh; cchCount1
0x140003a71  mov     [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x140003a79  mov     r8, rsi; lpString1
0x140003a7c  mov     edx, 1; dwCmpFlags
0x140003a81  mov     [rsp+98h+lpString2], rax; lpString2
0x140003a86  mov     ecx, 7Fh; Locale
0x140003a8b  call    cs:__imp_CompareStringW
0x140003a91  cmp     eax, 2
0x140003a94  jz      loc_140003D71
0x140003a9a  test    rdi, rdi
0x140003a9d  jz      short loc_140003A24
0x140003a9f  mov     r9, [rsp+98h+arg_18]
0x140003aa7  xor     r10d, r10d
0x140003aaa  xor     r8d, r8d
0x140003aad  mov     [rsp+98h+var_48], r10
0x140003ab2  xor     edx, edx
0x140003ab4  mov     [rsp+98h+var_54], r10d
0x140003ab9  xor     r15d, r15d
0x140003abc  mov     [rsp+98h+var_40], 0FFFFFFFFFFFFFFFFh
0x140003ac5  mov     [rsp+98h+var_58], r8d
0x140003aca  mov     [rsp+98h+var_50], edx
0x140003ace  mov     dword ptr [rsp+98h+arg_30], 0FFFFFFFFh
0x140003ad9  mov     [rsp+98h+arg_0], 0FFFFFFFFh
0x140003ae4  test    r9, r9
0x140003ae7  jz      short loc_140003B15
0x140003ae9  test    r12d, r12d
0x140003aec  jnz     loc_140003D85
0x140003af2  cmp     [rsp+98h+arg_20], edx
0x140003af9  jnz     loc_140003D85
0x140003aff  mov     eax, [r9+50h]
0x140003b03  mov     [rsp+98h+arg_0], eax
0x140003b0a  mov     eax, [r9+58h]
0x140003b0e  mov     dword ptr [rsp+98h+arg_30], eax
0x140003b15  test    rdi, rdi
0x140003b18  jz      loc_140003ED3
0x140003b1e  mov     rcx, [r14+28h]
0x140003b22  mov     rbx, [rdi+20h]
0x140003b26  cmp     rbx, rcx
0x140003b29  jz      loc_140003CA9
0x140003b2f  test    rbx, rbx
0x140003b32  jnz     loc_140003DB0
0x140003b38  xor     ebx, ebx
0x140003b3a  mov     rsi, rdi
0x140003b3d  test    rbx, rbx
0x140003b40  jz      short loc_140003B75
0x140003b42  mov     rax, [rbp+30h]
0x140003b46  mov     r9d, 0FFFFFFFFh; cchCount1
0x140003b4c  mov     r8, [rbx]; lpString1
0x140003b4f  mov     edx, 1; dwCmpFlags
0x140003b54  mov     [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x140003b5c  mov     ecx, 7Fh; Locale
0x140003b61  mov     [rsp+98h+lpString2], rax; lpString2
0x140003b66  call    cs:__imp_CompareStringW
0x140003b6c  cmp     eax, 2
0x140003b6f  jz      loc_140003CA1
0x140003b75  xor     edi, edi
0x140003b77  mov     rbx, [rsi+8]
0x140003b7b  test    rbx, rbx
0x140003b7e  jz      loc_140003CCC
0x140003b84  mov     eax, [rbp+38h]
0x140003b87  mov     r10, [rsp+98h+var_48]
0x140003b8c  cmp     [rbx+38h], eax
0x140003b8f  jnz     short loc_140003B15
0x140003b91  mov     eax, [rbp+4Ch]
0x140003b94  cmp     [rbx+4Ch], eax
0x140003b97  jnz     loc_140003B15
0x140003b9d  mov     eax, [rbp+0B8h]
0x140003ba3  cmp     [rbx+0B8h], eax
0x140003ba9  jnz     loc_140003B15
0x140003baf  mov     rsi, [rsp+98h+arg_18]
0x140003bb7  test    rsi, rsi
0x140003bba  jz      short loc_140003C15
0x140003bbc  mov     rcx, [rbx+20h]; lpString1
0x140003bc0  lea     r8, aAudioL16_1; "audio/L16"
0x140003bc7  mov     r9d, 9; cchCount2
0x140003bcd  mov     dword ptr [rsp+98h+lpString2], 1; bIgnoreCase
0x140003bd5  mov     edx, r9d; cchCount1
0x140003bd8  call    cs:__imp_CompareStringOrdinal
0x140003bde  mov     r9d, [rsp+98h+arg_28]; int
0x140003be6  xor     ecx, ecx
0x140003be8  cmp     eax, 2
0x140003beb  mov     [rsp+98h+cchCount2], 0; int
0x140003bf3  mov     r8d, r12d; int
0x140003bf6  mov     rdx, rsi; struct _WMCResElementParams *
0x140003bf9  setz    cl
0x140003bfc  mov     dword ptr [rsp+98h+lpString2], ecx; int
0x140003c00  mov     rcx, rbx; struct MDEProfile *
0x140003c03  call    ?IsMDEProfileSuitableForResElement@@YAHPEBUMDEProfile@@PEBU_WMCResElementParams@@HHHH@Z; IsMDEProfileSuitableForResElement(MDEProfile const *,_WMCResElementParams const *,int,int,int,int)
0x140003c08  mov     r10, [rsp+98h+var_48]
0x140003c0d  test    eax, eax
0x140003c0f  jz      loc_140003B15
0x140003c15  mov     edx, [rsp+98h+arg_20]
0x140003c1c  test    r12d, r12d
0x140003c1f  jnz     loc_140003D79
0x140003c25  test    edx, edx
0x140003c27  jz      loc_140003DC2
0x140003c2d  mov     ecx, [rbx+78h]
0x140003c30  lea     rax, [rbx+7Ch]
0x140003c34  mov     eax, [rax]
0x140003c36  imul    rcx, rax
0x140003c3a  cmp     rcx, r15
0x140003c3d  ja      loc_140003D51
0x140003c43  jnb     short loc_140003C50
0x140003c45  cmp     rcx, [rsp+98h+var_40]
0x140003c4a  jnb     loc_140003D5C
0x140003c50  mov     r10, [rsp+98h+var_48]
0x140003c55  test    edx, edx
0x140003c57  jz      loc_140003B15
0x140003c5d  cmp     rcx, r15
0x140003c60  jnz     loc_140003B15
0x140003c66  mov     eax, [rbx+60h]
0x140003c69  mov     ecx, [rbx+80h]
0x140003c6f  cmp     eax, 0FFFFFFFFh
0x140003c72  jz      loc_140003ECC
0x140003c78  lea     eax, ds:0[rax*8]
0x140003c7f  cmp     ecx, 0FFFFFFFFh
0x140003c82  jz      short loc_140003C86
0x140003c84  add     eax, ecx
0x140003c86  cmp     eax, [rsp+98h+var_54]
0x140003c8a  jbe     loc_140003B15
0x140003c90  mov     [rsp+98h+var_54], eax
0x140003c94  mov     r10, rbx
0x140003c97  mov     [rsp+98h+var_48], rbx
0x140003c9c  jmp     loc_140003B15
0x140003ca1  mov     rdi, rbx
0x140003ca4  jmp     loc_140003B77
0x140003ca9  mov     rbx, [rdi+28h]
0x140003cad  mov     rax, rdi
0x140003cb0  cmp     rbx, rcx
0x140003cb3  jz      loc_140003B38
0x140003cb9  cmp     rax, [rbx+20h]
0x140003cbd  jnz     loc_140003B3A
0x140003cc3  mov     rax, rbx
0x140003cc6  mov     rbx, [rbx+28h]
0x140003cca  jmp     short loc_140003CB0
0x140003ccc  mov     r10, cs:WPP_GLOBAL_Control
0x140003cd3  lea     r11, WPP_GLOBAL_Control
0x140003cda  mov     ebx, 8000FFFFh
0x140003cdf  mov     r15, [rsp+98h+var_38]
0x140003ce4  mov     r14, [rsp+98h+var_30]
0x140003ce9  mov     r12, [rsp+98h+var_28]
0x140003cee  mov     rdi, [rsp+98h+var_20]
0x140003cf3  mov     rsi, [rsp+98h+var_18]
0x140003cfb  mov     rbp, [rsp+98h+arg_8]
0x140003d03  cmp     r10, r11
0x140003d06  jz      short loc_140003D13
0x140003d08  test    byte ptr [r10+1Ch], 2
0x140003d0d  jnz     loc_140003EF7
0x140003d13  mov     eax, ebx
0x140003d15  add     rsp, 88h
0x140003d1c  pop     r13
0x140003d1e  pop     rbx
0x140003d1f  retn
0x140003d20  cmp     rcx, [rbx+18h]
0x140003d24  jnz     loc_140003A63
0x140003d2a  mov     rcx, rbx
0x140003d2d  mov     rbx, [rbx+28h]
0x140003d31  jmp     loc_140003A58
0x140003d36  test    rbx, rbx
0x140003d39  jz      loc_140003A61
0x140003d3f  mov     rcx, [rbx+20h]
0x140003d43  cmp     rcx, rax
0x140003d46  jz      loc_140003A63
0x140003d4c  mov     rbx, rcx
0x140003d4f  jmp     short loc_140003D3F
0x140003d51  cmp     r15, [rsp+98h+var_40]
0x140003d56  jnb     loc_140003EC4
0x140003d5c  mov     r15, rcx
0x140003d5f  mov     [rsp+98h+var_54], 0
0x140003d67  mov     [rsp+98h+var_48], rbx
0x140003d6c  jmp     loc_140003C50
0x140003d71  mov     rdi, rbx
0x140003d74  jmp     loc_140003A40
0x140003d79  mov     ecx, [rbx+68h]
0x140003d7c  lea     rax, [rbx+6Ch]
0x140003d80  jmp     loc_140003C34
0x140003d85  mov     ecx, [r9+4Ch]
0x140003d89  mov     eax, [r9+48h]
0x140003d8d  imul    rcx, rax
0x140003d91  mov     [rsp+98h+var_40], rcx
0x140003d96  jmp     loc_140003B15
0x140003d9b  mov     [rsp+98h+arg_20], 1
0x140003da6  jmp     loc_1400039B4
0x140003db0  mov     rax, [rbx+18h]
0x140003db4  cmp     rax, rcx
0x140003db7  jz      loc_140003B3A
0x140003dbd  mov     rbx, rax
0x140003dc0  jmp     short loc_140003DB0
0x140003dc2  cmp     [rsp+98h+arg_28], 0
0x140003dca  mov     r10, [rsp+98h+var_48]
0x140003dcf  jz      loc_140003B15
0x140003dd5  mov     eax, [rbx+58h]
0x140003dd8  mov     edx, [rsp+98h+var_50]
0x140003ddc  cmp     eax, edx
0x140003dde  ja      short loc_140003E2A
0x140003de0  jb      short loc_140003E4A
0x140003de2  jnz     loc_140003B15
0x140003de8  mov     r8d, [rsp+98h+var_58]
0x140003ded  mov     eax, [rbx+64h]
0x140003df0  cmp     eax, r8d
0x140003df3  ja      short loc_140003E0F
0x140003df5  mov     r10, [rsp+98h+var_48]
0x140003dfa  jnb     loc_140003B15
0x140003e00  cmp     eax, dword ptr [rsp+98h+arg_30]
0x140003e07  jb      loc_140003B15
0x140003e0d  jmp     short loc_140003E19
0x140003e0f  cmp     r8d, dword ptr [rsp+98h+arg_30]
0x140003e17  jnb     short loc_140003E59
0x140003e19  mov     [rsp+98h+var_58], eax
0x140003e1d  mov     r10, rbx
0x140003e20  mov     [rsp+98h+var_48], rbx
0x140003e25  jmp     loc_140003B15
0x140003e2a  cmp     edx, [rsp+98h+arg_0]
0x140003e31  jnb     loc_140003EBD
0x140003e37  xor     r8d, r8d
0x140003e3a  mov     [rsp+98h+var_50], eax
0x140003e3e  mov     [rsp+98h+var_58], r8d
0x140003e43  mov     [rsp+98h+var_48], rbx
0x140003e48  jmp     short loc_140003DED
0x140003e4a  cmp     eax, [rsp+98h+arg_0]
0x140003e51  jb      loc_140003B15
0x140003e57  jmp     short loc_140003E37
0x140003e59  cmp     eax, r8d
0x140003e5c  jmp     short loc_140003DF5
0x140003e5e  cmp     byte ptr [r10+19h], 5
0x140003e63  mov     ebx, [rsp+98h+arg_28]
0x140003e6a  jb      loc_14000399C
0x140003e70  mov     rcx, [r10+10h]
0x140003e74  mov     edx, 3Fh ; '?'
0x140003e79  mov     [rsp+98h+var_60], r13
0x140003e7e  mov     r9, r14
0x140003e81  mov     [rsp+98h+var_68], ebx
  ... truncated ...
```
