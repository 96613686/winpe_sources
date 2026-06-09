# TzChangeToastActivationHandler::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x180015bd0`
- end: `0x180015e26`
- name: `?Activate@TzChangeToastActivationHandler@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `598`
- prototype: `__int64 __fastcall(TzChangeToastActivationHandler *this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800011e4`
- `0x180001510`
- `0x1800015c0`
- `0x18000166c`
- `0x1800018fc`
- `0x18000da78`
- `0x18000e968`
- `0x180012df8`
- `0x180014704`
- `0x180015bd0`
- `0x18001b0f6`
- `0x18001b126`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d0a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180015ce7`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180015ce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015cf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015cff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015cf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015cff`

## string_xrefs

- `0x180015c42`: `OpenedSettings`

## pseudocode

```c
__int64 __fastcall TzChangeToastActivationHandler::Activate(
        TzChangeToastActivationHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  const wchar_t *v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 LastError; // r8
  int v9; // r9d
  __int64 v10; // rax
  __int64 v11; // rdx
  int v12; // r9d
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR CommandLine[40]; // [rsp+F0h] [rbp-10h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Scenario58454712>::GetImpl'::`2'::impl,
                          a2,
                          a3,
                          a4) )
  {
    TraceLoggingRegisterEx_EventRegister_EventSetInformation();
    v5 = L"Ignore";
    if ( wcscmp_0(a3, L"Ignore") )
    {
      if ( !wcscmp_0(a3, L"ms-settings:dateandtime") )
      {
        v5 = L"OpenedSettings";
        *(_QWORD *)&StartupInfo.cb = 104;
        memset_0(&StartupInfo.lpReserved, 0, 0x60u);
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        wcscpy(CommandLine, L"explorer.exe ms-settings:dandtime");
        if ( CreateProcessW(0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
        {
          CloseHandle(ProcessInformation.hProcess);
          CloseHandle(ProcessInformation.hThread);
        }
        else
        {
          LastError = GetLastError();
          v7 = (unsigned int)dword_180030000;
          if ( (unsigned int)dword_180030000 > 5
            && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180030000, 0x200000000000LL, LastError) )
          {
            LODWORD(v16) = LastError;
            v17 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              v7,
              (unsigned int)byte_18002A115,
              LastError,
              v9,
              (__int64)&v17,
              (__int64)&v16);
          }
        }
      }
      else
      {
        v5 = L"Accept";
        v10 = std::wstring::wstring(&ProcessInformation, a3);
        SystemTimezoneSetter(v10);
        LOBYTE(v11) = 1;
        std::wstring::_Tidy(&ProcessInformation, v11, 0);
      }
    }
    if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL, LastError) )
    {
      v17 = (__int64)v5;
      v16 = 16779264;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        v7,
        (unsigned int)byte_18002A085,
        LastError,
        v12,
        (__int64)&v16,
        (__int64)&v17);
    }
    TraceLoggingUnregister_EventUnregister(v7, v6, LastError);
  }
  else
  {
    v13 = std::wstring::wstring(&ProcessInformation, a3);
    SystemTimezoneSetter(v13);
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(&ProcessInformation, v14, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180015bd0  mov     [rsp-8+arg_0], rbx
0x180015bd5  mov     [rsp-8+arg_8], rdi
0x180015bda  push    rbp
0x180015bdb  lea     rbp, [rsp-50h]
0x180015be0  sub     rsp, 150h
0x180015be7  mov     rax, cs:__security_cookie
0x180015bee  xor     rax, rsp
0x180015bf1  mov     [rbp+50h+var_10], rax
0x180015bf5  mov     rbx, r8
0x180015bf8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Scenario58454712@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Scenario58454712@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712> `wil::Feature<__WilFeatureTraits_Feature_Scenario58454712>::GetImpl(void)'::`2'::impl
0x180015bff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Scenario58454712@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scenario58454712>::__private_IsEnabled(void)
0x180015c04  test    al, al
0x180015c06  jz      loc_180015DDF
0x180015c0c  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180015c11  lea     rdi, aIgnore; "Ignore"
0x180015c18  mov     rdx, rdi; String2
0x180015c1b  mov     rcx, rbx; String1
0x180015c1e  call    wcscmp_0
0x180015c23  test    eax, eax
0x180015c25  jz      loc_180015D8C
0x180015c2b  lea     rdx, aMsSettingsDate; "ms-settings:dateandtime"
0x180015c32  mov     rcx, rbx; String1
0x180015c35  call    wcscmp_0
0x180015c3a  test    eax, eax
0x180015c3c  jnz     loc_180015D61
0x180015c42  lea     rdi, aOpenedsettings; "OpenedSettings"
0x180015c49  mov     qword ptr [rsp+150h+StartupInfo.cb], 68h ; 'h'
0x180015c52  xor     edx, edx; Val
0x180015c54  lea     r8d, [rax+60h]; Size
0x180015c58  lea     rcx, [rsp+150h+StartupInfo.lpReserved]; void *
0x180015c5d  call    memset_0
0x180015c62  xorps   xmm0, xmm0
0x180015c65  xor     eax, eax
0x180015c67  movups  xmmword ptr [rbp+50h+ProcessInformation.hProcess], xmm0
0x180015c6b  mov     qword ptr [rbp+50h+ProcessInformation.dwProcessId], rax
0x180015c6f  movaps  xmm1, xmmword ptr cs:aExplorerExeMsS; "explorer.exe ms-settings:dateandtime"
0x180015c76  movaps  xmmword ptr [rbp+50h+CommandLine], xmm1
0x180015c7a  movaps  xmm0, xmmword ptr cs:aExplorerExeMsS+10h; ".exe ms-settings:dateandtime"
0x180015c81  movaps  [rbp+50h+var_50], xmm0
0x180015c85  movaps  xmm1, xmmword ptr cs:aExplorerExeMsS+20h; "settings:dateandtime"
0x180015c8c  movaps  [rbp+50h+var_40], xmm1
0x180015c90  movaps  xmm0, xmmword ptr cs:aExplorerExeMsS+30h; ":dateandtime"
0x180015c97  movaps  [rbp+50h+var_30], xmm0
0x180015c9b  movups  xmm1, xmmword ptr cs:aExplorerExeMsS+3Ah; "andtime"
0x180015ca2  movups  [rbp+50h+var_30+0Ah], xmm1
0x180015ca6  lea     rax, [rbp+50h+ProcessInformation]
0x180015caa  mov     [rsp+150h+lpProcessInformation], rax; lpProcessInformation
0x180015caf  lea     rax, [rsp+150h+StartupInfo]
0x180015cb4  mov     [rsp+150h+lpStartupInfo], rax; lpStartupInfo
0x180015cb9  mov     [rsp+150h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180015cc2  mov     [rsp+150h+lpEnvironment], 0; lpEnvironment
0x180015ccb  mov     [rsp+150h+dwCreationFlags], 0; dwCreationFlags
0x180015cd3  mov     [rsp+150h+bInheritHandles], 0; bInheritHandles
0x180015cdb  xor     r9d, r9d; lpThreadAttributes
0x180015cde  xor     r8d, r8d; lpProcessAttributes
0x180015ce1  lea     rdx, [rbp+50h+CommandLine]; lpCommandLine
0x180015ce5  xor     ecx, ecx; lpApplicationName
0x180015ce7  call    cs:__imp_CreateProcessW
0x180015ced  test    eax, eax
0x180015cef  jz      short loc_180015D0A
0x180015cf1  mov     rcx, [rbp+50h+ProcessInformation.hProcess]; hObject
0x180015cf5  call    cs:__imp_CloseHandle
0x180015cfb  mov     rcx, [rbp+50h+ProcessInformation.hThread]; hObject
0x180015cff  call    cs:__imp_CloseHandle
0x180015d05  jmp     loc_180015D8C
0x180015d0a  call    cs:__imp_GetLastError
0x180015d10  mov     r8d, eax
0x180015d13  mov     ecx, cs:dword_180030000
0x180015d19  cmp     ecx, 5
0x180015d1c  jbe     short loc_180015D8C
0x180015d1e  mov     rdx, 200000000000h
0x180015d28  call    _tlgKeywordOn
0x180015d2d  test    al, al
0x180015d2f  jz      short loc_180015D8C
0x180015d31  mov     dword ptr [rsp+150h+var_100], r8d
0x180015d36  mov     [rsp+150h+var_F8], 1000000h
0x180015d3f  lea     rax, [rsp+150h+var_100]
0x180015d44  mov     qword ptr [rsp+150h+dwCreationFlags], rax
0x180015d49  lea     rax, [rsp+150h+var_F8]
0x180015d4e  mov     qword ptr [rsp+150h+bInheritHandles], rax
0x180015d53  lea     rdx, byte_18002A115
0x180015d5a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180015d5f  jmp     short loc_180015D8C
0x180015d61  lea     rdi, aAccept; "Accept"
0x180015d68  mov     rdx, rbx
0x180015d6b  lea     rcx, [rbp+50h+ProcessInformation]
0x180015d6f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180015d74  nop
0x180015d75  mov     rcx, rax
0x180015d78  call    ?SystemTimezoneSetter@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemTimezoneSetter(std::wstring const &)
0x180015d7d  nop
0x180015d7e  xor     r8d, r8d
0x180015d81  mov     dl, 1
0x180015d83  lea     rcx, [rbp+50h+ProcessInformation]
0x180015d87  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015d8c  mov     eax, cs:dword_180030000
0x180015d92  cmp     eax, 5
0x180015d95  jbe     short loc_180015DD8
0x180015d97  mov     rdx, 400000000000h
0x180015da1  call    _tlgKeywordOn
0x180015da6  test    al, al
0x180015da8  jz      short loc_180015DD8
0x180015daa  mov     [rsp+150h+var_F8], rdi
0x180015daf  mov     [rsp+150h+var_100], 1000800h
0x180015db8  lea     rax, [rsp+150h+var_F8]
0x180015dbd  mov     qword ptr [rsp+150h+dwCreationFlags], rax
0x180015dc2  lea     rax, [rsp+150h+var_100]
0x180015dc7  mov     qword ptr [rsp+150h+bInheritHandles], rax
0x180015dcc  lea     rdx, byte_18002A085
0x180015dd3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180015dd8  call    TraceLoggingUnregister_EventUnregister
0x180015ddd  jmp     short loc_180015E03
0x180015ddf  mov     rdx, rbx
0x180015de2  lea     rcx, [rbp+50h+ProcessInformation]
0x180015de6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180015deb  nop
0x180015dec  mov     rcx, rax
0x180015def  call    ?SystemTimezoneSetter@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SystemTimezoneSetter(std::wstring const &)
0x180015df4  nop
0x180015df5  xor     r8d, r8d
0x180015df8  mov     dl, 1
0x180015dfa  lea     rcx, [rbp+50h+ProcessInformation]
0x180015dfe  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015e03  xor     eax, eax
0x180015e05  mov     rcx, [rbp+50h+var_10]
0x180015e09  xor     rcx, rsp; StackCookie
0x180015e0c  call    __security_check_cookie
0x180015e11  lea     r11, [rsp+150h+var_s0]
0x180015e19  mov     rbx, [r11+10h]
0x180015e1d  mov     rdi, [r11+18h]
0x180015e21  mov     rsp, r11
0x180015e24  pop     rbp
0x180015e25  retn
```
