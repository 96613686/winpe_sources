# CUserInformationStatics::_ValidateCallerCapability(bool *)

- ea: `0x1800d0354`
- end: `0x1800d0475`
- name: `?_ValidateCallerCapability@CUserInformationStatics@@AEAAJPEA_N@Z`
- size: `289`
- prototype: `__int64 __fastcall(CUserInformationStatics *__hidden this, bool *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800c9690`
- `0x1800c9ba0`
- `0x1800c9ec0`

## callees

- `0x180045fc8`
- `0x180054130`
- `0x1800d0354`
- `0x1800dcf48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d03db`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d043a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d03db`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d043a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d03bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d041b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d03bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d041b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800d044e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800d044e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserInformationStatics::_ValidateCallerCapability(CUserInformationStatics *this, bool *a2)
{
  int v3; // ebx
  __int64 v4; // rcx
  int v6; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-28h] BYREF

  *a2 = 0;
  v6 = 0;
  v3 = CheckAndGetCapability(WinCapabilityEnterpriseAuthenticationSid, a2, &v6, 0);
  if ( v3 >= 0 )
  {
    if ( v6 )
    {
      v3 = _ValidatePrivacyAccess();
      if ( v3 < 0 )
      {
        *a2 = 1;
        return 0;
      }
      return (unsigned int)v3;
    }
    v3 = -2147024891;
  }
  if ( v3 == -2147024891 )
  {
    if ( WindowsCreateStringReference(
           L"Caller does not have the EnterpriseAuthentication capability.",
           0x3Du,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v4 = 2147942405LL;
LABEL_14:
    RoOriginateError(v4, string);
    return (unsigned int)v3;
  }
  if ( v3 < 0 )
  {
    if ( WindowsCreateStringReference(L"Unable to check for capability.", 0x1Fu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v4 = (unsigned int)v3;
    goto LABEL_14;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800d0354  mov     [rsp+arg_0], rbx
0x1800d0359  push    rdi
0x1800d035a  sub     rsp, 50h
0x1800d035e  mov     rax, cs:__security_cookie
0x1800d0365  xor     rax, rsp
0x1800d0368  mov     [rsp+58h+var_10], rax
0x1800d036d  mov     rdi, rdx
0x1800d0370  mov     byte ptr [rdx], 0
0x1800d0373  mov     [rsp+58h+var_38], 0
0x1800d037b  xor     r9d, r9d; void **
0x1800d037e  lea     r8, [rsp+58h+var_38]; int *
0x1800d0383  lea     ecx, [r9+5Dh]; WellKnownSidType
0x1800d0387  call    ?CheckAndGetCapability@@YAJW4WELL_KNOWN_SID_TYPE@@PEAXPEAHPEAPEAX@Z; CheckAndGetCapability(WELL_KNOWN_SID_TYPE,void *,int *,void * *)
0x1800d038c  mov     ebx, eax
0x1800d038e  test    eax, eax
0x1800d0390  js      short loc_1800D039E
0x1800d0392  cmp     [rsp+58h+var_38], 0
0x1800d0397  jnz     short loc_1800D03EF
0x1800d0399  mov     ebx, 80070005h
0x1800d039e  cmp     ebx, 80070005h
0x1800d03a4  jnz     short loc_1800D0401
0x1800d03a6  lea     r9, [rsp+58h+string]; string
0x1800d03ab  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x1800d03b0  mov     edx, 3Dh ; '='; length
0x1800d03b5  lea     rcx, aCallerDoesNotH; "Caller does not have the EnterpriseAuth"...
0x1800d03bc  call    cs:__imp_WindowsCreateStringReference
0x1800d03c3  nop     dword ptr [rax+rax+00h]
0x1800d03c8  test    eax, eax
0x1800d03ca  jns     short loc_1800D03E8
0x1800d03cc  xor     r9d, r9d; lpArguments
0x1800d03cf  xor     r8d, r8d; nNumberOfArguments
0x1800d03d2  lea     edx, [r9+1]; dwExceptionFlags
0x1800d03d6  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800d03db  call    cs:__imp_RaiseException
0x1800d03e2  nop     dword ptr [rax+rax+00h]
0x1800d03e7  nop
0x1800d03e8  mov     ecx, 80070005h
0x1800d03ed  jmp     short loc_1800D0449
0x1800d03ef  call    ?_ValidatePrivacyAccess@@YAJXZ; _ValidatePrivacyAccess(void)
0x1800d03f4  mov     ebx, eax
0x1800d03f6  test    eax, eax
0x1800d03f8  jns     short loc_1800D045A
0x1800d03fa  mov     byte ptr [rdi], 1
0x1800d03fd  xor     ebx, ebx
0x1800d03ff  jmp     short loc_1800D045A
0x1800d0401  test    ebx, ebx
0x1800d0403  jns     short loc_1800D045A
0x1800d0405  lea     r9, [rsp+58h+string]; string
0x1800d040a  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x1800d040f  mov     edx, 1Fh; length
0x1800d0414  lea     rcx, aUnableToCheckF; "Unable to check for capability."
0x1800d041b  call    cs:__imp_WindowsCreateStringReference
0x1800d0422  nop     dword ptr [rax+rax+00h]
0x1800d0427  test    eax, eax
0x1800d0429  jns     short loc_1800D0447
0x1800d042b  xor     r9d, r9d; lpArguments
0x1800d042e  xor     r8d, r8d; nNumberOfArguments
0x1800d0431  lea     edx, [r9+1]; dwExceptionFlags
0x1800d0435  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800d043a  call    cs:__imp_RaiseException
0x1800d0441  nop     dword ptr [rax+rax+00h]
0x1800d0446  nop
0x1800d0447  mov     ecx, ebx
0x1800d0449  mov     rdx, [rsp+58h+string]
0x1800d044e  call    cs:__imp_RoOriginateError
0x1800d0455  nop     dword ptr [rax+rax+00h]
0x1800d045a  mov     eax, ebx
0x1800d045c  mov     rcx, [rsp+58h+var_10]
0x1800d0461  xor     rcx, rsp; StackCookie
0x1800d0464  call    __security_check_cookie
0x1800d0469  mov     rbx, [rsp+58h+arg_0]
0x1800d046e  add     rsp, 50h
0x1800d0472  pop     rdi
0x1800d0473  retn
```
