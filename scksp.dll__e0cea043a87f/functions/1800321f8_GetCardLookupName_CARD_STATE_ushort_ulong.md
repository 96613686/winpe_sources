# GetCardLookupName(_CARD_STATE *,ushort *,ulong)

- ea: `0x1800321f8`
- end: `0x180032312`
- name: `?GetCardLookupName@@YAKPEAU_CARD_STATE@@PEAGK@Z`
- size: `282`
- prototype: `unsigned int(struct _CARD_STATE *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180031a94`
- `0x180034aa0`

## callees

- `0x18000a408`
- `0x18001147c`
- `0x180011fd8`
- `0x180013734`
- `0x1800321f8`
- `0x180036878`

## string_xrefs

- `0x180032259`: `Cached_CardState`

## pseudocode

```c
__int64 __fastcall GetCardLookupName(struct _CARD_STATE *a1, unsigned __int16 *a2)
{
  PVOID v4; // rcx
  int v5; // eax
  char v6; // si
  unsigned int v7; // ebx
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  int v12; // [rsp+20h] [rbp-38h]

  WppTraceIndent((__int64)a1, 0);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  if ( a1 && a2 )
  {
    v12 = *((_DWORD *)a1 + 179);
    v5 = StringCchPrintfW(a2, 0x104u, L"%s_%u", L"Cached_CardState", v12);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v7 = 0;
    }
    else
    {
      v7 = (unsigned __int16)v5;
      WppTraceIndent((__int64)v4, 2u);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_sDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, v10, *((_DWORD *)a1 + 179), v6);
      }
    }
  }
  else
  {
    v7 = 87;
  }
  WppTraceIndent((__int64)v4, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x1800321f8  push    rbx
0x1800321fa  push    rbp
0x1800321fb  push    rsi
0x1800321fc  push    rdi
0x1800321fd  sub     rsp, 38h
0x180032201  mov     rbx, rdx
0x180032204  mov     rdi, rcx
0x180032207  xor     edx, edx
0x180032209  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003220e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032215  lea     rbp, WPP_GLOBAL_Control
0x18003221c  cmp     rcx, rbp
0x18003221f  jz      short loc_180032249
0x180032221  test    byte ptr [rcx+1Ch], 2
0x180032225  jz      short loc_180032249
0x180032227  cmp     byte ptr [rcx+19h], 5
0x18003222b  jb      short loc_180032249
0x18003222d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180032234  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x18003223b  mov     rcx, [rcx+10h]
0x18003223f  mov     edx, 0Fh
0x180032244  call    WPP_SF_s
0x180032249  test    rdi, rdi
0x18003224c  jz      short loc_1800322C0
0x18003224e  test    rbx, rbx
0x180032251  jz      short loc_1800322C0
0x180032253  mov     eax, [rdi+2CCh]
0x180032259  lea     r9, aCachedCardstat; "Cached_CardState"
0x180032260  lea     r8, aSU; "%s_%u"
0x180032267  mov     [rsp+58h+var_38], eax
0x18003226b  mov     edx, 104h; unsigned __int64
0x180032270  mov     rcx, rbx; unsigned __int16 *
0x180032273  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032278  mov     esi, eax
0x18003227a  test    eax, eax
0x18003227c  jns     short loc_1800322BC
0x18003227e  mov     edx, 2
0x180032283  movzx   ebx, si
0x180032286  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003228b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032292  cmp     rcx, rbp
0x180032295  jz      short loc_1800322C5
0x180032297  test    byte ptr [rcx+1Ch], 1
0x18003229b  jz      short loc_1800322C5
0x18003229d  cmp     byte ptr [rcx+19h], 4
0x1800322a1  jb      short loc_1800322C5
0x1800322a3  mov     eax, [rdi+2CCh]
0x1800322a9  mov     rcx, [rcx+10h]
0x1800322ad  mov     [rsp+58h+var_30], esi
0x1800322b1  mov     [rsp+58h+var_38], eax
0x1800322b5  call    WPP_SF_sDd
0x1800322ba  jmp     short loc_1800322C5
0x1800322bc  xor     ebx, ebx
0x1800322be  jmp     short loc_1800322C5
0x1800322c0  mov     ebx, 57h ; 'W'
0x1800322c5  mov     edx, 1
0x1800322ca  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800322cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800322d6  cmp     rcx, rbp
0x1800322d9  jz      short loc_180032307
0x1800322db  test    byte ptr [rcx+1Ch], 2
0x1800322df  jz      short loc_180032307
0x1800322e1  cmp     byte ptr [rcx+19h], 5
0x1800322e5  jb      short loc_180032307
0x1800322e7  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800322ee  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800322f5  mov     rcx, [rcx+10h]
0x1800322f9  mov     edx, 11h
0x1800322fe  mov     [rsp+58h+var_38], ebx
0x180032302  call    WPP_SF_sd
0x180032307  mov     eax, ebx
0x180032309  add     rsp, 38h
0x18003230d  pop     rdi
0x18003230e  pop     rsi
0x18003230f  pop     rbp
0x180032310  pop     rbx
0x180032311  retn
```
