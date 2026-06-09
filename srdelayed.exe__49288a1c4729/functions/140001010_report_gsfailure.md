# __report_gsfailure

- ea: `0x140001010`
- end: `0x140001187`
- name: `__report_gsfailure`
- size: `375`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003770`

## callees

- `0x140001010`
- `0x140001240`
- `0x14000124c`
- `0x140001258`
- `0x140001264`
- `0x140001270`

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
  qword_140005170 = ContextRecord.Rip;
  ContextRecord.Rcx = v7;
  dword_140005160 = -1073740791;
  dword_140005164 = 1;
  dword_140005178 = 1;
  qword_140005180[0] = 2;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  RtlUnhandledExceptionFilter_0((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
  NtTerminateProcess_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, -1073740791);
}

```

## disassembly

```asm
0x140001010  mov     [rsp+arg_0], rcx
0x140001015  sub     rsp, 88h
0x14000101c  mov     [rsp+88h+ControlPc], 0
0x140001025  mov     [rsp+88h+var_30], 0
0x14000102e  mov     [rsp+88h+FunctionEntry], 0
0x140001037  mov     [rsp+88h+var_28], 0
0x140001040  mov     [rsp+88h+ImageBase], 0
0x140001049  lea     rcx, ContextRecord; ContextRecord
0x140001050  call    RtlCaptureContext_0
0x140001055  mov     rax, cs:ContextRecord.Rip
0x14000105c  mov     [rsp+88h+ControlPc], rax
0x140001061  xor     r8d, r8d; HistoryTable
0x140001064  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x140001069  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x14000106e  call    RtlLookupFunctionEntry_0
0x140001073  mov     [rsp+88h+FunctionEntry], rax
0x140001078  cmp     [rsp+88h+FunctionEntry], 0
0x14000107e  jz      short loc_1400010C2
0x140001080  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x140001089  lea     rax, [rsp+88h+var_30]
0x14000108e  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x140001093  lea     rax, [rsp+88h+var_28]
0x140001098  mov     [rsp+88h+HandlerData], rax; HandlerData
0x14000109d  lea     rax, ContextRecord
0x1400010a4  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1400010a9  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1400010ae  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1400010b3  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1400010b8  xor     ecx, ecx; HandlerType
0x1400010ba  call    RtlVirtualUnwind_0
0x1400010bf  nop
0x1400010c0  jmp     short loc_1400010E4
0x1400010c2  mov     rax, [rsp+88h]
0x1400010ca  mov     cs:ContextRecord.Rip, rax
0x1400010d1  lea     rax, [rsp+88h]
0x1400010d9  add     rax, 8
0x1400010dd  mov     cs:ContextRecord.Rsp, rax
0x1400010e4  mov     rax, cs:ContextRecord.Rip
0x1400010eb  mov     cs:qword_140005170, rax
0x1400010f2  mov     rax, [rsp+88h+arg_0]
0x1400010fa  mov     cs:ContextRecord.Rcx, rax
0x140001101  mov     cs:dword_140005160, 0C0000409h
0x14000110b  mov     cs:dword_140005164, 1
0x140001115  mov     cs:dword_140005178, 1
0x14000111f  mov     eax, 8
0x140001124  imul    rax, 0
0x140001128  lea     rcx, qword_140005180
0x14000112f  mov     qword ptr [rcx+rax], 2
0x140001137  mov     eax, 8
0x14000113c  imul    rax, 0
0x140001140  mov     rcx, cs:__security_cookie
0x140001147  mov     [rsp+rax+88h+var_20], rcx
0x14000114c  mov     eax, 8
0x140001151  imul    rax, 1
0x140001155  mov     rcx, cs:__security_cookie_complement
0x14000115c  mov     [rsp+rax+88h+var_20], rcx
0x140001161  lea     rcx, ExceptionInfo; ExceptionInfo
0x140001168  call    RtlUnhandledExceptionFilter_0
0x14000116d  mov     edx, 0C0000409h; ExitStatus
0x140001172  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140001179  call    NtTerminateProcess_0
0x14000117e  nop
0x14000117f  add     rsp, 88h
0x140001186  retn
```
