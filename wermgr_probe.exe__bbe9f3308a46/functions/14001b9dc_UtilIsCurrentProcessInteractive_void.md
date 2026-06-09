# UtilIsCurrentProcessInteractive(void)

- ea: `0x14001b9dc`
- end: `0x14001bb2d`
- name: `?UtilIsCurrentProcessInteractive@@YAHXZ`
- size: `337`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000659c`
- `0x14000e49c`

## callees

- `0x140003200`
- `0x14000e318`
- `0x140018258`
- `0x140018390`
- `0x14001841c`
- `0x14001b9dc`
- `0x14001bb34`
- `0x14001be70`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001ba3f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001ba3f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14001ba81`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14001ba81`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14001bb04`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14001bb04`

## pseudocode

```c
__int64 UtilIsCurrentProcessInteractive(void)
{
  _QWORD *v0; // rcx
  __int64 v1; // rdx
  unsigned int v2; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  IsMember = 0;
  SidToCheck = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v1 = 16;
LABEL_5:
      WPP_SF_(v0[2], v1, &WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids);
      goto LABEL_12;
    }
    goto LABEL_12;
  }
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v1 = 17;
      goto LABEL_5;
    }
LABEL_12:
    if ( IsMember )
      goto LABEL_17;
    goto LABEL_13;
  }
  if ( IsMember )
  {
    IsMember = UtilIsInteractiveDesktop();
    goto LABEL_12;
  }
LABEL_13:
  if ( !(unsigned int)UtilIsSetupRunning() && (!UtilIsWinPE() || !(unsigned int)UtilIsInteractiveDesktop()) )
    goto LABEL_20;
  IsMember = 1;
LABEL_17:
  if ( (unsigned int)UtilIsWindowManagerToken(v0) && !UtilIsVirtualServer() )
  {
    v2 = IsMember;
    goto LABEL_21;
  }
LABEL_20:
  v2 = 0;
  IsMember = 0;
LABEL_21:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v2;
}

```

## disassembly

```asm
0x14001b9dc  mov     [rsp-8+arg_0], rbx
0x14001b9e1  mov     [rsp-8+arg_8], rdi
0x14001b9e6  push    rbp
0x14001b9e7  mov     rbp, rsp
0x14001b9ea  sub     rsp, 80h
0x14001b9f1  mov     rax, cs:__security_cookie
0x14001b9f8  xor     rax, rsp
0x14001b9fb  mov     [rbp+var_8], rax
0x14001b9ff  xor     edi, edi
0x14001ba01  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x14001ba07  lea     rax, [rbp+SidToCheck]
0x14001ba0b  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x14001ba0e  mov     [rsp+80h+pSid], rax; pSid
0x14001ba13  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x14001ba17  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x14001ba1b  xor     r9d, r9d; nSubAuthority1
0x14001ba1e  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x14001ba22  lea     r8d, [rdi+4]; nSubAuthority0
0x14001ba26  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x14001ba2a  mov     dl, 1; nSubAuthorityCount
0x14001ba2c  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x14001ba30  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x14001ba34  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x14001ba38  mov     [rbp+IsMember], edi
0x14001ba3b  mov     [rbp+SidToCheck], rdi
0x14001ba3f  call    cs:__imp_AllocateAndInitializeSid
0x14001ba45  test    eax, eax
0x14001ba47  jnz     short loc_14001BA77
0x14001ba49  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba50  lea     rax, WPP_GLOBAL_Control
0x14001ba57  cmp     rcx, rax
0x14001ba5a  jz      short loc_14001BAB8
0x14001ba5c  test    byte ptr [rcx+1Ch], 1
0x14001ba60  jz      short loc_14001BAB8
0x14001ba62  lea     edx, [rdi+10h]
0x14001ba65  mov     rcx, [rcx+10h]
0x14001ba69  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x14001ba70  call    WPP_SF_
0x14001ba75  jmp     short loc_14001BAB8
0x14001ba77  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x14001ba7b  lea     r8, [rbp+IsMember]; IsMember
0x14001ba7f  xor     ecx, ecx; TokenHandle
0x14001ba81  call    cs:__imp_CheckTokenMembership
0x14001ba87  test    eax, eax
0x14001ba89  jnz     short loc_14001BAAB
0x14001ba8b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba92  lea     rax, WPP_GLOBAL_Control
0x14001ba99  cmp     rcx, rax
0x14001ba9c  jz      short loc_14001BAB8
0x14001ba9e  test    byte ptr [rcx+1Ch], 1
0x14001baa2  jz      short loc_14001BAB8
0x14001baa4  mov     edx, 11h
0x14001baa9  jmp     short loc_14001BA65
0x14001baab  cmp     [rbp+IsMember], edi
0x14001baae  jz      short loc_14001BABD
0x14001bab0  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x14001bab5  mov     [rbp+IsMember], eax
0x14001bab8  cmp     [rbp+IsMember], edi
0x14001babb  jnz     short loc_14001BADF
0x14001babd  call    ?UtilIsSetupRunning@@YAHXZ; UtilIsSetupRunning(void)
0x14001bac2  test    eax, eax
0x14001bac4  jnz     short loc_14001BAD8
0x14001bac6  call    ?UtilIsWinPE@@YA_NXZ; UtilIsWinPE(void)
0x14001bacb  test    al, al
0x14001bacd  jz      short loc_14001BAF6
0x14001bacf  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x14001bad4  test    eax, eax
0x14001bad6  jz      short loc_14001BAF6
0x14001bad8  mov     [rbp+IsMember], 1
0x14001badf  call    ?UtilIsWindowManagerToken@@YAJPEAX@Z; UtilIsWindowManagerToken(void *)
0x14001bae4  test    eax, eax
0x14001bae6  jz      short loc_14001BAF6
0x14001bae8  call    ?UtilIsVirtualServer@@YA_NXZ; UtilIsVirtualServer(void)
0x14001baed  test    al, al
0x14001baef  jnz     short loc_14001BAF6
0x14001baf1  mov     ebx, [rbp+IsMember]
0x14001baf4  jmp     short loc_14001BAFB
0x14001baf6  mov     ebx, edi
0x14001baf8  mov     [rbp+IsMember], ebx
0x14001bafb  mov     rcx, [rbp+SidToCheck]; pSid
0x14001baff  test    rcx, rcx
0x14001bb02  jz      short loc_14001BB0A
0x14001bb04  call    cs:__imp_FreeSid
0x14001bb0a  mov     eax, ebx
0x14001bb0c  mov     rcx, [rbp+var_8]
0x14001bb10  xor     rcx, rsp; StackCookie
0x14001bb13  call    __security_check_cookie
0x14001bb18  lea     r11, [rsp+80h+var_s0]
0x14001bb20  mov     rbx, [r11+10h]
0x14001bb24  mov     rdi, [r11+18h]
0x14001bb28  mov     rsp, r11
0x14001bb2b  pop     rbp
0x14001bb2c  retn
```
