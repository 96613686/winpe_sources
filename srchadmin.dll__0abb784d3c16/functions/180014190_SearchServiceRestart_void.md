# SearchServiceRestart(void)

- ea: `0x180014190`
- end: `0x18001436b`
- name: `?SearchServiceRestart@@YAJXZ`
- size: `475`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000aab0`
- `0x18000bdd0`
- `0x1800134b0`

## callees

- `0x180005cc0`
- `0x18000d4dc`
- `0x180014190`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014249`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001429f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800142e1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014249`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001429f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800142e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014236`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001426f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800142ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014307`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014236`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001426f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800142ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014307`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800142ad`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800142ad`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001433a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001434c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001433a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001434c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800141bb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800141bb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800141e8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800141e8`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001420c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180014256`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800142be`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800142ee`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001420c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180014256`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800142be`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800142ee`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001422c`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001422c`

## string_xrefs

- `0x1800141ae`: `ServicesActive`

## pseudocode

```c
__int64 SearchServiceRestart(void)
{
  int Error; // ebx
  SC_HANDLE v1; // r14
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rdi
  DWORD TickCount; // esi
  DWORD v5; // esi
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-30h] BYREF

  Error = 0;
  v1 = OpenSCManagerW(0, L"ServicesActive", 1u);
  if ( v1 || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    v2 = OpenServiceW(v1, L"WSearch", 0x34u);
    v3 = v2;
    if ( !v2 )
    {
      Error = ResultFromKnownLastError();
      goto LABEL_34;
    }
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus(v2, &ServiceStatus) )
    {
      if ( ServiceStatus.dwCurrentState != 1 )
      {
        if ( ControlService(v3, 1u, &ServiceStatus) )
        {
          TickCount = GetTickCount();
          while ( ServiceStatus.dwCurrentState != 1 )
          {
            Sleep(0x3E8u);
            if ( QueryServiceStatus(v3, &ServiceStatus) )
            {
              if ( ServiceStatus.dwCurrentState != 1 && GetTickCount() - TickCount > 0xEA60 )
                goto LABEL_30;
            }
            else
            {
              Error = ResultFromKnownLastError();
            }
            if ( Error < 0 )
              goto LABEL_30;
          }
        }
        else
        {
          Error = ResultFromKnownLastError();
        }
      }
      if ( Error < 0 )
        goto LABEL_30;
      Sleep(0x7D0u);
      if ( StartServiceW(v3, 0, 0) && QueryServiceStatus(v3, &ServiceStatus) )
      {
        if ( ServiceStatus.dwCurrentState == 2 )
        {
          v5 = GetTickCount();
          while ( ServiceStatus.dwCurrentState == 2 )
          {
            Sleep(0x3E8u);
            if ( QueryServiceStatus(v3, &ServiceStatus) )
            {
              if ( ServiceStatus.dwCurrentState != 4 && GetTickCount() - v5 > 0x927C0 )
              {
                Error = -2147023436;
                goto LABEL_32;
              }
            }
            else
            {
              Error = ResultFromKnownLastError();
            }
            if ( Error < 0 )
              goto LABEL_32;
          }
          goto LABEL_32;
        }
        if ( ServiceStatus.dwCurrentState == 4 )
        {
LABEL_32:
          CloseServiceHandle(v3);
LABEL_34:
          CloseServiceHandle(v1);
          return (unsigned int)Error;
        }
LABEL_30:
        Error = -2147467259;
        goto LABEL_32;
      }
    }
    Error = ResultFromKnownLastError();
    goto LABEL_32;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180014190  push    rbp
0x180014192  push    rbx
0x180014193  push    rsi
0x180014194  push    rdi
0x180014195  push    r14
0x180014197  mov     rbp, rsp
0x18001419a  sub     rsp, 50h
0x18001419e  mov     rax, cs:__security_cookie
0x1800141a5  xor     rax, rsp
0x1800141a8  mov     [rbp+var_10], rax
0x1800141ac  xor     ebx, ebx
0x1800141ae  lea     rdx, DatabaseName; "ServicesActive"
0x1800141b5  xor     ecx, ecx; lpMachineName
0x1800141b7  lea     r8d, [rbx+1]; dwDesiredAccess
0x1800141bb  call    cs:__imp_OpenSCManagerW
0x1800141c1  mov     r14, rax
0x1800141c4  test    rax, rax
0x1800141c7  jnz     short loc_1800141D8
0x1800141c9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800141ce  mov     ebx, eax
0x1800141d0  test    eax, eax
0x1800141d2  js      loc_180014352
0x1800141d8  mov     r8d, 34h ; '4'; dwDesiredAccess
0x1800141de  lea     rdx, ServiceName; "WSearch"
0x1800141e5  mov     rcx, r14; hSCManager
0x1800141e8  call    cs:__imp_OpenServiceW
0x1800141ee  mov     rdi, rax
0x1800141f1  test    rax, rax
0x1800141f4  jz      loc_180014342
0x1800141fa  xorps   xmm0, xmm0
0x1800141fd  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180014201  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x180014205  mov     rcx, rax; hService
0x180014208  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x18001420c  call    cs:__imp_QueryServiceStatus
0x180014212  test    eax, eax
0x180014214  jz      loc_180014330
0x18001421a  cmp     [rbp+ServiceStatus.dwCurrentState], 1
0x18001421e  jz      short loc_180014292
0x180014220  lea     r8, [rbp+ServiceStatus]; lpServiceStatus
0x180014224  mov     edx, 1; dwControl
0x180014229  mov     rcx, rdi; hService
0x18001422c  call    cs:__imp_ControlService
0x180014232  test    eax, eax
0x180014234  jz      short loc_18001428B
0x180014236  call    cs:__imp_GetTickCount
0x18001423c  mov     esi, eax
0x18001423e  cmp     [rbp+ServiceStatus.dwCurrentState], 1
0x180014242  jz      short loc_180014292
0x180014244  mov     ecx, 3E8h; dwMilliseconds
0x180014249  call    cs:__imp_Sleep
0x18001424f  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180014253  mov     rcx, rdi; hService
0x180014256  call    cs:__imp_QueryServiceStatus
0x18001425c  test    eax, eax
0x18001425e  jnz     short loc_180014269
0x180014260  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014265  mov     ebx, eax
0x180014267  jmp     short loc_180014282
0x180014269  cmp     [rbp+ServiceStatus.dwCurrentState], 1
0x18001426d  jz      short loc_180014282
0x18001426f  call    cs:__imp_GetTickCount
0x180014275  sub     eax, esi
0x180014277  cmp     eax, 0EA60h
0x18001427c  ja      loc_180014329
0x180014282  test    ebx, ebx
0x180014284  jns     short loc_18001423E
0x180014286  jmp     loc_180014329
0x18001428b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014290  mov     ebx, eax
0x180014292  test    ebx, ebx
0x180014294  js      loc_180014329
0x18001429a  mov     ecx, 7D0h; dwMilliseconds
0x18001429f  call    cs:__imp_Sleep
0x1800142a5  xor     r8d, r8d; lpServiceArgVectors
0x1800142a8  xor     edx, edx; dwNumServiceArgs
0x1800142aa  mov     rcx, rdi; hService
0x1800142ad  call    cs:__imp_StartServiceW
0x1800142b3  test    eax, eax
0x1800142b5  jz      short loc_180014330
0x1800142b7  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1800142bb  mov     rcx, rdi; hService
0x1800142be  call    cs:__imp_QueryServiceStatus
0x1800142c4  test    eax, eax
0x1800142c6  jz      short loc_180014330
0x1800142c8  cmp     [rbp+ServiceStatus.dwCurrentState], 2
0x1800142cc  jnz     short loc_180014323
0x1800142ce  call    cs:__imp_GetTickCount
0x1800142d4  mov     esi, eax
0x1800142d6  cmp     [rbp+ServiceStatus.dwCurrentState], 2
0x1800142da  jnz     short loc_180014337
0x1800142dc  mov     ecx, 3E8h; dwMilliseconds
0x1800142e1  call    cs:__imp_Sleep
0x1800142e7  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x1800142eb  mov     rcx, rdi; hService
0x1800142ee  call    cs:__imp_QueryServiceStatus
0x1800142f4  test    eax, eax
0x1800142f6  jnz     short loc_180014301
0x1800142f8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800142fd  mov     ebx, eax
0x1800142ff  jmp     short loc_180014316
0x180014301  cmp     [rbp+ServiceStatus.dwCurrentState], 4
0x180014305  jz      short loc_180014316
0x180014307  call    cs:__imp_GetTickCount
0x18001430d  sub     eax, esi
0x18001430f  cmp     eax, 927C0h
0x180014314  ja      short loc_18001431C
0x180014316  test    ebx, ebx
0x180014318  jns     short loc_1800142D6
0x18001431a  jmp     short loc_180014337
0x18001431c  mov     ebx, 800705B4h
0x180014321  jmp     short loc_180014337
0x180014323  cmp     [rbp+ServiceStatus.dwCurrentState], 4
0x180014327  jz      short loc_180014337
0x180014329  mov     ebx, 80004005h
0x18001432e  jmp     short loc_180014337
0x180014330  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014335  mov     ebx, eax
0x180014337  mov     rcx, rdi; hSCObject
0x18001433a  call    cs:__imp_CloseServiceHandle
0x180014340  jmp     short loc_180014349
0x180014342  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014347  mov     ebx, eax
0x180014349  mov     rcx, r14; hSCObject
0x18001434c  call    cs:__imp_CloseServiceHandle
0x180014352  mov     eax, ebx
0x180014354  mov     rcx, [rbp+var_10]
0x180014358  xor     rcx, rsp; StackCookie
0x18001435b  call    __security_check_cookie
0x180014360  add     rsp, 50h
0x180014364  pop     r14
0x180014366  pop     rdi
0x180014367  pop     rsi
0x180014368  pop     rbx
0x180014369  pop     rbp
0x18001436a  retn
```
