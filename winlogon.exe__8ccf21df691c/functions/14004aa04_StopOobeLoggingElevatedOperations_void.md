# StopOobeLoggingElevatedOperations(void)

- ea: `0x14004aa04`
- end: `0x14004ae57`
- name: `?StopOobeLoggingElevatedOperations@@YAXXZ`
- size: `1107`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14007c988`

## callees

- `0x14000b41c`
- `0x1400271f0`
- `0x140031a90`
- `0x140032c50`
- `0x140034780`
- `0x14003ba30`
- `0x14004327c`
- `0x14004a75c`
- `0x14004aa04`
- `0x14004ae60`
- `0x14004b400`
- `0x14004b4e4`
- `0x140053720`
- `0x1400544e0`
- `0x14005d664`
- `0x14005f33c`
- `0x14009cbd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004ad1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004ad1f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14004ada8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14004add5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14004ada8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14004add5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004ac14`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004acd4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004ac14`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14004acd4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004ab67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004abd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004ac80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004ad8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004ab67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004abd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004ac80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004ad8b`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x14004aa6c`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x14004aa6c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004ac3d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004ac3d`

## string_xrefs

- `0x14004aab7`: `ETWAutoLoggerPath`
- `0x14004adce`: `RestoredWallPaperFullPath`

## pseudocode

```c
void StopOobeLoggingElevatedOperations(void)
{
  ULONG v0; // eax
  int RedirectionKeyPath; // eax
  __int64 v2; // rdx
  const char *v3; // r9
  unsigned int v4; // eax
  bool v5; // bl
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // eax
  int v11; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultc; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultd; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v21; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[16]; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_TRACE_PROPERTIES Properties; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1138h] [rbp+1038h]

  memset_0(&Properties, 0, 0x107Cu);
  Properties.Wnode.BufferSize = 4220;
  Properties.LoggerNameOffset = 120;
  Properties.LogFileNameOffset = 2170;
  v0 = ControlTraceW(0, L"CloudExperienceHostOobe", &Properties, 1u);
  if ( v0 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
      (const char *)v0,
      phkResult);
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  RedirectionKeyPath = GetRedirectionKeyPath(
                         L"ETWAutoLoggerPath",
                         L"SYSTEM\\CurrentControlSet\\Control\\WMI\\AutoLogger",
                         (unsigned __int16 **)&lpSubKey);
  if ( RedirectionKeyPath < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
      (const char *)(unsigned int)RedirectionKeyPath,
      phkResult);
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v21,
      L"SYSTEM\\CurrentControlSet\\Control\\WMI\\AutoLogger",
      -1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &lpSubKey,
      &v21);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v21);
    if ( !lpSubKey )
      wil::details::in1diag3::_Log_NullAlloc(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
        v3);
  }
  hKey = 0;
  if ( lpSubKey )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
    if ( v4 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
        (const char *)v4,
        phkResulta);
    }
    else
    {
      hkey = 0;
      pvData = 0;
      cbData = 4;
      *(_DWORD *)Data = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hkey,
        0);
      if ( !RegOpenKeyExW(hKey, L"CloudExperienceHostOobe", 0, 0x2001Fu, &hkey)
        && !RegGetValueW(hkey, 0, L"Start", 0x20000018u, 0, &pvData, &cbData)
        && pvData == 1 )
      {
        goto LABEL_18;
      }
      if ( CompareStringOrdinal(lpSubKey, -1, L"SYSTEM\\CurrentControlSet\\Control\\WMI\\AutoLogger", -1, 1) != 2 )
      {
        v21 = 0;
        v5 = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &v21,
          0);
        v6 = RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger\\CloudExperienceHostOobe",
               0,
               0x2001Fu,
               &v21);
        if ( v6 )
        {
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x42,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
            (const char *)v6,
            phkResultb);
        }
        else if ( !RegGetValueW(v21, 0, L"Start", 0x20000018u, 0, &pvData, &cbData) )
        {
          v5 = pvData == 1;
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
        if ( v5 )
        {
LABEL_18:
          v7 = RegSetValueExW(hkey, L"Start", 0, 4u, Data, cbData);
          if ( v7 )
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0x4D,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
              (const char *)v7,
              phkResultc);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    }
  }
  LOBYTE(v2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeRestoreDataLayer>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_OobeRestoreDataLayer>::GetImpl'::`2'::impl,
    v2);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE", 0, 0x2001Bu, &hkey);
  if ( v8 )
  {
    v9 = 84;
LABEL_27:
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
      (const char *)v8,
      phkResultd);
    goto LABEL_28;
  }
  v10 = RegDeleteValueW(hkey, L"RestoreStatus");
  if ( v10 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
      (const char *)v10,
      phkResultd);
  v8 = RegDeleteValueW(hkey, L"RestoredWallPaperFullPath");
  if ( v8 )
  {
    v9 = 87;
    goto LABEL_27;
  }
LABEL_28:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  OOBE::Health::details::OOBEHealthTracker::HandleEvent<26,bool>();
  v11 = OOBE::CompleteTime::SetAsCurrentTime();
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\StopOobeLogging.h",
      (const char *)(unsigned int)v11,
      phkResultd);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
}

```

## disassembly

```asm
0x14004aa04  push    rbp
0x14004aa06  push    rbx
0x14004aa07  push    rsi
0x14004aa08  push    r12
0x14004aa0a  push    r14
0x14004aa0c  lea     rbp, [rsp-1010h]
0x14004aa14  mov     eax, 1110h
0x14004aa19  call    _alloca_probe
0x14004aa1e  sub     rsp, rax
0x14004aa21  mov     rax, cs:__security_cookie
0x14004aa28  xor     rax, rsp
0x14004aa2b  mov     [rbp+1030h+var_30], rax
0x14004aa32  mov     ebx, 107Ch
0x14004aa37  lea     rcx, [rbp+1030h+Properties]; void *
0x14004aa3b  mov     r8d, ebx; Size
0x14004aa3e  xor     edx, edx; Val
0x14004aa40  call    memset_0
0x14004aa45  mov     r14d, 1
0x14004aa4b  mov     [rbp+1030h+Properties.Wnode.BufferSize], ebx
0x14004aa4e  mov     r9d, r14d; ControlCode
0x14004aa51  mov     [rbp+1030h+Properties.LoggerNameOffset], 78h ; 'x'
0x14004aa58  lea     r8, [rbp+1030h+Properties]; Properties
0x14004aa5c  mov     [rbp+1030h+Properties.LogFileNameOffset], 87Ah
0x14004aa63  lea     rdx, InstanceName; "CloudExperienceHostOobe"
0x14004aa6a  xor     ecx, ecx; TraceHandle
0x14004aa6c  call    cs:__imp_ControlTraceW
0x14004aa72  lea     rsi, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\StopO"...
0x14004aa79  test    eax, eax
0x14004aa7b  jz      short loc_14004AA93
0x14004aa7d  mov     rcx, [rbp+1038h]; this
0x14004aa84  lea     edx, [r14+1Eh]; void *
0x14004aa88  mov     r9d, eax; char *
0x14004aa8b  mov     r8, rsi; unsigned int
0x14004aa8e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14004aa93  xor     edx, edx
0x14004aa95  mov     [rsp+1130h+lpSubKey], 0
0x14004aa9e  lea     rcx, [rsp+1130h+lpSubKey]
0x14004aaa3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14004aaa8  lea     rbx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x14004aaaf  mov     rdx, rbx; unsigned __int16 *
0x14004aab2  lea     r8, [rsp+1130h+lpSubKey]; unsigned __int16 **
0x14004aab7  lea     rcx, aEtwautologgerp; "ETWAutoLoggerPath"
0x14004aabe  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x14004aac3  test    eax, eax
0x14004aac5  jns     short loc_14004AB24
0x14004aac7  mov     rcx, [rbp+1038h]; this
0x14004aace  mov     r9d, eax; char *
0x14004aad1  mov     r8, rsi; unsigned int
0x14004aad4  mov     edx, 27h ; '''; void *
0x14004aad9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14004aade  or      r8, 0FFFFFFFFFFFFFFFFh
0x14004aae2  lea     rcx, [rsp+1130h+var_10D0]
0x14004aae7  mov     rdx, rbx
0x14004aaea  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14004aaef  lea     rdx, [rsp+1130h+var_10D0]
0x14004aaf4  lea     rcx, [rsp+1130h+lpSubKey]
0x14004aaf9  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x14004aafe  lea     rcx, [rsp+1130h+var_10D0]
0x14004ab03  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14004ab08  cmp     [rsp+1130h+lpSubKey], 0
0x14004ab0e  jnz     short loc_14004AB24
0x14004ab10  mov     rcx, [rbp+1038h]; this
0x14004ab17  mov     r8, rsi; unsigned int
0x14004ab1a  mov     edx, 2Ah ; '*'; void *
0x14004ab1f  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x14004ab24  cmp     [rsp+1130h+lpSubKey], 0
0x14004ab2a  mov     r12, 0FFFFFFFF80000002h
0x14004ab31  mov     [rsp+1130h+hKey], 0
0x14004ab3a  jz      loc_14004AD4A
0x14004ab40  xor     edx, edx
0x14004ab42  lea     rcx, [rsp+1130h+hKey]
0x14004ab47  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x14004ab4c  mov     rdx, [rsp+1130h+lpSubKey]; lpSubKey
0x14004ab51  lea     rax, [rsp+1130h+hKey]
0x14004ab56  mov     r9d, 20019h; samDesired
0x14004ab5c  mov     [rsp+1130h+phkResult], rax; unsigned int
0x14004ab61  xor     r8d, r8d; ulOptions
0x14004ab64  mov     rcx, r12; hKey
0x14004ab67  call    cs:__imp_RegOpenKeyExW
0x14004ab6d  test    eax, eax
0x14004ab6f  jz      short loc_14004AB8D
0x14004ab71  mov     rcx, [rbp+1038h]; this
0x14004ab78  mov     r9d, eax; char *
0x14004ab7b  mov     r8, rsi; unsigned int
0x14004ab7e  mov     edx, 2Fh ; '/'; void *
0x14004ab83  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14004ab88  jmp     loc_14004AD4A
0x14004ab8d  xor     edx, edx
0x14004ab8f  mov     [rsp+1130h+hkey], 0
0x14004ab98  lea     rcx, [rsp+1130h+hkey]
0x14004ab9d  mov     [rsp+1130h+var_10E8], 0
0x14004aba5  mov     [rsp+1130h+cbData], 4
0x14004abad  mov     dword ptr [rsp+1130h+Data], 0
0x14004abb5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x14004abba  mov     rcx, [rsp+1130h+hKey]; hKey
0x14004abbf  lea     rax, [rsp+1130h+hkey]
0x14004abc4  mov     r9d, 2001Fh; samDesired
0x14004abca  mov     [rsp+1130h+phkResult], rax; phkResult
0x14004abcf  xor     r8d, r8d; ulOptions
0x14004abd2  lea     rdx, InstanceName; "CloudExperienceHostOobe"
0x14004abd9  call    cs:__imp_RegOpenKeyExW
0x14004abdf  test    eax, eax
0x14004abe1  jnz     short loc_14004AC29
0x14004abe3  mov     rcx, [rsp+1130h+hkey]; hkey
0x14004abe8  lea     rax, [rsp+1130h+cbData]
0x14004abed  mov     [rsp+1130h+pcbData], rax; pcbData
0x14004abf2  lea     r8, aStart; "Start"
0x14004abf9  lea     rax, [rsp+1130h+var_10E8]
0x14004abfe  mov     r9d, 20000018h; dwFlags
0x14004ac04  mov     [rsp+1130h+pvData], rax; pvData
0x14004ac09  xor     edx, edx; lpSubKey
0x14004ac0b  mov     [rsp+1130h+phkResult], 0; pdwType
0x14004ac14  call    cs:__imp_RegGetValueW
0x14004ac1a  test    eax, eax
0x14004ac1c  jnz     short loc_14004AC29
0x14004ac1e  cmp     [rsp+1130h+var_10E8], r14d
0x14004ac23  jz      loc_14004ACF8
0x14004ac29  mov     rcx, [rsp+1130h+lpSubKey]; lpString1
0x14004ac2e  or      r9d, 0FFFFFFFFh; cchCount2
0x14004ac32  or      edx, r9d; cchCount1
0x14004ac35  mov     dword ptr [rsp+1130h+phkResult], r14d; bIgnoreCase
0x14004ac3a  mov     r8, rbx; lpString2
0x14004ac3d  call    cs:__imp_CompareStringOrdinal
0x14004ac43  cmp     eax, 2
0x14004ac46  jz      loc_14004AD40
0x14004ac4c  xor     edx, edx
0x14004ac4e  mov     [rsp+1130h+var_10D0], 0
0x14004ac57  lea     rcx, [rsp+1130h+var_10D0]
0x14004ac5c  xor     bl, bl
0x14004ac5e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x14004ac63  lea     rax, [rsp+1130h+var_10D0]
0x14004ac68  mov     r9d, 2001Fh; samDesired
0x14004ac6e  xor     r8d, r8d; ulOptions
0x14004ac71  mov     [rsp+1130h+phkResult], rax; unsigned int
0x14004ac76  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x14004ac7d  mov     rcx, r12; hKey
0x14004ac80  call    cs:__imp_RegOpenKeyExW
0x14004ac86  test    eax, eax
0x14004ac88  jz      short loc_14004ACA3
0x14004ac8a  mov     rcx, [rbp+1038h]; this
0x14004ac91  mov     r9d, eax; char *
0x14004ac94  mov     r8, rsi; unsigned int
0x14004ac97  mov     edx, 42h ; 'B'; void *
0x14004ac9c  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14004aca1  jmp     short loc_14004ACEA
0x14004aca3  mov     rcx, [rsp+1130h+var_10D0]; hkey
0x14004aca8  lea     rax, [rsp+1130h+cbData]
0x14004acad  mov     [rsp+1130h+pcbData], rax; pcbData
0x14004acb2  lea     r8, aStart; "Start"
0x14004acb9  lea     rax, [rsp+1130h+var_10E8]
0x14004acbe  mov     r9d, 20000018h; dwFlags
0x14004acc4  mov     [rsp+1130h+pvData], rax; pvData
0x14004acc9  xor     edx, edx; lpSubKey
0x14004accb  mov     [rsp+1130h+phkResult], 0; pdwType
0x14004acd4  call    cs:__imp_RegGetValueW
0x14004acda  test    eax, eax
0x14004acdc  jnz     short loc_14004ACEA
0x14004acde  cmp     [rsp+1130h+var_10E8], r14d
0x14004ace3  movzx   ebx, bl
0x14004ace6  cmovz   ebx, r14d
0x14004acea  lea     rcx, [rsp+1130h+var_10D0]
0x14004acef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14004acf4  test    bl, bl
0x14004acf6  jz      short loc_14004AD40
0x14004acf8  mov     eax, [rsp+1130h+cbData]
0x14004acfc  lea     rdx, aStart; "Start"
0x14004ad03  mov     rcx, [rsp+1130h+hkey]; hKey
0x14004ad08  mov     r9d, 4; dwType
0x14004ad0e  mov     dword ptr [rsp+1130h+pvData], eax; cbData
0x14004ad12  xor     r8d, r8d; Reserved
0x14004ad15  lea     rax, [rsp+1130h+Data]
0x14004ad1a  mov     [rsp+1130h+phkResult], rax; unsigned int
0x14004ad1f  call    cs:__imp_RegSetValueExW
0x14004ad25  test    eax, eax
0x14004ad27  jz      short loc_14004AD40
0x14004ad29  mov     rcx, [rbp+1038h]; this
0x14004ad30  mov     r9d, eax; char *
0x14004ad33  mov     r8, rsi; unsigned int
0x14004ad36  mov     edx, 4Dh ; 'M'; void *
0x14004ad3b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14004ad40  lea     rcx, [rsp+1130h+hkey]
0x14004ad45  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14004ad4a  mov     dl, r14b
0x14004ad4d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OobeRestoreDataLayer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OobeRestoreDataLayer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeRestoreDataLayer> `wil::Feature<__WilFeatureTraits_Feature_OobeRestoreDataLayer>::GetImpl(void)'::`2'::impl
0x14004ad54  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_OobeRestoreDataLayer@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeRestoreDataLayer>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14004ad59  xor     edx, edx
0x14004ad5b  mov     [rsp+1130h+hkey], 0
0x14004ad64  lea     rcx, [rsp+1130h+hkey]
0x14004ad69  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x14004ad6e  lea     rax, [rsp+1130h+hkey]
0x14004ad73  mov     r9d, 2001Bh; samDesired
0x14004ad79  xor     r8d, r8d; ulOptions
0x14004ad7c  mov     [rsp+1130h+phkResult], rax; int
0x14004ad81  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14004ad88  mov     rcx, r12; hKey
0x14004ad8b  call    cs:__imp_RegOpenKeyExW
0x14004ad91  test    eax, eax
0x14004ad93  jz      short loc_14004AD9C
0x14004ad95  mov     edx, 54h ; 'T'
0x14004ad9a  jmp     short loc_14004ADE4
0x14004ad9c  mov     rcx, [rsp+1130h+hkey]; hKey
0x14004ada1  lea     rdx, aRestorestatus; "RestoreStatus"
0x14004ada8  call    cs:__imp_RegDeleteValueW
0x14004adae  test    eax, eax
0x14004adb0  jz      short loc_14004ADC9
0x14004adb2  mov     rcx, [rbp+1038h]; this
0x14004adb9  mov     r9d, eax; char *
0x14004adbc  mov     r8, rsi; unsigned int
0x14004adbf  mov     edx, 56h ; 'V'; void *
0x14004adc4  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14004adc9  mov     rcx, [rsp+1130h+hkey]; hKey
0x14004adce  lea     rdx, aRestoredwallpa; "RestoredWallPaperFullPath"
0x14004add5  call    cs:__imp_RegDeleteValueW
0x14004addb  test    eax, eax
0x14004addd  jz      short loc_14004ADF6
0x14004addf  mov     edx, 57h ; 'W'; void *
0x14004ade4  mov     rcx, [rbp+1038h]; this
0x14004adeb  mov     r9d, eax; char *
0x14004adee  mov     r8, rsi; unsigned int
0x14004adf1  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14004adf6  lea     rcx, [rsp+1130h+hkey]
0x14004adfb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14004ae00  call    ??$HandleEvent@$0BK@_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<26,bool>(bool)
0x14004ae05  call    OOBE__CompleteTime__SetAsCurrentTime
0x14004ae0a  test    eax, eax
0x14004ae0c  jns     short loc_14004AE25
0x14004ae0e  mov     rcx, [rbp+1038h]; this
0x14004ae15  mov     r9d, eax; char *
0x14004ae18  mov     r8, rsi; unsigned int
0x14004ae1b  mov     edx, 61h ; 'a'; void *
0x14004ae20  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14004ae25  lea     rcx, [rsp+1130h+hKey]
0x14004ae2a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14004ae2f  lea     rcx, [rsp+1130h+lpSubKey]
0x14004ae34  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14004ae39  mov     rcx, [rbp+1030h+var_30]
0x14004ae40  xor     rcx, rsp; StackCookie
0x14004ae43  call    __security_check_cookie
0x14004ae48  add     rsp, 1110h
0x14004ae4f  pop     r14
0x14004ae51  pop     r12
0x14004ae53  pop     rsi
0x14004ae54  pop     rbx
0x14004ae55  pop     rbp
0x14004ae56  retn
```
