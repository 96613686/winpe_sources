# GSM::StopAllServices(void)

- ea: `0x1800212f4`
- end: `0x1800214ac`
- name: `?StopAllServices@GSM@@YAXXZ`
- size: `440`
- prototype: `void __fastcall(GSM *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a040`

## callees

- `0x18001951c`
- `0x1800212f4`
- `0x1800221a4`
- `0x180032c6a`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180021341`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180021341`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180021321`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180021321`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180021482`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002148b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180021482`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002148b`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18002137f`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18002141d`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18002137f`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18002141d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180021479`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180021479`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002145a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002145a`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800213c1`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800213c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800213a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800213a2`

## pseudocode

```c
void __fastcall GSM::StopAllServices(GSM *this)
{
  SC_HANDLE v1; // rax
  GSM *v2; // r14
  SC_HANDLE v3; // rsi
  int Error; // ebx
  struct _ENUM_SERVICE_STATUSW *v5; // rdi
  size_t v6; // rbx
  const unsigned __int16 *v7; // r8
  __int64 v8; // r15
  int v9; // eax
  DWORD cbBufSize; // [rsp+30h] [rbp-40h] BYREF
  DWORD ServicesReturned; // [rsp+34h] [rbp-3Ch] BYREF
  LPMALLOC ppMalloc; // [rsp+38h] [rbp-38h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-30h] BYREF

  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = (GSM *)v1;
  if ( v1 )
  {
    v3 = OpenServiceW(v1, GSM::g_rgsubservice, 0x28u);
    if ( !v3 )
    {
LABEL_18:
      CloseServiceHandle((SC_HANDLE)v2);
      return;
    }
    cbBufSize = 0;
    ServicesReturned = 0;
    if ( EnumDependentServicesW(v3, 1u, 0, 0, &cbBufSize, &ServicesReturned) )
      goto LABEL_16;
    Error = ResultFromKnownLastError();
    if ( Error == -2147024662 )
    {
      v5 = (struct _ENUM_SERVICE_STATUSW *)CoTaskMemAlloc(cbBufSize);
      if ( !v5 )
        goto LABEL_17;
      v6 = 0;
      ppMalloc = 0;
      if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
      {
        v6 = ((__int64 (__fastcall *)(LPMALLOC, struct _ENUM_SERVICE_STATUSW *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v5);
        ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
      }
      memset_0(v5, 0, v6);
      if ( EnumDependentServicesW(v3, 1u, v5, cbBufSize, &cbBufSize, &ServicesReturned) )
      {
        v8 = 0;
        Error = 0;
        do
        {
          if ( (unsigned int)v8 >= ServicesReturned )
            break;
          v9 = GSM::_StopServiceAndWait(v2, v5[v8].lpServiceName, v7);
          v8 = (unsigned int)(v8 + 1);
          Error = v9;
        }
        while ( v9 >= 0 );
      }
      else
      {
        Error = ResultFromKnownLastError();
      }
      CoTaskMemFree(v5);
    }
    if ( Error >= 0 )
    {
LABEL_16:
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      ControlService(v3, 1u, &ServiceStatus);
    }
LABEL_17:
    CloseServiceHandle(v3);
    goto LABEL_18;
  }
}

```

## disassembly

```asm
0x1800212f4  push    rbp
0x1800212f6  push    rbx
0x1800212f7  push    rsi
0x1800212f8  push    rdi
0x1800212f9  push    r13
0x1800212fb  push    r14
0x1800212fd  push    r15
0x1800212ff  mov     rbp, rsp
0x180021302  sub     rsp, 70h
0x180021306  mov     rax, cs:__security_cookie
0x18002130d  xor     rax, rsp
0x180021310  mov     [rbp+var_10], rax
0x180021314  mov     r13d, 1
0x18002131a  xor     edx, edx; lpDatabaseName
0x18002131c  mov     r8d, r13d; dwDesiredAccess
0x18002131f  xor     ecx, ecx; lpMachineName
0x180021321  call    cs:__imp_OpenSCManagerW
0x180021327  mov     r14, rax
0x18002132a  test    rax, rax
0x18002132d  jz      loc_180021491
0x180021333  mov     rdx, cs:?g_rgsubservice@GSM@@3PAUSUBSERVICE@1@A; lpServiceName
0x18002133a  lea     r8d, [r13+27h]; dwDesiredAccess
0x18002133e  mov     rcx, rax; hSCManager
0x180021341  call    cs:__imp_OpenServiceW
0x180021347  mov     rsi, rax
0x18002134a  test    rax, rax
0x18002134d  jz      loc_180021488
0x180021353  lea     rax, [rbp+ServicesReturned]
0x180021357  mov     [rbp+cbBufSize], 0
0x18002135e  mov     [rsp+70h+lpServicesReturned], rax; lpServicesReturned
0x180021363  xor     r9d, r9d; cbBufSize
0x180021366  lea     rax, [rbp+cbBufSize]
0x18002136a  mov     [rbp+ServicesReturned], 0
0x180021371  xor     r8d, r8d; lpServices
0x180021374  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180021379  mov     edx, r13d; dwServiceState
0x18002137c  mov     rcx, rsi; hService
0x18002137f  call    cs:__imp_EnumDependentServicesW
0x180021385  test    eax, eax
0x180021387  jnz     loc_180021464
0x18002138d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180021392  mov     ebx, eax
0x180021394  cmp     eax, 800700EAh
0x180021399  jnz     loc_180021460
0x18002139f  mov     ecx, [rbp+cbBufSize]; cb
0x1800213a2  call    cs:__imp_CoTaskMemAlloc
0x1800213a8  mov     rdi, rax
0x1800213ab  test    rax, rax
0x1800213ae  jz      loc_18002147F
0x1800213b4  xor     ebx, ebx
0x1800213b6  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x1800213ba  mov     ecx, r13d; dwMemContext
0x1800213bd  mov     [rbp+ppMalloc], rbx
0x1800213c1  call    cs:__imp_CoGetMalloc
0x1800213c7  test    eax, eax
0x1800213c9  js      short loc_1800213F1
0x1800213cb  mov     rcx, [rbp+ppMalloc]
0x1800213cf  mov     rdx, [rcx]
0x1800213d2  mov     rax, [rdx+30h]
0x1800213d6  mov     rdx, rdi
0x1800213d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213de  mov     rcx, [rbp+ppMalloc]
0x1800213e2  mov     rbx, rax
0x1800213e5  mov     rdx, [rcx]
0x1800213e8  mov     rax, [rdx+10h]
0x1800213ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213f1  mov     r8, rbx; Size
0x1800213f4  xor     edx, edx; Val
0x1800213f6  mov     rcx, rdi; void *
0x1800213f9  call    memset_0
0x1800213fe  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x180021402  lea     rax, [rbp+ServicesReturned]
0x180021406  mov     [rsp+70h+lpServicesReturned], rax; lpServicesReturned
0x18002140b  mov     r8, rdi; lpServices
0x18002140e  lea     rax, [rbp+cbBufSize]
0x180021412  mov     edx, r13d; dwServiceState
0x180021415  mov     rcx, rsi; hService
0x180021418  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18002141d  call    cs:__imp_EnumDependentServicesW
0x180021423  test    eax, eax
0x180021425  jz      short loc_180021450
0x180021427  xor     r15d, r15d
0x18002142a  xor     ebx, ebx
0x18002142c  cmp     r15d, [rbp+ServicesReturned]
0x180021430  jnb     short loc_180021457
0x180021432  lea     rdx, [r15+r15*2]
0x180021436  mov     rcx, r14; this
0x180021439  add     rdx, rdx
0x18002143c  mov     rdx, [rdi+rdx*8]; struct SC_HANDLE__ *
0x180021440  call    ?_StopServiceAndWait@GSM@@YAJPEAUSC_HANDLE__@@PEBG@Z; GSM::_StopServiceAndWait(SC_HANDLE__ *,ushort const *)
0x180021445  add     r15d, r13d
0x180021448  mov     ebx, eax
0x18002144a  test    eax, eax
0x18002144c  jns     short loc_18002142C
0x18002144e  jmp     short loc_180021457
0x180021450  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180021455  mov     ebx, eax
0x180021457  mov     rcx, rdi; pv
0x18002145a  call    cs:__imp_CoTaskMemFree
0x180021460  test    ebx, ebx
0x180021462  js      short loc_18002147F
0x180021464  xorps   xmm0, xmm0
0x180021467  lea     r8, [rbp+ServiceStatus]; lpServiceStatus
0x18002146b  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x18002146f  mov     edx, r13d; dwControl
0x180021472  mov     rcx, rsi; hService
0x180021475  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x180021479  call    cs:__imp_ControlService
0x18002147f  mov     rcx, rsi; hSCObject
0x180021482  call    cs:__imp_CloseServiceHandle
0x180021488  mov     rcx, r14; hSCObject
0x18002148b  call    cs:__imp_CloseServiceHandle
0x180021491  mov     rcx, [rbp+var_10]
0x180021495  xor     rcx, rsp; StackCookie
0x180021498  call    __security_check_cookie
0x18002149d  add     rsp, 70h
0x1800214a1  pop     r15
0x1800214a3  pop     r14
0x1800214a5  pop     r13
0x1800214a7  pop     rdi
0x1800214a8  pop     rsi
0x1800214a9  pop     rbx
0x1800214aa  pop     rbp
0x1800214ab  retn
```
