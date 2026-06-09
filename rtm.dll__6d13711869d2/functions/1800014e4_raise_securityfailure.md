# __raise_securityfailure

- ea: `0x1800014e4`
- end: `0x180001518`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001520`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x180001511`
- `KERNEL32!GetCurrentProcess` at `0x1800014fe`
- `KERNEL32!GetCurrentProcess` at `0x1800014fe`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800014f8`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800014f8`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800014ef`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800014ef`

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
0x1800014e4  push    rbx
0x1800014e6  sub     rsp, 20h
0x1800014ea  mov     rbx, rcx
0x1800014ed  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800014ef  call    cs:__imp_SetUnhandledExceptionFilter
0x1800014f5  mov     rcx, rbx; ExceptionInfo
0x1800014f8  call    cs:__imp_UnhandledExceptionFilter
0x1800014fe  call    cs:__imp_GetCurrentProcess
0x180001504  mov     rcx, rax
0x180001507  mov     edx, 0C0000409h
0x18000150c  add     rsp, 20h
0x180001510  pop     rbx
0x180001511  jmp     cs:__imp_TerminateProcess
```
