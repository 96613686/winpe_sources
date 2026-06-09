# __raise_securityfailure

- ea: `0x180004094`
- end: `0x1800040c8`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800040d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800040c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800040ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800040ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000409f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000409f`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800040a8`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1800040a8`

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
0x180004094  push    rbx
0x180004096  sub     rsp, 20h
0x18000409a  mov     rbx, rcx
0x18000409d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000409f  call    cs:SetUnhandledExceptionFilter
0x1800040a5  mov     rcx, rbx; ExceptionInfo
0x1800040a8  call    cs:UnhandledExceptionFilter
0x1800040ae  call    cs:GetCurrentProcess
0x1800040b4  mov     rcx, rax
0x1800040b7  mov     edx, 0C0000409h
0x1800040bc  add     rsp, 20h
0x1800040c0  pop     rbx
0x1800040c1  jmp     cs:TerminateProcess
```
