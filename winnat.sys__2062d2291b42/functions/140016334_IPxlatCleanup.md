# IPxlatCleanup

- ea: `0x140016334`
- end: `0x1400164a1`
- name: `IPxlatCleanup`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000daf0`

## callees

- `0x140016334`
- `0x140017034`
- `0x14002e008`
- `0x14002e4b0`
- `0x14003476c`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140016414`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001644e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140016414`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001644e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400163d6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140016434`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400163d6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140016434`
- `ntoskrnl!ExDeleteResourceLite` at `0x140016468`
- `ntoskrnl!ExDeleteResourceLite` at `0x140016468`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14001637b`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14001637b`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140016362`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140016362`
- `fwpkclnt!FwpmBfeStateUnsubscribeChanges0` at `0x140016393`
- `fwpkclnt!FwpmBfeStateUnsubscribeChanges0` at `0x140016393`

## pseudocode

```c
NTSTATUS IPxlatCleanup()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // eax
  PVOID v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // r9
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  result = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( IPxlatGlobalState )
  {
    ExEnterCriticalRegionAndAcquireResourceExclusive(&stru_1400278F0);
    IPxlatGlobalState = 0;
    ExReleaseResourceAndLeaveCriticalRegion(&stru_1400278F0);
    if ( changeHandle )
    {
      v1 = FwpmBfeStateUnsubscribeChanges0(changeHandle);
      if ( v1 < 0 && (xmmword_1400272D0 & 2) != 0 )
        WPP_SF_d(513, 13, WPP_00475dad78ff34078f24129d9bdcf001_Traceguids, (unsigned int)v1);
      changeHandle = 0;
    }
    KeAcquireInStackQueuedSpinLock(&qword_140027958, &LockHandle);
    while ( 1 )
    {
      v2 = qword_1400278E0;
      if ( qword_1400278E0 == &qword_1400278E0 )
        break;
      if ( *((PVOID **)qword_1400278E0 + 1) != &qword_1400278E0
        || (v3 = *(_QWORD *)qword_1400278E0, *(PVOID *)(*(_QWORD *)qword_1400278E0 + 8LL) != qword_1400278E0) )
      {
        __fastfail(3u);
      }
      qword_1400278E0 = *(PVOID *)qword_1400278E0;
      *(_QWORD *)(v3 + 8) = &qword_1400278E0;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      IPxlatDeleteInstance(v2);
      KeAcquireInStackQueuedSpinLock(&qword_140027958, &LockHandle);
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    IPxlatConfigureCallouts(0);
    result = ExDeleteResourceLite(&stru_1400278F0);
    if ( (xmmword_1400272E0 & 2) != 0 )
    {
      LOBYTE(v5) = IPxlatGlobalState;
      return WPP_SF_c(v4, 14, WPP_00475dad78ff34078f24129d9bdcf001_Traceguids, v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140016334  mov     [rsp+arg_0], rbx
0x140016339  push    rdi
0x14001633a  sub     rsp, 40h
0x14001633e  xor     eax, eax
0x140016340  xor     ebx, ebx
0x140016342  cmp     cs:IPxlatGlobalState, bl
0x140016348  xorps   xmm0, xmm0
0x14001634b  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140016350  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140016355  jz      loc_140016495
0x14001635b  lea     rcx, stru_1400278F0; Resource
0x140016362  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140016369  nop     dword ptr [rax+rax+00h]
0x14001636e  lea     rcx, stru_1400278F0; Resource
0x140016375  mov     cs:IPxlatGlobalState, bl
0x14001637b  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140016382  nop     dword ptr [rax+rax+00h]
0x140016387  mov     rcx, cs:changeHandle; changeHandle
0x14001638e  test    rcx, rcx
0x140016391  jz      short loc_1400163CA
0x140016393  call    cs:__imp_FwpmBfeStateUnsubscribeChanges0
0x14001639a  nop     dword ptr [rax+rax+00h]
0x14001639f  test    eax, eax
0x1400163a1  jns     short loc_1400163C3
0x1400163a3  test    byte ptr cs:xmmword_1400272D0, 2
0x1400163aa  jz      short loc_1400163C3
0x1400163ac  lea     edx, [rbx+0Dh]
0x1400163af  mov     ecx, 201h
0x1400163b4  mov     r9d, eax
0x1400163b7  lea     r8, WPP_00475dad78ff34078f24129d9bdcf001_Traceguids
0x1400163be  call    WPP_SF_d
0x1400163c3  mov     cs:changeHandle, rbx
0x1400163ca  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x1400163cf  lea     rcx, qword_140027958; SpinLock
0x1400163d6  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400163dd  nop     dword ptr [rax+rax+00h]
0x1400163e2  lea     rdi, qword_1400278E0
0x1400163e9  mov     rbx, cs:qword_1400278E0
0x1400163f0  cmp     rbx, rdi
0x1400163f3  jz      short loc_140016449
0x1400163f5  cmp     [rbx+8], rdi
0x1400163f9  jnz     short loc_140016442
0x1400163fb  mov     rax, [rbx]
0x1400163fe  cmp     [rax+8], rbx
0x140016402  jnz     short loc_140016442
0x140016404  mov     cs:qword_1400278E0, rax
0x14001640b  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140016410  mov     [rax+8], rdi
0x140016414  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001641b  nop     dword ptr [rax+rax+00h]
0x140016420  mov     rcx, rbx; P
0x140016423  call    IPxlatDeleteInstance
0x140016428  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x14001642d  lea     rcx, qword_140027958; SpinLock
0x140016434  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001643b  nop     dword ptr [rax+rax+00h]
0x140016440  jmp     short loc_1400163E9
0x140016442  mov     ecx, 3
0x140016447  int     29h; Win8: RtlFailFast(ecx)
0x140016449  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14001644e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140016455  nop     dword ptr [rax+rax+00h]
0x14001645a  xor     ecx, ecx
0x14001645c  call    IPxlatConfigureCallouts
0x140016461  lea     rcx, stru_1400278F0; Resource
0x140016468  call    cs:__imp_ExDeleteResourceLite
0x14001646f  nop     dword ptr [rax+rax+00h]
0x140016474  test    byte ptr cs:xmmword_1400272E0, 2
0x14001647b  jz      short loc_140016495
0x14001647d  mov     r9b, cs:IPxlatGlobalState
0x140016484  lea     r8, WPP_00475dad78ff34078f24129d9bdcf001_Traceguids
0x14001648b  mov     edx, 0Eh
0x140016490  call    WPP_SF_c
0x140016495  mov     rbx, [rsp+48h+arg_0]
0x14001649a  add     rsp, 40h
0x14001649e  pop     rdi
0x14001649f  retn
```
