# __report_gsfailure

- ea: `0x180006330`
- end: `0x1800064a5`
- name: `__report_gsfailure`
- size: `373`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006c30`

## callees

- `0x180006330`
- `0x1800065c8`
- `0x1800065d4`
- `0x1800065e0`
- `0x1800065ec`
- `0x1800065f8`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-48h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-40h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-30h] BYREF
  PVOID HandlerData[5]; // [rsp+60h] [rbp-28h] BYREF
  DWORD64 retaddr; // [rsp+88h] [rbp+0h]
  uintptr_t v7; // [rsp+90h] [rbp+8h] BYREF

  v7 = StackCookie;
  EstablisherFrame = 0;
  HandlerData[0] = 0;
  ImageBase = 0;
  RtlCaptureContext_0(&ContextRecord);
  ControlPc = ContextRecord.Rip;
  FunctionEntry = RtlLookupFunctionEntry_0(ContextRecord.Rip, &ImageBase, 0);
  if ( FunctionEntry )
  {
    RtlVirtualUnwind_0(0, ImageBase, ControlPc, FunctionEntry, &ContextRecord, HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = retaddr;
    ContextRecord.Rsp = (DWORD64)&v7;
  }
  qword_18000A0F0 = ContextRecord.Rip;
  ContextRecord.Rcx = v7;
  dword_18000A0E0 = -1073740791;
  dword_18000A0E4 = 1;
  dword_18000A0F8 = 1;
  qword_18000A100[0] = 2;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  RtlUnhandledExceptionFilter_0((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
  NtTerminateProcess_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, -1073740791);
}

```

## disassembly

```asm
0x180006330  mov     [rsp+arg_0], rcx
0x180006335  sub     rsp, 88h
0x18000633c  mov     [rsp+88h+ControlPc], 0
0x180006345  mov     [rsp+88h+var_30], 0
0x18000634e  mov     [rsp+88h+FunctionEntry], 0
0x180006357  mov     [rsp+88h+var_28], 0
0x180006360  mov     [rsp+88h+ImageBase], 0
0x180006369  lea     rcx, ContextRecord; ContextRecord
0x180006370  call    RtlCaptureContext_0
0x180006375  mov     rax, cs:ContextRecord.Rip
0x18000637c  mov     [rsp+88h+ControlPc], rax
0x180006381  xor     r8d, r8d; HistoryTable
0x180006384  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180006389  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000638e  call    RtlLookupFunctionEntry_0
0x180006393  mov     [rsp+88h+FunctionEntry], rax
0x180006398  cmp     [rsp+88h+FunctionEntry], 0
0x18000639e  jz      short loc_1800063E1
0x1800063a0  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800063a9  lea     rax, [rsp+88h+var_30]
0x1800063ae  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800063b3  lea     rax, [rsp+88h+var_28]
0x1800063b8  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800063bd  lea     rax, ContextRecord
0x1800063c4  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800063c9  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800063ce  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800063d3  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800063d8  xor     ecx, ecx; HandlerType
0x1800063da  call    RtlVirtualUnwind_0
0x1800063df  jmp     short loc_180006403
0x1800063e1  mov     rax, [rsp+88h]
0x1800063e9  mov     cs:ContextRecord.Rip, rax
0x1800063f0  lea     rax, [rsp+88h]
0x1800063f8  add     rax, 8
0x1800063fc  mov     cs:ContextRecord.Rsp, rax
0x180006403  mov     rax, cs:ContextRecord.Rip
0x18000640a  mov     cs:qword_18000A0F0, rax
0x180006411  mov     rax, [rsp+88h+arg_0]
0x180006419  mov     cs:ContextRecord.Rcx, rax
0x180006420  mov     cs:dword_18000A0E0, 0C0000409h
0x18000642a  mov     cs:dword_18000A0E4, 1
0x180006434  mov     cs:dword_18000A0F8, 1
0x18000643e  mov     eax, 8
0x180006443  imul    rax, 0
0x180006447  lea     rcx, qword_18000A100
0x18000644e  mov     qword ptr [rcx+rax], 2
0x180006456  mov     eax, 8
0x18000645b  imul    rax, 0
0x18000645f  mov     rcx, cs:__security_cookie
0x180006466  mov     [rsp+rax+88h+var_20], rcx
0x18000646b  mov     eax, 8
0x180006470  imul    rax, 1
0x180006474  mov     rcx, cs:__security_cookie_complement
0x18000647b  mov     [rsp+rax+88h+var_20], rcx
0x180006480  lea     rcx, ExceptionInfo; ExceptionInfo
0x180006487  call    RtlUnhandledExceptionFilter_0
0x18000648c  mov     edx, 0C0000409h; ExitStatus
0x180006491  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180006498  call    NtTerminateProcess_0
0x18000649d  add     rsp, 88h
0x1800064a4  retn
```
