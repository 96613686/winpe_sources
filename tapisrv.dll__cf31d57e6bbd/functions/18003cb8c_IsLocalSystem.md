# IsLocalSystem

- ea: `0x18003cb8c`
- end: `0x18003cd2a`
- name: `IsLocalSystem`
- size: `414`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180026d60`
- `0x1800384f4`
- `0x1800390e4`

## callees

- `0x180001600`
- `0x18002c8d4`
- `0x180038ca8`
- `0x18003cb8c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003ccc1`
- `KERNEL32!GetLastError` at `0x18003ccc1`
- `ADVAPI32!FreeSid` at `0x18003ccec`
- `ADVAPI32!FreeSid` at `0x18003ccfb`
- `ADVAPI32!FreeSid` at `0x18003cd0a`
- `ADVAPI32!FreeSid` at `0x18003ccec`
- `ADVAPI32!FreeSid` at `0x18003ccfb`
- `ADVAPI32!FreeSid` at `0x18003cd0a`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18003cc0b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18003cc47`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18003cc7f`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18003cc0b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18003cc47`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18003cc7f`
- `ADVAPI32!EqualSid` at `0x18003cc90`
- `ADVAPI32!EqualSid` at `0x18003cca1`
- `ADVAPI32!EqualSid` at `0x18003ccb2`
- `ADVAPI32!EqualSid` at `0x18003cc90`
- `ADVAPI32!EqualSid` at `0x18003cca1`
- `ADVAPI32!EqualSid` at `0x18003ccb2`

## pseudocode

```c
__int64 __fastcall IsLocalSystem(void *a1)
{
  int TokenUser; // eax
  PSID *v2; // rdi
  unsigned int v3; // ebx
  signed int LastError; // eax
  PSID pSid1; // [rsp+60h] [rbp+7h] BYREF
  PSID pSid; // [rsp+68h] [rbp+Fh] BYREF
  PSID v8; // [rsp+70h] [rbp+17h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp+1Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid1 = 0;
  pSid = 0;
  v8 = 0;
  lpMem = 0;
  TokenUser = GetTokenUser(a1, (struct _TOKEN_USER **)&lpMem);
  v2 = (PSID *)lpMem;
  v3 = TokenUser;
  if ( TokenUser >= 0 )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid1)
      && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &pSid)
      && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &v8) )
    {
      if ( !EqualSid(pSid1, *v2) && !EqualSid(pSid, *v2) && !EqualSid(v8, *v2) )
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
  if ( pSid )
    FreeSid(pSid);
  if ( v8 )
    FreeSid(v8);
  return v3;
}

```

## disassembly

```asm
0x18003cb8c  push    rbp
0x18003cb8e  push    rbx
0x18003cb8f  push    rsi
0x18003cb90  push    rdi
0x18003cb91  lea     rbp, [rsp-3Fh]
0x18003cb96  sub     rsp, 98h
0x18003cb9d  mov     rax, cs:__security_cookie
0x18003cba4  xor     rax, rsp
0x18003cba7  mov     [rbp+57h+var_28], rax
0x18003cbab  xor     esi, esi
0x18003cbad  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18003cbb3  lea     rdx, [rbp+57h+lpMem]; struct _TOKEN_USER **
0x18003cbb7  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18003cbba  mov     [rbp+57h+pSid1], rsi
0x18003cbbe  mov     [rbp+57h+var_48], rsi
0x18003cbc2  mov     [rbp+57h+var_40], rsi
0x18003cbc6  mov     [rbp+57h+lpMem], rsi
0x18003cbca  call    ?GetTokenUser@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenUser(void *,_TOKEN_USER * *)
0x18003cbcf  mov     rdi, [rbp+57h+lpMem]
0x18003cbd3  mov     ebx, eax
0x18003cbd5  test    eax, eax
0x18003cbd7  js      loc_18003CCD6
0x18003cbdd  lea     rax, [rbp+57h+pSid1]
0x18003cbe1  xor     r9d, r9d; nSubAuthority1
0x18003cbe4  mov     [rsp+0B0h+pSid], rax; pSid
0x18003cbe9  lea     r8d, [rsi+12h]; nSubAuthority0
0x18003cbed  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x18003cbf1  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18003cbf5  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x18003cbf9  mov     dl, 1; nSubAuthorityCount
0x18003cbfb  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x18003cbff  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x18003cc03  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x18003cc07  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x18003cc0b  call    cs:__imp_AllocateAndInitializeSid
0x18003cc11  test    eax, eax
0x18003cc13  jz      loc_18003CCC1
0x18003cc19  lea     rax, [rbp+57h+var_48]
0x18003cc1d  xor     r9d, r9d; nSubAuthority1
0x18003cc20  mov     [rsp+0B0h+pSid], rax; pSid
0x18003cc25  lea     r8d, [rsi+13h]; nSubAuthority0
0x18003cc29  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x18003cc2d  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18003cc31  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x18003cc35  mov     dl, 1; nSubAuthorityCount
0x18003cc37  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x18003cc3b  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x18003cc3f  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x18003cc43  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x18003cc47  call    cs:__imp_AllocateAndInitializeSid
0x18003cc4d  test    eax, eax
0x18003cc4f  jz      short loc_18003CCC1
0x18003cc51  lea     rax, [rbp+57h+var_40]
0x18003cc55  xor     r9d, r9d; nSubAuthority1
0x18003cc58  mov     [rsp+0B0h+pSid], rax; pSid
0x18003cc5d  lea     r8d, [rsi+14h]; nSubAuthority0
0x18003cc61  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x18003cc65  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18003cc69  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x18003cc6d  mov     dl, 1; nSubAuthorityCount
0x18003cc6f  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x18003cc73  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x18003cc77  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x18003cc7b  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x18003cc7f  call    cs:__imp_AllocateAndInitializeSid
0x18003cc85  test    eax, eax
0x18003cc87  jz      short loc_18003CCC1
0x18003cc89  mov     rdx, [rdi]; pSid2
0x18003cc8c  mov     rcx, [rbp+57h+pSid1]; pSid1
0x18003cc90  call    cs:__imp_EqualSid
0x18003cc96  test    eax, eax
0x18003cc98  jnz     short loc_18003CCD6
0x18003cc9a  mov     rdx, [rdi]; pSid2
0x18003cc9d  mov     rcx, [rbp+57h+var_48]; pSid1
0x18003cca1  call    cs:__imp_EqualSid
0x18003cca7  test    eax, eax
0x18003cca9  jnz     short loc_18003CCD6
0x18003ccab  mov     rdx, [rdi]; pSid2
0x18003ccae  mov     rcx, [rbp+57h+var_40]; pSid1
0x18003ccb2  call    cs:__imp_EqualSid
0x18003ccb8  test    eax, eax
0x18003ccba  jnz     short loc_18003CCD6
0x18003ccbc  lea     ebx, [rsi+1]
0x18003ccbf  jmp     short loc_18003CCD6
0x18003ccc1  call    cs:__imp_GetLastError
0x18003ccc7  mov     ebx, eax
0x18003ccc9  test    eax, eax
0x18003cccb  jle     short loc_18003CCD6
0x18003cccd  movzx   ebx, ax
0x18003ccd0  or      ebx, 80070000h
0x18003ccd6  test    rdi, rdi
0x18003ccd9  jz      short loc_18003CCE3
0x18003ccdb  mov     rcx, rdi; lpMem
0x18003ccde  call    ServerFree
0x18003cce3  mov     rcx, [rbp+57h+pSid1]; pSid
0x18003cce7  test    rcx, rcx
0x18003ccea  jz      short loc_18003CCF2
0x18003ccec  call    cs:__imp_FreeSid
0x18003ccf2  mov     rcx, [rbp+57h+var_48]; pSid
0x18003ccf6  test    rcx, rcx
0x18003ccf9  jz      short loc_18003CD01
0x18003ccfb  call    cs:__imp_FreeSid
0x18003cd01  mov     rcx, [rbp+57h+var_40]; pSid
0x18003cd05  test    rcx, rcx
0x18003cd08  jz      short loc_18003CD10
0x18003cd0a  call    cs:__imp_FreeSid
0x18003cd10  mov     eax, ebx
0x18003cd12  mov     rcx, [rbp+57h+var_28]
0x18003cd16  xor     rcx, rsp; StackCookie
0x18003cd19  call    __security_check_cookie
0x18003cd1e  add     rsp, 98h
0x18003cd25  pop     rdi
0x18003cd26  pop     rsi
0x18003cd27  pop     rbx
0x18003cd28  pop     rbp
0x18003cd29  retn
```
