# URI_LOCK_LIST::QuerySharedLockCount(void)

- ea: `0x180003ad0`
- end: `0x180003ad7`
- name: `?QuerySharedLockCount@URI_LOCK_LIST@@UEAAKXZ`
- size: `7`
- prototype: `unsigned int __fastcall(URI_LOCK_LIST *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall URI_LOCK_LIST::QuerySharedLockCount(URI_LOCK_LIST *this)
{
  return *((unsigned int *)this + 187);
}

```

## disassembly

```asm
0x180003ad0  mov     eax, [rcx+2ECh]
0x180003ad6  retn
```
