# __report_gsfailure

- ea: `0x180001520`
- end: `0x1800016c0`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800021e0`

## callees

- `0x1800014d8`
- `0x180001520`

## import_xrefs

- `KERNEL32!RtlCaptureContext` at `0x180001560`
- `KERNEL32!RtlCaptureContext` at `0x180001560`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000157f`
- `KERNEL32!RtlLookupFunctionEntry` at `0x18000157f`
- `KERNEL32!RtlVirtualUnwind` at `0x1800015cc`
- `KERNEL32!RtlVirtualUnwind` at `0x1800015cc`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *FunctionEntry; // [rsp+40h] [rbp-48h]
  DWORD64 ControlPc; // [rsp+48h] [rbp-40h]
  unsigned __int64 ImageBase; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+58h] [rbp-30h] BYREF
  PVOID HandlerData[5]; // [rsp+60h] [rbp-28h] BYREF

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
    ContextRecord.Rip = *(_QWORD *)ContextRecord.Rsp;
    ContextRecord.Rsp += 8LL;
  }
  qword_1800060C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1800060B0 = -1073740791;
  dword_1800060B4 = 1;
  dword_1800060C8 = 3;
  qword_1800060D0[0] = 2;
  qword_1800060D0[1] = _security_cookie;
  qword_1800060D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001520  mov     [rsp+arg_0], rcx
0x180001525  sub     rsp, 88h
0x18000152c  mov     [rsp+88h+ControlPc], 0
0x180001535  mov     [rsp+88h+var_30], 0
0x18000153e  mov     [rsp+88h+FunctionEntry], 0
0x180001547  mov     [rsp+88h+var_28], 0
0x180001550  mov     [rsp+88h+ImageBase], 0
0x180001559  lea     rcx, ContextRecord; ContextRecord
0x180001560  call    cs:__imp_RtlCaptureContext
0x180001566  mov     rax, cs:ContextRecord.Rip
0x18000156d  mov     [rsp+88h+ControlPc], rax
0x180001572  xor     r8d, r8d; HistoryTable
0x180001575  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000157a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000157f  call    cs:__imp_RtlLookupFunctionEntry
0x180001585  mov     [rsp+88h+FunctionEntry], rax
0x18000158a  cmp     [rsp+88h+FunctionEntry], 0
0x180001590  jz      short loc_1800015D5
0x180001592  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000159b  lea     rax, [rsp+88h+var_30]
0x1800015a0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800015a5  lea     rax, [rsp+88h+var_28]
0x1800015aa  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800015af  lea     rax, ContextRecord
0x1800015b6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800015bb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x1800015c0  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x1800015c5  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800015ca  xor     ecx, ecx; HandlerType
0x1800015cc  call    cs:__imp_RtlVirtualUnwind
0x1800015d2  nop
0x1800015d3  jmp     short loc_1800015F8
0x1800015d5  mov     rax, cs:ContextRecord.Rsp
0x1800015dc  mov     rax, [rax]
0x1800015df  mov     cs:ContextRecord.Rip, rax
0x1800015e6  mov     rax, cs:ContextRecord.Rsp
0x1800015ed  add     rax, 8
0x1800015f1  mov     cs:ContextRecord.Rsp, rax
0x1800015f8  mov     rax, cs:ContextRecord.Rip
0x1800015ff  mov     cs:qword_1800060C0, rax
0x180001606  mov     rax, [rsp+88h+arg_0]
0x18000160e  mov     cs:ContextRecord.Rcx, rax
0x180001615  mov     cs:dword_1800060B0, 0C0000409h
0x18000161f  mov     cs:dword_1800060B4, 1
0x180001629  mov     cs:dword_1800060C8, 3
0x180001633  mov     eax, 8
0x180001638  imul    rax, 0
0x18000163c  lea     rcx, qword_1800060D0
0x180001643  mov     qword ptr [rcx+rax], 2
0x18000164b  mov     eax, 8
0x180001650  imul    rax, 1
0x180001654  lea     rcx, qword_1800060D0
0x18000165b  mov     rdx, cs:__security_cookie
0x180001662  mov     [rcx+rax], rdx
0x180001666  mov     eax, 8
0x18000166b  imul    rax, 2
0x18000166f  lea     rcx, qword_1800060D0
0x180001676  mov     rdx, cs:__security_cookie_complement
0x18000167d  mov     [rcx+rax], rdx
0x180001681  mov     eax, 8
0x180001686  imul    rax, 0
0x18000168a  mov     rcx, cs:__security_cookie
0x180001691  mov     [rsp+rax+88h+var_20], rcx
0x180001696  mov     eax, 8
0x18000169b  imul    rax, 1
0x18000169f  mov     rcx, cs:__security_cookie_complement
0x1800016a6  mov     [rsp+rax+88h+var_20], rcx
0x1800016ab  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800016b2  call    __raise_securityfailure
0x1800016b7  nop
0x1800016b8  add     rsp, 88h
0x1800016bf  retn
```
