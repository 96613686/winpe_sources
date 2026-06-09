# URI_LOCK_LIST::FindFirstLock(CPubIterator *)

- ea: `0x1800035b0`
- end: `0x1800035ca`
- name: `?FindFirstLock@URI_LOCK_LIST@@UEAAPEAVIPubLock@@PEAVCPubIterator@@@Z`
- size: `26`
- prototype: `struct IPubLock *__fastcall(URI_LOCK_LIST *__hidden this, struct CPubIterator *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004010`

## pseudocode

```c
struct IPubLock *__fastcall URI_LOCK_LIST::FindFirstLock(URI_LOCK_LIST *this, struct CPubIterator *a2)
{
  *((_DWORD *)a2 + 2) = 0;
  *(_QWORD *)a2 = (char *)this + 80;
  return (struct IPubLock *)(*(__int64 (__fastcall **)(URI_LOCK_LIST *))(*(_QWORD *)this + 40LL))(this);
}

```

## disassembly

```asm
0x1800035b0  lea     rax, [rcx+50h]
0x1800035b4  mov     dword ptr [rdx+8], 0
0x1800035bb  mov     [rdx], rax
0x1800035be  mov     rax, [rcx]
0x1800035c1  mov     rax, [rax+28h]
0x1800035c5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
