# I_VCardDataOpenLocking(VCARD_DATA *,ushort const *)

- ea: `0x1800292e8`
- end: `0x18002959c`
- name: `?I_VCardDataOpenLocking@@YAKPEAUVCARD_DATA@@PEBG@Z`
- size: `692`
- prototype: `__int64 __fastcall(struct VCARD_DATA *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180017448`
- `0x18002e918`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x180016740`
- `0x180027288`
- `0x1800277c0`
- `0x1800279dc`
- `0x180028610`
- `0x180028e48`
- `0x1800292e8`
- `0x1800295a4`
- `0x180029938`
- `0x180029e28`
- `0x1800348a0`

## string_xrefs

- `0x180029401`: `Unable to set card root path`
- `0x180029322`: `I_VCardDataOpenLocking`

## pseudocode

```c
__int64 __fastcall I_VCardDataOpenLocking(struct VCARD_DATA *a1, const unsigned __int16 *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rcx
  _QWORD *v8; // rcx
  int v9; // edx
  const char *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned int v14; // ebx
  unsigned int v16; // [rsp+30h] [rbp-19h] BYREF
  struct VCARD_DATA *v17; // [rsp+38h] [rbp-11h] BYREF
  int v18; // [rsp+40h] [rbp-9h] BYREF
  struct VCARD_DATA **v19; // [rsp+48h] [rbp-1h] BYREF
  __int16 v20; // [rsp+50h] [rbp+7h]
  struct VCARD_DATA **v21; // [rsp+58h] [rbp+Fh] BYREF
  _QWORD *v22; // [rsp+60h] [rbp+17h] BYREF
  _QWORD v23[3]; // [rsp+68h] [rbp+1Fh] BYREF
  char v24[24]; // [rsp+80h] [rbp+37h] BYREF

  v17 = a1;
  v16 = 0;
  v18 = 0;
  strcpy(v24, "I_VCardDataOpenLocking");
  v23[0] = v24;
  v23[1] = &v18;
  v23[2] = &v16;
  lambda_4d91f4cf7681b64cbd380a9be452ad98_::operator()(v23);
  v18 = 1;
  v22 = v23;
  if ( !v17 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3);
  if ( (unsigned int)I_VCardIsLoaded(v17) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5);
  *((_DWORD *)v17 + 4) = 0;
  _InterlockedExchange((volatile __int32 *)v17 + 30, 0);
  v19 = &v17;
  v20 = 258;
  v16 = I_SetVCardRoot(v17, a2);
  if ( v16 )
  {
    WppTraceIndent(v7, 2);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 37;
      v10 = "Unable to set card root path";
LABEL_12:
      WPP_SF_sDs(
        v8[2],
        v9,
        (unsigned int)WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids,
        (_DWORD)WPP_pszIndent,
        v16,
        (__int64)v10);
    }
  }
  else
  {
    v16 = I_InitializeProviders(v17);
    if ( v16 )
    {
      WppTraceIndent(v11, 2);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 38;
        v10 = "Algorithm provider initialization failed";
        goto LABEL_12;
      }
    }
    else
    {
      v21 = &v17;
      v16 = lambda_79ba3c88d95574faafea776cdcbad460_::operator()(&v21);
      if ( v16 )
      {
        WppTraceIndent(v12, 2);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 41;
          v10 = "Loading mapping files failed";
          goto LABEL_12;
        }
      }
      else
      {
        if ( (Microsoft_Windows_SmartCard_TPM_VCard_ModuleEnableBits & 4) != 0 )
          McTemplateU0p_EventWriteTransfer(v12, EVENT_VCARD_VERIFYING, v17);
        v16 = I_VerifyTpmState(v17);
        if ( v16 )
        {
          WppTraceIndent(v13, 2);
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v9 = 42;
            v10 = "TPM state verification failed";
            goto LABEL_12;
          }
        }
        else
        {
          if ( (Microsoft_Windows_SmartCard_TPM_VCard_ModuleEnableBits & 4) != 0 )
            McTemplateU0p_EventWriteTransfer(v13, EVENT_VCARD_VERIFIED, v17);
          *((_DWORD *)v17 + 4) = 1;
          HIBYTE(v20) = 0;
        }
      }
    }
  }
  v14 = v16;
  wil::details::ScopeExitFnGuard__lambda_7afff1fa9c927d39bc73e8aff8adf638___::operator()(&v19);
  WppTraceUnwinder__lambda_4d91f4cf7681b64cbd380a9be452ad98____::_WppTraceUnwinder__lambda_4d91f4cf7681b64cbd380a9be452ad98____(&v22);
  return v14;
}

```

## disassembly

```asm
0x1800292e8  mov     [rsp-8+arg_10], rbx
0x1800292ed  mov     [rsp-8+arg_18], rdi
0x1800292f2  push    rbp
0x1800292f3  lea     rbp, [rsp-57h]
0x1800292f8  sub     rsp, 0A0h
0x1800292ff  mov     rax, cs:__security_cookie
0x180029306  xor     rax, rsp
0x180029309  mov     [rbp+57h+var_8], rax
0x18002930d  mov     rbx, rdx
0x180029310  mov     [rbp+57h+var_68], rcx
0x180029314  mov     [rbp+57h+var_70], 0
0x18002931b  mov     [rbp+57h+var_60], 0
0x180029322  movups  xmm0, xmmword ptr cs:aIVcarddataopen; "I_VCardDataOpenLocking"
0x180029329  movups  xmmword ptr [rbp+57h+var_20], xmm0
0x18002932d  movsd   xmm1, qword ptr cs:aIVcarddataopen+0Fh; "Locking"
0x180029335  movsd   qword ptr [rbp+57h+var_20+0Fh], xmm1
0x18002933a  lea     rax, [rbp+57h+var_20]
0x18002933e  mov     [rbp+57h+var_38], rax
0x180029342  lea     rax, [rbp+57h+var_60]
0x180029346  mov     [rbp+57h+var_30], rax
0x18002934a  lea     rax, [rbp+57h+var_70]
0x18002934e  mov     [rbp+57h+var_28], rax
0x180029352  lea     rcx, [rbp+57h+var_38]
0x180029356  call    _lambda_4d91f4cf7681b64cbd380a9be452ad98___operator__
0x18002935b  mov     [rbp+57h+var_60], 1
0x180029362  lea     rax, [rbp+57h+var_38]
0x180029366  mov     [rbp+57h+var_40], rax
0x18002936a  cmp     [rbp+57h+var_68], 0
0x18002936f  jnz     short loc_180029376
0x180029371  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180029376  test    rbx, rbx
0x180029379  jnz     short loc_180029380
0x18002937b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180029380  mov     rcx, [rbp+57h+var_68]; struct VCARD_DATA *
0x180029384  call    ?I_VCardIsLoaded@@YAHPEBUVCARD_DATA@@@Z; I_VCardIsLoaded(VCARD_DATA const *)
0x180029389  test    eax, eax
0x18002938b  jz      short loc_180029392
0x18002938d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180029392  mov     rax, [rbp+57h+var_68]
0x180029396  mov     dword ptr [rax+10h], 0
0x18002939d  mov     rcx, [rbp+57h+var_68]
0x1800293a1  xor     eax, eax
0x1800293a3  xchg    eax, [rcx+78h]
0x1800293a6  lea     rcx, [rbp+57h+var_68]
0x1800293aa  mov     [rbp+57h+var_58], rcx
0x1800293ae  mov     edi, 2
0x1800293b3  mov     [rbp+57h+var_50], 102h
0x1800293b9  mov     rdx, rbx; unsigned __int16 *
0x1800293bc  mov     rcx, [rbp+57h+var_68]; struct VCARD_DATA *
0x1800293c0  call    ?I_SetVCardRoot@@YAKPEAUVCARD_DATA@@PEBG@Z; I_SetVCardRoot(VCARD_DATA *,ushort const *)
0x1800293c5  mov     [rbp+57h+var_70], eax
0x1800293c8  test    eax, eax
0x1800293ca  jz      short loc_180029430
0x1800293cc  mov     edx, edi
0x1800293ce  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800293d3  lea     rax, WPP_GLOBAL_Control
0x1800293da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800293e1  cmp     rcx, rax
0x1800293e4  jz      loc_180029563
0x1800293ea  test    byte ptr [rcx+1Ch], 1
0x1800293ee  jz      loc_180029563
0x1800293f4  cmp     [rcx+19h], dil
0x1800293f8  jb      loc_180029563
0x1800293fe  lea     edx, [rdi+23h]
0x180029401  lea     rax, aUnableToSetCar; "Unable to set card root path"
0x180029408  mov     [rsp+0A0h+var_78], rax
0x18002940d  mov     eax, [rbp+57h+var_70]
0x180029410  mov     [rsp+0A0h+var_80], eax
0x180029414  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002941b  lea     r8, WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids
0x180029422  mov     rcx, [rcx+10h]
0x180029426  call    WPP_SF_sDs
0x18002942b  jmp     loc_180029563
0x180029430  mov     rcx, [rbp+57h+var_68]; struct VCARD_DATA *
0x180029434  call    ?I_InitializeProviders@@YAKPEAUVCARD_DATA@@@Z; I_InitializeProviders(VCARD_DATA *)
0x180029439  mov     [rbp+57h+var_70], eax
0x18002943c  test    eax, eax
0x18002943e  jz      short loc_180029480
0x180029440  mov     edx, edi
0x180029442  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180029447  lea     rax, WPP_GLOBAL_Control
0x18002944e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029455  cmp     rcx, rax
0x180029458  jz      loc_180029563
0x18002945e  test    byte ptr [rcx+1Ch], 1
0x180029462  jz      loc_180029563
0x180029468  cmp     [rcx+19h], dil
0x18002946c  jb      loc_180029563
0x180029472  mov     edx, 26h ; '&'
0x180029477  lea     rax, aAlgorithmProvi; "Algorithm provider initialization faile"...
0x18002947e  jmp     short loc_180029408
0x180029480  lea     rax, [rbp+57h+var_68]
0x180029484  mov     [rbp+57h+var_48], rax
0x180029488  lea     rcx, [rbp+57h+var_48]
0x18002948c  call    _lambda_79ba3c88d95574faafea776cdcbad460___operator__
0x180029491  mov     [rbp+57h+var_70], eax
0x180029494  test    eax, eax
0x180029496  jz      short loc_1800294DB
0x180029498  mov     edx, edi
0x18002949a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002949f  lea     rax, WPP_GLOBAL_Control
0x1800294a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800294ad  cmp     rcx, rax
0x1800294b0  jz      loc_180029563
0x1800294b6  test    byte ptr [rcx+1Ch], 1
0x1800294ba  jz      loc_180029563
0x1800294c0  cmp     [rcx+19h], dil
0x1800294c4  jb      loc_180029563
0x1800294ca  mov     edx, 29h ; ')'
0x1800294cf  lea     rax, aLoadingMapping; "Loading mapping files failed"
0x1800294d6  jmp     loc_180029408
0x1800294db  test    cs:Microsoft_Windows_SmartCard_TPM_VCard_ModuleEnableBits, 4
0x1800294e2  jz      short loc_1800294F4
0x1800294e4  mov     r8, [rbp+57h+var_68]
0x1800294e8  lea     rdx, EVENT_VCARD_VERIFYING
0x1800294ef  call    McTemplateU0p_EventWriteTransfer
0x1800294f4  mov     rcx, [rbp+57h+var_68]
0x1800294f8  call    I_VerifyTpmState
0x1800294fd  mov     [rbp+57h+var_70], eax
0x180029500  test    eax, eax
0x180029502  jz      short loc_18002953B
0x180029504  mov     edx, edi
0x180029506  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002950b  lea     rax, WPP_GLOBAL_Control
0x180029512  mov     rcx, cs:WPP_GLOBAL_Control
0x180029519  cmp     rcx, rax
0x18002951c  jz      short loc_180029563
0x18002951e  test    byte ptr [rcx+1Ch], 1
0x180029522  jz      short loc_180029563
0x180029524  cmp     [rcx+19h], dil
0x180029528  jb      short loc_180029563
0x18002952a  mov     edx, 2Ah ; '*'
0x18002952f  lea     rax, aTpmStateVerifi; "TPM state verification failed"
0x180029536  jmp     loc_180029408
0x18002953b  test    cs:Microsoft_Windows_SmartCard_TPM_VCard_ModuleEnableBits, 4
0x180029542  jz      short loc_180029554
0x180029544  mov     r8, [rbp+57h+var_68]
0x180029548  lea     rdx, EVENT_VCARD_VERIFIED
0x18002954f  call    McTemplateU0p_EventWriteTransfer
0x180029554  mov     rax, [rbp+57h+var_68]
0x180029558  mov     dword ptr [rax+10h], 1
0x18002955f  mov     byte ptr [rbp+57h+var_50+1], 0
0x180029563  mov     ebx, [rbp+57h+var_70]
0x180029566  lea     rcx, [rbp+57h+var_58]
0x18002956a  call    wil__details__ScopeExitFnGuard__lambda_7afff1fa9c927d39bc73e8aff8adf638_____operator__
0x18002956f  nop
0x180029570  lea     rcx, [rbp+57h+var_40]
0x180029574  call    WppTraceUnwinder__lambda_4d91f4cf7681b64cbd380a9be452ad98_______WppTraceUnwinder__lambda_4d91f4cf7681b64cbd380a9be452ad98____
0x180029579  mov     eax, ebx
0x18002957b  mov     rcx, [rbp+57h+var_8]
0x18002957f  xor     rcx, rsp; StackCookie
0x180029582  call    __security_check_cookie
0x180029587  lea     r11, [rsp+0A0h+var_s0]
0x18002958f  mov     rbx, [r11+20h]
0x180029593  mov     rdi, [r11+28h]
0x180029597  mov     rsp, r11
0x18002959a  pop     rbp
0x18002959b  retn
```
