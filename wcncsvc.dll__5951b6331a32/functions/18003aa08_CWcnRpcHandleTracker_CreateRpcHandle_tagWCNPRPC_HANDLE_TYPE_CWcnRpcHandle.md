# CWcnRpcHandleTracker::CreateRpcHandle(tagWCNPRPC_HANDLE_TYPE,CWcnRpcHandle * *)

- ea: `0x18003aa08`
- end: `0x18003ad07`
- name: `?CreateRpcHandle@CWcnRpcHandleTracker@@QEAAJW4tagWCNPRPC_HANDLE_TYPE@@PEAPEAVCWcnRpcHandle@@@Z`
- size: `767`
- prototype: `__int64 __fastcall(__int64, int, CWcnRpcHandle **)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180034d20`
- `0x180034fd0`
- `0x180035c70`
- `0x180037d20`

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18003aa08`
- `0x18003ad10`
- `0x18003b0c0`
- `0x18003bdb0`
- `0x180053004`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003ac79`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ac79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003abfd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003abfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ac5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ac5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aafe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aafe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ab8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ab8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003aae0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003aae0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003aaf4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003aaf4`
- `RPCRT4!RpcRevertToSelf` at `0x18003ab27`
- `RPCRT4!RpcRevertToSelf` at `0x18003ab31`
- `RPCRT4!RpcRevertToSelf` at `0x18003ab27`
- `RPCRT4!RpcRevertToSelf` at `0x18003ab31`
- `RPCRT4!RpcImpersonateClient` at `0x18003aac9`
- `RPCRT4!RpcImpersonateClient` at `0x18003aac9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003ab52`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003ab52`

## pseudocode

```c
__int64 __fastcall CWcnRpcHandleTracker::CreateRpcHandle(__int64 a1, int a2, CWcnRpcHandle **a3)
{
  const char *Indent; // rax
  __int64 v7; // r10
  _QWORD *v8; // r10
  const char *v9; // rax
  __int64 v10; // r10
  signed int PerSessionData; // ebx
  RPC_STATUS v12; // eax
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  unsigned int v17; // ebx
  CWcnRpcHandle *v18; // rax
  CWcnRpcHandle *v19; // rdi
  struct CWcnRpcHandleTracker::tagPER_SESSION_DATA *v20; // rax
  unsigned int v21; // eax
  __int64 v22; // r10
  int v23; // r8d
  unsigned int v24; // eax
  __int64 v25; // r10
  void *TokenHandle; // [rsp+40h] [rbp-10h] BYREF
  struct CWcnRpcHandleTracker::tagPER_SESSION_DATA *v28; // [rsp+48h] [rbp-8h] BYREF
  unsigned int TokenInformation; // [rsp+80h] [rbp+30h] BYREF
  DWORD ReturnLength; // [rsp+98h] [rbp+48h] BYREF

  TokenInformation = 0;
  v28 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 11, WPP_165a2173c9f535ad9d13d67bd3efb8eb_Traceguids, Indent);
  }
  if ( !*(_DWORD *)(a1 + 64) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v10 + 16), 12, WPP_165a2173c9f535ad9d13d67bd3efb8eb_Traceguids, v9);
      v8 = WPP_GLOBAL_Control;
    }
    PerSessionData = -2147023641;
    goto LABEL_44;
  }
  TokenHandle = 0;
  v12 = RpcImpersonateClient(0);
  LastError = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      goto LABEL_21;
    goto LABEL_22;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    PerSessionData = 0;
    RpcRevertToSelf();
    ReturnLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
      goto LABEL_23;
    if ( (int)GetLastError() > 0 )
    {
      LOWORD(v12) = GetLastError();
LABEL_21:
      LastError = (unsigned __int16)v12 | 0x80070000;
      goto LABEL_22;
    }
    LastError = GetLastError();
LABEL_22:
    PerSessionData = LastError | 0x80000000;
    goto LABEL_23;
  }
  if ( (int)GetLastError() > 0 )
    v15 = (unsigned __int16)GetLastError() | 0x80070000;
  else
    v15 = GetLastError();
  PerSessionData = v15 | 0x80000000;
  RpcRevertToSelf();
LABEL_23:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( PerSessionData >= 0 )
  {
    v17 = TokenInformation;
    v18 = (CWcnRpcHandle *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v19 = v18;
    if ( v18 )
    {
      *((_DWORD *)v18 + 1) = a2;
      *((_QWORD *)v18 + 1) = 0;
      *((_QWORD *)v18 + 2) = 0;
      *((_DWORD *)v18 + 6) = v17;
      *(_DWORD *)v18 = 1749959511;
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      PerSessionData = CWcnRpcHandleTracker::GetPerSessionData((CWcnRpcHandleTracker *)a1, TokenInformation, &v28);
      if ( PerSessionData >= 0 )
      {
        v20 = v28;
        if ( *(_DWORD *)v28 < 0x1Eu )
        {
          *((_QWORD *)v19 + 2) = a1;
          ++*(_DWORD *)v20;
        }
        else
        {
          PerSessionData = -2147023604;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v21 = (unsigned int)GetIndent(0);
            WPP_SF_sDDd(*(_QWORD *)(v22 + 16), TokenInformation, v23, v21, TokenInformation);
          }
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      if ( PerSessionData < 0 )
      {
        CWcnRpcHandle::~CWcnRpcHandle(v19);
        operator delete(v19);
      }
      else
      {
        *a3 = v19;
      }
      goto LABEL_43;
    }
    PerSessionData = -2147024882;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)PerSessionData;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_44;
    v16 = 14;
LABEL_42:
    WPP_SF_d(v8[2], v16, WPP_165a2173c9f535ad9d13d67bd3efb8eb_Traceguids, (unsigned int)PerSessionData);
LABEL_43:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_44;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)PerSessionData;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = 13;
    goto LABEL_42;
  }
LABEL_44:
  if ( v8 != &WPP_GLOBAL_Control && (PerSessionData < 0 || *((_BYTE *)v8 + 25) >= 6u) )
  {
    v24 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(
      *(_QWORD *)(v25 + 16),
      16,
      (unsigned int)WPP_165a2173c9f535ad9d13d67bd3efb8eb_Traceguids,
      v24,
      PerSessionData);
  }
  return (unsigned int)PerSessionData;
}

```

## disassembly

```asm
0x18003aa08  mov     [rsp-28h+arg_8], rbx
0x18003aa0d  mov     [rsp-28h+arg_10], rsi
0x18003aa12  push    rbp
0x18003aa13  push    rdi
0x18003aa14  push    r13
0x18003aa16  push    r14
0x18003aa18  push    r15
0x18003aa1a  mov     rbp, rsp
0x18003aa1d  sub     rsp, 50h
0x18003aa21  mov     r15, r8
0x18003aa24  mov     [rbp+TokenInformation], 0
0x18003aa2b  mov     esi, edx
0x18003aa2d  mov     [rbp+var_8], 0
0x18003aa35  mov     r14, rcx
0x18003aa38  mov     r10, cs:WPP_GLOBAL_Control
0x18003aa3f  lea     r13, WPP_GLOBAL_Control
0x18003aa46  cmp     r10, r13
0x18003aa49  jz      short loc_18003AA74
0x18003aa4b  cmp     byte ptr [r10+19h], 6
0x18003aa50  jb      short loc_18003AA74
0x18003aa52  mov     ecx, 1; int
0x18003aa57  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003aa5c  mov     rcx, [r10+10h]
0x18003aa60  lea     r8, WPP_165a2173c9f535ad9d13d67bd3efb8eb_Traceguids
0x18003aa67  mov     edx, 0Bh
0x18003aa6c  mov     r9, rax
0x18003aa6f  call    WPP_SF_s
0x18003aa74  mov     eax, [r14+40h]
0x18003aa78  test    eax, eax
0x18003aa7a  jnz     short loc_18003AABF
0x18003aa7c  mov     r10, cs:WPP_GLOBAL_Control
0x18003aa83  cmp     r10, r13
0x18003aa86  jz      short loc_18003AAB5
0x18003aa88  cmp     byte ptr [r10+19h], 2
0x18003aa8d  jb      short loc_18003AAB5
0x18003aa8f  xor     ecx, ecx; int
0x18003aa91  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003aa96  mov     rcx, [r10+10h]
0x18003aa9a  lea     r8, WPP_165a2173c9f535ad9d13d67bd3efb8eb_Traceguids
0x18003aaa1  mov     edx, 0Ch
0x18003aaa6  mov     r9, rax
0x18003aaa9  call    WPP_SF_s
0x18003aaae  mov     r10, cs:WPP_GLOBAL_Control
0x18003aab5  mov     ebx, 800704E7h
0x18003aaba  jmp     loc_18003ACB8
0x18003aabf  xor     ecx, ecx; BindingHandle
0x18003aac1  mov     [rbp+TokenHandle], 0
0x18003aac9  call    cs:__imp_RpcImpersonateClient
0x18003aacf  mov     ebx, eax
0x18003aad1  test    eax, eax
0x18003aad3  jz      short loc_18003AAE0
0x18003aad5  jle     loc_18003AB7F
0x18003aadb  jmp     loc_18003AB76
0x18003aae0  call    cs:__imp_GetCurrentThread
0x18003aae6  xor     r8d, r8d; OpenAsSelf
0x18003aae9  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18003aaed  mov     rcx, rax; ThreadHandle
0x18003aaf0  lea     edx, [r8+8]; DesiredAccess
0x18003aaf4  call    cs:__imp_OpenThreadToken
0x18003aafa  test    eax, eax
0x18003aafc  jnz     short loc_18003AB2F
0x18003aafe  call    cs:__imp_GetLastError
0x18003ab04  test    eax, eax
0x18003ab06  jg      short loc_18003AB12
0x18003ab08  call    cs:__imp_GetLastError
0x18003ab0e  mov     ebx, eax
0x18003ab10  jmp     short loc_18003AB21
0x18003ab12  call    cs:__imp_GetLastError
0x18003ab18  movzx   ebx, ax
0x18003ab1b  or      ebx, 80070000h
0x18003ab21  or      ebx, 80000000h
0x18003ab27  call    cs:__imp_RpcRevertToSelf
0x18003ab2d  jmp     short loc_18003AB85
0x18003ab2f  xor     ebx, ebx
0x18003ab31  call    cs:__imp_RpcRevertToSelf
0x18003ab37  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003ab3b  lea     rax, [rbp+arg_18]
0x18003ab3f  lea     r9d, [rbx+4]; TokenInformationLength
0x18003ab43  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18003ab48  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18003ab4c  mov     [rbp+arg_18], ebx
0x18003ab4f  lea     edx, [rbx+0Ch]; TokenInformationClass
0x18003ab52  call    cs:__imp_GetTokenInformation
0x18003ab58  test    eax, eax
0x18003ab5a  jnz     short loc_18003AB85
0x18003ab5c  call    cs:__imp_GetLastError
0x18003ab62  test    eax, eax
0x18003ab64  jg      short loc_18003AB70
0x18003ab66  call    cs:__imp_GetLastError
0x18003ab6c  mov     ebx, eax
0x18003ab6e  jmp     short loc_18003AB7F
0x18003ab70  call    cs:__imp_GetLastError
0x18003ab76  movzx   ebx, ax
0x18003ab79  or      ebx, 80070000h
0x18003ab7f  or      ebx, 80000000h
0x18003ab85  mov     rcx, [rbp+TokenHandle]; hObject
0x18003ab89  test    rcx, rcx
0x18003ab8c  jz      short loc_18003AB94
0x18003ab8e  call    cs:__imp_CloseHandle
0x18003ab94  test    ebx, ebx
0x18003ab96  jns     short loc_18003ABBD
0x18003ab98  mov     r10, cs:WPP_GLOBAL_Control
0x18003ab9f  cmp     r10, r13
0x18003aba2  jz      loc_18003ACEC
0x18003aba8  cmp     byte ptr [r10+19h], 2
0x18003abad  jb      loc_18003ACB8
0x18003abb3  mov     edx, 0Dh
0x18003abb8  jmp     loc_18003AC9E
0x18003abbd  mov     ebx, [rbp+TokenInformation]
0x18003abc0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003abc7  mov     ecx, 20h ; ' '; unsigned __int64
0x18003abcc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003abd1  mov     rdi, rax
0x18003abd4  test    rax, rax
0x18003abd7  jz      loc_18003AC81
0x18003abdd  lea     rcx, [r14+10h]; lpCriticalSection
0x18003abe1  mov     [rax+4], esi
0x18003abe4  mov     qword ptr [rax+8], 0
0x18003abec  mov     qword ptr [rax+10h], 0
0x18003abf4  mov     [rax+18h], ebx
0x18003abf7  mov     dword ptr [rax], 684E4357h
0x18003abfd  call    cs:__imp_EnterCriticalSection
0x18003ac03  mov     edx, [rbp+TokenInformation]; unsigned int
0x18003ac06  lea     r8, [rbp+var_8]; struct CWcnRpcHandleTracker::tagPER_SESSION_DATA **
0x18003ac0a  mov     rcx, r14; this
0x18003ac0d  call    ?GetPerSessionData@CWcnRpcHandleTracker@@AEAAJKPEAPEAUtagPER_SESSION_DATA@1@@Z; CWcnRpcHandleTracker::GetPerSessionData(ulong,CWcnRpcHandleTracker::tagPER_SESSION_DATA * *)
0x18003ac12  mov     ebx, eax
0x18003ac14  test    eax, eax
0x18003ac16  js      short loc_18003AC5B
0x18003ac18  mov     rax, [rbp+var_8]
0x18003ac1c  cmp     dword ptr [rax], 1Eh
0x18003ac1f  jb      short loc_18003AC55
0x18003ac21  mov     ebx, 8007050Ch
0x18003ac26  mov     r10, cs:WPP_GLOBAL_Control
0x18003ac2d  cmp     r10, r13
0x18003ac30  jz      short loc_18003AC5B
0x18003ac32  cmp     byte ptr [r10+19h], 3
0x18003ac37  jb      short loc_18003AC5B
0x18003ac39  xor     ecx, ecx; int
0x18003ac3b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003ac40  mov     edx, [rbp+TokenInformation]
0x18003ac43  mov     r9, rax
0x18003ac46  mov     rcx, [r10+10h]
0x18003ac4a  mov     dword ptr [rsp+50h+ReturnLength], edx
0x18003ac4e  call    WPP_SF_sDDd
0x18003ac53  jmp     short loc_18003AC5B
0x18003ac55  mov     [rdi+10h], r14
0x18003ac59  inc     dword ptr [rax]
0x18003ac5b  lea     rcx, [r14+10h]; lpCriticalSection
0x18003ac5f  call    cs:__imp_LeaveCriticalSection
0x18003ac65  test    ebx, ebx
0x18003ac67  js      short loc_18003AC6E
0x18003ac69  mov     [r15], rdi
0x18003ac6c  jmp     short loc_18003ACB1
0x18003ac6e  mov     rcx, rdi; this
0x18003ac71  call    ??1CWcnRpcHandle@@QEAA@XZ; CWcnRpcHandle::~CWcnRpcHandle(void)
0x18003ac76  mov     rcx, rdi
0x18003ac79  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003ac7f  jmp     short loc_18003ACB1
0x18003ac81  mov     ebx, 8007000Eh
0x18003ac86  mov     r10, cs:WPP_GLOBAL_Control
0x18003ac8d  cmp     r10, r13
0x18003ac90  jz      short loc_18003ACEC
0x18003ac92  cmp     byte ptr [r10+19h], 2
0x18003ac97  jb      short loc_18003ACB8
0x18003ac99  mov     edx, 0Eh
0x18003ac9e  mov     rcx, [r10+10h]
0x18003aca2  lea     r8, WPP_165a2173c9f535ad9d13d67bd3efb8eb_Traceguids
0x18003aca9  mov     r9d, ebx
0x18003acac  call    WPP_SF_d
0x18003acb1  mov     r10, cs:WPP_GLOBAL_Control
0x18003acb8  cmp     r10, r13
0x18003acbb  jz      short loc_18003ACEC
0x18003acbd  test    ebx, ebx
0x18003acbf  js      short loc_18003ACC8
0x18003acc1  cmp     byte ptr [r10+19h], 6
0x18003acc6  jb      short loc_18003ACEC
0x18003acc8  or      ecx, 0FFFFFFFFh; int
0x18003accb  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003acd0  mov     rcx, [r10+10h]
0x18003acd4  lea     r8, WPP_165a2173c9f535ad9d13d67bd3efb8eb_Traceguids
0x18003acdb  mov     edx, 10h
0x18003ace0  mov     dword ptr [rsp+50h+ReturnLength], ebx
0x18003ace4  mov     r9, rax
0x18003ace7  call    WPP_SF_sd
0x18003acec  lea     r11, [rsp+50h+var_s0]
0x18003acf1  mov     eax, ebx
0x18003acf3  mov     rbx, [r11+38h]
0x18003acf7  mov     rsi, [r11+40h]
0x18003acfb  mov     rsp, r11
0x18003acfe  pop     r15
0x18003ad00  pop     r14
0x18003ad02  pop     r13
0x18003ad04  pop     rdi
0x18003ad05  pop     rbp
0x18003ad06  retn
```
