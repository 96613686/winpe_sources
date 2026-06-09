# __report_gsfailure

- ea: `0x140001360`
- end: `0x140001500`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400038e0`

## callees

- `0x140001318`
- `0x140001360`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1400013a0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1400013a0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x14000140c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x14000140c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1400013bf`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x1400013bf`

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
  qword_1400088E0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1400088D0 = -1073740791;
  dword_1400088D4 = 1;
  dword_1400088E8 = 3;
  qword_1400088F0[0] = 2;
  qword_1400088F0[1] = _security_cookie;
  qword_1400088F0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x140001360  mov     [rsp+arg_0], rcx
0x140001365  sub     rsp, 88h
0x14000136c  mov     [rsp+88h+ControlPc], 0
0x140001375  mov     [rsp+88h+var_30], 0
0x14000137e  mov     [rsp+88h+FunctionEntry], 0
0x140001387  mov     [rsp+88h+var_28], 0
0x140001390  mov     [rsp+88h+ImageBase], 0
0x140001399  lea     rcx, ContextRecord; ContextRecord
0x1400013a0  call    cs:__imp_RtlCaptureContext
0x1400013a6  mov     rax, cs:ContextRecord.Rip
0x1400013ad  mov     [rsp+88h+ControlPc], rax
0x1400013b2  xor     r8d, r8d; HistoryTable
0x1400013b5  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x1400013ba  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x1400013bf  call    cs:__imp_RtlLookupFunctionEntry
0x1400013c5  mov     [rsp+88h+FunctionEntry], rax
0x1400013ca  cmp     [rsp+88h+FunctionEntry], 0
0x1400013d0  jz      short loc_140001415
0x1400013d2  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x1400013db  lea     rax, [rsp+88h+var_30]
0x1400013e0  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x1400013e5  lea     rax, [rsp+88h+var_28]
0x1400013ea  mov     [rsp+88h+HandlerData], rax; HandlerData
0x1400013ef  lea     rax, ContextRecord
0x1400013f6  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x1400013fb  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x140001400  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x140001405  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x14000140a  xor     ecx, ecx; HandlerType
0x14000140c  call    cs:__imp_RtlVirtualUnwind
0x140001412  nop
0x140001413  jmp     short loc_140001438
0x140001415  mov     rax, cs:ContextRecord.Rsp
0x14000141c  mov     rax, [rax]
0x14000141f  mov     cs:ContextRecord.Rip, rax
0x140001426  mov     rax, cs:ContextRecord.Rsp
0x14000142d  add     rax, 8
0x140001431  mov     cs:ContextRecord.Rsp, rax
0x140001438  mov     rax, cs:ContextRecord.Rip
0x14000143f  mov     cs:qword_1400088E0, rax
0x140001446  mov     rax, [rsp+88h+arg_0]
0x14000144e  mov     cs:ContextRecord.Rcx, rax
0x140001455  mov     cs:dword_1400088D0, 0C0000409h
0x14000145f  mov     cs:dword_1400088D4, 1
0x140001469  mov     cs:dword_1400088E8, 3
0x140001473  mov     eax, 8
0x140001478  imul    rax, 0
0x14000147c  lea     rcx, qword_1400088F0
0x140001483  mov     qword ptr [rcx+rax], 2
0x14000148b  mov     eax, 8
0x140001490  imul    rax, 1
0x140001494  lea     rcx, qword_1400088F0
0x14000149b  mov     rdx, cs:__security_cookie
0x1400014a2  mov     [rcx+rax], rdx
0x1400014a6  mov     eax, 8
0x1400014ab  imul    rax, 2
0x1400014af  lea     rcx, qword_1400088F0
0x1400014b6  mov     rdx, cs:__security_cookie_complement
0x1400014bd  mov     [rcx+rax], rdx
0x1400014c1  mov     eax, 8
0x1400014c6  imul    rax, 0
0x1400014ca  mov     rcx, cs:__security_cookie
0x1400014d1  mov     [rsp+rax+88h+var_20], rcx
0x1400014d6  mov     eax, 8
0x1400014db  imul    rax, 1
0x1400014df  mov     rcx, cs:__security_cookie_complement
0x1400014e6  mov     [rsp+rax+88h+var_20], rcx
0x1400014eb  lea     rcx, ExceptionInfo; ExceptionInfo
0x1400014f2  call    __raise_securityfailure
0x1400014f7  nop
0x1400014f8  add     rsp, 88h
0x1400014ff  retn
```
