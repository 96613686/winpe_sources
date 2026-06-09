# IsServicingInProgress(void)

- ea: `0x180034588`
- end: `0x18003486e`
- name: `?IsServicingInProgress@@YA_NXZ`
- size: `742`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800349a8`

## callees

- `0x1800119a8`
- `0x18001b064`
- `0x180034588`
- `0x18006ea28`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034786`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034786`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034778`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800347d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003480d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034778`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800347d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003480d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800347e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003481b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800347e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003481b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003475c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003475c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003471e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003471e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800346f4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800346f4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800347ef`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800347fe`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003482a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180034839`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800347ef`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800347fe`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003482a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180034839`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003474e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800347a5`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18003474e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800347a5`

## string_xrefs

- `0x1800346eb`: `ServicesActive`
- `0x180034714`: `TrustedInstaller`
- `0x1800347b5`: `TrustedInstaller is set to auto start`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char IsServicingInProgress(void)
{
  __int64 *System; // rax
  __int64 v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rax
  int SystemValueOrDefault; // edi
  volatile signed __int32 *v5; // rbx
  volatile signed __int32 *v6; // rbx
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rdi
  bool v9; // r15
  SC_HANDLE v10; // rax
  SC_HANDLE v11; // rbx
  bool v12; // r12
  DWORD v13; // r14d
  HANDLE ProcessHeap; // rax
  struct _QUERY_SERVICE_CONFIGW *v15; // rax
  struct _QUERY_SERVICE_CONFIGW *v16; // rsi
  HANDLE v17; // rax
  HANDLE v19; // rax
  __int128 v20; // [rsp+48h] [rbp-29h] BYREF
  __int128 v21; // [rsp+58h] [rbp-19h] BYREF
  _QWORD v22[2]; // [rsp+68h] [rbp-9h] BYREF
  SC_HANDLE v23; // [rsp+78h] [rbp+7h] BYREF
  volatile signed __int32 *v24; // [rsp+80h] [rbp+Fh]
  __int64 v25; // [rsp+88h] [rbp+17h] BYREF
  volatile signed __int32 *v26; // [rsp+90h] [rbp+1Fh]
  DWORD pcbBytesNeeded; // [rsp+98h] [rbp+27h] BYREF

  System = SystemInterface::Service::GetSystem(&v25);
  v1 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, SC_HANDLE *))(*(_QWORD *)*System + 32LL))(*System, &v23);
  pcbBytesNeeded = 0;
  v2 = -1;
  do
    ++v2;
  while ( SystemInterface::Registry::SERVICING_IN_PROGRESS[v2] );
  v3 = -1;
  do
    ++v3;
  while ( SystemInterface::Registry::CBSINTERFACE_REDIRECTION_ID[v3] );
  *(_QWORD *)&v20 = SystemInterface::Registry::SERVICING_IN_PROGRESS;
  *((_QWORD *)&v20 + 1) = v2;
  v21 = 0;
  v22[0] = SystemInterface::Registry::CBSINTERFACE_REDIRECTION_ID;
  v22[1] = v3;
  SystemValueOrDefault = SystemInterface::Registry::GetSystemValueOrDefault(
                           v1,
                           (unsigned int)v22,
                           (unsigned int)&v21,
                           (unsigned int)&v20,
                           (__int64)&pcbBytesNeeded);
  v5 = v24;
  if ( v24 )
  {
    if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( !_InterlockedDecrement(v5 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  v6 = v26;
  if ( v26 )
  {
    if ( !_InterlockedDecrement(v26 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( !_InterlockedDecrement(v6 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  if ( SystemValueOrDefault != 2 )
    return 0;
  *(_QWORD *)&v20 = L"CBS servicing operation in progress";
  *((_QWORD *)&v20 + 1) = 35;
  SystemInterface::Log<>(&v20);
  v7 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v8 = v7;
  v23 = v7;
  v9 = v7 != 0;
  if ( !v7 )
  {
LABEL_31:
    if ( v9 )
      CloseServiceHandle(v8);
    return 0;
  }
  v10 = OpenServiceW(v7, L"TrustedInstaller", 1u);
  v11 = v10;
  v22[0] = v10;
  v12 = v10 != 0;
  if ( !v10
    || (pcbBytesNeeded = 0, QueryServiceConfigW(v10, 0, 0, &pcbBytesNeeded))
    || GetLastError() != 122
    || (v13 = pcbBytesNeeded) == 0 )
  {
LABEL_29:
    if ( v12 )
      CloseServiceHandle(v11);
    goto LABEL_31;
  }
  ProcessHeap = GetProcessHeap();
  v15 = (struct _QUERY_SERVICE_CONFIGW *)HeapAlloc(ProcessHeap, 0, v13);
  v16 = v15;
  *(_QWORD *)&v20 = v15;
  if ( !v15 || !QueryServiceConfigW(v11, v15, v13, &pcbBytesNeeded) || v16->dwStartType != 2 )
  {
    if ( v16 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v16);
    }
    goto LABEL_29;
  }
  *(_QWORD *)&v21 = L"TrustedInstaller is set to auto start";
  *((_QWORD *)&v21 + 1) = 37;
  SystemInterface::Log<>(&v21);
  v17 = GetProcessHeap();
  HeapFree(v17, 0, v16);
  if ( v12 )
    CloseServiceHandle(v11);
  if ( v9 )
    CloseServiceHandle(v8);
  return 1;
}

```

## disassembly

```asm
0x180034588  mov     rax, rsp
0x18003458b  mov     [rax+8], rbx
0x18003458f  mov     [rax+10h], rsi
0x180034593  mov     [rax+18h], rdi
0x180034597  push    rbp
0x180034598  push    r12
0x18003459a  push    r13
0x18003459c  push    r14
0x18003459e  push    r15
0x1800345a0  lea     rbp, [rax-5Fh]
0x1800345a4  sub     rsp, 0A0h
0x1800345ab  mov     rax, cs:__security_cookie
0x1800345b2  xor     rax, rsp
0x1800345b5  mov     [rbp+57h+var_28], rax
0x1800345b9  lea     rcx, [rbp+57h+var_40]
0x1800345bd  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800345c2  nop
0x1800345c3  mov     rcx, [rax]
0x1800345c6  mov     rax, [rcx]
0x1800345c9  lea     rdx, [rbp+57h+var_50]
0x1800345cd  mov     rax, [rax+20h]
0x1800345d1  call    _guard_dispatch_icall
0x1800345d6  nop
0x1800345d7  mov     rcx, [rax]
0x1800345da  xor     esi, esi
0x1800345dc  mov     [rbp+57h+pcbBytesNeeded], esi
0x1800345df  mov     r9, cs:?SERVICING_IN_PROGRESS@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::SERVICING_IN_PROGRESS
0x1800345e6  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800345ea  mov     rdx, r14
0x1800345ed  inc     rdx
0x1800345f0  cmp     [r9+rdx*2], si
0x1800345f5  jnz     short loc_1800345ED
0x1800345f7  mov     r8, cs:?CBSINTERFACE_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::CBSINTERFACE_REDIRECTION_ID
0x1800345fe  mov     rax, r14
0x180034601  inc     rax
0x180034604  cmp     [r8+rax*2], si
0x180034609  jnz     short loc_180034601
0x18003460b  mov     [rbp+57h+var_80], r9
0x18003460f  mov     [rbp+57h+var_78], rdx
0x180034613  xorps   xmm0, xmm0
0x180034616  movdqa  [rbp+57h+var_70], xmm0
0x18003461b  mov     [rbp+57h+var_60], r8
0x18003461f  mov     [rbp+57h+var_58], rax
0x180034623  lea     rax, [rbp+57h+pcbBytesNeeded]
0x180034627  mov     [rsp+0C0h+var_A0], rax
0x18003462c  lea     r9, [rbp+57h+var_80]
0x180034630  lea     r8, [rbp+57h+var_70]
0x180034634  lea     rdx, [rbp+57h+var_60]
0x180034638  call    ?GetSystemValueOrDefault@Registry@SystemInterface@@QEAAIV?$basic_zstring_view@_W@wil@@00AEBI@Z; SystemInterface::Registry::GetSystemValueOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,uint const &)
0x18003463d  mov     edi, eax
0x18003463f  mov     rbx, [rbp+57h+var_48]
0x180034643  test    rbx, rbx
0x180034646  jz      short loc_180034680
0x180034648  mov     ecx, r14d
0x18003464b  lock xadd [rbx+8], ecx
0x180034650  add     ecx, r14d
0x180034653  jnz     short loc_180034680
0x180034655  mov     rdx, [rbx]
0x180034658  mov     rcx, rbx
0x18003465b  mov     rax, [rdx]
0x18003465e  call    _guard_dispatch_icall
0x180034663  mov     eax, r14d
0x180034666  lock xadd [rbx+0Ch], eax
0x18003466b  add     eax, r14d
0x18003466e  jnz     short loc_180034680
0x180034670  mov     rax, [rbx]
0x180034673  mov     rcx, rbx
0x180034676  mov     rax, [rax+8]
0x18003467a  call    _guard_dispatch_icall
0x18003467f  nop
0x180034680  mov     rbx, [rbp+57h+var_38]
0x180034684  test    rbx, rbx
0x180034687  jz      short loc_1800346C0
0x180034689  mov     eax, r14d
0x18003468c  lock xadd [rbx+8], eax
0x180034691  add     eax, r14d
0x180034694  jnz     short loc_1800346C0
0x180034696  mov     rax, [rbx]
0x180034699  mov     rcx, rbx
0x18003469c  mov     rax, [rax]
0x18003469f  call    _guard_dispatch_icall
0x1800346a4  mov     eax, r14d
0x1800346a7  lock xadd [rbx+0Ch], eax
0x1800346ac  add     eax, r14d
0x1800346af  jnz     short loc_1800346C0
0x1800346b1  mov     rax, [rbx]
0x1800346b4  mov     rcx, rbx
0x1800346b7  mov     rax, [rax+8]
0x1800346bb  call    _guard_dispatch_icall
0x1800346c0  cmp     edi, 2
0x1800346c3  jnz     loc_18003483F
0x1800346c9  lea     rax, aCbsServicingOp; "CBS servicing operation in progress"
0x1800346d0  mov     [rbp+57h+var_80], rax
0x1800346d4  mov     [rbp+57h+var_78], 23h ; '#'
0x1800346dc  lea     rcx, [rbp+57h+var_80]
0x1800346e0  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1800346e5  lea     ebx, [rdi-1]
0x1800346e8  mov     r8d, ebx; dwDesiredAccess
0x1800346eb  lea     rdx, DatabaseName; "ServicesActive"
0x1800346f2  xor     ecx, ecx; lpMachineName
0x1800346f4  call    cs:__imp_OpenSCManagerW
0x1800346fa  mov     rdi, rax
0x1800346fd  mov     [rbp+57h+var_50], rax
0x180034701  test    rax, rax
0x180034704  setnz   r15b
0x180034708  test    rax, rax
0x18003470b  jz      loc_180034831
0x180034711  mov     r8d, ebx; dwDesiredAccess
0x180034714  lea     rdx, ServiceName; "TrustedInstaller"
0x18003471b  mov     rcx, rax; hSCManager
0x18003471e  call    cs:__imp_OpenServiceW
0x180034724  mov     rbx, rax
0x180034727  mov     [rbp+57h+var_60], rax
0x18003472b  test    rax, rax
0x18003472e  setnz   r12b
0x180034732  mov     [rbp+57h+var_90], r12b
0x180034736  test    rax, rax
0x180034739  jz      loc_180034822
0x18003473f  mov     [rbp+57h+pcbBytesNeeded], esi
0x180034742  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x180034746  xor     r8d, r8d; cbBufSize
0x180034749  xor     edx, edx; lpServiceConfig
0x18003474b  mov     rcx, rax; hService
0x18003474e  call    cs:__imp_QueryServiceConfigW
0x180034754  test    eax, eax
0x180034756  jnz     loc_180034822
0x18003475c  call    cs:__imp_GetLastError
0x180034762  cmp     eax, 7Ah ; 'z'
0x180034765  jnz     loc_180034822
0x18003476b  mov     r14d, [rbp+57h+pcbBytesNeeded]
0x18003476f  test    r14d, r14d
0x180034772  jz      loc_180034822
0x180034778  call    cs:__imp_GetProcessHeap
0x18003477e  mov     rcx, rax; hHeap
0x180034781  mov     r8d, r14d; dwBytes
0x180034784  xor     edx, edx; dwFlags
0x180034786  call    cs:__imp_HeapAlloc
0x18003478c  mov     rsi, rax
0x18003478f  mov     [rbp+57h+var_80], rax
0x180034793  test    rax, rax
0x180034796  jz      short loc_180034808
0x180034798  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x18003479c  mov     r8d, r14d; cbBufSize
0x18003479f  mov     rdx, rax; lpServiceConfig
0x1800347a2  mov     rcx, rbx; hService
0x1800347a5  call    cs:__imp_QueryServiceConfigW
0x1800347ab  test    eax, eax
0x1800347ad  jz      short loc_180034808
0x1800347af  cmp     dword ptr [rsi+4], 2
0x1800347b3  jnz     short loc_180034808
0x1800347b5  lea     rax, aTrustedinstall_0; "TrustedInstaller is set to auto start"
0x1800347bc  mov     qword ptr [rbp+57h+var_70], rax
0x1800347c0  mov     qword ptr [rbp+57h+var_70+8], 25h ; '%'
0x1800347c8  lea     rcx, [rbp+57h+var_70]
0x1800347cc  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1800347d1  nop
0x1800347d2  call    cs:__imp_GetProcessHeap
0x1800347d8  mov     rcx, rax; hHeap
0x1800347db  mov     r8, rsi; lpMem
0x1800347de  xor     edx, edx; dwFlags
0x1800347e0  call    cs:__imp_HeapFree
0x1800347e6  nop
0x1800347e7  test    r12b, r12b
0x1800347ea  jz      short loc_1800347F6
0x1800347ec  mov     rcx, rbx; hSCObject
0x1800347ef  call    cs:__imp_CloseServiceHandle
0x1800347f5  nop
0x1800347f6  test    r15b, r15b
0x1800347f9  jz      short loc_180034804
0x1800347fb  mov     rcx, rdi; hSCObject
0x1800347fe  call    cs:__imp_CloseServiceHandle
0x180034804  mov     al, 1
0x180034806  jmp     short loc_180034841
0x180034808  test    rsi, rsi
0x18003480b  jz      short loc_180034822
0x18003480d  call    cs:__imp_GetProcessHeap
0x180034813  mov     rcx, rax; hHeap
0x180034816  mov     r8, rsi; lpMem
0x180034819  xor     edx, edx; dwFlags
0x18003481b  call    cs:__imp_HeapFree
0x180034821  nop
0x180034822  test    r12b, r12b
0x180034825  jz      short loc_180034831
0x180034827  mov     rcx, rbx; hSCObject
0x18003482a  call    cs:__imp_CloseServiceHandle
0x180034830  nop
0x180034831  test    r15b, r15b
0x180034834  jz      short loc_18003483F
0x180034836  mov     rcx, rdi; hSCObject
0x180034839  call    cs:__imp_CloseServiceHandle
0x18003483f  xor     al, al
0x180034841  mov     rcx, [rbp+57h+var_28]
0x180034845  xor     rcx, rsp; StackCookie
0x180034848  call    __security_check_cookie
0x18003484d  lea     r11, [rsp+0C0h+var_20]
0x180034855  mov     rbx, [r11+30h]
0x180034859  mov     rsi, [r11+38h]
0x18003485d  mov     rdi, [r11+40h]
0x180034861  mov     rsp, r11
0x180034864  pop     r15
0x180034866  pop     r14
0x180034868  pop     r13
0x18003486a  pop     r12
0x18003486c  pop     rbp
0x18003486d  retn
```
