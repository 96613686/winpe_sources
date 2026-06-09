# GetCachedCardContainerProperty

- ea: `0x1800300a4`
- end: `0x18003036f`
- name: `GetCachedCardContainerProperty`
- size: `715`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: ``

## callers

- `0x180017f6c`
- `0x180031340`
- `0x18003256c`

## callees

- `0x180009e76`
- `0x180009e82`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x18002b140`
- `0x18002cda8`
- `0x18002eb6c`
- `0x18002fc8c`
- `0x18002fe08`
- `0x1800300a4`
- `0x180036a14`
- `0x18003c240`

## string_xrefs

- `0x180030117`: `Cached_ContainerProperty`

## pseudocode

```c
__int64 __fastcall GetCachedCardContainerProperty(__int64 a1, unsigned __int8 a2, __int64 a3, _QWORD *a4, _DWORD *a5)
{
  int v6; // r12d
  _DWORD *v9; // rsi
  unsigned int CardCacheForItem; // eax
  __int64 v11; // rdx
  unsigned int CardContainerProperty; // edi
  __int64 v13; // rcx
  int v14; // r9d
  __int64 v15; // rcx
  void *v16; // rbx
  void *v17; // rax
  __int64 v18; // rcx
  int v19; // eax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  void *Src; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+4Ch] [rbp-B4h]
  _BYTE v26[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v27[266]; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v28; // [rsp+268h] [rbp+168h]

  v6 = a2;
  Src = 0;
  LODWORD(Size) = 0;
  memset_0(v26, 0, 0x228u);
  if ( !a4 || !a5 )
    return 2148532228LL;
  *a4 = 0;
  *a5 = 0;
  v9 = 0;
  v24 = 7;
  v25 = 1;
  v23 = a1;
  StringCbPrintfW(v27, 0x208u, L"%s_%s_%d", L"Cached_ContainerProperty", a3, v6);
  CardCacheForItem = CspQueryCardCacheForItem((struct _CARD_CACHE_QUERY_INFO *)&v23);
  CardContainerProperty = CardCacheForItem;
  if ( !CardCacheForItem )
  {
    LODWORD(Size) = *(_DWORD *)(v28 + 12);
    v17 = MIDL_user_allocate((unsigned int)Size);
    v16 = v17;
    if ( !v17 )
    {
      WppTraceIndent(v18, 2u);
      CardContainerProperty = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_26;
    }
    memcpy_0(v17, (const void *)(v28 + 16), (unsigned int)Size);
    goto LABEL_25;
  }
  if ( CardCacheForItem == 1168 )
  {
    v13 = *(_QWORD *)(a1 + 8);
    if ( !v13 )
    {
      CardContainerProperty = 87;
      WppTraceIndent(0, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          v14,
          (__int64)"pCardState->pCardData");
      }
      goto LABEL_30;
    }
    LOBYTE(v11) = v6;
    CardContainerProperty = GetCardContainerProperty(v13, v11, a3, &Src, &Size);
    if ( CardContainerProperty )
      goto LABEL_16;
    v9 = MIDL_user_allocate((unsigned int)Size + 16LL);
    if ( !v9 )
    {
      WppTraceIndent(v15, 2u);
      CardContainerProperty = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
LABEL_16:
      v16 = Src;
LABEL_26:
      if ( v16 )
        CspFreeH(v16);
      if ( v9 )
        CspFreeH(v9);
      goto LABEL_30;
    }
    v16 = Src;
    v9[3] = Size;
    memcpy_0(v9 + 4, v16, (unsigned int)Size);
    CardContainerProperty = CspAddCardCacheItem((struct _CARD_CACHE_QUERY_INFO *)&v23, v9);
    if ( CardContainerProperty )
      goto LABEL_26;
LABEL_25:
    v19 = Size;
    *a4 = v16;
    v16 = 0;
    *a5 = v19;
    goto LABEL_26;
  }
LABEL_30:
  if ( v28 )
    CspFreeH(v28);
  return CardContainerProperty;
}

```

## disassembly

```asm
0x1800300a4  push    rbp
0x1800300a6  push    rbx
0x1800300a7  push    rsi
0x1800300a8  push    rdi
0x1800300a9  push    r12
0x1800300ab  push    r13
0x1800300ad  push    r14
0x1800300af  push    r15
0x1800300b1  lea     rbp, [rsp-198h]
0x1800300b9  sub     rsp, 298h
0x1800300c0  mov     rax, cs:__security_cookie
0x1800300c7  xor     rax, rsp
0x1800300ca  mov     [rbp+1D0h+var_50], rax
0x1800300d1  mov     r14, [rbp+1D0h+arg_20]
0x1800300d8  mov     r13, r8
0x1800300db  movzx   r12d, dl
0x1800300df  mov     rbx, rcx
0x1800300e2  xor     edi, edi
0x1800300e4  lea     rcx, [rsp+2D0h+var_280]; void *
0x1800300e9  xor     edx, edx; Val
0x1800300eb  mov     [rsp+2D0h+Src], rdi
0x1800300f0  mov     r8d, 228h; Size
0x1800300f6  mov     dword ptr [rsp+2D0h+Size], edi
0x1800300fa  mov     r15, r9
0x1800300fd  call    memset_0
0x180030102  test    r15, r15
0x180030105  jz      loc_180030347
0x18003010b  test    r14, r14
0x18003010e  jz      loc_180030347
0x180030114  mov     [r15], rdi
0x180030117  lea     r9, aCachedContaine; "Cached_ContainerProperty"
0x18003011e  mov     [rsp+2D0h+var_2A8], r12d
0x180030123  lea     r8, aSSD; "%s_%s_%d"
0x18003012a  mov     edx, 208h; unsigned __int64
0x18003012f  mov     [r14], edi
0x180030132  lea     rcx, [rsp+2D0h+var_27C]; unsigned __int16 *
0x180030137  mov     [rsp+2D0h+var_2B0], r13
0x18003013c  mov     esi, edi
0x18003013e  mov     [rsp+2D0h+var_288], 7
0x180030146  mov     [rsp+2D0h+var_284], 1
0x18003014e  mov     [rsp+2D0h+var_290], rbx
0x180030153  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030158  lea     rcx, [rsp+2D0h+var_290]; struct _CARD_CACHE_QUERY_INFO *
0x18003015d  call    CspQueryCardCacheForItem
0x180030162  mov     edi, eax
0x180030164  test    eax, eax
0x180030166  jz      loc_180030293
0x18003016c  cmp     eax, 490h
0x180030171  jnz     loc_180030332
0x180030177  mov     rcx, [rbx+8]
0x18003017b  test    rcx, rcx
0x18003017e  jnz     short loc_1800301DA
0x180030180  lea     edx, [rsi+2]
0x180030183  lea     edi, [rsi+57h]
0x180030186  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003018b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030192  lea     rax, WPP_GLOBAL_Control
0x180030199  cmp     rcx, rax
0x18003019c  jz      loc_180030332
0x1800301a2  test    byte ptr [rcx+1Ch], 1
0x1800301a6  jz      loc_180030332
0x1800301ac  cmp     byte ptr [rcx+19h], 2
0x1800301b0  jb      loc_180030332
0x1800301b6  mov     rcx, [rcx+10h]
0x1800301ba  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x1800301c1  lea     edx, [rsi+19h]
0x1800301c4  mov     [rsp+2D0h+var_2B0], rax
0x1800301c9  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x1800301d0  call    WPP_SF_ss
0x1800301d5  jmp     loc_180030332
0x1800301da  lea     rax, [rsp+2D0h+Size]
0x1800301df  mov     r8, r13
0x1800301e2  lea     r9, [rsp+2D0h+Src]
0x1800301e7  mov     [rsp+2D0h+var_2B0], rax
0x1800301ec  mov     dl, r12b
0x1800301ef  call    GetCardContainerProperty
0x1800301f4  mov     edi, eax
0x1800301f6  test    eax, eax
0x1800301f8  jnz     short loc_180030253
0x1800301fa  mov     ecx, dword ptr [rsp+2D0h+Size]
0x1800301fe  add     rcx, 10h; size
0x180030202  call    MIDL_user_allocate
0x180030207  mov     rsi, rax
0x18003020a  test    rax, rax
0x18003020d  jnz     short loc_18003025D
0x18003020f  lea     edx, [rdi+2]
0x180030212  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180030217  lea     edi, [rsi+8]
0x18003021a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030221  lea     rax, WPP_GLOBAL_Control
0x180030228  cmp     rcx, rax
0x18003022b  jz      short loc_180030253
0x18003022d  test    byte ptr [rcx+1Ch], 1
0x180030231  jz      short loc_180030253
0x180030233  cmp     byte ptr [rcx+19h], 2
0x180030237  jb      short loc_180030253
0x180030239  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180030240  lea     edx, [rsi+1Ah]
0x180030243  mov     rcx, [rcx+10h]
0x180030247  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18003024e  call    WPP_SF_s
0x180030253  mov     rbx, [rsp+2D0h+Src]
0x180030258  jmp     loc_180030318
0x18003025d  mov     eax, dword ptr [rsp+2D0h+Size]
0x180030261  lea     rcx, [rsi+10h]; void *
0x180030265  mov     rbx, [rsp+2D0h+Src]
0x18003026a  mov     [rsi+0Ch], eax
0x18003026d  mov     rdx, rbx; Src
0x180030270  mov     r8d, dword ptr [rsp+2D0h+Size]; Size
0x180030275  call    memcpy_0
0x18003027a  mov     rdx, rsi; Destination
0x18003027d  lea     rcx, [rsp+2D0h+var_290]; struct _CARD_CACHE_QUERY_INFO *
0x180030282  call    CspAddCardCacheItem
0x180030287  mov     edi, eax
0x180030289  test    eax, eax
0x18003028b  jnz     loc_180030318
0x180030291  jmp     short loc_18003030C
0x180030293  mov     rax, [rbp+1D0h+var_68]
0x18003029a  mov     ecx, [rax+0Ch]; size
0x18003029d  mov     dword ptr [rsp+2D0h+Size], ecx
0x1800302a1  call    MIDL_user_allocate
0x1800302a6  mov     rbx, rax
0x1800302a9  test    rax, rax
0x1800302ac  jnz     short loc_1800302F4
0x1800302ae  lea     edx, [rax+2]
0x1800302b1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800302b6  lea     edi, [rbx+8]
0x1800302b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800302c0  lea     rax, WPP_GLOBAL_Control
0x1800302c7  cmp     rcx, rax
0x1800302ca  jz      short loc_180030318
0x1800302cc  test    byte ptr [rcx+1Ch], 1
0x1800302d0  jz      short loc_180030318
0x1800302d2  cmp     byte ptr [rcx+19h], 2
0x1800302d6  jb      short loc_180030318
0x1800302d8  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800302df  lea     edx, [rbx+18h]
0x1800302e2  mov     rcx, [rcx+10h]
0x1800302e6  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x1800302ed  call    WPP_SF_s
0x1800302f2  jmp     short loc_180030318
0x1800302f4  mov     rdx, [rbp+1D0h+var_68]
0x1800302fb  mov     rcx, rax; void *
0x1800302fe  mov     r8d, dword ptr [rsp+2D0h+Size]; Size
0x180030303  add     rdx, 10h; Src
0x180030307  call    memcpy_0
0x18003030c  mov     eax, dword ptr [rsp+2D0h+Size]
0x180030310  mov     [r15], rbx
0x180030313  xor     ebx, ebx
0x180030315  mov     [r14], eax
0x180030318  test    rbx, rbx
0x18003031b  jz      short loc_180030325
0x18003031d  mov     rcx, rbx
0x180030320  call    CspFreeH
0x180030325  test    rsi, rsi
0x180030328  jz      short loc_180030332
0x18003032a  mov     rcx, rsi
0x18003032d  call    CspFreeH
0x180030332  mov     rcx, [rbp+1D0h+var_68]
0x180030339  test    rcx, rcx
0x18003033c  jz      short loc_180030343
0x18003033e  call    CspFreeH
0x180030343  mov     eax, edi
0x180030345  jmp     short loc_18003034C
0x180030347  mov     eax, 80100004h
0x18003034c  mov     rcx, [rbp+1D0h+var_50]
0x180030353  xor     rcx, rsp; StackCookie
0x180030356  call    __security_check_cookie
0x18003035b  add     rsp, 298h
0x180030362  pop     r15
0x180030364  pop     r14
0x180030366  pop     r13
0x180030368  pop     r12
0x18003036a  pop     rdi
0x18003036b  pop     rsi
0x18003036c  pop     rbx
0x18003036d  pop     rbp
0x18003036e  retn
```
