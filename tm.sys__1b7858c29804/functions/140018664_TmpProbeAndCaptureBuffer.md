# TmpProbeAndCaptureBuffer

- ea: `0x140018664`
- end: `0x1400186ee`
- name: `TmpProbeAndCaptureBuffer`
- size: `138`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140014a30`
- `0x140016f40`
- `0x1400181c0`
- `0x140018370`

## callees

- `0x1400014d4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400186d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400186d3`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140018693`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140018693`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022705`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022705`
- `ntoskrnl!ProbeForRead` at `0x14001867a`
- `ntoskrnl!ProbeForRead` at `0x14001867a`
- `ntoskrnl!ExRaiseStatus` at `0x1400186e1`
- `ntoskrnl!ExRaiseStatus` at `0x1400186e1`

## pseudocode

```c
PVOID __fastcall TmpProbeAndCaptureBuffer(void *Src, size_t Size, ULONG a3)
{
  unsigned int v4; // edi
  PVOID P; // [rsp+48h] [rbp+20h]

  v4 = Size;
  ProbeForRead(Src, (unsigned int)Size, a3);
  P = ExAllocatePoolWithQuotaTag(PagedPool, v4, 0x62436D54u);
  RtlCopyFromUser(P, Src, v4);
  return P;
}

```

## disassembly

```asm
0x140018664  mov     [rsp+arg_0], rbx
0x140018669  mov     [rsp+arg_8], rsi
0x14001866e  push    rdi
0x14001866f  sub     rsp, 20h
0x140018673  mov     rsi, rcx
0x140018676  mov     edi, edx
0x140018678  mov     edx, edx; Length
0x14001867a  call    cs:__imp_ProbeForRead
0x140018681  nop     dword ptr [rax+rax+00h]
0x140018686  mov     r8d, 62436D54h; Tag
0x14001868c  mov     edx, edi; NumberOfBytes
0x14001868e  mov     ecx, 1; PoolType
0x140018693  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x14001869a  nop     dword ptr [rax+rax+00h]
0x14001869f  mov     rbx, rax
0x1400186a2  mov     [rsp+28h+P], rax
0x1400186a7  mov     r8d, edi; Size
0x1400186aa  mov     rdx, rsi; Src
0x1400186ad  mov     rcx, rax; void *
0x1400186b0  call    RtlCopyFromUser
0x1400186b5  nop
0x1400186b6  mov     rax, rbx
0x1400186b9  mov     rbx, [rsp+28h+arg_0]
0x1400186be  mov     rsi, [rsp+28h+arg_8]
0x1400186c3  add     rsp, 20h
0x1400186c7  pop     rdi
0x1400186c8  retn
0x1400186ca  mov     ebx, eax
0x1400186cc  xor     edx, edx; Tag
0x1400186ce  mov     rcx, [rsp+28h+P]; P
0x1400186d3  call    cs:__imp_ExFreePoolWithTag
0x1400186da  nop     dword ptr [rax+rax+00h]
0x1400186df  mov     ecx, ebx; Status
0x1400186e1  call    cs:__imp_ExRaiseStatus
0x1400226fc  push    rbp
0x1400226fe  sub     rsp, 20h
0x140022702  mov     rbp, rdx
0x140022705  call    cs:__imp_ExSystemExceptionFilter
0x14002270c  nop     dword ptr [rax+rax+00h]
0x140022711  nop
0x140022712  add     rsp, 20h
0x140022716  pop     rbp
0x140022717  retn
```
