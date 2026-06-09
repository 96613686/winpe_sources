# LOCK_SET::QueryUriLockList(void)

- ea: `0x180003ae0`
- end: `0x180003ae5`
- name: `?QueryUriLockList@LOCK_SET@@UEAAPEAVIPubUriLockList@@XZ`
- size: `5`
- prototype: `struct IPubUriLockList *__fastcall(LOCK_SET *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
struct IPubUriLockList *__fastcall LOCK_SET::QueryUriLockList(LOCK_SET *this)
{
  return (LOCK_SET *)((char *)this + 8);
}

```

## disassembly

```asm
0x180003ae0  lea     rax, [rcx+8]
0x180003ae4  retn
```
