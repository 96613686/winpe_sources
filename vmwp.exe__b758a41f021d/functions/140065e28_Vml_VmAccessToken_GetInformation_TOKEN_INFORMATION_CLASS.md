# Vml::VmAccessToken::_GetInformation(_TOKEN_INFORMATION_CLASS)

- ea: `0x140065e28`
- end: `0x140065f15`
- name: `?_GetInformation@VmAccessToken@Vml@@AEBAPEAXW4_TOKEN_INFORMATION_CLASS@@@Z`
- size: `237`
- prototype: `void *__fastcall(Vml::VmAccessToken *__hidden this, enum _TOKEN_INFORMATION_CLASS)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14006570c`

## callees

- `0x140065e28`
- `0x140083990`
- `0x14011ea40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140065e88`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140065e88`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140065e73`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140065ed2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140065e73`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140065ed2`

## string_xrefs

- `0x140065ee7`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140065ea1`: `onecore\vm\common\vml\VmMemory.h`

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
0x140065e28  mov     r11, rsp
0x140065e2b  mov     [r11+10h], rbx
0x140065e2f  push    rdi
0x140065e30  sub     rsp, 50h
0x140065e34  mov     rax, cs:__security_cookie
0x140065e3b  xor     rax, rsp
0x140065e3e  mov     [rsp+58h+var_10], rax
0x140065e43  mov     rdi, rcx
0x140065e46  xorps   xmm0, xmm0
0x140065e49  movups  [rsp+58h+var_28], xmm0
0x140065e4e  mov     qword ptr [r11-28h], 0
0x140065e56  mov     dword ptr [rsp+58h+uBytes], 0
0x140065e5e  lea     rax, [r11-18h]
0x140065e62  mov     [r11-38h], rax
0x140065e66  xor     r9d, r9d; TokenInformationLength
0x140065e69  xor     r8d, r8d; TokenInformation
0x140065e6c  lea     edx, [r9+1]; TokenInformationClass
0x140065e70  mov     rcx, [rcx]; TokenHandle
0x140065e73  call    cs:__imp_GetTokenInformation
0x140065e7a  nop     dword ptr [rax+rax+00h]
0x140065e7f  mov     edx, dword ptr [rsp+58h+uBytes]; uBytes
0x140065e83  mov     ecx, 40h ; '@'; uFlags
0x140065e88  call    cs:__imp_LocalAlloc
0x140065e8f  nop     dword ptr [rax+rax+00h]
0x140065e94  mov     rbx, rax
0x140065e97  test    rax, rax
0x140065e9a  jnz     short loc_140065EB3
0x140065e9c  mov     rcx, [rsp+58h]; this
0x140065ea1  lea     r8, aOnecoreVmCommo_35; "onecore\\vm\\common\\vml\\VmMemory.h"
0x140065ea8  mov     edx, 355h; void *
0x140065ead  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140065eb3  mov     qword ptr [rsp+58h+var_28], rbx
0x140065eb8  lea     rax, [rsp+58h+uBytes]
0x140065ebd  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x140065ec2  mov     r9d, dword ptr [rsp+58h+uBytes]; TokenInformationLength
0x140065ec7  mov     r8, rbx; TokenInformation
0x140065eca  mov     edx, 1; TokenInformationClass
0x140065ecf  mov     rcx, [rdi]; TokenHandle
0x140065ed2  call    cs:__imp_GetTokenInformation
0x140065ed9  nop     dword ptr [rax+rax+00h]
0x140065ede  mov     rcx, [rsp+58h]; this
0x140065ee3  test    eax, eax
0x140065ee5  jnz     short loc_140065EF9
0x140065ee7  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140065eee  mov     edx, 199Ch; void *
0x140065ef3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140065ef9  mov     rax, rbx
0x140065efc  mov     rcx, [rsp+58h+var_10]
0x140065f01  xor     rcx, rsp; StackCookie
0x140065f04  call    __security_check_cookie
0x140065f09  mov     rbx, [rsp+58h+arg_8]
0x140065f0e  add     rsp, 50h
0x140065f12  pop     rdi
0x140065f13  retn
```
