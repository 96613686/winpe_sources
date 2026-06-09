# ServiceBase::_ServiceMainInner(void)

- ea: `0x18005f9f8`
- end: `0x18005fbe1`
- name: `?_ServiceMainInner@ServiceBase@@AEAAJXZ`
- size: `489`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18005f8b0`

## callees

- `0x180043d38`
- `0x18005f9f8`
- `0x18005fcb4`
- `0x18005fd7c`
- `0x18005fde4`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fb77`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18005fb31`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18005fb31`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18005fa6b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18005fae5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18005fa6b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18005fae5`

## pseudocode

```c
signed int __fastcall ServiceBase::_ServiceMainInner(ServiceBase *this)
{
  signed int result; // eax
  ServiceBase *v2; // rcx
  ServiceBase *v3; // rcx
  int v4; // ebx
  __int64 (__fastcall *v5)(__int64 *); // rax
  bool v6; // sf
  bool v7; // sf
  __int64 *v8; // rdx

  if ( !qword_18010C470 )
    return -2147467263;
  result = ServiceBase::_CheckServiceShutdownAlready(this);
  if ( result >= 0 )
  {
    result = ServiceBase::_CreateStopEvent(v2);
    if ( result >= 0 )
    {
      ++ServiceStatus.dwCheckPoint;
      ServiceStatus.dwCurrentState = 2;
      ServiceStatus.dwWaitHint = (*(__int64 (__fastcall **)(__int64 *))(qword_18010C3C0 + 72))(&qword_18010C3C0);
      if ( SetServiceStatus(hServiceStatus, &ServiceStatus) )
        goto LABEL_6;
      result = GetLastError();
      v6 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v6 = result < 0;
      }
      if ( !v6 )
      {
LABEL_6:
        v4 = (*(__int64 (__fastcall **)(__int64 *))(qword_18010C3C0 + 8))(&qword_18010C3C0);
        if ( v4 < 0 )
        {
          if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x20) != 0 )
          {
            v8 = ServiceBaseServiceStartingError;
LABEL_25:
            McTemplateU0zq_EventWriteTransfer(v3, v8, &ServiceName, (unsigned int)v4);
          }
        }
        else
        {
          ServiceStatus.dwControlsAccepted |= 0x401u;
          LODWORD(qword_18010C43C) = 1;
          ServiceStatus.dwCurrentState = 4;
          v5 = *(__int64 (__fastcall **)(__int64 *))(qword_18010C3C0 + 64);
          ServiceStatus.dwCheckPoint = 0;
          ServiceStatus.dwControlsAccepted |= v5(&qword_18010C3C0);
          if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
          {
            result = GetLastError();
            v7 = result < 0;
            if ( result > 0 )
            {
              result = (unsigned __int16)result | 0x80070000;
              v7 = result < 0;
            }
            if ( v7 )
              return result;
          }
          v4 = (*(__int64 (__fastcall **)(__int64 *))(qword_18010C3C0 + 24))(&qword_18010C3C0);
          if ( v4 >= 0 )
          {
            result = ServiceBase::_RegisterStopCallbackHandler(v3);
            if ( result >= 0 )
            {
              if ( HIDWORD(qword_18010C43C) )
                (*(void (__fastcall **)(__int64 *, _QWORD))(qword_18010C3C0 + 32))(
                  &qword_18010C3C0,
                  (unsigned int)dword_18010C444);
              CoFreeUnusedLibrariesEx(0x7530u, 0);
              return 0;
            }
            return result;
          }
          if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x20) != 0 )
          {
            v8 = ServiceBaseServiceStartedError;
            goto LABEL_25;
          }
        }
        return v4;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005f9f8  mov     [rsp+arg_0], rbx
0x18005f9fd  push    rsi
0x18005f9fe  sub     rsp, 20h
0x18005fa02  cmp     cs:qword_18010C470, 0
0x18005fa0a  jz      loc_18005FB8D
0x18005fa10  call    ?_CheckServiceShutdownAlready@ServiceBase@@AEAAJXZ; ServiceBase::_CheckServiceShutdownAlready(void)
0x18005fa15  test    eax, eax
0x18005fa17  jns     short loc_18005FA24
0x18005fa19  mov     rbx, [rsp+28h+arg_0]
0x18005fa1e  add     rsp, 20h
0x18005fa22  pop     rsi
0x18005fa23  retn
0x18005fa24  call    ?_CreateStopEvent@ServiceBase@@AEAAJXZ; ServiceBase::_CreateStopEvent(void)
0x18005fa29  test    eax, eax
0x18005fa2b  js      short loc_18005FA19
0x18005fa2d  mov     rax, cs:qword_18010C3C0
0x18005fa34  lea     rsi, qword_18010C3C0
0x18005fa3b  inc     cs:ServiceStatus.dwCheckPoint
0x18005fa41  mov     rcx, rsi
0x18005fa44  mov     cs:ServiceStatus.dwCurrentState, 2
0x18005fa4e  mov     rax, [rax+48h]
0x18005fa52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fa57  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18005fa5e  lea     rdx, ServiceStatus; lpServiceStatus
0x18005fa65  mov     cs:ServiceStatus.dwWaitHint, eax
0x18005fa6b  call    cs:__imp_SetServiceStatus
0x18005fa71  test    eax, eax
0x18005fa73  jz      loc_18005FB61
0x18005fa79  mov     rax, cs:qword_18010C3C0
0x18005fa80  mov     rcx, rsi
0x18005fa83  mov     rax, [rax+8]
0x18005fa87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fa8c  mov     ebx, eax
0x18005fa8e  test    eax, eax
0x18005fa90  js      loc_18005FB3E
0x18005fa96  mov     rax, cs:qword_18010C3C0
0x18005fa9d  mov     rcx, rsi
0x18005faa0  or      cs:ServiceStatus.dwControlsAccepted, 401h
0x18005faaa  mov     dword ptr cs:qword_18010C43C, 1
0x18005fab4  mov     cs:ServiceStatus.dwCurrentState, 4
0x18005fabe  mov     rax, [rax+40h]
0x18005fac2  mov     cs:ServiceStatus.dwCheckPoint, 0
0x18005facc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fad1  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18005fad8  lea     rdx, ServiceStatus; lpServiceStatus
0x18005fadf  or      cs:ServiceStatus.dwControlsAccepted, eax
0x18005fae5  call    cs:__imp_SetServiceStatus
0x18005faeb  test    eax, eax
0x18005faed  jz      loc_18005FB77
0x18005faf3  mov     rax, cs:qword_18010C3C0
0x18005fafa  mov     rcx, rsi
0x18005fafd  mov     rax, [rax+18h]
0x18005fb01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb06  mov     ebx, eax
0x18005fb08  test    eax, eax
0x18005fb0a  js      loc_18005FBB8
0x18005fb10  call    ?_RegisterStopCallbackHandler@ServiceBase@@AEAAJXZ; ServiceBase::_RegisterStopCallbackHandler(void)
0x18005fb15  test    eax, eax
0x18005fb17  js      loc_18005FA19
0x18005fb1d  cmp     dword ptr cs:qword_18010C43C+4, 0
0x18005fb24  jnz     loc_18005FBC3
0x18005fb2a  xor     edx, edx; dwReserved
0x18005fb2c  mov     ecx, 7530h; dwUnloadDelay
0x18005fb31  call    cs:__imp_CoFreeUnusedLibrariesEx
0x18005fb37  xor     eax, eax
0x18005fb39  jmp     loc_18005FA19
0x18005fb3e  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 20h
0x18005fb45  jnz     short loc_18005FB97
0x18005fb47  mov     eax, ebx
0x18005fb49  jmp     loc_18005FA19
0x18005fb4e  jns     loc_18005FA79
0x18005fb54  jmp     loc_18005FA19
0x18005fb59  js      loc_18005FA19
0x18005fb5f  jmp     short loc_18005FAF3
0x18005fb61  call    cs:__imp_GetLastError
0x18005fb67  test    eax, eax
0x18005fb69  jle     short loc_18005FB4E
0x18005fb6b  movzx   eax, ax
0x18005fb6e  or      eax, 80070000h
0x18005fb73  test    eax, eax
0x18005fb75  jmp     short loc_18005FB4E
0x18005fb77  call    cs:__imp_GetLastError
0x18005fb7d  test    eax, eax
0x18005fb7f  jle     short loc_18005FB59
0x18005fb81  movzx   eax, ax
0x18005fb84  or      eax, 80070000h
0x18005fb89  test    eax, eax
0x18005fb8b  jmp     short loc_18005FB59
0x18005fb8d  mov     eax, 80004001h
0x18005fb92  jmp     loc_18005FA19
0x18005fb97  lea     rdx, ServiceBaseServiceStartingError
0x18005fb9e  jmp     short loc_18005FBA7
0x18005fba0  lea     rdx, ServiceBaseServiceStartedError
0x18005fba7  lea     r8, ServiceName
0x18005fbae  mov     r9d, ebx
0x18005fbb1  call    McTemplateU0zq_EventWriteTransfer
0x18005fbb6  jmp     short loc_18005FB47
0x18005fbb8  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 20h
0x18005fbbf  jz      short loc_18005FB47
0x18005fbc1  jmp     short loc_18005FBA0
0x18005fbc3  mov     rax, cs:qword_18010C3C0
0x18005fbca  mov     rcx, rsi
0x18005fbcd  mov     edx, cs:dword_18010C444
0x18005fbd3  mov     rax, [rax+20h]
0x18005fbd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fbdc  jmp     loc_18005FB2A
```
