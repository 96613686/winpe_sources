# IsLocalSystemOnly

- ea: `0x18003cd30`
- end: `0x18003ce25`
- name: `IsLocalSystemOnly`
- size: `245`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180026d60`

## callees

- `0x180001600`
- `0x18002c8d4`
- `0x180038ca8`
- `0x18003cd30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003cdb9`
- `KERNEL32!GetLastError` at `0x18003cdb9`
- `ADVAPI32!FreeSid` at `0x18003cdf9`
- `ADVAPI32!FreeSid` at `0x18003cdf9`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18003cdaf`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18003cdaf`
- `ADVAPI32!EqualSid` at `0x18003cdd7`
- `ADVAPI32!EqualSid` at `0x18003cdd7`

## pseudocode

```c
__int64 __fastcall IsLocalSystemOnly(void *a1)
{
  int TokenUser; // eax
  PSID *v2; // rdi
  unsigned int v3; // ebx
  signed int LastError; // eax
  PSID pSid1; // [rsp+60h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid1 = 0;
  lpMem = 0;
  TokenUser = GetTokenUser(a1, (struct _TOKEN_USER **)&lpMem);
  v2 = (PSID *)lpMem;
  v3 = TokenUser;
  if ( TokenUser >= 0 )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid1) )
    {
      if ( !EqualSid(pSid1, *v2) )
        v3 = 1;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( v2 )
    ServerFree(v2);
  if ( pSid1 )
    FreeSid(pSid1);
  return v3;
}

```

## disassembly

```asm
0x18003cd30  mov     [rsp-18h+arg_8], rbx
0x18003cd35  mov     [rsp-18h+arg_10], rsi
0x18003cd3a  push    rbp
0x18003cd3b  push    rdi
0x18003cd3c  push    r14
0x18003cd3e  mov     rbp, rsp
0x18003cd41  sub     rsp, 80h
0x18003cd48  mov     rax, cs:__security_cookie
0x18003cd4f  xor     rax, rsp
0x18003cd52  mov     [rbp+var_8], rax
0x18003cd56  xor     esi, esi
0x18003cd58  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18003cd5e  lea     rdx, [rbp+lpMem]; struct _TOKEN_USER **
0x18003cd62  mov     dword ptr [rbp+pIdentifierAuthority.Value], esi
0x18003cd65  mov     [rbp+pSid1], rsi
0x18003cd69  mov     [rbp+lpMem], rsi
0x18003cd6d  call    ?GetTokenUser@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenUser(void *,_TOKEN_USER * *)
0x18003cd72  mov     rdi, [rbp+lpMem]
0x18003cd76  mov     ebx, eax
0x18003cd78  test    eax, eax
0x18003cd7a  js      short loc_18003CDE3
0x18003cd7c  lea     rax, [rbp+pSid1]
0x18003cd80  xor     r9d, r9d; nSubAuthority1
0x18003cd83  mov     [rsp+80h+pSid], rax; pSid
0x18003cd88  lea     r14d, [rsi+1]
0x18003cd8c  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x18003cd90  lea     r8d, [rsi+12h]; nSubAuthority0
0x18003cd94  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x18003cd98  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18003cd9c  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x18003cda0  mov     dl, r14b; nSubAuthorityCount
0x18003cda3  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x18003cda7  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x18003cdab  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x18003cdaf  call    cs:__imp_AllocateAndInitializeSid
0x18003cdb5  test    eax, eax
0x18003cdb7  jnz     short loc_18003CDD0
0x18003cdb9  call    cs:__imp_GetLastError
0x18003cdbf  mov     ebx, eax
0x18003cdc1  test    eax, eax
0x18003cdc3  jle     short loc_18003CDE3
0x18003cdc5  movzx   ebx, ax
0x18003cdc8  or      ebx, 80070000h
0x18003cdce  jmp     short loc_18003CDE3
0x18003cdd0  mov     rdx, [rdi]; pSid2
0x18003cdd3  mov     rcx, [rbp+pSid1]; pSid1
0x18003cdd7  call    cs:__imp_EqualSid
0x18003cddd  test    eax, eax
0x18003cddf  cmovz   ebx, r14d
0x18003cde3  test    rdi, rdi
0x18003cde6  jz      short loc_18003CDF0
0x18003cde8  mov     rcx, rdi; lpMem
0x18003cdeb  call    ServerFree
0x18003cdf0  mov     rcx, [rbp+pSid1]; pSid
0x18003cdf4  test    rcx, rcx
0x18003cdf7  jz      short loc_18003CDFF
0x18003cdf9  call    cs:__imp_FreeSid
0x18003cdff  mov     eax, ebx
0x18003ce01  mov     rcx, [rbp+var_8]
0x18003ce05  xor     rcx, rsp; StackCookie
0x18003ce08  call    __security_check_cookie
0x18003ce0d  lea     r11, [rsp+80h+var_s0]
0x18003ce15  mov     rbx, [r11+28h]
0x18003ce19  mov     rsi, [r11+30h]
0x18003ce1d  mov     rsp, r11
0x18003ce20  pop     r14
0x18003ce22  pop     rdi
0x18003ce23  pop     rbp
0x18003ce24  retn
```
