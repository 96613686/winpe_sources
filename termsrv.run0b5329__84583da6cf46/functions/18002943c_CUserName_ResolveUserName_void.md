# CUserName::ResolveUserName(void *)

- ea: `0x18002943c`
- end: `0x18002963e`
- name: `?ResolveUserName@CUserName@@AEAAJPEAX@Z`
- size: `514`
- prototype: `__int64 __fastcall(CUserName *__hidden this, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009f50`
- `0x180025ddc`

## callees

- `0x18000a210`
- `0x180017758`
- `0x18002943c`
- `0x1800342f4`
- `0x1800996dc`
- `0x1800b8d28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029588`
- `ext-ms-win-advapi32-lsa-l1-1-0!LsaGetUserName` at `0x1800294a2`
- `ext-ms-win-advapi32-lsa-l1-1-0!LsaGetUserName` at `0x1800294a2`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002957e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002957e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800295ee`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800295f8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029613`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002961d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800295ee`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800295f8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180029613`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002961d`

## string_xrefs

- `0x1800295a0`: `LookupAccountSid failed: 0x%x`
- `0x180029547`: `Impersonate.StopImpersonating failed: 0x%x in %s`
- `0x1800294ee`: `StringCchCopyN failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUserName::ResolveUserName(CUserName *this, void *a2)
{
  const unsigned __int16 *Buffer; // r8
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  signed int LastError; // eax
  PLSA_UNICODE_STRING v8; // rcx
  PLSA_UNICODE_STRING v9; // rcx
  DWORD cchReferencedDomainName; // [rsp+30h] [rbp-20h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-1Ch] BYREF
  PLSA_UNICODE_STRING DomainName; // [rsp+38h] [rbp-18h] BYREF
  PLSA_UNICODE_STRING UserName; // [rsp+40h] [rbp-10h] BYREF
  __int16 v15; // [rsp+70h] [rbp+20h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+78h] [rbp+28h] BYREF

  v15 = 0;
  UserName = 0;
  DomainName = 0;
  cchName = 257;
  cchReferencedDomainName = 256;
  peUse = 0;
  if ( CImpersonate::ImpersonateUser((CImpersonate *)&v15, a2) >= 0 )
  {
    if ( (unsigned __int8)IsLsaGetUserNamePresent() )
    {
      if ( !LsaGetUserName(&UserName, &DomainName) )
      {
        if ( UserName )
        {
          Buffer = UserName->Buffer;
          if ( Buffer )
          {
            if ( DomainName && DomainName->Buffer )
            {
              v4 = StringCchCopyNW(
                     (unsigned __int16 *)this + 1064,
                     cchName,
                     Buffer,
                     (unsigned __int64)UserName->Length >> 1);
              v5 = v4;
              if ( v4 < 0
                || (v4 = StringCchCopyNW(
                           (unsigned __int16 *)this + 808,
                           cchReferencedDomainName,
                           DomainName->Buffer,
                           (unsigned __int64)DomainName->Length >> 1),
                    v5 = v4,
                    v4 < 0) )
              {
                _DbgPrintMessage(8, "StringCchCopyN failed: 0x%x in %s", (unsigned int)v4, "CUserName::ResolveUserName");
              }
              goto LABEL_22;
            }
          }
        }
      }
    }
    v6 = CImpersonate::StopImpersonating((CImpersonate *)&v15);
    v5 = v6;
    if ( v6 < 0 )
    {
      _DbgPrintMessage(
        8,
        "Impersonate.StopImpersonating failed: 0x%x in %s",
        (unsigned int)v6,
        "CUserName::ResolveUserName");
      goto LABEL_22;
    }
  }
  if ( LookupAccountSidLocalW(
         **((PSID **)this + 201),
         (LPWSTR)this + 1064,
         &cchName,
         (LPWSTR)this + 808,
         &cchReferencedDomainName,
         &peUse) )
  {
    if ( ((peUse - 1) & 0xFFFFFFFB) != 0 )
    {
      _DbgPrintMessage(8, "Expecting user account to logon");
      v5 = -2147024891;
    }
    else
    {
      v5 = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "LookupAccountSid failed: 0x%x", v5);
  }
LABEL_22:
  v8 = UserName;
  if ( UserName )
  {
    if ( UserName->Buffer )
    {
      LsaFreeMemory(UserName->Buffer);
      v8 = UserName;
    }
    LsaFreeMemory(v8);
  }
  v9 = DomainName;
  if ( DomainName )
  {
    if ( DomainName->Buffer )
    {
      LsaFreeMemory(DomainName->Buffer);
      v9 = DomainName;
    }
    LsaFreeMemory(v9);
  }
  CImpersonate::StopImpersonating((CImpersonate *)&v15);
  return v5;
}

```

## disassembly

```asm
0x18002943c  mov     [rsp-8+arg_0], rbx
0x180029441  mov     [rsp-8+arg_8], rdi
0x180029446  push    rbp
0x180029447  mov     rbp, rsp
0x18002944a  sub     rsp, 50h
0x18002944e  mov     rdi, rcx
0x180029451  mov     [rbp+arg_10], 0
0x180029457  lea     rcx, [rbp+arg_10]; this
0x18002945b  mov     [rbp+UserName], 0
0x180029463  mov     [rbp+DomainName], 0
0x18002946b  mov     [rbp+cchName], 101h
0x180029472  mov     [rbp+var_20], 100h
0x180029479  mov     [rbp+arg_18], 0
0x180029480  call    ?ImpersonateUser@CImpersonate@@QEAAJPEAX@Z; CImpersonate::ImpersonateUser(void *)
0x180029485  test    eax, eax
0x180029487  js      loc_180029550
0x18002948d  call    IsLsaGetUserNamePresent
0x180029492  test    al, al
0x180029494  jz      loc_180029538
0x18002949a  lea     rdx, [rbp+DomainName]; DomainName
0x18002949e  lea     rcx, [rbp+UserName]; UserName
0x1800294a2  call    cs:__imp_LsaGetUserName
0x1800294a8  test    eax, eax
0x1800294aa  jnz     loc_180029538
0x1800294b0  mov     rax, [rbp+UserName]
0x1800294b4  test    rax, rax
0x1800294b7  jz      short loc_180029538
0x1800294b9  mov     r8, [rax+8]; unsigned __int16 *
0x1800294bd  test    r8, r8
0x1800294c0  jz      short loc_180029538
0x1800294c2  mov     rcx, [rbp+DomainName]
0x1800294c6  test    rcx, rcx
0x1800294c9  jz      short loc_180029538
0x1800294cb  cmp     qword ptr [rcx+8], 0
0x1800294d0  jz      short loc_180029538
0x1800294d2  movzx   r9d, word ptr [rax]
0x1800294d6  lea     rcx, [rdi+850h]; unsigned __int16 *
0x1800294dd  mov     edx, [rbp+cchName]; unsigned __int64
0x1800294e0  shr     r9, 1; unsigned __int64
0x1800294e3  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800294e8  mov     ebx, eax
0x1800294ea  test    eax, eax
0x1800294ec  jns     short loc_18002950E
0x1800294ee  lea     rdx, aStringcchcopyn; "StringCchCopyN failed: 0x%x in %s"
0x1800294f5  mov     r8d, eax
0x1800294f8  lea     r9, aCusernameResol; "CUserName::ResolveUserName"
0x1800294ff  mov     ecx, 8; int
0x180029504  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029509  jmp     loc_1800295D9
0x18002950e  mov     r8, [rbp+DomainName]
0x180029512  lea     rcx, [rdi+650h]; unsigned __int16 *
0x180029519  mov     edx, [rbp+var_20]; unsigned __int64
0x18002951c  movzx   r9d, word ptr [r8]
0x180029520  mov     r8, [r8+8]; unsigned __int16 *
0x180029524  shr     r9, 1; unsigned __int64
0x180029527  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18002952c  mov     ebx, eax
0x18002952e  test    eax, eax
0x180029530  jns     loc_1800295D9
0x180029536  jmp     short loc_1800294EE
0x180029538  lea     rcx, [rbp+arg_10]; this
0x18002953c  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x180029541  mov     ebx, eax
0x180029543  test    eax, eax
0x180029545  jns     short loc_180029550
0x180029547  lea     rdx, aImpersonateSto_0; "Impersonate.StopImpersonating failed: 0"...
0x18002954e  jmp     short loc_1800294F5
0x180029550  mov     rcx, [rdi+648h]
0x180029557  lea     rax, [rbp+arg_18]
0x18002955b  mov     [rsp+50h+peUse], rax; peUse
0x180029560  lea     r9, [rdi+650h]; ReferencedDomainName
0x180029567  lea     rax, [rbp+var_20]
0x18002956b  lea     r8, [rbp+cchName]; cchName
0x18002956f  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180029574  mov     rcx, [rcx]; Sid
0x180029577  lea     rdx, [rdi+850h]; Name
0x18002957e  call    cs:__imp_LookupAccountSidLocalW
0x180029584  test    eax, eax
0x180029586  jnz     short loc_1800295B3
0x180029588  call    cs:__imp_GetLastError
0x18002958e  mov     ebx, eax
0x180029590  test    eax, eax
0x180029592  jle     short loc_18002959D
0x180029594  movzx   ebx, ax
0x180029597  or      ebx, 80070000h
0x18002959d  mov     r8d, ebx
0x1800295a0  lea     rdx, aLookupaccounts_0; "LookupAccountSid failed: 0x%x"
0x1800295a7  mov     ecx, 8; int
0x1800295ac  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800295b1  jmp     short loc_1800295D9
0x1800295b3  mov     eax, [rbp+arg_18]
0x1800295b6  dec     eax
0x1800295b8  test    eax, 0FFFFFFFBh
0x1800295bd  jz      short loc_1800295D7
0x1800295bf  lea     rdx, aExpectingUserA; "Expecting user account to logon"
0x1800295c6  mov     ecx, 8; int
0x1800295cb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800295d0  mov     ebx, 80070005h
0x1800295d5  jmp     short loc_1800295D9
0x1800295d7  xor     ebx, ebx
0x1800295d9  mov     rcx, [rbp+UserName]
0x1800295dd  test    rcx, rcx
0x1800295e0  jz      short loc_1800295FE
0x1800295e2  mov     rax, [rcx+8]
0x1800295e6  test    rax, rax
0x1800295e9  jz      short loc_1800295F8
0x1800295eb  mov     rcx, rax; Buffer
0x1800295ee  call    cs:__imp_LsaFreeMemory
0x1800295f4  mov     rcx, [rbp+UserName]; Buffer
0x1800295f8  call    cs:__imp_LsaFreeMemory
0x1800295fe  mov     rcx, [rbp+DomainName]
0x180029602  test    rcx, rcx
0x180029605  jz      short loc_180029623
0x180029607  mov     rax, [rcx+8]
0x18002960b  test    rax, rax
0x18002960e  jz      short loc_18002961D
0x180029610  mov     rcx, rax; Buffer
0x180029613  call    cs:__imp_LsaFreeMemory
0x180029619  mov     rcx, [rbp+DomainName]; Buffer
0x18002961d  call    cs:__imp_LsaFreeMemory
0x180029623  lea     rcx, [rbp+arg_10]; this
0x180029627  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x18002962c  mov     rdi, [rsp+50h+arg_8]
0x180029631  mov     eax, ebx
0x180029633  mov     rbx, [rsp+50h+arg_0]
0x180029638  add     rsp, 50h
0x18002963c  pop     rbp
0x18002963d  retn
```
