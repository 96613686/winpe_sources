# SqospDestroyJob

- ea: `0x140001ab0`
- end: `0x140001bbc`
- name: `SqospDestroyJob`
- size: `268`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `7`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140001010`
- `0x1400011c0`
- `0x140002300`
- `0x140002490`
- `0x1400066e0`
- `0x140006a38`
- `0x140006b04`

## callees

- `0x140001ab0`
- `0x140001bd0`
- `0x140004910`
- `0x140007824`
- `0x140015810`
- `0x1400158a0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140001b21`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140001b21`
- `ntoskrnl!KeGetCurrentIrql` at `0x140001b56`
- `ntoskrnl!KeGetCurrentIrql` at `0x140001b56`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140001b90`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140001b90`

## pseudocode

```c
void __fastcall SqospDestroyJob(_BYTE *Entry)
{
  __int64 Context; // rdi
  __int64 v3; // rcx
  unsigned __int64 v4; // rdi

  if ( Entry[128]
    && (unsigned __int8)BalanceUpdateStatsForCompletedJob()
    && ClientPort
    && *(_DWORD *)(**((_QWORD **)Entry + 5) + 188LL) == 2 )
  {
    SqospSetVolumeStatsTimer();
  }
  Context = *(_QWORD *)(*((_QWORD *)Entry + 5) + 8LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Context + 12), 0xFFFFFFFF) == 1 )
  {
    if ( *(_BYTE *)(Context + 125) )
    {
      if ( KeGetCurrentIrql() > 1u )
        FltQueueGenericWorkItem(
          FltWorkItem,
          Filter,
          SqospClientRemovalWorkItemRoutine,
          DelayedWorkQueue,
          (PVOID)Context);
      else
        SqospRemoveClient((_DWORD *)Context);
    }
    else
    {
      SqospCleanupClient((PVOID)Context);
    }
  }
  v3 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)Entry + 4) + 8LL) + 144LL);
  v4 = v3 + ((unsigned __int64)(unsigned int)(*((_DWORD *)Entry + 30) + 1) << 7);
  if ( !*(_BYTE *)(v4 + 176) )
    PplpLazyInitializeLookasideList(v3, v4 + 64);
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v4 + 64), Entry);
}

```

## disassembly

```asm
0x140001ab0  mov     [rsp+arg_0], rbx
0x140001ab5  push    rdi
0x140001ab6  sub     rsp, 30h
0x140001aba  cmp     byte ptr [rcx+80h], 0
0x140001ac1  mov     rbx, rcx
0x140001ac4  jz      short loc_140001AD9
0x140001ac6  call    BalanceUpdateStatsForCompletedJob
0x140001acb  test    al, al
0x140001acd  jz      short loc_140001AD9
0x140001acf  cmp     cs:ClientPort, 0
0x140001ad7  jnz     short loc_140001B39
0x140001ad9  mov     rax, [rbx+28h]
0x140001add  mov     rdi, [rax+8]
0x140001ae1  mov     eax, 0FFFFFFFFh
0x140001ae6  lock xadd [rdi+0Ch], eax
0x140001aeb  cmp     eax, 1
0x140001aee  jz      short loc_140001B50
0x140001af0  mov     rax, [rbx+20h]
0x140001af4  mov     edi, [rbx+78h]
0x140001af7  inc     edi
0x140001af9  shl     rdi, 7
0x140001afd  mov     rcx, [rax+8]
0x140001b01  mov     rcx, [rcx+90h]
0x140001b08  add     rdi, rcx
0x140001b0b  movzx   eax, byte ptr [rdi+0B0h]
0x140001b12  test    al, al
0x140001b14  jz      loc_140001BAE
0x140001b1a  mov     rdx, rbx; Entry
0x140001b1d  lea     rcx, [rdi+40h]; Lookaside
0x140001b21  call    cs:__imp_ExFreeToLookasideListEx
0x140001b28  nop     dword ptr [rax+rax+00h]
0x140001b2d  mov     rbx, [rsp+38h+arg_0]
0x140001b32  add     rsp, 30h
0x140001b36  pop     rdi
0x140001b37  retn
0x140001b39  mov     rax, [rbx+28h]
0x140001b3d  mov     rcx, [rax]
0x140001b40  cmp     dword ptr [rcx+0BCh], 2
0x140001b47  jnz     short loc_140001AD9
0x140001b49  call    SqospSetVolumeStatsTimer
0x140001b4e  jmp     short loc_140001AD9
0x140001b50  cmp     byte ptr [rdi+7Dh], 0
0x140001b54  jz      short loc_140001BA1
0x140001b56  call    cs:__imp_KeGetCurrentIrql
0x140001b5d  nop     dword ptr [rax+rax+00h]
0x140001b62  cmp     al, 1
0x140001b64  ja      short loc_140001B70
0x140001b66  mov     rcx, rdi; Entry
0x140001b69  call    SqospRemoveClient
0x140001b6e  jmp     short loc_140001AF0
0x140001b70  mov     rdx, cs:Filter; FltObject
0x140001b77  lea     r8, SqospClientRemovalWorkItemRoutine; WorkerRoutine
0x140001b7e  mov     rcx, cs:FltWorkItem; FltWorkItem
0x140001b85  mov     r9d, 1; QueueType
0x140001b8b  mov     [rsp+38h+Context], rdi; Context
0x140001b90  call    cs:__imp_FltQueueGenericWorkItem
0x140001b97  nop     dword ptr [rax+rax+00h]
0x140001b9c  jmp     loc_140001AF0
0x140001ba1  mov     rcx, rdi; Entry
0x140001ba4  call    SqospCleanupClient
0x140001ba9  jmp     loc_140001AF0
0x140001bae  lea     rdx, [rdi+40h]
0x140001bb2  call    PplpLazyInitializeLookasideList
0x140001bb7  jmp     loc_140001B1A
```
