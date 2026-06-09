# __report_rangecheckfailure

- ea: `0x140001338`
- end: `0x14000145e`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006004`
- `0x140008994`
- `0x14001550c`

## callees

- `0x14000114c`
- `0x140001338`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x140001370`
- `KERNEL32!RtlCaptureContext` at `0x140001370`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000138f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x14000138f`
- `KERNEL32!RtlVirtualUnwind` at `0x1400013dc`
- `KERNEL32!RtlVirtualUnwind` at `0x1400013dc`

## pseudocode

```c
void __noreturn _report_rangecheckfailure()
{
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *FunctionEntry; // [rsp+40h] [rbp-38h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-30h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-20h] BYREF
  PVOID HandlerData; // [rsp+60h] [rbp-18h] BYREF

  EstablisherFrame = 0;
  HandlerData = 0;
  ImageBase = 0;
  RtlCaptureContext(&ContextRecord);
  ControlPc = ContextRecord.Rip;
  FunctionEntry = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( FunctionEntry )
  {
    RtlVirtualUnwind(0, ImageBase, ControlPc, FunctionEntry, &ContextRecord, &HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = *(_QWORD *)ContextRecord.Rsp;
    ContextRecord.Rsp += 8LL;
  }
  qword_140020270 = ContextRecord.Rip;
  dword_140020260 = -1073740791;
  dword_140020264 = 1;
  dword_140020278 = 1;
  qword_140020280[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x140001338  sub     rsp, 78h
0x14000133c  mov     [rsp+78h+ControlPc], 0
0x140001345  mov     [rsp+78h+var_20], 0
0x14000134e  mov     [rsp+78h+FunctionEntry], 0
0x140001357  mov     [rsp+78h+var_18], 0
0x140001360  mov     [rsp+78h+ImageBase], 0
0x140001369  lea     rcx, ContextRecord; ContextRecord
0x140001370  call    cs:__imp_RtlCaptureContext
0x140001376  mov     rax, cs:ContextRecord.Rip
0x14000137d  mov     [rsp+78h+ControlPc], rax
0x140001382  xor     r8d, r8d; HistoryTable
0x140001385  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x14000138a  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x14000138f  call    cs:__imp_RtlLookupFunctionEntry
0x140001395  mov     [rsp+78h+FunctionEntry], rax
0x14000139a  cmp     [rsp+78h+FunctionEntry], 0
0x1400013a0  jz      short loc_1400013E5
0x1400013a2  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x1400013ab  lea     rax, [rsp+78h+var_20]
0x1400013b0  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x1400013b5  lea     rax, [rsp+78h+var_18]
0x1400013ba  mov     [rsp+78h+HandlerData], rax; HandlerData
0x1400013bf  lea     rax, ContextRecord
0x1400013c6  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x1400013cb  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x1400013d0  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x1400013d5  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x1400013da  xor     ecx, ecx; HandlerType
0x1400013dc  call    cs:__imp_RtlVirtualUnwind
0x1400013e2  nop
0x1400013e3  jmp     short loc_140001408
0x1400013e5  mov     rax, cs:ContextRecord.Rsp
0x1400013ec  mov     rax, [rax]
0x1400013ef  mov     cs:ContextRecord.Rip, rax
0x1400013f6  mov     rax, cs:ContextRecord.Rsp
0x1400013fd  add     rax, 8
0x140001401  mov     cs:ContextRecord.Rsp, rax
0x140001408  mov     rax, cs:ContextRecord.Rip
0x14000140f  mov     cs:qword_140020270, rax
0x140001416  mov     cs:dword_140020260, 0C0000409h
0x140001420  mov     cs:dword_140020264, 1
0x14000142a  mov     cs:dword_140020278, 1
0x140001434  mov     eax, 8
0x140001439  imul    rax, 0
0x14000143d  lea     rcx, qword_140020280
0x140001444  mov     qword ptr [rcx+rax], 8
0x14000144c  lea     rcx, ExceptionInfo; ExceptionInfo
0x140001453  call    __raise_securityfailure
0x140001458  nop
0x140001459  add     rsp, 78h
0x14000145d  retn
```
