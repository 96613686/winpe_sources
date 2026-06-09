# __raise_securityfailure

- ea: `0x180002234`
- end: `0x180002268`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002270`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180002248`
- `KERNEL32!UnhandledExceptionFilter` at `0x180002248`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000223f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18000223f`
- `KERNEL32!GetCurrentProcess` at `0x18000224e`
- `KERNEL32!GetCurrentProcess` at `0x18000224e`
- `KERNEL32!TerminateProcess` at `0x180002261`

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
0x180002234  push    rbx
0x180002236  sub     rsp, 20h
0x18000223a  mov     rbx, rcx
0x18000223d  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18000223f  call    cs:__imp_SetUnhandledExceptionFilter
0x180002245  mov     rcx, rbx; ExceptionInfo
0x180002248  call    cs:__imp_UnhandledExceptionFilter
0x18000224e  call    cs:__imp_GetCurrentProcess
0x180002254  mov     rcx, rax
0x180002257  mov     edx, 0C0000409h
0x18000225c  add     rsp, 20h
0x180002260  pop     rbx
0x180002261  jmp     cs:__imp_TerminateProcess
```
