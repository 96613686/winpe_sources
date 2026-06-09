# sandbox::IsV4PrinterDriver(ushort const *)

- ea: `0x140074090`
- end: `0x140074184`
- name: `?IsV4PrinterDriver@sandbox@@YA_NPEBG@Z`
- size: `244`
- prototype: `bool __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140073c1c`

## callees

- `0x14000bb78`
- `0x140011020`
- `0x140073064`
- `0x140074090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400740c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400740f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400740c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400740f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140074107`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140074112`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140074107`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140074112`

## pseudocode

```c
unsigned __int8 __fastcall sandbox::IsV4PrinterDriver(LPCWSTR lpSubKey, const unsigned __int16 *a2)
{
  unsigned __int8 v3; // bl
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v3 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\Print\\Environments\\Windows x64\\Drivers\\Version-4",
          0,
          0x20019u,
          &hKey) )
  {
    phkResult = 0;
    if ( !RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult) )
    {
      v3 = 1;
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
  {
    SandboxTelemetry::WriteDbgTraceError("sandbox::IsV4PrinterDriver", L"Printer driver %ws is v4 %u", lpSubKey, v3);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v3, (_DWORD)lpSubKey, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x140074090  mov     r11, rsp
0x140074093  mov     [r11+8], rbx
0x140074097  push    rdi
0x140074098  sub     rsp, 30h
0x14007409c  mov     rdi, rcx
0x14007409f  mov     qword ptr [r11+10h], 0
0x1400740a7  lea     rax, [r11+10h]
0x1400740ab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400740b2  mov     r9d, 20019h; samDesired
0x1400740b8  mov     [r11-18h], rax
0x1400740bc  xor     r8d, r8d; ulOptions
0x1400740bf  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Pri"...
0x1400740c6  xor     bl, bl
0x1400740c8  call    cs:__imp_RegOpenKeyExW
0x1400740ce  test    eax, eax
0x1400740d0  jnz     short loc_140074118
0x1400740d2  mov     rcx, [rsp+38h+hKey]; hKey
0x1400740d7  lea     rax, [rsp+38h+arg_10]
0x1400740dc  mov     r9d, 20019h; samDesired
0x1400740e2  mov     [rsp+38h+phkResult], rax; phkResult
0x1400740e7  xor     r8d, r8d; ulOptions
0x1400740ea  mov     [rsp+38h+arg_10], 0
0x1400740f3  mov     rdx, rdi; lpSubKey
0x1400740f6  call    cs:__imp_RegOpenKeyExW
0x1400740fc  test    eax, eax
0x1400740fe  jnz     short loc_14007410D
0x140074100  mov     rcx, [rsp+38h+arg_10]; hKey
0x140074105  mov     bl, 1
0x140074107  call    cs:__imp_RegCloseKey
0x14007410d  mov     rcx, [rsp+38h+hKey]; hKey
0x140074112  call    cs:__imp_RegCloseKey
0x140074118  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x14007411f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x140074124  test    al, al
0x140074126  jz      short loc_140074144
0x140074128  movzx   r9d, bl
0x14007412c  lea     rdx, aPrinterDriverW; "Printer driver %ws is v4 %u"
0x140074133  mov     r8, rdi
0x140074136  lea     rcx, aSandboxIsv4pri; "sandbox::IsV4PrinterDriver"
0x14007413d  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140074142  jmp     short loc_140074177
0x140074144  mov     rcx, cs:WPP_GLOBAL_Control
0x14007414b  lea     rax, WPP_GLOBAL_Control
0x140074152  cmp     rcx, rax
0x140074155  jz      short loc_140074177
0x140074157  test    byte ptr [rcx+1Ch], 1
0x14007415b  jz      short loc_140074177
0x14007415d  mov     rcx, [rcx+10h]
0x140074161  mov     edx, 0Ah
0x140074166  movzx   r8d, bl
0x14007416a  mov     r9, rdi
0x14007416d  mov     dword ptr [rsp+38h+phkResult], r8d
0x140074172  call    WPP_SF_SD
0x140074177  mov     al, bl
0x140074179  mov     rbx, [rsp+38h+arg_0]
0x14007417e  add     rsp, 30h
0x140074182  pop     rdi
0x140074183  retn
```
