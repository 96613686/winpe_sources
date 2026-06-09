# CLockScreenHistory::s_GetCreativeLockScreenPath(ushort const *,ushort * *,ushort * *,ushort * *,bool *)

- ea: `0x18000bdcc`
- end: `0x18000c1b0`
- name: `?s_GetCreativeLockScreenPath@CLockScreenHistory@@SAJPEBGPEAPEAG11PEA_N@Z`
- size: `996`
- prototype: `__int64 __usercall@<rax>(CreativeFramework::LockScreenCreativeConfigHelpers *this@<rcx>, unsigned __int16 **@<rdx>, unsigned __int16 **@<r8>, unsigned __int16 **@<r9>, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000c600`

## callees

- `0x18000a490`
- `0x18000b700`
- `0x18000bdcc`
- `0x18000c1b8`
- `0x18000da00`
- `0x180036c2c`
- `0x18003729c`
- `0x18003c554`
- `0x180054130`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c12a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c12a`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000c025`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000c048`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000c088`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000c0a5`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000c025`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000c048`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000c088`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000c0a5`
- `SHELL32!__imp_PathComparePaths` at `0x18000c06a`
- `SHELL32!__imp_PathComparePaths` at `0x18000c0c3`
- `SHELL32!__imp_PathComparePaths` at `0x18000c06a`
- `SHELL32!__imp_PathComparePaths` at `0x18000c0c3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000bed8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000bed8`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000bf52`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000bf52`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000bfc2`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000bfc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CLockScreenHistory::s_GetCreativeLockScreenPath(
        CreativeFramework::LockScreenCreativeConfigHelpers *this,
        unsigned __int16 **a2,
        const WCHAR **a3,
        unsigned __int16 **a4,
        bool *a5)
{
  int v8; // eax
  unsigned int LastError; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  unsigned __int16 *v12; // r14
  const WCHAR *v13; // rdi
  const WCHAR *v14; // rsi
  const char *v15; // r9
  const char *v16; // r9
  int BasicProfileFolderPath; // eax
  __int64 v18; // rdx
  __int64 v19; // r9
  int ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  LPWSTR ReferencedDomainNamea; // [rsp+20h] [rbp-E0h]
  bool *cchReferencedDomainName; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v24; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR v27; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR pszPathIn; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v29[4]; // [rsp+68h] [rbp-98h] BYREF
  DWORD v30; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int16 **v32; // [rsp+78h] [rbp-88h]
  bool *v33; // [rsp+80h] [rbp-80h]
  WCHAR v34[20]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Name[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v36[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _BYTE v38[528]; // [rsp+6E0h] [rbp+5E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+948h] [rbp+848h]

  v32 = a4;
  v33 = a5;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  LOBYTE(v24) = 0;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
  v27 = 0;
  pszPathIn = 0;
  *(_QWORD *)v29 = 0;
  v8 = CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(
         this,
         v29,
         (unsigned __int16 **)&pszPathIn,
         (unsigned __int16 **)&v27,
         &v24,
         cchReferencedDomainName);
  LastError = v8;
  if ( v8 < 0 )
  {
    v10 = (unsigned int)v8;
    v11 = 397;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)v10,
      ReferencedDomainName);
    goto LABEL_38;
  }
  v12 = *(unsigned __int16 **)v29;
  if ( !*(_QWORD *)v29 || !**(_WORD **)v29 )
  {
    v11 = 398;
    goto LABEL_36;
  }
  v13 = pszPathIn;
  if ( !pszPathIn || !*pszPathIn )
  {
    v11 = 399;
    goto LABEL_36;
  }
  v14 = v27;
  if ( !v27 || !*v27 )
  {
    v11 = 400;
LABEL_36:
    LastError = -2147024894;
    v10 = 2147942402LL;
    goto LABEL_37;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW((LPCWSTR)this, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x19E,
                  (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
                  v15);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
LABEL_38:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v27);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPathIn);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v29);
    return LastError;
  }
  peUse = 0;
  cchName = 257;
  v30 = 16;
  if ( !LookupAccountSidW(0, Sid, Name, &cchName, v34, &v30, &peUse) )
  {
    BasicProfileFolderPath = wil::details::in1diag3::Return_GetLastError(
                               retaddr,
                               (void *)0x16B,
                               (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
                               v16);
    LastError = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v18 = 416;
LABEL_15:
      v19 = (unsigned int)BasicProfileFolderPath;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)v19,
        (int)ReferencedDomainNamea);
      goto LABEL_11;
    }
  }
  if ( peUse == SidTypeUser )
  {
    BasicProfileFolderPath = GetBasicProfileFolderPath(6, this, v38, 260);
    LastError = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v18 = 420;
      goto LABEL_15;
    }
    ReferencedDomainNamea = L"Packages\\Microsoft.Windows.ContentDeliveryManager_cw5n1h2txyewy\\LocalState\\Assets";
    BasicProfileFolderPath = StringCchPrintfW(Name, 0x104u, L"%s\\%s", v38);
    LastError = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v18 = 422;
      goto LABEL_15;
    }
    if ( PathCchCanonicalize(pszPathOut, 0x104u, Name) < 0
      || PathCchCanonicalize(v36, 0x104u, v13) < 0
      || (PathComparePaths(pszPathOut, v36) & 8) == 0 )
    {
      LastError = -2147024894;
      v19 = 2147942402LL;
      v18 = 426;
      goto LABEL_16;
    }
    if ( PathCchCanonicalize(v36, 0x104u, Name) < 0
      || PathCchCanonicalize(pszPathOut, 0x104u, v14) < 0
      || (PathComparePaths(v36, pszPathOut) & 8) == 0 )
    {
      LastError = -2147024894;
      v19 = 2147942402LL;
      v18 = 431;
      goto LABEL_16;
    }
  }
  *(_QWORD *)v29 = 0;
  *a2 = v12;
  pszPathIn = 0;
  *a3 = v13;
  v27 = 0;
  *v32 = (unsigned __int16 *)v14;
  *v33 = (char)v24;
  if ( Sid )
    LocalFree(Sid);
  return 0;
}

```

## disassembly

```asm
0x18000bdcc  push    rbp
0x18000bdce  push    rbx
0x18000bdcf  push    rsi
0x18000bdd0  push    rdi
0x18000bdd1  push    r12
0x18000bdd3  push    r13
0x18000bdd5  push    r14
0x18000bdd7  push    r15
0x18000bdd9  lea     rbp, [rsp-808h]
0x18000bde1  sub     rsp, 908h
0x18000bde8  mov     rax, cs:__security_cookie
0x18000bdef  xor     rax, rsp
0x18000bdf2  mov     [rbp+840h+var_50], rax
0x18000bdf9  mov     [rsp+940h+var_8C8], r9
0x18000bdfe  mov     r13, r8
0x18000be01  mov     r12, rdx
0x18000be04  mov     r15, rcx
0x18000be07  mov     rcx, [rbp+840h+arg_20]
0x18000be0e  mov     [rbp+840h+var_8C0], rcx
0x18000be12  xor     esi, esi
0x18000be14  mov     [rdx], rsi
0x18000be17  mov     [r8], rsi
0x18000be1a  mov     [r9], rsi
0x18000be1d  mov     [rcx], sil
0x18000be20  mov     qword ptr [rsp+940h+var_8D8], rsi
0x18000be25  mov     [rsp+940h+pszPathIn], rsi
0x18000be2a  mov     [rsp+940h+var_8E8], rsi
0x18000be2f  mov     byte ptr [rsp+940h+var_900], sil
0x18000be34  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x18000be3b  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18000be40  mov     [rsp+940h+var_8E8], rsi
0x18000be45  mov     [rsp+940h+pszPathIn], rsi
0x18000be4a  mov     qword ptr [rsp+940h+var_8D8], rsi
0x18000be4f  lea     rax, [rsp+940h+var_900]
0x18000be54  mov     [rsp+940h+ReferencedDomainName], rax; int
0x18000be59  lea     r9, [rsp+940h+var_8E8]; unsigned __int16 **
0x18000be5e  lea     r8, [rsp+940h+pszPathIn]; unsigned __int16 **
0x18000be63  lea     rdx, [rsp+940h+var_8D8]; unsigned __int16 *
0x18000be68  mov     rcx, r15; this
0x18000be6b  call    ?PeekLockScreenRegistryKeys@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBGPEAPEAG11PEA_N@Z; CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(ushort const *,ushort * *,ushort * *,ushort * *,bool *)
0x18000be70  mov     ebx, eax
0x18000be72  test    eax, eax
0x18000be74  jns     short loc_18000BE83
0x18000be76  mov     r9d, eax
0x18000be79  mov     edx, 18Dh
0x18000be7e  jmp     loc_18000C156
0x18000be83  mov     r14, qword ptr [rsp+940h+var_8D8]
0x18000be88  test    r14, r14
0x18000be8b  jz      loc_18000C149
0x18000be91  cmp     [r14], si
0x18000be95  jz      loc_18000C149
0x18000be9b  mov     rdi, [rsp+940h+pszPathIn]
0x18000bea0  test    rdi, rdi
0x18000bea3  jz      loc_18000C142
0x18000bea9  cmp     [rdi], si
0x18000beac  jz      loc_18000C142
0x18000beb2  mov     rsi, [rsp+940h+var_8E8]
0x18000beb7  xor     ebx, ebx
0x18000beb9  test    rsi, rsi
0x18000bebc  jz      loc_18000C13B
0x18000bec2  cmp     [rsi], bx
0x18000bec5  jz      loc_18000C13B
0x18000becb  mov     [rsp+940h+Sid], rbx
0x18000bed0  lea     rdx, [rsp+940h+Sid]; Sid
0x18000bed5  mov     rcx, r15; StringSid
0x18000bed8  call    cs:__imp_ConvertStringSidToSidW
0x18000bedf  nop     dword ptr [rax+rax+00h]
0x18000bee4  test    eax, eax
0x18000bee6  jnz     short loc_18000BF11
0x18000bee8  mov     rcx, [rbp+848h]; this
0x18000beef  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000bef6  mov     edx, 19Eh; void *
0x18000befb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bf00  mov     ebx, eax
0x18000bf02  lea     rcx, [rsp+940h+Sid]
0x18000bf07  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000bf0c  jmp     loc_18000C16A
0x18000bf11  mov     [rsp+940h+var_8F0], ebx
0x18000bf15  mov     [rsp+940h+cchName], 101h
0x18000bf1d  mov     [rsp+940h+var_8D0], 10h
0x18000bf25  lea     rax, [rsp+940h+var_8F0]
0x18000bf2a  mov     [rsp+940h+peUse], rax; peUse
0x18000bf2f  lea     rax, [rsp+940h+var_8D0]
0x18000bf34  mov     [rsp+940h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000bf39  lea     rax, [rbp+840h+var_8B8]
0x18000bf3d  mov     [rsp+940h+ReferencedDomainName], rax; int
0x18000bf42  lea     r9, [rsp+940h+cchName]; cchName
0x18000bf47  lea     r8, [rbp+840h+Name]; Name
0x18000bf4b  mov     rdx, [rsp+940h+Sid]; Sid
0x18000bf50  xor     ecx, ecx; lpSystemName
0x18000bf52  call    cs:__imp_LookupAccountSidW
0x18000bf59  nop     dword ptr [rax+rax+00h]
0x18000bf5e  test    eax, eax
0x18000bf60  jnz     short loc_18000BFA2
0x18000bf62  mov     rcx, [rbp+848h]; this
0x18000bf69  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000bf70  mov     edx, 16Bh; void *
0x18000bf75  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bf7a  mov     ebx, eax
0x18000bf7c  test    eax, eax
0x18000bf7e  jns     short loc_18000BFA0
0x18000bf80  mov     edx, 1A0h; void *
0x18000bf85  mov     r9d, eax; char *
0x18000bf88  mov     rcx, [rbp+848h]; this
0x18000bf8f  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000bf96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bf9b  jmp     loc_18000BF02
0x18000bfa0  xor     ebx, ebx
0x18000bfa2  cmp     [rsp+940h+var_8F0], 1
0x18000bfa7  jnz     loc_18000C0F7
0x18000bfad  mov     r9d, 104h
0x18000bfb3  lea     r8, [rbp+840h+var_260]
0x18000bfba  mov     rdx, r15
0x18000bfbd  mov     ecx, 6
0x18000bfc2  call    cs:__imp_GetBasicProfileFolderPath
0x18000bfc9  nop     dword ptr [rax+rax+00h]
0x18000bfce  mov     ebx, eax
0x18000bfd0  test    eax, eax
0x18000bfd2  jns     short loc_18000BFDB
0x18000bfd4  mov     edx, 1A4h
0x18000bfd9  jmp     short loc_18000BF85
0x18000bfdb  lea     rax, aPackagesMicros; "Packages\\Microsoft.Windows.ContentDeli"...
0x18000bfe2  mov     [rsp+940h+ReferencedDomainName], rax
0x18000bfe7  lea     r9, [rbp+840h+var_260]
0x18000bfee  lea     r8, aSS_1; "%s\\%s"
0x18000bff5  mov     r15d, 104h
0x18000bffb  mov     edx, r15d; unsigned __int64
0x18000bffe  lea     rcx, [rbp+840h+Name]; unsigned __int16 *
0x18000c002  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c007  mov     ebx, eax
0x18000c009  test    eax, eax
0x18000c00b  jns     short loc_18000C017
0x18000c00d  mov     edx, 1A6h
0x18000c012  jmp     loc_18000BF85
0x18000c017  lea     r8, [rbp+840h+Name]; pszPathIn
0x18000c01b  mov     rdx, r15; cchPathOut
0x18000c01e  lea     rcx, [rbp+840h+pszPathOut]; pszPathOut
0x18000c025  call    cs:__imp_PathCchCanonicalize
0x18000c02c  nop     dword ptr [rax+rax+00h]
0x18000c031  xor     ebx, ebx
0x18000c033  test    eax, eax
0x18000c035  js      loc_18000C0E5
0x18000c03b  mov     r8, rdi; pszPathIn
0x18000c03e  mov     rdx, r15; cchPathOut
0x18000c041  lea     rcx, [rbp+840h+var_680]; pszPathOut
0x18000c048  call    cs:__imp_PathCchCanonicalize
0x18000c04f  nop     dword ptr [rax+rax+00h]
0x18000c054  test    eax, eax
0x18000c056  js      loc_18000C0E5
0x18000c05c  lea     rdx, [rbp+840h+var_680]
0x18000c063  lea     rcx, [rbp+840h+pszPathOut]
0x18000c06a  call    cs:__imp_PathComparePaths
0x18000c071  nop     dword ptr [rax+rax+00h]
0x18000c076  test    al, 8
0x18000c078  jz      short loc_18000C0E5
0x18000c07a  lea     r8, [rbp+840h+Name]; pszPathIn
0x18000c07e  mov     rdx, r15; cchPathOut
0x18000c081  lea     rcx, [rbp+840h+var_680]; pszPathOut
0x18000c088  call    cs:__imp_PathCchCanonicalize
0x18000c08f  nop     dword ptr [rax+rax+00h]
0x18000c094  test    eax, eax
0x18000c096  js      short loc_18000C0D3
0x18000c098  mov     r8, rsi; pszPathIn
0x18000c09b  mov     rdx, r15; cchPathOut
0x18000c09e  lea     rcx, [rbp+840h+pszPathOut]; pszPathOut
0x18000c0a5  call    cs:__imp_PathCchCanonicalize
0x18000c0ac  nop     dword ptr [rax+rax+00h]
0x18000c0b1  test    eax, eax
0x18000c0b3  js      short loc_18000C0D3
0x18000c0b5  lea     rdx, [rbp+840h+pszPathOut]
0x18000c0bc  lea     rcx, [rbp+840h+var_680]
0x18000c0c3  call    cs:__imp_PathComparePaths
0x18000c0ca  nop     dword ptr [rax+rax+00h]
0x18000c0cf  test    al, 8
0x18000c0d1  jnz     short loc_18000C0F7
0x18000c0d3  mov     ebx, 80070002h
0x18000c0d8  mov     r9d, ebx
0x18000c0db  mov     edx, 1AFh
0x18000c0e0  jmp     loc_18000BF88
0x18000c0e5  mov     ebx, 80070002h
0x18000c0ea  mov     r9d, ebx
0x18000c0ed  mov     edx, 1AAh
0x18000c0f2  jmp     loc_18000BF88
0x18000c0f7  mov     qword ptr [rsp+940h+var_8D8], rbx
0x18000c0fc  mov     [r12], r14
0x18000c100  mov     [rsp+940h+pszPathIn], rbx
0x18000c105  mov     [r13+0], rdi
0x18000c109  mov     [rsp+940h+var_8E8], rbx
0x18000c10e  mov     rax, [rsp+940h+var_8C8]
0x18000c113  mov     [rax], rsi
0x18000c116  mov     al, byte ptr [rsp+940h+var_900]
0x18000c11a  mov     rcx, [rbp+840h+var_8C0]
0x18000c11e  mov     [rcx], al
0x18000c120  mov     rcx, [rsp+940h+Sid]; hMem
0x18000c125  test    rcx, rcx
0x18000c128  jz      short loc_18000C137
0x18000c12a  call    cs:__imp_LocalFree
0x18000c131  nop     dword ptr [rax+rax+00h]
0x18000c136  nop
0x18000c137  xor     eax, eax
0x18000c139  jmp     short loc_18000C18C
0x18000c13b  mov     edx, 190h
0x18000c140  jmp     short loc_18000C14E
0x18000c142  mov     edx, 18Fh
0x18000c147  jmp     short loc_18000C14E
0x18000c149  mov     edx, 18Eh; void *
0x18000c14e  mov     ebx, 80070002h
0x18000c153  mov     r9d, ebx; char *
0x18000c156  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000c15d  mov     rcx, [rbp+848h]; this
0x18000c164  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c169  nop
0x18000c16a  lea     rcx, [rsp+940h+var_8E8]
0x18000c16f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000c174  nop
0x18000c175  lea     rcx, [rsp+940h+pszPathIn]
0x18000c17a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000c17f  nop
0x18000c180  lea     rcx, [rsp+940h+var_8D8]
0x18000c185  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000c18a  mov     eax, ebx
0x18000c18c  mov     rcx, [rbp+840h+var_50]
0x18000c193  xor     rcx, rsp; StackCookie
0x18000c196  call    __security_check_cookie
0x18000c19b  add     rsp, 908h
0x18000c1a2  pop     r15
0x18000c1a4  pop     r14
0x18000c1a6  pop     r13
0x18000c1a8  pop     r12
0x18000c1aa  pop     rdi
0x18000c1ab  pop     rsi
0x18000c1ac  pop     rbx
0x18000c1ad  pop     rbp
0x18000c1ae  retn
```
