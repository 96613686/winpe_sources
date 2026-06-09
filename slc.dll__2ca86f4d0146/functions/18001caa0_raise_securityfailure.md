# __raise_securityfailure

- ea: `0x18001caa0`
- end: `0x18001cad4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001cae0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001caab`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18001caab`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18001cab4`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18001cab4`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18001cacd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001caba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001caba`

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
0x18001caa0  push    rbx
0x18001caa2  sub     rsp, 20h
0x18001caa6  mov     rbx, rcx
0x18001caa9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18001caab  call    cs:SetUnhandledExceptionFilter
0x18001cab1  mov     rcx, rbx; ExceptionInfo
0x18001cab4  call    cs:UnhandledExceptionFilter
0x18001caba  call    cs:GetCurrentProcess
0x18001cac0  mov     rcx, rax
0x18001cac3  mov     edx, 0C0000409h
0x18001cac8  add     rsp, 20h
0x18001cacc  pop     rbx
0x18001cacd  jmp     cs:TerminateProcess
```
