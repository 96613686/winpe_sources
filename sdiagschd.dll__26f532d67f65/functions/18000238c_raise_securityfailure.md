# __raise_securityfailure

- ea: `0x18000238c`
- end: `0x1800023c0`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800023d0`

## import_xrefs

- `KERNEL32!TerminateProcess` at `0x1800023b9`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002397`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x180002397`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800023a0`
- `KERNEL32!UnhandledExceptionFilter` at `0x1800023a0`
- `KERNEL32!GetCurrentProcess` at `0x1800023a6`
- `KERNEL32!GetCurrentProcess` at `0x1800023a6`

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
0x18000238c  push    rbx
0x18000238e  sub     rsp, 20h
0x180002392  mov     rbx, rcx
0x180002395  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180002397  call    cs:__imp_SetUnhandledExceptionFilter
0x18000239d  mov     rcx, rbx; ExceptionInfo
0x1800023a0  call    cs:__imp_UnhandledExceptionFilter
0x1800023a6  call    cs:__imp_GetCurrentProcess
0x1800023ac  mov     rcx, rax
0x1800023af  mov     edx, 0C0000409h
0x1800023b4  add     rsp, 20h
0x1800023b8  pop     rbx
0x1800023b9  jmp     cs:__imp_TerminateProcess
```
