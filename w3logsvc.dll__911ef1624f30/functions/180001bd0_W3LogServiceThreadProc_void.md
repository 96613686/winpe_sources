# W3LogServiceThreadProc(void *)

- ea: `0x180001bd0`
- end: `0x180001daa`
- name: `?W3LogServiceThreadProc@@YAKPEAX@Z`
- size: `474`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180001bd0`
- `0x18000aa54`
- `0x18000b324`
- `0x18000bc64`
- `0x18000e9a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001d35`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001d35`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180001d8a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180001d8a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180001bef`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180001bef`
- `iisutil!PuDbgPrintError` at `0x180001c67`
- `iisutil!PuDbgPrintError` at `0x180001c67`

## string_xrefs

- `0x180001c59`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\main.cpp`
- `0x180001c52`: `W3LogServiceThreadProc`

## pseudocode

```c
__int64 __fastcall W3LogServiceThreadProc(PVOID Parameter)
{
  int v1; // edi
  LOG_SVC_ADMIN *v2; // rax
  LOG_SVC_ADMIN *v3; // rcx
  signed int v4; // eax
  LOG_SVC_ADMIN *v5; // rcx
  PVOID v6; // rcx
  SERVICE_STATUS_HANDLE v7; // rbx
  LOG_SVC_ADMIN *v9; // [rsp+30h] [rbp-38h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-30h] BYREF

  v1 = 0;
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    v1 = 1;
    v2 = (LOG_SVC_ADMIN *)operator new(0x850u);
    v9 = v2;
    if ( v2 )
      v2 = LOG_SVC_ADMIN::LOG_SVC_ADMIN(v2);
    g_pLogSvcAdmin = v2;
    if ( v2 )
    {
      v4 = LOG_SVC_ADMIN::Initialize(v3);
      if ( v4 >= 0 )
      {
        LOG_SVC_ADMIN::ExecuteService(v5);
        v6 = g_pLogSvcAdmin;
        if ( g_RegisterServiceCalled )
        {
          v7 = (SERVICE_STATUS_HANDLE)*((_QWORD *)g_pLogSvcAdmin + 257);
          ServiceStatus = *(struct _SERVICE_STATUS *)((char *)g_pLogSvcAdmin + 2064);
          *((_QWORD *)g_pLogSvcAdmin + 257) = 0;
          (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)v6 + 24LL))(v6, 1);
          g_pLogSvcAdmin = 0;
          SetServiceStatus(v7, &ServiceStatus);
        }
        else
        {
          if ( g_pLogSvcAdmin )
            (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)g_pLogSvcAdmin + 24LL))(g_pLogSvcAdmin, 1);
          g_pLogSvcAdmin = 0;
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\main.cpp",
          206,
          "W3LogServiceThreadProc",
          v4,
          "Initialize LOG_SVC_ADMIN failed\n",
          v9);
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\main.cpp",
        194,
        "W3LogServiceThreadProc",
        -2147024882,
        "Allocating LOG_SVC_ADMIN failed\n",
        v9);
    }
  }
  if ( g_pLogSvcAdmin )
  {
    (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)g_pLogSvcAdmin + 24LL))(g_pLogSvcAdmin, 1);
    g_pLogSvcAdmin = 0;
  }
  if ( v1 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180001bd0  mov     [rsp+arg_0], rbx
0x180001bd5  push    rdi
0x180001bd6  sub     rsp, 60h
0x180001bda  mov     rax, cs:__security_cookie
0x180001be1  xor     rax, rsp
0x180001be4  mov     [rsp+68h+var_10], rax
0x180001be9  xor     edi, edi
0x180001beb  xor     edx, edx; dwCoInit
0x180001bed  xor     ecx, ecx; pvReserved
0x180001bef  call    cs:__imp_CoInitializeEx
0x180001bf5  test    eax, eax
0x180001bf7  js      loc_180001D5E
0x180001bfd  mov     edi, 1
0x180001c02  mov     ecx, 850h; Size
0x180001c07  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c0c  mov     [rsp+68h+var_38], rax
0x180001c11  test    rax, rax
0x180001c14  jz      short loc_180001C1F
0x180001c16  mov     rcx, rax; this
0x180001c19  call    ??0LOG_SVC_ADMIN@@QEAA@XZ; LOG_SVC_ADMIN::LOG_SVC_ADMIN(void)
0x180001c1e  nop
0x180001c1f  mov     cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA, rax; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x180001c26  test    rax, rax
0x180001c29  jnz     short loc_180001C72
0x180001c2b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180001c32  jz      loc_180001D5E
0x180001c38  lea     rax, aAllocatingLogS; "Allocating LOG_SVC_ADMIN failed\n"
0x180001c3f  mov     [rsp+68h+var_40], rax
0x180001c44  mov     [rsp+68h+var_48], 8007000Eh
0x180001c4c  mov     r8d, 0C2h
0x180001c52  lea     r9, aW3logserviceth_0; "W3LogServiceThreadProc"
0x180001c59  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180001c60  mov     rcx, cs:g_pDebug
0x180001c67  call    cs:__imp_PuDbgPrintError
0x180001c6d  jmp     loc_180001D5E
0x180001c72  call    ?Initialize@LOG_SVC_ADMIN@@QEAAJXZ; LOG_SVC_ADMIN::Initialize(void)
0x180001c77  test    eax, eax
0x180001c79  jns     short loc_180001CA0
0x180001c7b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180001c82  jz      loc_180001D5E
0x180001c88  lea     rcx, aInitializeLogS; "Initialize LOG_SVC_ADMIN failed\n"
0x180001c8f  mov     [rsp+68h+var_40], rcx
0x180001c94  mov     [rsp+68h+var_48], eax
0x180001c98  mov     r8d, 0CEh
0x180001c9e  jmp     short loc_180001C52
0x180001ca0  call    ?ExecuteService@LOG_SVC_ADMIN@@QEAAXXZ; LOG_SVC_ADMIN::ExecuteService(void)
0x180001ca5  mov     rcx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x180001cac  cmp     cs:?g_RegisterServiceCalled@@3HA, 0; int g_RegisterServiceCalled
0x180001cb3  jz      loc_180001D3D
0x180001cb9  mov     rbx, [rcx+808h]
0x180001cc0  mov     eax, [rcx+810h]
0x180001cc6  mov     [rsp+68h+ServiceStatus.dwServiceType], eax
0x180001cca  mov     eax, [rcx+814h]
0x180001cd0  mov     [rsp+68h+ServiceStatus.dwCurrentState], eax
0x180001cd4  mov     eax, [rcx+818h]
0x180001cda  mov     [rsp+68h+ServiceStatus.dwControlsAccepted], eax
0x180001cde  mov     eax, [rcx+81Ch]
0x180001ce4  mov     [rsp+68h+ServiceStatus.dwWin32ExitCode], eax
0x180001ce8  mov     eax, [rcx+820h]
0x180001cee  mov     [rsp+68h+ServiceStatus.dwServiceSpecificExitCode], eax
0x180001cf2  mov     eax, [rcx+824h]
0x180001cf8  mov     [rsp+68h+ServiceStatus.dwCheckPoint], eax
0x180001cfc  mov     eax, [rcx+828h]
0x180001d02  mov     [rsp+68h+ServiceStatus.dwWaitHint], eax
0x180001d06  mov     qword ptr [rcx+808h], 0
0x180001d11  mov     rax, [rcx]
0x180001d14  mov     edx, 1
0x180001d19  mov     rax, [rax+18h]
0x180001d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d22  mov     cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA, 0; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x180001d2d  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180001d32  mov     rcx, rbx; hServiceStatus
0x180001d35  call    cs:__imp_SetServiceStatus
0x180001d3b  jmp     short loc_180001D5E
0x180001d3d  test    rcx, rcx
0x180001d40  jz      short loc_180001D53
0x180001d42  mov     rax, [rcx]
0x180001d45  mov     edx, 1
0x180001d4a  mov     rax, [rax+18h]
0x180001d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d53  mov     cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA, 0; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x180001d5e  mov     rcx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x180001d65  test    rcx, rcx
0x180001d68  jz      short loc_180001D86
0x180001d6a  mov     rax, [rcx]
0x180001d6d  mov     edx, 1
0x180001d72  mov     rax, [rax+18h]
0x180001d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d7b  mov     cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA, 0; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x180001d86  test    edi, edi
0x180001d88  jz      short loc_180001D90
0x180001d8a  call    cs:__imp_CoUninitialize
0x180001d90  xor     eax, eax
0x180001d92  mov     rcx, [rsp+68h+var_10]
0x180001d97  xor     rcx, rsp; StackCookie
0x180001d9a  call    __security_check_cookie
0x180001d9f  mov     rbx, [rsp+68h+arg_0]
0x180001da4  add     rsp, 60h
0x180001da8  pop     rdi
0x180001da9  retn
```
