# __raise_securityfailure

- ea: `0x180010ab4`
- end: `0x180010ae8`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180010af0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180010ac8`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180010ac8`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180010abf`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180010abf`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180010ae1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010ace`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010ace`

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
0x180010ab4  push    rbx
0x180010ab6  sub     rsp, 20h
0x180010aba  mov     rbx, rcx
0x180010abd  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180010abf  call    cs:__imp_SetUnhandledExceptionFilter
0x180010ac5  mov     rcx, rbx; ExceptionInfo
0x180010ac8  call    cs:__imp_UnhandledExceptionFilter
0x180010ace  call    cs:__imp_GetCurrentProcess
0x180010ad4  mov     rcx, rax
0x180010ad7  mov     edx, 0C0000409h
0x180010adc  add     rsp, 20h
0x180010ae0  pop     rbx
0x180010ae1  jmp     cs:__imp_TerminateProcess
```
