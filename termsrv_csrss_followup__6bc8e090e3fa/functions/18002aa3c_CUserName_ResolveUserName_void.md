# CUserName::ResolveUserName(void *)

- ea: `0x18002aa3c`
- end: `0x18002ac69`
- name: `?ResolveUserName@CUserName@@AEAAJPEAX@Z`
- size: `557`
- prototype: `__int64 __fastcall(CUserName *__hidden this, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009630`
- `0x1800272cc`

## callees

- `0x180009940`
- `0x180018394`
- `0x18002aa3c`
- `0x180036094`
- `0x18009d86c`
- `0x1800bf63c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab94`
- `ext-ms-win-advapi32-lsa-l1-1-0!LsaGetUserName` at `0x18002aaa2`
- `ext-ms-win-advapi32-lsa-l1-1-0!LsaGetUserName` at `0x18002aaa2`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002ab84`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18002ab84`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ac00`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ac10`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ac31`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ac41`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ac00`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ac10`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ac31`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ac41`

## string_xrefs

- `0x18002abb2`: `LookupAccountSid failed: 0x%x`
- `0x18002ab4d`: `Impersonate.StopImpersonating failed: 0x%x in %s`
- `0x18002aaf4`: `StringCchCopyN failed: 0x%x in %s`

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
0x18002aa3c  mov     [rsp-8+arg_0], rbx
0x18002aa41  mov     [rsp-8+arg_8], rdi
0x18002aa46  push    rbp
0x18002aa47  mov     rbp, rsp
0x18002aa4a  sub     rsp, 50h
0x18002aa4e  mov     rdi, rcx
0x18002aa51  mov     [rbp+arg_10], 0
0x18002aa57  lea     rcx, [rbp+arg_10]; this
0x18002aa5b  mov     [rbp+UserName], 0
0x18002aa63  mov     [rbp+DomainName], 0
0x18002aa6b  mov     [rbp+cchName], 101h
0x18002aa72  mov     [rbp+var_20], 100h
0x18002aa79  mov     [rbp+arg_18], 0
0x18002aa80  call    ?ImpersonateUser@CImpersonate@@QEAAJPEAX@Z; CImpersonate::ImpersonateUser(void *)
0x18002aa85  test    eax, eax
0x18002aa87  js      loc_18002AB56
0x18002aa8d  call    IsLsaGetUserNamePresent
0x18002aa92  test    al, al
0x18002aa94  jz      loc_18002AB3E
0x18002aa9a  lea     rdx, [rbp+DomainName]; DomainName
0x18002aa9e  lea     rcx, [rbp+UserName]; UserName
0x18002aaa2  call    cs:__imp_LsaGetUserName
0x18002aaa9  nop     dword ptr [rax+rax+00h]
0x18002aaae  test    eax, eax
0x18002aab0  jnz     loc_18002AB3E
0x18002aab6  mov     rax, [rbp+UserName]
0x18002aaba  test    rax, rax
0x18002aabd  jz      short loc_18002AB3E
0x18002aabf  mov     r8, [rax+8]; unsigned __int16 *
0x18002aac3  test    r8, r8
0x18002aac6  jz      short loc_18002AB3E
0x18002aac8  mov     rcx, [rbp+DomainName]
0x18002aacc  test    rcx, rcx
0x18002aacf  jz      short loc_18002AB3E
0x18002aad1  cmp     qword ptr [rcx+8], 0
0x18002aad6  jz      short loc_18002AB3E
0x18002aad8  movzx   r9d, word ptr [rax]
0x18002aadc  lea     rcx, [rdi+850h]; unsigned __int16 *
0x18002aae3  mov     edx, [rbp+cchName]; unsigned __int64
0x18002aae6  shr     r9, 1; unsigned __int64
0x18002aae9  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18002aaee  mov     ebx, eax
0x18002aaf0  test    eax, eax
0x18002aaf2  jns     short loc_18002AB14
0x18002aaf4  lea     rdx, aStringcchcopyn; "StringCchCopyN failed: 0x%x in %s"
0x18002aafb  mov     r8d, eax
0x18002aafe  lea     r9, aCusernameResol; "CUserName::ResolveUserName"
0x18002ab05  mov     ecx, 8; int
0x18002ab0a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ab0f  jmp     loc_18002ABEB
0x18002ab14  mov     r8, [rbp+DomainName]
0x18002ab18  lea     rcx, [rdi+650h]; unsigned __int16 *
0x18002ab1f  mov     edx, [rbp+var_20]; unsigned __int64
0x18002ab22  movzx   r9d, word ptr [r8]
0x18002ab26  mov     r8, [r8+8]; unsigned __int16 *
0x18002ab2a  shr     r9, 1; unsigned __int64
0x18002ab2d  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18002ab32  mov     ebx, eax
0x18002ab34  test    eax, eax
0x18002ab36  jns     loc_18002ABEB
0x18002ab3c  jmp     short loc_18002AAF4
0x18002ab3e  lea     rcx, [rbp+arg_10]; this
0x18002ab42  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x18002ab47  mov     ebx, eax
0x18002ab49  test    eax, eax
0x18002ab4b  jns     short loc_18002AB56
0x18002ab4d  lea     rdx, aImpersonateSto_0; "Impersonate.StopImpersonating failed: 0"...
0x18002ab54  jmp     short loc_18002AAFB
0x18002ab56  mov     rcx, [rdi+648h]
0x18002ab5d  lea     rax, [rbp+arg_18]
0x18002ab61  mov     [rsp+50h+peUse], rax; peUse
0x18002ab66  lea     r9, [rdi+650h]; ReferencedDomainName
0x18002ab6d  lea     rax, [rbp+var_20]
0x18002ab71  lea     r8, [rbp+cchName]; cchName
0x18002ab75  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002ab7a  mov     rcx, [rcx]; Sid
0x18002ab7d  lea     rdx, [rdi+850h]; Name
0x18002ab84  call    cs:__imp_LookupAccountSidLocalW
0x18002ab8b  nop     dword ptr [rax+rax+00h]
0x18002ab90  test    eax, eax
0x18002ab92  jnz     short loc_18002ABC5
0x18002ab94  call    cs:__imp_GetLastError
0x18002ab9b  nop     dword ptr [rax+rax+00h]
0x18002aba0  mov     ebx, eax
0x18002aba2  test    eax, eax
0x18002aba4  jle     short loc_18002ABAF
0x18002aba6  movzx   ebx, ax
0x18002aba9  or      ebx, 80070000h
0x18002abaf  mov     r8d, ebx
0x18002abb2  lea     rdx, aLookupaccounts_0; "LookupAccountSid failed: 0x%x"
0x18002abb9  mov     ecx, 8; int
0x18002abbe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002abc3  jmp     short loc_18002ABEB
0x18002abc5  mov     eax, [rbp+arg_18]
0x18002abc8  dec     eax
0x18002abca  test    eax, 0FFFFFFFBh
0x18002abcf  jz      short loc_18002ABE9
0x18002abd1  lea     rdx, aExpectingUserA; "Expecting user account to logon"
0x18002abd8  mov     ecx, 8; int
0x18002abdd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002abe2  mov     ebx, 80070005h
0x18002abe7  jmp     short loc_18002ABEB
0x18002abe9  xor     ebx, ebx
0x18002abeb  mov     rcx, [rbp+UserName]
0x18002abef  test    rcx, rcx
0x18002abf2  jz      short loc_18002AC1C
0x18002abf4  mov     rax, [rcx+8]
0x18002abf8  test    rax, rax
0x18002abfb  jz      short loc_18002AC10
0x18002abfd  mov     rcx, rax; Buffer
0x18002ac00  call    cs:__imp_LsaFreeMemory
0x18002ac07  nop     dword ptr [rax+rax+00h]
0x18002ac0c  mov     rcx, [rbp+UserName]; Buffer
0x18002ac10  call    cs:__imp_LsaFreeMemory
0x18002ac17  nop     dword ptr [rax+rax+00h]
0x18002ac1c  mov     rcx, [rbp+DomainName]
0x18002ac20  test    rcx, rcx
0x18002ac23  jz      short loc_18002AC4D
0x18002ac25  mov     rax, [rcx+8]
0x18002ac29  test    rax, rax
0x18002ac2c  jz      short loc_18002AC41
0x18002ac2e  mov     rcx, rax; Buffer
0x18002ac31  call    cs:__imp_LsaFreeMemory
0x18002ac38  nop     dword ptr [rax+rax+00h]
0x18002ac3d  mov     rcx, [rbp+DomainName]; Buffer
0x18002ac41  call    cs:__imp_LsaFreeMemory
0x18002ac48  nop     dword ptr [rax+rax+00h]
0x18002ac4d  lea     rcx, [rbp+arg_10]; this
0x18002ac51  call    ?StopImpersonating@CImpersonate@@QEAAJXZ; CImpersonate::StopImpersonating(void)
0x18002ac56  mov     rdi, [rsp+50h+arg_8]
0x18002ac5b  mov     eax, ebx
0x18002ac5d  mov     rbx, [rsp+50h+arg_0]
0x18002ac62  add     rsp, 50h
0x18002ac66  pop     rbp
0x18002ac67  retn
```
