# __report_gsfailure

- ea: `0x1800039d0`
- end: `0x180003b70`
- name: `__report_gsfailure`
- size: `416`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004720`

## callees

- `0x180003994`
- `0x1800039d0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180003a7c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180003a7c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180003a10`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180003a10`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180003a2f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180003a2f`

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
  qword_1800090B0 = ContextRecord.Rip;
  ContextRecord.Rcx = StackCookie;
  dword_1800090A0 = -1073740791;
  dword_1800090A4 = 1;
  dword_1800090B8 = 3;
  qword_1800090C0[0] = 2;
  qword_1800090C0[1] = _security_cookie;
  qword_1800090C0[2] = _security_cookie_complement;
  HandlerData[2] = (PVOID)_security_cookie_complement;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800039d0  mov     [rsp+arg_0], rcx
0x1800039d5  sub     rsp, 88h
0x1800039dc  mov     [rsp+88h+ControlPc], 0
0x1800039e5  mov     [rsp+88h+var_30], 0
0x1800039ee  mov     [rsp+88h+FunctionEntry], 0
0x1800039f7  mov     [rsp+88h+var_28], 0
0x180003a00  mov     [rsp+88h+ImageBase], 0
0x180003a09  lea     rcx, ContextRecord; ContextRecord
0x180003a10  call    cs:__imp_RtlCaptureContext
0x180003a16  mov     rax, cs:ContextRecord.Rip
0x180003a1d  mov     [rsp+88h+ControlPc], rax
0x180003a22  xor     r8d, r8d; HistoryTable
0x180003a25  lea     rdx, [rsp+88h+ImageBase]; ImageBase
0x180003a2a  mov     rcx, [rsp+88h+ControlPc]; ControlPc
0x180003a2f  call    cs:__imp_RtlLookupFunctionEntry
0x180003a35  mov     [rsp+88h+FunctionEntry], rax
0x180003a3a  cmp     [rsp+88h+FunctionEntry], 0
0x180003a40  jz      short loc_180003A85
0x180003a42  mov     [rsp+88h+ContextPointers], 0; ContextPointers
0x180003a4b  lea     rax, [rsp+88h+var_30]
0x180003a50  mov     [rsp+88h+EstablisherFrame], rax; EstablisherFrame
0x180003a55  lea     rax, [rsp+88h+var_28]
0x180003a5a  mov     [rsp+88h+HandlerData], rax; HandlerData
0x180003a5f  lea     rax, ContextRecord
0x180003a66  mov     [rsp+88h+ContextRecord], rax; ContextRecord
0x180003a6b  mov     r9, [rsp+88h+FunctionEntry]; FunctionEntry
0x180003a70  mov     r8, [rsp+88h+ControlPc]; ControlPc
0x180003a75  mov     rdx, [rsp+88h+ImageBase]; ImageBase
0x180003a7a  xor     ecx, ecx; HandlerType
0x180003a7c  call    cs:__imp_RtlVirtualUnwind
0x180003a82  nop
0x180003a83  jmp     short loc_180003AA8
0x180003a85  mov     rax, cs:ContextRecord.Rsp
0x180003a8c  mov     rax, [rax]
0x180003a8f  mov     cs:ContextRecord.Rip, rax
0x180003a96  mov     rax, cs:ContextRecord.Rsp
0x180003a9d  add     rax, 8
0x180003aa1  mov     cs:ContextRecord.Rsp, rax
0x180003aa8  mov     rax, cs:ContextRecord.Rip
0x180003aaf  mov     cs:qword_1800090B0, rax
0x180003ab6  mov     rax, [rsp+88h+arg_0]
0x180003abe  mov     cs:ContextRecord.Rcx, rax
0x180003ac5  mov     cs:dword_1800090A0, 0C0000409h
0x180003acf  mov     cs:dword_1800090A4, 1
0x180003ad9  mov     cs:dword_1800090B8, 3
0x180003ae3  mov     eax, 8
0x180003ae8  imul    rax, 0
0x180003aec  lea     rcx, qword_1800090C0
0x180003af3  mov     qword ptr [rcx+rax], 2
0x180003afb  mov     eax, 8
0x180003b00  imul    rax, 1
0x180003b04  lea     rcx, qword_1800090C0
0x180003b0b  mov     rdx, cs:__security_cookie
0x180003b12  mov     [rcx+rax], rdx
0x180003b16  mov     eax, 8
0x180003b1b  imul    rax, 2
0x180003b1f  lea     rcx, qword_1800090C0
0x180003b26  mov     rdx, cs:__security_cookie_complement
0x180003b2d  mov     [rcx+rax], rdx
0x180003b31  mov     eax, 8
0x180003b36  imul    rax, 0
0x180003b3a  mov     rcx, cs:__security_cookie
0x180003b41  mov     [rsp+rax+88h+var_20], rcx
0x180003b46  mov     eax, 8
0x180003b4b  imul    rax, 1
0x180003b4f  mov     rcx, cs:__security_cookie_complement
0x180003b56  mov     [rsp+rax+88h+var_20], rcx
0x180003b5b  lea     rcx, ExceptionInfo; ExceptionInfo
0x180003b62  call    __raise_securityfailure
0x180003b67  nop
0x180003b68  add     rsp, 88h
0x180003b6f  retn
```
