# WdipSvcHandlerEx(ulong,ulong,void *,void *)

- ea: `0x180001370`
- end: `0x18000145d`
- name: `?WdipSvcHandlerEx@@YAKKKPEAX0@Z`
- size: `237`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001370`
- `0x180001470`
- `0x180002ba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001452`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800013cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800013cb`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800013c1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800013c1`

## pseudocode

```c
__int64 __fastcall WdipSvcHandlerEx(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  signed int Args; // eax
  bool v6; // sf
  DWORD v7; // ecx

  _m_prefetchw((const void *)&g_fControl);
  if ( (_InterlockedOr(&g_fControl, 2u) & 1) != 0 )
  {
LABEL_2:
    _InterlockedAnd(&g_fControl, 0xFFFFFFFD);
    return 0;
  }
  if ( dwControl == 4 )
  {
    if ( g_hService && !SetServiceStatus(g_hService, &g_sSvcStatus) )
    {
      Args = GetLastError();
      v6 = Args < 0;
      if ( Args > 0 )
      {
        Args = (unsigned __int16)Args | 0x80070000;
        v6 = Args < 0;
      }
      if ( v6 )
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\wdi.cpp",
          (int)L"WdipNotifySvc",
          639,
          (int)L"Error = %d",
          Args);
    }
    goto LABEL_2;
  }
  v7 = dwControl - 1;
  if ( !v7 || v7 == 4 )
  {
    if ( g_hHostShutdown )
      SetEvent(g_hHostShutdown);
    goto LABEL_2;
  }
  WdipNotifySvc(16, 0, 0, 0, 0);
  _InterlockedAnd(&g_fControl, 0xFFFFFFFD);
  return 16385;
}

```

## disassembly

```asm
0x180001370  push    rbx
0x180001372  sub     rsp, 30h
0x180001376  xor     ebx, ebx
0x180001378  prefetchw byte ptr cs:?g_fControl@@3JC; long volatile g_fControl
0x18000137f  mov     eax, cs:?g_fControl@@3JC; long volatile g_fControl
0x180001385  mov     edx, eax
0x180001387  or      edx, 2
0x18000138a  lock cmpxchg cs:?g_fControl@@3JC, edx; long volatile g_fControl
0x180001392  jnz     short loc_180001385
0x180001394  test    al, 1
0x180001396  jz      short loc_1800013A9
0x180001398  lock and cs:?g_fControl@@3JC, 0FFFFFFFDh; long volatile g_fControl
0x1800013a0  movzx   eax, bx
0x1800013a3  add     rsp, 30h
0x1800013a7  pop     rbx
0x1800013a8  retn
0x1800013a9  cmp     ecx, 4
0x1800013ac  jnz     short loc_180001400
0x1800013ae  mov     rcx, cs:?g_hService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800013b5  test    rcx, rcx
0x1800013b8  jz      short loc_180001398
0x1800013ba  lea     rdx, ?g_sSvcStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800013c1  call    cs:__imp_SetServiceStatus
0x1800013c7  test    eax, eax
0x1800013c9  jnz     short loc_180001398
0x1800013cb  call    cs:__imp_GetLastError
0x1800013d1  test    eax, eax
0x1800013d3  jg      short loc_180001436
0x1800013d5  jns     short loc_180001398
0x1800013d7  movzx   eax, ax
0x1800013da  lea     r9, aErrorD_0; "Error = %d"
0x1800013e1  mov     r8d, 27Fh; int
0x1800013e7  mov     dword ptr [rsp+38h+Args], eax; Args
0x1800013eb  lea     rdx, aWdipnotifysvc; "WdipNotifySvc"
0x1800013f2  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800013f9  call    WdipTraceError
0x1800013fe  jmp     short loc_180001398
0x180001400  sub     ecx, 1
0x180001403  jz      short loc_180001442
0x180001405  cmp     ecx, 4
0x180001408  jz      short loc_180001442
0x18000140a  xor     r9d, r9d
0x18000140d  mov     dword ptr [rsp+38h+Args], ebx
0x180001411  xor     r8d, r8d
0x180001414  xor     edx, edx
0x180001416  mov     ecx, 10h
0x18000141b  call    WdipNotifySvc
0x180001420  mov     ebx, 80004001h
0x180001425  lock and cs:?g_fControl@@3JC, 0FFFFFFFDh; long volatile g_fControl
0x18000142d  movzx   eax, bx
0x180001430  add     rsp, 30h
0x180001434  pop     rbx
0x180001435  retn
0x180001436  movzx   eax, ax
0x180001439  or      eax, 80070000h
0x18000143e  test    eax, eax
0x180001440  jmp     short loc_1800013D5
0x180001442  mov     rcx, cs:g_hHostShutdown; hEvent
0x180001449  test    rcx, rcx
0x18000144c  jz      loc_180001398
0x180001452  call    cs:__imp_SetEvent
0x180001458  jmp     loc_180001398
```
