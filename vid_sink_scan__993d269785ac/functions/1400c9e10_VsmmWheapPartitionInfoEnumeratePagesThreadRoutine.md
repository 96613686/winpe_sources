# VsmmWheapPartitionInfoEnumeratePagesThreadRoutine

- ea: `0x1400c9e10`
- end: `0x1400c9e6c`
- name: `VsmmWheapPartitionInfoEnumeratePagesThreadRoutine`
- size: `92`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400c99ec`
- `0x1400c9e10`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x1400c9e5a`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400c9e5a`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400c9e4c`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400c9e4c`

## pseudocode

```c
void __fastcall VsmmWheapPartitionInfoEnumeratePagesThreadRoutine(volatile signed __int64 **StartContext)
{
  unsigned __int64 v1; // rax
  unsigned __int64 *v2; // rdx

  v1 = _InterlockedCompareExchange64(StartContext[5], 0, 0);
  v2 = (unsigned __int64 *)StartContext[3];
  if ( v1 < *v2 )
    VsmmWheapPartitionInfoEnumeratePages(StartContext[2], v2, StartContext[4], StartContext[5]);
  KeReleaseSemaphore(&VsmmWheapPageRangeInfoEnumeratePartitionPagesConcurrentLimit, 0, 1, 0);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x1400c9e10  sub     rsp, 28h
0x1400c9e14  mov     rdx, [rcx+28h]
0x1400c9e18  xor     r8d, r8d
0x1400c9e1b  xor     eax, eax
0x1400c9e1d  lock cmpxchg [rdx], r8
0x1400c9e22  mov     rdx, [rcx+18h]
0x1400c9e26  cmp     rax, [rdx]
0x1400c9e29  jnb     short loc_1400C9E3C
0x1400c9e2b  mov     r9, [rcx+28h]
0x1400c9e2f  mov     r8, [rcx+20h]
0x1400c9e33  mov     rcx, [rcx+10h]
0x1400c9e37  call    VsmmWheapPartitionInfoEnumeratePages
0x1400c9e3c  xor     r9d, r9d; Wait
0x1400c9e3f  lea     rcx, VsmmWheapPageRangeInfoEnumeratePartitionPagesConcurrentLimit; Semaphore
0x1400c9e46  xor     edx, edx; Increment
0x1400c9e48  lea     r8d, [r9+1]; Adjustment
0x1400c9e4c  call    cs:__imp_KeReleaseSemaphore
0x1400c9e53  nop     dword ptr [rax+rax+00h]
0x1400c9e58  xor     ecx, ecx; ExitStatus
0x1400c9e5a  call    cs:__imp_PsTerminateSystemThread
0x1400c9e61  nop     dword ptr [rax+rax+00h]
0x1400c9e66  add     rsp, 28h
0x1400c9e6a  retn
```
