# __raise_securityfailure

- ea: `0x18001e4b4`
- end: `0x18001e4e8`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001e4f0`
- `0x18001e698`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x18001e4e1`
- `KERNEL32!GetCurrentProcess` at `0x18001e4ce`
- `KERNEL32!GetCurrentProcess` at `0x18001e4ce`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18001e4bf`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x18001e4bf`
- `KERNEL32!UnhandledExceptionFilter` at `0x18001e4c8`
- `KERNEL32!UnhandledExceptionFilter` at `0x18001e4c8`

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
0x18001e4b4  push    rbx
0x18001e4b6  sub     rsp, 20h
0x18001e4ba  mov     rbx, rcx
0x18001e4bd  xor     ecx, ecx; lpTopLevelExceptionFilter
0x18001e4bf  call    cs:__imp_SetUnhandledExceptionFilter
0x18001e4c5  mov     rcx, rbx; ExceptionInfo
0x18001e4c8  call    cs:__imp_UnhandledExceptionFilter
0x18001e4ce  call    cs:__imp_GetCurrentProcess
0x18001e4d4  mov     rcx, rax
0x18001e4d7  mov     edx, 0C0000409h
0x18001e4dc  add     rsp, 20h
0x18001e4e0  pop     rbx
0x18001e4e1  jmp     cs:__imp_TerminateProcess
```
