# ClipboardPolicyStatics::IsClipboardAccessAllowedForCaller(uchar *)

- ea: `0x1800672a0`
- end: `0x1800676e1`
- name: `?IsClipboardAccessAllowedForCaller@ClipboardPolicyStatics@@UEAAJPEAE@Z`
- size: `1089`
- prototype: `__int64 __fastcall(ClipboardPolicyStatics *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004dcc`
- `0x180048954`
- `0x1800671c0`
- `0x1800672a0`
- `0x18007b9e4`
- `0x18007bb34`
- `0x18007bc24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006730f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800674c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006730f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800674c6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180067419`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180067419`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006737a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067561`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006737a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006754e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800675b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006754e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800675b8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800675ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800675ae`
- `api-ms-win-core-com-l1-1-0!CoGetCallerTID` at `0x180067648`
- `api-ms-win-core-com-l1-1-0!CoGetCallerTID` at `0x180067648`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067372`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800673df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067481`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006752d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067559`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800675f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006762b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006767e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800676bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067372`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800673df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067481`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006752d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067559`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800675f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006762b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006767e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800676bf`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180067300`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800674b7`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180067300`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800674b7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x180067576`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x180067576`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x18006739a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x18006739a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ClipboardPolicyStatics::IsClipboardAccessAllowedForCaller(
        ClipboardPolicyStatics *this,
        unsigned __int8 *a2)
{
  int CallingProcessHandle; // eax
  unsigned int v4; // ebx
  RPC_STATUS v5; // eax
  DWORD CurrentProcessId; // esi
  __int64 v7; // rdx
  HANDLE v8; // r14
  DWORD LastError; // ebx
  int v10; // eax
  unsigned __int64 v11; // r9
  const char *v12; // r9
  __int64 result; // rax
  char *v14; // rdi
  DWORD ProcessId; // r13d
  char v16; // r15
  __int64 v17; // rdx
  __int64 v18; // rcx
  signed int IsProcessAppContainer; // ebx
  bool *v20; // r8
  char *v21; // rcx
  RPC_STATUS v22; // eax
  DWORD v23; // esi
  char *v24; // rcx
  DWORD v25; // ebx
  signed int v26; // eax
  HRESULT CallerTID; // eax
  HWND *v28; // rdx
  unsigned int v29; // ebx
  int ReturnLength; // [rsp+20h] [rbp-68h]
  int ReturnLengtha; // [rsp+20h] [rbp-68h]
  int ReturnLengthb; // [rsp+20h] [rbp-68h]
  DWORD v33; // [rsp+30h] [rbp-58h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-50h] BYREF
  HWND v35; // [rsp+40h] [rbp-48h] BYREF
  HANDLE v36; // [rsp+48h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int Pid; // [rsp+98h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+A0h] [rbp+18h] BYREF
  DWORD dwTID; // [rsp+A8h] [rbp+20h] BYREF

  *a2 = 0;
  v36 = 0;
  hObject = 0;
  try
  {
    CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(this, a2, &hObject);
    v4 = CallingProcessHandle;
    if ( CallingProcessHandle >= 0 )
      goto LABEL_21;
    if ( CallingProcessHandle == -2147024891 && (unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent() )
    {
      Pid = 0;
      v5 = I_RpcBindingInqLocalClientPID(0, &Pid);
      v4 = v5;
      if ( v5 == 1725 )
      {
        CurrentProcessId = GetCurrentProcessId();
        goto LABEL_12;
      }
      if ( v5 >= 1 )
        v4 = (unsigned __int16)v5 | 0x80010000;
      if ( (v4 & 0x80000000) == 0 )
      {
        CurrentProcessId = Pid;
LABEL_12:
        v8 = hObject;
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          LastError = GetLastError();
          CloseHandle(v8);
          SetLastError(LastError);
        }
        hObject = 0;
        v10 = UMgrOpenProcessHandleForAccess(4096, CurrentProcessId, &hObject);
        v4 = v10;
        if ( v10 < 0 )
        {
          v11 = (unsigned int)v10;
          v7 = 180;
LABEL_18:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v7,
            (unsigned int)"onecoreuap\\internal\\base\\inc\\UserAwareCallerIdentity.h",
            (const char *)v11,
            ReturnLength);
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x73,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboardpolicy.cpp",
            (const char *)v4,
            ReturnLengtha);
          return v4;
        }
LABEL_21:
        v14 = (char *)hObject;
        v36 = hObject;
        ProcessId = GetProcessId(hObject);
        v16 = 0;
        LOBYTE(Pid) = 0;
        hObject = 0;
        IsProcessAppContainer = CallerIdentity::GetCallingProcessHandle(v18, v17, &hObject);
        if ( IsProcessAppContainer >= 0 )
        {
          IsProcessAppContainer = CallerIdentity::IsProcessAppContainer(hObject, &Pid, v20);
          v16 = Pid;
        }
        v21 = (char *)hObject;
        hObject = 0;
        if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v21);
        if ( IsProcessAppContainer != -2147024891 || !(unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent() )
          goto LABEL_48;
        TokenHandle = 0;
        Pid = 0;
        v22 = I_RpcBindingInqLocalClientPID(0, &Pid);
        IsProcessAppContainer = v22;
        if ( v22 == 1725 )
        {
          v23 = GetCurrentProcessId();
        }
        else
        {
          if ( v22 >= 1 )
            IsProcessAppContainer = (unsigned __int16)v22 | 0x80010000;
          if ( IsProcessAppContainer < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x39,
              (unsigned int)"onecoreuap\\internal\\base\\inc\\UserAwareCallerIdentity.h",
              (const char *)(unsigned int)IsProcessAppContainer,
              ReturnLength);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x16A,
              (unsigned int)"onecoreuap\\internal\\base\\inc\\UserAwareCallerIdentity.h",
              (const char *)(unsigned int)IsProcessAppContainer,
              ReturnLengthb);
            v24 = (char *)TokenHandle;
            goto LABEL_33;
          }
          v23 = Pid;
        }
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          v25 = GetLastError();
          CloseHandle(TokenHandle);
          SetLastError(v25);
        }
        TokenHandle = 0;
        IsProcessAppContainer = UMgrOpenProcessTokenForQuery(v23, &TokenHandle);
        v24 = (char *)TokenHandle;
        if ( IsProcessAppContainer >= 0 )
        {
          v33 = 0;
          LODWORD(hObject) = 0;
          if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &hObject, 4u, &v33) )
          {
            v16 = (_DWORD)hObject != 0;
            IsProcessAppContainer = 0;
          }
          else
          {
            v26 = GetLastError();
            IsProcessAppContainer = v26;
            if ( v26 > 0 )
              IsProcessAppContainer = (unsigned __int16)v26 | 0x80070000;
            if ( IsProcessAppContainer >= 0 )
              IsProcessAppContainer = -2147467259;
          }
          if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(TokenHandle);
LABEL_48:
          if ( IsProcessAppContainer < 0 )
          {
LABEL_49:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x77,
              (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboardpolicy.cpp",
              (const char *)(unsigned int)IsProcessAppContainer,
              ReturnLength);
            if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v14);
            return (unsigned int)IsProcessAppContainer;
          }
          dwTID = 0;
          CallerTID = CoGetCallerTID(&dwTID);
          v29 = CallerTID;
          if ( CallerTID >= 0 )
          {
            v35 = 0;
            CallerIdentity::GetCoreWindowHandleForCallingThread((CallerIdentity *)&v35, v28);
            *a2 = IsClipboardAccessAllowed(ProcessId, dwTID, v35, v16);
            if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v14);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7A,
              (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboardpolicy.cpp",
              (const char *)(unsigned int)CallerTID,
              ReturnLength);
            if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v14);
            return v29;
          }
        }
LABEL_33:
        if ( (unsigned __int64)(v24 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v24);
        goto LABEL_49;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecoreuap\\internal\\base\\inc\\UserAwareCallerIdentity.h",
        (const char *)v4,
        ReturnLength);
      v7 = 179;
    }
    else
    {
      v7 = 182;
    }
    v11 = v4;
    goto LABEL_18;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x83,
                           (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\clipboardpolicy.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800672a0  mov     rax, rsp
0x1800672a3  push    rbx
0x1800672a4  push    rsi
0x1800672a5  push    rdi
0x1800672a6  push    r12
0x1800672a8  push    r13
0x1800672aa  push    r14
0x1800672ac  push    r15
0x1800672ae  sub     rsp, 50h
0x1800672b2  mov     r12, rdx
0x1800672b5  xor     r14d, r14d
0x1800672b8  mov     [rdx], r14b
0x1800672bb  mov     [rax-40h], r14
0x1800672bf  mov     [rax+18h], r14
0x1800672c3  lea     r8, [rax+18h]
0x1800672c7  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x1800672cc  mov     ebx, eax
0x1800672ce  test    eax, eax
0x1800672d0  jns     loc_180067409
0x1800672d6  cmp     eax, 80070005h
0x1800672db  jnz     loc_1800673B0
0x1800672e1  call    IsUMgrOpenProcessHandleForAccessPresent
0x1800672e6  test    al, al
0x1800672e8  jz      loc_1800673B0
0x1800672ee  mov     [rsp+88h+Pid], r14d
0x1800672f6  lea     rdx, [rsp+88h+Pid]; Pid
0x1800672fe  xor     ecx, ecx; Binding
0x180067300  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180067306  mov     ebx, eax
0x180067308  cmp     eax, 6BDh
0x18006730d  jnz     short loc_180067319
0x18006730f  call    cs:__imp_GetCurrentProcessId
0x180067315  mov     esi, eax
0x180067317  jmp     short loc_180067355
0x180067319  cmp     eax, 1
0x18006731c  jl      short loc_180067327
0x18006731e  movzx   ebx, ax
0x180067321  or      ebx, 80010000h
0x180067327  test    ebx, ebx
0x180067329  jns     short loc_18006734E
0x18006732b  mov     rcx, [rsp+88h]; this
0x180067333  mov     r9d, ebx; char *
0x180067336  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\base\\inc\\UserAw"...
0x18006733d  mov     edx, 39h ; '9'; void *
0x180067342  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067347  mov     edx, 0B3h
0x18006734c  jmp     short loc_1800673B5
0x18006734e  mov     esi, [rsp+88h+Pid]
0x180067355  mov     r14, [rsp+88h+hObject]
0x18006735d  lea     rax, [r14-1]
0x180067361  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180067365  ja      short loc_180067380
0x180067367  call    cs:__imp_GetLastError
0x18006736d  mov     ebx, eax
0x18006736f  mov     rcx, r14; hObject
0x180067372  call    cs:__imp_CloseHandle
0x180067378  mov     ecx, ebx; dwErrCode
0x18006737a  call    cs:__imp_SetLastError
0x180067380  xor     r14d, r14d
0x180067383  mov     [rsp+88h+hObject], r14
0x18006738b  lea     r8, [rsp+88h+hObject]
0x180067393  mov     edx, esi
0x180067395  mov     ecx, 1000h
0x18006739a  call    cs:__imp_UMgrOpenProcessHandleForAccess
0x1800673a0  mov     ebx, eax
0x1800673a2  test    eax, eax
0x1800673a4  jns     short loc_180067409
0x1800673a6  mov     r9d, eax
0x1800673a9  mov     edx, 0B4h
0x1800673ae  jmp     short loc_1800673B8
0x1800673b0  mov     edx, 0B6h; void *
0x1800673b5  mov     r9d, ebx; char *
0x1800673b8  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\base\\inc\\UserAw"...
0x1800673bf  mov     rcx, [rsp+88h]; this
0x1800673c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800673cc  nop
0x1800673cd  mov     rcx, [rsp+88h+hObject]; hObject
0x1800673d5  lea     rax, [rcx-1]
0x1800673d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800673dd  ja      short loc_1800673E5
0x1800673df  call    cs:__imp_CloseHandle
0x1800673e5  mov     rcx, [rsp+88h]; this
0x1800673ed  mov     r9d, ebx; char *
0x1800673f0  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x1800673f7  mov     edx, 73h ; 's'; void *
0x1800673fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067401  nop
0x180067402  mov     eax, ebx
0x180067404  jmp     loc_1800676D0
0x180067409  mov     rdi, [rsp+88h+hObject]
0x180067411  mov     [rsp+88h+var_40], rdi
0x180067416  mov     rcx, rdi; Process
0x180067419  call    cs:__imp_GetProcessId
0x18006741f  mov     r13d, eax
0x180067422  mov     r15b, r14b
0x180067425  mov     byte ptr [rsp+88h+Pid], r14b
0x18006742d  mov     [rsp+88h+hObject], r14
0x180067435  lea     r8, [rsp+88h+hObject]
0x18006743d  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x180067442  mov     ebx, eax
0x180067444  test    eax, eax
0x180067446  js      short loc_180067467
0x180067448  lea     rdx, [rsp+88h+Pid]; void *
0x180067450  mov     rcx, [rsp+88h+hObject]; ProcessHandle
0x180067458  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x18006745d  mov     ebx, eax
0x18006745f  mov     r15b, byte ptr [rsp+88h+Pid]
0x180067467  mov     rcx, [rsp+88h+hObject]; hObject
0x18006746f  mov     [rsp+88h+hObject], r14
0x180067477  lea     rax, [rcx-1]
0x18006747b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006747f  ja      short loc_180067487
0x180067481  call    cs:__imp_CloseHandle
0x180067487  cmp     ebx, 80070005h
0x18006748d  jnz     loc_1800675FD
0x180067493  call    IsUMgrOpenProcessHandleForAccessPresent
0x180067498  test    al, al
0x18006749a  jz      loc_1800675FD
0x1800674a0  mov     [rsp+88h+TokenHandle], r14
0x1800674a5  mov     [rsp+88h+Pid], r14d
0x1800674ad  lea     rdx, [rsp+88h+Pid]; Pid
0x1800674b5  xor     ecx, ecx; Binding
0x1800674b7  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800674bd  mov     ebx, eax
0x1800674bf  cmp     eax, 6BDh
0x1800674c4  jnz     short loc_1800674D0
0x1800674c6  call    cs:__imp_GetCurrentProcessId
0x1800674cc  mov     esi, eax
0x1800674ce  jmp     short loc_18006753F
0x1800674d0  cmp     eax, 1
0x1800674d3  jl      short loc_1800674DE
0x1800674d5  movzx   ebx, ax
0x1800674d8  or      ebx, 80010000h
0x1800674de  test    ebx, ebx
0x1800674e0  jns     short loc_180067538
0x1800674e2  mov     rcx, [rsp+88h]; this
0x1800674ea  mov     r9d, ebx; char *
0x1800674ed  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\base\\inc\\UserAw"...
0x1800674f4  mov     edx, 39h ; '9'; void *
0x1800674f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800674fe  mov     rcx, [rsp+88h]; this
0x180067506  mov     r9d, ebx; char *
0x180067509  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\base\\inc\\UserAw"...
0x180067510  mov     edx, 16Ah; void *
0x180067515  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006751a  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x18006751f  lea     rax, [rcx-1]
0x180067523  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180067527  ja      loc_180067601
0x18006752d  call    cs:__imp_CloseHandle
0x180067533  jmp     loc_180067601
0x180067538  mov     esi, [rsp+88h+Pid]
0x18006753f  mov     r14, [rsp+88h+TokenHandle]
0x180067544  lea     rax, [r14-1]
0x180067548  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006754c  ja      short loc_180067567
0x18006754e  call    cs:__imp_GetLastError
0x180067554  mov     ebx, eax
0x180067556  mov     rcx, r14; hObject
0x180067559  call    cs:__imp_CloseHandle
0x18006755f  mov     ecx, ebx; dwErrCode
0x180067561  call    cs:__imp_SetLastError
0x180067567  xor     r14d, r14d
0x18006756a  mov     [rsp+88h+TokenHandle], r14
0x18006756f  lea     rdx, [rsp+88h+TokenHandle]
0x180067574  mov     ecx, esi
0x180067576  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x18006757c  mov     ebx, eax
0x18006757e  mov     rcx, [rsp+88h+TokenHandle]; TokenHandle
0x180067583  test    eax, eax
0x180067585  js      short loc_18006751F
0x180067587  mov     [rsp+88h+var_58], r14d
0x18006758c  mov     dword ptr [rsp+88h+hObject], r14d
0x180067594  lea     rax, [rsp+88h+var_58]
0x180067599  mov     qword ptr [rsp+88h+ReturnLength], rax; int
0x18006759e  lea     r9d, [r14+4]; TokenInformationLength
0x1800675a2  lea     r8, [rsp+88h+hObject]; TokenInformation
0x1800675aa  lea     edx, [r14+1Dh]; TokenInformationClass
0x1800675ae  call    cs:__imp_GetTokenInformation
0x1800675b4  test    eax, eax
0x1800675b6  jnz     short loc_1800675D9
0x1800675b8  call    cs:__imp_GetLastError
0x1800675be  mov     ebx, eax
0x1800675c0  test    eax, eax
0x1800675c2  jle     short loc_1800675CD
0x1800675c4  movzx   ebx, ax
0x1800675c7  or      ebx, 80070000h
0x1800675cd  mov     eax, 80004005h
0x1800675d2  test    ebx, ebx
0x1800675d4  cmovns  ebx, eax
0x1800675d7  jmp     short loc_1800675E8
0x1800675d9  cmp     dword ptr [rsp+88h+hObject], r14d
0x1800675e1  setnz   r15b
0x1800675e5  mov     ebx, r14d
0x1800675e8  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x1800675ed  lea     rax, [rcx-1]
0x1800675f1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800675f5  ja      short loc_1800675FD
0x1800675f7  call    cs:__imp_CloseHandle
0x1800675fd  test    ebx, ebx
0x1800675ff  jns     short loc_180067638
0x180067601  mov     rcx, [rsp+88h]; this
0x180067609  mov     r9d, ebx; char *
0x18006760c  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180067613  mov     edx, 77h ; 'w'; void *
0x180067618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006761d  nop
0x18006761e  lea     rdx, [rdi-1]
0x180067622  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180067626  ja      short loc_180067631
0x180067628  mov     rcx, rdi; hObject
0x18006762b  call    cs:__imp_CloseHandle
0x180067631  mov     eax, ebx
0x180067633  jmp     loc_1800676D0
0x180067638  mov     [rsp+88h+dwTID], r14d
0x180067640  lea     rcx, [rsp+88h+dwTID]; lpdwTID
0x180067648  call    cs:__imp_CoGetCallerTID
0x18006764e  mov     ebx, eax
0x180067650  test    eax, eax
0x180067652  jns     short loc_180067688
0x180067654  mov     rcx, [rsp+88h]; this
0x18006765c  mov     r9d, eax; char *
0x18006765f  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\datatransfer\\lib\\c"...
0x180067666  mov     edx, 7Ah ; 'z'; void *
0x18006766b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067670  nop
0x180067671  lea     rcx, [rdi-1]
0x180067675  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180067679  ja      short loc_180067684
0x18006767b  mov     rcx, rdi; hObject
0x18006767e  call    cs:__imp_CloseHandle
0x180067684  mov     eax, ebx
0x180067686  jmp     short loc_1800676D0
0x180067688  mov     [rsp+88h+var_48], r14
0x18006768d  lea     rcx, [rsp+88h+var_48]; this
0x180067692  call    ?GetCoreWindowHandleForCallingThread@CallerIdentity@@YAJPEAPEAUHWND__@@@Z; CallerIdentity::GetCoreWindowHandleForCallingThread(HWND__ * *)
0x180067697  mov     r9b, r15b; bool
0x18006769a  mov     r8, [rsp+88h+var_48]; HWND
0x18006769f  mov     edx, [rsp+88h+dwTID]; unsigned int
0x1800676a6  mov     ecx, r13d; unsigned int
0x1800676a9  call    ?IsClipboardAccessAllowed@@YA_NKKPEAUHWND__@@_N@Z; IsClipboardAccessAllowed(ulong,ulong,HWND__ *,bool)
0x1800676ae  mov     [r12], al
0x1800676b2  lea     rax, [rdi-1]
0x1800676b6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800676ba  ja      short loc_1800676C5
0x1800676bc  mov     rcx, rdi; hObject
0x1800676bf  call    cs:__imp_CloseHandle
0x1800676c5  xor     eax, eax
0x1800676c7  jmp     short loc_1800676D0
0x1800676c9  mov     eax, [rsp+88h+Pid]
0x1800676d0  add     rsp, 50h
0x1800676d4  pop     r15
0x1800676d6  pop     r14
0x1800676d8  pop     r13
0x1800676da  pop     r12
0x1800676dc  pop     rdi
0x1800676dd  pop     rsi
0x1800676de  pop     rbx
0x1800676df  retn
```
