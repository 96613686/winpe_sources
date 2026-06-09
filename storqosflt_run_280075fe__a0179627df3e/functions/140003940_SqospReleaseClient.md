# SqospReleaseClient

- ea: `0x140003940`
- end: `0x1400039b4`
- name: `SqospReleaseClient`
- size: `116`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140006188`
- `0x1400117e4`
- `0x140011c5c`
- `0x140014d10`

## callees

- `0x140003940`
- `0x140015810`
- `0x1400158a0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140003965`
- `ntoskrnl!KeGetCurrentIrql` at `0x140003965`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000399f`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000399f`

## pseudocode

```c
void __fastcall SqospReleaseClient(volatile signed __int32 *Entry)
{
  if ( _InterlockedExchangeAdd(Entry + 3, 0xFFFFFFFF) == 1 )
  {
    if ( *((_BYTE *)Entry + 125) )
    {
      if ( KeGetCurrentIrql() > 1u )
        FltQueueGenericWorkItem(FltWorkItem, Filter, SqospClientRemovalWorkItemRoutine, DelayedWorkQueue, (PVOID)Entry);
      else
        SqospRemoveClient(Entry);
    }
    else
    {
      SqospCleanupClient((char *)Entry);
    }
  }
}

```

## disassembly

```asm
0x140003940  push    rbx
0x140003942  sub     rsp, 30h
0x140003946  mov     rbx, rcx
0x140003949  mov     eax, 0FFFFFFFFh
0x14000394e  lock xadd [rcx+0Ch], eax
0x140003953  cmp     eax, 1
0x140003956  jz      short loc_14000395F
0x140003958  add     rsp, 30h
0x14000395c  pop     rbx
0x14000395d  retn
0x14000395f  cmp     byte ptr [rcx+7Dh], 0
0x140003963  jz      short loc_1400039AD
0x140003965  call    cs:__imp_KeGetCurrentIrql
0x14000396c  nop     dword ptr [rax+rax+00h]
0x140003971  cmp     al, 1
0x140003973  ja      short loc_14000397F
0x140003975  mov     rcx, rbx; Entry
0x140003978  call    SqospRemoveClient
0x14000397d  jmp     short loc_140003958
0x14000397f  mov     rdx, cs:Filter; FltObject
0x140003986  lea     r8, SqospClientRemovalWorkItemRoutine; WorkerRoutine
0x14000398d  mov     rcx, cs:FltWorkItem; FltWorkItem
0x140003994  mov     r9d, 1; QueueType
0x14000399a  mov     [rsp+38h+Context], rbx; Context
0x14000399f  call    cs:__imp_FltQueueGenericWorkItem
0x1400039a6  nop     dword ptr [rax+rax+00h]
0x1400039ab  jmp     short loc_140003958
0x1400039ad  call    SqospCleanupClient
0x1400039b2  jmp     short loc_140003958
```
