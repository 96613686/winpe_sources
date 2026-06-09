# __raise_securityfailure

- ea: `0x180008d28`
- end: `0x180008d5c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180008d70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180008d3c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180008d3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180008d33`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180008d33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008d42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008d42`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180008d55`

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
0x180008d28  push    rbx
0x180008d2a  sub     rsp, 20h
0x180008d2e  mov     rbx, rcx
0x180008d31  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180008d33  call    cs:__imp_SetUnhandledExceptionFilter
0x180008d39  mov     rcx, rbx; ExceptionInfo
0x180008d3c  call    cs:__imp_UnhandledExceptionFilter
0x180008d42  call    cs:__imp_GetCurrentProcess
0x180008d48  mov     rcx, rax
0x180008d4b  mov     edx, 0C0000409h
0x180008d50  add     rsp, 20h
0x180008d54  pop     rbx
0x180008d55  jmp     cs:__imp_TerminateProcess
```
