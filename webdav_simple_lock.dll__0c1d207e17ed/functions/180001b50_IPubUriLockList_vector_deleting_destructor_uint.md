# IPubUriLockList::`vector deleting destructor'(uint)

- ea: `0x180001b50`
- end: `0x180001b76`
- name: `??_EIPubUriLockList@@UEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(IPubUriLockList *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x180001b50`

## pseudocode

```c
IPubUriLockList *__fastcall IPubUriLockList::`vector deleting destructor'(IPubUriLockList *this, char a2)
{
  *(_QWORD *)this = &IPubUriLockList::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001b50  push    rbx
0x180001b52  sub     rsp, 20h
0x180001b56  lea     rax, ??_7IPubUriLockList@@6B@; const IPubUriLockList::`vftable'
0x180001b5d  mov     rbx, rcx
0x180001b60  mov     [rcx], rax
0x180001b63  test    dl, 1
0x180001b66  jz      short loc_180001B6D
0x180001b68  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001b6d  mov     rax, rbx
0x180001b70  add     rsp, 20h
0x180001b74  pop     rbx
0x180001b75  retn
```
