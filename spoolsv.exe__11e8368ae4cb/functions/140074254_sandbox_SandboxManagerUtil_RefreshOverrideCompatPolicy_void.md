# sandbox::SandboxManagerUtil::RefreshOverrideCompatPolicy(void)

- ea: `0x140074254`
- end: `0x14007436e`
- name: `?RefreshOverrideCompatPolicy@SandboxManagerUtil@sandbox@@AEAAXXZ`
- size: `282`
- prototype: `void __fastcall(sandbox::SandboxManagerUtil *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140074374`

## callees

- `0x14000bb78`
- `0x140010d3c`
- `0x14007310c`
- `0x140074254`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007428c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007428c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400742c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400742c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400742e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400742e5`

## string_xrefs

- `0x140074311`: `Override compat policy is %ws`
- `0x1400742ff`: `kOverrideCompatOFF`
- `0x140074343`: `kOverrideCompatOFF`
- `0x140074306`: `kOverrideCompatON`
- `0x14007434e`: `kOverrideCompatON`
- `0x140074318`: `sandbox::SandboxManagerUtil::RefreshOverrideCompatPolicy`
- `0x1400742a1`: `PrintDriverIsolationOverrideCompat`

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
0x140074254  mov     [rsp-8+arg_0], rbx
0x140074259  push    rbp
0x14007425a  mov     rbp, rsp
0x14007425d  sub     rsp, 40h
0x140074261  mov     rbx, rcx
0x140074264  mov     [rbp+hKey], 0
0x14007426c  lea     rax, [rbp+hKey]
0x140074270  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140074277  mov     r9d, 20019h; samDesired
0x14007427d  mov     [rsp+40h+phkResult], rax; phkResult
0x140074282  xor     r8d, r8d; ulOptions
0x140074285  lea     rdx, aSoftwarePolici_4; "Software\\Policies\\Microsoft\\Windows "...
0x14007428c  call    cs:__imp_RegOpenKeyExW
0x140074292  test    eax, eax
0x140074294  jnz     short loc_1400742EB
0x140074296  mov     rcx, [rbp+hKey]; hKey
0x14007429a  lea     r9, [rbp+Type]; lpType
0x14007429e  mov     [rbp+Data], eax
0x1400742a1  lea     rdx, aPrintdriveriso; "PrintDriverIsolationOverrideCompat"
0x1400742a8  mov     [rbp+Type], eax
0x1400742ab  xor     r8d, r8d; lpReserved
0x1400742ae  lea     rax, [rbp+cbData]
0x1400742b2  mov     [rbp+cbData], 4
0x1400742b9  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1400742be  lea     rax, [rbp+Data]
0x1400742c2  mov     [rsp+40h+phkResult], rax; lpData
0x1400742c7  call    cs:__imp_RegQueryValueExW
0x1400742cd  test    eax, eax
0x1400742cf  jnz     short loc_1400742E1
0x1400742d1  cmp     [rbp+Type], 4
0x1400742d5  jnz     short loc_1400742E1
0x1400742d7  cmp     [rbp+Data], 1
0x1400742db  setz    al
0x1400742de  mov     [rbx+50h], eax
0x1400742e1  mov     rcx, [rbp+hKey]; hKey
0x1400742e5  call    cs:__imp_RegCloseKey
0x1400742eb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x1400742f2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x1400742f7  test    al, al
0x1400742f9  jz      short loc_140074326
0x1400742fb  cmp     dword ptr [rbx+50h], 1
0x1400742ff  lea     rax, aKoverridecompa; "kOverrideCompatOFF"
0x140074306  lea     r8, aKoverridecompa_0; "kOverrideCompatON"
0x14007430d  cmovnz  r8, rax
0x140074311  lea     rdx, aOverrideCompat; "Override compat policy is %ws"
0x140074318  lea     rcx, aSandboxSandbox_2; "sandbox::SandboxManagerUtil::RefreshOve"...
0x14007431f  call    ?WriteDbgTraceInfo@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140074324  jmp     short loc_140074363
0x140074326  mov     rcx, cs:WPP_GLOBAL_Control
0x14007432d  lea     rax, WPP_GLOBAL_Control
0x140074334  cmp     rcx, rax
0x140074337  jz      short loc_140074363
0x140074339  test    byte ptr [rcx+1Ch], 2
0x14007433d  jz      short loc_140074363
0x14007433f  cmp     dword ptr [rbx+50h], 1
0x140074343  lea     rax, aKoverridecompa; "kOverrideCompatOFF"
0x14007434a  mov     rcx, [rcx+10h]
0x14007434e  lea     r9, aKoverridecompa_0; "kOverrideCompatON"
0x140074355  cmovnz  r9, rax
0x140074359  mov     edx, 0Eh
0x14007435e  call    WPP_SF_S
0x140074363  mov     rbx, [rsp+40h+arg_0]
0x140074368  add     rsp, 40h
0x14007436c  pop     rbp
0x14007436d  retn
```
