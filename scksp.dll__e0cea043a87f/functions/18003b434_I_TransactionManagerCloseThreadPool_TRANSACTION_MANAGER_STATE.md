# I_TransactionManagerCloseThreadPool(_TRANSACTION_MANAGER_STATE *)

- ea: `0x18003b434`
- end: `0x18003b474`
- name: `?I_TransactionManagerCloseThreadPool@@YAKPEAU_TRANSACTION_MANAGER_STATE@@@Z`
- size: `64`
- prototype: `unsigned int __fastcall(struct _TRANSACTION_MANAGER_STATE *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180012d08`
- `0x18003b408`
- `0x18003b47c`
- `0x18003b9e0`

## callees

- `0x18003b434`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18003b44d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18003b44d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18003b457`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18003b457`

## pseudocode

```c
__int64 __fastcall I_TransactionManagerCloseThreadPool(struct _TRANSACTION_MANAGER_STATE *a1)
{
  struct _TP_CLEANUP_GROUP *v2; // rcx

  v2 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)a1 + 11);
  if ( v2 )
  {
    CloseThreadpoolCleanupGroupMembers(v2, 1, 0);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)a1 + 11));
    *((_QWORD *)a1 + 11) = 0;
  }
  *((_DWORD *)a1 + 24) = 0;
  return 0;
}

```

## disassembly

```asm
0x18003b434  push    rbx
0x18003b436  sub     rsp, 20h
0x18003b43a  mov     rbx, rcx
0x18003b43d  mov     rcx, [rcx+58h]; ptpcg
0x18003b441  test    rcx, rcx
0x18003b444  jz      short loc_18003B465
0x18003b446  xor     r8d, r8d; pvCleanupContext
0x18003b449  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18003b44d  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18003b453  mov     rcx, [rbx+58h]; ptpcg
0x18003b457  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18003b45d  mov     qword ptr [rbx+58h], 0
0x18003b465  mov     dword ptr [rbx+60h], 0
0x18003b46c  xor     eax, eax
0x18003b46e  add     rsp, 20h
0x18003b472  pop     rbx
0x18003b473  retn
```
