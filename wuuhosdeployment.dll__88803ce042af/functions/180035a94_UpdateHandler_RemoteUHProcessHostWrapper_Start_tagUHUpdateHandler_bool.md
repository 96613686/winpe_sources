# UpdateHandler::RemoteUHProcessHostWrapper::Start(tagUHUpdateHandler,bool)

- ea: `0x180035a94`
- end: `0x180035ddb`
- name: `?Start@RemoteUHProcessHostWrapper@UpdateHandler@@QEAAJW4tagUHUpdateHandler@@_N@Z`
- size: `839`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002e554`

## callees

- `0x180003950`
- `0x180003974`
- `0x18000956c`
- `0x180031804`
- `0x180035a94`
- `0x180035de4`
- `0x180036454`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035b53`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035b53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035b9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035bb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035b9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035bb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035ace`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035ace`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035b15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b02`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180035d2d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180035d2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035b0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035b0d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180035c8b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180035c8b`

## string_xrefs

- `0x180035b2c`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`
- `0x180035b66`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`
- `0x180035c03`: `Starting remote process for Update Handler %ws`
- `0x180035cd2`: `UpdateHandler::RemoteUHProcessHostWrapper::Start`

## pseudocode

```c
__int64 __fastcall UpdateHandler::RemoteUHProcessHostWrapper::Start(__int64 a1, __int64 a2, char a3)
{
  __int64 v3; // rbx
  HANDLE *v6; // r14
  char *v7; // rbp
  unsigned int v8; // edi
  __int64 v9; // rdx
  DWORD LastError; // edi
  HANDLE EventW; // rax
  const char *v12; // r9
  int started; // ebx
  __int64 v15; // rdx
  DWORD v16; // eax
  const char *v17; // r9
  DWORD v18; // eax
  unsigned int v19; // edx
  unsigned int v20; // ecx
  void *v21; // rcx
  DWORD v22; // [rsp+20h] [rbp-58h]
  DWORD ExitCode; // [rsp+40h] [rbp-38h] BYREF
  HANDLE Handles[2]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = a1 + 80;
  if ( a1 != -80 )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v6 = (HANDLE *)(a1 + 136);
  v7 = *(char **)(a1 + 136);
  if ( v7 && v7 != (char *)-1LL )
  {
    v8 = -2145112065;
    v9 = 271;
    goto LABEL_13;
  }
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v7);
    SetLastError(LastError);
  }
  *v6 = 0;
  if ( a1 == -136 )
  {
    v8 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\commonutil.cpp",
      (const char *)0x80004003LL,
      v22);
LABEL_12:
    v9 = 273;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)v8,
      v22);
    if ( v3 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
    return v8;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *v6 = EventW;
  if ( !EventW )
  {
    v8 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x1B9,
           (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\commonutil.cpp",
           v12);
    if ( (v8 & 0x80000000) != 0 )
      goto LABEL_12;
  }
  if ( v3 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  *(_BYTE *)(a1 + 56) = a3;
  started = UpdateHandler::RemoteUHProcessHostWrapper::StartDynamicCOMServer((UpdateHandler::RemoteUHProcessHostWrapper *)a1);
  if ( started < 0 )
  {
    v15 = 277;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)(unsigned int)started,
      v22);
    return (unsigned int)started;
  }
  v22 = 0;
  WUTrace(0, 0, 4096, 4);
  started = UpdateHandler::RemoteUHProcessHostWrapper::LaunchProcess(a1);
  if ( started < 0 )
  {
    v15 = 285;
    goto LABEL_20;
  }
  v22 = 0;
  WUTrace(0, 0, 4096, 4);
  Handles[0] = *v6;
  Handles[1] = *(HANDLE *)(a1 + 64);
  v16 = WaitForMultipleObjects(2u, Handles, 0, 0xEA60u);
  if ( v16 )
  {
    v18 = v16 - 1;
    if ( !v18 )
    {
      v21 = *(void **)(a1 + 64);
      ExitCode = 0;
      if ( !GetExitCodeProcess(v21, &ExitCode)
        || (started = ExitCode, v22 = ExitCode, WUTrace(0, 0, 4096, 3), started >= 0) )
      {
        v8 = -2145112065;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x134,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
          (const char *)0x80242FFFLL,
          v22);
        return v8;
      }
      v15 = 306;
      goto LABEL_20;
    }
    if ( v18 == 257 )
    {
      v22 = 0;
      WUTrace("UpdateHandler::RemoteUHProcessHostWrapper::Start", 314, 32, 3);
      WUTelemetryAssertTriggered(v20, v19);
      v15 = 315;
      started = -2145116121;
      goto LABEL_20;
    }
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x13F,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
             v17);
  }
  else
  {
    WUTrace(0, 0, 4096, 4);
    return 0;
  }
}

```

## disassembly

```asm
0x180035a94  mov     [rsp+arg_8], rbx
0x180035a99  mov     [rsp+arg_10], rbp
0x180035a9e  mov     [rsp+arg_18], rsi
0x180035aa3  push    rdi
0x180035aa4  push    r14
0x180035aa6  push    r15
0x180035aa8  sub     rsp, 60h
0x180035aac  mov     rax, cs:__security_cookie
0x180035ab3  xor     rax, rsp
0x180035ab6  mov     [rsp+78h+var_20], rax
0x180035abb  lea     rbx, [rcx+50h]
0x180035abf  mov     r15b, r8b
0x180035ac2  mov     rsi, rcx
0x180035ac5  test    rbx, rbx
0x180035ac8  jz      short loc_180035AD4
0x180035aca  lea     rcx, [rbx+8]; lpCriticalSection
0x180035ace  call    cs:__imp_EnterCriticalSection
0x180035ad4  lea     r14, [rsi+88h]
0x180035adb  mov     rbp, [r14]
0x180035ade  test    rbp, rbp
0x180035ae1  jz      short loc_180035AF8
0x180035ae3  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180035ae7  jz      short loc_180035AF8
0x180035ae9  mov     edi, 80242FFFh
0x180035aee  mov     edx, 10Fh
0x180035af3  jmp     loc_180035B82
0x180035af8  lea     rax, [rbp-1]
0x180035afc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180035b00  ja      short loc_180035B1B
0x180035b02  call    cs:__imp_GetLastError
0x180035b08  mov     rcx, rbp; hObject
0x180035b0b  mov     edi, eax
0x180035b0d  call    cs:__imp_CloseHandle
0x180035b13  mov     ecx, edi; dwErrCode
0x180035b15  call    cs:__imp_SetLastError
0x180035b1b  mov     qword ptr [r14], 0
0x180035b22  test    r14, r14
0x180035b25  jnz     short loc_180035B47
0x180035b27  mov     rcx, [rsp+78h]; this
0x180035b2c  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180035b33  mov     edi, 80004003h
0x180035b38  mov     edx, 1B3h; void *
0x180035b3d  mov     r9d, edi; char *
0x180035b40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035b45  jmp     short loc_180035B7D
0x180035b47  xor     r9d, r9d; lpName
0x180035b4a  xor     r8d, r8d; bInitialState
0x180035b4d  xor     ecx, ecx; lpEventAttributes
0x180035b4f  lea     edx, [r9+1]; bManualReset
0x180035b53  call    cs:__imp_CreateEventW
0x180035b59  mov     [r14], rax
0x180035b5c  test    rax, rax
0x180035b5f  jnz     short loc_180035BAC
0x180035b61  mov     rcx, [rsp+78h]; this
0x180035b66  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180035b6d  mov     edx, 1B9h; void *
0x180035b72  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035b77  mov     edi, eax
0x180035b79  test    eax, eax
0x180035b7b  jns     short loc_180035BAC
0x180035b7d  mov     edx, 111h; void *
0x180035b82  mov     rcx, [rsp+78h]; this
0x180035b87  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180035b8e  mov     r9d, edi; char *
0x180035b91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035b96  test    rbx, rbx
0x180035b99  jz      short loc_180035BA5
0x180035b9b  lea     rcx, [rbx+8]; lpCriticalSection
0x180035b9f  call    cs:__imp_LeaveCriticalSection
0x180035ba5  mov     eax, edi
0x180035ba7  jmp     loc_180035DB4
0x180035bac  test    rbx, rbx
0x180035baf  jz      short loc_180035BBB
0x180035bb1  lea     rcx, [rbx+8]; lpCriticalSection
0x180035bb5  call    cs:__imp_LeaveCriticalSection
0x180035bbb  mov     rcx, rsi; this
0x180035bbe  mov     [rsi+38h], r15b
0x180035bc2  call    ?StartDynamicCOMServer@RemoteUHProcessHostWrapper@UpdateHandler@@AEAAJXZ; UpdateHandler::RemoteUHProcessHostWrapper::StartDynamicCOMServer(void)
0x180035bc7  mov     ebx, eax
0x180035bc9  test    eax, eax
0x180035bcb  jns     short loc_180035BED
0x180035bcd  mov     edx, 115h; void *
0x180035bd2  mov     rcx, [rsp+78h]; this
0x180035bd7  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180035bde  mov     r9d, ebx; char *
0x180035be1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035be6  mov     eax, ebx
0x180035be8  jmp     loc_180035DB4
0x180035bed  lea     rax, aOsdeployment; "OSDeployment"
0x180035bf4  mov     ebp, 4
0x180035bf9  mov     [rsp+78h+var_48], rax
0x180035bfe  mov     edi, 1000h
0x180035c03  lea     rax, aStartingRemote; "Starting remote process for Update Hand"...
0x180035c0a  mov     r9d, ebp
0x180035c0d  mov     [rsp+78h+var_50], rax
0x180035c12  mov     r8d, edi
0x180035c15  xor     edx, edx
0x180035c17  mov     qword ptr [rsp+78h+var_58], 0
0x180035c20  xor     ecx, ecx
0x180035c22  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180035c27  mov     rcx, rsi
0x180035c2a  call    ?LaunchProcess@RemoteUHProcessHostWrapper@UpdateHandler@@AEAAJW4tagUHUpdateHandler@@@Z; UpdateHandler::RemoteUHProcessHostWrapper::LaunchProcess(tagUHUpdateHandler)
0x180035c2f  mov     ebx, eax
0x180035c31  test    eax, eax
0x180035c33  jns     short loc_180035C3C
0x180035c35  mov     edx, 11Dh
0x180035c3a  jmp     short loc_180035BD2
0x180035c3c  lea     rax, aRemoteProcessW; "Remote process was launched. Waiting fo"...
0x180035c43  mov     dword ptr [rsp+78h+var_48], 3Ch ; '<'
0x180035c4b  mov     [rsp+78h+var_50], rax
0x180035c50  mov     r9d, ebp
0x180035c53  mov     r8d, edi
0x180035c56  mov     qword ptr [rsp+78h+var_58], 0; int
0x180035c5f  xor     edx, edx
0x180035c61  xor     ecx, ecx
0x180035c63  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180035c68  mov     rax, [r14]
0x180035c6b  lea     rdx, [rsp+78h+Handles]; lpHandles
0x180035c70  xor     r8d, r8d; bWaitAll
0x180035c73  mov     [rsp+78h+Handles], rax
0x180035c78  mov     rax, [rsi+40h]
0x180035c7c  mov     r9d, 0EA60h; dwMilliseconds
0x180035c82  mov     [rsp+78h+var_28], rax
0x180035c87  lea     ecx, [r8+2]; nCount
0x180035c8b  call    cs:__imp_WaitForMultipleObjects
0x180035c91  test    eax, eax
0x180035c93  jz      loc_180035D8E
0x180035c99  sub     eax, 1
0x180035c9c  jz      short loc_180035D1C
0x180035c9e  cmp     eax, 101h
0x180035ca3  jz      short loc_180035CC0
0x180035ca5  mov     rcx, [rsp+78h]; this
0x180035caa  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180035cb1  mov     edx, 13Fh; void *
0x180035cb6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035cbb  jmp     loc_180035DB4
0x180035cc0  lea     rax, aRemoteuhproces_0; "RemoteUHProcessHostWrapper::Start() tim"...
0x180035cc7  mov     r9d, 3
0x180035ccd  mov     [rsp+78h+var_40], rax
0x180035cd2  lea     rcx, aUpdatehandlerR_0; "UpdateHandler::RemoteUHProcessHostWrapp"...
0x180035cd9  lea     rax, aFalse; "false"
0x180035ce0  mov     edx, 13Ah
0x180035ce5  mov     [rsp+78h+var_48], rax
0x180035cea  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x180035cf1  mov     [rsp+78h+var_50], rax
0x180035cf6  lea     r8d, [r9+1Dh]
0x180035cfa  mov     qword ptr [rsp+78h+var_58], 0
0x180035d03  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180035d08  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x180035d0d  mov     edx, 13Bh
0x180035d12  mov     ebx, 80242027h
0x180035d17  jmp     loc_180035BD2
0x180035d1c  mov     rcx, [rsi+40h]; hProcess
0x180035d20  lea     rdx, [rsp+78h+ExitCode]; lpExitCode
0x180035d25  mov     [rsp+78h+ExitCode], 0
0x180035d2d  call    cs:__imp_GetExitCodeProcess
0x180035d33  test    eax, eax
0x180035d35  jz      short loc_180035D6B
0x180035d37  mov     ebx, [rsp+78h+ExitCode]
0x180035d3b  lea     rax, aRemoteProcessS_0; "Remote process stopped before registeri"...
0x180035d42  mov     [rsp+78h+var_50], rax
0x180035d47  mov     r9d, 3
0x180035d4d  mov     r8d, edi
0x180035d50  mov     [rsp+78h+var_58], ebx
0x180035d54  xor     edx, edx
0x180035d56  xor     ecx, ecx
0x180035d58  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180035d5d  test    ebx, ebx
0x180035d5f  jns     short loc_180035D6B
0x180035d61  mov     edx, 132h
0x180035d66  jmp     loc_180035BD2
0x180035d6b  mov     rcx, [rsp+78h]; this
0x180035d70  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180035d77  mov     edi, 80242FFFh
0x180035d7c  mov     edx, 134h; void *
0x180035d81  mov     r9d, edi; char *
0x180035d84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035d89  jmp     loc_180035BA5
0x180035d8e  lea     rax, aRemoteProcessS; "Remote process started succesfully"
0x180035d95  mov     r9d, ebp
0x180035d98  mov     [rsp+78h+var_50], rax
0x180035d9d  mov     r8d, edi
0x180035da0  xor     edx, edx
0x180035da2  mov     qword ptr [rsp+78h+var_58], 0
0x180035dab  xor     ecx, ecx
0x180035dad  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180035db2  xor     eax, eax
0x180035db4  mov     rcx, [rsp+78h+var_20]
0x180035db9  xor     rcx, rsp; StackCookie
0x180035dbc  call    __security_check_cookie
0x180035dc1  lea     r11, [rsp+78h+var_18]
0x180035dc6  mov     rbx, [r11+28h]
0x180035dca  mov     rbp, [r11+30h]
0x180035dce  mov     rsi, [r11+38h]
0x180035dd2  mov     rsp, r11
0x180035dd5  pop     r15
0x180035dd7  pop     r14
0x180035dd9  pop     rdi
0x180035dda  retn
```
