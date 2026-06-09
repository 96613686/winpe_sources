# I_DeleteReferenceData(VCARD_DATA *,_CARD_ROLE)

- ea: `0x180009154`
- end: `0x1800093c2`
- name: `?I_DeleteReferenceData@@YAKPEAUVCARD_DATA@@W4_CARD_ROLE@@@Z`
- size: `622`
- prototype: `__int64 __fastcall(struct VCARD_DATA *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017448`

## callees

- `0x180001ec0`
- `0x180002a90`
- `0x180006778`
- `0x180006c74`
- `0x180007468`
- `0x18000794c`
- `0x180009154`
- `0x18000bc48`
- `0x18000c198`
- `0x180012580`
- `0x18001280c`
- `0x1800128c4`
- `0x180013814`
- `0x1800201f0`
- `0x1800348a0`

## string_xrefs

- `0x180009294`: `Unable to update user record`
- `0x18000918d`: `I_DeleteReferenceData`

## pseudocode

```c
__int64 __fastcall I_DeleteReferenceData(struct VCARD_DATA *a1, unsigned int a2)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned int v4; // ebx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  unsigned int v9; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v10; // [rsp+38h] [rbp-C8h] BYREF
  struct VCARD_DATA *v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v13; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v14[3]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v15; // [rsp+70h] [rbp-90h]
  _QWORD v16[3]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v17[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v18[80]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v19; // [rsp+F0h] [rbp-10h]
  int v20; // [rsp+F8h] [rbp-8h]
  unsigned __int16 v21[48]; // [rsp+100h] [rbp+0h] BYREF
  char v22[24]; // [rsp+160h] [rbp+60h] BYREF

  v11 = a1;
  v10 = a2;
  v9 = 0;
  v12 = 0;
  strcpy(v22, "I_DeleteReferenceData");
  v16[0] = v22;
  v16[1] = &v12;
  v16[2] = &v9;
  lambda_b7b8736f6fe601c2b5e23d4b0da0af21_::operator()(v16);
  v12 = 1;
  v13 = v16;
  if ( !v11 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2);
  v4 = v10;
  if ( v10 - 1 > 1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2);
    v4 = v10;
  }
  memset_0(v21, 0, 0x5Cu);
  I_PinMapGetRecord(v11, v4, v21);
  if ( !(unsigned int)I_PinMapIsActive((const struct PIN_MAP_RECORD *)v21) )
    goto LABEL_11;
  v19 = 0;
  v20 = 0;
  memset_0(v18, 0, sizeof(v18));
  v9 = I_PinMapSetRecord(v11, v10, v18);
  if ( v9 )
  {
    WppTraceIndent(v5, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        v9,
        (__int64)"Unable to update user record");
    }
LABEL_11:
    v6 = v9;
    goto LABEL_20;
  }
  v14[0] = &v11;
  v14[1] = &v10;
  v14[2] = v21;
  v15 = 258;
  v17[0] = &v11;
  v17[1] = &v10;
  v9 = lambda_373371ab0ddab111caf487dd5fefdaa9_::operator()(v17);
  if ( v9 )
  {
    WppTraceIndent(v7, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        116,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        v9,
        (__int64)"Deleting reference data failed");
    }
  }
  else
  {
    HIBYTE(v15) = 0;
    if ( !(unsigned int)I_PinMapIsBlocked((const struct PIN_MAP_RECORD *)v21) )
      I_DeleteKspKey(v11, v21);
  }
  v6 = v9;
  wil::details::ScopeExitFnGuard__lambda_f38f1c235d4bbfc7af7b18896877faaa___::operator()(v14);
LABEL_20:
  WppTraceUnwinder__lambda_b7b8736f6fe601c2b5e23d4b0da0af21____::_WppTraceUnwinder__lambda_b7b8736f6fe601c2b5e23d4b0da0af21____(&v13);
  return v6;
}

```

## disassembly

```asm
0x180009154  mov     [rsp-8+arg_10], rbx
0x180009159  push    rbp
0x18000915a  lea     rbp, [rsp-80h]
0x18000915f  sub     rsp, 180h
0x180009166  mov     rax, cs:__security_cookie
0x18000916d  xor     rax, rsp
0x180009170  mov     [rbp+80h+var_8], rax
0x180009174  mov     [rsp+180h+var_140], rcx
0x180009179  mov     [rsp+180h+var_148], edx
0x18000917d  mov     [rsp+180h+var_150], 0
0x180009185  mov     [rsp+180h+var_138], 0
0x18000918d  movups  xmm0, xmmword ptr cs:aIDeletereferen; "I_DeleteReferenceData"
0x180009194  movups  xmmword ptr [rbp+80h+var_20], xmm0
0x180009198  movsd   xmm1, qword ptr cs:aIDeletereferen+0Eh; "nceData"
0x1800091a0  movsd   qword ptr [rbp+80h+var_20+0Eh], xmm1
0x1800091a5  lea     rax, [rbp+80h+var_20]
0x1800091a9  mov     [rsp+180h+var_108], rax
0x1800091ae  lea     rax, [rsp+180h+var_138]
0x1800091b3  mov     [rbp+80h+var_100], rax
0x1800091b7  lea     rax, [rsp+180h+var_150]
0x1800091bc  mov     [rbp+80h+var_F8], rax
0x1800091c0  lea     rcx, [rsp+180h+var_108]
0x1800091c5  call    _lambda_b7b8736f6fe601c2b5e23d4b0da0af21___operator__
0x1800091ca  mov     [rsp+180h+var_138], 1
0x1800091d2  lea     rax, [rsp+180h+var_108]
0x1800091d7  mov     [rsp+180h+var_130], rax
0x1800091dc  cmp     [rsp+180h+var_140], 0
0x1800091e2  jnz     short loc_1800091E9
0x1800091e4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800091e9  mov     ebx, [rsp+180h+var_148]
0x1800091ed  lea     eax, [rbx-1]
0x1800091f0  cmp     eax, 1
0x1800091f3  jbe     short loc_1800091FE
0x1800091f5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800091fa  mov     ebx, [rsp+180h+var_148]
0x1800091fe  xor     edx, edx; Val
0x180009200  lea     r8d, [rdx+5Ch]; Size
0x180009204  lea     rcx, [rbp+80h+var_80]; void *
0x180009208  call    memset_0
0x18000920d  lea     r8, [rbp+80h+var_80]
0x180009211  mov     edx, ebx
0x180009213  mov     rcx, [rsp+180h+var_140]
0x180009218  call    ?I_PinMapGetRecord@@YAXPEBUVCARD_DATA@@W4_CARD_ROLE@@PEAUPIN_MAP_RECORD@@@Z; I_PinMapGetRecord(VCARD_DATA const *,_CARD_ROLE,PIN_MAP_RECORD *)
0x18000921d  lea     rcx, [rbp+80h+var_80]; struct PIN_MAP_RECORD *
0x180009221  call    ?I_PinMapIsActive@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsActive(PIN_MAP_RECORD const *)
0x180009226  test    eax, eax
0x180009228  jz      loc_1800092BF
0x18000922e  mov     [rbp+80h+var_90], 0
0x180009236  mov     [rbp+80h+var_88], 0
0x18000923d  xor     edx, edx; Val
0x18000923f  lea     r8d, [rdx+50h]; Size
0x180009243  lea     rcx, [rbp+80h+var_E0]; void *
0x180009247  call    memset_0
0x18000924c  lea     r8, [rbp+80h+var_E0]
0x180009250  mov     edx, [rsp+180h+var_148]
0x180009254  mov     rcx, [rsp+180h+var_140]
0x180009259  call    ?I_PinMapSetRecord@@YAKPEBUVCARD_DATA@@W4_CARD_ROLE@@PEBUPIN_MAP_RECORD@@@Z; I_PinMapSetRecord(VCARD_DATA const *,_CARD_ROLE,PIN_MAP_RECORD const *)
0x18000925e  mov     [rsp+180h+var_150], eax
0x180009262  test    eax, eax
0x180009264  jz      short loc_1800092C8
0x180009266  mov     edx, 2
0x18000926b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180009270  lea     rax, WPP_GLOBAL_Control
0x180009277  mov     rcx, cs:WPP_GLOBAL_Control
0x18000927e  cmp     rcx, rax
0x180009281  jz      short loc_1800092BF
0x180009283  test    byte ptr [rcx+1Ch], 1
0x180009287  jz      short loc_1800092BF
0x180009289  cmp     byte ptr [rcx+19h], 2
0x18000928d  jb      short loc_1800092BF
0x18000928f  mov     edx, 71h ; 'q'
0x180009294  lea     rax, aUnableToUpdate_1; "Unable to update user record"
0x18000929b  mov     [rsp+180h+var_158], rax
0x1800092a0  mov     eax, [rsp+180h+var_150]
0x1800092a4  mov     [rsp+180h+var_160], eax
0x1800092a8  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800092af  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x1800092b6  mov     rcx, [rcx+10h]
0x1800092ba  call    WPP_SF_sDs
0x1800092bf  mov     ebx, [rsp+180h+var_150]
0x1800092c3  jmp     loc_180009399
0x1800092c8  lea     rax, [rsp+180h+var_140]
0x1800092cd  mov     [rsp+180h+var_128], rax
0x1800092d2  lea     rax, [rsp+180h+var_148]
0x1800092d7  mov     [rsp+180h+var_120], rax
0x1800092dc  lea     rax, [rbp+80h+var_80]
0x1800092e0  mov     [rsp+180h+var_118], rax
0x1800092e5  mov     [rsp+180h+var_110], 102h
0x1800092ec  lea     rax, [rsp+180h+var_140]
0x1800092f1  mov     [rbp+80h+var_F0], rax
0x1800092f5  lea     rax, [rsp+180h+var_148]
0x1800092fa  mov     [rbp+80h+var_E8], rax
0x1800092fe  lea     rcx, [rbp+80h+var_F0]
0x180009302  call    _lambda_373371ab0ddab111caf487dd5fefdaa9___operator__
0x180009307  mov     [rsp+180h+var_150], eax
0x18000930b  test    eax, eax
0x18000930d  jz      short loc_18000936A
0x18000930f  mov     edx, 2
0x180009314  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180009319  lea     rax, WPP_GLOBAL_Control
0x180009320  mov     rcx, cs:WPP_GLOBAL_Control
0x180009327  cmp     rcx, rax
0x18000932a  jz      short loc_18000938A
0x18000932c  test    byte ptr [rcx+1Ch], 1
0x180009330  jz      short loc_18000938A
0x180009332  cmp     byte ptr [rcx+19h], 2
0x180009336  jb      short loc_18000938A
0x180009338  mov     edx, 74h ; 't'
0x18000933d  lea     rax, aDeletingRefere; "Deleting reference data failed"
0x180009344  mov     [rsp+180h+var_158], rax
0x180009349  mov     eax, [rsp+180h+var_150]
0x18000934d  mov     [rsp+180h+var_160], eax
0x180009351  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180009358  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000935f  mov     rcx, [rcx+10h]
0x180009363  call    WPP_SF_sDs
0x180009368  jmp     short loc_18000938A
0x18000936a  mov     byte ptr [rsp+180h+var_110+1], 0
0x18000936f  lea     rcx, [rbp+80h+var_80]; struct PIN_MAP_RECORD *
0x180009373  call    ?I_PinMapIsBlocked@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsBlocked(PIN_MAP_RECORD const *)
0x180009378  test    eax, eax
0x18000937a  jnz     short loc_18000938A
0x18000937c  lea     rdx, [rbp+80h+var_80]; unsigned __int16 *
0x180009380  mov     rcx, [rsp+180h+var_140]; struct VCARD_DATA *
0x180009385  call    ?I_DeleteKspKey@@YAKPEBUVCARD_DATA@@PEBG@Z; I_DeleteKspKey(VCARD_DATA const *,ushort const *)
0x18000938a  mov     ebx, [rsp+180h+var_150]
0x18000938e  lea     rcx, [rsp+180h+var_128]
0x180009393  call    wil__details__ScopeExitFnGuard__lambda_f38f1c235d4bbfc7af7b18896877faaa_____operator__
0x180009398  nop
0x180009399  lea     rcx, [rsp+180h+var_130]
0x18000939e  call    WppTraceUnwinder__lambda_b7b8736f6fe601c2b5e23d4b0da0af21_______WppTraceUnwinder__lambda_b7b8736f6fe601c2b5e23d4b0da0af21____
0x1800093a3  mov     eax, ebx
0x1800093a5  mov     rcx, [rbp+80h+var_8]
0x1800093a9  xor     rcx, rsp; StackCookie
0x1800093ac  call    __security_check_cookie
0x1800093b1  mov     rbx, [rsp+180h+arg_10]
0x1800093b9  add     rsp, 180h
0x1800093c0  pop     rbp
0x1800093c1  retn
```
