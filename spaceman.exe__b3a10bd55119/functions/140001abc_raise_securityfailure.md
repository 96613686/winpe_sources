# __raise_securityfailure

- ea: `0x140001abc`
- end: `0x140001af0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001ac7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140001ac7`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001ad0`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140001ad0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001ad6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140001ad6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140001ae9`

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
0x140001abc  push    rbx
0x140001abe  sub     rsp, 20h
0x140001ac2  mov     rbx, rcx
0x140001ac5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001ac7  call    cs:__imp_SetUnhandledExceptionFilter
0x140001acd  mov     rcx, rbx; ExceptionInfo
0x140001ad0  call    cs:__imp_UnhandledExceptionFilter
0x140001ad6  call    cs:__imp_GetCurrentProcess
0x140001adc  mov     rcx, rax
0x140001adf  mov     edx, 0C0000409h
0x140001ae4  add     rsp, 20h
0x140001ae8  pop     rbx
0x140001ae9  jmp     cs:__imp_TerminateProcess
```
