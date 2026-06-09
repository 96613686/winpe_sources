# ServiceBase::_ServiceMainInner(void)

- ea: `0x180067014`
- end: `0x1800671da`
- name: `?_ServiceMainInner@ServiceBase@@AEAAJXZ`
- size: `454`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180115e88`

## callees

- `0x180005c2c`
- `0x180067014`
- `0x1800671e0`
- `0x18007dbe4`
- `0x18007e408`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006714d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006714d`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x1800671c7`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x1800671c7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18006708a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180067143`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18006708a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180067143`

## pseudocode

```c
signed int __fastcall ServiceBase::_ServiceMainInner(ServiceBase *this)
{
  signed int result; // eax
  ServiceBase *v2; // rcx
  bool v3; // sf
  int v4; // ebx
  __int64 *v5; // rdx
  __int64 (__fastcall *v6)(__int64 *); // rax
  bool v7; // sf
  ServiceBase *v8; // rcx

  if ( !qword_18015D5F0 )
    return -2147467263;
  result = ServiceBase::_CheckServiceShutdownAlready(this);
  if ( result >= 0 )
  {
    result = ServiceBase::_CreateStopEvent(v2);
    if ( result >= 0 )
    {
      ++ServiceStatus.dwCheckPoint;
      ServiceStatus.dwCurrentState = 2;
      ServiceStatus.dwWaitHint = (*(__int64 (__fastcall **)(__int64 *))(qword_18015D540 + 72))(&qword_18015D540);
      if ( SetServiceStatus(hServiceStatus, &ServiceStatus) )
        goto LABEL_9;
      result = GetLastError();
      v3 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v3 = result < 0;
      }
      if ( !v3 )
      {
LABEL_9:
        v4 = (*(__int64 (__fastcall **)(__int64 *))(qword_18015D540 + 8))(&qword_18015D540);
        if ( v4 < 0 )
        {
          if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x20) == 0 )
            return v4;
          v5 = ServiceBaseServiceStartingError;
LABEL_12:
          McTemplateU0zq_EventWriteTransfer(
            &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context,
            v5,
            &ServiceName,
            (unsigned int)v4);
          return v4;
        }
        ServiceStatus.dwControlsAccepted |= 0x401u;
        LODWORD(qword_18015D5BC) = 1;
        ServiceStatus.dwCurrentState = 4;
        v6 = *(__int64 (__fastcall **)(__int64 *))(qword_18015D540 + 64);
        ServiceStatus.dwCheckPoint = 0;
        ServiceStatus.dwControlsAccepted |= v6(&qword_18015D540);
        if ( SetServiceStatus(hServiceStatus, &ServiceStatus) )
          goto LABEL_18;
        result = GetLastError();
        v7 = result < 0;
        if ( result > 0 )
        {
          result = (unsigned __int16)result | 0x80070000;
          v7 = result < 0;
        }
        if ( !v7 )
        {
LABEL_18:
          v4 = (*(__int64 (__fastcall **)(__int64 *))(qword_18015D540 + 24))(&qword_18015D540);
          if ( v4 < 0 )
          {
            if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x20) == 0 )
              return v4;
            v5 = ServiceBaseServiceStartedError;
            goto LABEL_12;
          }
          result = ServiceBase::_RegisterStopCallbackHandler(v8);
          if ( result >= 0 )
          {
            if ( HIDWORD(qword_18015D5BC) )
              (*(void (__fastcall **)(__int64 *, _QWORD))(qword_18015D540 + 32))(
                &qword_18015D540,
                (unsigned int)dword_18015D5C4);
            CoFreeUnusedLibrariesEx(0x7530u, 0);
            return 0;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180067014  mov     [rsp+arg_0], rbx
0x180067019  push    rsi
0x18006701a  sub     rsp, 20h
0x18006701e  cmp     cs:qword_18015D5F0, 0
0x180067026  jnz     short loc_180067032
0x180067028  mov     eax, 80004001h
0x18006702d  jmp     loc_1800671CF
0x180067032  call    ?_CheckServiceShutdownAlready@ServiceBase@@AEAAJXZ; ServiceBase::_CheckServiceShutdownAlready(void)
0x180067037  test    eax, eax
0x180067039  js      loc_1800671CF
0x18006703f  call    ?_CreateStopEvent@ServiceBase@@AEAAJXZ; ServiceBase::_CreateStopEvent(void)
0x180067044  test    eax, eax
0x180067046  js      loc_1800671CF
0x18006704c  mov     rax, cs:qword_18015D540
0x180067053  lea     rsi, qword_18015D540
0x18006705a  inc     cs:ServiceStatus.dwCheckPoint
0x180067060  mov     rcx, rsi
0x180067063  mov     cs:ServiceStatus.dwCurrentState, 2
0x18006706d  mov     rax, [rax+48h]
0x180067071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067076  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18006707d  lea     rdx, ServiceStatus; lpServiceStatus
0x180067084  mov     cs:ServiceStatus.dwWaitHint, eax
0x18006708a  call    cs:__imp_SetServiceStatus
0x180067090  test    eax, eax
0x180067092  jnz     short loc_1800670AE
0x180067094  call    cs:__imp_GetLastError
0x18006709a  test    eax, eax
0x18006709c  jle     short loc_1800670A8
0x18006709e  movzx   eax, ax
0x1800670a1  or      eax, 80070000h
0x1800670a6  test    eax, eax
0x1800670a8  js      loc_1800671CF
0x1800670ae  mov     rax, cs:qword_18015D540
0x1800670b5  mov     rcx, rsi
0x1800670b8  mov     rax, [rax+8]
0x1800670bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670c1  mov     ebx, eax
0x1800670c3  test    eax, eax
0x1800670c5  jns     short loc_1800670F4
0x1800670c7  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 20h
0x1800670ce  jz      short loc_1800670ED
0x1800670d0  lea     rdx, ServiceBaseServiceStartingError
0x1800670d7  lea     r8, ServiceName
0x1800670de  mov     r9d, ebx
0x1800670e1  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context
0x1800670e8  call    McTemplateU0zq_EventWriteTransfer
0x1800670ed  mov     eax, ebx
0x1800670ef  jmp     loc_1800671CF
0x1800670f4  mov     rax, cs:qword_18015D540
0x1800670fb  mov     rcx, rsi
0x1800670fe  or      cs:ServiceStatus.dwControlsAccepted, 401h
0x180067108  mov     dword ptr cs:qword_18015D5BC, 1
0x180067112  mov     cs:ServiceStatus.dwCurrentState, 4
0x18006711c  mov     rax, [rax+40h]
0x180067120  mov     cs:ServiceStatus.dwCheckPoint, 0
0x18006712a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006712f  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180067136  lea     rdx, ServiceStatus; lpServiceStatus
0x18006713d  or      cs:ServiceStatus.dwControlsAccepted, eax
0x180067143  call    cs:__imp_SetServiceStatus
0x180067149  test    eax, eax
0x18006714b  jnz     short loc_180067163
0x18006714d  call    cs:__imp_GetLastError
0x180067153  test    eax, eax
0x180067155  jle     short loc_180067161
0x180067157  movzx   eax, ax
0x18006715a  or      eax, 80070000h
0x18006715f  test    eax, eax
0x180067161  js      short loc_1800671CF
0x180067163  mov     rax, cs:qword_18015D540
0x18006716a  mov     rcx, rsi
0x18006716d  mov     rax, [rax+18h]
0x180067171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067176  mov     ebx, eax
0x180067178  test    eax, eax
0x18006717a  jns     short loc_180067195
0x18006717c  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 20h
0x180067183  jz      loc_1800670ED
0x180067189  lea     rdx, ServiceBaseServiceStartedError
0x180067190  jmp     loc_1800670D7
0x180067195  call    ?_RegisterStopCallbackHandler@ServiceBase@@AEAAJXZ; ServiceBase::_RegisterStopCallbackHandler(void)
0x18006719a  test    eax, eax
0x18006719c  js      short loc_1800671CF
0x18006719e  cmp     dword ptr cs:qword_18015D5BC+4, 0
0x1800671a5  jz      short loc_1800671C0
0x1800671a7  mov     rax, cs:qword_18015D540
0x1800671ae  mov     rcx, rsi
0x1800671b1  mov     edx, cs:dword_18015D5C4
0x1800671b7  mov     rax, [rax+20h]
0x1800671bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800671c0  xor     edx, edx; dwReserved
0x1800671c2  mov     ecx, 7530h; dwUnloadDelay
0x1800671c7  call    cs:__imp_CoFreeUnusedLibrariesEx
0x1800671cd  xor     eax, eax
0x1800671cf  mov     rbx, [rsp+28h+arg_0]
0x1800671d4  add     rsp, 20h
0x1800671d8  pop     rsi
0x1800671d9  retn
```
