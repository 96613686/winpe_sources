# WdipNotifySvc

- ea: `0x180001470`
- end: `0x18000153f`
- name: `WdipNotifySvc`
- size: `207`
- prototype: `__int64 __fastcall(char, DWORD, DWORD, DWORD, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180001370`

## callees

- `0x180001470`
- `0x180002ba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800014fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800014fb`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800014db`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800014db`

## pseudocode

```c
__int64 __fastcall WdipNotifySvc(char a1, DWORD a2, DWORD a3, DWORD a4, DWORD a5)
{
  signed int Args; // ebx
  signed int LastError; // eax

  if ( !g_hService )
    return 2147942487LL;
  Args = 0;
  if ( (a1 & 0x10) == 0 )
  {
    g_sSvcStatus.dwCurrentState = 0;
    *(_QWORD *)&g_sSvcStatus.dwCheckPoint = 0;
    g_sSvcStatus.dwWin32ExitCode = 0;
    if ( (a1 & 1) != 0 )
      g_sSvcStatus.dwCurrentState = a2;
    if ( (a1 & 2) != 0 )
      g_sSvcStatus.dwCheckPoint = a3;
    if ( (a1 & 4) != 0 )
      g_sSvcStatus.dwWaitHint = a4;
    if ( (a1 & 8) != 0 )
      g_sSvcStatus.dwWin32ExitCode = a5;
  }
  if ( !SetServiceStatus(g_hService, &g_sSvcStatus) )
  {
    LastError = GetLastError();
    Args = LastError;
    if ( LastError > 0 )
      Args = (unsigned __int16)LastError | 0x80070000;
    if ( Args < 0 )
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
        (int)L"WdipNotifySvc",
        639,
        (int)L"Error = %d",
        Args);
  }
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x180001470  sub     rsp, 38h
0x180001474  mov     r10, cs:?g_hService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_hService
0x18000147b  test    r10, r10
0x18000147e  jz      short loc_1800014F1
0x180001480  mov     [rsp+38h+var_8], rbx
0x180001485  xor     ebx, ebx
0x180001487  test    cl, 10h
0x18000148a  jnz     short loc_1800014D1
0x18000148c  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, ebx; _SERVICE_STATUS g_sSvcStatus ...
0x180001492  mov     qword ptr cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, rbx; _SERVICE_STATUS g_sSvcStatus ...
0x180001499  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, ebx; _SERVICE_STATUS g_sSvcStatus ...
0x18000149f  test    cl, 1
0x1800014a2  jz      short loc_1800014AA
0x1800014a4  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, edx; _SERVICE_STATUS g_sSvcStatus ...
0x1800014aa  test    cl, 2
0x1800014ad  jz      short loc_1800014B6
0x1800014af  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, r8d; _SERVICE_STATUS g_sSvcStatus ...
0x1800014b6  test    cl, 4
0x1800014b9  jz      short loc_1800014C2
0x1800014bb  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, r9d; _SERVICE_STATUS g_sSvcStatus ...
0x1800014c2  test    cl, 8
0x1800014c5  jz      short loc_1800014D1
0x1800014c7  mov     eax, [rsp+38h+arg_20]
0x1800014cb  mov     cs:?g_sSvcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, eax; _SERVICE_STATUS g_sSvcStatus ...
0x1800014d1  lea     rdx, ?g_sSvcStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800014d8  mov     rcx, r10; hServiceStatus
0x1800014db  call    cs:__imp_SetServiceStatus
0x1800014e1  test    eax, eax
0x1800014e3  jz      short loc_1800014FB
0x1800014e5  mov     eax, ebx
0x1800014e7  mov     rbx, [rsp+38h+var_8]
0x1800014ec  add     rsp, 38h
0x1800014f0  retn
0x1800014f1  mov     eax, 80070057h
0x1800014f6  add     rsp, 38h
0x1800014fa  retn
0x1800014fb  call    cs:__imp_GetLastError
0x180001501  mov     ebx, eax
0x180001503  test    eax, eax
0x180001505  jg      short loc_180001534
0x180001507  test    ebx, ebx
0x180001509  jns     short loc_1800014E5
0x18000150b  movzx   ecx, bx
0x18000150e  lea     r9, aErrorD_0; "Error = %d"
0x180001515  mov     dword ptr [rsp+38h+Args], ecx; Args
0x180001519  lea     rdx, aWdipnotifysvc; "WdipNotifySvc"
0x180001520  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180001527  mov     r8d, 27Fh; int
0x18000152d  call    WdipTraceError
0x180001532  jmp     short loc_1800014E5
0x180001534  movzx   ebx, ax
0x180001537  or      ebx, 80070000h
0x18000153d  jmp     short loc_180001507
```
