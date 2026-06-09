# TpmVCardCreateInProc

- ea: `0x1800305d0`
- end: `0x18003081d`
- name: `TpmVCardCreateInProc`
- size: `589`
- prototype: `__int64 __usercall@<rax>(struct VCARD_DATA *@<rcx>, __int64, __int64, __int64, __int64, __int64, char)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x1800295a4`
- `0x18002c290`
- `0x18002c98c`
- `0x18002de04`
- `0x1800305d0`

## string_xrefs

- `0x1800305fd`: `TpmVCardCreateInProc`

## pseudocode

```c
__int64 __fastcall TpmVCardCreateInProc(
        struct VCARD_DATA *a1,
        __int64 a2,
        char a3,
        char a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        char a10)
{
  __int64 v11; // rcx
  __int64 v12; // rcx
  _QWORD *v13; // rcx
  unsigned int v14; // ebx
  int v15; // edx
  const char *v16; // r8
  int v17; // eax
  int v19; // [rsp+38h] [rbp-69h] BYREF
  unsigned int v20; // [rsp+3Ch] [rbp-65h] BYREF
  _QWORD *v21; // [rsp+40h] [rbp-61h] BYREF
  _QWORD v22[3]; // [rsp+48h] [rbp-59h] BYREF
  _QWORD v23[9]; // [rsp+60h] [rbp-41h] BYREF
  char v24[24]; // [rsp+A8h] [rbp+7h] BYREF
  __int64 v25; // [rsp+E0h] [rbp+3Fh] BYREF
  char v26; // [rsp+E8h] [rbp+47h] BYREF
  char v27; // [rsp+F0h] [rbp+4Fh] BYREF

  v27 = a4;
  v26 = a3;
  v25 = a2;
  v22[0] = v24;
  v22[1] = &v19;
  strcpy(v24, "TpmVCardCreateInProc");
  v22[2] = &v20;
  v20 = 0;
  v19 = 0;
  lambda_45d82e41e36390cc040c986d1d86a018_::operator()(v22);
  v19 = 1;
  v21 = v22;
  if ( a1
    && v25
    && a5
    && *(_DWORD *)(a5 + 12)
    && (!a6 || *(_DWORD *)(a6 + 12) == 3)
    && (!a7 || *(_DWORD *)(a7 + 12))
    && a8
    && (!a9 || *(_DWORD *)(a9 + 12))
    && (unsigned __int8)(v26 + 0x80) <= 0x20u
    && (unsigned __int8)((v27 & 0xF) - 2) <= 3u )
  {
    if ( (unsigned int)I_VCardIsLoaded(a1) )
    {
      WppTraceIndent(v12, 2u);
      v13 = WPP_GLOBAL_Control;
      v14 = 1609;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 132;
        v16 = "Cannot operate on loaded card";
LABEL_26:
        WPP_SF_sDs(
          v13[2],
          v15,
          (unsigned int)WPP_19641971e2e2383bda07edbd33517adf_Traceguids,
          (_DWORD)WPP_pszIndent,
          v14,
          (__int64)v16);
      }
    }
    else
    {
      v23[0] = &v25;
      v23[1] = &v26;
      v23[2] = &v27;
      v23[3] = &a5;
      v23[4] = &a6;
      v23[5] = &a7;
      v23[6] = &a8;
      v23[7] = &a9;
      v23[8] = &a10;
      v17 = VCardErrorContract__lambda_1a445b3d6b6285831f5cc9af91362f3f_(v23);
      v14 = v17;
      if ( v17 > 0 )
        v14 = (unsigned __int16)v17 | 0x80070000;
      v20 = v14;
    }
  }
  else
  {
    WppTraceIndent(v11, 2u);
    v13 = WPP_GLOBAL_Control;
    v14 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 131;
      v16 = "Invalid parameter";
      goto LABEL_26;
    }
  }
  WppTraceUnwinder__lambda_45d82e41e36390cc040c986d1d86a018____::_WppTraceUnwinder__lambda_45d82e41e36390cc040c986d1d86a018____(&v21);
  return v14;
}

```

## disassembly

```asm
0x1800305d0  mov     rax, rsp
0x1800305d3  mov     [rax+8], rbx
0x1800305d7  mov     [rax+20h], r9b
0x1800305db  mov     [rax+18h], r8b
0x1800305df  mov     [rax+10h], rdx
0x1800305e3  push    rbp
0x1800305e4  lea     rbp, [rax-2Fh]
0x1800305e8  sub     rsp, 0C0h
0x1800305ef  mov     rax, cs:__security_cookie
0x1800305f6  xor     rax, rsp
0x1800305f9  mov     [rbp+27h+var_8], rax
0x1800305fd  movups  xmm0, xmmword ptr cs:aTpmvcardcreate_2; "TpmVCardCreateInProc"
0x180030604  lea     rax, [rbp+27h+var_20]
0x180030608  mov     rbx, rcx
0x18003060b  movsd   xmm1, qword ptr cs:aTpmvcardcreate_2+0Dh; "eInProc"
0x180030613  lea     rcx, [rbp+27h+var_80]
0x180030617  mov     [rbp+27h+var_80], rax
0x18003061b  lea     rax, [rbp+27h+var_90]
0x18003061f  mov     [rbp+27h+var_78], rax
0x180030623  lea     rax, [rbp+27h+var_8C]
0x180030627  movups  xmmword ptr [rbp+27h+var_20], xmm0
0x18003062b  mov     [rbp+27h+var_70], rax
0x18003062f  mov     [rbp+27h+var_8C], 0
0x180030636  mov     [rbp+27h+var_90], 0
0x18003063d  movsd   qword ptr [rbp+27h+var_20+0Dh], xmm1
0x180030642  call    _lambda_45d82e41e36390cc040c986d1d86a018___operator__
0x180030647  mov     [rbp+27h+var_90], 1
0x18003064e  lea     rax, [rbp+27h+var_80]
0x180030652  mov     [rbp+27h+var_88], rax
0x180030656  test    rbx, rbx
0x180030659  jz      loc_18003079D
0x18003065f  cmp     [rbp+27h+arg_8], 0
0x180030664  jz      loc_18003079D
0x18003066a  mov     rax, [rbp+27h+arg_20]
0x18003066e  test    rax, rax
0x180030671  jz      loc_18003079D
0x180030677  cmp     dword ptr [rax+0Ch], 0
0x18003067b  jz      loc_18003079D
0x180030681  mov     rax, [rbp+27h+arg_28]
0x180030685  test    rax, rax
0x180030688  jz      short loc_180030694
0x18003068a  cmp     dword ptr [rax+0Ch], 3
0x18003068e  jnz     loc_18003079D
0x180030694  mov     rax, [rbp+27h+arg_30]
0x180030698  test    rax, rax
0x18003069b  jz      short loc_1800306A7
0x18003069d  cmp     dword ptr [rax+0Ch], 0
0x1800306a1  jz      loc_18003079D
0x1800306a7  cmp     [rbp+27h+arg_38], 0
0x1800306ac  jz      loc_18003079D
0x1800306b2  mov     rax, [rbp+27h+arg_40]
0x1800306b6  test    rax, rax
0x1800306b9  jz      short loc_1800306C5
0x1800306bb  cmp     dword ptr [rax+0Ch], 0
0x1800306bf  jz      loc_18003079D
0x1800306c5  mov     al, [rbp+27h+arg_10]
0x1800306c8  sub     al, 80h
0x1800306ca  cmp     al, 20h ; ' '
0x1800306cc  ja      loc_18003079D
0x1800306d2  mov     al, [rbp+27h+arg_18]
0x1800306d5  and     al, 0Fh
0x1800306d7  sub     al, 2
0x1800306d9  cmp     al, 3
0x1800306db  ja      loc_18003079D
0x1800306e1  mov     rcx, rbx; struct VCARD_DATA *
0x1800306e4  call    ?I_VCardIsLoaded@@YAHPEBUVCARD_DATA@@@Z; I_VCardIsLoaded(VCARD_DATA const *)
0x1800306e9  test    eax, eax
0x1800306eb  jz      short loc_180030738
0x1800306ed  mov     edx, 2
0x1800306f2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800306f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306fe  lea     rax, WPP_GLOBAL_Control
0x180030705  mov     ebx, 649h
0x18003070a  cmp     rcx, rax
0x18003070d  jz      loc_1800307F5
0x180030713  test    byte ptr [rcx+1Ch], 1
0x180030717  jz      loc_1800307F5
0x18003071d  cmp     byte ptr [rcx+19h], 2
0x180030721  jb      loc_1800307F5
0x180030727  mov     edx, 84h
0x18003072c  lea     r8, aCannotOperateO; "Cannot operate on loaded card"
0x180030733  jmp     loc_1800307D5
0x180030738  lea     rax, [rbp+27h+arg_8]
0x18003073c  mov     [rbp+27h+var_68], rax
0x180030740  lea     rcx, [rbp+27h+var_68]
0x180030744  lea     rax, [rbp+27h+arg_10]
0x180030748  mov     [rbp+27h+var_60], rax
0x18003074c  lea     rax, [rbp+27h+arg_18]
0x180030750  mov     [rbp+27h+var_58], rax
0x180030754  lea     rax, [rbp+27h+arg_20]
0x180030758  mov     [rbp+27h+var_50], rax
0x18003075c  lea     rax, [rbp+27h+arg_28]
0x180030760  mov     [rbp+27h+var_48], rax
0x180030764  lea     rax, [rbp+27h+arg_30]
0x180030768  mov     [rbp+27h+var_40], rax
0x18003076c  lea     rax, [rbp+27h+arg_38]
0x180030770  mov     [rbp+27h+var_38], rax
0x180030774  lea     rax, [rbp+27h+arg_40]
0x180030778  mov     [rbp+27h+var_30], rax
0x18003077c  lea     rax, [rbp+27h+arg_48]
0x180030780  mov     [rbp+27h+var_28], rax
0x180030784  call    VCardErrorContract__lambda_1a445b3d6b6285831f5cc9af91362f3f___; VCardErrorContract__lambda_1a445b3d6b6285831f5cc9af91362f3f_
0x180030789  mov     ebx, eax
0x18003078b  test    eax, eax
0x18003078d  jle     short loc_180030798
0x18003078f  movzx   ebx, ax
0x180030792  or      ebx, 80070000h
0x180030798  mov     [rbp+27h+var_8C], ebx
0x18003079b  jmp     short loc_1800307F5
0x18003079d  mov     edx, 2
0x1800307a2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800307a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307ae  lea     rax, WPP_GLOBAL_Control
0x1800307b5  mov     ebx, 57h ; 'W'
0x1800307ba  cmp     rcx, rax
0x1800307bd  jz      short loc_1800307F5
0x1800307bf  test    byte ptr [rcx+1Ch], 1
0x1800307c3  jz      short loc_1800307F5
0x1800307c5  cmp     byte ptr [rcx+19h], 2
0x1800307c9  jb      short loc_1800307F5
0x1800307cb  lea     edx, [rbx+2Ch]
0x1800307ce  lea     r8, aInvalidParamet; "Invalid parameter"
0x1800307d5  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800307dc  mov     rcx, [rcx+10h]
0x1800307e0  mov     [rsp+28h], r8
0x1800307e5  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x1800307ec  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800307f0  call    WPP_SF_sDs
0x1800307f5  lea     rcx, [rbp+27h+var_88]
0x1800307f9  call    WppTraceUnwinder__lambda_45d82e41e36390cc040c986d1d86a018_______WppTraceUnwinder__lambda_45d82e41e36390cc040c986d1d86a018____
0x1800307fe  mov     eax, ebx
0x180030800  mov     rcx, [rbp+27h+var_8]
0x180030804  xor     rcx, rsp; StackCookie
0x180030807  call    __security_check_cookie
0x18003080c  mov     rbx, [rsp+0C0h+arg_0]
0x180030814  add     rsp, 0C0h
0x18003081b  pop     rbp
0x18003081c  retn
```
