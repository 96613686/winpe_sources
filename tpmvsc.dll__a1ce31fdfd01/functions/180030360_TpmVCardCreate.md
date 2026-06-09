# TpmVCardCreate

- ea: `0x180030360`
- end: `0x1800305c7`
- name: `TpmVCardCreate`
- size: `615`
- prototype: `__int64 __usercall@<rax>(struct VCARD_DATA *@<rcx>, __int64, __int64, __int64, __int64, __int64, char)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x1800295a4`
- `0x18002c824`
- `0x18002c970`
- `0x18002dd94`
- `0x180030360`

## string_xrefs

- `0x180030396`: `TpmVCardCreate`

## pseudocode

```c
__int64 __fastcall TpmVCardCreate(
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
  unsigned int v13; // ebx
  _QWORD *v14; // rcx
  int v15; // edx
  const char *v16; // rax
  int v18; // [rsp+38h] [rbp-79h] BYREF
  int v19; // [rsp+3Ch] [rbp-75h] BYREF
  _QWORD *v20; // [rsp+40h] [rbp-71h] BYREF
  struct VCARD_DATA *v21; // [rsp+48h] [rbp-69h] BYREF
  _QWORD v22[3]; // [rsp+50h] [rbp-61h] BYREF
  _QWORD v23[10]; // [rsp+68h] [rbp-49h] BYREF
  char v24[16]; // [rsp+B8h] [rbp+7h] BYREF
  __int64 v25; // [rsp+F0h] [rbp+3Fh] BYREF
  char v26; // [rsp+F8h] [rbp+47h] BYREF
  char v27; // [rsp+100h] [rbp+4Fh] BYREF

  v27 = a4;
  v26 = a3;
  v25 = a2;
  v22[0] = v24;
  v22[1] = &v19;
  v22[2] = &v18;
  v18 = 0;
  v19 = 0;
  strcpy(v24, "TpmVCardCreate");
  lambda_37bc69a7e3bcbcdb4a48df1b326b5ace_::operator()(v22);
  v19 = 1;
  v20 = v22;
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
    v21 = a1;
    if ( (unsigned int)I_VCardIsLoaded(a1) )
    {
      WppTraceIndent(v12, 2u);
      v13 = 1609;
      v18 = 1609;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 127;
        v16 = "Cannot operate on loaded card";
LABEL_24:
        WPP_SF_sDs(
          v14[2],
          v15,
          (unsigned int)WPP_19641971e2e2383bda07edbd33517adf_Traceguids,
          (_DWORD)WPP_pszIndent,
          v13,
          (__int64)v16);
        v13 = v18;
      }
    }
    else
    {
      v23[0] = &v21;
      v23[1] = &v25;
      v23[2] = &v26;
      v23[3] = &v27;
      v23[4] = &a5;
      v23[5] = &a6;
      v23[6] = &a7;
      v23[7] = &a8;
      v23[8] = &a9;
      v23[9] = &a10;
      v13 = VCardErrorContract__lambda_f5fb84ffdd45669e6dee99532ac1a9cf_(v23);
      v18 = v13;
    }
  }
  else
  {
    WppTraceIndent(v11, 2u);
    v13 = 87;
    v18 = 87;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 126;
      v16 = "Invalid parameter";
      goto LABEL_24;
    }
  }
  WppTraceUnwinder__lambda_37bc69a7e3bcbcdb4a48df1b326b5ace____::_WppTraceUnwinder__lambda_37bc69a7e3bcbcdb4a48df1b326b5ace____(&v20);
  return v13;
}

```

## disassembly

```asm
0x180030360  mov     rax, rsp
0x180030363  mov     [rax+8], rbx
0x180030367  mov     [rax+20h], r9b
0x18003036b  mov     [rax+18h], r8b
0x18003036f  mov     [rax+10h], rdx
0x180030373  push    rbp
0x180030374  lea     rbp, [rax-2Fh]
0x180030378  sub     rsp, 0D0h
0x18003037f  mov     rax, cs:__security_cookie
0x180030386  xor     rax, rsp
0x180030389  mov     [rbp+27h+var_10], rax
0x18003038d  mov     eax, dword ptr cs:aTpmvcardcreate_1+8; "Create"
0x180030393  mov     rbx, rcx
0x180030396  movsd   xmm0, qword ptr cs:aTpmvcardcreate_1; "TpmVCardCreate"
0x18003039e  lea     rcx, [rbp+27h+var_88]
0x1800303a2  mov     dword ptr [rbp+27h+var_20+8], eax
0x1800303a5  movzx   eax, word ptr cs:aTpmvcardcreate_1+0Ch; "te"
0x1800303ac  mov     word ptr [rbp+27h+var_20+0Ch], ax
0x1800303b0  mov     al, byte ptr cs:aTpmvcardcreate_1+0Eh; ""
0x1800303b6  mov     [rbp+27h+var_20+0Eh], al
0x1800303b9  lea     rax, [rbp+27h+var_20]
0x1800303bd  mov     [rbp+27h+var_88], rax
0x1800303c1  lea     rax, [rbp+27h+var_9C]
0x1800303c5  mov     [rbp+27h+var_80], rax
0x1800303c9  lea     rax, [rbp+27h+var_A0]
0x1800303cd  mov     [rbp+27h+var_78], rax
0x1800303d1  mov     [rbp+27h+var_A0], 0
0x1800303d8  mov     [rbp+27h+var_9C], 0
0x1800303df  movsd   qword ptr [rbp+27h+var_20], xmm0
0x1800303e4  call    _lambda_37bc69a7e3bcbcdb4a48df1b326b5ace___operator__
0x1800303e9  mov     [rbp+27h+var_9C], 1
0x1800303f0  lea     rax, [rbp+27h+var_88]
0x1800303f4  mov     [rbp+27h+var_98], rax
0x1800303f8  test    rbx, rbx
0x1800303fb  jz      loc_180030541
0x180030401  cmp     [rbp+27h+arg_8], 0
0x180030406  jz      loc_180030541
0x18003040c  mov     rax, [rbp+27h+arg_20]
0x180030410  test    rax, rax
0x180030413  jz      loc_180030541
0x180030419  cmp     dword ptr [rax+0Ch], 0
0x18003041d  jz      loc_180030541
0x180030423  mov     rax, [rbp+27h+arg_28]
0x180030427  test    rax, rax
0x18003042a  jz      short loc_180030436
0x18003042c  cmp     dword ptr [rax+0Ch], 3
0x180030430  jnz     loc_180030541
0x180030436  mov     rax, [rbp+27h+arg_30]
0x18003043a  test    rax, rax
0x18003043d  jz      short loc_180030449
0x18003043f  cmp     dword ptr [rax+0Ch], 0
0x180030443  jz      loc_180030541
0x180030449  cmp     [rbp+27h+arg_38], 0
0x18003044e  jz      loc_180030541
0x180030454  mov     rax, [rbp+27h+arg_40]
0x180030458  test    rax, rax
0x18003045b  jz      short loc_180030467
0x18003045d  cmp     dword ptr [rax+0Ch], 0
0x180030461  jz      loc_180030541
0x180030467  mov     al, [rbp+27h+arg_10]
0x18003046a  sub     al, 80h
0x18003046c  cmp     al, 20h ; ' '
0x18003046e  ja      loc_180030541
0x180030474  mov     al, [rbp+27h+arg_18]
0x180030477  and     al, 0Fh
0x180030479  sub     al, 2
0x18003047b  cmp     al, 3
0x18003047d  ja      loc_180030541
0x180030483  mov     rcx, rbx; struct VCARD_DATA *
0x180030486  mov     [rbp+27h+var_90], rbx
0x18003048a  call    ?I_VCardIsLoaded@@YAHPEBUVCARD_DATA@@@Z; I_VCardIsLoaded(VCARD_DATA const *)
0x18003048f  test    eax, eax
0x180030491  jz      short loc_1800304E1
0x180030493  mov     edx, 2
0x180030498  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003049d  mov     ebx, 649h
0x1800304a2  mov     [rbp+27h+var_A0], ebx
0x1800304a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800304ac  lea     rax, WPP_GLOBAL_Control
0x1800304b3  cmp     rcx, rax
0x1800304b6  jz      loc_18003059F
0x1800304bc  test    byte ptr [rcx+1Ch], 1
0x1800304c0  jz      loc_18003059F
0x1800304c6  cmp     byte ptr [rcx+19h], 2
0x1800304ca  jb      loc_18003059F
0x1800304d0  mov     edx, 7Fh
0x1800304d5  lea     rax, aCannotOperateO; "Cannot operate on loaded card"
0x1800304dc  jmp     loc_18003057C
0x1800304e1  lea     rax, [rbp+27h+var_90]
0x1800304e5  mov     [rbp+27h+var_70], rax
0x1800304e9  lea     rcx, [rbp+27h+var_70]
0x1800304ed  lea     rax, [rbp+27h+arg_8]
0x1800304f1  mov     [rbp+27h+var_68], rax
0x1800304f5  lea     rax, [rbp+27h+arg_10]
0x1800304f9  mov     [rbp+27h+var_60], rax
0x1800304fd  lea     rax, [rbp+27h+arg_18]
0x180030501  mov     [rbp+27h+var_58], rax
0x180030505  lea     rax, [rbp+27h+arg_20]
0x180030509  mov     [rbp+27h+var_50], rax
0x18003050d  lea     rax, [rbp+27h+arg_28]
0x180030511  mov     [rbp+27h+var_48], rax
0x180030515  lea     rax, [rbp+27h+arg_30]
0x180030519  mov     [rbp+27h+var_40], rax
0x18003051d  lea     rax, [rbp+27h+arg_38]
0x180030521  mov     [rbp+27h+var_38], rax
0x180030525  lea     rax, [rbp+27h+arg_40]
0x180030529  mov     [rbp+27h+var_30], rax
0x18003052d  lea     rax, [rbp+27h+arg_48]
0x180030531  mov     [rbp+27h+var_28], rax
0x180030535  call    VCardErrorContract__lambda_f5fb84ffdd45669e6dee99532ac1a9cf___; VCardErrorContract__lambda_f5fb84ffdd45669e6dee99532ac1a9cf_
0x18003053a  mov     ebx, eax
0x18003053c  mov     [rbp+27h+var_A0], eax
0x18003053f  jmp     short loc_18003059F
0x180030541  mov     edx, 2
0x180030546  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003054b  mov     ebx, 57h ; 'W'
0x180030550  mov     [rbp+27h+var_A0], ebx
0x180030553  mov     rcx, cs:WPP_GLOBAL_Control
0x18003055a  lea     rax, WPP_GLOBAL_Control
0x180030561  cmp     rcx, rax
0x180030564  jz      short loc_18003059F
0x180030566  test    byte ptr [rcx+1Ch], 1
0x18003056a  jz      short loc_18003059F
0x18003056c  cmp     byte ptr [rcx+19h], 2
0x180030570  jb      short loc_18003059F
0x180030572  lea     edx, [rbx+27h]
0x180030575  lea     rax, aInvalidParamet; "Invalid parameter"
0x18003057c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180030583  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x18003058a  mov     rcx, [rcx+10h]
0x18003058e  mov     [rsp+28h], rax
0x180030593  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x180030597  call    WPP_SF_sDs
0x18003059c  mov     ebx, [rbp+27h+var_A0]
0x18003059f  lea     rcx, [rbp+27h+var_98]
0x1800305a3  call    WppTraceUnwinder__lambda_37bc69a7e3bcbcdb4a48df1b326b5ace_______WppTraceUnwinder__lambda_37bc69a7e3bcbcdb4a48df1b326b5ace____
0x1800305a8  mov     eax, ebx
0x1800305aa  mov     rcx, [rbp+27h+var_10]
0x1800305ae  xor     rcx, rsp; StackCookie
0x1800305b1  call    __security_check_cookie
0x1800305b6  mov     rbx, [rsp+0D0h+arg_0]
0x1800305be  add     rsp, 0D0h
0x1800305c5  pop     rbp
0x1800305c6  retn
```
