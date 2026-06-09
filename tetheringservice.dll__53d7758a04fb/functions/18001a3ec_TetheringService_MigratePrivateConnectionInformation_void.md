# TetheringService::MigratePrivateConnectionInformation(void)

- ea: `0x18001a3ec`
- end: `0x18001a70c`
- name: `?MigratePrivateConnectionInformation@TetheringService@@AEAAJXZ`
- size: `800`
- prototype: `__int64 __fastcall(TetheringService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001935c`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18001a3ec`
- `0x18002c034`
- `0x18002d66c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a55e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a5b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a55e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a5b0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001a658`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001a691`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001a658`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001a691`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a4c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a4c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TetheringService::MigratePrivateConnectionInformation(TetheringService *this)
{
  int v1; // eax
  unsigned int v2; // eax
  unsigned int v3; // ebx
  TetheringServiceTelemetry *v4; // rcx
  __int64 v5; // rdx
  int v6; // eax
  _BYTE v8[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[66]; // [rsp+44h] [rbp-BCh] BYREF
  BYTE v13[130]; // [rsp+86h] [rbp-7Ah] BYREF
  int v14; // [rsp+108h] [rbp+8h]
  int v15; // [rsp+10Ch] [rbp+Ch]

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 393, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  hKey = 0;
  cbData = 0;
  memset_0(Data, 0, 0xC4u);
  v11 = 1;
  v14 = 3;
  v15 = 1;
  v8[0] = 0;
  if ( (int)TetheringIsAuthSupportedInternal(2, v8) >= 0 )
  {
    v1 = v15;
    if ( v8[0] )
      v1 = 2;
    v15 = v1;
  }
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WcmSvc\\TetheringManager", 0, 0x2001Fu, &hKey);
  v3 = v2;
  if ( v2 == 2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 394, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
LABEL_26:
    v3 = (unsigned __int16)v3 | 0x80070000;
    goto LABEL_32;
  }
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 395;
LABEL_24:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v2);
      v4 = WPP_GLOBAL_Control;
      goto LABEL_25;
    }
    goto LABEL_25;
  }
  cbData = 66;
  v2 = RegQueryValueExW(hKey, L"SSID", 0, 0, Data, &cbData);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 396;
      goto LABEL_24;
    }
LABEL_25:
    if ( (int)v3 <= 0 )
      goto LABEL_32;
    goto LABEL_26;
  }
  cbData = 130;
  v2 = RegQueryValueExW(hKey, L"Passphrase", 0, 0, v13, &cbData);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 397;
      goto LABEL_24;
    }
    goto LABEL_25;
  }
  v6 = TetheringSettingsSaveSettingGlobalInternal(7, &v11, 208);
  v3 = v6;
  if ( v6 >= 0 )
    goto LABEL_31;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      398,
      &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (unsigned int)v6);
LABEL_31:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_32:
  if ( hKey )
  {
    if ( RegDeleteValueW(hKey, L"SSID")
      && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 399, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    }
    if ( RegDeleteValueW(hKey, L"Passphrase")
      && WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 400, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    }
    RegCloseKey(hKey);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v4 + 2), 401, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18001a3ec  push    rbp
0x18001a3ee  push    rbx
0x18001a3ef  push    rsi
0x18001a3f0  push    r12
0x18001a3f2  push    r14
0x18001a3f4  lea     rbp, [rsp-20h]
0x18001a3f9  sub     rsp, 120h
0x18001a400  mov     rax, cs:__security_cookie
0x18001a407  xor     rax, rsp
0x18001a40a  mov     [rbp+40h+var_30], rax
0x18001a40e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a415  lea     rsi, WPP_GLOBAL_Control
0x18001a41c  lea     r14, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001a423  cmp     rcx, rsi
0x18001a426  jz      short loc_18001A43F
0x18001a428  test    byte ptr [rcx+1Ch], 8
0x18001a42c  jz      short loc_18001A43F
0x18001a42e  mov     rcx, [rcx+10h]
0x18001a432  mov     edx, 189h
0x18001a437  mov     r8, r14
0x18001a43a  call    WPP_SF_
0x18001a43f  xor     edx, edx; Val
0x18001a441  mov     [rsp+140h+hKey], 0
0x18001a44a  mov     r8d, 0C4h; Size
0x18001a450  mov     [rsp+140h+cbData], 0
0x18001a458  lea     rcx, [rsp+140h+Data]; void *
0x18001a45d  call    memset_0
0x18001a462  mov     r12d, 2
0x18001a468  mov     [rsp+140h+var_100], 1
0x18001a470  mov     ecx, r12d
0x18001a473  mov     [rbp+40h+var_38], 3
0x18001a47a  lea     rdx, [rsp+140h+var_110]
0x18001a47f  mov     [rbp+40h+var_34], 1
0x18001a486  mov     [rsp+140h+var_110], 0
0x18001a48b  call    ?TetheringIsAuthSupportedInternal@@YAJW4_TETHERING_AUTH_TYPE@@PEA_N@Z; TetheringIsAuthSupportedInternal(_TETHERING_AUTH_TYPE,bool *)
0x18001a490  test    eax, eax
0x18001a492  js      short loc_18001A4A3
0x18001a494  mov     eax, [rbp+40h+var_34]
0x18001a497  cmp     [rsp+140h+var_110], 0
0x18001a49c  cmovnz  eax, r12d
0x18001a4a0  mov     [rbp+40h+var_34], eax
0x18001a4a3  lea     rax, [rsp+140h+hKey]
0x18001a4a8  mov     r9d, 2001Fh; samDesired
0x18001a4ae  xor     r8d, r8d; ulOptions
0x18001a4b1  mov     [rsp+140h+phkResult], rax; phkResult
0x18001a4b6  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\WcmSvc\\TetheringM"...
0x18001a4bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a4c4  call    cs:__imp_RegOpenKeyExW
0x18001a4ca  mov     ebx, eax
0x18001a4cc  cmp     eax, r12d
0x18001a4cf  jnz     short loc_18001A508
0x18001a4d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4d8  cmp     rcx, rsi
0x18001a4db  jz      loc_18001A5ED
0x18001a4e1  test    byte ptr [rcx+1Ch], 4
0x18001a4e5  jz      loc_18001A5ED
0x18001a4eb  mov     rcx, [rcx+10h]
0x18001a4ef  mov     edx, 18Ah
0x18001a4f4  mov     r8, r14
0x18001a4f7  call    WPP_SF_
0x18001a4fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a503  jmp     loc_18001A5ED
0x18001a508  test    eax, eax
0x18001a50a  jz      short loc_18001A530
0x18001a50c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a513  cmp     rcx, rsi
0x18001a516  jz      loc_18001A5E9
0x18001a51c  test    byte ptr [rcx+1Ch], 1
0x18001a520  jz      loc_18001A5E9
0x18001a526  mov     edx, 18Bh
0x18001a52b  jmp     loc_18001A5D3
0x18001a530  mov     rcx, [rsp+140h+hKey]; hKey
0x18001a535  lea     rax, [rsp+140h+cbData]
0x18001a53a  mov     [rsp+140h+lpcbData], rax; lpcbData
0x18001a53f  lea     rdx, ValueName; "SSID"
0x18001a546  lea     rax, [rsp+140h+Data]
0x18001a54b  mov     [rsp+140h+cbData], 42h ; 'B'
0x18001a553  xor     r9d, r9d; lpType
0x18001a556  mov     [rsp+140h+phkResult], rax; lpData
0x18001a55b  xor     r8d, r8d; lpReserved
0x18001a55e  call    cs:__imp_RegQueryValueExW
0x18001a564  mov     ebx, eax
0x18001a566  test    eax, eax
0x18001a568  jz      short loc_18001A583
0x18001a56a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a571  cmp     rcx, rsi
0x18001a574  jz      short loc_18001A5E9
0x18001a576  test    byte ptr [rcx+1Ch], 1
0x18001a57a  jz      short loc_18001A5E9
0x18001a57c  mov     edx, 18Ch
0x18001a581  jmp     short loc_18001A5D3
0x18001a583  mov     rcx, [rsp+140h+hKey]; hKey
0x18001a588  lea     rax, [rsp+140h+cbData]
0x18001a58d  mov     [rsp+140h+lpcbData], rax; lpcbData
0x18001a592  lea     rdx, aPassphrase; "Passphrase"
0x18001a599  lea     rax, [rbp+40h+var_BA]
0x18001a59d  mov     [rsp+140h+cbData], 82h
0x18001a5a5  xor     r9d, r9d; lpType
0x18001a5a8  mov     [rsp+140h+phkResult], rax; lpData
0x18001a5ad  xor     r8d, r8d; lpReserved
0x18001a5b0  call    cs:__imp_RegQueryValueExW
0x18001a5b6  mov     ebx, eax
0x18001a5b8  test    eax, eax
0x18001a5ba  jz      short loc_18001A5F8
0x18001a5bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5c3  cmp     rcx, rsi
0x18001a5c6  jz      short loc_18001A5E9
0x18001a5c8  test    byte ptr [rcx+1Ch], 1
0x18001a5cc  jz      short loc_18001A5E9
0x18001a5ce  mov     edx, 18Dh
0x18001a5d3  mov     rcx, [rcx+10h]
0x18001a5d7  mov     r9d, eax
0x18001a5da  mov     r8, r14
0x18001a5dd  call    WPP_SF_d
0x18001a5e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5e9  test    ebx, ebx
0x18001a5eb  jle     short loc_18001A640
0x18001a5ed  movzx   ebx, bx
0x18001a5f0  or      ebx, 80070000h
0x18001a5f6  jmp     short loc_18001A640
0x18001a5f8  mov     r8d, 0D0h
0x18001a5fe  lea     rdx, [rsp+140h+var_100]
0x18001a603  mov     ecx, 7
0x18001a608  call    ?TetheringSettingsSaveSettingGlobalInternal@@YAJW4TetheringSettingGlobal@@PEAXK@Z; TetheringSettingsSaveSettingGlobalInternal(TetheringSettingGlobal,void *,ulong)
0x18001a60d  mov     ebx, eax
0x18001a60f  test    eax, eax
0x18001a611  jns     short loc_18001A639
0x18001a613  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a61a  cmp     rcx, rsi
0x18001a61d  jz      short loc_18001A640
0x18001a61f  test    byte ptr [rcx+1Ch], 1
0x18001a623  jz      short loc_18001A640
0x18001a625  mov     rcx, [rcx+10h]
0x18001a629  mov     edx, 18Eh
0x18001a62e  mov     r9d, eax
0x18001a631  mov     r8, r14
0x18001a634  call    WPP_SF_d
0x18001a639  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a640  mov     rax, [rsp+140h+hKey]
0x18001a645  test    rax, rax
0x18001a648  jz      loc_18001A6D0
0x18001a64e  lea     rdx, ValueName; "SSID"
0x18001a655  mov     rcx, rax; hKey
0x18001a658  call    cs:__imp_RegDeleteValueW
0x18001a65e  test    eax, eax
0x18001a660  jz      short loc_18001A685
0x18001a662  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a669  cmp     rcx, rsi
0x18001a66c  jz      short loc_18001A685
0x18001a66e  test    [rcx+1Ch], r12b
0x18001a672  jz      short loc_18001A685
0x18001a674  mov     rcx, [rcx+10h]
0x18001a678  mov     edx, 18Fh
0x18001a67d  mov     r8, r14
0x18001a680  call    WPP_SF_
0x18001a685  mov     rcx, [rsp+140h+hKey]; hKey
0x18001a68a  lea     rdx, aPassphrase; "Passphrase"
0x18001a691  call    cs:__imp_RegDeleteValueW
0x18001a697  test    eax, eax
0x18001a699  jz      short loc_18001A6BE
0x18001a69b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6a2  cmp     rcx, rsi
0x18001a6a5  jz      short loc_18001A6BE
0x18001a6a7  test    [rcx+1Ch], r12b
0x18001a6ab  jz      short loc_18001A6BE
0x18001a6ad  mov     rcx, [rcx+10h]
0x18001a6b1  mov     edx, 190h
0x18001a6b6  mov     r8, r14
0x18001a6b9  call    WPP_SF_
0x18001a6be  mov     rcx, [rsp+140h+hKey]; hKey
0x18001a6c3  call    cs:__imp_RegCloseKey
0x18001a6c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6d0  cmp     rcx, rsi
0x18001a6d3  jz      short loc_18001A6EF
0x18001a6d5  test    byte ptr [rcx+1Ch], 8
0x18001a6d9  jz      short loc_18001A6EF
0x18001a6db  mov     rcx, [rcx+10h]
0x18001a6df  mov     edx, 191h
0x18001a6e4  mov     r9d, ebx
0x18001a6e7  mov     r8, r14
0x18001a6ea  call    WPP_SF_d
0x18001a6ef  mov     eax, ebx
0x18001a6f1  mov     rcx, [rbp+40h+var_30]
0x18001a6f5  xor     rcx, rsp; StackCookie
0x18001a6f8  call    __security_check_cookie
0x18001a6fd  add     rsp, 120h
0x18001a704  pop     r14
0x18001a706  pop     r12
0x18001a708  pop     rsi
0x18001a709  pop     rbx
0x18001a70a  pop     rbp
0x18001a70b  retn
```
