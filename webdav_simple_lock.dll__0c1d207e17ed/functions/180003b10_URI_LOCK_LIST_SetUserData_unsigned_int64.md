# URI_LOCK_LIST::SetUserData(unsigned __int64)

- ea: `0x180003b10`
- end: `0x180003b1f`
- name: `?SetUserData@URI_LOCK_LIST@@UEAA_K_K@Z`
- size: `15`
- prototype: `unsigned __int64 __fastcall(URI_LOCK_LIST *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
unsigned __int64 __fastcall URI_LOCK_LIST::SetUserData(URI_LOCK_LIST *this, __int64 a2)
{
  unsigned __int64 result; // rax

  result = *((_QWORD *)this + 95);
  *((_QWORD *)this + 95) = a2;
  return result;
}

```

## disassembly

```asm
0x180003b10  mov     rax, [rcx+2F8h]
0x180003b17  mov     [rcx+2F8h], rdx
0x180003b1e  retn
```
