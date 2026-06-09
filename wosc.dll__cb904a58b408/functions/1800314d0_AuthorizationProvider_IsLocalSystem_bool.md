# AuthorizationProvider::IsLocalSystem(bool *)

- ea: `0x1800314d0`
- end: `0x180031607`
- name: `?IsLocalSystem@AuthorizationProvider@@AEAAJPEA_N@Z`
- size: `311`
- prototype: `__int64 __fastcall(AuthorizationProvider *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180031430`

## callees

- `0x180003110`
- `0x18000e5ac`
- `0x1800314d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800315a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800315a0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003155f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003155f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800315c2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800315de`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800315c2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800315de`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180031596`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180031596`

## pseudocode

```c
__int64 __fastcall AuthorizationProvider::IsLocalSystem(AuthorizationProvider *this, bool *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  signed int LastError; // eax
  signed int v7; // eax
  PSID v8; // rcx
  DWORD nSubAuthority2; // [rsp+20h] [rbp-60h]
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  if ( !a2 )
  {
    v3 = -2147024809;
    v4 = 228;
    goto LABEL_3;
  }
  IsMember = 0;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( (v3 & 0x80000000) == 0 )
      return v3;
    v4 = 243;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\identityprovider\\authorizationprovider.cpp",
      (const char *)v3,
      nSubAuthority2);
    return v3;
  }
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v7 = GetLastError();
    v3 = v7;
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
    if ( SidToCheck )
      FreeSid(SidToCheck);
    return v3;
  }
  v8 = SidToCheck;
  *a2 = IsMember != 0;
  if ( v8 )
    FreeSid(v8);
  return 0;
}

```

## disassembly

```asm
0x1800314d0  mov     [rsp-8+arg_0], rbx
0x1800314d5  mov     [rsp-8+arg_10], rdi
0x1800314da  push    rbp
0x1800314db  mov     rbp, rsp
0x1800314de  sub     rsp, 80h
0x1800314e5  mov     rax, cs:__security_cookie
0x1800314ec  xor     rax, rsp
0x1800314ef  mov     [rbp+var_8], rax
0x1800314f3  xor     edi, edi
0x1800314f5  mov     rbx, rdx
0x1800314f8  test    rdx, rdx
0x1800314fb  jnz     short loc_180031521
0x1800314fd  mov     ebx, 80070057h
0x180031502  mov     edx, 0E4h; void *
0x180031507  mov     rcx, [rbp+8]; this
0x18003150b  lea     r8, aOnecoreBaseFli_25; "onecore\\base\\flighting\\onesettings\\"...
0x180031512  mov     r9d, ebx; char *
0x180031515  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003151a  mov     eax, ebx
0x18003151c  jmp     loc_1800315E6
0x180031521  lea     rax, [rbp+SidToCheck]
0x180031525  mov     [rbp+IsMember], edi
0x180031528  mov     [rsp+80h+pSid], rax; pSid
0x18003152d  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180031531  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180031535  xor     r9d, r9d; nSubAuthority1
0x180031538  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x18003153c  mov     dl, 1; nSubAuthorityCount
0x18003153e  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x180031542  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180031546  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x18003154a  lea     r8d, [r9+12h]; nSubAuthority0
0x18003154e  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180031552  mov     [rbp+SidToCheck], rdi
0x180031556  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x180031559  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18003155f  call    cs:__imp_AllocateAndInitializeSid
0x180031565  test    eax, eax
0x180031567  jnz     short loc_18003158C
0x180031569  call    cs:__imp_GetLastError
0x18003156f  mov     ebx, eax
0x180031571  test    eax, eax
0x180031573  jle     short loc_18003157E
0x180031575  movzx   ebx, ax
0x180031578  or      ebx, 80070000h
0x18003157e  test    ebx, ebx
0x180031580  jns     short loc_18003151A
0x180031582  mov     edx, 0F3h
0x180031587  jmp     loc_180031507
0x18003158c  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180031590  lea     r8, [rbp+IsMember]; IsMember
0x180031594  xor     ecx, ecx; TokenHandle
0x180031596  call    cs:__imp_CheckTokenMembership
0x18003159c  test    eax, eax
0x18003159e  jnz     short loc_1800315CD
0x1800315a0  call    cs:__imp_GetLastError
0x1800315a6  mov     ebx, eax
0x1800315a8  test    eax, eax
0x1800315aa  jle     short loc_1800315B5
0x1800315ac  movzx   ebx, ax
0x1800315af  or      ebx, 80070000h
0x1800315b5  mov     rcx, [rbp+SidToCheck]; pSid
0x1800315b9  test    rcx, rcx
0x1800315bc  jz      loc_18003151A
0x1800315c2  call    cs:__imp_FreeSid
0x1800315c8  jmp     loc_18003151A
0x1800315cd  cmp     [rbp+IsMember], edi
0x1800315d0  mov     rcx, [rbp+SidToCheck]; pSid
0x1800315d4  setnz   al
0x1800315d7  mov     [rbx], al
0x1800315d9  test    rcx, rcx
0x1800315dc  jz      short loc_1800315E4
0x1800315de  call    cs:__imp_FreeSid
0x1800315e4  xor     eax, eax
0x1800315e6  mov     rcx, [rbp+var_8]
0x1800315ea  xor     rcx, rsp; StackCookie
0x1800315ed  call    __security_check_cookie
0x1800315f2  lea     r11, [rsp+80h+var_s0]
0x1800315fa  mov     rbx, [r11+10h]
0x1800315fe  mov     rdi, [r11+20h]
0x180031602  mov     rsp, r11
0x180031605  pop     rbp
0x180031606  retn
```
