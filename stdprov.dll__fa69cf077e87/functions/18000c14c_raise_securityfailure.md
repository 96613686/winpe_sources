# __raise_securityfailure

- ea: `0x18000c14c`
- end: `0x18000c180`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000c190`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000c160`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000c160`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000c157`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000c157`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000c179`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c166`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c166`

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
0x18000c14c  push    rbx
0x18000c14e  sub     rsp, 20h
0x18000c152  mov     rbx, rcx
0x18000c155  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000c157  call    cs:__imp_SetUnhandledExceptionFilter
0x18000c15d  mov     rcx, rbx; ExceptionInfo
0x18000c160  call    cs:__imp_UnhandledExceptionFilter
0x18000c166  call    cs:__imp_GetCurrentProcess
0x18000c16c  mov     rcx, rax
0x18000c16f  mov     edx, 0C0000409h
0x18000c174  add     rsp, 20h
0x18000c178  pop     rbx
0x18000c179  jmp     cs:__imp_TerminateProcess
```
