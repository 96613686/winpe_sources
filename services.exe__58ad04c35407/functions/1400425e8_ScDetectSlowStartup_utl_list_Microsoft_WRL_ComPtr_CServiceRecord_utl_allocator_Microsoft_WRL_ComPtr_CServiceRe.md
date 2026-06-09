# ScDetectSlowStartup(utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>> &)

- ea: `0x1400425e8`
- end: `0x1400427ba`
- name: `?ScDetectSlowStartup@@YAXAEAV?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@@Z`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140037084`

## callees

- `0x140004c58`
- `0x14001c738`
- `0x14001f99c`
- `0x1400425e8`
- `0x1400575b0`
- `0x14006fb40`
- `0x140070094`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004269d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14004269d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004266c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004266c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400426b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400426b7`
- `ntdll!RtlGetNtProductType` at `0x1400426d5`
- `ntdll!RtlGetNtProductType` at `0x1400426d5`

## string_xrefs

- `0x140042691`: `DisableServiceStartupMonitor`

## pseudocode

```c
void __fastcall ScDetectSlowStartup(_QWORD *a1)
{
  unsigned int v2; // eax
  DWORD v3; // eax
  _QWORD *i; // rbx
  CServiceRecord *v5; // rdi
  __int64 v6; // rcx
  DWORD Type; // [rsp+30h] [rbp-40h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+34h] [rbp-3Ch] BYREF
  DWORD cbData; // [rsp+38h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  _DWORD v11[8]; // [rsp+48h] [rbp-28h] BYREF

  ProductType = 0;
  if ( *(_DWORD *)&g_eSlowStartupMonitoringStatus == 1 )
    return;
  if ( *(_DWORD *)&g_eSlowStartupMonitoringStatus != 3 )
    goto LABEL_14;
  hKey = 0;
  Type = 0;
  cbData = 4;
  *(_DWORD *)&g_eSlowStartupMonitoringStatus = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control", 0, 0x20019u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"DisableServiceStartupMonitor", 0, &Type, &g_eSlowStartupMonitoringStatus, &cbData)
      && Type != 4 )
    {
      *(_DWORD *)&g_eSlowStartupMonitoringStatus = 0;
    }
    RegCloseKey(hKey);
  }
  if ( *(_DWORD *)&g_eSlowStartupMonitoringStatus != 1 )
  {
    *(_DWORD *)&g_eSlowStartupMonitoringStatus = 2;
    RtlGetNtProductType(&ProductType);
    v2 = 960000;
    if ( ProductType == NtProductWinNt )
      v2 = 240000;
    v3 = v2 / g_ServiceStartTimeout;
    g_usSlowStartupWarningLogEventThreshold = v3;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 10, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids, v3);
LABEL_14:
    for ( i = (_QWORD *)*a1; i != a1; i = (_QWORD *)*i )
    {
      v5 = (CServiceRecord *)i[2];
      if ( CServiceRecord::GetStartState(v5) == 2 )
      {
        memset(v11, 0, 28);
        if ( !(unsigned int)ScQueryServiceStatus(v6, v11, 0, 0) && v11[1] == 2 )
          CServiceRecord::LogSlowStartupEventIfApplicable(v5);
      }
    }
    return;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->StubInfo, 11, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids);
}

```

## disassembly

```asm
0x1400425e8  push    rbp
0x1400425ea  push    rbx
0x1400425eb  push    rsi
0x1400425ec  push    rdi
0x1400425ed  push    r15
0x1400425ef  mov     rbp, rsp
0x1400425f2  sub     rsp, 70h
0x1400425f6  mov     rax, cs:__security_cookie
0x1400425fd  xor     rax, rsp
0x140042600  mov     [rbp+var_8], rax
0x140042604  mov     eax, cs:?g_eSlowStartupMonitoringStatus@@3W4SERVICE_SLOW_STARTUP_MONITORING@@A; SERVICE_SLOW_STARTUP_MONITORING g_eSlowStartupMonitoringStatus
0x14004260a  mov     rsi, rcx
0x14004260d  mov     [rbp+ProductType], 0
0x140042614  cmp     eax, 1
0x140042617  jz      loc_1400427A3
0x14004261d  mov     r15d, 2
0x140042623  cmp     eax, 3
0x140042626  jnz     loc_14004272A
0x14004262c  lea     rax, [rbp+hKey]
0x140042630  mov     [rbp+hKey], 0
0x140042638  mov     r9d, 20019h; samDesired
0x14004263e  mov     [rsp+70h+phkResult], rax; phkResult
0x140042643  xor     r8d, r8d; ulOptions
0x140042646  mov     [rbp+Type], 0
0x14004264d  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control"
0x140042654  mov     [rbp+cbData], 4
0x14004265b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140042662  mov     cs:?g_eSlowStartupMonitoringStatus@@3W4SERVICE_SLOW_STARTUP_MONITORING@@A, 0; SERVICE_SLOW_STARTUP_MONITORING g_eSlowStartupMonitoringStatus
0x14004266c  call    cs:__imp_RegOpenKeyExW
0x140042672  test    eax, eax
0x140042674  jnz     short loc_1400426BD
0x140042676  mov     rcx, [rbp+hKey]; hKey
0x14004267a  lea     rax, [rbp+cbData]
0x14004267e  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140042683  lea     r9, [rbp+Type]; lpType
0x140042687  lea     rax, ?g_eSlowStartupMonitoringStatus@@3W4SERVICE_SLOW_STARTUP_MONITORING@@A; SERVICE_SLOW_STARTUP_MONITORING g_eSlowStartupMonitoringStatus
0x14004268e  xor     r8d, r8d; lpReserved
0x140042691  lea     rdx, aDisableservice; "DisableServiceStartupMonitor"
0x140042698  mov     [rsp+70h+phkResult], rax; lpData
0x14004269d  call    cs:__imp_RegQueryValueExW
0x1400426a3  test    eax, eax
0x1400426a5  jnz     short loc_1400426B3
0x1400426a7  cmp     [rbp+Type], 4
0x1400426ab  jz      short loc_1400426B3
0x1400426ad  mov     cs:?g_eSlowStartupMonitoringStatus@@3W4SERVICE_SLOW_STARTUP_MONITORING@@A, eax; SERVICE_SLOW_STARTUP_MONITORING g_eSlowStartupMonitoringStatus
0x1400426b3  mov     rcx, [rbp+hKey]; hKey
0x1400426b7  call    cs:__imp_RegCloseKey
0x1400426bd  cmp     cs:?g_eSlowStartupMonitoringStatus@@3W4SERVICE_SLOW_STARTUP_MONITORING@@A, 1; SERVICE_SLOW_STARTUP_MONITORING g_eSlowStartupMonitoringStatus
0x1400426c4  jz      loc_140042775
0x1400426ca  lea     rcx, [rbp+ProductType]; ProductType
0x1400426ce  mov     cs:?g_eSlowStartupMonitoringStatus@@3W4SERVICE_SLOW_STARTUP_MONITORING@@A, r15d; SERVICE_SLOW_STARTUP_MONITORING g_eSlowStartupMonitoringStatus
0x1400426d5  call    cs:__imp_RtlGetNtProductType
0x1400426db  xor     edx, edx
0x1400426dd  mov     eax, 0EA600h
0x1400426e2  cmp     [rbp+ProductType], 1
0x1400426e6  jnz     short loc_1400426ED
0x1400426e8  mov     eax, 3A980h
0x1400426ed  div     cs:?g_ServiceStartTimeout@@3KA; ulong g_ServiceStartTimeout
0x1400426f3  mov     r9d, eax
0x1400426f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400426fd  mov     cs:?g_usSlowStartupWarningLogEventThreshold@@3KA, eax; ulong g_usSlowStartupWarningLogEventThreshold
0x140042703  lea     rax, WPP_GLOBAL_Control
0x14004270a  cmp     rcx, rax
0x14004270d  jz      short loc_14004272A
0x14004270f  test    byte ptr [rcx+1Ch], 4
0x140042713  jz      short loc_14004272A
0x140042715  mov     rcx, [rcx+10h]
0x140042719  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140042720  mov     edx, 0Ah
0x140042725  call    WPP_SF_d
0x14004272a  mov     rbx, [rsi]
0x14004272d  cmp     rbx, rsi
0x140042730  jz      short loc_1400427A3
0x140042732  mov     rdi, [rbx+10h]
0x140042736  mov     rcx, rdi; this
0x140042739  call    ?GetStartState@CServiceRecord@@QEAAGXZ; CServiceRecord::GetStartState(void)
0x14004273e  cmp     ax, r15w
0x140042742  jnz     short loc_140042770
0x140042744  xorps   xmm0, xmm0
0x140042747  lea     rdx, [rbp+var_28]
0x14004274b  movups  xmmword ptr [rbp+var_28], xmm0
0x14004274f  xor     r9d, r9d
0x140042752  xor     r8d, r8d
0x140042755  movups  xmmword ptr [rbp+var_28+0Ch], xmm0
0x140042759  call    ?ScQueryServiceStatus@@YAKPEAVCServiceRecord@@TSTATUS_UNION@@HH@Z; ScQueryServiceStatus(CServiceRecord *,STATUS_UNION,int,int)
0x14004275e  test    eax, eax
0x140042760  jnz     short loc_140042770
0x140042762  cmp     [rbp+var_28+4], r15d
0x140042766  jnz     short loc_140042770
0x140042768  mov     rcx, rdi; this
0x14004276b  call    ?LogSlowStartupEventIfApplicable@CServiceRecord@@QEAAXXZ; CServiceRecord::LogSlowStartupEventIfApplicable(void)
0x140042770  mov     rbx, [rbx]
0x140042773  jmp     short loc_14004272D
0x140042775  mov     rcx, cs:WPP_GLOBAL_Control
0x14004277c  lea     rax, WPP_GLOBAL_Control
0x140042783  cmp     rcx, rax
0x140042786  jz      short loc_1400427A3
0x140042788  test    [rcx+1Ch], r15b
0x14004278c  jz      short loc_1400427A3
0x14004278e  mov     rcx, [rcx+10h]
0x140042792  lea     r8, WPP_21b4c565b436346f75e2b704ea64e4ae_Traceguids
0x140042799  mov     edx, 0Bh
0x14004279e  call    WPP_SF_
0x1400427a3  mov     rcx, [rbp+var_8]
0x1400427a7  xor     rcx, rsp; StackCookie
0x1400427aa  call    __security_check_cookie
0x1400427af  add     rsp, 70h
0x1400427b3  pop     r15
0x1400427b5  pop     rdi
0x1400427b6  pop     rsi
0x1400427b7  pop     rbx
0x1400427b8  pop     rbp
0x1400427b9  retn
```
