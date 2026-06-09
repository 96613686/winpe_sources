# __raise_securityfailure

- ea: `0x14001b028`
- end: `0x14001b05c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001b070`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001b042`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001b042`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14001b055`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14001b033`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14001b033`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14001b03c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14001b03c`

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
0x14001b028  push    rbx
0x14001b02a  sub     rsp, 20h
0x14001b02e  mov     rbx, rcx
0x14001b031  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14001b033  call    cs:__imp_SetUnhandledExceptionFilter
0x14001b039  mov     rcx, rbx; ExceptionInfo
0x14001b03c  call    cs:__imp_UnhandledExceptionFilter
0x14001b042  call    cs:__imp_GetCurrentProcess
0x14001b048  mov     rcx, rax
0x14001b04b  mov     edx, 0C0000409h
0x14001b050  add     rsp, 20h
0x14001b054  pop     rbx
0x14001b055  jmp     cs:__imp_TerminateProcess
```
