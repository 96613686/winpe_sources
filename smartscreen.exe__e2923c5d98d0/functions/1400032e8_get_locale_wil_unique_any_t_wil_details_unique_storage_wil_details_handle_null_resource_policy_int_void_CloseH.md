# get_locale(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)

- ea: `0x1400032e8`
- end: `0x140003424`
- name: `?get_locale@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `316`
- prototype: `__int64 __fastcall(__int64, HANDLE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000342c`

## callees

- `0x1400028ec`
- `0x140002968`
- `0x1400032e8`
- `0x14001609c`
- `0x1400160f0`
- `0x140025aa0`
- `0x14002f250`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x140003356`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x14000339b`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x140003356`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x14000339b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140003316`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140003316`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400033fd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400033fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall get_locale(__int64 a1, HANDLE *a2)
{
  const char *v3; // r9
  const char *v4; // r9
  PZZWSTR v5; // r8
  PZZWSTR v6; // rdx
  __int16 v8[2]; // [rsp+20h] [rbp-40h] BYREF
  char v9; // [rsp+25h] [rbp-3Bh]
  ULONG pcchLanguagesBuffer; // [rsp+2Ch] [rbp-34h] BYREF
  ULONG pulNumLanguages[2]; // [rsp+30h] [rbp-30h] BYREF
  PZZWSTR pwszLanguagesBuffer[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v13; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  *(_QWORD *)pulNumLanguages = a1;
  if ( !ImpersonateLoggedOnUser(*a2) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x156,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
      v3);
  v9 = 1;
  pulNumLanguages[0] = 0;
  pcchLanguagesBuffer = 0;
  GetThreadPreferredUILanguages(0x38u, pulNumLanguages, 0, &pcchLanguagesBuffer);
  v8[0] = 32;
  *(_OWORD *)pwszLanguagesBuffer = 0;
  v13 = 0;
  std::vector<unsigned short>::_Construct_n<unsigned short const &>(pwszLanguagesBuffer, pcchLanguagesBuffer, v8);
  if ( !GetThreadPreferredUILanguages(0x38u, pulNumLanguages, pwszLanguagesBuffer[0], &pcchLanguagesBuffer) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
      v4);
  v5 = pwszLanguagesBuffer[1];
  v6 = pwszLanguagesBuffer[0];
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  if ( v6 == v5 )
    std::wstring::_Construct_empty(a1);
  else
    std::wstring::_Construct<1,unsigned short const *>(a1, v6, v5 - v6);
  std::vector<unsigned short>::_Tidy(pwszLanguagesBuffer);
  RevertToSelf();
  return a1;
}

```

## disassembly

```asm
0x1400032e8  mov     [rsp-8+arg_10], rbx
0x1400032ed  mov     [rsp-8+arg_18], rdi
0x1400032f2  push    rbp
0x1400032f3  mov     rbp, rsp
0x1400032f6  sub     rsp, 60h
0x1400032fa  mov     rax, cs:__security_cookie
0x140003301  xor     rax, rsp
0x140003304  mov     [rbp+var_10], rax
0x140003308  mov     rbx, rcx
0x14000330b  mov     qword ptr [rbp+pulNumLanguages], rcx
0x14000330f  mov     rdi, [rbp+8]
0x140003313  mov     rcx, [rdx]; hToken
0x140003316  call    cs:__imp_ImpersonateLoggedOnUser
0x14000331c  test    eax, eax
0x14000331e  jnz     short loc_140003335
0x140003320  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140003327  mov     edx, 156h; void *
0x14000332c  mov     rcx, rdi; this
0x14000332f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140003335  mov     [rbp+var_3B], 1
0x140003339  mov     [rbp+pulNumLanguages], 0
0x140003340  mov     [rbp+pcchLanguagesBuffer], 0
0x140003347  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x14000334b  xor     r8d, r8d; pwszLanguagesBuffer
0x14000334e  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x140003352  lea     ecx, [r8+38h]; dwFlags
0x140003356  call    cs:__imp_GetThreadPreferredUILanguages
0x14000335c  mov     eax, 20h ; ' '
0x140003361  mov     [rbp+var_40], ax
0x140003365  xorps   xmm0, xmm0
0x140003368  movdqu  xmmword ptr [rbp+pwszLanguagesBuffer], xmm0
0x14000336d  mov     [rbp+var_18], 0
0x140003375  mov     edx, [rbp+pcchLanguagesBuffer]
0x140003378  lea     r8, [rbp+var_40]
0x14000337c  lea     rcx, [rbp+pwszLanguagesBuffer]
0x140003380  call    ??$_Construct_n@AEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBG@Z; std::vector<ushort>::_Construct_n<ushort const &>(unsigned __int64,ushort const &)
0x140003385  nop
0x140003386  mov     rdi, [rbp+8]
0x14000338a  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x14000338e  mov     r8, [rbp+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x140003392  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x140003396  mov     ecx, 38h ; '8'; dwFlags
0x14000339b  call    cs:__imp_GetThreadPreferredUILanguages
0x1400033a1  test    eax, eax
0x1400033a3  jnz     short loc_1400033BA
0x1400033a5  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400033ac  mov     edx, 15Dh; void *
0x1400033b1  mov     rcx, rdi; this
0x1400033b4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1400033ba  mov     r8, [rbp+pwszLanguagesBuffer+8]
0x1400033be  mov     rdx, [rbp+pwszLanguagesBuffer]
0x1400033c2  xorps   xmm0, xmm0
0x1400033c5  movups  xmmword ptr [rbx], xmm0
0x1400033c8  mov     qword ptr [rbx+10h], 0
0x1400033d0  mov     qword ptr [rbx+18h], 0
0x1400033d8  mov     rcx, rbx
0x1400033db  cmp     rdx, r8
0x1400033de  jnz     short loc_1400033E7
0x1400033e0  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1400033e5  jmp     short loc_1400033F3
0x1400033e7  sub     r8, rdx
0x1400033ea  sar     r8, 1
0x1400033ed  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400033f2  nop
0x1400033f3  lea     rcx, [rbp+pwszLanguagesBuffer]
0x1400033f7  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1400033fc  nop
0x1400033fd  call    cs:__imp_RevertToSelf
0x140003403  mov     rax, rbx
0x140003406  mov     rcx, [rbp+var_10]
0x14000340a  xor     rcx, rsp; StackCookie
0x14000340d  call    __security_check_cookie
0x140003412  lea     r11, [rsp+60h+var_s0]
0x140003417  mov     rbx, [r11+20h]
0x14000341b  mov     rdi, [r11+28h]
0x14000341f  mov     rsp, r11
0x140003422  pop     rbp
0x140003423  retn
```
