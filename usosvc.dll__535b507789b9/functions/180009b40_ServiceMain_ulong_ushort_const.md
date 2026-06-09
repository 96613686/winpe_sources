# ServiceMain(ulong,ushort * * const)

- ea: `0x180009b40`
- end: `0x180009be2`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `162`
- prototype: `void __fastcall(unsigned int, LPCWSTR *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009b40`
- `0x18000f010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180009b66`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180009b66`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009bbe`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009bbe`

## pseudocode

```c
void __fastcall ServiceMain(unsigned int a1, LPCWSTR *a2)
{
  if ( g_UsoSvcImplModule
    || (g_SvcStatusHandle = RegisterServiceCtrlHandlerExW(*a2, _scrt_stub_for_is_c_termination_complete, 0)) == 0 )
  {
    ((void (__fastcall *)(_QWORD, LPCWSTR *))g_ServiceMain)(a1, a2);
  }
  else
  {
    g_SvcStatus.dwCurrentState = 1;
    g_SvcStatus.dwControlsAccepted = 1;
    g_SvcStatus.dwServiceType = 32;
    g_SvcStatus.dwWin32ExitCode = 1066;
    g_SvcStatus.dwServiceSpecificExitCode = g_ExitCode;
    *(_QWORD *)&g_SvcStatus.dwCheckPoint = 0;
    SetServiceStatus(g_SvcStatusHandle, &g_SvcStatus);
  }
}

```

## disassembly

```asm
0x180009b40  mov     [rsp+arg_0], rbx
0x180009b45  push    rdi
0x180009b46  sub     rsp, 20h
0x180009b4a  cmp     cs:?g_UsoSvcImplModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> g_UsoSvcImplModule
0x180009b52  mov     rbx, rdx
0x180009b55  mov     edi, ecx
0x180009b57  jnz     short loc_180009BC6
0x180009b59  mov     rcx, [rbx]; lpServiceName
0x180009b5c  lea     rdx, __scrt_stub_for_is_c_termination_complete; lpHandlerProc
0x180009b63  xor     r8d, r8d; lpContext
0x180009b66  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180009b6c  mov     cs:?g_SvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_SvcStatusHandle
0x180009b73  mov     rcx, rax; hServiceStatus
0x180009b76  test    rax, rax
0x180009b79  jz      short loc_180009BC6
0x180009b7b  mov     eax, cs:?g_ExitCode@@3KA; ulong g_ExitCode
0x180009b81  mov     edx, 1
0x180009b86  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, edx; _SERVICE_STATUS g_SvcStatus ...
0x180009b8c  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, edx; _SERVICE_STATUS g_SvcStatus ...
0x180009b92  lea     rdx, ?g_SvcStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180009b99  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_SvcStatus ...
0x180009ba3  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 42Ah; _SERVICE_STATUS g_SvcStatus ...
0x180009bad  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, eax; _SERVICE_STATUS g_SvcStatus ...
0x180009bb3  mov     qword ptr cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_SvcStatus ...
0x180009bbe  call    cs:__imp_SetServiceStatus
0x180009bc4  jmp     short loc_180009BD7
0x180009bc6  mov     rax, cs:?g_ServiceMain@@3P6AXKPEAPEAG@ZEA; void (*g_ServiceMain)(ulong,ushort * *)
0x180009bcd  mov     rdx, rbx
0x180009bd0  mov     ecx, edi
0x180009bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bd7  mov     rbx, [rsp+28h+arg_0]
0x180009bdc  add     rsp, 20h
0x180009be0  pop     rdi
0x180009be1  retn
```
