# URI_LOCK_LIST::QueryUserData(void)

- ea: `0x180003b00`
- end: `0x180003b08`
- name: `?QueryUserData@URI_LOCK_LIST@@UEBA_KXZ`
- size: `8`
- prototype: `unsigned __int64 __fastcall(URI_LOCK_LIST *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
unsigned __int64 __fastcall URI_LOCK_LIST::QueryUserData(URI_LOCK_LIST *this)
{
  return *((_QWORD *)this + 95);
}

```

## disassembly

```asm
0x180003b00  mov     rax, [rcx+2F8h]
0x180003b07  retn
```
