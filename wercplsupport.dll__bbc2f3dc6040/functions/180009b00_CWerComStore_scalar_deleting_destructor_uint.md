# CWerComStore::`scalar deleting destructor'(uint)

- ea: `0x180009b00`
- end: `0x180009b2f`
- name: `??_GCWerComStore@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(CWerComStore *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001674`
- `0x180009244`
- `0x180009b00`

## pseudocode

```c
CWerComStore *__fastcall CWerComStore::`scalar deleting destructor'(CWerComStore *this, char a2)
{
  CWerComStore::~CWerComStore(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009b00  mov     [rsp+arg_0], rbx
0x180009b05  push    rdi
0x180009b06  sub     rsp, 20h
0x180009b0a  mov     ebx, edx
0x180009b0c  mov     rdi, rcx
0x180009b0f  call    ??1CWerComStore@@UEAA@XZ; CWerComStore::~CWerComStore(void)
0x180009b14  test    bl, 1
0x180009b17  jz      short loc_180009B21
0x180009b19  mov     rcx, rdi; Block
0x180009b1c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009b21  mov     rbx, [rsp+28h+arg_0]
0x180009b26  mov     rax, rdi
0x180009b29  add     rsp, 20h
0x180009b2d  pop     rdi
0x180009b2e  retn
```
