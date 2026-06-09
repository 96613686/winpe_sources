# VCardOpenChannel

- ea: `0x1800330b0`
- end: `0x180033239`
- name: `VCardOpenChannel`
- size: `393`
- prototype: `__int64 __fastcall(struct VCARD_DATA *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x1800295a4`
- `0x18002c5c4`
- `0x18002c9e0`
- `0x18002df54`
- `0x1800330b0`

## string_xrefs

- `0x1800330de`: `VCardOpenChannel`

## pseudocode

```c
__int64 __fastcall VCardOpenChannel(struct VCARD_DATA *a1, __int64 a2)
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
  char v16[24]; // [rsp+70h] [rbp+37h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+6Fh] BYREF

  v17 = a2;
  v10 = 0;
  v14[0] = v16;
  v14[1] = &v11;
  v14[2] = &v10;
  v11 = 0;
  strcpy(v16, "VCardOpenChannel");
  lambda_5492164a0b39a3c81533c4d39c966590_::operator()(v14);
  v11 = 1;
  v12 = v14;
  if ( a1 && v17 )
  {
    v13 = a1;
    if ( (unsigned int)I_VCardIsLoaded(a1) )
    {
      v15[0] = &v13;
      v15[1] = &v17;
      v5 = VCardErrorContract__lambda_749e69efa53665c07b146d3b83a7e89f_(v15);
      v10 = v5;
    }
    else
    {
      WppTraceIndent(v4, 2u);
      v5 = 1609;
      v10 = 1609;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 26;
        v8 = "Card has not been loaded";
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
      v7 = 25;
      v8 = "Invalid NULL parameter";
      goto LABEL_13;
    }
  }
  WppTraceUnwinder__lambda_5492164a0b39a3c81533c4d39c966590____::_WppTraceUnwinder__lambda_5492164a0b39a3c81533c4d39c966590____(&v12);
  return v5;
}

```

## disassembly

```asm
0x1800330b0  mov     [rsp-8+arg_0], rbx
0x1800330b5  mov     [rsp-8+arg_8], rdx
0x1800330ba  push    rbp
0x1800330bb  lea     rbp, [rsp-57h]
0x1800330c0  sub     rsp, 90h
0x1800330c7  mov     rax, cs:__security_cookie
0x1800330ce  xor     rax, rsp
0x1800330d1  mov     [rbp+57h+var_8], rax
0x1800330d5  mov     al, byte ptr cs:aVcardopenchann_0+10h; ""
0x1800330db  mov     rbx, rcx
0x1800330de  movups  xmm0, xmmword ptr cs:aVcardopenchann_0; "VCardOpenChannel"
0x1800330e5  mov     [rbp+57h+var_20+10h], al
0x1800330e8  lea     rcx, [rbp+57h+var_48]
0x1800330ec  lea     rax, [rbp+57h+var_20]
0x1800330f0  mov     [rbp+57h+var_60], 0
0x1800330f7  mov     [rbp+57h+var_48], rax
0x1800330fb  lea     rax, [rbp+57h+var_5C]
0x1800330ff  mov     [rbp+57h+var_40], rax
0x180033103  lea     rax, [rbp+57h+var_60]
0x180033107  mov     [rbp+57h+var_38], rax
0x18003310b  mov     [rbp+57h+var_5C], 0
0x180033112  movups  xmmword ptr [rbp+57h+var_20], xmm0
0x180033116  call    _lambda_5492164a0b39a3c81533c4d39c966590___operator__
0x18003311b  mov     [rbp+57h+var_5C], 1
0x180033122  lea     rax, [rbp+57h+var_48]
0x180033126  mov     [rbp+57h+var_58], rax
0x18003312a  test    rbx, rbx
0x18003312d  jz      loc_1800331B3
0x180033133  cmp     [rbp+57h+arg_8], 0
0x180033138  jz      short loc_1800331B3
0x18003313a  mov     rcx, rbx; struct VCARD_DATA *
0x18003313d  mov     [rbp+57h+var_50], rbx
0x180033141  call    ?I_VCardIsLoaded@@YAHPEBUVCARD_DATA@@@Z; I_VCardIsLoaded(VCARD_DATA const *)
0x180033146  test    eax, eax
0x180033148  jnz     short loc_180033193
0x18003314a  lea     edx, [rax+2]
0x18003314d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180033152  mov     ebx, 649h
0x180033157  mov     [rbp+57h+var_60], ebx
0x18003315a  mov     rcx, cs:WPP_GLOBAL_Control
0x180033161  lea     rax, WPP_GLOBAL_Control
0x180033168  cmp     rcx, rax
0x18003316b  jz      loc_180033211
0x180033171  test    byte ptr [rcx+1Ch], 1
0x180033175  jz      loc_180033211
0x18003317b  cmp     byte ptr [rcx+19h], 2
0x18003317f  jb      loc_180033211
0x180033185  mov     edx, 1Ah
0x18003318a  lea     rax, aCardHasNotBeen_0; "Card has not been loaded"
0x180033191  jmp     short loc_1800331EE
0x180033193  lea     rax, [rbp+57h+var_50]
0x180033197  mov     [rbp+57h+var_30], rax
0x18003319b  lea     rcx, [rbp+57h+var_30]
0x18003319f  lea     rax, [rbp+57h+arg_8]
0x1800331a3  mov     [rbp+57h+var_28], rax
0x1800331a7  call    VCardErrorContract__lambda_749e69efa53665c07b146d3b83a7e89f___; VCardErrorContract__lambda_749e69efa53665c07b146d3b83a7e89f_
0x1800331ac  mov     ebx, eax
0x1800331ae  mov     [rbp+57h+var_60], eax
0x1800331b1  jmp     short loc_180033211
0x1800331b3  mov     edx, 2
0x1800331b8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800331bd  mov     ebx, 57h ; 'W'
0x1800331c2  mov     [rbp+57h+var_60], ebx
0x1800331c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800331cc  lea     rax, WPP_GLOBAL_Control
0x1800331d3  cmp     rcx, rax
0x1800331d6  jz      short loc_180033211
0x1800331d8  test    byte ptr [rcx+1Ch], 1
0x1800331dc  jz      short loc_180033211
0x1800331de  cmp     byte ptr [rcx+19h], 2
0x1800331e2  jb      short loc_180033211
0x1800331e4  lea     edx, [rbx-3Eh]
0x1800331e7  lea     rax, aInvalidNullPar; "Invalid NULL parameter"
0x1800331ee  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800331f5  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x1800331fc  mov     rcx, [rcx+10h]
0x180033200  mov     [rsp+90h+var_68], rax
0x180033205  mov     [rsp+90h+var_70], ebx
0x180033209  call    WPP_SF_sDs
0x18003320e  mov     ebx, [rbp+57h+var_60]
0x180033211  lea     rcx, [rbp+57h+var_58]
0x180033215  call    WppTraceUnwinder__lambda_5492164a0b39a3c81533c4d39c966590_______WppTraceUnwinder__lambda_5492164a0b39a3c81533c4d39c966590____
0x18003321a  mov     eax, ebx
0x18003321c  mov     rcx, [rbp+57h+var_8]
0x180033220  xor     rcx, rsp; StackCookie
0x180033223  call    __security_check_cookie
0x180033228  mov     rbx, [rsp+90h+arg_0]
0x180033230  add     rsp, 90h
0x180033237  pop     rbp
0x180033238  retn
```
