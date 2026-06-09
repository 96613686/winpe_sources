# CTSSDFarmRpc::StartConnectionMonitoringTimer(void)

- ea: `0x180039ed8`
- end: `0x180039f89`
- name: `?StartConnectionMonitoringTimer@CTSSDFarmRpc@@AEAAJXZ`
- size: `177`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180038628`

## callees

- `0x180003f30`
- `0x180039ed8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039f1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039f1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039f5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039f5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039f71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039f71`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180039f12`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180039f12`

## string_xrefs

- `0x180039f3f`: `CreateTimerQueueTimer failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSDFarmRpc::StartConnectionMonitoringTimer(char *Parameter)
{
  signed int v1; // edi
  signed int LastError; // eax
  void *v5; // [rsp+58h] [rbp+10h] BYREF

  v1 = 0;
  v5 = 0;
  if ( CreateTimerQueueTimer(&v5, 0, CTSSDFarmRpc::WaitOrTimerCallback, Parameter, 0x493E0u, 0, 0x18u) )
    goto LABEL_6;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_6:
    EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 1608));
    *((_QWORD *)Parameter + 200) = v5;
    LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 1608));
  }
  else
  {
    _DbgPrintMessage(8, "CreateTimerQueueTimer failed: 0x%x in %s", v1, "CTSSDFarmRpc::StartConnectionMonitoringTimer");
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180039ed8  mov     rax, rsp
0x180039edb  mov     [rax+8], rbx
0x180039edf  mov     [rax+18h], rsi
0x180039ee3  push    rdi
0x180039ee4  sub     rsp, 40h
0x180039ee8  mov     dword ptr [rax-18h], 18h
0x180039eef  lea     r8, ?WaitOrTimerCallback@CTSSDFarmRpc@@CAXPEAXE@Z; Callback
0x180039ef6  xor     edi, edi
0x180039ef8  mov     rsi, rcx
0x180039efb  mov     r9, rcx; Parameter
0x180039efe  mov     [rax-20h], edi
0x180039f01  xor     edx, edx; TimerQueue
0x180039f03  mov     dword ptr [rax-28h], 493E0h
0x180039f0a  lea     rcx, [rax+10h]; phNewTimer
0x180039f0e  mov     [rax+10h], rdi
0x180039f12  call    cs:__imp_CreateTimerQueueTimer
0x180039f18  test    eax, eax
0x180039f1a  jnz     short loc_180039F52
0x180039f1c  call    cs:__imp_GetLastError
0x180039f22  mov     edi, eax
0x180039f24  test    eax, eax
0x180039f26  jle     short loc_180039F31
0x180039f28  movzx   edi, ax
0x180039f2b  or      edi, 80070000h
0x180039f31  test    edi, edi
0x180039f33  jns     short loc_180039F52
0x180039f35  lea     r9, aCtssdfarmrpcSt_2; "CTSSDFarmRpc::StartConnectionMonitoring"...
0x180039f3c  mov     r8d, edi
0x180039f3f  lea     rdx, aCreatetimerque; "CreateTimerQueueTimer failed: 0x%x in %"...
0x180039f46  mov     ecx, 8; int
0x180039f4b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180039f50  jmp     short loc_180039F77
0x180039f52  lea     rbx, [rsi+648h]
0x180039f59  mov     rcx, rbx; lpCriticalSection
0x180039f5c  call    cs:__imp_EnterCriticalSection
0x180039f62  mov     rdx, [rsp+48h+arg_8]
0x180039f67  mov     rcx, rbx; lpCriticalSection
0x180039f6a  mov     [rsi+640h], rdx
0x180039f71  call    cs:__imp_LeaveCriticalSection
0x180039f77  mov     rbx, [rsp+48h+arg_0]
0x180039f7c  mov     eax, edi
0x180039f7e  mov     rsi, [rsp+48h+arg_10]
0x180039f83  add     rsp, 40h
0x180039f87  pop     rdi
0x180039f88  retn
```
