# CServiceMonitor::~CServiceMonitor(void)

- ea: `0x180029b80`
- end: `0x180029bd7`
- name: `??1CServiceMonitor@@UEAA@XZ`
- size: `87`
- prototype: `void __fastcall(CServiceMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002ed28`

## callees

- `0x180029b80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bcb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180029bb6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180029bb6`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180029ba9`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180029ba9`

## pseudocode

```c
void __fastcall CServiceMonitor::~CServiceMonitor(CServiceMonitor *this)
{
  bool v1; // zf
  BOOL v3; // eax

  v1 = *((_QWORD *)this + 67) == 0;
  *(_QWORD *)this = &CServiceMonitor::`vftable';
  if ( !v1 )
  {
    if ( *((_QWORD *)this + 69) )
      UnsubscribeServiceChangeNotifications();
    v3 = CloseServiceHandle(*((SC_HANDLE *)this + 67));
    *((_QWORD *)this + 67) = 0;
    if ( !v3 )
      GetLastError();
  }
}

```

## disassembly

```asm
0x180029b80  push    rbx
0x180029b82  sub     rsp, 20h
0x180029b86  cmp     qword ptr [rcx+218h], 0
0x180029b8e  lea     rax, ??_7CServiceMonitor@@6B@; const CServiceMonitor::`vftable'
0x180029b95  mov     [rcx], rax
0x180029b98  mov     rbx, rcx
0x180029b9b  jz      short loc_180029BD1
0x180029b9d  mov     rcx, [rcx+228h]
0x180029ba4  test    rcx, rcx
0x180029ba7  jz      short loc_180029BAF
0x180029ba9  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x180029baf  mov     rcx, [rbx+218h]; hSCObject
0x180029bb6  call    cs:__imp_CloseServiceHandle
0x180029bbc  mov     qword ptr [rbx+218h], 0
0x180029bc7  test    eax, eax
0x180029bc9  jnz     short loc_180029BD1
0x180029bcb  call    cs:__imp_GetLastError
0x180029bd1  add     rsp, 20h
0x180029bd5  pop     rbx
0x180029bd6  retn
```
