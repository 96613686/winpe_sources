# CMDEProfileCollection::FindLowestProfileInGroup(ATL::CRBMultiMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<MDEProfile const *>> const *,MDEProfile const *,_WMCResElementParams const *,int,int,MDEProfile const * *)

- ea: `0x140004ae0`
- end: `0x140004fd4`
- name: `?FindLowestProfileInGroup@CMDEProfileCollection@@QEAAJPEBV?$CRBMultiMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBUMDEProfile@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEBUMDEProfile@@@2@@ATL@@PEBUMDEProfile@@PEBU_WMCResElementParams@@HHPEAPEBU4@@Z`
- size: `1268`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004fe0`

## callees

- `0x140004ae0`
- `0x14005480c`
- `0x14009aab8`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140004ba1`
- `KERNEL32!CompareStringW` at `0x140004c06`
- `KERNEL32!CompareStringW` at `0x140004d11`
- `KERNEL32!CompareStringW` at `0x140004ba1`
- `KERNEL32!CompareStringW` at `0x140004c06`
- `KERNEL32!CompareStringW` at `0x140004d11`

## pseudocode

```c
__int64 __fastcall CMDEProfileCollection::FindLowestProfileInGroup(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 *a7)
{
  PVOID *v10; // r10
  __int64 *v11; // r12
  int v12; // edi
  int v13; // ebx
  _QWORD *v14; // rdi
  const WCHAR *v15; // rsi
  __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rbx
  _QWORD *v20; // rcx
  int v21; // ebx
  __int64 v23; // r8
  unsigned int v24; // r13d
  unsigned int v25; // r12d
  unsigned int v26; // ebp
  _QWORD *v27; // rcx
  _QWORD *v28; // rbx
  _QWORD *v29; // rsi
  _DWORD *v30; // rcx
  unsigned int v31; // eax
  _QWORD *v32; // rax
  unsigned int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rdx
  unsigned int *v36; // rax
  unsigned __int64 v37; // r11
  unsigned __int64 v38; // rdx
  unsigned int v39; // r10d
  int v40; // eax
  int v41; // edx
  unsigned int v42; // eax
  unsigned int v43; // [rsp+40h] [rbp-48h]
  __int64 v44; // [rsp+48h] [rbp-40h]
  unsigned __int64 v45; // [rsp+50h] [rbp-38h]
  BOOL v46; // [rsp+90h] [rbp+8h]

  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v11 = a7;
    v13 = a6;
    v12 = a5;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_qqllq(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, a3, a2, a3, a5, a6, a7);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v11 = a7;
    v12 = a5;
    v13 = a6;
  }
  v46 = !v12 && !v13;
  if ( !v11 )
    goto LABEL_21;
  *v11 = 0;
  v14 = 0;
  v15 = *(const WCHAR **)(a3 + 48);
  v16 = *a2;
  while ( v16 != a2[5] )
  {
    if ( v14 )
      goto LABEL_13;
    v17 = CompareStringW(0x7Fu, 1u, v15, -1, *(PCNZWCH *)v16, -1) - 1;
    if ( v17 )
    {
      if ( v17 == 2 )
        v16 = *(_QWORD *)(v16 + 32);
      else
        v14 = (_QWORD *)v16;
    }
    else
    {
      v16 = *(_QWORD *)(v16 + 24);
    }
  }
  if ( !v14 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_21:
    v21 = -2147467259;
    goto LABEL_22;
  }
  while ( 1 )
  {
LABEL_13:
    v18 = a2[5];
    v19 = v14[3];
    if ( v19 == v18 )
    {
      v19 = v14[5];
      v20 = v14;
      while ( v19 != v18 )
      {
        if ( v20 != *(_QWORD **)(v19 + 24) )
          goto LABEL_17;
        v20 = (_QWORD *)v19;
        v19 = *(_QWORD *)(v19 + 40);
      }
LABEL_16:
      v19 = 0;
      goto LABEL_17;
    }
    if ( !v19 )
      goto LABEL_16;
    while ( *(_QWORD *)(v19 + 32) != v18 )
      v19 = *(_QWORD *)(v19 + 32);
LABEL_17:
    if ( !v19 || CompareStringW(0x7Fu, 1u, v15, -1, *(PCNZWCH *)v19, -1) != 2 )
      break;
    v14 = (_QWORD *)v19;
  }
  v23 = 0;
  v45 = -1;
  v44 = 0;
  v24 = 0;
  v43 = 0;
  v25 = -1;
  if ( a4 && a6 )
    v26 = *(_DWORD *)(a4 + 88);
  else
    v26 = -1;
  while ( v14 )
  {
    v27 = (_QWORD *)a2[5];
    v28 = (_QWORD *)v14[4];
    if ( v28 == v27 )
    {
      v28 = (_QWORD *)v14[5];
      v32 = v14;
      while ( v28 != v27 )
      {
        if ( v32 != (_QWORD *)v28[4] )
          goto LABEL_33;
        v32 = v28;
        v28 = (_QWORD *)v28[5];
      }
    }
    else if ( v28 )
    {
      while ( (_QWORD *)v28[3] != v27 )
        v28 = (_QWORD *)v28[3];
      goto LABEL_33;
    }
    v28 = 0;
LABEL_33:
    v29 = v14;
    if ( v28 && CompareStringW(0x7Fu, 1u, (PCNZWCH)*v28, -1, *(PCNZWCH *)(a3 + 48), -1) == 2 )
      v14 = v28;
    else
      v14 = 0;
    v30 = (_DWORD *)v29[1];
    if ( !v30 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      v21 = -2147418113;
      v11 = a7;
      goto LABEL_22;
    }
    v23 = v44;
    if ( v30[14] == *(_DWORD *)(a3 + 56) && v30[19] == *(_DWORD *)(a3 + 76) && v30[46] == *(_DWORD *)(a3 + 184) )
    {
      if ( a5 )
      {
        v35 = (unsigned int)v30[26];
        v36 = v30 + 27;
        goto LABEL_76;
      }
      if ( v46 )
      {
        v35 = (unsigned int)v30[30];
        v36 = v30 + 31;
LABEL_76:
        v37 = v45;
        v38 = *v36 * v35;
        if ( v38 >= v45 )
        {
          v39 = v43;
        }
        else
        {
          v39 = 0;
          v45 = v38;
          v43 = 0;
          v37 = v38;
          v23 = v29[1];
          v44 = v23;
        }
        if ( v46 && v38 == v37 )
        {
          v40 = v30[24];
          v41 = v30[32];
          if ( v40 == -1 )
          {
            v42 = v30[32];
          }
          else
          {
            v42 = 8 * v40;
            if ( v41 != -1 )
              v42 += v41;
          }
          if ( v42 > v39 )
          {
            v43 = v42;
            v23 = v29[1];
            v44 = v23;
          }
        }
      }
      else
      {
        if ( !a6 )
          continue;
        v31 = v30[22];
        if ( v31 < v25 )
        {
          v25 = v30[22];
          v44 = v29[1];
          v24 = 0;
        }
        else if ( v31 != v25 )
        {
          continue;
        }
        v33 = v30[25];
        v23 = v44;
        if ( v33 > v24 && v33 <= v26 )
        {
          v24 = v30[25];
          v44 = v29[1];
          v23 = v44;
        }
      }
    }
  }
  v11 = a7;
  v21 = -2147467259;
  if ( v23 )
    v21 = 0;
  *a7 = v23;
  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_22:
  if ( v10 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v10 + 28) & 2) != 0
    && *((unsigned __int8 *)v10 + 25) >= ((v21 >> 31) & 0xFFFFFFFD) + 5 )
  {
    if ( v11 )
      v34 = *v11;
    else
      v34 = 0;
    WPP_SF_dq(v10[2], 62, &WPP_12d29b41b149367017654092f21a41cc_Traceguids, (unsigned int)v21, v34);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x140004ae0  mov     rax, rsp
0x140004ae3  mov     [rax+8], rcx
0x140004ae7  push    rbx
0x140004ae8  push    r12
0x140004aea  sub     rsp, 78h
0x140004aee  mov     [rax+10h], rbp
0x140004af2  mov     rbp, r9
0x140004af5  mov     [rax+20h], rdi
0x140004af9  mov     [rax-20h], r14
0x140004afd  mov     r14, r8
0x140004b00  mov     [rax-28h], r15
0x140004b04  mov     r15, rdx
0x140004b07  mov     r10, cs:WPP_GLOBAL_Control
0x140004b0e  lea     rax, WPP_GLOBAL_Control
0x140004b15  cmp     r10, rax
0x140004b18  jz      short loc_140004B25
0x140004b1a  test    byte ptr [r10+1Ch], 2
0x140004b1f  jnz     loc_140004E92
0x140004b25  mov     r12, [rsp+88h+arg_30]
0x140004b2d  mov     edi, [rsp+88h+arg_20]
0x140004b34  mov     ebx, [rsp+88h+arg_28]
0x140004b3b  test    edi, edi
0x140004b3d  jz      loc_140004C67
0x140004b43  xor     eax, eax
0x140004b45  mov     [rsp+88h+arg_0], eax
0x140004b4c  mov     [rsp+88h+arg_10], rsi
0x140004b54  mov     [rsp+88h+var_18], r13
0x140004b59  test    r12, r12
0x140004b5c  jz      loc_140004C21
0x140004b62  mov     qword ptr [r12], 0
0x140004b6a  xor     edi, edi
0x140004b6c  mov     rsi, [r14+30h]
0x140004b70  mov     rbx, [r15]
0x140004b73  cmp     rbx, [r15+28h]
0x140004b77  jz      short loc_140004BB6
0x140004b79  test    rdi, rdi
0x140004b7c  jnz     short loc_140004BBB
0x140004b7e  mov     rax, [rbx]
0x140004b81  mov     r9d, 0FFFFFFFFh; cchCount1
0x140004b87  mov     [rsp+88h+cchCount2], 0FFFFFFFFh; cchCount2
0x140004b8f  mov     r8, rsi; lpString1
0x140004b92  mov     edx, 1; dwCmpFlags
0x140004b97  mov     [rsp+88h+lpString2], rax; lpString2
0x140004b9c  mov     ecx, 7Fh; Locale
0x140004ba1  call    cs:__imp_CompareStringW
0x140004ba7  sub     eax, 1
0x140004baa  jnz     loc_140004EE2
0x140004bb0  mov     rbx, [rbx+18h]
0x140004bb4  jmp     short loc_140004B73
0x140004bb6  test    rdi, rdi
0x140004bb9  jz      short loc_140004C1A
0x140004bbb  mov     rax, [r15+28h]
0x140004bbf  mov     rbx, [rdi+18h]
0x140004bc3  cmp     rbx, rax
0x140004bc6  jnz     loc_140004E0B
0x140004bcc  mov     rbx, [rdi+28h]
0x140004bd0  mov     rcx, rdi
0x140004bd3  cmp     rbx, rax
0x140004bd6  jnz     loc_140004E26
0x140004bdc  xor     ebx, ebx
0x140004bde  test    rbx, rbx
0x140004be1  jz      short loc_140004C15
0x140004be3  mov     rax, [rbx]
0x140004be6  mov     r9d, 0FFFFFFFFh; cchCount1
0x140004bec  mov     [rsp+88h+cchCount2], 0FFFFFFFFh; cchCount2
0x140004bf4  mov     r8, rsi; lpString1
0x140004bf7  mov     edx, 1; dwCmpFlags
0x140004bfc  mov     [rsp+88h+lpString2], rax; lpString2
0x140004c01  mov     ecx, 7Fh; Locale
0x140004c06  call    cs:__imp_CompareStringW
0x140004c0c  cmp     eax, 2
0x140004c0f  jz      loc_140004E3C
0x140004c15  test    rdi, rdi
0x140004c18  jnz     short loc_140004C7F
0x140004c1a  mov     r10, cs:WPP_GLOBAL_Control
0x140004c21  mov     ebx, 80004005h
0x140004c26  mov     r15, [rsp+88h+var_28]
0x140004c2b  lea     rax, WPP_GLOBAL_Control
0x140004c32  mov     r14, [rsp+88h+var_20]
0x140004c37  mov     r13, [rsp+88h+var_18]
0x140004c3c  mov     rdi, [rsp+88h+arg_18]
0x140004c44  mov     rsi, [rsp+88h+arg_10]
0x140004c4c  mov     rbp, [rsp+88h+arg_8]
0x140004c54  cmp     r10, rax
0x140004c57  jnz     loc_140004E44
0x140004c5d  mov     eax, ebx
0x140004c5f  add     rsp, 78h
0x140004c63  pop     r12
0x140004c65  pop     rbx
0x140004c66  retn
0x140004c67  test    ebx, ebx
0x140004c69  jnz     loc_140004B43
0x140004c6f  mov     [rsp+88h+arg_0], 1
0x140004c7a  jmp     loc_140004B4C
0x140004c7f  xor     r8d, r8d
0x140004c82  mov     [rsp+88h+var_38], 0FFFFFFFFFFFFFFFFh
0x140004c8b  xor     r10d, r10d
0x140004c8e  mov     [rsp+88h+var_40], r8
0x140004c93  xor     r13d, r13d
0x140004c96  mov     [rsp+88h+var_48], r10d
0x140004c9b  mov     r12d, 0FFFFFFFFh
0x140004ca1  test    rbp, rbp
0x140004ca4  jz      loc_140004EF8
0x140004caa  cmp     [rsp+88h+arg_28], r8d
0x140004cb2  jz      loc_140004EF8
0x140004cb8  mov     ebp, [rbp+58h]
0x140004cbb  nop     dword ptr [rax+rax+00h]
0x140004cc0  test    rdi, rdi
0x140004cc3  jz      loc_140004F8B
0x140004cc9  mov     rcx, [r15+28h]
0x140004ccd  mov     rbx, [rdi+20h]
0x140004cd1  cmp     rbx, rcx
0x140004cd4  jz      loc_140004D9B
0x140004cda  test    rbx, rbx
0x140004cdd  jnz     loc_140004E80
0x140004ce3  xor     ebx, ebx
0x140004ce5  mov     rsi, rdi
0x140004ce8  test    rbx, rbx
0x140004ceb  jz      short loc_140004D1C
0x140004ced  mov     rax, [r14+30h]
0x140004cf1  mov     r9d, 0FFFFFFFFh; cchCount1
0x140004cf7  mov     r8, [rbx]; lpString1
0x140004cfa  mov     edx, 1; dwCmpFlags
0x140004cff  mov     [rsp+88h+cchCount2], 0FFFFFFFFh; cchCount2
0x140004d07  mov     ecx, 7Fh; Locale
0x140004d0c  mov     [rsp+88h+lpString2], rax; lpString2
0x140004d11  call    cs:__imp_CompareStringW
0x140004d17  cmp     eax, 2
0x140004d1a  jz      short loc_140004D96
0x140004d1c  xor     edi, edi
0x140004d1e  mov     rcx, [rsi+8]
0x140004d22  test    rcx, rcx
0x140004d25  jz      loc_140004DF2
0x140004d2b  mov     eax, [r14+38h]
0x140004d2f  mov     r8, [rsp+88h+var_40]
0x140004d34  cmp     [rcx+38h], eax
0x140004d37  jnz     short loc_140004CC0
0x140004d39  mov     eax, [r14+4Ch]
0x140004d3d  cmp     [rcx+4Ch], eax
0x140004d40  jnz     loc_140004CC0
0x140004d46  mov     eax, [r14+0B8h]
0x140004d4d  cmp     [rcx+0B8h], eax
0x140004d53  jnz     loc_140004CC0
0x140004d59  cmp     [rsp+88h+arg_20], 0
0x140004d61  mov     r9d, [rsp+88h+arg_0]
0x140004d69  jnz     loc_140004F09
0x140004d6f  test    r9d, r9d
0x140004d72  jnz     loc_140004F00
0x140004d78  cmp     [rsp+88h+arg_28], r9d
0x140004d80  jz      loc_140004CC0
0x140004d86  mov     eax, [rcx+58h]
0x140004d89  cmp     eax, r12d
0x140004d8c  jb      short loc_140004DBE
0x140004d8e  jnz     loc_140004CC0
0x140004d94  jmp     short loc_140004DC9
0x140004d96  mov     rdi, rbx
0x140004d99  jmp     short loc_140004D1E
0x140004d9b  mov     rbx, [rdi+28h]
0x140004d9f  mov     rax, rdi
0x140004da2  cmp     rbx, rcx
0x140004da5  jz      loc_140004CE3
0x140004dab  cmp     rax, [rbx+20h]
0x140004daf  jnz     loc_140004CE5
0x140004db5  mov     rax, rbx
0x140004db8  mov     rbx, [rbx+28h]
0x140004dbc  jmp     short loc_140004DA2
0x140004dbe  mov     r12d, eax
0x140004dc1  mov     [rsp+88h+var_40], rcx
0x140004dc6  xor     r13d, r13d
0x140004dc9  mov     eax, [rcx+64h]
0x140004dcc  mov     r8, [rsp+88h+var_40]
0x140004dd1  cmp     eax, r13d
0x140004dd4  jbe     loc_140004CC0
0x140004dda  cmp     eax, ebp
0x140004ddc  ja      loc_140004CC0
0x140004de2  mov     r13d, eax
0x140004de5  mov     [rsp+88h+var_40], rcx
0x140004dea  mov     r8, rcx
0x140004ded  jmp     loc_140004CC0
0x140004df2  mov     r10, cs:WPP_GLOBAL_Control
0x140004df9  mov     ebx, 8000FFFFh
0x140004dfe  mov     r12, [rsp+88h+arg_30]
0x140004e06  jmp     loc_140004C26
0x140004e0b  test    rbx, rbx
0x140004e0e  jz      loc_140004BDC
0x140004e14  mov     rcx, [rbx+20h]
0x140004e18  cmp     rcx, rax
0x140004e1b  jz      loc_140004BDE
0x140004e21  mov     rbx, rcx
0x140004e24  jmp     short loc_140004E14
0x140004e26  cmp     rcx, [rbx+18h]
0x140004e2a  jnz     loc_140004BDE
0x140004e30  mov     rcx, rbx
0x140004e33  mov     rbx, [rbx+28h]
0x140004e37  jmp     loc_140004BD3
0x140004e3c  mov     rdi, rbx
0x140004e3f  jmp     loc_140004BBB
0x140004e44  test    byte ptr [r10+1Ch], 2
0x140004e49  jz      loc_140004C5D
0x140004e4f  movzx   eax, byte ptr [r10+19h]
0x140004e54  mov     ecx, ebx
0x140004e56  sar     ecx, 1Fh
0x140004e59  and     ecx, 0FFFFFFFDh
0x140004e5c  add     ecx, 5
0x140004e5f  cmp     eax, ecx
0x140004e61  jb      loc_140004C5D
0x140004e67  test    r12, r12
0x140004e6a  jz      loc_140004FB0
0x140004e70  mov     rax, [r12]
0x140004e74  jmp     loc_140004FB2
0x140004e80  mov     rax, [rbx+18h]
0x140004e84  cmp     rax, rcx
0x140004e87  jz      loc_140004CE5
0x140004e8d  mov     rbx, rax
0x140004e90  jmp     short loc_140004E80
0x140004e92  cmp     byte ptr [r10+19h], 5
0x140004e97  mov     r12, [rsp+88h+arg_30]
0x140004e9f  mov     ebx, [rsp+88h+arg_28]
0x140004ea6  mov     edi, [rsp+88h+arg_20]
0x140004ead  jb      loc_140004B3B
0x140004eb3  mov     rcx, [r10+10h]
0x140004eb7  mov     edx, 3Dh ; '='
0x140004ebc  mov     [rsp+88h+var_50], r12
0x140004ec1  mov     r9, r15
0x140004ec4  mov     [rsp+88h+var_58], ebx
0x140004ec8  mov     [rsp+88h+cchCount2], edi
0x140004ecc  mov     [rsp+88h+lpString2], r14
0x140004ed1  call    WPP_SF_qqllq
0x140004ed6  mov     r10, cs:WPP_GLOBAL_Control
0x140004edd  jmp     loc_140004B3B
0x140004ee2  cmp     eax, 2
0x140004ee5  jz      short loc_140004EEF
0x140004ee7  mov     rdi, rbx
0x140004eea  jmp     loc_140004B73
0x140004eef  mov     rbx, [rbx+20h]
0x140004ef3  jmp     loc_140004B73
0x140004ef8  mov     ebp, r12d
0x140004efb  jmp     loc_140004CC0
0x140004f00  mov     edx, [rcx+78h]
0x140004f03  lea     rax, [rcx+7Ch]
0x140004f07  jmp     short loc_140004F10
0x140004f09  mov     edx, [rcx+68h]
0x140004f0c  lea     rax, [rcx+6Ch]
0x140004f10  mov     eax, [rax]
0x140004f12  mov     r11, [rsp+88h+var_38]
0x140004f17  imul    rdx, rax
0x140004f1b  cmp     rdx, r11
0x140004f1e  jnb     short loc_140004F3A
0x140004f20  xor     r10d, r10d
0x140004f23  mov     [rsp+88h+var_38], rdx
0x140004f28  mov     [rsp+88h+var_48], r10d
0x140004f2d  mov     r11, rdx
0x140004f30  mov     r8, rcx
0x140004f33  mov     [rsp+88h+var_40], rcx
0x140004f38  jmp     short loc_140004F3F
0x140004f3a  mov     r10d, [rsp+88h+var_48]
0x140004f3f  test    r9d, r9d
0x140004f42  jz      loc_140004CC0
0x140004f48  cmp     rdx, r11
0x140004f4b  jnz     loc_140004CC0
0x140004f51  mov     eax, [rcx+60h]
0x140004f54  mov     edx, [rcx+80h]
0x140004f5a  cmp     eax, 0FFFFFFFFh
0x140004f5d  jz      short loc_140004F6F
0x140004f5f  lea     eax, ds:0[rax*8]
0x140004f66  cmp     edx, 0FFFFFFFFh
0x140004f69  jz      short loc_140004F71
0x140004f6b  add     eax, edx
0x140004f6d  jmp     short loc_140004F71
0x140004f6f  mov     eax, edx
0x140004f71  cmp     eax, r10d
0x140004f74  jbe     loc_140004CC0
0x140004f7a  mov     [rsp+88h+var_48], eax
0x140004f7e  mov     r8, rcx
0x140004f81  mov     [rsp+88h+var_40], rcx
0x140004f86  jmp     loc_140004CC0
0x140004f8b  mov     r12, [rsp+88h+arg_30]
0x140004f93  xor     eax, eax
0x140004f95  test    r8, r8
0x140004f98  mov     ebx, 80004005h
0x140004f9d  cmovnz  ebx, eax
0x140004fa0  mov     [r12], r8
0x140004fa4  mov     r10, cs:WPP_GLOBAL_Control
0x140004fab  jmp     loc_140004C26
0x140004fb0  xor     eax, eax
0x140004fb2  mov     rcx, [r10+10h]
0x140004fb6  lea     r8, WPP_12d29b41b149367017654092f21a41cc_Traceguids
0x140004fbd  mov     edx, 3Eh ; '>'
0x140004fc2  mov     [rsp+88h+lpString2], rax
0x140004fc7  mov     r9d, ebx
0x140004fca  call    WPP_SF_dq
0x140004fcf  jmp     loc_140004C5D
```
