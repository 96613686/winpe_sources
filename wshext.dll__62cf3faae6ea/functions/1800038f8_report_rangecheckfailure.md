# __report_rangecheckfailure

- ea: `0x1800038f8`
- end: `0x180003a1e`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004d28`
- `0x18000bbdc`

## callees

- `0x180003714`
- `0x1800038f8`

## import_xrefs

- `KERNEL32!RtlVirtualUnwind` at `0x18000399c`
- `KERNEL32!RtlVirtualUnwind` at `0x18000399c`
- `KERNEL32!RtlCaptureContext` at `0x180003930`
- `KERNEL32!RtlCaptureContext` at `0x180003930`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000394f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000394f`

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
  qword_1800142E0 = ContextRecord.Rip;
  dword_1800142D0 = -1073740791;
  dword_1800142D4 = 1;
  dword_1800142E8 = 1;
  qword_1800142F0[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800038f8  sub     rsp, 78h
0x1800038fc  mov     [rsp+78h+ControlPc], 0
0x180003905  mov     [rsp+78h+var_20], 0
0x18000390e  mov     [rsp+78h+FunctionEntry], 0
0x180003917  mov     [rsp+78h+var_18], 0
0x180003920  mov     [rsp+78h+ImageBase], 0
0x180003929  lea     rcx, ContextRecord; ContextRecord
0x180003930  call    cs:__imp_RtlCaptureContext
0x180003936  mov     rax, cs:ContextRecord.Rip
0x18000393d  mov     [rsp+78h+ControlPc], rax
0x180003942  xor     r8d, r8d; HistoryTable
0x180003945  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000394a  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x18000394f  call    cs:__imp_RtlLookupFunctionEntry
0x180003955  mov     [rsp+78h+FunctionEntry], rax
0x18000395a  cmp     [rsp+78h+FunctionEntry], 0
0x180003960  jz      short loc_1800039A5
0x180003962  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x18000396b  lea     rax, [rsp+78h+var_20]
0x180003970  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x180003975  lea     rax, [rsp+78h+var_18]
0x18000397a  mov     [rsp+78h+HandlerData], rax; HandlerData
0x18000397f  lea     rax, ContextRecord
0x180003986  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x18000398b  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x180003990  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x180003995  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000399a  xor     ecx, ecx; HandlerType
0x18000399c  call    cs:__imp_RtlVirtualUnwind
0x1800039a2  nop
0x1800039a3  jmp     short loc_1800039C8
0x1800039a5  mov     rax, cs:ContextRecord.Rsp
0x1800039ac  mov     rax, [rax]
0x1800039af  mov     cs:ContextRecord.Rip, rax
0x1800039b6  mov     rax, cs:ContextRecord.Rsp
0x1800039bd  add     rax, 8
0x1800039c1  mov     cs:ContextRecord.Rsp, rax
0x1800039c8  mov     rax, cs:ContextRecord.Rip
0x1800039cf  mov     cs:qword_1800142E0, rax
0x1800039d6  mov     cs:dword_1800142D0, 0C0000409h
0x1800039e0  mov     cs:dword_1800142D4, 1
0x1800039ea  mov     cs:dword_1800142E8, 1
0x1800039f4  mov     eax, 8
0x1800039f9  imul    rax, 0
0x1800039fd  lea     rcx, qword_1800142F0
0x180003a04  mov     qword ptr [rcx+rax], 8
0x180003a0c  lea     rcx, ExceptionInfo; ExceptionInfo
0x180003a13  call    __raise_securityfailure
0x180003a18  nop
0x180003a19  add     rsp, 78h
0x180003a1d  retn
```
