# GetCachedCardProperty

- ea: `0x180030500`
- end: `0x1800307c7`
- name: `GetCachedCardProperty`
- size: `711`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: ``

## callers

- `0x18002db88`
- `0x18002dc70`
- `0x18002dd50`
- `0x180032cf4`

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
- `0x180030500`
- `0x180036b04`
- `0x18003c240`

## string_xrefs

- `0x18003056f`: `Cached_CardProperty`

## pseudocode

```c
__int64 __fastcall GetCachedCardProperty(__int64 a1, const wchar_t *a2, _QWORD *a3, _DWORD *a4, int a5)
{
  _DWORD *v9; // rsi
  unsigned int CardCacheForItem; // eax
  unsigned int CardProperty; // edi
  __int64 v12; // rcx
  int v13; // r9d
  __int64 v14; // rcx
  void *v15; // rbx
  void *v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  void *Src; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+48h] [rbp-B8h]
  int v24; // [rsp+4Ch] [rbp-B4h]
  _BYTE v25[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v26[266]; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v27; // [rsp+268h] [rbp+168h]

  Src = 0;
  LODWORD(Size) = 0;
  memset_0(v25, 0, 0x228u);
  if ( !a3 || !a4 )
    return 2148532228LL;
  *a3 = 0;
  v9 = 0;
  *a4 = 0;
  v23 = 7;
  v24 = 1;
  v22 = a1;
  StringCbPrintfW(v26, 0x208u, L"%s_%s_%x", L"Cached_CardProperty", a2, a5);
  CardCacheForItem = CspQueryCardCacheForItem((struct _CARD_CACHE_QUERY_INFO *)&v22);
  CardProperty = CardCacheForItem;
  if ( !CardCacheForItem )
  {
    LODWORD(Size) = *(_DWORD *)(v27 + 12);
    v16 = MIDL_user_allocate((unsigned int)Size);
    v15 = v16;
    if ( !v16 )
    {
      WppTraceIndent(v17, 2u);
      CardProperty = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_26;
    }
    memcpy_0(v16, (const void *)(v27 + 16), (unsigned int)Size);
    goto LABEL_25;
  }
  if ( CardCacheForItem == 1168 )
  {
    v12 = *(_QWORD *)(a1 + 8);
    if ( !v12 )
    {
      CardProperty = 87;
      WppTraceIndent(0, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          v13,
          (__int64)"pCardState->pCardData");
      }
      goto LABEL_30;
    }
    CardProperty = GetCardProperty(v12, a2, &Src, (__int64)&Size, a5);
    if ( CardProperty )
      goto LABEL_16;
    v9 = MIDL_user_allocate((unsigned int)Size + 16LL);
    if ( !v9 )
    {
      WppTraceIndent(v14, 2u);
      CardProperty = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
LABEL_16:
      v15 = Src;
LABEL_26:
      if ( v15 )
        CspFreeH(v15);
      if ( v9 )
        CspFreeH(v9);
      goto LABEL_30;
    }
    v15 = Src;
    v9[3] = Size;
    memcpy_0(v9 + 4, v15, (unsigned int)Size);
    CardProperty = CspAddCardCacheItem((struct _CARD_CACHE_QUERY_INFO *)&v22, v9);
    if ( CardProperty )
      goto LABEL_26;
LABEL_25:
    v18 = Size;
    *a3 = v15;
    v15 = 0;
    *a4 = v18;
    goto LABEL_26;
  }
LABEL_30:
  if ( v27 )
    CspFreeH(v27);
  return CardProperty;
}

```

## disassembly

```asm
0x180030500  push    rbp
0x180030502  push    rbx
0x180030503  push    rsi
0x180030504  push    rdi
0x180030505  push    r12
0x180030507  push    r13
0x180030509  push    r14
0x18003050b  push    r15
0x18003050d  lea     rbp, [rsp-198h]
0x180030515  sub     rsp, 298h
0x18003051c  mov     rax, cs:__security_cookie
0x180030523  xor     rax, rsp
0x180030526  mov     [rbp+1D0h+var_50], rax
0x18003052d  mov     r15, r8
0x180030530  mov     r13, rdx
0x180030533  mov     rbx, rcx
0x180030536  xor     edi, edi
0x180030538  xor     edx, edx; Val
0x18003053a  mov     [rsp+2D0h+Src], rdi
0x18003053f  mov     r8d, 228h; Size
0x180030545  mov     dword ptr [rsp+2D0h+Size], edi
0x180030549  lea     rcx, [rsp+2D0h+var_280]; void *
0x18003054e  mov     r14, r9
0x180030551  call    memset_0
0x180030556  test    r15, r15
0x180030559  jz      loc_18003079F
0x18003055f  test    r14, r14
0x180030562  jz      loc_18003079F
0x180030568  mov     r12d, [rbp+1D0h+arg_20]
0x18003056f  lea     r9, aCachedCardprop; "Cached_CardProperty"
0x180030576  mov     [r15], rdi
0x180030579  lea     r8, aSSX; "%s_%s_%x"
0x180030580  mov     [rsp+2D0h+var_2A8], r12d
0x180030585  lea     rcx, [rsp+2D0h+var_27C]; unsigned __int16 *
0x18003058a  mov     edx, 208h; unsigned __int64
0x18003058f  mov     [rsp+2D0h+var_2B0], r13
0x180030594  mov     esi, edi
0x180030596  mov     [r14], edi
0x180030599  mov     [rsp+2D0h+var_288], 7
0x1800305a1  mov     [rsp+2D0h+var_284], 1
0x1800305a9  mov     [rsp+2D0h+var_290], rbx
0x1800305ae  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800305b3  lea     rcx, [rsp+2D0h+var_290]; struct _CARD_CACHE_QUERY_INFO *
0x1800305b8  call    CspQueryCardCacheForItem
0x1800305bd  mov     edi, eax
0x1800305bf  test    eax, eax
0x1800305c1  jz      loc_1800306EB
0x1800305c7  cmp     eax, 490h
0x1800305cc  jnz     loc_18003078A
0x1800305d2  mov     rcx, [rbx+8]
0x1800305d6  test    rcx, rcx
0x1800305d9  jnz     short loc_180030635
0x1800305db  lea     edx, [rsi+2]
0x1800305de  lea     edi, [rsi+57h]
0x1800305e1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800305e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305ed  lea     rax, WPP_GLOBAL_Control
0x1800305f4  cmp     rcx, rax
0x1800305f7  jz      loc_18003078A
0x1800305fd  test    byte ptr [rcx+1Ch], 1
0x180030601  jz      loc_18003078A
0x180030607  cmp     byte ptr [rcx+19h], 2
0x18003060b  jb      loc_18003078A
0x180030611  mov     rcx, [rcx+10h]
0x180030615  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18003061c  lea     edx, [rsi+1Ch]
0x18003061f  mov     [rsp+2D0h+var_2B0], rax
0x180030624  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18003062b  call    WPP_SF_ss
0x180030630  jmp     loc_18003078A
0x180030635  lea     r9, [rsp+2D0h+Size]
0x18003063a  mov     dword ptr [rsp+2D0h+var_2B0], r12d
0x18003063f  lea     r8, [rsp+2D0h+Src]
0x180030644  mov     rdx, r13
0x180030647  call    GetCardProperty
0x18003064c  mov     edi, eax
0x18003064e  test    eax, eax
0x180030650  jnz     short loc_1800306AB
0x180030652  mov     ecx, dword ptr [rsp+2D0h+Size]
0x180030656  add     rcx, 10h; size
0x18003065a  call    MIDL_user_allocate
0x18003065f  mov     rsi, rax
0x180030662  test    rax, rax
0x180030665  jnz     short loc_1800306B5
0x180030667  lea     edx, [rdi+2]
0x18003066a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003066f  lea     edi, [rsi+8]
0x180030672  mov     rcx, cs:WPP_GLOBAL_Control
0x180030679  lea     rax, WPP_GLOBAL_Control
0x180030680  cmp     rcx, rax
0x180030683  jz      short loc_1800306AB
0x180030685  test    byte ptr [rcx+1Ch], 1
0x180030689  jz      short loc_1800306AB
0x18003068b  cmp     byte ptr [rcx+19h], 2
0x18003068f  jb      short loc_1800306AB
0x180030691  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180030698  lea     edx, [rsi+1Dh]
0x18003069b  mov     rcx, [rcx+10h]
0x18003069f  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x1800306a6  call    WPP_SF_s
0x1800306ab  mov     rbx, [rsp+2D0h+Src]
0x1800306b0  jmp     loc_180030770
0x1800306b5  mov     eax, dword ptr [rsp+2D0h+Size]
0x1800306b9  lea     rcx, [rsi+10h]; void *
0x1800306bd  mov     rbx, [rsp+2D0h+Src]
0x1800306c2  mov     [rsi+0Ch], eax
0x1800306c5  mov     rdx, rbx; Src
0x1800306c8  mov     r8d, dword ptr [rsp+2D0h+Size]; Size
0x1800306cd  call    memcpy_0
0x1800306d2  mov     rdx, rsi; Destination
0x1800306d5  lea     rcx, [rsp+2D0h+var_290]; struct _CARD_CACHE_QUERY_INFO *
0x1800306da  call    CspAddCardCacheItem
0x1800306df  mov     edi, eax
0x1800306e1  test    eax, eax
0x1800306e3  jnz     loc_180030770
0x1800306e9  jmp     short loc_180030764
0x1800306eb  mov     rax, [rbp+1D0h+var_68]
0x1800306f2  mov     ecx, [rax+0Ch]; size
0x1800306f5  mov     dword ptr [rsp+2D0h+Size], ecx
0x1800306f9  call    MIDL_user_allocate
0x1800306fe  mov     rbx, rax
0x180030701  test    rax, rax
0x180030704  jnz     short loc_18003074C
0x180030706  lea     edx, [rax+2]
0x180030709  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003070e  lea     edi, [rbx+8]
0x180030711  mov     rcx, cs:WPP_GLOBAL_Control
0x180030718  lea     rax, WPP_GLOBAL_Control
0x18003071f  cmp     rcx, rax
0x180030722  jz      short loc_180030770
0x180030724  test    byte ptr [rcx+1Ch], 1
0x180030728  jz      short loc_180030770
0x18003072a  cmp     byte ptr [rcx+19h], 2
0x18003072e  jb      short loc_180030770
0x180030730  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180030737  lea     edx, [rbx+1Bh]
0x18003073a  mov     rcx, [rcx+10h]
0x18003073e  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180030745  call    WPP_SF_s
0x18003074a  jmp     short loc_180030770
0x18003074c  mov     rdx, [rbp+1D0h+var_68]
0x180030753  mov     rcx, rax; void *
0x180030756  mov     r8d, dword ptr [rsp+2D0h+Size]; Size
0x18003075b  add     rdx, 10h; Src
0x18003075f  call    memcpy_0
0x180030764  mov     eax, dword ptr [rsp+2D0h+Size]
0x180030768  mov     [r15], rbx
0x18003076b  xor     ebx, ebx
0x18003076d  mov     [r14], eax
0x180030770  test    rbx, rbx
0x180030773  jz      short loc_18003077D
0x180030775  mov     rcx, rbx
0x180030778  call    CspFreeH
0x18003077d  test    rsi, rsi
0x180030780  jz      short loc_18003078A
0x180030782  mov     rcx, rsi
0x180030785  call    CspFreeH
0x18003078a  mov     rcx, [rbp+1D0h+var_68]
0x180030791  test    rcx, rcx
0x180030794  jz      short loc_18003079B
0x180030796  call    CspFreeH
0x18003079b  mov     eax, edi
0x18003079d  jmp     short loc_1800307A4
0x18003079f  mov     eax, 80100004h
0x1800307a4  mov     rcx, [rbp+1D0h+var_50]
0x1800307ab  xor     rcx, rsp; StackCookie
0x1800307ae  call    __security_check_cookie
0x1800307b3  add     rsp, 298h
0x1800307ba  pop     r15
0x1800307bc  pop     r14
0x1800307be  pop     r13
0x1800307c0  pop     r12
0x1800307c2  pop     rdi
0x1800307c3  pop     rsi
0x1800307c4  pop     rbx
0x1800307c5  pop     rbp
0x1800307c6  retn
```
