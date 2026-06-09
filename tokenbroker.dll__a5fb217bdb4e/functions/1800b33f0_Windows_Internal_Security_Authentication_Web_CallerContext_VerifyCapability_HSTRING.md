# Windows::Internal::Security::Authentication::Web::CallerContext::VerifyCapability(HSTRING__ *)

- ea: `0x1800b33f0`
- end: `0x1800b34bb`
- name: `?VerifyCapability@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBAJPEAUHSTRING__@@@Z`
- size: `203`
- prototype: `int(Windows::Internal::Security::Authentication::Web::CallerContext *__hidden this, HSTRING)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ef40`
- `0x18005aa84`
- `0x18007f458`
- `0x1800a6a30`
- `0x1800a7600`
- `0x1800aef20`

## callees

- `0x18000bd40`
- `0x18002fbf0`
- `0x1800b33f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b3444`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b3444`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b345b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b345b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3479`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3479`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800b3463`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800b3463`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800b3418`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800b3418`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x1800b348c`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x1800b348c`

## string_xrefs

- `0x1800b342c`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CallerContext::VerifyCapability(
        Windows::Internal::Security::Authentication::Web::CallerContext *this,
        HSTRING a2)
{
  __int64 v3; // rdx
  HANDLE CurrentThread; // rax
  BOOL v6; // ebx
  PCWSTR StringRawBuffer; // rax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v10; // [rsp+40h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+20h] BYREF

  TokenHandle = 0;
  v10 = 0;
  if ( Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(this) )
  {
    if ( CoImpersonateClient() < 0 )
    {
      v3 = 273;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v3,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
        (const char *)0x80070005LL,
        v8);
      return 2147942405LL;
    }
    CurrentThread = GetCurrentThread();
    v6 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
    CoRevertToSelf();
    if ( !v6 )
    {
      v3 = 288;
      goto LABEL_4;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    if ( (int)CapabilityCheck(TokenHandle, StringRawBuffer, &v10) < 0 )
    {
      v3 = 298;
      goto LABEL_4;
    }
    if ( !v10 )
    {
      v3 = 303;
      goto LABEL_4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800b33f0  mov     [rsp+arg_0], rbx
0x1800b33f5  push    rdi; int
0x1800b33f6  sub     rsp, 20h
0x1800b33fa  mov     rdi, rdx
0x1800b33fd  mov     [rsp+28h+TokenHandle], 0
0x1800b3406  mov     [rsp+28h+arg_10], 0
0x1800b340b  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x1800b3410  test    al, al
0x1800b3412  jz      loc_1800B34AE
0x1800b3418  call    cs:__imp_CoImpersonateClient
0x1800b341e  test    eax, eax
0x1800b3420  jns     short loc_1800B3444
0x1800b3422  mov     edx, 111h; void *
0x1800b3427  mov     rcx, [rsp+28h]; this
0x1800b342c  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\tokenbroker\\inc"...
0x1800b3433  mov     ebx, 80070005h
0x1800b3438  mov     r9d, ebx; char *
0x1800b343b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3440  mov     eax, ebx
0x1800b3442  jmp     short loc_1800B34B0
0x1800b3444  call    cs:__imp_GetCurrentThread
0x1800b344a  mov     edx, 8; DesiredAccess
0x1800b344f  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800b3454  mov     rcx, rax; ThreadHandle
0x1800b3457  lea     r8d, [rdx-7]; OpenAsSelf
0x1800b345b  call    cs:__imp_OpenThreadToken
0x1800b3461  mov     ebx, eax
0x1800b3463  call    cs:__imp_CoRevertToSelf
0x1800b3469  test    ebx, ebx
0x1800b346b  jnz     short loc_1800B3474
0x1800b346d  mov     edx, 120h
0x1800b3472  jmp     short loc_1800B3427
0x1800b3474  xor     edx, edx; length
0x1800b3476  mov     rcx, rdi; string
0x1800b3479  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b347f  mov     rcx, [rsp+28h+TokenHandle]
0x1800b3484  lea     r8, [rsp+28h+arg_10]
0x1800b3489  mov     rdx, rax
0x1800b348c  call    cs:__imp_CapabilityCheck
0x1800b3492  test    eax, eax
0x1800b3494  jns     short loc_1800B349D
0x1800b3496  mov     edx, 12Ah
0x1800b349b  jmp     short loc_1800B3427
0x1800b349d  cmp     [rsp+28h+arg_10], 0
0x1800b34a2  jnz     short loc_1800B34AE
0x1800b34a4  mov     edx, 12Fh
0x1800b34a9  jmp     loc_1800B3427
0x1800b34ae  xor     eax, eax
0x1800b34b0  mov     rbx, [rsp+28h+arg_0]
0x1800b34b5  add     rsp, 20h
0x1800b34b9  pop     rdi
0x1800b34ba  retn
```
