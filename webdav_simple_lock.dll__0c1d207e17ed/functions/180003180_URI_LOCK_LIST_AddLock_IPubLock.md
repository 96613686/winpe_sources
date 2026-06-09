# URI_LOCK_LIST::AddLock(IPubLock *)

- ea: `0x180003180`
- end: `0x18000319c`
- name: `?AddLock@URI_LOCK_LIST@@UEAAJPEAVIPubLock@@@Z`
- size: `28`
- prototype: `__int64 __fastcall(URI_LOCK_LIST *__hidden this, struct IPubLock *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003058`

## pseudocode

```c
__int64 __fastcall URI_LOCK_LIST::AddLock(URI_LOCK_LIST *this, struct IPubLock *a2)
{
  struct LOCK_ENTRY *v3; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  return URI_LOCK_LIST::AddLock2(this, a2, &v3);
}

```

## disassembly

```asm
0x180003180  sub     rsp, 28h
0x180003184  lea     r8, [rsp+28h+arg_10]; struct LOCK_ENTRY **
0x180003189  mov     [rsp+28h+arg_10], 0
0x180003192  call    ?AddLock2@URI_LOCK_LIST@@QEAAJPEAVIPubLock@@PEAPEAULOCK_ENTRY@@@Z; URI_LOCK_LIST::AddLock2(IPubLock *,LOCK_ENTRY * *)
0x180003197  add     rsp, 28h
0x18000319b  retn
```
