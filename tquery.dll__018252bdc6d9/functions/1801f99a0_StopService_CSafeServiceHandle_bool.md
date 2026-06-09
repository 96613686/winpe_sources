# StopService(CSafeServiceHandle &,bool)

- ea: `0x1801f99a0`
- end: `0x1801f9b61`
- name: `?StopService@@YAJAEAVCSafeServiceHandle@@_N@Z`
- size: `449`
- prototype: `__int64 __fastcall(struct CSafeServiceHandle *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x1801a95c0`

## callees

- `0x18002e6fc`
- `0x18008a284`
- `0x180188d90`
- `0x18018e778`
- `0x1801a4420`
- `0x1801f9940`
- `0x1801f99a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f9a06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f9a06`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801f9ad4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801f9ad4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801f9ab3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801f9ac6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801f9ab3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801f9ac6`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801f9ae2`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1801f9ae2`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1801f9aa9`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1801f9b29`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1801f9aa9`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1801f9b29`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1801f99f8`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1801f9a57`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1801f99f8`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1801f9a57`

## pseudocode

```c
__int64 __fastcall StopService(SC_HANDLE *a1)
{
  struct _ENUM_SERVICE_STATUSW *v2; // rax
  struct _ENUM_SERVICE_STATUSW *v3; // rsi
  const wchar_t *v4; // r9
  __int64 i; // rdi
  ULONGLONG v6; // r14
  SC_HANDLE v7; // rcx
  DWORD cbBufSize; // [rsp+38h] [rbp-19h] BYREF
  DWORD ServicesReturned; // [rsp+3Ch] [rbp-15h] BYREF
  SC_HANDLE hService; // [rsp+40h] [rbp-11h] BYREF
  struct _ENUM_SERVICE_STATUSW *v12; // [rsp+48h] [rbp-9h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+50h] [rbp-1h] BYREF
  struct _SERVICE_STATUS v14; // [rsp+70h] [rbp+1Fh] BYREF

  cbBufSize = 0;
  ServicesReturned = 0;
  if ( !EnumDependentServicesW(*a1, 1u, 0, 0, &cbBufSize, &ServicesReturned) && GetLastError() == 234 )
  {
    v2 = (struct _ENUM_SERVICE_STATUSW *)operator new[](cbBufSize, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v2;
    v3 = v2;
    if ( v2 )
    {
      if ( EnumDependentServicesW(*a1, 1u, v2, cbBufSize, &cbBufSize, &ServicesReturned) )
      {
        for ( i = 0; (unsigned int)i < ServicesReturned; i = (unsigned int)(i + 1) )
        {
          CSafeServiceHandle::CSafeServiceHandle((CSafeServiceHandle *)&hService, v3[i].lpServiceName, 0x24u, v4);
          if ( hService )
          {
            memset(&ServiceStatus, 0, sizeof(ServiceStatus));
            if ( ControlService(hService, 1u, &ServiceStatus) )
            {
              v6 = GetTickCount64() + 30000;
              while ( ServiceStatus.dwCurrentState != 1 )
              {
                if ( GetTickCount64() >= v6 )
                  break;
                Sleep(ServiceStatus.dwWaitHint);
                if ( !QueryServiceStatus(hService, &ServiceStatus) && (int)ResultFromKnownLastError() < 0 )
                  break;
              }
            }
          }
          CSafeServiceHandle::~CSafeServiceHandle((CSafeServiceHandle *)&hService);
        }
      }
    }
    SecUtil::CSID_DefApp::~CSID_DefApp((SecUtil::CSID_DefApp *)&v12);
  }
  v7 = *a1;
  memset(&v14, 0, sizeof(v14));
  if ( ControlService(v7, 1u, &v14) )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x1801f99a0  mov     r11, rsp
0x1801f99a3  mov     [r11+10h], rsi
0x1801f99a7  mov     [r11+18h], rdi
0x1801f99ab  push    rbp
0x1801f99ac  push    r14
0x1801f99ae  push    r15
0x1801f99b0  lea     rbp, [r11-5Fh]
0x1801f99b4  sub     rsp, 90h
0x1801f99bb  mov     rax, cs:__security_cookie
0x1801f99c2  xor     rax, rsp
0x1801f99c5  mov     [rbp+57h+var_18], rax
0x1801f99c9  xor     r9d, r9d; cbBufSize
0x1801f99cc  mov     [rbp+57h+cbBufSize], 0
0x1801f99d3  lea     rax, [rbp+57h+ServicesReturned]
0x1801f99d7  mov     [rbp+57h+ServicesReturned], 0
0x1801f99de  mov     [r11-80h], rax
0x1801f99e2  mov     r15, rcx
0x1801f99e5  mov     rcx, [rcx]; hService
0x1801f99e8  lea     rax, [rbp+57h+cbBufSize]
0x1801f99ec  lea     edx, [r9+1]; dwServiceState
0x1801f99f0  mov     [rsp+0A0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1801f99f5  xor     r8d, r8d; lpServices
0x1801f99f8  call    cs:__imp_EnumDependentServicesW
0x1801f99fe  test    eax, eax
0x1801f9a00  jnz     loc_1801F9B12
0x1801f9a06  call    cs:__imp_GetLastError
0x1801f9a0c  cmp     eax, 0EAh
0x1801f9a11  jnz     loc_1801F9B12
0x1801f9a17  mov     ecx, [rbp+57h+cbBufSize]; unsigned __int64
0x1801f9a1a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801f9a21  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801f9a26  mov     [rbp+57h+var_60], rax
0x1801f9a2a  mov     rsi, rax
0x1801f9a2d  test    rax, rax
0x1801f9a30  jz      loc_1801F9B09
0x1801f9a36  mov     r9d, [rbp+57h+cbBufSize]; cbBufSize
0x1801f9a3a  lea     rax, [rbp+57h+ServicesReturned]
0x1801f9a3e  mov     rcx, [r15]; hService
0x1801f9a41  mov     r8, rsi; lpServices
0x1801f9a44  mov     [rsp+0A0h+lpServicesReturned], rax; lpServicesReturned
0x1801f9a49  mov     edx, 1; dwServiceState
0x1801f9a4e  lea     rax, [rbp+57h+cbBufSize]
0x1801f9a52  mov     [rsp+0A0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1801f9a57  call    cs:__imp_EnumDependentServicesW
0x1801f9a5d  test    eax, eax
0x1801f9a5f  jz      loc_1801F9B09
0x1801f9a65  xor     edi, edi
0x1801f9a67  cmp     [rbp+57h+ServicesReturned], edi
0x1801f9a6a  jbe     loc_1801F9B09
0x1801f9a70  lea     rdx, [rdi+rdi*2]
0x1801f9a74  mov     r8d, 24h ; '$'; unsigned int
0x1801f9a7a  add     rdx, rdx
0x1801f9a7d  lea     rcx, [rbp+57h+hService]; this
0x1801f9a81  mov     rdx, [rsi+rdx*8]; wchar_t *
0x1801f9a85  call    ??0CSafeServiceHandle@@QEAA@PEB_WK0@Z; CSafeServiceHandle::CSafeServiceHandle(wchar_t const *,ulong,wchar_t const *)
0x1801f9a8a  cmp     [rbp+57h+hService], 0
0x1801f9a8f  jz      short loc_1801F9AF5
0x1801f9a91  mov     rcx, [rbp+57h+hService]; hService
0x1801f9a95  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x1801f9a99  xorps   xmm0, xmm0
0x1801f9a9c  mov     edx, 1; dwControl
0x1801f9aa1  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x1801f9aa5  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x1801f9aa9  call    cs:__imp_ControlService
0x1801f9aaf  test    eax, eax
0x1801f9ab1  jz      short loc_1801F9AF5
0x1801f9ab3  call    cs:__imp_GetTickCount64
0x1801f9ab9  lea     r14, [rax+7530h]
0x1801f9ac0  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x1801f9ac4  jz      short loc_1801F9AF5
0x1801f9ac6  call    cs:__imp_GetTickCount64
0x1801f9acc  cmp     rax, r14
0x1801f9acf  jnb     short loc_1801F9AF5
0x1801f9ad1  mov     ecx, [rbp+57h+ServiceStatus.dwWaitHint]; dwMilliseconds
0x1801f9ad4  call    cs:__imp_Sleep
0x1801f9ada  mov     rcx, [rbp+57h+hService]; hService
0x1801f9ade  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x1801f9ae2  call    cs:__imp_QueryServiceStatus
0x1801f9ae8  test    eax, eax
0x1801f9aea  jnz     short loc_1801F9AC0
0x1801f9aec  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801f9af1  test    eax, eax
0x1801f9af3  jns     short loc_1801F9AC0
0x1801f9af5  lea     rcx, [rbp+57h+hService]; this
0x1801f9af9  call    ??1CSafeServiceHandle@@QEAA@XZ; CSafeServiceHandle::~CSafeServiceHandle(void)
0x1801f9afe  inc     edi
0x1801f9b00  cmp     edi, [rbp+57h+ServicesReturned]
0x1801f9b03  jb      loc_1801F9A70
0x1801f9b09  lea     rcx, [rbp+57h+var_60]; this
0x1801f9b0d  call    ??1CSID_DefApp@SecUtil@@QEAA@XZ; SecUtil::CSID_DefApp::~CSID_DefApp(void)
0x1801f9b12  mov     rcx, [r15]; hService
0x1801f9b15  lea     r8, [rbp+57h+var_38]; lpServiceStatus
0x1801f9b19  xorps   xmm0, xmm0
0x1801f9b1c  mov     edx, 1; dwControl
0x1801f9b21  movups  xmmword ptr [rbp+57h+var_38.dwServiceType], xmm0
0x1801f9b25  movups  xmmword ptr [rbp+57h+var_38.dwWin32ExitCode], xmm0
0x1801f9b29  call    cs:__imp_ControlService
0x1801f9b2f  test    eax, eax
0x1801f9b31  jz      short loc_1801F9B37
0x1801f9b33  xor     eax, eax
0x1801f9b35  jmp     short loc_1801F9B3C
0x1801f9b37  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801f9b3c  mov     rcx, [rbp+57h+var_18]
0x1801f9b40  xor     rcx, rsp; StackCookie
0x1801f9b43  call    __security_check_cookie
0x1801f9b48  lea     r11, [rsp+0A0h+var_10]
0x1801f9b50  mov     rsi, [r11+28h]
0x1801f9b54  mov     rdi, [r11+30h]
0x1801f9b58  mov     rsp, r11
0x1801f9b5b  pop     r15
0x1801f9b5d  pop     r14
0x1801f9b5f  pop     rbp
0x1801f9b60  retn
```
