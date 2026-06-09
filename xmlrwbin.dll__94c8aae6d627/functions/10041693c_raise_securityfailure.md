# __raise_securityfailure

- ea: `0x10041693c`
- end: `0x100416970`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x100416980`
- `0x100416a74`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x100416950`
- `KERNEL32!UnhandledExceptionFilter` at `0x100416950`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x100416947`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x100416947`
- `KERNEL32!GetCurrentProcess` at `0x100416956`
- `KERNEL32!GetCurrentProcess` at `0x100416956`
- `KERNEL32!TerminateProcess` at `0x100416969`

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
0x10041693c  push    rbx
0x10041693e  sub     rsp, 20h
0x100416942  mov     rbx, rcx
0x100416945  xor     ecx, ecx; lpTopLevelExceptionFilter
0x100416947  call    cs:__imp_SetUnhandledExceptionFilter
0x10041694d  mov     rcx, rbx; ExceptionInfo
0x100416950  call    cs:__imp_UnhandledExceptionFilter
0x100416956  call    cs:__imp_GetCurrentProcess
0x10041695c  mov     rcx, rax
0x10041695f  mov     edx, 0C0000409h
0x100416964  add     rsp, 20h
0x100416968  pop     rbx
0x100416969  jmp     cs:__imp_TerminateProcess
```
