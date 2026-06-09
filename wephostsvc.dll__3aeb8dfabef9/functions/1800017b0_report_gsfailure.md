# __report_gsfailure

- ea: `0x1800017b0`
- end: `0x180001950`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003be0`

## callees

- `0x18000176c`
- `0x1800017b0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000180f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x18000180f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800017f0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800017f0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000185c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x18000185c`

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
  qword_180008160 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_180008150 = -1073740791;
  dword_180008154 = 1;
  dword_180008168 = 3;
  qword_180008170[0] = 2;
  qword_180008170[1] = _security_cookie;
  qword_180008170[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800017b0  mov     [rsp+arg_0], rcx
0x1800017b5  sub     rsp, 88h
0x1800017bc  mov     [rsp+88h+ControlPc], 0
0x1800017c5  mov     [rsp+88h+var_30], 0
0x1800017ce  mov     [rsp+88h+FunctionEntry], 0
0x1800017d7  mov     [rsp+88h+var_28], 0
0x1800017e0  mov     [rsp+88h+ImageBase], 0
0x1800017e9  lea     rcx, ContextRecord; ContextRecord
0x1800017f0  call    cs:__imp_RtlCaptureContext
0x1800017f6  mov     rax, cs:ContextRecord.Rip
0x1800017fd  mov     [rsp+88h+ControlPc], rax
0x180001802  xor     r8d, r8d; HistoryTable
0x180001805  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000180a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x18000180f  call    cs:__imp_RtlLookupFunctionEntry
0x180001815  mov     [rsp+88h+FunctionEntry], rax
0x18000181a  cmp     [rsp+88h+FunctionEntry], 0
0x180001820  jz      short loc_180001865
0x180001822  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x18000182b  lea     rax, [rsp+88h+var_30]
0x180001830  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180001835  lea     rax, [rsp+88h+var_28]
0x18000183a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x18000183f  lea     rax, ContextRecord
0x180001846  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x18000184b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180001850  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180001855  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x18000185a  xor     ecx, ecx; HandlerType
0x18000185c  call    cs:__imp_RtlVirtualUnwind
0x180001862  nop
0x180001863  jmp     short loc_180001888
0x180001865  mov     rax, cs:ContextRecord.Rsp
0x18000186c  mov     rax, [rax]
0x18000186f  mov     cs:ContextRecord.Rip, rax
0x180001876  mov     rax, cs:ContextRecord.Rsp
0x18000187d  add     rax, 8
0x180001881  mov     cs:ContextRecord.Rsp, rax
0x180001888  mov     rax, cs:ContextRecord.Rip
0x18000188f  mov     cs:qword_180008160, rax
0x180001896  mov     rax, [rsp+88h+arg_0]
0x18000189e  mov     cs:ContextRecord.Rcx, rax
0x1800018a5  mov     cs:dword_180008150, 0C0000409h
0x1800018af  mov     cs:dword_180008154, 1
0x1800018b9  mov     cs:dword_180008168, 3
0x1800018c3  mov     eax, 8
0x1800018c8  imul    rax, 0
0x1800018cc  lea     rcx, qword_180008170
0x1800018d3  mov     qword ptr [rcx+rax], 2
0x1800018db  mov     eax, 8
0x1800018e0  imul    rax, 1
0x1800018e4  lea     rcx, qword_180008170
0x1800018eb  mov     rdx, cs:__security_cookie
0x1800018f2  mov     [rcx+rax], rdx
0x1800018f6  mov     eax, 8
0x1800018fb  imul    rax, 2
0x1800018ff  lea     rcx, qword_180008170
0x180001906  mov     rdx, cs:__security_cookie_complement
0x18000190d  mov     [rcx+rax], rdx
0x180001911  mov     eax, 8
0x180001916  imul    rax, 0
0x18000191a  mov     rcx, cs:__security_cookie
0x180001921  mov     [rsp+rax+88h+var_20], rcx
0x180001926  mov     eax, 8
0x18000192b  imul    rax, 1
0x18000192f  mov     rcx, cs:__security_cookie_complement
0x180001936  mov     [rsp+rax+88h+var_20], rcx
0x18000193b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001942  call    __raise_securityfailure
0x180001947  nop
0x180001948  add     rsp, 88h
0x18000194f  retn
```
