# wil::get_token_is_app_container_nothrow(void *,bool &)

- ea: `0x1800294a0`
- end: `0x180029510`
- name: `?get_token_is_app_container_nothrow@wil@@YAJPEAXAEA_N@Z`
- size: `112`
- prototype: `__int64 __fastcall(wil *__hidden this, void *, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f950`
- `0x180010c30`

## callees

- `0x18001f89c`
- `0x1800294a0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800294dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800294dc`

## string_xrefs

- `0x1800294eb`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_is_app_container_nothrow(wil *this, bool *a2, bool *a3)
{
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  int v8; // [rsp+44h] [rbp+Ch]
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  v8 = HIDWORD(this);
  TokenInformation = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x298,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v4);
  *a2 = TokenInformation != 0;
  return 0;
}

```

## disassembly

```asm
0x1800294a0  mov     rax, rsp
0x1800294a3  mov     [rax+8], rcx
0x1800294a7  push    rbx
0x1800294a8  sub     rsp, 30h
0x1800294ac  mov     r9d, 4; TokenInformationLength
0x1800294b2  mov     dword ptr [rax+8], 0
0x1800294b9  mov     dword ptr [rax+18h], 0
0x1800294c0  lea     rax, [rax+18h]
0x1800294c4  mov     rbx, rdx
0x1800294c7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800294cc  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800294d1  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800294d8  lea     edx, [r9+19h]; TokenInformationClass
0x1800294dc  call    cs:__imp_GetTokenInformation
0x1800294e2  test    eax, eax
0x1800294e4  jnz     short loc_1800294FE
0x1800294e6  mov     rcx, [rsp+38h]; this
0x1800294eb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800294f2  mov     edx, 298h; void *
0x1800294f7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800294fc  jmp     short loc_18002950A
0x1800294fe  cmp     [rsp+38h+TokenInformation], 0
0x180029503  setnz   al
0x180029506  mov     [rbx], al
0x180029508  xor     eax, eax
0x18002950a  add     rsp, 30h
0x18002950e  pop     rbx
0x18002950f  retn
```
