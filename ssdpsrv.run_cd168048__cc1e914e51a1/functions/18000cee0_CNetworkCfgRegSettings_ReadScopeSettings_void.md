# CNetworkCfgRegSettings::ReadScopeSettings(void)

- ea: `0x18000cee0`
- end: `0x18000cfc0`
- name: `?ReadScopeSettings@CNetworkCfgRegSettings@@QEAAXXZ`
- size: `224`
- prototype: `void __fastcall(CNetworkCfgRegSettings *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000c078`

## callees

- `0x18000cee0`
- `0x180027bac`
- `0x180029df0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cfad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cfad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000cf8f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000cf8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000cf21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000cf21`

## string_xrefs

- `0x18000cf13`: `System\CurrentControlSet\Services\SSDPSRV\Parameters`

## pseudocode

```c
void __fastcall CNetworkCfgRegSettings::ReadScopeSettings(BYTE *this)
{
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 4;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\SSDPSRV\\Parameters", 0, 0x20019u, &hKey) )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids);
  }
  else
  {
    cbData = 4;
    RegQueryValueExA(hKey, "AdditionalIPv6Scope", 0, &Type, this, &cbData);
  }
  CNetworkCfgRegSettings::ValidateAndCorrectSettings((CNetworkCfgRegSettings *)this);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18000cee0  mov     rax, rsp
0x18000cee3  push    rbx
0x18000cee4  sub     rsp, 30h
0x18000cee8  mov     qword ptr [rax+20h], 0
0x18000cef0  mov     rbx, rcx
0x18000cef3  mov     dword ptr [rax+18h], 0
0x18000cefa  mov     r9d, 20019h; samDesired
0x18000cf00  mov     dword ptr [rax+10h], 4
0x18000cf07  lea     rax, [rax+20h]
0x18000cf0b  xor     r8d, r8d; ulOptions
0x18000cf0e  mov     [rsp+38h+phkResult], rax; phkResult
0x18000cf13  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\SS"...
0x18000cf1a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000cf21  call    cs:__imp_RegOpenKeyExA
0x18000cf28  nop     dword ptr [rax+rax+00h]
0x18000cf2d  test    eax, eax
0x18000cf2f  jz      short loc_18000CF64
0x18000cf31  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf38  lea     rax, WPP_GLOBAL_Control
0x18000cf3f  cmp     rcx, rax
0x18000cf42  jz      short loc_18000CF9B
0x18000cf44  test    dword ptr [rcx+1Ch], 200h
0x18000cf4b  jz      short loc_18000CF9B
0x18000cf4d  mov     rcx, [rcx+10h]
0x18000cf51  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18000cf58  mov     edx, 0Ch
0x18000cf5d  call    WPP_SF_
0x18000cf62  jmp     short loc_18000CF9B
0x18000cf64  mov     rcx, [rsp+38h+hKey]; hKey
0x18000cf69  lea     rax, [rsp+38h+cbData]
0x18000cf6e  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000cf73  lea     r9, [rsp+38h+Type]; lpType
0x18000cf78  xor     r8d, r8d; lpReserved
0x18000cf7b  mov     [rsp+38h+phkResult], rbx; lpData
0x18000cf80  lea     rdx, aAdditionalipv6; "AdditionalIPv6Scope"
0x18000cf87  mov     [rsp+38h+cbData], 4
0x18000cf8f  call    cs:__imp_RegQueryValueExA
0x18000cf96  nop     dword ptr [rax+rax+00h]
0x18000cf9b  mov     rcx, rbx; this
0x18000cf9e  call    ?ValidateAndCorrectSettings@CNetworkCfgRegSettings@@AEAAXXZ; CNetworkCfgRegSettings::ValidateAndCorrectSettings(void)
0x18000cfa3  mov     rcx, [rsp+38h+hKey]; hKey
0x18000cfa8  test    rcx, rcx
0x18000cfab  jz      short loc_18000CFB9
0x18000cfad  call    cs:__imp_RegCloseKey
0x18000cfb4  nop     dword ptr [rax+rax+00h]
0x18000cfb9  add     rsp, 30h
0x18000cfbd  pop     rbx
0x18000cfbe  retn
```
