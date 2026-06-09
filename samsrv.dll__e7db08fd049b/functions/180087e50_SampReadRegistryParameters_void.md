# SampReadRegistryParameters(void *)

- ea: `0x180087e50`
- end: `0x18008812e`
- name: `?SampReadRegistryParameters@@YAJPEAX@Z`
- size: `734`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x1800799a8`

## callees

- `0x180012a28`
- `0x180027e24`
- `0x1800619e0`
- `0x1800798a0`
- `0x180079924`
- `0x180087e50`
- `0x18008d250`
- `0x18008d30c`
- `0x18008e480`
- `0x1800ac464`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087e92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087e92`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180087f12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180087fa8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180087ffe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180088051`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180087f12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180087fa8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180087ffe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180088051`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800880e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800880e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800880a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800880a3`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtTransformClaimsSetEcho` at `0x1800880c1`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtTransformClaimsSetEcho` at `0x1800880c1`

## pseudocode

```c
__int64 __fastcall SampReadRegistryParameters(void *a1)
{
  __int64 i; // rbx
  unsigned int v3; // ebx
  BYTE Data[4]; // [rsp+30h] [rbp-20h] BYREF
  BYTE v5[4]; // [rsp+34h] [rbp-1Ch] BYREF
  DWORD lpcbData; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  DWORD v8; // [rsp+88h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+40h] BYREF
  DWORD Type; // [rsp+98h] [rbp+48h] BYREF

  hKey = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 0x2000000u, &hKey) )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        206,
        WPP_6405431812663459a7a3c2922bf567cd_Traceguids,
        3221225473LL,
        -1073741823);
    return 3221225473LL;
  }
  else
  {
    for ( i = 0; i != 14; ++i )
    {
      cbData = 4;
      *(&off_1800C32F0)[2 * i + 1] = !RegQueryValueExA(hKey, (&off_1800C32F0)[2 * i], 0, &Type, Data, &cbData)
                                  && Type == 4
                                  && *(_DWORD *)Data == 1;
    }
    LOBYTE(v8) = 0;
    if ( SampIsSetupInProgress((bool *)&v8) )
      SampLimitBlankPasswordUse = 0;
    SampCheckNullSessionAccess(hKey);
    SampCheckRestrictRemoteAccess(hKey);
    SampInitEmulationSettings(hKey);
    *(_DWORD *)v5 = 1;
    v8 = 0;
    lpcbData = 4;
    if ( RegQueryValueExA(hKey, "SamRestrictOwfPasswordChange", 0, &v8, v5, &lpcbData)
      || v8 != 4
      || (SampRestrictOwfPasswordChange = *(_DWORD *)v5, *(_DWORD *)v5 > 2u) )
    {
      SampRestrictOwfPasswordChange = 1;
    }
    v8 = 0;
    *(_DWORD *)v5 = 0;
    lpcbData = 4;
    if ( RegQueryValueExA(hKey, "MaxSamConnections", 0, &v8, v5, &lpcbData) || v8 != 4 )
      SampMaxSamConnections = 2048;
    else
      SampMaxSamConnections = *(_DWORD *)v5;
    *(_DWORD *)v5 = 0;
    v8 = 0;
    lpcbData = 4;
    if ( RegQueryValueExA(hKey, "dsrmAdminLogonBehavior", 0, &v8, v5, &lpcbData)
      || v8 != 4
      || (SampDsrmAdminBehavior = *(_DWORD *)v5, *(_DWORD *)v5 > 2u) )
    {
      SampDsrmAdminBehavior = 0;
    }
    *(_DWORD *)v5 = 0;
    v8 = 0;
    lpcbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnableClaimsTransformationEcho", 0, &v8, v5, &lpcbData) && v8 == 4 )
    {
      v3 = *(_DWORD *)v5;
      if ( (int)SampShouldCallNtdsaApiSet() >= 0 )
        NtdsaExtTransformClaimsSetEcho(v3);
    }
    SampInitEnumerationCachePurgeInterval(hKey);
    SampInitEnumerationCacheEntryLifetime(hKey);
    SampPasswordModeChange(hKey);
    RegCloseKey(hKey);
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 207, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, 0, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x180087e50  mov     [rsp-28h+arg_0], rbx
0x180087e55  push    rbp
0x180087e56  push    rsi
0x180087e57  push    rdi
0x180087e58  push    r14
0x180087e5a  push    r15
0x180087e5c  mov     rbp, rsp
0x180087e5f  sub     rsp, 50h
0x180087e63  xor     esi, esi
0x180087e65  lea     rax, [rbp+hKey]
0x180087e69  mov     r9d, 2000000h; samDesired
0x180087e6f  mov     [rbp+hKey], rsi
0x180087e73  xor     r8d, r8d; ulOptions
0x180087e76  mov     [rbp+cbData], esi
0x180087e79  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\Lsa"
0x180087e80  mov     dword ptr [rbp+Data], esi
0x180087e83  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180087e8a  mov     [rbp+Type], esi
0x180087e8d  mov     [rsp+50h+phkResult], rax; phkResult
0x180087e92  call    cs:__imp_RegOpenKeyExW
0x180087e98  test    eax, eax
0x180087e9a  jz      short loc_180087ED7
0x180087e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180087ea3  mov     ebx, 0C0000001h
0x180087ea8  test    dword ptr [rcx+44h], 20000h
0x180087eaf  jz      short loc_180087ED0
0x180087eb1  mov     rcx, [rcx+38h]
0x180087eb5  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180087ebc  mov     edx, 0CEh
0x180087ec1  mov     dword ptr [rsp+50h+phkResult], ebx
0x180087ec5  mov     r9d, 0C0000001h
0x180087ecb  call    WPP_SF_Dd
0x180087ed0  mov     eax, ebx
0x180087ed2  jmp     loc_18008811A
0x180087ed7  mov     rbx, rsi
0x180087eda  lea     r15, off_1800C32F0; "SamReplicatePasswordsUrgently"
0x180087ee1  mov     r14d, 4
0x180087ee7  mov     rcx, [rbp+hKey]; hKey
0x180087eeb  lea     rax, [rbp+cbData]
0x180087eef  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180087ef4  lea     r9, [rbp+Type]; lpType
0x180087ef8  lea     rax, [rbp+Data]
0x180087efc  mov     [rbp+cbData], r14d
0x180087f00  mov     rdi, rbx
0x180087f03  mov     [rsp+50h+phkResult], rax; lpData
0x180087f08  add     rdi, rdi
0x180087f0b  xor     r8d, r8d; lpReserved
0x180087f0e  mov     rdx, [r15+rdi*8]; lpValueName
0x180087f12  call    cs:__imp_RegQueryValueExA
0x180087f18  test    eax, eax
0x180087f1a  jnz     short loc_180087F32
0x180087f1c  cmp     [rbp+Type], r14d
0x180087f20  jnz     short loc_180087F32
0x180087f22  cmp     dword ptr [rbp+Data], 1
0x180087f26  jnz     short loc_180087F32
0x180087f28  mov     rax, [r15+rdi*8+8]
0x180087f2d  mov     byte ptr [rax], 1
0x180087f30  jmp     short loc_180087F3A
0x180087f32  mov     rax, [r15+rdi*8+8]
0x180087f37  mov     [rax], sil
0x180087f3a  inc     rbx
0x180087f3d  cmp     rbx, 0Eh
0x180087f41  jnz     short loc_180087EE7
0x180087f43  lea     rcx, [rbp+arg_8]; unsigned __int8 *
0x180087f47  mov     byte ptr [rbp+arg_8], sil
0x180087f4b  call    ?SampIsSetupInProgress@@YAEPEAE@Z; SampIsSetupInProgress(uchar *)
0x180087f50  test    al, al
0x180087f52  jz      short loc_180087F5B
0x180087f54  mov     cs:?SampLimitBlankPasswordUse@@3EA, sil; uchar SampLimitBlankPasswordUse
0x180087f5b  mov     rcx, [rbp+hKey]; hKey
0x180087f5f  call    ?SampCheckNullSessionAccess@@YAXPEAUHKEY__@@@Z; SampCheckNullSessionAccess(HKEY__ *)
0x180087f64  mov     rcx, [rbp+hKey]; hKey
0x180087f68  call    ?SampCheckRestrictRemoteAccess@@YAXPEAUHKEY__@@@Z; SampCheckRestrictRemoteAccess(HKEY__ *)
0x180087f6d  mov     rcx, [rbp+hKey]; HKEY
0x180087f71  call    ?SampInitEmulationSettings@@YAXPEAUHKEY__@@@Z; SampInitEmulationSettings(HKEY__ *)
0x180087f76  mov     rcx, [rbp+hKey]; hKey
0x180087f7a  lea     rax, [rbp+var_18]
0x180087f7e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180087f83  lea     r9, [rbp+arg_8]; lpType
0x180087f87  lea     rax, [rbp+var_1C]
0x180087f8b  mov     dword ptr [rbp+var_1C], 1
0x180087f92  xor     r8d, r8d; lpReserved
0x180087f95  mov     [rsp+50h+phkResult], rax; lpData
0x180087f9a  lea     rdx, aSamrestrictowf; "SamRestrictOwfPasswordChange"
0x180087fa1  mov     [rbp+arg_8], esi
0x180087fa4  mov     [rbp+var_18], r14d
0x180087fa8  call    cs:__imp_RegQueryValueExA
0x180087fae  test    eax, eax
0x180087fb0  jnz     short loc_180087FC6
0x180087fb2  cmp     [rbp+arg_8], r14d
0x180087fb6  jnz     short loc_180087FC6
0x180087fb8  mov     eax, dword ptr [rbp+var_1C]
0x180087fbb  mov     cs:?SampRestrictOwfPasswordChange@@3KA, eax; ulong SampRestrictOwfPasswordChange
0x180087fc1  cmp     eax, 2
0x180087fc4  jbe     short loc_180087FD0
0x180087fc6  mov     cs:?SampRestrictOwfPasswordChange@@3KA, 1; ulong SampRestrictOwfPasswordChange
0x180087fd0  mov     rcx, [rbp+hKey]; hKey
0x180087fd4  lea     rax, [rbp+var_18]
0x180087fd8  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180087fdd  lea     r9, [rbp+arg_8]; lpType
0x180087fe1  lea     rax, [rbp+var_1C]
0x180087fe5  mov     [rbp+arg_8], esi
0x180087fe8  xor     r8d, r8d; lpReserved
0x180087feb  mov     [rsp+50h+phkResult], rax; lpData
0x180087ff0  lea     rdx, aMaxsamconnecti; "MaxSamConnections"
0x180087ff7  mov     dword ptr [rbp+var_1C], esi
0x180087ffa  mov     [rbp+var_18], r14d
0x180087ffe  call    cs:__imp_RegQueryValueExA
0x180088004  test    eax, eax
0x180088006  jnz     short loc_180088019
0x180088008  cmp     [rbp+arg_8], r14d
0x18008800c  jnz     short loc_180088019
0x18008800e  mov     eax, dword ptr [rbp+var_1C]
0x180088011  mov     cs:?SampMaxSamConnections@@3KA, eax; ulong SampMaxSamConnections
0x180088017  jmp     short loc_180088023
0x180088019  mov     cs:?SampMaxSamConnections@@3KA, 800h; ulong SampMaxSamConnections
0x180088023  mov     rcx, [rbp+hKey]; hKey
0x180088027  lea     rax, [rbp+var_18]
0x18008802b  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180088030  lea     r9, [rbp+arg_8]; lpType
0x180088034  lea     rax, [rbp+var_1C]
0x180088038  mov     dword ptr [rbp+var_1C], esi
0x18008803b  xor     r8d, r8d; lpReserved
0x18008803e  mov     [rsp+50h+phkResult], rax; lpData
0x180088043  lea     rdx, aDsrmadminlogon; "dsrmAdminLogonBehavior"
0x18008804a  mov     [rbp+arg_8], esi
0x18008804d  mov     [rbp+var_18], r14d
0x180088051  call    cs:__imp_RegQueryValueExA
0x180088057  test    eax, eax
0x180088059  jnz     short loc_18008806F
0x18008805b  cmp     [rbp+arg_8], r14d
0x18008805f  jnz     short loc_18008806F
0x180088061  mov     eax, dword ptr [rbp+var_1C]
0x180088064  mov     cs:?SampDsrmAdminBehavior@@3KA, eax; ulong SampDsrmAdminBehavior
0x18008806a  cmp     eax, 2
0x18008806d  jbe     short loc_180088075
0x18008806f  mov     cs:?SampDsrmAdminBehavior@@3KA, esi; ulong SampDsrmAdminBehavior
0x180088075  mov     rcx, [rbp+hKey]; hKey
0x180088079  lea     rax, [rbp+var_18]
0x18008807d  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180088082  lea     r9, [rbp+arg_8]; lpType
0x180088086  lea     rax, [rbp+var_1C]
0x18008808a  mov     dword ptr [rbp+var_1C], esi
0x18008808d  xor     r8d, r8d; lpReserved
0x180088090  mov     [rsp+50h+phkResult], rax; lpData
0x180088095  lea     rdx, aEnableclaimstr; "EnableClaimsTransformationEcho"
0x18008809c  mov     [rbp+arg_8], esi
0x18008809f  mov     [rbp+var_18], r14d
0x1800880a3  call    cs:__imp_RegQueryValueExW
0x1800880a9  test    eax, eax
0x1800880ab  jnz     short loc_1800880C7
0x1800880ad  cmp     [rbp+arg_8], r14d
0x1800880b1  jnz     short loc_1800880C7
0x1800880b3  mov     ebx, dword ptr [rbp+var_1C]
0x1800880b6  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x1800880bb  test    eax, eax
0x1800880bd  js      short loc_1800880C7
0x1800880bf  mov     ecx, ebx
0x1800880c1  call    cs:__imp_NtdsaExtTransformClaimsSetEcho
0x1800880c7  mov     rcx, [rbp+hKey]; HKEY
0x1800880cb  call    ?SampInitEnumerationCachePurgeInterval@@YAXPEAUHKEY__@@@Z; SampInitEnumerationCachePurgeInterval(HKEY__ *)
0x1800880d0  mov     rcx, [rbp+hKey]; HKEY
0x1800880d4  call    ?SampInitEnumerationCacheEntryLifetime@@YAXPEAUHKEY__@@@Z; SampInitEnumerationCacheEntryLifetime(HKEY__ *)
0x1800880d9  mov     rcx, [rbp+hKey]; HKEY
0x1800880dd  call    ?SampPasswordModeChange@@YAXPEAUHKEY__@@@Z; SampPasswordModeChange(HKEY__ *)
0x1800880e2  mov     rcx, [rbp+hKey]; hKey
0x1800880e6  call    cs:__imp_RegCloseKey
0x1800880ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800880f3  test    dword ptr [rcx+44h], 20000h
0x1800880fa  jz      short loc_180088118
0x1800880fc  mov     rcx, [rcx+38h]
0x180088100  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180088107  mov     edx, 0CFh
0x18008810c  mov     dword ptr [rsp+50h+phkResult], esi
0x180088110  xor     r9d, r9d
0x180088113  call    WPP_SF_Dd
0x180088118  xor     eax, eax
0x18008811a  mov     rbx, [rsp+50h+arg_0]
0x180088122  add     rsp, 50h
0x180088126  pop     r15
0x180088128  pop     r14
0x18008812a  pop     rdi
0x18008812b  pop     rsi
0x18008812c  pop     rbp
0x18008812d  retn
```
