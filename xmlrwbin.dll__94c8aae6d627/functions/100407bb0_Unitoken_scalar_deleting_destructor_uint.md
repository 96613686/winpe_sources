# Unitoken::`scalar deleting destructor'(uint)

- ea: `0x100407bb0`
- end: `0x100407be4`
- name: `??_GUnitoken@@QEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(Unitoken *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100410010`

## callees

- `0x100407330`
- `0x100407bb0`
- `0x100423a8c`

## pseudocode

```c
Unitoken *__fastcall Unitoken::`scalar deleting destructor'(Unitoken *this, char a2)
{
  WriterHandleEntry::~WriterHandleEntry(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x100407bb0  mov     [rsp+arg_0], rbx
0x100407bb5  push    rdi
0x100407bb6  sub     rsp, 20h
0x100407bba  mov     ebx, edx
0x100407bbc  mov     rdi, rcx
0x100407bbf  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x100407bc4  test    bl, 1
0x100407bc7  jz      short loc_100407BD6
0x100407bc9  mov     edx, 28h ; '('; unsigned __int64
0x100407bce  mov     rcx, rdi; void *
0x100407bd1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100407bd6  mov     rbx, [rsp+28h+arg_0]
0x100407bdb  mov     rax, rdi
0x100407bde  add     rsp, 20h
0x100407be2  pop     rdi
0x100407be3  retn
```
