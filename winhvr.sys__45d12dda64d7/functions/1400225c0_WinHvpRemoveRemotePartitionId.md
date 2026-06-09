# WinHvpRemoveRemotePartitionId

- ea: `0x1400225c0`
- end: `0x140022669`
- name: `WinHvpRemoveRemotePartitionId`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140021c40`

## callees

- `0x14000b040`
- `0x1400225c0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140022623`
- `ntoskrnl!ExReleaseFastMutex` at `0x140022623`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400225d9`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400225d9`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140022638`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140022638`

## pseudocode

```c
void __fastcall WinHvpRemoveRemotePartitionId(__int64 a1)
{
  struct _EX_RUNDOWN_REF *i; // rbx
  ULONG_PTR Count; // rax
  struct _EX_RUNDOWN_REF **v4; // rcx

  ExAcquireFastMutex(&WinHvpRemoteIdMapLock);
  for ( i = (struct _EX_RUNDOWN_REF *)WinHvpRemoteIdMap;
        i != (struct _EX_RUNDOWN_REF *)&WinHvpRemoteIdMap;
        i = (struct _EX_RUNDOWN_REF *)i->Count )
  {
    Count = i->Count;
    if ( i[2].Count == a1 )
    {
      if ( *(struct _EX_RUNDOWN_REF **)(Count + 8) != i || (v4 = (struct _EX_RUNDOWN_REF **)i[1].Count, *v4 != i) )
        __fastfail(3u);
      *v4 = (struct _EX_RUNDOWN_REF *)Count;
      *(_QWORD *)(Count + 8) = v4;
      break;
    }
  }
  ExReleaseFastMutex(&WinHvpRemoteIdMapLock);
  if ( i != (struct _EX_RUNDOWN_REF *)&WinHvpRemoteIdMap )
  {
    ExWaitForRundownProtectionRelease(i + 14);
    WinHvpFreePoolWithTag(i, 1500923991);
  }
}

```

## disassembly

```asm
0x1400225c0  mov     [rsp+arg_0], rbx
0x1400225c5  mov     [rsp+arg_8], rsi
0x1400225ca  push    rdi
0x1400225cb  sub     rsp, 20h
0x1400225cf  mov     rdi, rcx
0x1400225d2  lea     rcx, WinHvpRemoteIdMapLock; FastMutex
0x1400225d9  call    cs:__imp_ExAcquireFastMutex
0x1400225e0  nop     dword ptr [rax+rax+00h]
0x1400225e5  mov     rbx, cs:WinHvpRemoteIdMap
0x1400225ec  lea     rsi, WinHvpRemoteIdMap
0x1400225f3  cmp     rbx, rsi
0x1400225f6  jz      short loc_14002261C
0x1400225f8  mov     rax, [rbx]
0x1400225fb  cmp     [rbx+10h], rdi
0x1400225ff  jz      short loc_140022606
0x140022601  mov     rbx, rax
0x140022604  jmp     short loc_1400225F3
0x140022606  cmp     [rax+8], rbx
0x14002260a  jnz     short loc_140022662
0x14002260c  mov     rcx, [rbx+8]
0x140022610  cmp     [rcx], rbx
0x140022613  jnz     short loc_140022662
0x140022615  mov     [rcx], rax
0x140022618  mov     [rax+8], rcx
0x14002261c  lea     rcx, WinHvpRemoteIdMapLock; FastMutex
0x140022623  call    cs:__imp_ExReleaseFastMutex
0x14002262a  nop     dword ptr [rax+rax+00h]
0x14002262f  cmp     rbx, rsi
0x140022632  jz      short loc_140022651
0x140022634  lea     rcx, [rbx+70h]; RunRef
0x140022638  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14002263f  nop     dword ptr [rax+rax+00h]
0x140022644  mov     edx, 59764857h
0x140022649  mov     rcx, rbx
0x14002264c  call    WinHvpFreePoolWithTag
0x140022651  mov     rbx, [rsp+28h+arg_0]
0x140022656  mov     rsi, [rsp+28h+arg_8]
0x14002265b  add     rsp, 20h
0x14002265f  pop     rdi
0x140022660  retn
0x140022662  mov     ecx, 3
0x140022667  int     29h; Win8: RtlFailFast(ecx)
```
