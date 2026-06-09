# CSqmSession::SetCommonDataPoints(ulong)

- ea: `0x180014ba4`
- end: `0x180014cd5`
- name: `?SetCommonDataPoints@CSqmSession@@AEAAJK@Z`
- size: `305`
- prototype: `__int64 __fastcall(CSqmSession *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014cdc`

## callees

- `0x180001d60`
- `0x18000291e`
- `0x180014ba4`
- `0x180015214`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180014bbf`
- `KERNEL32!SetLastError` at `0x180014bc7`
- `KERNEL32!SetLastError` at `0x180014bcf`
- `KERNEL32!SetLastError` at `0x180014bd7`
- `KERNEL32!SetLastError` at `0x180014bdf`
- `KERNEL32!SetLastError` at `0x180014be7`
- `KERNEL32!SetLastError` at `0x180014c22`
- `KERNEL32!SetLastError` at `0x180014c2a`
- `KERNEL32!SetLastError` at `0x180014c32`
- `KERNEL32!SetLastError` at `0x180014c3a`
- `KERNEL32!SetLastError` at `0x180014c42`
- `KERNEL32!SetLastError` at `0x180014c80`
- `KERNEL32!SetLastError` at `0x180014c93`
- `KERNEL32!SetLastError` at `0x180014ca1`
- `KERNEL32!SetLastError` at `0x180014cb5`
- `KERNEL32!SetLastError` at `0x180014bbf`
- `KERNEL32!SetLastError` at `0x180014bc7`
- `KERNEL32!SetLastError` at `0x180014bcf`
- `KERNEL32!SetLastError` at `0x180014bd7`
- `KERNEL32!SetLastError` at `0x180014bdf`
- `KERNEL32!SetLastError` at `0x180014be7`
- `KERNEL32!SetLastError` at `0x180014c22`
- `KERNEL32!SetLastError` at `0x180014c2a`
- `KERNEL32!SetLastError` at `0x180014c32`
- `KERNEL32!SetLastError` at `0x180014c3a`
- `KERNEL32!SetLastError` at `0x180014c42`
- `KERNEL32!SetLastError` at `0x180014c80`
- `KERNEL32!SetLastError` at `0x180014c93`
- `KERNEL32!SetLastError` at `0x180014ca1`
- `KERNEL32!SetLastError` at `0x180014cb5`
- `KERNEL32!GetVersionExW` at `0x180014c0c`
- `KERNEL32!GetVersionExW` at `0x180014c0c`
- `KERNEL32!GetProductInfo` at `0x180014c74`
- `KERNEL32!GetProductInfo` at `0x180014c74`
- `SHLWAPI!__imp_IsOS` at `0x180014c8b`
- `SHLWAPI!__imp_IsOS` at `0x180014c8b`
- `POWRPROF!PowerDeterminePlatformRole` at `0x180014c99`
- `POWRPROF!PowerDeterminePlatformRole` at `0x180014c99`

## pseudocode

```c
__int64 __fastcall CSqmSession::SetCommonDataPoints(CSqmSession *this)
{
  DWORD pdwReturnedProductType[4]; // [rsp+30h] [rbp-148h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-138h] BYREF
  unsigned __int16 v4; // [rsp+154h] [rbp-24h]
  unsigned __int16 v5; // [rsp+156h] [rbp-22h]

  SetLastError(0);
  SetLastError(0);
  SetLastError(0);
  SetLastError(0);
  SetLastError(0);
  SetLastError(0);
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
    return 2147500037LL;
  SetLastError(0);
  SetLastError(0);
  SetLastError(0);
  SetLastError(0);
  SetLastError(0);
  pdwReturnedProductType[0] = 0;
  if ( GetProductInfo(
         VersionInformation.dwMajorVersion,
         VersionInformation.dwMinorVersion,
         v4,
         v5,
         pdwReturnedProductType) )
  {
    SetLastError(0);
  }
  IsOS(0x1Cu);
  SetLastError(0);
  PowerDeterminePlatformRole();
  SetLastError(0);
  WmcHashStringToDWORD(L"__BUILDMACHINE__");
  SetLastError(0);
  return 0;
}

```

## disassembly

```asm
0x180014ba4  sub     rsp, 178h
0x180014bab  mov     rax, cs:__security_cookie
0x180014bb2  xor     rax, rsp
0x180014bb5  mov     [rsp+178h+var_18], rax
0x180014bbd  xor     ecx, ecx; dwErrCode
0x180014bbf  call    cs:__imp_SetLastError
0x180014bc5  xor     ecx, ecx; dwErrCode
0x180014bc7  call    cs:__imp_SetLastError
0x180014bcd  xor     ecx, ecx; dwErrCode
0x180014bcf  call    cs:__imp_SetLastError
0x180014bd5  xor     ecx, ecx; dwErrCode
0x180014bd7  call    cs:__imp_SetLastError
0x180014bdd  xor     ecx, ecx; dwErrCode
0x180014bdf  call    cs:__imp_SetLastError
0x180014be5  xor     ecx, ecx; dwErrCode
0x180014be7  call    cs:__imp_SetLastError
0x180014bed  xor     edx, edx; Val
0x180014bef  lea     rcx, [rsp+178h+VersionInformation.dwMajorVersion]; void *
0x180014bf4  mov     r8d, 118h; Size
0x180014bfa  call    memset_0
0x180014bff  lea     rcx, [rsp+178h+VersionInformation]; lpVersionInformation
0x180014c04  mov     [rsp+178h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180014c0c  call    cs:__imp_GetVersionExW
0x180014c12  test    eax, eax
0x180014c14  jnz     short loc_180014C20
0x180014c16  mov     eax, 80004005h
0x180014c1b  jmp     loc_180014CBD
0x180014c20  xor     ecx, ecx; dwErrCode
0x180014c22  call    cs:__imp_SetLastError
0x180014c28  xor     ecx, ecx; dwErrCode
0x180014c2a  call    cs:__imp_SetLastError
0x180014c30  xor     ecx, ecx; dwErrCode
0x180014c32  call    cs:__imp_SetLastError
0x180014c38  xor     ecx, ecx; dwErrCode
0x180014c3a  call    cs:__imp_SetLastError
0x180014c40  xor     ecx, ecx; dwErrCode
0x180014c42  call    cs:__imp_SetLastError
0x180014c48  movzx   r9d, [rsp+178h+var_22]; dwSpMinorVersion
0x180014c51  lea     rax, [rsp+178h+var_148]
0x180014c56  movzx   r8d, [rsp+178h+var_24]; dwSpMajorVersion
0x180014c5f  mov     edx, [rsp+178h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x180014c63  mov     ecx, [rsp+178h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x180014c67  mov     [rsp+178h+pdwReturnedProductType], rax; pdwReturnedProductType
0x180014c6c  mov     [rsp+178h+var_148], 0
0x180014c74  call    cs:__imp_GetProductInfo
0x180014c7a  test    eax, eax
0x180014c7c  jz      short loc_180014C86
0x180014c7e  xor     ecx, ecx; dwErrCode
0x180014c80  call    cs:__imp_SetLastError
0x180014c86  mov     ecx, 1Ch; dwOS
0x180014c8b  call    cs:__imp_IsOS
0x180014c91  xor     ecx, ecx; dwErrCode
0x180014c93  call    cs:__imp_SetLastError
0x180014c99  call    cs:__imp_PowerDeterminePlatformRole
0x180014c9f  xor     ecx, ecx; dwErrCode
0x180014ca1  call    cs:__imp_SetLastError
0x180014ca7  lea     rcx, aBuildmachine; "__BUILDMACHINE__"
0x180014cae  call    ?WmcHashStringToDWORD@@YAKPEBG@Z; WmcHashStringToDWORD(ushort const *)
0x180014cb3  xor     ecx, ecx; dwErrCode
0x180014cb5  call    cs:__imp_SetLastError
0x180014cbb  xor     eax, eax
0x180014cbd  mov     rcx, [rsp+178h+var_18]
0x180014cc5  xor     rcx, rsp; StackCookie
0x180014cc8  call    __security_check_cookie
0x180014ccd  add     rsp, 178h
0x180014cd4  retn
```
