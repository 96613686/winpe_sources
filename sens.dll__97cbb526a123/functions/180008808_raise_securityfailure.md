# __raise_securityfailure

- ea: `0x180008808`
- end: `0x18000883c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180008850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000881c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000881c`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180008813`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180008813`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180008835`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008822`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008822`

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
0x180008808  push    rbx
0x18000880a  sub     rsp, 20h
0x18000880e  mov     rbx, rcx
0x180008811  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180008813  call    cs:__imp_SetUnhandledExceptionFilter
0x180008819  mov     rcx, rbx; ExceptionInfo
0x18000881c  call    cs:__imp_UnhandledExceptionFilter
0x180008822  call    cs:__imp_GetCurrentProcess
0x180008828  mov     rcx, rax
0x18000882b  mov     edx, 0C0000409h
0x180008830  add     rsp, 20h
0x180008834  pop     rbx
0x180008835  jmp     cs:__imp_TerminateProcess
```
