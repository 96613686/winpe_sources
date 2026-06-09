# CheckForSaclPriv(void)

- ea: `0x180012ee8`
- end: `0x180012fda`
- name: `?CheckForSaclPriv@@YAJXZ`
- size: `242`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800043c0`

## callees

- `0x18000bb30`
- `0x180012ee8`
- `0x180015680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012fa4`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180012f76`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180012f76`
- `wbemcomn!GetAccessToken` at `0x180012f16`
- `wbemcomn!GetAccessToken` at `0x180012f16`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180012f43`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180012f43`

## string_xrefs

- `0x180012f3a`: `SeSecurityPrivilege`

## pseudocode

```c
__int64 CheckForSaclPriv(void)
{
  signed int AccessToken; // ebx
  signed int LastError; // eax
  signed int v2; // eax
  BOOL pfResult; // [rsp+20h] [rbp-40h] BYREF
  HANDLE ClientToken; // [rsp+28h] [rbp-38h] BYREF
  struct _LUID Luid; // [rsp+30h] [rbp-30h] BYREF
  HANDLE v7; // [rsp+38h] [rbp-28h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+40h] [rbp-20h] BYREF

  ClientToken = (HANDLE)-1LL;
  pfResult = 1;
  AccessToken = GetAccessToken(&ClientToken);
  if ( AccessToken >= 0 )
  {
    v7 = ClientToken;
    Luid = 0;
    if ( LookupPrivilegeValueW(0, L"SeSecurityPrivilege", &Luid) )
    {
      RequiredPrivileges.PrivilegeCount = 1;
      RequiredPrivileges.Control = 1;
      RequiredPrivileges.Privilege[0].Luid = Luid;
      RequiredPrivileges.Privilege[0].Attributes = 0;
      if ( PrivilegeCheck(ClientToken, &RequiredPrivileges, &pfResult) )
      {
        if ( !pfResult )
          AccessToken = -2147217310;
      }
      else
      {
        LastError = GetLastError();
        AccessToken = LastError;
        if ( LastError > 0 )
          AccessToken = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v2 = GetLastError();
      if ( v2 > 0 )
        v2 = (unsigned __int16)v2 | 0x80070000;
      AccessToken = v2;
    }
    CCloseMe::~CCloseMe((CCloseMe *)&v7);
  }
  return (unsigned int)AccessToken;
}

```

## disassembly

```asm
0x180012ee8  mov     [rsp-8+arg_0], rbx
0x180012eed  push    rbp
0x180012eee  mov     rbp, rsp
0x180012ef1  sub     rsp, 60h
0x180012ef5  mov     rax, cs:__security_cookie
0x180012efc  xor     rax, rsp
0x180012eff  mov     [rbp+var_8], rax
0x180012f03  mov     [rbp+ClientToken], 0FFFFFFFFFFFFFFFFh
0x180012f0b  mov     [rbp+pfResult], 1
0x180012f12  lea     rcx, [rbp+ClientToken]
0x180012f16  call    cs:__imp_?GetAccessToken@@YAJAEAPEAX@Z; GetAccessToken(void * &)
0x180012f1c  mov     ebx, eax
0x180012f1e  test    eax, eax
0x180012f20  js      loc_180012FC1
0x180012f26  mov     rcx, [rbp+ClientToken]
0x180012f2a  mov     [rbp+var_28], rcx
0x180012f2e  mov     qword ptr [rbp+Luid.LowPart], 0
0x180012f36  lea     r8, [rbp+Luid]; lpLuid
0x180012f3a  lea     rdx, Name; "SeSecurityPrivilege"
0x180012f41  xor     ecx, ecx; lpSystemName
0x180012f43  call    cs:__imp_LookupPrivilegeValueW
0x180012f49  test    eax, eax
0x180012f4b  jz      short loc_180012FA4
0x180012f4d  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x180012f54  mov     [rbp+RequiredPrivileges.Control], 1
0x180012f5b  mov     rax, qword ptr [rbp+Luid.LowPart]
0x180012f5f  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], rax
0x180012f63  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 0
0x180012f6a  lea     r8, [rbp+pfResult]; pfResult
0x180012f6e  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x180012f72  mov     rcx, [rbp+ClientToken]; ClientToken
0x180012f76  call    cs:__imp_PrivilegeCheck
0x180012f7c  test    eax, eax
0x180012f7e  jnz     short loc_180012F97
0x180012f80  call    cs:__imp_GetLastError
0x180012f86  mov     ebx, eax
0x180012f88  test    eax, eax
0x180012f8a  jle     short loc_180012FB8
0x180012f8c  movzx   ebx, ax
0x180012f8f  or      ebx, 80070000h
0x180012f95  jmp     short loc_180012FB8
0x180012f97  cmp     [rbp+pfResult], 0
0x180012f9b  jnz     short loc_180012FB8
0x180012f9d  mov     ebx, 80041062h
0x180012fa2  jmp     short loc_180012FB8
0x180012fa4  call    cs:__imp_GetLastError
0x180012faa  test    eax, eax
0x180012fac  jle     short loc_180012FB6
0x180012fae  movzx   eax, ax
0x180012fb1  or      eax, 80070000h
0x180012fb6  mov     ebx, eax
0x180012fb8  lea     rcx, [rbp+var_28]; this
0x180012fbc  call    ??1CCloseMe@@QEAA@XZ; CCloseMe::~CCloseMe(void)
0x180012fc1  mov     eax, ebx
0x180012fc3  mov     rcx, [rbp+var_8]
0x180012fc7  xor     rcx, rsp; StackCookie
0x180012fca  call    __security_check_cookie
0x180012fcf  mov     rbx, [rsp+60h+arg_0]
0x180012fd4  add     rsp, 60h
0x180012fd8  pop     rbp
0x180012fd9  retn
```
