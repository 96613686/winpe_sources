# CUserName::ResolveUserName(void *)

- ea: `0x180013160`
- end: `0x180013362`
- name: `?ResolveUserName@CUserName@@AEAAJPEAX@Z`
- size: `514`
- prototype: `__int64 __fastcall(CUserName *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800178e0`

## callees

- `0x180003f30`
- `0x180013160`
- `0x18001ccb8`
- `0x18005a0ec`
- `0x18005a17c`
- `0x18005b374`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132ac`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800132a2`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800132a2`
- `ext-ms-win-advapi32-lsa-l1-1-0!LsaGetUserName` at `0x1800131c6`
- `ext-ms-win-advapi32-lsa-l1-1-0!LsaGetUserName` at `0x1800131c6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180013312`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001331c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180013337`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180013341`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180013312`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001331c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180013337`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180013341`

## string_xrefs

- `0x1800132c4`: `LookupAccountSid failed: 0x%x`
- `0x180013212`: `StringCchCopyN failed: 0x%x in %s`
- `0x18001326b`: `Impersonate.StopImpersonating failed: 0x%x in %s`

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
0x180013160  mov     [rsp-8+arg_0], rbx
0x180013165  mov     [rsp-8+arg_8], rdi
0x18001316a  push    rbp
0x18001316b  mov     rbp, rsp
0x18001316e  sub     rsp, 50h
0x180013172  mov     rdi, rcx
0x180013175  mov     [rbp+arg_10], 0
0x18001317b  lea     rcx, [rbp+arg_10]; this
0x18001317f  mov     [rbp+UserName], 0
0x180013187  mov     [rbp+DomainName], 0
0x18001318f  mov     [rbp+cchName], 101h
0x180013196  mov     [rbp+var_20], 100h
0x18001319d  mov     [rbp+arg_18], 0
0x1800131a4  call    ?ImpersonateUser@CImpersonate@@QEAAJPEAX@Z; CImpersonate::ImpersonateUser(void *)
0x1800131a9  test    eax, eax
0x1800131ab  js      loc_180013274
0x1800131b1  call    IsLsaGetUserNamePresent
0x1800131b6  test    al, al
0x1800131b8  jz      loc_18001325C
0x1800131be  lea     rdx, [rbp+DomainName]; DomainName
0x1800131c2  lea     rcx, [rbp+UserName]; UserName
0x1800131c6  call    cs:__imp_LsaGetUserName
0x1800131cc  test    eax, eax
0x1800131ce  jnz     loc_18001325C
0x1800131d4  mov     rax, [rbp+UserName]
0x1800131d8  test    rax, rax
0x1800131db  jz      short loc_18001325C
0x1800131dd  mov     r8, [rax+8]; unsigned __int16 *
0x1800131e1  test    r8, r8
0x1800131e4  jz      short loc_18001325C
0x1800131e6  mov     rcx, [rbp+DomainName]
0x1800131ea  test    rcx, rcx
0x1800131ed  jz      short loc_18001325C
0x1800131ef  cmp     qword ptr [rcx+8], 0
0x1800131f4  jz      short loc_18001325C
0x1800131f6  movzx   r9d, word ptr [rax]
0x1800131fa  lea     rcx, [rdi+850h]; unsigned __int16 *
0x180013201  mov     edx, [rbp+cchName]; unsigned __int64
0x180013204  shr     r9, 1; unsigned __int64
0x180013207  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001320c  mov     ebx, eax
0x18001320e  test    eax, eax
0x180013210  jns     short loc_180013232
0x180013212  lea     rdx, aStringcchcopyn; "StringCchCopyN failed: 0x%x in %s"
0x180013219  mov     r8d, eax
0x18001321c  lea     r9, aCusernameResol; "CUserName::ResolveUserName"
0x180013223  mov     ecx, 8; int
0x180013228  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001322d  jmp     loc_1800132FD
0x180013232  mov     r8, [rbp+DomainName]
0x180013236  lea     rcx, [rdi+650h]; unsigned __int16 *
0x18001323d  mov     edx, [rbp+var_20]; unsigned __int64
0x180013240  movzx   r9d, word ptr [r8]
0x180013244  mov     r8, [r8+8]; unsigned __int16 *
0x180013248  shr     r9, 1; unsigned __int64
0x18001324b  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180013250  mov     ebx, eax
0x180013252  test    eax, eax
0x180013254  jns     loc_1800132FD
0x18001325a  jmp     short loc_180013212
0x18001325c  lea     rcx, [rbp+arg_10]; this
0x180013260  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x180013265  mov     ebx, eax
0x180013267  test    eax, eax
0x180013269  jns     short loc_180013274
0x18001326b  lea     rdx, aImpersonateSto; "Impersonate.StopImpersonating failed: 0"...
0x180013272  jmp     short loc_180013219
0x180013274  mov     rcx, [rdi+648h]
0x18001327b  lea     rax, [rbp+arg_18]
0x18001327f  mov     [rsp+50h+peUse], rax; peUse
0x180013284  lea     r9, [rdi+650h]; ReferencedDomainName
0x18001328b  lea     rax, [rbp+var_20]
0x18001328f  lea     r8, [rbp+cchName]; cchName
0x180013293  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180013298  mov     rcx, [rcx]; Sid
0x18001329b  lea     rdx, [rdi+850h]; Name
0x1800132a2  call    cs:__imp_LookupAccountSidLocalW
0x1800132a8  test    eax, eax
0x1800132aa  jnz     short loc_1800132D7
0x1800132ac  call    cs:__imp_GetLastError
0x1800132b2  mov     ebx, eax
0x1800132b4  test    eax, eax
0x1800132b6  jle     short loc_1800132C1
0x1800132b8  movzx   ebx, ax
0x1800132bb  or      ebx, 80070000h
0x1800132c1  mov     r8d, ebx
0x1800132c4  lea     rdx, aLookupaccounts_3; "LookupAccountSid failed: 0x%x"
0x1800132cb  mov     ecx, 8; int
0x1800132d0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800132d5  jmp     short loc_1800132FD
0x1800132d7  mov     eax, [rbp+arg_18]
0x1800132da  dec     eax
0x1800132dc  test    eax, 0FFFFFFFBh
0x1800132e1  jz      short loc_1800132FB
0x1800132e3  lea     rdx, aExpectingUserA; "Expecting user account to logon"
0x1800132ea  mov     ecx, 8; int
0x1800132ef  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800132f4  mov     ebx, 80070005h
0x1800132f9  jmp     short loc_1800132FD
0x1800132fb  xor     ebx, ebx
0x1800132fd  mov     rcx, [rbp+UserName]
0x180013301  test    rcx, rcx
0x180013304  jz      short loc_180013322
0x180013306  mov     rax, [rcx+8]
0x18001330a  test    rax, rax
0x18001330d  jz      short loc_18001331C
0x18001330f  mov     rcx, rax; Buffer
0x180013312  call    cs:__imp_LsaFreeMemory
0x180013318  mov     rcx, [rbp+UserName]; Buffer
0x18001331c  call    cs:__imp_LsaFreeMemory
0x180013322  mov     rcx, [rbp+DomainName]
0x180013326  test    rcx, rcx
0x180013329  jz      short loc_180013347
0x18001332b  mov     rax, [rcx+8]
0x18001332f  test    rax, rax
0x180013332  jz      short loc_180013341
0x180013334  mov     rcx, rax; Buffer
0x180013337  call    cs:__imp_LsaFreeMemory
0x18001333d  mov     rcx, [rbp+DomainName]; Buffer
0x180013341  call    cs:__imp_LsaFreeMemory
0x180013347  lea     rcx, [rbp+arg_10]; this
0x18001334b  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x180013350  mov     rdi, [rsp+50h+arg_8]
0x180013355  mov     eax, ebx
0x180013357  mov     rbx, [rsp+50h+arg_0]
0x18001335c  add     rsp, 50h
0x180013360  pop     rbp
0x180013361  retn
```
