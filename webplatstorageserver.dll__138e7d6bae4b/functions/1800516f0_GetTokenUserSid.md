# GetTokenUserSid

- ea: `0x1800516f0`
- end: `0x1800517b5`
- name: `GetTokenUserSid`
- size: `197`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID pDestinationSid)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800514b4`
- `0x1800574a4`

## callees

- `0x1800245f0`
- `0x1800516f0`
- `0x180063500`
- `0x180080fb0`
- `0x180081b40`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180051783`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180051783`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180051749`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180051749`

## string_xrefs

- `0x18005175e`: `onecoreuap\inetcore\webplatstorageserver\dll\broker.cpp`

## pseudocode

```c
__int64 __fastcall GetTokenUserSid(HANDLE TokenHandle, PSID pDestinationSid)
{
  const char *v4; // r9
  __int64 v5; // rdx
  void *v7; // rbx
  DWORD v8; // eax
  DWORD ReturnLength[4]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength[0] = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, ReturnLength) )
  {
    v5 = 24;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\dll\\broker.cpp",
             v4);
  }
  v7 = (void *)TokenInformation[0];
  v8 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(68);
  if ( !CopySid(v8, pDestinationSid, v7) )
  {
    v5 = 26;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\dll\\broker.cpp",
             v4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800516f0  mov     [rsp+arg_10], rbx
0x1800516f5  push    rdi
0x1800516f6  sub     rsp, 0B0h
0x1800516fd  mov     rax, cs:__security_cookie
0x180051704  xor     rax, rsp
0x180051707  mov     [rsp+0B8h+var_18], rax
0x18005170f  mov     rdi, rdx
0x180051712  mov     rbx, rcx
0x180051715  xor     edx, edx; Val
0x180051717  lea     rcx, [rsp+0B8h+TokenInformation]; void *
0x18005171c  lea     r8d, [rdx+58h]; Size
0x180051720  call    memset_0
0x180051725  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18005172b  mov     [rsp+0B8h+var_88], 0
0x180051733  lea     rax, [rsp+0B8h+var_88]
0x180051738  mov     rcx, rbx; TokenHandle
0x18005173b  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180051740  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180051745  lea     edx, [r9-57h]; TokenInformationClass
0x180051749  call    cs:__imp_GetTokenInformation
0x18005174f  test    eax, eax
0x180051751  jnz     short loc_18005176C
0x180051753  lea     edx, [rax+18h]; void *
0x180051756  mov     rcx, [rsp+0B8h]; this
0x18005175e  lea     r8, aOnecoreuapInet_26; "onecoreuap\\inetcore\\webplatstorageser"...
0x180051765  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005176a  jmp     short loc_180051794
0x18005176c  mov     rbx, [rsp+0B8h+TokenInformation]
0x180051771  mov     ecx, 44h ; 'D'
0x180051776  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18005177b  mov     r8, rbx; pSourceSid
0x18005177e  mov     rdx, rdi; pDestinationSid
0x180051781  mov     ecx, eax; nDestinationSidLength
0x180051783  call    cs:__imp_CopySid
0x180051789  test    eax, eax
0x18005178b  jnz     short loc_180051792
0x18005178d  lea     edx, [rax+1Ah]
0x180051790  jmp     short loc_180051756
0x180051792  xor     eax, eax
0x180051794  mov     rcx, [rsp+0B8h+var_18]
0x18005179c  xor     rcx, rsp; StackCookie
0x18005179f  call    __security_check_cookie
0x1800517a4  mov     rbx, [rsp+0B8h+arg_10]
0x1800517ac  add     rsp, 0B0h
0x1800517b3  pop     rdi
0x1800517b4  retn
```
