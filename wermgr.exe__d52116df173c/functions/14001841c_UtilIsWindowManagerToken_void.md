# UtilIsWindowManagerToken(void *)

- ea: `0x14001841c`
- end: `0x140018525`
- name: `?UtilIsWindowManagerToken@@YAJPEAX@Z`
- size: `265`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001b9dc`

## callees

- `0x140003200`
- `0x14001841c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400184d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400184d4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001848c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001848c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400184c0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400184c0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400184ac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400184fc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400184ac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400184fc`

## pseudocode

```c
__int64 __fastcall UtilIsWindowManagerToken(void *a1)
{
  BOOL v1; // ebx
  PSID v2; // rcx
  int v3; // ebx
  signed int LastError; // eax
  WINBOOL IsMember; // [rsp+68h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+1Fh] BYREF
  PSID v8; // [rsp+78h] [rbp+27h] BYREF
  PSID *p_SidToCheck; // [rsp+80h] [rbp+2Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+3Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  p_SidToCheck = &SidToCheck;
  IsMember = 0;
  v8 = 0;
  SidToCheck = 0;
  v1 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x5Au, 0, 0, 0, 0, 0, 0, 0, &v8);
  if ( v8 )
  {
    v2 = *p_SidToCheck;
    *p_SidToCheck = v8;
    if ( v2 )
      FreeSid(v2);
  }
  if ( v1 && CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v3 = IsMember == 0;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001841c  mov     r11, rsp
0x14001841f  mov     [r11+8], rbx
0x140018423  mov     [r11+10h], rdi
0x140018427  push    rbp
0x140018428  lea     rbp, [r11-5Fh]
0x14001842c  sub     rsp, 0A0h
0x140018433  mov     rax, cs:__security_cookie
0x14001843a  xor     rax, rsp
0x14001843d  mov     [rbp+57h+var_10], rax
0x140018441  xor     edi, edi
0x140018443  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140018449  lea     rax, [rbp+57h+SidToCheck]
0x14001844d  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x140018450  mov     [rbp+57h+var_28], rax
0x140018454  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140018458  lea     rax, [rbp+57h+var_30]
0x14001845c  mov     [rbp+57h+IsMember], edi
0x14001845f  mov     [r11-58h], rax
0x140018463  lea     r8d, [rdi+5Ah]; nSubAuthority0
0x140018467  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x14001846b  xor     r9d, r9d; nSubAuthority1
0x14001846e  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x140018472  mov     dl, 2; nSubAuthorityCount
0x140018474  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x140018478  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x14001847c  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x140018480  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x140018484  mov     [rbp+57h+var_30], rdi
0x140018488  mov     [rbp+57h+SidToCheck], rdi
0x14001848c  call    cs:__imp_AllocateAndInitializeSid
0x140018492  mov     r8, [rbp+57h+var_30]
0x140018496  mov     ebx, eax
0x140018498  test    r8, r8
0x14001849b  jz      short loc_1400184B2
0x14001849d  mov     rdx, [rbp+57h+var_28]
0x1400184a1  mov     rcx, [rdx]; pSid
0x1400184a4  mov     [rdx], r8
0x1400184a7  test    rcx, rcx
0x1400184aa  jz      short loc_1400184B2
0x1400184ac  call    cs:__imp_FreeSid
0x1400184b2  test    ebx, ebx
0x1400184b4  jz      short loc_1400184D4
0x1400184b6  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1400184ba  lea     r8, [rbp+57h+IsMember]; IsMember
0x1400184be  xor     ecx, ecx; TokenHandle
0x1400184c0  call    cs:__imp_CheckTokenMembership
0x1400184c6  test    eax, eax
0x1400184c8  jz      short loc_1400184D4
0x1400184ca  cmp     [rbp+57h+IsMember], edi
0x1400184cd  mov     ebx, edi
0x1400184cf  setz    bl
0x1400184d2  jmp     short loc_1400184F3
0x1400184d4  call    cs:__imp_GetLastError
0x1400184da  mov     ebx, eax
0x1400184dc  test    eax, eax
0x1400184de  jle     short loc_1400184E9
0x1400184e0  movzx   ebx, ax
0x1400184e3  or      ebx, 80070000h
0x1400184e9  test    ebx, ebx
0x1400184eb  mov     eax, 80004005h
0x1400184f0  cmovns  ebx, eax
0x1400184f3  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1400184f7  test    rcx, rcx
0x1400184fa  jz      short loc_140018502
0x1400184fc  call    cs:__imp_FreeSid
0x140018502  mov     eax, ebx
0x140018504  mov     rcx, [rbp+57h+var_10]
0x140018508  xor     rcx, rsp; StackCookie
0x14001850b  call    __security_check_cookie
0x140018510  lea     r11, [rsp+0A0h+var_s0]
0x140018518  mov     rbx, [r11+10h]
0x14001851c  mov     rdi, [r11+18h]
0x140018520  mov     rsp, r11
0x140018523  pop     rbp
0x140018524  retn
```
