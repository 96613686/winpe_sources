# wil::get_token_is_app_container_nothrow(void *,bool &)

- ea: `0x18002b0ac`
- end: `0x18002b123`
- name: `?get_token_is_app_container_nothrow@wil@@YAJPEAXAEA_N@Z`
- size: `119`
- prototype: `__int64 __fastcall(wil *__hidden this, void *, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010490`
- `0x180011bf0`

## callees

- `0x180020f6c`
- `0x18002b0ac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b0e8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002b0e8`

## string_xrefs

- `0x18002b0fd`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x18002b0ac  mov     rax, rsp
0x18002b0af  mov     [rax+8], rcx
0x18002b0b3  push    rbx
0x18002b0b4  sub     rsp, 30h
0x18002b0b8  mov     r9d, 4; TokenInformationLength
0x18002b0be  mov     dword ptr [rax+8], 0
0x18002b0c5  mov     dword ptr [rax+18h], 0
0x18002b0cc  lea     rax, [rax+18h]
0x18002b0d0  mov     rbx, rdx
0x18002b0d3  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002b0d8  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18002b0dd  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18002b0e4  lea     edx, [r9+19h]; TokenInformationClass
0x18002b0e8  call    cs:__imp_GetTokenInformation
0x18002b0ef  nop     dword ptr [rax+rax+00h]
0x18002b0f4  test    eax, eax
0x18002b0f6  jnz     short loc_18002B110
0x18002b0f8  mov     rcx, [rsp+38h]; this
0x18002b0fd  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b104  mov     edx, 298h; void *
0x18002b109  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b10e  jmp     short loc_18002B11C
0x18002b110  cmp     [rsp+38h+TokenInformation], 0
0x18002b115  setnz   al
0x18002b118  mov     [rbx], al
0x18002b11a  xor     eax, eax
0x18002b11c  add     rsp, 30h
0x18002b120  pop     rbx
0x18002b121  retn
```
