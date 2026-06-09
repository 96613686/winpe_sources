# I_ChangePinLocking(VCHANNEL_DATA *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &)

- ea: `0x180008324`
- end: `0x1800085af`
- name: `?I_ChangePinLocking@@YAKPEAUVCHANNEL_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@2@Z`
- size: `651`
- prototype: `__int64 __fastcall(struct VCHANNEL_DATA *, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18002ccc8`

## callees

- `0x180001ec0`
- `0x1800067b0`
- `0x180007548`
- `0x180007a78`
- `0x180008324`
- `0x1800085b8`
- `0x180008c3c`
- `0x18000bc48`
- `0x18000c0c8`
- `0x18000c198`
- `0x180013e58`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008580`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008580`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008434`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008434`

## string_xrefs

- `0x180008483`: `New PIN does not meet complexity requirement`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall I_ChangePinLocking(struct VCHANNEL_DATA *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int v11; // ebx
  RTL_SRWLOCK *v12; // rbx
  __int64 v13; // rcx
  int v14; // edi
  __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned int v18; // [rsp+30h] [rbp-29h] BYREF
  int v19; // [rsp+34h] [rbp-25h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-21h] BYREF
  _QWORD v21[4]; // [rsp+40h] [rbp-19h] BYREF
  char v22[24]; // [rsp+60h] [rbp+7h] BYREF

  v18 = 0;
  v19 = 0;
  strcpy(v22, "I_ChangePinLocking");
  v21[0] = v22;
  v21[1] = &v19;
  v21[2] = &v18;
  lambda_c9712cbb2926dbaaea074c81e95892d9_::operator()(v21);
  v19 = 1;
  v20 = v21;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( a2 - 1 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  v18 = I_Deauthenticate(a1);
  if ( v18 )
  {
    WppTraceIndent(v10, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        v18,
        (__int64)"Unable to deauthenticate the card");
    }
    v11 = v18;
    goto LABEL_34;
  }
  v12 = (RTL_SRWLOCK *)(*(_QWORD *)a1 + 72LL);
  AcquireSRWLockExclusive(v12);
  v21[3] = v12;
  if ( !(unsigned int)I_PinMapValidatePinComplexity(*(_QWORD *)a1, a2, a4) )
  {
    WppTraceIndent(v13, 2);
    v14 = -2146435068;
    v18 = -2146435068;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      77,
      (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
      (_DWORD)WPP_pszIndent,
      4,
      (__int64)"New PIN does not meet complexity requirement");
LABEL_16:
    v14 = v18;
LABEL_17:
    if ( v12 )
      ReleaseSRWLockExclusive(v12);
    v11 = v14;
    goto LABEL_34;
  }
  v18 = I_ChangeReferenceData(*(_QWORD *)a1, a2, a3, a4);
  if ( v18 )
  {
    WppTraceIndent(v15, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        v18,
        (__int64)"Unable to change PIN");
    }
    goto LABEL_16;
  }
  v18 = I_AuthenticatePin(a1, a2, a4);
  if ( v18 )
  {
    WppTraceIndent(v16, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids);
    }
    v18 = 0;
  }
  if ( v12 )
    ReleaseSRWLockExclusive(v12);
  v11 = 0;
LABEL_34:
  WppTraceUnwinder__lambda_c9712cbb2926dbaaea074c81e95892d9____::_WppTraceUnwinder__lambda_c9712cbb2926dbaaea074c81e95892d9____(&v20);
  return v11;
}

```

## disassembly

```asm
0x180008324  push    rbp
0x180008326  push    rbx
0x180008327  push    rsi
0x180008328  push    rdi
0x180008329  push    r14
0x18000832b  push    r15
0x18000832d  lea     rbp, [rsp-2Fh]
0x180008332  sub     rsp, 88h
0x180008339  mov     rax, cs:__security_cookie
0x180008340  xor     rax, rsp
0x180008343  mov     [rbp+57h+var_38], rax
0x180008347  mov     r14, r9
0x18000834a  mov     r15, r8
0x18000834d  mov     esi, edx
0x18000834f  mov     rdi, rcx
0x180008352  mov     [rbp+57h+var_80], 0
0x180008359  mov     [rbp+57h+var_7C], 0
0x180008360  movups  xmm0, xmmword ptr cs:aIChangepinlock; "I_ChangePinLocking"
0x180008367  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18000836b  mov     eax, dword ptr cs:aIChangepinlock+0Fh; "ing"
0x180008371  mov     dword ptr [rbp+57h+var_50+0Fh], eax
0x180008374  lea     rax, [rbp+57h+var_50]
0x180008378  mov     [rbp+57h+var_70], rax
0x18000837c  lea     rax, [rbp+57h+var_7C]
0x180008380  mov     [rbp+57h+var_68], rax
0x180008384  lea     rax, [rbp+57h+var_80]
0x180008388  mov     [rbp+57h+var_60], rax
0x18000838c  lea     rcx, [rbp+57h+var_70]
0x180008390  call    _lambda_c9712cbb2926dbaaea074c81e95892d9___operator__
0x180008395  mov     [rbp+57h+var_7C], 1
0x18000839c  lea     rax, [rbp+57h+var_70]
0x1800083a0  mov     [rbp+57h+var_78], rax
0x1800083a4  test    rdi, rdi
0x1800083a7  jnz     short loc_1800083AE
0x1800083a9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800083ae  lea     eax, [rsi-1]
0x1800083b1  cmp     eax, 1
0x1800083b4  jbe     short loc_1800083BB
0x1800083b6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800083bb  mov     rcx, rdi; struct VCHANNEL_DATA *
0x1800083be  call    ?I_Deauthenticate@@YAKPEAUVCHANNEL_DATA@@@Z; I_Deauthenticate(VCHANNEL_DATA *)
0x1800083c3  mov     [rbp+57h+var_80], eax
0x1800083c6  test    eax, eax
0x1800083c8  jz      short loc_18000842A
0x1800083ca  mov     edx, 2
0x1800083cf  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800083d4  lea     rax, WPP_GLOBAL_Control
0x1800083db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083e2  cmp     rcx, rax
0x1800083e5  jz      short loc_180008422
0x1800083e7  test    byte ptr [rcx+1Ch], 1
0x1800083eb  jz      short loc_180008422
0x1800083ed  cmp     byte ptr [rcx+19h], 2
0x1800083f1  jb      short loc_180008422
0x1800083f3  mov     edx, 4Ch ; 'L'
0x1800083f8  lea     rax, aUnableToDeauth; "Unable to deauthenticate the card"
0x1800083ff  mov     [rsp+0B0h+var_88], rax
0x180008404  mov     eax, [rbp+57h+var_80]
0x180008407  mov     [rsp+0B0h+var_90], eax
0x18000840b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180008412  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x180008419  mov     rcx, [rcx+10h]
0x18000841d  call    WPP_SF_sDs
0x180008422  mov     ebx, [rbp+57h+var_80]
0x180008425  jmp     loc_180008588
0x18000842a  mov     rbx, [rdi]
0x18000842d  add     rbx, 48h ; 'H'
0x180008431  mov     rcx, rbx; SRWLock
0x180008434  call    cs:__imp_AcquireSRWLockExclusive
0x18000843a  mov     [rbp+57h+var_58], rbx
0x18000843e  mov     r8, r14
0x180008441  mov     edx, esi
0x180008443  mov     rcx, [rdi]
0x180008446  call    ?I_PinMapValidatePinComplexity@@YAHPEBUVCARD_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_PinMapValidatePinComplexity(VCARD_DATA const *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x18000844b  test    eax, eax
0x18000844d  jnz     short loc_1800084C2
0x18000844f  lea     edx, [rax+2]
0x180008452  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180008457  mov     edi, 80100004h
0x18000845c  mov     [rbp+57h+var_80], edi
0x18000845f  lea     rax, WPP_GLOBAL_Control
0x180008466  mov     rcx, cs:WPP_GLOBAL_Control
0x18000846d  cmp     rcx, rax
0x180008470  jz      short loc_1800084AD
0x180008472  test    byte ptr [rcx+1Ch], 1
0x180008476  jz      short loc_1800084AD
0x180008478  cmp     byte ptr [rcx+19h], 2
0x18000847c  jb      short loc_1800084AD
0x18000847e  mov     edx, 4Dh ; 'M'
0x180008483  lea     rax, aNewPinDoesNotM; "New PIN does not meet complexity requir"...
0x18000848a  mov     [rsp+0B0h+var_88], rax
0x18000848f  mov     [rsp+0B0h+var_90], edi
0x180008493  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000849a  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x1800084a1  mov     rcx, [rcx+10h]
0x1800084a5  call    WPP_SF_sDs
0x1800084aa  mov     edi, [rbp+57h+var_80]
0x1800084ad  test    rbx, rbx
0x1800084b0  jz      short loc_1800084BB
0x1800084b2  mov     rcx, rbx; SRWLock
0x1800084b5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800084bb  mov     ebx, edi
0x1800084bd  jmp     loc_180008588
0x1800084c2  mov     r9, r14
0x1800084c5  mov     r8, r15
0x1800084c8  mov     edx, esi
0x1800084ca  mov     rcx, [rdi]
0x1800084cd  call    ?I_ChangeReferenceData@@YAKPEAUVCARD_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@2@Z; I_ChangeReferenceData(VCARD_DATA *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x1800084d2  mov     [rbp+57h+var_80], eax
0x1800084d5  test    eax, eax
0x1800084d7  jz      short loc_18000851F
0x1800084d9  mov     edx, 2
0x1800084de  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800084e3  lea     rax, WPP_GLOBAL_Control
0x1800084ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084f1  cmp     rcx, rax
0x1800084f4  jz      short loc_1800084AA
0x1800084f6  test    byte ptr [rcx+1Ch], 1
0x1800084fa  jz      short loc_1800084AA
0x1800084fc  cmp     byte ptr [rcx+19h], 2
0x180008500  jb      short loc_1800084AA
0x180008502  mov     edx, 4Eh ; 'N'
0x180008507  lea     rax, aUnableToChange; "Unable to change PIN"
0x18000850e  mov     [rsp+0B0h+var_88], rax
0x180008513  mov     eax, [rbp+57h+var_80]
0x180008516  mov     [rsp+0B0h+var_90], eax
0x18000851a  jmp     loc_180008493
0x18000851f  mov     r8, r14
0x180008522  mov     edx, esi
0x180008524  mov     rcx, rdi
0x180008527  call    I_AuthenticatePin
0x18000852c  mov     [rbp+57h+var_80], eax
0x18000852f  test    eax, eax
0x180008531  jz      short loc_180008578
0x180008533  mov     edx, 2
0x180008538  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000853d  lea     rax, WPP_GLOBAL_Control
0x180008544  mov     rcx, cs:WPP_GLOBAL_Control
0x18000854b  cmp     rcx, rax
0x18000854e  jz      short loc_180008571
0x180008550  test    byte ptr [rcx+1Ch], 1
0x180008554  jz      short loc_180008571
0x180008556  cmp     byte ptr [rcx+19h], 3
0x18000855a  jb      short loc_180008571
0x18000855c  mov     edx, 4Fh ; 'O'
0x180008561  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x180008568  mov     rcx, [rcx+10h]
0x18000856c  call    WPP_SF_s
0x180008571  mov     [rbp+57h+var_80], 0
0x180008578  test    rbx, rbx
0x18000857b  jz      short loc_180008586
0x18000857d  mov     rcx, rbx; SRWLock
0x180008580  call    cs:__imp_ReleaseSRWLockExclusive
0x180008586  xor     ebx, ebx
0x180008588  lea     rcx, [rbp+57h+var_78]
0x18000858c  call    WppTraceUnwinder__lambda_c9712cbb2926dbaaea074c81e95892d9_______WppTraceUnwinder__lambda_c9712cbb2926dbaaea074c81e95892d9____
0x180008591  mov     eax, ebx
0x180008593  mov     rcx, [rbp+57h+var_38]
0x180008597  xor     rcx, rsp; StackCookie
0x18000859a  call    __security_check_cookie
0x18000859f  add     rsp, 88h
0x1800085a6  pop     r15
0x1800085a8  pop     r14
0x1800085aa  pop     rdi
0x1800085ab  pop     rsi
0x1800085ac  pop     rbx
0x1800085ad  pop     rbp
0x1800085ae  retn
```
