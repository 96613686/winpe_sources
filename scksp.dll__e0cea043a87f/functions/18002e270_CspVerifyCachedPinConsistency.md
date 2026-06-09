# CspVerifyCachedPinConsistency

- ea: `0x18002e270`
- end: `0x18002e3b6`
- name: `CspVerifyCachedPinConsistency`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001b6f8`

## callees

- `0x180009e82`
- `0x18000a408`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x18002cda8`
- `0x18002e270`
- `0x18002fe08`
- `0x18003c240`

## string_xrefs

- `0x18002e2ff`: `Cached_Pin`

## pseudocode

```c
__int64 __fastcall CspVerifyCachedPinConsistency(__int64 a1, int a2)
{
  __int64 v4; // rcx
  unsigned int CardCacheForItem; // eax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-268h]
  __int64 v10; // [rsp+30h] [rbp-258h] BYREF
  int v11; // [rsp+38h] [rbp-250h]
  int v12; // [rsp+3Ch] [rbp-24Ch]
  unsigned __int16 v13[266]; // [rsp+44h] [rbp-244h] BYREF
  __int64 v14; // [rsp+258h] [rbp-30h]

  memset_0(&v10, 0, 0x238u);
  WppTraceIndent(v4, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids, WPP_pszIndent);
  }
  memset_0(&v10, 0, 0x238u);
  v9 = a2;
  StringCbPrintfW(v13, 0x104u, L"%s\\%d", L"Cached_Pin", v9);
  v10 = a1;
  v11 = 1;
  v12 = 1;
  CardCacheForItem = CspQueryCardCacheForItem((struct _CARD_CACHE_QUERY_INFO *)&v10);
  v6 = v14;
  v7 = CardCacheForItem;
  if ( v14 )
    CspFreeH(v14);
  WppTraceIndent(v6, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
      (_DWORD)WPP_pszIndent,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x18002e270  mov     [rsp+arg_0], rbx
0x18002e275  mov     [rsp+arg_10], rsi
0x18002e27a  push    rdi
0x18002e27b  sub     rsp, 280h
0x18002e282  mov     rax, cs:__security_cookie
0x18002e289  xor     rax, rsp
0x18002e28c  mov     [rsp+288h+var_18], rax
0x18002e294  mov     edi, edx
0x18002e296  mov     rbx, rcx
0x18002e299  xor     edx, edx; Val
0x18002e29b  lea     rcx, [rsp+288h+var_258]; void *
0x18002e2a0  mov     r8d, 238h; Size
0x18002e2a6  call    memset_0
0x18002e2ab  xor     edx, edx
0x18002e2ad  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002e2b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e2b9  lea     rsi, WPP_GLOBAL_Control
0x18002e2c0  cmp     rcx, rsi
0x18002e2c3  jz      short loc_18002E2ED
0x18002e2c5  test    byte ptr [rcx+1Ch], 2
0x18002e2c9  jz      short loc_18002E2ED
0x18002e2cb  cmp     byte ptr [rcx+19h], 5
0x18002e2cf  jb      short loc_18002E2ED
0x18002e2d1  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002e2d8  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002e2df  mov     rcx, [rcx+10h]
0x18002e2e3  mov     edx, 14h
0x18002e2e8  call    WPP_SF_s
0x18002e2ed  xor     edx, edx; Val
0x18002e2ef  lea     rcx, [rsp+288h+var_258]; void *
0x18002e2f4  mov     r8d, 238h; Size
0x18002e2fa  call    memset_0
0x18002e2ff  lea     r9, aCachedPin; "Cached_Pin"
0x18002e306  mov     [rsp+288h+var_268], edi
0x18002e30a  lea     r8, aSD; "%s\\%d"
0x18002e311  mov     edx, 104h; unsigned __int64
0x18002e316  lea     rcx, [rsp+288h+var_244]; unsigned __int16 *
0x18002e31b  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e320  mov     edi, 1
0x18002e325  mov     [rsp+288h+var_258], rbx
0x18002e32a  lea     rcx, [rsp+288h+var_258]; struct _CARD_CACHE_QUERY_INFO *
0x18002e32f  mov     [rsp+288h+var_250], edi
0x18002e333  mov     [rsp+288h+var_24C], edi
0x18002e337  call    CspQueryCardCacheForItem
0x18002e33c  mov     rcx, [rsp+288h+var_30]
0x18002e344  mov     ebx, eax
0x18002e346  test    rcx, rcx
0x18002e349  jz      short loc_18002E350
0x18002e34b  call    CspFreeH
0x18002e350  mov     edx, edi
0x18002e352  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002e357  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e35e  cmp     rcx, rsi
0x18002e361  jz      short loc_18002E38F
0x18002e363  test    byte ptr [rcx+1Ch], 2
0x18002e367  jz      short loc_18002E38F
0x18002e369  cmp     byte ptr [rcx+19h], 5
0x18002e36d  jb      short loc_18002E38F
0x18002e36f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002e376  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002e37d  mov     rcx, [rcx+10h]
0x18002e381  mov     edx, 15h
0x18002e386  mov     [rsp+288h+var_268], ebx
0x18002e38a  call    WPP_SF_sd
0x18002e38f  mov     eax, ebx
0x18002e391  mov     rcx, [rsp+288h+var_18]
0x18002e399  xor     rcx, rsp; StackCookie
0x18002e39c  call    __security_check_cookie
0x18002e3a1  lea     r11, [rsp+288h+var_8]
0x18002e3a9  mov     rbx, [r11+10h]
0x18002e3ad  mov     rsi, [r11+20h]
0x18002e3b1  mov     rsp, r11
0x18002e3b4  pop     rdi
0x18002e3b5  retn
```
