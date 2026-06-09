# TmpAdjustVirtualClock

- ea: `0x1400209fc`
- end: `0x140020a64`
- name: `TmpAdjustVirtualClock`
- size: `104`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fed0`
- `0x140010140`
- `0x140010220`
- `0x140010500`
- `0x1400106c0`
- `0x14001a000`
- `0x14001c010`
- `0x140020250`

## callees

- `0x1400209fc`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140020a25`
- `ntoskrnl!ExAcquireFastMutex` at `0x140020a25`
- `ntoskrnl!ExReleaseFastMutex` at `0x140020a47`
- `ntoskrnl!ExReleaseFastMutex` at `0x140020a47`

## pseudocode

```c
void __fastcall TmpAdjustVirtualClock(__int64 a1, _QWORD *a2)
{
  struct _FAST_MUTEX *v4; // rsi

  if ( a1 && a2 )
  {
    v4 = (struct _FAST_MUTEX *)(a1 + 592);
    ExAcquireFastMutex((PFAST_MUTEX)(a1 + 592));
    if ( *a2 > *(_QWORD *)(a1 + 584) )
      *(_QWORD *)(a1 + 584) = *a2;
    ExReleaseFastMutex(v4);
  }
}

```

## disassembly

```asm
0x1400209fc  test    rcx, rcx
0x1400209ff  jz      short locret_140020A62
0x140020a01  mov     [rsp+arg_0], rbx
0x140020a06  mov     [rsp+arg_8], rsi
0x140020a0b  push    rdi
0x140020a0c  sub     rsp, 20h
0x140020a10  mov     rdi, rdx
0x140020a13  mov     rbx, rcx
0x140020a16  test    rdx, rdx
0x140020a19  jz      short loc_140020A53
0x140020a1b  lea     rsi, [rcx+250h]
0x140020a22  mov     rcx, rsi; FastMutex
0x140020a25  call    cs:__imp_ExAcquireFastMutex
0x140020a2c  nop     dword ptr [rax+rax+00h]
0x140020a31  mov     rax, [rdi]
0x140020a34  cmp     rax, [rbx+248h]
0x140020a3b  jle     short loc_140020A44
0x140020a3d  mov     [rbx+248h], rax
0x140020a44  mov     rcx, rsi; FastMutex
0x140020a47  call    cs:__imp_ExReleaseFastMutex
0x140020a4e  nop     dword ptr [rax+rax+00h]
0x140020a53  mov     rbx, [rsp+28h+arg_0]
0x140020a58  mov     rsi, [rsp+28h+arg_8]
0x140020a5d  add     rsp, 20h
0x140020a61  pop     rdi
0x140020a62  retn
```
