# LOCK_SET::FindChild(ushort const *)

- ea: `0x180003530`
- end: `0x180003552`
- name: `?FindChild@LOCK_SET@@UEAAPEAVIPubUriLockList@@PEBG@Z`
- size: `34`
- prototype: `struct IPubUriLockList *__fastcall(LOCK_SET *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003614`

## pseudocode

```c
struct IPubUriLockList *__fastcall LOCK_SET::FindChild(LOCK_SET *this, wchar_t *a2)
{
  struct STATIC_WSTRING_HASH_RECORD *Key; // rax

  Key = STATIC_WSTRING_HASH::FindKey((LOCK_SET *)((char *)this + 1832), a2);
  return (struct IPubUriLockList *)(((unsigned __int64)Key - 32) & -(__int64)(Key != 0));
}

```

## disassembly

```asm
0x180003530  sub     rsp, 28h
0x180003534  add     rcx, 728h; this
0x18000353b  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180003540  lea     rcx, [rax-20h]
0x180003544  neg     rax
0x180003547  sbb     rax, rax
0x18000354a  and     rax, rcx
0x18000354d  add     rsp, 28h
0x180003551  retn
```
