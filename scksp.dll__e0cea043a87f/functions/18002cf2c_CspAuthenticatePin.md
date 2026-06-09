# CspAuthenticatePin

- ea: `0x18002cf2c`
- end: `0x18002d247`
- name: `CspAuthenticatePin`
- size: `795`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18003a700`

## callees

- `0x180009e82`
- `0x18000a408`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x18002b140`
- `0x18002cda8`
- `0x18002cf2c`
- `0x18002eb6c`
- `0x18002fc8c`
- `0x18002fe08`
- `0x18003c240`
- `0x18003d010`

## string_xrefs

- `0x18002cfc2`: `Cached_Pin`

## pseudocode

```c
__int64 __fastcall CspAuthenticatePin(__int64 a1, unsigned int a2, __int64 a3, char a4)
{
  void *v8; // rdi
  __int64 v9; // rcx
  unsigned int CardCacheForItem; // eax
  __int64 v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rcx
  void *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r10
  int v18; // r9d
  const wchar_t *v19; // rdx
  unsigned int v20; // eax
  __int64 v21; // r8
  __int64 v22; // [rsp+50h] [rbp-278h] BYREF
  int v23; // [rsp+58h] [rbp-270h]
  int v24; // [rsp+5Ch] [rbp-26Ch]
  unsigned __int16 v25[266]; // [rsp+64h] [rbp-264h] BYREF
  __int64 v26; // [rsp+278h] [rbp-50h]
  int v27; // [rsp+280h] [rbp-48h]

  memset_0(&v22, 0, 0x238u);
  v8 = 0;
  WppTraceIndent(v9, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids, WPP_pszIndent);
  }
  memset_0(&v22, 0, 0x238u);
  StringCbPrintfW(v25, 0x104u, L"%s\\%d", L"Cached_Pin", a2);
  v23 = 1;
  v24 = 1;
  v22 = a1;
  CardCacheForItem = CspQueryCardCacheForItem((struct _CARD_CACHE_QUERY_INFO *)&v22);
  v12 = CardCacheForItem;
  if ( CardCacheForItem )
  {
    if ( CardCacheForItem != 1168 )
      goto LABEL_9;
    if ( v27 == 1 )
    {
      v12 = -2146434965;
      goto LABEL_9;
    }
    v15 = MIDL_user_allocate(0x10u);
    v8 = v15;
    if ( !v15 )
    {
      WppTraceIndent(v16, 2u);
      v12 = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_9;
    }
    v12 = CspAddCardCacheItem((struct _CARD_CACHE_QUERY_INFO *)&v22, v15);
    if ( v12 )
      goto LABEL_36;
  }
  v17 = *(_QWORD *)(a1 + 8);
  if ( v17 )
  {
    if ( *(_DWORD *)v17 >= 6u )
    {
      v21 = (*(_DWORD *)(a3 + 4) != 0 ? 0x20000000 : 0) | 0x40u;
      if ( (a4 & 0x40) == 0 )
        v21 = *(_DWORD *)(a3 + 4) != 0 ? 0x20000000 : 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD, __int64, __int64, _QWORD))(v17 + 360))(
              v17,
              a2,
              v21,
              *(_QWORD *)(a3 + 16),
              *(_DWORD *)(a3 + 12),
              a3 + 48,
              a3 + 40,
              0);
    }
    else
    {
      v19 = L"user";
      if ( a2 != 1 )
        v19 = L"admin";
      v20 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, _QWORD))(v17 + 160))(
              v17,
              v19,
              *(_QWORD *)(a3 + 16),
              *(unsigned int *)(a3 + 12),
              0);
    }
    v12 = v20;
  }
  else
  {
    v12 = 87;
    WppTraceIndent(v11, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
        v18,
        (__int64)"pCardState->pCardData");
    }
  }
  if ( v8 )
LABEL_36:
    CspFreeH(v8);
LABEL_9:
  v13 = v26;
  if ( v26 )
    CspFreeH(v26);
  WppTraceIndent(v13, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
      (_DWORD)WPP_pszIndent,
      v12);
  }
  return v12;
}

```

## disassembly

```asm
0x18002cf2c  mov     [rsp+arg_18], rbx
0x18002cf31  push    rbp
0x18002cf32  push    rsi
0x18002cf33  push    rdi
0x18002cf34  push    r14
0x18002cf36  push    r15
0x18002cf38  sub     rsp, 2A0h
0x18002cf3f  mov     rax, cs:__security_cookie
0x18002cf46  xor     rax, rsp
0x18002cf49  mov     [rsp+2C8h+var_38], rax
0x18002cf51  mov     rsi, r8
0x18002cf54  mov     r14d, edx
0x18002cf57  mov     rbp, rcx
0x18002cf5a  mov     ebx, 238h
0x18002cf5f  mov     r8d, ebx; Size
0x18002cf62  lea     rcx, [rsp+2C8h+var_278]; void *
0x18002cf67  xor     edx, edx; Val
0x18002cf69  mov     r15d, r9d
0x18002cf6c  call    memset_0
0x18002cf71  xor     edx, edx
0x18002cf73  xor     edi, edi
0x18002cf75  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002cf7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cf81  lea     rax, WPP_GLOBAL_Control
0x18002cf88  cmp     rcx, rax
0x18002cf8b  jz      short loc_18002CFB3
0x18002cf8d  test    byte ptr [rcx+1Ch], 2
0x18002cf91  jz      short loc_18002CFB3
0x18002cf93  cmp     byte ptr [rcx+19h], 5
0x18002cf97  jb      short loc_18002CFB3
0x18002cf99  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002cfa0  lea     edx, [rdi+16h]
0x18002cfa3  mov     rcx, [rcx+10h]
0x18002cfa7  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002cfae  call    WPP_SF_s
0x18002cfb3  mov     r8, rbx; Size
0x18002cfb6  lea     rcx, [rsp+2C8h+var_278]; void *
0x18002cfbb  xor     edx, edx; Val
0x18002cfbd  call    memset_0
0x18002cfc2  lea     r9, aCachedPin; "Cached_Pin"
0x18002cfc9  mov     dword ptr [rsp+2C8h+var_2A8], r14d
0x18002cfce  lea     r8, aSD; "%s\\%d"
0x18002cfd5  mov     edx, 104h; unsigned __int64
0x18002cfda  lea     rcx, [rsp+2C8h+var_264]; unsigned __int16 *
0x18002cfdf  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002cfe4  lea     rcx, [rsp+2C8h+var_278]; struct _CARD_CACHE_QUERY_INFO *
0x18002cfe9  mov     [rsp+2C8h+var_270], 1
0x18002cff1  mov     [rsp+2C8h+var_26C], 1
0x18002cff9  mov     [rsp+2C8h+var_278], rbp
0x18002cffe  call    CspQueryCardCacheForItem
0x18002d003  mov     ebx, eax
0x18002d005  test    eax, eax
0x18002d007  jz      loc_18002D129
0x18002d00d  cmp     eax, 490h
0x18002d012  jnz     short loc_18002D027
0x18002d014  cmp     [rsp+2C8h+var_48], 1
0x18002d01c  jnz     loc_18002D0AB
0x18002d022  mov     ebx, 8010006Bh
0x18002d027  lea     rsi, WPP_GLOBAL_Control
0x18002d02e  mov     rcx, [rsp+2C8h+var_50]
0x18002d036  test    rcx, rcx
0x18002d039  jz      short loc_18002D040
0x18002d03b  call    CspFreeH
0x18002d040  mov     edx, 1
0x18002d045  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d04a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d051  cmp     rcx, rsi
0x18002d054  jz      short loc_18002D082
0x18002d056  test    byte ptr [rcx+1Ch], 2
0x18002d05a  jz      short loc_18002D082
0x18002d05c  cmp     byte ptr [rcx+19h], 5
0x18002d060  jb      short loc_18002D082
0x18002d062  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002d069  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002d070  mov     rcx, [rcx+10h]
0x18002d074  mov     edx, 19h
0x18002d079  mov     dword ptr [rsp+2C8h+var_2A8], ebx
0x18002d07d  call    WPP_SF_sd
0x18002d082  mov     eax, ebx
0x18002d084  mov     rcx, [rsp+2C8h+var_38]
0x18002d08c  xor     rcx, rsp; StackCookie
0x18002d08f  call    __security_check_cookie
0x18002d094  mov     rbx, [rsp+2C8h+arg_18]
0x18002d09c  add     rsp, 2A0h
0x18002d0a3  pop     r15
0x18002d0a5  pop     r14
0x18002d0a7  pop     rdi
0x18002d0a8  pop     rsi
0x18002d0a9  pop     rbp
0x18002d0aa  retn
0x18002d0ab  mov     ecx, 10h; size
0x18002d0b0  call    MIDL_user_allocate
0x18002d0b5  mov     rdi, rax
0x18002d0b8  test    rax, rax
0x18002d0bb  jnz     short loc_18002D112
0x18002d0bd  lea     edx, [rax+2]
0x18002d0c0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d0c5  lea     ebx, [rdi+8]
0x18002d0c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0cf  lea     rsi, WPP_GLOBAL_Control
0x18002d0d6  cmp     rcx, rsi
0x18002d0d9  jz      loc_18002D02E
0x18002d0df  test    byte ptr [rcx+1Ch], 1
0x18002d0e3  jz      loc_18002D02E
0x18002d0e9  cmp     byte ptr [rcx+19h], 2
0x18002d0ed  jb      loc_18002D02E
0x18002d0f3  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002d0fa  lea     edx, [rdi+17h]
0x18002d0fd  mov     rcx, [rcx+10h]
0x18002d101  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002d108  call    WPP_SF_s
0x18002d10d  jmp     loc_18002D02E
0x18002d112  mov     rdx, rax; Destination
0x18002d115  lea     rcx, [rsp+2C8h+var_278]; struct _CARD_CACHE_QUERY_INFO *
0x18002d11a  call    CspAddCardCacheItem
0x18002d11f  mov     ebx, eax
0x18002d121  test    eax, eax
0x18002d123  jnz     loc_18002D233
0x18002d129  mov     r10, [rbp+8]
0x18002d12d  test    r10, r10
0x18002d130  jnz     short loc_18002D18D
0x18002d132  lea     ebx, [r10+57h]
0x18002d136  lea     edx, [rbx-55h]
0x18002d139  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d13e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d145  lea     rsi, WPP_GLOBAL_Control
0x18002d14c  cmp     rcx, rsi
0x18002d14f  jz      loc_18002D228
0x18002d155  test    byte ptr [rcx+1Ch], 1
0x18002d159  jz      loc_18002D228
0x18002d15f  cmp     byte ptr [rcx+19h], 2
0x18002d163  jb      loc_18002D228
0x18002d169  mov     rcx, [rcx+10h]
0x18002d16d  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002d174  lea     edx, [rbx-3Fh]
0x18002d177  mov     [rsp+2C8h+var_2A8], rax
0x18002d17c  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002d183  call    WPP_SF_ss
0x18002d188  jmp     loc_18002D228
0x18002d18d  cmp     dword ptr [r10], 6
0x18002d191  jnb     short loc_18002D1CB
0x18002d193  mov     r9d, [rsi+0Ch]
0x18002d197  lea     rax, aAdmin; "admin"
0x18002d19e  mov     r8, [rsi+10h]
0x18002d1a2  lea     rdx, aUser; "user"
0x18002d1a9  cmp     r14d, 1
0x18002d1ad  mov     [rsp+2C8h+var_2A8], 0
0x18002d1b6  mov     rcx, r10
0x18002d1b9  cmovnz  rdx, rax
0x18002d1bd  mov     rax, [r10+0A0h]
0x18002d1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1c9  jmp     short loc_18002D21F
0x18002d1cb  mov     eax, [rsi+4]
0x18002d1ce  lea     r9, [rsi+30h]
0x18002d1d2  neg     eax
0x18002d1d4  mov     [rsp+2C8h+var_290], 0
0x18002d1dd  lea     rax, [rsi+28h]
0x18002d1e1  mov     edx, r14d
0x18002d1e4  sbb     ecx, ecx
0x18002d1e6  mov     [rsp+2C8h+var_298], rax
0x18002d1eb  mov     rax, [r10+168h]
0x18002d1f2  and     ecx, 20000000h
0x18002d1f8  mov     r8d, ecx
0x18002d1fb  mov     [rsp+2C8h+var_2A0], r9
0x18002d200  mov     r9, [rsi+10h]
0x18002d204  or      r8d, 40h
0x18002d208  test    r15b, 40h
0x18002d20c  cmovz   r8d, ecx
0x18002d210  mov     ecx, [rsi+0Ch]
0x18002d213  mov     dword ptr [rsp+2C8h+var_2A8], ecx
0x18002d217  mov     rcx, r10
0x18002d21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d21f  lea     rsi, WPP_GLOBAL_Control
0x18002d226  mov     ebx, eax
0x18002d228  test    rdi, rdi
0x18002d22b  jz      loc_18002D02E
0x18002d231  jmp     short loc_18002D23A
0x18002d233  lea     rsi, WPP_GLOBAL_Control
0x18002d23a  mov     rcx, rdi
0x18002d23d  call    CspFreeH
0x18002d242  jmp     loc_18002D02E
```
