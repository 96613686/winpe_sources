# CUserProfile::CreateHomeDrectory(IUserName *,ushort *)

- ea: `0x18006aee8`
- end: `0x18006b0c3`
- name: `?CreateHomeDrectory@CUserProfile@@CAJPEAUIUserName@@PEAG@Z`
- size: `475`
- prototype: `__int64 __fastcall(struct IUserName *, LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006b838`

## callees

- `0x18000a210`
- `0x180017758`
- `0x18006aee8`
- `0x1800b8c8c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006af79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006af79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b09e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b09e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006af6f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006af6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b08f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b08f`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18006aff3`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x18006aff3`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18006b052`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18006b052`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18006b006`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18006b006`

## string_xrefs

- `0x18006b01f`: `SetEntriesInAcl failed: 0x%x in %s`
- `0x18006b075`: `CUserProfile::CreateHomeDrectory`
- `0x18006af46`: `CImpersonate::ImpersonateUser failed: 0x%x in %s`
- `0x18006afa1`: `CreateDirectory failed: 0x%x in %s`
- `0x18006afc9`: `pUserName->GetUserSid failed: 0x%x in %s`
- `0x18006b06b`: `SetNamedSecurityInfo failed: 0x%x in %s`

## pseudocode

```c
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
0x18006aee8  mov     [rsp-8+arg_0], rbx
0x18006aeed  push    rbp
0x18006aeee  push    rsi
0x18006aeef  push    rdi
0x18006aef0  lea     rbp, [rsp-47h]
0x18006aef5  sub     rsp, 90h
0x18006aefc  mov     rsi, rdx
0x18006aeff  mov     rdi, rcx
0x18006af02  mov     [rbp+57h+arg_10], 0
0x18006af08  mov     [rbp+57h+NewAcl], 0
0x18006af10  xorps   xmm0, xmm0
0x18006af13  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18006af17  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18006af1b  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18006af1f  mov     [rbp+57h+pSid], 0
0x18006af27  xor     eax, eax
0x18006af29  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x18006af2d  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x18006af31  mov     rdx, rcx; struct IUserName *
0x18006af34  lea     rcx, [rbp+57h+arg_10]; this
0x18006af38  call    ?ImpersonateUser@CImpersonate@@QEAAJPEAUIUserName@@@Z; CImpersonate::ImpersonateUser(IUserName *)
0x18006af3d  mov     ebx, eax
0x18006af3f  test    eax, eax
0x18006af41  jns     short loc_18006AF52
0x18006af43  mov     r8d, eax
0x18006af46  lea     rdx, aCimpersonateIm_1; "CImpersonate::ImpersonateUser failed: 0"...
0x18006af4d  jmp     loc_18006B075
0x18006af52  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x18006af59  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], 0
0x18006af61  mov     [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x18006af68  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18006af6c  mov     rcx, rsi; lpPathName
0x18006af6f  call    cs:__imp_CreateDirectoryW
0x18006af75  test    eax, eax
0x18006af77  jnz     short loc_18006AFAD
0x18006af79  call    cs:__imp_GetLastError
0x18006af7f  mov     ebx, eax
0x18006af81  test    eax, eax
0x18006af83  jle     short loc_18006AF8E
0x18006af85  movzx   ebx, ax
0x18006af88  or      ebx, 80070000h
0x18006af8e  cmp     ebx, 800700B7h
0x18006af94  jnz     short loc_18006AF9D
0x18006af96  xor     ebx, ebx
0x18006af98  jmp     loc_18006B086
0x18006af9d  test    ebx, ebx
0x18006af9f  jns     short loc_18006AFAD
0x18006afa1  lea     rdx, aCreatedirector; "CreateDirectory failed: 0x%x in %s"
0x18006afa8  jmp     loc_18006B072
0x18006afad  mov     rax, [rdi]
0x18006afb0  lea     rdx, [rbp+57h+pSid]
0x18006afb4  mov     rcx, rdi
0x18006afb7  mov     rax, [rax+48h]
0x18006afbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afc0  mov     ebx, eax
0x18006afc2  test    eax, eax
0x18006afc4  jns     short loc_18006AFD5
0x18006afc6  mov     r8d, eax
0x18006afc9  lea     rdx, aPusernameGetus; "pUserName->GetUserSid failed: 0x%x in %"...
0x18006afd0  jmp     loc_18006B075
0x18006afd5  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x18006afdc  mov     edi, 1
0x18006afe1  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], edi
0x18006afe4  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], 3
0x18006afeb  mov     rdx, [rbp+57h+pSid]; pSid
0x18006afef  lea     rcx, [rbp+57h+pListOfExplicitEntries.Trustee]; pTrustee
0x18006aff3  call    cs:__imp_BuildTrusteeWithSidW
0x18006aff9  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x18006affd  xor     r8d, r8d; OldAcl
0x18006b000  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18006b004  mov     ecx, edi; cCountOfExplicitEntries
0x18006b006  call    cs:__imp_SetEntriesInAclW
0x18006b00c  mov     ebx, eax
0x18006b00e  test    eax, eax
0x18006b010  jle     short loc_18006B01B
0x18006b012  movzx   ebx, ax
0x18006b015  or      ebx, 80070000h
0x18006b01b  test    ebx, ebx
0x18006b01d  jns     short loc_18006B028
0x18006b01f  lea     rdx, aSetentriesinac_0; "SetEntriesInAcl failed: 0x%x in %s"
0x18006b026  jmp     short loc_18006B072
0x18006b028  mov     [rsp+0A0h+pSacl], 0; pSacl
0x18006b031  mov     rax, [rbp+57h+NewAcl]
0x18006b035  mov     [rsp+0A0h+pDacl], rax; pDacl
0x18006b03a  mov     [rsp+0A0h+psidGroup], 0; psidGroup
0x18006b043  mov     r9, [rbp+57h+pSid]; psidOwner
0x18006b047  mov     r8d, 20000005h; SecurityInfo
0x18006b04d  mov     edx, edi; ObjectType
0x18006b04f  mov     rcx, rsi; pObjectName
0x18006b052  call    cs:__imp_SetNamedSecurityInfoW
0x18006b058  mov     ebx, eax
0x18006b05a  test    eax, eax
0x18006b05c  jle     short loc_18006B067
0x18006b05e  movzx   ebx, ax
0x18006b061  or      ebx, 80070000h
0x18006b067  test    ebx, ebx
0x18006b069  jns     short loc_18006B086
0x18006b06b  lea     rdx, aSetnamedsecuri_0; "SetNamedSecurityInfo failed: 0x%x in %s"
0x18006b072  mov     r8d, ebx
0x18006b075  lea     r9, aCuserprofileCr; "CUserProfile::CreateHomeDrectory"
0x18006b07c  mov     ecx, 8; int
0x18006b081  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b086  mov     rcx, [rbp+57h+pSid]; pv
0x18006b08a  test    rcx, rcx
0x18006b08d  jz      short loc_18006B095
0x18006b08f  call    cs:__imp_CoTaskMemFree
0x18006b095  mov     rcx, [rbp+57h+NewAcl]; hMem
0x18006b099  test    rcx, rcx
0x18006b09c  jz      short loc_18006B0A5
0x18006b09e  call    cs:__imp_LocalFree
0x18006b0a4  nop
0x18006b0a5  lea     rcx, [rbp+57h+arg_10]; this
0x18006b0a9  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x18006b0ae  mov     eax, ebx
0x18006b0b0  mov     rbx, [rsp+0A0h+arg_0]
0x18006b0b8  add     rsp, 90h
0x18006b0bf  pop     rdi
0x18006b0c0  pop     rsi
0x18006b0c1  pop     rbp
0x18006b0c2  retn
```
