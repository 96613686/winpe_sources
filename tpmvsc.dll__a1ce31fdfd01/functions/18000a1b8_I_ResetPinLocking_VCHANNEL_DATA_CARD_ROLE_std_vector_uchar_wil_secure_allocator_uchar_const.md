# I_ResetPinLocking(VCHANNEL_DATA *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &)

- ea: `0x18000a1b8`
- end: `0x18000a464`
- name: `?I_ResetPinLocking@@YAKPEAUVCHANNEL_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z`
- size: `684`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18002dbb4`

## callees

- `0x180001ec0`
- `0x1800067cc`
- `0x1800069b8`
- `0x1800075b8`
- `0x1800079b8`
- `0x18000a110`
- `0x18000a1b8`
- `0x18000a81c`
- `0x18000bc48`
- `0x18000c198`
- `0x180013e58`
- `0x180029644`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a3b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a433`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a3b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a433`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a272`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a272`

## string_xrefs

- `0x18000a2f9`: `New PIN does not meet complexity requirement`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall I_ResetPinLocking(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  RTL_SRWLOCK *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned int v12; // edi
  _QWORD *v13; // rcx
  int v14; // edx
  const char *v15; // rax
  __int64 v16; // rcx
  int v18; // [rsp+30h] [rbp-29h] BYREF
  RTL_SRWLOCK **v19; // [rsp+38h] [rbp-21h] BYREF
  int v20; // [rsp+40h] [rbp-19h] BYREF
  _QWORD *v21; // [rsp+48h] [rbp-11h] BYREF
  __int64 *v22; // [rsp+50h] [rbp-9h] BYREF
  __int16 v23; // [rsp+58h] [rbp-1h]
  _QWORD v24[4]; // [rsp+60h] [rbp+7h] BYREF
  char v25[24]; // [rsp+80h] [rbp+27h] BYREF

  v19 = (RTL_SRWLOCK **)a1;
  v18 = 0;
  v20 = 0;
  strcpy(v25, "I_ResetPinLocking");
  v24[0] = v25;
  v24[1] = &v20;
  v24[2] = &v18;
  lambda_d307f3d6b6349934b6d0bb20197bc679_::operator()(v24);
  v20 = 1;
  v21 = v24;
  if ( !v19 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5);
  if ( a2 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5);
  if ( !(unsigned int)I_IsRoleAuthenticated((__int64)v19, 3) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  v9 = *v19 + 9;
  AcquireSRWLockExclusive(v9);
  v24[3] = v9;
  if ( (unsigned int)I_VCardIsUsingPuk((const struct VCARD_DATA *)*v19) || (v10 = (__int64)v19, v19[19] == v19[20]) )
  {
    WppTraceIndent(v10, 2);
    v12 = -2146435038;
    v18 = -2146435038;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 86;
      v15 = "Challenge/response based PIN reset not supported";
      goto LABEL_27;
    }
LABEL_28:
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    WppTraceUnwinder__lambda_d307f3d6b6349934b6d0bb20197bc679____::_WppTraceUnwinder__lambda_d307f3d6b6349934b6d0bb20197bc679____(&v21);
    return v12;
  }
  if ( !I_PinMapValidatePinComplexity((__int64)*v19, a2, a3) )
  {
    WppTraceIndent(v11, 2);
    v12 = -2146435068;
    v18 = -2146435068;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 87;
      v15 = "New PIN does not meet complexity requirement";
LABEL_27:
      WPP_SF_sDs(
        v13[2],
        v14,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        v12,
        (__int64)v15);
      v12 = v18;
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=(v19 + 16, (__int64)(v19 + 19));
  v22 = (__int64 *)&v19;
  v23 = 258;
  v18 = I_SetReferenceData(v19, a2, a3);
  if ( v18 )
  {
    WppTraceIndent(v16, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        v18,
        (__int64)"Unable to reset the user PIN");
    }
    v12 = v18;
    wil::details::ScopeExitFnGuard__lambda_e4819bc7d4d7c528f40e1c7e2380f75e___::operator()(&v22);
    goto LABEL_28;
  }
  wil::details::ScopeExitFnGuard__lambda_e4819bc7d4d7c528f40e1c7e2380f75e___::operator()(&v22);
  if ( v9 )
    ReleaseSRWLockExclusive(v9);
  WppTraceUnwinder__lambda_d307f3d6b6349934b6d0bb20197bc679____::_WppTraceUnwinder__lambda_d307f3d6b6349934b6d0bb20197bc679____(&v21);
  return 0;
}

```

## disassembly

```asm
0x18000a1b8  mov     [rsp-8+arg_18], rbx
0x18000a1bd  push    rbp
0x18000a1be  push    rsi
0x18000a1bf  push    rdi
0x18000a1c0  lea     rbp, [rsp-47h]
0x18000a1c5  sub     rsp, 0A0h
0x18000a1cc  mov     rax, cs:__security_cookie
0x18000a1d3  xor     rax, rsp
0x18000a1d6  mov     [rbp+57h+var_18], rax
0x18000a1da  mov     rsi, r8
0x18000a1dd  mov     edi, edx
0x18000a1df  mov     [rbp+57h+var_78], rcx
0x18000a1e3  mov     [rbp+57h+var_80], 0
0x18000a1ea  mov     [rbp+57h+var_70], 0
0x18000a1f1  movups  xmm0, xmmword ptr cs:aIResetpinlocki; "I_ResetPinLocking"
0x18000a1f8  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x18000a1fc  movzx   eax, word ptr cs:aIResetpinlocki+10h; "g"
0x18000a203  mov     word ptr [rbp+57h+var_30+10h], ax
0x18000a207  lea     rax, [rbp+57h+var_30]
0x18000a20b  mov     [rbp+57h+var_50], rax
0x18000a20f  lea     rax, [rbp+57h+var_70]
0x18000a213  mov     [rbp+57h+var_48], rax
0x18000a217  lea     rax, [rbp+57h+var_80]
0x18000a21b  mov     [rbp+57h+var_40], rax
0x18000a21f  lea     rcx, [rbp+57h+var_50]
0x18000a223  call    _lambda_d307f3d6b6349934b6d0bb20197bc679___operator__
0x18000a228  mov     [rbp+57h+var_70], 1
0x18000a22f  lea     rax, [rbp+57h+var_50]
0x18000a233  mov     [rbp+57h+var_68], rax
0x18000a237  cmp     [rbp+57h+var_78], 0
0x18000a23c  jnz     short loc_18000A243
0x18000a23e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a243  cmp     edi, 1
0x18000a246  jz      short loc_18000A24D
0x18000a248  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a24d  mov     edx, 3
0x18000a252  mov     rcx, [rbp+57h+var_78]
0x18000a256  call    ?I_IsRoleAuthenticated@@YAHPEBUVCHANNEL_DATA@@W4_CARD_ROLE@@@Z; I_IsRoleAuthenticated(VCHANNEL_DATA const *,_CARD_ROLE)
0x18000a25b  test    eax, eax
0x18000a25d  jnz     short loc_18000A264
0x18000a25f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a264  mov     rax, [rbp+57h+var_78]
0x18000a268  mov     rbx, [rax]
0x18000a26b  add     rbx, 48h ; 'H'
0x18000a26f  mov     rcx, rbx; SRWLock
0x18000a272  call    cs:__imp_AcquireSRWLockExclusive
0x18000a278  mov     [rbp+57h+var_38], rbx
0x18000a27c  mov     rcx, [rbp+57h+var_78]
0x18000a280  mov     rcx, [rcx]; struct VCARD_DATA *
0x18000a283  call    ?I_VCardIsUsingPuk@@YAHPEBUVCARD_DATA@@@Z; I_VCardIsUsingPuk(VCARD_DATA const *)
0x18000a288  test    eax, eax
0x18000a28a  jnz     loc_18000A3CB
0x18000a290  mov     rcx, [rbp+57h+var_78]
0x18000a294  mov     rax, [rcx+0A0h]
0x18000a29b  cmp     [rcx+98h], rax
0x18000a2a2  jz      loc_18000A3CB
0x18000a2a8  mov     r8, rsi
0x18000a2ab  mov     edx, edi
0x18000a2ad  mov     rcx, [rcx]
0x18000a2b0  call    ?I_PinMapValidatePinComplexity@@YAHPEBUVCARD_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_PinMapValidatePinComplexity(VCARD_DATA const *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x18000a2b5  test    eax, eax
0x18000a2b7  jnz     short loc_18000A305
0x18000a2b9  lea     edx, [rax+2]
0x18000a2bc  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000a2c1  mov     edi, 80100004h
0x18000a2c6  mov     [rbp+57h+var_80], edi
0x18000a2c9  lea     rax, WPP_GLOBAL_Control
0x18000a2d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2d7  cmp     rcx, rax
0x18000a2da  jz      loc_18000A42B
0x18000a2e0  test    byte ptr [rcx+1Ch], 1
0x18000a2e4  jz      loc_18000A42B
0x18000a2ea  cmp     byte ptr [rcx+19h], 2
0x18000a2ee  jb      loc_18000A42B
0x18000a2f4  mov     edx, 57h ; 'W'
0x18000a2f9  lea     rax, aNewPinDoesNotM; "New PIN does not meet complexity requir"...
0x18000a300  jmp     loc_18000A408
0x18000a305  mov     rcx, [rbp+57h+var_78]
0x18000a309  lea     rdx, [rcx+98h]
0x18000a310  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18000a314  call    ??4?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::operator=(std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x18000a319  lea     rax, [rbp+57h+var_78]
0x18000a31d  mov     [rbp+57h+var_60], rax
0x18000a321  mov     [rbp+57h+var_58], 102h
0x18000a327  mov     r8, rsi
0x18000a32a  mov     edx, edi
0x18000a32c  mov     rcx, [rbp+57h+var_78]
0x18000a330  call    ?I_SetReferenceData@@YAKPEAUVCHANNEL_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_SetReferenceData(VCHANNEL_DATA *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x18000a335  mov     [rbp+57h+var_80], eax
0x18000a338  test    eax, eax
0x18000a33a  jz      short loc_18000A3A5
0x18000a33c  mov     edx, 2
0x18000a341  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000a346  lea     rax, WPP_GLOBAL_Control
0x18000a34d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a354  cmp     rcx, rax
0x18000a357  jz      short loc_18000A394
0x18000a359  test    byte ptr [rcx+1Ch], 1
0x18000a35d  jz      short loc_18000A394
0x18000a35f  cmp     byte ptr [rcx+19h], 2
0x18000a363  jb      short loc_18000A394
0x18000a365  mov     edx, 58h ; 'X'
0x18000a36a  lea     rax, aUnableToResetT; "Unable to reset the user PIN"
0x18000a371  mov     [rsp+0B0h+var_88], rax
0x18000a376  mov     eax, [rbp+57h+var_80]
0x18000a379  mov     [rsp+0B0h+var_90], eax
0x18000a37d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000a384  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000a38b  mov     rcx, [rcx+10h]
0x18000a38f  call    WPP_SF_sDs
0x18000a394  mov     edi, [rbp+57h+var_80]
0x18000a397  lea     rcx, [rbp+57h+var_60]
0x18000a39b  call    wil__details__ScopeExitFnGuard__lambda_e4819bc7d4d7c528f40e1c7e2380f75e_____operator__
0x18000a3a0  jmp     loc_18000A42B
0x18000a3a5  lea     rcx, [rbp+57h+var_60]
0x18000a3a9  call    wil__details__ScopeExitFnGuard__lambda_e4819bc7d4d7c528f40e1c7e2380f75e_____operator__
0x18000a3ae  nop
0x18000a3af  test    rbx, rbx
0x18000a3b2  jz      short loc_18000A3BE
0x18000a3b4  mov     rcx, rbx; SRWLock
0x18000a3b7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a3bd  nop
0x18000a3be  lea     rcx, [rbp+57h+var_68]
0x18000a3c2  call    WppTraceUnwinder__lambda_d307f3d6b6349934b6d0bb20197bc679_______WppTraceUnwinder__lambda_d307f3d6b6349934b6d0bb20197bc679____
0x18000a3c7  xor     eax, eax
0x18000a3c9  jmp     short loc_18000A445
0x18000a3cb  mov     edx, 2
0x18000a3d0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000a3d5  mov     edi, 80100022h
0x18000a3da  mov     [rbp+57h+var_80], edi
0x18000a3dd  lea     rax, WPP_GLOBAL_Control
0x18000a3e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3eb  cmp     rcx, rax
0x18000a3ee  jz      short loc_18000A42B
0x18000a3f0  test    byte ptr [rcx+1Ch], 1
0x18000a3f4  jz      short loc_18000A42B
0x18000a3f6  cmp     byte ptr [rcx+19h], 2
0x18000a3fa  jb      short loc_18000A42B
0x18000a3fc  mov     edx, 56h ; 'V'
0x18000a401  lea     rax, aChallengeRespo; "Challenge/response based PIN reset not "...
0x18000a408  mov     [rsp+0B0h+var_88], rax
0x18000a40d  mov     [rsp+0B0h+var_90], edi
0x18000a411  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000a418  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000a41f  mov     rcx, [rcx+10h]
0x18000a423  call    WPP_SF_sDs
0x18000a428  mov     edi, [rbp+57h+var_80]
0x18000a42b  test    rbx, rbx
0x18000a42e  jz      short loc_18000A43A
0x18000a430  mov     rcx, rbx; SRWLock
0x18000a433  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a439  nop
0x18000a43a  lea     rcx, [rbp+57h+var_68]
0x18000a43e  call    WppTraceUnwinder__lambda_d307f3d6b6349934b6d0bb20197bc679_______WppTraceUnwinder__lambda_d307f3d6b6349934b6d0bb20197bc679____
0x18000a443  mov     eax, edi
0x18000a445  mov     rcx, [rbp+57h+var_18]
0x18000a449  xor     rcx, rsp; StackCookie
0x18000a44c  call    __security_check_cookie
0x18000a451  mov     rbx, [rsp+0B0h+arg_18]
0x18000a459  add     rsp, 0A0h
0x18000a460  pop     rdi
0x18000a461  pop     rsi
0x18000a462  pop     rbp
0x18000a463  retn
```
