# WanpLastOidComplete

- ea: `0x1400030e0`
- end: `0x1400031a4`
- name: `WanpLastOidComplete`
- size: `196`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400031b0`
- `0x140003210`
- `0x140003280`

## callees

- `0x1400030e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400030f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400030f8`
- `ntoskrnl!ExQueueWorkItem` at `0x14000318c`
- `ntoskrnl!ExQueueWorkItem` at `0x14000318c`

## pseudocode

```c
void __fastcall WanpLastOidComplete(__int64 a1, void *a2, int a3)
{
  int *v5; // rax
  int *v6; // rax
  struct _WORK_QUEUE_ITEM *v7; // rcx
  __int64 (__fastcall *v8)(char); // rax

  ExFreePoolWithTag(a2, 0);
  if ( a3 )
  {
    v5 = &dword_140009A24;
    if ( a1 != 212578788 )
      v5 = &dword_140009B44;
    *v5 = a3;
    v6 = &dword_140009A20;
    if ( a1 != 212578788 )
      v6 = &Status;
    v7 = (struct _WORK_QUEUE_ITEM *)qword_140009A50;
    *v6 = a3;
    if ( a1 != 212578788 )
      v7 = &stru_140009B70;
    v8 = (__int64 (__fastcall *)(char))WanpCloseNdisWan;
  }
  else
  {
    v7 = (struct _WORK_QUEUE_ITEM *)qword_140009A30;
    if ( a1 != 212578788 )
      v7 = &WorkItem;
    v8 = WanpNdisCompleteBindAdapter;
  }
  v7->Parameter = (PVOID)(a1 == 212578788);
  v7->WorkerRoutine = (PWORKER_THREAD_ROUTINE)v8;
  v7->List.Flink = 0;
  ExQueueWorkItem(v7, DelayedWorkQueue);
}

```

## disassembly

```asm
0x1400030e0  mov     [rsp+arg_0], rbx
0x1400030e5  push    rdi
0x1400030e6  sub     rsp, 20h
0x1400030ea  mov     rax, rdx
0x1400030ed  mov     rbx, rcx
0x1400030f0  mov     rcx, rax; P
0x1400030f3  xor     edx, edx; Tag
0x1400030f5  mov     edi, r8d
0x1400030f8  call    cs:__imp_ExFreePoolWithTag
0x1400030ff  nop     dword ptr [rax+rax+00h]
0x140003104  xor     edx, edx
0x140003106  mov     r8d, 0CABB1E4h
0x14000310c  cmp     rbx, r8
0x14000310f  setz    dl
0x140003112  test    edi, edi
0x140003114  jz      short loc_14000315C
0x140003116  cmp     rbx, r8
0x140003119  lea     rcx, dword_140009B44
0x140003120  lea     rax, dword_140009A24
0x140003127  cmovnz  rax, rcx
0x14000312b  lea     rcx, Status
0x140003132  mov     [rax], edi
0x140003134  lea     rax, dword_140009A20
0x14000313b  cmovnz  rax, rcx
0x14000313f  lea     rcx, qword_140009A50
0x140003146  mov     [rax], edi
0x140003148  lea     rax, stru_140009B70
0x14000314f  cmovnz  rcx, rax
0x140003153  lea     rax, WanpCloseNdisWan
0x14000315a  jmp     short loc_140003178
0x14000315c  lea     rax, WorkItem
0x140003163  cmp     rbx, r8
0x140003166  lea     rcx, qword_140009A30
0x14000316d  cmovnz  rcx, rax; WorkItem
0x140003171  lea     rax, WanpNdisCompleteBindAdapter
0x140003178  mov     [rcx+18h], rdx
0x14000317c  mov     edx, 1; QueueType
0x140003181  mov     [rcx+10h], rax
0x140003185  mov     qword ptr [rcx], 0
0x14000318c  call    cs:__imp_ExQueueWorkItem
0x140003193  nop     dword ptr [rax+rax+00h]
0x140003198  mov     rbx, [rsp+28h+arg_0]
0x14000319d  add     rsp, 20h
0x1400031a1  pop     rdi
0x1400031a2  retn
```
