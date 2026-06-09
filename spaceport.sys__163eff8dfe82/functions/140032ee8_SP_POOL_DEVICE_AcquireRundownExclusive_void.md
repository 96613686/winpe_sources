# SP_POOL_DEVICE::AcquireRundownExclusive(void)

- ea: `0x140032ee8`
- end: `0x140032f39`
- name: `?AcquireRundownExclusive@SP_POOL_DEVICE@@QEAAXXZ`
- size: `81`
- prototype: `void __fastcall(SP_POOL_DEVICE *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14008ce50`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140032f06`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032f06`
- `ntoskrnl!KeClearEvent` at `0x140032f16`
- `ntoskrnl!KeClearEvent` at `0x140032f16`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140032f26`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140032f26`

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
0x140032ee8  push    rbx
0x140032eea  sub     rsp, 30h
0x140032eee  mov     rbx, rcx
0x140032ef1  mov     [rsp+38h+Timeout], 0; Timeout
0x140032efa  add     rcx, 18h; Object
0x140032efe  xor     r9d, r9d; Alertable
0x140032f01  xor     r8d, r8d; WaitMode
0x140032f04  xor     edx, edx; WaitReason
0x140032f06  call    cs:__imp_KeWaitForSingleObject
0x140032f0d  nop     dword ptr [rax+rax+00h]
0x140032f12  lea     rcx, [rbx+58h]; Event
0x140032f16  call    cs:__imp_KeClearEvent
0x140032f1d  nop     dword ptr [rax+rax+00h]
0x140032f22  mov     rcx, [rbx+50h]; RunRef
0x140032f26  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140032f2d  nop     dword ptr [rax+rax+00h]
0x140032f32  add     rsp, 30h
0x140032f36  pop     rbx
0x140032f37  retn
```
