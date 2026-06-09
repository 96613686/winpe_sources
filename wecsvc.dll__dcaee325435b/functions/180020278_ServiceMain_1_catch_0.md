# _ServiceMain_::_1_::catch$0

- ea: `0x180020278`
- end: `0x1800202cf`
- name: `_ServiceMain_::_1_::catch$0`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180002b78`
- `0x180023010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800202b7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800202b7`

## pseudocode

```c
__int64 __fastcall ServiceMain_::_1_::catch_0(__int64 a1, __int64 a2)
{
  Shutdown();
  g_serviceStatus.dwCurrentState = 1;
  g_serviceStatus.dwWin32ExitCode = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 64))(*(_QWORD *)(a2 + 64));
  SetServiceStatus(g_serviceControl, &g_serviceStatus);
  return 0;
}

```

## disassembly

```asm
0x180020278  mov     [rsp+arg_8], rdx
0x18002027d  push    rbp
0x18002027e  sub     rsp, 40h
0x180020282  mov     rbp, rdx
0x180020285  call    ?Shutdown@@YAXXZ; Shutdown(void)
0x18002028a  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_serviceStatus ...
0x180020294  mov     rcx, [rbp+40h]
0x180020298  mov     rax, [rcx]
0x18002029b  mov     rax, [rax]
0x18002029e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202a3  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, eax; _SERVICE_STATUS g_serviceStatus ...
0x1800202a9  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800202b0  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800202b7  call    cs:__imp_SetServiceStatus
0x1800202bd  nop
0x1800202be  mov     rax, 0
0x1800202c8  add     rsp, 40h
0x1800202cc  pop     rbp
0x1800202cd  retn
```
