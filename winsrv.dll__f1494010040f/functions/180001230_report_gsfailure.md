# __report_gsfailure

- ea: `0x180001230`
- end: `0x1800013a4`
- name: `__report_gsfailure`
- size: `372`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c80`

## callees

- `0x180001230`

## import_xrefs

- `ntdll!RtlVirtualUnwind` at `0x1800012dc`
- `ntdll!RtlVirtualUnwind` at `0x1800012dc`
- `ntdll!RtlCaptureContext` at `0x180001270`
- `ntdll!RtlCaptureContext` at `0x180001270`
- `ntdll!RtlLookupFunctionEntry` at `0x18000128f`
- `ntdll!RtlLookupFunctionEntry` at `0x18000128f`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001374`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180001374`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001381`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x180001381`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001387`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001387`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001395`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180001395`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  HANDLE CurrentProcess; // rax
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-48h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-40h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-30h] BYREF
  PVOID HandlerData[5]; // [rsp+60h] [rbp-28h] BYREF
  DWORD64 retaddr; // [rsp+88h] [rbp+0h]
  uintptr_t v8; // [rsp+90h] [rbp+8h] BYREF

  v8 = StackCookie;
  EstablisherFrame = 0;
  HandlerData[0] = 0;
  ImageBase = 0;
  RtlCaptureContext(&ContextRecord);
  ControlPc = ContextRecord.Rip;
  FunctionEntry = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( FunctionEntry )
  {
    RtlVirtualUnwind(0, ImageBase, ControlPc, FunctionEntry, &ContextRecord, HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = retaddr;
    ContextRecord.Rsp = (DWORD64)&v8;
  }
  qword_180005030 = ContextRecord.Rip;
  ContextRecord.Rcx = v8;
  dword_180005020 = -1073740791;
  dword_180005024 = 1;
  dword_180005038 = 1;
  qword_180005040[0] = 2;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  SetUnhandledExceptionFilter(0);
  UnhandledExceptionFilter((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, 0xC0000409);
}

```

## disassembly

```asm
0x180001230  mov     [rsp+arg_0], rcx
0x180001235  sub     rsp, 88h
0x18000123c  mov     [rsp+88h+ControlPc], 0
0x180001245  mov     [rsp+88h+var_30], 0
0x18000124e  mov     [rsp+88h+FunctionEntry], 0
0x180001257  mov     [rsp+88h+var_28], 0
0x180001260  mov     [rsp+88h+ImageBase], 0
0x180001269  lea     rcx, ContextRecord; ContextRecord
0x180001270  call    cs:__imp_RtlCaptureContext
0x180001276  mov     rax, cs:ContextRecord.Rip
0x18000127d  mov     [rsp+88h+ControlPc], rax
0x180001282  xor     r8d, r8d; HistoryTable
0x180001285  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000128a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000128f  call    cs:__imp_RtlLookupFunctionEntry
0x180001295  mov     [rsp+88h+FunctionEntry], rax
0x18000129a  cmp     [rsp+88h+FunctionEntry], 0
0x1800012a0  jz      short loc_1800012E5
0x1800012a2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800012ab  lea     rax, [rsp+88h+var_30]
0x1800012b0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800012b5  lea     rax, [rsp+88h+var_28]
0x1800012ba  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800012bf  lea     rax, ContextRecord
0x1800012c6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800012cb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800012d0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800012d5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800012da  xor     ecx, ecx; HandlerType
0x1800012dc  call    cs:__imp_RtlVirtualUnwind
0x1800012e2  nop
0x1800012e3  jmp     short loc_180001307
0x1800012e5  mov     rax, [rsp+88h]
0x1800012ed  mov     cs:ContextRecord.Rip, rax
0x1800012f4  lea     rax, [rsp+88h]
0x1800012fc  add     rax, 8
0x180001300  mov     cs:ContextRecord.Rsp, rax
0x180001307  mov     rax, cs:ContextRecord.Rip
0x18000130e  mov     cs:qword_180005030, rax
0x180001315  mov     rax, [rsp+88h+arg_0]
0x18000131d  mov     cs:ContextRecord.Rcx, rax
0x180001324  mov     cs:dword_180005020, 0C0000409h
0x18000132e  mov     cs:dword_180005024, 1
0x180001338  mov     cs:dword_180005038, 1
0x180001342  mov     eax, 8
0x180001347  imul    rax, 0
0x18000134b  lea     rcx, qword_180005040
0x180001352  mov     qword ptr [rcx+rax], 2
0x18000135a  mov     rax, cs:__security_cookie
0x180001361  mov     [rsp+88h+var_20], rax
0x180001366  mov     rax, cs:__security_cookie_complement
0x18000136d  mov     [rsp+88h+var_18], rax
0x180001372  xor     ecx, ecx; lpTopLevelExceptionFilter
0x180001374  call    cs:__imp_SetUnhandledExceptionFilter
0x18000137a  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001381  call    cs:__imp_UnhandledExceptionFilter
0x180001387  call    cs:__imp_GetCurrentProcess
0x18000138d  mov     edx, 0C0000409h; uExitCode
0x180001392  mov     rcx, rax; hProcess
0x180001395  call    cs:__imp_TerminateProcess
0x18000139b  nop
0x18000139c  add     rsp, 88h
0x1800013a3  retn
```
