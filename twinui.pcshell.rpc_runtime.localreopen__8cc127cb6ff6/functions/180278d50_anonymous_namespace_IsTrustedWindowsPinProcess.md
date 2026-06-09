# _anonymous_namespace_::IsTrustedWindowsPinProcess

- ea: `0x180278d50`
- end: `0x18027908c`
- name: `_anonymous_namespace_::IsTrustedWindowsPinProcess`
- size: `828`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180278b18`
- `0x180278cac`

## callees

- `0x18001d664`
- `0x180268684`
- `0x1802699ac`
- `0x180276bc0`
- `0x180278d50`
- `0x1802c9b2c`
- `0x180356360`
- `0x180356734`
- `0x18035b4ac`
- `0x18035b514`
- `0x180434e5c`
- `0x1805f14a8`
- `0x1805f9d3c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180278e27`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180278eb1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180278f0e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180278f39`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180278f5c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180278ff1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180278e27`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180278eb1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180278f0e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180278f39`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180278f5c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180278ff1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180278d9d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180278f1c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180278d9d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180278f1c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCpyNW` at `0x180278dc5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCpyNW` at `0x180278dc5`

## string_xrefs

- `0x180278e6b`: `%windir%\system32\RuntimeBroker.exe`
- `0x180278fb6`: `%windir%\system32\RuntimeBroker.exe`
- `0x18027905a`: `%windir%\system32\ShellHost.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall anonymous_namespace_::IsTrustedWindowsPinProcess(__int64 a1, __int64 a2)
{
  const WCHAR *v3; // rbx
  const WCHAR *FileNameW; // rdi
  __int64 v5; // rax
  char v6; // di
  LPCWCH *v7; // rsi
  const WCHAR *v8; // rsi
  __int64 v9; // rdx
  const WCHAR *v10; // rsi
  _QWORD *v12; // rsi
  char v13[8]; // [rsp+30h] [rbp-29h] BYREF
  LPCWSTR pszPath; // [rsp+38h] [rbp-21h] BYREF
  const WCHAR *v15; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v16[3]; // [rsp+48h] [rbp-11h] BYREF
  _QWORD v17[4]; // [rsp+60h] [rbp+7h] BYREF
  LPCWCH lpString1; // [rsp+80h] [rbp+27h] BYREF

  pszPath = 0;
  TryGetProcessImagePath(&pszPath, a1);
  v3 = pszPath;
  if ( pszPath )
  {
    FileNameW = PathFindFileNameW(pszPath);
    v5 = tip2::tip_test<tip2::details::merged_data<PinManagerTipTests::_tip_PinManagerPinTest,PinManagerTipTests::_tip_PinManagerPinTest>>::operator->(
           a2,
           &lpString1);
    StrCpyNW((PWSTR)(*(_QWORD *)v5 + 796LL), FileNameW, 260);
    tip2::test_data_control<tip2::details::merged_data<PinManagerTipTests::_tip_PinManagerPinTest,PinManagerTipTests::_tip_PinManagerPinTest>>::~test_data_control<tip2::details::merged_data<PinManagerTipTests::_tip_PinManagerPinTest,PinManagerTipTests::_tip_PinManagerPinTest>>(&lpString1);
    v6 = 1;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellHostPinning>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShellHostPinning>::GetImpl'::`2'::impl) )
      goto LABEL_26;
    if ( dword_1808DC2F8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 16LL) )
    {
      Init_thread_header(&dword_1808DC2F8);
      if ( dword_1808DC2F8 == -1 )
      {
        ::lpString1 = 0;
        wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
          &::lpString1,
          L"%windir%\\system32\\ShellHost.exe");
        atexit(_anonymous_namespace_::IsTrustedWindowsPinProcess_::_8_::_dynamic_atexit_destructor_for__expandedShellHostPath__);
        Init_thread_footer(&dword_1808DC2F8);
      }
    }
    if ( CompareStringOrdinal(::lpString1, -1, v3, -1, 1) == 2 )
    {
LABEL_5:
      v13[0] = 1;
      lpString1 = v3;
      PinManagerTelemetry::TaskbarPinTrustedProcessChecked<unsigned short *,bool>(&lpString1, v13);
    }
    else
    {
LABEL_26:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_53852258>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53852258>::GetImpl'::`2'::impl) )
      {
        v17[0] = L"%windir%\\explorer.exe";
        v17[1] = L"%windir%\\system32\\RuntimeBroker.exe";
        v17[2] = L"%windir%\\SystemApps\\Microsoft.Windows.StartMenuExperienceHost_cw5n1h2txyewy\\StartMenuExperienceHost.exe";
        v17[3] = L"%windir%\\SystemApps\\MicrosoftWindows.Client.CBS_cw5n1h2txyewy\\SearchHost.exe";
        v7 = (LPCWCH *)v17;
        while ( 1 )
        {
          lpString1 = 0;
          wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
            &lpString1,
            *v7);
          if ( CompareStringOrdinal(lpString1, -1, v3, -1, 1) == 2 )
            break;
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpString1);
          if ( ++v7 == &lpString1 )
          {
            v8 = *(const WCHAR **)wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
                                    &lpString1,
                                    L"%localappdata%\\DevelopmentFiles\\MicrosoftWindows.Search");
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpString1);
            v9 = -1;
            do
              ++v9;
            while ( v8[v9] );
            if ( CompareStringOrdinal(v8, v9 - 1, v3, v9 - 1, 1) == 2 )
            {
              v10 = PathFindFileNameW(v3);
              if ( CompareStringOrdinal(L"SearchHost.exe", -1, v10, -1, 1) == 2
                || CompareStringOrdinal(L"Search.TestHost.exe", -1, v10, -1, 1) == 2 )
              {
                goto LABEL_5;
              }
            }
            goto LABEL_15;
          }
        }
      }
      else
      {
        v16[0] = L"%windir%\\explorer.exe";
        v16[1] = L"%windir%\\system32\\RuntimeBroker.exe";
        v16[2] = L"%windir%\\SystemApps\\Microsoft.Windows.StartMenuExperienceHost_cw5n1h2txyewy\\StartMenuExperienceHost.exe";
        v12 = v16;
        while ( 1 )
        {
          lpString1 = 0;
          wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
            &lpString1,
            *v12);
          if ( CompareStringOrdinal(lpString1, -1, v3, -1, 1) == 2 )
            break;
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpString1);
          if ( ++v12 == v17 )
            goto LABEL_15;
        }
      }
      v13[0] = 1;
      v15 = v3;
      PinManagerTelemetry::TaskbarPinTrustedProcessChecked<unsigned short *,bool>(&v15, v13);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpString1);
    }
  }
  else
  {
LABEL_15:
    v13[0] = 0;
    v15 = v3;
    PinManagerTelemetry::TaskbarPinTrustedProcessChecked<unsigned short *,bool>(&v15, v13);
    v6 = 0;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
  return v6;
}

```

## disassembly

```asm
0x180278d50  mov     [rsp-8+arg_10], rbx
0x180278d55  push    rbp
0x180278d56  push    rsi
0x180278d57  push    rdi
0x180278d58  push    r14
0x180278d5a  push    r15
0x180278d5c  lea     rbp, [rsp-37h]
0x180278d61  sub     rsp, 90h
0x180278d68  mov     rax, cs:__security_cookie
0x180278d6f  xor     rax, rsp
0x180278d72  mov     [rbp+57h+var_28], rax
0x180278d76  mov     rsi, rdx
0x180278d79  xor     r14d, r14d
0x180278d7c  mov     [rbp+57h+pszPath], r14
0x180278d80  mov     rdx, rcx
0x180278d83  lea     rcx, [rbp+57h+pszPath]
0x180278d87  call    ?TryGetProcessImagePath@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@Z; TryGetProcessImagePath(void *)
0x180278d8c  nop
0x180278d8d  mov     rbx, [rbp+57h+pszPath]
0x180278d91  test    rbx, rbx
0x180278d94  jz      loc_180278F6B
0x180278d9a  mov     rcx, rbx; pszPath
0x180278d9d  call    cs:__imp_PathFindFileNameW
0x180278da3  mov     rdi, rax
0x180278da6  lea     rdx, [rbp+57h+lpString1]
0x180278daa  mov     rcx, rsi
0x180278dad  call    ??C?$tip_test@V?$merged_data@U_tip_PinManagerPinTest@PinManagerTipTests@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PinManagerPinTest@PinManagerTipTests@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<PinManagerTipTests::_tip_PinManagerPinTest,PinManagerTipTests::_tip_PinManagerPinTest>>::operator->(void)
0x180278db2  mov     rcx, [rax]
0x180278db5  add     rcx, 31Ch; pszDst
0x180278dbc  mov     r8d, 104h; cchMax
0x180278dc2  mov     rdx, rdi; pszSrc
0x180278dc5  call    cs:__imp_StrCpyNW
0x180278dcb  lea     rcx, [rbp+57h+lpString1]
0x180278dcf  call    ??1?$test_data_control@V?$merged_data@U_tip_PinManagerPinTest@PinManagerTipTests@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<PinManagerTipTests::_tip_PinManagerPinTest,PinManagerTipTests::_tip_PinManagerPinTest>>::~test_data_control<tip2::details::merged_data<PinManagerTipTests::_tip_PinManagerPinTest,PinManagerTipTests::_tip_PinManagerPinTest>>(void)
0x180278dd4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShellHostPinning@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShellHostPinning@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellHostPinning> `wil::Feature<__WilFeatureTraits_Feature_ShellHostPinning>::GetImpl(void)'::`2'::impl
0x180278ddb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShellHostPinning@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellHostPinning>::__private_IsEnabled(void)
0x180278de0  or      r15, 0FFFFFFFFFFFFFFFFh
0x180278de4  lea     edi, [r14+1]
0x180278de8  test    al, al
0x180278dea  jz      short loc_180278E4C
0x180278dec  mov     ecx, cs:_tls_index
0x180278df2  mov     rax, gs:58h
0x180278dfb  mov     edx, 10h
0x180278e00  mov     rax, [rax+rcx*8]
0x180278e04  mov     ecx, [rdx+rax]
0x180278e07  cmp     cs:dword_1808DC2F8, ecx
0x180278e0d  jg      loc_18027903A
0x180278e13  mov     [rsp+0B0h+bIgnoreCase], edi; bIgnoreCase
0x180278e17  mov     r9d, r15d; cchCount2
0x180278e1a  mov     r8, rbx; lpString2
0x180278e1d  mov     edx, r15d; cchCount1
0x180278e20  mov     rcx, cs:lpString1; lpString1
0x180278e27  call    cs:__imp_CompareStringOrdinal
0x180278e2d  cmp     eax, 2
0x180278e30  jnz     short loc_180278E4C
0x180278e32  mov     [rbp+57h+var_80], dil
0x180278e36  mov     [rbp+57h+lpString1], rbx
0x180278e3a  lea     rdx, [rbp+57h+var_80]
0x180278e3e  lea     rcx, [rbp+57h+lpString1]
0x180278e42  call    ??$TaskbarPinTrustedProcessChecked@PEAG_N@PinManagerTelemetry@@SAX$$QEAPEAG$$QEA_N@Z; PinManagerTelemetry::TaskbarPinTrustedProcessChecked<ushort *,bool>(ushort * &&,bool &&)
0x180278e47  jmp     loc_180278F83
0x180278e4c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53852258@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53852258@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53852258> `wil::Feature<__WilFeatureTraits_Feature_53852258>::GetImpl(void)'::`2'::impl
0x180278e53  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53852258@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53852258>::__private_IsEnabled(void)
0x180278e58  test    al, al
0x180278e5a  lea     rax, aWindirExplorer; "%windir%\\explorer.exe"
0x180278e61  jz      loc_180278FB2
0x180278e67  mov     [rbp+57h+var_50], rax
0x180278e6b  lea     rax, aWindirSystem32; "%windir%\\system32\\RuntimeBroker.exe"
0x180278e72  mov     [rbp+57h+var_48], rax
0x180278e76  lea     rax, aWindirSystemap; "%windir%\\SystemApps\\Microsoft.Windows"...
0x180278e7d  mov     [rbp+57h+var_40], rax
0x180278e81  lea     rax, aWindirSystemap_0; "%windir%\\SystemApps\\MicrosoftWindows."...
0x180278e88  mov     [rbp+57h+var_38], rax
0x180278e8c  lea     rsi, [rbp+57h+var_50]
0x180278e90  mov     [rbp+57h+lpString1], r14
0x180278e94  mov     rdx, [rsi]
0x180278e97  lea     rcx, [rbp+57h+lpString1]
0x180278e9b  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180278ea0  mov     [rsp+0B0h+bIgnoreCase], edi; bIgnoreCase
0x180278ea4  mov     r9d, r15d; cchCount2
0x180278ea7  mov     r8, rbx; lpString2
0x180278eaa  mov     edx, r15d; cchCount1
0x180278ead  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180278eb1  call    cs:__imp_CompareStringOrdinal
0x180278eb7  cmp     eax, 2
0x180278eba  jz      loc_180279017
0x180278ec0  lea     rcx, [rbp+57h+lpString1]
0x180278ec4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180278ec9  add     rsi, 8
0x180278ecd  lea     rax, [rbp+57h+lpString1]
0x180278ed1  cmp     rsi, rax
0x180278ed4  jnz     short loc_180278E90
0x180278ed6  lea     rdx, aLocalappdataDe; "%localappdata%\\DevelopmentFiles\\Micro"...
0x180278edd  lea     rcx, [rbp+57h+lpString1]
0x180278ee1  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180278ee6  mov     rsi, [rax]
0x180278ee9  lea     rcx, [rbp+57h+lpString1]
0x180278eed  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180278ef2  mov     rdx, r15
0x180278ef5  inc     rdx
0x180278ef8  cmp     [rsi+rdx*2], r14w
0x180278efd  jnz     short loc_180278EF5
0x180278eff  dec     edx; cchCount1
0x180278f01  mov     [rsp+0B0h+bIgnoreCase], edi; bIgnoreCase
0x180278f05  mov     r9d, edx; cchCount2
0x180278f08  mov     r8, rbx; lpString2
0x180278f0b  mov     rcx, rsi; lpString1
0x180278f0e  call    cs:__imp_CompareStringOrdinal
0x180278f14  cmp     eax, 2
0x180278f17  jnz     short loc_180278F6B
0x180278f19  mov     rcx, rbx; pszPath
0x180278f1c  call    cs:__imp_PathFindFileNameW
0x180278f22  mov     rsi, rax
0x180278f25  mov     [rsp+0B0h+bIgnoreCase], edi; bIgnoreCase
0x180278f29  mov     r9d, r15d; cchCount2
0x180278f2c  mov     r8, rax; lpString2
0x180278f2f  mov     edx, r15d; cchCount1
0x180278f32  lea     rcx, aSearchhostExe; "SearchHost.exe"
0x180278f39  call    cs:__imp_CompareStringOrdinal
0x180278f3f  cmp     eax, 2
0x180278f42  jz      loc_180278E32
0x180278f48  mov     [rsp+0B0h+bIgnoreCase], edi; bIgnoreCase
0x180278f4c  mov     r9d, r15d; cchCount2
0x180278f4f  mov     r8, rsi; lpString2
0x180278f52  mov     edx, r15d; cchCount1
0x180278f55  lea     rcx, aSearchTesthost; "Search.TestHost.exe"
0x180278f5c  call    cs:__imp_CompareStringOrdinal
0x180278f62  cmp     eax, 2
0x180278f65  jz      loc_180278E32
0x180278f6b  mov     [rbp+57h+var_80], r14b
0x180278f6f  mov     [rbp+57h+var_70], rbx
0x180278f73  lea     rdx, [rbp+57h+var_80]
0x180278f77  lea     rcx, [rbp+57h+var_70]
0x180278f7b  call    ??$TaskbarPinTrustedProcessChecked@PEAG_N@PinManagerTelemetry@@SAX$$QEAPEAG$$QEA_N@Z; PinManagerTelemetry::TaskbarPinTrustedProcessChecked<ushort *,bool>(ushort * &&,bool &&)
0x180278f80  mov     dil, r14b
0x180278f83  lea     rcx, [rbp+57h+pszPath]
0x180278f87  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180278f8c  mov     al, dil
0x180278f8f  mov     rcx, [rbp+57h+var_28]
0x180278f93  xor     rcx, rsp; StackCookie
0x180278f96  call    __security_check_cookie
0x180278f9b  mov     rbx, [rsp+0B0h+arg_10]
0x180278fa3  add     rsp, 90h
0x180278faa  pop     r15
0x180278fac  pop     r14
0x180278fae  pop     rdi
0x180278faf  pop     rsi
0x180278fb0  pop     rbp
0x180278fb1  retn
0x180278fb2  mov     [rbp+57h+var_68], rax
0x180278fb6  lea     rax, aWindirSystem32; "%windir%\\system32\\RuntimeBroker.exe"
0x180278fbd  mov     [rbp+57h+var_60], rax
0x180278fc1  lea     rax, aWindirSystemap; "%windir%\\SystemApps\\Microsoft.Windows"...
0x180278fc8  mov     [rbp+57h+var_58], rax
0x180278fcc  lea     rsi, [rbp+57h+var_68]
0x180278fd0  mov     [rbp+57h+lpString1], r14
0x180278fd4  mov     rdx, [rsi]
0x180278fd7  lea     rcx, [rbp+57h+lpString1]
0x180278fdb  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180278fe0  mov     [rsp+0B0h+bIgnoreCase], edi; bIgnoreCase
0x180278fe4  mov     r9d, r15d; cchCount2
0x180278fe7  mov     r8, rbx; lpString2
0x180278fea  mov     edx, r15d; cchCount1
0x180278fed  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180278ff1  call    cs:__imp_CompareStringOrdinal
0x180278ff7  cmp     eax, 2
0x180278ffa  jz      short loc_180279017
0x180278ffc  lea     rcx, [rbp+57h+lpString1]
0x180279000  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180279005  add     rsi, 8
0x180279009  lea     rax, [rbp+57h+var_50]
0x18027900d  cmp     rsi, rax
0x180279010  jnz     short loc_180278FD0
0x180279012  jmp     loc_180278F6B
0x180279017  mov     [rbp+57h+var_80], dil
0x18027901b  mov     [rbp+57h+var_70], rbx
0x18027901f  lea     rdx, [rbp+57h+var_80]
0x180279023  lea     rcx, [rbp+57h+var_70]
0x180279027  call    ??$TaskbarPinTrustedProcessChecked@PEAG_N@PinManagerTelemetry@@SAX$$QEAPEAG$$QEA_N@Z; PinManagerTelemetry::TaskbarPinTrustedProcessChecked<ushort *,bool>(ushort * &&,bool &&)
0x18027902c  lea     rcx, [rbp+57h+lpString1]
0x180279030  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180279035  jmp     loc_180278F83
0x18027903a  lea     rcx, dword_1808DC2F8
0x180279041  call    _Init_thread_header
0x180279046  cmp     cs:dword_1808DC2F8, r15d
0x18027904d  jnz     loc_180278E13
0x180279053  mov     cs:lpString1, r14
0x18027905a  lea     rdx, aWindirSystem32_0; "%windir%\\system32\\ShellHost.exe"
0x180279061  lea     rcx, lpString1
0x180279068  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x18027906d  lea     rcx, __anonymous_namespace___IsTrustedWindowsPinProcess____8____dynamic_atexit_destructor_for__expandedShellHostPath__; void (__cdecl *)()
0x180279074  call    atexit
0x180279079  nop
0x18027907a  lea     rcx, dword_1808DC2F8
0x180279081  call    _Init_thread_footer
0x180279086  jmp     loc_180278E13
```
