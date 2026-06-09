# StartMonitoringNetprofmService(void)

- ea: `0x1800c0768`
- end: `0x1800c08b2`
- name: `?StartMonitoringNetprofmService@@YAKXZ`
- size: `330`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180014fe8`

## callees

- `0x1800085d0`
- `0x180012300`
- `0x180014f1c`
- `0x1800c0768`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c07bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c07e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c07bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c07e8`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800c0825`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800c0825`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800c0871`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800c0871`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c087f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c088d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c087f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800c088d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800c07af`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800c07af`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800c07da`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800c07da`

## string_xrefs

- `0x1800c07fc`: `StartMonitoringNetprofmService`
- `0x1800c0854`: `StartMonitoringNetprofmService`
- `0x1800c07ee`: `OpenService netprofm failed (0x%08X)`
- `0x1800c0843`: `SubscribeServiceChangeNotifications to netprofm service succeeded`
- `0x1800c0833`: `SubscribeServiceChangeNotifications failed (0x%08X)`

## pseudocode

```c
__int64 StartMonitoringNetprofmService(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  SC_HANDLE v2; // rbx
  __int64 LastError; // rdi
  unsigned int v4; // eax
  __int64 v6; // [rsp+30h] [rbp-38h]
  WCHAR ServiceName[12]; // [rsp+38h] [rbp-30h] BYREF

  wcscpy(ServiceName, L"netprofm");
  v6 = 0;
  v0 = OpenSCManagerW(0, 0, 1u);
  v1 = v0;
  if ( v0 )
  {
    v2 = OpenServiceW(v0, ServiceName, 4u);
    if ( v2 )
    {
      v4 = SubscribeServiceChangeNotifications(v2, 2, s_ServiceStatusNotification);
      LODWORD(LastError) = v4;
      if ( v4 )
      {
        WwanLog::Error("StartMonitoringNetprofmService", 0, L"SubscribeServiceChangeNotifications failed (0x%08X)", v4);
      }
      else
      {
        v6 = *(&g_nlaContext + 1);
        *(&g_nlaContext + 1) = 0;
        WwanLog::Info(
          "StartMonitoringNetprofmService",
          0,
          L"SubscribeServiceChangeNotifications to netprofm service succeeded");
      }
    }
    else
    {
      LastError = GetLastError();
      WwanLog::Error("StartMonitoringNetprofmService", 0, L"OpenService netprofm failed (0x%08X)", LastError);
    }
  }
  else
  {
    v2 = 0;
    LODWORD(LastError) = GetLastError();
  }
  if ( v6 )
    UnsubscribeServiceChangeNotifications();
  if ( v2 )
    CloseServiceHandle(v2);
  if ( v1 )
    CloseServiceHandle(v1);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800c0768  mov     [rsp+arg_0], rbx
0x1800c076d  mov     [rsp+arg_8], rsi
0x1800c0772  push    rdi
0x1800c0773  sub     rsp, 60h
0x1800c0777  mov     rax, cs:__security_cookie
0x1800c077e  xor     rax, rsp
0x1800c0781  mov     [rsp+68h+var_18], rax
0x1800c0786  movups  xmm0, xmmword ptr cs:aNetprofm; "netprofm"
0x1800c078d  movzx   eax, word ptr cs:aNetprofm+10h; ""
0x1800c0794  xor     edx, edx; lpDatabaseName
0x1800c0796  xor     ecx, ecx; lpMachineName
0x1800c0798  mov     [rsp+68h+var_20], ax
0x1800c079d  movups  xmmword ptr [rsp+68h+ServiceName], xmm0
0x1800c07a2  mov     [rsp+68h+var_38], 0
0x1800c07ab  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800c07af  call    cs:__imp_OpenSCManagerW
0x1800c07b5  mov     rsi, rax
0x1800c07b8  test    rax, rax
0x1800c07bb  jnz     short loc_1800C07CC
0x1800c07bd  xor     ebx, ebx
0x1800c07bf  call    cs:__imp_GetLastError
0x1800c07c5  mov     edi, eax
0x1800c07c7  jmp     loc_1800C0867
0x1800c07cc  mov     r8d, 4; dwDesiredAccess
0x1800c07d2  lea     rdx, [rsp+68h+ServiceName]; lpServiceName
0x1800c07d7  mov     rcx, rsi; hSCManager
0x1800c07da  call    cs:__imp_OpenServiceW
0x1800c07e0  mov     rbx, rax
0x1800c07e3  test    rax, rax
0x1800c07e6  jnz     short loc_1800C080A
0x1800c07e8  call    cs:__imp_GetLastError
0x1800c07ee  lea     r8, aOpenserviceNet; "OpenService netprofm failed (0x%08X)"
0x1800c07f5  xor     edx, edx; struct _GUID *
0x1800c07f7  mov     edi, eax
0x1800c07f9  mov     r9d, eax
0x1800c07fc  lea     rcx, aStartmonitorin; "StartMonitoringNetprofmService"
0x1800c0803  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800c0808  jmp     short loc_1800C0867
0x1800c080a  xor     r9d, r9d
0x1800c080d  lea     rax, [rsp+68h+var_38]
0x1800c0812  lea     r8, s_ServiceStatusNotification
0x1800c0819  mov     [rsp+68h+var_48], rax
0x1800c081e  mov     rcx, rbx
0x1800c0821  lea     edx, [r9+2]
0x1800c0825  call    cs:__imp_SubscribeServiceChangeNotifications
0x1800c082b  xor     edx, edx; struct _GUID *
0x1800c082d  mov     edi, eax
0x1800c082f  test    eax, eax
0x1800c0831  jz      short loc_1800C083C
0x1800c0833  lea     r8, aSubscribeservi_0; "SubscribeServiceChangeNotifications fai"...
0x1800c083a  jmp     short loc_1800C07F9
0x1800c083c  mov     rcx, qword ptr cs:?g_nlaContext@@3UWWAN_NLA_PLUGIN_CTXT_BLOCK@@A+8; WWAN_NLA_PLUGIN_CTXT_BLOCK g_nlaContext
0x1800c0843  lea     r8, aSubscribeservi; "SubscribeServiceChangeNotifications to "...
0x1800c084a  mov     rax, [rsp+68h+var_38]
0x1800c084f  mov     [rsp+68h+var_38], rcx
0x1800c0854  lea     rcx, aStartmonitorin; "StartMonitoringNetprofmService"
0x1800c085b  mov     qword ptr cs:?g_nlaContext@@3UWWAN_NLA_PLUGIN_CTXT_BLOCK@@A+8, rax; WWAN_NLA_PLUGIN_CTXT_BLOCK g_nlaContext
0x1800c0862  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800c0867  mov     rcx, [rsp+68h+var_38]
0x1800c086c  test    rcx, rcx
0x1800c086f  jz      short loc_1800C0877
0x1800c0871  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x1800c0877  test    rbx, rbx
0x1800c087a  jz      short loc_1800C0885
0x1800c087c  mov     rcx, rbx; hSCObject
0x1800c087f  call    cs:__imp_CloseServiceHandle
0x1800c0885  test    rsi, rsi
0x1800c0888  jz      short loc_1800C0893
0x1800c088a  mov     rcx, rsi; hSCObject
0x1800c088d  call    cs:__imp_CloseServiceHandle
0x1800c0893  mov     eax, edi
0x1800c0895  mov     rcx, [rsp+68h+var_18]
0x1800c089a  xor     rcx, rsp; StackCookie
0x1800c089d  call    __security_check_cookie
0x1800c08a2  mov     rbx, [rsp+68h+arg_0]
0x1800c08a7  mov     rsi, [rsp+68h+arg_8]
0x1800c08ac  add     rsp, 60h
0x1800c08b0  pop     rdi
0x1800c08b1  retn
```
