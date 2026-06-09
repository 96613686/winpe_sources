# __raise_securityfailure

- ea: `0x180009598`
- end: `0x1800095cc`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800095e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800095ac`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800095ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800095a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800095a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800095b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800095b2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800095c5`

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
0x180009598  push    rbx
0x18000959a  sub     rsp, 20h
0x18000959e  mov     rbx, rcx
0x1800095a1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800095a3  call    cs:__imp_SetUnhandledExceptionFilter
0x1800095a9  mov     rcx, rbx; ExceptionInfo
0x1800095ac  call    cs:__imp_UnhandledExceptionFilter
0x1800095b2  call    cs:__imp_GetCurrentProcess
0x1800095b8  mov     rcx, rax
0x1800095bb  mov     edx, 0C0000409h
0x1800095c0  add     rsp, 20h
0x1800095c4  pop     rbx
0x1800095c5  jmp     cs:__imp_TerminateProcess
```
