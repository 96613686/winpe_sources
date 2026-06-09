# sandbox::IsV4PrinterDriver(ushort const *)

- ea: `0x14007b1d4`
- end: `0x14007b2e1`
- name: `?IsV4PrinterDriver@sandbox@@YA_NPEBG@Z`
- size: `269`
- prototype: `bool __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14007ad40`

## callees

- `0x14000cbf8`
- `0x1400123c0`
- `0x14007a128`
- `0x14007b1d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007b20c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007b240`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007b20c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007b240`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007b257`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007b268`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007b257`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007b268`

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
0x14007b1d4  mov     r11, rsp
0x14007b1d7  mov     [r11+8], rbx
0x14007b1db  push    rdi
0x14007b1dc  sub     rsp, 30h
0x14007b1e0  mov     rdi, rcx
0x14007b1e3  mov     qword ptr [r11+10h], 0
0x14007b1eb  lea     rax, [r11+10h]
0x14007b1ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14007b1f6  mov     r9d, 20019h; samDesired
0x14007b1fc  mov     [r11-18h], rax
0x14007b200  xor     r8d, r8d; ulOptions
0x14007b203  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Pri"...
0x14007b20a  xor     bl, bl
0x14007b20c  call    cs:__imp_RegOpenKeyExW
0x14007b213  nop     dword ptr [rax+rax+00h]
0x14007b218  test    eax, eax
0x14007b21a  jnz     short loc_14007B274
0x14007b21c  mov     rcx, [rsp+38h+hKey]; hKey
0x14007b221  lea     rax, [rsp+38h+arg_10]
0x14007b226  mov     r9d, 20019h; samDesired
0x14007b22c  mov     [rsp+38h+phkResult], rax; phkResult
0x14007b231  xor     r8d, r8d; ulOptions
0x14007b234  mov     [rsp+38h+arg_10], 0
0x14007b23d  mov     rdx, rdi; lpSubKey
0x14007b240  call    cs:__imp_RegOpenKeyExW
0x14007b247  nop     dword ptr [rax+rax+00h]
0x14007b24c  test    eax, eax
0x14007b24e  jnz     short loc_14007B263
0x14007b250  mov     rcx, [rsp+38h+arg_10]; hKey
0x14007b255  mov     bl, 1
0x14007b257  call    cs:__imp_RegCloseKey
0x14007b25e  nop     dword ptr [rax+rax+00h]
0x14007b263  mov     rcx, [rsp+38h+hKey]; hKey
0x14007b268  call    cs:__imp_RegCloseKey
0x14007b26f  nop     dword ptr [rax+rax+00h]
0x14007b274  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x14007b27b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x14007b280  test    al, al
0x14007b282  jz      short loc_14007B2A0
0x14007b284  movzx   r9d, bl
0x14007b288  lea     rdx, aPrinterDriverW; "Printer driver %ws is v4 %u"
0x14007b28f  mov     r8, rdi
0x14007b292  lea     rcx, aSandboxIsv4pri; "sandbox::IsV4PrinterDriver"
0x14007b299  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14007b29e  jmp     short loc_14007B2D3
0x14007b2a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b2a7  lea     rax, WPP_GLOBAL_Control
0x14007b2ae  cmp     rcx, rax
0x14007b2b1  jz      short loc_14007B2D3
0x14007b2b3  test    byte ptr [rcx+1Ch], 1
0x14007b2b7  jz      short loc_14007B2D3
0x14007b2b9  mov     rcx, [rcx+10h]
0x14007b2bd  mov     edx, 0Ah
0x14007b2c2  movzx   r8d, bl
0x14007b2c6  mov     r9, rdi
0x14007b2c9  mov     dword ptr [rsp+38h+phkResult], r8d
0x14007b2ce  call    WPP_SF_SD
0x14007b2d3  mov     al, bl
0x14007b2d5  mov     rbx, [rsp+38h+arg_0]
0x14007b2da  add     rsp, 30h
0x14007b2de  pop     rdi
0x14007b2df  retn
```
