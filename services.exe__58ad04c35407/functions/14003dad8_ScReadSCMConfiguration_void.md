# ScReadSCMConfiguration(void)

- ea: `0x14003dad8`
- end: `0x14003df27`
- name: `?ScReadSCMConfiguration@@YAXXZ`
- size: `1103`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1400848e0`

## callees

- `0x140004c58`
- `0x14002330c`
- `0x140036e30`
- `0x1400376c4`
- `0x140037830`
- `0x140038698`
- `0x14003dad8`
- `0x140040128`
- `0x1400422c4`
- `0x1400575b0`
- `0x1400840f8`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x14003dc3e`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x14003dc3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003dbbd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003dc1c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003dd85`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003ddd1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003de1d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003de77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003ded7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003dbbd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003dc1c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003dd85`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003ddd1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003de1d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003de77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003ded7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003db36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003db36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003df08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003df08`
- `api-ms-win-core-sysinfo-l1-2-6!IsUserCetAvailableInEnvironment` at `0x14003de9b`
- `api-ms-win-core-sysinfo-l1-2-6!IsUserCetAvailableInEnvironment` at `0x14003de9b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14003db07`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14003db07`

## string_xrefs

- `0x14003de11`: `RemoteAccessExemption`
- `0x14003de6b`: `ValidateServiceDisplayName`

## pseudocode

```c
void __fastcall ScReadSCMConfiguration(__int64 a1)
{
  unsigned int v1; // eax
  unsigned int RetryNetworkLogonTimeout; // eax
  HKEY v3; // rbx
  int v4; // eax
  __int64 v5; // rdx
  int IsSvchostDebugValueSet; // eax
  bool v7; // zf
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  HKEY v11; // rcx
  int v12; // eax
  DWORD cbData; // [rsp+30h] [rbp-69h] BYREF
  DWORD Type; // [rsp+34h] [rbp-65h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-61h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-59h] BYREF
  BYTE v17[4]; // [rsp+48h] [rbp-51h] BYREF
  int v18; // [rsp+4Ch] [rbp-4Dh] BYREF
  int v19; // [rsp+50h] [rbp-49h] BYREF
  __int64 v20; // [rsp+58h] [rbp-41h] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+60h] [rbp-39h] BYREF
  BYTE *v22; // [rsp+A0h] [rbp+7h]
  __int64 v23; // [rsp+A8h] [rbp+Fh]
  __int64 *v24; // [rsp+B0h] [rbp+17h]
  __int64 v25; // [rsp+B8h] [rbp+1Fh]

  hKey = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)v17 = 0;
  g_StateSeparationEnabled = (unsigned __int8)RtlIsStateSeparationEnabled(a1);
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control", 0, 0x20019u, &hKey);
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 10, WPP_73e763182c4133cee281a4c48659d989_Traceguids, v1);
    hKey = 0;
  }
  RetryNetworkLogonTimeout = ScGetRetryNetworkLogonTimeout();
  v3 = hKey;
  g_NetworkLogonRetryTimeout = RetryNetworkLogonTimeout;
  *(_DWORD *)&g_fEnableTakeOwnershipEvent = 0;
  cbData = 4;
  if ( hKey )
  {
    if ( !RegQueryValueExW(hKey, L"EnableTakeOwnershipEvent", 0, &Type, &g_fEnableTakeOwnershipEvent, &cbData)
      && Type != 4 )
    {
      *(_DWORD *)&g_fEnableTakeOwnershipEvent = 0;
    }
    v3 = hKey;
  }
  memset(&Buffer, 0, sizeof(Buffer));
  Buffer.dwLength = 64;
  *(_DWORD *)Data = 0;
  cbData = 4;
  if ( v3 )
  {
    if ( RegQueryValueExW(v3, L"SvcHostSplitThresholdInKB", 0, &Type, Data, &cbData) || Type == 4 )
    {
      v4 = *(_DWORD *)Data;
    }
    else
    {
      v4 = 0;
      *(_DWORD *)Data = 0;
    }
    if ( v4 && GlobalMemoryStatusEx(&Buffer) && Buffer.ullTotalPhys >= (unsigned __int64)*(unsigned int *)Data << 10 )
    {
      LOBYTE(v5) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_SvchostSplit>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_SvchostSplit>::GetImpl'::`2'::impl,
        v5);
      IsSvchostDebugValueSet = 1;
      goto LABEL_22;
    }
    v3 = hKey;
  }
  IsSvchostDebugValueSet = ScIsSvchostDebugValueSet(v3);
LABEL_22:
  g_fSplitSvcHost = IsSvchostDebugValueSet;
  *(_DWORD *)Data = 0;
  v7 = (unsigned int)ScGetRedirectedSCMConfigDword(L"HandleTracking", (unsigned int *)Data) == 0;
  v10 = 0;
  if ( v7 )
    LOBYTE(v10) = *(_DWORD *)Data != 0;
  g_HandleTrackingEnabled = v10;
  if ( (unsigned int)dword_1400BA2A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400BA2A0, 0x400000000000LL, v9) )
  {
    *(_DWORD *)Data = g_HandleTrackingEnabled;
    v18 = g_StateSeparationEnabled;
    v19 = g_fSplitSvcHost;
    v24 = &v20;
    v22 = Data;
    Buffer.ullAvailVirtual = (DWORDLONG)&v18;
    Buffer.ullAvailPageFile = (DWORDLONG)&v19;
    v20 = 0x1000000;
    v25 = 8;
    v23 = 4;
    Buffer.ullAvailExtendedVirtual = 4;
    Buffer.ullTotalVirtual = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_1400BA2A0);
  }
  v11 = hKey;
  *(_DWORD *)&g_dwRpcOverTcpKeepAliveTimes = 0;
  cbData = 4;
  if ( hKey )
  {
    if ( !RegQueryValueExW(hKey, L"RpcOverTcpKeepAliveTimes", 0, &Type, &g_dwRpcOverTcpKeepAliveTimes, &cbData)
      && Type != 4 )
    {
      *(_DWORD *)&g_dwRpcOverTcpKeepAliveTimes = 0;
    }
    v11 = hKey;
  }
  *(_DWORD *)&g_fDisableRemoteScmEndpoints = 0;
  cbData = 4;
  if ( v11 )
  {
    if ( !RegQueryValueExW(v11, L"DisableRemoteScmEndpoints", 0, &Type, &g_fDisableRemoteScmEndpoints, &cbData)
      && Type != 4 )
    {
      *(_DWORD *)&g_fDisableRemoteScmEndpoints = 0;
    }
    v11 = hKey;
  }
  *(_DWORD *)&g_ExemptRemoteCaller = 0;
  cbData = 4;
  if ( v11 && !RegQueryValueExW(v11, L"RemoteAccessExemption", 0, &Type, &g_ExemptRemoteCaller, &cbData) && Type != 4 )
    *(_DWORD *)&g_ExemptRemoteCaller = 0;
  LOBYTE(v8) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableUniqueServiceDisplayNameValidation>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DisableUniqueServiceDisplayNameValidation>::GetImpl'::`2'::impl,
    v8);
  *(_DWORD *)&g_EnableUniqueDisplayNameValidation = 0;
  cbData = 4;
  if ( hKey
    && !RegQueryValueExW(hKey, L"ValidateServiceDisplayName", 0, &Type, &g_EnableUniqueDisplayNameValidation, &cbData)
    && Type != 4 )
  {
    *(_DWORD *)&g_EnableUniqueDisplayNameValidation = 0;
  }
  g_GlobalProcessAffinityMask = ScGetGlobalProcessAffinityMask();
  g_CetSupportEnabled = IsUserCetAvailableInEnvironment(0);
  *(_DWORD *)v17 = 0;
  cbData = 4;
  if ( hKey )
  {
    if ( RegQueryValueExW(hKey, L"RelaxGroupLoadOrder", 0, &Type, v17, &cbData) || Type == 4 )
    {
      v12 = *(_DWORD *)v17;
    }
    else
    {
      v12 = 0;
      *(_DWORD *)v17 = 0;
    }
    if ( v12 )
      g_RelaxGroupLoadOrder = 1;
    if ( hKey )
      RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x14003dad8  push    rbp
0x14003dada  push    rbx
0x14003dadb  push    rsi
0x14003dadc  push    r14
0x14003dade  lea     rbp, [rsp-3Fh]
0x14003dae3  sub     rsp, 0D8h
0x14003daea  mov     rax, cs:__security_cookie
0x14003daf1  xor     rax, rsp
0x14003daf4  mov     [rbp+57h+var_30], rax
0x14003daf8  xor     esi, esi
0x14003dafa  mov     [rbp+57h+hKey], rsi
0x14003dafe  mov     [rbp+57h+Type], esi
0x14003db01  mov     [rbp+57h+cbData], esi
0x14003db04  mov     dword ptr [rbp+57h+var_A8], esi
0x14003db07  call    cs:__imp_RtlIsStateSeparationEnabled
0x14003db0d  movzx   eax, al
0x14003db10  mov     r9d, 20019h; samDesired
0x14003db16  mov     cs:?g_StateSeparationEnabled@@3HA, eax; int g_StateSeparationEnabled
0x14003db1c  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control"
0x14003db23  lea     rax, [rbp+57h+hKey]
0x14003db27  xor     r8d, r8d; ulOptions
0x14003db2a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003db31  mov     [rsp+0F0h+phkResult], rax; phkResult
0x14003db36  call    cs:__imp_RegOpenKeyExW
0x14003db3c  test    eax, eax
0x14003db3e  jz      short loc_14003DB73
0x14003db40  mov     rcx, cs:WPP_GLOBAL_Control
0x14003db47  lea     rdx, WPP_GLOBAL_Control
0x14003db4e  cmp     rcx, rdx
0x14003db51  jz      short loc_14003DB6F
0x14003db53  test    byte ptr [rcx+1Ch], 1
0x14003db57  jz      short loc_14003DB6F
0x14003db59  mov     rcx, [rcx+10h]
0x14003db5d  lea     edx, [rsi+0Ah]
0x14003db60  mov     r9d, eax
0x14003db63  lea     r8, WPP_73e763182c4133cee281a4c48659d989_Traceguids
0x14003db6a  call    WPP_SF_d
0x14003db6f  mov     [rbp+57h+hKey], rsi
0x14003db73  call    ?ScGetRetryNetworkLogonTimeout@@YAKXZ; ScGetRetryNetworkLogonTimeout(void)
0x14003db78  mov     rbx, [rbp+57h+hKey]
0x14003db7c  mov     r14d, 4
0x14003db82  mov     cs:?g_NetworkLogonRetryTimeout@@3KA, eax; ulong g_NetworkLogonRetryTimeout
0x14003db88  mov     cs:?g_fEnableTakeOwnershipEvent@@3HA, esi; int g_fEnableTakeOwnershipEvent
0x14003db8e  mov     [rbp+57h+cbData], r14d
0x14003db92  test    rbx, rbx
0x14003db95  jz      short loc_14003DBD7
0x14003db97  lea     rax, [rbp+57h+cbData]
0x14003db9b  xor     r8d, r8d; lpReserved
0x14003db9e  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x14003dba3  lea     r9, [rbp+57h+Type]; lpType
0x14003dba7  lea     rax, ?g_fEnableTakeOwnershipEvent@@3HA; int g_fEnableTakeOwnershipEvent
0x14003dbae  mov     rcx, rbx; hKey
0x14003dbb1  lea     rdx, aEnabletakeowne; "EnableTakeOwnershipEvent"
0x14003dbb8  mov     [rsp+0F0h+phkResult], rax; lpData
0x14003dbbd  call    cs:__imp_RegQueryValueExW
0x14003dbc3  test    eax, eax
0x14003dbc5  jnz     short loc_14003DBD3
0x14003dbc7  cmp     [rbp+57h+Type], r14d
0x14003dbcb  jz      short loc_14003DBD3
0x14003dbcd  mov     cs:?g_fEnableTakeOwnershipEvent@@3HA, esi; int g_fEnableTakeOwnershipEvent
0x14003dbd3  mov     rbx, [rbp+57h+hKey]
0x14003dbd7  xor     edx, edx; Val
0x14003dbd9  lea     rcx, [rbp+57h+Buffer]; void *
0x14003dbdd  lea     r8d, [rdx+40h]; Size
0x14003dbe1  call    memset
0x14003dbe6  mov     [rbp+57h+Buffer.dwLength], 40h ; '@'
0x14003dbed  mov     dword ptr [rbp+57h+Data], esi
0x14003dbf0  mov     [rbp+57h+cbData], r14d
0x14003dbf4  test    rbx, rbx
0x14003dbf7  jz      short loc_14003DC6E
0x14003dbf9  lea     rax, [rbp+57h+cbData]
0x14003dbfd  xor     r8d, r8d; lpReserved
0x14003dc00  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x14003dc05  lea     r9, [rbp+57h+Type]; lpType
0x14003dc09  lea     rax, [rbp+57h+Data]
0x14003dc0d  mov     rcx, rbx; hKey
0x14003dc10  lea     rdx, aSvchostsplitth; "SvcHostSplitThresholdInKB"
0x14003dc17  mov     [rsp+0F0h+phkResult], rax; lpData
0x14003dc1c  call    cs:__imp_RegQueryValueExW
0x14003dc22  test    eax, eax
0x14003dc24  jnz     short loc_14003DC33
0x14003dc26  cmp     [rbp+57h+Type], r14d
0x14003dc2a  jz      short loc_14003DC33
0x14003dc2c  mov     eax, esi
0x14003dc2e  mov     dword ptr [rbp+57h+Data], eax
0x14003dc31  jmp     short loc_14003DC36
0x14003dc33  mov     eax, dword ptr [rbp+57h+Data]
0x14003dc36  test    eax, eax
0x14003dc38  jz      short loc_14003DC6A
0x14003dc3a  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x14003dc3e  call    cs:__imp_GlobalMemoryStatusEx
0x14003dc44  test    eax, eax
0x14003dc46  jz      short loc_14003DC6A
0x14003dc48  mov     eax, dword ptr [rbp+57h+Data]
0x14003dc4b  shl     rax, 0Ah
0x14003dc4f  cmp     [rbp+57h+Buffer.ullTotalPhys], rax
0x14003dc53  jb      short loc_14003DC6A
0x14003dc55  mov     dl, 1
0x14003dc57  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SvchostSplit@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SvchostSplit@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SvchostSplit> `wil::Feature<__WilFeatureTraits_Feature_SvchostSplit>::GetImpl(void)'::`2'::impl
0x14003dc5e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_SvchostSplit@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SvchostSplit>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14003dc63  mov     eax, 1
0x14003dc68  jmp     short loc_14003DC76
0x14003dc6a  mov     rbx, [rbp+57h+hKey]
0x14003dc6e  mov     rcx, rbx; HKEY
0x14003dc71  call    ?ScIsSvchostDebugValueSet@@YAHPEAUHKEY__@@@Z; ScIsSvchostDebugValueSet(HKEY__ *)
0x14003dc76  lea     rdx, [rbp+57h+Data]; unsigned int *
0x14003dc7a  mov     cs:?g_fSplitSvcHost@@3HA, eax; int g_fSplitSvcHost
0x14003dc80  lea     rcx, aHandletracking; "HandleTracking"
0x14003dc87  mov     dword ptr [rbp+57h+Data], esi
0x14003dc8a  call    ?ScGetRedirectedSCMConfigDword@@YAKPEBGPEAK@Z; ScGetRedirectedSCMConfigDword(ushort const *,ulong *)
0x14003dc8f  test    eax, eax
0x14003dc91  mov     eax, esi
0x14003dc93  jnz     short loc_14003DC9B
0x14003dc95  cmp     dword ptr [rbp+57h+Data], esi
0x14003dc98  setnz   al
0x14003dc9b  mov     cs:?g_HandleTrackingEnabled@@3HA, eax; int g_HandleTrackingEnabled
0x14003dca1  mov     eax, cs:dword_1400BA2A0
0x14003dca7  cmp     eax, 5
0x14003dcaa  jbe     loc_14003DD4F
0x14003dcb0  mov     rdx, 400000000000h
0x14003dcba  lea     rcx, dword_1400BA2A0
0x14003dcc1  call    _tlgKeywordOn
0x14003dcc6  test    al, al
0x14003dcc8  jz      loc_14003DD4F
0x14003dcce  mov     eax, cs:?g_HandleTrackingEnabled@@3HA; int g_HandleTrackingEnabled
0x14003dcd4  lea     rdx, word_1400AF3A6
0x14003dcdb  mov     dword ptr [rbp+57h+Data], eax
0x14003dcde  lea     rcx, dword_1400BA2A0
0x14003dce5  mov     eax, cs:?g_StateSeparationEnabled@@3HA; int g_StateSeparationEnabled
0x14003dceb  xor     r9d, r9d
0x14003dcee  mov     [rbp+57h+var_A4], eax
0x14003dcf1  xor     r8d, r8d
0x14003dcf4  mov     eax, cs:?g_fSplitSvcHost@@3HA; int g_fSplitSvcHost
0x14003dcfa  mov     [rbp+57h+var_A0], eax
0x14003dcfd  lea     rax, [rbp+57h+var_98]
0x14003dd01  mov     [rbp+57h+var_40], rax
0x14003dd05  lea     rax, [rbp+57h+Data]
0x14003dd09  mov     [rbp+57h+var_50], rax
0x14003dd0d  lea     rax, [rbp+57h+var_A4]
0x14003dd11  mov     [rbp+57h+Buffer.ullAvailVirtual], rax
0x14003dd15  lea     rax, [rbp+57h+var_A0]
0x14003dd19  mov     [rbp+57h+Buffer.ullAvailPageFile], rax
0x14003dd1d  lea     rax, [rbp+57h+Buffer]
0x14003dd21  mov     [rsp+0F0h+lpcbData], rax
0x14003dd26  mov     dword ptr [rsp+0F0h+phkResult], 6
0x14003dd2e  mov     [rbp+57h+var_98], 1000000h
0x14003dd36  mov     [rbp+57h+var_38], 8
0x14003dd3e  mov     [rbp+57h+var_48], r14
0x14003dd42  mov     [rbp+57h+Buffer.ullAvailExtendedVirtual], r14
0x14003dd46  mov     [rbp+57h+Buffer.ullTotalVirtual], r14
0x14003dd4a  call    _tlgWriteTransfer_EventWriteTransfer
0x14003dd4f  mov     rcx, [rbp+57h+hKey]; hKey
0x14003dd53  mov     cs:?g_dwRpcOverTcpKeepAliveTimes@@3KA, esi; ulong g_dwRpcOverTcpKeepAliveTimes
0x14003dd59  mov     [rbp+57h+cbData], r14d
0x14003dd5d  test    rcx, rcx
0x14003dd60  jz      short loc_14003DD9F
0x14003dd62  lea     rax, [rbp+57h+cbData]
0x14003dd66  xor     r8d, r8d; lpReserved
0x14003dd69  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x14003dd6e  lea     r9, [rbp+57h+Type]; lpType
0x14003dd72  lea     rax, ?g_dwRpcOverTcpKeepAliveTimes@@3KA; ulong g_dwRpcOverTcpKeepAliveTimes
0x14003dd79  lea     rdx, aRpcovertcpkeep; "RpcOverTcpKeepAliveTimes"
0x14003dd80  mov     [rsp+0F0h+phkResult], rax; lpData
0x14003dd85  call    cs:__imp_RegQueryValueExW
0x14003dd8b  test    eax, eax
0x14003dd8d  jnz     short loc_14003DD9B
0x14003dd8f  cmp     [rbp+57h+Type], r14d
0x14003dd93  jz      short loc_14003DD9B
0x14003dd95  mov     cs:?g_dwRpcOverTcpKeepAliveTimes@@3KA, esi; ulong g_dwRpcOverTcpKeepAliveTimes
0x14003dd9b  mov     rcx, [rbp+57h+hKey]; hKey
0x14003dd9f  mov     cs:?g_fDisableRemoteScmEndpoints@@3HA, esi; int g_fDisableRemoteScmEndpoints
0x14003dda5  mov     [rbp+57h+cbData], r14d
0x14003dda9  test    rcx, rcx
0x14003ddac  jz      short loc_14003DDEB
0x14003ddae  lea     rax, [rbp+57h+cbData]
0x14003ddb2  xor     r8d, r8d; lpReserved
0x14003ddb5  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x14003ddba  lea     r9, [rbp+57h+Type]; lpType
0x14003ddbe  lea     rax, ?g_fDisableRemoteScmEndpoints@@3HA; int g_fDisableRemoteScmEndpoints
0x14003ddc5  lea     rdx, aDisableremotes; "DisableRemoteScmEndpoints"
0x14003ddcc  mov     [rsp+0F0h+phkResult], rax; lpData
0x14003ddd1  call    cs:__imp_RegQueryValueExW
0x14003ddd7  test    eax, eax
0x14003ddd9  jnz     short loc_14003DDE7
0x14003dddb  cmp     [rbp+57h+Type], r14d
0x14003dddf  jz      short loc_14003DDE7
0x14003dde1  mov     cs:?g_fDisableRemoteScmEndpoints@@3HA, esi; int g_fDisableRemoteScmEndpoints
0x14003dde7  mov     rcx, [rbp+57h+hKey]; hKey
0x14003ddeb  mov     cs:?g_ExemptRemoteCaller@@3HA, esi; int g_ExemptRemoteCaller
0x14003ddf1  mov     [rbp+57h+cbData], r14d
0x14003ddf5  test    rcx, rcx
0x14003ddf8  jz      short loc_14003DE33
0x14003ddfa  lea     rax, [rbp+57h+cbData]
0x14003ddfe  xor     r8d, r8d; lpReserved
0x14003de01  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x14003de06  lea     r9, [rbp+57h+Type]; lpType
0x14003de0a  lea     rax, ?g_ExemptRemoteCaller@@3HA; int g_ExemptRemoteCaller
0x14003de11  lea     rdx, aRemoteaccessex; "RemoteAccessExemption"
0x14003de18  mov     [rsp+0F0h+phkResult], rax; lpData
0x14003de1d  call    cs:__imp_RegQueryValueExW
0x14003de23  test    eax, eax
0x14003de25  jnz     short loc_14003DE33
0x14003de27  cmp     [rbp+57h+Type], r14d
0x14003de2b  jz      short loc_14003DE33
0x14003de2d  mov     cs:?g_ExemptRemoteCaller@@3HA, esi; int g_ExemptRemoteCaller
0x14003de33  mov     dl, 1
0x14003de35  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DisableUniqueServiceDisplayNameValidation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DisableUniqueServiceDisplayNameValidation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableUniqueServiceDisplayNameValidation> `wil::Feature<__WilFeatureTraits_Feature_DisableUniqueServiceDisplayNameValidation>::GetImpl(void)'::`2'::impl
0x14003de3c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DisableUniqueServiceDisplayNameValidation@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableUniqueServiceDisplayNameValidation>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14003de41  mov     rcx, [rbp+57h+hKey]; hKey
0x14003de45  mov     cs:?g_EnableUniqueDisplayNameValidation@@3HA, esi; int g_EnableUniqueDisplayNameValidation
0x14003de4b  mov     [rbp+57h+cbData], r14d
0x14003de4f  test    rcx, rcx
0x14003de52  jz      short loc_14003DE8D
0x14003de54  lea     rax, [rbp+57h+cbData]
0x14003de58  xor     r8d, r8d; lpReserved
0x14003de5b  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x14003de60  lea     r9, [rbp+57h+Type]; lpType
0x14003de64  lea     rax, ?g_EnableUniqueDisplayNameValidation@@3HA; int g_EnableUniqueDisplayNameValidation
0x14003de6b  lea     rdx, aValidateservic; "ValidateServiceDisplayName"
0x14003de72  mov     [rsp+0F0h+phkResult], rax; lpData
0x14003de77  call    cs:__imp_RegQueryValueExW
0x14003de7d  test    eax, eax
0x14003de7f  jnz     short loc_14003DE8D
0x14003de81  cmp     [rbp+57h+Type], r14d
0x14003de85  jz      short loc_14003DE8D
0x14003de87  mov     cs:?g_EnableUniqueDisplayNameValidation@@3HA, esi; int g_EnableUniqueDisplayNameValidation
0x14003de8d  call    ?ScGetGlobalProcessAffinityMask@@YA_KXZ; ScGetGlobalProcessAffinityMask(void)
0x14003de92  xor     ecx, ecx
0x14003de94  mov     cs:?g_GlobalProcessAffinityMask@@3_KA, rax; unsigned __int64 g_GlobalProcessAffinityMask
0x14003de9b  call    cs:__imp_IsUserCetAvailableInEnvironment
0x14003dea1  mov     rcx, [rbp+57h+hKey]; hKey
0x14003dea5  mov     cs:?g_CetSupportEnabled@@3HA, eax; int g_CetSupportEnabled
0x14003deab  mov     dword ptr [rbp+57h+var_A8], esi
0x14003deae  mov     [rbp+57h+cbData], r14d
0x14003deb2  test    rcx, rcx
0x14003deb5  jz      short loc_14003DF0E
0x14003deb7  lea     rax, [rbp+57h+cbData]
0x14003debb  xor     r8d, r8d; lpReserved
0x14003debe  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x14003dec3  lea     r9, [rbp+57h+Type]; lpType
0x14003dec7  lea     rax, [rbp+57h+var_A8]
0x14003decb  lea     rdx, aRelaxgroupload; "RelaxGroupLoadOrder"
0x14003ded2  mov     [rsp+0F0h+phkResult], rax; lpData
0x14003ded7  call    cs:__imp_RegQueryValueExW
0x14003dedd  test    eax, eax
0x14003dedf  jnz     short loc_14003DEEE
0x14003dee1  cmp     [rbp+57h+Type], r14d
0x14003dee5  jz      short loc_14003DEEE
0x14003dee7  mov     eax, esi
0x14003dee9  mov     dword ptr [rbp+57h+var_A8], eax
0x14003deec  jmp     short loc_14003DEF1
0x14003deee  mov     eax, dword ptr [rbp+57h+var_A8]
0x14003def1  test    eax, eax
0x14003def3  jz      short loc_14003DEFF
0x14003def5  mov     cs:?g_RelaxGroupLoadOrder@@3HA, 1; int g_RelaxGroupLoadOrder
0x14003deff  mov     rcx, [rbp+57h+hKey]; hKey
0x14003df03  test    rcx, rcx
0x14003df06  jz      short loc_14003DF0E
0x14003df08  call    cs:__imp_RegCloseKey
0x14003df0e  mov     rcx, [rbp+57h+var_30]
0x14003df12  xor     rcx, rsp; StackCookie
0x14003df15  call    __security_check_cookie
0x14003df1a  add     rsp, 0D8h
0x14003df21  pop     r14
0x14003df23  pop     rsi
0x14003df24  pop     rbx
0x14003df25  pop     rbp
0x14003df26  retn
```
