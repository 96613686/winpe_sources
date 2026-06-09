# __raise_securityfailure

- ea: `0x180001a9c`
- end: `0x180001ad0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001ae0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001ab6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001ab6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001ac9`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001aa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001aa7`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001ab0`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001ab0`

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
0x180001a9c  push    rbx
0x180001a9e  sub     rsp, 20h
0x180001aa2  mov     rbx, rcx
0x180001aa5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001aa7  call    cs:__imp_SetUnhandledExceptionFilter
0x180001aad  mov     rcx, rbx; ExceptionInfo
0x180001ab0  call    cs:__imp_UnhandledExceptionFilter
0x180001ab6  call    cs:__imp_GetCurrentProcess
0x180001abc  mov     rcx, rax
0x180001abf  mov     edx, 0C0000409h
0x180001ac4  add     rsp, 20h
0x180001ac8  pop     rbx
0x180001ac9  jmp     cs:__imp_TerminateProcess
```
