# SslInitSystemMapper(void)

- ea: `0x18004cf18`
- end: `0x18004d0c3`
- name: `?SslInitSystemMapper@@YAKXZ`
- size: `427`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025c38`

## callees

- `0x18004cf18`
- `0x1800597b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004d049`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004d049`
- `ntdll!RtlGetNtProductType` at `0x18004d087`
- `ntdll!RtlGetNtProductType` at `0x18004d087`
- `ntdll!RtlCopySid` at `0x18004d077`
- `ntdll!RtlCopySid` at `0x18004d077`
- `ntdll!RtlLengthSid` at `0x18004d038`
- `ntdll!RtlLengthSid` at `0x18004d038`
- `ntdll!RtlSubAuthoritySid` at `0x18004d016`
- `ntdll!RtlSubAuthoritySid` at `0x18004d028`
- `ntdll!RtlSubAuthoritySid` at `0x18004d016`
- `ntdll!RtlSubAuthoritySid` at `0x18004d028`
- `ntdll!RtlInitializeSid` at `0x18004d00a`
- `ntdll!RtlInitializeSid` at `0x18004d00a`
- `ntdll!RtlInitString` at `0x18004cf90`
- `ntdll!RtlInitString` at `0x18004cfbd`
- `ntdll!RtlInitString` at `0x18004cf90`
- `ntdll!RtlInitString` at `0x18004cfbd`
- `ntdll!RtlNtStatusToDosError` at `0x18004cf7a`
- `ntdll!RtlNtStatusToDosError` at `0x18004cf7a`
- `SspiCli!LsaRegisterLogonProcess` at `0x18004cf6e`
- `SspiCli!LsaRegisterLogonProcess` at `0x18004cf6e`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18004cfa8`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18004cfd5`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18004cfa8`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18004cfd5`

## pseudocode

```c
ULONG SslInitSystemMapper(void)
{
  int v0; // eax
  BOOL v2; // ebx
  ULONG v3; // edi
  struct _TOKEN_GROUPS *v4; // rax
  _NT_PRODUCT_TYPE ProductType; // [rsp+20h] [rbp-29h] BYREF
  ULONG SecurityMode; // [rsp+24h] [rbp-25h] BYREF
  struct _STRING DestinationString; // [rsp+28h] [rbp-21h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+38h] [rbp-11h] BYREF
  _BYTE Sid[80]; // [rsp+40h] [rbp-9h] BYREF

  DestinationString = 0;
  SecurityMode = 0;
  ProductType = 0;
  if ( !SslLogonHandle )
  {
    v0 = LsaRegisterLogonProcess(&SslPackageNameA, &SslLogonHandle, &SecurityMode);
    if ( v0 < 0 )
      return RtlNtStatusToDosError(v0);
  }
  RtlInitString(&DestinationString, "Kerberos");
  v0 = LsaLookupAuthenticationPackage(SslLogonHandle, (PLSA_STRING)&DestinationString, &SslKerberosPackageId);
  if ( v0 < 0 )
    return RtlNtStatusToDosError(v0);
  RtlInitString(&DestinationString, "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0");
  v0 = LsaLookupAuthenticationPackage(SslLogonHandle, (PLSA_STRING)&DestinationString, &SslMsvPackageId);
  if ( v0 < 0 )
    return RtlNtStatusToDosError(v0);
  v2 = 1;
  if ( !SslPackageSid )
  {
    *(_DWORD *)IdentifierAuthority.Value = 0;
    *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
    RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
    *RtlSubAuthoritySid(Sid, 0) = 64;
    *RtlSubAuthoritySid(Sid, 1u) = 14;
    v3 = RtlLengthSid(Sid);
    v4 = (struct _TOKEN_GROUPS *)LocalAlloc(0x40u, v3 + 24LL);
    SslPackageSid = v4;
    if ( !v4 )
      return 14;
    v4->GroupCount = 1;
    v4->Groups[0].Sid = &v4[1];
    v4->Groups[0].Attributes = 7;
    RtlCopySid(v3, &v4[1], Sid);
  }
  g_SslS4U2SelfInitialized = 1;
  if ( RtlGetNtProductType(&ProductType) )
    v2 = ProductType == NtProductLanManNt;
  fUseLocalMapping = v2;
  return 0;
}

```

## disassembly

```asm
0x18004cf18  mov     [rsp-8+arg_0], rbx
0x18004cf1d  mov     [rsp-8+arg_8], rdi
0x18004cf22  push    rbp
0x18004cf23  lea     rbp, [rsp-57h]
0x18004cf28  sub     rsp, 0A0h
0x18004cf2f  mov     rax, cs:__security_cookie
0x18004cf36  xor     rax, rsp
0x18004cf39  mov     [rbp+57h+var_10], rax
0x18004cf3d  cmp     cs:?SslLogonHandle@@3PEAXEA, 0; void * SslLogonHandle
0x18004cf45  xorps   xmm0, xmm0
0x18004cf48  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18004cf4c  mov     [rbp+57h+SecurityMode], 0
0x18004cf53  mov     [rbp+57h+ProductType], 0
0x18004cf5a  jnz     short loc_18004CF85
0x18004cf5c  lea     r8, [rbp+57h+SecurityMode]; SecurityMode
0x18004cf60  lea     rdx, ?SslLogonHandle@@3PEAXEA; LsaHandle
0x18004cf67  lea     rcx, ?SslPackageNameA@@3U_STRING@@A; LogonProcessName
0x18004cf6e  call    cs:__imp_LsaRegisterLogonProcess
0x18004cf74  test    eax, eax
0x18004cf76  jns     short loc_18004CF85
0x18004cf78  mov     ecx, eax; Status
0x18004cf7a  call    cs:__imp_RtlNtStatusToDosError
0x18004cf80  jmp     loc_18004D0A2
0x18004cf85  lea     rdx, aKerberos; "Kerberos"
0x18004cf8c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18004cf90  call    cs:__imp_RtlInitString
0x18004cf96  mov     rcx, cs:?SslLogonHandle@@3PEAXEA; LsaHandle
0x18004cf9d  lea     r8, ?SslKerberosPackageId@@3KA; AuthenticationPackage
0x18004cfa4  lea     rdx, [rbp+57h+DestinationString]; PackageName
0x18004cfa8  call    cs:__imp_LsaLookupAuthenticationPackage
0x18004cfae  test    eax, eax
0x18004cfb0  js      short loc_18004CF78
0x18004cfb2  lea     rdx, aMicrosoftAuthe; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x18004cfb9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18004cfbd  call    cs:__imp_RtlInitString
0x18004cfc3  mov     rcx, cs:?SslLogonHandle@@3PEAXEA; LsaHandle
0x18004cfca  lea     r8, ?SslMsvPackageId@@3KA; AuthenticationPackage
0x18004cfd1  lea     rdx, [rbp+57h+DestinationString]; PackageName
0x18004cfd5  call    cs:__imp_LsaLookupAuthenticationPackage
0x18004cfdb  test    eax, eax
0x18004cfdd  js      short loc_18004CF78
0x18004cfdf  cmp     cs:?SslPackageSid@@3PEAU_TOKEN_GROUPS@@EA, 0; _TOKEN_GROUPS * SslPackageSid
0x18004cfe7  mov     ebx, 1
0x18004cfec  jnz     loc_18004D07D
0x18004cff2  mov     r8b, 2; SubAuthorityCount
0x18004cff5  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], 0
0x18004cffc  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18004d000  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18004d006  lea     rcx, [rbp+57h+Sid]; Sid
0x18004d00a  call    cs:__imp_RtlInitializeSid
0x18004d010  xor     edx, edx; SubAuthority
0x18004d012  lea     rcx, [rbp+57h+Sid]; Sid
0x18004d016  call    cs:__imp_RtlSubAuthoritySid
0x18004d01c  mov     edx, ebx; SubAuthority
0x18004d01e  lea     rcx, [rbp+57h+Sid]; Sid
0x18004d022  mov     dword ptr [rax], 40h ; '@'
0x18004d028  call    cs:__imp_RtlSubAuthoritySid
0x18004d02e  lea     rcx, [rbp+57h+Sid]; Sid
0x18004d032  mov     dword ptr [rax], 0Eh
0x18004d038  call    cs:__imp_RtlLengthSid
0x18004d03e  mov     edx, eax
0x18004d040  lea     ecx, [rbx+3Fh]; uFlags
0x18004d043  add     rdx, 18h; uBytes
0x18004d047  mov     edi, eax
0x18004d049  call    cs:__imp_LocalAlloc
0x18004d04f  mov     cs:?SslPackageSid@@3PEAU_TOKEN_GROUPS@@EA, rax; _TOKEN_GROUPS * SslPackageSid
0x18004d056  test    rax, rax
0x18004d059  jnz     short loc_18004D060
0x18004d05b  lea     eax, [rbx+0Dh]
0x18004d05e  jmp     short loc_18004D0A2
0x18004d060  lea     rdx, [rax+18h]; DestinationSid
0x18004d064  mov     [rax], ebx
0x18004d066  lea     r8, [rbp+57h+Sid]; SourceSid
0x18004d06a  mov     [rax+8], rdx
0x18004d06e  mov     ecx, edi; DestinationSidLength
0x18004d070  mov     dword ptr [rax+10h], 7
0x18004d077  call    cs:__imp_RtlCopySid
0x18004d07d  lea     rcx, [rbp+57h+ProductType]; ProductType
0x18004d081  mov     cs:?g_SslS4U2SelfInitialized@@3HA, ebx; int g_SslS4U2SelfInitialized
0x18004d087  call    cs:__imp_RtlGetNtProductType
0x18004d08d  test    al, al
0x18004d08f  jz      short loc_18004D09A
0x18004d091  xor     ebx, ebx
0x18004d093  cmp     [rbp+57h+ProductType], 2
0x18004d097  setz    bl
0x18004d09a  mov     cs:?fUseLocalMapping@@3HA, ebx; int fUseLocalMapping
0x18004d0a0  xor     eax, eax
0x18004d0a2  mov     rcx, [rbp+57h+var_10]
0x18004d0a6  xor     rcx, rsp; StackCookie
0x18004d0a9  call    __security_check_cookie
0x18004d0ae  lea     r11, [rsp+0A0h+var_s0]
0x18004d0b6  mov     rbx, [r11+10h]
0x18004d0ba  mov     rdi, [r11+18h]
0x18004d0be  mov     rsp, r11
0x18004d0c1  pop     rbp
0x18004d0c2  retn
```
