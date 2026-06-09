# URI_LOCK_LIST::QueryUriPath(void)

- ea: `0x180003af0`
- end: `0x180003af5`
- name: `?QueryUriPath@URI_LOCK_LIST@@UEAAPEBGXZ`
- size: `5`
- prototype: `const unsigned __int16 *__fastcall(URI_LOCK_LIST *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
const unsigned __int16 *__fastcall URI_LOCK_LIST::QueryUriPath(URI_LOCK_LIST *this)
{
  return (const unsigned __int16 *)*((_QWORD *)this + 7);
}

```

## disassembly

```asm
0x180003af0  mov     rax, [rcx+38h]
0x180003af4  retn
```
