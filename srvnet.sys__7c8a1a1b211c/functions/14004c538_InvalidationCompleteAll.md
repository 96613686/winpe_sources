# InvalidationCompleteAll

- ea: `0x14004c538`
- end: `0x14004c665`
- name: `InvalidationCompleteAll`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004c670`

## callees

- `0x140007ec0`
- `0x1400146a4`
- `0x140016cc8`
- `0x140029724`
- `0x14004c538`
- `0x14004ca10`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004c5b3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004c625`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004c5b3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004c625`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004c5d2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004c5d2`
- `ntoskrnl!IoFreeWorkItem` at `0x14004c640`
- `ntoskrnl!IoFreeWorkItem` at `0x14004c640`

## pseudocode

```c
__int64 __fastcall InvalidationCompleteAll(__int64 a1)
{
  int v2; // r8d
  unsigned int v3; // ebx
  __int64 v4; // r8
  _QWORD *matched; // rax
  _QWORD *v6; // rsi
  __int64 v7; // rbx
  int v9; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(_DWORD *)(*(_QWORD *)(a1 + 128) + 32LL);
  v9 = v2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_65854c2b783f3b66712a66400b9887aa_Traceguids, a1, v2);
  }
  while ( 1 )
  {
    ExAcquirePushLockExclusiveEx(&NodeInfo, 0);
    matched = (_QWORD *)RfsHashTableBucketLookupMatchEntry(SrvNodeTasksTable, &v9, v4, 0);
    v6 = matched;
    if ( !matched )
      break;
    RfsHashTableRemove((__int64)SrvNodeTasksTable, matched, (__int64)&v9, 1u);
    v3 = *(_DWORD *)(a1 + 112);
    ExReleasePushLockExclusiveEx(&NodeInfo, 0);
    ReplyToRequestor(v6, v3);
  }
  v7 = *(_QWORD *)(a1 + 128);
  RfsHashTableRemove((__int64)SrvNodeActiveTasksTable, (_QWORD *)(a1 + 96), (__int64)&v9, 1u);
  ExReleasePushLockExclusiveEx(&NodeInfo, 0);
  ReplyToRequestor(v7, *(unsigned int *)(a1 + 112));
  IoFreeWorkItem(*(PIO_WORKITEM *)(a1 + 120));
  return SrvNetWskNotifyCleanupProviderContext(a1);
}

```

## disassembly

```asm
0x14004c538  mov     r11, rsp
0x14004c53b  mov     [r11+10h], rbx
0x14004c53f  mov     [r11+18h], rsi
0x14004c543  push    rdi
0x14004c544  sub     rsp, 30h
0x14004c548  mov     rax, [rcx+80h]
0x14004c54f  mov     rdi, rcx
0x14004c552  mov     r8d, [rax+20h]
0x14004c556  mov     [r11+8], r8d
0x14004c55a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004c561  lea     rax, WPP_GLOBAL_Control
0x14004c568  cmp     rcx, rax
0x14004c56b  jz      short loc_14004C5C9
0x14004c56d  mov     eax, [rcx+2Ch]
0x14004c570  test    al, 20h
0x14004c572  jz      short loc_14004C5C9
0x14004c574  cmp     byte ptr [rcx+29h], 4
0x14004c578  jb      short loc_14004C5C9
0x14004c57a  mov     rcx, [rcx+18h]
0x14004c57e  mov     edx, 12h
0x14004c583  mov     [r11-18h], r8d
0x14004c587  mov     r9, rdi
0x14004c58a  lea     r8, WPP_65854c2b783f3b66712a66400b9887aa_Traceguids
0x14004c591  call    WPP_SF_qD
0x14004c596  jmp     short loc_14004C5C9
0x14004c598  mov     rcx, cs:SrvNodeTasksTable
0x14004c59f  mov     rdx, rsi
0x14004c5a2  call    RfsHashTableRemove
0x14004c5a7  mov     ebx, [rdi+70h]
0x14004c5aa  lea     rcx, NodeInfo
0x14004c5b1  xor     edx, edx
0x14004c5b3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14004c5ba  nop     dword ptr [rax+rax+00h]
0x14004c5bf  mov     edx, ebx
0x14004c5c1  mov     rcx, rsi
0x14004c5c4  call    ReplyToRequestor
0x14004c5c9  xor     edx, edx
0x14004c5cb  lea     rcx, NodeInfo
0x14004c5d2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14004c5d9  nop     dword ptr [rax+rax+00h]
0x14004c5de  mov     rcx, cs:SrvNodeTasksTable
0x14004c5e5  lea     rdx, [rsp+38h+arg_0]
0x14004c5ea  xor     r9d, r9d
0x14004c5ed  call    RfsHashTableBucketLookupMatchEntry
0x14004c5f2  lea     r8, [rsp+38h+arg_0]
0x14004c5f7  mov     rsi, rax
0x14004c5fa  mov     r9d, 1
0x14004c600  test    rax, rax
0x14004c603  jnz     short loc_14004C598
0x14004c605  mov     rcx, cs:SrvNodeActiveTasksTable
0x14004c60c  lea     rdx, [rdi+60h]
0x14004c610  mov     rbx, [rdi+80h]
0x14004c617  call    RfsHashTableRemove
0x14004c61c  xor     edx, edx
0x14004c61e  lea     rcx, NodeInfo
0x14004c625  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14004c62c  nop     dword ptr [rax+rax+00h]
0x14004c631  mov     edx, [rdi+70h]
0x14004c634  mov     rcx, rbx
0x14004c637  call    ReplyToRequestor
0x14004c63c  mov     rcx, [rdi+78h]; IoWorkItem
0x14004c640  call    cs:__imp_IoFreeWorkItem
0x14004c647  nop     dword ptr [rax+rax+00h]
0x14004c64c  mov     rcx, rdi
0x14004c64f  call    SrvNetWskNotifyCleanupProviderContext
0x14004c654  mov     rbx, [rsp+38h+arg_8]
0x14004c659  mov     rsi, [rsp+38h+arg_10]
0x14004c65e  add     rsp, 30h
0x14004c662  pop     rdi
0x14004c663  retn
```
