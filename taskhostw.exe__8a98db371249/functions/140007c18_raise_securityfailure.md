# __raise_securityfailure

- ea: `0x140007c18`
- end: `0x140007c4c`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140007c60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140007c32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140007c32`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140007c45`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140007c23`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140007c23`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140007c2c`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140007c2c`

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
0x140007c18  push    rbx
0x140007c1a  sub     rsp, 20h
0x140007c1e  mov     rbx, rcx
0x140007c21  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140007c23  call    cs:__imp_SetUnhandledExceptionFilter
0x140007c29  mov     rcx, rbx; ExceptionInfo
0x140007c2c  call    cs:__imp_UnhandledExceptionFilter
0x140007c32  call    cs:__imp_GetCurrentProcess
0x140007c38  mov     rcx, rax
0x140007c3b  mov     edx, 0C0000409h
0x140007c40  add     rsp, 20h
0x140007c44  pop     rbx
0x140007c45  jmp     cs:__imp_TerminateProcess
```
