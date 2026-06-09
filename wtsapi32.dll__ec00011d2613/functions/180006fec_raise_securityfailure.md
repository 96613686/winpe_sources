# __raise_securityfailure

- ea: `0x180006fec`
- end: `0x180007020`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007030`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180006ff7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180006ff7`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180007000`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180007000`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180007019`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007006`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007006`

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
0x180006fec  push    rbx
0x180006fee  sub     rsp, 20h
0x180006ff2  mov     rbx, rcx
0x180006ff5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180006ff7  call    cs:__imp_SetUnhandledExceptionFilter
0x180006ffd  mov     rcx, rbx; ExceptionInfo
0x180007000  call    cs:__imp_UnhandledExceptionFilter
0x180007006  call    cs:__imp_GetCurrentProcess
0x18000700c  mov     rcx, rax
0x18000700f  mov     edx, 0C0000409h
0x180007014  add     rsp, 20h
0x180007018  pop     rbx
0x180007019  jmp     cs:__imp_TerminateProcess
```
