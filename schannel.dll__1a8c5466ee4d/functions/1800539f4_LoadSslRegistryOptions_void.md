# LoadSslRegistryOptions(void)

- ea: `0x1800539f4`
- end: `0x180053be5`
- name: `?LoadSslRegistryOptions@@YAHXZ`
- size: `497`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025c38`

## callees

- `0x180021da8`
- `0x180043f78`
- `0x1800539f4`
- `0x180053bec`
- `0x180053d90`
- `0x180069730`
- `0x180069900`
- `0x18006a7d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053a1c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053a8b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053abe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053af1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053a1c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053a8b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053abe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053af1`
- `ntdll!RtlRegisterWait` at `0x180053bd0`
- `ntdll!RtlRegisterWait` at `0x180053bd0`
- `bcrypt!BCryptRegisterConfigChangeNotify` at `0x180053b69`
- `bcrypt!BCryptRegisterConfigChangeNotify` at `0x180053b69`

## string_xrefs

- `0x180053a37`: `System\CurrentControlSet\Control\SecurityProviders\Schannel`
- `0x180053b0c`: `System\CurrentControlSet\Control\Cryptography\Configuration\Local\SSL\00010002`
- `0x180053ae1`: `Software\Policies\Microsoft\Cryptography\Configuration\SSL\00010002`

## pseudocode

```c
__int64 LoadSslRegistryOptions(void)
{
  NTSTATUS v0; // eax
  CCipherMill *v2; // rcx

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::GetImpl'::`2'::impl)
    || !qword_1800AE080 )
  {
    qword_1800AE080 = (__int64)CreateEventW(0, 0, 0, 0);
  }
  qword_1800AE098 = (__int64)SslWatchParamKey;
  qword_1800AE090 = (__int64)L"System\\CurrentControlSet\\Control\\SecurityProviders\\Schannel";
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::GetImpl'::`2'::impl) )
    SslWatchParamKey(&g_BaseSslRegOptions, 0);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::GetImpl'::`2'::impl)
    && !LsaTable )
  {
    return 1;
  }
  qword_1800AE0A8 = (__int64)CreateEventW(0, 0, 0, 0);
  qword_1800AE0C0 = (__int64)FipsWatchParamKey;
  qword_1800AE0B8 = (__int64)L"System\\CurrentControlSet\\Control\\Lsa";
  qword_1800AE0D0 = (__int64)CreateEventW(0, 0, 0, 0);
  qword_1800AE0E8 = (__int64)UserMappingsWatchParamKey;
  qword_1800AE0E0 = (__int64)L"Software\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL\\00010002";
  qword_1800AE058 = (__int64)CreateEventW(0, 0, 0, 0);
  qword_1800AE070 = (__int64)DefaultEccCurveWatchParamKey;
  qword_1800AE068 = (__int64)L"System\\CurrentControlSet\\Control\\Cryptography\\Configuration\\Local\\SSL\\00010002";
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::GetImpl'::`2'::impl) )
    SslWatchParamKey(&g_BaseSslRegOptions, 0);
  FipsWatchParamKey(&g_FipsRegOptions, 1u);
  UserMappingsWatchParamKey(&g_UserMappingRegOptions, 0);
  DefaultEccCurveWatchParamKey(&g_DefaultEccCurveRegOptions, 1u);
  v0 = BCryptRegisterConfigChangeNotify(&g_hBcryptEvent);
  if ( v0 >= 0 )
  {
    RtlRegisterWait(&g_hBcryptWait, g_hBcryptEvent, WatchBcryptEvent, 0, 0xFFFFFFFF, 0);
    CCipherMill::BuildCipherMill(v2);
    return 1;
  }
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4fb7ce66239637259400787d336cb585_Traceguids, (unsigned int)v0);
  return 0;
}

```

## disassembly

```asm
0x1800539f4  sub     rsp, 38h
0x1800539f8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions> `wil::Feature<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::GetImpl(void)'::`2'::impl
0x1800539ff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::__private_IsEnabled(void)
0x180053a04  test    al, al
0x180053a06  jz      short loc_180053A12
0x180053a08  cmp     cs:qword_1800AE080, 0
0x180053a10  jnz     short loc_180053A29
0x180053a12  xor     r9d, r9d; lpName
0x180053a15  xor     r8d, r8d; bInitialState
0x180053a18  xor     edx, edx; bManualReset
0x180053a1a  xor     ecx, ecx; lpEventAttributes
0x180053a1c  call    cs:__imp_CreateEventW
0x180053a22  mov     cs:qword_1800AE080, rax
0x180053a29  lea     rax, ?SslWatchParamKey@@YAXPEAXE@Z; SslWatchParamKey(void *,uchar)
0x180053a30  mov     cs:qword_1800AE098, rax
0x180053a37  lea     rax, SubKey; "System\\CurrentControlSet\\Control\\Sec"...
0x180053a3e  mov     cs:qword_1800AE090, rax
0x180053a45  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions> `wil::Feature<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::GetImpl(void)'::`2'::impl
0x180053a4c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::__private_IsEnabled(void)
0x180053a51  test    al, al
0x180053a53  jz      short loc_180053A63
0x180053a55  xor     edx, edx; unsigned __int8
0x180053a57  lea     rcx, ?g_BaseSslRegOptions@@3USSL_REG_OPTIONS@@A; void *
0x180053a5e  call    ?SslWatchParamKey@@YAXPEAXE@Z; SslWatchParamKey(void *,uchar)
0x180053a63  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions> `wil::Feature<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::GetImpl(void)'::`2'::impl
0x180053a6a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::__private_IsEnabled(void)
0x180053a6f  test    al, al
0x180053a71  jz      short loc_180053A81
0x180053a73  cmp     cs:LsaTable, 0
0x180053a7b  jz      loc_180053BDB
0x180053a81  xor     r9d, r9d; lpName
0x180053a84  xor     r8d, r8d; bInitialState
0x180053a87  xor     edx, edx; bManualReset
0x180053a89  xor     ecx, ecx; lpEventAttributes
0x180053a8b  call    cs:__imp_CreateEventW
0x180053a91  mov     cs:qword_1800AE0A8, rax
0x180053a98  xor     r9d, r9d; lpName
0x180053a9b  lea     rax, ?FipsWatchParamKey@@YAXPEAXE@Z; FipsWatchParamKey(void *,uchar)
0x180053aa2  xor     r8d, r8d; bInitialState
0x180053aa5  mov     cs:qword_1800AE0C0, rax
0x180053aac  xor     edx, edx; bManualReset
0x180053aae  lea     rax, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Lsa"
0x180053ab5  xor     ecx, ecx; lpEventAttributes
0x180053ab7  mov     cs:qword_1800AE0B8, rax
0x180053abe  call    cs:__imp_CreateEventW
0x180053ac4  mov     cs:qword_1800AE0D0, rax
0x180053acb  xor     r9d, r9d; lpName
0x180053ace  lea     rax, ?UserMappingsWatchParamKey@@YAXPEAXE@Z; UserMappingsWatchParamKey(void *,uchar)
0x180053ad5  xor     r8d, r8d; bInitialState
0x180053ad8  mov     cs:qword_1800AE0E8, rax
0x180053adf  xor     edx, edx; bManualReset
0x180053ae1  lea     rax, aSoftwarePolici; "Software\\Policies\\Microsoft\\Cryptogr"...
0x180053ae8  xor     ecx, ecx; lpEventAttributes
0x180053aea  mov     cs:qword_1800AE0E0, rax
0x180053af1  call    cs:__imp_CreateEventW
0x180053af7  mov     cs:qword_1800AE058, rax
0x180053afe  lea     rax, ?DefaultEccCurveWatchParamKey@@YAXPEAXE@Z; DefaultEccCurveWatchParamKey(void *,uchar)
0x180053b05  mov     cs:qword_1800AE070, rax
0x180053b0c  lea     rax, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Cry"...
0x180053b13  mov     cs:qword_1800AE068, rax
0x180053b1a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions> `wil::Feature<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::GetImpl(void)'::`2'::impl
0x180053b21  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Schannel_SslCopyTlsExtensions>::__private_IsEnabled(void)
0x180053b26  test    al, al
0x180053b28  jnz     short loc_180053B38
0x180053b2a  xor     edx, edx; unsigned __int8
0x180053b2c  lea     rcx, ?g_BaseSslRegOptions@@3USSL_REG_OPTIONS@@A; void *
0x180053b33  call    ?SslWatchParamKey@@YAXPEAXE@Z; SslWatchParamKey(void *,uchar)
0x180053b38  mov     dl, 1; unsigned __int8
0x180053b3a  lea     rcx, ?g_FipsRegOptions@@3USSL_REG_OPTIONS@@A; void *
0x180053b41  call    ?FipsWatchParamKey@@YAXPEAXE@Z; FipsWatchParamKey(void *,uchar)
0x180053b46  xor     edx, edx; unsigned __int8
0x180053b48  lea     rcx, ?g_UserMappingRegOptions@@3USSL_REG_OPTIONS@@A; void *
0x180053b4f  call    ?UserMappingsWatchParamKey@@YAXPEAXE@Z; UserMappingsWatchParamKey(void *,uchar)
0x180053b54  mov     dl, 1; unsigned __int8
0x180053b56  lea     rcx, ?g_DefaultEccCurveRegOptions@@3USSL_REG_OPTIONS@@A; void *
0x180053b5d  call    ?DefaultEccCurveWatchParamKey@@YAXPEAXE@Z; DefaultEccCurveWatchParamKey(void *,uchar)
0x180053b62  lea     rcx, ?g_hBcryptEvent@@3PEAXEA; phEvent
0x180053b69  call    cs:__imp_BCryptRegisterConfigChangeNotify
0x180053b6f  test    eax, eax
0x180053b71  jns     short loc_180053BA8
0x180053b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b7a  lea     rdx, WPP_GLOBAL_Control
0x180053b81  cmp     rcx, rdx
0x180053b84  jz      short loc_180053BA4
0x180053b86  test    byte ptr [rcx+1Ch], 1
0x180053b8a  jz      short loc_180053BA4
0x180053b8c  mov     rcx, [rcx+10h]
0x180053b90  lea     r8, WPP_4fb7ce66239637259400787d336cb585_Traceguids
0x180053b97  mov     edx, 0Ah
0x180053b9c  mov     r9d, eax
0x180053b9f  call    WPP_SF_d
0x180053ba4  xor     eax, eax
0x180053ba6  jmp     short loc_180053BE0
0x180053ba8  mov     rdx, cs:?g_hBcryptEvent@@3PEAXEA; hObject
0x180053baf  lea     r8, ?WatchBcryptEvent@@YAXPEAXE@Z; Callback
0x180053bb6  mov     [rsp+38h+ulFlags], 0; ulFlags
0x180053bbe  lea     rcx, ?g_hBcryptWait@@3PEAXEA; phNewWaitObject
0x180053bc5  xor     r9d, r9d; pvContext
0x180053bc8  mov     [rsp+38h+ulMilliseconds], 0FFFFFFFFh; ulMilliseconds
0x180053bd0  call    cs:__imp_RtlRegisterWait
0x180053bd6  call    ?BuildCipherMill@CCipherMill@@QEAAKXZ; CCipherMill::BuildCipherMill(void)
0x180053bdb  mov     eax, 1
0x180053be0  add     rsp, 38h
0x180053be4  retn
```
