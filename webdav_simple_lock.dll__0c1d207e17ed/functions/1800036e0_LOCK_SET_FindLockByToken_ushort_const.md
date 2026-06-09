# LOCK_SET::FindLockByToken(ushort const *)

- ea: `0x1800036e0`
- end: `0x180003707`
- name: `?FindLockByToken@LOCK_SET@@UEAAPEAVIPubLock@@PEBG@Z`
- size: `39`
- prototype: `struct IPubLock *__fastcall(LOCK_SET *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003614`
- `0x1800036e0`

## pseudocode

```c
struct IPubLock *__fastcall LOCK_SET::FindLockByToken(LOCK_SET *this, wchar_t *a2)
{
  struct STATIC_WSTRING_HASH_RECORD *Key; // rax
  struct IPubLock *result; // rax

  Key = STATIC_WSTRING_HASH::FindKey((LOCK_SET *)((char *)this + 3944), a2);
  result = (struct IPubLock *)(((unsigned __int64)Key - 16) & -(__int64)(Key != 0));
  if ( result )
    return *(struct IPubLock **)result;
  return result;
}

```

## disassembly

```asm
0x1800036e0  sub     rsp, 28h
0x1800036e4  add     rcx, 0F68h; this
0x1800036eb  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x1800036f0  lea     rcx, [rax-10h]
0x1800036f4  neg     rax
0x1800036f7  sbb     rax, rax
0x1800036fa  and     rax, rcx
0x1800036fd  jz      short loc_180003702
0x1800036ff  mov     rax, [rax]
0x180003702  add     rsp, 28h
0x180003706  retn
```
