# __raise_securityfailure

- ea: `0x180001b80`
- end: `0x180001bb4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001bc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001b8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001b8b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001b94`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001b94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001b9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001b9a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001bad`

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
0x180001b80  push    rbx
0x180001b82  sub     rsp, 20h
0x180001b86  mov     rbx, rcx
0x180001b89  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001b8b  call    cs:__imp_SetUnhandledExceptionFilter
0x180001b91  mov     rcx, rbx; ExceptionInfo
0x180001b94  call    cs:__imp_UnhandledExceptionFilter
0x180001b9a  call    cs:__imp_GetCurrentProcess
0x180001ba0  mov     rcx, rax
0x180001ba3  mov     edx, 0C0000409h
0x180001ba8  add     rsp, 20h
0x180001bac  pop     rbx
0x180001bad  jmp     cs:__imp_TerminateProcess
```
