# SearchSettings::SearchSettingsHelper::CreateKeyAndSetSecurityDescriptorRecursively(wchar_t const *)

- ea: `0x180132ed8`
- end: `0x180133110`
- name: `?CreateKeyAndSetSecurityDescriptorRecursively@SearchSettingsHelper@SearchSettings@@SAJPEB_W@Z`
- size: `568`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180132d4c`

## callees

- `0x180005a74`
- `0x1800483f4`
- `0x1800e2988`
- `0x1800e34bc`
- `0x18011f7d8`
- `0x180132ed8`
- `0x18034a838`
- `0x180461b90`
- `0x180461be8`
- `0x180461fd4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180132f4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801330f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180132f4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801330f6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180132f14`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180132f14`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x180132f88`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x180132f88`

## string_xrefs

- `0x18013304e`: `Software\Microsoft\Windows\CurrentVersion\SearchSettings\WebSearchProviders\InstalledDates`
- `0x180132f2d`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`
- `0x180132fb3`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`
- `0x1801330d3`: `shellcommon\internal\shell\inc\Search\SearchSettingsHelper.h`

## pseudocode

```c
__int64 __fastcall SearchSettings::SearchSettingsHelper::CreateKeyAndSetSecurityDescriptorRecursively(
        const wchar_t *a1)
{
  BOOL v2; // ebx
  const char *v3; // r9
  int LastError; // ebx
  HLOCAL v5; // rcx
  __int64 v7; // rdx
  const wchar_t *v8; // rcx
  int v9; // eax
  HLOCAL v10; // rcx
  HLOCAL *p_hMem; // [rsp+20h] [rbp-50h] BYREF
  PSID Sid; // [rsp+28h] [rbp-48h] BYREF
  char v13; // [rsp+30h] [rbp-40h]
  struct _EXPLICIT_ACCESS_W v14; // [rsp+38h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  HLOCAL hMem; // [rsp+88h] [rbp+18h] BYREF

  hMem = 0;
  p_hMem = &hMem;
  Sid = 0;
  v13 = 1;
  v2 = ConvertStringSidToSidW(
         L"S-1-15-3-1024-1086922356-207614091-3724853071-841836187-4018695103-34218837-3164163255-155871754",
         &Sid);
  wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( !v2 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x70,
                  (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
                  v3);
LABEL_3:
    v5 = hMem;
    hMem = 0;
    if ( v5 )
      LocalFree(v5);
    return (unsigned int)LastError;
  }
  memset(&v14.grfInheritance + 1, 0, 36);
  v14.grfAccessPermissions = 196639;
  v14.grfAccessMode = GRANT_ACCESS;
  v14.grfInheritance = 2;
  BuildTrusteeWithSidW(&v14.Trustee, hMem);
  LastError = SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(
                L"Software\\Microsoft\\Windows\\CurrentVersion\\SearchSettings",
                a1,
                &v14);
  if ( LastError < 0 )
  {
    v7 = 120;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
      (const char *)(unsigned int)LastError,
      (int)p_hMem);
    goto LABEL_3;
  }
  LastError = SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(
                L"Software\\Microsoft\\Windows\\CurrentVersion\\SearchSettings\\Dynamic",
                a1,
                &v14);
  if ( LastError < 0 )
  {
    v7 = 121;
    goto LABEL_8;
  }
  LastError = SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(
                L"Software\\Microsoft\\Windows\\CurrentVersion\\SearchSettings\\Dynamic\\Current",
                a1,
                &v14);
  if ( LastError < 0 )
  {
    v7 = 122;
    goto LABEL_8;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_40979072>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_40979072>::GetImpl'::`2'::impl) )
  {
    LastError = SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\SearchSettings\\WebSearchProviders",
                  a1,
                  &v14);
    if ( LastError < 0 )
    {
      v7 = 125;
      goto LABEL_8;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54865932>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54865932>::GetImpl'::`2'::impl) )
  {
    LastError = SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\SearchSettings\\WebSearchProviders\\InstalledDates",
                  a1,
                  &v14);
    if ( LastError < 0 )
    {
      v7 = 130;
      goto LABEL_8;
    }
    LastError = SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\SearchSettings\\WebSearchProviders\\Index",
                  a1,
                  &v14);
    if ( LastError < 0 )
    {
      v7 = 131;
      goto LABEL_8;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56370341>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56370341>::GetImpl'::`2'::impl) )
  {
    LastError = SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\SearchSettings\\FileSearchProviders",
                  a1,
                  &v14);
    if ( LastError < 0 )
    {
      v7 = 136;
      goto LABEL_8;
    }
  }
  v9 = SearchSettings::SearchSettingsHelper::EnsureKeyPathAndSetSecurityDescriptor(v8, a1);
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Search\\SearchSettingsHelper.h",
      (const char *)(unsigned int)v9,
      (int)p_hMem);
  v10 = hMem;
  hMem = 0;
  if ( v10 )
    LocalFree(v10);
  return 0;
}

```

## disassembly

```asm
0x180132ed8  mov     [rsp-8+arg_0], rbx
0x180132edd  mov     [rsp-8+arg_10], rdi
0x180132ee2  push    rbp
0x180132ee3  mov     rbp, rsp
0x180132ee6  sub     rsp, 70h
0x180132eea  mov     rdi, rcx
0x180132eed  mov     [rbp+hMem], 0
0x180132ef5  lea     rax, [rbp+hMem]
0x180132ef9  mov     [rbp+var_50], rax
0x180132efd  mov     [rbp+Sid], 0
0x180132f05  mov     [rbp+var_40], 1
0x180132f09  lea     rdx, [rbp+Sid]; Sid
0x180132f0d  lea     rcx, StringSid; "S-1-15-3-1024-1086922356-207614091-3724"...
0x180132f14  call    cs:__imp_ConvertStringSidToSidW
0x180132f1a  mov     ebx, eax
0x180132f1c  lea     rcx, [rbp+var_50]
0x180132f20  call    ??1?$out_param_ptr_t@PEAPEAU_ACL@@V?$unique_ptr@U_ACL@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<_ACL * *,wistd::unique_ptr<_ACL,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180132f25  test    ebx, ebx
0x180132f27  jnz     short loc_180132F5C
0x180132f29  mov     rcx, [rbp+8]; this
0x180132f2d  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Sear"...
0x180132f34  lea     edx, [rbx+70h]; void *
0x180132f37  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180132f3c  mov     ebx, eax
0x180132f3e  mov     rcx, [rbp+hMem]; hMem
0x180132f42  mov     [rbp+hMem], 0
0x180132f4a  test    rcx, rcx
0x180132f4d  jz      short loc_180132F55
0x180132f4f  call    cs:__imp_LocalFree
0x180132f55  mov     eax, ebx
0x180132f57  jmp     loc_1801330FE
0x180132f5c  xorps   xmm0, xmm0
0x180132f5f  movups  xmmword ptr [rbp+var_38.grfAccessPermissions], xmm0
0x180132f63  movups  xmmword ptr [rbp+var_38.Trustee.pMultipleTrustee], xmm0
0x180132f67  movups  xmmword ptr [rbp+var_38.Trustee.TrusteeType], xmm0
0x180132f6b  mov     [rbp+var_38.grfAccessPermissions], 3001Fh
0x180132f72  mov     [rbp+var_38.grfAccessMode], 1
0x180132f79  mov     [rbp+var_38.grfInheritance], 2
0x180132f80  mov     rdx, [rbp+hMem]; pSid
0x180132f84  lea     rcx, [rbp+var_38.Trustee]; pTrustee
0x180132f88  call    cs:__imp_BuildTrusteeWithSidW
0x180132f8e  lea     r8, [rbp+var_38]; struct _EXPLICIT_ACCESS_W *
0x180132f92  mov     rdx, rdi; wchar_t *
0x180132f95  lea     rcx, aSoftwareMicros_37; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180132f9c  call    ?AddAceToKeyRecursively@SearchSettingsHelper@SearchSettings@@CAJPEB_W0PEAU_EXPLICIT_ACCESS_W@@@Z; SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(wchar_t const *,wchar_t const *,_EXPLICIT_ACCESS_W *)
0x180132fa1  mov     ebx, eax
0x180132fa3  test    eax, eax
0x180132fa5  jns     short loc_180132FC4
0x180132fa7  mov     edx, 78h ; 'x'; void *
0x180132fac  mov     rcx, [rbp+8]; this
0x180132fb0  mov     r9d, ebx; char *
0x180132fb3  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Sear"...
0x180132fba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180132fbf  jmp     loc_180132F3E
0x180132fc4  lea     r8, [rbp+var_38]; struct _EXPLICIT_ACCESS_W *
0x180132fc8  mov     rdx, rdi; wchar_t *
0x180132fcb  lea     rcx, aSoftwareMicros_27; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180132fd2  call    ?AddAceToKeyRecursively@SearchSettingsHelper@SearchSettings@@CAJPEB_W0PEAU_EXPLICIT_ACCESS_W@@@Z; SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(wchar_t const *,wchar_t const *,_EXPLICIT_ACCESS_W *)
0x180132fd7  mov     ebx, eax
0x180132fd9  test    eax, eax
0x180132fdb  jns     short loc_180132FE4
0x180132fdd  mov     edx, 79h ; 'y'
0x180132fe2  jmp     short loc_180132FAC
0x180132fe4  lea     r8, [rbp+var_38]; struct _EXPLICIT_ACCESS_W *
0x180132fe8  mov     rdx, rdi; wchar_t *
0x180132feb  lea     rcx, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180132ff2  call    ?AddAceToKeyRecursively@SearchSettingsHelper@SearchSettings@@CAJPEB_W0PEAU_EXPLICIT_ACCESS_W@@@Z; SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(wchar_t const *,wchar_t const *,_EXPLICIT_ACCESS_W *)
0x180132ff7  mov     ebx, eax
0x180132ff9  test    eax, eax
0x180132ffb  jns     short loc_180133004
0x180132ffd  mov     edx, 7Ah ; 'z'
0x180133002  jmp     short loc_180132FAC
0x180133004  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_40979072@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_40979072@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40979072> `wil::Feature<__WilFeatureTraits_Feature_40979072>::GetImpl(void)'::`2'::impl
0x18013300b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_40979072@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40979072>::__private_IsEnabled(void)
0x180133010  test    al, al
0x180133012  jz      short loc_180133037
0x180133014  lea     r8, [rbp+var_38]; struct _EXPLICIT_ACCESS_W *
0x180133018  mov     rdx, rdi; wchar_t *
0x18013301b  lea     rcx, aSoftwareMicros_62; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180133022  call    ?AddAceToKeyRecursively@SearchSettingsHelper@SearchSettings@@CAJPEB_W0PEAU_EXPLICIT_ACCESS_W@@@Z; SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(wchar_t const *,wchar_t const *,_EXPLICIT_ACCESS_W *)
0x180133027  mov     ebx, eax
0x180133029  test    eax, eax
0x18013302b  jns     short loc_180133037
0x18013302d  mov     edx, 7Dh ; '}'
0x180133032  jmp     loc_180132FAC
0x180133037  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54865932@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54865932@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54865932> `wil::Feature<__WilFeatureTraits_Feature_54865932>::GetImpl(void)'::`2'::impl
0x18013303e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54865932@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54865932>::__private_IsEnabled(void)
0x180133043  test    al, al
0x180133045  jz      short loc_18013308D
0x180133047  lea     r8, [rbp+var_38]; struct _EXPLICIT_ACCESS_W *
0x18013304b  mov     rdx, rdi; wchar_t *
0x18013304e  lea     rcx, aSoftwareMicros_21; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180133055  call    ?AddAceToKeyRecursively@SearchSettingsHelper@SearchSettings@@CAJPEB_W0PEAU_EXPLICIT_ACCESS_W@@@Z; SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(wchar_t const *,wchar_t const *,_EXPLICIT_ACCESS_W *)
0x18013305a  mov     ebx, eax
0x18013305c  test    eax, eax
0x18013305e  jns     short loc_18013306A
0x180133060  mov     edx, 82h
0x180133065  jmp     loc_180132FAC
0x18013306a  lea     r8, [rbp+var_38]; struct _EXPLICIT_ACCESS_W *
0x18013306e  mov     rdx, rdi; wchar_t *
0x180133071  lea     rcx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180133078  call    ?AddAceToKeyRecursively@SearchSettingsHelper@SearchSettings@@CAJPEB_W0PEAU_EXPLICIT_ACCESS_W@@@Z; SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(wchar_t const *,wchar_t const *,_EXPLICIT_ACCESS_W *)
0x18013307d  mov     ebx, eax
0x18013307f  test    eax, eax
0x180133081  jns     short loc_18013308D
0x180133083  mov     edx, 83h
0x180133088  jmp     loc_180132FAC
0x18013308d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56370341@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56370341@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56370341> `wil::Feature<__WilFeatureTraits_Feature_56370341>::GetImpl(void)'::`2'::impl
0x180133094  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56370341@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56370341>::__private_IsEnabled(void)
0x180133099  test    al, al
0x18013309b  jz      short loc_1801330C0
0x18013309d  lea     r8, [rbp+var_38]; struct _EXPLICIT_ACCESS_W *
0x1801330a1  mov     rdx, rdi; wchar_t *
0x1801330a4  lea     rcx, aSoftwareMicros_64; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801330ab  call    ?AddAceToKeyRecursively@SearchSettingsHelper@SearchSettings@@CAJPEB_W0PEAU_EXPLICIT_ACCESS_W@@@Z; SearchSettings::SearchSettingsHelper::AddAceToKeyRecursively(wchar_t const *,wchar_t const *,_EXPLICIT_ACCESS_W *)
0x1801330b0  mov     ebx, eax
0x1801330b2  test    eax, eax
0x1801330b4  jns     short loc_1801330C0
0x1801330b6  mov     edx, 88h
0x1801330bb  jmp     loc_180132FAC
0x1801330c0  mov     rdx, rdi; wchar_t *
0x1801330c3  call    ?EnsureKeyPathAndSetSecurityDescriptor@SearchSettingsHelper@SearchSettings@@SAJPEB_W0@Z; SearchSettings::SearchSettingsHelper::EnsureKeyPathAndSetSecurityDescriptor(wchar_t const *,wchar_t const *)
0x1801330c8  mov     rcx, [rbp+8]; this
0x1801330cc  test    eax, eax
0x1801330ce  jns     short loc_1801330E5
0x1801330d0  mov     r9d, eax; char *
0x1801330d3  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Sear"...
0x1801330da  mov     edx, 8Bh; void *
0x1801330df  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801330e4  nop
0x1801330e5  mov     rcx, [rbp+hMem]; hMem
0x1801330e9  mov     [rbp+hMem], 0
0x1801330f1  test    rcx, rcx
0x1801330f4  jz      short loc_1801330FC
0x1801330f6  call    cs:__imp_LocalFree
0x1801330fc  xor     eax, eax
0x1801330fe  lea     r11, [rsp+70h+var_s0]
0x180133103  mov     rbx, [r11+10h]
0x180133107  mov     rdi, [r11+20h]
0x18013310b  mov     rsp, r11
0x18013310e  pop     rbp
0x18013310f  retn
```
