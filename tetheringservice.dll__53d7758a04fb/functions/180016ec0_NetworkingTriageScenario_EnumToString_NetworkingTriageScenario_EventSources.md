# NetworkingTriageScenario::EnumToString(NetworkingTriageScenario::EventSources)

- ea: `0x180016ec0`
- end: `0x180017083`
- name: `?EnumToString@NetworkingTriageScenario@@YAPEBDW4EventSources@1@@Z`
- size: `451`
- prototype: `const char *__fastcall(int)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020150`
- `0x18002035c`
- `0x180020524`
- `0x18002072c`
- `0x1800209c4`

## callees

- `0x180016ec0`
- `0x180031190`

## string_xrefs

- `0x180017053`: `SharedAccess`

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
0x180016ec0  sub     rsp, 28h
0x180016ec4  cmp     ecx, 0Dh
0x180016ec7  jg      loc_180016FC5
0x180016ecd  jz      loc_180016FB9
0x180016ed3  cmp     ecx, 6
0x180016ed6  jg      short loc_180016F4F
0x180016ed8  jz      short loc_180016F43
0x180016eda  test    ecx, ecx
0x180016edc  jz      short loc_180016F37
0x180016ede  sub     ecx, 1
0x180016ee1  jz      short loc_180016F2B
0x180016ee3  sub     ecx, 1
0x180016ee6  jz      short loc_180016F1F
0x180016ee8  sub     ecx, 1
0x180016eeb  jz      short loc_180016F13
0x180016eed  sub     ecx, 1
0x180016ef0  jz      short loc_180016F07
0x180016ef2  cmp     ecx, 1
0x180016ef5  jnz     loc_180017045
0x180016efb  lea     rax, aWwan; "Wwan"
0x180016f02  jmp     loc_18001707E
0x180016f07  lea     rax, aWindowsconnect; "WindowsConnectionManager"
0x180016f0e  jmp     loc_18001707E
0x180016f13  lea     rax, aTcpip; "TcpIp"
0x180016f1a  jmp     loc_18001707E
0x180016f1f  lea     rax, aNcsi; "NCSI"
0x180016f26  jmp     loc_18001707E
0x180016f2b  lea     rax, aDusm; "DUSM"
0x180016f32  jmp     loc_18001707E
0x180016f37  lea     rax, aNetworklistman; "NetworkListManager"
0x180016f3e  jmp     loc_18001707E
0x180016f43  lea     rax, aPni; "PNI"
0x180016f4a  jmp     loc_18001707E
0x180016f4f  sub     ecx, 7
0x180016f52  jz      short loc_180016FAD
0x180016f54  sub     ecx, 1
0x180016f57  jz      short loc_180016FA1
0x180016f59  sub     ecx, 1
0x180016f5c  jz      short loc_180016F95
0x180016f5e  sub     ecx, 1
0x180016f61  jz      short loc_180016F89
0x180016f63  sub     ecx, 1
0x180016f66  jz      short loc_180016F7D
0x180016f68  cmp     ecx, 1
0x180016f6b  jnz     loc_180017045
0x180016f71  lea     rax, aWifiwinrtapis; "WiFiWinRTAPIs"
0x180016f78  jmp     loc_18001707E
0x180016f7d  lea     rax, aNetworksetting; "NetworkSettingHandlers"
0x180016f84  jmp     loc_18001707E
0x180016f89  lea     rax, aWifinetworkman; "WiFiNetworkManager"
0x180016f90  jmp     loc_18001707E
0x180016f95  lea     rax, aNetworkicon; "NetworkIcon"
0x180016f9c  jmp     loc_18001707E
0x180016fa1  lea     rax, aNetworkux; "NetworkUX"
0x180016fa8  jmp     loc_18001707E
0x180016fad  lea     rax, aNetworkstatus; "NetworkStatus"
0x180016fb4  jmp     loc_18001707E
0x180016fb9  lea     rax, aWlanmediamanag; "WlanMediaManager"
0x180016fc0  jmp     loc_18001707E
0x180016fc5  cmp     ecx, 14h
0x180016fc8  jg      short loc_18001702C
0x180016fca  jz      short loc_180017023
0x180016fcc  sub     ecx, 0Eh
0x180016fcf  jz      short loc_18001701A
0x180016fd1  sub     ecx, 1
0x180016fd4  jz      short loc_180017011
0x180016fd6  sub     ecx, 1
0x180016fd9  jz      short loc_180017008
0x180016fdb  sub     ecx, 1
0x180016fde  jz      short loc_180016FFF
0x180016fe0  sub     ecx, 1
0x180016fe3  jz      short loc_180016FF6
0x180016fe5  cmp     ecx, 1
0x180016fe8  jnz     short loc_180017045
0x180016fea  lea     rax, aPeap; "Peap"
0x180016ff1  jmp     loc_18001707E
0x180016ff6  lea     rax, aEaphost; "EapHost"
0x180016ffd  jmp     short loc_18001707E
0x180016fff  lea     rax, aEaptls; "EapTls"
0x180017006  jmp     short loc_18001707E
0x180017008  lea     rax, aFirewall; "Firewall"
0x18001700f  jmp     short loc_18001707E
0x180017011  lea     rax, aWifi; "WiFi"
0x180017018  jmp     short loc_18001707E
0x18001701a  lea     rax, aEaprequesthand; "EapRequestHandler"
0x180017021  jmp     short loc_18001707E
0x180017023  lea     rax, aEthernetmediam; "EthernetMediaManager"
0x18001702a  jmp     short loc_18001707E
0x18001702c  sub     ecx, 15h
0x18001702f  jz      short loc_180017077
0x180017031  sub     ecx, 1
0x180017034  jz      short loc_18001706E
0x180017036  sub     ecx, 2
0x180017039  jz      short loc_180017065
0x18001703b  sub     ecx, 1
0x18001703e  jz      short loc_18001705C
0x180017040  cmp     ecx, 1
0x180017043  jz      short loc_180017053
0x180017045  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001704a  lea     rax, aUnknown; "Unknown"
0x180017051  jmp     short loc_18001707E
0x180017053  lea     rax, aSharedaccess_0; "SharedAccess"
0x18001705a  jmp     short loc_18001707E
0x18001705c  lea     rax, aTetheringsvc; "TetheringSvc"
0x180017063  jmp     short loc_18001707E
0x180017065  lea     rax, aEsimpolicymana; "EsimPolicyManager"
0x18001706c  jmp     short loc_18001707E
0x18001706e  lea     rax, aSettingsapp; "SettingsApp"
0x180017075  jmp     short loc_18001707E
0x180017077  lea     rax, aDot3; "Dot3"
0x18001707e  add     rsp, 28h
0x180017082  retn
```
