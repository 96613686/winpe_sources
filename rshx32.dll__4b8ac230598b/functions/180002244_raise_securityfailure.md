# __raise_securityfailure

- ea: `0x180002244`
- end: `0x180002278`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002258`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180002258`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000224f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x18000224f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000225e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000225e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002271`

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
0x180002244  push    rbx
0x180002246  sub     rsp, 20h
0x18000224a  mov     rbx, rcx
0x18000224d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000224f  call    cs:__imp_SetUnhandledExceptionFilter
0x180002255  mov     rcx, rbx; ExceptionInfo
0x180002258  call    cs:__imp_UnhandledExceptionFilter
0x18000225e  call    cs:__imp_GetCurrentProcess
0x180002264  mov     rcx, rax
0x180002267  mov     edx, 0C0000409h
0x18000226c  add     rsp, 20h
0x180002270  pop     rbx
0x180002271  jmp     cs:__imp_TerminateProcess
```
