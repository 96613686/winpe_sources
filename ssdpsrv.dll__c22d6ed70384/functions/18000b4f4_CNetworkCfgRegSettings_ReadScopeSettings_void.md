# CNetworkCfgRegSettings::ReadScopeSettings(void)

- ea: `0x18000b4f4`
- end: `0x18000b5c1`
- name: `?ReadScopeSettings@CNetworkCfgRegSettings@@QEAAXXZ`
- size: `205`
- prototype: `void __fastcall(BYTE *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000a768`

## callees

- `0x18000b4f4`
- `0x180025e88`
- `0x180028000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b5b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b5b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000b59d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000b59d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000b535`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000b535`

## string_xrefs

- `0x18000b527`: `System\CurrentControlSet\Services\SSDPSRV\Parameters`

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
0x18000b4f4  mov     rax, rsp
0x18000b4f7  push    rbx
0x18000b4f8  sub     rsp, 30h
0x18000b4fc  mov     qword ptr [rax+20h], 0
0x18000b504  mov     rbx, rcx
0x18000b507  mov     dword ptr [rax+18h], 0
0x18000b50e  mov     r9d, 20019h; samDesired
0x18000b514  mov     dword ptr [rax+10h], 4
0x18000b51b  lea     rax, [rax+20h]
0x18000b51f  xor     r8d, r8d; ulOptions
0x18000b522  mov     [rsp+38h+phkResult], rax; phkResult
0x18000b527  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\SS"...
0x18000b52e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b535  call    cs:__imp_RegOpenKeyExA
0x18000b53b  test    eax, eax
0x18000b53d  jz      short loc_18000B572
0x18000b53f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b546  lea     rax, WPP_GLOBAL_Control
0x18000b54d  cmp     rcx, rax
0x18000b550  jz      short loc_18000B5A3
0x18000b552  test    dword ptr [rcx+1Ch], 200h
0x18000b559  jz      short loc_18000B5A3
0x18000b55b  mov     rcx, [rcx+10h]
0x18000b55f  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18000b566  mov     edx, 0Ch
0x18000b56b  call    WPP_SF_
0x18000b570  jmp     short loc_18000B5A3
0x18000b572  mov     rcx, [rsp+38h+hKey]; hKey
0x18000b577  lea     rax, [rsp+38h+cbData]
0x18000b57c  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000b581  lea     r9, [rsp+38h+Type]; lpType
0x18000b586  xor     r8d, r8d; lpReserved
0x18000b589  mov     [rsp+38h+phkResult], rbx; lpData
0x18000b58e  lea     rdx, aAdditionalipv6; "AdditionalIPv6Scope"
0x18000b595  mov     [rsp+38h+cbData], 4
0x18000b59d  call    cs:__imp_RegQueryValueExA
0x18000b5a3  mov     rcx, rbx; this
0x18000b5a6  call    ?ValidateAndCorrectSettings@CNetworkCfgRegSettings@@AEAAXXZ; CNetworkCfgRegSettings::ValidateAndCorrectSettings(void)
0x18000b5ab  mov     rcx, [rsp+38h+hKey]; hKey
0x18000b5b0  test    rcx, rcx
0x18000b5b3  jz      short loc_18000B5BB
0x18000b5b5  call    cs:__imp_RegCloseKey
0x18000b5bb  add     rsp, 30h
0x18000b5bf  pop     rbx
0x18000b5c0  retn
```
