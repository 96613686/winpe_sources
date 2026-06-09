# VhdmpiEnqueueControlDeviceIoctl

- ea: `0x14002f8bc`
- end: `0x14002fa1e`
- name: `VhdmpiEnqueueControlDeviceIoctl`
- size: `354`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400358f8`
- `0x14009f454`
- `0x1400d25d0`

## callees

- `0x140023980`
- `0x14002f8bc`
- `0x140036284`

## import_xrefs

- `ntoskrnl!IoCsqInsertIrpEx` at `0x14002f938`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x14002f938`
- `ntoskrnl!IofCompleteRequest` at `0x14002f9a2`
- `ntoskrnl!IofCompleteRequest` at `0x14002f9a2`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f9b5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002f9b5`

## pseudocode

```c
unsigned __int8 __fastcall VhdmpiEnqueueControlDeviceIoctl(PIRP Irp)
{
  struct _EX_RUNDOWN_REF *FsContext2; // rsi
  struct _IO_CSQ *v3; // rcx
  int inserted; // edi
  unsigned __int8 v5; // bl

  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
    TraceEvents("VhdmpiEnqueueControlDeviceIoctl", 0x28Cu, 5u, 2u, "VhdmpiEnqueueControlDeviceIoctl: enter...");
  FsContext2 = (struct _EX_RUNDOWN_REF *)Irp->Tail.Overlay.CurrentStackLocation->FileObject->FsContext2;
  v3 = (struct _IO_CSQ *)(VhdmpControlExtension + 8);
  Irp->IoStatus.Status = 259;
  inserted = IoCsqInsertIrpEx(v3, Irp, 0, 0);
  if ( inserted < 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
      TraceEvents(
        "VhdmpiEnqueueControlDeviceIoctl",
        0x2A8u,
        2u,
        2u,
        "VhdmpiEnqueueControlDeviceIoctl: failed to insert(0x%x)",
        inserted);
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = inserted;
    IofCompleteRequest(Irp, 0);
    ExReleaseRundownProtection(FsContext2 + 33);
    v5 = 0;
  }
  else
  {
    v5 = 1;
  }
  if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 2) )
    TraceEvents(
      "VhdmpiEnqueueControlDeviceIoctl",
      0x2B4u,
      5u,
      2u,
      "VhdmpiEnqueueControlDeviceIoctl: leaving... (0x%08x)",
      v5);
  return v5;
}

```

## disassembly

```asm
0x14002f8bc  push    rbx
0x14002f8be  push    rbp
0x14002f8bf  push    rsi
0x14002f8c0  push    rdi
0x14002f8c1  sub     rsp, 38h
0x14002f8c5  mov     eax, cs:dword_1400876D0
0x14002f8cb  mov     rbx, rcx
0x14002f8ce  mov     ebp, 2
0x14002f8d3  cmp     eax, 5
0x14002f8d6  jbe     short loc_14002F90E
0x14002f8d8  mov     edx, ebp
0x14002f8da  lea     rcx, dword_1400876D0
0x14002f8e1  call    _tlgKeywordOn
0x14002f8e6  test    al, al
0x14002f8e8  jz      short loc_14002F90E
0x14002f8ea  lea     rax, aVhdmpienqueuec_2; "VhdmpiEnqueueControlDeviceIoctl: enter."...
0x14002f8f1  mov     edx, 28Ch; int
0x14002f8f6  mov     r9d, ebp; int
0x14002f8f9  mov     [rsp+58h+var_38], rax; char *
0x14002f8fe  lea     r8d, [rbp+3]; int
0x14002f902  lea     rcx, aVhdmpienqueuec_1; "VhdmpiEnqueueControlDeviceIoctl"
0x14002f909  call    TraceEvents
0x14002f90e  mov     rax, [rbx+0B8h]
0x14002f915  xor     r9d, r9d; InsertContext
0x14002f918  xor     r8d, r8d; Context
0x14002f91b  mov     rdx, rbx; Irp
0x14002f91e  mov     rcx, [rax+30h]
0x14002f922  mov     rsi, [rcx+20h]
0x14002f926  mov     rcx, cs:VhdmpControlExtension
0x14002f92d  add     rcx, 8; Csq
0x14002f931  mov     dword ptr [rbx+30h], 103h
0x14002f938  call    cs:__imp_IoCsqInsertIrpEx
0x14002f93f  nop     dword ptr [rax+rax+00h]
0x14002f944  mov     edi, eax
0x14002f946  test    eax, eax
0x14002f948  js      short loc_14002F94E
0x14002f94a  mov     bl, 1
0x14002f94c  jmp     short loc_14002F9C3
0x14002f94e  mov     eax, cs:dword_1400876D0
0x14002f954  cmp     eax, ebp
0x14002f956  jbe     short loc_14002F992
0x14002f958  mov     rdx, rbp
0x14002f95b  lea     rcx, dword_1400876D0
0x14002f962  call    _tlgKeywordOn
0x14002f967  test    al, al
0x14002f969  jz      short loc_14002F992
0x14002f96b  lea     rax, aVhdmpienqueuec_0; "VhdmpiEnqueueControlDeviceIoctl: failed"...
0x14002f972  mov     dword ptr [rsp+58h+var_30], edi; char
0x14002f976  mov     edx, 2A8h; int
0x14002f97b  mov     [rsp+58h+var_38], rax; char *
0x14002f980  mov     r9d, ebp; int
0x14002f983  lea     rcx, aVhdmpienqueuec_1; "VhdmpiEnqueueControlDeviceIoctl"
0x14002f98a  mov     r8d, ebp; int
0x14002f98d  call    TraceEvents
0x14002f992  xor     edx, edx; PriorityBoost
0x14002f994  mov     qword ptr [rbx+38h], 0
0x14002f99c  mov     rcx, rbx; Irp
0x14002f99f  mov     [rbx+30h], edi
0x14002f9a2  call    cs:__imp_IofCompleteRequest
0x14002f9a9  nop     dword ptr [rax+rax+00h]
0x14002f9ae  lea     rcx, [rsi+108h]; RunRef
0x14002f9b5  call    cs:__imp_ExReleaseRundownProtection
0x14002f9bc  nop     dword ptr [rax+rax+00h]
0x14002f9c1  xor     bl, bl
0x14002f9c3  mov     eax, cs:dword_1400876D0
0x14002f9c9  cmp     eax, 5
0x14002f9cc  jbe     short loc_14002FA12
0x14002f9ce  mov     rdx, rbp
0x14002f9d1  lea     rcx, dword_1400876D0
0x14002f9d8  call    _tlgKeywordOn
0x14002f9dd  test    al, al
0x14002f9df  jz      short loc_14002FA12
0x14002f9e1  movzx   edx, bl
0x14002f9e4  lea     rax, aVhdmpienqueuec; "VhdmpiEnqueueControlDeviceIoctl: leavin"...
0x14002f9eb  mov     dword ptr [rsp+58h+var_30], edx; char
0x14002f9ef  lea     rcx, aVhdmpienqueuec_1; "VhdmpiEnqueueControlDeviceIoctl"
0x14002f9f6  mov     r10d, 2B4h
0x14002f9fc  mov     [rsp+58h+var_38], rax; char *
0x14002fa01  mov     edx, r10d; int
0x14002fa04  mov     r9d, ebp; int
0x14002fa07  mov     r8d, 5; int
0x14002fa0d  call    TraceEvents
0x14002fa12  mov     al, bl
0x14002fa14  add     rsp, 38h
0x14002fa18  pop     rdi
0x14002fa19  pop     rsi
0x14002fa1a  pop     rbp
0x14002fa1b  pop     rbx
0x14002fa1c  retn
```
