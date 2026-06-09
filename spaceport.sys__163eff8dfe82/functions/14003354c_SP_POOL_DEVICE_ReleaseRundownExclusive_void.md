# SP_POOL_DEVICE::ReleaseRundownExclusive(void)

- ea: `0x14003354c`
- end: `0x140033593`
- name: `?ReleaseRundownExclusive@SP_POOL_DEVICE@@QEAAXXZ`
- size: `71`
- prototype: `void __fastcall(SP_POOL_DEVICE *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14008ce50`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140033559`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140033559`
- `ntoskrnl!KeSetEvent` at `0x14003356e`
- `ntoskrnl!KeSetEvent` at `0x14003356e`
- `ntoskrnl!KeReleaseMutex` at `0x140033580`
- `ntoskrnl!KeReleaseMutex` at `0x140033580`

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
0x14003354c  push    rbx
0x14003354e  sub     rsp, 20h
0x140033552  mov     rbx, rcx
0x140033555  mov     rcx, [rcx+50h]; RunRefCacheAware
0x140033559  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x140033560  nop     dword ptr [rax+rax+00h]
0x140033565  lea     rcx, [rbx+58h]; Event
0x140033569  xor     r8d, r8d; Wait
0x14003356c  xor     edx, edx; Increment
0x14003356e  call    cs:__imp_KeSetEvent
0x140033575  nop     dword ptr [rax+rax+00h]
0x14003357a  lea     rcx, [rbx+18h]; Mutex
0x14003357e  xor     edx, edx; Wait
0x140033580  call    cs:__imp_KeReleaseMutex
0x140033587  nop     dword ptr [rax+rax+00h]
0x14003358c  add     rsp, 20h
0x140033590  pop     rbx
0x140033591  retn
```
