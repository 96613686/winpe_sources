# TmpLogGrowthCompletedNotification

- ea: `0x14000df30`
- end: `0x14000df92`
- name: `TmpLogGrowthCompletedNotification`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000dfa0`
- `0x14000fa08`

## callees

- `0x14000df30`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x14000df80`
- `ntoskrnl!ExQueueWorkItem` at `0x14000df80`

## pseudocode

```c
void __fastcall TmpLogGrowthCompletedNotification(__int64 a1, int a2, char a3, __int64 a4)
{
  *(_DWORD *)(a4 + 892) = a2;
  _InterlockedOr((volatile signed __int32 *)(a4 + 132), a3 != 0 ? 6 : 2);
  if ( !a3 )
    _InterlockedAnd((volatile signed __int32 *)(a4 + 132), 0xFFFFFFFB);
  *(_QWORD *)(a4 + 776) = a4;
  *(_QWORD *)(a4 + 768) = TmpLogFullCompletedWorker;
  *(_QWORD *)(a4 + 752) = 0;
  ExQueueWorkItem((PWORK_QUEUE_ITEM)(a4 + 752), DelayedWorkQueue);
}

```

## disassembly

```asm
0x14000df30  sub     rsp, 28h
0x14000df34  mov     al, r8b
0x14000df37  mov     [r9+37Ch], edx
0x14000df3e  neg     al
0x14000df40  sbb     ecx, ecx
0x14000df42  and     ecx, 4
0x14000df45  add     ecx, 2
0x14000df48  lock or [r9+84h], ecx
0x14000df50  test    r8b, r8b
0x14000df53  jnz     short loc_14000DF5E
0x14000df55  lock and dword ptr [r9+84h], 0FFFFFFFBh
0x14000df5e  lea     rcx, [r9+2F0h]; WorkItem
0x14000df65  mov     edx, 1; QueueType
0x14000df6a  lea     rax, TmpLogFullCompletedWorker
0x14000df71  mov     [rcx+18h], r9
0x14000df75  mov     [rcx+10h], rax
0x14000df79  mov     qword ptr [rcx], 0
0x14000df80  call    cs:__imp_ExQueueWorkItem
0x14000df87  nop     dword ptr [rax+rax+00h]
0x14000df8c  add     rsp, 28h
0x14000df90  retn
```
