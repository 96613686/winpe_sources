# __raise_securityfailure

- ea: `0x180002d64`
- end: `0x180002d98`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002da0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002d6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002d6f`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002d78`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002d78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002d7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002d7e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002d91`

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
0x180002d64  push    rbx
0x180002d66  sub     rsp, 20h
0x180002d6a  mov     rbx, rcx
0x180002d6d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002d6f  call    cs:__imp_SetUnhandledExceptionFilter
0x180002d75  mov     rcx, rbx; ExceptionInfo
0x180002d78  call    cs:__imp_UnhandledExceptionFilter
0x180002d7e  call    cs:__imp_GetCurrentProcess
0x180002d84  mov     rcx, rax
0x180002d87  mov     edx, 0C0000409h
0x180002d8c  add     rsp, 20h
0x180002d90  pop     rbx
0x180002d91  jmp     cs:__imp_TerminateProcess
```
