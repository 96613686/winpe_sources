# __raise_securityfailure

- ea: `0x14000190c`
- end: `0x140001940`
- name: `__raise_securityfailure`
- size: `52`
- prototype: `BOOL __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001950`

## import_xrefs

- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001917`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x140001917`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001920`
- `KERNEL32!UnhandledExceptionFilter` at `0x140001920`
- `KERNEL32!GetCurrentProcess` at `0x140001926`
- `KERNEL32!GetCurrentProcess` at `0x140001926`
- `KERNEL32!TerminateProcess` at `0x140001939`

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
0x14000190c  push    rbx
0x14000190e  sub     rsp, 20h
0x140001912  mov     rbx, rcx
0x140001915  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140001917  call    cs:__imp_SetUnhandledExceptionFilter
0x14000191d  mov     rcx, rbx; ExceptionInfo
0x140001920  call    cs:__imp_UnhandledExceptionFilter
0x140001926  call    cs:__imp_GetCurrentProcess
0x14000192c  mov     rcx, rax
0x14000192f  mov     edx, 0C0000409h
0x140001934  add     rsp, 20h
0x140001938  pop     rbx
0x140001939  jmp     cs:__imp_TerminateProcess
```
