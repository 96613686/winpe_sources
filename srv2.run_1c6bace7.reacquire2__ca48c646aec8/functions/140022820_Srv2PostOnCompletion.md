# Srv2PostOnCompletion

- ea: `0x140022820`
- end: `0x1400228b6`
- name: `Srv2PostOnCompletion`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140004960`
- `0x140005070`
- `0x140022820`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140022867`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140022867`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140022883`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140022883`

## string_xrefs

- `0x14002284e`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Srv2PostOnCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  __int64 v5; // rbx
  __int64 v6; // rbx
  char v8; // [rsp+20h] [rbp-18h]

  v3 = *(_DWORD *)(a3 + 8) == 5;
  *(_DWORD *)(a3 + 72) = 0;
  if ( v3 )
  {
    v8 = 1;
    LOBYTE(a2) = 1;
    SRV2_PERF_ENTER_EX(a3 + 584, a2, 391, "Srv2PostToThreadPool", v8);
  }
  v5 = *(_QWORD *)(*(_QWORD *)(a3 + 64) + 136LL);
  v6 = *(_QWORD *)(v5 + 8LL * KeGetCurrentNodeNumber() + 8);
  if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v6 + 16), (PSLIST_ENTRY)(a3 + 32)) && *(_WORD *)(v6 + 66) )
    RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v6);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140022820  mov     [rsp+arg_0], rbx
0x140022825  push    rdi
0x140022826  sub     rsp, 30h
0x14002282a  cmp     dword ptr [r8+8], 5
0x14002282f  mov     rdi, r8
0x140022832  mov     dword ptr [r8+48h], 0
0x14002283a  jnz     short loc_14002285C
0x14002283c  lea     rcx, [r8+248h]
0x140022843  mov     [rsp+38h+var_18], 1
0x140022848  mov     r8d, 187h
0x14002284e  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140022855  mov     dl, 1
0x140022857  call    SRV2_PERF_ENTER_EX
0x14002285c  mov     rax, [rdi+40h]
0x140022860  mov     rbx, [rax+88h]
0x140022867  call    cs:__imp_KeGetCurrentNodeNumber
0x14002286e  nop     dword ptr [rax+rax+00h]
0x140022873  movzx   eax, ax
0x140022876  lea     rdx, [rdi+20h]; ListEntry
0x14002287a  mov     rbx, [rbx+rax*8+8]
0x14002287f  lea     rcx, [rbx+10h]; ListHead
0x140022883  call    cs:__imp_ExpInterlockedPushEntrySList
0x14002288a  nop     dword ptr [rax+rax+00h]
0x14002288f  test    rax, rax
0x140022892  jnz     short loc_1400228A5
0x140022894  movzx   edx, word ptr [rbx+42h]
0x140022898  cmp     ax, dx
0x14002289b  jz      short loc_1400228A5
0x14002289d  mov     rcx, rbx
0x1400228a0  call    RfspThreadPoolNodeWakeIdleWorker
0x1400228a5  mov     rbx, [rsp+38h+arg_0]
0x1400228aa  mov     eax, 0C0000016h
0x1400228af  add     rsp, 30h
0x1400228b3  pop     rdi
0x1400228b4  retn
```
