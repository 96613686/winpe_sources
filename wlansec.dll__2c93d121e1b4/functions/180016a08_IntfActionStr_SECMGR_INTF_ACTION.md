# IntfActionStr(SECMGR_INTF_ACTION)

- ea: `0x180016a08`
- end: `0x180016b12`
- name: `?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z`
- size: `266`
- prototype: ``
- caller_count: `27`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012df0`
- `0x1800141d0`
- `0x180014998`
- `0x180014d24`
- `0x180015600`
- `0x180017cf0`
- `0x18001d400`
- `0x18001d8ac`
- `0x18002a638`
- `0x180030690`
- `0x180030cb0`
- `0x180035ed0`
- `0x1800363c0`
- `0x180038518`
- `0x180039810`
- `0x18003c910`
- `0x180052140`
- `0x180052fa0`
- `0x1800536d0`
- `0x1800540d0`
- `0x180054f40`
- `0x1800552e0`
- `0x180056ea4`
- `0x180057390`
- `0x180058fc8`
- `0x180059604`
- `0x18006a6a4`

## callees

- `0x180016a08`

## string_xrefs

- `0x180016a27`: `PostAssociate Security`
- `0x180016a39`: `Stop Security`
- `0x180016a5a`: `PreAssociate Completion`
- `0x180016a63`: `Stop PostAssociate Security`
- `0x180016a91`: `PreAssociate Security`
- `0x180016a7f`: `Security UI Response/Check pending`
- `0x180016b0a`: `Redo Security`
- `0x180016af8`: `Post connect key update`

## pseudocode

```c
const wchar_t *__fastcall IntfActionStr(int a1)
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

  if ( a1 == 10 )
    return L"Device Indication";
  if ( a1 <= 10 )
  {
    v1 = a1 - 1;
    if ( !v1 )
      return L"PreAssociate Security";
    v2 = v1 - 1;
    if ( !v2 )
      return L"PreAssociate Completion";
    v3 = v2 - 1;
    if ( !v3 )
      return L"Stop Security";
    v4 = v3 - 1;
    if ( !v4 )
      return L"PostAssociate Security";
    v6 = v4 - 1;
    if ( !v6 )
      return L"Stop PostAssociate Security";
    v7 = v6 - 1;
    if ( !v7 )
      return L"Receive packet";
    v8 = v7 - 1;
    if ( !v8 )
      return L"OneX Callback";
    v9 = v8 - 1;
    if ( !v9 )
      return L"Security UI Response/Check pending";
    if ( v9 == 1 )
      return L"OneX UI Response/Check pending";
    return L"Invalid action";
  }
  v10 = a1 - 11;
  if ( !v10 )
    return L"Redo Security";
  v11 = v10 - 1;
  if ( !v11 )
    return L"Connection health check";
  v12 = v11 - 1;
  if ( !v12 )
    return L"Post connect key update";
  v13 = v12 - 1;
  if ( !v13 )
    return L"Set runtime state";
  v14 = v13 - 1;
  if ( !v14 )
    return L"Set WCN OneX enable";
  v15 = v14 - 1;
  if ( !v15 )
    return L"Set AP secondary key";
  v16 = v15 - 1;
  if ( v16 )
  {
    if ( v16 == 1 )
      return L"Get AP client key index";
    return L"Invalid action";
  }
  return L"Set AP peer key";
}

```

## disassembly

```asm
0x180016a08  cmp     ecx, 0Ah
0x180016a0b  jz      short loc_180016A30
0x180016a0d  jg      loc_180016A9A
0x180016a13  sub     ecx, 1
0x180016a16  jz      short loc_180016A91
0x180016a18  sub     ecx, 1
0x180016a1b  jz      short loc_180016A5A
0x180016a1d  sub     ecx, 1
0x180016a20  jz      short loc_180016A39
0x180016a22  sub     ecx, 1
0x180016a25  jnz     short loc_180016A42
0x180016a27  lea     rax, aPostassociateS; "PostAssociate Security"
0x180016a2e  retn
0x180016a30  lea     rax, aDeviceIndicati; "Device Indication"
0x180016a37  retn
0x180016a39  lea     rax, aStopSecurity; "Stop Security"
0x180016a40  retn
0x180016a42  sub     ecx, 1
0x180016a45  jz      short loc_180016A63
0x180016a47  sub     ecx, 1
0x180016a4a  jz      short loc_180016A88
0x180016a4c  sub     ecx, 1
0x180016a4f  jnz     short loc_180016A6C
0x180016a51  lea     rax, aOnexCallback; "OneX Callback"
0x180016a58  retn
0x180016a5a  lea     rax, aPreassociateCo; "PreAssociate Completion"
0x180016a61  retn
0x180016a63  lea     rax, aStopPostassoci; "Stop PostAssociate Security"
0x180016a6a  retn
0x180016a6c  sub     ecx, 1
0x180016a6f  jz      short loc_180016A7F
0x180016a71  cmp     ecx, 1
0x180016a74  jnz     short loc_180016ACB
0x180016a76  lea     rax, aOnexUiResponse; "OneX UI Response/Check pending"
0x180016a7d  retn
0x180016a7f  lea     rax, aSecurityUiResp; "Security UI Response/Check pending"
0x180016a86  retn
0x180016a88  lea     rax, aReceivePacket; "Receive packet"
0x180016a8f  retn
0x180016a91  lea     rax, aPreassociateSe; "PreAssociate Security"
0x180016a98  retn
0x180016a9a  sub     ecx, 0Bh
0x180016a9d  jz      short loc_180016B0A
0x180016a9f  sub     ecx, 1
0x180016aa2  jz      short loc_180016B01
0x180016aa4  sub     ecx, 1
0x180016aa7  jz      short loc_180016AF8
0x180016aa9  sub     ecx, 1
0x180016aac  jz      short loc_180016AEF
0x180016aae  sub     ecx, 1
0x180016ab1  jz      short loc_180016AE6
0x180016ab3  sub     ecx, 1
0x180016ab6  jz      short loc_180016ADD
0x180016ab8  sub     ecx, 1
0x180016abb  jz      short loc_180016AD4
0x180016abd  cmp     ecx, 1
0x180016ac0  jnz     short loc_180016ACB
0x180016ac2  lea     rax, aGetApClientKey; "Get AP client key index"
0x180016ac9  retn
0x180016acb  lea     rax, aInvalidAction; "Invalid action"
0x180016ad2  retn
0x180016ad4  lea     rax, aSetApPeerKey; "Set AP peer key"
0x180016adb  retn
0x180016add  lea     rax, aSetApSecondary; "Set AP secondary key"
0x180016ae4  retn
0x180016ae6  lea     rax, aSetWcnOnexEnab; "Set WCN OneX enable"
0x180016aed  retn
0x180016aef  lea     rax, aSetRuntimeStat; "Set runtime state"
0x180016af6  retn
0x180016af8  lea     rax, aPostConnectKey; "Post connect key update"
0x180016aff  retn
0x180016b01  lea     rax, aConnectionHeal; "Connection health check"
0x180016b08  retn
0x180016b0a  lea     rax, aRedoSecurity; "Redo Security"
0x180016b11  retn
```
