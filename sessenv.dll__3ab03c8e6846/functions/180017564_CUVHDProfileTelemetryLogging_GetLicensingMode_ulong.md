# CUVHDProfileTelemetryLogging::GetLicensingMode(ulong *)

- ea: `0x180017564`
- end: `0x180017669`
- name: `?GetLicensingMode@CUVHDProfileTelemetryLogging@@CAJPEAK@Z`
- size: `261`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004620`
- `0x1800337b0`

## callees

- `0x180003f30`
- `0x180017564`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800175af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800175af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017610`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017610`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017659`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017659`

## string_xrefs

- `0x1800175c8`: `RegOpenKeyEx REG_CONTROL_TSERVER failed failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUVHDProfileTelemetryLogging::GetLicensingMode(unsigned int *a1)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\RCM\\Licensing Core",
         0,
         0x20019u,
         &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    cbData = 4;
    v4 = RegQueryValueExW(hKey, L"LicensingMode", 0, &Type, (LPBYTE)&Data, &cbData);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 >= 0 )
    {
      if ( Type == 4 )
      {
        if ( a1 )
          *a1 = Data;
      }
      else
      {
        v3 = -2147024809;
        _DbgPrintMessage(
          8,
          "REG_LICENSING_MODE_VALUE not REG_DWORD failed: 0x%x in %s",
          2147942487LL,
          "CUVHDProfileTelemetryLogging::GetLicensingMode");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "RegQueryValueEx REG_LICENSING_MODE_VALUE failed failed: 0x%x in %s",
        (unsigned int)v3,
        "CUVHDProfileTelemetryLogging::GetLicensingMode");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "RegOpenKeyEx REG_CONTROL_TSERVER failed failed: 0x%x in %s",
      (unsigned int)v3,
      "CUVHDProfileTelemetryLogging::GetLicensingMode");
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180017564  push    rbp
0x180017566  push    rbx
0x180017567  push    rdi
0x180017568  mov     rbp, rsp
0x18001756b  sub     rsp, 40h
0x18001756f  mov     rdi, rcx
0x180017572  mov     [rbp+hKey], 0
0x18001757a  lea     rax, [rbp+hKey]
0x18001757e  mov     [rbp+Type], 0
0x180017585  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001758c  mov     [rsp+40h+phkResult], rax; phkResult
0x180017591  mov     r9d, 20019h; samDesired
0x180017597  mov     [rbp+cbData], 0
0x18001759e  xor     r8d, r8d; ulOptions
0x1800175a1  mov     [rbp+Data], 0
0x1800175a8  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Ter"...
0x1800175af  call    cs:__imp_RegOpenKeyExW
0x1800175b5  mov     ebx, eax
0x1800175b7  test    eax, eax
0x1800175b9  jle     short loc_1800175C4
0x1800175bb  movzx   ebx, ax
0x1800175be  or      ebx, 80070000h
0x1800175c4  test    ebx, ebx
0x1800175c6  jns     short loc_1800175E5
0x1800175c8  lea     rdx, aRegopenkeyexRe_0; "RegOpenKeyEx REG_CONTROL_TSERVER failed"...
0x1800175cf  lea     r9, aCuvhdprofilete; "CUVHDProfileTelemetryLogging::GetLicens"...
0x1800175d6  mov     r8d, ebx
0x1800175d9  mov     ecx, 8; int
0x1800175de  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800175e3  jmp     short loc_180017650
0x1800175e5  mov     rcx, [rbp+hKey]; hKey
0x1800175e9  lea     rax, [rbp+cbData]
0x1800175ed  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800175f2  lea     r9, [rbp+Type]; lpType
0x1800175f6  lea     rax, [rbp+Data]
0x1800175fa  mov     [rbp+cbData], 4
0x180017601  xor     r8d, r8d; lpReserved
0x180017604  mov     [rsp+40h+phkResult], rax; lpData
0x180017609  lea     rdx, aLicensingmode; "LicensingMode"
0x180017610  call    cs:__imp_RegQueryValueExW
0x180017616  mov     ebx, eax
0x180017618  test    eax, eax
0x18001761a  jle     short loc_180017625
0x18001761c  movzx   ebx, ax
0x18001761f  or      ebx, 80070000h
0x180017625  test    ebx, ebx
0x180017627  jns     short loc_180017632
0x180017629  lea     rdx, aRegqueryvaluee_6; "RegQueryValueEx REG_LICENSING_MODE_VALU"...
0x180017630  jmp     short loc_1800175CF
0x180017632  cmp     [rbp+Type], 4
0x180017636  jz      short loc_180017646
0x180017638  mov     ebx, 80070057h
0x18001763d  lea     rdx, aRegLicensingMo; "REG_LICENSING_MODE_VALUE not REG_DWORD "...
0x180017644  jmp     short loc_1800175CF
0x180017646  test    rdi, rdi
0x180017649  jz      short loc_180017650
0x18001764b  mov     ecx, [rbp+Data]
0x18001764e  mov     [rdi], ecx
0x180017650  mov     rcx, [rbp+hKey]; hKey
0x180017654  test    rcx, rcx
0x180017657  jz      short loc_18001765F
0x180017659  call    cs:__imp_RegCloseKey
0x18001765f  mov     eax, ebx
0x180017661  add     rsp, 40h
0x180017665  pop     rdi
0x180017666  pop     rbx
0x180017667  pop     rbp
0x180017668  retn
```
