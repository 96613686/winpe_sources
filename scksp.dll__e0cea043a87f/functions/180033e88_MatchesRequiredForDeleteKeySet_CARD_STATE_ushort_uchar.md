# MatchesRequiredForDeleteKeySet(_CARD_STATE *,ushort *,uchar *)

- ea: `0x180033e88`
- end: `0x180033f53`
- name: `?MatchesRequiredForDeleteKeySet@@YAKPEAU_CARD_STATE@@PEAGPEAE@Z`
- size: `203`
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
- `0x180033e88`

## pseudocode

```c
__int64 __fastcall MatchesRequiredForDeleteKeySet(struct _CARD_STATE *a1, unsigned __int16 *a2, unsigned __int8 *a3)
{
  PVOID v6; // rcx
  unsigned int v7; // ebx

  WppTraceIndent((__int64)a1, 0);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  if ( *((_DWORD *)a1 + 175) )
  {
    v7 = -2146435020;
  }
  else
  {
    v7 = MatchesRequiredContainerNameInCard(a1, a2, a3);
    if ( v7 )
      v7 = -2146435024;
  }
  WppTraceIndent((__int64)v6, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x180033e88  push    rbx
0x180033e8a  push    rbp
0x180033e8b  push    rsi
0x180033e8c  push    rdi
0x180033e8d  sub     rsp, 38h
0x180033e91  mov     rsi, rdx
0x180033e94  mov     rdi, r8
0x180033e97  xor     edx, edx
0x180033e99  mov     rbx, rcx
0x180033e9c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180033ea1  mov     rcx, cs:WPP_GLOBAL_Control
0x180033ea8  lea     rbp, WPP_GLOBAL_Control
0x180033eaf  cmp     rcx, rbp
0x180033eb2  jz      short loc_180033EDC
0x180033eb4  test    byte ptr [rcx+1Ch], 2
0x180033eb8  jz      short loc_180033EDC
0x180033eba  cmp     byte ptr [rcx+19h], 5
0x180033ebe  jb      short loc_180033EDC
0x180033ec0  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180033ec7  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180033ece  mov     rcx, [rcx+10h]
0x180033ed2  mov     edx, 2Eh ; '.'
0x180033ed7  call    WPP_SF_s
0x180033edc  cmp     dword ptr [rbx+2BCh], 0
0x180033ee3  jz      short loc_180033EEC
0x180033ee5  mov     ebx, 80100034h
0x180033eea  jmp     short loc_180033F06
0x180033eec  mov     r8, rdi; unsigned __int8 *
0x180033eef  mov     rdx, rsi; unsigned __int16 *
0x180033ef2  mov     rcx, rbx; struct _CARD_STATE *
0x180033ef5  call    ?MatchesRequiredContainerNameInCard@@YAKPEAU_CARD_STATE@@PEAGPEAE@Z; MatchesRequiredContainerNameInCard(_CARD_STATE *,ushort *,uchar *)
0x180033efa  mov     ebx, eax
0x180033efc  mov     eax, 80100030h
0x180033f01  test    ebx, ebx
0x180033f03  cmovnz  ebx, eax
0x180033f06  mov     edx, 1
0x180033f0b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180033f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f17  cmp     rcx, rbp
0x180033f1a  jz      short loc_180033F48
0x180033f1c  test    byte ptr [rcx+1Ch], 2
0x180033f20  jz      short loc_180033F48
0x180033f22  cmp     byte ptr [rcx+19h], 5
0x180033f26  jb      short loc_180033F48
0x180033f28  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180033f2f  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180033f36  mov     rcx, [rcx+10h]
0x180033f3a  mov     edx, 2Fh ; '/'
0x180033f3f  mov     [rsp+58h+var_38], ebx
0x180033f43  call    WPP_SF_sd
0x180033f48  mov     eax, ebx
0x180033f4a  add     rsp, 38h
0x180033f4e  pop     rdi
0x180033f4f  pop     rsi
0x180033f50  pop     rbp
0x180033f51  pop     rbx
0x180033f52  retn
```
