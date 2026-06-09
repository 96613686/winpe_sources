# __raise_securityfailure

- ea: `0x180001c08`
- end: `0x180001c3c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001c50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001c13`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001c13`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001c1c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001c1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001c22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001c22`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001c35`

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
0x180001c08  push    rbx
0x180001c0a  sub     rsp, 20h
0x180001c0e  mov     rbx, rcx
0x180001c11  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001c13  call    cs:__imp_SetUnhandledExceptionFilter
0x180001c19  mov     rcx, rbx; ExceptionInfo
0x180001c1c  call    cs:__imp_UnhandledExceptionFilter
0x180001c22  call    cs:__imp_GetCurrentProcess
0x180001c28  mov     rcx, rax
0x180001c2b  mov     edx, 0C0000409h
0x180001c30  add     rsp, 20h
0x180001c34  pop     rbx
0x180001c35  jmp     cs:__imp_TerminateProcess
```
