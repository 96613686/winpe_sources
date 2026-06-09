# I_CspQueryCapabilities(_CARD_STATE *,_CARD_CAPABILITIES *)

- ea: `0x18002c67c`
- end: `0x18002c805`
- name: `?I_CspQueryCapabilities@@YAKPEAU_CARD_STATE@@PEAU_CARD_CAPABILITIES@@@Z`
- size: `393`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, struct _CARD_CAPABILITIES *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002db88`

## callees

- `0x18000d9d0`
- `0x180011fd8`
- `0x18002c67c`
- `0x18002cda8`
- `0x18002eb6c`
- `0x18002fb68`
- `0x180030378`
- `0x18003c240`
- `0x18003d010`

## string_xrefs

- `0x18002c6be`: `Cached_CardCapabilities`

## pseudocode

```c
__int64 __fastcall I_CspQueryCapabilities(struct _CARD_STATE *a1, struct _CARD_CAPABILITIES *a2)
{
  unsigned int CachedCardData; // eax
  __int64 v5; // rcx
  _QWORD *v6; // rdi
  unsigned int v7; // ebx
  __int64 v8; // rax
  int v9; // r9d
  int v11; // [rsp+40h] [rbp-248h] BYREF
  _QWORD *v12; // [rsp+48h] [rbp-240h] BYREF
  unsigned __int16 v13[264]; // [rsp+50h] [rbp-238h] BYREF

  v12 = 0;
  v11 = 0;
  StringCbPrintfW(v13, 0x104u, L"%s", L"Cached_CardCapabilities");
  CachedCardData = GetCachedCardData((__int64)a1, v13, 0, 0, &v12, &v11, 0);
  v6 = v12;
  v7 = CachedCardData;
  if ( CachedCardData )
  {
    if ( CachedCardData == 1168 )
    {
      v8 = *((_QWORD *)a1 + 1);
      if ( v8 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, struct _CARD_CAPABILITIES *))(v8 + 128))(*((_QWORD *)a1 + 1), a2);
        if ( !v7 )
          v7 = AddCachedCardData((__int64)a1, v13, 0, 0, a2, 0xCu, 0);
      }
      else
      {
        v7 = 87;
        WppTraceIndent(v5, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_ss(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
            v9,
            (__int64)"pCardState->pCardData");
        }
      }
    }
  }
  else if ( v11 == 12 )
  {
    *(_QWORD *)a2 = *v12;
    *((_DWORD *)a2 + 2) = *((_DWORD *)v6 + 2);
  }
  else
  {
    v7 = -2146893820;
  }
  if ( v6 )
    CspFreeH(v6);
  return v7;
}

```

## disassembly

```asm
0x18002c67c  mov     [rsp+arg_10], rbx
0x18002c681  push    rbp
0x18002c682  push    rsi
0x18002c683  push    rdi
0x18002c684  sub     rsp, 270h
0x18002c68b  mov     rax, cs:__security_cookie
0x18002c692  xor     rax, rsp
0x18002c695  mov     [rsp+288h+var_28], rax
0x18002c69d  mov     rsi, rdx
0x18002c6a0  mov     [rsp+288h+var_240], 0
0x18002c6a9  mov     rbp, rcx
0x18002c6ac  mov     [rsp+288h+var_248], 0
0x18002c6b4  mov     edx, 104h; unsigned __int64
0x18002c6b9  lea     rcx, [rsp+288h+var_238]; unsigned __int16 *
0x18002c6be  lea     r9, aCachedCardcapa; "Cached_CardCapabilities"
0x18002c6c5  lea     r8, aS; "%s"
0x18002c6cc  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c6d1  lea     rax, [rsp+288h+var_248]
0x18002c6d6  mov     [rsp+288h+var_258], 0
0x18002c6df  mov     [rsp+288h+var_260], rax
0x18002c6e4  lea     rdx, [rsp+288h+var_238]
0x18002c6e9  lea     rax, [rsp+288h+var_240]
0x18002c6ee  xor     r9d, r9d
0x18002c6f1  xor     r8d, r8d
0x18002c6f4  mov     [rsp+288h+var_268], rax
0x18002c6f9  mov     rcx, rbp
0x18002c6fc  call    GetCachedCardData
0x18002c701  mov     rdi, [rsp+288h+var_240]
0x18002c706  mov     ebx, eax
0x18002c708  test    eax, eax
0x18002c70a  jz      loc_18002C7B7
0x18002c710  cmp     eax, 490h
0x18002c715  jnz     loc_18002C7D3
0x18002c71b  mov     rax, [rbp+8]
0x18002c71f  test    rax, rax
0x18002c722  jnz     short loc_18002C777
0x18002c724  lea     edx, [rax+2]
0x18002c727  lea     ebx, [rax+57h]
0x18002c72a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c72f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c736  lea     rax, WPP_GLOBAL_Control
0x18002c73d  cmp     rcx, rax
0x18002c740  jz      loc_18002C7D3
0x18002c746  test    byte ptr [rcx+1Ch], 1
0x18002c74a  jz      loc_18002C7D3
0x18002c750  cmp     byte ptr [rcx+19h], 2
0x18002c754  jb      short loc_18002C7D3
0x18002c756  mov     rcx, [rcx+10h]
0x18002c75a  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002c761  lea     edx, [rbx-4Dh]
0x18002c764  mov     [rsp+288h+var_268], rax
0x18002c769  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002c770  call    WPP_SF_ss
0x18002c775  jmp     short loc_18002C7D3
0x18002c777  mov     rcx, rax
0x18002c77a  mov     rdx, rsi
0x18002c77d  mov     rax, [rax+80h]
0x18002c784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c789  mov     ebx, eax
0x18002c78b  test    eax, eax
0x18002c78d  jnz     short loc_18002C7D3
0x18002c78f  mov     dword ptr [rsp+288h+var_258], eax
0x18002c793  lea     rdx, [rsp+288h+var_238]
0x18002c798  mov     dword ptr [rsp+288h+var_260], 0Ch
0x18002c7a0  xor     r9d, r9d
0x18002c7a3  xor     r8d, r8d
0x18002c7a6  mov     [rsp+288h+var_268], rsi
0x18002c7ab  mov     rcx, rbp
0x18002c7ae  call    AddCachedCardData
0x18002c7b3  mov     ebx, eax
0x18002c7b5  jmp     short loc_18002C7D3
0x18002c7b7  cmp     [rsp+288h+var_248], 0Ch
0x18002c7bc  jz      short loc_18002C7C5
0x18002c7be  mov     ebx, 80090004h
0x18002c7c3  jmp     short loc_18002C7D3
0x18002c7c5  movsd   xmm0, qword ptr [rdi]
0x18002c7c9  movsd   qword ptr [rsi], xmm0
0x18002c7cd  mov     eax, [rdi+8]
0x18002c7d0  mov     [rsi+8], eax
0x18002c7d3  test    rdi, rdi
0x18002c7d6  jz      short loc_18002C7E0
0x18002c7d8  mov     rcx, rdi
0x18002c7db  call    CspFreeH
0x18002c7e0  mov     eax, ebx
0x18002c7e2  mov     rcx, [rsp+288h+var_28]
0x18002c7ea  xor     rcx, rsp; StackCookie
0x18002c7ed  call    __security_check_cookie
0x18002c7f2  mov     rbx, [rsp+288h+arg_10]
0x18002c7fa  add     rsp, 270h
0x18002c801  pop     rdi
0x18002c802  pop     rsi
0x18002c803  pop     rbp
0x18002c804  retn
```
