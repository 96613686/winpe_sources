# WsInitializeLsa

- ea: `0x180006964`
- end: `0x180006a91`
- name: `WsInitializeLsa`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006a98`

## callees

- `0x180005df0`
- `0x180006964`

## import_xrefs

- `ntdll!RtlInitString` at `0x1800069a1`
- `ntdll!RtlInitString` at `0x1800069a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006a07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006a07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006a72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006a72`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006a48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006a48`
- `SspiCli!LsaConnectUntrusted` at `0x18000697f`
- `SspiCli!LsaConnectUntrusted` at `0x18000697f`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800069bf`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800069bf`

## pseudocode

```c
__int64 WsInitializeLsa()
{
  NTSTATUS v0; // eax
  __int64 v1; // rcx
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  _STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+20h] BYREF

  DestinationString = 0;
  v0 = LsaConnectUntrusted(&LsaHandle);
  if ( v0 >= 0 )
  {
    RtlInitString(&DestinationString, "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0");
    v2 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&DestinationString, &AuthenticationPackage);
    *(_DWORD *)&WsLsaRestrictAnonymous = 0;
    v3 = v2;
    if ( v2 >= 0 )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Lsa", 0, 0x20019u, &hKey) )
      {
        Type = 0;
        cbData = 4;
        if ( RegQueryValueExW(hKey, L"RestrictAnonymous", 0, &Type, &WsLsaRestrictAnonymous, &cbData)
          || Type != 4
          || cbData != 4 )
        {
          *(_DWORD *)&WsLsaRestrictAnonymous = 0;
        }
        RegCloseKey(hKey);
      }
    }
    v1 = v3;
  }
  else
  {
    v1 = (unsigned int)v0;
  }
  return WsMapStatus(v1);
}

```

## disassembly

```asm
0x180006964  mov     [rsp-8+arg_18], rbx
0x180006969  push    rbp
0x18000696a  mov     rbp, rsp
0x18000696d  sub     rsp, 40h
0x180006971  xorps   xmm0, xmm0
0x180006974  lea     rcx, LsaHandle; LsaHandle
0x18000697b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000697f  call    cs:__imp_LsaConnectUntrusted
0x180006986  nop     dword ptr [rax+rax+00h]
0x18000698b  test    eax, eax
0x18000698d  jns     short loc_180006996
0x18000698f  mov     ecx, eax
0x180006991  jmp     loc_180006A80
0x180006996  lea     rdx, SourceString; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x18000699d  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800069a1  call    cs:__imp_RtlInitString
0x1800069a8  nop     dword ptr [rax+rax+00h]
0x1800069ad  mov     rcx, cs:LsaHandle; LsaHandle
0x1800069b4  lea     r8, AuthenticationPackage; AuthenticationPackage
0x1800069bb  lea     rdx, [rbp+DestinationString]; PackageName
0x1800069bf  call    cs:__imp_LsaLookupAuthenticationPackage
0x1800069c6  nop     dword ptr [rax+rax+00h]
0x1800069cb  mov     cs:WsLsaRestrictAnonymous, 0
0x1800069d5  mov     ebx, eax
0x1800069d7  test    eax, eax
0x1800069d9  js      loc_180006A7E
0x1800069df  lea     rax, [rbp+hKey]
0x1800069e3  mov     [rbp+hKey], 0
0x1800069eb  mov     r9d, 20019h; samDesired
0x1800069f1  mov     [rsp+40h+phkResult], rax; phkResult
0x1800069f6  xor     r8d, r8d; ulOptions
0x1800069f9  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Lsa"
0x180006a00  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006a07  call    cs:__imp_RegOpenKeyExW
0x180006a0e  nop     dword ptr [rax+rax+00h]
0x180006a13  test    eax, eax
0x180006a15  jnz     short loc_180006A7E
0x180006a17  mov     rcx, [rbp+hKey]; hKey
0x180006a1b  lea     r9, [rbp+Type]; lpType
0x180006a1f  mov     [rbp+Type], eax
0x180006a22  lea     rdx, ValueName; "RestrictAnonymous"
0x180006a29  lea     rax, [rbp+cbData]
0x180006a2d  mov     [rbp+cbData], 4
0x180006a34  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180006a39  xor     r8d, r8d; lpReserved
0x180006a3c  lea     rax, WsLsaRestrictAnonymous
0x180006a43  mov     [rsp+40h+phkResult], rax; lpData
0x180006a48  call    cs:__imp_RegQueryValueExW
0x180006a4f  nop     dword ptr [rax+rax+00h]
0x180006a54  test    eax, eax
0x180006a56  jnz     short loc_180006A64
0x180006a58  cmp     [rbp+Type], 4
0x180006a5c  jnz     short loc_180006A64
0x180006a5e  cmp     [rbp+cbData], 4
0x180006a62  jz      short loc_180006A6E
0x180006a64  mov     cs:WsLsaRestrictAnonymous, 0
0x180006a6e  mov     rcx, [rbp+hKey]; hKey
0x180006a72  call    cs:__imp_RegCloseKey
0x180006a79  nop     dword ptr [rax+rax+00h]
0x180006a7e  mov     ecx, ebx
0x180006a80  call    WsMapStatus
0x180006a85  mov     rbx, [rsp+40h+arg_18]
0x180006a8a  add     rsp, 40h
0x180006a8e  pop     rbp
0x180006a8f  retn
```
