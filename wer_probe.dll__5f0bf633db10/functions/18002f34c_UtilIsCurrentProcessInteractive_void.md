# UtilIsCurrentProcessInteractive(void)

- ea: `0x18002f34c`
- end: `0x18002f49d`
- name: `?UtilIsCurrentProcessInteractive@@YAHXZ`
- size: `337`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003285c`
- `0x180041aac`
- `0x18006fc58`

## callees

- `0x180004bb4`
- `0x18001c04c`
- `0x18002c26c`
- `0x18002f34c`
- `0x18004230c`
- `0x180050db0`
- `0x180098930`
- `0x180098aa4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f474`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f474`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002f3af`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002f3af`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002f3f1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002f3f1`

## pseudocode

```c
__int64 UtilIsCurrentProcessInteractive(void)
{
  wchar_t *v0; // rcx
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
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v1 = 16;
LABEL_5:
      WPP_SF_(*((_QWORD *)v0 + 2), v1, &WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids);
      goto LABEL_12;
    }
    goto LABEL_12;
  }
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
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
0x18002f34c  mov     [rsp-8+arg_0], rbx
0x18002f351  mov     [rsp-8+arg_8], rdi
0x18002f356  push    rbp
0x18002f357  mov     rbp, rsp
0x18002f35a  sub     rsp, 80h
0x18002f361  mov     rax, cs:__security_cookie
0x18002f368  xor     rax, rsp
0x18002f36b  mov     [rbp+var_8], rax
0x18002f36f  xor     edi, edi
0x18002f371  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18002f377  lea     rax, [rbp+SidToCheck]
0x18002f37b  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x18002f37e  mov     [rsp+80h+pSid], rax; pSid
0x18002f383  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18002f387  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x18002f38b  xor     r9d, r9d; nSubAuthority1
0x18002f38e  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x18002f392  lea     r8d, [rdi+4]; nSubAuthority0
0x18002f396  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x18002f39a  mov     dl, 1; nSubAuthorityCount
0x18002f39c  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x18002f3a0  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x18002f3a4  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x18002f3a8  mov     [rbp+IsMember], edi
0x18002f3ab  mov     [rbp+SidToCheck], rdi
0x18002f3af  call    cs:__imp_AllocateAndInitializeSid
0x18002f3b5  test    eax, eax
0x18002f3b7  jnz     short loc_18002F3E7
0x18002f3b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f3c0  lea     rax, WPP_GLOBAL_Control
0x18002f3c7  cmp     rcx, rax
0x18002f3ca  jz      short loc_18002F428
0x18002f3cc  test    byte ptr [rcx+1Ch], 1
0x18002f3d0  jz      short loc_18002F428
0x18002f3d2  lea     edx, [rdi+10h]
0x18002f3d5  mov     rcx, [rcx+10h]
0x18002f3d9  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x18002f3e0  call    WPP_SF_
0x18002f3e5  jmp     short loc_18002F428
0x18002f3e7  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18002f3eb  lea     r8, [rbp+IsMember]; IsMember
0x18002f3ef  xor     ecx, ecx; TokenHandle
0x18002f3f1  call    cs:__imp_CheckTokenMembership
0x18002f3f7  test    eax, eax
0x18002f3f9  jnz     short loc_18002F41B
0x18002f3fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f402  lea     rax, WPP_GLOBAL_Control
0x18002f409  cmp     rcx, rax
0x18002f40c  jz      short loc_18002F428
0x18002f40e  test    byte ptr [rcx+1Ch], 1
0x18002f412  jz      short loc_18002F428
0x18002f414  mov     edx, 11h
0x18002f419  jmp     short loc_18002F3D5
0x18002f41b  cmp     [rbp+IsMember], edi
0x18002f41e  jz      short loc_18002F42D
0x18002f420  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x18002f425  mov     [rbp+IsMember], eax
0x18002f428  cmp     [rbp+IsMember], edi
0x18002f42b  jnz     short loc_18002F44F
0x18002f42d  call    ?UtilIsSetupRunning@@YAHXZ; UtilIsSetupRunning(void)
0x18002f432  test    eax, eax
0x18002f434  jnz     short loc_18002F448
0x18002f436  call    ?UtilIsWinPE@@YA_NXZ; UtilIsWinPE(void)
0x18002f43b  test    al, al
0x18002f43d  jz      short loc_18002F466
0x18002f43f  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x18002f444  test    eax, eax
0x18002f446  jz      short loc_18002F466
0x18002f448  mov     [rbp+IsMember], 1
0x18002f44f  call    ?UtilIsWindowManagerToken@@YAJPEAX@Z; UtilIsWindowManagerToken(void *)
0x18002f454  test    eax, eax
0x18002f456  jz      short loc_18002F466
0x18002f458  call    ?UtilIsVirtualServer@@YA_NXZ; UtilIsVirtualServer(void)
0x18002f45d  test    al, al
0x18002f45f  jnz     short loc_18002F466
0x18002f461  mov     ebx, [rbp+IsMember]
0x18002f464  jmp     short loc_18002F46B
0x18002f466  mov     ebx, edi
0x18002f468  mov     [rbp+IsMember], ebx
0x18002f46b  mov     rcx, [rbp+SidToCheck]; pSid
0x18002f46f  test    rcx, rcx
0x18002f472  jz      short loc_18002F47A
0x18002f474  call    cs:__imp_FreeSid
0x18002f47a  mov     eax, ebx
0x18002f47c  mov     rcx, [rbp+var_8]
0x18002f480  xor     rcx, rsp; StackCookie
0x18002f483  call    __security_check_cookie
0x18002f488  lea     r11, [rsp+80h+var_s0]
0x18002f490  mov     rbx, [r11+10h]
0x18002f494  mov     rdi, [r11+18h]
0x18002f498  mov     rsp, r11
0x18002f49b  pop     rbp
0x18002f49c  retn
```
