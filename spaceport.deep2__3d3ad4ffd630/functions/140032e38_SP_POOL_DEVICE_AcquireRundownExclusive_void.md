# SP_POOL_DEVICE::AcquireRundownExclusive(void)

- ea: `0x140032e38`
- end: `0x140032e89`
- name: `?AcquireRundownExclusive@SP_POOL_DEVICE@@QEAAXXZ`
- size: `81`
- prototype: `void __fastcall(SP_POOL_DEVICE *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14008ce50`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140032e56`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032e56`
- `ntoskrnl!KeClearEvent` at `0x140032e66`
- `ntoskrnl!KeClearEvent` at `0x140032e66`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140032e76`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140032e76`

## pseudocode

```c
void __fastcall SP_POOL_DEVICE::AcquireRundownExclusive(SP_POOL_DEVICE *this)
{
  KeWaitForSingleObject((char *)this + 24, Executive, 0, 0, 0);
  KeClearEvent((PRKEVENT)((char *)this + 88));
  ExWaitForRundownProtectionReleaseCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)this + 10));
}

```

## disassembly

```asm
0x140032e38  push    rbx
0x140032e3a  sub     rsp, 30h
0x140032e3e  mov     rbx, rcx
0x140032e41  mov     [rsp+38h+Timeout], 0; Timeout
0x140032e4a  add     rcx, 18h; Object
0x140032e4e  xor     r9d, r9d; Alertable
0x140032e51  xor     r8d, r8d; WaitMode
0x140032e54  xor     edx, edx; WaitReason
0x140032e56  call    cs:__imp_KeWaitForSingleObject
0x140032e5d  nop     dword ptr [rax+rax+00h]
0x140032e62  lea     rcx, [rbx+58h]; Event
0x140032e66  call    cs:__imp_KeClearEvent
0x140032e6d  nop     dword ptr [rax+rax+00h]
0x140032e72  mov     rcx, [rbx+50h]; RunRef
0x140032e76  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140032e7d  nop     dword ptr [rax+rax+00h]
0x140032e82  add     rsp, 30h
0x140032e86  pop     rbx
0x140032e87  retn
```
