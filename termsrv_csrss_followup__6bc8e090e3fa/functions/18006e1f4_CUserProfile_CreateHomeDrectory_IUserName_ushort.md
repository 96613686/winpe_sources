# CUserProfile::CreateHomeDrectory(IUserName *,ushort *)

- ea: `0x18006e1f4`
- end: `0x18006e3fa`
- name: `?CreateHomeDrectory@CUserProfile@@CAJPEAUIUserName@@PEAG@Z`
- size: `518`
- prototype: `__int64 __fastcall(struct IUserName *, LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006ebdc`

## callees

- `0x180009940`
- `0x180018394`
- `0x18006e1f4`
- `0x1800bf598`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e28b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e28b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e3ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e3ce`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006e27b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006e27b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e3b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e3b9`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18006e30b`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18006e30b`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18006e376`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18006e376`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18006e324`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18006e324`

## string_xrefs

- `0x18006e343`: `SetEntriesInAcl failed: 0x%x in %s`
- `0x18006e39f`: `CUserProfile::CreateHomeDrectory`
- `0x18006e252`: `CImpersonate::ImpersonateUser failed: 0x%x in %s`
- `0x18006e2b9`: `CreateDirectory failed: 0x%x in %s`
- `0x18006e2e1`: `pUserName->GetUserSid failed: 0x%x in %s`
- `0x18006e395`: `SetNamedSecurityInfo failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserProfile::CreateHomeDrectory(struct IUserName *a1, LPWSTR pObjectName)
{
  int v4; // eax
  signed int v5; // ebx
  signed int LastError; // eax
  const char *v7; // rdx
  int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  PACL NewAcl; // [rsp+40h] [rbp-9h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+48h] [rbp-1h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+60h] [rbp+17h] BYREF
  __int16 v15; // [rsp+C0h] [rbp+77h] BYREF
  PSID pSid; // [rsp+C8h] [rbp+7Fh] BYREF

  v15 = 0;
  NewAcl = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  pSid = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v4 = CImpersonate::ImpersonateUser((CImpersonate *)&v15, a1);
  v5 = v4;
  if ( v4 < 0 )
  {
    _DbgPrintMessage(
      8,
      "CImpersonate::ImpersonateUser failed: 0x%x in %s",
      (unsigned int)v4,
      "CUserProfile::CreateHomeDrectory");
    goto LABEL_21;
  }
  SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = 0;
  SecurityAttributes.bInheritHandle = 0;
  if ( !CreateDirectoryW(pObjectName, &SecurityAttributes) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 == -2147024713 )
    {
      v5 = 0;
      goto LABEL_21;
    }
    if ( v5 < 0 )
    {
      v7 = "CreateDirectory failed: 0x%x in %s";
LABEL_20:
      _DbgPrintMessage(8, v7, (unsigned int)v5, "CUserProfile::CreateHomeDrectory");
      goto LABEL_21;
    }
  }
  v8 = (*(__int64 (__fastcall **)(struct IUserName *, PSID *))(*(_QWORD *)a1 + 72LL))(a1, &pSid);
  v5 = v8;
  if ( v8 < 0 )
  {
    _DbgPrintMessage(
      8,
      "pUserName->GetUserSid failed: 0x%x in %s",
      (unsigned int)v8,
      "CUserProfile::CreateHomeDrectory");
    goto LABEL_21;
  }
  pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
  pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
  pListOfExplicitEntries.grfInheritance = 3;
  BuildTrusteeWithSidW(&pListOfExplicitEntries.Trustee, pSid);
  v9 = SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl);
  v5 = v9;
  if ( v9 > 0 )
    v5 = (unsigned __int16)v9 | 0x80070000;
  if ( v5 < 0 )
  {
    v7 = "SetEntriesInAcl failed: 0x%x in %s";
    goto LABEL_20;
  }
  v10 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x20000005u, pSid, 0, NewAcl, 0);
  v5 = v10;
  if ( v10 > 0 )
    v5 = (unsigned __int16)v10 | 0x80070000;
  if ( v5 < 0 )
  {
    v7 = "SetNamedSecurityInfo failed: 0x%x in %s";
    goto LABEL_20;
  }
LABEL_21:
  if ( pSid )
    CoTaskMemFree(pSid);
  if ( NewAcl )
    LocalFree(NewAcl);
  CImpersonate::StopImpersonating((CImpersonate *)&v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006e1f4  mov     [rsp-8+arg_0], rbx
0x18006e1f9  push    rbp
0x18006e1fa  push    rsi
0x18006e1fb  push    rdi
0x18006e1fc  lea     rbp, [rsp-47h]
0x18006e201  sub     rsp, 90h
0x18006e208  mov     rsi, rdx
0x18006e20b  mov     rdi, rcx
0x18006e20e  mov     [rbp+57h+arg_10], 0
0x18006e214  mov     [rbp+57h+NewAcl], 0
0x18006e21c  xorps   xmm0, xmm0
0x18006e21f  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18006e223  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18006e227  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18006e22b  mov     [rbp+57h+pSid], 0
0x18006e233  xor     eax, eax
0x18006e235  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x18006e239  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x18006e23d  mov     rdx, rcx; struct IUserName *
0x18006e240  lea     rcx, [rbp+57h+arg_10]; this
0x18006e244  call    ?ImpersonateUser@CImpersonate@@QEAAJPEAUIUserName@@@Z; CImpersonate::ImpersonateUser(IUserName *)
0x18006e249  mov     ebx, eax
0x18006e24b  test    eax, eax
0x18006e24d  jns     short loc_18006E25E
0x18006e24f  mov     r8d, eax
0x18006e252  lea     rdx, aCimpersonateIm_1; "CImpersonate::ImpersonateUser failed: 0"...
0x18006e259  jmp     loc_18006E39F
0x18006e25e  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x18006e265  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], 0
0x18006e26d  mov     [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x18006e274  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18006e278  mov     rcx, rsi; lpPathName
0x18006e27b  call    cs:__imp_CreateDirectoryW
0x18006e282  nop     dword ptr [rax+rax+00h]
0x18006e287  test    eax, eax
0x18006e289  jnz     short loc_18006E2C5
0x18006e28b  call    cs:__imp_GetLastError
0x18006e292  nop     dword ptr [rax+rax+00h]
0x18006e297  mov     ebx, eax
0x18006e299  test    eax, eax
0x18006e29b  jle     short loc_18006E2A6
0x18006e29d  movzx   ebx, ax
0x18006e2a0  or      ebx, 80070000h
0x18006e2a6  cmp     ebx, 800700B7h
0x18006e2ac  jnz     short loc_18006E2B5
0x18006e2ae  xor     ebx, ebx
0x18006e2b0  jmp     loc_18006E3B0
0x18006e2b5  test    ebx, ebx
0x18006e2b7  jns     short loc_18006E2C5
0x18006e2b9  lea     rdx, aCreatedirector; "CreateDirectory failed: 0x%x in %s"
0x18006e2c0  jmp     loc_18006E39C
0x18006e2c5  mov     rax, [rdi]
0x18006e2c8  lea     rdx, [rbp+57h+pSid]
0x18006e2cc  mov     rcx, rdi
0x18006e2cf  mov     rax, [rax+48h]
0x18006e2d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e2d8  mov     ebx, eax
0x18006e2da  test    eax, eax
0x18006e2dc  jns     short loc_18006E2ED
0x18006e2de  mov     r8d, eax
0x18006e2e1  lea     rdx, aPusernameGetus; "pUserName->GetUserSid failed: 0x%x in %"...
0x18006e2e8  jmp     loc_18006E39F
0x18006e2ed  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x18006e2f4  mov     edi, 1
0x18006e2f9  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], edi
0x18006e2fc  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x18006e303  mov     rdx, [rbp+57h+pSid]; pSid
0x18006e307  lea     rcx, [rbp+57h+pListOfExplicitEntries.Trustee]; pTrustee
0x18006e30b  call    cs:__imp_BuildTrusteeWithSidW
0x18006e312  nop     dword ptr [rax+rax+00h]
0x18006e317  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x18006e31b  xor     r8d, r8d; OldAcl
0x18006e31e  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18006e322  mov     ecx, edi; cCountOfExplicitEntries
0x18006e324  call    cs:__imp_SetEntriesInAclW
0x18006e32b  nop     dword ptr [rax+rax+00h]
0x18006e330  mov     ebx, eax
0x18006e332  test    eax, eax
0x18006e334  jle     short loc_18006E33F
0x18006e336  movzx   ebx, ax
0x18006e339  or      ebx, 80070000h
0x18006e33f  test    ebx, ebx
0x18006e341  jns     short loc_18006E34C
0x18006e343  lea     rdx, aSetentriesinac_0; "SetEntriesInAcl failed: 0x%x in %s"
0x18006e34a  jmp     short loc_18006E39C
0x18006e34c  mov     [rsp+0A0h+pSacl], 0; pSacl
0x18006e355  mov     rax, [rbp+57h+NewAcl]
0x18006e359  mov     [rsp+0A0h+pDacl], rax; pDacl
0x18006e35e  mov     [rsp+0A0h+psidGroup], 0; psidGroup
0x18006e367  mov     r9, [rbp+57h+pSid]; psidOwner
0x18006e36b  mov     r8d, 20000005h; SecurityInfo
0x18006e371  mov     edx, edi; ObjectType
0x18006e373  mov     rcx, rsi; pObjectName
0x18006e376  call    cs:__imp_SetNamedSecurityInfoW
0x18006e37d  nop     dword ptr [rax+rax+00h]
0x18006e382  mov     ebx, eax
0x18006e384  test    eax, eax
0x18006e386  jle     short loc_18006E391
0x18006e388  movzx   ebx, ax
0x18006e38b  or      ebx, 80070000h
0x18006e391  test    ebx, ebx
0x18006e393  jns     short loc_18006E3B0
0x18006e395  lea     rdx, aSetnamedsecuri_0; "SetNamedSecurityInfo failed: 0x%x in %s"
0x18006e39c  mov     r8d, ebx
0x18006e39f  lea     r9, aCuserprofileCr; "CUserProfile::CreateHomeDrectory"
0x18006e3a6  mov     ecx, 8; int
0x18006e3ab  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006e3b0  mov     rcx, [rbp+57h+pSid]; pv
0x18006e3b4  test    rcx, rcx
0x18006e3b7  jz      short loc_18006E3C5
0x18006e3b9  call    cs:__imp_CoTaskMemFree
0x18006e3c0  nop     dword ptr [rax+rax+00h]
0x18006e3c5  mov     rcx, [rbp+57h+NewAcl]; hMem
0x18006e3c9  test    rcx, rcx
0x18006e3cc  jz      short loc_18006E3DB
0x18006e3ce  call    cs:__imp_LocalFree
0x18006e3d5  nop     dword ptr [rax+rax+00h]
0x18006e3da  nop
0x18006e3db  lea     rcx, [rbp+57h+arg_10]; this
0x18006e3df  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x18006e3e4  mov     eax, ebx
0x18006e3e6  mov     rbx, [rsp+0A0h+arg_0]
0x18006e3ee  add     rsp, 90h
0x18006e3f5  pop     rdi
0x18006e3f6  pop     rsi
0x18006e3f7  pop     rbp
0x18006e3f8  retn
```
