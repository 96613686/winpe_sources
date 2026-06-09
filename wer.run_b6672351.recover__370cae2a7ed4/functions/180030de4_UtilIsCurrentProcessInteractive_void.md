# UtilIsCurrentProcessInteractive(void)

- ea: `0x180030de4`
- end: `0x180030f48`
- name: `?UtilIsCurrentProcessInteractive@@YAHXZ`
- size: `356`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180034288`
- `0x180043804`
- `0x180072f9c`

## callees

- `0x180004c64`
- `0x18001ed6c`
- `0x18002dca0`
- `0x180030de4`
- `0x180045630`
- `0x180053300`
- `0x18009ce84`
- `0x18009d00c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180030f18`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180030f18`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180030e47`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180030e47`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180030e8f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180030e8f`

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
      WPP_SF_(*((_QWORD *)v0 + 2), v1, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids);
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
0x180030de4  mov     [rsp-8+arg_0], rbx
0x180030de9  mov     [rsp-8+arg_8], rdi
0x180030dee  push    rbp
0x180030def  mov     rbp, rsp
0x180030df2  sub     rsp, 80h
0x180030df9  mov     rax, cs:__security_cookie
0x180030e00  xor     rax, rsp
0x180030e03  mov     [rbp+var_8], rax
0x180030e07  xor     edi, edi
0x180030e09  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180030e0f  lea     rax, [rbp+SidToCheck]
0x180030e13  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x180030e16  mov     [rsp+80h+pSid], rax; pSid
0x180030e1b  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180030e1f  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180030e23  xor     r9d, r9d; nSubAuthority1
0x180030e26  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180030e2a  lea     r8d, [rdi+4]; nSubAuthority0
0x180030e2e  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x180030e32  mov     dl, 1; nSubAuthorityCount
0x180030e34  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180030e38  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x180030e3c  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180030e40  mov     [rbp+IsMember], edi
0x180030e43  mov     [rbp+SidToCheck], rdi
0x180030e47  call    cs:__imp_AllocateAndInitializeSid
0x180030e4e  nop     dword ptr [rax+rax+00h]
0x180030e53  test    eax, eax
0x180030e55  jnz     short loc_180030E85
0x180030e57  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e5e  lea     rax, WPP_GLOBAL_Control
0x180030e65  cmp     rcx, rax
0x180030e68  jz      short loc_180030ECC
0x180030e6a  test    byte ptr [rcx+1Ch], 1
0x180030e6e  jz      short loc_180030ECC
0x180030e70  lea     edx, [rdi+10h]
0x180030e73  mov     rcx, [rcx+10h]
0x180030e77  lea     r8, WPP_6bd4eed010b8306f92cf4eba78e3d712_Traceguids
0x180030e7e  call    WPP_SF_
0x180030e83  jmp     short loc_180030ECC
0x180030e85  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180030e89  lea     r8, [rbp+IsMember]; IsMember
0x180030e8d  xor     ecx, ecx; TokenHandle
0x180030e8f  call    cs:__imp_CheckTokenMembership
0x180030e96  nop     dword ptr [rax+rax+00h]
0x180030e9b  test    eax, eax
0x180030e9d  jnz     short loc_180030EBF
0x180030e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ea6  lea     rax, WPP_GLOBAL_Control
0x180030ead  cmp     rcx, rax
0x180030eb0  jz      short loc_180030ECC
0x180030eb2  test    byte ptr [rcx+1Ch], 1
0x180030eb6  jz      short loc_180030ECC
0x180030eb8  mov     edx, 11h
0x180030ebd  jmp     short loc_180030E73
0x180030ebf  cmp     [rbp+IsMember], edi
0x180030ec2  jz      short loc_180030ED1
0x180030ec4  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x180030ec9  mov     [rbp+IsMember], eax
0x180030ecc  cmp     [rbp+IsMember], edi
0x180030ecf  jnz     short loc_180030EF3
0x180030ed1  call    ?UtilIsSetupRunning@@YAHXZ; UtilIsSetupRunning(void)
0x180030ed6  test    eax, eax
0x180030ed8  jnz     short loc_180030EEC
0x180030eda  call    ?UtilIsWinPE@@YA_NXZ; UtilIsWinPE(void)
0x180030edf  test    al, al
0x180030ee1  jz      short loc_180030F0A
0x180030ee3  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x180030ee8  test    eax, eax
0x180030eea  jz      short loc_180030F0A
0x180030eec  mov     [rbp+IsMember], 1
0x180030ef3  call    ?UtilIsWindowManagerToken@@YAJPEAX@Z; UtilIsWindowManagerToken(void *)
0x180030ef8  test    eax, eax
0x180030efa  jz      short loc_180030F0A
0x180030efc  call    ?UtilIsVirtualServer@@YA_NXZ; UtilIsVirtualServer(void)
0x180030f01  test    al, al
0x180030f03  jnz     short loc_180030F0A
0x180030f05  mov     ebx, [rbp+IsMember]
0x180030f08  jmp     short loc_180030F0F
0x180030f0a  mov     ebx, edi
0x180030f0c  mov     [rbp+IsMember], ebx
0x180030f0f  mov     rcx, [rbp+SidToCheck]; pSid
0x180030f13  test    rcx, rcx
0x180030f16  jz      short loc_180030F24
0x180030f18  call    cs:__imp_FreeSid
0x180030f1f  nop     dword ptr [rax+rax+00h]
0x180030f24  mov     eax, ebx
0x180030f26  mov     rcx, [rbp+var_8]
0x180030f2a  xor     rcx, rsp; StackCookie
0x180030f2d  call    __security_check_cookie
0x180030f32  lea     r11, [rsp+80h+var_s0]
0x180030f3a  mov     rbx, [r11+10h]
0x180030f3e  mov     rdi, [r11+18h]
0x180030f42  mov     rsp, r11
0x180030f45  pop     rbp
0x180030f46  retn
```
