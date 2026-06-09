# I_UnblockPinLocking(VCHANNEL_DATA *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &)

- ea: `0x18000b85c`
- end: `0x18000bb0e`
- name: `?I_UnblockPinLocking@@YAKPEAUVCHANNEL_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@2@Z`
- size: `690`
- prototype: `__int64 __fastcall(__int64 *, unsigned int, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18002db00`

## callees

- `0x180001ec0`
- `0x180006804`
- `0x1800077fc`
- `0x1800079b8`
- `0x180007bcc`
- `0x18000a81c`
- `0x18000b85c`
- `0x18000bc48`
- `0x18000c198`
- `0x180013e58`
- `0x180029644`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b9e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bae1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b9e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bae1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b902`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b902`

## string_xrefs

- `0x18000b9aa`: `New PIN does not meet complexity requirement`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall I_UnblockPinLocking(__int64 *a1, unsigned int a2, __int64 a3, _QWORD *a4)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  RTL_SRWLOCK *v9; // rbx
  __int64 v10; // rcx
  unsigned int v11; // esi
  _QWORD *v12; // rcx
  int v13; // edx
  const char *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int Auth; // [rsp+30h] [rbp-39h] BYREF
  __int64 *v20; // [rsp+38h] [rbp-31h] BYREF
  int v21; // [rsp+40h] [rbp-29h] BYREF
  __int64 **v22; // [rsp+48h] [rbp-21h] BYREF
  __int16 v23; // [rsp+50h] [rbp-19h]
  _QWORD *v24; // [rsp+58h] [rbp-11h] BYREF
  _QWORD v25[4]; // [rsp+60h] [rbp-9h] BYREF
  char v26[24]; // [rsp+80h] [rbp+17h] BYREF

  v20 = a1;
  Auth = 0;
  v21 = 0;
  strcpy(v26, "I_UnblockPinLocking");
  v25[0] = v26;
  v25[1] = &v21;
  v25[2] = &Auth;
  lambda_f7112acefc520f67fb8d9967532f83ee_::operator()(v25);
  v21 = 1;
  v24 = v25;
  if ( !v20 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  if ( a2 - 1 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  v9 = (RTL_SRWLOCK *)(*v20 + 72);
  AcquireSRWLockExclusive(v9);
  v25[3] = v9;
  if ( !(unsigned int)I_VCardIsUsingPuk((const struct VCARD_DATA *)*v20) )
  {
    WppTraceIndent(v10, 2);
    v11 = -2146435038;
    Auth = -2146435038;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 81;
      v14 = "PUK based PIN unblock not supported";
LABEL_15:
      WPP_SF_sDs(
        v12[2],
        v13,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        v11,
        (__int64)v14);
LABEL_16:
      v11 = Auth;
      goto LABEL_17;
    }
    goto LABEL_17;
  }
  if ( !I_PinMapValidatePinComplexity(*v20, a2, a4) )
  {
    WppTraceIndent(v15, 2);
    v11 = -2146435068;
    Auth = -2146435068;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 82;
      v14 = "New PIN does not meet complexity requirement";
      goto LABEL_15;
    }
LABEL_17:
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    goto LABEL_33;
  }
  Auth = I_AuthenticatePinAndLoadAuth(v20, 2, a3);
  if ( Auth )
  {
    WppTraceIndent(v16, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        83,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        Auth,
        (__int64)"Unable to authenticate PUK");
    }
    goto LABEL_16;
  }
  v22 = &v20;
  v23 = 258;
  Auth = I_SetReferenceData(v20, a2, (__int64)a4);
  if ( Auth )
  {
    WppTraceIndent(v17, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        Auth,
        (__int64)"Unable to unblock the user PIN");
    }
    v11 = Auth;
    wil::details::ScopeExitFnGuard__lambda_e4819bc7d4d7c528f40e1c7e2380f75e___::operator()(&v22);
    goto LABEL_17;
  }
  wil::details::ScopeExitFnGuard__lambda_e4819bc7d4d7c528f40e1c7e2380f75e___::operator()(&v22);
  if ( v9 )
    ReleaseSRWLockExclusive(v9);
  v11 = 0;
LABEL_33:
  WppTraceUnwinder__lambda_f7112acefc520f67fb8d9967532f83ee____::_WppTraceUnwinder__lambda_f7112acefc520f67fb8d9967532f83ee____(&v24);
  return v11;
}

```

## disassembly

```asm
0x18000b85c  push    rbp
0x18000b85e  push    rbx
0x18000b85f  push    rsi
0x18000b860  push    rdi
0x18000b861  push    r14
0x18000b863  lea     rbp, [rsp-37h]
0x18000b868  sub     rsp, 0A0h
0x18000b86f  mov     rax, cs:__security_cookie
0x18000b876  xor     rax, rsp
0x18000b879  mov     [rbp+57h+var_28], rax
0x18000b87d  mov     r14, r9
0x18000b880  mov     rdi, r8
0x18000b883  mov     esi, edx
0x18000b885  mov     [rbp+57h+var_88], rcx
0x18000b889  mov     [rbp+57h+var_90], 0
0x18000b890  mov     [rbp+57h+var_80], 0
0x18000b897  movups  xmm0, xmmword ptr cs:aIUnblockpinloc; "I_UnblockPinLocking"
0x18000b89e  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18000b8a2  mov     eax, dword ptr cs:aIUnblockpinloc+10h; "ing"
0x18000b8a8  mov     dword ptr [rbp+57h+var_40+10h], eax
0x18000b8ab  lea     rax, [rbp+57h+var_40]
0x18000b8af  mov     [rbp+57h+var_60], rax
0x18000b8b3  lea     rax, [rbp+57h+var_80]
0x18000b8b7  mov     [rbp+57h+var_58], rax
0x18000b8bb  lea     rax, [rbp+57h+var_90]
0x18000b8bf  mov     [rbp+57h+var_50], rax
0x18000b8c3  lea     rcx, [rbp+57h+var_60]
0x18000b8c7  call    _lambda_f7112acefc520f67fb8d9967532f83ee___operator__
0x18000b8cc  mov     [rbp+57h+var_80], 1
0x18000b8d3  lea     rax, [rbp+57h+var_60]
0x18000b8d7  mov     [rbp+57h+var_68], rax
0x18000b8db  cmp     [rbp+57h+var_88], 0
0x18000b8e0  jnz     short loc_18000B8E7
0x18000b8e2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b8e7  lea     eax, [rsi-1]
0x18000b8ea  cmp     eax, 1
0x18000b8ed  jbe     short loc_18000B8F4
0x18000b8ef  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b8f4  mov     rax, [rbp+57h+var_88]
0x18000b8f8  mov     rbx, [rax]
0x18000b8fb  add     rbx, 48h ; 'H'
0x18000b8ff  mov     rcx, rbx; SRWLock
0x18000b902  call    cs:__imp_AcquireSRWLockExclusive
0x18000b908  mov     [rbp+57h+var_48], rbx
0x18000b90c  mov     rcx, [rbp+57h+var_88]
0x18000b910  mov     rcx, [rcx]; struct VCARD_DATA *
0x18000b913  call    ?I_VCardIsUsingPuk@@YAHPEBUVCARD_DATA@@@Z; I_VCardIsUsingPuk(VCARD_DATA const *)
0x18000b918  test    eax, eax
0x18000b91a  jnz     short loc_18000B961
0x18000b91c  lea     edi, [rax+2]
0x18000b91f  mov     edx, edi
0x18000b921  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000b926  mov     esi, 80100022h
0x18000b92b  mov     [rbp+57h+var_90], esi
0x18000b92e  lea     rax, WPP_GLOBAL_Control
0x18000b935  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b93c  cmp     rcx, rax
0x18000b93f  jz      loc_18000B9D4
0x18000b945  test    byte ptr [rcx+1Ch], 1
0x18000b949  jz      loc_18000B9D4
0x18000b94f  cmp     [rcx+19h], dil
0x18000b953  jb      short loc_18000B9D4
0x18000b955  lea     edx, [rdi+4Fh]
0x18000b958  lea     rax, aPukBasedPinUnb; "PUK based PIN unblock not supported"
0x18000b95f  jmp     short loc_18000B9B1
0x18000b961  mov     r8, r14
0x18000b964  mov     edx, esi
0x18000b966  mov     rcx, [rbp+57h+var_88]
0x18000b96a  mov     rcx, [rcx]
0x18000b96d  call    ?I_PinMapValidatePinComplexity@@YAHPEBUVCARD_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_PinMapValidatePinComplexity(VCARD_DATA const *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x18000b972  test    eax, eax
0x18000b974  jnz     short loc_18000B9EB
0x18000b976  lea     edi, [rax+2]
0x18000b979  mov     edx, edi
0x18000b97b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000b980  mov     esi, 80100004h
0x18000b985  mov     [rbp+57h+var_90], esi
0x18000b988  lea     rax, WPP_GLOBAL_Control
0x18000b98f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b996  cmp     rcx, rax
0x18000b999  jz      short loc_18000B9D4
0x18000b99b  test    byte ptr [rcx+1Ch], 1
0x18000b99f  jz      short loc_18000B9D4
0x18000b9a1  cmp     [rcx+19h], dil
0x18000b9a5  jb      short loc_18000B9D4
0x18000b9a7  lea     edx, [rdi+50h]
0x18000b9aa  lea     rax, aNewPinDoesNotM; "New PIN does not meet complexity requir"...
0x18000b9b1  mov     [rsp+0C0h+var_98], rax
0x18000b9b6  mov     [rsp+0C0h+var_A0], esi
0x18000b9ba  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000b9c1  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000b9c8  mov     rcx, [rcx+10h]
0x18000b9cc  call    WPP_SF_sDs
0x18000b9d1  mov     esi, [rbp+57h+var_90]
0x18000b9d4  test    rbx, rbx
0x18000b9d7  jz      loc_18000BAE9
0x18000b9dd  mov     rcx, rbx; SRWLock
0x18000b9e0  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b9e6  jmp     loc_18000BAE9
0x18000b9eb  mov     r8, rdi
0x18000b9ee  mov     edi, 2
0x18000b9f3  mov     edx, edi
0x18000b9f5  mov     rcx, [rbp+57h+var_88]
0x18000b9f9  call    I_AuthenticatePinAndLoadAuth
0x18000b9fe  mov     [rbp+57h+var_90], eax
0x18000ba01  test    eax, eax
0x18000ba03  jz      short loc_18000BA46
0x18000ba05  mov     edx, edi
0x18000ba07  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000ba0c  lea     rax, WPP_GLOBAL_Control
0x18000ba13  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba1a  cmp     rcx, rax
0x18000ba1d  jz      short loc_18000B9D1
0x18000ba1f  test    byte ptr [rcx+1Ch], 1
0x18000ba23  jz      short loc_18000B9D1
0x18000ba25  cmp     [rcx+19h], dil
0x18000ba29  jb      short loc_18000B9D1
0x18000ba2b  lea     edx, [rdi+51h]
0x18000ba2e  lea     rax, aUnableToAuthen; "Unable to authenticate PUK"
0x18000ba35  mov     [rsp+0C0h+var_98], rax
0x18000ba3a  mov     eax, [rbp+57h+var_90]
0x18000ba3d  mov     [rsp+0C0h+var_A0], eax
0x18000ba41  jmp     loc_18000B9BA
0x18000ba46  lea     rax, [rbp+57h+var_88]
0x18000ba4a  mov     [rbp+57h+var_78], rax
0x18000ba4e  mov     [rbp+57h+var_70], 102h
0x18000ba54  mov     r8, r14
0x18000ba57  mov     edx, esi
0x18000ba59  mov     rcx, [rbp+57h+var_88]
0x18000ba5d  call    ?I_SetReferenceData@@YAKPEAUVCHANNEL_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_SetReferenceData(VCHANNEL_DATA *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x18000ba62  mov     [rbp+57h+var_90], eax
0x18000ba65  test    eax, eax
0x18000ba67  jz      short loc_18000BACF
0x18000ba69  mov     edx, edi
0x18000ba6b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000ba70  lea     rax, WPP_GLOBAL_Control
0x18000ba77  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba7e  cmp     rcx, rax
0x18000ba81  jz      short loc_18000BABE
0x18000ba83  test    byte ptr [rcx+1Ch], 1
0x18000ba87  jz      short loc_18000BABE
0x18000ba89  cmp     [rcx+19h], dil
0x18000ba8d  jb      short loc_18000BABE
0x18000ba8f  mov     edx, 54h ; 'T'
0x18000ba94  lea     rax, aUnableToUnbloc; "Unable to unblock the user PIN"
0x18000ba9b  mov     [rsp+0C0h+var_98], rax
0x18000baa0  mov     eax, [rbp+57h+var_90]
0x18000baa3  mov     [rsp+0C0h+var_A0], eax
0x18000baa7  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000baae  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000bab5  mov     rcx, [rcx+10h]
0x18000bab9  call    WPP_SF_sDs
0x18000babe  mov     esi, [rbp+57h+var_90]
0x18000bac1  lea     rcx, [rbp+57h+var_78]
0x18000bac5  call    wil__details__ScopeExitFnGuard__lambda_e4819bc7d4d7c528f40e1c7e2380f75e_____operator__
0x18000baca  jmp     loc_18000B9D4
0x18000bacf  lea     rcx, [rbp+57h+var_78]
0x18000bad3  call    wil__details__ScopeExitFnGuard__lambda_e4819bc7d4d7c528f40e1c7e2380f75e_____operator__
0x18000bad8  nop
0x18000bad9  test    rbx, rbx
0x18000badc  jz      short loc_18000BAE7
0x18000bade  mov     rcx, rbx; SRWLock
0x18000bae1  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bae7  xor     esi, esi
0x18000bae9  lea     rcx, [rbp+57h+var_68]
0x18000baed  call    WppTraceUnwinder__lambda_f7112acefc520f67fb8d9967532f83ee_______WppTraceUnwinder__lambda_f7112acefc520f67fb8d9967532f83ee____
0x18000baf2  mov     eax, esi
0x18000baf4  mov     rcx, [rbp+57h+var_28]
0x18000baf8  xor     rcx, rsp; StackCookie
0x18000bafb  call    __security_check_cookie
0x18000bb00  add     rsp, 0A0h
0x18000bb07  pop     r14
0x18000bb09  pop     rdi
0x18000bb0a  pop     rsi
0x18000bb0b  pop     rbx
0x18000bb0c  pop     rbp
0x18000bb0d  retn
```
