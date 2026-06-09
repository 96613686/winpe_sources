# VCardCreateKey

- ea: `0x180031270`
- end: `0x1800314e4`
- name: `VCardCreateKey`
- size: `628`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x18001a2f8`
- `0x18002c378`
- `0x18002cac0`
- `0x18002e8a8`
- `0x180031270`

## string_xrefs

- `0x1800312a5`: `VCardCreateKey`

## pseudocode

```c
__int64 __fastcall VCardCreateKey(__int64 a1, char a2, unsigned __int8 a3, char a4)
{
  __int64 v5; // rcx
  char v6; // dl
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  int v9; // edx
  const char *v10; // rax
  int v12; // [rsp+38h] [rbp-19h] BYREF
  int v13; // [rsp+3Ch] [rbp-15h] BYREF
  _QWORD *v14; // [rsp+40h] [rbp-11h] BYREF
  __int64 v15; // [rsp+48h] [rbp-9h] BYREF
  _QWORD v16[3]; // [rsp+50h] [rbp-1h] BYREF
  _QWORD v17[4]; // [rsp+68h] [rbp+17h] BYREF
  char v18[16]; // [rsp+88h] [rbp+37h] BYREF
  char v19; // [rsp+C0h] [rbp+6Fh] BYREF
  unsigned __int8 v20; // [rsp+C8h] [rbp+77h] BYREF
  char v21; // [rsp+D0h] [rbp+7Fh] BYREF

  v21 = a4;
  v20 = a3;
  v19 = a2;
  v16[0] = v18;
  v16[1] = &v13;
  v16[2] = &v12;
  v12 = 0;
  v13 = 0;
  strcpy(v18, "VCardCreateKey");
  lambda_932c6d37aefe48ce5f2eba2f6189556a_::operator()(v16);
  v13 = 1;
  v14 = v16;
  if ( a1 && (unsigned __int8)(v19 + 0x80) <= 0x20u && I_IsAsymAlg(v20) )
  {
    if ( (unsigned __int8)((v6 & 0xF) - 12) > 2u )
    {
      if ( (v21 & 1) != 0 )
      {
        WppTraceIndent(v5, 2u);
        v7 = -2146435038;
        v12 = -2146435038;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 60;
          v10 = "Using an asymmetric key for authentication is not supported";
          goto LABEL_24;
        }
      }
      else if ( (v21 & 6) != 0 )
      {
        v15 = a1;
        v17[0] = &v15;
        v17[1] = &v19;
        v17[2] = &v20;
        v17[3] = &v21;
        v7 = VCardErrorContract__lambda_29a933c783bff5720d487fb08642d072_(v17);
        v12 = v7;
      }
      else
      {
        WppTraceIndent(v5, 2u);
        v7 = 87;
        v12 = 87;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 61;
          v10 = "The key has no CRTs";
          goto LABEL_24;
        }
      }
    }
    else
    {
      WppTraceIndent(v5, 2u);
      v7 = -2146435038;
      v12 = -2146435038;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 59;
        v10 = "ECC algorithms are not supported";
LABEL_24:
        WPP_SF_sDs(
          v8[2],
          v9,
          (unsigned int)WPP_19641971e2e2383bda07edbd33517adf_Traceguids,
          (_DWORD)WPP_pszIndent,
          v7,
          (__int64)v10);
        v7 = v12;
      }
    }
  }
  else
  {
    WppTraceIndent(v5, 2u);
    v7 = 87;
    v12 = 87;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 58;
      v10 = "Invalid parameter";
      goto LABEL_24;
    }
  }
  WppTraceUnwinder__lambda_932c6d37aefe48ce5f2eba2f6189556a____::_WppTraceUnwinder__lambda_932c6d37aefe48ce5f2eba2f6189556a____(&v14);
  return v7;
}

```

## disassembly

```asm
0x180031270  mov     rax, rsp
0x180031273  mov     [rax+8], rbx
0x180031277  mov     [rax+20h], r9b
0x18003127b  mov     [rax+18h], r8b
0x18003127f  mov     [rax+10h], dl
0x180031282  push    rbp
0x180031283  lea     rbp, [rax-5Fh]
0x180031287  sub     rsp, 0A0h
0x18003128e  mov     rax, cs:__security_cookie
0x180031295  xor     rax, rsp
0x180031298  mov     [rbp+57h+var_10], rax
0x18003129c  mov     eax, dword ptr cs:aVcardcreatekey_0+8; "ateKey"
0x1800312a2  mov     rbx, rcx
0x1800312a5  movsd   xmm0, qword ptr cs:aVcardcreatekey_0; "VCardCreateKey"
0x1800312ad  lea     rcx, [rbp+57h+var_58]
0x1800312b1  mov     dword ptr [rbp+57h+var_20+8], eax
0x1800312b4  movzx   eax, word ptr cs:aVcardcreatekey_0+0Ch; "ey"
0x1800312bb  mov     word ptr [rbp+57h+var_20+0Ch], ax
0x1800312bf  mov     al, byte ptr cs:aVcardcreatekey_0+0Eh; ""
0x1800312c5  mov     [rbp+57h+var_20+0Eh], al
0x1800312c8  lea     rax, [rbp+57h+var_20]
0x1800312cc  mov     [rbp+57h+var_58], rax
0x1800312d0  lea     rax, [rbp+57h+var_6C]
0x1800312d4  mov     [rbp+57h+var_50], rax
0x1800312d8  lea     rax, [rbp+57h+var_70]
0x1800312dc  mov     [rbp+57h+var_48], rax
0x1800312e0  mov     [rbp+57h+var_70], 0
0x1800312e7  mov     [rbp+57h+var_6C], 0
0x1800312ee  movsd   qword ptr [rbp+57h+var_20], xmm0
0x1800312f3  call    _lambda_932c6d37aefe48ce5f2eba2f6189556a___operator__
0x1800312f8  mov     [rbp+57h+var_6C], 1
0x1800312ff  lea     rax, [rbp+57h+var_58]
0x180031303  mov     [rbp+57h+var_68], rax
0x180031307  test    rbx, rbx
0x18003130a  jz      loc_18003145E
0x180031310  mov     al, [rbp+57h+arg_8]
0x180031313  sub     al, 80h
0x180031315  cmp     al, 20h ; ' '
0x180031317  ja      loc_18003145E
0x18003131d  mov     dl, [rbp+57h+arg_10]
0x180031320  mov     cl, dl; unsigned __int8
0x180031322  call    ?I_IsAsymAlg@@YAHE@Z; I_IsAsymAlg(uchar)
0x180031327  test    eax, eax
0x180031329  jz      loc_18003145E
0x18003132f  and     dl, 0Fh
0x180031332  sub     dl, 0Ch
0x180031335  cmp     dl, 2
0x180031338  ja      short loc_180031388
0x18003133a  mov     edx, 2
0x18003133f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180031344  mov     ebx, 80100022h
0x180031349  mov     [rbp+57h+var_70], ebx
0x18003134c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031353  lea     rax, WPP_GLOBAL_Control
0x18003135a  cmp     rcx, rax
0x18003135d  jz      loc_1800314BC
0x180031363  test    byte ptr [rcx+1Ch], 1
0x180031367  jz      loc_1800314BC
0x18003136d  cmp     byte ptr [rcx+19h], 2
0x180031371  jb      loc_1800314BC
0x180031377  mov     edx, 3Bh ; ';'
0x18003137c  lea     rax, aEccAlgorithmsA; "ECC algorithms are not supported"
0x180031383  jmp     loc_180031499
0x180031388  mov     al, [rbp+57h+arg_18]
0x18003138b  test    al, 1
0x18003138d  jz      short loc_1800313DD
0x18003138f  mov     edx, 2
0x180031394  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180031399  mov     ebx, 80100022h
0x18003139e  mov     [rbp+57h+var_70], ebx
0x1800313a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800313a8  lea     rax, WPP_GLOBAL_Control
0x1800313af  cmp     rcx, rax
0x1800313b2  jz      loc_1800314BC
0x1800313b8  test    byte ptr [rcx+1Ch], 1
0x1800313bc  jz      loc_1800314BC
0x1800313c2  cmp     byte ptr [rcx+19h], 2
0x1800313c6  jb      loc_1800314BC
0x1800313cc  mov     edx, 3Ch ; '<'
0x1800313d1  lea     rax, aUsingAnAsymmet; "Using an asymmetric key for authenticat"...
0x1800313d8  jmp     loc_180031499
0x1800313dd  test    al, 6
0x1800313df  jnz     short loc_18003142A
0x1800313e1  mov     edx, 2
0x1800313e6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800313eb  mov     ebx, 57h ; 'W'
0x1800313f0  mov     [rbp+57h+var_70], ebx
0x1800313f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800313fa  lea     rax, WPP_GLOBAL_Control
0x180031401  cmp     rcx, rax
0x180031404  jz      loc_1800314BC
0x18003140a  test    byte ptr [rcx+1Ch], 1
0x18003140e  jz      loc_1800314BC
0x180031414  cmp     byte ptr [rcx+19h], 2
0x180031418  jb      loc_1800314BC
0x18003141e  lea     edx, [rbx-1Ah]
0x180031421  lea     rax, aTheKeyHasNoCrt_0; "The key has no CRTs"
0x180031428  jmp     short loc_180031499
0x18003142a  lea     rax, [rbp+57h+var_60]
0x18003142e  mov     [rbp+57h+var_60], rbx
0x180031432  mov     [rbp+57h+var_40], rax
0x180031436  lea     rcx, [rbp+57h+var_40]
0x18003143a  lea     rax, [rbp+57h+arg_8]
0x18003143e  mov     [rbp+57h+var_38], rax
0x180031442  lea     rax, [rbp+57h+arg_10]
0x180031446  mov     [rbp+57h+var_30], rax
0x18003144a  lea     rax, [rbp+57h+arg_18]
0x18003144e  mov     [rbp+57h+var_28], rax
0x180031452  call    VCardErrorContract__lambda_29a933c783bff5720d487fb08642d072___; VCardErrorContract__lambda_29a933c783bff5720d487fb08642d072_
0x180031457  mov     ebx, eax
0x180031459  mov     [rbp+57h+var_70], eax
0x18003145c  jmp     short loc_1800314BC
0x18003145e  mov     edx, 2
0x180031463  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180031468  mov     ebx, 57h ; 'W'
0x18003146d  mov     [rbp+57h+var_70], ebx
0x180031470  mov     rcx, cs:WPP_GLOBAL_Control
0x180031477  lea     rax, WPP_GLOBAL_Control
0x18003147e  cmp     rcx, rax
0x180031481  jz      short loc_1800314BC
0x180031483  test    byte ptr [rcx+1Ch], 1
0x180031487  jz      short loc_1800314BC
0x180031489  cmp     byte ptr [rcx+19h], 2
0x18003148d  jb      short loc_1800314BC
0x18003148f  lea     edx, [rbx-1Dh]
0x180031492  lea     rax, aInvalidParamet; "Invalid parameter"
0x180031499  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800314a0  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x1800314a7  mov     rcx, [rcx+10h]
0x1800314ab  mov     [rsp+28h], rax
0x1800314b0  mov     dword ptr [rsp+0A0h+var_80], ebx
0x1800314b4  call    WPP_SF_sDs
0x1800314b9  mov     ebx, [rbp+57h+var_70]
0x1800314bc  lea     rcx, [rbp+57h+var_68]
0x1800314c0  call    WppTraceUnwinder__lambda_932c6d37aefe48ce5f2eba2f6189556a_______WppTraceUnwinder__lambda_932c6d37aefe48ce5f2eba2f6189556a____
0x1800314c5  mov     eax, ebx
0x1800314c7  mov     rcx, [rbp+57h+var_10]
0x1800314cb  xor     rcx, rsp; StackCookie
0x1800314ce  call    __security_check_cookie
0x1800314d3  mov     rbx, [rsp+0A0h+arg_0]
0x1800314db  add     rsp, 0A0h
0x1800314e2  pop     rbp
0x1800314e3  retn
```
