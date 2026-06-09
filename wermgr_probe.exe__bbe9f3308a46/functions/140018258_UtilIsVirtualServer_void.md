# UtilIsVirtualServer(void)

- ea: `0x140018258`
- end: `0x14001838a`
- name: `?UtilIsVirtualServer@@YA_NXZ`
- size: `306`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001b9dc`

## callees

- `0x140003200`
- `0x14000e318`
- `0x140018258`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1400182c8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1400182c8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14001831a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14001831a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400182e8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140018361`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1400182e8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140018361`

## pseudocode

```c
bool UtilIsVirtualServer(void)
{
  BOOL v0; // ebx
  PSID v1; // rcx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  bool v4; // bl
  WINBOOL IsMember; // [rsp+68h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+1Fh] BYREF
  PSID v8; // [rsp+78h] [rbp+27h] BYREF
  PSID *p_SidToCheck; // [rsp+80h] [rbp+2Fh]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+3Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  p_SidToCheck = &SidToCheck;
  IsMember = 0;
  v8 = 0;
  SidToCheck = 0;
  v0 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x53u, 0, 0, 0, 0, 0, 0, 0, &v8);
  if ( v8 )
  {
    v1 = *p_SidToCheck;
    *p_SidToCheck = v8;
    if ( v1 )
      FreeSid(v1);
  }
  if ( v0 )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v3 = 31;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 30;
LABEL_12:
      WPP_SF_(v2[2], v3, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    }
  }
  v4 = IsMember != 0;
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v4;
}

```

## disassembly

```asm
0x140018258  mov     r11, rsp
0x14001825b  mov     [r11+8], rbx
0x14001825f  mov     [r11+10h], rdi
0x140018263  push    rbp
0x140018264  lea     rbp, [r11-5Fh]
0x140018268  sub     rsp, 0A0h
0x14001826f  mov     rax, cs:__security_cookie
0x140018276  xor     rax, rsp
0x140018279  mov     [rbp+57h+var_10], rax
0x14001827d  xor     edi, edi
0x14001827f  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140018285  lea     rax, [rbp+57h+SidToCheck]
0x140018289  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x14001828c  mov     [rbp+57h+var_28], rax
0x140018290  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140018294  lea     rax, [rbp+57h+var_30]
0x140018298  mov     [rbp+57h+IsMember], edi
0x14001829b  mov     [r11-58h], rax
0x14001829f  lea     r8d, [rdi+53h]; nSubAuthority0
0x1400182a3  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x1400182a7  xor     r9d, r9d; nSubAuthority1
0x1400182aa  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x1400182ae  mov     dl, 2; nSubAuthorityCount
0x1400182b0  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x1400182b4  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x1400182b8  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x1400182bc  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x1400182c0  mov     [rbp+57h+var_30], rdi
0x1400182c4  mov     [rbp+57h+SidToCheck], rdi
0x1400182c8  call    cs:__imp_AllocateAndInitializeSid
0x1400182ce  mov     r8, [rbp+57h+var_30]
0x1400182d2  mov     ebx, eax
0x1400182d4  test    r8, r8
0x1400182d7  jz      short loc_1400182EE
0x1400182d9  mov     rdx, [rbp+57h+var_28]
0x1400182dd  mov     rcx, [rdx]; pSid
0x1400182e0  mov     [rdx], r8
0x1400182e3  test    rcx, rcx
0x1400182e6  jz      short loc_1400182EE
0x1400182e8  call    cs:__imp_FreeSid
0x1400182ee  test    ebx, ebx
0x1400182f0  jnz     short loc_140018310
0x1400182f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400182f9  lea     rax, WPP_GLOBAL_Control
0x140018300  cmp     rcx, rax
0x140018303  jz      short loc_140018352
0x140018305  test    byte ptr [rcx+1Ch], 1
0x140018309  jz      short loc_140018352
0x14001830b  lea     edx, [rbx+1Eh]
0x14001830e  jmp     short loc_140018342
0x140018310  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140018314  lea     r8, [rbp+57h+IsMember]; IsMember
0x140018318  xor     ecx, ecx; TokenHandle
0x14001831a  call    cs:__imp_CheckTokenMembership
0x140018320  test    eax, eax
0x140018322  jnz     short loc_140018352
0x140018324  mov     rcx, cs:WPP_GLOBAL_Control
0x14001832b  lea     rax, WPP_GLOBAL_Control
0x140018332  cmp     rcx, rax
0x140018335  jz      short loc_140018352
0x140018337  test    byte ptr [rcx+1Ch], 1
0x14001833b  jz      short loc_140018352
0x14001833d  mov     edx, 1Fh
0x140018342  mov     rcx, [rcx+10h]
0x140018346  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x14001834d  call    WPP_SF_
0x140018352  cmp     [rbp+57h+IsMember], edi
0x140018355  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x140018359  setnz   bl
0x14001835c  test    rcx, rcx
0x14001835f  jz      short loc_140018367
0x140018361  call    cs:__imp_FreeSid
0x140018367  mov     al, bl
0x140018369  mov     rcx, [rbp+57h+var_10]
0x14001836d  xor     rcx, rsp; StackCookie
0x140018370  call    __security_check_cookie
0x140018375  lea     r11, [rsp+0A0h+var_s0]
0x14001837d  mov     rbx, [r11+10h]
0x140018381  mov     rdi, [r11+18h]
0x140018385  mov     rsp, r11
0x140018388  pop     rbp
0x140018389  retn
```
