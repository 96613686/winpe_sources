# __raise_securityfailure

- ea: `0x140002414`
- end: `0x140002448`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002450`
- `0x1400025f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000241f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14000241f`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002428`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x140002428`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000242e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000242e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140002441`

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
0x140002414  push    rbx
0x140002416  sub     rsp, 20h
0x14000241a  mov     rbx, rcx
0x14000241d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x14000241f  call    cs:__imp_SetUnhandledExceptionFilter
0x140002425  mov     rcx, rbx; ExceptionInfo
0x140002428  call    cs:__imp_UnhandledExceptionFilter
0x14000242e  call    cs:__imp_GetCurrentProcess
0x140002434  mov     rcx, rax
0x140002437  mov     edx, 0C0000409h
0x14000243c  add     rsp, 20h
0x140002440  pop     rbx
0x140002441  jmp     cs:__imp_TerminateProcess
```
