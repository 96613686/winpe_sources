# I_CspQueryKeySizes(_CARD_STATE *,ulong,ulong,_CARD_KEY_SIZES *)

- ea: `0x18002c99c`
- end: `0x18002cb2e`
- name: `?I_CspQueryKeySizes@@YAKPEAU_CARD_STATE@@KKPEAU_CARD_KEY_SIZES@@@Z`
- size: `402`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, unsigned int, unsigned int, struct _CARD_KEY_SIZES *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002dd50`

## callees

- `0x18000d9d0`
- `0x180011fd8`
- `0x18002c99c`
- `0x18002cda8`
- `0x18002eb6c`
- `0x18002fb68`
- `0x180030378`
- `0x18003c240`
- `0x18003d010`

## string_xrefs

- `0x18002c9da`: `Cached_KeySizes`

## pseudocode

```c
__int64 __fastcall I_CspQueryKeySizes(struct _CARD_STATE *a1, unsigned int a2, __int64 a3, struct _CARD_KEY_SIZES *a4)
{
  unsigned int CachedCardData; // eax
  __int64 v8; // rcx
  _OWORD *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // rax
  int v12; // r9d
  int v14; // [rsp+40h] [rbp-258h] BYREF
  _OWORD *v15; // [rsp+48h] [rbp-250h] BYREF
  unsigned __int16 v16[264]; // [rsp+50h] [rbp-248h] BYREF

  v15 = 0;
  v14 = 0;
  StringCbPrintfW(v16, 0x104u, L"%s\\%d", L"Cached_KeySizes", a2);
  CachedCardData = GetCachedCardData((__int64)a1, v16, 0, 0, &v15, &v14, 0);
  v9 = v15;
  v10 = CachedCardData;
  if ( CachedCardData )
  {
    if ( CachedCardData == 1168 )
    {
      v11 = *((_QWORD *)a1 + 1);
      if ( v11 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct _CARD_KEY_SIZES *))(v11 + 296))(
                *((_QWORD *)a1 + 1),
                a2,
                0,
                a4);
        if ( !v10 )
          v10 = AddCachedCardData((__int64)a1, v16, 0, 0, a4, 0x14u, 0);
      }
      else
      {
        v10 = 87;
        WppTraceIndent(v8, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_ss(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
            v12,
            (__int64)"pCardState->pCardData");
        }
      }
    }
  }
  else if ( v14 == 20 )
  {
    *(_OWORD *)a4 = *v15;
    *((_DWORD *)a4 + 4) = *((_DWORD *)v9 + 4);
  }
  else
  {
    v10 = -2146893820;
  }
  if ( v9 )
    CspFreeH(v9);
  return v10;
}

```

## disassembly

```asm
0x18002c99c  push    rbx
0x18002c99e  push    rbp
0x18002c99f  push    rsi
0x18002c9a0  push    rdi
0x18002c9a1  push    r14
0x18002c9a3  sub     rsp, 270h
0x18002c9aa  mov     rax, cs:__security_cookie
0x18002c9b1  xor     rax, rsp
0x18002c9b4  mov     [rsp+298h+var_38], rax
0x18002c9bc  mov     rsi, r9
0x18002c9bf  mov     dword ptr [rsp+298h+var_278], edx
0x18002c9c3  mov     r14d, edx
0x18002c9c6  mov     [rsp+298h+var_250], 0
0x18002c9cf  mov     rbp, rcx
0x18002c9d2  mov     [rsp+298h+var_258], 0
0x18002c9da  lea     r9, aCachedKeysizes; "Cached_KeySizes"
0x18002c9e1  mov     edx, 104h; unsigned __int64
0x18002c9e6  lea     rcx, [rsp+298h+var_248]; unsigned __int16 *
0x18002c9eb  lea     r8, aSD; "%s\\%d"
0x18002c9f2  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c9f7  lea     rax, [rsp+298h+var_258]
0x18002c9fc  mov     [rsp+298h+var_268], 0
0x18002ca05  mov     [rsp+298h+var_270], rax
0x18002ca0a  lea     rdx, [rsp+298h+var_248]
0x18002ca0f  lea     rax, [rsp+298h+var_250]
0x18002ca14  xor     r9d, r9d
0x18002ca17  xor     r8d, r8d
0x18002ca1a  mov     [rsp+298h+var_278], rax
0x18002ca1f  mov     rcx, rbp
0x18002ca22  call    GetCachedCardData
0x18002ca27  mov     rdi, [rsp+298h+var_250]
0x18002ca2c  mov     ebx, eax
0x18002ca2e  test    eax, eax
0x18002ca30  jz      loc_18002CAE7
0x18002ca36  cmp     eax, 490h
0x18002ca3b  jnz     loc_18002CB01
0x18002ca41  mov     rax, [rbp+8]
0x18002ca45  test    rax, rax
0x18002ca48  jnz     short loc_18002CAA1
0x18002ca4a  lea     edx, [rax+2]
0x18002ca4d  lea     ebx, [rax+57h]
0x18002ca50  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002ca55  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca5c  lea     rax, WPP_GLOBAL_Control
0x18002ca63  cmp     rcx, rax
0x18002ca66  jz      loc_18002CB01
0x18002ca6c  test    byte ptr [rcx+1Ch], 1
0x18002ca70  jz      loc_18002CB01
0x18002ca76  cmp     byte ptr [rcx+19h], 2
0x18002ca7a  jb      loc_18002CB01
0x18002ca80  mov     rcx, [rcx+10h]
0x18002ca84  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002ca8b  lea     edx, [rbx-36h]
0x18002ca8e  mov     [rsp+298h+var_278], rax
0x18002ca93  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002ca9a  call    WPP_SF_ss
0x18002ca9f  jmp     short loc_18002CB01
0x18002caa1  mov     rcx, rax
0x18002caa4  mov     r9, rsi
0x18002caa7  mov     rax, [rax+128h]
0x18002caae  xor     r8d, r8d
0x18002cab1  mov     edx, r14d
0x18002cab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cab9  mov     ebx, eax
0x18002cabb  test    eax, eax
0x18002cabd  jnz     short loc_18002CB01
0x18002cabf  mov     dword ptr [rsp+298h+var_268], eax
0x18002cac3  lea     rdx, [rsp+298h+var_248]
0x18002cac8  mov     dword ptr [rsp+298h+var_270], 14h
0x18002cad0  xor     r9d, r9d
0x18002cad3  xor     r8d, r8d
0x18002cad6  mov     [rsp+298h+var_278], rsi
0x18002cadb  mov     rcx, rbp
0x18002cade  call    AddCachedCardData
0x18002cae3  mov     ebx, eax
0x18002cae5  jmp     short loc_18002CB01
0x18002cae7  cmp     [rsp+298h+var_258], 14h
0x18002caec  jz      short loc_18002CAF5
0x18002caee  mov     ebx, 80090004h
0x18002caf3  jmp     short loc_18002CB01
0x18002caf5  movups  xmm0, xmmword ptr [rdi]
0x18002caf8  movups  xmmword ptr [rsi], xmm0
0x18002cafb  mov     eax, [rdi+10h]
0x18002cafe  mov     [rsi+10h], eax
0x18002cb01  test    rdi, rdi
0x18002cb04  jz      short loc_18002CB0E
0x18002cb06  mov     rcx, rdi
0x18002cb09  call    CspFreeH
0x18002cb0e  mov     eax, ebx
0x18002cb10  mov     rcx, [rsp+298h+var_38]
0x18002cb18  xor     rcx, rsp; StackCookie
0x18002cb1b  call    __security_check_cookie
0x18002cb20  add     rsp, 270h
0x18002cb27  pop     r14
0x18002cb29  pop     rdi
0x18002cb2a  pop     rsi
0x18002cb2b  pop     rbp
0x18002cb2c  pop     rbx
0x18002cb2d  retn
```
