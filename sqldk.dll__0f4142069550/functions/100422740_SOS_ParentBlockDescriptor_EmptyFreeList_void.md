# SOS_ParentBlockDescriptor::EmptyFreeList(void)

- ea: `0x100422740`
- end: `0x1004227b4`
- name: `?EmptyFreeList@SOS_ParentBlockDescriptor@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(SOS_ParentBlockDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1004226c0`

## callees

- `0x10040a8b0`
- `0x100422740`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x1004ac0e8`
- `KERNEL32!VirtualProtect` at `0x1004ac0e8`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ac109`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ac145`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ac177`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ac1b3`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ac109`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ac145`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ac177`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ac1b3`
- `KERNEL32!InterlockedPopEntrySList` at `0x100422797`
- `KERNEL32!InterlockedPopEntrySList` at `0x100422797`

## pseudocode

```c
void __fastcall SOS_ParentBlockDescriptor::EmptyFreeList(union _SLIST_HEADER *this)
{
  struct _SLIST_ENTRY *i; // rbx
  struct _SLIST_ENTRY *Next; // rax
  PSLIST_ENTRY v4; // rax
  struct _SLIST_ENTRY *Alignment; // rcx
  unsigned __int64 v6; // rbx
  DWORD flOldProtect; // [rsp+40h] [rbp+8h] BYREF

  for ( i = (struct _SLIST_ENTRY *)SOS_ParentBlockDescriptor::PopCommitted(this);
        i;
        i = (struct _SLIST_ENTRY *)SOS_ParentBlockDescriptor::PopCommitted(this) )
  {
    Next = i[1].Next;
    if ( Next != i )
    {
      Alignment = (struct _SLIST_ENTRY *)this[2].Alignment;
      if ( Next == Alignment && (SOS_Tracing_osTrace & 0x800) != 0 && LODWORD(i[3].Next) == 1 )
        VirtualProtect(Alignment, 0x1000u, 4u, &flOldProtect);
      _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)i & 0xFFFFFFFFFFFFE000uLL) + 8168));
      InterlockedPushEntrySList((PSLIST_HEADER)(((unsigned __int64)i & 0xFFFFFFFFFFFFE000uLL) + 8128), i);
      if ( *(_DWORD *)(((unsigned __int64)i & 0xFFFFFFFFFFFFE000uLL) + 0x1FF0) == 1
        && _InterlockedCompareExchange(
             (volatile signed __int32 *)(((unsigned __int64)i & 0xFFFFFFFFFFFFE000uLL) + 8176),
             2,
             1) == 1 )
      {
        InterlockedPushEntrySList(
          (PSLIST_HEADER)&qword_1007415C0[24
                                        * *(unsigned __int16 *)(((unsigned __int64)i & 0xFFFFFFFFFFFFE000uLL) + 0x1FEC)
                                        + 2
                                        * ((unsigned __int64)*(unsigned int *)(((unsigned __int64)i
                                                                              & 0xFFFFFFFFFFFFE000uLL)
                                                                             + 0x1FE8) >> 5)],
          (PSLIST_ENTRY)(((unsigned __int64)i & 0xFFFFFFFFFFFFE000uLL) + 8144));
      }
    }
  }
  while ( 1 )
  {
    v4 = InterlockedPopEntrySList(this + 8);
    if ( !v4 )
      break;
    if ( v4[1].Next != v4 )
    {
      v6 = ((unsigned __int64)v4 & 0xFFFFFFFFFFFFE000uLL) + 8128;
      _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)v4 & 0xFFFFFFFFFFFFE000uLL) + 8168));
      InterlockedPushEntrySList((PSLIST_HEADER)v6, v4);
      if ( *(_DWORD *)(v6 + 48) == 1 && _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 48), 2, 1) == 1 )
        InterlockedPushEntrySList(
          (PSLIST_HEADER)&qword_1007415C0[24 * *(unsigned __int16 *)(v6 + 44)
                                        + 2 * ((unsigned __int64)*(unsigned int *)(v6 + 40) >> 5)],
          (PSLIST_ENTRY)(v6 + 16));
    }
  }
}

```

## disassembly

```asm
0x100422740  mov     [rsp+arg_18], rbx
0x100422745  push    rbp
0x100422746  push    rsi
0x100422747  push    r14
0x100422749  sub     rsp, 20h
0x10042274d  mov     rsi, rcx
0x100422750  call    ?PopCommitted@SOS_ParentBlockDescriptor@@AEAAPEAVSOS_MemoryFreeBlock@@XZ; SOS_ParentBlockDescriptor::PopCommitted(void)
0x100422755  lea     r14, qword_1007415C0
0x10042275c  mov     rbx, rax
0x10042275f  mov     ebp, 2
0x100422764  test    rax, rax
0x100422767  jz      short loc_100422790
0x100422769  mov     [rsp+38h+arg_10], rdi
0x10042276e  mov     rax, [rbx+10h]
0x100422772  cmp     rax, rbx
0x100422775  jnz     loc_1004AC0BD
0x10042277b  mov     rcx, rsi; this
0x10042277e  call    ?PopCommitted@SOS_ParentBlockDescriptor@@AEAAPEAVSOS_MemoryFreeBlock@@XZ; SOS_ParentBlockDescriptor::PopCommitted(void)
0x100422783  mov     rbx, rax
0x100422786  test    rax, rax
0x100422789  jnz     short loc_10042276E
0x10042278b  mov     rdi, [rsp+38h+arg_10]
0x100422790  lea     rcx, [rsi+80h]; ListHead
0x100422797  call    cs:__imp_InterlockedPopEntrySList
0x10042279d  test    rax, rax
0x1004227a0  jnz     loc_1004AC152
0x1004227a6  mov     rbx, [rsp+38h+arg_18]
0x1004227ab  add     rsp, 20h
0x1004227af  pop     r14
0x1004227b1  pop     rsi
0x1004227b2  pop     rbp
0x1004227b3  retn
0x1004ac0bd  mov     rcx, [rsi+20h]; lpAddress
0x1004ac0c1  cmp     rax, rcx
0x1004ac0c4  jnz     short loc_1004AC0EE
0x1004ac0c6  test    cs:?SOS_Tracing_osTrace@@3KA, 800h; ulong SOS_Tracing_osTrace
0x1004ac0d0  jz      short loc_1004AC0EE
0x1004ac0d2  cmp     dword ptr [rbx+30h], 1
0x1004ac0d6  jnz     short loc_1004AC0EE
0x1004ac0d8  lea     r9, [rsp+38h+flOldProtect]; lpflOldProtect
0x1004ac0dd  mov     edx, 1000h; dwSize
0x1004ac0e2  mov     r8d, 4; flNewProtect
0x1004ac0e8  call    cs:__imp_VirtualProtect
0x1004ac0ee  mov     rdi, rbx
0x1004ac0f1  and     rdi, 0FFFFFFFFFFFFE000h
0x1004ac0f8  add     rdi, 1FC0h
0x1004ac0ff  lock inc dword ptr [rdi+28h]
0x1004ac103  mov     rdx, rbx; ListEntry
0x1004ac106  mov     rcx, rdi; ListHead
0x1004ac109  call    cs:__imp_InterlockedPushEntrySList
0x1004ac10f  mov     eax, [rdi+30h]
0x1004ac112  cmp     eax, 1
0x1004ac115  jnz     loc_10042277B
0x1004ac11b  lock cmpxchg [rdi+30h], ebp
0x1004ac120  jnz     loc_10042277B
0x1004ac126  mov     r8d, [rdi+28h]
0x1004ac12a  lea     rdx, [rdi+10h]; ListEntry
0x1004ac12e  movzx   eax, word ptr [rdi+2Ch]
0x1004ac132  shr     r8, 5
0x1004ac136  lea     rcx, [rax+rax*2]
0x1004ac13a  lea     rcx, [r8+rcx*4]
0x1004ac13e  shl     rcx, 4
0x1004ac142  add     rcx, r14; ListHead
0x1004ac145  call    cs:__imp_InterlockedPushEntrySList
0x1004ac14b  nop
0x1004ac14c  jmp     loc_10042277B
0x1004ac152  cmp     [rax+10h], rax
0x1004ac156  jz      loc_100422790
0x1004ac15c  mov     rbx, rax
0x1004ac15f  and     rbx, 0FFFFFFFFFFFFE000h
0x1004ac166  add     rbx, 1FC0h
0x1004ac16d  lock inc dword ptr [rbx+28h]
0x1004ac171  mov     rdx, rax; ListEntry
0x1004ac174  mov     rcx, rbx; ListHead
0x1004ac177  call    cs:__imp_InterlockedPushEntrySList
0x1004ac17d  mov     eax, [rbx+30h]
0x1004ac180  cmp     eax, 1
0x1004ac183  jnz     loc_100422790
0x1004ac189  lock cmpxchg [rbx+30h], ebp
0x1004ac18e  jnz     loc_100422790
0x1004ac194  mov     r8d, [rbx+28h]
0x1004ac198  lea     rdx, [rbx+10h]; ListEntry
0x1004ac19c  movzx   eax, word ptr [rbx+2Ch]
0x1004ac1a0  shr     r8, 5
0x1004ac1a4  lea     rcx, [rax+rax*2]
0x1004ac1a8  lea     rcx, [r8+rcx*4]
0x1004ac1ac  shl     rcx, 4
0x1004ac1b0  add     rcx, r14; ListHead
0x1004ac1b3  call    cs:__imp_InterlockedPushEntrySList
0x1004ac1b9  jmp     loc_100422790
```
