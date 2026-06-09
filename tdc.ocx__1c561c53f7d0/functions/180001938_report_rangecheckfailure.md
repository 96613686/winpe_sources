# __report_rangecheckfailure

- ea: `0x180001938`
- end: `0x180001a5e`
- name: `__report_rangecheckfailure`
- size: `294`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008b40`
- `0x1800109ec`
- `0x180012cac`
- `0x180013070`

## callees

- `0x18000174c`
- `0x180001938`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x180001970`
- `KERNEL32!RtlCaptureContext` at `0x180001970`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000198f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000198f`
- `KERNEL32!RtlVirtualUnwind` at `0x1800019dc`
- `KERNEL32!RtlVirtualUnwind` at `0x1800019dc`

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
  qword_18001B7A0 = ContextRecord.Rip;
  dword_18001B790 = -1073740791;
  dword_18001B794 = 1;
  dword_18001B7A8 = 1;
  qword_18001B7B0[0] = 8;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001938  sub     rsp, 78h
0x18000193c  mov     [rsp+78h+ControlPc], 0
0x180001945  mov     [rsp+78h+var_20], 0
0x18000194e  mov     [rsp+78h+FunctionEntry], 0
0x180001957  mov     [rsp+78h+var_18], 0
0x180001960  mov     [rsp+78h+ImageBase], 0
0x180001969  lea     rcx, ContextRecord; ContextRecord
0x180001970  call    cs:__imp_RtlCaptureContext
0x180001976  mov     rax, cs:ContextRecord.Rip
0x18000197d  mov     [rsp+78h+ControlPc], rax
0x180001982  xor     r8d, r8d; HistoryTable
0x180001985  lea     rdx, [rsp+78h+ImageBase]; ImageBase
0x18000198a  mov     rcx, [rsp+78h+ControlPc]; ControlPc
0x18000198f  call    cs:__imp_RtlLookupFunctionEntry
0x180001995  mov     [rsp+78h+FunctionEntry], rax
0x18000199a  cmp     [rsp+78h+FunctionEntry], 0
0x1800019a0  jz      short loc_1800019E5
0x1800019a2  mov     [rsp+78h+ContextPointers], 0; ContextPointers
0x1800019ab  lea     rax, [rsp+78h+var_20]
0x1800019b0  mov     [rsp+78h+EstablisherFrame], rax; EstablisherFrame
0x1800019b5  lea     rax, [rsp+78h+var_18]
0x1800019ba  mov     [rsp+78h+HandlerData], rax; HandlerData
0x1800019bf  lea     rax, ContextRecord
0x1800019c6  mov     [rsp+78h+ContextRecord], rax; ContextRecord
0x1800019cb  mov     r9, [rsp+78h+FunctionEntry]; FunctionEntry
0x1800019d0  mov     r8, [rsp+78h+ControlPc]; ControlPc
0x1800019d5  mov     rdx, [rsp+78h+ImageBase]; ImageBase
0x1800019da  xor     ecx, ecx; HandlerType
0x1800019dc  call    cs:__imp_RtlVirtualUnwind
0x1800019e2  nop
0x1800019e3  jmp     short loc_180001A08
0x1800019e5  mov     rax, cs:ContextRecord.Rsp
0x1800019ec  mov     rax, [rax]
0x1800019ef  mov     cs:ContextRecord.Rip, rax
0x1800019f6  mov     rax, cs:ContextRecord.Rsp
0x1800019fd  add     rax, 8
0x180001a01  mov     cs:ContextRecord.Rsp, rax
0x180001a08  mov     rax, cs:ContextRecord.Rip
0x180001a0f  mov     cs:qword_18001B7A0, rax
0x180001a16  mov     cs:dword_18001B790, 0C0000409h
0x180001a20  mov     cs:dword_18001B794, 1
0x180001a2a  mov     cs:dword_18001B7A8, 1
0x180001a34  mov     eax, 8
0x180001a39  imul    rax, 0
0x180001a3d  lea     rcx, qword_18001B7B0
0x180001a44  mov     qword ptr [rcx+rax], 8
0x180001a4c  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001a53  call    __raise_securityfailure
0x180001a58  nop
0x180001a59  add     rsp, 78h
0x180001a5d  retn
```
