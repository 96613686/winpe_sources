# I_TransactionManagerInitializeThreadPool(_TRANSACTION_MANAGER_STATE *)

- ea: `0x18003b47c`
- end: `0x18003b520`
- name: `?I_TransactionManagerInitializeThreadPool@@YAKPEAU_TRANSACTION_MANAGER_STATE@@@Z`
- size: `164`
- prototype: `unsigned int __fastcall(struct _TRANSACTION_MANAGER_STATE *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003b9e0`

## callees

- `0x18003b434`
- `0x18003b47c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b4e8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18003b4d9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18003b4d9`

## pseudocode

```c
__int64 __fastcall I_TransactionManagerInitializeThreadPool(struct _TRANSACTION_MANAGER_STATE *a1)
{
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  DWORD LastError; // edi
  void *v4; // rcx

  *((_DWORD *)a1 + 4) = 3;
  *((_DWORD *)a1 + 19) = 1;
  *((_QWORD *)a1 + 3) = 0;
  *((_QWORD *)a1 + 4) = 0;
  *((_QWORD *)a1 + 5) = 0;
  *((_QWORD *)a1 + 6) = 0;
  *((_QWORD *)a1 + 7) = 0;
  *((_QWORD *)a1 + 8) = 0;
  *((_DWORD *)a1 + 18) = 0;
  *((_DWORD *)a1 + 20) = 72;
  *((_DWORD *)a1 + 24) = 1;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)a1 + 11) = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    v4 = g_hInst;
    LastError = 0;
    *((_QWORD *)a1 + 5) = 0;
    *((_QWORD *)a1 + 4) = ThreadpoolCleanupGroup;
    *((_QWORD *)a1 + 6) = v4;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
      I_TransactionManagerCloseThreadPool(a1);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003b47c  mov     [rsp+arg_0], rbx
0x18003b481  push    rdi
0x18003b482  sub     rsp, 20h
0x18003b486  mov     eax, 1
0x18003b48b  mov     dword ptr [rcx+10h], 3
0x18003b492  mov     [rcx+4Ch], eax
0x18003b495  mov     rbx, rcx
0x18003b498  mov     qword ptr [rcx+18h], 0
0x18003b4a0  mov     qword ptr [rcx+20h], 0
0x18003b4a8  mov     qword ptr [rcx+28h], 0
0x18003b4b0  mov     qword ptr [rcx+30h], 0
0x18003b4b8  mov     qword ptr [rcx+38h], 0
0x18003b4c0  mov     qword ptr [rcx+40h], 0
0x18003b4c8  mov     dword ptr [rcx+48h], 0
0x18003b4cf  mov     dword ptr [rcx+50h], 48h ; 'H'
0x18003b4d6  mov     [rcx+60h], eax
0x18003b4d9  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18003b4df  mov     [rbx+58h], rax
0x18003b4e3  test    rax, rax
0x18003b4e6  jnz     short loc_18003B4FE
0x18003b4e8  call    cs:__imp_GetLastError
0x18003b4ee  mov     edi, eax
0x18003b4f0  test    eax, eax
0x18003b4f2  jz      short loc_18003B513
0x18003b4f4  mov     rcx, rbx; struct _TRANSACTION_MANAGER_STATE *
0x18003b4f7  call    ?I_TransactionManagerCloseThreadPool@@YAKPEAU_TRANSACTION_MANAGER_STATE@@@Z; I_TransactionManagerCloseThreadPool(_TRANSACTION_MANAGER_STATE *)
0x18003b4fc  jmp     short loc_18003B513
0x18003b4fe  mov     rcx, cs:?g_hInst@@3PEAXEA; void * g_hInst
0x18003b505  xor     edi, edi
0x18003b507  mov     [rbx+28h], rdi
0x18003b50b  mov     [rbx+20h], rax
0x18003b50f  mov     [rbx+30h], rcx
0x18003b513  mov     rbx, [rsp+28h+arg_0]
0x18003b518  mov     eax, edi
0x18003b51a  add     rsp, 20h
0x18003b51e  pop     rdi
0x18003b51f  retn
```
