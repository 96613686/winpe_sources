# I_RedirectionContextLookupItem(_REDIRECTION_CONTEXT * *,_REDIRECTION_CONTEXT * *)

- ea: `0x180013590`
- end: `0x180013ac5`
- name: `?I_RedirectionContextLookupItem@@YAKPEAPEAU_REDIRECTION_CONTEXT@@0@Z`
- size: `1333`
- prototype: `unsigned int __fastcall(struct _REDIRECTION_CONTEXT **, struct _REDIRECTION_CONTEXT **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000605c`

## callees

- `0x180006890`
- `0x180013590`
- `0x18001991c`
- `0x1800239b8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180013781`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180013781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001372c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001378b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001372c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001378b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001374f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001374f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800135bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800135bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001370c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001370c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013722`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013722`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001373c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001373c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001379e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001379e`

## pseudocode

```c
__int64 __fastcall I_RedirectionContextLookupItem(LPCRITICAL_SECTION *a1, LPCRITICAL_SECTION *a2)
{
  LPCRITICAL_SECTION DebugInfo; // rbx
  DWORD LastError; // r15d
  DWORD CurrentThreadId; // eax
  int v7; // r10d
  unsigned __int64 *v8; // rdx
  int v9; // edi
  DWORD v10; // r9d
  int v11; // r8d
  unsigned int i; // eax
  bool v13; // zf
  int v14; // edx
  int v15; // r10d
  char *v16; // rcx
  int v17; // r13d
  __int64 v18; // rbp
  __int64 v19; // rdx
  char *v20; // rax
  const char *v21; // r9
  char *v22; // r8
  __int64 v23; // rax
  char *v24; // rax
  LPCRITICAL_SECTION v25; // rax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  int SpinCount; // eax
  DWORD v29; // eax
  unsigned __int64 v30; // rdx
  int v31; // r10d
  unsigned int j; // ecx
  bool v33; // zf
  int v34; // r11d
  char *v35; // rcx
  char *v36; // rax
  char *v37; // r12
  const char *v38; // rax
  __int64 v39; // r8
  char *v40; // rax
  __int64 v42; // rdx
  int v43; // r10d
  int v44; // r11d
  int v45; // r11d
  void *TokenHandle[9]; // [rsp+30h] [rbp-48h] BYREF
  int TokenInformation; // [rsp+90h] [rbp+18h] BYREF
  DWORD ReturnLength; // [rsp+98h] [rbp+20h] BYREF

  DebugInfo = g_pRedirectionContextList;
  LastError = 0;
  TokenInformation = 0;
  CurrentThreadId = GetCurrentThreadId();
  v7 = `WppTraceIndent'::`2'::idxCurrentThread;
  v8 = &`WppTraceIndent'::`2'::ThreadTable;
  v9 = -1;
  v10 = CurrentThreadId;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v7 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
    dword_180045874 = 0;
    goto LABEL_15;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != CurrentThreadId )
  {
    v11 = -1;
    for ( i = 0; ; ++i )
    {
      v13 = i == 32;
      if ( i >= 0x20 )
        break;
      v14 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
      if ( v14 == v10 )
      {
        v7 = i;
        `WppTraceIndent'::`2'::idxCurrentThread = i;
        v8 = &`WppTraceIndent'::`2'::ThreadTable;
        v13 = i == 32;
        break;
      }
      if ( v11 == -1 && !v14 )
        v11 = i;
      v8 = &`WppTraceIndent'::`2'::ThreadTable;
    }
    if ( v13 )
    {
      if ( v11 == -1 )
      {
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_78;
      }
      v7 = v11;
      `WppTraceIndent'::`2'::idxCurrentThread = v11;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v11) = v10;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v11 + 1) = 0;
    }
  }
  if ( v7 >= 0 )
  {
LABEL_15:
    v15 = ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v7 + 1);
    goto LABEL_16;
  }
LABEL_78:
  v15 = 0;
LABEL_16:
  v16 = (char *)WPP_GLOBAL_Control;
  v17 = 1;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v15 >= 1 )
  {
    while ( !(unsigned int)StringCbCatA(v16, (unsigned __int64)v8, "..") && v44 + 1 <= v43 )
      ;
    v16 = (char *)WPP_GLOBAL_Control;
  }
  v18 = 256;
  v19 = 256;
  v20 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v20 )
  {
    ++v20;
    if ( !--v19 )
      goto LABEL_26;
  }
  v21 = ">";
  v22 = (char *)&`wil::SetLastError'::`5'::depth - v19;
  v23 = 2147483646;
  do
  {
    if ( !v23 )
      break;
    if ( !*v21 )
      break;
    *v22++ = *v21++;
    --v23;
    --v19;
  }
  while ( v19 );
  v24 = v22 - 1;
  if ( v19 )
    v24 = v22;
  *v24 = 0;
LABEL_26:
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v16 != (char *)&WPP_GLOBAL_Control && (v16[28] & 2) != 0 && (unsigned __int8)v16[25] >= 5u )
    WPP_SF_s(*((_QWORD *)v16 + 2), 20, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
  v25 = *a1;
  *a2 = 0;
  if ( v25 )
  {
    SpinCount = v25[1].SpinCount;
    TokenInformation = SpinCount;
    *a1 = 0;
    goto LABEL_39;
  }
  TokenHandle[0] = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_35;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
    {
LABEL_34:
      LastError = GetLastError();
      goto LABEL_35;
    }
    LastError = 0;
  }
  if ( !GetTokenInformation(TokenHandle[0], TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    goto LABEL_34;
LABEL_35:
  if ( TokenHandle[0] )
    CloseHandle(TokenHandle[0]);
  if ( LastError )
    goto LABEL_44;
  SpinCount = TokenInformation;
LABEL_39:
  if ( DebugInfo )
  {
    while ( SpinCount != LODWORD(DebugInfo[1].SpinCount) )
    {
      *a2 = DebugInfo;
      DebugInfo = (LPCRITICAL_SECTION)DebugInfo[12].DebugInfo;
      if ( !DebugInfo )
        goto LABEL_40;
    }
    *a1 = DebugInfo;
  }
  else
  {
LABEL_40:
    LastError = 1168;
  }
LABEL_44:
  v29 = GetCurrentThreadId();
  v31 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v31 = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v29;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_180045874 = 0;
    goto LABEL_58;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != v29 )
  {
    for ( j = 0; ; ++j )
    {
      v33 = j == 32;
      if ( j >= 0x20 )
        break;
      v30 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)j);
      if ( (_DWORD)v30 == v29 )
      {
        v31 = j;
        `WppTraceIndent'::`2'::idxCurrentThread = j;
        v33 = j == 32;
        break;
      }
      if ( v9 == -1 && !(_DWORD)v30 )
        v9 = j;
    }
    if ( v33 )
    {
      if ( v9 == -1 )
      {
        v31 = -2;
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_80;
      }
      v31 = v9;
      `WppTraceIndent'::`2'::idxCurrentThread = v9;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v9) = v29;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v9 + 1) = 0;
    }
  }
  if ( v31 >= 0 )
  {
LABEL_58:
    v34 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v31 + 1);
    goto LABEL_59;
  }
LABEL_80:
  v34 = 0;
LABEL_59:
  v35 = (char *)WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v34 >= 1 )
  {
    do
    {
      if ( (unsigned int)StringCbCatA(v35, v30, "..") )
        break;
      ++v17;
    }
    while ( v17 <= v45 );
    v35 = (char *)WPP_GLOBAL_Control;
  }
  v36 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v36 )
  {
    ++v36;
    if ( !--v18 )
      goto LABEL_69;
  }
  v37 = (char *)&`wil::SetLastError'::`5'::depth - v18;
  v38 = "<";
  v39 = 2147483646;
  do
  {
    if ( !v39 )
      break;
    if ( !*v38 )
      break;
    *v37++ = *v38++;
    --v39;
    --v18;
  }
  while ( v18 );
  v40 = v37 - 1;
  if ( v18 )
    v40 = v37;
  *v40 = 0;
LABEL_69:
  if ( v31 >= 0 )
  {
    v42 = 8LL * v31;
    v13 = (*(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v42 + 4))-- == 1;
    if ( v13 )
      *(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v42) = 0;
  }
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v35 != (char *)&WPP_GLOBAL_Control && (v35[28] & 2) != 0 && (unsigned __int8)v35[25] >= 5u )
    WPP_SF_sd(
      *((_QWORD *)v35 + 2),
      21,
      (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
      (unsigned int)&`WppTraceIndent'::`2'::szIndentPrefix,
      LastError);
  return LastError;
}

```

## disassembly

```asm
0x180013590  mov     [rsp+arg_0], rbx
0x180013595  push    rbp
0x180013596  push    rsi
0x180013597  push    rdi
0x180013598  push    r12
0x18001359a  push    r13
0x18001359c  push    r14
0x18001359e  push    r15
0x1800135a0  sub     rsp, 40h
0x1800135a4  mov     rbx, cs:?g_pRedirectionContextList@@3PEAU_REDIRECTION_CONTEXT@@EA; _REDIRECTION_CONTEXT * g_pRedirectionContextList
0x1800135ab  xor     r15d, r15d
0x1800135ae  mov     [rsp+78h+TokenInformation], r15d
0x1800135b6  mov     r14, rdx
0x1800135b9  mov     rsi, rcx
0x1800135bc  call    cs:__imp_GetCurrentThreadId
0x1800135c2  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800135c9  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x1800135d0  mov     edi, 0FFFFFFFFh
0x1800135d5  mov     r9d, eax
0x1800135d8  cmp     r10d, edi
0x1800135db  jz      loc_1800137BD
0x1800135e1  cmp     r10d, 0FFFFFFFEh
0x1800135e5  jz      short loc_1800135ED
0x1800135e7  cmp     [rdx+r10*8], eax
0x1800135eb  jz      short loc_180013634
0x1800135ed  mov     r8d, edi
0x1800135f0  mov     eax, r15d
0x1800135f3  cmp     eax, 20h ; ' '
0x1800135f6  jnb     short loc_18001362E
0x1800135f8  movsxd  rcx, eax
0x1800135fb  mov     edx, [rdx+rcx*8]
0x1800135fe  cmp     edx, r9d
0x180013601  jz      short loc_18001361B
0x180013603  cmp     r8d, edi
0x180013606  jz      short loc_180013613
0x180013608  inc     eax
0x18001360a  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180013611  jmp     short loc_1800135F3
0x180013613  test    edx, edx
0x180013615  cmovz   r8d, eax
0x180013619  jmp     short loc_180013608
0x18001361b  mov     r10d, eax
0x18001361e  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, eax; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180013624  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; unsigned __int64
0x18001362b  cmp     eax, 20h ; ' '
0x18001362e  jz      loc_1800139A2
0x180013634  test    r10d, r10d
0x180013637  js      loc_180013963
0x18001363d  movsxd  rax, r10d
0x180013640  inc     dword ptr [rdx+rax*8+4]
0x180013644  mov     r10d, [rdx+rax*8+4]
0x180013649  mov     rcx, cs:WPP_GLOBAL_Control; char *
0x180013650  mov     r13d, 1
0x180013656  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, r15b; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18001365d  test    byte ptr [rcx+1Ch], 2
0x180013661  jnz     loc_180013A30
0x180013667  mov     ebp, 100h
0x18001366c  lea     r10, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180013673  mov     edx, ebp
0x180013675  mov     rax, r10
0x180013678  lea     r12, ?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001367f  cmp     [rax], r15b
0x180013682  jnz     loc_1800139F6
0x180013688  mov     r8, r12
0x18001368b  lea     r9, asc_1800382D0; ">"
0x180013692  sub     r8, rdx
0x180013695  mov     eax, 7FFFFFFEh
0x18001369a  test    rdx, rdx
0x18001369d  jz      short loc_1800136C5
0x18001369f  test    rax, rax
0x1800136a2  jz      short loc_1800136BE
0x1800136a4  movzx   r10d, byte ptr [r9]
0x1800136a8  test    r10b, r10b
0x1800136ab  jz      short loc_1800136BE
0x1800136ad  mov     [r8], r10b
0x1800136b0  inc     r9
0x1800136b3  inc     r8
0x1800136b6  dec     rax
0x1800136b9  sub     rdx, r13
0x1800136bc  jnz     short loc_18001369F
0x1800136be  lea     r10, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x1800136c5  test    rdx, rdx
0x1800136c8  lea     rax, [r8-1]
0x1800136cc  cmovnz  rax, r8
0x1800136d0  mov     [rax], r15b
0x1800136d3  mov     cs:?WPP_pszIndent@@3PEADEA, r10; char * WPP_pszIndent
0x1800136da  lea     rax, WPP_GLOBAL_Control
0x1800136e1  cmp     rcx, rax
0x1800136e4  jz      short loc_1800136F0
0x1800136e6  test    byte ptr [rcx+1Ch], 2
0x1800136ea  jnz     loc_180013A6A
0x1800136f0  mov     rax, [rsi]
0x1800136f3  mov     [r14], r15
0x1800136f6  test    rax, rax
0x1800136f9  jnz     loc_180013912
0x1800136ff  mov     [rsp+78h+TokenHandle], r15
0x180013704  mov     [rsp+78h+arg_18], r15d
0x18001370c  call    cs:__imp_GetCurrentThread
0x180013712  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x180013717  mov     r8d, r13d; OpenAsSelf
0x18001371a  mov     rcx, rax; ThreadHandle
0x18001371d  mov     edx, 8; DesiredAccess
0x180013722  call    cs:__imp_OpenThreadToken
0x180013728  test    eax, eax
0x18001372a  jnz     short loc_18001375C
0x18001372c  call    cs:__imp_GetLastError
0x180013732  mov     r15d, eax
0x180013735  cmp     eax, 3F0h
0x18001373a  jnz     short loc_180013794
0x18001373c  call    cs:__imp_GetCurrentProcess
0x180013742  lea     r8, [rsp+78h+TokenHandle]; TokenHandle
0x180013747  mov     edx, 8; DesiredAccess
0x18001374c  mov     rcx, rax; ProcessHandle
0x18001374f  call    cs:__imp_OpenProcessToken
0x180013755  test    eax, eax
0x180013757  jz      short loc_18001378B
0x180013759  xor     r15d, r15d
0x18001375c  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x180013761  lea     rax, [rsp+78h+arg_18]
0x180013769  mov     r9d, 4; TokenInformationLength
0x18001376f  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180013774  lea     r8, [rsp+78h+TokenInformation]; TokenInformation
0x18001377c  mov     edx, 0Ch; TokenInformationClass
0x180013781  call    cs:__imp_GetTokenInformation
0x180013787  test    eax, eax
0x180013789  jnz     short loc_180013794
0x18001378b  call    cs:__imp_GetLastError
0x180013791  mov     r15d, eax
0x180013794  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x180013799  test    rcx, rcx
0x18001379c  jz      short loc_1800137A4
0x18001379e  call    cs:__imp_CloseHandle
0x1800137a4  test    r15d, r15d
0x1800137a7  jnz     short loc_1800137EC
0x1800137a9  mov     eax, [rsp+78h+TokenInformation]
0x1800137b0  test    rbx, rbx
0x1800137b3  jnz     short loc_1800137E0
0x1800137b5  mov     r15d, 490h
0x1800137bb  jmp     short loc_1800137EC
0x1800137bd  mov     r10d, r15d
0x1800137c0  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r15d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800137c7  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r9d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x1800137ce  mov     cs:dword_180045874, r15d
0x1800137d5  jmp     loc_18001363D
0x1800137e0  cmp     eax, [rbx+48h]
0x1800137e3  jnz     loc_180013924
0x1800137e9  mov     [rsi], rbx
0x1800137ec  call    cs:__imp_GetCurrentThreadId
0x1800137f2  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800137f9  lea     rbx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180013800  mov     r8d, eax
0x180013803  cmp     r10d, edi
0x180013806  jz      loc_18001393C
0x18001380c  cmp     r10d, 0FFFFFFFEh
0x180013810  jz      short loc_180013818
0x180013812  cmp     [rbx+r10*8], eax
0x180013816  jz      short loc_180013852
0x180013818  xor     ecx, ecx
0x18001381a  nop     word ptr [rax+rax+00h]
0x180013820  cmp     ecx, 20h ; ' '
0x180013823  jnb     short loc_18001384C
0x180013825  movsxd  rax, ecx
0x180013828  mov     edx, [rbx+rax*8]; unsigned __int64
0x18001382b  cmp     edx, r8d
0x18001382e  jz      short loc_180013840
0x180013830  cmp     edi, 0FFFFFFFFh
0x180013833  jz      short loc_180013839
0x180013835  inc     ecx
0x180013837  jmp     short loc_180013820
0x180013839  test    edx, edx
0x18001383b  cmovz   edi, ecx
0x18001383e  jmp     short loc_180013835
0x180013840  mov     r10d, ecx
0x180013843  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180013849  cmp     ecx, 20h ; ' '
0x18001384c  jz      loc_1800139C2
0x180013852  test    r10d, r10d
0x180013855  js      loc_180013978
0x18001385b  movsxd  rax, r10d
0x18001385e  mov     r11d, [rbx+rax*8+4]
0x180013863  mov     rcx, cs:WPP_GLOBAL_Control; char *
0x18001386a  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180013871  test    byte ptr [rcx+1Ch], 2
0x180013875  jnz     loc_180013A8E
0x18001387b  lea     r9, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180013882  mov     rax, r9
0x180013885  cmp     byte ptr [rax], 0
0x180013888  jnz     loc_1800139E4
0x18001388e  sub     r12, rbp
0x180013891  lea     rax, asc_1800382CC; "<"
0x180013898  test    rbp, rbp
0x18001389b  jz      short loc_1800138C2
0x18001389d  mov     r8d, 7FFFFFFEh
0x1800138a3  test    r8, r8
0x1800138a6  jz      short loc_1800138C2
0x1800138a8  movzx   edx, byte ptr [rax]
0x1800138ab  test    dl, dl
0x1800138ad  jz      short loc_1800138C2
0x1800138af  mov     [r12], dl
0x1800138b3  inc     rax
0x1800138b6  inc     r12
0x1800138b9  dec     r8
0x1800138bc  sub     rbp, 1
0x1800138c0  jnz     short loc_1800138A3
0x1800138c2  test    rbp, rbp
0x1800138c5  lea     rax, [r12-1]
0x1800138ca  cmovnz  rax, r12
0x1800138ce  mov     byte ptr [rax], 0
0x1800138d1  test    r10d, r10d
0x1800138d4  jns     loc_180013980
0x1800138da  mov     cs:?WPP_pszIndent@@3PEADEA, r9; char * WPP_pszIndent
0x1800138e1  lea     rax, WPP_GLOBAL_Control
0x1800138e8  cmp     rcx, rax
0x1800138eb  jz      short loc_1800138F7
0x1800138ed  test    byte ptr [rcx+1Ch], 2
0x1800138f1  jnz     loc_180013A07
0x1800138f7  mov     rbx, [rsp+78h+arg_0]
0x1800138ff  mov     eax, r15d
0x180013902  add     rsp, 40h
0x180013906  pop     r15
0x180013908  pop     r14
0x18001390a  pop     r13
0x18001390c  pop     r12
0x18001390e  pop     rdi
0x18001390f  pop     rsi
0x180013910  pop     rbp
0x180013911  retn
0x180013912  mov     eax, [rax+48h]
0x180013915  mov     [rsp+78h+TokenInformation], eax
0x18001391c  mov     [rsi], r15
0x18001391f  jmp     loc_1800137B0
0x180013924  mov     [r14], rbx
0x180013927  mov     rbx, [rbx+1E0h]
0x18001392e  test    rbx, rbx
0x180013931  jnz     loc_1800137E0
0x180013937  jmp     loc_1800137B5
0x18001393c  xor     r10d, r10d
0x18001393f  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r8d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180013946  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r10d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18001394d  mov     cs:dword_180045874, r10d
0x180013954  jmp     loc_18001385B
0x180013959  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, 0FFFFFFFEh; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180013963  mov     r10d, r15d
0x180013966  jmp     loc_180013649
0x18001396b  mov     r10d, 0FFFFFFFEh
0x180013971  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r10d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180013978  xor     r11d, r11d
0x18001397b  jmp     loc_180013863
0x180013980  movsxd  rax, r10d
0x180013983  lea     rdx, ds:0[rax*8]
0x18001398b  sub     dword ptr [rdx+rbx+4], 1
0x180013990  jnz     loc_1800138DA
0x180013996  mov     dword ptr [rdx+rbx], 0
0x18001399d  jmp     loc_1800138DA
0x1800139a2  cmp     r8d, edi
0x1800139a5  jz      short loc_180013959
0x1800139a7  movsxd  rax, r8d
0x1800139aa  mov     r10d, r8d
0x1800139ad  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r8d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800139b4  mov     [rdx+rax*8], r9d
0x1800139b8  mov     [rdx+rax*8+4], r15d
0x1800139bd  jmp     loc_180013634
0x1800139c2  cmp     edi, 0FFFFFFFFh
0x1800139c5  jz      short loc_18001396B
0x1800139c7  movsxd  rax, edi
0x1800139ca  mov     r10d, edi
0x1800139cd  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, edi; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x1800139d3  mov     [rbx+rax*8], r8d
0x1800139d7  mov     dword ptr [rbx+rax*8+4], 0
0x1800139df  jmp     loc_180013852
0x1800139e4  inc     rax
0x1800139e7  sub     rbp, 1
0x1800139eb  jnz     loc_180013885
0x1800139f1  jmp     loc_1800138D1
0x1800139f6  inc     rax
0x1800139f9  sub     rdx, r13
0x1800139fc  jnz     loc_180013678
0x180013a02  jmp     loc_1800136D3
0x180013a07  cmp     byte ptr [rcx+19h], 5
0x180013a0b  jb      loc_1800138F7
0x180013a11  mov     rcx, [rcx+10h]
0x180013a15  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180013a1c  mov     edx, 15h
0x180013a21  mov     dword ptr [rsp+78h+ReturnLength], r15d
0x180013a26  call    WPP_SF_sd
0x180013a2b  jmp     loc_1800138F7
0x180013a30  cmp     byte ptr [rcx+19h], 5
0x180013a34  jb      loc_180013667
0x180013a3a  mov     r11d, r13d
0x180013a3d  cmp     r10d, r13d
0x180013a40  jl      loc_180013667
0x180013a46  lea     r8, asc_18003926C; ".."
0x180013a4d  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x180013a52  test    eax, eax
0x180013a54  jnz     short loc_180013A5E
0x180013a56  inc     r11d
0x180013a59  cmp     r11d, r10d
0x180013a5c  jle     short loc_180013A46
0x180013a5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a65  jmp     loc_180013667
  ... truncated ...
```
