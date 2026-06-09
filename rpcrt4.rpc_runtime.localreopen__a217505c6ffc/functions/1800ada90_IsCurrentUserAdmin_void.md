# IsCurrentUserAdmin(void)

- ea: `0x1800ada90`
- end: `0x1800adb6c`
- name: `?IsCurrentUserAdmin@@YAJXZ`
- size: `220`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008f718`

## callees

- `0x1800ada90`
- `0x1800ceda0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800adb3c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800adb3c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800adb10`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800adb10`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800adaf6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800adaf6`

## pseudocode

```c
__int64 IsCurrentUserAdmin(void)
{
  unsigned int v0; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) || (v0 = 0, !IsMember) )
      v0 = 5;
  }
  else
  {
    v0 = 14;
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v0;
}

```

## disassembly

```asm
0x1800ada90  mov     [rsp-8+arg_0], rbx
0x1800ada95  mov     [rsp-8+arg_8], rdi
0x1800ada9a  push    rbp
0x1800ada9b  mov     rbp, rsp
0x1800ada9e  sub     rsp, 80h
0x1800adaa5  mov     rax, cs:__security_cookie
0x1800adaac  xor     rax, rsp
0x1800adaaf  mov     [rbp+var_8], rax
0x1800adab3  xor     edi, edi
0x1800adab5  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800adabb  lea     rax, [rbp+SidToCheck]
0x1800adabf  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x1800adac2  mov     [rsp+80h+pSid], rax; pSid
0x1800adac7  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800adacb  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x1800adacf  mov     r9d, 220h; nSubAuthority1
0x1800adad5  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x1800adad9  lea     r8d, [rdi+20h]; nSubAuthority0
0x1800adadd  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x1800adae1  mov     dl, 2; nSubAuthorityCount
0x1800adae3  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x1800adae7  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x1800adaeb  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x1800adaef  mov     [rbp+SidToCheck], rdi
0x1800adaf3  mov     [rbp+IsMember], edi
0x1800adaf6  call    cs:__imp_AllocateAndInitializeSid
0x1800adafd  nop     dword ptr [rax+rax+00h]
0x1800adb02  test    eax, eax
0x1800adb04  jz      short loc_1800ADB2E
0x1800adb06  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1800adb0a  lea     r8, [rbp+IsMember]; IsMember
0x1800adb0e  xor     ecx, ecx; TokenHandle
0x1800adb10  call    cs:__imp_CheckTokenMembership
0x1800adb17  nop     dword ptr [rax+rax+00h]
0x1800adb1c  test    eax, eax
0x1800adb1e  jz      short loc_1800ADB27
0x1800adb20  mov     ebx, edi
0x1800adb22  cmp     [rbp+IsMember], edi
0x1800adb25  jnz     short loc_1800ADB33
0x1800adb27  mov     ebx, 5
0x1800adb2c  jmp     short loc_1800ADB33
0x1800adb2e  mov     ebx, 0Eh
0x1800adb33  mov     rcx, [rbp+SidToCheck]; pSid
0x1800adb37  test    rcx, rcx
0x1800adb3a  jz      short loc_1800ADB48
0x1800adb3c  call    cs:__imp_FreeSid
0x1800adb43  nop     dword ptr [rax+rax+00h]
0x1800adb48  mov     eax, ebx
0x1800adb4a  mov     rcx, [rbp+var_8]
0x1800adb4e  xor     rcx, rsp; StackCookie
0x1800adb51  call    __security_check_cookie
0x1800adb56  lea     r11, [rsp+80h+var_s0]
0x1800adb5e  mov     rbx, [r11+10h]
0x1800adb62  mov     rdi, [r11+18h]
0x1800adb66  mov     rsp, r11
0x1800adb69  pop     rbp
0x1800adb6a  retn
```
