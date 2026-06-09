# RpcpReportFatalError

- ea: `0x18001b930`
- end: `0x18001b9ab`
- name: `RpcpReportFatalError`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007be0`
- `0x180008b30`
- `0x180009aa4`
- `0x18000a4ec`
- `0x18000ab40`
- `0x18000b780`
- `0x18000f74c`
- `0x180012110`
- `0x18001adac`
- `0x18001f9f4`
- `0x18001fc58`
- `0x18002129c`

## callees

- `0x18001b930`
- `0x180024629`

## import_xrefs

- `ntdll!RtlRaiseException` at `0x18001b992`
- `ntdll!RtlRaiseException` at `0x18001b992`
- `ntdll!RtlReportException` at `0x18002470c`
- `ntdll!RtlReportException` at `0x18002470c`
- `KERNEL32!GetCurrentProcess` at `0x18002471b`
- `KERNEL32!GetCurrentProcess` at `0x18002471b`
- `KERNEL32!TerminateProcess` at `0x180024726`
- `KERNEL32!TerminateProcess` at `0x180024726`

## pseudocode

```c
void __fastcall RpcpReportFatalError(ULONG_PTR a1, ULONG_PTR a2)
{
  struct _EXCEPTION_RECORD ExceptionRecord; // [rsp+30h] [rbp-A8h] BYREF

  memset_0(&ExceptionRecord, 0, sizeof(ExceptionRecord));
  ExceptionRecord.ExceptionCode = -1073610685;
  ExceptionRecord.ExceptionFlags = 0;
  ExceptionRecord.ExceptionRecord = 0;
  ExceptionRecord.ExceptionAddress = RpcpReportFatalError;
  ExceptionRecord.NumberParameters = 2;
  ExceptionRecord.ExceptionInformation[0] = a1;
  ExceptionRecord.ExceptionInformation[1] = a2;
  RtlRaiseException(&ExceptionRecord);
}

```

## disassembly

```asm
0x18001b930  mov     [rsp+arg_0], rbx
0x18001b935  push    rdi
0x18001b936  sub     rsp, 0D0h
0x18001b93d  mov     rbx, rdx
0x18001b940  mov     rdi, rcx
0x18001b943  xor     edx, edx; Val
0x18001b945  mov     r8d, 98h; Size
0x18001b94b  lea     rcx, [rsp+0D8h+ExceptionRecord]; void *
0x18001b950  call    memset_0
0x18001b955  nop
0x18001b956  mov     [rsp+0D8h+ExceptionRecord.ExceptionCode], 0C0020043h
0x18001b95e  mov     [rsp+0D8h+ExceptionRecord.ExceptionFlags], 0
0x18001b966  mov     [rsp+0D8h+ExceptionRecord.ExceptionRecord], 0
0x18001b96f  lea     rax, RpcpReportFatalError
0x18001b976  mov     [rsp+0D8h+ExceptionRecord.ExceptionAddress], rax
0x18001b97b  mov     [rsp+0D8h+ExceptionRecord.NumberParameters], 2
0x18001b983  mov     [rsp+0D8h+ExceptionRecord.ExceptionInformation], rdi
0x18001b988  mov     [rsp+0D8h+ExceptionRecord.ExceptionInformation+8], rbx
0x18001b98d  lea     rcx, [rsp+0D8h+ExceptionRecord]; ExceptionRecord
0x18001b992  call    cs:__imp_RtlRaiseException
0x18001b998  jmp     short $+2
0x18001b99a  mov     rbx, [rsp+0D8h+arg_0]
0x18001b9a2  add     rsp, 0D0h
0x18001b9a9  pop     rdi
0x18001b9aa  retn
0x1800246ec  push    rbx
0x1800246ee  push    rbp
0x1800246ef  sub     rsp, 28h
0x1800246f3  mov     rbp, rdx
0x1800246f6  mov     [rbp+28h], rcx
0x1800246fa  mov     rax, [rbp+28h]
0x1800246fe  mov     rdx, [rax+8]
0x180024702  mov     rcx, [rbp+28h]
0x180024706  xor     r8d, r8d
0x180024709  mov     rcx, [rcx]
0x18002470c  call    cs:__imp_RtlReportException
0x180024712  mov     rax, [rbp+28h]
0x180024716  mov     rcx, [rax]
0x180024719  mov     ebx, [rcx]
0x18002471b  call    cs:__imp_GetCurrentProcess
0x180024721  mov     edx, ebx; uExitCode
0x180024723  mov     rcx, rax; hProcess
0x180024726  call    cs:__imp_TerminateProcess
0x18002472c  mov     dword ptr [rbp+20h], 0
0x180024733  mov     eax, [rbp+20h]
0x180024736  add     rsp, 28h
0x18002473a  pop     rbp
0x18002473b  pop     rbx
0x18002473c  retn
```
