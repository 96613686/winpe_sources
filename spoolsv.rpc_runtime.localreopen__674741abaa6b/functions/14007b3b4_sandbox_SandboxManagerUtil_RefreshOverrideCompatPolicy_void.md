# sandbox::SandboxManagerUtil::RefreshOverrideCompatPolicy(void)

- ea: `0x14007b3b4`
- end: `0x14007b4e1`
- name: `?RefreshOverrideCompatPolicy@SandboxManagerUtil@sandbox@@AEAAXXZ`
- size: `301`
- prototype: `void __fastcall(sandbox::SandboxManagerUtil *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14007b4e8`

## callees

- `0x14000cbf8`
- `0x1400120e0`
- `0x14007a1d4`
- `0x14007b3b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007b3ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007b3ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007b42d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007b42d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007b451`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007b451`

## string_xrefs

- `0x14007b478`: `kOverrideCompatON`
- `0x14007b4c0`: `kOverrideCompatON`
- `0x14007b48a`: `sandbox::SandboxManagerUtil::RefreshOverrideCompatPolicy`
- `0x14007b483`: `Override compat policy is %ws`
- `0x14007b471`: `kOverrideCompatOFF`
- `0x14007b4b5`: `kOverrideCompatOFF`
- `0x14007b407`: `PrintDriverIsolationOverrideCompat`

## pseudocode

```c
void __fastcall sandbox::SandboxManagerUtil::RefreshOverrideCompatPolicy(sandbox::SandboxManagerUtil *this)
{
  LSTATUS v2; // eax
  __int64 v3; // r8
  const wchar_t *v4; // r8
  const wchar_t *v5; // r9
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+58h] [rbp+18h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows NT\\Printers", 0, 0x20019u, &hKey) )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    v2 = RegQueryValueExW(hKey, L"PrintDriverIsolationOverrideCompat", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v2 && Type == 4 )
    {
      LOBYTE(v2) = Data == 1;
      *((_DWORD *)this + 20) = v2;
    }
    RegCloseKey(hKey);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
  {
    v4 = L"kOverrideCompatON";
    if ( *((_DWORD *)this + 20) != 1 )
      v4 = L"kOverrideCompatOFF";
    SandboxTelemetry::WriteDbgTraceInfo(
      "sandbox::SandboxManagerUtil::RefreshOverrideCompatPolicy",
      L"Override compat policy is %ws",
      v4);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v5 = L"kOverrideCompatON";
    if ( *((_DWORD *)this + 20) != 1 )
      v5 = L"kOverrideCompatOFF";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v3, v5);
  }
}

```

## disassembly

```asm
0x14007b3b4  mov     [rsp-8+arg_0], rbx
0x14007b3b9  push    rbp
0x14007b3ba  mov     rbp, rsp
0x14007b3bd  sub     rsp, 40h
0x14007b3c1  mov     rbx, rcx
0x14007b3c4  mov     [rbp+hKey], 0
0x14007b3cc  lea     rax, [rbp+hKey]
0x14007b3d0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14007b3d7  mov     r9d, 20019h; samDesired
0x14007b3dd  mov     [rsp+40h+phkResult], rax; phkResult
0x14007b3e2  xor     r8d, r8d; ulOptions
0x14007b3e5  lea     rdx, aSoftwarePolici_4; "Software\\Policies\\Microsoft\\Windows "...
0x14007b3ec  call    cs:__imp_RegOpenKeyExW
0x14007b3f3  nop     dword ptr [rax+rax+00h]
0x14007b3f8  test    eax, eax
0x14007b3fa  jnz     short loc_14007B45D
0x14007b3fc  mov     rcx, [rbp+hKey]; hKey
0x14007b400  lea     r9, [rbp+Type]; lpType
0x14007b404  mov     [rbp+Data], eax
0x14007b407  lea     rdx, aPrintdriveriso; "PrintDriverIsolationOverrideCompat"
0x14007b40e  mov     [rbp+Type], eax
0x14007b411  xor     r8d, r8d; lpReserved
0x14007b414  lea     rax, [rbp+cbData]
0x14007b418  mov     [rbp+cbData], 4
0x14007b41f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14007b424  lea     rax, [rbp+Data]
0x14007b428  mov     [rsp+40h+phkResult], rax; lpData
0x14007b42d  call    cs:__imp_RegQueryValueExW
0x14007b434  nop     dword ptr [rax+rax+00h]
0x14007b439  test    eax, eax
0x14007b43b  jnz     short loc_14007B44D
0x14007b43d  cmp     [rbp+Type], 4
0x14007b441  jnz     short loc_14007B44D
0x14007b443  cmp     [rbp+Data], 1
0x14007b447  setz    al
0x14007b44a  mov     [rbx+50h], eax
0x14007b44d  mov     rcx, [rbp+hKey]; hKey
0x14007b451  call    cs:__imp_RegCloseKey
0x14007b458  nop     dword ptr [rax+rax+00h]
0x14007b45d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x14007b464  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x14007b469  test    al, al
0x14007b46b  jz      short loc_14007B498
0x14007b46d  cmp     dword ptr [rbx+50h], 1
0x14007b471  lea     rax, aKoverridecompa; "kOverrideCompatOFF"
0x14007b478  lea     r8, aKoverridecompa_0; "kOverrideCompatON"
0x14007b47f  cmovnz  r8, rax
0x14007b483  lea     rdx, aOverrideCompat; "Override compat policy is %ws"
0x14007b48a  lea     rcx, aSandboxSandbox_2; "sandbox::SandboxManagerUtil::RefreshOve"...
0x14007b491  call    ?WriteDbgTraceInfo@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14007b496  jmp     short loc_14007B4D5
0x14007b498  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b49f  lea     rax, WPP_GLOBAL_Control
0x14007b4a6  cmp     rcx, rax
0x14007b4a9  jz      short loc_14007B4D5
0x14007b4ab  test    byte ptr [rcx+1Ch], 2
0x14007b4af  jz      short loc_14007B4D5
0x14007b4b1  cmp     dword ptr [rbx+50h], 1
0x14007b4b5  lea     rax, aKoverridecompa; "kOverrideCompatOFF"
0x14007b4bc  mov     rcx, [rcx+10h]
0x14007b4c0  lea     r9, aKoverridecompa_0; "kOverrideCompatON"
0x14007b4c7  cmovnz  r9, rax
0x14007b4cb  mov     edx, 0Eh
0x14007b4d0  call    WPP_SF_S
0x14007b4d5  mov     rbx, [rsp+40h+arg_0]
0x14007b4da  add     rsp, 40h
0x14007b4de  pop     rbp
0x14007b4df  retn
```
