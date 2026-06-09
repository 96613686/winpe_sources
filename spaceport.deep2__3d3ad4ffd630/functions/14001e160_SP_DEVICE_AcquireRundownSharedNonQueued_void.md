# SP_DEVICE::AcquireRundownSharedNonQueued(void)

- ea: `0x14001e160`
- end: `0x14001e1f1`
- name: `?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ`
- size: `145`
- prototype: `__int64 __fastcall(SP_DEVICE *__hidden this)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x14001e060`
- `0x140028e80`
- `0x14002b360`
- `0x14002b608`
- `0x140038c60`
- `0x14003bbb0`
- `0x14003bc50`
- `0x14008c360`
- `0x140095d18`
- `0x1400a0a10`
- `0x1400a2870`
- `0x1400a5308`
- `0x1400a5960`
- `0x1400ada94`
- `0x1400b6030`
- `0x1400b7130`

## callees

- `0x14001e160`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001e19f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001e19f`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e1db`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e1db`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14001e176`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14001e1b2`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14001e176`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14001e1b2`

## pseudocode

```c
__int64 __fastcall SP_DEVICE::AcquireRundownSharedNonQueued(PEX_RUNDOWN_REF_CACHE_AWARE *this)
{
  while ( !ExAcquireRundownProtectionCacheAware(this[30]) )
    KeWaitForSingleObject(this + 32, Executive, 0, 0, 0);
  if ( this[403] )
    return 0;
  ExReleaseRundownProtectionCacheAware(this[30]);
  return 3221225486LL;
}

```

## disassembly

```asm
0x14001e160  mov     [rsp+arg_8], rbx
0x14001e165  push    rsi
0x14001e166  sub     rsp, 30h
0x14001e16a  mov     rbx, rcx
0x14001e16d  xor     esi, esi
0x14001e16f  mov     rcx, [rcx+0F0h]; RunRefCacheAware
0x14001e176  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14001e17d  nop     dword ptr [rax+rax+00h]
0x14001e182  test    al, al
0x14001e184  jnz     short loc_14001E1C7
0x14001e186  mov     [rsp+38h+arg_0], rdi
0x14001e18b  xor     r9d, r9d; Alertable
0x14001e18e  mov     [rsp+38h+Timeout], rsi; Timeout
0x14001e193  xor     r8d, r8d; WaitMode
0x14001e196  lea     rcx, [rbx+100h]; Object
0x14001e19d  xor     edx, edx; WaitReason
0x14001e19f  call    cs:__imp_KeWaitForSingleObject
0x14001e1a6  nop     dword ptr [rax+rax+00h]
0x14001e1ab  mov     rcx, [rbx+0F0h]; RunRefCacheAware
0x14001e1b2  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14001e1b9  nop     dword ptr [rax+rax+00h]
0x14001e1be  test    al, al
0x14001e1c0  jz      short loc_14001E18B
0x14001e1c2  mov     rdi, [rsp+38h+arg_0]
0x14001e1c7  cmp     [rbx+0C98h], rsi
0x14001e1ce  jnz     loc_14006B3A6
0x14001e1d4  mov     rcx, [rbx+0F0h]; RunRefCacheAware
0x14001e1db  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14001e1e2  nop     dword ptr [rax+rax+00h]
0x14001e1e7  mov     eax, 0C000000Eh
0x14001e1ec  jmp     loc_14006B3A8
0x14006b3a6  mov     eax, esi
0x14006b3a8  mov     rbx, [rsp+38h+arg_8]
0x14006b3ad  add     rsp, 30h
0x14006b3b1  pop     rsi
0x14006b3b2  retn
```
