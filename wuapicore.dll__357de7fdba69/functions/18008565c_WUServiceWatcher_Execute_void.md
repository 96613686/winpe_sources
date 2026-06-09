# WUServiceWatcher::Execute(void)

- ea: `0x18008565c`
- end: `0x1800858a7`
- name: `?Execute@WUServiceWatcher@@AEAAJXZ`
- size: `587`
- prototype: `__int64 __fastcall(WUServiceWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180085650`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x180007ecc`
- `0x18008565c`
- `0x1800858b0`
- `0x18008662c`
- `0x180090bc8`
- `0x18009ae75`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008583e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180085853`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008583e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180085853`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180085710`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180085710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800856fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800856fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085872`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085872`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180085751`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180085751`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18008580d`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18008580d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800856c4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800856c4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085708`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085834`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085849`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085708`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085834`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180085849`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800856ec`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800856ec`

## string_xrefs

- `0x180085727`: `C:\__w\1\s\src\Client\lib\util\WUServiceWatcher.cpp`
- `0x180085794`: `C:\__w\1\s\src\Client\lib\util\WUServiceWatcher.cpp`
- `0x1800857dd`: `C:\__w\1\s\src\Client\lib\util\WUServiceWatcher.cpp`
- `0x18008581e`: `C:\__w\1\s\src\Client\lib\util\WUServiceWatcher.cpp`
- `0x18008576e`: `Queried service %s is not running`
- `0x1800857a7`: `Queried service %s is running`
- `0x1800856bb`: `ServicesActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WUServiceWatcher::Execute(HANDLE *this)
{
  void *v2; // rbx
  SC_HANDLE v3; // rax
  const char *v4; // r9
  SC_HANDLE v5; // r14
  __int64 v6; // rdx
  SC_HANDLE v7; // r15
  SC_HANDLE v8; // r12
  DWORD v9; // edi
  unsigned int LastError; // edi
  int v11; // eax
  DWORD v12; // eax
  unsigned int v14; // [rsp+28h] [rbp-79h]
  int v15; // [rsp+28h] [rbp-79h]
  void *v16; // [rsp+48h] [rbp-59h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+58h] [rbp-49h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+A8h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]

  v2 = 0;
  v16 = 0;
  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  pNotifyBuffer.dwVersion = 2;
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)anonymous_namespace_::NotifyCallback;
  v3 = OpenSCManagerW(0, L"ServicesActive", 5u);
  v5 = v3;
  if ( !v3 )
  {
    v6 = 162;
LABEL_7:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v6,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUServiceWatcher.cpp",
                  v4);
    goto LABEL_14;
  }
  v7 = OpenServiceW(v3, L"wuauserv", 4u);
  v8 = (SC_HANDLE)*this;
  if ( *this )
  {
    v9 = GetLastError();
    CloseServiceHandle(v8);
    SetLastError(v9);
  }
  *this = v7;
  if ( !v7 )
  {
    v6 = 166;
    goto LABEL_7;
  }
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( QueryServiceStatus(v7, &ServiceStatus) )
  {
    if ( ServiceStatus.dwCurrentState != 4 )
    {
      WUTrace(0, 0, 32, 3, 0, L"Queried service %s is not running");
      LastError = -2145120257;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUServiceWatcher.cpp",
        (const char *)0x80240FFFLL,
        v15);
      goto LABEL_14;
    }
    WUTrace(0, 0, 32, 5, 0, L"Queried service %s is running");
  }
  v11 = CreateSingleTriggerEvent(&v16);
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUServiceWatcher.cpp",
      (const char *)(unsigned int)v11,
      v14);
    v2 = v16;
LABEL_14:
    if ( !v5 )
    {
LABEL_19:
      SetEvent(this[4]);
      goto LABEL_21;
    }
LABEL_18:
    CloseServiceHandle(v5);
    goto LABEL_19;
  }
  v2 = v16;
  pNotifyBuffer.pContext = v16;
  v12 = NotifyServiceStatusChangeW((SC_HANDLE)*this, 1u, &pNotifyBuffer);
  if ( v12 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xB0,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WUServiceWatcher.cpp",
                  (const char *)v12,
                  v14);
    goto LABEL_18;
  }
  CloseServiceHandle(v5);
  SetEvent(this[4]);
  LastError = WUServiceWatcher::WaitAndRun((WUServiceWatcher *)this, v2, &pNotifyBuffer.ServiceStatus.dwWin32ExitCode);
LABEL_21:
  if ( v2 )
    CloseHandle(v2);
  return LastError;
}

```

## disassembly

```asm
0x18008565c  mov     rax, rsp
0x18008565f  mov     [rax+10h], rbx
0x180085663  mov     [rax+18h], rsi
0x180085667  mov     [rax+20h], rdi
0x18008566b  push    rbp
0x18008566c  push    r12
0x18008566e  push    r13
0x180085670  push    r14
0x180085672  push    r15
0x180085674  lea     rbp, [rax-5Fh]
0x180085678  sub     rsp, 0D0h
0x18008567f  mov     rax, cs:__security_cookie
0x180085686  xor     rax, rsp
0x180085689  mov     [rbp+57h+var_30], rax
0x18008568d  mov     rsi, rcx
0x180085690  xor     ebx, ebx
0x180085692  mov     [rbp+57h+var_B0], rbx
0x180085696  xor     edx, edx; Val
0x180085698  lea     r8d, [rbx+50h]; Size
0x18008569c  lea     rcx, [rbp+57h+pNotifyBuffer]; void *
0x1800856a0  call    memset_0
0x1800856a5  mov     [rbp+57h+pNotifyBuffer.dwVersion], 2
0x1800856ac  lea     rax, _anonymous_namespace___NotifyCallback
0x1800856b3  mov     [rbp+57h+pNotifyBuffer.pfnNotifyCallback], rax
0x1800856b7  lea     r8d, [rbx+5]; dwDesiredAccess
0x1800856bb  lea     rdx, DatabaseName; "ServicesActive"
0x1800856c2  xor     ecx, ecx; lpMachineName
0x1800856c4  call    cs:__imp_OpenSCManagerW
0x1800856ca  mov     r14, rax
0x1800856cd  test    rax, rax
0x1800856d0  jnz     short loc_1800856D9
0x1800856d2  mov     edx, 0A2h
0x1800856d7  jmp     short loc_180085723
0x1800856d9  mov     r8d, 4; dwDesiredAccess
0x1800856df  lea     r13, ?c_szWuauservService@@3QB_WB; "wuauserv"
0x1800856e6  mov     rdx, r13; lpServiceName
0x1800856e9  mov     rcx, r14; hSCManager
0x1800856ec  call    cs:__imp_OpenServiceW
0x1800856f2  mov     r15, rax
0x1800856f5  mov     r12, [rsi]
0x1800856f8  test    r12, r12
0x1800856fb  jz      short loc_180085716
0x1800856fd  call    cs:__imp_GetLastError
0x180085703  mov     edi, eax
0x180085705  mov     rcx, r12; hSCObject
0x180085708  call    cs:__imp_CloseServiceHandle
0x18008570e  mov     ecx, edi; dwErrCode
0x180085710  call    cs:__imp_SetLastError
0x180085716  mov     [rsi], r15
0x180085719  test    r15, r15
0x18008571c  jnz     short loc_18008573A
0x18008571e  mov     edx, 0A6h; void *
0x180085723  mov     rcx, [rbp+5Fh]; this
0x180085727  lea     r8, aCW1SSrcClientL_30; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18008572e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180085733  mov     edi, eax
0x180085735  jmp     loc_1800857F2
0x18008573a  xorps   xmm0, xmm0
0x18008573d  xor     eax, eax
0x18008573f  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180085743  mov     qword ptr [rbp+57h+ServiceStatus.dwServiceSpecificExitCode], rax
0x180085747  mov     [rbp+57h+ServiceStatus.dwWaitHint], eax
0x18008574a  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18008574e  mov     rcx, r15; hService
0x180085751  call    cs:__imp_QueryServiceStatus
0x180085757  test    eax, eax
0x180085759  jz      short loc_1800857C7
0x18008575b  mov     [rsp+0F0h+var_C0], r13
0x180085760  xor     edx, edx
0x180085762  xor     ecx, ecx
0x180085764  lea     r8d, [rdx+20h]
0x180085768  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 4
0x18008576c  jz      short loc_1800857A7
0x18008576e  lea     rax, aQueriedService_0; "Queried service %s is not running"
0x180085775  mov     [rsp+0F0h+var_C8], rax
0x18008577a  mov     qword ptr [rsp+0F0h+var_D0], rcx; int
0x18008577f  lea     r9d, [rdx+3]
0x180085783  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180085788  mov     rcx, [rbp+5Fh]; this
0x18008578c  mov     edi, 80240FFFh
0x180085791  mov     r9d, edi; char *
0x180085794  lea     r8, aCW1SSrcClientL_30; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18008579b  mov     edx, 0A7h; void *
0x1800857a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800857a5  jmp     short loc_1800857F2
0x1800857a7  lea     rax, aQueriedService; "Queried service %s is running"
0x1800857ae  mov     [rsp+0F0h+var_C8], rax
0x1800857b3  mov     qword ptr [rsp+0F0h+var_D0], 0; unsigned int
0x1800857bc  mov     r9d, 5
0x1800857c2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800857c7  lea     rcx, [rbp+57h+var_B0]; void **
0x1800857cb  call    ?CreateSingleTriggerEvent@@YAJPEAPEAX@Z; CreateSingleTriggerEvent(void * *)
0x1800857d0  mov     edi, eax
0x1800857d2  test    eax, eax
0x1800857d4  jns     short loc_1800857F9
0x1800857d6  mov     rcx, [rbp+5Fh]; this
0x1800857da  mov     r9d, eax; char *
0x1800857dd  lea     r8, aCW1SSrcClientL_30; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800857e4  mov     edx, 0AAh; void *
0x1800857e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800857ee  mov     rbx, [rbp+57h+var_B0]
0x1800857f2  test    r14, r14
0x1800857f5  jz      short loc_18008583A
0x1800857f7  jmp     short loc_180085831
0x1800857f9  mov     rbx, [rbp+57h+var_B0]
0x1800857fd  mov     [rbp+57h+pNotifyBuffer.pContext], rbx
0x180085801  lea     r8, [rbp+57h+pNotifyBuffer]; pNotifyBuffer
0x180085805  mov     edx, 1; dwNotifyMask
0x18008580a  mov     rcx, [rsi]; hService
0x18008580d  call    cs:__imp_NotifyServiceStatusChangeW
0x180085813  test    eax, eax
0x180085815  jz      short loc_180085846
0x180085817  mov     rcx, [rbp+5Fh]; this
0x18008581b  mov     r9d, eax; char *
0x18008581e  lea     r8, aCW1SSrcClientL_30; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180085825  mov     edx, 0B0h; void *
0x18008582a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008582f  mov     edi, eax
0x180085831  mov     rcx, r14; hSCObject
0x180085834  call    cs:__imp_CloseServiceHandle
0x18008583a  mov     rcx, [rsi+20h]; hEvent
0x18008583e  call    cs:__imp_SetEvent
0x180085844  jmp     short loc_18008586A
0x180085846  mov     rcx, r14; hSCObject
0x180085849  call    cs:__imp_CloseServiceHandle
0x18008584f  mov     rcx, [rsi+20h]; hEvent
0x180085853  call    cs:__imp_SetEvent
0x180085859  lea     r8, [rbp+57h+pNotifyBuffer.ServiceStatus.dwWin32ExitCode]; unsigned int *
0x18008585d  mov     rdx, rbx; void *
0x180085860  mov     rcx, rsi; this
0x180085863  call    ?WaitAndRun@WUServiceWatcher@@AEAAJPEAXAEBK@Z; WUServiceWatcher::WaitAndRun(void *,ulong const &)
0x180085868  mov     edi, eax
0x18008586a  test    rbx, rbx
0x18008586d  jz      short loc_180085878
0x18008586f  mov     rcx, rbx; hObject
0x180085872  call    cs:__imp_CloseHandle
0x180085878  mov     eax, edi
0x18008587a  mov     rcx, [rbp+57h+var_30]
0x18008587e  xor     rcx, rsp; StackCookie
0x180085881  call    __security_check_cookie
0x180085886  lea     r11, [rsp+0F0h+var_20]
0x18008588e  mov     rbx, [r11+38h]
0x180085892  mov     rsi, [r11+40h]
0x180085896  mov     rdi, [r11+48h]
0x18008589a  mov     rsp, r11
0x18008589d  pop     r15
0x18008589f  pop     r14
0x1800858a1  pop     r13
0x1800858a3  pop     r12
0x1800858a5  pop     rbp
0x1800858a6  retn
```
