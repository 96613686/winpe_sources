# __raise_securityfailure

- ea: `0x18001872c`
- end: `0x180018760`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180018770`
- `0x180018918`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180018740`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180018740`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180018737`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180018737`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180018759`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018746`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018746`

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
0x18001872c  push    rbx
0x18001872e  sub     rsp, 20h
0x180018732  mov     rbx, rcx
0x180018735  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180018737  call    cs:__imp_SetUnhandledExceptionFilter
0x18001873d  mov     rcx, rbx; ExceptionInfo
0x180018740  call    cs:__imp_UnhandledExceptionFilter
0x180018746  call    cs:__imp_GetCurrentProcess
0x18001874c  mov     rcx, rax
0x18001874f  mov     edx, 0C0000409h
0x180018754  add     rsp, 20h
0x180018758  pop     rbx
0x180018759  jmp     cs:__imp_TerminateProcess
```
