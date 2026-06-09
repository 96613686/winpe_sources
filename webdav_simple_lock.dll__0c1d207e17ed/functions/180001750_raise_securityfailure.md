# __raise_securityfailure

- ea: `0x180001750`
- end: `0x180001784`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001790`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000176a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000176a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000177d`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000175b`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000175b`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001764`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001764`

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
0x180001750  push    rbx
0x180001752  sub     rsp, 20h
0x180001756  mov     rbx, rcx
0x180001759  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000175b  call    cs:__imp_SetUnhandledExceptionFilter
0x180001761  mov     rcx, rbx; ExceptionInfo
0x180001764  call    cs:__imp_UnhandledExceptionFilter
0x18000176a  call    cs:__imp_GetCurrentProcess
0x180001770  mov     rcx, rax
0x180001773  mov     edx, 0C0000409h
0x180001778  add     rsp, 20h
0x18000177c  pop     rbx
0x18000177d  jmp     cs:__imp_TerminateProcess
```
