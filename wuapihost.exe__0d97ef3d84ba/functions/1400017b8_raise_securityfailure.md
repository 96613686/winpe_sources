# __raise_securityfailure

- ea: `0x1400017b8`
- end: `0x1400017ec`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1400017cc`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1400017cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1400017c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1400017c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400017d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400017d2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1400017e5`

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
0x1400017b8  push    rbx
0x1400017ba  sub     rsp, 20h
0x1400017be  mov     rbx, rcx
0x1400017c1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1400017c3  call    cs:__imp_SetUnhandledExceptionFilter
0x1400017c9  mov     rcx, rbx; ExceptionInfo
0x1400017cc  call    cs:__imp_UnhandledExceptionFilter
0x1400017d2  call    cs:__imp_GetCurrentProcess
0x1400017d8  mov     rcx, rax
0x1400017db  mov     edx, 0C0000409h
0x1400017e0  add     rsp, 20h
0x1400017e4  pop     rbx
0x1400017e5  jmp     cs:__imp_TerminateProcess
```
