# __raise_securityfailure

- ea: `0x180002048`
- end: `0x18000207c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002090`
- `0x180002238`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002053`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180002053`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000205c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000205c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002075`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002062`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002062`

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
0x180002048  push    rbx
0x18000204a  sub     rsp, 20h
0x18000204e  mov     rbx, rcx
0x180002051  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002053  call    cs:__imp_SetUnhandledExceptionFilter
0x180002059  mov     rcx, rbx; ExceptionInfo
0x18000205c  call    cs:__imp_UnhandledExceptionFilter
0x180002062  call    cs:__imp_GetCurrentProcess
0x180002068  mov     rcx, rax
0x18000206b  mov     edx, 0C0000409h
0x180002070  add     rsp, 20h
0x180002074  pop     rbx
0x180002075  jmp     cs:__imp_TerminateProcess
```
