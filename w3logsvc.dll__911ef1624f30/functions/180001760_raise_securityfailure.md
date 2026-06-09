# __raise_securityfailure

- ea: `0x180001760`
- end: `0x180001794`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800017a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000176b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000176b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001774`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001774`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000178d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000177a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000177a`

## pseudocode

```c
BOOL __fastcall _raise_securityfailure(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  HANDLE CurrentProcess; // rax

  SetUnhandledExceptionFilter(0);
  UnhandledExceptionFilter(ExceptionInfo);
  CurrentProcess = GetCurrentProcess();
  return TerminateProcess(CurrentProcess, 0xC0000409);
}

```

## disassembly

```asm
0x180001760  push    rbx
0x180001762  sub     rsp, 20h
0x180001766  mov     rbx, rcx
0x180001769  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000176b  call    cs:__imp_SetUnhandledExceptionFilter
0x180001771  mov     rcx, rbx; ExceptionInfo
0x180001774  call    cs:__imp_UnhandledExceptionFilter
0x18000177a  call    cs:__imp_GetCurrentProcess
0x180001780  mov     rcx, rax
0x180001783  mov     edx, 0C0000409h
0x180001788  add     rsp, 20h
0x18000178c  pop     rbx
0x18000178d  jmp     cs:__imp_TerminateProcess
```
