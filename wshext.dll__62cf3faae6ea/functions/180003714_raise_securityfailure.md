# __raise_securityfailure

- ea: `0x180003714`
- end: `0x180003748`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003750`
- `0x1800038f8`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180003741`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000371f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000371f`
- `KERNEL32!UnhandledExceptionFilter` at `0x180003728`
- `KERNEL32!UnhandledExceptionFilter` at `0x180003728`
- `KERNEL32!GetCurrentProcess` at `0x18000372e`
- `KERNEL32!GetCurrentProcess` at `0x18000372e`

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
0x180003714  push    rbx
0x180003716  sub     rsp, 20h
0x18000371a  mov     rbx, rcx
0x18000371d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000371f  call    cs:__imp_SetUnhandledExceptionFilter
0x180003725  mov     rcx, rbx; ExceptionInfo
0x180003728  call    cs:__imp_UnhandledExceptionFilter
0x18000372e  call    cs:__imp_GetCurrentProcess
0x180003734  mov     rcx, rax
0x180003737  mov     edx, 0C0000409h
0x18000373c  add     rsp, 20h
0x180003740  pop     rbx
0x180003741  jmp     cs:__imp_TerminateProcess
```
