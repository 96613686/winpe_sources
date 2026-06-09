# GetSidStringFromToken

- ea: `0x1800555e4`
- end: `0x1800556f6`
- name: `GetSidStringFromToken`
- size: `274`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPWSTR *StringSid)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180054774`
- `0x1800548d8`
- `0x180054940`

## callees

- `0x180010c04`
- `0x180042038`
- `0x1800555e4`
- `0x180067258`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005561e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005561e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055648`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055648`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800556de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800556de`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180055614`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005568e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180055614`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005568e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800556b7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800556b7`

## string_xrefs

- `0x18005562e`: `onecoreuap\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x18005565b`: `onecoreuap\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x1800556c9`: `onecoreuap\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`

## pseudocode

```c
__int64 __fastcall GetSidStringFromToken(HANDLE TokenHandle, LPWSTR *StringSid)
{
  const char *v4; // r9
  PSID *v6; // rdi
  unsigned int LastError; // ebx
  const char *v8; // r9
  __int64 v9; // rdx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SIZE_T cb; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(cb) = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&cb) && GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1F,
             (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
             v4);
  v6 = (PSID *)CoTaskMemAlloc((unsigned int)cb);
  if ( v6 )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, v6, cb, (PDWORD)&cb) )
    {
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(StringSid);
      StringSid[1] = (LPWSTR)-1LL;
      StringSid[2] = (LPWSTR)-1LL;
      if ( ConvertSidToStringSidW(*v6, StringSid) )
      {
        LastError = 0;
        goto LABEL_12;
      }
      v9 = 36;
    }
    else
    {
      v9 = 35;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
                  v8);
LABEL_12:
    CoTaskMemFree(v6);
    return LastError;
  }
  LastError = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x22,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
    (const char *)0x8007000ELL,
    ReturnLength);
  return LastError;
}

```

## disassembly

```asm
0x1800555e4  mov     rax, rsp
0x1800555e7  mov     [rax+8], rbx
0x1800555eb  mov     [rax+10h], rsi
0x1800555ef  push    rdi
0x1800555f0  sub     rsp, 30h
0x1800555f4  xor     r9d, r9d; TokenInformationLength
0x1800555f7  mov     dword ptr [rax+18h], 0
0x1800555fe  mov     rbx, rdx
0x180055601  lea     rax, [rax+18h]
0x180055605  xor     r8d, r8d; TokenInformation
0x180055608  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18005560d  mov     rsi, rcx
0x180055610  lea     edx, [r9+1]; TokenInformationClass
0x180055614  call    cs:__imp_GetTokenInformation
0x18005561a  test    eax, eax
0x18005561c  jnz     short loc_180055644
0x18005561e  call    cs:__imp_GetLastError
0x180055624  cmp     eax, 7Ah ; 'z'
0x180055627  jz      short loc_180055644
0x180055629  mov     rcx, [rsp+38h]; this
0x18005562e  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180055635  mov     edx, 1Fh; void *
0x18005563a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005563f  jmp     loc_1800556E6
0x180055644  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x180055648  call    cs:__imp_CoTaskMemAlloc
0x18005564e  mov     rdi, rax
0x180055651  test    rax, rax
0x180055654  jnz     short loc_180055674
0x180055656  mov     rcx, [rsp+38h]; this
0x18005565b  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180055662  mov     ebx, 8007000Eh
0x180055667  lea     edx, [rax+22h]; void *
0x18005566a  mov     r9d, ebx; char *
0x18005566d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055672  jmp     short loc_1800556E4
0x180055674  mov     r9d, dword ptr [rsp+38h+cb]; TokenInformationLength
0x180055679  lea     rax, [rsp+38h+cb]
0x18005567e  mov     r8, rdi; TokenInformation
0x180055681  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180055686  mov     edx, 1; TokenInformationClass
0x18005568b  mov     rcx, rsi; TokenHandle
0x18005568e  call    cs:__imp_GetTokenInformation
0x180055694  test    eax, eax
0x180055696  jnz     short loc_18005569D
0x180055698  lea     edx, [rax+23h]
0x18005569b  jmp     short loc_1800556C4
0x18005569d  mov     rcx, rbx
0x1800556a0  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1800556a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800556a9  mov     rdx, rbx; StringSid
0x1800556ac  mov     [rbx+8], rax
0x1800556b0  mov     [rbx+10h], rax
0x1800556b4  mov     rcx, [rdi]; Sid
0x1800556b7  call    cs:__imp_ConvertSidToStringSidW
0x1800556bd  test    eax, eax
0x1800556bf  jnz     short loc_1800556D9
0x1800556c1  lea     edx, [rax+24h]; void *
0x1800556c4  mov     rcx, [rsp+38h]; this
0x1800556c9  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800556d0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800556d5  mov     ebx, eax
0x1800556d7  jmp     short loc_1800556DB
0x1800556d9  xor     ebx, ebx
0x1800556db  mov     rcx, rdi; pv
0x1800556de  call    cs:__imp_CoTaskMemFree
0x1800556e4  mov     eax, ebx
0x1800556e6  mov     rbx, [rsp+38h+arg_0]
0x1800556eb  mov     rsi, [rsp+38h+arg_8]
0x1800556f0  add     rsp, 30h
0x1800556f4  pop     rdi
0x1800556f5  retn
```
