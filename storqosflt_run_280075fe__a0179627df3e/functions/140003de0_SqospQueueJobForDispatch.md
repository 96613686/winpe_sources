# SqospQueueJobForDispatch

- ea: `0x140003de0`
- end: `0x140003ead`
- name: `SqospQueueJobForDispatch`
- size: `205`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002790`
- `0x140002a30`
- `0x140004d44`
- `0x140006e98`

## callees

- `0x140002bf0`
- `0x140003de0`

## import_xrefs

- `ntoskrnl!ExTryQueueWorkItem` at `0x140003e7a`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140003e7a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140003e1d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140003e1d`
- `ntoskrnl!KeInsertQueue` at `0x140003e95`
- `ntoskrnl!KeInsertQueue` at `0x140003e95`

## pseudocode

```c
int __fastcall SqospQueueJobForDispatch(__int64 a1, __int64 a2)
{
  union _SLIST_HEADER *v4; // rcx
  signed __int64 v5; // rax
  signed __int64 *v6; // r8
  unsigned __int64 *v7; // rbx
  signed __int64 v8; // rcx
  struct _LIST_ENTRY *v9; // rbx

  if ( *(_BYTE *)(a1 + 128) || !BalanceUpdateStatsForStartingJob(a1) )
  {
    v6 = (signed __int64 *)(*(_QWORD *)(*(_QWORD *)(a2 + 8) + 80LL)
                          + ((unsigned __int64)*(unsigned int *)(a1 + 120) << 6));
    v7 = (unsigned __int64 *)(a1 + 112);
    _m_prefetchw(v6);
    v5 = *v6;
    do
    {
      *v7 = v5 & 0xFFFFFFFFFFFFFFFEuLL;
      v8 = v5;
      v5 = _InterlockedCompareExchange64(v6, (signed __int64)v7, v5);
    }
    while ( v5 != v8 );
    if ( !v5 )
    {
      if ( *(signed __int64 **)(a2 + 16) == v6 )
      {
        *(_BYTE *)(a2 + 26) = 1;
      }
      else
      {
        v9 = (struct _LIST_ENTRY *)(v6 + 1);
        LODWORD(v5) = ExTryQueueWorkItem(v6 + 1, 1);
        if ( !(_BYTE)v5 )
          LODWORD(v5) = KeInsertQueue((PRKQUEUE)(*(_QWORD *)(a2 + 8) + 8LL), v9);
      }
    }
  }
  else
  {
    *(_BYTE *)(a2 + 25) = 1;
    v4 = (union _SLIST_HEADER *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 8LL) + 256LL);
    *(_BYTE *)(a1 + 124) = 1;
    LODWORD(v5) = (unsigned int)ExpInterlockedPushEntrySList(v4, (PSLIST_ENTRY)(a1 + 48));
  }
  return v5;
}

```

## disassembly

```asm
0x140003de0  mov     [rsp+arg_0], rbx
0x140003de5  push    rdi
0x140003de6  sub     rsp, 20h
0x140003dea  cmp     byte ptr [rcx+80h], 0
0x140003df1  mov     rdi, rdx
0x140003df4  mov     rbx, rcx
0x140003df7  jnz     short loc_140003E2B
0x140003df9  call    BalanceUpdateStatsForStartingJob
0x140003dfe  test    al, al
0x140003e00  jz      short loc_140003E2B
0x140003e02  mov     byte ptr [rdi+19h], 1
0x140003e06  lea     rdx, [rbx+30h]; ListEntry
0x140003e0a  mov     rax, [rbx+20h]
0x140003e0e  mov     rcx, [rax+8]
0x140003e12  add     rcx, 100h; ListHead
0x140003e19  mov     byte ptr [rbx+7Ch], 1
0x140003e1d  call    cs:__imp_ExpInterlockedPushEntrySList
0x140003e24  nop     dword ptr [rax+rax+00h]
0x140003e29  jmp     short loc_140003EA1
0x140003e2b  mov     r8d, [rbx+78h]
0x140003e2f  mov     rax, [rdi+8]
0x140003e33  shl     r8, 6
0x140003e37  add     r8, [rax+50h]
0x140003e3b  add     rbx, 70h ; 'p'
0x140003e3f  prefetchw byte ptr [r8]
0x140003e43  mov     rax, [r8]
0x140003e46  mov     rcx, rax
0x140003e49  and     rcx, 0FFFFFFFFFFFFFFFEh
0x140003e4d  mov     [rbx], rcx
0x140003e50  mov     rcx, rax
0x140003e53  lock cmpxchg [r8], rbx
0x140003e58  cmp     rax, rcx
0x140003e5b  jnz     short loc_140003E46
0x140003e5d  test    rax, rax
0x140003e60  jnz     short loc_140003EA1
0x140003e62  cmp     [rdi+10h], r8
0x140003e66  jnz     short loc_140003E6E
0x140003e68  mov     byte ptr [rdi+1Ah], 1
0x140003e6c  jmp     short loc_140003EA1
0x140003e6e  lea     rbx, [r8+8]
0x140003e72  mov     edx, 1
0x140003e77  mov     rcx, rbx
0x140003e7a  call    cs:__imp_ExTryQueueWorkItem
0x140003e81  nop     dword ptr [rax+rax+00h]
0x140003e86  test    al, al
0x140003e88  jnz     short loc_140003EA1
0x140003e8a  mov     rcx, [rdi+8]
0x140003e8e  mov     rdx, rbx; Entry
0x140003e91  add     rcx, 8; Queue
0x140003e95  call    cs:__imp_KeInsertQueue
0x140003e9c  nop     dword ptr [rax+rax+00h]
0x140003ea1  mov     rbx, [rsp+28h+arg_0]
0x140003ea6  add     rsp, 20h
0x140003eaa  pop     rdi
0x140003eab  retn
```
