# LOCK_SET::FindParent(ushort const *)

- ea: `0x1800039e0`
- end: `0x180003a02`
- name: `?FindParent@LOCK_SET@@UEAAPEAVIPubUriLockList@@PEBG@Z`
- size: `34`
- prototype: `struct IPubUriLockList *__fastcall(LOCK_SET *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003614`

## pseudocode

```c
struct IPubUriLockList *__fastcall LOCK_SET::FindParent(LOCK_SET *this, wchar_t *a2)
{
  struct STATIC_WSTRING_HASH_RECORD *Key; // rax

  Key = STATIC_WSTRING_HASH::FindKey((LOCK_SET *)((char *)this + 776), a2);
  return (struct IPubUriLockList *)(((unsigned __int64)Key - 8) & -(__int64)(Key != 0));
}

```

## disassembly

```asm
0x1800039e0  sub     rsp, 28h
0x1800039e4  add     rcx, 308h; this
0x1800039eb  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x1800039f0  lea     rcx, [rax-8]
0x1800039f4  neg     rax
0x1800039f7  sbb     rax, rax
0x1800039fa  and     rax, rcx
0x1800039fd  add     rsp, 28h
0x180003a01  retn
```
