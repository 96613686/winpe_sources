# WimFSFReleaseConfigLock

- ea: `0x14000d250`
- end: `0x14000d278`
- name: `WimFSFReleaseConfigLock`
- size: `40`
- prototype: `__int64 __fastcall(_QWORD)`
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

- `ntoskrnl!KeReleaseMutex` at `0x14000d25a`
- `ntoskrnl!KeReleaseMutex` at `0x14000d25a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d266`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d266`

## pseudocode

```c
void __fastcall WimFSFReleaseConfigLock(__int64 a1)
{
  KeReleaseMutex((PRKMUTEX)(a1 + 40), 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14000d250  sub     rsp, 28h
0x14000d254  add     rcx, 28h ; '('; Mutex
0x14000d258  xor     edx, edx; Wait
0x14000d25a  call    cs:__imp_KeReleaseMutex
0x14000d261  nop     dword ptr [rax+rax+00h]
0x14000d266  call    cs:__imp_KeLeaveCriticalRegion
0x14000d26d  nop     dword ptr [rax+rax+00h]
0x14000d272  add     rsp, 28h
0x14000d276  retn
```
