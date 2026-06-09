# __report_gsfailure

- ea: `0x180001860`
- end: `0x180001a00`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800051a0`

## callees

- `0x180001818`
- `0x180001860`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x1800018a0`
- `ntdll!RtlCaptureContext` at `0x1800018a0`
- `ntdll!RtlVirtualUnwind` at `0x18000190c`
- `ntdll!RtlVirtualUnwind` at `0x18000190c`
- `ntdll!RtlLookupFunctionEntry` at `0x1800018bf`
- `ntdll!RtlLookupFunctionEntry` at `0x1800018bf`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  struct _RUNTIME_FUNCTION *FunctionEntry; // [rsp+40h] [rbp-48h]
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
  qword_18000C1C0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_18000C1B0 = -1073740791;
  dword_18000C1B4 = 1;
  dword_18000C1C8 = 3;
  qword_18000C1D0[0] = 2;
  qword_18000C1D0[1] = _security_cookie;
  qword_18000C1D0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001860  mov     [rsp+arg_0], rcx
0x180001865  sub     rsp, 88h
0x18000186c  mov     [rsp+88h+ControlPc], 0
0x180001875  mov     [rsp+88h+var_30], 0
0x18000187e  mov     [rsp+88h+FunctionEntry], 0
0x180001887  mov     [rsp+88h+var_28], 0
0x180001890  mov     [rsp+88h+ImageBase], 0
0x180001899  lea     rcx, ContextRecord; ContextRecord
0x1800018a0  call    cs:__imp_RtlCaptureContext
0x1800018a6  mov     rax, cs:ContextRecord.Rip
0x1800018ad  mov     [rsp+88h+ControlPc], rax
0x1800018b2  xor     r8d, r8d; HistoryTable
0x1800018b5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1800018ba  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1800018bf  call    cs:__imp_RtlLookupFunctionEntry
0x1800018c5  mov     [rsp+88h+FunctionEntry], rax
0x1800018ca  cmp     [rsp+88h+FunctionEntry], 0
0x1800018d0  jz      short loc_180001915
0x1800018d2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1800018db  lea     rax, [rsp+88h+var_30]
0x1800018e0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1800018e5  lea     rax, [rsp+88h+var_28]
0x1800018ea  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1800018ef  lea     rax, ContextRecord
0x1800018f6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1800018fb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001900  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001905  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000190a  xor     ecx, ecx; HandlerType
0x18000190c  call    cs:__imp_RtlVirtualUnwind
0x180001912  nop
0x180001913  jmp     short loc_180001938
0x180001915  mov     rax, cs:ContextRecord.Rsp
0x18000191c  mov     rax, [rax]
0x18000191f  mov     cs:ContextRecord.Rip, rax
0x180001926  mov     rax, cs:ContextRecord.Rsp
0x18000192d  add     rax, 8
0x180001931  mov     cs:ContextRecord.Rsp, rax
0x180001938  mov     rax, cs:ContextRecord.Rip
0x18000193f  mov     cs:qword_18000C1C0, rax
0x180001946  mov     rax, [rsp+88h+arg_0]
0x18000194e  mov     cs:ContextRecord.Rcx, rax
0x180001955  mov     cs:dword_18000C1B0, 0C0000409h
0x18000195f  mov     cs:dword_18000C1B4, 1
0x180001969  mov     cs:dword_18000C1C8, 3
0x180001973  mov     eax, 8
0x180001978  imul    rax, 0
0x18000197c  lea     rcx, qword_18000C1D0
0x180001983  mov     qword ptr [rcx+rax], 2
0x18000198b  mov     eax, 8
0x180001990  imul    rax, 1
0x180001994  lea     rcx, qword_18000C1D0
0x18000199b  mov     rdx, cs:__security_cookie
0x1800019a2  mov     [rcx+rax], rdx
0x1800019a6  mov     eax, 8
0x1800019ab  imul    rax, 2
0x1800019af  lea     rcx, qword_18000C1D0
0x1800019b6  mov     rdx, cs:__security_cookie_complement
0x1800019bd  mov     [rcx+rax], rdx
0x1800019c1  mov     eax, 8
0x1800019c6  imul    rax, 0
0x1800019ca  mov     rcx, cs:__security_cookie
0x1800019d1  mov     [rsp+rax+88h+var_20], rcx
0x1800019d6  mov     eax, 8
0x1800019db  imul    rax, 1
0x1800019df  mov     rcx, cs:__security_cookie_complement
0x1800019e6  mov     [rsp+rax+88h+var_20], rcx
0x1800019eb  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800019f2  call    __raise_securityfailure
0x1800019f7  nop
0x1800019f8  add     rsp, 88h
0x1800019ff  retn
```
