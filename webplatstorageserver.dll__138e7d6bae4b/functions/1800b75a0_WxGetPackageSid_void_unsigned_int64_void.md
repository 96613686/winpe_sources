# WxGetPackageSid(void *,unsigned __int64,void *)

- ea: `0x1800b75a0`
- end: `0x1800b7732`
- name: `?WxGetPackageSid@@YAJPEAX_K0@Z`
- size: `402`
- prototype: `__int64 __fastcall(HANDLE token, unsigned __int64, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002a210`

## callees

- `0x180080fb0`
- `0x18008cae0`
- `0x1800b75a0`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800b7619`
- `ntdll!NtQueryInformationToken` at `0x1800b7619`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x1800b767d`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x1800b767d`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x1800b7645`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x1800b7645`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x1800b7708`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x1800b7708`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackageSecurityContext` at `0x1800b76a8`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackageSecurityContext` at `0x1800b76a8`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackageSecurityProperty` at `0x1800b76e1`
- `api-ms-win-appmodel-runtime-internal-l1-1-0!GetPackageSecurityProperty` at `0x1800b76e1`

## pseudocode

```c
__int64 __fastcall WxGetPackageSid(HANDLE token, __int64 a2, void *a3)
{
  NTSTATUS v5; // eax
  signed int v6; // ebx
  LONG PackageFullNameFromToken; // eax
  LONG v8; // eax
  int PackageSecurityContext; // eax
  int PackageSecurityProperty; // eax
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+48h] [rbp-B8h] BYREF
  ULONG ReturnLength; // [rsp+4Ch] [rbp-B4h] BYREF
  UINT32 packageFullNameLength[4]; // [rsp+50h] [rbp-B0h] BYREF
  PSID TokenInformation[12]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR packageFullName[128]; // [rsp+C0h] [rbp-40h] BYREF

  ReturnLength = 0;
  packageFullNameLength[0] = 128;
  packageInfoReference = 0;
  v13 = 0;
  v14 = 0;
  v5 = NtQueryInformationToken(token, TokenUser, TokenInformation, 0x54u, &ReturnLength);
  v6 = HRESULT_FROM_NTSTATUS(v5);
  if ( v6 >= 0 )
  {
    PackageFullNameFromToken = GetPackageFullNameFromToken(token, packageFullNameLength, packageFullName);
    v6 = PackageFullNameFromToken;
    if ( PackageFullNameFromToken > 0 )
      v6 = (unsigned __int16)PackageFullNameFromToken | 0x80070000;
    if ( v6 >= 0 )
    {
      v8 = OpenPackageInfoByFullNameForUser(TokenInformation[0], packageFullName, 0, &packageInfoReference);
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      if ( v6 >= 0 )
      {
        PackageSecurityContext = GetPackageSecurityContext(packageInfoReference, 0, &v13);
        v6 = PackageSecurityContext;
        if ( PackageSecurityContext > 0 )
          v6 = (unsigned __int16)PackageSecurityContext | 0x80070000;
        if ( v6 >= 0 )
        {
          v14 = 68;
          PackageSecurityProperty = GetPackageSecurityProperty(v13, 2, &v14, a3);
          v6 = PackageSecurityProperty;
          if ( PackageSecurityProperty > 0 )
            v6 = (unsigned __int16)PackageSecurityProperty | 0x80070000;
        }
      }
    }
  }
  if ( packageInfoReference )
    ClosePackageInfo(packageInfoReference);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800b75a0  mov     [rsp-8+arg_8], rbx
0x1800b75a5  push    rbp
0x1800b75a6  push    rsi
0x1800b75a7  push    rdi
0x1800b75a8  lea     rbp, [rsp-0D0h]
0x1800b75b0  sub     rsp, 1D0h
0x1800b75b7  mov     rax, cs:__security_cookie
0x1800b75be  xor     rax, rsp
0x1800b75c1  mov     [rbp+0E0h+var_20], rax
0x1800b75c8  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1800b75ce  mov     [rsp+1E0h+var_1AC], 0
0x1800b75d6  mov     rsi, r8
0x1800b75d9  mov     [rsp+1E0h+var_194], 0
0x1800b75e1  lea     rax, [rsp+1E0h+var_194]
0x1800b75e6  mov     [rsp+1E0h+packageFullNameLength], 80h
0x1800b75ee  lea     r8, [rsp+1E0h+TokenInformation]; TokenInformation
0x1800b75f3  mov     [rsp+1E0h+packageInfoReference], 0
0x1800b75fc  lea     edx, [r9-53h]; TokenInformationClass
0x1800b7600  mov     [rsp+1E0h+var_1A0], 0
0x1800b7609  mov     rdi, rcx
0x1800b760c  mov     [rsp+1E0h+var_198], 0
0x1800b7614  mov     [rsp+1E0h+ReturnLength], rax; ReturnLength
0x1800b7619  call    cs:__imp_NtQueryInformationToken
0x1800b761f  mov     ecx, eax; int
0x1800b7621  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x1800b7626  mov     ebx, eax
0x1800b7628  test    eax, eax
0x1800b762a  jns     short loc_1800B7639
0x1800b762c  mov     [rsp+1E0h+var_1AC], 7Ch ; '|'
0x1800b7634  jmp     loc_1800B76FE
0x1800b7639  lea     r8, [rbp+0E0h+packageFullName]; packageFullName
0x1800b763d  mov     rcx, rdi; token
0x1800b7640  lea     rdx, [rsp+1E0h+packageFullNameLength]; packageFullNameLength
0x1800b7645  call    cs:__imp_GetPackageFullNameFromToken
0x1800b764b  mov     ebx, eax
0x1800b764d  mov     edi, 80070000h
0x1800b7652  test    eax, eax
0x1800b7654  jle     short loc_1800B765B
0x1800b7656  movzx   ebx, ax
0x1800b7659  or      ebx, edi
0x1800b765b  test    ebx, ebx
0x1800b765d  jns     short loc_1800B766C
0x1800b765f  mov     [rsp+1E0h+var_1AC], 7Dh ; '}'
0x1800b7667  jmp     loc_1800B76FE
0x1800b766c  mov     rcx, [rsp+1E0h+TokenInformation]; userSid
0x1800b7671  lea     r9, [rsp+1E0h+packageInfoReference]; packageInfoReference
0x1800b7676  xor     r8d, r8d; reserved
0x1800b7679  lea     rdx, [rbp+0E0h+packageFullName]; packageFullName
0x1800b767d  call    cs:__imp_OpenPackageInfoByFullNameForUser
0x1800b7683  mov     ebx, eax
0x1800b7685  test    eax, eax
0x1800b7687  jle     short loc_1800B768E
0x1800b7689  movzx   ebx, ax
0x1800b768c  or      ebx, edi
0x1800b768e  test    ebx, ebx
0x1800b7690  jns     short loc_1800B769C
0x1800b7692  mov     [rsp+1E0h+var_1AC], 7Fh
0x1800b769a  jmp     short loc_1800B76FE
0x1800b769c  mov     rcx, [rsp+1E0h+packageInfoReference]
0x1800b76a1  lea     r8, [rsp+1E0h+var_1A0]
0x1800b76a6  xor     edx, edx
0x1800b76a8  call    cs:__imp_GetPackageSecurityContext
0x1800b76ae  mov     ebx, eax
0x1800b76b0  test    eax, eax
0x1800b76b2  jle     short loc_1800B76B9
0x1800b76b4  movzx   ebx, ax
0x1800b76b7  or      ebx, edi
0x1800b76b9  test    ebx, ebx
0x1800b76bb  jns     short loc_1800B76C7
0x1800b76bd  mov     [rsp+1E0h+var_1AC], 80h
0x1800b76c5  jmp     short loc_1800B76FE
0x1800b76c7  mov     rcx, [rsp+1E0h+var_1A0]
0x1800b76cc  lea     r8, [rsp+1E0h+var_198]
0x1800b76d1  mov     r9, rsi
0x1800b76d4  mov     [rsp+1E0h+var_198], 44h ; 'D'
0x1800b76dc  mov     edx, 2
0x1800b76e1  call    cs:__imp_GetPackageSecurityProperty
0x1800b76e7  mov     ebx, eax
0x1800b76e9  test    eax, eax
0x1800b76eb  jle     short loc_1800B76F2
0x1800b76ed  movzx   ebx, ax
0x1800b76f0  or      ebx, edi
0x1800b76f2  test    ebx, ebx
0x1800b76f4  jns     short loc_1800B76FE
0x1800b76f6  mov     [rsp+1E0h+var_1AC], 83h
0x1800b76fe  mov     rcx, [rsp+1E0h+packageInfoReference]; packageInfoReference
0x1800b7703  test    rcx, rcx
0x1800b7706  jz      short loc_1800B770E
0x1800b7708  call    cs:__imp_ClosePackageInfo
0x1800b770e  mov     eax, ebx
0x1800b7710  mov     rcx, [rbp+0E0h+var_20]
0x1800b7717  xor     rcx, rsp; StackCookie
0x1800b771a  call    __security_check_cookie
0x1800b771f  mov     rbx, [rsp+1E0h+arg_8]
0x1800b7727  add     rsp, 1D0h
0x1800b772e  pop     rdi
0x1800b772f  pop     rsi
0x1800b7730  pop     rbp
0x1800b7731  retn
```
