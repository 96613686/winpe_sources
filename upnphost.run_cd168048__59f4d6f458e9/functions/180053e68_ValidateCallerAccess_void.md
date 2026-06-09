# ValidateCallerAccess(void)

- ea: `0x180053e68`
- end: `0x180054289`
- name: `?ValidateCallerAccess@@YAJXZ`
- size: `1057`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002f590`
- `0x18004a768`
- `0x18004a928`
- `0x18004ad9c`
- `0x1800537b4`

## callees

- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x180053e68`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053fc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054069`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005409d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800541ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800541d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053fc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054069`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005409d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800541ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800541d9`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180053eb7`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180053eb7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053f26`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053f26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180053f0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180053f0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054197`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054197`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180053f81`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005410a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180053f81`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18005410a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005401a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18005401a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180054008`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180054008`

## pseudocode

```c
__int64 ValidateCallerAccess(void)
{
  int v0; // r12d
  int v1; // ebx
  HANDLE CurrentThread; // rax
  BOOL v3; // r14d
  signed int LastError; // eax
  DWORD v5; // eax
  unsigned int v6; // r15d
  BOOL v7; // ebx
  signed int v8; // eax
  DWORD v9; // eax
  BOOL v10; // eax
  signed int v11; // eax
  DWORD v12; // eax
  signed int v13; // eax
  DWORD v14; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp-19h] BYREF
  void *ppInterface; // [rsp+68h] [rbp-11h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp-9h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-1h] BYREF
  DWORD nSubAuthority0[4]; // [rsp+80h] [rbp+7h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+17h] BYREF

  nSubAuthority0[0] = 18;
  ppInterface = 0;
  nSubAuthority0[1] = 19;
  v0 = 0;
  nSubAuthority0[2] = 20;
  v1 = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
  if ( v1 < 0 )
    goto LABEL_38;
  if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
    goto LABEL_5;
  v1 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
  if ( v1 < 0 )
  {
LABEL_38:
    if ( v1 == -2147417833 )
      v1 = 0;
    goto LABEL_40;
  }
  v0 = 1;
LABEL_5:
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    SidToCheck = 0;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    v3 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck);
    if ( !v3 )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
      {
        v5 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, v5);
      }
    }
    v6 = 0;
    while ( v3 )
    {
      IsMember = 0;
      v7 = CheckTokenMembership(TokenHandle, SidToCheck, &IsMember);
      FreeSid(SidToCheck);
      if ( v7 )
      {
        if ( IsMember )
        {
          v1 = 0;
          break;
        }
        v1 = -2147024891;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids);
      }
      else
      {
        v8 = GetLastError();
        v1 = v8;
        if ( v8 > 0 )
          v1 = (unsigned __int16)v8 | 0x80070000;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        {
          v9 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, v9);
        }
      }
      if ( v6 >= 3 )
        break;
      v10 = AllocateAndInitializeSid(&pIdentifierAuthority, 1u, nSubAuthority0[v6++], 0, 0, 0, 0, 0, 0, 0, &SidToCheck);
      v3 = v10;
      if ( !v10 )
      {
        v11 = GetLastError();
        v1 = v11;
        if ( v11 > 0 )
          v1 = (unsigned __int16)v11 | 0x80070000;
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        {
          v12 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, v12);
        }
      }
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    v13 = GetLastError();
    v1 = v13;
    if ( v13 > 0 )
      v1 = (unsigned __int16)v13 | 0x80070000;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    {
      v14 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, v14);
    }
  }
LABEL_40:
  if ( v0 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 40LL))(ppInterface);
  if ( ppInterface )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
  if ( v1 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids, (unsigned int)v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180053e68  push    rbp
0x180053e6a  push    rbx
0x180053e6b  push    r12
0x180053e6d  push    r13
0x180053e6f  push    r14
0x180053e71  push    r15
0x180053e73  lea     rbp, [rsp-2Fh]
0x180053e78  sub     rsp, 0A8h
0x180053e7f  mov     rax, cs:__security_cookie
0x180053e86  xor     rax, rsp
0x180053e89  mov     [rbp+57h+var_38], rax
0x180053e8d  xor     r13d, r13d
0x180053e90  mov     [rbp+57h+nSubAuthority0], 12h
0x180053e97  lea     rdx, [rbp+57h+ppInterface]; ppInterface
0x180053e9b  mov     [rbp+57h+ppInterface], r13
0x180053e9f  lea     rcx, IID_IServerSecurity; riid
0x180053ea6  mov     [rbp+57h+var_4C], 13h
0x180053ead  mov     r12d, r13d
0x180053eb0  mov     [rbp+57h+var_48], 14h
0x180053eb7  call    cs:__imp_CoGetCallContext
0x180053ebe  nop     dword ptr [rax+rax+00h]
0x180053ec3  lea     r15, WPP_GLOBAL_Control
0x180053eca  mov     ebx, eax
0x180053ecc  test    eax, eax
0x180053ece  js      loc_180054206
0x180053ed4  mov     rcx, [rbp+57h+ppInterface]
0x180053ed8  mov     rdx, [rcx]
0x180053edb  mov     rax, [rdx+30h]
0x180053edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ee4  test    eax, eax
0x180053ee6  jnz     short loc_180053F06
0x180053ee8  mov     rcx, [rbp+57h+ppInterface]
0x180053eec  mov     rax, [rcx]
0x180053eef  mov     rax, [rax+20h]
0x180053ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ef8  mov     ebx, eax
0x180053efa  test    eax, eax
0x180053efc  js      loc_180054206
0x180053f02  lea     r12d, [r13+1]
0x180053f06  mov     [rbp+57h+TokenHandle], r13
0x180053f0a  call    cs:__imp_GetCurrentThread
0x180053f11  nop     dword ptr [rax+rax+00h]
0x180053f16  mov     edx, 8; DesiredAccess
0x180053f1b  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180053f1f  mov     rcx, rax; ThreadHandle
0x180053f22  lea     r8d, [rdx-7]; OpenAsSelf
0x180053f26  call    cs:__imp_OpenThreadToken
0x180053f2d  nop     dword ptr [rax+rax+00h]
0x180053f32  test    eax, eax
0x180053f34  jz      loc_1800541AC
0x180053f3a  lea     rax, [rbp+57h+SidToCheck]
0x180053f3e  mov     [rbp+57h+SidToCheck], r13
0x180053f42  mov     [rsp+0D0h+pSid], rax; pSid
0x180053f47  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180053f4b  mov     [rsp+0D0h+nSubAuthority7], r13d; nSubAuthority7
0x180053f50  mov     r9d, 220h; nSubAuthority1
0x180053f56  mov     [rsp+0D0h+nSubAuthority6], r13d; nSubAuthority6
0x180053f5b  mov     r8d, 20h ; ' '; nSubAuthority0
0x180053f61  mov     [rsp+0D0h+nSubAuthority5], r13d; nSubAuthority5
0x180053f66  mov     dl, 2; nSubAuthorityCount
0x180053f68  mov     [rsp+0D0h+nSubAuthority4], r13d; nSubAuthority4
0x180053f6d  mov     [rsp+0D0h+nSubAuthority3], r13d; nSubAuthority3
0x180053f72  mov     [rsp+0D0h+nSubAuthority2], r13d; nSubAuthority2
0x180053f77  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x180053f7b  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180053f81  call    cs:__imp_AllocateAndInitializeSid
0x180053f88  nop     dword ptr [rax+rax+00h]
0x180053f8d  mov     r14d, eax
0x180053f90  test    eax, eax
0x180053f92  jnz     short loc_180053FEC
0x180053f94  call    cs:__imp_GetLastError
0x180053f9b  nop     dword ptr [rax+rax+00h]
0x180053fa0  mov     ebx, eax
0x180053fa2  test    eax, eax
0x180053fa4  jle     short loc_180053FAF
0x180053fa6  movzx   ebx, ax
0x180053fa9  or      ebx, 80070000h
0x180053faf  mov     rax, cs:WPP_GLOBAL_Control
0x180053fb6  cmp     rax, r15
0x180053fb9  jz      short loc_180053FEC
0x180053fbb  test    byte ptr [rax+1Ch], 40h
0x180053fbf  jz      short loc_180053FEC
0x180053fc1  call    cs:__imp_GetLastError
0x180053fc8  nop     dword ptr [rax+rax+00h]
0x180053fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180053fd4  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x180053fdb  mov     edx, 17h
0x180053fe0  mov     r9d, eax
0x180053fe3  mov     rcx, [rcx+10h]
0x180053fe7  call    WPP_SF_d
0x180053fec  mov     r15d, r13d
0x180053fef  test    r14d, r14d
0x180053ff2  jz      loc_180054193
0x180053ff8  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180053ffc  lea     r8, [rbp+57h+IsMember]; IsMember
0x180054000  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180054004  mov     [rbp+57h+IsMember], r13d
0x180054008  call    cs:__imp_CheckTokenMembership
0x18005400f  nop     dword ptr [rax+rax+00h]
0x180054014  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x180054018  mov     ebx, eax
0x18005401a  call    cs:__imp_FreeSid
0x180054021  nop     dword ptr [rax+rax+00h]
0x180054026  test    ebx, ebx
0x180054028  jz      short loc_180054069
0x18005402a  cmp     [rbp+57h+IsMember], r13d
0x18005402e  jnz     loc_180054190
0x180054034  mov     ebx, 80070005h
0x180054039  mov     rcx, cs:WPP_GLOBAL_Control
0x180054040  lea     rax, WPP_GLOBAL_Control
0x180054047  cmp     rcx, rax
0x18005404a  jz      short loc_1800540C8
0x18005404c  test    byte ptr [rcx+1Ch], 40h
0x180054050  jz      short loc_1800540C8
0x180054052  mov     rcx, [rcx+10h]
0x180054056  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x18005405d  mov     edx, 18h
0x180054062  call    WPP_SF_
0x180054067  jmp     short loc_1800540C8
0x180054069  call    cs:__imp_GetLastError
0x180054070  nop     dword ptr [rax+rax+00h]
0x180054075  mov     ebx, eax
0x180054077  test    eax, eax
0x180054079  jle     short loc_180054084
0x18005407b  movzx   ebx, ax
0x18005407e  or      ebx, 80070000h
0x180054084  mov     rax, cs:WPP_GLOBAL_Control
0x18005408b  lea     rcx, WPP_GLOBAL_Control
0x180054092  cmp     rax, rcx
0x180054095  jz      short loc_1800540C8
0x180054097  test    byte ptr [rax+1Ch], 40h
0x18005409b  jz      short loc_1800540C8
0x18005409d  call    cs:__imp_GetLastError
0x1800540a4  nop     dword ptr [rax+rax+00h]
0x1800540a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800540b0  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x1800540b7  mov     edx, 19h
0x1800540bc  mov     r9d, eax
0x1800540bf  mov     rcx, [rcx+10h]
0x1800540c3  call    WPP_SF_d
0x1800540c8  cmp     r15d, 3
0x1800540cc  jnb     loc_180054193
0x1800540d2  lea     rax, [rbp+57h+SidToCheck]
0x1800540d6  mov     r8d, r15d
0x1800540d9  mov     [rsp+0D0h+pSid], rax; pSid
0x1800540de  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800540e2  mov     [rsp+0D0h+nSubAuthority7], r13d; nSubAuthority7
0x1800540e7  xor     r9d, r9d; nSubAuthority1
0x1800540ea  mov     [rsp+0D0h+nSubAuthority6], r13d; nSubAuthority6
0x1800540ef  mov     dl, 1; nSubAuthorityCount
0x1800540f1  mov     r8d, [rbp+r8*4+57h+nSubAuthority0]; nSubAuthority0
0x1800540f6  mov     [rsp+0D0h+nSubAuthority5], r13d; nSubAuthority5
0x1800540fb  mov     [rsp+0D0h+nSubAuthority4], r13d; nSubAuthority4
0x180054100  mov     [rsp+0D0h+nSubAuthority3], r13d; nSubAuthority3
0x180054105  mov     [rsp+0D0h+nSubAuthority2], r13d; nSubAuthority2
0x18005410a  call    cs:__imp_AllocateAndInitializeSid
0x180054111  nop     dword ptr [rax+rax+00h]
0x180054116  inc     r15d
0x180054119  mov     r14d, eax
0x18005411c  test    eax, eax
0x18005411e  jnz     loc_180053FEF
0x180054124  call    cs:__imp_GetLastError
0x18005412b  nop     dword ptr [rax+rax+00h]
0x180054130  mov     ebx, eax
0x180054132  test    eax, eax
0x180054134  jle     short loc_18005413F
0x180054136  movzx   ebx, ax
0x180054139  or      ebx, 80070000h
0x18005413f  mov     rax, cs:WPP_GLOBAL_Control
0x180054146  lea     rcx, WPP_GLOBAL_Control
0x18005414d  cmp     rax, rcx
0x180054150  jz      loc_180053FEF
0x180054156  test    byte ptr [rax+1Ch], 40h
0x18005415a  jz      loc_180053FEF
0x180054160  call    cs:__imp_GetLastError
0x180054167  nop     dword ptr [rax+rax+00h]
0x18005416c  mov     rcx, cs:WPP_GLOBAL_Control
0x180054173  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x18005417a  mov     edx, 1Ah
0x18005417f  mov     r9d, eax
0x180054182  mov     rcx, [rcx+10h]
0x180054186  call    WPP_SF_d
0x18005418b  jmp     loc_180053FEF
0x180054190  mov     ebx, r13d
0x180054193  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180054197  call    cs:__imp_CloseHandle
0x18005419e  nop     dword ptr [rax+rax+00h]
0x1800541a3  lea     r15, WPP_GLOBAL_Control
0x1800541aa  jmp     short loc_180054210
0x1800541ac  call    cs:__imp_GetLastError
0x1800541b3  nop     dword ptr [rax+rax+00h]
0x1800541b8  mov     ebx, eax
0x1800541ba  test    eax, eax
0x1800541bc  jle     short loc_1800541C7
0x1800541be  movzx   ebx, ax
0x1800541c1  or      ebx, 80070000h
0x1800541c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800541ce  cmp     rcx, r15
0x1800541d1  jz      short loc_180054210
0x1800541d3  test    byte ptr [rcx+1Ch], 40h
0x1800541d7  jz      short loc_180054210
0x1800541d9  call    cs:__imp_GetLastError
0x1800541e0  nop     dword ptr [rax+rax+00h]
0x1800541e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800541ec  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x1800541f3  mov     edx, 1Bh
0x1800541f8  mov     r9d, eax
0x1800541fb  mov     rcx, [rcx+10h]
0x1800541ff  call    WPP_SF_d
0x180054204  jmp     short loc_180054210
0x180054206  cmp     ebx, 80010117h
0x18005420c  cmovz   ebx, r13d
0x180054210  test    r12d, r12d
0x180054213  jz      short loc_180054225
0x180054215  mov     rcx, [rbp+57h+ppInterface]
0x180054219  mov     rax, [rcx]
0x18005421c  mov     rax, [rax+28h]
0x180054220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054225  mov     rcx, [rbp+57h+ppInterface]
0x180054229  test    rcx, rcx
0x18005422c  jz      short loc_18005423A
0x18005422e  mov     rax, [rcx]
0x180054231  mov     rax, [rax+10h]
0x180054235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005423a  test    ebx, ebx
0x18005423c  jz      short loc_180054268
0x18005423e  mov     rcx, cs:WPP_GLOBAL_Control
0x180054245  cmp     rcx, r15
0x180054248  jz      short loc_180054268
0x18005424a  test    byte ptr [rcx+1Ch], 1
0x18005424e  jz      short loc_180054268
0x180054250  mov     rcx, [rcx+10h]
0x180054254  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x18005425b  mov     edx, 1Ch
0x180054260  mov     r9d, ebx
0x180054263  call    WPP_SF_d
0x180054268  mov     eax, ebx
0x18005426a  mov     rcx, [rbp+57h+var_38]
0x18005426e  xor     rcx, rsp; StackCookie
0x180054271  call    __security_check_cookie
0x180054276  add     rsp, 0A8h
0x18005427d  pop     r15
0x18005427f  pop     r14
0x180054281  pop     r13
0x180054283  pop     r12
0x180054285  pop     rbx
0x180054286  pop     rbp
0x180054287  retn
```
