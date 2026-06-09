# GetSidStringFromToken

- ea: `0x18006c4c8`
- end: `0x18006c5de`
- name: `GetSidStringFromToken`
- size: `278`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPWSTR *StringSid)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006c0a0`
- `0x18006c114`
- `0x18010ac64`

## callees

- `0x18006c4c8`
- `0x18006c944`
- `0x1800e2988`
- `0x1800e34bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c502`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006c4f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006c539`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006c4f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006c539`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c55c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c55c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006c511`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006c511`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006c5c6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006c5c6`

## string_xrefs

- `0x18006c54b`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x18006c56b`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x18006c591`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`

## pseudocode

```c
__int64 __fastcall GetSidStringFromToken(HANDLE TokenHandle, LPWSTR *StringSid)
{
  const char *v4; // r9
  PSID *v5; // rdi
  const char *v6; // r9
  __int64 v7; // rdx
  unsigned int LastError; // ebx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SIZE_T cb; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(cb) = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&cb) || GetLastError() == 122 )
  {
    v5 = (PSID *)CoTaskMemAlloc((unsigned int)cb);
    if ( !v5 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
        (const char *)0x8007000ELL,
        ReturnLength);
      return LastError;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v5, cb, (PDWORD)&cb) )
    {
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Free(StringSid);
      StringSid[1] = (LPWSTR)-1LL;
      StringSid[2] = (LPWSTR)-1LL;
      if ( ConvertSidToStringSidW(*v5, StringSid) )
      {
        LastError = 0;
        goto LABEL_7;
      }
      v7 = 34;
    }
    else
    {
      v7 = 33;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v7,
                  (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
                  v6);
LABEL_7:
    CoTaskMemFree(v5);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x1D,
           (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
           v4);
}

```

## disassembly

```asm
0x18006c4c8  mov     rax, rsp
0x18006c4cb  mov     [rax+8], rbx
0x18006c4cf  mov     [rax+10h], rsi
0x18006c4d3  push    rdi
0x18006c4d4  sub     rsp, 30h
0x18006c4d8  xor     r9d, r9d; TokenInformationLength
0x18006c4db  mov     dword ptr [rax+18h], 0
0x18006c4e2  mov     rbx, rdx
0x18006c4e5  lea     rax, [rax+18h]
0x18006c4e9  xor     r8d, r8d; TokenInformation
0x18006c4ec  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18006c4f1  mov     rsi, rcx
0x18006c4f4  lea     edx, [r9+1]; TokenInformationClass
0x18006c4f8  call    cs:__imp_GetTokenInformation
0x18006c4fe  test    eax, eax
0x18006c500  jnz     short loc_18006C50D
0x18006c502  call    cs:__imp_GetLastError
0x18006c508  cmp     eax, 7Ah ; 'z'
0x18006c50b  jnz     short loc_18006C566
0x18006c50d  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x18006c511  call    cs:__imp_CoTaskMemAlloc
0x18006c517  mov     rdi, rax
0x18006c51a  test    rax, rax
0x18006c51d  jz      short loc_18006C58C
0x18006c51f  mov     r9d, dword ptr [rsp+38h+cb]; TokenInformationLength
0x18006c524  lea     rax, [rsp+38h+cb]
0x18006c529  mov     r8, rdi; TokenInformation
0x18006c52c  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18006c531  mov     edx, 1; TokenInformationClass
0x18006c536  mov     rcx, rsi; TokenHandle
0x18006c539  call    cs:__imp_GetTokenInformation
0x18006c53f  test    eax, eax
0x18006c541  jnz     short loc_18006C5AC
0x18006c543  lea     edx, [rax+21h]; void *
0x18006c546  mov     rcx, [rsp+38h]; this
0x18006c54b  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x18006c552  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006c557  mov     ebx, eax
0x18006c559  mov     rcx, rdi; pv
0x18006c55c  call    cs:__imp_CoTaskMemFree
0x18006c562  mov     eax, ebx
0x18006c564  jmp     short loc_18006C57C
0x18006c566  mov     rcx, [rsp+38h]; this
0x18006c56b  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x18006c572  mov     edx, 1Dh; void *
0x18006c577  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006c57c  mov     rbx, [rsp+38h+arg_0]
0x18006c581  mov     rsi, [rsp+38h+arg_8]
0x18006c586  add     rsp, 30h
0x18006c58a  pop     rdi
0x18006c58b  retn
0x18006c58c  mov     rcx, [rsp+38h]; this
0x18006c591  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x18006c598  mov     ebx, 8007000Eh
0x18006c59d  mov     edx, 20h ; ' '; void *
0x18006c5a2  mov     r9d, ebx; char *
0x18006c5a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c5aa  jmp     short loc_18006C562
0x18006c5ac  mov     rcx, rbx
0x18006c5af  call    ?_Free@?$NativeString@V?$LocalMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Free(void)
0x18006c5b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006c5b8  mov     rdx, rbx; StringSid
0x18006c5bb  mov     [rbx+8], rax
0x18006c5bf  mov     [rbx+10h], rax
0x18006c5c3  mov     rcx, [rdi]; Sid
0x18006c5c6  call    cs:__imp_ConvertSidToStringSidW
0x18006c5cc  test    eax, eax
0x18006c5ce  jz      short loc_18006C5D4
0x18006c5d0  xor     ebx, ebx
0x18006c5d2  jmp     short loc_18006C559
0x18006c5d4  mov     edx, 22h ; '"'
0x18006c5d9  jmp     loc_18006C546
```
