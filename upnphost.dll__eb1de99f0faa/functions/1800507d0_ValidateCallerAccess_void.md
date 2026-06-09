# ValidateCallerAccess(void)

- ea: `0x1800507d0`
- end: `0x180050b90`
- name: `?ValidateCallerAccess@@YAJXZ`
- size: `960`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002dd70`
- `0x1800479b0`
- `0x180047b60`
- `0x180047fc4`
- `0x180050164`

## callees

- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x1800507d0`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005090b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800509a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800509cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050ac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005090b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800509a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800509cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050ac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050ae7`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18005081f`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18005081f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180050882`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180050882`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005086c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005086c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050ab1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050ab1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800508d7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180050a36`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800508d7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180050a36`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180050958`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180050958`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005094c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005094c`

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
0x1800507d0  push    rbp
0x1800507d2  push    rbx
0x1800507d3  push    r12
0x1800507d5  push    r13
0x1800507d7  push    r14
0x1800507d9  push    r15
0x1800507db  lea     rbp, [rsp-2Fh]
0x1800507e0  sub     rsp, 0A8h
0x1800507e7  mov     rax, cs:__security_cookie
0x1800507ee  xor     rax, rsp
0x1800507f1  mov     [rbp+57h+var_38], rax
0x1800507f5  xor     r13d, r13d
0x1800507f8  mov     [rbp+57h+nSubAuthority0], 12h
0x1800507ff  lea     rdx, [rbp+57h+ppInterface]; ppInterface
0x180050803  mov     [rbp+57h+ppInterface], r13
0x180050807  lea     rcx, IID_IServerSecurity; riid
0x18005080e  mov     [rbp+57h+var_4C], 13h
0x180050815  mov     r12d, r13d
0x180050818  mov     [rbp+57h+var_48], 14h
0x18005081f  call    cs:__imp_CoGetCallContext
0x180050825  lea     r15, WPP_GLOBAL_Control
0x18005082c  mov     ebx, eax
0x18005082e  test    eax, eax
0x180050830  js      loc_180050B0E
0x180050836  mov     rcx, [rbp+57h+ppInterface]
0x18005083a  mov     rdx, [rcx]
0x18005083d  mov     rax, [rdx+30h]
0x180050841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050846  test    eax, eax
0x180050848  jnz     short loc_180050868
0x18005084a  mov     rcx, [rbp+57h+ppInterface]
0x18005084e  mov     rax, [rcx]
0x180050851  mov     rax, [rax+20h]
0x180050855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005085a  mov     ebx, eax
0x18005085c  test    eax, eax
0x18005085e  js      loc_180050B0E
0x180050864  lea     r12d, [r13+1]
0x180050868  mov     [rbp+57h+TokenHandle], r13
0x18005086c  call    cs:__imp_GetCurrentThread
0x180050872  mov     edx, 8; DesiredAccess
0x180050877  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18005087b  mov     rcx, rax; ThreadHandle
0x18005087e  lea     r8d, [rdx-7]; OpenAsSelf
0x180050882  call    cs:__imp_OpenThreadToken
0x180050888  test    eax, eax
0x18005088a  jz      loc_180050AC0
0x180050890  lea     rax, [rbp+57h+SidToCheck]
0x180050894  mov     [rbp+57h+SidToCheck], r13
0x180050898  mov     [rsp+0D0h+pSid], rax; pSid
0x18005089d  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800508a1  mov     [rsp+0D0h+nSubAuthority7], r13d; nSubAuthority7
0x1800508a6  mov     r9d, 220h; nSubAuthority1
0x1800508ac  mov     [rsp+0D0h+nSubAuthority6], r13d; nSubAuthority6
0x1800508b1  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800508b7  mov     [rsp+0D0h+nSubAuthority5], r13d; nSubAuthority5
0x1800508bc  mov     dl, 2; nSubAuthorityCount
0x1800508be  mov     [rsp+0D0h+nSubAuthority4], r13d; nSubAuthority4
0x1800508c3  mov     [rsp+0D0h+nSubAuthority3], r13d; nSubAuthority3
0x1800508c8  mov     [rsp+0D0h+nSubAuthority2], r13d; nSubAuthority2
0x1800508cd  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x1800508d1  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800508d7  call    cs:__imp_AllocateAndInitializeSid
0x1800508dd  mov     r14d, eax
0x1800508e0  test    eax, eax
0x1800508e2  jnz     short loc_180050930
0x1800508e4  call    cs:__imp_GetLastError
0x1800508ea  mov     ebx, eax
0x1800508ec  test    eax, eax
0x1800508ee  jle     short loc_1800508F9
0x1800508f0  movzx   ebx, ax
0x1800508f3  or      ebx, 80070000h
0x1800508f9  mov     rax, cs:WPP_GLOBAL_Control
0x180050900  cmp     rax, r15
0x180050903  jz      short loc_180050930
0x180050905  test    byte ptr [rax+1Ch], 40h
0x180050909  jz      short loc_180050930
0x18005090b  call    cs:__imp_GetLastError
0x180050911  mov     rcx, cs:WPP_GLOBAL_Control
0x180050918  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x18005091f  mov     edx, 17h
0x180050924  mov     r9d, eax
0x180050927  mov     rcx, [rcx+10h]
0x18005092b  call    WPP_SF_d
0x180050930  mov     r15d, r13d
0x180050933  test    r14d, r14d
0x180050936  jz      loc_180050AAD
0x18005093c  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180050940  lea     r8, [rbp+57h+IsMember]; IsMember
0x180050944  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180050948  mov     [rbp+57h+IsMember], r13d
0x18005094c  call    cs:__imp_CheckTokenMembership
0x180050952  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x180050956  mov     ebx, eax
0x180050958  call    cs:__imp_FreeSid
0x18005095e  test    ebx, ebx
0x180050960  jz      short loc_1800509A1
0x180050962  cmp     [rbp+57h+IsMember], r13d
0x180050966  jnz     loc_180050AAA
0x18005096c  mov     ebx, 80070005h
0x180050971  mov     rcx, cs:WPP_GLOBAL_Control
0x180050978  lea     rax, WPP_GLOBAL_Control
0x18005097f  cmp     rcx, rax
0x180050982  jz      short loc_1800509F4
0x180050984  test    byte ptr [rcx+1Ch], 40h
0x180050988  jz      short loc_1800509F4
0x18005098a  mov     rcx, [rcx+10h]
0x18005098e  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x180050995  mov     edx, 18h
0x18005099a  call    WPP_SF_
0x18005099f  jmp     short loc_1800509F4
0x1800509a1  call    cs:__imp_GetLastError
0x1800509a7  mov     ebx, eax
0x1800509a9  test    eax, eax
0x1800509ab  jle     short loc_1800509B6
0x1800509ad  movzx   ebx, ax
0x1800509b0  or      ebx, 80070000h
0x1800509b6  mov     rax, cs:WPP_GLOBAL_Control
0x1800509bd  lea     rcx, WPP_GLOBAL_Control
0x1800509c4  cmp     rax, rcx
0x1800509c7  jz      short loc_1800509F4
0x1800509c9  test    byte ptr [rax+1Ch], 40h
0x1800509cd  jz      short loc_1800509F4
0x1800509cf  call    cs:__imp_GetLastError
0x1800509d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800509dc  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x1800509e3  mov     edx, 19h
0x1800509e8  mov     r9d, eax
0x1800509eb  mov     rcx, [rcx+10h]
0x1800509ef  call    WPP_SF_d
0x1800509f4  cmp     r15d, 3
0x1800509f8  jnb     loc_180050AAD
0x1800509fe  lea     rax, [rbp+57h+SidToCheck]
0x180050a02  mov     r8d, r15d
0x180050a05  mov     [rsp+0D0h+pSid], rax; pSid
0x180050a0a  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180050a0e  mov     [rsp+0D0h+nSubAuthority7], r13d; nSubAuthority7
0x180050a13  xor     r9d, r9d; nSubAuthority1
0x180050a16  mov     [rsp+0D0h+nSubAuthority6], r13d; nSubAuthority6
0x180050a1b  mov     dl, 1; nSubAuthorityCount
0x180050a1d  mov     r8d, [rbp+r8*4+57h+nSubAuthority0]; nSubAuthority0
0x180050a22  mov     [rsp+0D0h+nSubAuthority5], r13d; nSubAuthority5
0x180050a27  mov     [rsp+0D0h+nSubAuthority4], r13d; nSubAuthority4
0x180050a2c  mov     [rsp+0D0h+nSubAuthority3], r13d; nSubAuthority3
0x180050a31  mov     [rsp+0D0h+nSubAuthority2], r13d; nSubAuthority2
0x180050a36  call    cs:__imp_AllocateAndInitializeSid
0x180050a3c  inc     r15d
0x180050a3f  mov     r14d, eax
0x180050a42  test    eax, eax
0x180050a44  jnz     loc_180050933
0x180050a4a  call    cs:__imp_GetLastError
0x180050a50  mov     ebx, eax
0x180050a52  test    eax, eax
0x180050a54  jle     short loc_180050A5F
0x180050a56  movzx   ebx, ax
0x180050a59  or      ebx, 80070000h
0x180050a5f  mov     rax, cs:WPP_GLOBAL_Control
0x180050a66  lea     rcx, WPP_GLOBAL_Control
0x180050a6d  cmp     rax, rcx
0x180050a70  jz      loc_180050933
0x180050a76  test    byte ptr [rax+1Ch], 40h
0x180050a7a  jz      loc_180050933
0x180050a80  call    cs:__imp_GetLastError
0x180050a86  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a8d  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x180050a94  mov     edx, 1Ah
0x180050a99  mov     r9d, eax
0x180050a9c  mov     rcx, [rcx+10h]
0x180050aa0  call    WPP_SF_d
0x180050aa5  jmp     loc_180050933
0x180050aaa  mov     ebx, r13d
0x180050aad  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180050ab1  call    cs:__imp_CloseHandle
0x180050ab7  lea     r15, WPP_GLOBAL_Control
0x180050abe  jmp     short loc_180050B18
0x180050ac0  call    cs:__imp_GetLastError
0x180050ac6  mov     ebx, eax
0x180050ac8  test    eax, eax
0x180050aca  jle     short loc_180050AD5
0x180050acc  movzx   ebx, ax
0x180050acf  or      ebx, 80070000h
0x180050ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x180050adc  cmp     rcx, r15
0x180050adf  jz      short loc_180050B18
0x180050ae1  test    byte ptr [rcx+1Ch], 40h
0x180050ae5  jz      short loc_180050B18
0x180050ae7  call    cs:__imp_GetLastError
0x180050aed  mov     rcx, cs:WPP_GLOBAL_Control
0x180050af4  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x180050afb  mov     edx, 1Bh
0x180050b00  mov     r9d, eax
0x180050b03  mov     rcx, [rcx+10h]
0x180050b07  call    WPP_SF_d
0x180050b0c  jmp     short loc_180050B18
0x180050b0e  cmp     ebx, 80010117h
0x180050b14  cmovz   ebx, r13d
0x180050b18  test    r12d, r12d
0x180050b1b  jz      short loc_180050B2D
0x180050b1d  mov     rcx, [rbp+57h+ppInterface]
0x180050b21  mov     rax, [rcx]
0x180050b24  mov     rax, [rax+28h]
0x180050b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b2d  mov     rcx, [rbp+57h+ppInterface]
0x180050b31  test    rcx, rcx
0x180050b34  jz      short loc_180050B42
0x180050b36  mov     rax, [rcx]
0x180050b39  mov     rax, [rax+10h]
0x180050b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b42  test    ebx, ebx
0x180050b44  jz      short loc_180050B70
0x180050b46  mov     rcx, cs:WPP_GLOBAL_Control
0x180050b4d  cmp     rcx, r15
0x180050b50  jz      short loc_180050B70
0x180050b52  test    byte ptr [rcx+1Ch], 1
0x180050b56  jz      short loc_180050B70
0x180050b58  mov     rcx, [rcx+10h]
0x180050b5c  lea     r8, WPP_cfeffffca17e32bb09beafeef3f68c4e_Traceguids
0x180050b63  mov     edx, 1Ch
0x180050b68  mov     r9d, ebx
0x180050b6b  call    WPP_SF_d
0x180050b70  mov     eax, ebx
0x180050b72  mov     rcx, [rbp+57h+var_38]
0x180050b76  xor     rcx, rsp; StackCookie
0x180050b79  call    __security_check_cookie
0x180050b7e  add     rsp, 0A8h
0x180050b85  pop     r15
0x180050b87  pop     r14
0x180050b89  pop     r13
0x180050b8b  pop     r12
0x180050b8d  pop     rbx
0x180050b8e  pop     rbp
0x180050b8f  retn
```
