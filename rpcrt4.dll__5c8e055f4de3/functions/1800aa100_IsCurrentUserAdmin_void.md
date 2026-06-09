# IsCurrentUserAdmin(void)

- ea: `0x1800aa100`
- end: `0x1800aa1c9`
- name: `?IsCurrentUserAdmin@@YAJXZ`
- size: `201`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006d1e4`

## callees

- `0x1800aa100`
- `0x1800ca140`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800aa1a0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800aa1a0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800aa17a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800aa17a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800aa166`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800aa166`

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
0x1800aa100  mov     [rsp-8+arg_0], rbx
0x1800aa105  mov     [rsp-8+arg_8], rdi
0x1800aa10a  push    rbp
0x1800aa10b  mov     rbp, rsp
0x1800aa10e  sub     rsp, 80h
0x1800aa115  mov     rax, cs:__security_cookie
0x1800aa11c  xor     rax, rsp
0x1800aa11f  mov     [rbp+var_8], rax
0x1800aa123  xor     edi, edi
0x1800aa125  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800aa12b  lea     rax, [rbp+SidToCheck]
0x1800aa12f  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x1800aa132  mov     [rsp+80h+pSid], rax; pSid
0x1800aa137  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800aa13b  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x1800aa13f  mov     r9d, 220h; nSubAuthority1
0x1800aa145  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x1800aa149  lea     r8d, [rdi+20h]; nSubAuthority0
0x1800aa14d  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x1800aa151  mov     dl, 2; nSubAuthorityCount
0x1800aa153  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x1800aa157  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x1800aa15b  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x1800aa15f  mov     [rbp+SidToCheck], rdi
0x1800aa163  mov     [rbp+IsMember], edi
0x1800aa166  call    cs:__imp_AllocateAndInitializeSid
0x1800aa16c  test    eax, eax
0x1800aa16e  jz      short loc_1800AA192
0x1800aa170  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1800aa174  lea     r8, [rbp+IsMember]; IsMember
0x1800aa178  xor     ecx, ecx; TokenHandle
0x1800aa17a  call    cs:__imp_CheckTokenMembership
0x1800aa180  test    eax, eax
0x1800aa182  jz      short loc_1800AA18B
0x1800aa184  mov     ebx, edi
0x1800aa186  cmp     [rbp+IsMember], edi
0x1800aa189  jnz     short loc_1800AA197
0x1800aa18b  mov     ebx, 5
0x1800aa190  jmp     short loc_1800AA197
0x1800aa192  mov     ebx, 0Eh
0x1800aa197  mov     rcx, [rbp+SidToCheck]; pSid
0x1800aa19b  test    rcx, rcx
0x1800aa19e  jz      short loc_1800AA1A6
0x1800aa1a0  call    cs:__imp_FreeSid
0x1800aa1a6  mov     eax, ebx
0x1800aa1a8  mov     rcx, [rbp+var_8]
0x1800aa1ac  xor     rcx, rsp; StackCookie
0x1800aa1af  call    __security_check_cookie
0x1800aa1b4  lea     r11, [rsp+80h+var_s0]
0x1800aa1bc  mov     rbx, [r11+10h]
0x1800aa1c0  mov     rdi, [r11+18h]
0x1800aa1c4  mov     rsp, r11
0x1800aa1c7  pop     rbp
0x1800aa1c8  retn
```
