# get_locale(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)

- ea: `0x140003414`
- end: `0x140003569`
- name: `?get_locale@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140003570`

## callees

- `0x140002a00`
- `0x140002a80`
- `0x140003414`
- `0x140016c8c`
- `0x140016ce4`
- `0x140026c20`
- `0x140030510`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x140003488`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1400034d3`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x140003488`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1400034d3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140003442`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140003442`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000353b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14000353b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x140003414  mov     [rsp-8+arg_10], rbx
0x140003419  mov     [rsp-8+arg_18], rdi
0x14000341e  push    rbp
0x14000341f  mov     rbp, rsp
0x140003422  sub     rsp, 60h
0x140003426  mov     rax, cs:__security_cookie
0x14000342d  xor     rax, rsp
0x140003430  mov     [rbp+var_10], rax
0x140003434  mov     rbx, rcx
0x140003437  mov     qword ptr [rbp+pulNumLanguages], rcx
0x14000343b  mov     rdi, [rbp+8]
0x14000343f  mov     rcx, [rdx]; hToken
0x140003442  call    cs:__imp_ImpersonateLoggedOnUser
0x140003449  nop     dword ptr [rax+rax+00h]
0x14000344e  test    eax, eax
0x140003450  jnz     short loc_140003467
0x140003452  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140003459  mov     edx, 156h; void *
0x14000345e  mov     rcx, rdi; this
0x140003461  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140003467  mov     [rbp+var_3B], 1
0x14000346b  mov     [rbp+pulNumLanguages], 0
0x140003472  mov     [rbp+pcchLanguagesBuffer], 0
0x140003479  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x14000347d  xor     r8d, r8d; pwszLanguagesBuffer
0x140003480  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x140003484  lea     ecx, [r8+38h]; dwFlags
0x140003488  call    cs:__imp_GetThreadPreferredUILanguages
0x14000348f  nop     dword ptr [rax+rax+00h]
0x140003494  mov     eax, 20h ; ' '
0x140003499  mov     [rbp+var_40], ax
0x14000349d  xorps   xmm0, xmm0
0x1400034a0  movdqu  xmmword ptr [rbp+pwszLanguagesBuffer], xmm0
0x1400034a5  mov     [rbp+var_18], 0
0x1400034ad  mov     edx, [rbp+pcchLanguagesBuffer]
0x1400034b0  lea     r8, [rbp+var_40]
0x1400034b4  lea     rcx, [rbp+pwszLanguagesBuffer]
0x1400034b8  call    ??$_Construct_n@AEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBG@Z; std::vector<ushort>::_Construct_n<ushort const &>(unsigned __int64,ushort const &)
0x1400034bd  nop
0x1400034be  mov     rdi, [rbp+8]
0x1400034c2  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1400034c6  mov     r8, [rbp+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x1400034ca  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x1400034ce  mov     ecx, 38h ; '8'; dwFlags
0x1400034d3  call    cs:__imp_GetThreadPreferredUILanguages
0x1400034da  nop     dword ptr [rax+rax+00h]
0x1400034df  test    eax, eax
0x1400034e1  jnz     short loc_1400034F8
0x1400034e3  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x1400034ea  mov     edx, 15Dh; void *
0x1400034ef  mov     rcx, rdi; this
0x1400034f2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1400034f8  mov     r8, [rbp+pwszLanguagesBuffer+8]
0x1400034fc  mov     rdx, [rbp+pwszLanguagesBuffer]
0x140003500  xorps   xmm0, xmm0
0x140003503  movups  xmmword ptr [rbx], xmm0
0x140003506  mov     qword ptr [rbx+10h], 0
0x14000350e  mov     qword ptr [rbx+18h], 0
0x140003516  mov     rcx, rbx
0x140003519  cmp     rdx, r8
0x14000351c  jnz     short loc_140003525
0x14000351e  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x140003523  jmp     short loc_140003531
0x140003525  sub     r8, rdx
0x140003528  sar     r8, 1
0x14000352b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140003530  nop
0x140003531  lea     rcx, [rbp+pwszLanguagesBuffer]
0x140003535  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x14000353a  nop
0x14000353b  call    cs:__imp_RevertToSelf
0x140003542  nop     dword ptr [rax+rax+00h]
0x140003547  mov     rax, rbx
0x14000354a  mov     rcx, [rbp+var_10]
0x14000354e  xor     rcx, rsp; StackCookie
0x140003551  call    __security_check_cookie
0x140003556  lea     r11, [rsp+60h+var_s0]
0x14000355b  mov     rbx, [r11+20h]
0x14000355f  mov     rdi, [r11+28h]
0x140003563  mov     rsp, r11
0x140003566  pop     rbp
0x140003567  retn
```
