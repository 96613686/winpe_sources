# VCardCreateClaim

- ea: `0x1800310d0`
- end: `0x180031262`
- name: `VCardCreateClaim`
- size: `402`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x18002c270`
- `0x18002cb4c`
- `0x18002f090`
- `0x1800310d0`

## string_xrefs

- `0x180031105`: `VCardCreateClaim`

## pseudocode

```c
__int64 __fastcall VCardCreateClaim(__int64 a1, char a2, char a3, char a4, char a5, __int64 a6, __int64 a7)
{
  __int64 v8; // rcx
  unsigned int v9; // ebx
  int v11; // [rsp+38h] [rbp-51h] BYREF
  int v12; // [rsp+3Ch] [rbp-4Dh] BYREF
  _QWORD *v13; // [rsp+40h] [rbp-49h] BYREF
  __int64 v14; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v15[3]; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v16[7]; // [rsp+68h] [rbp-21h] BYREF
  char v17[24]; // [rsp+A0h] [rbp+17h] BYREF
  char v18; // [rsp+E0h] [rbp+57h] BYREF
  char v19; // [rsp+E8h] [rbp+5Fh] BYREF
  char v20; // [rsp+F0h] [rbp+67h] BYREF

  v20 = a4;
  v19 = a3;
  v18 = a2;
  v11 = 0;
  v15[0] = v17;
  v15[1] = &v12;
  v15[2] = &v11;
  v12 = 0;
  strcpy(v17, "VCardCreateClaim");
  lambda_ac7418f7d4b93cf80124ce60ec02f6ac_::operator()(v15);
  v12 = 1;
  v13 = v15;
  if ( a1
    && a6
    && a7
    && (unsigned __int8)(v18 + 0x80) <= 0x20u
    && (unsigned __int8)((v19 & 0xF) - 6) <= 3u
    && (unsigned __int8)(v20 + 0x80) <= 0x20u
    && (unsigned __int8)((a5 & 0xF) - 6) <= 3u )
  {
    v14 = a1;
    v16[0] = &v14;
    v16[1] = &a6;
    v16[2] = &v18;
    v16[3] = &v19;
    v16[4] = &v20;
    v16[5] = &a5;
    v16[6] = &a7;
    v9 = VCardErrorContract__lambda_17690280cf4271506b598890e7390e01_(v16);
    v11 = v9;
  }
  else
  {
    WppTraceIndent(v8, 2u);
    v9 = 87;
    v11 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        112,
        (unsigned int)WPP_19641971e2e2383bda07edbd33517adf_Traceguids,
        (_DWORD)WPP_pszIndent,
        87,
        (__int64)"Invalid parameter");
      v9 = v11;
    }
  }
  WppTraceUnwinder__lambda_ac7418f7d4b93cf80124ce60ec02f6ac____::_WppTraceUnwinder__lambda_ac7418f7d4b93cf80124ce60ec02f6ac____(&v13);
  return v9;
}

```

## disassembly

```asm
0x1800310d0  mov     rax, rsp
0x1800310d3  mov     [rax+8], rbx
0x1800310d7  mov     [rax+20h], r9b
0x1800310db  mov     [rax+18h], r8b
0x1800310df  mov     [rax+10h], dl
0x1800310e2  push    rbp
0x1800310e3  lea     rbp, [rax-47h]
0x1800310e7  sub     rsp, 0C0h
0x1800310ee  mov     rax, cs:__security_cookie
0x1800310f5  xor     rax, rsp
0x1800310f8  mov     [rbp+3Fh+var_10], rax
0x1800310fc  mov     al, byte ptr cs:aVcardcreatecla_0+10h; ""
0x180031102  mov     rbx, rcx
0x180031105  movups  xmm0, xmmword ptr cs:aVcardcreatecla_0; "VCardCreateClaim"
0x18003110c  mov     [rbp+3Fh+var_28+10h], al
0x18003110f  lea     rcx, [rbp+3Fh+var_78]
0x180031113  lea     rax, [rbp+3Fh+var_28]
0x180031117  mov     [rbp+3Fh+var_90], 0
0x18003111e  mov     [rbp+3Fh+var_78], rax
0x180031122  lea     rax, [rbp+3Fh+var_8C]
0x180031126  mov     [rbp+3Fh+var_70], rax
0x18003112a  lea     rax, [rbp+3Fh+var_90]
0x18003112e  mov     [rbp+3Fh+var_68], rax
0x180031132  mov     [rbp+3Fh+var_8C], 0
0x180031139  movups  xmmword ptr [rbp+3Fh+var_28], xmm0
0x18003113d  call    _lambda_ac7418f7d4b93cf80124ce60ec02f6ac___operator__
0x180031142  mov     [rbp+3Fh+var_8C], 1
0x180031149  lea     rax, [rbp+3Fh+var_78]
0x18003114d  mov     [rbp+3Fh+var_88], rax
0x180031151  test    rbx, rbx
0x180031154  jz      loc_1800311DC
0x18003115a  cmp     [rbp+3Fh+arg_28], 0
0x18003115f  jz      short loc_1800311DC
0x180031161  cmp     [rbp+3Fh+arg_30], 0
0x180031166  jz      short loc_1800311DC
0x180031168  mov     al, [rbp+3Fh+arg_8]
0x18003116b  sub     al, 80h
0x18003116d  cmp     al, 20h ; ' '
0x18003116f  ja      short loc_1800311DC
0x180031171  mov     al, [rbp+3Fh+arg_10]
0x180031174  and     al, 0Fh
0x180031176  sub     al, 6
0x180031178  cmp     al, 3
0x18003117a  ja      short loc_1800311DC
0x18003117c  mov     al, [rbp+3Fh+arg_18]
0x18003117f  sub     al, 80h
0x180031181  cmp     al, 20h ; ' '
0x180031183  ja      short loc_1800311DC
0x180031185  mov     al, [rbp+3Fh+arg_20]
0x180031188  and     al, 0Fh
0x18003118a  sub     al, 6
0x18003118c  cmp     al, 3
0x18003118e  ja      short loc_1800311DC
0x180031190  lea     rax, [rbp+3Fh+var_80]
0x180031194  mov     [rbp+3Fh+var_80], rbx
0x180031198  mov     [rbp+3Fh+var_60], rax
0x18003119c  lea     rcx, [rbp+3Fh+var_60]
0x1800311a0  lea     rax, [rbp+3Fh+arg_28]
0x1800311a4  mov     [rbp+3Fh+var_58], rax
0x1800311a8  lea     rax, [rbp+3Fh+arg_8]
0x1800311ac  mov     [rbp+3Fh+var_50], rax
0x1800311b0  lea     rax, [rbp+3Fh+arg_10]
0x1800311b4  mov     [rbp+3Fh+var_48], rax
0x1800311b8  lea     rax, [rbp+3Fh+arg_18]
0x1800311bc  mov     [rbp+3Fh+var_40], rax
0x1800311c0  lea     rax, [rbp+3Fh+arg_20]
0x1800311c4  mov     [rbp+3Fh+var_38], rax
0x1800311c8  lea     rax, [rbp+3Fh+arg_30]
0x1800311cc  mov     [rbp+3Fh+var_30], rax
0x1800311d0  call    VCardErrorContract__lambda_17690280cf4271506b598890e7390e01___; VCardErrorContract__lambda_17690280cf4271506b598890e7390e01_
0x1800311d5  mov     ebx, eax
0x1800311d7  mov     [rbp+3Fh+var_90], eax
0x1800311da  jmp     short loc_18003123A
0x1800311dc  mov     edx, 2
0x1800311e1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800311e6  mov     ebx, 57h ; 'W'
0x1800311eb  mov     [rbp+3Fh+var_90], ebx
0x1800311ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800311f5  lea     rax, WPP_GLOBAL_Control
0x1800311fc  cmp     rcx, rax
0x1800311ff  jz      short loc_18003123A
0x180031201  test    byte ptr [rcx+1Ch], 1
0x180031205  jz      short loc_18003123A
0x180031207  cmp     byte ptr [rcx+19h], 2
0x18003120b  jb      short loc_18003123A
0x18003120d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180031214  lea     rax, aInvalidParamet; "Invalid parameter"
0x18003121b  mov     rcx, [rcx+10h]
0x18003121f  lea     edx, [rbx+19h]
0x180031222  mov     [rsp+28h], rax
0x180031227  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x18003122e  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180031232  call    WPP_SF_sDs
0x180031237  mov     ebx, [rbp+3Fh+var_90]
0x18003123a  lea     rcx, [rbp+3Fh+var_88]
0x18003123e  call    WppTraceUnwinder__lambda_ac7418f7d4b93cf80124ce60ec02f6ac_______WppTraceUnwinder__lambda_ac7418f7d4b93cf80124ce60ec02f6ac____
0x180031243  mov     eax, ebx
0x180031245  mov     rcx, [rbp+3Fh+var_10]
0x180031249  xor     rcx, rsp; StackCookie
0x18003124c  call    __security_check_cookie
0x180031251  mov     rbx, [rsp+0C0h+arg_0]
0x180031259  add     rsp, 0C0h
0x180031260  pop     rbp
0x180031261  retn
```
