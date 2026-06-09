# Vml::VmAccessToken::_GetInformation(_TOKEN_INFORMATION_CLASS)

- ea: `0x1400c41bc`
- end: `0x1400c42a9`
- name: `?_GetInformation@VmAccessToken@Vml@@AEBAPEAXW4_TOKEN_INFORMATION_CLASS@@@Z`
- size: `237`
- prototype: `void *__fastcall(Vml::VmAccessToken *__hidden this, enum _TOKEN_INFORMATION_CLASS)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400c3aa0`

## callees

- `0x14005b648`
- `0x1400c41bc`
- `0x140132960`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400c421c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400c421c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400c4207`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400c4266`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400c4207`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400c4266`

## string_xrefs

- `0x1400c427b`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400c4235`: `onecore\vm\common\vml\VmMemory.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HLOCAL __fastcall Vml::VmAccessToken::_GetInformation(HANDLE *this, enum _TOKEN_INFORMATION_CLASS a2)
{
  HLOCAL v3; // rax
  const char *v4; // r9
  HLOCAL v5; // rbx
  const char *v6; // r9
  SIZE_T uBytes; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  LODWORD(uBytes) = 0;
  GetTokenInformation(*this, TokenUser, 0, 0, (PDWORD)&uBytes);
  v3 = LocalAlloc(0x40u, (unsigned int)uBytes);
  v5 = v3;
  if ( !v3 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x355,
      (unsigned int)"onecore\\vm\\common\\vml\\VmMemory.h",
      v4);
  if ( !GetTokenInformation(*this, TokenUser, v3, uBytes, (PDWORD)&uBytes) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x199C,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v6);
  return v5;
}

```

## disassembly

```asm
0x1400c41bc  mov     r11, rsp
0x1400c41bf  mov     [r11+10h], rbx
0x1400c41c3  push    rdi
0x1400c41c4  sub     rsp, 50h
0x1400c41c8  mov     rax, cs:__security_cookie
0x1400c41cf  xor     rax, rsp
0x1400c41d2  mov     [rsp+58h+var_10], rax
0x1400c41d7  mov     rdi, rcx
0x1400c41da  xorps   xmm0, xmm0
0x1400c41dd  movups  [rsp+58h+var_28], xmm0
0x1400c41e2  mov     qword ptr [r11-28h], 0
0x1400c41ea  mov     dword ptr [rsp+58h+uBytes], 0
0x1400c41f2  lea     rax, [r11-18h]
0x1400c41f6  mov     [r11-38h], rax
0x1400c41fa  xor     r9d, r9d; TokenInformationLength
0x1400c41fd  xor     r8d, r8d; TokenInformation
0x1400c4200  lea     edx, [r9+1]; TokenInformationClass
0x1400c4204  mov     rcx, [rcx]; TokenHandle
0x1400c4207  call    cs:__imp_GetTokenInformation
0x1400c420e  nop     dword ptr [rax+rax+00h]
0x1400c4213  mov     edx, dword ptr [rsp+58h+uBytes]; uBytes
0x1400c4217  mov     ecx, 40h ; '@'; uFlags
0x1400c421c  call    cs:__imp_LocalAlloc
0x1400c4223  nop     dword ptr [rax+rax+00h]
0x1400c4228  mov     rbx, rax
0x1400c422b  test    rax, rax
0x1400c422e  jnz     short loc_1400C4247
0x1400c4230  mov     rcx, [rsp+58h]; this
0x1400c4235  lea     r8, aOnecoreVmCommo_36; "onecore\\vm\\common\\vml\\VmMemory.h"
0x1400c423c  mov     edx, 355h; void *
0x1400c4241  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c4247  mov     qword ptr [rsp+58h+var_28], rbx
0x1400c424c  lea     rax, [rsp+58h+uBytes]
0x1400c4251  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1400c4256  mov     r9d, dword ptr [rsp+58h+uBytes]; TokenInformationLength
0x1400c425b  mov     r8, rbx; TokenInformation
0x1400c425e  mov     edx, 1; TokenInformationClass
0x1400c4263  mov     rcx, [rdi]; TokenHandle
0x1400c4266  call    cs:__imp_GetTokenInformation
0x1400c426d  nop     dword ptr [rax+rax+00h]
0x1400c4272  mov     rcx, [rsp+58h]; this
0x1400c4277  test    eax, eax
0x1400c4279  jnz     short loc_1400C428D
0x1400c427b  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400c4282  mov     edx, 199Ch; void *
0x1400c4287  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c428d  mov     rax, rbx
0x1400c4290  mov     rcx, [rsp+58h+var_10]
0x1400c4295  xor     rcx, rsp; StackCookie
0x1400c4298  call    __security_check_cookie
0x1400c429d  mov     rbx, [rsp+58h+arg_8]
0x1400c42a2  add     rsp, 50h
0x1400c42a6  pop     rdi
0x1400c42a7  retn
```
