# SysMtServiceControlHandler

- ea: `0x18004bf80`
- end: `0x18004c018`
- name: `SysMtServiceControlHandler`
- size: `152`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18004bf80`
- `0x18004c020`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004bf9d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004bf9d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004bfc0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004bfc0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004bfdf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004bfdf`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18004c010`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18004c010`

## pseudocode

```c
__int64 __fastcall SysMtServiceControlHandler(
        DWORD dwControl,
        DWORD dwEventType,
        __int64 lpEventData,
        LPVOID lpContext)
{
  RtlAcquireSRWLockExclusive(&PfSvcGlobalsLock);
  PfSvServiceControlNotify(dwControl, dwEventType, lpEventData);
  if ( ((dwControl - 1) & 0xFFFFFFFB) == 0 )
  {
    SetEvent(hEvent);
    if ( ServiceStatus.dwCurrentState != 1 )
    {
      ServiceStatus.dwCurrentState = 3;
      ServiceStatus.dwWaitHint = 10000;
      SetServiceStatus(SysMtGlobals, &ServiceStatus);
    }
  }
  RtlReleaseSRWLockExclusive(&PfSvcGlobalsLock);
  return 0;
}

```

## disassembly

```asm
0x18004bf80  mov     [rsp+arg_0], rbx
0x18004bf85  mov     [rsp+arg_8], rsi
0x18004bf8a  push    rdi
0x18004bf8b  sub     rsp, 20h
0x18004bf8f  mov     esi, ecx
0x18004bf91  mov     rbx, r8
0x18004bf94  lea     rcx, PfSvcGlobalsLock
0x18004bf9b  mov     edi, edx
0x18004bf9d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18004bfa3  mov     r8, rbx
0x18004bfa6  mov     edx, edi
0x18004bfa8  mov     ecx, esi
0x18004bfaa  call    PfSvServiceControlNotify
0x18004bfaf  lea     eax, [rsi-1]
0x18004bfb2  test    eax, 0FFFFFFFBh
0x18004bfb7  jz      short loc_18004BFD8
0x18004bfb9  lea     rcx, PfSvcGlobalsLock
0x18004bfc0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18004bfc6  mov     rbx, [rsp+28h+arg_0]
0x18004bfcb  xor     eax, eax
0x18004bfcd  mov     rsi, [rsp+28h+arg_8]
0x18004bfd2  add     rsp, 20h
0x18004bfd6  pop     rdi
0x18004bfd7  retn
0x18004bfd8  mov     rcx, cs:hEvent; hEvent
0x18004bfdf  call    cs:__imp_SetEvent
0x18004bfe5  cmp     cs:ServiceStatus.dwCurrentState, 1
0x18004bfec  jz      short loc_18004BFB9
0x18004bfee  mov     rcx, cs:SysMtGlobals; hServiceStatus
0x18004bff5  lea     rdx, ServiceStatus; lpServiceStatus
0x18004bffc  mov     cs:ServiceStatus.dwCurrentState, 3
0x18004c006  mov     cs:ServiceStatus.dwWaitHint, 2710h
0x18004c010  call    cs:__imp_SetServiceStatus
0x18004c016  jmp     short loc_18004BFB9
```
