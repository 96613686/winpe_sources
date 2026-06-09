# __raise_securityfailure

- ea: `0x180002b9c`
- end: `0x180002bd0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002be0`
- `0x180002d88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002bb0`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002bb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002ba7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002ba7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002bc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002bb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002bb6`

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
0x180002b9c  push    rbx
0x180002b9e  sub     rsp, 20h
0x180002ba2  mov     rbx, rcx
0x180002ba5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002ba7  call    cs:__imp_SetUnhandledExceptionFilter
0x180002bad  mov     rcx, rbx; ExceptionInfo
0x180002bb0  call    cs:__imp_UnhandledExceptionFilter
0x180002bb6  call    cs:__imp_GetCurrentProcess
0x180002bbc  mov     rcx, rax
0x180002bbf  mov     edx, 0C0000409h
0x180002bc4  add     rsp, 20h
0x180002bc8  pop     rbx
0x180002bc9  jmp     cs:__imp_TerminateProcess
```
