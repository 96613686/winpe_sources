# CLuaSettingsChecktoid::OnFix(void)

- ea: `0x180034b30`
- end: `0x180034e0c`
- name: `?OnFix@CLuaSettingsChecktoid@@MEAAJXZ`
- size: `732`
- prototype: `__int64 __fastcall(LPCWSTR *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003e40`
- `0x180028320`
- `0x180034b30`
- `0x18003e358`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180034c1c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180034c1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034d9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034dae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034d9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034dae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034c83`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034d02`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034c83`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034d02`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180034b71`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180034b71`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034ba1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034ba1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180034dd1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180034dd1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLuaSettingsChecktoid::OnFix(LPCWSTR *this)
{
  int RegistryDwordValue; // ebx
  LSTATUS v3; // eax
  HKEY v4; // rcx
  HKEY v5; // rcx
  LSTATUS v6; // eax
  HKEY v7; // rcx
  LSTATUS v8; // eax
  HKEY v9; // rcx
  BYTE Data[4]; // [rsp+50h] [rbp-9h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-1h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp+7h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+Fh] BYREF
  _DWORD v15[4]; // [rsp+70h] [rbp+17h] BYREF
  _DWORD v16[4]; // [rsp+80h] [rbp+27h] BYREF

  ppv = 0;
  hKey = 0;
  phkResult = 0;
  *(_DWORD *)Data = 0;
  RegistryDwordValue = CoInitializeEx(0, 2u);
  if ( RegistryDwordValue >= 0 )
  {
    RegistryDwordValue = CoCreateInstance(&CLSID_GroupPolicyObject, 0, 1u, &IID_IGroupPolicyObject, &ppv);
    if ( RegistryDwordValue >= 0 )
    {
      RegistryDwordValue = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 40LL))(ppv, 1);
      if ( RegistryDwordValue >= 0 )
      {
        RegistryDwordValue = (*(__int64 (__fastcall **)(LPVOID, __int64, HKEY *))(*(_QWORD *)ppv + 120LL))(
                               ppv,
                               2,
                               &hKey);
        if ( RegistryDwordValue >= 0 )
        {
          v3 = RegCreateKeyExW(hKey, this[1], 0, 0, 0, 3u, 0, &phkResult, 0);
          RegistryDwordValue = v3;
          if ( !v3 )
            goto LABEL_9;
          if ( v3 > 0 )
            RegistryDwordValue = (unsigned __int16)v3 | 0x80070000;
          if ( RegistryDwordValue >= 0 )
          {
LABEL_9:
            RegistryDwordValue = CUtil::QueryRegistryDwordValue(v4, this[1], L"EnableLUA", (unsigned int *)Data);
            if ( RegistryDwordValue < 0 || *(_DWORD *)Data )
              goto LABEL_16;
            *(_DWORD *)Data = 1;
            v6 = RegSetValueExW(phkResult, L"EnableLUA", 0, 4u, Data, 4u);
            if ( v6 )
            {
              if ( v6 > 0 )
                RegistryDwordValue = (unsigned __int16)v6 | 0x80070000;
              else
                RegistryDwordValue = v6;
            }
            CUtil::SetRegistryDwordValue(v7, this[1], L"EnableLUA", 1u);
            if ( RegistryDwordValue >= 0 )
            {
LABEL_16:
              RegistryDwordValue = CUtil::QueryRegistryDwordValue(
                                     v5,
                                     this[1],
                                     L"ConsentPromptBehaviorAdmin",
                                     (unsigned int *)Data);
              if ( RegistryDwordValue < 0 || *(_DWORD *)Data )
                goto LABEL_23;
              *(_DWORD *)Data = 2;
              v8 = RegSetValueExW(phkResult, L"ConsentPromptBehaviorAdmin", 0, 4u, Data, 4u);
              if ( v8 )
              {
                if ( v8 > 0 )
                  RegistryDwordValue = (unsigned __int16)v8 | 0x80070000;
                else
                  RegistryDwordValue = v8;
              }
              CUtil::SetRegistryDwordValue(v9, this[1], L"ConsentPromptBehaviorAdmin", 2u);
              if ( RegistryDwordValue >= 0 )
              {
LABEL_23:
                v16[0] = 892833452;
                v16[1] = 299001919;
                v16[2] = -1073702232;
                v16[3] = -1563444401;
                v15[0] = -1038005774;
                v15[1] = 1077365993;
                v15[2] = -1230914911;
                v15[3] = -1802540717;
                RegistryDwordValue = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, _DWORD *, _DWORD *))(*(_QWORD *)ppv + 56LL))(
                                       ppv,
                                       1,
                                       1,
                                       v16,
                                       v15);
              }
            }
          }
        }
      }
    }
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  CoUninitialize();
  if ( RegistryDwordValue >= 0 && (unsigned int)CLuaSettingsChecktoid::IsRebootNeeded() )
    return 1;
  return (unsigned int)RegistryDwordValue;
}

```

## disassembly

```asm
0x180034b30  mov     [rsp-8+arg_8], rbx
0x180034b35  mov     [rsp-8+arg_10], rsi
0x180034b3a  push    rbp
0x180034b3b  push    rdi
0x180034b3c  push    r14
0x180034b3e  lea     rbp, [rsp-47h]
0x180034b43  sub     rsp, 0A0h
0x180034b4a  mov     rax, cs:__security_cookie
0x180034b51  xor     rax, rsp
0x180034b54  mov     [rbp+57h+var_20], rax
0x180034b58  xor     esi, esi
0x180034b5a  mov     rdi, rcx
0x180034b5d  xor     ecx, ecx; pvReserved
0x180034b5f  mov     [rbp+57h+var_58], rsi
0x180034b63  mov     [rbp+57h+hKey], rsi
0x180034b67  mov     [rbp+57h+var_50], rsi
0x180034b6b  lea     edx, [rsi+2]; dwCoInit
0x180034b6e  mov     dword ptr [rbp+57h+Data], esi
0x180034b71  call    cs:__imp_CoInitializeEx
0x180034b77  lea     r14d, [rsi+1]
0x180034b7b  mov     ebx, eax
0x180034b7d  test    eax, eax
0x180034b7f  js      loc_180034D92
0x180034b85  lea     rax, [rbp+57h+var_58]
0x180034b89  mov     r8d, r14d; dwClsContext
0x180034b8c  lea     r9, IID_IGroupPolicyObject; riid
0x180034b93  mov     [rsp+0B0h+ppv], rax; ppv
0x180034b98  xor     edx, edx; pUnkOuter
0x180034b9a  lea     rcx, CLSID_GroupPolicyObject; rclsid
0x180034ba1  call    cs:__imp_CoCreateInstance
0x180034ba7  mov     ebx, eax
0x180034ba9  test    eax, eax
0x180034bab  js      loc_180034D92
0x180034bb1  mov     rcx, [rbp+57h+var_58]
0x180034bb5  mov     edx, r14d
0x180034bb8  mov     rax, [rcx]
0x180034bbb  mov     rax, [rax+28h]
0x180034bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bc4  mov     ebx, eax
0x180034bc6  test    eax, eax
0x180034bc8  js      loc_180034D92
0x180034bce  mov     rcx, [rbp+57h+var_58]
0x180034bd2  lea     r8, [rbp+57h+hKey]
0x180034bd6  lea     edx, [rsi+2]
0x180034bd9  mov     rax, [rcx]
0x180034bdc  mov     rax, [rax+78h]
0x180034be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034be5  mov     ebx, eax
0x180034be7  test    eax, eax
0x180034be9  js      loc_180034D92
0x180034bef  mov     rdx, [rdi+8]; lpSubKey
0x180034bf3  lea     rax, [rbp+57h+var_50]
0x180034bf7  mov     rcx, [rbp+57h+hKey]; hKey
0x180034bfb  xor     r9d, r9d; lpClass
0x180034bfe  mov     [rsp+0B0h+lpdwDisposition], rsi; lpdwDisposition
0x180034c03  xor     r8d, r8d; Reserved
0x180034c06  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180034c0b  mov     [rsp+0B0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180034c10  mov     [rsp+0B0h+samDesired], 3; samDesired
0x180034c18  mov     dword ptr [rsp+0B0h+ppv], esi; dwOptions
0x180034c1c  call    cs:__imp_RegCreateKeyExW
0x180034c22  mov     ebx, eax
0x180034c24  test    eax, eax
0x180034c26  jz      short loc_180034C3B
0x180034c28  jle     short loc_180034C33
0x180034c2a  movzx   ebx, ax
0x180034c2d  or      ebx, 80070000h
0x180034c33  test    ebx, ebx
0x180034c35  js      loc_180034D92
0x180034c3b  mov     rdx, [rdi+8]; unsigned __int16 *
0x180034c3f  lea     r9, [rbp+57h+Data]; unsigned int *
0x180034c43  lea     r8, aEnablelua; "EnableLUA"
0x180034c4a  call    ?QueryRegistryDwordValue@CUtil@@SAJPEAUHKEY__@@PEBG1PEAK@Z; CUtil::QueryRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180034c4f  mov     ebx, eax
0x180034c51  test    eax, eax
0x180034c53  js      short loc_180034CB7
0x180034c55  cmp     dword ptr [rbp+57h+Data], esi
0x180034c58  jnz     short loc_180034CB7
0x180034c5a  mov     rcx, [rbp+57h+var_50]; hKey
0x180034c5e  lea     rax, [rbp+57h+Data]
0x180034c62  mov     [rsp+0B0h+samDesired], 4; cbData
0x180034c6a  lea     rdx, aEnablelua; "EnableLUA"
0x180034c71  mov     r9d, 4; dwType
0x180034c77  mov     [rsp+0B0h+ppv], rax; lpData
0x180034c7c  xor     r8d, r8d; Reserved
0x180034c7f  mov     dword ptr [rbp+57h+Data], r14d
0x180034c83  call    cs:__imp_RegSetValueExW
0x180034c89  test    eax, eax
0x180034c8b  jz      short loc_180034C9C
0x180034c8d  jg      short loc_180034C93
0x180034c8f  mov     ebx, eax
0x180034c91  jmp     short loc_180034C9C
0x180034c93  movzx   ebx, ax
0x180034c96  or      ebx, 80070000h
0x180034c9c  mov     rdx, [rdi+8]; unsigned __int16 *
0x180034ca0  lea     r8, aEnablelua; "EnableLUA"
0x180034ca7  mov     r9d, r14d; unsigned int
0x180034caa  call    ?SetRegistryDwordValue@CUtil@@SAJPEAUHKEY__@@PEBG1K@Z; CUtil::SetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong)
0x180034caf  test    ebx, ebx
0x180034cb1  js      loc_180034D92
0x180034cb7  mov     rdx, [rdi+8]; unsigned __int16 *
0x180034cbb  lea     r9, [rbp+57h+Data]; unsigned int *
0x180034cbf  lea     r8, aConsentpromptb; "ConsentPromptBehaviorAdmin"
0x180034cc6  call    ?QueryRegistryDwordValue@CUtil@@SAJPEAUHKEY__@@PEBG1PEAK@Z; CUtil::QueryRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180034ccb  mov     ebx, eax
0x180034ccd  test    eax, eax
0x180034ccf  js      short loc_180034D35
0x180034cd1  cmp     dword ptr [rbp+57h+Data], esi
0x180034cd4  jnz     short loc_180034D35
0x180034cd6  mov     rcx, [rbp+57h+var_50]; hKey
0x180034cda  lea     rax, [rbp+57h+Data]
0x180034cde  mov     [rsp+0B0h+samDesired], 4; cbData
0x180034ce6  lea     rdx, aConsentpromptb; "ConsentPromptBehaviorAdmin"
0x180034ced  mov     r9d, 4; dwType
0x180034cf3  mov     [rsp+0B0h+ppv], rax; lpData
0x180034cf8  xor     r8d, r8d; Reserved
0x180034cfb  mov     dword ptr [rbp+57h+Data], 2
0x180034d02  call    cs:__imp_RegSetValueExW
0x180034d08  test    eax, eax
0x180034d0a  jz      short loc_180034D1B
0x180034d0c  jg      short loc_180034D12
0x180034d0e  mov     ebx, eax
0x180034d10  jmp     short loc_180034D1B
0x180034d12  movzx   ebx, ax
0x180034d15  or      ebx, 80070000h
0x180034d1b  mov     rdx, [rdi+8]; unsigned __int16 *
0x180034d1f  lea     r8, aConsentpromptb; "ConsentPromptBehaviorAdmin"
0x180034d26  mov     r9d, 2; unsigned int
0x180034d2c  call    ?SetRegistryDwordValue@CUtil@@SAJPEAUHKEY__@@PEBG1K@Z; CUtil::SetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong)
0x180034d31  test    ebx, ebx
0x180034d33  js      short loc_180034D92
0x180034d35  mov     rcx, [rbp+57h+var_58]
0x180034d39  lea     rdx, [rbp+57h+var_40]
0x180034d3d  mov     [rbp+57h+var_30], 35378EACh
0x180034d44  lea     r9, [rbp+57h+var_30]
0x180034d48  mov     [rbp+57h+var_2C], 11D2683Fh
0x180034d4f  mov     r8d, r14d
0x180034d52  mov     [rbp+57h+var_28], 0C0009AA8h
0x180034d59  mov     [rbp+57h+var_24], 0A2CFBB4Fh
0x180034d60  mov     [rbp+57h+var_40], 0C22149F2h
0x180034d67  mov     [rbp+57h+var_3C], 40374CE9h
0x180034d6e  mov     [rbp+57h+var_38], 0B6A1BAA1h
0x180034d75  mov     [rbp+57h+var_34], 948F6953h
0x180034d7c  mov     rax, [rcx]
0x180034d7f  mov     [rsp+0B0h+ppv], rdx
0x180034d84  mov     edx, r14d
0x180034d87  mov     rax, [rax+38h]
0x180034d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d90  mov     ebx, eax
0x180034d92  mov     rcx, [rbp+57h+var_50]; hKey
0x180034d96  test    rcx, rcx
0x180034d99  jz      short loc_180034DA5
0x180034d9b  call    cs:__imp_RegCloseKey
0x180034da1  mov     [rbp+57h+var_50], rsi
0x180034da5  mov     rcx, [rbp+57h+hKey]; hKey
0x180034da9  test    rcx, rcx
0x180034dac  jz      short loc_180034DB8
0x180034dae  call    cs:__imp_RegCloseKey
0x180034db4  mov     [rbp+57h+hKey], rsi
0x180034db8  mov     rcx, [rbp+57h+var_58]
0x180034dbc  test    rcx, rcx
0x180034dbf  jz      short loc_180034DD1
0x180034dc1  mov     rax, [rcx]
0x180034dc4  mov     rax, [rax+10h]
0x180034dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034dcd  mov     [rbp+57h+var_58], rsi
0x180034dd1  call    cs:__imp_CoUninitialize
0x180034dd7  test    ebx, ebx
0x180034dd9  js      short loc_180034DE6
0x180034ddb  call    ?IsRebootNeeded@CLuaSettingsChecktoid@@CAHXZ; CLuaSettingsChecktoid::IsRebootNeeded(void)
0x180034de0  test    eax, eax
0x180034de2  cmovnz  ebx, r14d
0x180034de6  mov     eax, ebx
0x180034de8  mov     rcx, [rbp+57h+var_20]
0x180034dec  xor     rcx, rsp; StackCookie
0x180034def  call    __security_check_cookie
0x180034df4  lea     r11, [rsp+0B0h+var_10]
0x180034dfc  mov     rbx, [r11+28h]
0x180034e00  mov     rsi, [r11+30h]
0x180034e04  mov     rsp, r11
0x180034e07  pop     r14
0x180034e09  pop     rdi
0x180034e0a  pop     rbp
0x180034e0b  retn
```
