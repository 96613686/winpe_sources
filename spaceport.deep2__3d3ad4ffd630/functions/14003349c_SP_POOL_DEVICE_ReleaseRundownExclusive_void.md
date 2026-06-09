# SP_POOL_DEVICE::ReleaseRundownExclusive(void)

- ea: `0x14003349c`
- end: `0x1400334e3`
- name: `?ReleaseRundownExclusive@SP_POOL_DEVICE@@QEAAXXZ`
- size: `71`
- prototype: `void __fastcall(SP_POOL_DEVICE *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14008ce50`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1400334a9`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1400334a9`
- `ntoskrnl!KeSetEvent` at `0x1400334be`
- `ntoskrnl!KeSetEvent` at `0x1400334be`
- `ntoskrnl!KeReleaseMutex` at `0x1400334d0`
- `ntoskrnl!KeReleaseMutex` at `0x1400334d0`

## pseudocode

```c
void __fastcall SP_POOL_DEVICE::ReleaseRundownExclusive(SP_POOL_DEVICE *this)
{
  ExReInitializeRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)this + 10));
  KeSetEvent((PRKEVENT)((char *)this + 88), 0, 0);
  KeReleaseMutex((PRKMUTEX)((char *)this + 24), 0);
}

```

## disassembly

```asm
0x14003349c  push    rbx
0x14003349e  sub     rsp, 20h
0x1400334a2  mov     rbx, rcx
0x1400334a5  mov     rcx, [rcx+50h]; RunRefCacheAware
0x1400334a9  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x1400334b0  nop     dword ptr [rax+rax+00h]
0x1400334b5  lea     rcx, [rbx+58h]; Event
0x1400334b9  xor     r8d, r8d; Wait
0x1400334bc  xor     edx, edx; Increment
0x1400334be  call    cs:__imp_KeSetEvent
0x1400334c5  nop     dword ptr [rax+rax+00h]
0x1400334ca  lea     rcx, [rbx+18h]; Mutex
0x1400334ce  xor     edx, edx; Wait
0x1400334d0  call    cs:__imp_KeReleaseMutex
0x1400334d7  nop     dword ptr [rax+rax+00h]
0x1400334dc  add     rsp, 20h
0x1400334e0  pop     rbx
0x1400334e1  retn
```
