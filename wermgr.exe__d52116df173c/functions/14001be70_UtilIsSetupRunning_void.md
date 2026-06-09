# UtilIsSetupRunning(void)

- ea: `0x14001be70`
- end: `0x14001bfd0`
- name: `?UtilIsSetupRunning@@YAHXZ`
- size: `352`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001b9dc`

## callees

- `0x140003200`
- `0x14000e318`
- `0x14001bb34`
- `0x14001be70`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001bfab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001bfab`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001bedd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001bedd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14001bf2f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14001bf2f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14001befd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14001bf77`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14001befd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14001bf77`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14001bf99`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x14001bf99`

## pseudocode

```c
__int64 UtilIsSetupRunning(void)
{
  unsigned int v0; // ebx
  BOOL v1; // edi
  PSID v2; // rcx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  bool v5; // di
  char *v6; // rcx
  WINBOOL IsMember; // [rsp+60h] [rbp-9h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-1h] BYREF
  PSID pSid; // [rsp+70h] [rbp+7h] BYREF
  PSID *p_SidToCheck; // [rsp+78h] [rbp+Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  p_SidToCheck = &SidToCheck;
  IsMember = 0;
  v0 = 0;
  pSid = 0;
  SidToCheck = 0;
  v1 = AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid);
  if ( pSid )
  {
    v2 = *p_SidToCheck;
    *p_SidToCheck = pSid;
    if ( v2 )
      FreeSid(v2);
  }
  if ( v1 )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 33;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 32;
LABEL_12:
      WPP_SF_(v3[2], v4, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    }
  }
  v5 = IsMember != 0;
  if ( SidToCheck )
    FreeSid(SidToCheck);
  if ( v5 )
  {
    if ( (unsigned int)UtilIsInteractiveDesktop() )
    {
      v6 = (char *)OpenMutexW(0x1F0001u, 0, L"Global\\Microsoft.Windows.Setup");
      if ( v6 != (char *)-1LL && v6 + 1 != (char *)1 )
      {
        CloseHandle(v6);
        return 1;
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x14001be70  push    rbp
0x14001be72  push    rbx
0x14001be73  push    rsi
0x14001be74  push    rdi
0x14001be75  lea     rbp, [rsp-3Fh]
0x14001be7a  sub     rsp, 0A8h
0x14001be81  mov     rax, cs:__security_cookie
0x14001be88  xor     rax, rsp
0x14001be8b  mov     [rbp+57h+var_30], rax
0x14001be8f  xor     esi, esi
0x14001be91  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x14001be97  lea     rax, [rbp+57h+SidToCheck]
0x14001be9b  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x14001be9e  mov     [rbp+57h+var_48], rax
0x14001bea2  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14001bea6  lea     rax, [rbp+57h+var_50]
0x14001beaa  mov     [rbp+57h+IsMember], esi
0x14001bead  mov     [rsp+0C0h+pSid], rax; pSid
0x14001beb2  lea     r8d, [rsi+12h]; nSubAuthority0
0x14001beb6  mov     [rsp+0C0h+nSubAuthority7], esi; nSubAuthority7
0x14001beba  xor     r9d, r9d; nSubAuthority1
0x14001bebd  mov     [rsp+0C0h+nSubAuthority6], esi; nSubAuthority6
0x14001bec1  mov     dl, 1; nSubAuthorityCount
0x14001bec3  mov     [rsp+0C0h+nSubAuthority5], esi; nSubAuthority5
0x14001bec7  mov     ebx, esi
0x14001bec9  mov     [rsp+0C0h+nSubAuthority4], esi; nSubAuthority4
0x14001becd  mov     [rsp+0C0h+nSubAuthority3], esi; nSubAuthority3
0x14001bed1  mov     [rsp+0C0h+nSubAuthority2], esi; nSubAuthority2
0x14001bed5  mov     [rbp+57h+var_50], rsi
0x14001bed9  mov     [rbp+57h+SidToCheck], rsi
0x14001bedd  call    cs:__imp_AllocateAndInitializeSid
0x14001bee3  mov     rdx, [rbp+57h+var_50]
0x14001bee7  mov     edi, eax
0x14001bee9  test    rdx, rdx
0x14001beec  jz      short loc_14001BF03
0x14001beee  mov     rax, [rbp+57h+var_48]
0x14001bef2  mov     rcx, [rax]; pSid
0x14001bef5  mov     [rax], rdx
0x14001bef8  test    rcx, rcx
0x14001befb  jz      short loc_14001BF03
0x14001befd  call    cs:__imp_FreeSid
0x14001bf03  test    edi, edi
0x14001bf05  jnz     short loc_14001BF25
0x14001bf07  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf0e  lea     rax, WPP_GLOBAL_Control
0x14001bf15  cmp     rcx, rax
0x14001bf18  jz      short loc_14001BF67
0x14001bf1a  test    byte ptr [rcx+1Ch], 1
0x14001bf1e  jz      short loc_14001BF67
0x14001bf20  lea     edx, [rdi+20h]
0x14001bf23  jmp     short loc_14001BF57
0x14001bf25  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x14001bf29  lea     r8, [rbp+57h+IsMember]; IsMember
0x14001bf2d  xor     ecx, ecx; TokenHandle
0x14001bf2f  call    cs:__imp_CheckTokenMembership
0x14001bf35  test    eax, eax
0x14001bf37  jnz     short loc_14001BF67
0x14001bf39  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf40  lea     rax, WPP_GLOBAL_Control
0x14001bf47  cmp     rcx, rax
0x14001bf4a  jz      short loc_14001BF67
0x14001bf4c  test    byte ptr [rcx+1Ch], 1
0x14001bf50  jz      short loc_14001BF67
0x14001bf52  mov     edx, 21h ; '!'
0x14001bf57  mov     rcx, [rcx+10h]
0x14001bf5b  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x14001bf62  call    WPP_SF_
0x14001bf67  cmp     [rbp+57h+IsMember], esi
0x14001bf6a  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x14001bf6e  setnz   dil
0x14001bf72  test    rcx, rcx
0x14001bf75  jz      short loc_14001BF7D
0x14001bf77  call    cs:__imp_FreeSid
0x14001bf7d  test    dil, dil
0x14001bf80  jz      short loc_14001BFB6
0x14001bf82  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x14001bf87  test    eax, eax
0x14001bf89  jz      short loc_14001BFB6
0x14001bf8b  lea     r8, aGlobalMicrosof; "Global\\Microsoft.Windows.Setup"
0x14001bf92  xor     edx, edx; bInheritHandle
0x14001bf94  mov     ecx, 1F0001h; dwDesiredAccess
0x14001bf99  call    cs:__imp_OpenMutexW
0x14001bf9f  mov     rcx, rax; hObject
0x14001bfa2  inc     rax
0x14001bfa5  cmp     rax, 1
0x14001bfa9  jbe     short loc_14001BFB6
0x14001bfab  call    cs:__imp_CloseHandle
0x14001bfb1  mov     ebx, 1
0x14001bfb6  mov     eax, ebx
0x14001bfb8  mov     rcx, [rbp+57h+var_30]
0x14001bfbc  xor     rcx, rsp; StackCookie
0x14001bfbf  call    __security_check_cookie
0x14001bfc4  add     rsp, 0A8h
0x14001bfcb  pop     rdi
0x14001bfcc  pop     rsi
0x14001bfcd  pop     rbx
0x14001bfce  pop     rbp
0x14001bfcf  retn
```
