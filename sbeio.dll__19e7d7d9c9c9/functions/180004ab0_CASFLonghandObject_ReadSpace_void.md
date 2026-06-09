# CASFLonghandObject::ReadSpace(void)

- ea: `0x180004ab0`
- end: `0x180004ab5`
- name: `?ReadSpace@CASFLonghandObject@@UEAA_KXZ`
- size: `5`
- prototype: `unsigned __int64 __fastcall(CASFLonghandObject *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
unsigned __int64 __fastcall CASFLonghandObject::ReadSpace(CASFLonghandObject *this)
{
  return *((_QWORD *)this + 4);
}

```

## disassembly

```asm
0x180004ab0  mov     rax, [rcx+20h]
0x180004ab4  retn
```
