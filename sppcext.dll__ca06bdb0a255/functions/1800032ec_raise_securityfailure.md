# __raise_securityfailure

- ea: `0x1800032ec`
- end: `0x180003320`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003330`
- `0x1800034d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800032f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1800032f7`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180003300`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180003300`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180003319`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003306`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003306`

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
0x1800032ec  push    rbx
0x1800032ee  sub     rsp, 20h
0x1800032f2  mov     rbx, rcx
0x1800032f5  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800032f7  call    cs:SetUnhandledExceptionFilter
0x1800032fd  mov     rcx, rbx; ExceptionInfo
0x180003300  call    cs:UnhandledExceptionFilter
0x180003306  call    cs:GetCurrentProcess
0x18000330c  mov     rcx, rax
0x18000330f  mov     edx, 0C0000409h
0x180003314  add     rsp, 20h
0x180003318  pop     rbx
0x180003319  jmp     cs:TerminateProcess
```
