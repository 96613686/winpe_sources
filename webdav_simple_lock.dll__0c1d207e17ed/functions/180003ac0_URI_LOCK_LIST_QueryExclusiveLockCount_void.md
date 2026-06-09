# URI_LOCK_LIST::QueryExclusiveLockCount(void)

- ea: `0x180003ac0`
- end: `0x180003ac7`
- name: `?QueryExclusiveLockCount@URI_LOCK_LIST@@UEAAKXZ`
- size: `7`
- prototype: `unsigned int __fastcall(URI_LOCK_LIST *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall URI_LOCK_LIST::QueryExclusiveLockCount(URI_LOCK_LIST *this)
{
  return *((unsigned int *)this + 186);
}

```

## disassembly

```asm
0x180003ac0  mov     eax, [rcx+2E8h]
0x180003ac6  retn
```
