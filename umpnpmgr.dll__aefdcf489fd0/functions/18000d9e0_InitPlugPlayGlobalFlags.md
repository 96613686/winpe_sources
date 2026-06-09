# InitPlugPlayGlobalFlags

- ea: `0x18000d9e0`
- end: `0x18000de5e`
- name: `InitPlugPlayGlobalFlags`
- size: `1150`
- prototype: `LSTATUS()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000cf30`

## callees

- `0x18000d9e0`
- `0x1800117d4`
- `0x180011964`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000ddfc`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000ddfc`
- `ntdll!RtlQueryWnfStateData` at `0x18000ddba`
- `ntdll!RtlQueryWnfStateData` at `0x18000ddba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd8a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000da5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dba9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dc2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dca8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dd3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000da5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000db17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dba9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dc2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dca8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dd3a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000da23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000da23`

## string_xrefs

- `0x18000da51`: `FactoryPreInstallInProgress`

## pseudocode

```c
LSTATUS InitPlugPlayGlobalFlags()
{
  LSTATUS result; // eax
  _QWORD *v1; // rcx
  char v2; // al
  char v3; // al
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF
  int Data; // [rsp+78h] [rbp+28h] BYREF
  DWORD Type; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v10; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 0;
  Type = 0;
  v10 = 0;
  PnpGlobalFlags = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 1u, &hKey);
  if ( result )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    {
      v5 = 19;
      return WPP_SF_d(v4[2], v5, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids, (unsigned int)result);
    }
  }
  else
  {
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"FactoryPreInstallInProgress", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && cbData == 4
      && Data )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids);
        v1 = WPP_GLOBAL_Control;
      }
      PnpGlobalFlags |= 2u;
      if ( v1 != &WPP_GLOBAL_Control && (*((_DWORD *)v1 + 7) & 0x40000) != 0 )
        WPP_SF_(v1[2], 12, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids);
    }
    if ( (PnpGlobalFlags & 2) == 0 )
    {
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"SystemSetupInProgress", 0, &Type, (LPBYTE)&Data, &cbData)
        && Data
        && Type == 4
        && cbData == 4 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids);
        }
        v2 = PnpGlobalFlags | 1;
        PnpGlobalFlags |= 1u;
      }
      else
      {
        v2 = PnpGlobalFlags;
      }
      if ( (v2 & 1) != 0 )
      {
        Data = 0;
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"MiniSetupInProgress", 0, &Type, (LPBYTE)&Data, &cbData)
          && Type == 4
          && cbData == 4
          && Data )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids);
          }
          Data = 0;
          cbData = 4;
          if ( !RegQueryValueExW(hKey, L"MiniSetupDoPnP", 0, &Type, (LPBYTE)&Data, &cbData)
            && Type == 4
            && cbData == 4
            && Data )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids);
            }
          }
          else
          {
            PnpGlobalFlags &= ~1u;
          }
        }
      }
    }
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"OobeInProgress", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && cbData == 4
      && Data )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids);
      v3 = PnpGlobalFlags | 4;
      PnpGlobalFlags |= 4u;
    }
    else
    {
      v3 = PnpGlobalFlags;
    }
    if ( (v3 & 1) == 0 && (v3 & 4) != 0 )
    {
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"PnpSetupInProgress", 0, &Type, (LPBYTE)&Data, &cbData)
        && Type == 4
        && cbData == 4
        && Data )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids);
        }
        PnpGlobalFlags |= 8u;
      }
    }
    result = RegCloseKey(hKey);
    if ( (PnpGlobalFlags & 4) != 0 )
    {
      v10 = 0;
      result = RtlQueryWnfStateData(&v10, WNF_DEP_OOBE_COMPLETE, PnpOobeCompleteStateChangeCallback, 0, 0);
      if ( result < 0
        || (PnpGlobalFlags & 4) != 0
        && (result = RtlSubscribeWnfStateChangeNotification(
                       &PnpOobeCompleteSubscription,
                       WNF_DEP_OOBE_COMPLETE,
                       v10,
                       PnpOobeCompleteStateChangeCallback,
                       0,
                       0,
                       0,
                       0),
            result < 0) )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
        {
          v5 = 18;
          return WPP_SF_d(v4[2], v5, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids, (unsigned int)result);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d9e0  push    rbp
0x18000d9e2  push    rbx
0x18000d9e3  push    rdi
0x18000d9e4  mov     rbp, rsp
0x18000d9e7  sub     rsp, 50h
0x18000d9eb  xor     edi, edi
0x18000d9ed  lea     rax, [rbp+hKey]
0x18000d9f1  mov     r9d, 1; samDesired
0x18000d9f7  mov     [rbp+hKey], rdi
0x18000d9fb  xor     r8d, r8d; ulOptions
0x18000d9fe  mov     [rbp+Data], edi
0x18000da01  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x18000da08  mov     [rbp+cbData], edi
0x18000da0b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000da12  mov     [rbp+Type], edi
0x18000da15  mov     [rbp+arg_18], edi
0x18000da18  mov     cs:PnpGlobalFlags, edi
0x18000da1e  mov     [rsp+50h+phkResult], rax; phkResult
0x18000da23  call    cs:__imp_RegOpenKeyExW
0x18000da29  test    eax, eax
0x18000da2b  jnz     loc_18000DE22
0x18000da31  mov     rcx, [rbp+hKey]; hKey
0x18000da35  lea     rax, [rbp+cbData]
0x18000da39  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000da3e  lea     r9, [rbp+Type]; lpType
0x18000da42  lea     rax, [rbp+Data]
0x18000da46  mov     [rbp+Data], edi
0x18000da49  xor     r8d, r8d; lpReserved
0x18000da4c  mov     [rsp+50h+phkResult], rax; lpData
0x18000da51  lea     rdx, aFactorypreinst; "FactoryPreInstallInProgress"
0x18000da58  mov     [rbp+cbData], 4
0x18000da5f  call    cs:__imp_RegQueryValueExW
0x18000da65  lea     rbx, WPP_GLOBAL_Control
0x18000da6c  test    eax, eax
0x18000da6e  jnz     short loc_18000DADC
0x18000da70  cmp     [rbp+Type], 4
0x18000da74  jnz     short loc_18000DADC
0x18000da76  cmp     [rbp+cbData], 4
0x18000da7a  jnz     short loc_18000DADC
0x18000da7c  cmp     [rbp+Data], edi
0x18000da7f  jz      short loc_18000DADC
0x18000da81  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da88  cmp     rcx, rbx
0x18000da8b  jz      short loc_18000DAB2
0x18000da8d  test    dword ptr [rcx+1Ch], 40000h
0x18000da94  jz      short loc_18000DAB2
0x18000da96  mov     rcx, [rcx+10h]
0x18000da9a  lea     r8, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids
0x18000daa1  mov     edx, 0Bh
0x18000daa6  call    WPP_SF_
0x18000daab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dab2  or      cs:PnpGlobalFlags, 2
0x18000dab9  cmp     rcx, rbx
0x18000dabc  jz      short loc_18000DADC
0x18000dabe  test    dword ptr [rcx+1Ch], 40000h
0x18000dac5  jz      short loc_18000DADC
0x18000dac7  mov     rcx, [rcx+10h]
0x18000dacb  lea     r8, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids
0x18000dad2  mov     edx, 0Ch
0x18000dad7  call    WPP_SF_
0x18000dadc  test    byte ptr cs:PnpGlobalFlags, 2
0x18000dae3  jnz     loc_18000DC7A
0x18000dae9  mov     rcx, [rbp+hKey]; hKey
0x18000daed  lea     rax, [rbp+cbData]
0x18000daf1  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000daf6  lea     r9, [rbp+Type]; lpType
0x18000dafa  lea     rax, [rbp+Data]
0x18000dafe  mov     [rbp+Data], edi
0x18000db01  xor     r8d, r8d; lpReserved
0x18000db04  mov     [rsp+50h+phkResult], rax; lpData
0x18000db09  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x18000db10  mov     [rbp+cbData], 4
0x18000db17  call    cs:__imp_RegQueryValueExW
0x18000db1d  test    eax, eax
0x18000db1f  jnz     short loc_18000DB6D
0x18000db21  cmp     [rbp+Data], edi
0x18000db24  jz      short loc_18000DB6D
0x18000db26  cmp     [rbp+Type], 4
0x18000db2a  jnz     short loc_18000DB6D
0x18000db2c  cmp     [rbp+cbData], 4
0x18000db30  jnz     short loc_18000DB6D
0x18000db32  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db39  cmp     rcx, rbx
0x18000db3c  jz      short loc_18000DB5C
0x18000db3e  test    dword ptr [rcx+1Ch], 40000h
0x18000db45  jz      short loc_18000DB5C
0x18000db47  mov     rcx, [rcx+10h]
0x18000db4b  lea     r8, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids
0x18000db52  mov     edx, 0Dh
0x18000db57  call    WPP_SF_
0x18000db5c  mov     eax, cs:PnpGlobalFlags
0x18000db62  or      eax, 1
0x18000db65  mov     cs:PnpGlobalFlags, eax
0x18000db6b  jmp     short loc_18000DB73
0x18000db6d  mov     eax, cs:PnpGlobalFlags
0x18000db73  test    al, 1
0x18000db75  jz      loc_18000DC7A
0x18000db7b  mov     rcx, [rbp+hKey]; hKey
0x18000db7f  lea     rax, [rbp+cbData]
0x18000db83  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000db88  lea     r9, [rbp+Type]; lpType
0x18000db8c  lea     rax, [rbp+Data]
0x18000db90  mov     [rbp+Data], edi
0x18000db93  xor     r8d, r8d; lpReserved
0x18000db96  mov     [rsp+50h+phkResult], rax; lpData
0x18000db9b  lea     rdx, aMinisetupinpro; "MiniSetupInProgress"
0x18000dba2  mov     [rbp+cbData], 4
0x18000dba9  call    cs:__imp_RegQueryValueExW
0x18000dbaf  test    eax, eax
0x18000dbb1  jnz     loc_18000DC7A
0x18000dbb7  cmp     [rbp+Type], 4
0x18000dbbb  jnz     loc_18000DC7A
0x18000dbc1  cmp     [rbp+cbData], 4
0x18000dbc5  jnz     loc_18000DC7A
0x18000dbcb  cmp     [rbp+Data], edi
0x18000dbce  jz      loc_18000DC7A
0x18000dbd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbdb  cmp     rcx, rbx
0x18000dbde  jz      short loc_18000DBFE
0x18000dbe0  test    dword ptr [rcx+1Ch], 40000h
0x18000dbe7  jz      short loc_18000DBFE
0x18000dbe9  mov     rcx, [rcx+10h]
0x18000dbed  lea     r8, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids
0x18000dbf4  mov     edx, 0Eh
0x18000dbf9  call    WPP_SF_
0x18000dbfe  mov     rcx, [rbp+hKey]; hKey
0x18000dc02  lea     rax, [rbp+cbData]
0x18000dc06  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000dc0b  lea     r9, [rbp+Type]; lpType
0x18000dc0f  lea     rax, [rbp+Data]
0x18000dc13  mov     [rbp+Data], edi
0x18000dc16  xor     r8d, r8d; lpReserved
0x18000dc19  mov     [rsp+50h+phkResult], rax; lpData
0x18000dc1e  lea     rdx, aMinisetupdopnp; "MiniSetupDoPnP"
0x18000dc25  mov     [rbp+cbData], 4
0x18000dc2c  call    cs:__imp_RegQueryValueExW
0x18000dc32  test    eax, eax
0x18000dc34  jnz     short loc_18000DC73
0x18000dc36  cmp     [rbp+Type], 4
0x18000dc3a  jnz     short loc_18000DC73
0x18000dc3c  cmp     [rbp+cbData], 4
0x18000dc40  jnz     short loc_18000DC73
0x18000dc42  cmp     [rbp+Data], edi
0x18000dc45  jz      short loc_18000DC73
0x18000dc47  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc4e  cmp     rcx, rbx
0x18000dc51  jz      short loc_18000DC7A
0x18000dc53  test    dword ptr [rcx+1Ch], 40000h
0x18000dc5a  jz      short loc_18000DC7A
0x18000dc5c  mov     rcx, [rcx+10h]
0x18000dc60  lea     r8, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids
0x18000dc67  mov     edx, 0Fh
0x18000dc6c  call    WPP_SF_
0x18000dc71  jmp     short loc_18000DC7A
0x18000dc73  and     cs:PnpGlobalFlags, 0FFFFFFFEh
0x18000dc7a  mov     rcx, [rbp+hKey]; hKey
0x18000dc7e  lea     rax, [rbp+cbData]
0x18000dc82  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000dc87  lea     r9, [rbp+Type]; lpType
0x18000dc8b  lea     rax, [rbp+Data]
0x18000dc8f  mov     [rbp+Data], edi
0x18000dc92  xor     r8d, r8d; lpReserved
0x18000dc95  mov     [rsp+50h+phkResult], rax; lpData
0x18000dc9a  lea     rdx, aOobeinprogress; "OobeInProgress"
0x18000dca1  mov     [rbp+cbData], 4
0x18000dca8  call    cs:__imp_RegQueryValueExW
0x18000dcae  test    eax, eax
0x18000dcb0  jnz     short loc_18000DCFE
0x18000dcb2  cmp     [rbp+Type], 4
0x18000dcb6  jnz     short loc_18000DCFE
0x18000dcb8  cmp     [rbp+cbData], 4
0x18000dcbc  jnz     short loc_18000DCFE
0x18000dcbe  cmp     [rbp+Data], edi
0x18000dcc1  jz      short loc_18000DCFE
0x18000dcc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcca  cmp     rcx, rbx
0x18000dccd  jz      short loc_18000DCED
0x18000dccf  test    dword ptr [rcx+1Ch], 40000h
0x18000dcd6  jz      short loc_18000DCED
0x18000dcd8  mov     rcx, [rcx+10h]
0x18000dcdc  lea     r8, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids
0x18000dce3  mov     edx, 10h
0x18000dce8  call    WPP_SF_
0x18000dced  mov     eax, cs:PnpGlobalFlags
0x18000dcf3  or      eax, 4
0x18000dcf6  mov     cs:PnpGlobalFlags, eax
0x18000dcfc  jmp     short loc_18000DD04
0x18000dcfe  mov     eax, cs:PnpGlobalFlags
0x18000dd04  test    al, 1
0x18000dd06  jnz     short loc_18000DD86
0x18000dd08  test    al, 4
0x18000dd0a  jz      short loc_18000DD86
0x18000dd0c  mov     rcx, [rbp+hKey]; hKey
0x18000dd10  lea     rax, [rbp+cbData]
0x18000dd14  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000dd19  lea     r9, [rbp+Type]; lpType
0x18000dd1d  lea     rax, [rbp+Data]
0x18000dd21  mov     [rbp+Data], edi
0x18000dd24  xor     r8d, r8d; lpReserved
0x18000dd27  mov     [rsp+50h+phkResult], rax; lpData
0x18000dd2c  lea     rdx, aPnpsetupinprog; "PnpSetupInProgress"
0x18000dd33  mov     [rbp+cbData], 4
0x18000dd3a  call    cs:__imp_RegQueryValueExW
0x18000dd40  test    eax, eax
0x18000dd42  jnz     short loc_18000DD86
0x18000dd44  cmp     [rbp+Type], 4
0x18000dd48  jnz     short loc_18000DD86
0x18000dd4a  cmp     [rbp+cbData], 4
0x18000dd4e  jnz     short loc_18000DD86
0x18000dd50  cmp     [rbp+Data], edi
0x18000dd53  jz      short loc_18000DD86
0x18000dd55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd5c  cmp     rcx, rbx
0x18000dd5f  jz      short loc_18000DD7F
0x18000dd61  test    dword ptr [rcx+1Ch], 40000h
0x18000dd68  jz      short loc_18000DD7F
0x18000dd6a  mov     rcx, [rcx+10h]
0x18000dd6e  lea     r8, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids
0x18000dd75  mov     edx, 11h
0x18000dd7a  call    WPP_SF_
0x18000dd7f  or      cs:PnpGlobalFlags, 8
0x18000dd86  mov     rcx, [rbp+hKey]; hKey
0x18000dd8a  call    cs:__imp_RegCloseKey
0x18000dd90  test    byte ptr cs:PnpGlobalFlags, 4
0x18000dd97  jz      loc_18000DE56
0x18000dd9d  mov     rdx, cs:WNF_DEP_OOBE_COMPLETE
0x18000dda4  lea     r8, PnpOobeCompleteStateChangeCallback
0x18000ddab  xor     r9d, r9d
0x18000ddae  mov     [rbp+arg_18], edi
0x18000ddb1  lea     rcx, [rbp+arg_18]
0x18000ddb5  mov     [rsp+50h+phkResult], rdi
0x18000ddba  call    cs:__imp_RtlQueryWnfStateData
0x18000ddc0  test    eax, eax
0x18000ddc2  js      short loc_18000DE06
0x18000ddc4  test    byte ptr cs:PnpGlobalFlags, 4
0x18000ddcb  jz      loc_18000DE56
0x18000ddd1  mov     r8d, [rbp+arg_18]
0x18000ddd5  lea     r9, PnpOobeCompleteStateChangeCallback
0x18000dddc  mov     rdx, cs:WNF_DEP_OOBE_COMPLETE
0x18000dde3  lea     rcx, PnpOobeCompleteSubscription
0x18000ddea  mov     [rsp+50h+var_18], edi
0x18000ddee  mov     [rsp+50h+var_20], edi
0x18000ddf2  mov     [rsp+50h+lpcbData], rdi
0x18000ddf7  mov     [rsp+50h+phkResult], rdi
0x18000ddfc  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18000de02  test    eax, eax
0x18000de04  jns     short loc_18000DE56
0x18000de06  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de0d  cmp     rcx, rbx
0x18000de10  jz      short loc_18000DE56
0x18000de12  test    dword ptr [rcx+1Ch], 10000h
0x18000de19  jz      short loc_18000DE56
0x18000de1b  mov     edx, 12h
0x18000de20  jmp     short loc_18000DE43
0x18000de22  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de29  lea     rbx, WPP_GLOBAL_Control
0x18000de30  cmp     rcx, rbx
0x18000de33  jz      short loc_18000DE56
0x18000de35  test    dword ptr [rcx+1Ch], 10000h
0x18000de3c  jz      short loc_18000DE56
0x18000de3e  mov     edx, 13h
0x18000de43  mov     rcx, [rcx+10h]
0x18000de47  lea     r8, WPP_0633fa21021a33e0f34dc584e27475f5_Traceguids
0x18000de4e  mov     r9d, eax
0x18000de51  call    WPP_SF_d
0x18000de56  add     rsp, 50h
0x18000de5a  pop     rdi
0x18000de5b  pop     rbx
0x18000de5c  pop     rbp
0x18000de5d  retn
```
