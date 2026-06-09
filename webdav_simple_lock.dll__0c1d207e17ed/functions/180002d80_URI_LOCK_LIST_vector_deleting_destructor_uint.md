# URI_LOCK_LIST::`vector deleting destructor'(uint)

- ea: `0x180002d80`
- end: `0x180002daf`
- name: `??_EURI_LOCK_LIST@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(URI_LOCK_LIST *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x180002c28`
- `0x180002d80`

## pseudocode

```c
URI_LOCK_LIST *__fastcall URI_LOCK_LIST::`vector deleting destructor'(URI_LOCK_LIST *this, char a2)
{
  URI_LOCK_LIST::~URI_LOCK_LIST(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002d80  mov     [rsp+arg_0], rbx
0x180002d85  push    rdi
0x180002d86  sub     rsp, 20h
0x180002d8a  mov     ebx, edx
0x180002d8c  mov     rdi, rcx
0x180002d8f  call    ??1URI_LOCK_LIST@@UEAA@XZ; URI_LOCK_LIST::~URI_LOCK_LIST(void)
0x180002d94  test    bl, 1
0x180002d97  jz      short loc_180002DA1
0x180002d99  mov     rcx, rdi; Block
0x180002d9c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002da1  mov     rbx, [rsp+28h+arg_0]
0x180002da6  mov     rax, rdi
0x180002da9  add     rsp, 20h
0x180002dad  pop     rdi
0x180002dae  retn
```
