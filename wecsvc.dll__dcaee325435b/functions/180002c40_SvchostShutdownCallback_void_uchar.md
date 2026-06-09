# SvchostShutdownCallback(void *,uchar)

- ea: `0x180002c40`
- end: `0x180002ca9`
- name: `?SvchostShutdownCallback@@YAXPEAXE@Z`
- size: `105`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180002b78`
- `0x180002c40`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002c5c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002c99`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002c5c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002c99`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180002c6b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180002c6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SvchostShutdownCallback(void *a1)
{
  g_serviceStatus.dwCurrentState = 3;
  SetServiceStatus(g_serviceControl, &g_serviceStatus);
  UnregisterWaitEx(g_svchostShutdownWaitHandle, 0);
  g_svchostShutdownWaitHandle = 0;
  Shutdown();
  g_serviceStatus.dwCurrentState = 1;
  SetServiceStatus(g_serviceControl, &g_serviceStatus);
}

```

## disassembly

```asm
0x180002c40  sub     rsp, 38h
0x180002c44  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_serviceStatus ...
0x180002c4e  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180002c55  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180002c5c  call    cs:__imp_SetServiceStatus
0x180002c62  xor     edx, edx; CompletionEvent
0x180002c64  mov     rcx, cs:?g_svchostShutdownWaitHandle@@3PEAXEA; WaitHandle
0x180002c6b  call    cs:__imp_UnregisterWaitEx
0x180002c71  mov     cs:?g_svchostShutdownWaitHandle@@3PEAXEA, 0; void * g_svchostShutdownWaitHandle
0x180002c7c  call    ?Shutdown@@YAXXZ; Shutdown(void)
0x180002c81  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_serviceStatus ...
0x180002c8b  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180002c92  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180002c99  call    cs:__imp_SetServiceStatus
0x180002c9f  nop
0x180002ca0  jmp     short loc_180002CA4
0x180002ca2  jmp     short $+2
0x180002ca4  add     rsp, 38h
0x180002ca8  retn
```
