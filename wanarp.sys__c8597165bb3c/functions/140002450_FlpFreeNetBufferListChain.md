# FlpFreeNetBufferListChain

- ea: `0x140002450`
- end: `0x1400024bc`
- name: `FlpFreeNetBufferListChain`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002450`
- `0x14000f728`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002470`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002470`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002483`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002483`
- `NETIO!NetioCompleteCopyNetBufferListChain` at `0x140002460`
- `NETIO!NetioCompleteCopyNetBufferListChain` at `0x140002460`

## pseudocode

```c
void __fastcall FlpFreeNetBufferListChain(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  int v4; // ebx
  KIRQL v5; // al

  v3 = *(_QWORD *)(a1 + 88);
  v4 = a2;
  NetioCompleteCopyNetBufferListChain(a1, a2, a3);
  v5 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(v3 + 80));
  KeReleaseSpinLock(*(PKSPIN_LOCK *)(v3 + 80), v5);
  while ( v4 )
  {
    --v4;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 96), 0xFFFFFFFF) == 1 )
      WanpDeleteConnEntry((PVOID)v3);
  }
}

```

## disassembly

```asm
0x140002450  mov     [rsp+arg_0], rbx
0x140002455  push    rdi
0x140002456  sub     rsp, 20h
0x14000245a  mov     rdi, [rcx+58h]
0x14000245e  mov     ebx, edx
0x140002460  call    cs:__imp_NetioCompleteCopyNetBufferListChain
0x140002467  nop     dword ptr [rax+rax+00h]
0x14000246c  mov     rcx, [rdi+50h]; SpinLock
0x140002470  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002477  nop     dword ptr [rax+rax+00h]
0x14000247c  mov     rcx, [rdi+50h]; SpinLock
0x140002480  movzx   edx, al; NewIrql
0x140002483  call    cs:__imp_KeReleaseSpinLock
0x14000248a  nop     dword ptr [rax+rax+00h]
0x14000248f  test    ebx, ebx
0x140002491  jz      short loc_1400024B0
0x140002493  dec     ebx
0x140002495  mov     eax, 0FFFFFFFFh
0x14000249a  lock xadd [rdi+60h], eax
0x14000249f  cmp     eax, 1
0x1400024a2  jnz     short loc_1400024AC
0x1400024a4  mov     rcx, rdi; Entry
0x1400024a7  call    WanpDeleteConnEntry
0x1400024ac  test    ebx, ebx
0x1400024ae  jnz     short loc_140002493
0x1400024b0  mov     rbx, [rsp+28h+arg_0]
0x1400024b5  add     rsp, 20h
0x1400024b9  pop     rdi
0x1400024ba  retn
```
