# __raise_securityfailure

- ea: `0x180003994`
- end: `0x1800039c8`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800039d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800039a8`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800039a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000399f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000399f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800039ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800039ae`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800039c1`

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
0x180003994  push    rbx
0x180003996  sub     rsp, 20h
0x18000399a  mov     rbx, rcx
0x18000399d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000399f  call    cs:__imp_SetUnhandledExceptionFilter
0x1800039a5  mov     rcx, rbx; ExceptionInfo
0x1800039a8  call    cs:__imp_UnhandledExceptionFilter
0x1800039ae  call    cs:__imp_GetCurrentProcess
0x1800039b4  mov     rcx, rax
0x1800039b7  mov     edx, 0C0000409h
0x1800039bc  add     rsp, 20h
0x1800039c0  pop     rbx
0x1800039c1  jmp     cs:__imp_TerminateProcess
```
