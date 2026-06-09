# __report_gsfailure

- ea: `0x180006400`
- end: `0x180006577`
- name: `__report_gsfailure`
- size: `375`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006cf0`

## callees

- `0x180006400`
- `0x18000669c`
- `0x1800066a8`
- `0x1800066b4`
- `0x1800066c0`
- `0x1800066cc`

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
  qword_18000B0F0 = ContextRecord.Rip;
  ContextRecord.Rcx = v7;
  dword_18000B0E0 = -1073740791;
  dword_18000B0E4 = 1;
  dword_18000B0F8 = 1;
  qword_18000B100[0] = 2;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  RtlUnhandledExceptionFilter_0((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
  NtTerminateProcess_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, -1073740791);
}

```

## disassembly

```asm
0x180006400  mov     [rsp+arg_0], rcx
0x180006405  sub     rsp, 88h
0x18000640c  mov     [rsp+88h+ControlPc], 0
0x180006415  mov     [rsp+88h+var_30], 0
0x18000641e  mov     [rsp+88h+FunctionEntry], 0
0x180006427  mov     [rsp+88h+var_28], 0
0x180006430  mov     [rsp+88h+ImageBase], 0
0x180006439  lea     rcx, ContextRecord; ContextRecord
0x180006440  call    RtlCaptureContext_0
0x180006445  mov     rax, cs:ContextRecord.Rip
0x18000644c  mov     [rsp+88h+ControlPc], rax
0x180006451  xor     r8d, r8d; HistoryTable
0x180006454  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180006459  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000645e  call    RtlLookupFunctionEntry_0
0x180006463  mov     [rsp+88h+FunctionEntry], rax
0x180006468  cmp     [rsp+88h+FunctionEntry], 0
0x18000646e  jz      short loc_1800064B2
0x180006470  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180006479  lea     rax, [rsp+88h+var_30]
0x18000647e  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180006483  lea     rax, [rsp+88h+var_28]
0x180006488  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000648d  lea     rax, ContextRecord
0x180006494  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180006499  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x18000649e  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800064a3  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800064a8  xor     ecx, ecx; HandlerType
0x1800064aa  call    RtlVirtualUnwind_0
0x1800064af  nop
0x1800064b0  jmp     short loc_1800064D4
0x1800064b2  mov     rax, [rsp+88h]
0x1800064ba  mov     cs:ContextRecord.Rip, rax
0x1800064c1  lea     rax, [rsp+88h]
0x1800064c9  add     rax, 8
0x1800064cd  mov     cs:ContextRecord.Rsp, rax
0x1800064d4  mov     rax, cs:ContextRecord.Rip
0x1800064db  mov     cs:qword_18000B0F0, rax
0x1800064e2  mov     rax, [rsp+88h+arg_0]
0x1800064ea  mov     cs:ContextRecord.Rcx, rax
0x1800064f1  mov     cs:dword_18000B0E0, 0C0000409h
0x1800064fb  mov     cs:dword_18000B0E4, 1
0x180006505  mov     cs:dword_18000B0F8, 1
0x18000650f  mov     eax, 8
0x180006514  imul    rax, 0
0x180006518  lea     rcx, qword_18000B100
0x18000651f  mov     qword ptr [rcx+rax], 2
0x180006527  mov     eax, 8
0x18000652c  imul    rax, 0
0x180006530  mov     rcx, cs:__security_cookie
0x180006537  mov     [rsp+rax+88h+var_20], rcx
0x18000653c  mov     eax, 8
0x180006541  imul    rax, 1
0x180006545  mov     rcx, cs:__security_cookie_complement
0x18000654c  mov     [rsp+rax+88h+var_20], rcx
0x180006551  lea     rcx, ExceptionInfo; ExceptionInfo
0x180006558  call    RtlUnhandledExceptionFilter_0
0x18000655d  mov     edx, 0C0000409h; ExitStatus
0x180006562  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180006569  call    NtTerminateProcess_0
0x18000656e  nop
0x18000656f  add     rsp, 88h
0x180006576  retn
```
