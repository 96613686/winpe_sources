# Smb2SequentialReadComplete

- ea: `0x140004560`
- end: `0x1400046d1`
- name: `Smb2SequentialReadComplete`
- size: `369`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400041a0`
- `0x14007f4c0`
- `0x14007fd00`
- `0x1400800c4`

## callees

- `0x140004560`
- `0x140004960`
- `0x140005070`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140004649`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140004649`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140004665`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140004665`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400045b0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400045b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000458a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000458a`

## string_xrefs

- `0x14000462a`: `Srv2PostToThreadPool`

## pseudocode

```c
void __fastcall Smb2SequentialReadComplete(__int64 a1)
{
  __int64 v1; // rdx
  _QWORD *v2; // rcx
  _QWORD *v3; // rax
  __int64 v4; // rdx
  _QWORD *v5; // rdi
  bool v6; // zf
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rbx
  __int64 v10; // rcx
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( Smb2AllowSequentialRead )
  {
    v9 = *(_QWORD *)(a1 + 560);
    v10 = *(_QWORD *)(v9 + 72);
    if ( (*(_DWORD *)(v10 + 192) & 4) != 0 )
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v10 + 112), &LockHandle);
      v1 = *(_QWORD *)(v9 + 72);
      v2 = (_QWORD *)(v1 + 432);
      v3 = *(_QWORD **)(v1 + 432);
      if ( v3 == (_QWORD *)(v1 + 432) )
      {
        *(_QWORD *)(v1 + 448) = 0;
      }
      else
      {
        if ( (_QWORD *)v3[1] != v2 || (v4 = *v3, *(_QWORD **)(*v3 + 8LL) != v3) )
          __fastfail(3u);
        *v2 = v4;
        *(_QWORD *)(v4 + 8) = v2;
        v5 = v3 - 71;
        v5[6] = Smb2ExecuteReadCallback;
        *(_QWORD *)(*(_QWORD *)(v9 + 72) + 448LL) = v3 - 71;
        v6 = *((_DWORD *)v3 - 140) == 5;
        *((_DWORD *)v5 + 18) = 0;
        if ( v6 )
        {
          LOBYTE(v4) = 1;
          SRV2_PERF_ENTER_EX(v5 + 73, v4, 391, "Srv2PostToThreadPool", 1);
        }
        v7 = *(_QWORD *)(v5[8] + 136LL);
        v8 = *(_QWORD *)(v7 + 8LL * KeGetCurrentNodeNumber() + 8);
        if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v8 + 16), (PSLIST_ENTRY)v5 + 2) )
        {
          if ( *(_WORD *)(v8 + 66) )
            RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v8);
        }
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
  }
}

```

## disassembly

```asm
0x140004560  sub     rsp, 58h
0x140004564  xor     eax, eax
0x140004566  xorps   xmm0, xmm0
0x140004569  cmp     cs:Smb2AllowSequentialRead, al
0x14000456f  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x140004574  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x140004579  jnz     loc_140004699
0x14000457f  add     rsp, 58h
0x140004583  retn
0x140004585  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14000458a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140004591  nop     dword ptr [rax+rax+00h]
0x140004596  mov     rsi, [rsp+58h+arg_8]
0x14000459b  mov     rbx, [rsp+58h+arg_0]
0x1400045a0  jmp     short loc_14000457F
0x1400045a2  add     rcx, 70h ; 'p'; SpinLock
0x1400045a6  mov     [rsp+58h+arg_8], rsi
0x1400045ab  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x1400045b0  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400045b7  nop     dword ptr [rax+rax+00h]
0x1400045bc  mov     rdx, [rbx+48h]
0x1400045c0  lea     rcx, [rdx+1B0h]
0x1400045c7  mov     rax, [rcx]
0x1400045ca  cmp     rax, rcx
0x1400045cd  jz      loc_1400046BC
0x1400045d3  cmp     [rax+8], rcx
0x1400045d7  jnz     loc_1400046CA
0x1400045dd  mov     rdx, [rax]
0x1400045e0  cmp     [rdx+8], rax
0x1400045e4  jnz     loc_1400046CA
0x1400045ea  mov     [rcx], rdx
0x1400045ed  xor     esi, esi
0x1400045ef  mov     [rdx+8], rcx
0x1400045f3  mov     [rsp+58h+var_8], rdi
0x1400045f8  lea     rdi, [rax-238h]
0x1400045ff  lea     rax, Smb2ExecuteReadCallback
0x140004606  mov     [rdi+30h], rax
0x14000460a  mov     rax, [rbx+48h]
0x14000460e  mov     [rax+1C0h], rdi
0x140004615  cmp     dword ptr [rdi+8], 5
0x140004619  mov     [rdi+48h], esi
0x14000461c  jnz     short loc_14000463E
0x14000461e  lea     rcx, [rdi+248h]
0x140004625  mov     [rsp+58h+var_38], 1
0x14000462a  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140004631  mov     r8d, 187h
0x140004637  mov     dl, 1
0x140004639  call    SRV2_PERF_ENTER_EX
0x14000463e  mov     rax, [rdi+40h]
0x140004642  mov     rbx, [rax+88h]
0x140004649  call    cs:__imp_KeGetCurrentNodeNumber
0x140004650  nop     dword ptr [rax+rax+00h]
0x140004655  movzx   eax, ax
0x140004658  lea     rdx, [rdi+20h]; ListEntry
0x14000465c  mov     rbx, [rbx+rax*8+8]
0x140004661  lea     rcx, [rbx+10h]; ListHead
0x140004665  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000466c  nop     dword ptr [rax+rax+00h]
0x140004671  mov     rdi, [rsp+58h+var_8]
0x140004676  test    rax, rax
0x140004679  jnz     loc_140004585
0x14000467f  movzx   eax, word ptr [rbx+42h]
0x140004683  cmp     si, ax
0x140004686  jz      loc_140004585
0x14000468c  mov     rcx, rbx
0x14000468f  call    RfspThreadPoolNodeWakeIdleWorker
0x140004694  jmp     loc_140004585
0x140004699  mov     [rsp+58h+arg_0], rbx
0x14000469e  mov     rbx, [rcx+230h]
0x1400046a5  mov     rcx, [rbx+48h]
0x1400046a9  mov     eax, [rcx+0C0h]
0x1400046af  test    al, 4
0x1400046b1  jz      loc_14000459B
0x1400046b7  jmp     loc_1400045A2
0x1400046bc  xor     esi, esi
0x1400046be  mov     [rdx+1C0h], rsi
0x1400046c5  jmp     loc_140004585
0x1400046ca  mov     ecx, 3
0x1400046cf  int     29h; Win8: RtlFailFast(ecx)
```
