# I_TransactionManagerCancelTimer(_CARD_STATE *)

- ea: `0x18003b388`
- end: `0x18003b402`
- name: `?I_TransactionManagerCancelTimer@@YAKPEAU_CARD_STATE@@@Z`
- size: `122`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18003b788`
- `0x18003b858`

## callees

- `0x18003ae44`
- `0x18003aec8`
- `0x18003b388`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003b3e1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003b3e1`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18003b3a7`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18003b3a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003b3c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003b3c0`

## pseudocode

```c
__int64 __fastcall I_TransactionManagerCancelTimer(PTP_TIMER *a1)
{
  unsigned int v1; // ebx

  v1 = 0;
  if ( a1[75] )
  {
    do
    {
      if ( !IsThreadpoolTimerSet(a1[75]) )
        break;
      SetThreadpoolTimer(a1[75], 0, 0, 0);
      CspLeaveCriticalSection(a1 + 78);
      WaitForThreadpoolTimerCallbacks(a1[75], 1);
      v1 = CspEnterCriticalSection(a1 + 78);
    }
    while ( !v1 );
  }
  return v1;
}

```

## disassembly

```asm
0x18003b388  mov     [rsp+arg_0], rbx
0x18003b38d  push    rdi
0x18003b38e  sub     rsp, 20h
0x18003b392  xor     ebx, ebx
0x18003b394  mov     rdi, rcx
0x18003b397  cmp     [rcx+258h], rbx
0x18003b39e  jz      short loc_18003B3F5
0x18003b3a0  mov     rcx, [rdi+258h]; pti
0x18003b3a7  call    cs:__imp_IsThreadpoolTimerSet
0x18003b3ad  test    eax, eax
0x18003b3af  jz      short loc_18003B3F5
0x18003b3b1  mov     rcx, [rdi+258h]; pti
0x18003b3b8  xor     r9d, r9d; msWindowLength
0x18003b3bb  xor     r8d, r8d; msPeriod
0x18003b3be  xor     edx, edx; pftDueTime
0x18003b3c0  call    cs:__imp_SetThreadpoolTimer
0x18003b3c6  lea     rbx, [rdi+270h]
0x18003b3cd  mov     rcx, rbx
0x18003b3d0  call    CspLeaveCriticalSection
0x18003b3d5  mov     rcx, [rdi+258h]; pti
0x18003b3dc  mov     edx, 1; fCancelPendingCallbacks
0x18003b3e1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003b3e7  mov     rcx, rbx
0x18003b3ea  call    CspEnterCriticalSection
0x18003b3ef  mov     ebx, eax
0x18003b3f1  test    eax, eax
0x18003b3f3  jz      short loc_18003B3A0
0x18003b3f5  mov     eax, ebx
0x18003b3f7  mov     rbx, [rsp+28h+arg_0]
0x18003b3fc  add     rsp, 20h
0x18003b400  pop     rdi
0x18003b401  retn
```
