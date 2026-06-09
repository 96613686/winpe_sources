# NetworkingTriageScenario::EnumToString(NetworkingTriageScenario::EventSources)

- ea: `0x180006408`
- end: `0x1800065cc`
- name: `?EnumToString@NetworkingTriageScenario@@YAPEBDW4EventSources@1@@Z`
- size: `452`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004f70`
- `0x18000e514`
- `0x18000e5b0`
- `0x18000e6c8`
- `0x18000e7c8`
- `0x18000e8a8`

## callees

- `0x180006408`
- `0x18001c57c`

## string_xrefs

- `0x18000659b`: `SharedAccess`

## pseudocode

```c
const char *__fastcall NetworkingTriageScenario::EnumToString(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx

  if ( a1 <= 13 )
  {
    if ( a1 == 13 )
      return "WlanMediaManager";
    if ( a1 > 6 )
    {
      v6 = a1 - 7;
      if ( !v6 )
        return "NetworkStatus";
      v7 = v6 - 1;
      if ( !v7 )
        return "NetworkUX";
      v8 = v7 - 1;
      if ( !v8 )
        return "NetworkIcon";
      v9 = v8 - 1;
      if ( !v9 )
        return "WiFiNetworkManager";
      v10 = v9 - 1;
      if ( !v10 )
        return "NetworkSettingHandlers";
      if ( v10 == 1 )
        return "WiFiWinRTAPIs";
    }
    else
    {
      if ( a1 == 6 )
        return "PNI";
      if ( !a1 )
        return "NetworkListManager";
      v1 = a1 - 1;
      if ( !v1 )
        return "DUSM";
      v2 = v1 - 1;
      if ( !v2 )
        return "NCSI";
      v3 = v2 - 1;
      if ( !v3 )
        return "TcpIp";
      v4 = v3 - 1;
      if ( !v4 )
        return "WindowsConnectionManager";
      if ( v4 == 1 )
        return "Wwan";
    }
    goto LABEL_51;
  }
  if ( a1 <= 20 )
  {
    if ( a1 == 20 )
      return "EthernetMediaManager";
    v11 = a1 - 14;
    if ( !v11 )
      return "EapRequestHandler";
    v12 = v11 - 1;
    if ( !v12 )
      return "WiFi";
    v13 = v12 - 1;
    if ( !v13 )
      return "Firewall";
    v14 = v13 - 1;
    if ( !v14 )
      return "EapTls";
    v15 = v14 - 1;
    if ( !v15 )
      return "EapHost";
    if ( v15 == 1 )
      return "Peap";
    goto LABEL_51;
  }
  v16 = a1 - 21;
  if ( !v16 )
    return "Dot3";
  v17 = v16 - 1;
  if ( !v17 )
    return "SettingsApp";
  v18 = v17 - 2;
  if ( !v18 )
    return "EsimPolicyManager";
  v19 = v18 - 1;
  if ( !v19 )
    return "TetheringSvc";
  if ( v19 != 1 )
  {
LABEL_51:
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return "Unknown";
  }
  return "SharedAccess";
}

```

## disassembly

```asm
0x180006408  sub     rsp, 28h
0x18000640c  cmp     ecx, 0Dh
0x18000640f  jg      loc_18000650D
0x180006415  jz      loc_180006501
0x18000641b  cmp     ecx, 6
0x18000641e  jg      short loc_180006497
0x180006420  jz      short loc_18000648B
0x180006422  test    ecx, ecx
0x180006424  jz      short loc_18000647F
0x180006426  sub     ecx, 1
0x180006429  jz      short loc_180006473
0x18000642b  sub     ecx, 1
0x18000642e  jz      short loc_180006467
0x180006430  sub     ecx, 1
0x180006433  jz      short loc_18000645B
0x180006435  sub     ecx, 1
0x180006438  jz      short loc_18000644F
0x18000643a  cmp     ecx, 1
0x18000643d  jnz     loc_18000658D
0x180006443  lea     rax, aWwan; "Wwan"
0x18000644a  jmp     loc_1800065C6
0x18000644f  lea     rax, aWindowsconnect; "WindowsConnectionManager"
0x180006456  jmp     loc_1800065C6
0x18000645b  lea     rax, aTcpip; "TcpIp"
0x180006462  jmp     loc_1800065C6
0x180006467  lea     rax, aNcsi; "NCSI"
0x18000646e  jmp     loc_1800065C6
0x180006473  lea     rax, aDusm; "DUSM"
0x18000647a  jmp     loc_1800065C6
0x18000647f  lea     rax, aNetworklistman; "NetworkListManager"
0x180006486  jmp     loc_1800065C6
0x18000648b  lea     rax, aPni; "PNI"
0x180006492  jmp     loc_1800065C6
0x180006497  sub     ecx, 7
0x18000649a  jz      short loc_1800064F5
0x18000649c  sub     ecx, 1
0x18000649f  jz      short loc_1800064E9
0x1800064a1  sub     ecx, 1
0x1800064a4  jz      short loc_1800064DD
0x1800064a6  sub     ecx, 1
0x1800064a9  jz      short loc_1800064D1
0x1800064ab  sub     ecx, 1
0x1800064ae  jz      short loc_1800064C5
0x1800064b0  cmp     ecx, 1
0x1800064b3  jnz     loc_18000658D
0x1800064b9  lea     rax, aWifiwinrtapis; "WiFiWinRTAPIs"
0x1800064c0  jmp     loc_1800065C6
0x1800064c5  lea     rax, aNetworksetting; "NetworkSettingHandlers"
0x1800064cc  jmp     loc_1800065C6
0x1800064d1  lea     rax, aWifinetworkman; "WiFiNetworkManager"
0x1800064d8  jmp     loc_1800065C6
0x1800064dd  lea     rax, aNetworkicon; "NetworkIcon"
0x1800064e4  jmp     loc_1800065C6
0x1800064e9  lea     rax, aNetworkux; "NetworkUX"
0x1800064f0  jmp     loc_1800065C6
0x1800064f5  lea     rax, aNetworkstatus; "NetworkStatus"
0x1800064fc  jmp     loc_1800065C6
0x180006501  lea     rax, aWlanmediamanag; "WlanMediaManager"
0x180006508  jmp     loc_1800065C6
0x18000650d  cmp     ecx, 14h
0x180006510  jg      short loc_180006574
0x180006512  jz      short loc_18000656B
0x180006514  sub     ecx, 0Eh
0x180006517  jz      short loc_180006562
0x180006519  sub     ecx, 1
0x18000651c  jz      short loc_180006559
0x18000651e  sub     ecx, 1
0x180006521  jz      short loc_180006550
0x180006523  sub     ecx, 1
0x180006526  jz      short loc_180006547
0x180006528  sub     ecx, 1
0x18000652b  jz      short loc_18000653E
0x18000652d  cmp     ecx, 1
0x180006530  jnz     short loc_18000658D
0x180006532  lea     rax, aPeap; "Peap"
0x180006539  jmp     loc_1800065C6
0x18000653e  lea     rax, aEaphost; "EapHost"
0x180006545  jmp     short loc_1800065C6
0x180006547  lea     rax, aEaptls; "EapTls"
0x18000654e  jmp     short loc_1800065C6
0x180006550  lea     rax, aFirewall; "Firewall"
0x180006557  jmp     short loc_1800065C6
0x180006559  lea     rax, aWifi; "WiFi"
0x180006560  jmp     short loc_1800065C6
0x180006562  lea     rax, aEaprequesthand; "EapRequestHandler"
0x180006569  jmp     short loc_1800065C6
0x18000656b  lea     rax, aEthernetmediam; "EthernetMediaManager"
0x180006572  jmp     short loc_1800065C6
0x180006574  sub     ecx, 15h
0x180006577  jz      short loc_1800065BF
0x180006579  sub     ecx, 1
0x18000657c  jz      short loc_1800065B6
0x18000657e  sub     ecx, 2
0x180006581  jz      short loc_1800065AD
0x180006583  sub     ecx, 1
0x180006586  jz      short loc_1800065A4
0x180006588  cmp     ecx, 1
0x18000658b  jz      short loc_18000659B
0x18000658d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006592  lea     rax, aUnknown; "Unknown"
0x180006599  jmp     short loc_1800065C6
0x18000659b  lea     rax, aSharedaccess; "SharedAccess"
0x1800065a2  jmp     short loc_1800065C6
0x1800065a4  lea     rax, aTetheringsvc; "TetheringSvc"
0x1800065ab  jmp     short loc_1800065C6
0x1800065ad  lea     rax, aEsimpolicymana; "EsimPolicyManager"
0x1800065b4  jmp     short loc_1800065C6
0x1800065b6  lea     rax, aSettingsapp; "SettingsApp"
0x1800065bd  jmp     short loc_1800065C6
0x1800065bf  lea     rax, aDot3; "Dot3"
0x1800065c6  add     rsp, 28h
0x1800065ca  retn
```
