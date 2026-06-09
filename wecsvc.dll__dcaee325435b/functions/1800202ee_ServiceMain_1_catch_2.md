# _ServiceMain_::_1_::catch$2

- ea: `0x1800202ee`
- end: `0x180020340`
- name: `_ServiceMain_::_1_::catch$2`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180023010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180020328`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180020328`

## pseudocode

```c
__int64 __fastcall ServiceMain_::_1_::catch_2(__int64 a1, __int64 a2)
{
  g_serviceStatus.dwCurrentState = 1;
  g_serviceStatus.dwWin32ExitCode = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 72))(*(_QWORD *)(a2 + 72));
  SetServiceStatus(g_serviceControl, &g_serviceStatus);
  return 0;
}

```

## disassembly

```asm
0x1800202ee  mov     [rsp+arg_8], rdx
0x1800202f3  push    rbp
0x1800202f4  sub     rsp, 40h
0x1800202f8  mov     rbp, rdx
0x1800202fb  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_serviceStatus ...
0x180020305  mov     rcx, [rbp+48h]
0x180020309  mov     rax, [rcx]
0x18002030c  mov     rax, [rax]
0x18002030f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020314  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, eax; _SERVICE_STATUS g_serviceStatus ...
0x18002031a  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180020321  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180020328  call    cs:__imp_SetServiceStatus
0x18002032e  nop
0x18002032f  mov     rax, 0
0x180020339  add     rsp, 40h
0x18002033d  pop     rbp
0x18002033e  retn
```
