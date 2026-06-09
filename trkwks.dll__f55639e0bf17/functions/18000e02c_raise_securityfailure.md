# __raise_securityfailure

- ea: `0x18000e02c`
- end: `0x18000e060`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000e070`
- `0x18000e218`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000e037`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000e037`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000e040`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000e040`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e046`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e046`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000e059`

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
0x18000e02c  push    rbx
0x18000e02e  sub     rsp, 20h
0x18000e032  mov     rbx, rcx
0x18000e035  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000e037  call    cs:__imp_SetUnhandledExceptionFilter
0x18000e03d  mov     rcx, rbx; ExceptionInfo
0x18000e040  call    cs:__imp_UnhandledExceptionFilter
0x18000e046  call    cs:__imp_GetCurrentProcess
0x18000e04c  mov     rcx, rax
0x18000e04f  mov     edx, 0C0000409h
0x18000e054  add     rsp, 20h
0x18000e058  pop     rbx
0x18000e059  jmp     cs:__imp_TerminateProcess
```
