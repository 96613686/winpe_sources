# WimFSFAcquireConfigLock

- ea: `0x14000c3bc`
- end: `0x14000c3f9`
- name: `WimFSFAcquireConfigLock`
- size: `61`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1400227a0`
- `0x1400263f0`
- `0x1400273c0`
- `0x140027820`
- `0x14002d3d4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000c3e6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c3e6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c3c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c3c5`

## pseudocode

```c
NTSTATUS __fastcall WimFSFAcquireConfigLock(__int64 a1)
{
  KeEnterCriticalRegion();
  return KeWaitForSingleObject((PVOID)(a1 + 40), Executive, 0, 0, 0);
}

```

## disassembly

```asm
0x14000c3bc  push    rbx
0x14000c3be  sub     rsp, 30h
0x14000c3c2  mov     rbx, rcx
0x14000c3c5  call    cs:__imp_KeEnterCriticalRegion
0x14000c3cc  nop     dword ptr [rax+rax+00h]
0x14000c3d1  lea     rcx, [rbx+28h]; Object
0x14000c3d5  mov     [rsp+38h+Timeout], 0; Timeout
0x14000c3de  xor     r9d, r9d; Alertable
0x14000c3e1  xor     r8d, r8d; WaitMode
0x14000c3e4  xor     edx, edx; WaitReason
0x14000c3e6  call    cs:__imp_KeWaitForSingleObject
0x14000c3ed  nop     dword ptr [rax+rax+00h]
0x14000c3f2  add     rsp, 30h
0x14000c3f6  pop     rbx
0x14000c3f7  retn
```
