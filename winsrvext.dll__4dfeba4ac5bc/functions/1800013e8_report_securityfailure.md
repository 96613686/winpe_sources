# __report_securityfailure

- ea: `0x1800013e8`
- end: `0x18000146f`
- name: `__report_securityfailure`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800013cc`

## callees

- `0x180001214`

## import_xrefs

- `ntdll!RtlCaptureContext` at `0x1800013f7`
- `ntdll!RtlCaptureContext` at `0x1800013f7`

## pseudocode

```c
void __fastcall __noreturn _report_securityfailure(unsigned int a1)
{
  DWORD64 retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  RtlCaptureContext(&ContextRecord);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v2;
  qword_18001D230 = retaddr;
  dword_18001D220 = -1073740791;
  dword_18001D224 = 1;
  dword_18001D238 = 1;
  qword_18001D240[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800013e8  mov     [rsp+arg_0], ecx
0x1800013ec  sub     rsp, 28h
0x1800013f0  lea     rcx, ContextRecord; ContextRecord
0x1800013f7  call    cs:__imp_RtlCaptureContext
0x1800013fd  mov     rax, [rsp+28h]
0x180001402  mov     cs:ContextRecord.Rip, rax
0x180001409  lea     rax, [rsp+28h]
0x18000140e  add     rax, 8
0x180001412  mov     cs:ContextRecord.Rsp, rax
0x180001419  mov     rax, cs:ContextRecord.Rip
0x180001420  mov     cs:qword_18001D230, rax
0x180001427  mov     cs:dword_18001D220, 0C0000409h
0x180001431  mov     cs:dword_18001D224, 1
0x18000143b  mov     cs:dword_18001D238, 1
0x180001445  mov     eax, 8
0x18000144a  imul    rax, 0
0x18000144e  lea     rcx, qword_18001D240
0x180001455  mov     edx, [rsp+28h+arg_0]
0x180001459  mov     [rcx+rax], rdx
0x18000145d  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001464  call    __raise_securityfailure
0x180001469  nop
0x18000146a  add     rsp, 28h
0x18000146e  retn
```
