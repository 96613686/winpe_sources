# CHost::GetTrustPolicyFromRegistry(void)

- ea: `0x14000a3f8`
- end: `0x14000a55f`
- name: `?GetTrustPolicyFromRegistry@CHost@@IEAAXXZ`
- size: `359`
- prototype: `void __fastcall(CHost *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000919c`

## callees

- `0x14000a3f8`
- `0x14001550c`
- `0x140015794`
- `0x140015a7c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000a53f`
- `ADVAPI32!RegCloseKey` at `0x14000a54e`
- `ADVAPI32!RegCloseKey` at `0x14000a53f`
- `ADVAPI32!RegCloseKey` at `0x14000a54e`

## pseudocode

```c
void __fastcall CHost::GetTrustPolicyFromRegistry(CHost *this)
{
  bool v2; // bl
  char v3; // di
  unsigned int v4; // edi
  HKEY v5; // rcx
  signed int RegSettingsBool; // eax
  HKEY phkResult; // [rsp+20h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+28h] [rbp-8h] BYREF
  bool v9; // [rsp+68h] [rbp+38h] BYREF
  bool v10; // [rsp+70h] [rbp+40h] BYREF
  int Data; // [rsp+78h] [rbp+48h] BYREF

  hKey = 0;
  phkResult = 0;
  v2 = 0;
  v10 = 0;
  Data = 0;
  v9 = 0;
  v3 = 0;
  OpenRegSettings(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows Script Host\\Settings", 0x20019u, &phkResult);
  if ( !phkResult || (GetRegSettingsBool(phkResult, L"IgnoreUserSettings", &v10), !v10) )
    OpenRegSettings(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows Script Host\\Settings", 0x20019u, &hKey);
  if ( hKey )
  {
    v4 = (unsigned int)GetRegSettingsInt(hKey, L"TrustPolicy", (LPBYTE)&Data) >> 31;
    v2 = GetRegSettingsBool(hKey, L"UseWINSAFER", &v9) >= 0;
    v3 = v4 ^ 1;
    if ( v3 )
      goto LABEL_9;
  }
  v5 = phkResult;
  if ( phkResult )
  {
    if ( GetRegSettingsInt(phkResult, L"TrustPolicy", (LPBYTE)&Data) >= 0 )
      v3 = 1;
LABEL_9:
    v5 = phkResult;
  }
  if ( !v2 && v5 )
  {
    RegSettingsBool = GetRegSettingsBool(v5, L"UseWINSAFER", &v9);
    v5 = phkResult;
    v2 = RegSettingsBool >= 0;
  }
  if ( v3 && Data > *((_DWORD *)this + 19) )
    *((_DWORD *)this + 19) = Data;
  if ( v2 )
    *((_BYTE *)this + 74) = v9;
  if ( hKey )
  {
    RegCloseKey(hKey);
    v5 = phkResult;
  }
  if ( v5 )
    RegCloseKey(v5);
}

```

## disassembly

```asm
0x14000a3f8  push    rbp
0x14000a3fa  push    rbx
0x14000a3fb  push    rsi
0x14000a3fc  push    rdi
0x14000a3fd  push    r15
0x14000a3ff  mov     rbp, rsp
0x14000a402  sub     rsp, 30h
0x14000a406  mov     rsi, rcx
0x14000a409  mov     [rbp+hKey], 0
0x14000a411  mov     r15d, 20019h
0x14000a417  mov     [rbp+phkResult], 0
0x14000a41f  xor     bl, bl
0x14000a421  mov     [rbp+arg_10], 0
0x14000a425  mov     r8d, r15d; samDesired
0x14000a428  mov     [rbp+Data], 0
0x14000a42f  lea     r9, [rbp+phkResult]; phkResult
0x14000a433  mov     [rbp+arg_8], bl
0x14000a436  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Script Hos"...
0x14000a43d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000a444  xor     dil, dil
0x14000a447  call    ?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x14000a44c  mov     rcx, [rbp+phkResult]; hKey
0x14000a450  test    rcx, rcx
0x14000a453  jz      short loc_14000A46A
0x14000a455  lea     r8, [rbp+arg_10]; bool *
0x14000a459  lea     rdx, aIgnoreusersett; "IgnoreUserSettings"
0x14000a460  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x14000a465  cmp     [rbp+arg_10], bl
0x14000a468  jnz     short loc_14000A484
0x14000a46a  lea     r9, [rbp+hKey]; phkResult
0x14000a46e  mov     r8d, r15d; samDesired
0x14000a471  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Script Hos"...
0x14000a478  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000a47f  call    ?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x14000a484  mov     rax, [rbp+hKey]
0x14000a488  mov     r15d, 1
0x14000a48e  test    rax, rax
0x14000a491  jz      short loc_14000A4CC
0x14000a493  lea     r8, [rbp+Data]; lpData
0x14000a497  mov     rcx, rax; hKey
0x14000a49a  lea     rdx, aTrustpolicy; "TrustPolicy"
0x14000a4a1  call    ?GetRegSettingsInt@@YAJPEAUHKEY__@@PEBGPEAK@Z; GetRegSettingsInt(HKEY__ *,ushort const *,ulong *)
0x14000a4a6  mov     rcx, [rbp+hKey]; hKey
0x14000a4aa  lea     r8, [rbp+arg_8]; bool *
0x14000a4ae  mov     edi, eax
0x14000a4b0  lea     rdx, aUsewinsafer; "UseWINSAFER"
0x14000a4b7  shr     edi, 1Fh
0x14000a4ba  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x14000a4bf  mov     ebx, eax
0x14000a4c1  shr     ebx, 1Fh
0x14000a4c4  xor     bl, r15b
0x14000a4c7  xor     dil, r15b
0x14000a4ca  jnz     short loc_14000A4EF
0x14000a4cc  mov     rcx, [rbp+phkResult]; hKey
0x14000a4d0  test    rcx, rcx
0x14000a4d3  jz      short loc_14000A4F3
0x14000a4d5  lea     r8, [rbp+Data]; lpData
0x14000a4d9  lea     rdx, aTrustpolicy; "TrustPolicy"
0x14000a4e0  call    ?GetRegSettingsInt@@YAJPEAUHKEY__@@PEBGPEAK@Z; GetRegSettingsInt(HKEY__ *,ushort const *,ulong *)
0x14000a4e5  test    eax, eax
0x14000a4e7  movzx   edi, dil
0x14000a4eb  cmovns  edi, r15d
0x14000a4ef  mov     rcx, [rbp+phkResult]; hKey
0x14000a4f3  test    bl, bl
0x14000a4f5  jnz     short loc_14000A519
0x14000a4f7  test    rcx, rcx
0x14000a4fa  jz      short loc_14000A519
0x14000a4fc  lea     r8, [rbp+arg_8]; bool *
0x14000a500  lea     rdx, aUsewinsafer; "UseWINSAFER"
0x14000a507  call    ?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z; GetRegSettingsBool(HKEY__ *,ushort const *,bool *)
0x14000a50c  mov     rcx, [rbp+phkResult]
0x14000a510  test    eax, eax
0x14000a512  movzx   ebx, bl
0x14000a515  cmovns  ebx, r15d
0x14000a519  test    dil, dil
0x14000a51c  jz      short loc_14000A529
0x14000a51e  mov     eax, [rbp+Data]
0x14000a521  cmp     eax, [rsi+4Ch]
0x14000a524  jle     short loc_14000A529
0x14000a526  mov     [rsi+4Ch], eax
0x14000a529  test    bl, bl
0x14000a52b  jz      short loc_14000A533
0x14000a52d  mov     al, [rbp+arg_8]
0x14000a530  mov     [rsi+4Ah], al
0x14000a533  mov     rax, [rbp+hKey]
0x14000a537  test    rax, rax
0x14000a53a  jz      short loc_14000A549
0x14000a53c  mov     rcx, rax; hKey
0x14000a53f  call    cs:__imp_RegCloseKey
0x14000a545  mov     rcx, [rbp+phkResult]; hKey
0x14000a549  test    rcx, rcx
0x14000a54c  jz      short loc_14000A554
0x14000a54e  call    cs:__imp_RegCloseKey
0x14000a554  add     rsp, 30h
0x14000a558  pop     r15
0x14000a55a  pop     rdi
0x14000a55b  pop     rsi
0x14000a55c  pop     rbx
0x14000a55d  pop     rbp
0x14000a55e  retn
```
