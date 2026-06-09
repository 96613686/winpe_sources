# __raise_securityfailure

- ea: `0x18000174c`
- end: `0x180001780`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001757`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001757`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001760`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001760`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001766`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001766`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001779`

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
0x18000174c  push    rbx
0x18000174e  sub     rsp, 20h
0x180001752  mov     rbx, rcx
0x180001755  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001757  call    cs:__imp_SetUnhandledExceptionFilter
0x18000175d  mov     rcx, rbx; ExceptionInfo
0x180001760  call    cs:__imp_UnhandledExceptionFilter
0x180001766  call    cs:__imp_GetCurrentProcess
0x18000176c  mov     rcx, rax
0x18000176f  mov     edx, 0C0000409h
0x180001774  add     rsp, 20h
0x180001778  pop     rbx
0x180001779  jmp     cs:__imp_TerminateProcess
```
