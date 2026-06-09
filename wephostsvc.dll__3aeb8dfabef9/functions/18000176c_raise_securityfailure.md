# __raise_securityfailure

- ea: `0x18000176c`
- end: `0x1800017a0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800017b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001777`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001777`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001780`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001780`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001786`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001786`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001799`

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
0x18000176c  push    rbx
0x18000176e  sub     rsp, 20h
0x180001772  mov     rbx, rcx
0x180001775  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001777  call    cs:__imp_SetUnhandledExceptionFilter
0x18000177d  mov     rcx, rbx; ExceptionInfo
0x180001780  call    cs:__imp_UnhandledExceptionFilter
0x180001786  call    cs:__imp_GetCurrentProcess
0x18000178c  mov     rcx, rax
0x18000178f  mov     edx, 0C0000409h
0x180001794  add     rsp, 20h
0x180001798  pop     rbx
0x180001799  jmp     cs:__imp_TerminateProcess
```
