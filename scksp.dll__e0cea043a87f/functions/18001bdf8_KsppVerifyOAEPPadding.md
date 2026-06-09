# KsppVerifyOAEPPadding

- ea: `0x18001bdf8`
- end: `0x18001c0aa`
- name: `KsppVerifyOAEPPadding`
- size: `690`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001b440`
- `0x18001dbc8`

## callees

- `0x18000a408`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x18001bdf8`
- `0x18002b140`
- `0x18002bb90`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x18001bece`
- `bcrypt!BCryptGetProperty` at `0x18001bf3f`
- `bcrypt!BCryptGetProperty` at `0x18001bece`
- `bcrypt!BCryptGetProperty` at `0x18001bf3f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001be47`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001be47`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001c089`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001c089`

## pseudocode

```c
__int64 __fastcall KsppVerifyOAEPPadding(__int64 a1, unsigned int a2, __int64 a3, _QWORD *a4, __int64 a5)
{
  size_t v6; // rsi
  const WCHAR *v9; // rdx
  __int64 v10; // rcx
  unsigned int Property; // ebx
  _QWORD *v12; // rax
  int v13; // edx
  __int64 v14; // rcx
  __int64 v15; // rcx
  void *v16; // rdi
  __int64 v17; // rcx
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-10h] BYREF
  UCHAR v20[4]; // [rsp+54h] [rbp-Ch] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-8h] BYREF
  ULONG pcbResult; // [rsp+A0h] [rbp+40h] BYREF

  v6 = a2;
  phAlgorithm = 0;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v20 = 0;
  v9 = *(const WCHAR **)a3;
  pcbResult = 4;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, v9, 0, 0);
  if ( Property )
  {
    WppTraceIndent(v10, 2u);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 223;
LABEL_6:
      WPP_SF_sd(
        v12[2],
        v13,
        (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
        (_DWORD)WPP_pszIndent,
        Property);
    }
  }
  else
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property )
    {
      WppTraceIndent(v14, 2u);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 224;
        goto LABEL_6;
      }
    }
    else
    {
      pcbResult = 4;
      Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v20, 4u, &pcbResult, 0);
      if ( Property )
      {
        WppTraceIndent(v15, 2u);
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = 225;
          goto LABEL_6;
        }
      }
      else
      {
        v16 = MIDL_user_allocate(v6);
        if ( v16 )
        {
          Property = CheckOAEPPadding(
                       phAlgorithm,
                       *(unsigned int *)v20,
                       *(unsigned int *)pbOutput,
                       *(_QWORD *)(a3 + 8),
                       *(_DWORD *)(a3 + 16),
                       a1,
                       v6,
                       v16,
                       v6,
                       a5);
          if ( Property )
          {
            WppTraceIndent(v17, 2u);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                227,
                (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
                (_DWORD)WPP_pszIndent,
                Property);
            }
            CspFreeH(v16);
          }
          else
          {
            *a4 = v16;
          }
        }
        else
        {
          Property = -2146893810;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              226,
              &WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
              WPP_pszIndent);
          }
        }
      }
    }
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return Property;
}

```

## disassembly

```asm
0x18001bdf8  mov     [rsp-28h+arg_0], rbx
0x18001bdfd  mov     [rsp-28h+arg_8], rsi
0x18001be02  push    rbp
0x18001be03  push    rdi
0x18001be04  push    r12
0x18001be06  push    r14
0x18001be08  push    r15
0x18001be0a  mov     rbp, rsp
0x18001be0d  sub     rsp, 60h
0x18001be11  mov     r14, r8
0x18001be14  mov     esi, edx
0x18001be16  mov     r15, r9
0x18001be19  mov     [rbp+phAlgorithm], 0
0x18001be21  mov     r12, rcx
0x18001be24  mov     dword ptr [rbp+pbOutput], 0
0x18001be2b  mov     edi, 4
0x18001be30  mov     dword ptr [rbp+var_C], 0
0x18001be37  mov     rdx, [r14]; pszAlgId
0x18001be3a  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18001be3e  xor     r9d, r9d; dwFlags
0x18001be41  mov     [rbp+arg_10], edi
0x18001be44  xor     r8d, r8d; pszImplementation
0x18001be47  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001be4d  mov     ebx, eax
0x18001be4f  test    eax, eax
0x18001be51  jz      short loc_18001BEAB
0x18001be53  lea     edx, [rdi-2]
0x18001be56  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001be5b  mov     rax, cs:WPP_GLOBAL_Control
0x18001be62  lea     rcx, WPP_GLOBAL_Control
0x18001be69  cmp     rax, rcx
0x18001be6c  jz      loc_18001C07E
0x18001be72  test    byte ptr [rax+1Ch], 1
0x18001be76  jz      loc_18001C07E
0x18001be7c  cmp     byte ptr [rax+19h], 2
0x18001be80  jb      loc_18001C07E
0x18001be86  mov     edx, 0DFh
0x18001be8b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001be92  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x18001be99  mov     rcx, [rax+10h]
0x18001be9d  mov     dword ptr [rsp+60h+pcbResult], ebx
0x18001bea1  call    WPP_SF_sd
0x18001bea6  jmp     loc_18001C07E
0x18001beab  mov     rcx, [rbp+phAlgorithm]; hObject
0x18001beaf  lea     rax, [rbp+arg_10]
0x18001beb3  mov     [rsp+60h+dwFlags], 0; dwFlags
0x18001bebb  lea     r8, [rbp+pbOutput]; pbOutput
0x18001bebf  mov     r9d, edi; cbOutput
0x18001bec2  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18001bec7  lea     rdx, aObjectlength; "ObjectLength"
0x18001bece  call    cs:__imp_BCryptGetProperty
0x18001bed4  mov     ebx, eax
0x18001bed6  test    eax, eax
0x18001bed8  jz      short loc_18001BF19
0x18001beda  mov     edx, 2
0x18001bedf  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001bee4  mov     rax, cs:WPP_GLOBAL_Control
0x18001beeb  lea     rcx, WPP_GLOBAL_Control
0x18001bef2  cmp     rax, rcx
0x18001bef5  jz      loc_18001C07E
0x18001befb  test    byte ptr [rax+1Ch], 1
0x18001beff  jz      loc_18001C07E
0x18001bf05  cmp     byte ptr [rax+19h], 2
0x18001bf09  jb      loc_18001C07E
0x18001bf0f  mov     edx, 0E0h
0x18001bf14  jmp     loc_18001BE8B
0x18001bf19  mov     rcx, [rbp+phAlgorithm]; hObject
0x18001bf1d  lea     rax, [rbp+arg_10]
0x18001bf21  mov     [rsp+60h+dwFlags], 0; dwFlags
0x18001bf29  lea     r8, [rbp+var_C]; pbOutput
0x18001bf2d  mov     r9d, edi; cbOutput
0x18001bf30  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18001bf35  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18001bf3c  mov     [rbp+arg_10], edi
0x18001bf3f  call    cs:__imp_BCryptGetProperty
0x18001bf45  mov     ebx, eax
0x18001bf47  test    eax, eax
0x18001bf49  jz      short loc_18001BF8A
0x18001bf4b  mov     edx, 2
0x18001bf50  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001bf55  mov     rax, cs:WPP_GLOBAL_Control
0x18001bf5c  lea     rcx, WPP_GLOBAL_Control
0x18001bf63  cmp     rax, rcx
0x18001bf66  jz      loc_18001C07E
0x18001bf6c  test    byte ptr [rax+1Ch], 1
0x18001bf70  jz      loc_18001C07E
0x18001bf76  cmp     byte ptr [rax+19h], 2
0x18001bf7a  jb      loc_18001C07E
0x18001bf80  mov     edx, 0E1h
0x18001bf85  jmp     loc_18001BE8B
0x18001bf8a  mov     rcx, rsi; size
0x18001bf8d  call    MIDL_user_allocate
0x18001bf92  mov     rdi, rax
0x18001bf95  test    rax, rax
0x18001bf98  jnz     short loc_18001BFEB
0x18001bf9a  mov     ebx, 8009000Eh
0x18001bf9f  mov     rax, cs:WPP_GLOBAL_Control
0x18001bfa6  lea     rcx, WPP_GLOBAL_Control
0x18001bfad  cmp     rax, rcx
0x18001bfb0  jz      loc_18001C07E
0x18001bfb6  test    byte ptr [rax+1Ch], 1
0x18001bfba  jz      loc_18001C07E
0x18001bfc0  cmp     byte ptr [rax+19h], 2
0x18001bfc4  jb      loc_18001C07E
0x18001bfca  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001bfd1  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x18001bfd8  mov     rcx, [rax+10h]
0x18001bfdc  mov     edx, 0E2h
0x18001bfe1  call    WPP_SF_s
0x18001bfe6  jmp     loc_18001C07E
0x18001bfeb  mov     rax, [rbp+arg_20]
0x18001bfef  mov     r9, [r14+8]
0x18001bff3  mov     r8d, dword ptr [rbp+pbOutput]
0x18001bff7  mov     edx, dword ptr [rbp+var_C]
0x18001bffa  mov     rcx, [rbp+phAlgorithm]
0x18001bffe  mov     [rsp+60h+var_18], rax
0x18001c003  mov     eax, [r14+10h]
0x18001c007  mov     [rsp+60h+var_20], esi
0x18001c00b  mov     [rsp+60h+var_28], rdi
0x18001c010  mov     [rsp+60h+var_30], esi
0x18001c014  mov     qword ptr [rsp+60h+dwFlags], r12
0x18001c019  mov     dword ptr [rsp+60h+pcbResult], eax
0x18001c01d  call    CheckOAEPPadding
0x18001c022  mov     ebx, eax
0x18001c024  test    eax, eax
0x18001c026  jz      short loc_18001C07B
0x18001c028  mov     edx, 2
0x18001c02d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001c032  mov     rax, cs:WPP_GLOBAL_Control
0x18001c039  lea     rcx, WPP_GLOBAL_Control
0x18001c040  cmp     rax, rcx
0x18001c043  jz      short loc_18001C071
0x18001c045  test    byte ptr [rax+1Ch], 1
0x18001c049  jz      short loc_18001C071
0x18001c04b  cmp     byte ptr [rax+19h], 2
0x18001c04f  jb      short loc_18001C071
0x18001c051  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001c058  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x18001c05f  mov     rcx, [rax+10h]
0x18001c063  mov     edx, 0E3h
0x18001c068  mov     dword ptr [rsp+60h+pcbResult], ebx
0x18001c06c  call    WPP_SF_sd
0x18001c071  mov     rcx, rdi
0x18001c074  call    CspFreeH
0x18001c079  jmp     short loc_18001C07E
0x18001c07b  mov     [r15], rdi
0x18001c07e  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18001c082  test    rcx, rcx
0x18001c085  jz      short loc_18001C08F
0x18001c087  xor     edx, edx; dwFlags
0x18001c089  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001c08f  lea     r11, [rsp+60h+var_s0]
0x18001c094  mov     eax, ebx
0x18001c096  mov     rbx, [r11+30h]
0x18001c09a  mov     rsi, [r11+38h]
0x18001c09e  mov     rsp, r11
0x18001c0a1  pop     r15
0x18001c0a3  pop     r14
0x18001c0a5  pop     r12
0x18001c0a7  pop     rdi
0x18001c0a8  pop     rbp
0x18001c0a9  retn
```
