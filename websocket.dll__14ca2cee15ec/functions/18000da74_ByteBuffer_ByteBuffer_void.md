# ByteBuffer::~ByteBuffer(void)

- ea: `0x18000da74`
- end: `0x18000daa6`
- name: `??1ByteBuffer@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(ByteBuffer *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ba64`
- `0x18000c7c0`
- `0x18000caf0`
- `0x18000cb8c`

## callees

- `0x180001274`
- `0x18000da74`

## pseudocode

```c
void __fastcall ByteBuffer::~ByteBuffer(ByteBuffer *this)
{
  void *v2; // rcx

  v2 = *(void **)this;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)this = 0;
  }
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x18000da74  push    rbx
0x18000da76  sub     rsp, 20h
0x18000da7a  mov     rbx, rcx
0x18000da7d  mov     rcx, [rcx]; Block
0x18000da80  test    rcx, rcx
0x18000da83  jz      short loc_18000DA91
0x18000da85  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000da8a  mov     qword ptr [rbx], 0
0x18000da91  mov     qword ptr [rbx+8], 0
0x18000da99  mov     dword ptr [rbx+10h], 0
0x18000daa0  add     rsp, 20h
0x18000daa4  pop     rbx
0x18000daa5  retn
```
