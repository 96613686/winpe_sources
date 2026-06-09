# SlbNatCreateExternalAddress

- ea: `0x14003118c`
- end: `0x1400311eb`
- name: `SlbNatCreateExternalAddress`
- size: `95`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400309b0`
- `0x140036580`

## callees

- `0x140014dcc`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400311d1`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400311d1`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400311a3`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400311a3`

## pseudocode

```c
__int64 __fastcall SlbNatCreateExternalAddress(__int64 a1, __int16 *a2)
{
  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  LODWORD(a2) = SlbNatCreateExternalAddressWithLock(a1, a2, 0, 1, 0);
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x14003118c  mov     [rsp+arg_0], rbx
0x140031191  push    rdi
0x140031192  sub     rsp, 30h
0x140031196  mov     rdi, rcx
0x140031199  mov     rbx, rdx
0x14003119c  lea     rcx, Resource; Resource
0x1400311a3  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400311aa  nop     dword ptr [rax+rax+00h]
0x1400311af  mov     r9b, 1
0x1400311b2  mov     [rsp+38h+var_18], 0
0x1400311ba  xor     r8d, r8d
0x1400311bd  mov     rdx, rbx
0x1400311c0  mov     rcx, rdi
0x1400311c3  call    SlbNatCreateExternalAddressWithLock
0x1400311c8  lea     rcx, Resource; Resource
0x1400311cf  mov     ebx, eax
0x1400311d1  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400311d8  nop     dword ptr [rax+rax+00h]
0x1400311dd  mov     eax, ebx
0x1400311df  mov     rbx, [rsp+38h+arg_0]
0x1400311e4  add     rsp, 30h
0x1400311e8  pop     rdi
0x1400311e9  retn
```
