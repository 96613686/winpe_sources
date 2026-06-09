# __raise_securityfailure

- ea: `0x180001214`
- end: `0x180001248`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800013e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001241`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000122e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000122e`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000121f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000121f`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001228`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001228`

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
0x180001214  push    rbx
0x180001216  sub     rsp, 20h
0x18000121a  mov     rbx, rcx
0x18000121d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000121f  call    cs:__imp_SetUnhandledExceptionFilter
0x180001225  mov     rcx, rbx; ExceptionInfo
0x180001228  call    cs:__imp_UnhandledExceptionFilter
0x18000122e  call    cs:__imp_GetCurrentProcess
0x180001234  mov     rcx, rax
0x180001237  mov     edx, 0C0000409h
0x18000123c  add     rsp, 20h
0x180001240  pop     rbx
0x180001241  jmp     cs:__imp_TerminateProcess
```
