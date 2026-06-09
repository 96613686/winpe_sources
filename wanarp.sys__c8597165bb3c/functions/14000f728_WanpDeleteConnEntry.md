# WanpDeleteConnEntry

- ea: `0x14000f728`
- end: `0x14000f784`
- name: `WanpDeleteConnEntry`
- size: `92`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x140001010`
- `0x1400021b0`
- `0x140002450`
- `0x140003344`
- `0x14000f250`
- `0x14000f834`
- `0x14000f9c8`
- `0x14000fdc4`
- `0x140010448`
- `0x1400110bc`
- `0x140012e3c`
- `0x140015100`
- `0x1400152e0`
- `0x140015440`

## callees

- `0x14000f728`
- `0x140015db0`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x14000f760`
- `ntoskrnl!ExQueueWorkItem` at `0x14000f760`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f731`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f731`

## pseudocode

```c
void __fastcall WanpDeleteConnEntry(char *Entry)
{
  if ( KeGetCurrentIrql() == 2 )
  {
    *((_QWORD *)Entry + 24) = Entry;
    *((_QWORD *)Entry + 23) = WanpDeleteConnEntryPassive;
    *((_QWORD *)Entry + 21) = 0;
    ExQueueWorkItem((PWORK_QUEUE_ITEM)(Entry + 168), CriticalWorkQueue);
    Entry[200] = 1;
  }
  else
  {
    WanpDeleteConnEntryPassive(Entry);
  }
}

```

## disassembly

```asm
0x14000f728  push    rbx
0x14000f72a  sub     rsp, 20h
0x14000f72e  mov     rbx, rcx
0x14000f731  call    cs:__imp_KeGetCurrentIrql
0x14000f738  nop     dword ptr [rax+rax+00h]
0x14000f73d  cmp     al, 2
0x14000f73f  jnz     short loc_14000F775
0x14000f741  lea     rcx, [rbx+0A8h]; WorkItem
0x14000f748  xor     edx, edx; QueueType
0x14000f74a  lea     rax, WanpDeleteConnEntryPassive
0x14000f751  mov     [rcx+18h], rbx
0x14000f755  mov     [rcx+10h], rax
0x14000f759  mov     qword ptr [rcx], 0
0x14000f760  call    cs:__imp_ExQueueWorkItem
0x14000f767  nop     dword ptr [rax+rax+00h]
0x14000f76c  mov     byte ptr [rbx+0C8h], 1
0x14000f773  jmp     short loc_14000F77D
0x14000f775  mov     rcx, rbx; Entry
0x14000f778  call    WanpDeleteConnEntryPassive
0x14000f77d  add     rsp, 20h
0x14000f781  pop     rbx
0x14000f782  retn
```
