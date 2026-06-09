# __raise_securityfailure

- ea: `0x1800157b0`
- end: `0x1800157e4`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800157f0`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x1800157c4`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800157c4`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800157bb`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1800157bb`
- `KERNEL32!GetCurrentProcess` at `0x1800157ca`
- `KERNEL32!GetCurrentProcess` at `0x1800157ca`
- `KERNEL32!TerminateProcess` at `0x1800157dd`

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
0x1800157b0  push    rbx
0x1800157b2  sub     rsp, 20h
0x1800157b6  mov     rbx, rcx
0x1800157b9  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1800157bb  call    cs:__imp_SetUnhandledExceptionFilter
0x1800157c1  mov     rcx, rbx; ExceptionInfo
0x1800157c4  call    cs:__imp_UnhandledExceptionFilter
0x1800157ca  call    cs:__imp_GetCurrentProcess
0x1800157d0  mov     rcx, rax
0x1800157d3  mov     edx, 0C0000409h
0x1800157d8  add     rsp, 20h
0x1800157dc  pop     rbx
0x1800157dd  jmp     cs:__imp_TerminateProcess
```
