# UtilIsSystem(void)

- ea: `0x18002dd04`
- end: `0x18002de49`
- name: `?UtilIsSystem@@YA_NXZ`
- size: `325`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002dca0`

## callees

- `0x180004c64`
- `0x18002dd04`
- `0x1800431ac`
- `0x180053300`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002de19`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002de19`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002dd80`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002dd80`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002ddcc`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002ddcc`

## pseudocode

```c
bool UtilIsSystem(void)
{
  BOOL v0; // ebx
  wchar_t *v1; // rcx
  __int64 v2; // rdx
  bool v3; // bl
  WINBOOL IsMember; // [rsp+60h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+1Fh] BYREF
  PSID pSid; // [rsp+70h] [rbp+27h] BYREF
  PSID *p_SidToCheck; // [rsp+78h] [rbp+2Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+3Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  pSid = 0;
  p_SidToCheck = &SidToCheck;
  tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>::reset(&SidToCheck, 0);
  v0 = AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid);
  if ( pSid )
    tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>::reset(p_SidToCheck, pSid);
  if ( v0 )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v2 = 33;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v2 = 32;
LABEL_11:
      WPP_SF_(*((_QWORD *)v1 + 2), v2, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
    }
  }
  v3 = IsMember != 0;
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v3;
}

```

## disassembly

```asm
0x18002dd04  mov     [rsp-8+arg_0], rbx
0x18002dd09  mov     [rsp-8+arg_8], rdi
0x18002dd0e  push    rbp
0x18002dd0f  lea     rbp, [rsp-57h]
0x18002dd14  sub     rsp, 0A0h
0x18002dd1b  mov     rax, cs:__security_cookie
0x18002dd22  xor     rax, rsp
0x18002dd25  mov     [rbp+57h+var_10], rax
0x18002dd29  xor     edi, edi
0x18002dd2b  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18002dd31  lea     rax, [rbp+57h+SidToCheck]
0x18002dd35  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x18002dd38  xor     edx, edx
0x18002dd3a  mov     [rbp+57h+SidToCheck], rdi
0x18002dd3e  lea     rcx, [rbp+57h+SidToCheck]
0x18002dd42  mov     [rbp+57h+IsMember], edi
0x18002dd45  mov     [rbp+57h+var_30], rdi
0x18002dd49  mov     [rbp+57h+var_28], rax
0x18002dd4d  call    ?reset@?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>::reset(void *)
0x18002dd52  lea     rax, [rbp+57h+var_30]
0x18002dd56  xor     r9d, r9d; nSubAuthority1
0x18002dd59  mov     [rsp+0A0h+pSid], rax; pSid
0x18002dd5e  lea     r8d, [rdi+12h]; nSubAuthority0
0x18002dd62  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x18002dd66  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18002dd6a  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x18002dd6e  mov     dl, 1; nSubAuthorityCount
0x18002dd70  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x18002dd74  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x18002dd78  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x18002dd7c  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x18002dd80  call    cs:__imp_AllocateAndInitializeSid
0x18002dd87  nop     dword ptr [rax+rax+00h]
0x18002dd8c  mov     rdx, [rbp+57h+var_30]
0x18002dd90  mov     ebx, eax
0x18002dd92  test    rdx, rdx
0x18002dd95  jz      short loc_18002DDA0
0x18002dd97  mov     rcx, [rbp+57h+var_28]
0x18002dd9b  call    ?reset@?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>::reset(void *)
0x18002dda0  test    ebx, ebx
0x18002dda2  jnz     short loc_18002DDC2
0x18002dda4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ddab  lea     rax, WPP_GLOBAL_Control
0x18002ddb2  cmp     rcx, rax
0x18002ddb5  jz      short loc_18002DE0A
0x18002ddb7  test    byte ptr [rcx+1Ch], 1
0x18002ddbb  jz      short loc_18002DE0A
0x18002ddbd  lea     edx, [rbx+20h]
0x18002ddc0  jmp     short loc_18002DDFA
0x18002ddc2  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18002ddc6  lea     r8, [rbp+57h+IsMember]; IsMember
0x18002ddca  xor     ecx, ecx; TokenHandle
0x18002ddcc  call    cs:__imp_CheckTokenMembership
0x18002ddd3  nop     dword ptr [rax+rax+00h]
0x18002ddd8  test    eax, eax
0x18002ddda  jnz     short loc_18002DE0A
0x18002dddc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dde3  lea     rax, WPP_GLOBAL_Control
0x18002ddea  cmp     rcx, rax
0x18002dded  jz      short loc_18002DE0A
0x18002ddef  test    byte ptr [rcx+1Ch], 1
0x18002ddf3  jz      short loc_18002DE0A
0x18002ddf5  mov     edx, 21h ; '!'
0x18002ddfa  mov     rcx, [rcx+10h]
0x18002ddfe  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18002de05  call    WPP_SF_
0x18002de0a  cmp     [rbp+57h+IsMember], edi
0x18002de0d  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18002de11  setnz   bl
0x18002de14  test    rcx, rcx
0x18002de17  jz      short loc_18002DE25
0x18002de19  call    cs:__imp_FreeSid
0x18002de20  nop     dword ptr [rax+rax+00h]
0x18002de25  mov     al, bl
0x18002de27  mov     rcx, [rbp+57h+var_10]
0x18002de2b  xor     rcx, rsp; StackCookie
0x18002de2e  call    __security_check_cookie
0x18002de33  lea     r11, [rsp+0A0h+var_s0]
0x18002de3b  mov     rbx, [r11+10h]
0x18002de3f  mov     rdi, [r11+18h]
0x18002de43  mov     rsp, r11
0x18002de46  pop     rbp
0x18002de47  retn
```
