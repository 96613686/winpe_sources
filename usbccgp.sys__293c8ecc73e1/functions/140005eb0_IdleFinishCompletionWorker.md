# IdleFinishCompletionWorker

- ea: `0x140005eb0`
- end: `0x140005f59`
- name: `IdleFinishCompletionWorker`
- size: `169`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004b08`
- `0x140005bb0`
- `0x140013eb0`

## callees

- `0x1400054a0`
- `0x140005eb0`
- `0x14000773c`
- `0x140008230`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005eef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005eef`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140005f2e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140005f2e`
- `ntoskrnl!KeSetEvent` at `0x140005f07`
- `ntoskrnl!KeSetEvent` at `0x140005f07`

## pseudocode

```c
void __fastcall IdleFinishCompletionWorker(__int64 a1, __int64 a2, __int64 a3)
{
  void *v4; // rsi

  v4 = *(void **)(a2 + 16);
  if ( !*(_BYTE *)(a1 + 1362) || *(_DWORD *)(a1 + 576) == 2 )
    CompleteAllFunctionIdleIrps(a1, *(_DWORD *)(a2 + 8));
  LOBYTE(a3) = 1;
  ChangeIdleState(a1, 0, a3);
  ExFreePoolWithTag((PVOID)a2, 0x43627355u);
  KeSetEvent((PRKEVENT)(a1 + 960), 0, 0);
  UsbcReleaseRemoveLock(a1, v4);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 200), v4, 0x20u);
}

```

## disassembly

```asm
0x140005eb0  mov     [rsp+arg_0], rbx
0x140005eb5  mov     [rsp+arg_8], rsi
0x140005eba  push    rdi
0x140005ebb  sub     rsp, 20h
0x140005ebf  cmp     byte ptr [rcx+552h], 0
0x140005ec6  mov     rdi, rdx
0x140005ec9  mov     rsi, [rdx+10h]
0x140005ecd  mov     rbx, rcx
0x140005ed0  jnz     short loc_140005F4B
0x140005ed2  mov     edx, [rdx+8]
0x140005ed5  call    CompleteAllFunctionIdleIrps
0x140005eda  mov     r8b, 1
0x140005edd  xor     edx, edx
0x140005edf  mov     rcx, rbx
0x140005ee2  call    ChangeIdleState
0x140005ee7  mov     edx, 43627355h; Tag
0x140005eec  mov     rcx, rdi; P
0x140005eef  call    cs:__imp_ExFreePoolWithTag
0x140005ef6  nop     dword ptr [rax+rax+00h]
0x140005efb  lea     rcx, [rbx+3C0h]; Event
0x140005f02  xor     r8d, r8d; Wait
0x140005f05  xor     edx, edx; Increment
0x140005f07  call    cs:__imp_KeSetEvent
0x140005f0e  nop     dword ptr [rax+rax+00h]
0x140005f13  mov     rdx, rsi
0x140005f16  mov     rcx, rbx
0x140005f19  call    UsbcReleaseRemoveLock
0x140005f1e  lea     rcx, [rbx+0C8h]; RemoveLock
0x140005f25  mov     r8d, 20h ; ' '; RemlockSize
0x140005f2b  mov     rdx, rsi; Tag
0x140005f2e  call    cs:__imp_IoReleaseRemoveLockEx
0x140005f35  nop     dword ptr [rax+rax+00h]
0x140005f3a  mov     rbx, [rsp+28h+arg_0]
0x140005f3f  mov     rsi, [rsp+28h+arg_8]
0x140005f44  add     rsp, 20h
0x140005f48  pop     rdi
0x140005f49  retn
0x140005f4b  cmp     dword ptr [rcx+240h], 2
0x140005f52  jnz     short loc_140005EDA
0x140005f54  jmp     loc_140005ED2
```
