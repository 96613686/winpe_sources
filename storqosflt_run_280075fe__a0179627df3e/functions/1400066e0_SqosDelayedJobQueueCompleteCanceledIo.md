# SqosDelayedJobQueueCompleteCanceledIo

- ea: `0x1400066e0`
- end: `0x1400067b7`
- name: `SqosDelayedJobQueueCompleteCanceledIo`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001ab0`
- `0x140004550`
- `0x1400066e0`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140006758`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140006758`
- `HAL!KeQueryPerformanceCounter` at `0x140006707`
- `HAL!KeQueryPerformanceCounter` at `0x140006707`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14000679a`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14000679a`
- `FLTMGR!FltReferenceContext` at `0x140006735`
- `FLTMGR!FltReferenceContext` at `0x140006735`
- `FLTMGR!FltReleaseContext` at `0x14000676f`
- `FLTMGR!FltReleaseContext` at `0x14000676f`

## pseudocode

```c
void __fastcall SqosDelayedJobQueueCompleteCanceledIo(__int64 a1, struct _FLT_CALLBACK_DATA *a2)
{
  PVOID v2; // rbx
  void *v4; // rsi
  union _SLIST_HEADER *v5; // rcx

  v2 = a2->QueueContext[0];
  v4 = *(void **)(*((_QWORD *)v2 + 4) + 8LL);
  *((_BYTE *)v2 + 132) = 1;
  *((LARGE_INTEGER *)v2 + 22) = KeQueryPerformanceCounter(0);
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = -1073741536;
  if ( *((_BYTE *)v2 + 128) )
  {
    FltReferenceContext(v4);
    v5 = (union _SLIST_HEADER *)(*(_QWORD *)(*((_QWORD *)v2 + 4) + 8LL) + 272LL);
    *((_BYTE *)v2 + 125) = 1;
    ExpInterlockedPushEntrySList(v5, (PSLIST_ENTRY)v2 + 4);
    SqospQueueDeviceTimer(v4);
    FltReleaseContext(v4);
  }
  else
  {
    _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)v2 + 5) + 520LL));
    SqospDestroyJob(v2);
    FltCompletePendedPreOperation(a2, FLT_PREOP_COMPLETE, 0);
  }
}

```

## disassembly

```asm
0x1400066e0  mov     [rsp+arg_0], rbx
0x1400066e5  mov     [rsp+arg_8], rsi
0x1400066ea  push    rdi
0x1400066eb  sub     rsp, 20h
0x1400066ef  mov     rbx, [rdx+40h]
0x1400066f3  xor     ecx, ecx; PerformanceFrequency
0x1400066f5  mov     rdi, rdx
0x1400066f8  mov     rax, [rbx+20h]
0x1400066fc  mov     rsi, [rax+8]
0x140006700  mov     byte ptr [rbx+84h], 1
0x140006707  call    cs:__imp_KeQueryPerformanceCounter
0x14000670e  nop     dword ptr [rax+rax+00h]
0x140006713  mov     [rbx+0B0h], rax
0x14000671a  mov     qword ptr [rdi+20h], 0
0x140006722  mov     dword ptr [rdi+18h], 0C0000120h
0x140006729  cmp     byte ptr [rbx+80h], 0
0x140006730  jz      short loc_14000677D
0x140006732  mov     rcx, rsi; Context
0x140006735  call    cs:__imp_FltReferenceContext
0x14000673c  nop     dword ptr [rax+rax+00h]
0x140006741  mov     rax, [rbx+20h]
0x140006745  lea     rdx, [rbx+40h]; ListEntry
0x140006749  mov     rcx, [rax+8]
0x14000674d  add     rcx, 110h; ListHead
0x140006754  mov     byte ptr [rbx+7Dh], 1
0x140006758  call    cs:__imp_ExpInterlockedPushEntrySList
0x14000675f  nop     dword ptr [rax+rax+00h]
0x140006764  mov     rcx, rsi; Context
0x140006767  call    SqospQueueDeviceTimer
0x14000676c  mov     rcx, rsi; Context
0x14000676f  call    cs:__imp_FltReleaseContext
0x140006776  nop     dword ptr [rax+rax+00h]
0x14000677b  jmp     short loc_1400067A6
0x14000677d  mov     rax, [rbx+28h]
0x140006781  mov     rcx, rbx; Entry
0x140006784  lock dec dword ptr [rax+208h]
0x14000678b  call    SqospDestroyJob
0x140006790  xor     r8d, r8d; Context
0x140006793  mov     rcx, rdi; CallbackData
0x140006796  lea     edx, [r8+4]; CallbackStatus
0x14000679a  call    cs:__imp_FltCompletePendedPreOperation
0x1400067a1  nop     dword ptr [rax+rax+00h]
0x1400067a6  mov     rbx, [rsp+28h+arg_0]
0x1400067ab  mov     rsi, [rsp+28h+arg_8]
0x1400067b0  add     rsp, 20h
0x1400067b4  pop     rdi
0x1400067b5  retn
```
