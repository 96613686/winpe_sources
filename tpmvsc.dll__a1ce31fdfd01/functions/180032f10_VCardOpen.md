# VCardOpen

- ea: `0x180032f10`
- end: `0x18003309f`
- name: `VCardOpen`
- size: `399`
- prototype: `__int64 __fastcall(struct VCARD_DATA *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x1800295a4`
- `0x18002c604`
- `0x18002c954`
- `0x18002dd24`
- `0x180032f10`

## string_xrefs

- `0x180032f3f`: `VCardOpen`
- `0x180032ff0`: `Card has already been loaded`

## pseudocode

```c
__int64 __fastcall VCardOpen(struct VCARD_DATA *a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  int v7; // edx
  const char *v8; // rax
  int v10; // [rsp+30h] [rbp-9h] BYREF
  int v11; // [rsp+34h] [rbp-5h] BYREF
  _QWORD *v12; // [rsp+38h] [rbp-1h] BYREF
  struct VCARD_DATA *v13; // [rsp+40h] [rbp+7h] BYREF
  _QWORD v14[3]; // [rsp+48h] [rbp+Fh] BYREF
  _QWORD v15[2]; // [rsp+60h] [rbp+27h] BYREF
  char v16[16]; // [rsp+70h] [rbp+37h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+6Fh] BYREF

  v17 = a2;
  v14[0] = v16;
  v14[1] = &v11;
  v14[2] = &v10;
  v10 = 0;
  v11 = 0;
  strcpy(v16, "VCardOpen");
  lambda_36430d8ad368df6148122c27ce3d98b2_::operator()(v14);
  v11 = 1;
  v12 = v14;
  if ( a1 && v17 )
  {
    v13 = a1;
    if ( (unsigned int)I_VCardIsLoaded(a1) )
    {
      WppTraceIndent(v4, 2u);
      v5 = 1609;
      v10 = 1609;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 19;
        v8 = "Card has already been loaded";
LABEL_13:
        WPP_SF_sDs(
          v6[2],
          v7,
          (unsigned int)WPP_19641971e2e2383bda07edbd33517adf_Traceguids,
          (_DWORD)WPP_pszIndent,
          v5,
          (__int64)v8);
        v5 = v10;
      }
    }
    else
    {
      v15[0] = &v13;
      v15[1] = &v17;
      v5 = VCardErrorContract__lambda_96886d0da464eb5d5263a4c467f3732a_(v15);
      v10 = v5;
    }
  }
  else
  {
    WppTraceIndent(v3, 2u);
    v5 = 87;
    v10 = 87;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 18;
      v8 = "Invalid NULL parameter";
      goto LABEL_13;
    }
  }
  WppTraceUnwinder__lambda_36430d8ad368df6148122c27ce3d98b2____::_WppTraceUnwinder__lambda_36430d8ad368df6148122c27ce3d98b2____(&v12);
  return v5;
}

```

## disassembly

```asm
0x180032f10  mov     [rsp-8+arg_0], rbx
0x180032f15  mov     [rsp-8+arg_8], rdx
0x180032f1a  push    rbp
0x180032f1b  lea     rbp, [rsp-57h]
0x180032f20  sub     rsp, 90h
0x180032f27  mov     rax, cs:__security_cookie
0x180032f2e  xor     rax, rsp
0x180032f31  mov     [rbp+57h+var_10], rax
0x180032f35  movzx   eax, word ptr cs:aVcardopen_0+8; "n"
0x180032f3c  mov     rbx, rcx
0x180032f3f  movsd   xmm0, qword ptr cs:aVcardopen_0; "VCardOpen"
0x180032f47  lea     rcx, [rbp+57h+var_48]
0x180032f4b  mov     word ptr [rbp+57h+var_20+8], ax
0x180032f4f  lea     rax, [rbp+57h+var_20]
0x180032f53  mov     [rbp+57h+var_48], rax
0x180032f57  lea     rax, [rbp+57h+var_5C]
0x180032f5b  mov     [rbp+57h+var_40], rax
0x180032f5f  lea     rax, [rbp+57h+var_60]
0x180032f63  mov     [rbp+57h+var_38], rax
0x180032f67  mov     [rbp+57h+var_60], 0
0x180032f6e  mov     [rbp+57h+var_5C], 0
0x180032f75  movsd   qword ptr [rbp+57h+var_20], xmm0
0x180032f7a  call    _lambda_36430d8ad368df6148122c27ce3d98b2___operator__
0x180032f7f  mov     [rbp+57h+var_5C], 1
0x180032f86  lea     rax, [rbp+57h+var_48]
0x180032f8a  mov     [rbp+57h+var_58], rax
0x180032f8e  test    rbx, rbx
0x180032f91  jz      loc_180033019
0x180032f97  cmp     [rbp+57h+arg_8], 0
0x180032f9c  jz      short loc_180033019
0x180032f9e  mov     rcx, rbx; struct VCARD_DATA *
0x180032fa1  mov     [rbp+57h+var_50], rbx
0x180032fa5  call    ?I_VCardIsLoaded@@YAHPEBUVCARD_DATA@@@Z; I_VCardIsLoaded(VCARD_DATA const *)
0x180032faa  test    eax, eax
0x180032fac  jz      short loc_180032FF9
0x180032fae  mov     edx, 2
0x180032fb3  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180032fb8  mov     ebx, 649h
0x180032fbd  mov     [rbp+57h+var_60], ebx
0x180032fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180032fc7  lea     rax, WPP_GLOBAL_Control
0x180032fce  cmp     rcx, rax
0x180032fd1  jz      loc_180033077
0x180032fd7  test    byte ptr [rcx+1Ch], 1
0x180032fdb  jz      loc_180033077
0x180032fe1  cmp     byte ptr [rcx+19h], 2
0x180032fe5  jb      loc_180033077
0x180032feb  mov     edx, 13h
0x180032ff0  lea     rax, aCardHasAlready; "Card has already been loaded"
0x180032ff7  jmp     short loc_180033054
0x180032ff9  lea     rax, [rbp+57h+var_50]
0x180032ffd  mov     [rbp+57h+var_30], rax
0x180033001  lea     rcx, [rbp+57h+var_30]
0x180033005  lea     rax, [rbp+57h+arg_8]
0x180033009  mov     [rbp+57h+var_28], rax
0x18003300d  call    VCardErrorContract__lambda_96886d0da464eb5d5263a4c467f3732a___; VCardErrorContract__lambda_96886d0da464eb5d5263a4c467f3732a_
0x180033012  mov     ebx, eax
0x180033014  mov     [rbp+57h+var_60], eax
0x180033017  jmp     short loc_180033077
0x180033019  mov     edx, 2
0x18003301e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180033023  mov     ebx, 57h ; 'W'
0x180033028  mov     [rbp+57h+var_60], ebx
0x18003302b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033032  lea     rax, WPP_GLOBAL_Control
0x180033039  cmp     rcx, rax
0x18003303c  jz      short loc_180033077
0x18003303e  test    byte ptr [rcx+1Ch], 1
0x180033042  jz      short loc_180033077
0x180033044  cmp     byte ptr [rcx+19h], 2
0x180033048  jb      short loc_180033077
0x18003304a  lea     edx, [rbx-45h]
0x18003304d  lea     rax, aInvalidNullPar; "Invalid NULL parameter"
0x180033054  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003305b  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x180033062  mov     rcx, [rcx+10h]
0x180033066  mov     [rsp+90h+var_68], rax
0x18003306b  mov     [rsp+90h+var_70], ebx
0x18003306f  call    WPP_SF_sDs
0x180033074  mov     ebx, [rbp+57h+var_60]
0x180033077  lea     rcx, [rbp+57h+var_58]
0x18003307b  call    WppTraceUnwinder__lambda_36430d8ad368df6148122c27ce3d98b2_______WppTraceUnwinder__lambda_36430d8ad368df6148122c27ce3d98b2____
0x180033080  mov     eax, ebx
0x180033082  mov     rcx, [rbp+57h+var_10]
0x180033086  xor     rcx, rsp; StackCookie
0x180033089  call    __security_check_cookie
0x18003308e  mov     rbx, [rsp+90h+arg_0]
0x180033096  add     rsp, 90h
0x18003309d  pop     rbp
0x18003309e  retn
```
