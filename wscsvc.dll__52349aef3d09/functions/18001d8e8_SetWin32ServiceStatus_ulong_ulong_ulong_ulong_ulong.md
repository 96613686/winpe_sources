# SetWin32ServiceStatus(ulong,ulong,ulong,ulong,ulong)

- ea: `0x18001d8e8`
- end: `0x18001d9cf`
- name: `?SetWin32ServiceStatus@@YAJKKKKK@Z`
- size: `231`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001d2f0`

## callees

- `0x180008e48`
- `0x18001d8e8`
- `0x1800202e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d97d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d97d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001d973`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001d973`

## pseudocode

```c
__int64 __fastcall SetWin32ServiceStatus(DWORD a1, DWORD a2, DWORD a3, DWORD a4, DWORD a5)
{
  DWORD LastError; // ebx

  if ( g_serviceStatusHandle )
  {
    g_serviceStatus.dwCurrentState = a1;
    g_serviceStatus.dwControlsAccepted = a2;
    g_serviceStatus.dwWaitHint = a5;
    g_serviceStatus.dwServiceType = 48;
    g_serviceStatus.dwServiceSpecificExitCode = 0;
    g_serviceStatus.dwWin32ExitCode = a3;
    g_serviceStatus.dwCheckPoint = a4;
    if ( SetServiceStatus(g_serviceStatusHandle, &g_serviceStatus) )
    {
      return 0;
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids, LastError);
      }
      if ( (int)LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return LastError;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001d8e8  push    rbx
0x18001d8ea  sub     rsp, 20h
0x18001d8ee  mov     eax, ecx
0x18001d8f0  mov     rcx, cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18001d8f7  test    rcx, rcx
0x18001d8fa  jnz     short loc_18001D934
0x18001d8fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d903  lea     rax, WPP_GLOBAL_Control
0x18001d90a  cmp     rcx, rax
0x18001d90d  jz      short loc_18001D92A
0x18001d90f  test    byte ptr [rcx+1Ch], 1
0x18001d913  jz      short loc_18001D92A
0x18001d915  mov     rcx, [rcx+10h]
0x18001d919  lea     r8, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids
0x18001d920  mov     edx, 14h
0x18001d925  call    WPP_SF_
0x18001d92a  mov     eax, 80070057h
0x18001d92f  jmp     loc_18001D9C9
0x18001d934  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, eax; _SERVICE_STATUS g_serviceStatus ...
0x18001d93a  mov     eax, [rsp+28h+arg_20]
0x18001d93e  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, edx; _SERVICE_STATUS g_serviceStatus ...
0x18001d944  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18001d94b  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, eax; _SERVICE_STATUS g_serviceStatus ...
0x18001d951  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 30h ; '0'; _SERVICE_STATUS g_serviceStatus ...
0x18001d95b  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, 0; _SERVICE_STATUS g_serviceStatus ...
0x18001d965  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, r8d; _SERVICE_STATUS g_serviceStatus ...
0x18001d96c  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, r9d; _SERVICE_STATUS g_serviceStatus ...
0x18001d973  call    cs:__imp_SetServiceStatus
0x18001d979  test    eax, eax
0x18001d97b  jnz     short loc_18001D9C7
0x18001d97d  call    cs:__imp_GetLastError
0x18001d983  mov     ebx, eax
0x18001d985  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d98c  lea     rax, WPP_GLOBAL_Control
0x18001d993  cmp     rcx, rax
0x18001d996  jz      short loc_18001D9B6
0x18001d998  test    byte ptr [rcx+1Ch], 1
0x18001d99c  jz      short loc_18001D9B6
0x18001d99e  mov     rcx, [rcx+10h]
0x18001d9a2  lea     r8, WPP_b798000f0de738f41d9362b18d9c2686_Traceguids
0x18001d9a9  mov     edx, 15h
0x18001d9ae  mov     r9d, ebx
0x18001d9b1  call    WPP_SF_d
0x18001d9b6  test    ebx, ebx
0x18001d9b8  jle     short loc_18001D9C3
0x18001d9ba  movzx   ebx, bx
0x18001d9bd  or      ebx, 80070000h
0x18001d9c3  mov     eax, ebx
0x18001d9c5  jmp     short loc_18001D9C9
0x18001d9c7  xor     eax, eax
0x18001d9c9  add     rsp, 20h
0x18001d9cd  pop     rbx
0x18001d9ce  retn
```
