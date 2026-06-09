# MatchesRequiredForOpenKeySet(_CARD_STATE *,ushort *,uchar *)

- ea: `0x1800343f8`
- end: `0x1800344bc`
- name: `?MatchesRequiredForOpenKeySet@@YAKPEAU_CARD_STATE@@PEAGPEAE@Z`
- size: `196`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, unsigned __int16 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800339ac`

## callees

- `0x18000a408`
- `0x180011fd8`
- `0x180013734`
- `0x180033ce0`
- `0x1800343f8`

## pseudocode

```c
__int64 __fastcall MatchesRequiredForOpenKeySet(struct _CARD_STATE *a1, unsigned __int16 *a2, unsigned __int8 *a3)
{
  unsigned int v4; // ebx
  PVOID v7; // rcx

  v4 = 0;
  WppTraceIndent((__int64)a1, 0);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  if ( a2 )
  {
    v4 = MatchesRequiredContainerNameInCard(a1, a2, a3);
    if ( v4 )
      v4 = -2146435024;
  }
  WppTraceIndent((__int64)v7, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      v4);
  }
  return v4;
}

```

## disassembly

```asm
0x1800343f8  push    rbx
0x1800343fa  push    rbp
0x1800343fb  push    rsi
0x1800343fc  push    rdi
0x1800343fd  push    r14
0x1800343ff  sub     rsp, 30h
0x180034403  mov     rdi, rdx
0x180034406  xor     ebx, ebx
0x180034408  xor     edx, edx
0x18003440a  mov     rsi, r8
0x18003440d  mov     rbp, rcx
0x180034410  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034415  mov     rcx, cs:WPP_GLOBAL_Control
0x18003441c  lea     r14, WPP_GLOBAL_Control
0x180034423  cmp     rcx, r14
0x180034426  jz      short loc_18003444E
0x180034428  test    byte ptr [rcx+1Ch], 2
0x18003442c  jz      short loc_18003444E
0x18003442e  cmp     byte ptr [rcx+19h], 5
0x180034432  jb      short loc_18003444E
0x180034434  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003443b  lea     edx, [rbx+29h]
0x18003443e  mov     rcx, [rcx+10h]
0x180034442  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034449  call    WPP_SF_s
0x18003444e  test    rdi, rdi
0x180034451  jz      short loc_18003446D
0x180034453  mov     r8, rsi; unsigned __int8 *
0x180034456  mov     rdx, rdi; unsigned __int16 *
0x180034459  mov     rcx, rbp; struct _CARD_STATE *
0x18003445c  call    ?MatchesRequiredContainerNameInCard@@YAKPEAU_CARD_STATE@@PEAGPEAE@Z; MatchesRequiredContainerNameInCard(_CARD_STATE *,ushort *,uchar *)
0x180034461  mov     ebx, eax
0x180034463  mov     eax, 80100030h
0x180034468  test    ebx, ebx
0x18003446a  cmovnz  ebx, eax
0x18003446d  mov     edx, 1
0x180034472  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034477  mov     rcx, cs:WPP_GLOBAL_Control
0x18003447e  cmp     rcx, r14
0x180034481  jz      short loc_1800344AF
0x180034483  test    byte ptr [rcx+1Ch], 2
0x180034487  jz      short loc_1800344AF
0x180034489  cmp     byte ptr [rcx+19h], 5
0x18003448d  jb      short loc_1800344AF
0x18003448f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180034496  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x18003449d  mov     rcx, [rcx+10h]
0x1800344a1  mov     edx, 2Ah ; '*'
0x1800344a6  mov     [rsp+58h+var_38], ebx
0x1800344aa  call    WPP_SF_sd
0x1800344af  mov     eax, ebx
0x1800344b1  add     rsp, 30h
0x1800344b5  pop     r14
0x1800344b7  pop     rdi
0x1800344b8  pop     rsi
0x1800344b9  pop     rbp
0x1800344ba  pop     rbx
0x1800344bb  retn
```
