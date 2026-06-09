# VCardDeleteKey

- ea: `0x180031990`
- end: `0x180031b26`
- name: `VCardDeleteKey`
- size: `406`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x18002c398`
- `0x18002ca88`
- `0x18002e4dc`
- `0x180031990`

## string_xrefs

- `0x1800319bd`: `VCardDeleteKey`
- `0x180031a73`: `The AIK can not be deleted`

## pseudocode

```c
__int64 __fastcall VCardDeleteKey(__int64 a1, char a2)
{
  __int64 v3; // rcx
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  int v6; // edx
  const char *v7; // rax
  int v9; // [rsp+30h] [rbp-9h] BYREF
  int v10; // [rsp+34h] [rbp-5h] BYREF
  _QWORD *v11; // [rsp+38h] [rbp-1h] BYREF
  __int64 v12; // [rsp+40h] [rbp+7h] BYREF
  _QWORD v13[3]; // [rsp+48h] [rbp+Fh] BYREF
  _QWORD v14[2]; // [rsp+60h] [rbp+27h] BYREF
  char v15[16]; // [rsp+70h] [rbp+37h] BYREF
  char v16; // [rsp+A8h] [rbp+6Fh] BYREF

  v16 = a2;
  v13[0] = v15;
  v13[1] = &v10;
  v13[2] = &v9;
  v9 = 0;
  v10 = 0;
  strcpy(v15, "VCardDeleteKey");
  lambda_7fc91cdaf70c904f7754c23eb88eda68_::operator()(v13);
  v10 = 1;
  v11 = v13;
  if ( a1 && (unsigned __int8)(v16 + 0x80) <= 0x20u )
  {
    if ( v16 == -96 )
    {
      WppTraceIndent(v3, 2u);
      v4 = 87;
      v9 = 87;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 82;
        v7 = "The AIK can not be deleted";
LABEL_13:
        WPP_SF_sDs(
          v5[2],
          v6,
          (unsigned int)WPP_19641971e2e2383bda07edbd33517adf_Traceguids,
          (_DWORD)WPP_pszIndent,
          87,
          (__int64)v7);
        v4 = v9;
      }
    }
    else
    {
      v12 = a1;
      v14[0] = &v12;
      v14[1] = &v16;
      v4 = VCardErrorContract__lambda_29c7ac33dacc7d14558cbb3379439785_(v14);
      v9 = v4;
    }
  }
  else
  {
    WppTraceIndent(v3, 2u);
    v4 = 87;
    v9 = 87;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 81;
      v7 = "Invalid parameter";
      goto LABEL_13;
    }
  }
  WppTraceUnwinder__lambda_7fc91cdaf70c904f7754c23eb88eda68____::_WppTraceUnwinder__lambda_7fc91cdaf70c904f7754c23eb88eda68____(&v11);
  return v4;
}

```

## disassembly

```asm
0x180031990  mov     [rsp-8+arg_0], rbx
0x180031995  mov     [rsp-8+arg_8], dl
0x180031999  push    rbp
0x18003199a  lea     rbp, [rsp-57h]
0x18003199f  sub     rsp, 90h
0x1800319a6  mov     rax, cs:__security_cookie
0x1800319ad  xor     rax, rsp
0x1800319b0  mov     [rbp+57h+var_10], rax
0x1800319b4  mov     eax, dword ptr cs:aVcarddeletekey_0+8; "eteKey"
0x1800319ba  mov     rbx, rcx
0x1800319bd  movsd   xmm0, qword ptr cs:aVcarddeletekey_0; "VCardDeleteKey"
0x1800319c5  lea     rcx, [rbp+57h+var_48]
0x1800319c9  mov     dword ptr [rbp+57h+var_20+8], eax
0x1800319cc  movzx   eax, word ptr cs:aVcarddeletekey_0+0Ch; "ey"
0x1800319d3  mov     word ptr [rbp+57h+var_20+0Ch], ax
0x1800319d7  mov     al, byte ptr cs:aVcarddeletekey_0+0Eh; ""
0x1800319dd  mov     [rbp+57h+var_20+0Eh], al
0x1800319e0  lea     rax, [rbp+57h+var_20]
0x1800319e4  mov     [rbp+57h+var_48], rax
0x1800319e8  lea     rax, [rbp+57h+var_5C]
0x1800319ec  mov     [rbp+57h+var_40], rax
0x1800319f0  lea     rax, [rbp+57h+var_60]
0x1800319f4  mov     [rbp+57h+var_38], rax
0x1800319f8  mov     [rbp+57h+var_60], 0
0x1800319ff  mov     [rbp+57h+var_5C], 0
0x180031a06  movsd   qword ptr [rbp+57h+var_20], xmm0
0x180031a0b  call    _lambda_7fc91cdaf70c904f7754c23eb88eda68___operator__
0x180031a10  mov     [rbp+57h+var_5C], 1
0x180031a17  lea     rax, [rbp+57h+var_48]
0x180031a1b  mov     [rbp+57h+var_58], rax
0x180031a1f  test    rbx, rbx
0x180031a22  jz      short loc_180031AA0
0x180031a24  mov     al, [rbp+57h+arg_8]
0x180031a27  sub     al, 80h
0x180031a29  cmp     al, 20h ; ' '
0x180031a2b  ja      short loc_180031AA0
0x180031a2d  cmp     [rbp+57h+arg_8], 0A0h
0x180031a31  jnz     short loc_180031A7C
0x180031a33  mov     edx, 2
0x180031a38  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180031a3d  mov     ebx, 57h ; 'W'
0x180031a42  mov     [rbp+57h+var_60], ebx
0x180031a45  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a4c  lea     rax, WPP_GLOBAL_Control
0x180031a53  cmp     rcx, rax
0x180031a56  jz      loc_180031AFE
0x180031a5c  test    byte ptr [rcx+1Ch], 1
0x180031a60  jz      loc_180031AFE
0x180031a66  cmp     byte ptr [rcx+19h], 2
0x180031a6a  jb      loc_180031AFE
0x180031a70  lea     edx, [rbx-5]
0x180031a73  lea     rax, aTheAikCanNotBe_0; "The AIK can not be deleted"
0x180031a7a  jmp     short loc_180031ADB
0x180031a7c  lea     rax, [rbp+57h+var_50]
0x180031a80  mov     [rbp+57h+var_50], rbx
0x180031a84  mov     [rbp+57h+var_30], rax
0x180031a88  lea     rcx, [rbp+57h+var_30]
0x180031a8c  lea     rax, [rbp+57h+arg_8]
0x180031a90  mov     [rbp+57h+var_28], rax
0x180031a94  call    VCardErrorContract__lambda_29c7ac33dacc7d14558cbb3379439785___; VCardErrorContract__lambda_29c7ac33dacc7d14558cbb3379439785_
0x180031a99  mov     ebx, eax
0x180031a9b  mov     [rbp+57h+var_60], eax
0x180031a9e  jmp     short loc_180031AFE
0x180031aa0  mov     edx, 2
0x180031aa5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180031aaa  mov     ebx, 57h ; 'W'
0x180031aaf  mov     [rbp+57h+var_60], ebx
0x180031ab2  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ab9  lea     rax, WPP_GLOBAL_Control
0x180031ac0  cmp     rcx, rax
0x180031ac3  jz      short loc_180031AFE
0x180031ac5  test    byte ptr [rcx+1Ch], 1
0x180031ac9  jz      short loc_180031AFE
0x180031acb  cmp     byte ptr [rcx+19h], 2
0x180031acf  jb      short loc_180031AFE
0x180031ad1  lea     edx, [rbx-6]
0x180031ad4  lea     rax, aInvalidParamet; "Invalid parameter"
0x180031adb  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180031ae2  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x180031ae9  mov     rcx, [rcx+10h]
0x180031aed  mov     [rsp+90h+var_68], rax
0x180031af2  mov     [rsp+90h+var_70], ebx
0x180031af6  call    WPP_SF_sDs
0x180031afb  mov     ebx, [rbp+57h+var_60]
0x180031afe  lea     rcx, [rbp+57h+var_58]
0x180031b02  call    WppTraceUnwinder__lambda_7fc91cdaf70c904f7754c23eb88eda68_______WppTraceUnwinder__lambda_7fc91cdaf70c904f7754c23eb88eda68____
0x180031b07  mov     eax, ebx
0x180031b09  mov     rcx, [rbp+57h+var_10]
0x180031b0d  xor     rcx, rsp; StackCookie
0x180031b10  call    __security_check_cookie
0x180031b15  mov     rbx, [rsp+90h+arg_0]
0x180031b1d  add     rsp, 90h
0x180031b24  pop     rbp
0x180031b25  retn
```
