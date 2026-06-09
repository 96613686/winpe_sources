# WsShutdownDfs

- ea: `0x18002fca0`
- end: `0x18002fe68`
- name: `WsShutdownDfs`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180030544`

## callees

- `0x18002fca0`

## import_xrefs

- `ntdll!RtlDeregisterWaitEx` at `0x18002fdbc`
- `ntdll!RtlDeregisterWaitEx` at `0x18002fdbc`
- `ntdll!RtlDeleteElementGenericTable` at `0x18002fce1`
- `ntdll!RtlDeleteElementGenericTable` at `0x18002fce1`
- `ntdll!RtlEnumerateGenericTable` at `0x18002fcf6`
- `ntdll!RtlEnumerateGenericTable` at `0x18002fcf6`
- `ntdll!NtClose` at `0x18002fdf2`
- `ntdll!NtClose` at `0x18002fdf2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002fd8b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002fd8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fd3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fd7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fe07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fd3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fd7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fe07`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002fda1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002fda1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fcc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fd4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fcc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fd4e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fe1a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fe2d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fe1a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fe2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fe45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fe45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fd1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fd1d`
- `SspiCli!LsaUnregisterPolicyChangeNotification` at `0x18002fdd0`
- `SspiCli!LsaUnregisterPolicyChangeNotification` at `0x18002fdd0`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18002fcb6`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18002fcb6`

## pseudocode

```c
void WsShutdownDfs()
{
  PVOID v0; // rax
  HANDLE v1; // rbx

  if ( WsDfsIpNotify )
    CancelMibChangeNotify2(WsDfsIpNotify);
  EnterCriticalSection(&WsDfsNetLuidTableCriticalSection);
  while ( 1 )
  {
    v0 = RtlEnumerateGenericTable(WsDfsNetLuidTable, 1u);
    if ( !v0 )
      break;
    RtlDeleteElementGenericTable(WsDfsNetLuidTable, v0);
  }
  HeapFree(NtCurrentPeb()->ProcessHeap, 0, WsDfsNetLuidTable);
  WsDfsNetLuidTable = 0;
  LeaveCriticalSection(&WsDfsNetLuidTableCriticalSection);
  EnterCriticalSection(&WsDfsTearDownCriticalSection);
  v1 = g_WsDomainNameChangeEvent;
  if ( g_WsDomainNameChangeEvent == (HANDLE)-1LL )
  {
    LeaveCriticalSection(&WsDfsTearDownCriticalSection);
  }
  else
  {
    g_WsDomainNameChangeEvent = (HANDLE)-1LL;
    LeaveCriticalSection(&WsDfsTearDownCriticalSection);
    SetEvent(v1);
    WaitForSingleObject(WsDfsTearDownDoneEvent, 0xFFFFFFFF);
    if ( g_WsDomainNameChangeWorkItem != (HANDLE)-1LL )
      RtlDeregisterWaitEx(g_WsDomainNameChangeWorkItem, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    LsaUnregisterPolicyChangeNotification(PolicyNotifyDnsDomainInformation, v1);
    CloseHandle(v1);
    NtClose(WsDfsTearDownDoneEvent);
    WsDfsTearDownDoneEvent = (HANDLE)-1LL;
  }
  DeleteCriticalSection(&WsDfsTearDownCriticalSection);
  DeleteCriticalSection(&WsDfsNetLuidTableCriticalSection);
  if ( hMupEvent )
  {
    CloseHandle(hMupEvent);
    hMupEvent = 0;
  }
}

```

## disassembly

```asm
0x18002fca0  mov     [rsp+arg_0], rbx
0x18002fca5  push    rsi
0x18002fca6  sub     rsp, 20h
0x18002fcaa  mov     rcx, cs:WsDfsIpNotify; NotificationHandle
0x18002fcb1  test    rcx, rcx
0x18002fcb4  jz      short loc_18002FCC2
0x18002fcb6  call    cs:__imp_CancelMibChangeNotify2
0x18002fcbd  nop     dword ptr [rax+rax+00h]
0x18002fcc2  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18002fcc9  call    cs:__imp_EnterCriticalSection
0x18002fcd0  nop     dword ptr [rax+rax+00h]
0x18002fcd5  jmp     short loc_18002FCED
0x18002fcd7  mov     rcx, cs:WsDfsNetLuidTable; Table
0x18002fcde  mov     rdx, rax; Buffer
0x18002fce1  call    cs:__imp_RtlDeleteElementGenericTable
0x18002fce8  nop     dword ptr [rax+rax+00h]
0x18002fced  mov     rcx, cs:WsDfsNetLuidTable; Table
0x18002fcf4  mov     dl, 1; Restart
0x18002fcf6  call    cs:__imp_RtlEnumerateGenericTable
0x18002fcfd  nop     dword ptr [rax+rax+00h]
0x18002fd02  test    rax, rax
0x18002fd05  jnz     short loc_18002FCD7
0x18002fd07  mov     rcx, gs:60h
0x18002fd10  xor     edx, edx; dwFlags
0x18002fd12  mov     r8, cs:WsDfsNetLuidTable; lpMem
0x18002fd19  mov     rcx, [rcx+30h]; hHeap
0x18002fd1d  call    cs:__imp_HeapFree
0x18002fd24  nop     dword ptr [rax+rax+00h]
0x18002fd29  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18002fd30  mov     cs:WsDfsNetLuidTable, 0
0x18002fd3b  call    cs:__imp_LeaveCriticalSection
0x18002fd42  nop     dword ptr [rax+rax+00h]
0x18002fd47  lea     rcx, WsDfsTearDownCriticalSection; lpCriticalSection
0x18002fd4e  call    cs:__imp_EnterCriticalSection
0x18002fd55  nop     dword ptr [rax+rax+00h]
0x18002fd5a  mov     rbx, cs:g_WsDomainNameChangeEvent
0x18002fd61  lea     rcx, WsDfsTearDownCriticalSection; lpCriticalSection
0x18002fd68  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002fd6c  cmp     rbx, rsi
0x18002fd6f  jz      loc_18002FE07
0x18002fd75  mov     cs:g_WsDomainNameChangeEvent, rsi
0x18002fd7c  call    cs:__imp_LeaveCriticalSection
0x18002fd83  nop     dword ptr [rax+rax+00h]
0x18002fd88  mov     rcx, rbx; hEvent
0x18002fd8b  call    cs:__imp_SetEvent
0x18002fd92  nop     dword ptr [rax+rax+00h]
0x18002fd97  mov     rcx, cs:WsDfsTearDownDoneEvent; hHandle
0x18002fd9e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002fda1  call    cs:__imp_WaitForSingleObject
0x18002fda8  nop     dword ptr [rax+rax+00h]
0x18002fdad  mov     rcx, cs:g_WsDomainNameChangeWorkItem; hWaitHandle
0x18002fdb4  cmp     rcx, rsi
0x18002fdb7  jz      short loc_18002FDC8
0x18002fdb9  mov     rdx, rsi; hCompletionEvent
0x18002fdbc  call    cs:__imp_RtlDeregisterWaitEx
0x18002fdc3  nop     dword ptr [rax+rax+00h]
0x18002fdc8  mov     rdx, rbx; NotificationEventHandle
0x18002fdcb  mov     ecx, 4; InformationClass
0x18002fdd0  call    cs:__imp_LsaUnregisterPolicyChangeNotification
0x18002fdd7  nop     dword ptr [rax+rax+00h]
0x18002fddc  mov     rcx, rbx; hObject
0x18002fddf  call    cs:__imp_CloseHandle
0x18002fde6  nop     dword ptr [rax+rax+00h]
0x18002fdeb  mov     rcx, cs:WsDfsTearDownDoneEvent; Handle
0x18002fdf2  call    cs:__imp_NtClose
0x18002fdf9  nop     dword ptr [rax+rax+00h]
0x18002fdfe  mov     cs:WsDfsTearDownDoneEvent, rsi
0x18002fe05  jmp     short loc_18002FE13
0x18002fe07  call    cs:__imp_LeaveCriticalSection
0x18002fe0e  nop     dword ptr [rax+rax+00h]
0x18002fe13  lea     rcx, WsDfsTearDownCriticalSection; lpCriticalSection
0x18002fe1a  call    cs:__imp_DeleteCriticalSection
0x18002fe21  nop     dword ptr [rax+rax+00h]
0x18002fe26  lea     rcx, WsDfsNetLuidTableCriticalSection; lpCriticalSection
0x18002fe2d  call    cs:__imp_DeleteCriticalSection
0x18002fe34  nop     dword ptr [rax+rax+00h]
0x18002fe39  mov     rcx, cs:hMupEvent; hObject
0x18002fe40  test    rcx, rcx
0x18002fe43  jz      short loc_18002FE5C
0x18002fe45  call    cs:__imp_CloseHandle
0x18002fe4c  nop     dword ptr [rax+rax+00h]
0x18002fe51  mov     cs:hMupEvent, 0
0x18002fe5c  mov     rbx, [rsp+28h+arg_0]
0x18002fe61  add     rsp, 20h
0x18002fe65  pop     rsi
0x18002fe66  retn
```
