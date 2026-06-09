# VmpAcquireRundownShared(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140002910`
- end: `0x1400029d7`
- name: `?VmpAcquireRundownShared@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400014d0`
- `0x1400015a0`
- `0x1400018e0`
- `0x140001ae0`

## callees

- `0x140002910`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002994`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002994`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000293a`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400029be`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000293a`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400029be`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400029ae`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400029ae`

## pseudocode

```c
__int64 __fastcall VmpAcquireRundownShared(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v3; // rcx
  unsigned int v5; // ebx
  struct _LIST_ENTRY *v7; // rdi
  struct _LIST_ENTRY *Blink; // rcx
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  v3 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)a1 + 14);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v5 = 0;
  if ( !ExAcquireRundownProtectionCacheAware(v3) )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a1 + 17, &LockHandle);
    if ( !ExAcquireRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)a1 + 14)) )
    {
      v7 = (struct _LIST_ENTRY *)((char *)a1 + 120);
      a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      Blink = v7->Blink;
      if ( Blink->Flink != v7 )
        __fastfail(3u);
      v5 = 259;
      a2->Tail.Overlay.ListEntry.Flink = v7;
      a2->Tail.Overlay.ListEntry.Blink = Blink;
      Blink->Flink = &a2->Tail.Overlay.ListEntry;
      v7->Blink = &a2->Tail.Overlay.ListEntry;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  return v5;
}

```

## disassembly

```asm
0x140002910  mov     [rsp+arg_0], rbx
0x140002915  mov     [rsp+arg_8], rsi
0x14000291a  push    rdi
0x14000291b  sub     rsp, 40h
0x14000291f  mov     rdi, rcx
0x140002922  xorps   xmm0, xmm0
0x140002925  mov     rcx, [rcx+70h]; RunRefCacheAware
0x140002929  xor     eax, eax
0x14000292b  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x140002930  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x140002935  mov     rsi, rdx
0x140002938  xor     ebx, ebx
0x14000293a  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140002941  nop     dword ptr [rax+rax+00h]
0x140002946  test    al, al
0x140002948  jz      short loc_1400029A2
0x14000294a  mov     rsi, [rsp+48h+arg_8]
0x14000294f  mov     eax, ebx
0x140002951  mov     rbx, [rsp+48h+arg_0]
0x140002956  add     rsp, 40h
0x14000295a  pop     rdi
0x14000295b  retn
0x14000295d  mov     rax, [rsi+0B8h]
0x140002964  add     rdi, 78h ; 'x'
0x140002968  or      byte ptr [rax+3], 1
0x14000296c  mov     rcx, [rdi+8]
0x140002970  cmp     [rcx], rdi
0x140002973  jnz     short loc_1400029D0
0x140002975  lea     rax, [rsi+0A8h]
0x14000297c  mov     ebx, 103h
0x140002981  mov     [rax], rdi
0x140002984  mov     [rax+8], rcx
0x140002988  mov     [rcx], rax
0x14000298b  mov     [rdi+8], rax
0x14000298f  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x140002994  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000299b  nop     dword ptr [rax+rax+00h]
0x1400029a0  jmp     short loc_14000294A
0x1400029a2  lea     rcx, [rdi+88h]; SpinLock
0x1400029a9  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x1400029ae  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400029b5  nop     dword ptr [rax+rax+00h]
0x1400029ba  mov     rcx, [rdi+70h]; RunRefCacheAware
0x1400029be  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x1400029c5  nop     dword ptr [rax+rax+00h]
0x1400029ca  test    al, al
0x1400029cc  jnz     short loc_14000298F
0x1400029ce  jmp     short loc_14000295D
0x1400029d0  mov     ecx, 3
0x1400029d5  int     29h; Win8: RtlFailFast(ecx)
```
