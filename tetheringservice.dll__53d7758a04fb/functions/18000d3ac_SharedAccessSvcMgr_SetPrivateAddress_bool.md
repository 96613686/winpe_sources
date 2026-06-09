# SharedAccessSvcMgr::SetPrivateAddress(bool)

- ea: `0x18000d3ac`
- end: `0x18000d57c`
- name: `?SetPrivateAddress@SharedAccessSvcMgr@@AEAAJ_N@Z`
- size: `464`
- prototype: `__int64 __fastcall(const WCHAR *this, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000d584`

## callees

- `0x18000304c`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000d3ac`
- `0x18000d868`
- `0x18002b1f0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000d4d7`
- `ntdll!RtlNtStatusToDosError` at `0x18000d4d7`
- `ntdll!RtlIpv4StringToAddressW` at `0x18000d452`
- `ntdll!RtlIpv4StringToAddressW` at `0x18000d452`
- `HNetCfgClient!HNetCfgSetDhcpScopeAddress` at `0x18000d4ad`
- `HNetCfgClient!HNetCfgSetDhcpScopeAddress` at `0x18000d4ad`

## pseudocode

```c
__int64 __fastcall SharedAccessSvcMgr::SetPrivateAddress(const WCHAR *this, char a2)
{
  TetheringServiceTelemetry *v3; // rcx
  unsigned int v4; // eax
  const WCHAR *SettingValueGlobalInternal; // rax
  WCHAR *v6; // rdi
  NTSTATUS v7; // eax
  ULONG S_addr; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  TetheringServiceTelemetry *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  signed int v14; // eax
  TetheringServiceTelemetry *v15; // rcx
  LPCWSTR Terminator; // [rsp+60h] [rbp+8h] BYREF
  in_addr Addr; // [rsp+68h] [rbp+10h] BYREF

  Terminator = this;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  v4 = 5;
  if ( a2 )
  {
    if ( v3 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)v3 + 2), 39, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids);
    v4 = 9;
  }
  SettingValueGlobalInternal = (const WCHAR *)TetheringSettingsGetSettingValueGlobalInternal(v4);
  v6 = (WCHAR *)SettingValueGlobalInternal;
  if ( SettingValueGlobalInternal )
  {
    Terminator = 0;
    Addr = 0;
    v7 = RtlIpv4StringToAddressW(SettingValueGlobalInternal, 1u, &Terminator, &Addr);
    if ( v7 < 0 )
    {
      v14 = RtlNtStatusToDosError(v7);
      v10 = v14;
      if ( v14 > 0 )
        v10 = (unsigned __int16)v14 | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_24;
      }
      v12 = 42;
      v13 = v10;
    }
    else
    {
      S_addr = Addr.S_un.S_addr;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_DDDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          Addr.S_un.S_un_b.s_b2,
          Addr.S_un.S_un_b.s_b3,
          Addr.S_un.S_addr,
          Addr.S_un.S_un_b.s_b1,
          Addr.S_un.S_un_b.s_b2,
          Addr.S_un.S_un_b.s_b3,
          Addr.S_un.S_un_b.s_b4);
      }
      v9 = HNetCfgSetDhcpScopeAddress(S_addr);
      v10 = v9;
      if ( v9 >= 0 )
        goto LABEL_24;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_24;
      }
      v12 = 41;
      v13 = (unsigned int)v9;
    }
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids, v13);
LABEL_24:
    free(v6);
LABEL_28:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  v10 = -2147467259;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    return v10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids, 2147500037LL);
    goto LABEL_28;
  }
LABEL_29:
  if ( v15 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v15 + 2), 44, &WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18000d3ac  mov     [rsp+arg_10], rbx
0x18000d3b1  mov     [rsp+Terminator], rcx
0x18000d3b6  push    rbp
0x18000d3b7  push    rsi
0x18000d3b8  push    rdi
0x18000d3b9  sub     rsp, 40h
0x18000d3bd  mov     bl, dl
0x18000d3bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3c6  lea     rsi, WPP_GLOBAL_Control
0x18000d3cd  lea     rbp, WPP_61b13f64d1073f22fbe44920aae21d64_Traceguids
0x18000d3d4  cmp     rcx, rsi
0x18000d3d7  jz      short loc_18000D3F7
0x18000d3d9  test    byte ptr [rcx+1Ch], 8
0x18000d3dd  jz      short loc_18000D3F7
0x18000d3df  mov     rcx, [rcx+10h]
0x18000d3e3  mov     edx, 26h ; '&'
0x18000d3e8  mov     r8, rbp
0x18000d3eb  call    WPP_SF_
0x18000d3f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3f7  mov     eax, 5
0x18000d3fc  test    bl, bl
0x18000d3fe  jz      short loc_18000D41F
0x18000d400  cmp     rcx, rsi
0x18000d403  jz      short loc_18000D41A
0x18000d405  test    byte ptr [rcx+1Ch], 8
0x18000d409  jz      short loc_18000D41A
0x18000d40b  mov     rcx, [rcx+10h]
0x18000d40f  lea     edx, [rax+22h]
0x18000d412  mov     r8, rbp
0x18000d415  call    WPP_SF_
0x18000d41a  mov     eax, 9
0x18000d41f  mov     ecx, eax
0x18000d421  call    ?TetheringSettingsGetSettingValueGlobalInternal@@YAPEAXW4TetheringSettingGlobal@@@Z; TetheringSettingsGetSettingValueGlobalInternal(TetheringSettingGlobal)
0x18000d426  mov     rdi, rax
0x18000d429  test    rax, rax
0x18000d42c  jz      loc_18000D51C
0x18000d432  lea     r9, [rsp+58h+Addr]; Addr
0x18000d437  mov     [rsp+58h+Terminator], 0
0x18000d440  lea     r8, [rsp+58h+Terminator]; Terminator
0x18000d445  mov     dword ptr [rsp+58h+Addr.S_un], 0
0x18000d44d  mov     dl, 1; Strict
0x18000d44f  mov     rcx, rax; S
0x18000d452  call    cs:__imp_RtlIpv4StringToAddressW
0x18000d458  test    eax, eax
0x18000d45a  js      short loc_18000D4D5
0x18000d45c  mov     ebx, dword ptr [rsp+58h+Addr.S_un]
0x18000d460  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d467  cmp     rcx, rsi
0x18000d46a  jz      short loc_18000D4AB
0x18000d46c  test    byte ptr [rcx+1Ch], 8
0x18000d470  jz      short loc_18000D4AB
0x18000d472  mov     rcx, [rcx+10h]
0x18000d476  mov     eax, ebx
0x18000d478  shr     eax, 10h
0x18000d47b  mov     r9d, ebx
0x18000d47e  movzx   r8d, al
0x18000d482  mov     eax, ebx
0x18000d484  shr     eax, 8
0x18000d487  shr     r9d, 18h
0x18000d48b  mov     [rsp+58h+var_20], r9d
0x18000d490  mov     r9d, ebx
0x18000d493  movzx   edx, al
0x18000d496  mov     [rsp+58h+var_28], r8d
0x18000d49b  movzx   eax, bl
0x18000d49e  mov     [rsp+58h+var_30], edx
0x18000d4a2  mov     [rsp+58h+var_38], eax
0x18000d4a6  call    WPP_SF_DDDDD
0x18000d4ab  mov     ecx, ebx
0x18000d4ad  call    cs:__imp_HNetCfgSetDhcpScopeAddress
0x18000d4b3  mov     ebx, eax
0x18000d4b5  test    eax, eax
0x18000d4b7  jns     short loc_18000D512
0x18000d4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4c0  cmp     rcx, rsi
0x18000d4c3  jz      short loc_18000D512
0x18000d4c5  test    byte ptr [rcx+1Ch], 1
0x18000d4c9  jz      short loc_18000D512
0x18000d4cb  mov     edx, 29h ; ')'
0x18000d4d0  mov     r9d, eax
0x18000d4d3  jmp     short loc_18000D506
0x18000d4d5  mov     ecx, eax; Status
0x18000d4d7  call    cs:__imp_RtlNtStatusToDosError
0x18000d4dd  mov     ebx, eax
0x18000d4df  test    eax, eax
0x18000d4e1  jle     short loc_18000D4EC
0x18000d4e3  movzx   ebx, ax
0x18000d4e6  or      ebx, 80070000h
0x18000d4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4f3  cmp     rcx, rsi
0x18000d4f6  jz      short loc_18000D512
0x18000d4f8  test    byte ptr [rcx+1Ch], 1
0x18000d4fc  jz      short loc_18000D512
0x18000d4fe  mov     edx, 2Ah ; '*'
0x18000d503  mov     r9d, ebx
0x18000d506  mov     rcx, [rcx+10h]
0x18000d50a  mov     r8, rbp
0x18000d50d  call    WPP_SF_d
0x18000d512  mov     rcx, rdi; Block
0x18000d515  call    free
0x18000d51a  jmp     short loc_18000D547
0x18000d51c  mov     ebx, 80004005h
0x18000d521  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d528  cmp     rcx, rsi
0x18000d52b  jz      short loc_18000D56D
0x18000d52d  test    byte ptr [rcx+1Ch], 1
0x18000d531  jz      short loc_18000D54E
0x18000d533  mov     rcx, [rcx+10h]
0x18000d537  mov     edx, 2Bh ; '+'
0x18000d53c  mov     r9d, ebx
0x18000d53f  mov     r8, rbp
0x18000d542  call    WPP_SF_d
0x18000d547  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d54e  cmp     rcx, rsi
0x18000d551  jz      short loc_18000D56D
0x18000d553  test    byte ptr [rcx+1Ch], 8
0x18000d557  jz      short loc_18000D56D
0x18000d559  mov     rcx, [rcx+10h]
0x18000d55d  mov     edx, 2Ch ; ','
0x18000d562  mov     r9d, ebx
0x18000d565  mov     r8, rbp
0x18000d568  call    WPP_SF_d
0x18000d56d  mov     eax, ebx
0x18000d56f  mov     rbx, [rsp+58h+arg_10]
0x18000d574  add     rsp, 40h
0x18000d578  pop     rdi
0x18000d579  pop     rsi
0x18000d57a  pop     rbp
0x18000d57b  retn
```
