# __raise_securityfailure

- ea: `0x18000ef74`
- end: `0x18000efa8`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000efb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ef8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ef8e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000efa1`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000ef88`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x18000ef88`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000ef7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000ef7f`

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
0x18000ef74  push    rbx
0x18000ef76  sub     rsp, 20h
0x18000ef7a  mov     rbx, rcx
0x18000ef7d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000ef7f  call    cs:__imp_SetUnhandledExceptionFilter
0x18000ef85  mov     rcx, rbx; ExceptionInfo
0x18000ef88  call    cs:__imp_UnhandledExceptionFilter
0x18000ef8e  call    cs:__imp_GetCurrentProcess
0x18000ef94  mov     rcx, rax
0x18000ef97  mov     edx, 0C0000409h
0x18000ef9c  add     rsp, 20h
0x18000efa0  pop     rbx
0x18000efa1  jmp     cs:__imp_TerminateProcess
```
