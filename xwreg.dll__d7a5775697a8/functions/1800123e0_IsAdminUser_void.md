# IsAdminUser(void)

- ea: `0x1800123e0`
- end: `0x180012506`
- name: `?IsAdminUser@@YAHXZ`
- size: `294`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011fac`

## callees

- `0x180003b90`
- `0x180007820`
- `0x1800123e0`
- `0x180012800`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800124a1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800124a1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180012455`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180012455`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012441`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012441`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 IsAdminUser(void)
{
  unsigned int LastErrorHRESULT; // eax
  unsigned int v1; // eax
  BOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      IsMember = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        LastErrorHRESULT = GetLastErrorHRESULT();
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_be4055bde441366cc1643dc23f64a7ff_Traceguids,
          LastErrorHRESULT);
      }
    }
    FreeSid(SidToCheck);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v1 = GetLastErrorHRESULT();
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_be4055bde441366cc1643dc23f64a7ff_Traceguids, v1);
  }
  return IsMember;
}

```

## disassembly

```asm
0x1800123e0  mov     [rsp-8+arg_0], rbx
0x1800123e5  push    rbp
0x1800123e6  mov     rbp, rsp
0x1800123e9  sub     rsp, 80h
0x1800123f0  mov     rax, cs:__security_cookie
0x1800123f7  xor     rax, rsp
0x1800123fa  mov     [rbp+var_8], rax
0x1800123fe  xor     ebx, ebx
0x180012400  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180012406  lea     rax, [rbp+SidToCheck]
0x18001240a  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x18001240d  mov     [rsp+80h+pSid], rax; pSid
0x180012412  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180012416  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x18001241a  mov     r9d, 220h; nSubAuthority1
0x180012420  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x180012424  lea     r8d, [rbx+20h]; nSubAuthority0
0x180012428  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x18001242c  mov     dl, 2; nSubAuthorityCount
0x18001242e  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x180012432  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x180012436  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x18001243a  mov     [rbp+SidToCheck], rbx
0x18001243e  mov     [rbp+IsMember], ebx
0x180012441  call    cs:__imp_AllocateAndInitializeSid
0x180012447  test    eax, eax
0x180012449  jz      short loc_1800124A9
0x18001244b  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18001244f  lea     r8, [rbp+IsMember]; IsMember
0x180012453  xor     ecx, ecx; TokenHandle
0x180012455  call    cs:__imp_CheckTokenMembership
0x18001245b  test    eax, eax
0x18001245d  jnz     short loc_18001249D
0x18001245f  mov     [rbp+IsMember], ebx
0x180012462  mov     rcx, cs:WPP_GLOBAL_Control
0x180012469  lea     rax, WPP_GLOBAL_Control
0x180012470  cmp     rcx, rax
0x180012473  jz      short loc_18001249D
0x180012475  test    byte ptr [rcx+1Ch], 4
0x180012479  jz      short loc_18001249D
0x18001247b  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180012480  mov     rcx, cs:WPP_GLOBAL_Control
0x180012487  lea     edx, [rbx+0Ah]
0x18001248a  mov     r9d, eax
0x18001248d  lea     r8, WPP_be4055bde441366cc1643dc23f64a7ff_Traceguids
0x180012494  mov     rcx, [rcx+10h]
0x180012498  call    WPP_SF_D
0x18001249d  mov     rcx, [rbp+SidToCheck]; pSid
0x1800124a1  call    cs:__imp_FreeSid
0x1800124a7  jmp     short loc_1800124E6
0x1800124a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124b0  lea     rax, WPP_GLOBAL_Control
0x1800124b7  cmp     rcx, rax
0x1800124ba  jz      short loc_1800124E6
0x1800124bc  test    byte ptr [rcx+1Ch], 4
0x1800124c0  jz      short loc_1800124E6
0x1800124c2  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800124c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124ce  lea     r8, WPP_be4055bde441366cc1643dc23f64a7ff_Traceguids
0x1800124d5  mov     edx, 0Bh
0x1800124da  mov     r9d, eax
0x1800124dd  mov     rcx, [rcx+10h]
0x1800124e1  call    WPP_SF_D
0x1800124e6  mov     eax, [rbp+IsMember]
0x1800124e9  mov     rcx, [rbp+var_8]
0x1800124ed  xor     rcx, rsp; StackCookie
0x1800124f0  call    __security_check_cookie
0x1800124f5  mov     rbx, [rsp+80h+arg_0]
0x1800124fd  add     rsp, 80h
0x180012504  pop     rbp
0x180012505  retn
```
